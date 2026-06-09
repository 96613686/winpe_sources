# CmsRpcSrv_CreateContainerWithContainerStorage

- ea: `0x180018120`
- end: `0x180019353`
- name: `CmsRpcSrv_CreateContainerWithContainerStorage`
- size: `4659`
- prototype: `__int64 __fastcall(int, int, int, int, PSECURITY_DESCRIPTOR SecurityDescriptorInput, ULONG SecurityDescriptorLength, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180018100`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180008414`
- `0x180008d04`
- `0x180009ba0`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x18000eb6c`
- `0x1800103a4`
- `0x180018120`
- `0x18001f5c4`
- `0x18002c418`
- `0x18002e95c`
- `0x18002ebd4`
- `0x18002efc0`
- `0x18002f230`
- `0x18003ff20`
- `0x18004b318`
- `0x180190fe0`

## import_xrefs

- `ntdll!RtlNewSecurityObject` at `0x1800183fe`
- `ntdll!RtlNewSecurityObject` at `0x1800183fe`
- `ntdll!RtlMapGenericMask` at `0x1800188b8`
- `ntdll!RtlMapGenericMask` at `0x1800188b8`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180018308`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x180018308`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018cc1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180018cc1`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180018adf`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x180018adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183c8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018eae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180018eae`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018ede`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180018ede`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001821f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800186be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001894a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018b7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018c4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018dfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800191c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001929e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800192f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001821f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800182b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018466`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018511`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800186be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018852`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001894a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018a0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018b21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018b7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018bf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018c4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018d80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018dfc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800190a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019101`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800191c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001929e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800192f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001844d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800184f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800185ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800186a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001877f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018931`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800189f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018d67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019207`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800192de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001844d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800184f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800185ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800186a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001877f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018931`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800189f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018d67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e3c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800190e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019207`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800192de`

## string_xrefs

