# SeComRouterDelete

- ea: `0x180035af4`
- end: `0x180035ce8`
- name: `SeComRouterDelete`
- size: `500`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007c4c`
- `0x180056ab8`

## callees

- `0x180024a80`
- `0x180035af4`
- `0x180035dec`
- `0x18005764c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180035cba`
- `ntdll!RtlDeleteCriticalSection` at `0x180035cba`
- `ntdll!RtlFreeHeap` at `0x180035b7c`
- `ntdll!RtlFreeHeap` at `0x180035b9a`
- `ntdll!RtlFreeHeap` at `0x180035bb8`
- `ntdll!RtlFreeHeap` at `0x180035c3c`
- `ntdll!RtlFreeHeap` at `0x180035c63`
- `ntdll!RtlFreeHeap` at `0x180035c8d`
- `ntdll!RtlFreeHeap` at `0x180035cd2`
- `ntdll!RtlFreeHeap` at `0x180035b7c`
- `ntdll!RtlFreeHeap` at `0x180035b9a`
- `ntdll!RtlFreeHeap` at `0x180035bb8`
- `ntdll!RtlFreeHeap` at `0x180035c3c`
- `ntdll!RtlFreeHeap` at `0x180035c63`
- `ntdll!RtlFreeHeap` at `0x180035c8d`
- `ntdll!RtlFreeHeap` at `0x180035cd2`

## pseudocode

```c
void __fastcall SeComRouterDelete(PRTL_CRITICAL_SECTION P)
{
  HANDLE OwningThread; // rax
  ULONGLONG i; // rsi
  struct _RTL_CRITICAL_SECTION_DEBUG *v4; // rdi
  ULONGLONG v5; // rcx
  struct _RTL_CRITICAL_SECTION *CriticalSection; // r8
  struct _LIST_ENTRY *Blink; // r8
  struct _LIST_ENTRY *Flink; // r8
  ULONG_PTR SpinCount; // rax
  ULONGLONG j; // rdi
  char *v11; // rdx
  ULONGLONG LockSemaphore; // rcx
  char *v13; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r8
  void *v15; // r8
  HANDLE v16; // r8
  ULONGLONG pullResult; // [rsp+30h] [rbp+8h] BYREF

  if ( P )
  {
    if ( P == g_ActiveComRouter )
      g_ActiveComRouter = 0;
    OwningThread = P[1].OwningThread;
    if ( OwningThread )
    {
      for ( i = 0; i < (unsigned __int64)OwningThread; ++i )
      {
        v4 = 0;
        if ( i < (unsigned __int64)OwningThread )
        {
          v5 = *(_QWORD *)&P[1].LockCount;
          pullResult = 0;
          if ( ULongLongMult(v5, i, &pullResult) < 0
            || (v4 = (PRTL_CRITICAL_SECTION_DEBUG)((char *)P[2].DebugInfo + pullResult), v4 < P[2].DebugInfo) )
          {
            v4 = 0;
          }
        }
        CriticalSection = v4->CriticalSection;
        if ( CriticalSection )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, CriticalSection);
        Blink = v4->ProcessLocksList.Blink;
        if ( Blink )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Blink);
        Flink = v4->ProcessLocksList.Flink;
        if ( Flink )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Flink);
        OwningThread = P[1].OwningThread;
      }
    }
    SpinCount = P[3].SpinCount;
    if ( SpinCount )
    {
      for ( j = 0; j < SpinCount; ++j )
      {
        v11 = 0;
        if ( j < SpinCount )
        {
          LockSemaphore = (ULONGLONG)P[3].LockSemaphore;
          pullResult = 0;
          if ( ULongLongMult(LockSemaphore, j, &pullResult) < 0
            || (v13 = (char *)P[4].OwningThread, v11 = &v13[pullResult], &v13[pullResult] < v13) )
          {
            v11 = 0;
          }
        }
        SepComRouterHookedObjectDelete(v11);
        SpinCount = P[3].SpinCount;
      }
    }
    DebugInfo = P[2].DebugInfo;
    if ( DebugInfo )
      RtlFreeHeap(P[1].DebugInfo, 0, DebugInfo);
    *(_OWORD *)&P[1].DebugInfo = 0;
    *(_OWORD *)&P[1].OwningThread = 0;
    *(_OWORD *)&P[1].SpinCount = 0;
    v15 = *(void **)&P[3].LockCount;
    if ( v15 )
      RtlFreeHeap(*(HANDLE *)&P[2].LockCount, 0, v15);
    *(_OWORD *)&P[2].LockCount = 0;
    *(_OWORD *)&P[2].LockSemaphore = 0;
    *(_OWORD *)&P[3].DebugInfo = 0;
    v16 = P[4].OwningThread;
    if ( v16 )
      RtlFreeHeap(P[3].OwningThread, 0, v16);
    *(_OWORD *)&P[3].OwningThread = 0;
    *(_OWORD *)&P[3].SpinCount = 0;
    *(_OWORD *)&P[4].LockCount = 0;
    SeInExDelete(P[4].LockSemaphore);
    RtlDeleteCriticalSection(P);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
}

