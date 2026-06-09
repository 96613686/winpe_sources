# CmsRpcSrv_GetContainerSecurityInformation

- ea: `0x18001a350`
- end: `0x18001a706`
- name: `CmsRpcSrv_GetContainerSecurityInformation`
- size: `950`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004bd0`
- `0x1800069db`
- `0x180007c0c`
- `0x180007e54`
- `0x180009cc0`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x18000ef2c`
- `0x18001063c`
- `0x18001a350`
- `0x180191360`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x18001a3f3`
- `ntdll!RtlAreAllAccessesGranted` at `0x18001a3f3`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001a5cf`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001a5cf`
- `ntdll!RtlQuerySecurityObject` at `0x18001a490`
- `ntdll!RtlQuerySecurityObject` at `0x18001a525`
- `ntdll!RtlQuerySecurityObject` at `0x18001a490`
- `ntdll!RtlQuerySecurityObject` at `0x18001a525`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a4d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a55a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a615`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a66e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a55a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a615`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a66e`

## string_xrefs

- `0x18001a395`: `GetContainerSecurityInformation`
- `0x18001a411`: `onecore\base\gendrv\silos\clem\service\RpcContextHandles.h`
- `0x18001a432`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001a591`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001a5fc`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001a6cf`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001a4b6`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18001a4fb`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`
- `0x18001a544`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRpcSrv_GetContainerSecurityInformation(
        ACCESS_MASK *a1,
        SECURITY_INFORMATION a2,
        _QWORD *a3,
        _DWORD *a4)
{
  ACCESS_MASK v8; // edx
  int v9; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 result; // rax
  void *v13; // rbx
  void *v14; // rdi
  NTSTATUS SecurityObject; // eax
  unsigned int v16; // edi
  HLOCAL v17; // r14
  NTSTATUS v18; // eax
  size_t v19; // rsi
  void *v20; // rax
  void *v21; // rdi
  unsigned int ReturnLength; // [rsp+20h] [rbp-1B8h]
  int ReturnLengtha; // [rsp+20h] [rbp-1B8h]
  int ReturnLengthb; // [rsp+20h] [rbp-1B8h]
  int ReturnLengthc; // [rsp+20h] [rbp-1B8h]
  ULONG DescriptorLength[4]; // [rsp+30h] [rbp-1A8h] BYREF
  _QWORD v27[42]; // [rsp+40h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  *a3 = 0;
  *a4 = 0;
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v27,
    "GetContainerSecurityInformation");
  v27[0] = &CmTraceProvider::GetContainerSecurityInformation::`vftable';
  try
  {
    CmTraceProvider::GetContainerSecurityInformation::StartActivity();
    if ( !a2 || (a2 & 0xFFFFFFF0) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D9,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)0x80070057LL,
        ReturnLength);
      v27[0] = &CmTraceProvider::GetContainerSecurityInformation::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v27);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v27);
      return 2147942487LL;
    }
    v8 = ((a2 & 8) << 21) | 0x20000;
    if ( (a2 & 7) == 0 )
      v8 = (a2 & 8) << 21;
    if ( !RtlAreAllAccessesGranted(a1[4], v8) )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3B,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\RpcContextHandles.h",
             (const char *)5,
             ReturnLength);
      v10 = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v9,
          ReturnLengtha);
        v27[0] = &CmTraceProvider::GetContainerSecurityInformation::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v27);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v27);
        return v10;
      }
    }
    v13 = 0;
    v14 = *(void **)(*(_QWORD *)(*(_QWORD *)a1 + 8LL) + 80LL);
    DescriptorLength[0] = 0;
    SecurityObject = RtlQuerySecurityObject(v14, a2, 0, 0, DescriptorLength);
    if ( SecurityObject == -1073741789 )
    {
      v17 = LocalAlloc(0x40u, DescriptorLength[0]);
      if ( !v17 )
      {
        v16 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x361,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
          (const char *)0x8007000ELL,
          ReturnLengthb);
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1CDF,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)v16,
          ReturnLengthb);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F6,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)v16,
          ReturnLengthc);
        v27[0] = &CmTraceProvider::GetContainerSecurityInformation::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v27);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v27);
        return v16;
      }
      v18 = RtlQuerySecurityObject(v14, a2, v17, DescriptorLength[0], DescriptorLength);
      if ( v18 < 0 )
      {
        v16 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x368,
                (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
                (const char *)(unsigned int)v18,
                ReturnLengthb);
        LocalFree(v17);
LABEL_16:
        if ( (v16 & 0x80000000) != 0 )
          goto LABEL_17;
        goto LABEL_19;
      }
      v13 = v17;
    }
    else if ( SecurityObject < 0 )
    {
      v16 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x35A,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
              (const char *)(unsigned int)SecurityObject,
              ReturnLengthb);
      goto LABEL_16;
    }
LABEL_19:
    v19 = RtlLengthSecurityDescriptor(v13);
    v20 = MIDL_user_allocate(v19);
    v21 = v20;
    if ( v20 )
    {
      memcpy_0(v20, v13, v19);
      *a3 = v21;
      *a4 = v19;
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v27, 0);
      if ( v13 )
        LocalFree(v13);
      v27[0] = &CmTraceProvider::GetContainerSecurityInformation::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v27);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v27);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)0x8007000ELL,
        ReturnLengthb);
      if ( v13 )
        LocalFree(v13);
      v27[0] = &CmTraceProvider::GetContainerSecurityInformation::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v27);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v27);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x40E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      v11);
  }
  return result;
}

```

