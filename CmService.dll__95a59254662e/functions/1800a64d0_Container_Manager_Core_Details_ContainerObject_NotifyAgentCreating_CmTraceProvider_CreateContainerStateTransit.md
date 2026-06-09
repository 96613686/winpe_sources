# Container::Manager::Core::Details::ContainerObject::NotifyAgentCreating(CmTraceProvider::CreateContainerStateTransition const &,utl::optional<_GUID>,bool,bool,utl::optional<unsigned __int64> &,utl::optional<ulong> &)

- ea: `0x1800a64d0`
- end: `0x1800a6bd8`
- name: `?NotifyAgentCreating@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVCreateContainerStateTransition@CmTraceProvider@@V?$optional@U_GUID@@@utl@@_N2AEAV?$optional@_K@9@AEAV?$optional@K@9@@Z`
- size: `1800`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a71b4`

## callees

- `0x180004bd0`
- `0x180007b48`
- `0x180007dd4`
- `0x180008d04`
- `0x180009ba0`
- `0x18000b49c`
- `0x18000da88`
- `0x18000dab0`
- `0x1800103a4`
- `0x180016718`
- `0x18002bd50`
- `0x18002e2b4`
- `0x1800471dc`
- `0x18004eff8`
- `0x1800a32d0`
- `0x1800a3388`
- `0x1800a64d0`
- `0x1800aab8c`
- `0x1800af5bc`
- `0x1800fb1dc`
- `0x1800fb3a4`
- `0x180110cc8`
- `0x1801935bc`

## import_xrefs

- `ntdll!NtCreateCrossVmEvent` at `0x1800a659a`
- `ntdll!NtCreateCrossVmEvent` at `0x1800a659a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a67bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a67bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6828`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a68d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6828`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a6870`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a68d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a67cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a67cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a65d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a65d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6629`

## string_xrefs

