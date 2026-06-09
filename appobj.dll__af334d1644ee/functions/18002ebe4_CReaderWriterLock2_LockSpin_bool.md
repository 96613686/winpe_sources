# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x18002ebe4`
- end: `0x18002eced`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `265`
- prototype: `void __fastcall(CReaderWriterLock2 *this, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004040`
- `0x180005230`
- `0x18002f168`

## callees

- `0x18002eb74`
- `0x18002eb94`
- `0x18002ebe4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ebff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ebff`

## pseudocode

```c
void __fastcall CReaderWriterLock2::_LockSpin(CReaderWriterLock2 *this, char a2)
{
  DWORD v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // r8d
  signed __int32 v10; // edx
  signed __int32 v11; // ecx
  char v12; // al

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_18004EB20[CurrentThreadId % 0xD]);
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
      v8 = (int)((double)v8 * CReaderWriterLock2::sm_dblDfltSpinAdjFctr);
      if ( v8 <= 10000 )
      {
        if ( v8 <= 100 )
          v8 = 100;
      }
      else
      {
        v8 = 10000;
      }
      v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
      ++v7;
      goto LABEL_2;
    }
    v10 = *(_DWORD *)this;
    if ( a2 )
    {
      if ( !(_WORD)v10 )
      {
        v11 = v10 | 0xFFFF;
        goto LABEL_11;
      }
    }
    else if ( (v10 & 0xFFFF8000) == 0 )
    {
      v11 = v10 + 1;
LABEL_11:
      v12 = 1;
      if ( v10 == _InterlockedCompareExchange((volatile signed __int32 *)this, v11, v10) )
        goto LABEL_13;
    }
    v12 = 0;
LABEL_13:
    if ( v12 )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x18002ebe4  push    rbx
0x18002ebe6  push    rbp
0x18002ebe7  push    rsi
0x18002ebe8  push    rdi
0x18002ebe9  push    r13
0x18002ebeb  push    r14
0x18002ebed  push    r15
0x18002ebef  sub     rsp, 20h
0x18002ebf3  xor     r15d, r15d
0x18002ebf6  mov     r14b, dl
0x18002ebf9  mov     ebp, r15d
0x18002ebfc  mov     rdi, rcx
0x18002ebff  call    cs:__imp_GetCurrentThreadId
0x18002ec05  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x18002ec0c  lea     r13d, [r15+64h]
0x18002ec10  mov     r9d, eax
0x18002ec13  mov     esi, r15d
0x18002ec16  mov     eax, 4EC4EC4Fh
0x18002ec1b  mul     r9d
0x18002ec1e  movd    xmm0, ecx
0x18002ec22  cvtdq2pd xmm0, xmm0
0x18002ec26  shr     edx, 2
0x18002ec29  imul    r8d, edx, 0Dh
0x18002ec2d  lea     rdx, qword_18004EB20
0x18002ec34  sub     r9d, r8d
0x18002ec37  mulsd   xmm0, qword ptr [rdx+r9*8]
0x18002ec3d  cvttsd2si ebx, xmm0
0x18002ec41  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18002ec48  mov     r8d, ebx
0x18002ec4b  jb      short loc_18002EC52
0x18002ec4d  test    cx, cx
0x18002ec50  jnz     short loc_18002EC58
0x18002ec52  mov     r8d, 1
0x18002ec58  sub     r8d, 1
0x18002ec5c  js      short loc_18002EC96
0x18002ec5e  mov     edx, [rdi]
0x18002ec60  test    r14b, r14b
0x18002ec63  jz      short loc_18002EC74
0x18002ec65  test    dx, dx
0x18002ec68  jnz     short loc_18002EC8B
0x18002ec6a  mov     ecx, edx
0x18002ec6c  or      ecx, 0FFFFh
0x18002ec72  jmp     short loc_18002EC7F
0x18002ec74  test    edx, 0FFFF8000h
0x18002ec7a  jnz     short loc_18002EC8B
0x18002ec7c  lea     ecx, [rdx+1]
0x18002ec7f  mov     eax, edx
0x18002ec81  lock cmpxchg [rdi], ecx
0x18002ec85  cmp     edx, eax
0x18002ec87  mov     al, 1
0x18002ec89  jz      short loc_18002EC8E
0x18002ec8b  mov     al, r15b
0x18002ec8e  test    al, al
0x18002ec90  jnz     short loc_18002ECDE
0x18002ec92  pause
0x18002ec94  jmp     short loc_18002EC58
0x18002ec96  mov     ecx, ebp; dwMilliseconds
0x18002ec98  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18002ec9d  mov     ecx, esi; unsigned int
0x18002ec9f  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18002eca4  movd    xmm0, ebx
0x18002eca8  mov     ebp, eax
0x18002ecaa  cvtdq2pd xmm0, xmm0
0x18002ecae  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x18002ecb6  cvttsd2si ebx, xmm0
0x18002ecba  cmp     ebx, 2710h
0x18002ecc0  jle     short loc_18002ECC9
0x18002ecc2  mov     ebx, 2710h
0x18002ecc7  jmp     short loc_18002ECD0
0x18002ecc9  cmp     ebx, r13d
0x18002eccc  cmovle  ebx, r13d
0x18002ecd0  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x18002ecd7  inc     esi
0x18002ecd9  jmp     loc_18002EC41
0x18002ecde  add     rsp, 20h
0x18002ece2  pop     r15
0x18002ece4  pop     r14
0x18002ece6  pop     r13
0x18002ece8  pop     rdi
0x18002ece9  pop     rsi
0x18002ecea  pop     rbp
0x18002eceb  pop     rbx
0x18002ecec  retn
```
