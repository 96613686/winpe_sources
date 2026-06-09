# NetSetupApiAdapter::GetObjects(NetSetupTransaction &,NetSetupOperation *,_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,ulong,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong *,_NETSETUP_OBJECT const * *)

- ea: `0x1800096d0`
- end: `0x18000a421`
- name: `?GetObjects@NetSetupApiAdapter@@SAXAEAVNetSetupTransaction@@PEAVNetSetupOperation@@W4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KKPEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@PEAKPEAPEBU_NETSETUP_OBJECT@@@Z`
- size: `3409`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18003a3b0`
- `0x180040500`

## callees

- `0x180007fc8`
- `0x180008150`
- `0x180009440`
- `0x1800096d0`
- `0x18000a430`
- `0x180012830`
- `0x18001e110`
- `0x180032d40`
- `0x180033600`
- `0x18003555c`
- `0x180041650`
- `0x18005097c`
- `0x18005c848`
- `0x1800646b8`
- `0x180064704`
- `0x1800647e0`
- `0x180065035`
- `0x180065056`
- `0x1800673c0`
- `0x1800677f4`
- `0x1800678fc`
- `0x1800679d0`
- `0x1800810a2`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800097f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a1b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800097f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a1b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000979b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000979b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a362`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a376`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a362`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a376`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a3c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009abb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009bc8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009a2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009abb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009b33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009bc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a39b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009bba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a368`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a39b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a3b5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000977d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000977d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0fc`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180009d7f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180009d7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall NetSetupApiAdapter::GetObjects(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _OWORD *a4,
        char a5,
        unsigned int a6,
        __int64 a7,
        unsigned int a8,
        __int64 a9,
        _DWORD *a10,
        _QWORD *a11)
{
  __int64 v15; // rsi
  DWORD v16; // ecx
  unsigned int Value; // eax
  __int64 v18; // rbx
  unsigned __int64 v19; // rdi
  __int64 v20; // rsi
  __int64 v21; // rcx
  __int64 ObjectProvider; // rax
  __int64 v23; // rbx
  volatile signed __int32 *v24; // rdi
  _QWORD *v25; // rsi
  std::_Ref_count_base *v26; // rcx
  __int64 v27; // r14
  volatile signed __int32 *v28; // rbx
  __int64 i; // r8
  unsigned __int64 v30; // rsi
  void ***v31; // r12
  void ***v32; // r13
  HANDLE ProcessHeap; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // r15
  char *v36; // rcx
  char *v37; // rbx
  HANDLE v38; // rax
  _DWORD *v39; // r14
  void **v40; // r12
  SIZE_T v41; // r13
  HANDLE v42; // rax
  _DWORD *v43; // rax
  unsigned __int64 k; // rbx
  _OWORD *v45; // rcx
  __int64 v46; // r13
  _QWORD *v47; // rax
  __int64 v48; // r12
  __int64 v49; // rcx
  SIZE_T v50; // r12
  HANDLE v51; // rax
  void *v52; // rax
  void ***m; // r15
  void **v54; // rsi
  char *v55; // rbx
  char *n; // rdi
  char *ii; // rdi
  volatile signed __int32 *v58; // rbx
  PCONDITION_VARIABLE v59; // rdi
  char *Ptr; // rax
  RTL_SRWLOCK *v61; // rcx
  unsigned __int64 j; // r14
  _QWORD *v63; // rbx
  void **v64; // rcx
  unsigned __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // rax
  unsigned __int64 v68; // r14
  unsigned __int64 v69; // rsi
  unsigned __int64 v70; // rdx
  volatile signed __int32 *v71; // rbx
  void *v72; // rdi
  std::_Ref_count_base *v73; // rcx
  volatile signed __int32 *v74; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v76; // rcx
  __int64 v77; // rax
  __int128 v78; // xmm0
  int v79; // edx
  __int64 v80; // rcx
  _DWORD *v81; // rax
  NetSetup2::Property **v82; // rdi
  NetSetup2::Property *v83; // rbx
  NetSetup2::Property *v84; // rdi
  void *v85; // r12
  HANDLE v86; // rax
  HANDLE v87; // rax
  void *v88; // rbx
  HANDLE v89; // rax
  HANDLE v90; // rax
  __int64 v91; // [rsp+30h] [rbp-D0h]
  char *v92; // [rsp+38h] [rbp-C8h]
  __int128 v93; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v94; // [rsp+50h] [rbp-B0h]
  _QWORD *v95; // [rsp+58h] [rbp-A8h]
  _DWORD *v96; // [rsp+60h] [rbp-A0h]
  __int64 v97; // [rsp+68h] [rbp-98h]
  _BYTE pExceptionObject[208]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v99; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v100; // [rsp+148h] [rbp+48h] BYREF
  void ***v101; // [rsp+150h] [rbp+50h] BYREF
  void *v102; // [rsp+158h] [rbp+58h] BYREF
  void **v103; // [rsp+160h] [rbp+60h] BYREF
  void *Block[4]; // [rsp+170h] [rbp+70h] BYREF
  volatile signed __int32 *v105; // [rsp+190h] [rbp+90h]
  _QWORD *v106; // [rsp+1A0h] [rbp+A0h] BYREF
  volatile signed __int32 *v107; // [rsp+1A8h] [rbp+A8h]
  void *v108[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v109; // [rsp+1C0h] [rbp+C0h]
  PCONDITION_VARIABLE ConditionVariable[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v111; // [rsp+1D8h] [rbp+D8h]
  __int64 v112; // [rsp+1E0h] [rbp+E0h]
  char v113; // [rsp+1E8h] [rbp+E8h]
  _QWORD v114[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v115; // [rsp+200h] [rbp+100h]

  v97 = -2;
  v100 = a8;
  v99 = a9;
  v96 = a10;
  v95 = a11;
  *(_OWORD *)ConditionVariable = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v15 = 0;
  v16 = *(_DWORD *)(a1 + 856);
  if ( v16 != -1 )
  {
    Value = (unsigned int)TlsGetValue(v16);
    if ( Value )
      v15 = Value;
  }
  v18 = *(_QWORD *)(a1 + 904);
  ConditionVariable[0] = (PCONDITION_VARIABLE)v18;
  AcquireSRWLockExclusive((PSRWLOCK)(v18 + 8));
  *(_DWORD *)(v18 + 16) = GetCurrentThreadId();
  while ( 1 )
  {
    if ( !*(_QWORD *)(v18 + 24) )
    {
LABEL_6:
      ConditionVariable[1] = 0;
      LODWORD(v111) = 1;
      HIDWORD(v111) = GetCurrentThreadId();
      v112 = *(_QWORD *)(v18 + 24);
      *(_QWORD *)(v18 + 24) = &ConditionVariable[1];
      goto LABEL_7;
    }
    CurrentThreadId = GetCurrentThreadId();
    v76 = *(_QWORD *)(v18 + 24);
    if ( *(_DWORD *)(v76 + 12) == CurrentThreadId )
      break;
    if ( !v76 || v15 == *(_QWORD *)v76 && v15 )
      goto LABEL_6;
    RtlConditionVariable::SleepInfinite((PCONDITION_VARIABLE)v18, (PSRWLOCK)(v18 + 8));
  }
  ++*(_DWORD *)(v76 + 8);
LABEL_7:
  *(_DWORD *)(v18 + 16) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)(v18 + 8));
  v113 = 1;
  if ( *(_BYTE *)(a1 + 654) && a3 == 7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147019873);
    throw (HResultException *)pExceptionObject;
  }
  v114[0] = a1;
  v114[1] = a2;
  v115 = *(_DWORD *)(a1 + 648);
  v93 = 0;
  v19 = 0;
  v20 = 0;
  v94 = 0;
  if ( a3 == 10 )
  {
    NetSetupReflectedProperty::EnumObjects(v100, v99, &v93);
    v27 = *((_QWORD *)&v93 + 1);
    v91 = *((_QWORD *)&v93 + 1);
LABEL_20:
    if ( v100 )
    {
      Block[0] = (void *)a1;
      Block[1] = &v100;
      Block[2] = &v99;
      std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::pair_NetSetupObjectId_std::shared_ptr_INetSetupObject___________lambda_2a78eff69415bb7ebe25c324f1e20a26___(
        &v106,
        v93,
        v27,
        Block);
      std::vector<std::pair<NetSetupObjectId,std::shared_ptr<INetSetupObject>>>::resize(
        &v93,
        0xCCCCCCCCCCCCCCCDuLL * ((__int64)((__int64)v106 - v93) >> 3));
      v27 = *((_QWORD *)&v93 + 1);
      v91 = *((_QWORD *)&v93 + 1);
    }
    goto LABEL_22;
  }
  v21 = a1 + 480;
  if ( a4 )
  {
    LODWORD(Block[0]) = a3;
    *(_OWORD *)((char *)Block + 4) = *a4;
    ObjectProvider = NetSetupObjectProviderFactory::GetObjectProvider(v21, a3);
    (*(void (__fastcall **)(__int64, _QWORD **, _QWORD *, char *))(*(_QWORD *)ObjectProvider + 8LL))(
      ObjectProvider,
      &v106,
      v114,
      (char *)Block + 4);
    if ( v106 )
    {
      std::vector<std::pair<NetSetupObjectId,std::shared_ptr<INetSetupObject>>>::_Reallocate(&v93, 1);
      v23 = *((_QWORD *)&v93 + 1);
      **((_OWORD **)&v93 + 1) = *(_OWORD *)Block;
      *(_DWORD *)(v23 + 16) = Block[2];
      *(_QWORD *)(v23 + 24) = 0;
      *(_QWORD *)(v23 + 32) = 0;
      v24 = v107;
      v25 = v106;
      if ( v107 )
        _InterlockedIncrement(v107 + 2);
      v26 = *(std::_Ref_count_base **)(v23 + 32);
      if ( v26 )
        std::_Ref_count_base::_Decref(v26);
      *(_QWORD *)(v23 + 32) = v24;
      *(_QWORD *)(v23 + 24) = v25;
      v27 = v23 + 40;
      *((_QWORD *)&v93 + 1) = v23 + 40;
      v19 = 0;
    }
    else
    {
      v27 = *((_QWORD *)&v93 + 1);
    }
    v91 = v27;
    v28 = v107;
    if ( v107 )
    {
      if ( _InterlockedExchangeAdd(v107 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
    goto LABEL_20;
  }
  v67 = NetSetupObjectProviderFactory::GetObjectProvider(v21, a3);
  (*(void (__fastcall **)(__int64, void **, _QWORD *, __int64, __int64))(*(_QWORD *)v67 + 64LL))(
    v67,
    &v102,
    v114,
    v99,
    v99 + 56LL * v100);
  (**(void (__fastcall ***)(void *, void **))v102)(v102, (void **)&v101);
  (*(void (__fastcall **)(void *, void ***))(*(_QWORD *)v102 + 8LL))(v102, &v103);
  v27 = *((_QWORD *)&v93 + 1);
  v91 = *((_QWORD *)&v93 + 1);
  while ( !((unsigned __int8 (__fastcall *)(void ***, void **))(*v101)[3])(v101, v103) )
  {
    ((void (__fastcall *)(void ***, void **))**v101)(v101, Block);
    if ( v27 == v20 && !(0xCCCCCCCCCCCCCCCDuLL * ((v20 - v27) >> 3)) )
    {
      v68 = 0xCCCCCCCCCCCCCCCDuLL * ((v27 - (__int64)v93) >> 3);
      if ( v68 == 0x666666666666666LL )
        std::_Xlength_error("vector<T> too long");
      v69 = 0xCCCCCCCCCCCCCCCDuLL * ((v20 - (__int64)v93) >> 3);
      v70 = 0;
      if ( 0x666666666666666LL - (v69 >> 1) >= v69 )
        v70 = v69 + (v69 >> 1);
      if ( v70 < v68 + 1 )
        v70 = v68 + 1;
      std::vector<std::pair<NetSetupObjectId,std::shared_ptr<INetSetupObject>>>::_Reallocate(&v93, v70);
      v20 = v94;
      v27 = *((_QWORD *)&v93 + 1);
    }
    *(_OWORD *)v27 = *(_OWORD *)Block;
    *(_DWORD *)(v27 + 16) = Block[2];
    *(_QWORD *)(v27 + 24) = 0;
    *(_QWORD *)(v27 + 32) = 0;
    v71 = v105;
    v72 = Block[3];
    if ( v105 )
      _InterlockedIncrement(v105 + 2);
    v73 = *(std::_Ref_count_base **)(v27 + 32);
    if ( v73 )
      std::_Ref_count_base::_Decref(v73);
    *(_QWORD *)(v27 + 32) = v71;
    *(_QWORD *)(v27 + 24) = v72;
    v27 += 40;
    v91 = v27;
    *((_QWORD *)&v93 + 1) = v27;
    v74 = v105;
    if ( v105 )
    {
      if ( _InterlockedExchangeAdd(v105 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v74)(v74);
        if ( _InterlockedExchangeAdd(v74 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v74 + 8LL))(v74);
      }
    }
    ((void (__fastcall *)(void ***))(*v101)[1])(v101);
  }
  if ( v103 )
    (*((void (__fastcall **)(void **, __int64))*v103 + 5))(v103, 1);
  if ( v101 )
    ((void (__fastcall *)(void ***, __int64))(*v101)[5])(v101, 1);
  if ( v102 )
    (*(void (__fastcall **)(void *, __int64))(*(_QWORD *)v102 + 16LL))(v102, 1);
  v19 = 0;
  v99 = 0;
  v100 = 0;
LABEL_22:
  *(_OWORD *)v108 = 0;
  v109 = 0;
  std::vector<_NETSETUPPROPKEY>::resize(v108, a6);
  for ( i = 0; (unsigned int)i < a6; i = (unsigned int)(i + 1) )
  {
    v77 = 32LL * (unsigned int)i;
    v78 = *(_OWORD *)(v77 + a7);
    v79 = *(_DWORD *)(v77 + a7 + 16);
    v80 = 5LL * (unsigned int)i;
    v81 = v108[0];
    *(_OWORD *)((char *)v108[0] + 4 * v80) = v78;
    v81[v80 + 4] = v79;
  }
  memset(Block, 0, 24);
  v92 = (char *)v93;
  v30 = 0xCCCCCCCCCCCCCCCDuLL * ((v27 - (__int64)v93) >> 3);
  if ( v30 )
  {
    if ( v30 > 0x1FFFFFFFFFFFFFFFLL )
LABEL_129:
      std::_Xlength_error("vector<T> too long");
    std::vector<std::unique_ptr<NetSetup2::PropertyArray>>::_Reallocate(
      Block,
      0xCCCCCCCCCCCCCCCDuLL * ((v27 - (__int64)v93) >> 3),
      i);
  }
  v31 = (void ***)Block[1];
  v32 = (void ***)Block[0];
  v101 = (void ***)Block[1];
  v102 = Block[0];
  if ( v108[0] != v108[1] )
  {
    for ( j = 0; j < v30; ++j )
    {
      v63 = operator new(0x18u);
      v106 = v63;
      if ( v63 )
      {
        *v63 = 0;
        v63[1] = 0;
        v63[2] = 0;
      }
      else
      {
        v63 = 0;
      }
      if ( v31 == Block[2] )
      {
        std::vector<std::unique_ptr<NetSetup2::PropertyArray>>::_Reserve(Block);
        v31 = (void ***)Block[1];
        v32 = (void ***)Block[0];
        v102 = Block[0];
      }
      *v31++ = (void **)v63;
      v101 = v31;
      Block[1] = v31;
      v64 = v32[j];
      v65 = 0xCCCCCCCCCCCCCCCDuLL * (((char *)v108[1] - (char *)v108[0]) >> 2);
      if ( 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)v64[2] - (_BYTE *)*v64) >> 4) < v65 )
      {
        if ( v65 > 0x555555555555555LL )
          goto LABEL_129;
        std::vector<NetSetup2::Property>::_Reallocate(v64);
      }
      v66 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v92[40 * j + 24] + 32LL))(*(_QWORD *)&v92[40 * j + 24]);
      (*(void (__fastcall **)(__int64, __int64, void **, void **))(*(_QWORD *)v66 + 8LL))(v66, a1, v108, v32[j]);
      if ( (a5 & 4) != 0 )
      {
        v82 = (NetSetup2::Property **)v32[j];
        v83 = *v82;
        v84 = v82[1];
        while ( v83 != v84 )
        {
          ResolveIndirectString(v83);
          v83 = (NetSetup2::Property *)((char *)v83 + 48);
        }
      }
    }
    v27 = v91;
    v19 = 0;
  }
  if ( v95 )
  {
    ProcessHeap = GetProcessHeap();
    v34 = HeapAlloc(ProcessHeap, 0, 32 * v30);
    v35 = v34;
    if ( !v34 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024882);
      throw (HResultException *)pExceptionObject;
    }
    memset_0(v34, 0, 32 * v30);
    while ( v19 < 0xCCCCCCCCCCCCCCCDuLL * ((v27 - (__int64)v92) >> 3) )
    {
      v36 = &v92[40 * v19];
      v37 = (char *)&v35[4 * v19];
      v106 = v37;
      *(_DWORD *)v37 = *(_DWORD *)v36;
      *(_OWORD *)(v37 + 4) = *(_OWORD *)(v36 + 4);
      if ( v108[0] == v108[1] )
      {
        *((_DWORD *)v37 + 5) = 0;
        v38 = GetProcessHeap();
        v39 = HeapAlloc(v38, 0, 0);
      }
      else
      {
        *((_DWORD *)v37 + 5) = -1431655765 * (((_BYTE *)v32[v19][1] - (_BYTE *)*v32[v19]) >> 4);
        v40 = v32[v19];
        v103 = v40;
        v41 = 16 * (((_BYTE *)v40[1] - (_BYTE *)*v40) >> 4);
        v42 = GetProcessHeap();
        v43 = HeapAlloc(v42, 0, v41);
        v39 = v43;
        if ( v43 )
        {
          memset_0(v43, 0, v41);
          for ( k = 0; ; ++k )
          {
            v45 = *v40;
            if ( k >= 0xAAAAAAAAAAAAAAABuLL * (((_BYTE *)v40[1] - (_BYTE *)*v40) >> 4) )
              break;
            v46 = 6 * k;
            *(_OWORD *)&v39[2 * v46] = v45[3 * k];
            v39[2 * v46 + 4] = v45[3 * k + 1];
            v39[2 * v46 + 8] = *((_DWORD *)*v40 + 12 * k + 5);
            v47 = *v40;
            v48 = *((_QWORD *)*v40 + 6 * k + 4);
            v49 = v47[6 * k + 3];
            if ( v49 != v48 )
            {
              v50 = v48 - v49;
              v51 = GetProcessHeap();
              v52 = HeapAlloc(v51, 0, v50);
              *(_QWORD *)&v39[12 * k + 10] = v52;
              if ( !v52 )
              {
                for ( ; k; --k )
                {
                  v85 = *(void **)&v39[12 * k - 2];
                  if ( v85 )
                  {
                    v86 = GetProcessHeap();
                    HeapFree(v86, 0, v85);
                  }
                  v87 = GetProcessHeap();
                  HeapFree(v87, 0, v39);
                }
                v39 = 0;
                break;
              }
              v39[12 * k + 9] = v50;
              memcpy_0(v52, *((const void **)*v103 + 6 * k + 3), v50);
            }
            v40 = v103;
          }
          v37 = (char *)v106;
        }
        else
        {
          v39 = 0;
        }
      }
      *((_QWORD *)v37 + 3) = v39;
      if ( !v39 )
      {
        for ( ; v19; --v19 )
        {
          v88 = (void *)v35[4 * v19 - 1];
          v89 = GetProcessHeap();
          HeapFree(v89, 0, v88);
        }
        v90 = GetProcessHeap();
        HeapFree(v90, 0, v35);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_5aa39ad1df123bafbedc0e28a7fdf70b_Traceguids);
        HResultException::HResultException((HResultException *)pExceptionObject, -2147024882);
        throw (HResultException *)pExceptionObject;
      }
      ++v19;
      v27 = v91;
      v32 = (void ***)v102;
    }
    *v95 = v35;
    v31 = v101;
  }
  *v96 = v30;
  if ( v32 )
  {
    for ( m = v32; m != v31; ++m )
    {
      v54 = *m;
      if ( *m )
      {
        v55 = (char *)*v54;
        if ( *v54 )
        {
          for ( n = (char *)v54[1]; v55 != n; v55 += 48 )
            std::vector<_NETSETUPPROPKEY>::_Tidy(v55 + 24);
          operator delete(*v54);
          *v54 = 0;
          v54[1] = 0;
          v54[2] = 0;
        }
        operator delete(v54);
      }
    }
    operator delete(v32);
  }
  if ( v108[0] )
  {
    operator delete(v108[0]);
    *(_OWORD *)v108 = 0;
    v109 = 0;
  }
  if ( v92 )
  {
    for ( ii = v92; ii != (char *)v27; ii += 40 )
    {
      v58 = (volatile signed __int32 *)*((_QWORD *)ii + 4);
      if ( v58 )
      {
        if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
          if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
        }
      }
    }
    operator delete(v92);
  }
  if ( v113 )
  {
    v113 = 0;
    v59 = ConditionVariable[0];
    AcquireSRWLockExclusive((PSRWLOCK)&ConditionVariable[0][1]);
    LODWORD(v59[2].Ptr) = GetCurrentThreadId();
    --*((_DWORD *)v59[3].Ptr + 2);
    Ptr = (char *)v59[3].Ptr;
    v61 = (RTL_SRWLOCK *)&v59[1];
    if ( *((_DWORD *)Ptr + 2) )
    {
      LODWORD(v59[2].Ptr) = 0;
      ReleaseSRWLockExclusive(v61);
    }
    else
    {
      v59[3].Ptr = *(PVOID *)(Ptr + 16);
      LODWORD(v59[2].Ptr) = 0;
      ReleaseSRWLockExclusive(v61);
      WakeAllConditionVariable(v59);
    }
  }
}

```