- `0x1800a687c`: `CreateContainerStateTransition_AgentNotifyCreating`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::NotifyAgentCreating(
        Container::Manager::Core::Details::ContainerObject *this,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        _OWORD *a6,
        _QWORD *a7)
{
  __int128 v10; // xmm7
  __int64 v11; // rdi
  int Guid; // eax
  unsigned int v13; // ebx
  __int64 v14; // rax
  int CrossVmEvent; // eax
  __int128 v17; // xmm6
  int RuntimeFeatureConfigurationsBuffer; // eax
  utl::_RefCountBase *v19; // rcx
  __int64 v20; // rdi
  utl::_RefCountBase *v21; // rbx
  int HotPatches; // eax
  unsigned int v23; // edi
  bool IsManualHotPatchMode; // al
  int v25; // eax
  int v26; // esi
  RTL_SRWLOCK *v27; // rcx
  RTL_SRWLOCK *v28; // rcx
  __int64 v29; // rsi
  int v30; // r9d
  __int64 v31; // rax
  __int64 v32; // r15
  __int64 v33; // r10
  char v34; // dl
  RTL_SRWLOCK *v35; // rbx
  int v36; // eax
  int v37; // [rsp+28h] [rbp-E0h]
  utl::_RefCountBase **v38; // [rsp+28h] [rbp-E0h]
  int v39; // [rsp+28h] [rbp-E0h]
  __int64 v40; // [rsp+48h] [rbp-C0h]
  RTL_SRWLOCK *hObject; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE hObject_8[2]; // [rsp+60h] [rbp-A8h]
  __int64 v43; // [rsp+70h] [rbp-98h]
  int v44[4]; // [rsp+78h] [rbp-90h] BYREF
  int v45; // [rsp+88h] [rbp-80h]
  __int64 v46; // [rsp+98h] [rbp-70h]
  _OWORD v47[3]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-38h]
  _OWORD *v49; // [rsp+D8h] [rbp-30h]
  _QWORD *v50; // [rsp+E0h] [rbp-28h]
  int v51[4]; // [rsp+E8h] [rbp-20h] BYREF
  int v52; // [rsp+F8h] [rbp-10h]
  __int64 v53[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v54; // [rsp+118h] [rbp+10h]
  __int64 v55; // [rsp+128h] [rbp+20h]
  __int128 v56; // [rsp+130h] [rbp+28h] BYREF
  __m256i v57; // [rsp+140h] [rbp+38h]
  char v58; // [rsp+160h] [rbp+58h]
  utl::_RefCountBase *v59[2]; // [rsp+168h] [rbp+60h] BYREF
  char v60; // [rsp+178h] [rbp+70h]
  __int16 v61; // [rsp+179h] [rbp+71h]
  char v62; // [rsp+17Bh] [rbp+73h]
  _QWORD v63[34]; // [rsp+188h] [rbp+80h] BYREF
  __int64 v64; // [rsp+298h] [rbp+190h]
  wil::details::in1diag3 *retaddr; // [rsp+340h] [rbp+238h]

  v46 = a3;
  v49 = a6;
  v50 = a7;
  v10 = 0;
  v11 = *((_QWORD *)this + 69);
  *(_OWORD *)v59 = 0;
  Guid = Csl::CreateGuid((Csl *)v59, (struct _GUID *)a2);
  v13 = Guid;
  if ( Guid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\heartbeatmonitor.cpp",
      (const char *)(unsigned int)Guid,
      v37);
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D59,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)v13,
      (int)v38);
    return v13;
  }
  hObject = 0;
  v14 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&hObject);
  v38 = v59;
  CrossVmEvent = NtCreateCrossVmEvent(v14, 2031619, 0, 0);
  if ( CrossVmEvent >= 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
      v11 + 48,
      &hObject);
    v10 = *(_OWORD *)v59;
    if ( (unsigned __int64)&hObject[-1].Ptr + 7 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
  }
  else
  {
    v13 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0xE9,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\heartbeatmonitor.cpp",
            (const char *)(unsigned int)CrossVmEvent,
            (int)v59);
    if ( (unsigned __int64)&hObject[-1].Ptr + 7 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    if ( (v13 & 0x80000000) != 0 )
      goto LABEL_7;
  }
  v17 = 0;
  *(_OWORD *)hObject_8 = 0;
  v43 = 0;
  if ( a4 )
  {
    *(_QWORD *)v44 = 0;
    *(_OWORD *)v59 = 0;
    RuntimeFeatureConfigurationsBuffer = Container::Manager::Core::Details::SystemConfigurationManager::QueryRuntimeFeatureConfigurationsBuffer(
                                           *((PSRWLOCK *)this + 175),
                                           v44,
                                           v59);
    v13 = RuntimeFeatureConfigurationsBuffer;
    if ( RuntimeFeatureConfigurationsBuffer < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D66,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)RuntimeFeatureConfigurationsBuffer,
        (int)v38);
      if ( v59[1] )
        utl::_RefCountBase::_DecStrong(v59[1]);
      if ( (_BYTE)v43 )
      {
        if ( hObject_8[1] )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hObject_8[1]);
      }
      return v13;
    }
    LOBYTE(v44[2]) = 1;
    v17 = *(_OWORD *)v44;
    hObject_8[0] = v59[0];
    if ( (_BYTE)v43 )
    {
      v19 = (utl::_RefCountBase *)hObject_8[1];
      hObject_8[1] = v59[1];
      if ( v19 )
        utl::_RefCountBase::_DecStrong(v19);
    }
    else
    {
      hObject_8[1] = v59[1];
      LOBYTE(v43) = 1;
    }
  }
  v20 = 0;
  *(_QWORD *)v44 = 0;
  v21 = 0;
  v59[0] = 0;
  memset(v47, 0, sizeof(v47));
  v48 = 0;
  if ( a5 )
  {
    HotPatches = Container::Manager::Core::Details::SystemConfigurationManager::QueryHotPatches(*((PSRWLOCK *)this + 175));
    v23 = HotPatches;
    if ( HotPatches < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D74,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)HotPatches,
        (int)v38);
      utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(v47);
      if ( (_BYTE)v43 && hObject_8[1] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hObject_8[1]);
      return v23;
    }
    IsManualHotPatchMode = Container::Manager::Core::Details::PolicyManager::IsManualHotPatchMode(*((Container::Manager::Core::Details::PolicyManager **)this
                                                                                                  + 163));
    v20 = *(_QWORD *)v44;
    if ( !IsManualHotPatchMode )
      v21 = *(utl::_RefCountBase **)v44;
    v59[0] = v21;
    AcquireSRWLockExclusive((PSRWLOCK)this + 57);
    *((_DWORD *)this + 116) = GetCurrentThreadId();
    hObject = (RTL_SRWLOCK *)((char *)this + 456);
    if ( !(_BYTE)v48 )
      __int2c();
    v25 = Container::Manager::Core::Details::ContainerObject::PrepareForHotPatching(this);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D83,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v25,
        (int)v38);
      v27 = hObject;
      if ( hObject )
      {
        LODWORD(hObject[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v27);
        hObject = 0;
      }
      utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(v47);
      if ( (_BYTE)v43 && hObject_8[1] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hObject_8[1]);
      return (unsigned int)v26;
    }
    v28 = hObject;
    if ( hObject )
    {
      LODWORD(hObject[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v28);
    }
  }
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v63,
    "CreateContainerStateTransition_AgentNotifyCreating");
  v63[0] = &CmTraceProvider::CreateContainerStateTransition_AgentNotifyCreating::`vftable';
  v29 = *(_QWORD *)(a2 + 272);
  wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(v63, &hObject);
  v31 = v64;
  *(_OWORD *)(v64 + 24) = *(_OWORD *)(v29 + 8);
  *(_BYTE *)(v31 + 4) = 1;
  if ( hObject )
    ReleaseSRWLockExclusive(hObject);
  LOBYTE(v30) = a4;
  v32 = v46;
  CmTraceProvider::CreateContainerStateTransition_AgentNotifyCreating::StartActivity(
    (unsigned int)v63,
    v46,
    (_DWORD)this + 16,
    v30,
    a5,
    (__int64)v44,
    (__int64)v59,
    *((_BYTE *)this + 1640));
  v33 = *((_QWORD *)this + 159);
  v34 = *((_BYTE *)this + 1640);
  LOBYTE(v56) = 0;
  v58 = 0;
  if ( (_BYTE)v48 )
  {
    v56 = v47[0];
    v57 = *(__m256i *)&v47[1];
    v47[0] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    *(_QWORD *)&v47[1] = -1;
    *(_OWORD *)((char *)&v47[1] + 8) = v47[0];
    *((_QWORD *)&v47[2] + 1) = -1;
    v58 = 1;
  }
  LOBYTE(v53[0]) = 0;
  LOBYTE(v54) = 0;
  if ( (_BYTE)v43 )
  {
    *(_OWORD *)v53 = *(_OWORD *)hObject_8;
    *(_OWORD *)hObject_8 = 0;
    LOBYTE(v54) = 1;
  }
  LODWORD(hObject) = *(_DWORD *)(*((_QWORD *)this + 169) + 20LL);
  BYTE4(hObject) = 1;
  *(_WORD *)((char *)&hObject + 5) = *(_WORD *)((char *)&v46 + 5);
  HIBYTE(hObject) = HIBYTE(v46);
  *(_OWORD *)v59 = v10;
  v60 = 1;
  v61 = *(_WORD *)((char *)&v52 + 1);
  v62 = HIBYTE(v52);
  *(_OWORD *)v44 = *((_OWORD *)this + 1);
  v45 = *((_DWORD *)this + 8);
  *(_OWORD *)v51 = *(_OWORD *)v32;
  v52 = *(_DWORD *)(v32 + 16);
  LOBYTE(v40) = v34;
  v26 = Container::Manager::Agent::Client::CmAgentConnection::NotifyCreating(
          v33,
          (int)v51,
          (int)v44,
          (int)v59,
          (__int64)hObject,
          v53,
          (__int64)&v56,
          (char)v21,
          v40);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v63,
    (unsigned int)v26);
  if ( v26 < 0 || (*(_DWORD *)(*((_QWORD *)this + 163) + 96LL) & 0x80000) != 0 )
  {
    v35 = (RTL_SRWLOCK *)*((_QWORD *)this + 181);
    *(_OWORD *)v53 = 0;
    v54 = 0;
    v55 = 0;
    Container::Manager::Core::Details::PolicyManager::IsSystemLoggerConfigured(*((Container::Manager::Core::Details::PolicyManager **)this
                                                                               + 163));
    v36 = Container::Manager::Core::Details::LogManager::CopyLogsFromComputeSystem(
            v35,
            *((Container::Manager::Hcs::ComputeSystem **)this + 157),
            (__int64)v53);
    if ( v36 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2DA5,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v36,
        v39);
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DA8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v26,
        v39);
      v63[0] = &CmTraceProvider::CreateContainerStateTransition_AgentNotifyCreating::`vftable';
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v63);
      wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v63);
      utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(v47);
      if ( (_BYTE)v43 && hObject_8[1] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hObject_8[1]);
      return (unsigned int)v26;
    }
  }
  *v49 = v17;
  *v50 = v20;
  v63[0] = &CmTraceProvider::CreateContainerStateTransition_AgentNotifyCreating::`vftable';
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v63);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v63);
  utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(v47);
  if ( (_BYTE)v43 && hObject_8[1] )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)hObject_8[1]);
  return 0;
}

```

