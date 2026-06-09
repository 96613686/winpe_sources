# SeComRouterHookObject

- ea: `0x1800254c8`
- end: `0x180025973`
- name: `SeComRouterHookObject`
- size: `1195`
- prototype: `__int64 __usercall@<rax>(PRTL_CRITICAL_SECTION CriticalSection@<rcx>, __int64, __int64, int)`
- caller_count: `5`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180025150`
- `0x1800253b4`
- `0x180033dc0`
- `0x180053e20`
- `0x1800575b0`

## callees

- `0x18000f114`
- `0x1800252c8`
- `0x1800254c8`
- `0x18002597c`
- `0x180025bfc`
- `0x18002606c`
- `0x180059235`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002594b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002594b`
- `ntdll!RtlEnterCriticalSection` at `0x180025513`
- `ntdll!RtlEnterCriticalSection` at `0x180025513`
- `ntdll!RtlReAllocateHeap` at `0x180025767`
- `ntdll!RtlReAllocateHeap` at `0x180025767`
- `ntdll!_wcsicmp` at `0x1800258b9`
- `ntdll!_wcsicmp` at `0x1800258b9`
- `ntdll!RtlAllocateHeap` at `0x180025747`
- `ntdll!RtlAllocateHeap` at `0x180025747`

## string_xrefs

- `0x18002556f`: `SeComRouterHookObject`
- `0x1800255c2`: `SeComRouterHookObject`
- `0x180025604`: `SeComRouterHookObject`

## pseudocode

