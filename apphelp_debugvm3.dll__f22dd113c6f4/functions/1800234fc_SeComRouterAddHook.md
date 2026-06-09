# SeComRouterAddHook

- ea: `0x1800234fc`
- end: `0x1800237e2`
- name: `SeComRouterAddHook`
- size: `742`
- prototype: `__int64 __usercall@<rax>(PRTL_CRITICAL_SECTION CriticalSection@<rcx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053530`
- `0x180053d00`

## callees

- `0x18000f114`
- `0x1800234fc`
- `0x180024a80`
- `0x18002606c`
- `0x180059175`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002376b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002376b`
- `ntdll!RtlEnterCriticalSection` at `0x180023527`
- `ntdll!RtlEnterCriticalSection` at `0x180023527`
- `ntdll!RtlReAllocateHeap` at `0x1800236cf`
- `ntdll!RtlReAllocateHeap` at `0x1800236cf`
- `ntdll!RtlFreeHeap` at `0x180023788`
- `ntdll!RtlFreeHeap` at `0x1800237a5`
- `ntdll!RtlFreeHeap` at `0x1800237c2`
- `ntdll!RtlFreeHeap` at `0x180023788`
- `ntdll!RtlFreeHeap` at `0x1800237a5`
- `ntdll!RtlFreeHeap` at `0x1800237c2`
- `ntdll!RtlAllocateHeap` at `0x180023546`
- `ntdll!RtlAllocateHeap` at `0x1800235d6`
- `ntdll!RtlAllocateHeap` at `0x1800236af`
- `ntdll!RtlAllocateHeap` at `0x180023546`
- `ntdll!RtlAllocateHeap` at `0x1800235d6`
- `ntdll!RtlAllocateHeap` at `0x1800236af`

## string_xrefs

- `0x180023561`: `SeComRouterAddHook`
- `0x1800235a7`: `SeComRouterAddHook`
- `0x180023757`: `SeComRouterAddHook`
- `0x18002374a`: `Failed to add com hook`

## pseudocode

```c
__int64 __fastcall SeComRouterAddHook(
        PRTL_CRITICAL_SECTION CriticalSection,
        __int64 a2,
        _OWORD *a3,
        wchar_t *a4,
        __int128 *a5,
        __int64 a6,
        __int64 a7)
{
  void *v11; // rsi
  _OWORD *v12; // r14
  void *v13; // r15
  _OWORD *Heap; // rax
  unsigned int v15; // ebx
  __int128 v16; // xmm0
  __int64 v17; // rax
  char *OwningThread; // rax
  ULONG_PTR v19; // r12
  ULONGLONG v20; // rdx
  HANDLE LockSemaphore; // rcx
  __int64 v22; // r9
  void *v23; // r12
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r8
  size_t v25; // r13
  PRTL_CRITICAL_SECTION_DEBUG v26; // rcx
  struct _RTL_CRITICAL_SECTION_DEBUG *v27; // rax
  struct _RTL_CRITICAL_SECTION_DEBUG *v28; // rbx
  ULONGLONG v29; // rcx
  char *v30; // rdx
  __int128 v31; // xmm1
  __int128 v32; // xmm0
  ULONGLONG pullResult; // [rsp+20h] [rbp-40h] BYREF
  __int128 v35; // [rsp+28h] [rbp-38h]
  __int128 v36; // [rsp+38h] [rbp-28h]
  __int128 v37; // [rsp+48h] [rbp-18h]
  ULONGLONG Size; // [rsp+A0h] [rbp+40h] BYREF
  char *v39; // [rsp+B0h] [rbp+50h]

  v11 = 0;
  v12 = 0;
  v13 = 0;
  RtlEnterCriticalSection(CriticalSection);
  if ( a3 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
    v11 = Heap;
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SeComRouterAddHook", 484, "Failed to allocate class id");
LABEL_4:
      v15 = -1073741801;
      goto LABEL_30;
    }
    *Heap = *a3;
  }
  if ( a4 )
  {
    v13 = (void *)DsUtilityDuplicateStringW(a4);
    if ( !v13 )
    {
      AslLogCallPrintf(1, "SeComRouterAddHook", 494, "Failed to duplicate activation id");
      v15 = -1073741595;
      goto LABEL_30;
    }
  }
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
  if ( !v12 )
  {
    AslLogCallPrintf(1, "SeComRouterAddHook", 502, "Failed to allocate interface id");
    goto LABEL_4;
  }
  *(_QWORD *)&v35 = a2;
  *((_QWORD *)&v35 + 1) = v11;
  *(_QWORD *)&v36 = v13;
  v16 = *a5;
  *(_QWORD *)&v37 = a6;
  v17 = a7;
  *v12 = v16;
  *((_QWORD *)&v37 + 1) = v17;
  OwningThread = (char *)CriticalSection[1].OwningThread;
  *((_QWORD *)&v36 + 1) = v12;
  v39 = OwningThread;
  if ( OwningThread >= CriticalSection[1].LockSemaphore )
  {
    if ( OwningThread + 1 <= CriticalSection[1].LockSemaphore )
    {
      v15 = -1073741811;
      goto LABEL_29;
    }
    v19 = CriticalSection[1].SpinCount - 1;
    if ( &OwningThread[CriticalSection[1].SpinCount] < OwningThread + 1
      || (v20 = *(_QWORD *)&CriticalSection[1].LockCount,
          LockSemaphore = CriticalSection[1].LockSemaphore,
          Size = 0,
          ULongLongMult((ULONGLONG)LockSemaphore, v20, &pullResult) < 0)
      || (v23 = (void *)(v22 & ~v19), ULongLongMult((ULONGLONG)v23, *(_QWORD *)&CriticalSection[1].LockCount, &Size) < 0) )
    {
      v15 = -1073741675;
      goto LABEL_29;
    }
    DebugInfo = CriticalSection[2].DebugInfo;
    v25 = Size;
    v26 = CriticalSection[1].DebugInfo;
    if ( DebugInfo )
    {
      v28 = (struct _RTL_CRITICAL_SECTION_DEBUG *)RtlReAllocateHeap(v26, 0, DebugInfo, Size);
    }
    else
    {
      v27 = (struct _RTL_CRITICAL_SECTION_DEBUG *)RtlAllocateHeap(v26, 0, Size);
      v28 = v27;
      if ( v27 )
        memset_0(v27, 0, v25);
    }
    if ( !v28 )
    {
      v15 = -1073741801;
      goto LABEL_29;
    }
    OwningThread = v39;
    CriticalSection[2].DebugInfo = v28;
    CriticalSection[1].LockSemaphore = v23;
  }
  v29 = *(_QWORD *)&CriticalSection[1].LockCount;
  Size = 0;
  if ( ULongLongMult(v29, (ULONGLONG)OwningThread, &Size) >= 0 )
  {
    v30 = (char *)CriticalSection[2].DebugInfo + Size;
    if ( (PRTL_CRITICAL_SECTION_DEBUG)v30 >= CriticalSection[2].DebugInfo )
    {
      v31 = v36;
      *(_OWORD *)v30 = v35;
      v32 = v37;
      *((_OWORD *)v30 + 1) = v31;
      *((_OWORD *)v30 + 2) = v32;
      ++CriticalSection[1].OwningThread;
      v11 = 0;
      v12 = 0;
      v13 = 0;
      v15 = 0;
      goto LABEL_30;
    }
  }
  v15 = -1073741675;