## disassembly

```asm
0x1800a64d0  mov     rax, rsp
0x1800a64d3  mov     [rax+10h], rbx
0x1800a64d7  push    rbp
0x1800a64d8  push    rsi
0x1800a64d9  push    rdi
0x1800a64da  push    r12
0x1800a64dc  push    r13
0x1800a64de  push    r14
0x1800a64e0  push    r15
0x1800a64e2  lea     rbp, [rax-238h]
0x1800a64e9  sub     rsp, 300h
0x1800a64f0  movaps  xmmword ptr [rax-48h], xmm6
0x1800a64f4  movaps  xmmword ptr [rax-58h], xmm7
0x1800a64f8  mov     rax, cs:__security_cookie
0x1800a64ff  xor     rax, rsp
0x1800a6502  mov     [rbp+230h+var_60], rax
0x1800a6509  mov     r12b, r9b
0x1800a650c  mov     [rbp+230h+var_2A0], r8
0x1800a6510  mov     r13, rdx
0x1800a6513  mov     r14, rcx
0x1800a6516  mov     rax, [rbp+230h+arg_28]
0x1800a651d  mov     [rbp+230h+var_260], rax
0x1800a6521  mov     rax, [rbp+230h+arg_30]
0x1800a6528  mov     [rbp+230h+var_258], rax
0x1800a652c  xorps   xmm7, xmm7
0x1800a652f  mov     rdi, [rcx+228h]
0x1800a6536  xorps   xmm0, xmm0
0x1800a6539  movups  xmmword ptr [rbp+230h+var_1D0], xmm0
0x1800a653d  lea     rcx, [rbp+230h+var_1D0]; this
0x1800a6541  call    ?CreateGuid@Csl@@YAJAEAU_GUID@@@Z; Csl::CreateGuid(_GUID &)
0x1800a6546  mov     ebx, eax
0x1800a6548  xor     esi, esi
0x1800a654a  test    eax, eax
0x1800a654c  jns     short loc_1800A656B
0x1800a654e  mov     rcx, [rbp+238h]; this
0x1800a6555  mov     r9d, eax; char *
0x1800a6558  lea     r8, aOnecoreBaseGen_30; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a655f  mov     edx, 0E0h; void *
0x1800a6564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6569  jmp     short loc_1800A65E6
0x1800a656b  mov     [rsp+330h+hObject], rsi
0x1800a6570  mov     rbx, [rdi+20h]
0x1800a6574  lea     rcx, [rsp+330h+hObject]
0x1800a6579  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x1800a657e  mov     [rsp+330h+var_308], rbx
0x1800a6583  lea     rcx, [rbp+230h+var_1D0]
0x1800a6587  mov     [rsp+330h+var_310], rcx; int
0x1800a658c  xor     r9d, r9d
0x1800a658f  xor     r8d, r8d
0x1800a6592  mov     edx, 1F0003h
0x1800a6597  mov     rcx, rax
0x1800a659a  call    cs:__imp_NtCreateCrossVmEvent
0x1800a65a1  nop     dword ptr [rax+rax+00h]
0x1800a65a6  test    eax, eax
0x1800a65a8  jns     short loc_1800A6608
0x1800a65aa  mov     rcx, [rbp+238h]; this
0x1800a65b1  mov     r9d, eax; char *
0x1800a65b4  lea     r8, aOnecoreBaseGen_30; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a65bb  mov     edx, 0E9h; void *
0x1800a65c0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a65c5  mov     ebx, eax
0x1800a65c7  mov     rcx, [rsp+330h+hObject]; hObject
0x1800a65cc  lea     rax, [rcx-1]
0x1800a65d0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a65d4  ja      short loc_1800A65E2
0x1800a65d6  call    cs:__imp_CloseHandle
0x1800a65dd  nop     dword ptr [rax+rax+00h]
0x1800a65e2  test    ebx, ebx
0x1800a65e4  jns     short loc_1800A6635
0x1800a65e6  mov     rcx, [rbp+238h]; this
0x1800a65ed  mov     r9d, ebx; char *
0x1800a65f0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a65f7  mov     edx, 2D59h; void *
0x1800a65fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6601  mov     eax, ebx
0x1800a6603  jmp     loc_1800A6BA3
0x1800a6608  lea     rcx, [rdi+30h]
0x1800a660c  lea     rdx, [rsp+330h+hObject]
0x1800a6611  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800a6616  movaps  xmm7, xmmword ptr [rbp+230h+var_1D0]
0x1800a661a  mov     rcx, [rsp+330h+hObject]; hObject
0x1800a661f  lea     rax, [rcx-1]
0x1800a6623  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a6627  ja      short loc_1800A6635
0x1800a6629  call    cs:__imp_CloseHandle
0x1800a6630  nop     dword ptr [rax+rax+00h]
0x1800a6635  xorps   xmm6, xmm6
0x1800a6638  xorps   xmm0, xmm0
0x1800a663b  xor     eax, eax
0x1800a663d  movups  xmmword ptr [rsp+330h+hObject+8], xmm0
0x1800a6642  mov     qword ptr [rsp+330h+var_2C8], rax
0x1800a6647  test    r12b, r12b
0x1800a664a  jz      loc_1800A6709
0x1800a6650  mov     qword ptr [rsp+330h+var_2C8+8], rsi
0x1800a6655  movdqu  xmmword ptr [rbp+230h+var_1D0], xmm0
0x1800a665a  lea     r8, [rbp+230h+var_1D0]
0x1800a665e  lea     rdx, [rsp+330h+var_2C8+8]
0x1800a6663  mov     rcx, [r14+578h]; SRWLock
0x1800a666a  call    ?QueryRuntimeFeatureConfigurationsBuffer@SystemConfigurationManager@Details@Core@Manager@Container@@QEAAJAEA_KAEAV?$shared_ptr@V?$vector@EV?$allocator@E@utl@@@utl@@@utl@@@Z; Container::Manager::Core::Details::SystemConfigurationManager::QueryRuntimeFeatureConfigurationsBuffer(unsigned __int64 &,utl::shared_ptr<utl::vector<uchar,utl::allocator<uchar>>> &)
0x1800a666f  mov     ebx, eax
0x1800a6671  test    eax, eax
0x1800a6673  jns     short loc_1800A66C0
0x1800a6675  mov     rcx, [rbp+238h]; this
0x1800a667c  mov     r9d, eax; char *
0x1800a667f  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a6686  mov     edx, 2D66h; void *
0x1800a668b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6690  nop
0x1800a6691  mov     rcx, [rbp+230h+var_1D0+8]; this
0x1800a6695  test    rcx, rcx
0x1800a6698  jz      short loc_1800A66A0
0x1800a669a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a669f  nop
0x1800a66a0  cmp     byte ptr [rsp+330h+var_2C8], sil
0x1800a66a5  jz      loc_1800A6601
0x1800a66ab  mov     rcx, [rsp+330h+var_2D0]; this
0x1800a66b0  test    rcx, rcx
0x1800a66b3  jz      short loc_1800A66BB
0x1800a66b5  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a66ba  nop
0x1800a66bb  jmp     loc_1800A6601
0x1800a66c0  mov     rax, qword ptr [rsp+330h+var_2C8+8]
0x1800a66c5  mov     qword ptr [rsp+330h+var_2C8+8], rax
0x1800a66ca  mov     [rsp+330h+var_2B8], 1
0x1800a66cf  movaps  xmm6, xmmword ptr [rsp+330h+var_2C8+8]
0x1800a66d4  mov     rax, [rbp+230h+var_1D0]
0x1800a66d8  mov     [rsp+330h+hObject+8], rax
0x1800a66dd  mov     rax, [rbp+230h+var_1D0+8]
0x1800a66e1  cmp     byte ptr [rsp+330h+var_2C8], sil
0x1800a66e6  jz      short loc_1800A66FF
0x1800a66e8  mov     rcx, [rsp+330h+var_2D0]; this
0x1800a66ed  mov     [rsp+330h+var_2D0], rax
0x1800a66f2  test    rcx, rcx
0x1800a66f5  jz      short loc_1800A66FD
0x1800a66f7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a66fc  nop
0x1800a66fd  jmp     short loc_1800A6709
0x1800a66ff  mov     [rsp+330h+var_2D0], rax
0x1800a6704  mov     byte ptr [rsp+330h+var_2C8], 1
0x1800a6709  mov     rdi, rsi
0x1800a670c  mov     qword ptr [rsp+330h+var_2C8+8], rsi
0x1800a6711  mov     rbx, rsi
0x1800a6714  mov     [rbp+230h+var_1D0], rbx
0x1800a6718  xorps   xmm0, xmm0
0x1800a671b  xor     eax, eax
0x1800a671d  movups  [rbp+230h+var_298], xmm0
0x1800a6721  movups  [rbp+230h+var_288], xmm0
0x1800a6725  movups  [rbp+230h+var_278], xmm0
0x1800a6729  mov     [rbp+230h+var_268], rax
0x1800a672d  mov     r15b, [rbp+230h+arg_20]
0x1800a6734  test    r15b, r15b
0x1800a6737  jz      loc_1800A687C
0x1800a673d  lea     r8, [rbp+230h+var_298]
0x1800a6741  lea     rdx, [rsp+330h+var_2C8+8]
0x1800a6746  mov     rcx, [r14+578h]; SRWLock
0x1800a674d  call    ?QueryHotPatches@SystemConfigurationManager@Details@Core@Manager@Container@@QEBAJAEAV?$optional@K@utl@@AEAV?$optional@UHotPatches@Common@Manager@Container@@@7@@Z; Container::Manager::Core::Details::SystemConfigurationManager::QueryHotPatches(utl::optional<ulong> &,utl::optional<Container::Manager::Common::HotPatches> &)
0x1800a6752  mov     edi, eax
0x1800a6754  test    eax, eax
0x1800a6756  jns     short loc_1800A679A
0x1800a6758  mov     rcx, [rbp+238h]; this
0x1800a675f  mov     r9d, eax; char *
0x1800a6762  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a6769  mov     edx, 2D74h; void *
0x1800a676e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6773  lea     rcx, [rbp+230h+var_298]
0x1800a6777  call    ??1?$_OptionalData1@UHotPatches@Common@Manager@Container@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(void)
0x1800a677c  cmp     byte ptr [rsp+330h+var_2C8], sil
0x1800a6781  jz      short loc_1800A6793
0x1800a6783  mov     rcx, [rsp+330h+var_2D0]; this
0x1800a6788  test    rcx, rcx
0x1800a678b  jz      short loc_1800A6793
0x1800a678d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a6792  nop
0x1800a6793  mov     eax, edi
0x1800a6795  jmp     loc_1800A6BA3
0x1800a679a  mov     rcx, [r14+518h]; this
0x1800a67a1  call    ?IsManualHotPatchMode@PolicyManager@Details@Core@Manager@Container@@QEBA_NXZ; Container::Manager::Core::Details::PolicyManager::IsManualHotPatchMode(void)
0x1800a67a6  mov     rdi, qword ptr [rsp+330h+var_2C8+8]
0x1800a67ab  test    al, al
0x1800a67ad  cmovz   rbx, rdi
0x1800a67b1  mov     [rbp+230h+var_1D0], rbx
0x1800a67b5  lea     rsi, [r14+1C8h]
0x1800a67bc  mov     rcx, rsi; SRWLock
0x1800a67bf  call    cs:__imp_AcquireSRWLockExclusive
0x1800a67c6  nop     dword ptr [rax+rax+00h]
0x1800a67cb  call    cs:__imp_GetCurrentThreadId
0x1800a67d2  nop     dword ptr [rax+rax+00h]
0x1800a67d7  mov     [rsi+8], eax
0x1800a67da  mov     [rsp+330h+hObject], rsi
0x1800a67df  cmp     byte ptr [rbp+230h+var_268], 0
0x1800a67e3  jnz     short loc_1800A67E7
0x1800a67e5  int     2Ch; Windows NT - assertion failure
0x1800a67e7  lea     r8, [rsp+330h+hObject]
0x1800a67ec  lea     rdx, [rbp+230h+var_298]
0x1800a67f0  mov     rcx, r14; this
0x1800a67f3  call    ?PrepareForHotPatching@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAUHotPatches@Common@45@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::PrepareForHotPatching(Container::Manager::Common::HotPatches &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800a67f8  mov     esi, eax
0x1800a67fa  test    eax, eax
0x1800a67fc  jns     short loc_1800A685F
0x1800a67fe  mov     rcx, [rbp+238h]; this
0x1800a6805  mov     r9d, eax; char *
0x1800a6808  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a680f  mov     edx, 2D83h; void *
0x1800a6814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6819  mov     rcx, [rsp+330h+hObject]; SRWLock
0x1800a681e  xor     ebx, ebx
0x1800a6820  test    rcx, rcx
0x1800a6823  jz      short loc_1800A6839
0x1800a6825  mov     [rcx+8], ebx
0x1800a6828  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a682f  nop     dword ptr [rax+rax+00h]
0x1800a6834  mov     [rsp+330h+hObject], rbx
0x1800a6839  lea     rcx, [rbp+230h+var_298]
0x1800a683d  call    ??1?$_OptionalData1@UHotPatches@Common@Manager@Container@@$0A@@utl@@QEAA@XZ; utl::_OptionalData1<Container::Manager::Common::HotPatches,0>::~_OptionalData1<Container::Manager::Common::HotPatches,0>(void)
0x1800a6842  cmp     byte ptr [rsp+330h+var_2C8], bl
0x1800a6846  jz      short loc_1800A6858
0x1800a6848  mov     rcx, [rsp+330h+var_2D0]; this
0x1800a684d  test    rcx, rcx
0x1800a6850  jz      short loc_1800A6858
0x1800a6852  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800a6857  nop
0x1800a6858  mov     eax, esi
0x1800a685a  jmp     loc_1800A6BA3
0x1800a685f  mov     rcx, [rsp+330h+hObject]; SRWLock
0x1800a6864  test    rcx, rcx
0x1800a6867  jz      short loc_1800A687C
0x1800a6869  mov     dword ptr [rcx+8], 0
0x1800a6870  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a6877  nop     dword ptr [rax+rax+00h]
0x1800a687c  lea     rdx, aCreatecontaine_8; "CreateContainerStateTransition_AgentNot"...
0x1800a6883  lea     rcx, [rbp+230h+var_1B0]
0x1800a688a  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800a688f  lea     rax, ??_7CreateContainerStateTransition_AgentNotifyCreating@CmTraceProvider@@6B@; const CmTraceProvider::CreateContainerStateTransition_AgentNotifyCreating::`vftable'
0x1800a6896  mov     [rbp+230h+var_1B0], rax
0x1800a689d  mov     rsi, [r13+110h]
0x1800a68a4  lea     rdx, [rsp+330h+hObject]
0x1800a68a9  lea     rcx, [rbp+230h+var_1B0]
0x1800a68b0  call    ?LockExclusive@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800a68b5  mov     rax, [rbp+230h+var_A0]
0x1800a68bc  movups  xmm0, xmmword ptr [rsi+8]
0x1800a68c0  movdqu  xmmword ptr [rax+18h], xmm0
0x1800a68c5  mov     byte ptr [rax+4], 1
0x1800a68c9  mov     rcx, [rsp+330h+hObject]; SRWLock
0x1800a68ce  xor     r13d, r13d
0x1800a68d1  test    rcx, rcx
0x1800a68d4  jz      short loc_1800A68E2
0x1800a68d6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a68dd  nop     dword ptr [rax+rax+00h]
0x1800a68e2  mov     al, [r14+668h]
0x1800a68e9  mov     [rsp+330h+var_2F8], al
0x1800a68ed  lea     rax, [rbp+230h+var_1D0]
0x1800a68f1  mov     [rsp+330h+var_300], rax
0x1800a68f6  lea     rax, [rsp+330h+var_2C8+8]
0x1800a68fb  mov     [rsp+330h+var_308], rax
0x1800a6900  mov     byte ptr [rsp+330h+var_310], r15b
0x1800a6905  mov     r9b, r12b
0x1800a6908  lea     r8, [r14+10h]
0x1800a690c  mov     r15, [rbp+230h+var_2A0]
0x1800a6910  mov     rdx, r15
0x1800a6913  lea     rcx, [rbp+230h+var_1B0]
0x1800a691a  call    ?StartActivity@CreateContainerStateTransition_AgentNotifyCreating@CmTraceProvider@@QEAAXAEBV?$optional@U_GUID@@@utl@@0_N1AEBV?$optional@K@4@21@Z; CmTraceProvider::CreateContainerStateTransition_AgentNotifyCreating::StartActivity(utl::optional<_GUID> const &,utl::optional<_GUID> const &,bool,bool,utl::optional<ulong> const &,utl::optional<ulong> const &,bool)
0x1800a691f  mov     r10, [r14+4F8h]
0x1800a6926  mov     dl, [r14+668h]
0x1800a692d  mov     byte ptr [rbp+230h+var_208], r13b
0x1800a6931  mov     [rbp+230h+var_1D8], r13b
0x1800a6935  cmp     byte ptr [rbp+230h+var_268], r13b
0x1800a6939  jz      short loc_1800A698D
0x1800a693b  mov     rax, qword ptr [rbp+230h+var_298]
0x1800a693f  mov     qword ptr [rbp+230h+var_208], rax
0x1800a6943  mov     rax, qword ptr [rbp+230h+var_298+8]
0x1800a6947  mov     qword ptr [rbp+230h+var_208+8], rax
0x1800a694b  mov     rax, qword ptr [rbp+230h+var_288]
0x1800a694f  mov     qword ptr [rbp+230h+var_1F8], rax
0x1800a6953  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800a695b  movdqu  [rbp+230h+var_298], xmm0
0x1800a6960  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a6964  mov     qword ptr [rbp+230h+var_288], rcx
0x1800a6968  mov     rax, qword ptr [rbp+230h+var_288+8]
0x1800a696c  mov     qword ptr [rbp+230h+var_1F8+8], rax
0x1800a6970  mov     rax, qword ptr [rbp+230h+var_278]
0x1800a6974  mov     qword ptr [rbp+230h+var_1E8], rax
0x1800a6978  mov     rax, qword ptr [rbp+230h+var_278+8]
0x1800a697c  mov     qword ptr [rbp+230h+var_1E8+8], rax
0x1800a6980  movdqu  [rbp+230h+var_288+8], xmm0
0x1800a6985  mov     qword ptr [rbp+230h+var_278+8], rcx
0x1800a6989  mov     [rbp+230h+var_1D8], 1
0x1800a698d  mov     byte ptr [rbp+230h+var_230], r13b
0x1800a6991  mov     byte ptr [rbp+230h+var_220], r13b
0x1800a6995  cmp     byte ptr [rsp+330h+var_2C8], r13b
0x1800a699a  jz      short loc_1800A69BB
0x1800a699c  mov     rax, [rsp+330h+hObject+8]
0x1800a69a1  mov     [rbp+230h+var_230], rax
0x1800a69a5  mov     rax, [rsp+330h+var_2D0]
0x1800a69aa  mov     [rbp+230h+var_230+8], rax
0x1800a69ae  xorps   xmm0, xmm0
0x1800a69b1  movdqu  xmmword ptr [rsp+330h+hObject+8], xmm0
0x1800a69b7  mov     byte ptr [rbp+230h+var_220], 1
0x1800a69bb  mov     rax, [r14+548h]
0x1800a69c2  mov     ecx, [rax+14h]
0x1800a69c5  mov     dword ptr [rsp+330h+hObject], ecx
  ... truncated ...
```
