# CmsRpcSrv_UnmapFolderFromContainer

- ea: `0x18001e850`
- end: `0x18001ec48`
- name: `CmsRpcSrv_UnmapFolderFromContainer`
- size: `1016`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x180007c0c`
- `0x180007e54`
- `0x180009cc0`
- `0x18000da88`
- `0x18000dad8`
- `0x18000fe40`
- `0x18001063c`
- `0x18001e850`
- `0x18002fc34`
- `0x1800982a8`
- `0x18009b018`
- `0x1800ac950`
- `0x1800b8d48`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x18001e8d5`
- `ntdll!RtlAreAllAccessesGranted` at `0x18001e8d5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ea6f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ea6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ead0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001eb41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ebcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ead0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001eb41`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ebcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ea34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ea55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ea34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ea55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e9f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e9f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ea7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ea7b`

## string_xrefs

- `0x18001e8f4`: `onecore\base\gendrv\silos\clem\service\RpcContextHandles.h`
- `0x18001e915`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001e99b`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001eb74`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRpcSrv_UnmapFolderFromContainer(ACCESS_MASK *a1, RTL_SRWLOCK *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  RTL_SRWLOCK *v11; // rdi
  int v12; // ebx
  __int64 v13; // rdi
  RTL_SRWLOCK *v14; // rcx
  RTL_SRWLOCK *v15; // rcx
  unsigned int v16; // [rsp+20h] [rbp-1C8h]
  unsigned int v17; // [rsp+20h] [rbp-1C8h]
  unsigned int v18; // [rsp+20h] [rbp-1C8h]
  PSRWLOCK SRWLock[2]; // [rsp+30h] [rbp-1B8h] BYREF
  void *v20[2]; // [rsp+40h] [rbp-1A8h] BYREF
  _WORD v21[8]; // [rsp+50h] [rbp-198h] BYREF
  _QWORD v22[42]; // [rsp+60h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v4 = *(_DWORD *)(*(_QWORD *)a1 + 8LL);
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v22,
    "UnmapFolderFromContainer");
  v22[0] = &CmTraceProvider::UnmapFolderFromContainer::`vftable';
  v16 = v4;
  try
  {
    CmTraceProvider::UnmapFolderFromContainer::StartActivity();
    if ( !RtlAreAllAccessesGranted(a1[4], 0x40u) )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\RpcContextHandles.h",
             (const char *)5,
             v4);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x749,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v5,
          v16);
        v22[0] = &CmTraceProvider::UnmapFolderFromContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v22);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v22);
        return v6;
      }
    }
    v20[0] = v21;
    v20[1] = v21;
    v21[0] = 0;
    SRWLock[0] = a2;
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)&a2->Ptr + v9) );
    SRWLock[1] = (PSRWLOCK)v9;
    if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v20) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)0x8007000ELL,
        v16);
      if ( v20[0] != v21 )
        operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
      v22[0] = &CmTraceProvider::UnmapFolderFromContainer::`vftable';
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v22);
      wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v22);
      return 2147942414LL;
    }
    v10 = *(_QWORD *)a1;
    v11 = (RTL_SRWLOCK *)(*(_QWORD *)(*(_QWORD *)a1 + 40LL) + 456LL);
    AcquireSRWLockShared(v11);
    if ( *(_DWORD *)(v10 + 56) != 4 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x21E,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
              (const char *)0x139F,
              v16);
      if ( v11 )
        ReleaseSRWLockShared(v11);
      if ( v12 < 0 )
        goto LABEL_25;
      goto LABEL_30;
    }
    if ( v11 )
      ReleaseSRWLockShared(v11);
    v13 = *(_QWORD *)(v10 + 40);
    AcquireSRWLockExclusive((PSRWLOCK)(v13 + 456));
    *(_DWORD *)(v13 + 464) = GetCurrentThreadId();
    SRWLock[0] = (PSRWLOCK)(v13 + 456);
    if ( utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(
           v13 + 736,
           v20) == v13 + 736 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x15CD,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
              (const char *)0x490,
              v16);
      *(_DWORD *)(v13 + 464) = 0;
      ReleaseSRWLockExclusive((PSRWLOCK)(v13 + 456));
      if ( v12 < 0 )
      {
LABEL_24:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x223,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
          (const char *)(unsigned int)v12,
          v18);
LABEL_25:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74F,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v12,
          v17);
        if ( v20[0] != v21 )
          operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
        v22[0] = &CmTraceProvider::UnmapFolderFromContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v22);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v22);
        return (unsigned int)v12;
      }
    }
    else
    {
      Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
        v13,
        SRWLock);
      v12 = Container::Manager::Core::Details::ContainerObject::UnmapSharedFolderInternal(v13, (__int64)v20, SRWLock);
      Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference((Container::Manager::Core::Details::ContainerObject *)v13);
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15DB,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v12,
          v16);
        v14 = SRWLock[0];
        if ( SRWLock[0] )
        {
          LODWORD(SRWLock[0][1].Ptr) = 0;
          ReleaseSRWLockExclusive(v14);
        }
        goto LABEL_24;
      }
      v15 = SRWLock[0];
      if ( SRWLock[0] )
      {
        LODWORD(SRWLock[0][1].Ptr) = 0;
        ReleaseSRWLockExclusive(v15);
      }
    }
LABEL_30:
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v22, 0);
    if ( v20[0] != v21 )
      operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
    v22[0] = &CmTraceProvider::UnmapFolderFromContainer::`vftable';
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v22);
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v22);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x756,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      v7);
  }
  return result;
}

