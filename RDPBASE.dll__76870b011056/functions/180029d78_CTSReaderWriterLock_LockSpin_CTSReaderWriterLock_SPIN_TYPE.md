# CTSReaderWriterLock::_LockSpin(CTSReaderWriterLock::SPIN_TYPE)

- ea: `0x180029d78`
- end: `0x180029ec9`
- name: `?_LockSpin@CTSReaderWriterLock@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180072250`

## callees

- `0x180016b50`
- `0x180029d78`
- `0x18002a43c`
- `0x180072220`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180029e5f`
- `api-ms-win-core-processthreads-l1-1-0!SwitchToThread` at `0x180029e5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029e16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029e2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029d92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029e16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029e2f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029ec1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029ec1`

## pseudocode

```c
__int64 __fastcall CTSReaderWriterLock::_LockSpin(__int64 a1, int a2)
{
  DWORD v2; // r15d
  double v5; // xmm0_8
  int v6; // edi
  int v7; // ebp
  signed __int32 v8; // edx
  __int64 result; // rax
  signed __int32 v10; // r14d
  DWORD CurrentThreadId; // ecx

  v2 = 0;
  v5 = *(double *)&`CTSReaderWriterLock::_RandomBackoffFactor'::`2'::s_aFactors[GetCurrentThreadId() % 0xD] * 4000.0;
LABEL_2:
  v6 = (int)v5;
  if ( (int)v5 > 10000 )
  {
    v6 = 10000;
  }
  else if ( v6 <= 100 )
  {
    v6 = 100;
  }
  v7 = 1;
  if ( *(_DWORD *)(a1 + 12) )
    v7 = v6;
  while ( 1 )
  {
    if ( a2 == 1 )
    {
      if ( *(_DWORD *)(a1 + 4)
        || (unsigned __int16)*(_DWORD *)a1
        || (v8 = *(_DWORD *)a1, v8 != _InterlockedCompareExchange((volatile signed __int32 *)a1, v8 | 0xFFFF, v8)) )
      {
        if ( *(_DWORD *)(a1 + 4) != GetCurrentThreadId() )
        {
          result = 0;
          goto LABEL_18;
        }
        PAL_System_AtomicIncrement(a1 + 8);
      }
      else
      {
        v10 = *(_DWORD *)(a1 + 4);
        CurrentThreadId = GetCurrentThreadId();
        if ( a1 != -4 )
          _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 4), CurrentThreadId, v10);
        if ( a1 != -8 )
          _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), 1, *(_DWORD *)(a1 + 8));
      }
      result = 1;
    }
    else
    {
      result = a2 == 2
             ? CTSReaderWriterLock::_TryReadLock((CTSReaderWriterLock *)a1)
             : CTSReaderWriterLock::_TryReadLockRecursive((CTSReaderWriterLock *)a1);
    }
LABEL_18:
    if ( (_DWORD)result )
      return result;
    if ( !--v7 )
    {
      if ( !SwitchToThread() )
        Sleep(v2);
      v2 ^= 1u;
      v5 = (double)v6 * 0.5;
      goto LABEL_2;
    }
  }
}

