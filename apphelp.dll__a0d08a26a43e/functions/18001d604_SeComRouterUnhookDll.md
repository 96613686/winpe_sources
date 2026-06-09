# SeComRouterUnhookDll

- ea: `0x18001d604`
- end: `0x18001da95`
- name: `SeComRouterUnhookDll`
- size: `1169`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d190`

## callees

- `0x18000f114`
- `0x18001d604`
- `0x18001df40`
- `0x180024a80`
- `0x18005764c`
- `0x180059169`
- `0x180059175`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001d6db`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d6db`
- `ntdll!RtlEnterCriticalSection` at `0x18001d61d`
- `ntdll!RtlEnterCriticalSection` at `0x18001d61d`
- `ntdll!RtlReAllocateHeap` at `0x18001d903`
- `ntdll!RtlReAllocateHeap` at `0x18001da8a`
- `ntdll!RtlReAllocateHeap` at `0x18001d903`
- `ntdll!RtlReAllocateHeap` at `0x18001da8a`
- `ntdll!RtlAllocateHeap` at `0x18001d8ca`
- `ntdll!RtlAllocateHeap` at `0x18001da4e`
- `ntdll!RtlAllocateHeap` at `0x18001d8ca`
- `ntdll!RtlAllocateHeap` at `0x18001da4e`

## string_xrefs

- `0x18001d73d`: `SeComRouterUnhookDll`
- `0x18001d79f`: `SeComRouterUnhookDll`
- `0x18001d72b`: `Cleanup of COM Interface Map on unload of %S`
- `0x18001d78d`: `Cleanup of COM HookedObjects on unload of %S`

## pseudocode

```c
__int64 __fastcall SeComRouterUnhookDll(PRTL_CRITICAL_SECTION CriticalSection, __int64 a2)
{
  unsigned __int64 LockSemaphore; // rdi
  unsigned __int64 v5; // rcx
  _QWORD *v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  ULONG_PTR v10; // rdi
  char *v11; // rcx
  char *v12; // r8
  __int64 v13; // r8
  __int64 v14; // rax
  HANDLE OwningThread; // rcx
  ULONGLONG v17; // rcx
  void *v18; // r14
  HANDLE v19; // rcx
  char *v20; // rcx
  char *v21; // r14
  bool v22; // zf
  char *v23; // rsi
  HANDLE v24; // rcx
  ULONGLONG v25; // rcx
  ULONG_PTR SpinCount; // r14
  ULONGLONG v27; // rdx
  ULONG_PTR v28; // r14
  void *v29; // r8
  void *v30; // rcx
  PVOID v31; // rax
  PVOID Heap; // rsi
  ULONG_PTR v33; // rsi
  HANDLE v34; // rcx
  char *v35; // rcx
  ULONG_PTR v36; // rcx
  ULONGLONG DebugInfo; // rsi
  ULONGLONG v38; // rdx
  struct _RTL_CRITICAL_SECTION_DEBUG *v39; // rsi
  HANDLE v40; // r8
  HANDLE v41; // rcx
  PVOID v42; // rax
  PVOID v43; // r14
  ULONGLONG pullResult; // [rsp+60h] [rbp+30h] BYREF
  ULONGLONG Size; // [rsp+70h] [rbp+40h] BYREF

  RtlEnterCriticalSection(CriticalSection);
  LockSemaphore = (unsigned __int64)CriticalSection[2].LockSemaphore;
  while ( (--LockSemaphore & 0x8000000000000000uLL) == 0LL )
  {
    v6 = 0;
    if ( (HANDLE)LockSemaphore < CriticalSection[2].LockSemaphore )
    {
      pullResult = 0;
      v9 = (unsigned __int64)CriticalSection[2].OwningThread * LockSemaphore;
      if ( !is_mul_ok((unsigned __int64)CriticalSection[2].OwningThread, LockSemaphore)
        || (v5 = *(_QWORD *)&CriticalSection[3].LockCount, v6 = (_QWORD *)(v5 + v9), v5 + v9 < v5) )
      {
        v6 = 0;
      }
    }
    if ( (unsigned int)SeUtilsInDll(a2, *v6) || (unsigned int)SeUtilsInDll(v7, *(_QWORD *)(v8 + 16)) )
    {
      if ( (HANDLE)LockSemaphore < CriticalSection[2].LockSemaphore )
      {
        OwningThread = CriticalSection[2].OwningThread;
        pullResult = 0;
        if ( ULongLongMult((ULONGLONG)OwningThread, LockSemaphore, &pullResult) >= 0 )
        {
          v17 = *(_QWORD *)&CriticalSection[3].LockCount;
          v18 = (void *)(v17 + pullResult);
          if ( v17 + pullResult >= v17 )
          {
            v22 = (char *)CriticalSection[2].LockSemaphore + ~LockSemaphore == 0;
            v23 = (char *)CriticalSection[2].LockSemaphore + ~LockSemaphore;
            Size = (ULONGLONG)v23;
            if ( !v22 )
            {
              if ( ULongLongMult((ULONGLONG)v23, (ULONGLONG)CriticalSection[2].OwningThread, &Size) < 0 )
                goto LABEL_21;
              v24 = CriticalSection[2].OwningThread;
              pullResult = 0;
              if ( ULongLongMult((ULONGLONG)v24, LockSemaphore + 1, &pullResult) < 0 )
                goto LABEL_21;
              v25 = *(_QWORD *)&CriticalSection[3].LockCount;
              if ( v25 + pullResult < v25 )
                goto LABEL_21;
              v23 = (char *)Size;
              memmove_0(v18, (const void *)(v25 + pullResult), Size);
            }
            memset_0(&v23[(_QWORD)v18], 0, (size_t)CriticalSection[2].OwningThread);
            if ( --CriticalSection[2].LockSemaphore > (HANDLE)0x10 )
            {
              SpinCount = CriticalSection[2].SpinCount;
              v27 = (ULONGLONG)CriticalSection[2].OwningThread;
              if ( v27 * SpinCount >= 0x400 && CriticalSection[2].LockSemaphore < (HANDLE)(SpinCount >> 2) )
              {
                pullResult = 0;
                if ( ULongLongMult(SpinCount, v27, &Size) >= 0 )
                {
                  v28 = SpinCount >> 1;
                  if ( ULongLongMult(v28, (ULONGLONG)CriticalSection[2].OwningThread, &pullResult) >= 0 )
                  {
                    v29 = *(void **)&CriticalSection[3].LockCount;
                    v30 = *(void **)&CriticalSection[2].LockCount;
                    if ( v29 )
                    {
                      Heap = RtlReAllocateHeap(v30, 0, v29, pullResult);
                    }
                    else
                    {
                      v31 = RtlAllocateHeap(v30, 0, pullResult);
                      Heap = v31;
                      if ( v31 )
                        memset_0(v31, 0, pullResult);
                    }
                    if ( Heap )
                    {
                      *(_QWORD *)&CriticalSection[3].LockCount = Heap;
                      CriticalSection[2].SpinCount = v28;
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_21:
      AslLogCallPrintf(
        3,
        "SeComRouterUnhookDll",
        608,
        "Cleanup of COM Interface Map on unload of %S",
        *(const wchar_t **)(a2 + 80));
    }
  }
  v10 = CriticalSection[3].SpinCount;
  while ( (--v10 & 0x8000000000000000uLL) == 0LL )
  {
    v12 = 0;
    if ( v10 < CriticalSection[3].SpinCount )
    {
      pullResult = 0;
      v14 = (ULONG_PTR)CriticalSection[3].LockSemaphore * v10;
      if ( !is_mul_ok((unsigned __int64)CriticalSection[3].LockSemaphore, v10)
        || (v11 = (char *)CriticalSection[4].OwningThread, v12 = &v11[v14], &v11[v14] < v11) )
      {
        v12 = 0;
      }
    }
    if ( (unsigned int)SeUtilsInDll(a2, *((_QWORD *)v12 + 1)) )
    {
      SepComRouterHookedObjectDelete(v13);
      if ( v10 < CriticalSection[3].SpinCount )
      {
        v19 = CriticalSection[3].LockSemaphore;
        pullResult = 0;
        if ( ULongLongMult((ULONGLONG)v19, v10, &pullResult) >= 0 )
        {
          v20 = (char *)CriticalSection[4].OwningThread;
          v21 = &v20[pullResult];
          if ( &v20[pullResult] >= v20 )
          {
            v22 = CriticalSection[3].SpinCount + ~v10 == 0;
            v33 = CriticalSection[3].SpinCount + ~v10;
            Size = v33;
            if ( !v22 )
            {
              if ( ULongLongMult(v33, (ULONGLONG)CriticalSection[3].LockSemaphore, &Size) < 0 )
                goto LABEL_24;
              v34 = CriticalSection[3].LockSemaphore;
              pullResult = 0;
              if ( ULongLongMult((ULONGLONG)v34, v10 + 1, &pullResult) < 0 )
                goto LABEL_24;
              v35 = (char *)CriticalSection[4].OwningThread;
              if ( &v35[pullResult] < v35 )
                goto LABEL_24;
              v33 = Size;
              memmove_0(v21, &v35[pullResult], Size);
            }
            memset_0(&v21[v33], 0, (size_t)CriticalSection[3].LockSemaphore);
            v36 = --CriticalSection[3].SpinCount;
            if ( v36 > 0x10 )
            {
              DebugInfo = (ULONGLONG)CriticalSection[4].DebugInfo;
              v38 = (ULONGLONG)CriticalSection[3].LockSemaphore;
              if ( v38 * DebugInfo >= 0x400 && v36 < DebugInfo >> 2 )
              {
                pullResult = 0;
                if ( ULongLongMult(DebugInfo, v38, &Size) >= 0 )
                {
                  v39 = (struct _RTL_CRITICAL_SECTION_DEBUG *)(DebugInfo >> 1);
                  if ( ULongLongMult((ULONGLONG)v39, (ULONGLONG)CriticalSection[3].LockSemaphore, &pullResult) >= 0 )
                  {
                    v40 = CriticalSection[4].OwningThread;
                    v41 = CriticalSection[3].OwningThread;
                    if ( v40 )
                    {
                      v43 = RtlReAllocateHeap(v41, 0, v40, pullResult);
                    }
                    else
                    {
                      v42 = RtlAllocateHeap(v41, 0, pullResult);
                      v43 = v42;
                      if ( v42 )
                        memset_0(v42, 0, pullResult);
                    }
                    if ( v43 )
                    {
                      CriticalSection[4].OwningThread = v43;
                      CriticalSection[4].DebugInfo = v39;
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_24:
      AslLogCallPrintf(
        3,
        "SeComRouterUnhookDll",
        624,
        "Cleanup of COM HookedObjects on unload of %S",
        *(const wchar_t **)(a2 + 80));
    }
  }
  RtlLeaveCriticalSection(CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x18001d604  mov     [rsp-28h+arg_8], rbx
0x18001d609  push    rbp
0x18001d60a  push    rsi
0x18001d60b  push    rdi
0x18001d60c  push    r13
0x18001d60e  push    r14
0x18001d610  mov     rbp, rsp
0x18001d613  sub     rsp, 30h
0x18001d617  mov     r13, rdx
0x18001d61a  mov     rbx, rcx
0x18001d61d  call    cs:__imp_RtlEnterCriticalSection
0x18001d623  mov     rdi, [rbx+68h]
0x18001d627  jmp     short loc_18001D660
0x18001d629  mov     rcx, [rbx+80h]
0x18001d630  lea     r8, [rcx+rax]
0x18001d634  cmp     r8, rcx
0x18001d637  jnb     short loc_18001D63C
0x18001d639  xor     r8d, r8d
0x18001d63c  mov     rdx, [r8]
0x18001d63f  mov     rcx, r13
0x18001d642  call    SeUtilsInDll
0x18001d647  test    eax, eax
0x18001d649  jnz     loc_18001D7B5
0x18001d64f  mov     rdx, [r8+10h]
0x18001d653  call    SeUtilsInDll
0x18001d658  test    eax, eax
0x18001d65a  jnz     loc_18001D7B5
0x18001d660  sub     rdi, 1
0x18001d664  js      short loc_18001D681
0x18001d666  xor     r8d, r8d
0x18001d669  cmp     rdi, [rbx+68h]
0x18001d66d  jnb     short loc_18001D63C
0x18001d66f  mov     rax, rdi
0x18001d672  mov     [rbp+pullResult], r8
0x18001d676  mul     qword ptr [rbx+60h]
0x18001d67a  test    rdx, rdx
0x18001d67d  jnz     short loc_18001D639
0x18001d67f  jmp     short loc_18001D629
0x18001d681  mov     rdi, [rbx+98h]
0x18001d688  jmp     short loc_18001D6B1
0x18001d68a  mov     rcx, [rbx+0B0h]
0x18001d691  lea     r8, [rax+rcx]
0x18001d695  cmp     r8, rcx
0x18001d698  jnb     short loc_18001D69D
0x18001d69a  xor     r8d, r8d
0x18001d69d  mov     rdx, [r8+8]
0x18001d6a1  mov     rcx, r13
0x18001d6a4  call    SeUtilsInDll
0x18001d6a9  test    eax, eax
0x18001d6ab  jnz     loc_18001D90E
0x18001d6b1  sub     rdi, 1
0x18001d6b5  js      short loc_18001D6D8
0x18001d6b7  xor     r8d, r8d
0x18001d6ba  cmp     rdi, [rbx+98h]
0x18001d6c1  jnb     short loc_18001D69D
0x18001d6c3  mov     rax, rdi
0x18001d6c6  mov     [rbp+pullResult], r8
0x18001d6ca  mul     qword ptr [rbx+90h]
0x18001d6d1  test    rdx, rdx
0x18001d6d4  jnz     short loc_18001D69A
0x18001d6d6  jmp     short loc_18001D68A
0x18001d6d8  mov     rcx, rbx; CriticalSection
0x18001d6db  call    cs:__imp_RtlLeaveCriticalSection
0x18001d6e1  mov     rbx, [rsp+30h+arg_8]
0x18001d6e6  xor     eax, eax
0x18001d6e8  add     rsp, 30h
0x18001d6ec  pop     r14
0x18001d6ee  pop     r13
0x18001d6f0  pop     rdi
0x18001d6f1  pop     rsi
0x18001d6f2  pop     rbp
0x18001d6f3  retn
0x18001d6f4  mov     rcx, [rbx+60h]; ullMultiplicand
0x18001d6f8  lea     r8, [rbp+pullResult]; pullResult
0x18001d6fc  mov     rdx, rdi; ullMultiplier
0x18001d6ff  mov     [rbp+pullResult], 0
0x18001d707  call    ULongLongMult
0x18001d70c  test    eax, eax
0x18001d70e  js      short loc_18001D727
0x18001d710  mov     rcx, [rbx+80h]
0x18001d717  mov     r14, [rbp+pullResult]
0x18001d71b  add     r14, rcx
0x18001d71e  cmp     r14, rcx
0x18001d721  jnb     loc_18001D7C4
0x18001d727  mov     rax, [r13+50h]
0x18001d72b  lea     r9, aCleanupOfComIn; "Cleanup of COM Interface Map on unload "...
0x18001d732  mov     r8d, 260h
0x18001d738  mov     [rsp+30h+var_10], rax
0x18001d73d  lea     rdx, aSecomrouterunh; "SeComRouterUnhookDll"
0x18001d744  mov     ecx, 3
0x18001d749  call    AslLogCallPrintf
0x18001d74e  jmp     loc_18001D660
0x18001d753  mov     rcx, [rbx+90h]; ullMultiplicand
0x18001d75a  lea     r8, [rbp+pullResult]; pullResult
0x18001d75e  mov     rdx, rdi; ullMultiplier
0x18001d761  mov     [rbp+pullResult], 0
0x18001d769  call    ULongLongMult
0x18001d76e  test    eax, eax
0x18001d770  js      short loc_18001D789
0x18001d772  mov     rcx, [rbx+0B0h]
0x18001d779  mov     r14, [rbp+pullResult]
0x18001d77d  add     r14, rcx
0x18001d780  cmp     r14, rcx
0x18001d783  jnb     loc_18001D928
0x18001d789  mov     rax, [r13+50h]
0x18001d78d  lea     r9, aCleanupOfComHo; "Cleanup of COM HookedObjects on unload "...
0x18001d794  mov     r8d, 270h
0x18001d79a  mov     [rsp+30h+var_10], rax
0x18001d79f  lea     rdx, aSecomrouterunh; "SeComRouterUnhookDll"
0x18001d7a6  mov     ecx, 3
0x18001d7ab  call    AslLogCallPrintf
0x18001d7b0  jmp     loc_18001D6B1
0x18001d7b5  cmp     rdi, [rbx+68h]
0x18001d7b9  jnb     loc_18001D727
0x18001d7bf  jmp     loc_18001D6F4
0x18001d7c4  mov     rsi, rdi
0x18001d7c7  not     rsi
0x18001d7ca  add     rsi, [rbx+68h]
0x18001d7ce  mov     [rbp+Size], rsi
0x18001d7d2  jz      short loc_18001D833
0x18001d7d4  mov     rdx, [rbx+60h]; ullMultiplier
0x18001d7d8  lea     r8, [rbp+Size]; pullResult
0x18001d7dc  mov     rcx, rsi; ullMultiplicand
0x18001d7df  call    ULongLongMult
0x18001d7e4  test    eax, eax
0x18001d7e6  js      loc_18001D727
0x18001d7ec  mov     rcx, [rbx+60h]; ullMultiplicand
0x18001d7f0  lea     rdx, [rdi+1]; ullMultiplier
0x18001d7f4  lea     r8, [rbp+pullResult]; pullResult
0x18001d7f8  mov     [rbp+pullResult], 0
0x18001d800  call    ULongLongMult
0x18001d805  test    eax, eax
0x18001d807  js      loc_18001D727
0x18001d80d  mov     rcx, [rbx+80h]
0x18001d814  mov     rdx, [rbp+pullResult]
0x18001d818  add     rdx, rcx; Src
0x18001d81b  cmp     rdx, rcx
0x18001d81e  jb      loc_18001D727
0x18001d824  mov     rsi, [rbp+Size]
0x18001d828  mov     rcx, r14; void *
0x18001d82b  mov     r8, rsi; Size
0x18001d82e  call    memmove_0
0x18001d833  mov     r8, [rbx+60h]; Size
0x18001d837  lea     rcx, [r14+rsi]; void *
0x18001d83b  xor     edx, edx; Val
0x18001d83d  call    memset_0
0x18001d842  dec     qword ptr [rbx+68h]
0x18001d846  cmp     qword ptr [rbx+68h], 10h
0x18001d84b  jbe     loc_18001D727
0x18001d851  mov     r14, [rbx+70h]
0x18001d855  mov     rdx, [rbx+60h]; ullMultiplier
0x18001d859  mov     rax, r14
0x18001d85c  imul    rax, rdx
0x18001d860  cmp     rax, 400h
0x18001d866  jb      loc_18001D727
0x18001d86c  mov     rax, r14
0x18001d86f  shr     rax, 2
0x18001d873  cmp     [rbx+68h], rax
0x18001d877  jnb     loc_18001D727
0x18001d87d  lea     r8, [rbp+Size]; pullResult
0x18001d881  mov     [rbp+pullResult], 0
0x18001d889  mov     rcx, r14; ullMultiplicand
0x18001d88c  call    ULongLongMult
0x18001d891  test    eax, eax
0x18001d893  js      loc_18001D727
0x18001d899  mov     rdx, [rbx+60h]; ullMultiplier
0x18001d89d  lea     r8, [rbp+pullResult]; pullResult
0x18001d8a1  shr     r14, 1
0x18001d8a4  mov     rcx, r14; ullMultiplicand
0x18001d8a7  call    ULongLongMult
0x18001d8ac  test    eax, eax
0x18001d8ae  js      loc_18001D727
0x18001d8b4  mov     r8, [rbx+80h]; Ptr
0x18001d8bb  xor     edx, edx; Flags
0x18001d8bd  mov     rcx, [rbx+58h]; Heap
0x18001d8c1  test    r8, r8
0x18001d8c4  jnz     short loc_18001D8FF
0x18001d8c6  mov     r8, [rbp+pullResult]; Size
0x18001d8ca  call    cs:__imp_RtlAllocateHeap
0x18001d8d0  mov     rsi, rax
0x18001d8d3  test    rax, rax
0x18001d8d6  jz      short loc_18001D8E6
0x18001d8d8  mov     r8, [rbp+pullResult]; Size
0x18001d8dc  xor     edx, edx; Val
0x18001d8de  mov     rcx, rax; void *
0x18001d8e1  call    memset_0
0x18001d8e6  test    rsi, rsi
0x18001d8e9  jz      loc_18001D727
0x18001d8ef  mov     [rbx+80h], rsi
0x18001d8f6  mov     [rbx+70h], r14
0x18001d8fa  jmp     loc_18001D727
0x18001d8ff  mov     r9, [rbp+pullResult]; Size
0x18001d903  call    cs:__imp_RtlReAllocateHeap
0x18001d909  mov     rsi, rax
0x18001d90c  jmp     short loc_18001D8E6
0x18001d90e  mov     rcx, r8
0x18001d911  call    SepComRouterHookedObjectDelete
0x18001d916  cmp     rdi, [rbx+98h]
0x18001d91d  jnb     loc_18001D789
0x18001d923  jmp     loc_18001D753
0x18001d928  mov     rsi, rdi
0x18001d92b  not     rsi
0x18001d92e  add     rsi, [rbx+98h]
0x18001d935  mov     [rbp+Size], rsi
0x18001d939  jz      short loc_18001D9A0
0x18001d93b  mov     rdx, [rbx+90h]; ullMultiplier
0x18001d942  lea     r8, [rbp+Size]; pullResult
0x18001d946  mov     rcx, rsi; ullMultiplicand
0x18001d949  call    ULongLongMult
0x18001d94e  test    eax, eax
0x18001d950  js      loc_18001D789
0x18001d956  mov     rcx, [rbx+90h]; ullMultiplicand
0x18001d95d  lea     rdx, [rdi+1]; ullMultiplier
0x18001d961  lea     r8, [rbp+pullResult]; pullResult
0x18001d965  mov     [rbp+pullResult], 0
0x18001d96d  call    ULongLongMult
0x18001d972  test    eax, eax
0x18001d974  js      loc_18001D789
0x18001d97a  mov     rcx, [rbx+0B0h]
0x18001d981  mov     rdx, [rbp+pullResult]
0x18001d985  add     rdx, rcx; Src
0x18001d988  cmp     rdx, rcx
0x18001d98b  jb      loc_18001D789
0x18001d991  mov     rsi, [rbp+Size]
0x18001d995  mov     rcx, r14; void *
0x18001d998  mov     r8, rsi; Size
0x18001d99b  call    memmove_0
0x18001d9a0  mov     r8, [rbx+90h]; Size
0x18001d9a7  lea     rcx, [r14+rsi]; void *
0x18001d9ab  xor     edx, edx; Val
0x18001d9ad  call    memset_0
0x18001d9b2  dec     qword ptr [rbx+98h]
0x18001d9b9  mov     rcx, [rbx+98h]
0x18001d9c0  cmp     rcx, 10h
0x18001d9c4  jbe     loc_18001D789
0x18001d9ca  mov     rsi, [rbx+0A0h]
0x18001d9d1  mov     rdx, [rbx+90h]; ullMultiplier
0x18001d9d8  mov     rax, rsi
0x18001d9db  imul    rax, rdx
0x18001d9df  cmp     rax, 400h
0x18001d9e5  jb      loc_18001D789
0x18001d9eb  mov     rax, rsi
0x18001d9ee  shr     rax, 2
0x18001d9f2  cmp     rcx, rax
0x18001d9f5  jnb     loc_18001D789
0x18001d9fb  lea     r8, [rbp+Size]; pullResult
0x18001d9ff  mov     [rbp+pullResult], 0
0x18001da07  mov     rcx, rsi; ullMultiplicand
0x18001da0a  call    ULongLongMult
0x18001da0f  test    eax, eax
0x18001da11  js      loc_18001D789
0x18001da17  mov     rdx, [rbx+90h]; ullMultiplier
0x18001da1e  lea     r8, [rbp+pullResult]; pullResult
0x18001da22  shr     rsi, 1
0x18001da25  mov     rcx, rsi; ullMultiplicand
0x18001da28  call    ULongLongMult
0x18001da2d  test    eax, eax
0x18001da2f  js      loc_18001D789
0x18001da35  mov     r8, [rbx+0B0h]; Ptr
0x18001da3c  xor     edx, edx; Flags
0x18001da3e  mov     rcx, [rbx+88h]; Heap
0x18001da45  test    r8, r8
0x18001da48  jnz     short loc_18001DA86
0x18001da4a  mov     r8, [rbp+pullResult]; Size
0x18001da4e  call    cs:__imp_RtlAllocateHeap
0x18001da54  mov     r14, rax
0x18001da57  test    rax, rax
0x18001da5a  jz      short loc_18001DA6A
0x18001da5c  mov     r8, [rbp+pullResult]; Size
0x18001da60  xor     edx, edx; Val
0x18001da62  mov     rcx, rax; void *
0x18001da65  call    memset_0
0x18001da6a  test    r14, r14
0x18001da6d  jz      loc_18001D789
0x18001da73  mov     [rbx+0B0h], r14
0x18001da7a  mov     [rbx+0A0h], rsi
0x18001da81  jmp     loc_18001D789
0x18001da86  mov     r9, [rbp+pullResult]; Size
0x18001da8a  call    cs:__imp_RtlReAllocateHeap
0x18001da90  mov     r14, rax
0x18001da93  jmp     short loc_18001DA6A
```
