# CmsRpcSrv_CreateActivity

- ea: `0x180017b70`
- end: `0x1800180ee`
- name: `CmsRpcSrv_CreateActivity`
- size: `1406`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x180007b48`
- `0x180007dd4`
- `0x180007fec`
- `0x180009ba0`
- `0x18000b134`
- `0x18000da88`
- `0x18000dad8`
- `0x18000ea3c`
- `0x18001076c`
- `0x180017b70`
- `0x18002c110`
- `0x18004b55c`
- `0x180066b84`
- `0x180190a40`
- `0x180190f8c`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x180017bed`
- `ntdll!RtlAreAllAccessesGranted` at `0x180017bed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017dad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017eb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001801d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001809a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017dad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017eb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017f8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001801d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001809a`

## string_xrefs

- `0x180017bb4`: `CreateActivity`
- `0x180017c09`: `onecore\base\gendrv\silos\clem\service\RpcContextHandles.h`
- `0x180017c2a`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180017c87`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180017d08`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180017d88`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180017e83`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x180017fef`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001807f`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRpcSrv_CreateActivity(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        Container::Manager::Core::Activity ***a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // eax
  void *v13; // rdx
  unsigned int v14; // edi
  Container::Manager::Core::Activity *v15; // rbx
  int v16; // eax
  unsigned int v17; // ebx
  Container::Manager::Core::Activity *v18; // rdi
  int CurrentThreadUserSid; // eax
  Container::Manager::Core::Activity *v20; // rbx
  _QWORD *v21; // rsi
  HLOCAL v22; // rbx
  int v23; // eax
  Container::Manager::Core::Activity *v24; // rbx
  Container::Manager::Core::Activity **v25; // rax
  Container::Manager::Core::Activity **v26; // rdi
  Container::Manager::Core::Activity *v27; // r14
  unsigned int v28; // edx
  Container::Manager::Core::Activity *v29; // rbx
  Container::Manager::Core::Activity *v30; // rbx
  Container::Manager::Core::Activity *v31; // [rsp+20h] [rbp-1B8h] BYREF
  HLOCAL hMem; // [rsp+28h] [rbp-1B0h] BYREF
  __int64 v33; // [rsp+30h] [rbp-1A8h] BYREF
  char v34; // [rsp+38h] [rbp-1A0h]
  _QWORD v35[42]; // [rsp+40h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  *a3 = 0;
  *a4 = 0;
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v35,
    "CreateActivity");
  v35[0] = &CmTraceProvider::CreateActivity::`vftable';
  try
  {
    CmTraceProvider::CreateActivity::StartActivity();
    if ( !RtlAreAllAccessesGranted(*(_DWORD *)(a1 + 16), 0x20u) )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3B,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\RpcContextHandles.h",
             (const char *)5,
             (unsigned int)v31);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x49C,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v8,
          (int)v31);
        v35[0] = &CmTraceProvider::CreateActivity::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v35);
        return v9;
      }
    }
    v31 = 0;
    v12 = Container::Manager::Core::ContainerHandle::CreateActivity(*(_QWORD *)a1, a2, &v31);
    v14 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A1,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v12,
        (int)v31);
      v15 = v31;
      if ( v31 )
      {
        Container::Manager::Core::Activity::~Activity(v31);
        operator delete(v15, (const struct std::nothrow_t *)0x1C0);
      }
LABEL_25:
      v35[0] = &CmTraceProvider::CreateActivity::`vftable';
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v35);
      return v14;
    }
    hMem = 0;
    v33 = 0;
    v34 = 0;
    v16 = Container::Manager::Rpc::Impersonator::Impersonate((Container::Manager::Rpc::Impersonator *)&v33, v13);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v16,
        (int)v31);
      Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v33);
      v18 = v31;
      if ( v31 )
      {
        Container::Manager::Core::Activity::~Activity(v31);
        operator delete(v18, (const struct std::nothrow_t *)0x1C0);
      }
      v35[0] = &CmTraceProvider::CreateActivity::`vftable';
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v35);
      return v17;
    }
    CurrentThreadUserSid = Csl::GetCurrentThreadUserSid(&hMem);
    v14 = CurrentThreadUserSid;
    if ( CurrentThreadUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4AA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)CurrentThreadUserSid,
        (int)v31);
      Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v33);
      if ( hMem )
        LocalFree(hMem);
      v20 = v31;
      if ( v31 )
      {
        Container::Manager::Core::Activity::~Activity(v31);
        operator delete(v20, (const struct std::nothrow_t *)0x1C0);
      }
      goto LABEL_25;
    }
    Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v33);
    v21 = operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v21 )
    {
      *v21 = 0;
      v21[1] = 0;
      v21[2] = 0;
      v21[5] = 0;
      v21[6] = 0;
      v21[7] = 0;
      v21[8] = 0;
      v21[9] = 0;
      v21[10] = 0;
      v21[12] = 0;
      *((_BYTE *)v21 + 104) = 0;
      v21[11] = 0;
      v22 = hMem;
      v23 = Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize((char *)v21, pSid, hMem);
      v14 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4B5,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v23,
          (int)v31);
        Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>((__int64)v21);
        operator delete(v21, (const struct std::nothrow_t *)0x70);
        if ( v22 )
          LocalFree(v22);
        v24 = v31;
        if ( v31 )
        {
          Container::Manager::Core::Activity::~Activity(v31);
          operator delete(v24, (const struct std::nothrow_t *)0x1C0);
        }
        goto LABEL_25;
      }
      v25 = (Container::Manager::Core::Activity **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v26 = v25;
      if ( v25 )
      {
        v25[1] = 0;
        *((_DWORD *)v25 + 4) = 0;
        *((_BYTE *)v25 + 20) = 0;
        *v25 = v31;
        v27 = v25[1];
        v25[1] = (Container::Manager::Core::Activity *)v21;
        if ( v27 )
        {
          Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>((__int64)v27);
          operator delete(v27, (const struct std::nothrow_t *)0x70);
        }
        *((_DWORD *)v26 + 4) = *(_DWORD *)(a1 + 16);
        *((_BYTE *)v26 + 20) = *(_BYTE *)(a1 + 20);
        v28 = *((_DWORD *)*v26 + 2);
        *a3 = *((_QWORD *)v26[1] + 11);
        *a4 = v26;
        CmTraceProvider::CreateActivity::Stop((CmTraceProvider::CreateActivity *)v35, v28);
        if ( v22 )
          LocalFree(v22);
        v35[0] = &CmTraceProvider::CreateActivity::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v35);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4BB,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)0x8007000ELL,
        (int)v31);
      Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>((__int64)v21);
      operator delete(v21, (const struct std::nothrow_t *)0x70);
      if ( v22 )
        LocalFree(v22);
      v29 = v31;
      if ( v31 )
      {
        Container::Manager::Core::Activity::~Activity(v31);
        operator delete(v29, (const struct std::nothrow_t *)0x1C0);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B2,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)0x8007000ELL,
        (int)v31);
      if ( hMem )
        LocalFree(hMem);
      v30 = v31;
      if ( v31 )
      {
        Container::Manager::Core::Activity::~Activity(v31);
        operator delete(v30, (const struct std::nothrow_t *)0x1C0);
      }
    }
    v35[0] = &CmTraceProvider::CreateActivity::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v35);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v35);
    result = 2147942414LL;
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x4CF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      v10);
  }
  return result;
}

```

