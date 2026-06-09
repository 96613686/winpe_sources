# CReaderWriterLock::_LockSpin(bool)

- ea: `0x18002ee40`
- end: `0x18002ef5d`
- name: `?_LockSpin@CReaderWriterLock@@AEAAX_N@Z`
- size: `285`
- prototype: `void __fastcall(CReaderWriterLock *this, char)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002cf0`
- `0x1800040c0`
- `0x180004e50`
- `0x180005250`
- `0x180005430`

## callees

- `0x18002eb74`
- `0x18002eb94`
- `0x18002ee40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ee62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ee62`

## pseudocode

```c
void __fastcall CReaderWriterLock::_LockSpin(CReaderWriterLock *this, char a2)
{
  DWORD v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // r8d
  bool v10; // zf
  signed __int32 v11; // edx
  char v12; // al

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock::sm_wDefaultSpinCount * *(double *)&qword_18004EB20[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      SwitchOrSleep(v3);
      v3 = SleepTime(v7);
      v8 = (int)((double)v8 * CReaderWriterLock::sm_dblDfltSpinAdjFctr);
      if ( v8 <= 10000 )
      {
        if ( v8 <= 100 )
          v8 = 100;
      }
      else
      {
        v8 = 10000;
      }
      v6 = CReaderWriterLock::sm_wDefaultSpinCount;
      ++v7;
      goto LABEL_2;
    }
    if ( a2 )
    {
      if ( !*(_DWORD *)this )
      {
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)this, -1, 0) == 0;
        goto LABEL_12;
      }
    }
    else if ( *(_DWORD *)this != -1 && !*((_DWORD *)this + 1) )
    {
      v11 = *(_DWORD *)this;
      v10 = v11 == _InterlockedCompareExchange((volatile signed __int32 *)this, v11 + 1, v11);
LABEL_12:
      v12 = 1;
      if ( v10 )
        goto LABEL_14;
    }
    v12 = 0;
LABEL_14:
    if ( v12 )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x18002ee40  mov     [rsp+arg_0], rbx
0x18002ee45  mov     [rsp+arg_10], rbp
0x18002ee4a  push    rsi
0x18002ee4b  push    rdi
0x18002ee4c  push    r13
0x18002ee4e  push    r14
0x18002ee50  push    r15
0x18002ee52  sub     rsp, 20h
0x18002ee56  xor     r15d, r15d
0x18002ee59  mov     r14b, dl
0x18002ee5c  mov     ebp, r15d
0x18002ee5f  mov     rdi, rcx
0x18002ee62  call    cs:__imp_GetCurrentThreadId
0x18002ee68  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock@@1GA; ushort CReaderWriterLock::sm_wDefaultSpinCount
0x18002ee6f  mov     esi, r15d
0x18002ee72  mov     r9d, eax
0x18002ee75  mov     eax, 4EC4EC4Fh
0x18002ee7a  mul     r9d
0x18002ee7d  movd    xmm0, ecx
0x18002ee81  cvtdq2pd xmm0, xmm0
0x18002ee85  shr     edx, 2
0x18002ee88  imul    r8d, edx, 0Dh
0x18002ee8c  lea     rdx, qword_18004EB20
0x18002ee93  sub     r9d, r8d
0x18002ee96  or      r13d, 0FFFFFFFFh
0x18002ee9a  mulsd   xmm0, qword ptr [rdx+r9*8]
0x18002eea0  cvttsd2si ebx, xmm0
0x18002eea4  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18002eeab  mov     r8d, ebx
0x18002eeae  jb      short loc_18002EEB5
0x18002eeb0  test    cx, cx
0x18002eeb3  jnz     short loc_18002EEBB
0x18002eeb5  mov     r8d, 1
0x18002eebb  sub     r8d, 1
0x18002eebf  js      short loc_18002EEFB
0x18002eec1  test    r14b, r14b
0x18002eec4  jz      short loc_18002EED3
0x18002eec6  mov     eax, [rdi]
0x18002eec8  test    eax, eax
0x18002eeca  jnz     short loc_18002EEF0
0x18002eecc  lock cmpxchg [rdi], r13d
0x18002eed1  jmp     short loc_18002EEEC
0x18002eed3  mov     edx, [rdi]
0x18002eed5  cmp     edx, r13d
0x18002eed8  jz      short loc_18002EEF0
0x18002eeda  mov     eax, [rdi+4]
0x18002eedd  test    eax, eax
0x18002eedf  jnz     short loc_18002EEF0
0x18002eee1  lea     ecx, [rdx+1]
0x18002eee4  mov     eax, edx
0x18002eee6  lock cmpxchg [rdi], ecx
0x18002eeea  cmp     edx, eax
0x18002eeec  mov     al, 1
0x18002eeee  jz      short loc_18002EEF3
0x18002eef0  mov     al, r15b
0x18002eef3  test    al, al
0x18002eef5  jnz     short loc_18002EF46
0x18002eef7  pause
0x18002eef9  jmp     short loc_18002EEBB
0x18002eefb  mov     ecx, ebp; dwMilliseconds
0x18002eefd  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18002ef02  mov     ecx, esi; unsigned int
0x18002ef04  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18002ef09  movd    xmm0, ebx
0x18002ef0d  mov     ebp, eax
0x18002ef0f  cvtdq2pd xmm0, xmm0
0x18002ef13  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock@@1NA; double CReaderWriterLock::sm_dblDfltSpinAdjFctr
0x18002ef1b  cvttsd2si ebx, xmm0
0x18002ef1f  cmp     ebx, 2710h
0x18002ef25  jle     short loc_18002EF2E
0x18002ef27  mov     ebx, 2710h
0x18002ef2c  jmp     short loc_18002EF38
0x18002ef2e  mov     eax, 64h ; 'd'
0x18002ef33  cmp     ebx, eax
0x18002ef35  cmovle  ebx, eax
0x18002ef38  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock@@1GA; ushort CReaderWriterLock::sm_wDefaultSpinCount
0x18002ef3f  inc     esi
0x18002ef41  jmp     loc_18002EEA4
0x18002ef46  mov     rbx, [rsp+48h+arg_0]
0x18002ef4b  mov     rbp, [rsp+48h+arg_10]
0x18002ef50  add     rsp, 20h
0x18002ef54  pop     r15
0x18002ef56  pop     r14
0x18002ef58  pop     r13
0x18002ef5a  pop     rdi
0x18002ef5b  pop     rsi
0x18002ef5c  retn
```