```c
__int64 __fastcall SeComRouterHookObject(
        PRTL_CRITICAL_SECTION CriticalSection,
        __int64 *a2,
        wchar_t *a3,
        __int64 *a4,
        const void **a5,
        __int64 a6,
        int a7)
{
  __int64 *v7; // r15
  __int64 v11; // rsi
  const void **v12; // rbx
  unsigned int v13; // ebx
  const char *v14; // rcx
  __int64 v15; // r13
  unsigned int (__fastcall *v16)(const void *, __int64 *, __int64 *); // rax
  __int64 *v17; // rax
  __int128 v18; // xmm6
  ULONG_PTR SpinCount; // r13
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx
  int v21; // r8d
  __int64 *v22; // rax
  __int128 v23; // xmm0
  ULONG_PTR v24; // rcx
  __int64 v25; // rsi
  ULONG_PTR v26; // r8
  unsigned __int64 LockSemaphore; // rcx
  unsigned __int64 v28; // rsi
  unsigned __int128 v29; // rax
  SIZE_T v30; // r15
  HANDLE OwningThread; // r8
  HANDLE v32; // rcx
  PVOID v33; // rax
  PVOID Heap; // rbx
  char *v35; // rcx
  char *v36; // rax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int64 v39; // rax
  HANDLE v40; // rax
  unsigned __int64 v41; // rsi
  __int64 v42; // r9
  __int64 v43; // r13
  _QWORD *v44; // rbx
  unsigned __int64 v45; // rax
  PRTL_CRITICAL_SECTION_DEBUG v46; // rcx
  _QWORD *v47; // rcx
  __int64 v48; // rax
  const wchar_t *v49; // rcx
  int v50; // eax
  _QWORD *v51; // rcx
  __int64 v52; // rax
  _QWORD *v53; // rcx
  __int64 v54; // rax
  __int128 v56; // [rsp+48h] [rbp-41h] BYREF
  __m256i v57; // [rsp+68h] [rbp-21h]
  __int64 v58; // [rsp+D8h] [rbp+4Fh] BYREF
  __int64 *v59; // [rsp+E0h] [rbp+57h]

  v59 = a2;
  v7 = a2;
  v58 = 0;
  memset_0(&v56, 0, 0x40u);
  RtlEnterCriticalSection(CriticalSection);
  v11 = a6;
  v12 = a5;
  if ( a6 || !SepComRouterFindHookedObject(CriticalSection, *a5, (unsigned __int64)a4 & -(__int64)(a3 != 0)) )
  {
    v14 = "Class factory";
    if ( !a7 )
      v14 = "Object";
    AslLogCallPrintf(3, "SeComRouterHookObject", 1181, "New %s! pThis: 0x%p", v14, *v12);
    v15 = *(_QWORD *)*v12;
    a6 = v15;
    if ( (int)SepComRouterPatchFunction(CriticalSection, v15, 0, &SepComRouterQueryInterfaceHook) < 0 )
      AslLogCallPrintf(1, "SeComRouterHookObject", 1228, "Failed to patch QueryInterface hook for %p", *v12);
    if ( (int)SepComRouterPatchFunction(CriticalSection, v15, 2, SepComRouterReleaseHook) < 0 )
      AslLogCallPrintf(1, "SeComRouterHookObject", 1236, "Failed to patch Release hook for %p", *v12);
    if ( !v11 )
    {
      v16 = (unsigned int (__fastcall *)(const void *, __int64 *, __int64 *))SeComRouterLookup(CriticalSection);
      if ( v16 )
      {
        if ( !v16(*v12, &SE_IID_IUnknown, &v58) )
        {
          v11 = v58;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
        }
      }
    }
    v17 = v7;
    if ( !v7 )
      v17 = &SE_CLSID_NULL;
    v18 = *(_OWORD *)v17;
    if ( a3 )
      v57.m256i_i64[0] = DsUtilityDuplicateStringW(a3);
    else
      v57.m256i_i64[0] = 0;
    SpinCount = CriticalSection[3].SpinCount;
    DebugInfo = CriticalSection[4].DebugInfo;
    v21 = a7;
    v22 = a4;
    if ( !a4 )
      v22 = SE_IID_NULL;
    v57.m256i_i32[6] = a7;
    *(_QWORD *)&v56 = v11;
    v23 = *(_OWORD *)v22;
    *((_QWORD *)&v56 + 1) = *v12;
    *(_OWORD *)&v57.m256i_u64[1] = v23;
    if ( SpinCount >= (unsigned __int64)DebugInfo )
    {
      v24 = SpinCount + 1;
      if ( SpinCount + 1 <= (unsigned __int64)DebugInfo )
      {
        v13 = -1073741811;
        goto LABEL_70;
      }
      v25 = *(_QWORD *)&CriticalSection[4].LockCount - 1LL;
      v26 = v25 + v24;
      if ( v25 + v24 < v24
        || (LockSemaphore = (unsigned __int64)CriticalSection[3].LockSemaphore,
            !is_mul_ok((unsigned __int64)DebugInfo, LockSemaphore))
        || (v28 = v26 & ~v25,
            v29 = v28 * (unsigned __int128)LockSemaphore,
            v30 = v28 * LockSemaphore,
            !is_mul_ok(v28, LockSemaphore)) )
      {
        v13 = -1073741675;
        goto LABEL_70;
      }
      OwningThread = CriticalSection[4].OwningThread;
      v32 = CriticalSection[3].OwningThread;
      if ( OwningThread )
      {
        Heap = RtlReAllocateHeap(v32, DWORD2(v29), OwningThread, v30);
      }
      else
      {
        v33 = RtlAllocateHeap(v32, DWORD2(v29), v29);
        Heap = v33;
        if ( v33 )
          memset_0(v33, 0, v30);
      }
      v7 = v59;
      v21 = a7;
      if ( !Heap )
      {
        v13 = -1073741801;
        goto LABEL_70;
      }
      CriticalSection[4].OwningThread = Heap;
      CriticalSection[4].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v28;
    }
    if ( !is_mul_ok((unsigned __int64)CriticalSection[3].LockSemaphore, SpinCount)
      || (v35 = (char *)CriticalSection[4].OwningThread,
          v36 = &v35[(ULONG_PTR)CriticalSection[3].LockSemaphore * SpinCount],
          v36 < v35) )
    {
      v13 = -1073741675;
      goto LABEL_70;
    }
    v37 = *(_OWORD *)&v57.m256i_u64[2];
    *(_OWORD *)v36 = v56;
    v38 = *(_OWORD *)v57.m256i_i8;
    *((_OWORD *)v36 + 1) = v18;
    *((_OWORD *)v36 + 2) = v38;
    *((_OWORD *)v36 + 3) = v37;
    ++CriticalSection[3].SpinCount;
    if ( !v21 )
      goto LABEL_42;
    v39 = SE_IID_IClassFactory - *a4;
    if ( SE_IID_IClassFactory == *a4 )
      v39 = 0x46000000000000C0LL - a4[1];
    if ( v39 )
    {
LABEL_42:
      v40 = CriticalSection[1].OwningThread;
      if ( v40 )
      {
        v41 = 0;
        v42 = SE_CLSID_NULL;
        v43 = a6;
        do
        {
          v44 = 0;
          if ( v41 < (unsigned __int64)v40 )
          {
            v45 = *(_QWORD *)&CriticalSection[1].LockCount * v41;
            if ( !is_mul_ok(*(_QWORD *)&CriticalSection[1].LockCount, v41)
              || (v46 = CriticalSection[2].DebugInfo,
                  v44 = (_QWORD *)((char *)&v46->Type + v45),
                  (PRTL_CRITICAL_SECTION_DEBUG)((char *)v46 + v45) < v46) )
            {
              v44 = 0;
            }
          }
          if ( !a3 && !v44[2] )
          {
            if ( !v7 )
              goto LABEL_63;
            v47 = (_QWORD *)v44[1];
            if ( !v47 )
              goto LABEL_63;
            v48 = *v47 - v42;
            if ( *v47 == v42 )
              v48 = v47[1];
            if ( !v48 )
              goto LABEL_63;
          }
          v49 = (const wchar_t *)v44[2];
          if ( v49 )
          {
            if ( a3 )
            {
              v50 = _wcsicmp(v49, a3);
              v42 = SE_CLSID_NULL;
              if ( !v50 )
                goto LABEL_63;
            }
          }
          v51 = (_QWORD *)v44[1];
          if ( v51 && v7 )
          {
            v52 = *v51 - *v7;
            if ( *v51 == *v7 )
              v52 = v51[1] - v7[1];
            if ( !v52 )
            {
LABEL_63:
              v53 = (_QWORD *)v44[3];
              v54 = *v53 - *a4;
              if ( *v53 == *a4 )
                v54 = v53[1] - a4[1];
              if ( !v54 )
              {
                SepComRouterPatchFunction(CriticalSection, v43, v44[4], v44[5]);
                v42 = SE_CLSID_NULL;
              }
            }
          }
          v40 = CriticalSection[1].OwningThread;
          ++v41;
        }
        while ( v41 < (unsigned __int64)v40 );
      }
    }
    else
    {
      SepComRouterPatchFunction(CriticalSection, a6, 3, &SepComHookCreateInstanceHook);
    }
  }
  v13 = 0;
LABEL_70:
  RtlLeaveCriticalSection(CriticalSection);
  return v13;
}

```