LABEL_29:
  AslLogCallPrintf(1, "SeComRouterAddHook", 525, "Failed to add com hook");
LABEL_30:
  RtlLeaveCriticalSection(CriticalSection);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( v12 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( v13 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  return v15;
}

```

## disassembly

```asm
0x1800234fc  mov     [rsp-38h+arg_8], rbx
0x180023501  push    rbp
0x180023502  push    rsi
0x180023503  push    rdi
0x180023504  push    r12
0x180023506  push    r13
0x180023508  push    r14
0x18002350a  push    r15
0x18002350c  mov     rbp, rsp
0x18002350f  sub     rsp, 60h
0x180023513  mov     rbx, r9
0x180023516  mov     r12, r8
0x180023519  mov     r13, rdx
0x18002351c  mov     rdi, rcx
0x18002351f  xor     esi, esi
0x180023521  xor     r14d, r14d
0x180023524  xor     r15d, r15d
0x180023527  call    cs:__imp_RtlEnterCriticalSection
0x18002352d  test    r12, r12
0x180023530  jz      short loc_180023585
0x180023532  mov     rcx, gs:60h
0x18002353b  lea     edx, [rsi+8]; Flags
0x18002353e  lea     r8d, [rsi+10h]; Size
0x180023542  mov     rcx, [rcx+30h]; HeapHandle
0x180023546  call    cs:__imp_RtlAllocateHeap
0x18002354c  mov     rsi, rax
0x18002354f  test    rax, rax
0x180023552  jnz     short loc_18002357C
0x180023554  lea     r9, aFailedToAlloca_6; "Failed to allocate class id"
0x18002355b  mov     r8d, 1E4h
0x180023561  lea     rdx, aSecomrouteradd_0; "SeComRouterAddHook"
0x180023568  mov     ecx, 1
0x18002356d  call    AslLogCallPrintf
0x180023572  mov     ebx, 0C0000017h
0x180023577  jmp     loc_180023768
0x18002357c  movups  xmm0, xmmword ptr [r12]
0x180023581  movdqu  xmmword ptr [rax], xmm0
0x180023585  test    rbx, rbx
0x180023588  jz      short loc_1800235C0
0x18002358a  mov     rcx, rbx; Source
0x18002358d  call    DsUtilityDuplicateStringW
0x180023592  mov     r15, rax
0x180023595  test    rax, rax
0x180023598  jnz     short loc_1800235C0
0x18002359a  lea     r9, aFailedToDuplic_1; "Failed to duplicate activation id"
0x1800235a1  mov     r8d, 1EEh
0x1800235a7  lea     rdx, aSecomrouteradd_0; "SeComRouterAddHook"
0x1800235ae  lea     ecx, [rax+1]
0x1800235b1  call    AslLogCallPrintf
0x1800235b6  mov     ebx, 0C00000E5h
0x1800235bb  jmp     loc_180023768
0x1800235c0  mov     rcx, gs:60h
0x1800235c9  mov     edx, 8; Flags
0x1800235ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800235d2  lea     r8d, [rdx+8]; Size
0x1800235d6  call    cs:__imp_RtlAllocateHeap
0x1800235dc  mov     r14, rax
0x1800235df  test    rax, rax
0x1800235e2  jnz     short loc_1800235F6
0x1800235e4  lea     r9, aFailedToAlloca_33; "Failed to allocate interface id"
0x1800235eb  mov     r8d, 1F6h
0x1800235f1  jmp     loc_180023561
0x1800235f6  mov     rax, [rbp+arg_20]
0x1800235fa  mov     qword ptr [rbp+var_38], r13
0x1800235fe  mov     qword ptr [rbp+var_38+8], rsi
0x180023602  mov     qword ptr [rbp+var_28], r15
0x180023606  movups  xmm0, xmmword ptr [rax]
0x180023609  mov     rax, [rbp+arg_28]
0x18002360d  mov     qword ptr [rbp+var_18], rax
0x180023611  mov     rax, [rbp+arg_30]
0x180023615  movdqu  xmmword ptr [r14], xmm0
0x18002361a  mov     qword ptr [rbp+var_18+8], rax
0x18002361e  mov     rax, [rdi+38h]
0x180023622  mov     qword ptr [rbp+var_28+8], r14
0x180023626  mov     [rbp+arg_10], rax
0x18002362a  cmp     rax, [rdi+40h]
0x18002362e  jb      loc_1800236F4
0x180023634  lea     rcx, [rax+1]
0x180023638  cmp     rcx, [rdi+40h]
0x18002363c  ja      short loc_180023648
0x18002363e  mov     ebx, 0C000000Dh
0x180023643  jmp     loc_1800236E2
0x180023648  mov     r12, [rdi+48h]
0x18002364c  dec     r12
0x18002364f  lea     r9, [r12+rcx]
0x180023653  cmp     r9, rcx
0x180023656  jnb     short loc_180023662
0x180023658  mov     ebx, 0C0000095h
0x18002365d  jmp     loc_1800236E2
0x180023662  mov     rdx, [rdi+30h]; ullMultiplier
0x180023666  lea     r8, [rbp+pullResult]; pullResult
0x18002366a  mov     rcx, [rdi+40h]; ullMultiplicand
0x18002366e  mov     [rbp+Size], 0
0x180023676  call    ULongLongMult
0x18002367b  test    eax, eax
0x18002367d  js      short loc_180023658
0x18002367f  mov     rdx, [rdi+30h]; ullMultiplier
0x180023683  lea     r8, [rbp+Size]; pullResult
0x180023687  not     r12
0x18002368a  and     r12, r9
0x18002368d  mov     rcx, r12; ullMultiplicand
0x180023690  call    ULongLongMult
0x180023695  test    eax, eax
0x180023697  js      short loc_180023658
0x180023699  mov     r8, [rdi+50h]; Ptr
0x18002369d  xor     edx, edx; Flags
0x18002369f  mov     r13, [rbp+Size]
0x1800236a3  mov     rcx, [rdi+28h]; Heap
0x1800236a7  test    r8, r8
0x1800236aa  jnz     short loc_1800236CC
0x1800236ac  mov     r8, r13; Size
0x1800236af  call    cs:__imp_RtlAllocateHeap
0x1800236b5  mov     rbx, rax
0x1800236b8  test    rax, rax
0x1800236bb  jz      short loc_1800236D8
0x1800236bd  mov     r8, r13; Size
0x1800236c0  xor     edx, edx; Val
0x1800236c2  mov     rcx, rax; void *
0x1800236c5  call    memset_0
0x1800236ca  jmp     short loc_1800236D8
0x1800236cc  mov     r9, r13; Size
0x1800236cf  call    cs:__imp_RtlReAllocateHeap
0x1800236d5  mov     rbx, rax
0x1800236d8  test    rbx, rbx
0x1800236db  jnz     short loc_1800236E8
0x1800236dd  mov     ebx, 0C0000017h
0x1800236e2  test    ebx, ebx
0x1800236e4  js      short loc_18002374A
0x1800236e6  jmp     short loc_180023739
0x1800236e8  mov     rax, [rbp+arg_10]
0x1800236ec  mov     [rdi+50h], rbx
0x1800236f0  mov     [rdi+40h], r12
0x1800236f4  mov     rcx, [rdi+30h]; ullMultiplicand
0x1800236f8  lea     r8, [rbp+Size]; pullResult
0x1800236fc  mov     rdx, rax; ullMultiplier
0x1800236ff  mov     [rbp+Size], 0
0x180023707  call    ULongLongMult
0x18002370c  test    eax, eax
0x18002370e  js      short loc_180023745
0x180023710  mov     rdx, [rbp+Size]
0x180023714  add     rdx, [rdi+50h]
0x180023718  cmp     rdx, [rdi+50h]
0x18002371c  jb      short loc_180023745
0x18002371e  movups  xmm0, [rbp+var_38]
0x180023722  movups  xmm1, [rbp+var_28]
0x180023726  movups  xmmword ptr [rdx], xmm0
0x180023729  movups  xmm0, [rbp+var_18]
0x18002372d  movups  xmmword ptr [rdx+10h], xmm1
0x180023731  movups  xmmword ptr [rdx+20h], xmm0
0x180023735  inc     qword ptr [rdi+38h]
0x180023739  xor     esi, esi
0x18002373b  xor     r14d, r14d
0x18002373e  xor     r15d, r15d
0x180023741  xor     ebx, ebx
0x180023743  jmp     short loc_180023768
0x180023745  mov     ebx, 0C0000095h
0x18002374a  lea     r9, aFailedToAddCom; "Failed to add com hook"
0x180023751  mov     r8d, 20Dh
0x180023757  lea     rdx, aSecomrouteradd_0; "SeComRouterAddHook"
0x18002375e  mov     ecx, 1
0x180023763  call    AslLogCallPrintf
0x180023768  mov     rcx, rdi; CriticalSection
0x18002376b  call    cs:__imp_RtlLeaveCriticalSection
0x180023771  test    rsi, rsi
0x180023774  jz      short loc_18002378E
0x180023776  mov     rcx, gs:60h
0x18002377f  mov     r8, rsi; P
0x180023782  xor     edx, edx; Flags
0x180023784  mov     rcx, [rcx+30h]; HeapHandle
0x180023788  call    cs:__imp_RtlFreeHeap
0x18002378e  test    r14, r14
0x180023791  jz      short loc_1800237AB
0x180023793  mov     rcx, gs:60h
0x18002379c  mov     r8, r14; P
0x18002379f  xor     edx, edx; Flags
0x1800237a1  mov     rcx, [rcx+30h]; HeapHandle
0x1800237a5  call    cs:__imp_RtlFreeHeap
0x1800237ab  test    r15, r15
0x1800237ae  jz      short loc_1800237C8
0x1800237b0  mov     rcx, gs:60h
0x1800237b9  mov     r8, r15; P
0x1800237bc  xor     edx, edx; Flags
0x1800237be  mov     rcx, [rcx+30h]; HeapHandle
0x1800237c2  call    cs:__imp_RtlFreeHeap
0x1800237c8  mov     eax, ebx
0x1800237ca  mov     rbx, [rsp+60h+arg_8]
0x1800237d2  add     rsp, 60h
0x1800237d6  pop     r15
0x1800237d8  pop     r14
0x1800237da  pop     r13
0x1800237dc  pop     r12
0x1800237de  pop     rdi
0x1800237df  pop     rsi
0x1800237e0  pop     rbp
0x1800237e1  retn
```
