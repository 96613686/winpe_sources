# CmsRpcSrv_MapVirtualDiskToContainer

- ea: `0x18001bfb0`
- end: `0x18001c760`
- name: `CmsRpcSrv_MapVirtualDiskToContainer`
- size: `1968`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007c0c`
- `0x180007e54`
- `0x180008d04`
- `0x180009cc0`
- `0x18000da68`
- `0x18000da88`
- `0x18000dad8`
- `0x18000f6d4`
- `0x18001063c`
- `0x180016ad4`
- `0x18001bfb0`
- `0x18002e324`
- `0x18002fc34`
- `0x180067600`
- `0x180190a40`
- `0x180190f8c`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x18001c03e`
- `ntdll!RtlAreAllAccessesGranted` at `0x18001c03e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c16c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c16c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c27a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c30e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c31d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c390`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c650`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c704`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c26b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c27a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c30e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c31d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c390`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c39f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c471`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c57e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c650`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c65f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c6f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c704`

## string_xrefs

- `0x18001c05c`: `onecore\base\gendrv\silos\clem\service\RpcContextHandles.h`
- `0x18001c07c`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c0e7`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c194`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c241`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c2ee`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c36e`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c436`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c522`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001c5f4`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRpcSrv_MapVirtualDiskToContainer(ACCESS_MASK *a1, const WCHAR *a2, const WCHAR *a3)
{
  unsigned int v6; // ebx
  void *v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // ebx
  char *FileW; // rbx
  const char *v15; // r9
  unsigned int LastError; // edi
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rdi
  __int64 v23; // rax
  int v24; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-218h]
  bool *dwCreationDispositiona; // [rsp+20h] [rbp-218h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-218h]
  unsigned int v28; // [rsp+40h] [rbp-1F8h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-1F0h] BYREF
  const WCHAR *v30; // [rsp+50h] [rbp-1E8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-1E0h]
  void *v32[2]; // [rsp+60h] [rbp-1D8h] BYREF
  _WORD v33[8]; // [rsp+70h] [rbp-1C8h] BYREF
  void *v34[2]; // [rsp+80h] [rbp-1B8h] BYREF
  _WORD v35[8]; // [rsp+90h] [rbp-1A8h] BYREF
  _QWORD v36[42]; // [rsp+A0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v6 = *(_DWORD *)(*(_QWORD *)a1 + 8LL);
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v36,
    "MapVirtualDiskToContainer");
  v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
  dwCreationDisposition = v6;
  try
  {
    CmTraceProvider::MapVirtualDiskToContainer::StartActivity();
    if ( !RtlAreAllAccessesGranted(a1[4], 0x40u) )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\RpcContextHandles.h",
             (const char *)5,
             v6);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x624,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v8,
          dwCreationDisposition);
        v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
        return v9;
      }
    }
    hObject = 0;
    v30 = 0;
    LOBYTE(v31) = 0;
    v12 = Container::Manager::Rpc::Impersonator::Impersonate((Container::Manager::Rpc::Impersonator *)&v30, v7);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v12,
        dwCreationDisposition);
      Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v30);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
      return v13;
    }
    FileW = (char *)CreateFileW(a2, 0x20000u, 3u, 0, 3u, 0, 0);
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x63D,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
                    v15);
      Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v30);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
      return LastError;
    }
    v17 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
    v18 = wil::open_current_access_token_nothrow(v17, 8);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x640,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v18,
        (int)dwCreationDispositiona);
      Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v30);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      CloseHandle(FileW);
      v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
      return v19;
    }
    Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v30);
    LOBYTE(v28) = 0;
    v20 = Csl::AccessCheckFile((Csl *)FileW, hObject, (void *)0x16019F, (unsigned int)&v28, dwCreationDispositiona);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v20,
        dwCreationDispositionb);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
LABEL_52:
      CloseHandle(FileW);
      v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
      return v21;
    }
    if ( !(_BYTE)v28 )
    {
      v21 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x651,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
              (const char *)5,
              dwCreationDispositionb);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_52;
    }
    v32[0] = v33;
    v32[1] = v33;
    v33[0] = 0;
    v30 = a2;
    v22 = -1;
    v23 = -1;
    do
      ++v23;
    while ( a2[v23] );
    v31 = v23;
    if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v32) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x656,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)0x8007000ELL,
        dwCreationDispositionb);
      if ( v32[0] != v33 )
        operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