## disassembly

```asm
0x1800254c8  mov     rax, rsp
0x1800254cb  mov     [rax+18h], rbx
0x1800254cf  mov     [rax+10h], rdx
0x1800254d3  push    rbp
0x1800254d4  push    rsi
0x1800254d5  push    rdi
0x1800254d6  push    r12
0x1800254d8  push    r13
0x1800254da  push    r14
0x1800254dc  push    r15
0x1800254de  lea     rbp, [rax-47h]
0x1800254e2  sub     rsp, 90h
0x1800254e9  mov     r15, rdx
0x1800254ec  movaps  xmmword ptr [rax-48h], xmm6
0x1800254f0  xor     edx, edx; Val
0x1800254f2  mov     [rbp+3Fh+arg_0], 0
0x1800254fa  mov     r12, r8
0x1800254fd  mov     rdi, rcx
0x180025500  lea     rcx, [rbp+3Fh+var_80]; void *
0x180025504  mov     r14, r9
0x180025507  lea     r8d, [rdx+40h]; Size
0x18002550b  call    memset_0
0x180025510  mov     rcx, rdi; CriticalSection
0x180025513  call    cs:__imp_RtlEnterCriticalSection
0x180025519  mov     rsi, [rbp+3Fh+arg_28]
0x18002551d  mov     rbx, [rbp+3Fh+arg_20]
0x180025521  test    rsi, rsi
0x180025524  jnz     short loc_180025549
0x180025526  mov     rdx, [rbx]
0x180025529  mov     rax, r12
0x18002552c  neg     rax
0x18002552f  mov     rcx, rdi
0x180025532  sbb     r8, r8
0x180025535  and     r8, r14
0x180025538  call    SepComRouterFindHookedObject
0x18002553d  test    rax, rax
0x180025540  jz      short loc_180025549
0x180025542  xor     ebx, ebx
0x180025544  jmp     loc_180025948
0x180025549  cmp     [rbp+3Fh+arg_30], 0
0x18002554d  lea     rax, aObject; "Object"
0x180025554  lea     rcx, aClassFactory; "Class factory"
0x18002555b  mov     r8d, 49Dh
0x180025561  cmovz   rcx, rax
0x180025565  lea     r9, aNewSPthis0xP; "New %s! pThis: 0x%p"
0x18002556c  mov     rax, [rbx]
0x18002556f  lea     rdx, aSecomrouterhoo; "SeComRouterHookObject"
0x180025576  mov     [rsp+0C0h+var_98], rax
0x18002557b  mov     [rsp+0C0h+var_A0], rcx
0x180025580  mov     ecx, 3
0x180025585  call    AslLogCallPrintf
0x18002558a  mov     rax, [rbx]
0x18002558d  lea     r9, SepComRouterQueryInterfaceHook
0x180025594  xor     r8d, r8d
0x180025597  mov     rcx, rdi
0x18002559a  mov     r13, [rax]
0x18002559d  mov     rdx, r13
0x1800255a0  mov     [rbp+3Fh+arg_28], r13
0x1800255a4  call    SepComRouterPatchFunction
0x1800255a9  test    eax, eax
0x1800255ab  jns     short loc_1800255D3
0x1800255ad  mov     rax, [rbx]
0x1800255b0  lea     r9, aFailedToPatchQ; "Failed to patch QueryInterface hook for"...
0x1800255b7  mov     r8d, 4CCh
0x1800255bd  mov     [rsp+0C0h+var_A0], rax
0x1800255c2  lea     rdx, aSecomrouterhoo; "SeComRouterHookObject"
0x1800255c9  mov     ecx, 1
0x1800255ce  call    AslLogCallPrintf
0x1800255d3  lea     r9, SepComRouterReleaseHook
0x1800255da  mov     r8d, 2
0x1800255e0  mov     rdx, r13
0x1800255e3  mov     rcx, rdi
0x1800255e6  call    SepComRouterPatchFunction
0x1800255eb  test    eax, eax
0x1800255ed  jns     short loc_180025615
0x1800255ef  mov     rax, [rbx]
0x1800255f2  lea     r9, aFailedToPatchR; "Failed to patch Release hook for %p"
0x1800255f9  mov     r8d, 4D4h
0x1800255ff  mov     [rsp+0C0h+var_A0], rax
0x180025604  lea     rdx, aSecomrouterhoo; "SeComRouterHookObject"
0x18002560b  mov     ecx, 1
0x180025610  call    AslLogCallPrintf
0x180025615  test    rsi, rsi
0x180025618  jnz     short loc_18002565B
0x18002561a  mov     rdx, [rbx]
0x18002561d  lea     r8, SepComRouterQueryInterfaceHook
0x180025624  mov     rcx, rdi; CriticalSection
0x180025627  call    SeComRouterLookup
0x18002562c  test    rax, rax
0x18002562f  jz      short loc_18002565B
0x180025631  mov     rcx, [rbx]
0x180025634  lea     r8, [rbp+3Fh+arg_0]
0x180025638  lea     rdx, SE_IID_IUnknown
0x18002563f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025644  test    eax, eax
0x180025646  jnz     short loc_18002565B
0x180025648  mov     rsi, [rbp+3Fh+arg_0]
0x18002564c  mov     rcx, rsi
0x18002564f  mov     rax, [rsi]
0x180025652  mov     rax, [rax+10h]
0x180025656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002565b  test    r15, r15
0x18002565e  lea     rcx, SE_CLSID_NULL
0x180025665  mov     rax, r15
0x180025668  cmovz   rax, rcx
0x18002566c  movups  xmm6, xmmword ptr [rax]
0x18002566f  test    r12, r12
0x180025672  jz      short loc_180025682
0x180025674  mov     rcx, r12; Source
0x180025677  call    DsUtilityDuplicateStringW
0x18002567c  mov     qword ptr [rbp+3Fh+var_60], rax
0x180025680  jmp     short loc_18002568A
0x180025682  mov     qword ptr [rbp+3Fh+var_60], 0
0x18002568a  mov     r13, [rdi+98h]
0x180025691  lea     rcx, SE_IID_NULL
0x180025698  mov     rdx, [rdi+0A0h]; Flags
0x18002569f  test    r14, r14
0x1800256a2  mov     r8d, [rbp+3Fh+arg_30]
0x1800256a6  mov     rax, r14
0x1800256a9  cmovz   rax, rcx
0x1800256ad  mov     [rbp+3Fh+var_48], r8d
0x1800256b1  mov     qword ptr [rbp+3Fh+var_80], rsi
0x1800256b5  movups  xmm0, xmmword ptr [rax]
0x1800256b8  mov     rax, [rbx]
0x1800256bb  mov     qword ptr [rbp+3Fh+var_80+8], rax
0x1800256bf  movdqu  [rbp+3Fh+var_60+8], xmm0
0x1800256c4  cmp     r13, rdx
0x1800256c7  jb      loc_180025795
0x1800256cd  lea     rcx, [r13+1]
0x1800256d1  cmp     rcx, rdx
0x1800256d4  ja      short loc_1800256E0
0x1800256d6  mov     ebx, 0C000000Dh
0x1800256db  jmp     loc_18002582F
0x1800256e0  mov     rsi, [rdi+0A8h]
0x1800256e7  dec     rsi
0x1800256ea  lea     r8, [rsi+rcx]
0x1800256ee  cmp     r8, rcx
0x1800256f1  jb      loc_180025826
0x1800256f7  mov     rcx, [rdi+90h]
0x1800256fe  mov     rax, rcx
0x180025701  mov     [rbp+3Fh+var_90], 0
0x180025709  mul     rdx
0x18002570c  test    rdx, rdx
0x18002570f  jnz     loc_180025826
0x180025715  not     rsi
0x180025718  mov     [rbp+3Fh+var_90], rdx
0x18002571c  and     rsi, r8
0x18002571f  mov     rax, rcx
0x180025722  mul     rsi
0x180025725  mov     r15, rax
0x180025728  test    rdx, rdx
0x18002572b  jnz     loc_180025822
0x180025731  mov     r8, [rdi+0B0h]; Ptr
0x180025738  mov     rcx, [rdi+88h]; Heap
0x18002573f  test    r8, r8
0x180025742  jnz     short loc_180025764
0x180025744  mov     r8, rax; Size
0x180025747  call    cs:__imp_RtlAllocateHeap
0x18002574d  mov     rbx, rax
0x180025750  test    rax, rax
0x180025753  jz      short loc_180025770
0x180025755  mov     r8, r15; Size
0x180025758  xor     edx, edx; Val
0x18002575a  mov     rcx, rax; void *
0x18002575d  call    memset_0
0x180025762  jmp     short loc_180025770
0x180025764  mov     r9, r15; Size
0x180025767  call    cs:__imp_RtlReAllocateHeap
0x18002576d  mov     rbx, rax
0x180025770  mov     r15, [rbp+3Fh+arg_8]
0x180025774  mov     r8d, [rbp+3Fh+arg_30]
0x180025778  test    rbx, rbx
0x18002577b  jnz     short loc_180025787
0x18002577d  mov     ebx, 0C0000017h
0x180025782  jmp     loc_18002582F
0x180025787  mov     [rdi+0B0h], rbx
0x18002578e  mov     [rdi+0A0h], rsi
0x180025795  mov     rax, r13
0x180025798  mov     [rbp+3Fh+var_90], 0
0x1800257a0  mul     qword ptr [rdi+90h]
0x1800257a7  test    rdx, rdx
0x1800257aa  jnz     loc_180025943
0x1800257b0  mov     rcx, [rdi+0B0h]
0x1800257b7  add     rax, rcx
0x1800257ba  cmp     rax, rcx
0x1800257bd  jb      loc_180025943
0x1800257c3  movaps  xmm0, [rbp+3Fh+var_80]
0x1800257c7  movaps  xmm1, xmmword ptr [rbp-11h]
0x1800257cb  movups  xmmword ptr [rax], xmm0
0x1800257ce  movaps  xmm0, [rbp+3Fh+var_60]
0x1800257d2  movups  xmmword ptr [rax+10h], xmm6
0x1800257d6  movups  xmmword ptr [rax+20h], xmm0
0x1800257da  movups  xmmword ptr [rax+30h], xmm1
0x1800257de  inc     qword ptr [rdi+98h]
0x1800257e5  test    r8d, r8d
0x1800257e8  jz      short loc_180025838
0x1800257ea  mov     rax, cs:SE_IID_IClassFactory
0x1800257f1  sub     rax, [r14]
0x1800257f4  jnz     short loc_180025801
0x1800257f6  mov     rax, cs:qword_180062498
0x1800257fd  sub     rax, [r14+8]
0x180025801  test    rax, rax
0x180025804  jnz     short loc_180025838
0x180025806  mov     rdx, [rbp+3Fh+arg_28]
0x18002580a  lea     r9, SepComHookCreateInstanceHook
0x180025811  lea     r8d, [rax+3]
0x180025815  mov     rcx, rdi
0x180025818  call    SepComRouterPatchFunction
0x18002581d  jmp     loc_180025542
0x180025822  mov     r15, [rbp+3Fh+arg_8]
0x180025826  mov     r8d, [rbp+3Fh+arg_30]
0x18002582a  mov     ebx, 0C0000095h
0x18002582f  test    ebx, ebx
0x180025831  jns     short loc_1800257E5
0x180025833  jmp     loc_180025948
0x180025838  mov     rax, [rdi+38h]
0x18002583c  test    rax, rax
0x18002583f  jz      loc_180025542
0x180025845  mov     r8, cs:qword_1800623C0
0x18002584c  xor     esi, esi
0x18002584e  mov     r9, cs:SE_CLSID_NULL
0x180025855  mov     r13, [rbp+3Fh+arg_28]
0x180025859  xor     ebx, ebx
0x18002585b  cmp     rsi, rax
0x18002585e  jnb     short loc_18002587B
0x180025860  mov     rax, rsi
0x180025863  mul     qword ptr [rdi+30h]
0x180025867  test    rdx, rdx
0x18002586a  jnz     short loc_180025879
0x18002586c  mov     rcx, [rdi+50h]
0x180025870  lea     rbx, [rcx+rax]
0x180025874  cmp     rbx, rcx
0x180025877  jnb     short loc_18002587B
0x180025879  xor     ebx, ebx
0x18002587b  test    r12, r12
0x18002587e  jnz     short loc_1800258A8
0x180025880  cmp     [rbx+10h], r12
0x180025884  jnz     short loc_1800258A8
0x180025886  test    r15, r15
0x180025889  jz      short loc_1800258F4
0x18002588b  mov     rcx, [rbx+8]
0x18002588f  test    rcx, rcx
0x180025892  jz      short loc_1800258F4
0x180025894  mov     rax, [rcx]
0x180025897  sub     rax, r9
0x18002589a  jnz     short loc_1800258A3
0x18002589c  mov     rax, [rcx+8]
0x1800258a0  sub     rax, r8
0x1800258a3  test    rax, rax
0x1800258a6  jz      short loc_1800258F4
0x1800258a8  mov     rcx, [rbx+10h]; String1
0x1800258ac  test    rcx, rcx
0x1800258af  jz      short loc_1800258D1
0x1800258b1  test    r12, r12
0x1800258b4  jz      short loc_1800258D1
0x1800258b6  mov     rdx, r12; String2
0x1800258b9  call    cs:__imp__wcsicmp
0x1800258bf  mov     r8, cs:qword_1800623C0
0x1800258c6  mov     r9, cs:SE_CLSID_NULL
0x1800258cd  test    eax, eax
0x1800258cf  jz      short loc_1800258F4
0x1800258d1  mov     rcx, [rbx+8]
0x1800258d5  test    rcx, rcx
0x1800258d8  jz      short loc_18002592E
0x1800258da  test    r15, r15
0x1800258dd  jz      short loc_18002592E
0x1800258df  mov     rax, [rcx]
0x1800258e2  sub     rax, [r15]
0x1800258e5  jnz     short loc_1800258EF
0x1800258e7  mov     rax, [rcx+8]
0x1800258eb  sub     rax, [r15+8]
0x1800258ef  test    rax, rax
0x1800258f2  jnz     short loc_18002592E
0x1800258f4  mov     rcx, [rbx+18h]
0x1800258f8  mov     rax, [rcx]
0x1800258fb  sub     rax, [r14]
0x1800258fe  jnz     short loc_180025908
0x180025900  mov     rax, [rcx+8]
0x180025904  sub     rax, [r14+8]
0x180025908  test    rax, rax
0x18002590b  jnz     short loc_18002592E
0x18002590d  mov     r9, [rbx+28h]
0x180025911  mov     rdx, r13
0x180025914  mov     r8, [rbx+20h]
0x180025918  mov     rcx, rdi
0x18002591b  call    SepComRouterPatchFunction
0x180025920  mov     r9, cs:SE_CLSID_NULL
0x180025927  mov     r8, cs:qword_1800623C0
0x18002592e  mov     rax, [rdi+38h]
0x180025932  inc     rsi
0x180025935  cmp     rsi, rax
0x180025938  jb      loc_180025859
0x18002593e  jmp     loc_180025542
0x180025943  mov     ebx, 0C0000095h
0x180025948  mov     rcx, rdi; CriticalSection
0x18002594b  call    cs:__imp_RtlLeaveCriticalSection
0x180025951  lea     r11, [rsp+0C0h+var_30]
0x180025959  mov     eax, ebx
0x18002595b  mov     rbx, [r11+50h]
0x18002595f  movaps  xmm6, xmmword ptr [r11-10h]
  ... truncated ...
```