- `0x180018194`: `CreateContainer`
- `0x180018cdd`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x1800181fc`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001827c`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001832c`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180018420`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x1800184cd`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180018581`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001865e`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001873a`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x1800187f1`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x1800188ec`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x1800189ac`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180018afb`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180018bd0`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180018d04`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180018dd6`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180018efd`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180019069`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180019188`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CmsRpcSrv_CreateContainerWithContainerStorage(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        PSECURITY_DESCRIPTOR SecurityDescriptorInput,
        ULONG SecurityDescriptorLength,
        DWORD a7,
        _QWORD *a8,
        Container::Manager::Service::ContainerRpcContextHandle **a9)
{
  int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  __int64 result; // rax
  char *v14; // r13
  int UserSidFromToken; // eax
  unsigned int v16; // ebx
  Csl *v17; // rdi
  void *v18; // rdx
  Csl *v19; // rbx
  DWORD LastError; // esi
  void *v21; // rdx
  NTSTATUS v22; // eax
  void *v23; // rdx
  bool *v24; // r9
  void *v25; // rdx
  HLOCAL v26; // rbx
  void *v27; // rdx
  int DefaultSecurityDescriptor; // eax
  unsigned int v29; // edi
  void *v30; // rdx
  Csl *v31; // rsi
  int v32; // eax
  unsigned int v33; // esi
  void *v34; // rdx
  int v35; // eax
  unsigned int v36; // r15d
  void *v37; // rdx
  void *v38; // rdx
  unsigned int v39; // r14d
  bool *v40; // r8
  int IsAdminOrSystem; // eax
  void *v42; // rdx
  void *v43; // rdx
  HANDLE v44; // rcx
  const char *v45; // r9
  HANDLE v46; // rdx
  HANDLE v47; // rdx
  __int64 v48; // rcx
  const char *v49; // r9
  int v50; // eax
  void *v51; // rdx
  HANDLE v52; // rdx
  HANDLE *v53; // r15
  HANDLE CurrentProcess; // r14
  HANDLE v55; // rax
  const char *v56; // r9
  HANDLE v57; // rdx
  __int128 v58; // xmm0
  _QWORD *v59; // r14
  int Container; // eax
  __int64 v61; // r9
  void *v62; // rdx
  HLOCAL v63; // r14
  int v64; // eax
  void *v65; // rdx
  Container::Manager::Service::ContainerRpcContextHandle *v66; // r14
  Container::Manager::Service::ContainerRpcContextHandle *v67; // rax
  void *v68; // rdx
  int Token; // [rsp+20h] [rbp-248h]
  unsigned int Tokena; // [rsp+20h] [rbp-248h]
  unsigned int Tokenb; // [rsp+20h] [rbp-248h]
  int v72; // [rsp+40h] [rbp-228h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-220h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+50h] [rbp-218h] BYREF
  HANDLE v75; // [rsp+58h] [rbp-210h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-208h] BYREF
  DWORD AccessMask; // [rsp+68h] [rbp-200h] BYREF
  WINBOOL pfResult; // [rsp+6Ch] [rbp-1FCh] BYREF
  Container::Manager::Service::ContainerRpcContextHandle *v79; // [rsp+70h] [rbp-1F8h] BYREF
  PSECURITY_DESCRIPTOR v80; // [rsp+78h] [rbp-1F0h] BYREF
  __int128 v81; // [rsp+80h] [rbp-1E8h]
  __int64 v82; // [rsp+90h] [rbp-1D8h]
  _QWORD *v83; // [rsp+98h] [rbp-1D0h]
  Container::Manager::Service::ContainerRpcContextHandle **v84; // [rsp+A0h] [rbp-1C8h]
  _QWORD v85[42]; // [rsp+B0h] [rbp-1B8h] BYREF
  _BYTE RequiredPrivileges[32]; // [rsp+200h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_QWORD *)&v81 = a4;
  LODWORD(v79) = a2;
  v82 = a1;
  v83 = a8;
  v84 = a9;
  *a8 = 0;
  *a9 = 0;
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v85,
    "CreateContainer");
  v85[0] = &CmTraceProvider::CreateContainer::`vftable';
  Token = *(_DWORD *)(a3 + 8);
  try
  {
    CmTraceProvider::CreateContainer::StartActivity();
    hObject = 0;
    v10 = Container::Manager::Rpc::OpenRpcClientAccessToken(10, &hObject);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v10,
        Token);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v85[0] = &CmTraceProvider::CreateContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
      return v11;
    }
    hMem = 0;
    v14 = (char *)hObject;
    UserSidFromToken = Csl::GetUserSidFromToken(hObject, &hMem);
    v16 = UserSidFromToken;
    if ( UserSidFromToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)UserSidFromToken,
        Token);
      if ( hMem )
        LocalFree(hMem);
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v14);
LABEL_11:
      v85[0] = &CmTraceProvider::CreateContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
      return v16;
    }
    v17 = 0;
    hObject = 0;
    NewDescriptor = 0;
    if ( SecurityDescriptorInput )
    {
      if ( !RtlValidRelativeSecurityDescriptor(SecurityDescriptorInput, SecurityDescriptorLength, 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)0x80070057LL,
          Token);
        if ( NewDescriptor )
          Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v18);
        if ( hMem )
          LocalFree(hMem);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
LABEL_20:
        v85[0] = &CmTraceProvider::CreateContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
        return 2147942487LL;
      }
      v19 = (Csl *)NewDescriptor;
      if ( NewDescriptor )
      {
        LastError = GetLastError();
        Csl::DeleteSecurityObjectWrapper(v19, v21);
        SetLastError(LastError);
      }
      NewDescriptor = 0;
      v22 = RtlNewSecurityObject(0, SecurityDescriptorInput, &NewDescriptor, 0, v14, (PGENERIC_MAPPING)&stru_1801D0FA0);
      if ( v22 < 0 )
      {
        v16 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0xBA,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
                (const char *)(unsigned int)v22,
                Tokena);
        if ( NewDescriptor )
          Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v25);
        if ( hMem )
          LocalFree(hMem);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
        goto LABEL_11;
      }
      v80 = NewDescriptor;
      v26 = hMem;
    }
    else
    {
      if ( SecurityDescriptorLength )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)0x80070057LL,
          Token);
        if ( NewDescriptor )
          Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v27);
        if ( hMem )
          LocalFree(hMem);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
        goto LABEL_20;
      }
      v26 = hMem;
      DefaultSecurityDescriptor = Csl::CreateDefaultSecurityDescriptor(
                                    hMem,
                                    0xF00FFu,
                                    (PGENERIC_MAPPING)&stru_1801D0FA0,
                                    (int)v14,
                                    (__int64)&hObject);
      v29 = DefaultSecurityDescriptor;
      if ( DefaultSecurityDescriptor < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCB,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)DefaultSecurityDescriptor,
          Tokena);
        if ( NewDescriptor )
          Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v30);
        if ( hObject )
          Csl::DeleteSecurityObjectWrapper((Csl *)hObject, v30);
        if ( v26 )
          LocalFree(v26);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
        v85[0] = &CmTraceProvider::CreateContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
        return v29;
      }
      v17 = (Csl *)hObject;
      v80 = hObject;
    }
    v31 = 0;
    hMem = 0;
    if ( !(_QWORD)v81 )
    {
      v32 = Csl::CreateDefaultSecurityDescriptor(
              v26,
              0x1F01BFu,
              (PGENERIC_MAPPING)&GenericMapping,
              (int)v14,
              (__int64)&hMem);
      v33 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDB,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v32,
          Tokena);
        if ( hMem )
          Csl::DeleteSecurityObjectWrapper((Csl *)hMem, v34);
        if ( NewDescriptor )
          Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v34);
        if ( v17 )
          Csl::DeleteSecurityObjectWrapper(v17, v34);
        if ( v26 )
          LocalFree(v26);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
        v85[0] = &CmTraceProvider::CreateContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
        return v33;
      }
      v31 = (Csl *)hMem;
    }
    if ( (a7 & 0x1000000) != 0 )
    {
      LOBYTE(v72) = 0;
      v35 = Csl::SinglePrivilegeCheck((Csl *)v14, v23, (int)&v72, v24);
      v36 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v35,
          Tokena);
        if ( v31 )
          Csl::DeleteSecurityObjectWrapper(v31, v37);
        if ( NewDescriptor )
          Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v37);
        if ( v17 )
          Csl::DeleteSecurityObjectWrapper(v17, v37);
        if ( v26 )
          LocalFree(v26);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
LABEL_232:
        v85[0] = &CmTraceProvider::CreateContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
        return v36;
      }
      if ( !(_BYTE)v72 )
      {
        v39 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xED,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
                (const char *)0x522,
                Tokena);
        if ( v31 )
          Csl::DeleteSecurityObjectWrapper(v31, v38);
        if ( NewDescriptor )
          Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v38);
        if ( v17 )
          Csl::DeleteSecurityObjectWrapper(v17, v38);
        if ( v26 )
          LocalFree(v26);
        if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v14);
LABEL_193:
        v85[0] = &CmTraceProvider::CreateContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
        return v39;
      }
    }
    AccessMask = a7;
    if ( (a7 & 0x2000000) != 0 )
      AccessMask = a7 & 0xFDF0FF00 | 0xF00FF;
    RtlMapGenericMask(&AccessMask, (PGENERIC_MAPPING)&stru_1801D0FA0);
    LOBYTE(v72) = 0;
    IsAdminOrSystem = Csl::IsAdminOrSystem(v14, &v72, v40);
    v39 = IsAdminOrSystem;
    if ( IsAdminOrSystem < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)IsAdminOrSystem,
        Tokena);
      if ( v31 )
        Csl::DeleteSecurityObjectWrapper(v31, v42);
      if ( NewDescriptor )
        Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v42);
      if ( v17 )
        Csl::DeleteSecurityObjectWrapper(v17, v42);
      if ( v26 )
        LocalFree(v26);
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v14);
      goto LABEL_193;
    }
    if ( *(_DWORD *)(a3 + 12) == 2 && !(_BYTE)v72 )
    {
      v39 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x111,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
              (const char *)5,
              Tokena);
      if ( v31 )
        Csl::DeleteSecurityObjectWrapper(v31, v43);
      if ( NewDescriptor )
        Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v43);
      if ( v17 )
        Csl::DeleteSecurityObjectWrapper(v17, v43);
      if ( v26 )
        LocalFree(v26);
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v14);
      goto LABEL_193;
    }
    v44 = 0;
    v75 = 0;
    if ( *(_DWORD *)(a3 + 12) == 1 )
    {
      if ( *(_QWORD *)(a3 + 56) )
      {
        *(_OWORD *)&RequiredPrivileges[16] = 0;
        hMem = (HLOCAL)29;
        *(_QWORD *)&RequiredPrivileges[8] = 29;
        *(_DWORD *)RequiredPrivileges = 1;
        if ( (*(_BYTE *)(a3 + 88) & 2) != 0 )
        {
          hMem = (HLOCAL)3;
          *(_QWORD *)&RequiredPrivileges[20] = 3;
          *(_DWORD *)RequiredPrivileges = 2;
        }
        *(_DWORD *)&RequiredPrivileges[4] = 1;
        pfResult = 0;
        if ( !PrivilegeCheck(v14, (PPRIVILEGE_SET)RequiredPrivileges, &pfResult) )
        {
          v39 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x14D,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
                  v45);
          v46 = v75;
          if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(v75);
          if ( v31 )
            Csl::DeleteSecurityObjectWrapper(v31, v46);
          if ( NewDescriptor )
            Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v46);
          if ( v17 )
            Csl::DeleteSecurityObjectWrapper(v17, v46);
          if ( v26 )
            LocalFree(v26);
          if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v14);
          goto LABEL_193;
        }
        if ( !pfResult )
        {
          v39 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x151,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
                  (const char *)0x522,
                  Tokena);
          v47 = v75;
          if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(v75);
          if ( v31 )
            Csl::DeleteSecurityObjectWrapper(v31, v47);
          if ( NewDescriptor )
            Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v47);
          if ( v17 )
            Csl::DeleteSecurityObjectWrapper(v17, v47);
          if ( v26 )
            LocalFree(v26);
          if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v14);
          goto LABEL_193;
        }
        LODWORD(hObject) = 0;
        v48 = -6;
        if ( *(_QWORD *)(a3 + 56) )
          v48 = *(_QWORD *)(a3 + 56);
        LODWORD(hMem) = 4;
        if ( !GetTokenInformation((HANDLE)v48, TokenImpersonationLevel, &hObject, 4u, (PDWORD)&hMem) )
        {
          v50 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x128,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
                  v49);
          v39 = v50;
          if ( v50 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x159,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
              (const char *)(unsigned int)v50,
              Tokenb);
            if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              CloseHandle(v75);
            if ( v31 )
              Csl::DeleteSecurityObjectWrapper(v31, v51);
            if ( NewDescriptor )
              Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v51);
            if ( v17 )
              Csl::DeleteSecurityObjectWrapper(v17, v51);
            if ( v26 )
              LocalFree(v26);
            if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v14);
            goto LABEL_193;
          }
        }
        if ( (int)hObject < 2 )
        {
          v39 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x15D,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
                  (const char *)0x542,
                  Tokenb);
          v52 = v75;
          if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(v75);
          if ( v31 )
            Csl::DeleteSecurityObjectWrapper(v31, v52);
          if ( NewDescriptor )
            Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v52);
          if ( v17 )
            Csl::DeleteSecurityObjectWrapper(v17, v52);
          if ( v26 )
            LocalFree(v26);
          if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v14);
          goto LABEL_193;
        }
      }
      else
      {
        v53 = (HANDLE *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&v75);
        CurrentProcess = GetCurrentProcess();
        v55 = GetCurrentProcess();
        if ( !DuplicateHandle(v55, v14, CurrentProcess, v53, 0xEu, 0, 0) )
        {
          v39 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x16B,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
                  v56);
          v57 = v75;
          if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(v75);
          if ( v31 )
            Csl::DeleteSecurityObjectWrapper(v31, v57);
          if ( NewDescriptor )
            Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v57);
          if ( v17 )
            Csl::DeleteSecurityObjectWrapper(v17, v57);
          if ( v26 )
            LocalFree(v26);
          if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v14);
          goto LABEL_193;
        }
      }
      v44 = v75;
    }
    v58 = 0;
    if ( (_QWORD)v81 )
    {
      BYTE8(v81) = 1;
      v58 = v81;
    }
    v59 = (_QWORD *)(a3 + 56);
    if ( (((unsigned __int64)v44 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      *v59 = v44;
    hMem = 0;
    v81 = v58;
    Container = Container::Manager::Core::CreateContainer(v82, (unsigned int)v79, a3, v80);
    v36 = Container;
    if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      *v59 = 0;
    if ( Container < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)Container,
        (int)v31);
      v63 = hMem;
      if ( hMem )
      {
        Container::Manager::Core::ContainerHandle::~ContainerHandle((Container::Manager::Core::ContainerHandle *)hMem);
        operator delete(v63, (const struct std::nothrow_t *)0x58);
      }
      if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v75);
      if ( v31 )
        Csl::DeleteSecurityObjectWrapper(v31, v62);
      if ( NewDescriptor )
        Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v62);
      if ( v17 )
        Csl::DeleteSecurityObjectWrapper(v17, v62);
      if ( v26 )
        LocalFree(v26);
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v14);
      goto LABEL_232;
    }
    v79 = 0;
    v80 = hMem;
    LOBYTE(v61) = v72;
    v64 = CreateContainerRpcContextHandle(&v80, v26, AccessMask, v61);
    v36 = v64;
    if ( v64 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v64,
        (int)&v79);
      v66 = v79;
      if ( v79 )
      {
        Container::Manager::Service::ContainerRpcContextHandle::~ContainerRpcContextHandle(v79);
        operator delete(v66, (const struct std::nothrow_t *)0x18);
      }
      if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v75);
      if ( v31 )
        Csl::DeleteSecurityObjectWrapper(v31, v65);
      if ( NewDescriptor )
        Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v65);
      if ( v17 )
        Csl::DeleteSecurityObjectWrapper(v17, v65);
      if ( v26 )
        LocalFree(v26);
      if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v14);
      goto LABEL_232;
    }
    v67 = v79;
    *v83 = *(_QWORD *)(*((_QWORD *)v79 + 1) + 88LL);
    *v84 = v67;
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v85, 0);
    if ( (char *)v75 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v75);
    if ( v31 )
      Csl::DeleteSecurityObjectWrapper(v31, v68);
    if ( NewDescriptor )
      Csl::DeleteSecurityObjectWrapper((Csl *)NewDescriptor, v68);
    if ( v17 )
      Csl::DeleteSecurityObjectWrapper(v17, v68);
    if ( v26 )
      LocalFree(v26);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v14);
    v85[0] = &CmTraceProvider::CreateContainer::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v85);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v85);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      v12);
  }
  return result;
}

```