LABEL_34:
      CloseHandle(FileW);
      v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
      return 2147942414LL;
    }
    v34[0] = v35;
    v34[1] = v35;
    v35[0] = 0;
    v30 = a3;
    do
      ++v22;
    while ( a3[v22] );
    v31 = v22;
    if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v34) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x659,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)0x8007000ELL,
        dwCreationDispositionb);
      if ( v34[0] != v35 )
        operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v32[0] != v33 )
        operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_34;
    }
    v24 = Container::Manager::Core::Activity::MapVirtualDisk(
            *(Container::Manager::Core::Activity **)a1,
            (const struct Path *)v32,
            (const struct Path *)v34);
    v21 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v24,
        dwCreationDispositionb);
      if ( v34[0] != v35 )
        operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v32[0] != v33 )
        operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      goto LABEL_52;
    }
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v36, 0);
    if ( v34[0] != v35 )
      operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v32[0] != v33 )
      operator delete(v32[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    CloseHandle(FileW);
    v36[0] = &CmTraceProvider::MapVirtualDiskToContainer::`vftable';
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v36);
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v36);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x663,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      v10);
  }
  return result;
}

```

## disassembly

```asm
0x18001bfb0  push    rbx
0x18001bfb2  push    rsi
0x18001bfb3  push    rdi
0x18001bfb4  push    r12
0x18001bfb6  push    r13
0x18001bfb8  push    r14
0x18001bfba  push    r15
0x18001bfbc  sub     rsp, 200h
0x18001bfc3  mov     rax, cs:__security_cookie
0x18001bfca  xor     rax, rsp
0x18001bfcd  mov     [rsp+238h+var_48], rax
0x18001bfd5  mov     r12, r8
0x18001bfd8  mov     r15, rdx
0x18001bfdb  mov     r13, rcx
0x18001bfde  mov     rax, [rcx]
0x18001bfe1  mov     ebx, [rax+8]
0x18001bfe4  mov     edi, [rax+4]
0x18001bfe7  mov     esi, [rax]
0x18001bfe9  mov     r14, [rax+28h]
0x18001bfed  lea     rdx, aMapvirtualdisk; "MapVirtualDiskToContainer"
0x18001bff4  lea     rcx, [rsp+238h+var_198]
0x18001bffc  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001c001  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c008  mov     [rsp+238h+var_198], rax
0x18001c010  mov     [rsp+238h+hTemplateFile], r12
0x18001c015  mov     qword ptr [rsp+238h+dwFlagsAndAttributes], r15
0x18001c01a  mov     dword ptr [rsp+238h+dwCreationDisposition], ebx; int
0x18001c01e  mov     r9d, edi
0x18001c021  mov     r8d, esi
0x18001c024  mov     rdx, r14
0x18001c027  lea     rcx, [rsp+238h+var_198]
0x18001c02f  call    ?StartActivity@MapVirtualDiskToContainer@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@KPEBG3@Z; CmTraceProvider::MapVirtualDiskToContainer::StartActivity(_GUID const &,_CMS_CLIENT_ID,_CMS_ACTIVITY_ID,ulong,ushort const *,ushort const *)
0x18001c034  nop
0x18001c035  mov     edx, 40h ; '@'; DesiredAccess
0x18001c03a  mov     ecx, [r13+10h]; GrantedAccess
0x18001c03e  call    cs:__imp_RtlAreAllAccessesGranted
0x18001c045  nop     dword ptr [rax+rax+00h]
0x18001c04a  xor     esi, esi
0x18001c04c  test    al, al
0x18001c04e  jnz     short loc_18001C0BD
0x18001c050  mov     rcx, [rsp+238h]; this
0x18001c058  lea     r9d, [rsi+5]; char *
0x18001c05c  lea     r8, aOnecoreBaseGen_15; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c063  lea     edx, [rsi+7Ah]; void *
0x18001c066  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c06b  mov     ebx, eax
0x18001c06d  test    eax, eax
0x18001c06f  jns     short loc_18001C0BD
0x18001c071  mov     rcx, [rsp+238h]; this
0x18001c079  mov     r9d, eax; char *
0x18001c07c  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c083  mov     edx, 624h; void *
0x18001c088  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c08d  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c094  mov     [rsp+238h+var_198], rax
0x18001c09c  lea     rcx, [rsp+238h+var_198]
0x18001c0a4  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c0a9  lea     rcx, [rsp+238h+var_198]
0x18001c0b1  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c0b6  mov     eax, ebx
0x18001c0b8  jmp     loc_18001C73C
0x18001c0bd  mov     [rsp+238h+hObject], rsi
0x18001c0c2  mov     [rsp+238h+var_1E8], rsi
0x18001c0c7  mov     byte ptr [rsp+238h+var_1E0], sil
0x18001c0cc  lea     rcx, [rsp+238h+var_1E8]; this
0x18001c0d1  call    ?Impersonate@Impersonator@Rpc@Manager@Container@@QEAAJPEAX@Z; Container::Manager::Rpc::Impersonator::Impersonate(void *)
0x18001c0d6  mov     ebx, eax
0x18001c0d8  test    eax, eax
0x18001c0da  jns     short loc_18001C14D
0x18001c0dc  mov     rcx, [rsp+238h]; this
0x18001c0e4  mov     r9d, eax; char *
0x18001c0e7  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c0ee  mov     edx, 62Fh; void *
0x18001c0f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0f8  lea     rcx, [rsp+238h+var_1E8]; this
0x18001c0fd  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x18001c102  mov     rcx, [rsp+238h+hObject]; hObject
0x18001c107  lea     rdx, [rcx-1]
0x18001c10b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c10f  ja      short loc_18001C11D
0x18001c111  call    cs:__imp_CloseHandle
0x18001c118  nop     dword ptr [rax+rax+00h]
0x18001c11d  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c124  mov     [rsp+238h+var_198], rax
0x18001c12c  lea     rcx, [rsp+238h+var_198]
0x18001c134  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c139  lea     rcx, [rsp+238h+var_198]
0x18001c141  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c146  mov     eax, ebx
0x18001c148  jmp     loc_18001C73C
0x18001c14d  mov     [rsp+238h+hTemplateFile], rsi; hTemplateFile
0x18001c152  mov     [rsp+238h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18001c156  mov     r8d, 3; dwShareMode
0x18001c15c  mov     dword ptr [rsp+238h+dwCreationDisposition], r8d; int
0x18001c161  xor     r9d, r9d; lpSecurityAttributes
0x18001c164  mov     edx, 20000h; dwDesiredAccess
0x18001c169  mov     rcx, r15; lpFileName
0x18001c16c  call    cs:__imp_CreateFileW
0x18001c173  nop     dword ptr [rax+rax+00h]
0x18001c178  mov     rbx, rax
0x18001c17b  lea     rcx, [rax+1]
0x18001c17f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001c186  jnz     loc_18001C215
0x18001c18c  mov     rcx, [rsp+238h]; this
0x18001c194  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c19b  mov     edx, 63Dh; void *
0x18001c1a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001c1a5  mov     edi, eax
0x18001c1a7  lea     rcx, [rsp+238h+var_1E8]; this
0x18001c1ac  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x18001c1b1  mov     rcx, [rsp+238h+hObject]; hObject
0x18001c1b6  lea     rdx, [rcx-1]
0x18001c1ba  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c1be  ja      short loc_18001C1CC
0x18001c1c0  call    cs:__imp_CloseHandle
0x18001c1c7  nop     dword ptr [rax+rax+00h]
0x18001c1cc  lea     rcx, [rbx-1]
0x18001c1d0  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001c1d4  ja      short loc_18001C1E5
0x18001c1d6  mov     rcx, rbx; hObject
0x18001c1d9  call    cs:__imp_CloseHandle
0x18001c1e0  nop     dword ptr [rax+rax+00h]
0x18001c1e5  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c1ec  mov     [rsp+238h+var_198], rax
0x18001c1f4  lea     rcx, [rsp+238h+var_198]
0x18001c1fc  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c201  lea     rcx, [rsp+238h+var_198]
0x18001c209  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c20e  mov     eax, edi
0x18001c210  jmp     loc_18001C73C
0x18001c215  lea     rcx, [rsp+238h+hObject]
0x18001c21a  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x18001c21f  mov     rcx, rax
0x18001c222  mov     edx, 8
0x18001c227  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x18001c22c  mov     edi, eax
0x18001c22e  test    eax, eax
0x18001c230  jns     loc_18001C2B6
0x18001c236  mov     rcx, [rsp+238h]; this
0x18001c23e  mov     r9d, eax; char *
0x18001c241  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c248  mov     edx, 640h; void *
0x18001c24d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c252  lea     rcx, [rsp+238h+var_1E8]; this
0x18001c257  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x18001c25c  mov     rcx, [rsp+238h+hObject]; hObject
0x18001c261  lea     rdx, [rcx-1]
0x18001c265  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c269  ja      short loc_18001C277
0x18001c26b  call    cs:__imp_CloseHandle
0x18001c272  nop     dword ptr [rax+rax+00h]
0x18001c277  mov     rcx, rbx; hObject
0x18001c27a  call    cs:__imp_CloseHandle
0x18001c281  nop     dword ptr [rax+rax+00h]
0x18001c286  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c28d  mov     [rsp+238h+var_198], rax
0x18001c295  lea     rcx, [rsp+238h+var_198]
0x18001c29d  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c2a2  lea     rcx, [rsp+238h+var_198]
0x18001c2aa  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c2af  mov     eax, edi
0x18001c2b1  jmp     loc_18001C73C
0x18001c2b6  lea     rcx, [rsp+238h+var_1E8]; this
0x18001c2bb  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x18001c2c0  mov     byte ptr [rsp+238h+var_1F8], sil
0x18001c2c5  lea     r9, [rsp+238h+var_1F8]; unsigned int
0x18001c2ca  mov     r8d, 16019Fh; void *
0x18001c2d0  mov     rdx, [rsp+238h+hObject]; void *
0x18001c2d5  mov     rcx, rbx; this
0x18001c2d8  call    ?AccessCheckFile@Csl@@YAJPEAX0KAEA_N@Z; Csl::AccessCheckFile(void *,void *,ulong,bool &)
0x18001c2dd  mov     edi, eax
0x18001c2df  test    eax, eax
0x18001c2e1  jns     short loc_18001C359
0x18001c2e3  mov     rcx, [rsp+238h]; this
0x18001c2eb  mov     r9d, eax; char *
0x18001c2ee  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c2f5  mov     edx, 64Dh; void *
0x18001c2fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2ff  mov     rcx, [rsp+238h+hObject]; hObject
0x18001c304  lea     rdx, [rcx-1]
0x18001c308  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c30c  ja      short loc_18001C31A
0x18001c30e  call    cs:__imp_CloseHandle
0x18001c315  nop     dword ptr [rax+rax+00h]
0x18001c31a  mov     rcx, rbx; hObject
0x18001c31d  call    cs:__imp_CloseHandle
0x18001c324  nop     dword ptr [rax+rax+00h]
0x18001c329  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c330  mov     [rsp+238h+var_198], rax
0x18001c338  lea     rcx, [rsp+238h+var_198]
0x18001c340  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c345  lea     rcx, [rsp+238h+var_198]
0x18001c34d  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c352  mov     eax, edi
0x18001c354  jmp     loc_18001C73C
0x18001c359  cmp     byte ptr [rsp+238h+var_1F8], sil
0x18001c35e  jnz     short loc_18001C3DB
0x18001c360  mov     rcx, [rsp+238h]; this
0x18001c368  mov     r9d, 5; char *
0x18001c36e  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c375  mov     edx, 651h; void *
0x18001c37a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c37f  mov     edi, eax
0x18001c381  mov     rcx, [rsp+238h+hObject]; hObject
0x18001c386  lea     rdx, [rcx-1]
0x18001c38a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c38e  ja      short loc_18001C39C
0x18001c390  call    cs:__imp_CloseHandle
0x18001c397  nop     dword ptr [rax+rax+00h]
0x18001c39c  mov     rcx, rbx; hObject
0x18001c39f  call    cs:__imp_CloseHandle
0x18001c3a6  nop     dword ptr [rax+rax+00h]
0x18001c3ab  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c3b2  mov     [rsp+238h+var_198], rax
0x18001c3ba  lea     rcx, [rsp+238h+var_198]
0x18001c3c2  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c3c7  lea     rcx, [rsp+238h+var_198]
0x18001c3cf  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c3d4  mov     eax, edi
0x18001c3d6  jmp     loc_18001C73C
0x18001c3db  lea     rax, [rsp+238h+var_1C8]
0x18001c3e0  mov     [rsp+238h+var_1D8], rax
0x18001c3e5  lea     rax, [rsp+238h+var_1C8]
0x18001c3ea  mov     [rsp+238h+var_1D0], rax
0x18001c3ef  mov     [rsp+238h+var_1C8], si
0x18001c3f4  mov     [rsp+238h+var_1E8], r15
0x18001c3f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c3fd  mov     rax, rdi
0x18001c400  inc     rax
0x18001c403  cmp     [r15+rax*2], si
0x18001c408  jnz     short loc_18001C400
0x18001c40a  mov     [rsp+238h+var_1E0], rax
0x18001c40f  lea     rdx, [rsp+238h+var_1E8]
0x18001c414  lea     rcx, [rsp+238h+var_1D8]; this
0x18001c419  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18001c41e  test    al, al
0x18001c420  jnz     loc_18001C4BC
0x18001c426  mov     rcx, [rsp+238h]; this
0x18001c42e  mov     edi, 8007000Eh
0x18001c433  mov     r9d, edi; char *
0x18001c436  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c43d  mov     edx, 656h; void *
0x18001c442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c447  mov     rcx, [rsp+238h+var_1D8]; void *
0x18001c44c  lea     rax, [rsp+238h+var_1C8]
0x18001c451  cmp     rcx, rax
0x18001c454  jz      short loc_18001C462
0x18001c456  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c45d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c462  mov     rcx, [rsp+238h+hObject]; hObject
0x18001c467  lea     rdx, [rcx-1]
0x18001c46b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001c46f  ja      short loc_18001C47D
0x18001c471  call    cs:__imp_CloseHandle
0x18001c478  nop     dword ptr [rax+rax+00h]
0x18001c47d  mov     rcx, rbx; hObject
0x18001c480  call    cs:__imp_CloseHandle
0x18001c487  nop     dword ptr [rax+rax+00h]
0x18001c48c  lea     rax, ??_7MapVirtualDiskToContainer@CmTraceProvider@@6B@; const CmTraceProvider::MapVirtualDiskToContainer::`vftable'
0x18001c493  mov     [rsp+238h+var_198], rax
0x18001c49b  lea     rcx, [rsp+238h+var_198]
0x18001c4a3  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001c4a8  lea     rcx, [rsp+238h+var_198]
0x18001c4b0  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001c4b5  mov     eax, edi
0x18001c4b7  jmp     loc_18001C73C
0x18001c4bc  lea     rax, [rsp+238h+var_1A8]
0x18001c4c4  mov     [rsp+238h+var_1B8], rax
0x18001c4cc  lea     rax, [rsp+238h+var_1A8]
0x18001c4d4  mov     [rsp+238h+var_1B0], rax
0x18001c4dc  mov     [rsp+238h+var_1A8], si
0x18001c4e4  mov     [rsp+238h+var_1E8], r12
0x18001c4e9  inc     rdi
0x18001c4ec  cmp     [r12+rdi*2], si
0x18001c4f1  jnz     short loc_18001C4E9
0x18001c4f3  mov     [rsp+238h+var_1E0], rdi
0x18001c4f8  lea     rdx, [rsp+238h+var_1E8]
0x18001c4fd  lea     rcx, [rsp+238h+var_1B8]; this
0x18001c505  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18001c50a  test    al, al
0x18001c50c  jnz     loc_18001C5C9
0x18001c512  mov     rcx, [rsp+238h]; this
0x18001c51a  mov     edi, 8007000Eh
0x18001c51f  mov     r9d, edi; char *
0x18001c522  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001c529  mov     edx, 659h; void *
0x18001c52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c533  mov     rcx, [rsp+238h+var_1B8]; void *
0x18001c53b  lea     rax, [rsp+238h+var_1A8]
0x18001c543  cmp     rcx, rax
0x18001c546  jz      short loc_18001C554
0x18001c548  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c54f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c554  mov     rcx, [rsp+238h+var_1D8]; void *
0x18001c559  lea     rax, [rsp+238h+var_1C8]
0x18001c55e  cmp     rcx, rax
0x18001c561  jz      short loc_18001C56F
0x18001c563  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001c56a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001c56f  mov     rcx, [rsp+238h+hObject]; hObject
  ... truncated ...
```
