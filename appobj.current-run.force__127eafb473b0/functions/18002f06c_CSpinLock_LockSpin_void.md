# CSpinLock::_LockSpin(void)

- ea: `0x18002f06c`
- end: `0x18002f161`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `245`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800051f0`

## callees

- `0x18002eb74`
- `0x18002eb94`
- `0x18002f06c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f0ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f089`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f0ed`

## pseudocode

```c
void __fastcall CSpinLock::_LockSpin(CSpinLock *this)
{
  int v1; // ebx
  DWORD v2; // ebp
  unsigned int v4; // esi
  int v5; // ebx
  int v6; // edx

  v1 = CSpinLock::sm_wDefaultSpinCount;
  v2 = 0;
  v4 = 0;
  v5 = (int)((double)v1 * *(double *)&qword_18004EB20[GetCurrentThreadId() % 0xD]);
  while ( 1 )
  {
    if ( g_cProcessors > 1 && CSpinLock::sm_wDefaultSpinCount )
    {
LABEL_13:
      v6 = v5;
      while ( *(_DWORD *)this )
      {
        if ( --v6 < 0 )
        {
          SwitchOrSleep(v2);
          v2 = SleepTime(v4);
          v5 = (int)((double)v5 * CSpinLock::sm_dblDfltSpinAdjFctr);
          if ( v5 <= 10000 )
          {
            if ( v5 <= 100 )
              v5 = 100;
          }
          else
          {
            v5 = 10000;
          }
          goto LABEL_13;
        }
        _mm_pause();
      }
    }
    else
    {
      SwitchOrSleep(v2);
      v2 = SleepTime(v4);
    }
    if ( !*(_DWORD *)this
      && !_InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) )
    {
      break;
    }
    ++v4;
  }
}

```

## disassembly

```asm
0x18002f06c  push    rbx
0x18002f06e  push    rbp
0x18002f06f  push    rsi
0x18002f070  push    rdi
0x18002f071  push    r12
0x18002f073  push    r14
0x18002f075  sub     rsp, 28h
0x18002f079  movzx   ebx, cs:?sm_wDefaultSpinCount@CSpinLock@@1GA; ushort CSpinLock::sm_wDefaultSpinCount
0x18002f080  xor     r14d, r14d
0x18002f083  mov     ebp, r14d
0x18002f086  mov     rdi, rcx
0x18002f089  call    cs:__imp_GetCurrentThreadId
0x18002f08f  movd    xmm0, ebx
0x18002f093  lea     rcx, qword_18004EB20
0x18002f09a  mov     r9d, eax
0x18002f09d  lea     r12d, [r14+64h]
0x18002f0a1  mov     eax, 4EC4EC4Fh
0x18002f0a6  mov     esi, r14d
0x18002f0a9  mul     r9d
0x18002f0ac  cvtdq2pd xmm0, xmm0
0x18002f0b0  shr     edx, 2
0x18002f0b3  imul    r8d, edx, 0Dh
0x18002f0b7  sub     r9d, r8d
0x18002f0ba  mulsd   xmm0, qword ptr [rcx+r9*8]
0x18002f0c0  cvttsd2si ebx, xmm0
0x18002f0c4  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x18002f0cb  jbe     short loc_18002F0D7
0x18002f0cd  cmp     cs:?sm_wDefaultSpinCount@CSpinLock@@1GA, r14w; ushort CSpinLock::sm_wDefaultSpinCount
0x18002f0d5  jnz     short loc_18002F146
0x18002f0d7  mov     ecx, ebp; dwMilliseconds
0x18002f0d9  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18002f0de  mov     ecx, esi; unsigned int
0x18002f0e0  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18002f0e5  mov     ebp, eax
0x18002f0e7  mov     eax, [rdi]
0x18002f0e9  test    eax, eax
0x18002f0eb  jnz     short loc_18002F103
0x18002f0ed  call    cs:__imp_GetCurrentThreadId
0x18002f0f3  mov     ecx, eax
0x18002f0f5  and     ecx, 0FFFFFFFDh
0x18002f0f8  or      ecx, 1
0x18002f0fb  xor     eax, eax
0x18002f0fd  lock cmpxchg [rdi], ecx
0x18002f101  jz      short loc_18002F154
0x18002f103  inc     esi
0x18002f105  jmp     short loc_18002F0C4
0x18002f107  sub     edx, 1
0x18002f10a  jns     short loc_18002F14A
0x18002f10c  mov     ecx, ebp; dwMilliseconds
0x18002f10e  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18002f113  mov     ecx, esi; unsigned int
0x18002f115  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18002f11a  movd    xmm0, ebx
0x18002f11e  mov     ebp, eax
0x18002f120  cvtdq2pd xmm0, xmm0
0x18002f124  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSpinLock@@1NA; double CSpinLock::sm_dblDfltSpinAdjFctr
0x18002f12c  cvttsd2si ebx, xmm0
0x18002f130  cmp     ebx, 2710h
0x18002f136  jle     short loc_18002F13F
0x18002f138  mov     ebx, 2710h
0x18002f13d  jmp     short loc_18002F146
0x18002f13f  cmp     ebx, r12d
0x18002f142  cmovle  ebx, r12d
0x18002f146  mov     edx, ebx
0x18002f148  jmp     short loc_18002F14C
0x18002f14a  pause
0x18002f14c  mov     eax, [rdi]
0x18002f14e  test    eax, eax
0x18002f150  jnz     short loc_18002F107
0x18002f152  jmp     short loc_18002F0E7
0x18002f154  add     rsp, 28h
0x18002f158  pop     r14
0x18002f15a  pop     r12
0x18002f15c  pop     rdi
0x18002f15d  pop     rsi
0x18002f15e  pop     rbp
0x18002f15f  pop     rbx
0x18002f160  retn
```