```

## disassembly

```asm
0x180029d78  push    rbx
0x180029d7a  push    rbp
0x180029d7b  push    rsi
0x180029d7c  push    rdi
0x180029d7d  push    r12
0x180029d7f  push    r13
0x180029d81  push    r14
0x180029d83  push    r15
0x180029d85  sub     rsp, 28h
0x180029d89  xor     r15d, r15d
0x180029d8c  mov     r12d, edx
0x180029d8f  mov     rbx, rcx
0x180029d92  call    cs:__imp_GetCurrentThreadId
0x180029d98  mov     r9d, eax
0x180029d9b  mov     eax, 4EC4EC4Fh
0x180029da0  lea     rcx, ?s_aFactors@?1??_RandomBackoffFactor@CTSReaderWriterLock@@AEAANXZ@4QBNB; double const near * const `CTSReaderWriterLock::_RandomBackoffFactor(void)'::`2'::s_aFactors
0x180029da7  mul     r9d
0x180029daa  lea     r13d, [r15+1]
0x180029dae  shr     edx, 2
0x180029db1  imul    r8d, edx, 0Dh
0x180029db5  sub     r9d, r8d
0x180029db8  movsd   xmm0, qword ptr [rcx+r9*8]
0x180029dbe  mulsd   xmm0, cs:__real@40af400000000000
0x180029dc6  cvttsd2si edi, xmm0
0x180029dca  mov     eax, 64h ; 'd'
0x180029dcf  cmp     edi, 2710h
0x180029dd5  jg      loc_180029EB4
0x180029ddb  cmp     edi, eax
0x180029ddd  cmovle  edi, eax
0x180029de0  cmp     dword ptr [rbx+0Ch], 0
0x180029de4  mov     ebp, r13d
0x180029de7  cmovnz  ebp, edi
0x180029dea  cmp     r12d, r13d
0x180029ded  jnz     loc_180029E92
0x180029df3  lea     rsi, [rbx+4]
0x180029df7  mov     eax, [rsi]
0x180029df9  test    eax, eax
0x180029dfb  jnz     short loc_180029E16
0x180029dfd  mov     edx, [rbx]
0x180029dff  test    dx, dx
0x180029e02  jnz     short loc_180029E16
0x180029e04  mov     ecx, edx
0x180029e06  mov     eax, edx
0x180029e08  or      ecx, 0FFFFh
0x180029e0e  lock cmpxchg [rbx], ecx
0x180029e12  cmp     edx, eax
0x180029e14  jz      short loc_180029E2B
0x180029e16  call    cs:__imp_GetCurrentThreadId
0x180029e1c  mov     ecx, [rbx+4]
0x180029e1f  cmp     ecx, eax
0x180029e21  jz      loc_180029EA9
0x180029e27  xor     eax, eax
0x180029e29  jmp     short loc_180029E56
0x180029e2b  mov     r14d, [rbx+4]
0x180029e2f  call    cs:__imp_GetCurrentThreadId
0x180029e35  mov     ecx, eax
0x180029e37  test    rsi, rsi
0x180029e3a  jz      short loc_180029E43
0x180029e3c  mov     eax, r14d
0x180029e3f  lock cmpxchg [rsi], ecx
0x180029e43  lea     rcx, [rbx+8]
0x180029e47  mov     eax, [rcx]
0x180029e49  test    rcx, rcx
0x180029e4c  jz      short loc_180029E53
0x180029e4e  lock cmpxchg [rcx], r13d
0x180029e53  mov     eax, r13d
0x180029e56  test    eax, eax
0x180029e58  jnz     short loc_180029E81
0x180029e5a  sub     ebp, r13d
0x180029e5d  jnz     short loc_180029DEA
0x180029e5f  call    cs:__imp_SwitchToThread
0x180029e65  test    eax, eax
0x180029e67  jz      short loc_180029EBE
0x180029e69  movd    xmm0, edi
0x180029e6d  xor     r15d, r13d
0x180029e70  cvtdq2pd xmm0, xmm0
0x180029e74  mulsd   xmm0, cs:__real@3fe0000000000000
0x180029e7c  jmp     loc_180029DC6
0x180029e81  add     rsp, 28h
0x180029e85  pop     r15
0x180029e87  pop     r14
0x180029e89  pop     r13
0x180029e8b  pop     r12
0x180029e8d  pop     rdi
0x180029e8e  pop     rsi
0x180029e8f  pop     rbp
0x180029e90  pop     rbx
0x180029e91  retn
0x180029e92  mov     rcx, rbx; this
0x180029e95  cmp     r12d, 2
0x180029e99  jnz     short loc_180029EA2
0x180029e9b  call    ?_TryReadLock@CTSReaderWriterLock@@AEAAHXZ; CTSReaderWriterLock::_TryReadLock(void)
0x180029ea0  jmp     short loc_180029E56
0x180029ea2  call    ?_TryReadLockRecursive@CTSReaderWriterLock@@AEAAHXZ; CTSReaderWriterLock::_TryReadLockRecursive(void)
0x180029ea7  jmp     short loc_180029E56
0x180029ea9  lea     rcx, [rbx+8]
0x180029ead  call    PAL_System_AtomicIncrement
0x180029eb2  jmp     short loc_180029E53
0x180029eb4  mov     edi, 2710h
0x180029eb9  jmp     loc_180029DE0
0x180029ebe  mov     ecx, r15d; dwMilliseconds
0x180029ec1  call    cs:__imp_Sleep
0x180029ec7  jmp     short loc_180029E69
```
