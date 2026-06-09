# CRealTimePen::AcquireLock(RtsLockType)

- ea: `0x18001f1c0`
- end: `0x18001f32e`
- name: `?AcquireLock@CRealTimePen@@UEAAJW4RtsLockType@@@Z`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a870`

## callees

- `0x18001f1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f1ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f244`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f275`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f2f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f1ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f244`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f275`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f2f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f2b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f2b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f2c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f2d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f309`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f284`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f295`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f2c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f2d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f309`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18001f253`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18001f253`

## pseudocode

```c
__int64 __fastcall CRealTimePen::AcquireLock(__int64 a1, int a2)
{
  volatile signed __int32 *v4; // r14
  unsigned int v5; // r12d
  int v7; // edi

  v4 = (volatile signed __int32 *)(a1 + 112);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 112));
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  if ( !*(_BYTE *)(a1 + 116) || (v7 = *(_DWORD *)(a1 + 120), GetCurrentThreadId() == v7) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
    if ( (a2 & 0xFFFFFFF0) != 0 )
    {
      v5 = -2147024809;
    }
    else if ( (a2 & 8) != 0
           && (GetCurrentThreadId() == *(_DWORD *)(a1 + 360) || GetCurrentThreadId() == *(_DWORD *)(a1 + 364)) )
    {
      v5 = -2147220937;
    }
    else
    {
      if ( (a2 & 2) != 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 168));
        if ( (a2 & 8) == 0 )
          _InterlockedExchange((volatile __int32 *)(a1 + 360), GetCurrentThreadId());
      }
      if ( (a2 & 4) != 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 208));
        if ( (a2 & 8) == 0 )
          _InterlockedExchange((volatile __int32 *)(a1 + 364), GetCurrentThreadId());
      }
      if ( (a2 & 1) != 0 )
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
    }
  }
  else
  {
    v5 = -2147467259;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  }
  _InterlockedDecrement(v4);
  WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 104));
  return v5;
}

```

## disassembly

```asm
0x18001f1c0  mov     [rsp+arg_8], rbx
0x18001f1c5  mov     [rsp+arg_0], rcx
0x18001f1ca  push    rsi
0x18001f1cb  push    rdi
0x18001f1cc  push    r12
0x18001f1ce  push    r14
0x18001f1d0  push    r15
0x18001f1d2  sub     rsp, 30h
0x18001f1d6  mov     ebx, edx
0x18001f1d8  mov     rsi, rcx
0x18001f1db  lea     r14, [rcx+70h]
0x18001f1df  mov     [rsp+58h+var_38], r14
0x18001f1e4  lock inc dword ptr [r14]
0x18001f1e8  xor     r12d, r12d
0x18001f1eb  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18001f1ef  call    cs:__imp_EnterCriticalSection
0x18001f1f5  cmp     [rsi+74h], r12b
0x18001f1f9  jnz     loc_18001F292
0x18001f1ff  lea     rcx, [rsi+80h]; lpCriticalSection
0x18001f206  call    cs:__imp_LeaveCriticalSection
0x18001f20c  test    ebx, 0FFFFFFF0h
0x18001f212  jnz     loc_18001F2B8
0x18001f218  mov     byte ptr [rsp+58h+arg_10], r12b
0x18001f21d  mov     [rsp+58h+arg_18], r12b
0x18001f222  mov     edi, ebx
0x18001f224  and     edi, 8
0x18001f227  jnz     loc_18001F2C0
0x18001f22d  test    bl, 2
0x18001f230  jnz     loc_18001F2EF
0x18001f236  test    bl, 4
0x18001f239  jnz     short loc_18001F26E
0x18001f23b  test    bl, 1
0x18001f23e  jz      short loc_18001F24B
0x18001f240  lea     rcx, [rsi+28h]; lpCriticalSection
0x18001f244  call    cs:__imp_EnterCriticalSection
0x18001f24a  nop
0x18001f24b  lock dec dword ptr [r14]
0x18001f24f  lea     rcx, [rsi+68h]; ConditionVariable
0x18001f253  call    cs:__imp_WakeConditionVariable
0x18001f259  mov     eax, r12d
0x18001f25c  mov     rbx, [rsp+58h+arg_8]
0x18001f261  add     rsp, 30h
0x18001f265  pop     r15
0x18001f267  pop     r14
0x18001f269  pop     r12
0x18001f26b  pop     rdi
0x18001f26c  pop     rsi
0x18001f26d  retn
0x18001f26e  lea     rcx, [rsi+0D0h]; lpCriticalSection
0x18001f275  call    cs:__imp_EnterCriticalSection
0x18001f27b  mov     byte ptr [rsp+58h+arg_10], 1
0x18001f280  test    edi, edi
0x18001f282  jnz     short loc_18001F23B
0x18001f284  call    cs:__imp_GetCurrentThreadId
0x18001f28a  xchg    eax, [rsi+16Ch]
0x18001f290  jmp     short loc_18001F23B
0x18001f292  mov     edi, [rsi+78h]
0x18001f295  call    cs:__imp_GetCurrentThreadId
0x18001f29b  cmp     eax, edi
0x18001f29d  jz      loc_18001F1FF
0x18001f2a3  mov     r12d, 80004005h
0x18001f2a9  lea     rcx, [rsi+80h]; lpCriticalSection
0x18001f2b0  call    cs:__imp_LeaveCriticalSection
0x18001f2b6  jmp     short loc_18001F24B
0x18001f2b8  mov     r12d, 80070057h
0x18001f2be  jmp     short loc_18001F24B
0x18001f2c0  call    cs:__imp_GetCurrentThreadId
0x18001f2c6  mov     ecx, [rsi+168h]
0x18001f2cc  cmp     eax, ecx
0x18001f2ce  jz      short loc_18001F2E4
0x18001f2d0  call    cs:__imp_GetCurrentThreadId
0x18001f2d6  mov     ecx, [rsi+16Ch]
0x18001f2dc  cmp     eax, ecx
0x18001f2de  jnz     loc_18001F22D
0x18001f2e4  mov     r12d, 80040237h
0x18001f2ea  jmp     loc_18001F24B
0x18001f2ef  lea     rcx, [rsi+0A8h]; lpCriticalSection
0x18001f2f6  call    cs:__imp_EnterCriticalSection
0x18001f2fc  mov     [rsp+58h+arg_18], 1
0x18001f301  test    edi, edi
0x18001f303  jnz     loc_18001F236
0x18001f309  call    cs:__imp_GetCurrentThreadId
0x18001f30f  xchg    eax, [rsi+168h]
0x18001f315  jmp     loc_18001F236
0x18001f31a  mov     rsi, [rsp+58h+arg_0]
0x18001f31f  mov     r12d, [rsp+58h+arg_10]
0x18001f324  mov     r14, [rsp+58h+var_38]
0x18001f329  jmp     loc_18001F24B
```