## disassembly

```asm
0x180017b70  push    rbx
0x180017b72  push    rsi
0x180017b73  push    rdi
0x180017b74  push    r12
0x180017b76  push    r13
0x180017b78  push    r14
0x180017b7a  push    r15
0x180017b7c  sub     rsp, 1A0h
0x180017b83  mov     rax, cs:__security_cookie
0x180017b8a  xor     rax, rsp
0x180017b8d  mov     [rsp+1D8h+var_48], rax
0x180017b95  mov     r13, r9
0x180017b98  mov     r12, r8
0x180017b9b  mov     esi, edx
0x180017b9d  mov     r15, rcx
0x180017ba0  xor     eax, eax
0x180017ba2  mov     [r8], rax
0x180017ba5  xor     r14d, r14d
0x180017ba8  mov     [r9], r14
0x180017bab  mov     rax, [rcx]
0x180017bae  mov     ebx, [rax]
0x180017bb0  mov     rdi, [rax+8]
0x180017bb4  lea     rdx, aCreateactivity; "CreateActivity"
0x180017bbb  lea     rcx, [rsp+1D8h+var_198]
0x180017bc0  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017bc5  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x180017bcc  mov     [rsp+1D8h+var_198], rax
0x180017bd1  mov     r9d, esi
0x180017bd4  mov     r8d, ebx
0x180017bd7  mov     rdx, rdi
0x180017bda  lea     rcx, [rsp+1D8h+var_198]
0x180017bdf  call    ?StartActivity@CreateActivity@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@@Z; CmTraceProvider::CreateActivity::StartActivity(_GUID const &,_CMS_CLIENT_ID,_CMS_ACTIVITY_ID)
0x180017be4  nop
0x180017be5  lea     edx, [r14+20h]; DesiredAccess
0x180017be9  mov     ecx, [r15+10h]; GrantedAccess
0x180017bed  call    cs:__imp_RtlAreAllAccessesGranted
0x180017bf4  nop     dword ptr [rax+rax+00h]
0x180017bf9  test    al, al
0x180017bfb  jnz     short loc_180017C62
0x180017bfd  mov     rcx, [rsp+1D8h]; this
0x180017c05  lea     r9d, [r14+5]; char *
0x180017c09  lea     r8, aOnecoreBaseGen_15; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180017c10  lea     edx, [r14+3Bh]; void *
0x180017c14  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017c19  mov     ebx, eax
0x180017c1b  test    eax, eax
0x180017c1d  jns     short loc_180017C62
0x180017c1f  mov     rcx, [rsp+1D8h]; this
0x180017c27  mov     r9d, eax; char *
0x180017c2a  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180017c31  mov     edx, 49Ch; void *
0x180017c36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c3b  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x180017c42  mov     [rsp+1D8h+var_198], rax
0x180017c47  lea     rcx, [rsp+1D8h+var_198]
0x180017c4c  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017c51  lea     rcx, [rsp+1D8h+var_198]
0x180017c56  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017c5b  mov     eax, ebx
0x180017c5d  jmp     loc_180017FBB
0x180017c62  mov     [rsp+1D8h+var_1B8], r14; int
0x180017c67  lea     r8, [rsp+1D8h+var_1B8]
0x180017c6c  mov     edx, esi
0x180017c6e  mov     rcx, [r15]
0x180017c71  call    ?CreateActivity@ContainerHandle@Core@Manager@Container@@QEAAJW4_CMS_ACTIVITY_ID@@AEAV?$unique_ptr@VActivity@Core@Manager@Container@@U?$default_delete@VActivity@Core@Manager@Container@@@wistd@@@wistd@@@Z; Container::Manager::Core::ContainerHandle::CreateActivity(_CMS_ACTIVITY_ID,wistd::unique_ptr<Container::Manager::Core::Activity,wistd::default_delete<Container::Manager::Core::Activity>> &)
0x180017c76  mov     edi, eax
0x180017c78  test    eax, eax
0x180017c7a  jns     short loc_180017CDE
0x180017c7c  mov     rcx, [rsp+1D8h]; this
0x180017c84  mov     r9d, eax; char *
0x180017c87  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180017c8e  mov     edx, 4A1h; void *
0x180017c93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c98  mov     rbx, [rsp+1D8h+var_1B8]
0x180017c9d  test    rbx, rbx
0x180017ca0  jz      short loc_180017CB7
0x180017ca2  mov     rcx, rbx; this
0x180017ca5  call    ??1Activity@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Activity::~Activity(void)
0x180017caa  mov     edx, 1C0h; struct std::nothrow_t *
0x180017caf  mov     rcx, rbx; void *
0x180017cb2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017cb7  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x180017cbe  mov     [rsp+1D8h+var_198], rax
0x180017cc3  lea     rcx, [rsp+1D8h+var_198]
0x180017cc8  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017ccd  lea     rcx, [rsp+1D8h+var_198]
0x180017cd2  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017cd7  mov     eax, edi
0x180017cd9  jmp     loc_180017FBB
0x180017cde  mov     [rsp+1D8h+hMem], r14
0x180017ce3  mov     [rsp+1D8h+var_1A8], r14
0x180017ce8  mov     [rsp+1D8h+var_1A0], r14b
0x180017ced  lea     rcx, [rsp+1D8h+var_1A8]; this
0x180017cf2  call    ?Impersonate@Impersonator@Rpc@Manager@Container@@QEAAJPEAX@Z; Container::Manager::Rpc::Impersonator::Impersonate(void *)
0x180017cf7  mov     ebx, eax
0x180017cf9  test    eax, eax
0x180017cfb  jns     short loc_180017D69
0x180017cfd  mov     rcx, [rsp+1D8h]; this
0x180017d05  mov     r9d, eax; char *
0x180017d08  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180017d0f  mov     edx, 4A8h; void *
0x180017d14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d19  lea     rcx, [rsp+1D8h+var_1A8]; this
0x180017d1e  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x180017d23  mov     rdi, [rsp+1D8h+var_1B8]
0x180017d28  test    rdi, rdi
0x180017d2b  jz      short loc_180017D42
0x180017d2d  mov     rcx, rdi; this
0x180017d30  call    ??1Activity@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Activity::~Activity(void)
0x180017d35  mov     edx, 1C0h; struct std::nothrow_t *
0x180017d3a  mov     rcx, rdi; void *
0x180017d3d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017d42  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x180017d49  mov     [rsp+1D8h+var_198], rax
0x180017d4e  lea     rcx, [rsp+1D8h+var_198]
0x180017d53  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017d58  lea     rcx, [rsp+1D8h+var_198]
0x180017d5d  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017d62  mov     eax, ebx
0x180017d64  jmp     loc_180017FBB
0x180017d69  lea     rcx, [rsp+1D8h+hMem]
0x180017d6e  call    ?GetCurrentThreadUserSid@Csl@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Csl::GetCurrentThreadUserSid(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180017d73  mov     edi, eax
0x180017d75  test    eax, eax
0x180017d77  jns     loc_180017DFF
0x180017d7d  mov     rcx, [rsp+1D8h]; this
0x180017d85  mov     r9d, eax; char *
0x180017d88  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180017d8f  mov     edx, 4AAh; void *
0x180017d94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d99  lea     rcx, [rsp+1D8h+var_1A8]; this
0x180017d9e  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x180017da3  mov     rcx, [rsp+1D8h+hMem]; hMem
0x180017da8  test    rcx, rcx
0x180017dab  jz      short loc_180017DB9
0x180017dad  call    cs:__imp_LocalFree
0x180017db4  nop     dword ptr [rax+rax+00h]
0x180017db9  mov     rbx, [rsp+1D8h+var_1B8]
0x180017dbe  test    rbx, rbx
0x180017dc1  jz      short loc_180017DD8
0x180017dc3  mov     rcx, rbx; this
0x180017dc6  call    ??1Activity@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Activity::~Activity(void)
0x180017dcb  mov     edx, 1C0h; struct std::nothrow_t *
0x180017dd0  mov     rcx, rbx; void *
0x180017dd3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017dd8  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x180017ddf  mov     [rsp+1D8h+var_198], rax
0x180017de4  lea     rcx, [rsp+1D8h+var_198]
0x180017de9  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017dee  lea     rcx, [rsp+1D8h+var_198]
0x180017df3  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017df8  mov     eax, edi
0x180017dfa  jmp     loc_180017FBB
0x180017dff  lea     rcx, [rsp+1D8h+var_1A8]; this
0x180017e04  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x180017e09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017e10  mov     ecx, 70h ; 'p'; unsigned __int64
0x180017e15  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017e1a  mov     rsi, rax
0x180017e1d  test    rax, rax
0x180017e20  jz      loc_18001806F
0x180017e26  xor     eax, eax
0x180017e28  mov     [rsi], rax
0x180017e2b  mov     [rsi+8], rax
0x180017e2f  mov     [rsi+10h], rax
0x180017e33  mov     [rsi+28h], r14
0x180017e37  mov     [rsi+30h], r14
0x180017e3b  mov     [rsi+38h], r14
0x180017e3f  mov     [rsi+40h], r14
0x180017e43  mov     [rsi+48h], r14
0x180017e47  mov     [rsi+50h], rax
0x180017e4b  mov     [rsi+60h], r14
0x180017e4f  mov     [rsi+68h], r14b
0x180017e53  mov     [rsi+58h], rax
0x180017e57  mov     rbx, [rsp+1D8h+hMem]
0x180017e5c  mov     r8, rbx; PSID
0x180017e5f  mov     rdx, cs:pSid; pSid
0x180017e66  mov     rcx, rsi; pv
0x180017e69  call    ?Initialize@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAAJPEAX0@Z; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::Initialize(void *,void *)
0x180017e6e  mov     edi, eax
0x180017e70  test    eax, eax
0x180017e72  jns     loc_180017F03
0x180017e78  mov     rcx, [rsp+1D8h]; this
0x180017e80  mov     r9d, eax; char *
0x180017e83  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180017e8a  mov     edx, 4B5h; void *
0x180017e8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e94  mov     rcx, rsi
0x180017e97  call    ??1?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180017e9c  mov     edx, 70h ; 'p'; struct std::nothrow_t *
0x180017ea1  mov     rcx, rsi; void *
0x180017ea4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017ea9  test    rbx, rbx
0x180017eac  jz      short loc_180017EBD
0x180017eae  mov     rcx, rbx; hMem
0x180017eb1  call    cs:__imp_LocalFree
0x180017eb8  nop     dword ptr [rax+rax+00h]
0x180017ebd  mov     rbx, [rsp+1D8h+var_1B8]
0x180017ec2  test    rbx, rbx
0x180017ec5  jz      short loc_180017EDC
0x180017ec7  mov     rcx, rbx; this
0x180017eca  call    ??1Activity@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Activity::~Activity(void)
0x180017ecf  mov     edx, 1C0h; struct std::nothrow_t *
0x180017ed4  mov     rcx, rbx; void *
0x180017ed7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017edc  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x180017ee3  mov     [rsp+1D8h+var_198], rax
0x180017ee8  lea     rcx, [rsp+1D8h+var_198]
0x180017eed  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017ef2  lea     rcx, [rsp+1D8h+var_198]
0x180017ef7  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017efc  mov     eax, edi
0x180017efe  jmp     loc_180017FBB
0x180017f03  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017f0a  mov     ecx, 18h; unsigned __int64
0x180017f0f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017f14  mov     rdi, rax
0x180017f17  test    rax, rax
0x180017f1a  jz      loc_180017FDF
0x180017f20  mov     [rax+8], r14
0x180017f24  mov     [rax+10h], r14d
0x180017f28  mov     [rax+14h], r14b
0x180017f2c  mov     rdx, [rsp+1D8h+var_1B8]
0x180017f31  mov     [rax], rdx
0x180017f34  mov     r14, [rax+8]
0x180017f38  mov     [rax+8], rsi
0x180017f3c  test    r14, r14
0x180017f3f  jz      short loc_180017F56
0x180017f41  mov     rcx, r14
0x180017f44  call    ??1?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180017f49  mov     edx, 70h ; 'p'; struct std::nothrow_t *
0x180017f4e  mov     rcx, r14; void *
0x180017f51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017f56  mov     eax, [r15+10h]
0x180017f5a  mov     [rdi+10h], eax
0x180017f5d  mov     al, [r15+14h]
0x180017f61  mov     [rdi+14h], al
0x180017f64  mov     rax, [rdi]
0x180017f67  mov     edx, [rax+8]; unsigned int
0x180017f6a  mov     rax, [rdi+8]
0x180017f6e  mov     rcx, [rax+58h]
0x180017f72  mov     [r12], rcx
0x180017f76  mov     [r13+0], rdi
0x180017f7a  lea     rcx, [rsp+1D8h+var_198]; this
0x180017f7f  call    ?Stop@CreateActivity@CmTraceProvider@@QEAAXK@Z; CmTraceProvider::CreateActivity::Stop(ulong)
0x180017f84  test    rbx, rbx
0x180017f87  jz      short loc_180017F98
0x180017f89  mov     rcx, rbx; hMem
0x180017f8c  call    cs:__imp_LocalFree
0x180017f93  nop     dword ptr [rax+rax+00h]
0x180017f98  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x180017f9f  mov     [rsp+1D8h+var_198], rax
0x180017fa4  lea     rcx, [rsp+1D8h+var_198]
0x180017fa9  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017fae  lea     rcx, [rsp+1D8h+var_198]
0x180017fb3  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017fb8  nop
0x180017fb9  xor     eax, eax
0x180017fbb  mov     rcx, [rsp+1D8h+var_48]
0x180017fc3  xor     rcx, rsp; StackCookie
0x180017fc6  call    __security_check_cookie
0x180017fcb  add     rsp, 1A0h
0x180017fd2  pop     r15
0x180017fd4  pop     r14
0x180017fd6  pop     r13
0x180017fd8  pop     r12
0x180017fda  pop     rdi
0x180017fdb  pop     rsi
0x180017fdc  pop     rbx
0x180017fdd  retn
0x180017fdf  mov     rcx, [rsp+1D8h]; this
0x180017fe7  mov     edi, 8007000Eh
0x180017fec  mov     r9d, edi; char *
0x180017fef  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180017ff6  mov     edx, 4BBh; void *
0x180017ffb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018000  mov     rcx, rsi
0x180018003  call    ??1?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180018008  mov     edx, 70h ; 'p'; struct std::nothrow_t *
0x18001800d  mov     rcx, rsi; void *
0x180018010  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018015  test    rbx, rbx
0x180018018  jz      short loc_180018029
0x18001801a  mov     rcx, rbx; hMem
0x18001801d  call    cs:__imp_LocalFree
0x180018024  nop     dword ptr [rax+rax+00h]
0x180018029  mov     rbx, [rsp+1D8h+var_1B8]
0x18001802e  test    rbx, rbx
0x180018031  jz      short loc_180018048
0x180018033  mov     rcx, rbx; this
0x180018036  call    ??1Activity@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Activity::~Activity(void)
0x18001803b  mov     edx, 1C0h; struct std::nothrow_t *
0x180018040  mov     rcx, rbx; void *
0x180018043  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018048  lea     rax, ??_7CreateActivity@CmTraceProvider@@6B@; const CmTraceProvider::CreateActivity::`vftable'
0x18001804f  mov     [rsp+1D8h+var_198], rax
0x180018054  lea     rcx, [rsp+1D8h+var_198]
0x180018059  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001805e  lea     rcx, [rsp+1D8h+var_198]
0x180018063  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
  ... truncated ...
```