```

## disassembly

```asm
0x18001e850  mov     [rsp+arg_10], rbx
0x18001e855  mov     [rsp+arg_18], rsi
0x18001e85a  push    rdi
0x18001e85b  push    r12
0x18001e85d  push    r13
0x18001e85f  push    r14
0x18001e861  push    r15
0x18001e863  sub     rsp, 1C0h
0x18001e86a  mov     rax, cs:__security_cookie
0x18001e871  xor     rax, rsp
0x18001e874  mov     [rsp+1E8h+var_38], rax
0x18001e87c  mov     r15, rdx
0x18001e87f  mov     r12, rcx
0x18001e882  mov     rax, [rcx]
0x18001e885  mov     ebx, [rax+8]
0x18001e888  mov     edi, [rax+4]
0x18001e88b  mov     esi, [rax]
0x18001e88d  mov     r14, [rax+28h]
0x18001e891  lea     rdx, aUnmapfolderfro; "UnmapFolderFromContainer"
0x18001e898  lea     rcx, [rsp+1E8h+var_188]
0x18001e89d  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001e8a2  lea     r13, ??_7UnmapFolderFromContainer@CmTraceProvider@@6B@; const CmTraceProvider::UnmapFolderFromContainer::`vftable'
0x18001e8a9  mov     [rsp+1E8h+var_188], r13
0x18001e8ae  mov     [rsp+1E8h+var_1C0], r15
0x18001e8b3  mov     [rsp+1E8h+var_1C8], ebx; int
0x18001e8b7  mov     r9d, edi
0x18001e8ba  mov     r8d, esi
0x18001e8bd  mov     rdx, r14
0x18001e8c0  lea     rcx, [rsp+1E8h+var_188]
0x18001e8c5  call    ?StartActivity@UnmapFolderFromContainer@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@KPEBG@Z; CmTraceProvider::UnmapFolderFromContainer::StartActivity(_GUID const &,_CMS_CLIENT_ID,_CMS_ACTIVITY_ID,ulong,ushort const *)
0x18001e8ca  nop
0x18001e8cb  mov     edx, 40h ; '@'; DesiredAccess
0x18001e8d0  mov     ecx, [r12+10h]; GrantedAccess
0x18001e8d5  call    cs:__imp_RtlAreAllAccessesGranted
0x18001e8dc  nop     dword ptr [rax+rax+00h]
0x18001e8e1  xor     r14d, r14d
0x18001e8e4  test    al, al
0x18001e8e6  jnz     short loc_18001E946
0x18001e8e8  mov     rcx, [rsp+1E8h]; this
0x18001e8f0  lea     r9d, [r14+5]; char *
0x18001e8f4  lea     r8, aOnecoreBaseGen_15; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001e8fb  lea     edx, [r14+7Ah]; void *
0x18001e8ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001e904  mov     ebx, eax
0x18001e906  test    eax, eax
0x18001e908  jns     short loc_18001E946
0x18001e90a  mov     rcx, [rsp+1E8h]; this
0x18001e912  mov     r9d, eax; char *
0x18001e915  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001e91c  mov     edx, 749h; void *
0x18001e921  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e926  mov     [rsp+1E8h+var_188], r13
0x18001e92b  lea     rcx, [rsp+1E8h+var_188]
0x18001e930  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001e935  lea     rcx, [rsp+1E8h+var_188]
0x18001e93a  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001e93f  mov     eax, ebx
0x18001e941  jmp     loc_18001EC1A
0x18001e946  lea     rax, [rsp+1E8h+var_198]
0x18001e94b  mov     [rsp+1E8h+var_1A8], rax
0x18001e950  lea     rax, [rsp+1E8h+var_198]
0x18001e955  mov     [rsp+1E8h+var_1A0], rax
0x18001e95a  mov     [rsp+1E8h+var_198], r14w
0x18001e960  mov     [rsp+1E8h+SRWLock], r15
0x18001e965  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e969  inc     rax
0x18001e96c  cmp     [r15+rax*2], r14w
0x18001e971  jnz     short loc_18001E969
0x18001e973  mov     [rsp+1E8h+var_1B0], rax
0x18001e978  lea     rdx, [rsp+1E8h+SRWLock]
0x18001e97d  lea     rcx, [rsp+1E8h+var_1A8]; this
0x18001e982  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18001e987  test    al, al
0x18001e989  jnz     short loc_18001E9E7
0x18001e98b  mov     rcx, [rsp+1E8h]; this
0x18001e993  mov     ebx, 8007000Eh
0x18001e998  mov     r9d, ebx; char *
0x18001e99b  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001e9a2  mov     edx, 74Ch; void *
0x18001e9a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9ac  mov     rcx, [rsp+1E8h+var_1A8]; void *
0x18001e9b1  lea     rdx, [rsp+1E8h+var_198]
0x18001e9b6  cmp     rcx, rdx
0x18001e9b9  jz      short loc_18001E9C7
0x18001e9bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e9c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e9c7  mov     [rsp+1E8h+var_188], r13
0x18001e9cc  lea     rcx, [rsp+1E8h+var_188]
0x18001e9d1  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001e9d6  lea     rcx, [rsp+1E8h+var_188]
0x18001e9db  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001e9e0  mov     eax, ebx
0x18001e9e2  jmp     loc_18001EC1A
0x18001e9e7  mov     rbx, [r12]
0x18001e9eb  mov     rdi, [rbx+28h]
0x18001e9ef  add     rdi, 1C8h
0x18001e9f6  mov     rcx, rdi; SRWLock
0x18001e9f9  call    cs:__imp_AcquireSRWLockShared
0x18001ea00  nop     dword ptr [rax+rax+00h]
0x18001ea05  cmp     dword ptr [rbx+38h], 4
0x18001ea09  jz      short loc_18001EA4D
0x18001ea0b  mov     rcx, [rsp+1E8h]; this
0x18001ea13  mov     r9d, 139Fh; char *
0x18001ea19  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001ea20  mov     edx, 21Eh; void *
0x18001ea25  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ea2a  mov     ebx, eax
0x18001ea2c  test    rdi, rdi
0x18001ea2f  jz      short loc_18001EA40
0x18001ea31  mov     rcx, rdi; SRWLock
0x18001ea34  call    cs:__imp_ReleaseSRWLockShared
0x18001ea3b  nop     dword ptr [rax+rax+00h]
0x18001ea40  test    ebx, ebx
0x18001ea42  jns     loc_18001EBD7
0x18001ea48  jmp     loc_18001EB69
0x18001ea4d  test    rdi, rdi
0x18001ea50  jz      short loc_18001EA61
0x18001ea52  mov     rcx, rdi; SRWLock
0x18001ea55  call    cs:__imp_ReleaseSRWLockShared
0x18001ea5c  nop     dword ptr [rax+rax+00h]
0x18001ea61  mov     rdi, [rbx+28h]
0x18001ea65  lea     rsi, [rdi+1C8h]
0x18001ea6c  mov     rcx, rsi; SRWLock
0x18001ea6f  call    cs:__imp_AcquireSRWLockExclusive
0x18001ea76  nop     dword ptr [rax+rax+00h]
0x18001ea7b  call    cs:__imp_GetCurrentThreadId
0x18001ea82  nop     dword ptr [rax+rax+00h]
0x18001ea87  mov     [rsi+8], eax
0x18001ea8a  mov     [rsp+1E8h+SRWLock], rsi
0x18001ea8f  lea     rbx, [rdi+2E0h]
0x18001ea96  lea     rdx, [rsp+1E8h+var_1A8]
0x18001ea9b  mov     rcx, rbx
0x18001ea9e  call    ??$_FindImpl@VPath@Csl@@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@4@$0A@@utl@@AEBAPEAU?$_TreeNode@U?$pair@$$CBVPath@Csl@@V?$unique_ptr@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@U?$default_delete@UMappedFolderConfigurationEntry@ContainerObject@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@1@AEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,wistd::unique_ptr<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry,wistd::default_delete<Container::Manager::Core::Details::ContainerObject::MappedFolderConfigurationEntry>>>>,0>::_FindImpl<Csl::Path>(Csl::Path const &)
0x18001eaa3  cmp     rax, rbx
0x18001eaa6  jnz     short loc_18001EAE6
0x18001eaa8  mov     rcx, [rsp+1E8h]; this
0x18001eab0  mov     r9d, 490h; char *
0x18001eab6  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001eabd  mov     edx, 15CDh; void *
0x18001eac2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001eac7  mov     ebx, eax
0x18001eac9  mov     [rsi+8], r14d
0x18001eacd  mov     rcx, rsi; SRWLock
0x18001ead0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ead7  nop     dword ptr [rax+rax+00h]
0x18001eadc  test    ebx, ebx
0x18001eade  jns     loc_18001EBD7
0x18001eae4  jmp     short loc_18001EB4D
0x18001eae6  lea     rdx, [rsp+1E8h+SRWLock]
0x18001eaeb  mov     rcx, rdi
0x18001eaee  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18001eaf3  lea     r8, [rsp+1E8h+SRWLock]
0x18001eaf8  lea     rdx, [rsp+1E8h+var_1A8]
0x18001eafd  mov     rcx, rdi
0x18001eb00  call    ?UnmapSharedFolderInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@7@@Z; Container::Manager::Core::Details::ContainerObject::UnmapSharedFolderInternal(Csl::Path const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18001eb05  mov     ebx, eax
0x18001eb07  mov     rcx, rdi; this
0x18001eb0a  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x18001eb0f  test    ebx, ebx
0x18001eb11  jns     loc_18001EBBD
0x18001eb17  mov     rcx, [rsp+1E8h]; this
0x18001eb1f  mov     r9d, ebx; char *
0x18001eb22  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001eb29  mov     edx, 15DBh; void *
0x18001eb2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb33  mov     rcx, [rsp+1E8h+SRWLock]; SRWLock
0x18001eb38  test    rcx, rcx
0x18001eb3b  jz      short loc_18001EB4D
0x18001eb3d  mov     [rcx+8], r14d
0x18001eb41  call    cs:__imp_ReleaseSRWLockExclusive
0x18001eb48  nop     dword ptr [rax+rax+00h]
0x18001eb4d  mov     rcx, [rsp+1E8h]; this
0x18001eb55  mov     r9d, ebx; char *
0x18001eb58  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001eb5f  mov     edx, 223h; void *
0x18001eb64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb69  mov     rcx, [rsp+1E8h]; this
0x18001eb71  mov     r9d, ebx; char *
0x18001eb74  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001eb7b  mov     edx, 74Fh; void *
0x18001eb80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb85  mov     rcx, [rsp+1E8h+var_1A8]; void *
0x18001eb8a  lea     rax, [rsp+1E8h+var_198]
0x18001eb8f  cmp     rcx, rax
0x18001eb92  jz      short loc_18001EBA0
0x18001eb94  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001eb9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001eba0  mov     [rsp+1E8h+var_188], r13
0x18001eba5  lea     rcx, [rsp+1E8h+var_188]
0x18001ebaa  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ebaf  lea     rcx, [rsp+1E8h+var_188]
0x18001ebb4  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001ebb9  mov     eax, ebx
0x18001ebbb  jmp     short loc_18001EC1A
0x18001ebbd  mov     rcx, [rsp+1E8h+SRWLock]; SRWLock
0x18001ebc2  test    rcx, rcx
0x18001ebc5  jz      short loc_18001EBD7
0x18001ebc7  mov     [rcx+8], r14d
0x18001ebcb  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ebd2  nop     dword ptr [rax+rax+00h]
0x18001ebd7  xor     edx, edx
0x18001ebd9  lea     rcx, [rsp+1E8h+var_188]
0x18001ebde  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001ebe3  mov     rcx, [rsp+1E8h+var_1A8]; void *
0x18001ebe8  lea     rax, [rsp+1E8h+var_198]
0x18001ebed  cmp     rcx, rax
0x18001ebf0  jz      short loc_18001EBFE
0x18001ebf2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ebf9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ebfe  mov     [rsp+1E8h+var_188], r13
0x18001ec03  lea     rcx, [rsp+1E8h+var_188]
0x18001ec08  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001ec0d  lea     rcx, [rsp+1E8h+var_188]
0x18001ec12  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001ec17  nop
0x18001ec18  xor     eax, eax
0x18001ec1a  mov     rcx, [rsp+1E8h+var_38]
0x18001ec22  xor     rcx, rsp; StackCookie
0x18001ec25  call    __security_check_cookie
0x18001ec2a  lea     r11, [rsp+1E8h+var_28]
0x18001ec32  mov     rbx, [r11+40h]
0x18001ec36  mov     rsi, [r11+48h]
0x18001ec3a  mov     rsp, r11
0x18001ec3d  pop     r15
0x18001ec3f  pop     r14
0x18001ec41  pop     r13
0x18001ec43  pop     r12
0x18001ec45  pop     rdi
0x18001ec46  retn
```
