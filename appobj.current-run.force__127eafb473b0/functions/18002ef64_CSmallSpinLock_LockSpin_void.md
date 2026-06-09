# CSmallSpinLock::_LockSpin(void)

- ea: `0x18002ef64`
- end: `0x18002f064`
- name: `?_LockSpin@CSmallSpinLock@@AEAAXXZ`
- size: `256`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004120`

## callees

- `0x18002eb74`
- `0x18002eb94`
- `0x18002ef64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ef7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002efb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002efd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ef7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002efb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002efd1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002efbf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18002efbf`

## pseudocode

```c
void __fastcall CSmallSpinLock::_LockSpin(CSmallSpinLock *this)
{
  int v1; // r14d
  DWORD v3; // ebp
  int v4; // ebx
  unsigned int v5; // edi
  int v6; // edx

  v1 = CSmallSpinLock::sm_wDefaultSpinCount;
  v3 = 0;
  v4 = (int)((double)v1 * *(double *)&qword_18004EB20[GetCurrentThreadId() % 0xD]);
  if ( *(_DWORD *)this == GetCurrentThreadId() )
    DebugBreak();
  v5 = 0;
  while ( *(_DWORD *)this || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) )
  {
    if ( g_cProcessors > 1 && v1 )
    {
      v6 = v4;
      while ( *(_DWORD *)this )
      {
        if ( --v6 >= 0 )
        {
          _mm_pause();
        }
        else
        {
          SwitchOrSleep(v3);
          v4 = (int)((double)v4 * CSmallSpinLock::sm_dblDfltSpinAdjFctr);
          if ( v4 <= 10000 )
          {
            if ( v4 <= 100 )
              v4 = 100;
          }
          else
          {
            v4 = 10000;
          }
          v3 = SleepTime(v5);
        }
      }
    }
    else
    {
      SwitchOrSleep(v3);
      v3 = SleepTime(v5);
    }
    ++v5;
  }
}

```

## disassembly

```asm
0x18002ef64  push    rbx
0x18002ef66  push    rbp
0x18002ef67  push    rsi
0x18002ef68  push    rdi
0x18002ef69  push    r12
0x18002ef6b  push    r14
0x18002ef6d  sub     rsp, 28h
0x18002ef71  movzx   r14d, cs:?sm_wDefaultSpinCount@CSmallSpinLock@@1GA; ushort CSmallSpinLock::sm_wDefaultSpinCount
0x18002ef79  mov     rsi, rcx
0x18002ef7c  xor     ebp, ebp
0x18002ef7e  call    cs:__imp_GetCurrentThreadId
0x18002ef84  movd    xmm0, r14d
0x18002ef89  lea     rcx, qword_18004EB20
0x18002ef90  mov     r9d, eax
0x18002ef93  mov     eax, 4EC4EC4Fh
0x18002ef98  mul     r9d
0x18002ef9b  cvtdq2pd xmm0, xmm0
0x18002ef9f  shr     edx, 2
0x18002efa2  imul    r8d, edx, 0Dh
0x18002efa6  sub     r9d, r8d
0x18002efa9  mulsd   xmm0, qword ptr [rcx+r9*8]
0x18002efaf  cvttsd2si ebx, xmm0
0x18002efb3  call    cs:__imp_GetCurrentThreadId
0x18002efb9  mov     ecx, [rsi]
0x18002efbb  cmp     ecx, eax
0x18002efbd  jnz     short loc_18002EFC5
0x18002efbf  call    cs:__imp_DebugBreak
0x18002efc5  xor     edi, edi
0x18002efc7  lea     r12d, [rdi+64h]
0x18002efcb  mov     eax, [rsi]
0x18002efcd  test    eax, eax
0x18002efcf  jnz     short loc_18002EFE1
0x18002efd1  call    cs:__imp_GetCurrentThreadId
0x18002efd7  mov     ecx, eax
0x18002efd9  xor     eax, eax
0x18002efdb  lock cmpxchg [rsi], ecx
0x18002efdf  jz      short loc_18002F057
0x18002efe1  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x18002efe8  jbe     short loc_18002F040
0x18002efea  test    r14d, r14d
0x18002efed  jz      short loc_18002F040
0x18002efef  mov     edx, ebx
0x18002eff1  jmp     short loc_18002F038
0x18002eff3  sub     edx, 1
0x18002eff6  jns     short loc_18002F036
0x18002eff8  mov     ecx, ebp; dwMilliseconds
0x18002effa  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18002efff  movd    xmm0, ebx
0x18002f003  cvtdq2pd xmm0, xmm0
0x18002f007  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSmallSpinLock@@1NA; double CSmallSpinLock::sm_dblDfltSpinAdjFctr
0x18002f00f  cvttsd2si ebx, xmm0
0x18002f013  cmp     ebx, 2710h
0x18002f019  jle     short loc_18002F022
0x18002f01b  mov     ebx, 2710h
0x18002f020  jmp     short loc_18002F029
0x18002f022  cmp     ebx, r12d
0x18002f025  cmovle  ebx, r12d
0x18002f029  mov     ecx, edi; unsigned int
0x18002f02b  mov     edx, ebx
0x18002f02d  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18002f032  mov     ebp, eax
0x18002f034  jmp     short loc_18002F038
0x18002f036  pause
0x18002f038  mov     eax, [rsi]
0x18002f03a  test    eax, eax
0x18002f03c  jnz     short loc_18002EFF3
0x18002f03e  jmp     short loc_18002F050
0x18002f040  mov     ecx, ebp; dwMilliseconds
0x18002f042  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18002f047  mov     ecx, edi; unsigned int
0x18002f049  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18002f04e  mov     ebp, eax
0x18002f050  inc     edi
0x18002f052  jmp     loc_18002EFCB
0x18002f057  add     rsp, 28h
0x18002f05b  pop     r14
0x18002f05d  pop     r12
0x18002f05f  pop     rdi
0x18002f060  pop     rsi
0x18002f061  pop     rbp
0x18002f062  pop     rbx
0x18002f063  retn
```