## disassembly

```asm
0x18001a350  push    rbx
0x18001a352  push    rsi
0x18001a353  push    rdi
0x18001a354  push    r12
0x18001a356  push    r14
0x18001a358  push    r15
0x18001a35a  sub     rsp, 1A8h
0x18001a361  mov     rax, cs:__security_cookie
0x18001a368  xor     rax, rsp
0x18001a36b  mov     [rsp+1D8h+var_48], rax
0x18001a373  mov     r12, r9
0x18001a376  mov     r15, r8
0x18001a379  mov     esi, edx
0x18001a37b  mov     r14, rcx
0x18001a37e  mov     qword ptr [r8], 0
0x18001a385  mov     dword ptr [r9], 0
0x18001a38c  mov     rax, [rcx]
0x18001a38f  mov     ebx, [rax]
0x18001a391  mov     rdi, [rax+8]
0x18001a395  lea     rdx, aGetcontainerse; "GetContainerSecurityInformation"
0x18001a39c  lea     rcx, [rsp+1D8h+var_198]
0x18001a3a1  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001a3a6  lea     rax, ??_7GetContainerSecurityInformation@CmTraceProvider@@6B@; const CmTraceProvider::GetContainerSecurityInformation::`vftable'
0x18001a3ad  mov     [rsp+1D8h+var_198], rax
0x18001a3b2  mov     r9d, esi
0x18001a3b5  mov     r8d, ebx
0x18001a3b8  mov     rdx, rdi
0x18001a3bb  lea     rcx, [rsp+1D8h+var_198]
0x18001a3c0  call    ?StartActivity@GetContainerSecurityInformation@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@K@Z; CmTraceProvider::GetContainerSecurityInformation::StartActivity(_GUID const &,_CMS_CLIENT_ID,ulong)
0x18001a3c5  nop
0x18001a3c6  test    esi, esi
0x18001a3c8  jz      loc_18001A6BF
0x18001a3ce  test    esi, 0FFFFFFF0h
0x18001a3d4  jnz     loc_18001A6BF
0x18001a3da  mov     ecx, esi
0x18001a3dc  and     ecx, 8
0x18001a3df  shl     ecx, 15h
0x18001a3e2  mov     edx, ecx
0x18001a3e4  bts     edx, 11h
0x18001a3e8  test    sil, 7
0x18001a3ec  cmovz   edx, ecx; DesiredAccess
0x18001a3ef  mov     ecx, [r14+10h]; GrantedAccess
0x18001a3f3  call    cs:__imp_RtlAreAllAccessesGranted
0x18001a3fa  nop     dword ptr [rax+rax+00h]
0x18001a3ff  test    al, al
0x18001a401  jnz     short loc_18001A46A
0x18001a403  mov     rcx, [rsp+1D8h]; this
0x18001a40b  mov     r9d, 5; char *
0x18001a411  lea     r8, aOnecoreBaseGen_15; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001a418  lea     edx, [r9+36h]; void *
0x18001a41c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a421  mov     ebx, eax
0x18001a423  test    eax, eax
0x18001a425  jns     short loc_18001A46A
0x18001a427  mov     rcx, [rsp+1D8h]; this
0x18001a42f  mov     r9d, eax; char *
0x18001a432  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001a439  mov     edx, 3F0h; void *
0x18001a43e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a443  lea     rax, ??_7GetContainerSecurityInformation@CmTraceProvider@@6B@; const CmTraceProvider::GetContainerSecurityInformation::`vftable'
0x18001a44a  mov     [rsp+1D8h+var_198], rax
0x18001a44f  lea     rcx, [rsp+1D8h+var_198]
0x18001a454  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a459  lea     rcx, [rsp+1D8h+var_198]
0x18001a45e  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a463  mov     eax, ebx
0x18001a465  jmp     loc_18001A69D
0x18001a46a  xor     ebx, ebx
0x18001a46c  mov     rax, [r14]
0x18001a46f  mov     rcx, [rax+8]
0x18001a473  mov     rdi, [rcx+50h]
0x18001a477  mov     [rsp+1D8h+DescriptorLength], ebx
0x18001a47b  lea     rax, [rsp+1D8h+DescriptorLength]
0x18001a480  mov     qword ptr [rsp+1D8h+ReturnLength], rax; int
0x18001a485  xor     r9d, r9d; DescriptorLength
0x18001a488  xor     r8d, r8d; ResultantDescriptor
0x18001a48b  mov     edx, esi; SecurityInformation
0x18001a48d  mov     rcx, rdi; ObjectDescriptor
0x18001a490  call    cs:__imp_RtlQuerySecurityObject
0x18001a497  nop     dword ptr [rax+rax+00h]
0x18001a49c  cmp     eax, 0C0000023h
0x18001a4a1  jz      short loc_18001A4CE
0x18001a4a3  test    eax, eax
0x18001a4a5  jns     loc_18001A5CC
0x18001a4ab  mov     rcx, [rsp+1D8h]; this
0x18001a4b3  mov     r9d, eax; char *
0x18001a4b6  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001a4bd  mov     edx, 35Ah; void *
0x18001a4c2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a4c7  mov     edi, eax
0x18001a4c9  jmp     loc_18001A566
0x18001a4ce  mov     edx, [rsp+1D8h+DescriptorLength]; uBytes
0x18001a4d2  mov     ecx, 40h ; '@'; uFlags
0x18001a4d7  call    cs:__imp_LocalAlloc
0x18001a4de  nop     dword ptr [rax+rax+00h]
0x18001a4e3  mov     r14, rax
0x18001a4e6  test    rax, rax
0x18001a4e9  jnz     short loc_18001A50E
0x18001a4eb  mov     rcx, [rsp+1D8h]; this
0x18001a4f3  mov     edi, 8007000Eh
0x18001a4f8  mov     r9d, edi; char *
0x18001a4fb  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001a502  mov     edx, 361h; void *
0x18001a507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a50c  jmp     short loc_18001A56A
0x18001a50e  lea     rax, [rsp+1D8h+DescriptorLength]
0x18001a513  mov     qword ptr [rsp+1D8h+ReturnLength], rax; int
0x18001a518  mov     r9d, [rsp+1D8h+DescriptorLength]; DescriptorLength
0x18001a51d  mov     r8, r14; ResultantDescriptor
0x18001a520  mov     edx, esi; SecurityInformation
0x18001a522  mov     rcx, rdi; ObjectDescriptor
0x18001a525  call    cs:__imp_RtlQuerySecurityObject
0x18001a52c  nop     dword ptr [rax+rax+00h]
0x18001a531  test    eax, eax
0x18001a533  jns     loc_18001A5C9
0x18001a539  mov     rcx, [rsp+1D8h]; this
0x18001a541  mov     r9d, eax; char *
0x18001a544  lea     r8, aOnecoreBaseGen_71; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001a54b  mov     edx, 368h; void *
0x18001a550  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a555  mov     edi, eax
0x18001a557  mov     rcx, r14; hMem
0x18001a55a  call    cs:__imp_LocalFree
0x18001a561  nop     dword ptr [rax+rax+00h]
0x18001a566  test    edi, edi
0x18001a568  jns     short loc_18001A5CC
0x18001a56a  mov     rcx, [rsp+1D8h]; this
0x18001a572  mov     r9d, edi; char *
0x18001a575  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001a57c  mov     edx, 1CDFh; void *
0x18001a581  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a586  mov     rcx, [rsp+1D8h]; this
0x18001a58e  mov     r9d, edi; char *
0x18001a591  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001a598  mov     edx, 3F6h; void *
0x18001a59d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a5a2  lea     rax, ??_7GetContainerSecurityInformation@CmTraceProvider@@6B@; const CmTraceProvider::GetContainerSecurityInformation::`vftable'
0x18001a5a9  mov     [rsp+1D8h+var_198], rax
0x18001a5ae  lea     rcx, [rsp+1D8h+var_198]
0x18001a5b3  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a5b8  lea     rcx, [rsp+1D8h+var_198]
0x18001a5bd  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a5c2  mov     eax, edi
0x18001a5c4  jmp     loc_18001A69D
0x18001a5c9  mov     rbx, r14
0x18001a5cc  mov     rcx, rbx; SecurityDescriptor
0x18001a5cf  call    cs:__imp_RtlLengthSecurityDescriptor
0x18001a5d6  nop     dword ptr [rax+rax+00h]
0x18001a5db  mov     esi, eax
0x18001a5dd  mov     ecx, eax; size
0x18001a5df  call    MIDL_user_allocate
0x18001a5e4  mov     rdi, rax
0x18001a5e7  test    rax, rax
0x18001a5ea  jnz     short loc_18001A645
0x18001a5ec  mov     rcx, [rsp+1D8h]; this
0x18001a5f4  mov     edi, 8007000Eh
0x18001a5f9  mov     r9d, edi; char *
0x18001a5fc  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001a603  mov     edx, 3FEh; void *
0x18001a608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a60d  test    rbx, rbx
0x18001a610  jz      short loc_18001A621
0x18001a612  mov     rcx, rbx; hMem
0x18001a615  call    cs:__imp_LocalFree
0x18001a61c  nop     dword ptr [rax+rax+00h]
0x18001a621  lea     rax, ??_7GetContainerSecurityInformation@CmTraceProvider@@6B@; const CmTraceProvider::GetContainerSecurityInformation::`vftable'
0x18001a628  mov     [rsp+1D8h+var_198], rax
0x18001a62d  lea     rcx, [rsp+1D8h+var_198]
0x18001a632  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a637  lea     rcx, [rsp+1D8h+var_198]
0x18001a63c  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a641  mov     eax, edi
0x18001a643  jmp     short loc_18001A69D
0x18001a645  mov     r8, rsi; Size
0x18001a648  mov     rdx, rbx; Src
0x18001a64b  mov     rcx, rdi; void *
0x18001a64e  call    memcpy_0
0x18001a653  mov     [r15], rdi
0x18001a656  mov     [r12], esi
0x18001a65a  xor     edx, edx
0x18001a65c  lea     rcx, [rsp+1D8h+var_198]
0x18001a661  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001a666  test    rbx, rbx
0x18001a669  jz      short loc_18001A67A
0x18001a66b  mov     rcx, rbx; hMem
0x18001a66e  call    cs:__imp_LocalFree
0x18001a675  nop     dword ptr [rax+rax+00h]
0x18001a67a  lea     rax, ??_7GetContainerSecurityInformation@CmTraceProvider@@6B@; const CmTraceProvider::GetContainerSecurityInformation::`vftable'
0x18001a681  mov     [rsp+1D8h+var_198], rax
0x18001a686  lea     rcx, [rsp+1D8h+var_198]
0x18001a68b  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a690  lea     rcx, [rsp+1D8h+var_198]
0x18001a695  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a69a  nop
0x18001a69b  xor     eax, eax
0x18001a69d  mov     rcx, [rsp+1D8h+var_48]
0x18001a6a5  xor     rcx, rsp; StackCookie
0x18001a6a8  call    __security_check_cookie
0x18001a6ad  add     rsp, 1A8h
0x18001a6b4  pop     r15
0x18001a6b6  pop     r14
0x18001a6b8  pop     r12
0x18001a6ba  pop     rdi
0x18001a6bb  pop     rsi
0x18001a6bc  pop     rbx
0x18001a6bd  retn
0x18001a6bf  mov     rcx, [rsp+1D8h]; this
0x18001a6c7  mov     ebx, 80070057h
0x18001a6cc  mov     r9d, ebx; char *
0x18001a6cf  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001a6d6  mov     edx, 3D9h; void *
0x18001a6db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a6e0  lea     rax, ??_7GetContainerSecurityInformation@CmTraceProvider@@6B@; const CmTraceProvider::GetContainerSecurityInformation::`vftable'
0x18001a6e7  mov     [rsp+1D8h+var_198], rax
0x18001a6ec  lea     rcx, [rsp+1D8h+var_198]
0x18001a6f1  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001a6f6  lea     rcx, [rsp+1D8h+var_198]
0x18001a6fb  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001a700  mov     eax, ebx
0x18001a702  jmp     short loc_18001A69D
```