```

## disassembly

```asm
0x180035af4  test    rcx, rcx
0x180035af7  jz      locret_180035CE7
0x180035afd  mov     [rsp+arg_8], rbx
0x180035b02  mov     [rsp+arg_10], rsi
0x180035b07  push    rdi
0x180035b08  sub     rsp, 20h
0x180035b0c  cmp     rcx, cs:g_ActiveComRouter
0x180035b13  mov     rbx, rcx
0x180035b16  jnz     short loc_180035B23
0x180035b18  mov     cs:g_ActiveComRouter, 0
0x180035b23  mov     rax, [rcx+38h]
0x180035b27  test    rax, rax
0x180035b2a  jz      loc_180035BCE
0x180035b30  xor     esi, esi
0x180035b32  xor     edi, edi
0x180035b34  cmp     rsi, rax
0x180035b37  jnb     short loc_180035B64
0x180035b39  mov     rcx, [rbx+30h]; ullMultiplicand
0x180035b3d  lea     r8, [rsp+28h+pullResult]; pullResult
0x180035b42  mov     rdx, rsi; ullMultiplier
0x180035b45  mov     [rsp+28h+pullResult], rdi
0x180035b4a  call    ULongLongMult
0x180035b4f  test    eax, eax
0x180035b51  js      short loc_180035B62
0x180035b53  mov     rdi, [rsp+28h+pullResult]
0x180035b58  add     rdi, [rbx+50h]
0x180035b5c  cmp     rdi, [rbx+50h]
0x180035b60  jnb     short loc_180035B64
0x180035b62  xor     edi, edi
0x180035b64  mov     r8, [rdi+8]; P
0x180035b68  test    r8, r8
0x180035b6b  jz      short loc_180035B82
0x180035b6d  mov     rcx, gs:60h
0x180035b76  xor     edx, edx; Flags
0x180035b78  mov     rcx, [rcx+30h]; HeapHandle
0x180035b7c  call    cs:__imp_RtlFreeHeap
0x180035b82  mov     r8, [rdi+18h]; P
0x180035b86  test    r8, r8
0x180035b89  jz      short loc_180035BA0
0x180035b8b  mov     rcx, gs:60h
0x180035b94  xor     edx, edx; Flags
0x180035b96  mov     rcx, [rcx+30h]; HeapHandle
0x180035b9a  call    cs:__imp_RtlFreeHeap
0x180035ba0  mov     r8, [rdi+10h]; P
0x180035ba4  test    r8, r8
0x180035ba7  jz      short loc_180035BBE
0x180035ba9  mov     rcx, gs:60h
0x180035bb2  xor     edx, edx; Flags
0x180035bb4  mov     rcx, [rcx+30h]; HeapHandle
0x180035bb8  call    cs:__imp_RtlFreeHeap
0x180035bbe  mov     rax, [rbx+38h]
0x180035bc2  inc     rsi
0x180035bc5  cmp     rsi, rax
0x180035bc8  jb      loc_180035B32
0x180035bce  mov     rax, [rbx+98h]
0x180035bd5  test    rax, rax
0x180035bd8  jz      short loc_180035C2D
0x180035bda  xor     edi, edi
0x180035bdc  xor     edx, edx
0x180035bde  cmp     rdi, rax
0x180035be1  jnb     short loc_180035C16
0x180035be3  mov     rcx, [rbx+90h]; ullMultiplicand
0x180035bea  lea     r8, [rsp+28h+pullResult]; pullResult
0x180035bef  mov     [rsp+28h+pullResult], rdx
0x180035bf4  mov     rdx, rdi; ullMultiplier
0x180035bf7  call    ULongLongMult
0x180035bfc  test    eax, eax
0x180035bfe  js      short loc_180035C14
0x180035c00  mov     rcx, [rbx+0B0h]
0x180035c07  mov     rdx, [rsp+28h+pullResult]
0x180035c0c  add     rdx, rcx
0x180035c0f  cmp     rdx, rcx
0x180035c12  jnb     short loc_180035C16
0x180035c14  xor     edx, edx
0x180035c16  mov     rcx, rdx
0x180035c19  call    SepComRouterHookedObjectDelete
0x180035c1e  mov     rax, [rbx+98h]
0x180035c25  inc     rdi
0x180035c28  cmp     rdi, rax
0x180035c2b  jb      short loc_180035BDC
0x180035c2d  mov     r8, [rbx+50h]; P
0x180035c31  test    r8, r8
0x180035c34  jz      short loc_180035C42
0x180035c36  mov     rcx, [rbx+28h]; HeapHandle
0x180035c3a  xor     edx, edx; Flags
0x180035c3c  call    cs:__imp_RtlFreeHeap
0x180035c42  xorps   xmm0, xmm0
0x180035c45  movups  xmmword ptr [rbx+28h], xmm0
0x180035c49  movups  xmmword ptr [rbx+38h], xmm0
0x180035c4d  movups  xmmword ptr [rbx+48h], xmm0
0x180035c51  mov     r8, [rbx+80h]; P
0x180035c58  test    r8, r8
0x180035c5b  jz      short loc_180035C69
0x180035c5d  mov     rcx, [rbx+58h]; HeapHandle
0x180035c61  xor     edx, edx; Flags
0x180035c63  call    cs:__imp_RtlFreeHeap
0x180035c69  xorps   xmm0, xmm0
0x180035c6c  movups  xmmword ptr [rbx+58h], xmm0
0x180035c70  movups  xmmword ptr [rbx+68h], xmm0
0x180035c74  movups  xmmword ptr [rbx+78h], xmm0
0x180035c78  mov     r8, [rbx+0B0h]; P
0x180035c7f  test    r8, r8
0x180035c82  jz      short loc_180035C93
0x180035c84  mov     rcx, [rbx+88h]; HeapHandle
0x180035c8b  xor     edx, edx; Flags
0x180035c8d  call    cs:__imp_RtlFreeHeap
0x180035c93  xorps   xmm0, xmm0
0x180035c96  movups  xmmword ptr [rbx+88h], xmm0
0x180035c9d  movups  xmmword ptr [rbx+98h], xmm0
0x180035ca4  movups  xmmword ptr [rbx+0A8h], xmm0
0x180035cab  mov     rcx, [rbx+0B8h]; void *
0x180035cb2  call    SeInExDelete
0x180035cb7  mov     rcx, rbx; CriticalSection
0x180035cba  call    cs:__imp_RtlDeleteCriticalSection
0x180035cc0  mov     rcx, gs:60h
0x180035cc9  mov     r8, rbx; P
0x180035ccc  xor     edx, edx; Flags
0x180035cce  mov     rcx, [rcx+30h]; HeapHandle
0x180035cd2  call    cs:__imp_RtlFreeHeap
0x180035cd8  mov     rbx, [rsp+28h+arg_8]
0x180035cdd  mov     rsi, [rsp+28h+arg_10]
0x180035ce2  add     rsp, 20h
0x180035ce6  pop     rdi
0x180035ce7  retn
```