## disassembly

```asm
0x180018120  push    rbx
0x180018122  push    rsi
0x180018123  push    rdi
0x180018124  push    r12
0x180018126  push    r13
0x180018128  push    r14
0x18001812a  push    r15
0x18001812c  sub     rsp, 230h
0x180018133  mov     rax, cs:__security_cookie
0x18001813a  xor     rax, rsp
0x18001813d  mov     [rsp+268h+var_48], rax
0x180018145  mov     qword ptr [rsp+268h+var_1E8], r9
0x18001814d  mov     r12, r8
0x180018150  mov     edi, edx
0x180018152  mov     dword ptr [rsp+268h+var_1F8], edx
0x180018156  mov     rbx, rcx
0x180018159  mov     [rsp+268h+var_1D8], rcx
0x180018161  mov     r14, [rsp+268h+SecurityDescriptorInput]
0x180018169  mov     rax, [rsp+268h+arg_38]
0x180018171  mov     [rsp+268h+var_1D0], rax
0x180018179  mov     rcx, [rsp+268h+arg_40]
0x180018181  mov     [rsp+268h+var_1C8], rcx
0x180018189  xor     edx, edx
0x18001818b  mov     [rax], rdx
0x18001818e  xor     r15d, r15d
0x180018191  mov     [rcx], r15
0x180018194  lea     rdx, aCreatecontaine_7; "CreateContainer"
0x18001819b  lea     rcx, [rsp+268h+var_1B8]
0x1800181a3  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800181a8  lea     rsi, ??_7CreateContainer@CmTraceProvider@@6B@; const CmTraceProvider::CreateContainer::`vftable'
0x1800181af  mov     [rsp+268h+var_1B8], rsi
0x1800181b7  mov     eax, [r12+8]
0x1800181bc  mov     dword ptr [rsp+268h+Token], eax; int
0x1800181c0  mov     r9, [r12]
0x1800181c4  mov     r8d, edi
0x1800181c7  mov     rdx, rbx
0x1800181ca  lea     rcx, [rsp+268h+var_1B8]
0x1800181d2  call    ?StartActivity@CreateContainer@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@PEBGW4_CMS_CONTAINER_TELEMETRY_ID@@@Z; CmTraceProvider::CreateContainer::StartActivity(_GUID const &,_CMS_CLIENT_ID,ushort const *,_CMS_CONTAINER_TELEMETRY_ID)
0x1800181d7  nop
0x1800181d8  mov     [rsp+268h+hObject], r15
0x1800181dd  lea     rdx, [rsp+268h+hObject]
0x1800181e2  lea     ecx, [r15+0Ah]
0x1800181e6  call    ?OpenRpcClientAccessToken@Rpc@Manager@Container@@YAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Container::Manager::Rpc::OpenRpcClientAccessToken(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800181eb  mov     ebx, eax
0x1800181ed  test    eax, eax
0x1800181ef  jns     short loc_180018254
0x1800181f1  mov     rcx, [rsp+268h]; this
0x1800181f9  mov     r9d, eax; char *
0x1800181fc  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180018203  mov     edx, 97h; void *
0x180018208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001820d  mov     rdx, [rsp+268h+hObject]
0x180018212  lea     rcx, [rdx-1]
0x180018216  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001821a  ja      short loc_18001822B
0x18001821c  mov     rcx, rdx; hObject
0x18001821f  call    cs:__imp_CloseHandle
0x180018226  nop     dword ptr [rax+rax+00h]
0x18001822b  mov     [rsp+268h+var_1B8], rsi
0x180018233  lea     rcx, [rsp+268h+var_1B8]
0x18001823b  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180018240  lea     rcx, [rsp+268h+var_1B8]
0x180018248  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001824d  mov     eax, ebx
0x18001824f  jmp     loc_18001932F
0x180018254  mov     [rsp+268h+hMem], r15
0x180018259  lea     rdx, [rsp+268h+hMem]
0x18001825e  mov     r13, [rsp+268h+hObject]
0x180018263  mov     rcx, r13
0x180018266  call    ?GetUserSidFromToken@Csl@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Csl::GetUserSidFromToken(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18001826b  mov     ebx, eax
0x18001826d  test    eax, eax
0x18001826f  jns     short loc_1800182E5
0x180018271  mov     rcx, [rsp+268h]; this
0x180018279  mov     r9d, eax; char *
0x18001827c  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180018283  mov     edx, 9Bh; void *
0x180018288  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001828d  mov     rcx, [rsp+268h+hMem]; hMem
0x180018292  test    rcx, rcx
0x180018295  jz      short loc_1800182A3
0x180018297  call    cs:__imp_LocalFree
0x18001829e  nop     dword ptr [rax+rax+00h]
0x1800182a3  lea     rax, [r13-1]
0x1800182a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800182ab  ja      short loc_1800182BC
0x1800182ad  mov     rcx, r13; hObject
0x1800182b0  call    cs:__imp_CloseHandle
0x1800182b7  nop     dword ptr [rax+rax+00h]
0x1800182bc  mov     [rsp+268h+var_1B8], rsi
0x1800182c4  lea     rcx, [rsp+268h+var_1B8]
0x1800182cc  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800182d1  lea     rcx, [rsp+268h+var_1B8]
0x1800182d9  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800182de  mov     eax, ebx
0x1800182e0  jmp     loc_18001932F
0x1800182e5  mov     rdi, r15
0x1800182e8  mov     [rsp+268h+hObject], r15
0x1800182ed  mov     [rsp+268h+NewDescriptor], r15
0x1800182f2  test    r14, r14
0x1800182f5  jz      loc_1800184AF
0x1800182fb  xor     r8d, r8d; RequiredInformation
0x1800182fe  mov     edx, [rsp+268h+SecurityDescriptorLength]; SecurityDescriptorLength
0x180018305  mov     rcx, r14; SecurityDescriptorInput
0x180018308  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18001830f  nop     dword ptr [rax+rax+00h]
0x180018314  test    al, al
0x180018316  jnz     loc_1800183A5
0x18001831c  mov     rcx, [rsp+268h]; this
0x180018324  mov     ebx, 80070057h
0x180018329  mov     r9d, ebx; char *
0x18001832c  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180018333  mov     edx, 0ACh; void *
0x180018338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001833d  mov     rcx, [rsp+268h+NewDescriptor]; this
0x180018342  test    rcx, rcx
0x180018345  jz      short loc_18001834D
0x180018347  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x18001834c  nop
0x18001834d  mov     rcx, [rsp+268h+hMem]; hMem
0x180018352  test    rcx, rcx
0x180018355  jz      short loc_180018363
0x180018357  call    cs:__imp_LocalFree
0x18001835e  nop     dword ptr [rax+rax+00h]
0x180018363  lea     rcx, [r13-1]
0x180018367  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001836b  ja      short loc_18001837C
0x18001836d  mov     rcx, r13; hObject
0x180018370  call    cs:__imp_CloseHandle
0x180018377  nop     dword ptr [rax+rax+00h]
0x18001837c  mov     [rsp+268h+var_1B8], rsi
0x180018384  lea     rcx, [rsp+268h+var_1B8]
0x18001838c  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180018391  lea     rcx, [rsp+268h+var_1B8]
0x180018399  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001839e  mov     eax, ebx
0x1800183a0  jmp     loc_18001932F
0x1800183a5  mov     rbx, [rsp+268h+NewDescriptor]
0x1800183aa  test    rbx, rbx
0x1800183ad  jz      short loc_1800183DB
0x1800183af  call    cs:__imp_GetLastError
0x1800183b6  nop     dword ptr [rax+rax+00h]
0x1800183bb  mov     esi, eax
0x1800183bd  mov     rcx, rbx; this
0x1800183c0  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x1800183c5  nop
0x1800183c6  mov     ecx, esi; dwErrCode
0x1800183c8  call    cs:__imp_SetLastError
0x1800183cf  nop     dword ptr [rax+rax+00h]
0x1800183d4  lea     rsi, ??_7CreateContainer@CmTraceProvider@@6B@; const CmTraceProvider::CreateContainer::`vftable'
0x1800183db  mov     [rsp+268h+NewDescriptor], r15
0x1800183e0  lea     r15, stru_1801D0FA0
0x1800183e7  mov     [rsp+268h+GenericMapping], r15; GenericMapping
0x1800183ec  mov     [rsp+268h+Token], r13; int
0x1800183f1  xor     r9d, r9d; IsDirectoryObject
0x1800183f4  lea     r8, [rsp+268h+NewDescriptor]; NewDescriptor
0x1800183f9  mov     rdx, r14; CreatorDescriptor
0x1800183fc  xor     ecx, ecx; ParentDescriptor
0x1800183fe  call    cs:__imp_RtlNewSecurityObject
0x180018405  nop     dword ptr [rax+rax+00h]
0x18001840a  xor     r15d, r15d
0x18001840d  test    eax, eax
0x18001840f  jns     loc_18001849B
0x180018415  mov     rcx, [rsp+268h]; this
0x18001841d  mov     r9d, eax; char *
0x180018420  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180018427  mov     edx, 0BAh; void *
0x18001842c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180018431  mov     ebx, eax
0x180018433  mov     rcx, [rsp+268h+NewDescriptor]; this
0x180018438  test    rcx, rcx
0x18001843b  jz      short loc_180018443
0x18001843d  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x180018442  nop
0x180018443  mov     rcx, [rsp+268h+hMem]; hMem
0x180018448  test    rcx, rcx
0x18001844b  jz      short loc_180018459
0x18001844d  call    cs:__imp_LocalFree
0x180018454  nop     dword ptr [rax+rax+00h]
0x180018459  lea     rax, [r13-1]
0x18001845d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018461  ja      short loc_180018472
0x180018463  mov     rcx, r13; hObject
0x180018466  call    cs:__imp_CloseHandle
0x18001846d  nop     dword ptr [rax+rax+00h]
0x180018472  mov     [rsp+268h+var_1B8], rsi
0x18001847a  lea     rcx, [rsp+268h+var_1B8]
0x180018482  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180018487  lea     rcx, [rsp+268h+var_1B8]
0x18001848f  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180018494  mov     eax, ebx
0x180018496  jmp     loc_18001932F
0x18001849b  mov     rax, [rsp+268h+NewDescriptor]
0x1800184a0  mov     [rsp+268h+var_1F0], rax
0x1800184a5  mov     rbx, [rsp+268h+hMem]
0x1800184aa  jmp     loc_180018612
0x1800184af  cmp     [rsp+268h+SecurityDescriptorLength], r15d
0x1800184b7  jz      loc_180018546
0x1800184bd  mov     rcx, [rsp+268h]; this
0x1800184c5  mov     ebx, 80070057h
0x1800184ca  mov     r9d, ebx; char *
0x1800184cd  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x1800184d4  mov     edx, 0C2h; void *
0x1800184d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184de  mov     rcx, [rsp+268h+NewDescriptor]; this
0x1800184e3  test    rcx, rcx
0x1800184e6  jz      short loc_1800184EE
0x1800184e8  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x1800184ed  nop
0x1800184ee  mov     rcx, [rsp+268h+hMem]; hMem
0x1800184f3  test    rcx, rcx
0x1800184f6  jz      short loc_180018504
0x1800184f8  call    cs:__imp_LocalFree
0x1800184ff  nop     dword ptr [rax+rax+00h]
0x180018504  lea     rax, [r13-1]
0x180018508  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001850c  ja      short loc_18001851D
0x18001850e  mov     rcx, r13; hObject
0x180018511  call    cs:__imp_CloseHandle
0x180018518  nop     dword ptr [rax+rax+00h]
0x18001851d  mov     [rsp+268h+var_1B8], rsi
0x180018525  lea     rcx, [rsp+268h+var_1B8]
0x18001852d  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180018532  lea     rcx, [rsp+268h+var_1B8]
0x18001853a  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001853f  mov     eax, ebx
0x180018541  jmp     loc_18001932F
0x180018546  lea     rax, [rsp+268h+hObject]
0x18001854b  mov     [rsp+268h+Token], rax; int
0x180018550  mov     r9, r13; int
0x180018553  lea     r8, stru_1801D0FA0; GenericMapping
0x18001855a  mov     edx, 0F00FFh; AccessMask
0x18001855f  mov     rbx, [rsp+268h+hMem]
0x180018564  mov     rcx, rbx; Sid
0x180018567  call    ?CreateDefaultSecurityDescriptor@Csl@@YAJPEAXKPEAU_GENERIC_MAPPING@@0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@_E$1?DeleteSecurityObjectWrapper@Csl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x18001856c  mov     edi, eax
0x18001856e  test    eax, eax
0x180018570  jns     loc_180018608
0x180018576  mov     rcx, [rsp+268h]; this
0x18001857e  mov     r9d, eax; char *
0x180018581  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180018588  mov     edx, 0CBh; void *
0x18001858d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018592  mov     rcx, [rsp+268h+NewDescriptor]; this
0x180018597  test    rcx, rcx
0x18001859a  jz      short loc_1800185A2
0x18001859c  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x1800185a1  nop
0x1800185a2  mov     rcx, [rsp+268h+hObject]; this
0x1800185a7  test    rcx, rcx
0x1800185aa  jz      short loc_1800185B2
0x1800185ac  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x1800185b1  nop
0x1800185b2  test    rbx, rbx
0x1800185b5  jz      short loc_1800185C6
0x1800185b7  mov     rcx, rbx; hMem
0x1800185ba  call    cs:__imp_LocalFree
0x1800185c1  nop     dword ptr [rax+rax+00h]
0x1800185c6  lea     rax, [r13-1]
0x1800185ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800185ce  ja      short loc_1800185DF
0x1800185d0  mov     rcx, r13; hObject
0x1800185d3  call    cs:__imp_CloseHandle
0x1800185da  nop     dword ptr [rax+rax+00h]
0x1800185df  mov     [rsp+268h+var_1B8], rsi
0x1800185e7  lea     rcx, [rsp+268h+var_1B8]
0x1800185ef  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800185f4  lea     rcx, [rsp+268h+var_1B8]
0x1800185fc  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180018601  mov     eax, edi
0x180018603  jmp     loc_18001932F
0x180018608  mov     rdi, [rsp+268h+hObject]
0x18001860d  mov     [rsp+268h+var_1F0], rdi
0x180018612  mov     rsi, r15
0x180018615  mov     [rsp+268h+hMem], r15
0x18001861a  cmp     qword ptr [rsp+268h+var_1E8], r15
0x180018622  jnz     loc_1800186FF
0x180018628  lea     rax, [rsp+268h+hMem]
0x18001862d  mov     [rsp+268h+Token], rax; unsigned int
0x180018632  mov     r9, r13; int
0x180018635  lea     r8, GenericMapping; GenericMapping
0x18001863c  mov     edx, 1F01BFh; AccessMask
0x180018641  mov     rcx, rbx; Sid
0x180018644  call    ?CreateDefaultSecurityDescriptor@Csl@@YAJPEAXKPEAU_GENERIC_MAPPING@@0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@_E$1?DeleteSecurityObjectWrapper@Csl@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z
0x180018649  mov     esi, eax
0x18001864b  test    eax, eax
0x18001864d  jns     loc_1800186FA
0x180018653  mov     rcx, [rsp+268h]; this
0x18001865b  mov     r9d, eax; char *
0x18001865e  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180018665  mov     edx, 0DBh; void *
0x18001866a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001866f  mov     rcx, [rsp+268h+hMem]; this
0x180018674  test    rcx, rcx
0x180018677  jz      short loc_18001867F
0x180018679  call    ?DeleteSecurityObjectWrapper@Csl@@YAXPEAX@Z; Csl::DeleteSecurityObjectWrapper(void *)
0x18001867e  nop
0x18001867f  mov     rcx, [rsp+268h+NewDescriptor]; this
0x180018684  test    rcx, rcx
0x180018687  jz      short loc_18001868F
  ... truncated ...
```