## disassembly

```asm
0x1800096d0  push    rbp
0x1800096d2  push    rsi
0x1800096d3  push    rdi
0x1800096d4  push    r12
0x1800096d6  push    r13
0x1800096d8  push    r14
0x1800096da  push    r15
0x1800096dc  lea     rbp, [rsp-110h]
0x1800096e4  sub     rsp, 210h
0x1800096eb  mov     [rsp+240h+var_1D8], 0FFFFFFFFFFFFFFFEh
0x1800096f4  mov     [rsp+240h+arg_8], rbx
0x1800096fc  mov     rax, cs:__security_cookie
0x180009703  xor     rax, rsp
0x180009706  mov     [rbp+140h+var_38], rax
0x18000970d  mov     r12, r9
0x180009710  mov     r14d, r8d
0x180009713  mov     r13, rdx
0x180009716  mov     r15, rcx
0x180009719  mov     eax, [rbp+140h+arg_28]
0x18000971f  mov     dword ptr [rsp+240h+var_208], eax
0x180009723  mov     eax, [rbp+140h+arg_38]
0x180009729  mov     [rbp+140h+var_F8], eax
0x18000972c  mov     rax, [rbp+140h+arg_40]
0x180009733  mov     [rbp+140h+var_100], rax
0x180009737  mov     rax, [rbp+140h+arg_48]
0x18000973e  mov     [rsp+240h+var_1E0], rax
0x180009743  mov     rax, [rbp+140h+arg_50]
0x18000974a  mov     [rsp+240h+var_1E8], rax
0x18000974f  xor     eax, eax
0x180009751  xorps   xmm0, xmm0
0x180009754  movdqu  xmmword ptr [rbp+140h+ConditionVariable], xmm0
0x18000975c  mov     [rbp+140h+var_68], rax
0x180009763  mov     [rbp+140h+var_60], rax
0x18000976a  mov     [rbp+140h+var_58], al
0x180009770  mov     esi, eax
0x180009772  mov     ecx, [rcx+358h]; dwTlsIndex
0x180009778  cmp     ecx, 0FFFFFFFFh
0x18000977b  jz      short loc_180009789
0x18000977d  call    cs:__imp_TlsGetValue
0x180009783  test    eax, eax
0x180009785  jz      short loc_180009789
0x180009787  mov     esi, eax
0x180009789  mov     rbx, [r15+388h]
0x180009790  mov     [rbp+140h+ConditionVariable], rbx
0x180009797  lea     rcx, [rbx+8]; SRWLock
0x18000979b  call    cs:__imp_AcquireSRWLockExclusive
0x1800097a1  call    cs:__imp_GetCurrentThreadId
0x1800097a7  mov     [rbx+10h], eax
0x1800097aa  cmp     qword ptr [rbx+18h], 0
0x1800097af  jnz     loc_18000A0FC
0x1800097b5  mov     [rbp+140h+ConditionVariable+8], 0
0x1800097c0  mov     dword ptr [rbp+140h+var_68], 1
0x1800097ca  call    cs:__imp_GetCurrentThreadId
0x1800097d0  mov     dword ptr [rbp+140h+var_68+4], eax
0x1800097d6  mov     rax, [rbx+18h]
0x1800097da  mov     [rbp+140h+var_60], rax
0x1800097e1  lea     rax, [rbp+140h+ConditionVariable+8]
0x1800097e8  mov     [rbx+18h], rax
0x1800097ec  mov     dword ptr [rbx+10h], 0
0x1800097f3  lea     rcx, [rbx+8]; SRWLock
0x1800097f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800097fd  mov     [rbp+140h+var_58], 1
0x180009804  cmp     byte ptr [r15+28Eh], 0
0x18000980c  jnz     loc_18000A1FC
0x180009812  mov     [rbp+140h+var_50], r15
0x180009819  mov     [rbp+140h+var_48], r13
0x180009820  mov     eax, [r15+288h]
0x180009827  mov     [rbp+140h+var_40], eax
0x18000982d  xorps   xmm0, xmm0
0x180009830  movdqu  [rsp+240h+var_200], xmm0
0x180009836  xor     edi, edi
0x180009838  mov     esi, edi
0x18000983a  mov     [rsp+240h+var_1F0], rdi
0x18000983f  mov     r13, 0CCCCCCCCCCCCCCCDh
0x180009849  cmp     r14d, 0Ah
0x18000984d  jz      loc_18000A1DC
0x180009853  mov     edx, r14d
0x180009856  lea     rcx, [r15+1E0h]
0x18000985d  test    r12, r12
0x180009860  jz      loc_180009EC3
0x180009866  mov     dword ptr [rbp+140h+Block], r14d
0x18000986a  mov     rax, [r12]
0x18000986e  mov     [rbp+140h+Block+4], rax
0x180009872  mov     rax, [r12+8]
0x180009877  mov     [rbp+140h+Block+0Ch], rax
0x18000987b  call    ?GetObjectProvider@NetSetupObjectProviderFactory@@QEBAAEAVINetSetupObjectProvider@@W4_NETSETUP_OBJECT_TYPE@@@Z; NetSetupObjectProviderFactory::GetObjectProvider(_NETSETUP_OBJECT_TYPE)
0x180009880  mov     r10, rax
0x180009883  mov     rcx, [rax]
0x180009886  mov     rax, [rcx+8]
0x18000988a  lea     r9, [rbp+140h+Block+4]
0x18000988e  lea     r8, [rbp+140h+var_50]
0x180009895  lea     rdx, [rbp+140h+var_A0]
0x18000989c  mov     rcx, r10
0x18000989f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a4  nop
0x1800098a5  cmp     [rbp+140h+var_A0], rdi
0x1800098ac  jz      loc_180009EB9
0x1800098b2  mov     edx, 1
0x1800098b7  lea     rcx, [rsp+240h+var_200]
0x1800098bc  call    ?_Reallocate@?$vector@U?$pair@UNetSetupObjectId@@V?$shared_ptr@VINetSetupObject@@@std@@@std@@V?$allocator@U?$pair@UNetSetupObjectId@@V?$shared_ptr@VINetSetupObject@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::pair<NetSetupObjectId,std::shared_ptr<INetSetupObject>>>::_Reallocate(unsigned __int64)
0x1800098c1  mov     rbx, qword ptr [rsp+240h+var_200+8]
0x1800098c6  movups  xmm0, xmmword ptr [rbp+140h+Block]
0x1800098ca  movups  xmmword ptr [rbx], xmm0
0x1800098cd  mov     eax, dword ptr [rbp+140h+var_C0]
0x1800098d3  mov     [rbx+10h], eax
0x1800098d6  mov     [rbx+18h], rdi
0x1800098da  mov     [rbx+20h], rdi
0x1800098de  mov     rdi, [rbp+140h+var_98]
0x1800098e5  mov     rsi, [rbp+140h+var_A0]
0x1800098ec  test    rdi, rdi
0x1800098ef  jz      short loc_1800098F5
0x1800098f1  lock inc dword ptr [rdi+8]
0x1800098f5  mov     rcx, [rbx+20h]; this
0x1800098f9  test    rcx, rcx
0x1800098fc  jnz     loc_18000A1CA
0x180009902  mov     [rbx+20h], rdi
0x180009906  mov     [rbx+18h], rsi
0x18000990a  lea     r14, [rbx+28h]
0x18000990e  mov     qword ptr [rsp+240h+var_200+8], r14
0x180009913  xor     edi, edi
0x180009915  mov     [rsp+240h+var_210], r14
0x18000991a  mov     rbx, [rbp+140h+var_98]
0x180009921  test    rbx, rbx
0x180009924  jz      short loc_180009962
0x180009926  mov     eax, 0FFFFFFFFh
0x18000992b  lock xadd [rbx+8], eax
0x180009930  cmp     eax, 1
0x180009933  jnz     short loc_180009962
0x180009935  mov     rax, [rbx]
0x180009938  mov     rcx, rbx
0x18000993b  mov     rax, [rax]
0x18000993e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009943  mov     eax, 0FFFFFFFFh
0x180009948  lock xadd [rbx+0Ch], eax
0x18000994d  cmp     eax, 1
0x180009950  jnz     short loc_180009962
0x180009952  mov     rax, [rbx]
0x180009955  mov     rcx, rbx
0x180009958  mov     rax, [rax+8]
0x18000995c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009961  nop
0x180009962  cmp     [rbp+140h+var_F8], 0
0x180009966  ja      loc_18000A262
0x18000996c  xorps   xmm0, xmm0
0x18000996f  movdqu  xmmword ptr [rbp+140h+var_90], xmm0
0x180009977  mov     [rbp+140h+var_80], rdi
0x18000997e  mov     ebx, dword ptr [rsp+240h+var_208]
0x180009982  mov     edx, ebx
0x180009984  lea     rcx, [rbp+140h+var_90]
0x18000998b  call    ?resize@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@QEAAX_K@Z; std::vector<_NETSETUPPROPKEY>::resize(unsigned __int64)
0x180009990  nop
0x180009991  mov     r8d, edi
0x180009994  test    ebx, ebx
0x180009996  jnz     loc_18000A13B
0x18000999c  xorps   xmm0, xmm0
0x18000999f  movdqu  xmmword ptr [rbp+140h+Block], xmm0
0x1800099a4  mov     [rbp+140h+var_C0], rdi
0x1800099ab  mov     rsi, r14
0x1800099ae  mov     rcx, qword ptr [rsp+240h+var_200]
0x1800099b3  mov     [rsp+240h+var_208], rcx
0x1800099b8  sub     rsi, rcx
0x1800099bb  sar     rsi, 3
0x1800099bf  imul    rsi, r13
0x1800099c3  test    rsi, rsi
0x1800099c6  jz      short loc_1800099E7
0x1800099c8  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800099d2  cmp     rsi, rax
0x1800099d5  ja      loc_18000A2DF
0x1800099db  mov     rdx, rsi
0x1800099de  lea     rcx, [rbp+140h+Block]
0x1800099e2  call    ?_Reallocate@?$vector@V?$unique_ptr@VPropertyArray@NetSetup2@@U?$default_delete@VPropertyArray@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VPropertyArray@NetSetup2@@U?$default_delete@VPropertyArray@NetSetup2@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<NetSetup2::PropertyArray>>::_Reallocate(unsigned __int64)
0x1800099e7  mov     rax, [rbp+140h+var_90+8]
0x1800099ee  mov     r12, [rbp+140h+Block+8]
0x1800099f2  mov     r13, [rbp+140h+Block]
0x1800099f6  mov     [rbp+140h+var_F0], r12
0x1800099fa  mov     [rbp+140h+var_E8], r13
0x1800099fe  cmp     [rbp+140h+var_90], rax
0x180009a05  jnz     loc_180009DBB
0x180009a0b  cmp     [rsp+240h+var_1E8], 0
0x180009a11  jz      loc_180009C1A
0x180009a17  mov     rbx, rsi
0x180009a1a  shl     rbx, 5
0x180009a1e  call    cs:__imp_GetProcessHeap
0x180009a24  mov     rcx, rax; hHeap
0x180009a27  mov     r8, rbx; dwBytes
0x180009a2a  xor     edx, edx; dwFlags
0x180009a2c  call    cs:__imp_HeapAlloc
0x180009a32  mov     r15, rax
0x180009a35  test    rax, rax
0x180009a38  jz      loc_18000A2EC
0x180009a3e  mov     r8, rbx; Size
0x180009a41  xor     edx, edx; Val
0x180009a43  mov     rcx, rax; void *
0x180009a46  call    memset_0
0x180009a4b  mov     rax, r14
0x180009a4e  mov     rcx, [rsp+240h+var_208]
0x180009a53  sub     rax, rcx
0x180009a56  sar     rax, 3
0x180009a5a  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x180009a64  imul    rax, rdx
0x180009a68  cmp     rdi, rax
0x180009a6b  jnb     loc_180009C0E
0x180009a71  lea     rax, [rdi+rdi*4]
0x180009a75  lea     rcx, [rcx+rax*8]
0x180009a79  mov     rbx, rdi
0x180009a7c  shl     rbx, 5
0x180009a80  add     rbx, r15
0x180009a83  mov     [rbp+140h+var_A0], rbx
0x180009a8a  mov     eax, [rcx]
0x180009a8c  mov     [rbx], eax
0x180009a8e  movups  xmm0, xmmword ptr [rcx+4]
0x180009a92  movups  xmmword ptr [rbx+4], xmm0
0x180009a96  mov     rax, [rbp+140h+var_90+8]
0x180009a9d  cmp     [rbp+140h+var_90], rax
0x180009aa4  jnz     short loc_180009AE2
0x180009aa6  mov     dword ptr [rbx+14h], 0
0x180009aad  call    cs:__imp_GetProcessHeap
0x180009ab3  mov     rcx, rax; hHeap
0x180009ab6  xor     r8d, r8d; dwBytes
0x180009ab9  xor     edx, edx; dwFlags
0x180009abb  call    cs:__imp_HeapAlloc
0x180009ac1  mov     r14, rax
0x180009ac4  mov     [rbx+18h], r14
0x180009ac8  test    r14, r14
0x180009acb  jz      loc_18000A38A
0x180009ad1  inc     rdi
0x180009ad4  mov     r14, [rsp+240h+var_210]
0x180009ad9  mov     r13, [rbp+140h+var_E8]
0x180009add  jmp     loc_180009A4B
0x180009ae2  mov     rax, [r13+rdi*8+0]
0x180009ae7  mov     rcx, [rax+8]
0x180009aeb  sub     rcx, [rax]
0x180009aee  sar     rcx, 4
0x180009af2  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180009afc  imul    rcx, rdx
0x180009b00  mov     [rbx+14h], ecx
0x180009b03  mov     r12, [r13+rdi*8+0]
0x180009b08  mov     [rbp+140h+var_E0], r12
0x180009b0c  mov     rax, [r12+8]
0x180009b11  sub     rax, [r12]
0x180009b15  sar     rax, 4
0x180009b19  imul    rax, rdx
0x180009b1d  lea     r13, [rax+rax*2]
0x180009b21  shl     r13, 4
0x180009b25  call    cs:__imp_GetProcessHeap
0x180009b2b  mov     rcx, rax; hHeap
0x180009b2e  mov     r8, r13; dwBytes
0x180009b31  xor     edx, edx; dwFlags
0x180009b33  call    cs:__imp_HeapAlloc
0x180009b39  mov     r14, rax
0x180009b3c  test    rax, rax
0x180009b3f  jz      loc_18000A1D4
0x180009b45  mov     r8, r13; Size
0x180009b48  xor     edx, edx; Val
0x180009b4a  mov     rcx, rax; void *
0x180009b4d  call    memset_0
0x180009b52  xor     ebx, ebx
0x180009b54  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180009b5e  mov     rcx, [r12]
0x180009b62  mov     rax, [r12+8]
0x180009b67  sub     rax, rcx
0x180009b6a  sar     rax, 4
0x180009b6e  imul    rax, rdx
0x180009b72  cmp     rbx, rax
0x180009b75  jnb     loc_180009DAF
0x180009b7b  lea     r13, [rbx+rbx*2]
0x180009b7f  add     r13, r13
0x180009b82  movups  xmm0, xmmword ptr [rcx+r13*8]
0x180009b87  movups  xmmword ptr [r14+r13*8], xmm0
0x180009b8c  mov     eax, [rcx+r13*8+10h]
0x180009b91  mov     [r14+r13*8+10h], eax
0x180009b96  mov     rax, [r12]
0x180009b9a  mov     ecx, [rax+r13*8+14h]
0x180009b9f  mov     [r14+r13*8+20h], ecx
0x180009ba4  mov     rax, [r12]
0x180009ba8  mov     r12, [rax+r13*8+20h]
0x180009bad  mov     rcx, [rax+r13*8+18h]
0x180009bb2  cmp     rcx, r12
0x180009bb5  jz      short loc_180009C02
0x180009bb7  sub     r12, rcx
0x180009bba  call    cs:__imp_GetProcessHeap
0x180009bc0  mov     rcx, rax; hHeap
0x180009bc3  mov     r8, r12; dwBytes
0x180009bc6  xor     edx, edx; dwFlags
0x180009bc8  call    cs:__imp_HeapAlloc
0x180009bce  mov     [r14+r13*8+28h], rax
0x180009bd3  test    rax, rax
0x180009bd6  jz      loc_18000A33E
0x180009bdc  mov     [r14+r13*8+24h], r12d
0x180009be1  mov     rdx, [rbp+140h+var_E0]
0x180009be5  mov     rdx, [rdx]
0x180009be8  mov     r8, r12; Size
0x180009beb  mov     rdx, [rdx+r13*8+18h]; Src
0x180009bf0  mov     rcx, rax; void *
0x180009bf3  call    memcpy_0
0x180009bf8  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180009c02  inc     rbx
0x180009c05  mov     r12, [rbp+140h+var_E0]
0x180009c09  jmp     loc_180009B5E
0x180009c0e  mov     rax, [rsp+240h+var_1E8]
  ... truncated ...
```
