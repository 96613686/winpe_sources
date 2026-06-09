# CmsRpcSrv_CreateProcessInContainer

- ea: `0x180019360`
- end: `0x1800198f5`
- name: `CmsRpcSrv_CreateProcessInContainer`
- size: `1429`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007c0c`
- `0x180007e54`
- `0x1800088c8`
- `0x180009cc0`
- `0x18000da88`
- `0x18000dad8`
- `0x18000ed18`
- `0x18001063c`
- `0x180019360`
- `0x18001f96c`
- `0x180049f4c`
- `0x18009e938`
- `0x180122bf4`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x180019486`
- `ntdll!RtlAreAllAccessesGranted` at `0x180019486`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019625`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180019625`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800195c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800195c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019710`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019867`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019899`

## string_xrefs

- `0x1800193f6`: `CreateProcessInContainer`
- `0x1800194a2`: `onecore\base\gendrv\silos\clem\service\RpcContextHandles.h`
- `0x1800194c3`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180019524`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x1800196d9`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRpcSrv_CreateProcessInContainer(
        ACCESS_MASK *a1,
        __int64 a2,
        int a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        unsigned int *a8,
        Container::Manager::Service::ProcessRpcContextHandle **a9)
{
  unsigned int v10; // ebx
  char *v11; // r14
  void *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  __int64 result; // rax
  int v17; // eax
  unsigned int v18; // edi
  Container::Manager::Service::ProcessRpcContextHandle *v19; // rbx
  Container::Manager::Service::ProcessRpcContextHandle *v20; // rsi
  Container::Manager::Core::Process *v21; // r15
  char *v22; // rdi
  char *v23; // rbx
  __int64 v24; // r12
  RTL_SRWLOCK *v25; // r13
  int v26; // r12d
  int ProcessW; // eax
  Container::Manager::Core::Process *v28; // r12
  char *v29; // rcx
  char *v30; // rcx
  char *v31; // r15
  unsigned int ProcessId; // eax
  unsigned int v33; // [rsp+20h] [rbp-238h]
  int v34; // [rsp+20h] [rbp-238h]
  int v35; // [rsp+20h] [rbp-238h]
  Container::Manager::Service::ProcessRpcContextHandle *v36; // [rsp+40h] [rbp-218h] BYREF
  int v37; // [rsp+48h] [rbp-210h]
  int v38[2]; // [rsp+50h] [rbp-208h] BYREF
  char *v39; // [rsp+58h] [rbp-200h] BYREF
  char *v40; // [rsp+60h] [rbp-1F8h] BYREF
  _QWORD *v41; // [rsp+68h] [rbp-1F0h]
  _QWORD *v42; // [rsp+70h] [rbp-1E8h]
  _QWORD *v43; // [rsp+78h] [rbp-1E0h]
  unsigned int *v44; // [rsp+80h] [rbp-1D8h]
  Container::Manager::Service::ProcessRpcContextHandle **v45; // [rsp+88h] [rbp-1D0h]
  __int64 v46; // [rsp+90h] [rbp-1C8h]
  __int64 v47; // [rsp+98h] [rbp-1C0h]
  _QWORD *v48; // [rsp+A0h] [rbp-1B8h]
  int v49; // [rsp+A8h] [rbp-1B0h]
  __int64 v50; // [rsp+B8h] [rbp-1A0h]
  _QWORD v51[42]; // [rsp+C0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v41 = a4;
  v37 = a3;
  v47 = a2;
  v48 = a5;
  v42 = a6;
  v43 = a7;
  v44 = a8;
  v45 = a9;
  v10 = *(_DWORD *)(*(_QWORD *)a1 + 8LL);
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v51,
    "CreateProcessInContainer");
  v51[0] = &CmTraceProvider::CreateProcessInContainer::`vftable';
  v33 = v10;
  try
  {
    CmTraceProvider::CreateProcessInContainer::StartActivity();
    v11 = 0;
    *v45 = 0;
    *v44 = 0;
    *a5 = 0;
    *v42 = 0;
    *v43 = 0;
    *v41 = 0;
    if ( !RtlAreAllAccessesGranted(a1[4], 0x80u) )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x7A,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\RpcContextHandles.h",
              (const char *)5,
              v10);
      v14 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x813,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v13,
          v33);
        v51[0] = &CmTraceProvider::CreateProcessInContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v51);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v51);
        return v14;
      }
    }
    v36 = 0;
    v17 = CreateProcessRpcContextHandle(&v36, v12);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x818,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v17,
        v33);
      v19 = v36;
      if ( v36 )
      {
        Container::Manager::Service::ProcessRpcContextHandle::~ProcessRpcContextHandle(v36);
        operator delete(v19, (const struct std::nothrow_t *)0x10);
      }
      v51[0] = &CmTraceProvider::CreateProcessInContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v51);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v51);
      return v18;
    }
    v20 = v36;
    v46 = *((_QWORD *)v36 + 1);
    v21 = 0;
    v36 = 0;
    v22 = 0;
    *(_QWORD *)v38 = 0;
    v23 = 0;
    v39 = 0;
    v40 = 0;
    v24 = *(_QWORD *)a1;
    v25 = (RTL_SRWLOCK *)(*(_QWORD *)(v24 + 40) + 456LL);
    AcquireSRWLockShared(v25);
    if ( *(_DWORD *)(v24 + 56) == 4 )
    {
      if ( v25 )
        ReleaseSRWLockShared(v25);
      v50 = v46;
      v49 = 2;
      ProcessW = Container::Manager::Core::Details::ContainerObject::CreateProcessW(
                   *(Container::Manager::Core::Details::ContainerObject **)(v24 + 40),
                   (unsigned int)v38,
                   (__int64)&v39,
                   (__int64)&v40,
                   (__int64)&v36);
      v26 = ProcessW;
      if ( ProcessW < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x125,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
          (const char *)(unsigned int)ProcessW,
          v35);
        v21 = v36;
        v22 = *(char **)v38;
        v23 = v39;
        v11 = v40;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x82D,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v26,
          v34);
        if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v11);
        if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v23);
        if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v22);
        if ( v21 )
        {
          Container::Manager::Core::Process::~Process(v21);
          operator delete(v21, (const struct std::nothrow_t *)0x40);
        }
        if ( v20 )
        {
          Container::Manager::Service::ProcessRpcContextHandle::~ProcessRpcContextHandle(v20);
          operator delete(v20, (const struct std::nothrow_t *)0x10);
        }
        v51[0] = &CmTraceProvider::CreateProcessInContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v51);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v51);
        return (unsigned int)v26;
      }
      v21 = v36;
      v22 = *(char **)v38;
      v23 = v39;
      v11 = v40;
    }
    else
    {
      v26 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x11A,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
              (const char *)0x139F,
              v33);
      if ( v25 )
        ReleaseSRWLockShared(v25);
      if ( v26 < 0 )
        goto LABEL_18;
    }
    v28 = *(Container::Manager::Core::Process **)v20;
    *(_QWORD *)v20 = v21;
    if ( v28 )
    {
      Container::Manager::Core::Process::~Process(v28);
      operator delete(v28, (const struct std::nothrow_t *)0x40);
    }
    *v41 = *(_QWORD *)(*((_QWORD *)v20 + 1) + 80LL);
    v29 = v22;
    if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v22 = 0;
      *v48 = v29;
    }
    v30 = v23;
    if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v23 = 0;
      *v42 = v30;
    }
    v31 = v11;
    if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v11 = 0;
      *v43 = v31;
      v31 = 0;
    }
    ProcessId = Container::Manager::Hcs::ComputeSystemProcess::GetProcessId(*(Container::Manager::Hcs::ComputeSystemProcess **)(*(_QWORD *)v20 + 24LL));
    *v44 = ProcessId;
    *v45 = v20;
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v51, 0);
    if ( (unsigned __int64)(v31 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v11);
    if ( (unsigned __int64)(v23 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v23);
    if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v22);
    v51[0] = &CmTraceProvider::CreateProcessInContainer::`vftable';
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v51);
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v51);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x851,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      v15);
  }
  return result;
}

```

## disassembly

```asm
0x180019360  push    rbx
0x180019362  push    rsi
0x180019363  push    rdi
0x180019364  push    r12
0x180019366  push    r13
0x180019368  push    r14
0x18001936a  push    r15
0x18001936c  sub     rsp, 220h
0x180019373  mov     rax, cs:__security_cookie
0x18001937a  xor     rax, rsp
0x18001937d  mov     [rsp+258h+var_48], rax
0x180019385  mov     [rsp+258h+var_1F0], r9
0x18001938a  mov     [rsp+258h+var_210], r8d
0x18001938f  mov     r15, rdx
0x180019392  mov     [rsp+258h+var_1C0], rdx
0x18001939a  mov     r12, rcx
0x18001939d  mov     r13, [rsp+258h+arg_20]
0x1800193a5  mov     [rsp+258h+var_1B8], r13
0x1800193ad  mov     rax, [rsp+258h+arg_28]
0x1800193b5  mov     [rsp+258h+var_1E8], rax
0x1800193ba  mov     rax, [rsp+258h+arg_30]
0x1800193c2  mov     [rsp+258h+var_1E0], rax
0x1800193c7  mov     rax, [rsp+258h+arg_38]
0x1800193cf  mov     [rsp+258h+var_1D8], rax
0x1800193d7  mov     rax, [rsp+258h+arg_40]
0x1800193df  mov     [rsp+258h+var_1D0], rax
0x1800193e7  mov     rax, [rcx]
0x1800193ea  mov     ebx, [rax+8]
0x1800193ed  mov     edi, [rax+4]
0x1800193f0  mov     esi, [rax]
0x1800193f2  mov     r14, [rax+28h]
0x1800193f6  lea     rdx, aCreateprocessi; "CreateProcessInContainer"
0x1800193fd  lea     rcx, [rsp+258h+var_198]
0x180019405  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001940a  lea     rax, ??_7CreateProcessInContainer@CmTraceProvider@@6B@; const CmTraceProvider::CreateProcessInContainer::`vftable'
0x180019411  mov     [rsp+258h+var_198], rax
0x180019419  mov     rax, [r15]
0x18001941c  mov     [rsp+258h+var_228], rax
0x180019421  mov     rax, [r15+8]
0x180019425  mov     [rsp+258h+var_230], rax
0x18001942a  mov     [rsp+258h+var_238], ebx; unsigned int
0x18001942e  mov     r9d, edi
0x180019431  mov     r8d, esi
0x180019434  mov     rdx, r14
0x180019437  lea     rcx, [rsp+258h+var_198]
0x18001943f  call    ?StartActivity@CreateProcessInContainer@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@KPEBG3@Z; CmTraceProvider::CreateProcessInContainer::StartActivity(_GUID const &,_CMS_CLIENT_ID,_CMS_ACTIVITY_ID,ulong,ushort const *,ushort const *)
0x180019444  nop
0x180019445  xor     r14d, r14d
0x180019448  mov     rax, [rsp+258h+var_1D0]
0x180019450  mov     [rax], r14
0x180019453  mov     rax, [rsp+258h+var_1D8]
0x18001945b  mov     [rax], r14d
0x18001945e  mov     [r13+0], r14
0x180019462  mov     rax, [rsp+258h+var_1E8]
0x180019467  mov     [rax], r14
0x18001946a  mov     rax, [rsp+258h+var_1E0]
0x18001946f  mov     [rax], r14
0x180019472  xor     ecx, ecx
0x180019474  mov     rax, [rsp+258h+var_1F0]
0x180019479  mov     [rax], rcx
0x18001947c  mov     edx, 80h; DesiredAccess
0x180019481  mov     ecx, [r12+10h]; GrantedAccess
0x180019486  call    cs:__imp_RtlAreAllAccessesGranted
0x18001948d  nop     dword ptr [rax+rax+00h]
0x180019492  test    al, al
0x180019494  jnz     short loc_180019504
0x180019496  mov     rcx, [rsp+258h]; this
0x18001949e  lea     r9d, [r14+5]; char *
0x1800194a2  lea     r8, aOnecoreBaseGen_15; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x1800194a9  lea     edx, [r14+7Ah]; void *
0x1800194ad  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800194b2  mov     ebx, eax
0x1800194b4  test    eax, eax
0x1800194b6  jns     short loc_180019504
0x1800194b8  mov     rcx, [rsp+258h]; this
0x1800194c0  mov     r9d, eax; char *
0x1800194c3  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x1800194ca  mov     edx, 813h; void *
0x1800194cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194d4  lea     rax, ??_7CreateProcessInContainer@CmTraceProvider@@6B@; const CmTraceProvider::CreateProcessInContainer::`vftable'
0x1800194db  mov     [rsp+258h+var_198], rax
0x1800194e3  lea     rcx, [rsp+258h+var_198]
0x1800194eb  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800194f0  lea     rcx, [rsp+258h+var_198]
0x1800194f8  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800194fd  mov     eax, ebx
0x1800194ff  jmp     loc_1800198D1
0x180019504  mov     [rsp+258h+var_218], r14
0x180019509  lea     rcx, [rsp+258h+var_218]
0x18001950e  call    CreateProcessRpcContextHandle
0x180019513  mov     edi, eax
0x180019515  test    eax, eax
0x180019517  jns     short loc_180019584
0x180019519  mov     rcx, [rsp+258h]; this
0x180019521  mov     r9d, eax; char *
0x180019524  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001952b  mov     edx, 818h; void *
0x180019530  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019535  mov     rbx, [rsp+258h+var_218]
0x18001953a  test    rbx, rbx
0x18001953d  jz      short loc_180019554
0x18001953f  mov     rcx, rbx; this
0x180019542  call    ??1ProcessRpcContextHandle@Service@Manager@Container@@QEAA@XZ; Container::Manager::Service::ProcessRpcContextHandle::~ProcessRpcContextHandle(void)
0x180019547  mov     edx, 10h; struct std::nothrow_t *
0x18001954c  mov     rcx, rbx; void *
0x18001954f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019554  lea     rax, ??_7CreateProcessInContainer@CmTraceProvider@@6B@; const CmTraceProvider::CreateProcessInContainer::`vftable'
0x18001955b  mov     [rsp+258h+var_198], rax
0x180019563  lea     rcx, [rsp+258h+var_198]
0x18001956b  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180019570  lea     rcx, [rsp+258h+var_198]
0x180019578  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001957d  mov     eax, edi
0x18001957f  jmp     loc_1800198D1
0x180019584  mov     rsi, [rsp+258h+var_218]
0x180019589  mov     rax, [rsi+8]
0x18001958d  mov     [rsp+258h+var_1C8], rax
0x180019595  mov     r15, r14
0x180019598  mov     [rsp+258h+var_218], r14
0x18001959d  mov     rdi, r14
0x1800195a0  mov     qword ptr [rsp+258h+var_208], r14
0x1800195a5  mov     rbx, r14
0x1800195a8  mov     [rsp+258h+var_200], rbx
0x1800195ad  mov     [rsp+258h+var_1F8], r14
0x1800195b2  mov     r12, [r12]
0x1800195b6  mov     r13, [r12+28h]
0x1800195bb  add     r13, 1C8h
0x1800195c2  mov     rcx, r13; SRWLock
0x1800195c5  call    cs:__imp_AcquireSRWLockShared
0x1800195cc  nop     dword ptr [rax+rax+00h]
0x1800195d1  cmp     dword ptr [r12+38h], 4
0x1800195d7  jz      short loc_18001961D
0x1800195d9  mov     rcx, [rsp+258h]; this
0x1800195e1  mov     r9d, 139Fh; char *
0x1800195e7  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800195ee  mov     edx, 11Ah; void *
0x1800195f3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800195f8  mov     r12d, eax
0x1800195fb  test    r13, r13
0x1800195fe  jz      short loc_18001960F
0x180019600  mov     rcx, r13; SRWLock
0x180019603  call    cs:__imp_ReleaseSRWLockShared
0x18001960a  nop     dword ptr [rax+rax+00h]
0x18001960f  test    r12d, r12d
0x180019612  jns     loc_1800197AE
0x180019618  jmp     loc_1800196CE
0x18001961d  test    r13, r13
0x180019620  jz      short loc_180019631
0x180019622  mov     rcx, r13; SRWLock
0x180019625  call    cs:__imp_ReleaseSRWLockShared
0x18001962c  nop     dword ptr [rax+rax+00h]
0x180019631  mov     rax, [rsp+258h+var_1C8]
0x180019639  mov     [rsp+258h+var_1A0], rax
0x180019641  mov     [rsp+258h+var_1B0], 2
0x18001964c  lea     rax, [rsp+258h+var_218]
0x180019651  mov     [rsp+258h+var_220], rax
0x180019656  lea     rax, [rsp+258h+var_1F8]
0x18001965b  mov     [rsp+258h+var_228], rax
0x180019660  lea     rax, [rsp+258h+var_200]
0x180019665  mov     [rsp+258h+var_230], rax
0x18001966a  lea     rax, [rsp+258h+var_208]
0x18001966f  mov     qword ptr [rsp+258h+var_238], rax; int
0x180019674  lea     r9, [rsp+258h+var_1B0]
0x18001967c  mov     r8d, [rsp+258h+var_210]
0x180019681  mov     rdx, [rsp+258h+var_1C0]
0x180019689  mov     rcx, [r12+28h]
0x18001968e  call    ?CreateProcessW@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBU_CMS_PROCESS_PROPERTIES@@W4_CMS_PROCESS_CREATION_FLAGS@@V?$NotificationPublisher@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@33AEAV?$unique_ptr@VProcess@Core@Manager@Container@@U?$default_delete@VProcess@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::Details::ContainerObject::CreateProcessW(_CMS_PROCESS_PROPERTIES const &,_CMS_PROCESS_CREATION_FLAGS,Csl::NotificationPublisher<_CMS_PROCESS_NOTIFICATION,1>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wistd::unique_ptr<Container::Manager::Core::Process,wistd::default_delete<Container::Manager::Core::Process>> &)
0x180019693  mov     r12d, eax
0x180019696  test    eax, eax
0x180019698  jns     loc_18001979A
0x18001969e  mov     rcx, [rsp+258h]; this
0x1800196a6  mov     r9d, eax; char *
0x1800196a9  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800196b0  mov     edx, 125h; void *
0x1800196b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800196ba  mov     r15, [rsp+258h+var_218]
0x1800196bf  mov     rdi, qword ptr [rsp+258h+var_208]
0x1800196c4  mov     rbx, [rsp+258h+var_200]
0x1800196c9  mov     r14, [rsp+258h+var_1F8]
0x1800196ce  mov     rcx, [rsp+258h]; this
0x1800196d6  mov     r9d, r12d; char *
0x1800196d9  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x1800196e0  mov     edx, 82Dh; void *
0x1800196e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800196ea  lea     rax, [r14-1]
0x1800196ee  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800196f2  ja      short loc_180019703
0x1800196f4  mov     rcx, r14; hObject
0x1800196f7  call    cs:__imp_CloseHandle
0x1800196fe  nop     dword ptr [rax+rax+00h]
0x180019703  lea     rax, [rbx-1]
0x180019707  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001970b  ja      short loc_18001971C
0x18001970d  mov     rcx, rbx; hObject
0x180019710  call    cs:__imp_CloseHandle
0x180019717  nop     dword ptr [rax+rax+00h]
0x18001971c  lea     rax, [rdi-1]
0x180019720  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019724  ja      short loc_180019735
0x180019726  mov     rcx, rdi; hObject
0x180019729  call    cs:__imp_CloseHandle
0x180019730  nop     dword ptr [rax+rax+00h]
0x180019735  test    r15, r15
0x180019738  jz      short loc_18001974F
0x18001973a  mov     rcx, r15; this
0x18001973d  call    ??1Process@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Process::~Process(void)
0x180019742  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x180019747  mov     rcx, r15; void *
0x18001974a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001974f  test    rsi, rsi
0x180019752  jz      short loc_180019769
0x180019754  mov     rcx, rsi; this
0x180019757  call    ??1ProcessRpcContextHandle@Service@Manager@Container@@QEAA@XZ; Container::Manager::Service::ProcessRpcContextHandle::~ProcessRpcContextHandle(void)
0x18001975c  mov     edx, 10h; struct std::nothrow_t *
0x180019761  mov     rcx, rsi; void *
0x180019764  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019769  lea     rax, ??_7CreateProcessInContainer@CmTraceProvider@@6B@; const CmTraceProvider::CreateProcessInContainer::`vftable'
0x180019770  mov     [rsp+258h+var_198], rax
0x180019778  lea     rcx, [rsp+258h+var_198]
0x180019780  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180019785  lea     rcx, [rsp+258h+var_198]
0x18001978d  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180019792  mov     eax, r12d
0x180019795  jmp     loc_1800198D1
0x18001979a  mov     r15, [rsp+258h+var_218]
0x18001979f  mov     rdi, qword ptr [rsp+258h+var_208]
0x1800197a4  mov     rbx, [rsp+258h+var_200]
0x1800197a9  mov     r14, [rsp+258h+var_1F8]
0x1800197ae  mov     r12, [rsi]
0x1800197b1  mov     [rsi], r15
0x1800197b4  test    r12, r12
0x1800197b7  jz      short loc_1800197CE
0x1800197b9  mov     rcx, r12; this
0x1800197bc  call    ??1Process@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Process::~Process(void)
0x1800197c1  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x1800197c6  mov     rcx, r12; void *
0x1800197c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800197ce  mov     rax, [rsi+8]
0x1800197d2  mov     rcx, [rax+50h]
0x1800197d6  mov     rax, [rsp+258h+var_1F0]
0x1800197db  mov     [rax], rcx
0x1800197de  mov     rcx, rdi
0x1800197e1  lea     rax, [rdi-1]
0x1800197e5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800197e9  ja      short loc_1800197F8
0x1800197eb  xor     edi, edi
0x1800197ed  mov     rax, [rsp+258h+var_1B8]
0x1800197f5  mov     [rax], rcx
0x1800197f8  mov     rcx, rbx
0x1800197fb  lea     rax, [rbx-1]
0x1800197ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019803  ja      short loc_18001980F
0x180019805  xor     ebx, ebx
0x180019807  mov     rax, [rsp+258h+var_1E8]
0x18001980c  mov     [rax], rcx
0x18001980f  mov     r15, r14
0x180019812  lea     rax, [r14-1]
0x180019816  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001981a  ja      short loc_18001982A
0x18001981c  xor     r14d, r14d
0x18001981f  mov     rax, [rsp+258h+var_1E0]
0x180019824  mov     [rax], r15
0x180019827  xor     r15d, r15d
0x18001982a  mov     rcx, [rsi]
0x18001982d  mov     rcx, [rcx+18h]; this
0x180019831  call    ?GetProcessId@ComputeSystemProcess@Hcs@Manager@Container@@QEBAKXZ; Container::Manager::Hcs::ComputeSystemProcess::GetProcessId(void)
0x180019836  mov     rcx, [rsp+258h+var_1D8]
0x18001983e  mov     [rcx], eax
0x180019840  mov     rax, [rsp+258h+var_1D0]
0x180019848  mov     [rax], rsi
0x18001984b  xor     edx, edx
0x18001984d  lea     rcx, [rsp+258h+var_198]
0x180019855  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001985a  lea     rax, [r15-1]
0x18001985e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019862  ja      short loc_180019873
0x180019864  mov     rcx, r14; hObject
0x180019867  call    cs:__imp_CloseHandle
0x18001986e  nop     dword ptr [rax+rax+00h]
0x180019873  lea     rax, [rbx-1]
0x180019877  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001987b  ja      short loc_18001988C
0x18001987d  mov     rcx, rbx; hObject
0x180019880  call    cs:__imp_CloseHandle
0x180019887  nop     dword ptr [rax+rax+00h]
0x18001988c  lea     rax, [rdi-1]
0x180019890  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019894  ja      short loc_1800198A5
0x180019896  mov     rcx, rdi; hObject
0x180019899  call    cs:__imp_CloseHandle
0x1800198a0  nop     dword ptr [rax+rax+00h]
0x1800198a5  lea     rax, ??_7CreateProcessInContainer@CmTraceProvider@@6B@; const CmTraceProvider::CreateProcessInContainer::`vftable'
0x1800198ac  mov     [rsp+258h+var_198], rax
0x1800198b4  lea     rcx, [rsp+258h+var_198]
0x1800198bc  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800198c1  lea     rcx, [rsp+258h+var_198]
0x1800198c9  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800198ce  nop
0x1800198cf  xor     eax, eax
0x1800198d1  mov     rcx, [rsp+258h+var_48]
  ... truncated ...
```
