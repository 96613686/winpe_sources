# CRdpIdAdapter::ProcessStartProcessor(_GUID const &)

- ea: `0x18001b1a0`
- end: `0x18001b529`
- name: `?ProcessStartProcessor@CRdpIdAdapter@@AEAAXAEBU_GUID@@@Z`
- size: `905`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800185bc`
- `0x18001a25c`

## callees

- `0x180006f84`
- `0x18000e114`
- `0x18000ead8`
- `0x18001072c`
- `0x180012ad4`
- `0x1800177b0`
- `0x1800177fc`
- `0x1800178c8`
- `0x180017914`
- `0x18001b1a0`
- `0x18001dd70`
- `0x18001ddf4`
- `0x180021750`
- `0x180021830`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b234`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b234`

## string_xrefs

- `0x18001b2d2`: `Failed to open property store`
- `0x18001b1c8`: `Video encoder dll has not been loaded`
- `0x18001b206`: `Encoding processor has already been started`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CRdpIdAdapter::ProcessStartProcessor(CRdpIdAdapter *this, const struct _GUID *a2)
{
  FARPROC ProcAddress; // rbx
  unsigned int v5; // eax
  __int64 *v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // eax
  const struct _GUID *v9; // r9
  unsigned int v10; // eax
  unsigned int v11; // r9d
  unsigned int v12; // eax
  const struct _LUID *v13; // r9
  unsigned int v14; // eax
  unsigned int v15; // r9d
  unsigned int v16; // eax
  const struct _tagpropertykey *v17; // r8
  bool v18; // r9
  unsigned int v19; // eax
  const struct _tagpropertykey *v20; // r8
  bool v21; // r9
  unsigned int v22; // eax
  _QWORD *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdi
  unsigned int v26; // eax
  char *v27; // [rsp+28h] [rbp-18h]
  char *v28; // [rsp+28h] [rbp-18h]
  char *v29; // [rsp+28h] [rbp-18h]
  char *v30; // [rsp+28h] [rbp-18h]
  char *v31; // [rsp+28h] [rbp-18h]
  char *v32; // [rsp+28h] [rbp-18h]
  char *v33; // [rsp+28h] [rbp-18h]
  char *v34; // [rsp+28h] [rbp-18h]
  char *v35; // [rsp+28h] [rbp-18h]
  const char *v36; // [rsp+30h] [rbp-10h] BYREF
  std::_Ref_count_base *v37; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  Rdp::Utils::Props *v39; // [rsp+70h] [rbp+30h] BYREF
  _QWORD *v40; // [rsp+78h] [rbp+38h]

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xC2D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 52) == 0,
    (bool)"Video encoder dll has not been loaded",
    v36);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xC35,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_QWORD *)this + 70) != 0,
    (bool)"Encoding processor has already been started",
    v36);
  ProcAddress = GetProcAddress(*((HMODULE *)this + 52), "ClassFactory");
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(
    retaddr,
    3130,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    ProcAddress,
    "Failed to load address of ClassFactory");
  wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset((char *)this + 560);
  v5 = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, char *))ProcAddress)(
         a2,
         &GUID_adddf56d_f95b_444f_bfb5_db18b475f325,
         (char *)this + 560);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC44,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v5,
    (int)"Failed to instantiate video encoder processor",
    v27);
  *((struct _GUID *)this + 34) = *a2;
  v39 = 0;
  v6 = (__int64 *)*((_QWORD *)this + 70);
  v7 = *v6;
  v39 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, Rdp::Utils::Props **))(v7 + 24))(v6, &v39);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC4D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v8,
    (int)"Failed to open property store",
    v28);
  v10 = Rdp::Utils::Props::IPropertyStore_SetCLSID(
          v39,
          (struct IPropertyStore *)&PKEY_Activity_Id,
          (const struct _tagpropertykey *)&RdpIddLoggingProviderWithCorrelationId::g_CorrelationId,
          v9);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC57,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v10,
    (int)"Failed to set PKEY_Activity_Id property",
    v29);
  v12 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v39,
          (struct IPropertyStore *)&PKEY_Session_Id,
          (const struct _tagpropertykey *)*((unsigned int *)this + 129),
          v11);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC61,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v12,
    (int)"Failed to set PKEY_Session_Id property",
    v30);
  v14 = Rdp::Utils::Props::IPropertyStore_SetLuid(
          v39,
          (struct IPropertyStore *)&PKEY_Terminal_Luid,
          (const struct _tagpropertykey *)this + 26,
          v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC6B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v14,
    (int)"Failed to set PKEY_Terminal_Luid property",
    v31);
  v16 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v39,
          (struct IPropertyStore *)&PKEY_Bind_Process_Pid,
          (const struct _tagpropertykey *)*((unsigned int *)this + 135),
          v15);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC75,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v16,
    (int)"Failed to set PKEY_Bind_Process_Pid property",
    v32);
  LOBYTE(v17) = *((_BYTE *)this + 592);
  v19 = Rdp::Utils::Props::IPropertyStore_SetBool(v39, (struct IPropertyStore *)&PKEY_Console_Mode_Enabled, v17, v18);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC7F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v19,
    (int)"Failed to set PKEY_Console_Mode_Enabled property",
    v33);
  LOBYTE(v20) = *((_BYTE *)this + 444) & 1;
  v22 = Rdp::Utils::Props::IPropertyStore_SetBool(v39, (struct IPropertyStore *)&PKEY_Large_Cursor_Enabled, v20, v21);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC89,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v22,
    (int)"Failed to set PKEY_Large_Cursor_Enabled property",
    v34);
  v23 = operator new(0x28u);
  v40 = v23;
  v24 = std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(this, &v36);
  *v23 = &winrt::impl::producers_base<CRdpIdAdapter::CInnerComSink,std::tuple<Rdp::Avenc::ICriticalErrorEvents>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v23[2] = 1;
  *v23 = &CRdpIdAdapter::CInnerComSink::`vftable'{for `winrt::impl::producers_base<CRdpIdAdapter::CInnerComSink,std::tuple<Rdp::Avenc::ICriticalErrorEvents>>'};
  v23[1] = &CRdpIdAdapter::CInnerComSink::`vftable'{for `winrt::impl::root_implements<CRdpIdAdapter::CInnerComSink,Rdp::Avenc::ICriticalErrorEvents>'};
  std::weak_ptr<CRdpIdAdapter>::weak_ptr<CRdpIdAdapter>(v23 + 3, v24);
  v25 = *((_QWORD *)this + 53);
  *((_QWORD *)this + 53) = v23;
  (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v37 )
    std::_Ref_count_base::_Decref(v37);
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 70) + 32LL))(
          *((_QWORD *)this + 70),
          *((_QWORD *)this + 53));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC90,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v26,
    (int)"Failed to start encoding processor",
    v35);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v39);
}

```

## disassembly

```asm
0x18001b1a0  mov     [rsp-28h+arg_10], rbx
0x18001b1a5  push    rbp
0x18001b1a6  push    rsi
0x18001b1a7  push    rdi
0x18001b1a8  push    r14
0x18001b1aa  push    r15
0x18001b1ac  mov     rbp, rsp
0x18001b1af  sub     rsp, 40h
0x18001b1b3  mov     rdi, rdx
0x18001b1b6  mov     rsi, rcx
0x18001b1b9  cmp     qword ptr [rcx+1A0h], 0
0x18001b1c1  setz    al
0x18001b1c4  mov     rcx, [rbp+28h]; this
0x18001b1c8  lea     rdx, aVideoEncoderDl; "Video encoder dll has not been loaded"
0x18001b1cf  mov     [rsp+40h+var_18], rdx; bool
0x18001b1d4  mov     [rsp+40h+var_20], al; char
0x18001b1d8  mov     ebx, 80070057h
0x18001b1dd  mov     r9d, ebx; char *
0x18001b1e0  lea     r15, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001b1e7  mov     r8, r15; unsigned int
0x18001b1ea  mov     edx, 0C2Dh; void *
0x18001b1ef  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001b1f4  lea     r14, [rsi+230h]
0x18001b1fb  cmp     qword ptr [r14], 0
0x18001b1ff  setnz   al
0x18001b202  mov     rcx, [rbp+28h]; this
0x18001b206  lea     rdx, aEncodingProces_1; "Encoding processor has already been sta"...
0x18001b20d  mov     [rsp+40h+var_18], rdx; char *
0x18001b212  mov     [rsp+40h+var_20], al; char
0x18001b216  mov     r9d, ebx; char *
0x18001b219  mov     r8, r15; unsigned int
0x18001b21c  mov     edx, 0C35h; void *
0x18001b221  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001b226  lea     rdx, aClassfactory; "ClassFactory"
0x18001b22d  mov     rcx, [rsi+1A0h]; hModule
0x18001b234  call    cs:__imp_GetProcAddress
0x18001b23b  nop     dword ptr [rax+rax+00h]
0x18001b240  mov     rbx, rax
0x18001b243  mov     rcx, [rbp+28h]
0x18001b247  lea     rax, aFailedToLoadAd_0; "Failed to load address of ClassFactory"
0x18001b24e  mov     qword ptr [rsp+40h+var_20], rax
0x18001b253  mov     r9, rbx
0x18001b256  mov     r8, r15
0x18001b259  mov     edx, 0C3Ah
0x18001b25e  call    ??$Throw_GetLastErrorIfNullMsg@P6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU123@1@Z$0A@@in1diag3@details@wil@@YAP6AJPEBUAVENC_VERSION_INFO@Avenc@Rdp@@PEAU345@1@ZPEAXIPEBDP6AJ011@Z3ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),0>(void *,uint,char const *,long (*)(Rdp::Avenc::AVENC_VERSION_INFO const *,Rdp::Avenc::AVENC_VERSION_INFO *,Rdp::Avenc::AVENC_VERSION_INFO *),char const *,...)
0x18001b263  mov     rcx, r14
0x18001b266  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x18001b26b  mov     r8, r14
0x18001b26e  lea     rdx, _GUID_adddf56d_f95b_444f_bfb5_db18b475f325
0x18001b275  mov     rcx, rdi
0x18001b278  mov     rax, rbx
0x18001b27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b280  mov     rcx, [rbp+28h]; this
0x18001b284  lea     rdx, aFailedToInstan; "Failed to instantiate video encoder pro"...
0x18001b28b  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b290  mov     r9d, eax; char *
0x18001b293  mov     r8, r15; unsigned int
0x18001b296  mov     edx, 0C44h; void *
0x18001b29b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b2a0  movups  xmm0, xmmword ptr [rdi]
0x18001b2a3  movdqu  xmmword ptr [rsi+220h], xmm0
0x18001b2ab  mov     [rbp+arg_0], 0
0x18001b2b3  mov     rcx, [r14]
0x18001b2b6  mov     rax, [rcx]
0x18001b2b9  mov     [rbp+arg_0], 0
0x18001b2c1  lea     rdx, [rbp+arg_0]
0x18001b2c5  mov     rax, [rax+18h]
0x18001b2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2ce  mov     rcx, [rbp+28h]; this
0x18001b2d2  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x18001b2d9  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b2de  mov     r9d, eax; char *
0x18001b2e1  mov     r8, r15; unsigned int
0x18001b2e4  mov     edx, 0C4Dh; void *
0x18001b2e9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b2ee  lea     r8, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _tagpropertykey *
0x18001b2f5  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x18001b2fc  mov     rcx, [rbp+arg_0]; this
0x18001b300  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x18001b305  mov     rcx, [rbp+28h]; this
0x18001b309  lea     rdx, aFailedToSetPke_38; "Failed to set PKEY_Activity_Id property"
0x18001b310  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b315  mov     r9d, eax; char *
0x18001b318  mov     r8, r15; unsigned int
0x18001b31b  mov     edx, 0C57h; void *
0x18001b320  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b325  mov     r8d, [rsi+204h]; struct _tagpropertykey *
0x18001b32c  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x18001b333  mov     rcx, [rbp+arg_0]; this
0x18001b337  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001b33c  mov     rcx, [rbp+28h]; this
0x18001b340  lea     rdx, aFailedToSetPke_3; "Failed to set PKEY_Session_Id property"
0x18001b347  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b34c  mov     r9d, eax; char *
0x18001b34f  mov     r8, r15; unsigned int
0x18001b352  mov     edx, 0C61h; void *
0x18001b357  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b35c  lea     r8, [rsi+208h]; struct _tagpropertykey *
0x18001b363  lea     rdx, PKEY_Terminal_Luid; struct IPropertyStore *
0x18001b36a  mov     rcx, [rbp+arg_0]; this
0x18001b36e  call    ?IPropertyStore_SetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetLuid(IPropertyStore *,_tagpropertykey const &,_LUID const &)
0x18001b373  mov     rcx, [rbp+28h]; this
0x18001b377  lea     rdx, aFailedToSetPke_6; "Failed to set PKEY_Terminal_Luid proper"...
0x18001b37e  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b383  mov     r9d, eax; char *
0x18001b386  mov     r8, r15; unsigned int
0x18001b389  mov     edx, 0C6Bh; void *
0x18001b38e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b393  mov     r8d, [rsi+21Ch]; struct _tagpropertykey *
0x18001b39a  lea     rdx, PKEY_Bind_Process_Pid; struct IPropertyStore *
0x18001b3a1  mov     rcx, [rbp+arg_0]; this
0x18001b3a5  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001b3aa  mov     rcx, [rbp+28h]; this
0x18001b3ae  lea     rdx, aFailedToSetPke_5; "Failed to set PKEY_Bind_Process_Pid pro"...
0x18001b3b5  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b3ba  mov     r9d, eax; char *
0x18001b3bd  mov     r8, r15; unsigned int
0x18001b3c0  mov     edx, 0C75h; void *
0x18001b3c5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b3ca  mov     r8b, [rsi+250h]; struct _tagpropertykey *
0x18001b3d1  lea     rdx, PKEY_Console_Mode_Enabled; struct IPropertyStore *
0x18001b3d8  mov     rcx, [rbp+arg_0]; this
0x18001b3dc  call    ?IPropertyStore_SetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@_N@Z; Rdp::Utils::Props::IPropertyStore_SetBool(IPropertyStore *,_tagpropertykey const &,bool)
0x18001b3e1  mov     rcx, [rbp+28h]; this
0x18001b3e5  lea     rdx, aFailedToSetPke_17; "Failed to set PKEY_Console_Mode_Enabled"...
0x18001b3ec  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b3f1  mov     r9d, eax; char *
0x18001b3f4  mov     r8, r15; unsigned int
0x18001b3f7  mov     edx, 0C7Fh; void *
0x18001b3fc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b401  mov     r8b, [rsi+1BCh]
0x18001b408  and     r8b, 1; struct _tagpropertykey *
0x18001b40c  lea     rdx, PKEY_Large_Cursor_Enabled; struct IPropertyStore *
0x18001b413  mov     rcx, [rbp+arg_0]; this
0x18001b417  call    ?IPropertyStore_SetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@_N@Z; Rdp::Utils::Props::IPropertyStore_SetBool(IPropertyStore *,_tagpropertykey const &,bool)
0x18001b41c  mov     rcx, [rbp+28h]; this
0x18001b420  lea     rdx, aFailedToSetPke_41; "Failed to set PKEY_Large_Cursor_Enabled"...
0x18001b427  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b42c  mov     r9d, eax; char *
0x18001b42f  mov     r8, r15; unsigned int
0x18001b432  mov     edx, 0C89h; void *
0x18001b437  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b43c  mov     ecx, 28h ; '('; Size
0x18001b441  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b446  mov     rbx, rax
0x18001b449  mov     [rbp+arg_8], rax
0x18001b44d  lea     rdx, [rbp+var_10]
0x18001b451  mov     rcx, rsi
0x18001b454  call    ?shared_from_this@?$enable_shared_from_this@VCRdpIdAdapter@@@std@@QEAA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::enable_shared_from_this<CRdpIdAdapter>::shared_from_this(void)
0x18001b459  lea     rcx, ??_7?$producers_base@VCInnerComSink@CRdpIdAdapter@@V?$tuple@UICriticalErrorEvents@Avenc@Rdp@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CRdpIdAdapter::CInnerComSink,std::tuple<Rdp::Avenc::ICriticalErrorEvents>>::`vftable'
0x18001b460  mov     [rbx], rcx
0x18001b463  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001b46a  mov     qword ptr [rbx+10h], 1
0x18001b472  lea     rcx, ??_7CInnerComSink@CRdpIdAdapter@@6B?$producers_base@VCInnerComSink@CRdpIdAdapter@@V?$tuple@UICriticalErrorEvents@Avenc@Rdp@@@std@@@impl@winrt@@@; const CRdpIdAdapter::CInnerComSink::`vftable'{for `winrt::impl::producers_base<CRdpIdAdapter::CInnerComSink,std::tuple<Rdp::Avenc::ICriticalErrorEvents>>'}
0x18001b479  mov     [rbx], rcx
0x18001b47c  lea     rcx, ??_7CInnerComSink@CRdpIdAdapter@@6B?$root_implements@VCInnerComSink@CRdpIdAdapter@@UICriticalErrorEvents@Avenc@Rdp@@@impl@winrt@@@; const CRdpIdAdapter::CInnerComSink::`vftable'{for `winrt::impl::root_implements<CRdpIdAdapter::CInnerComSink,Rdp::Avenc::ICriticalErrorEvents>'}
0x18001b483  mov     [rbx+8], rcx
0x18001b487  lea     rcx, [rbx+18h]
0x18001b48b  mov     rdx, rax
0x18001b48e  call    ??$?0VCRdpIdAdapter@@$0A@@?$weak_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV?$shared_ptr@VCRdpIdAdapter@@@1@@Z; std::weak_ptr<CRdpIdAdapter>::weak_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18001b493  nop
0x18001b494  mov     rdi, [rsi+1A8h]
0x18001b49b  mov     [rsi+1A8h], rbx
0x18001b4a2  mov     rax, [rbx]
0x18001b4a5  mov     rcx, rbx
0x18001b4a8  mov     rax, [rax+8]
0x18001b4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4b1  test    rdi, rdi
0x18001b4b4  jz      short loc_18001B4C6
0x18001b4b6  mov     rax, [rdi]
0x18001b4b9  mov     rcx, rdi
0x18001b4bc  mov     rax, [rax+10h]
0x18001b4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4c5  nop
0x18001b4c6  mov     rcx, [rbp+var_8]; this
0x18001b4ca  test    rcx, rcx
0x18001b4cd  jz      short loc_18001B4D4
0x18001b4cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001b4d4  mov     rcx, [r14]
0x18001b4d7  mov     rax, [rcx]
0x18001b4da  mov     rdx, [rsi+1A8h]
0x18001b4e1  mov     rax, [rax+20h]
0x18001b4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4ea  mov     rcx, [rbp+28h]; this
0x18001b4ee  lea     rdx, aFailedToStartE; "Failed to start encoding processor"
0x18001b4f5  mov     qword ptr [rsp+40h+var_20], rdx; int
0x18001b4fa  mov     r9d, eax; char *
0x18001b4fd  mov     r8, r15; unsigned int
0x18001b500  mov     edx, 0C90h; void *
0x18001b505  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001b50a  nop
0x18001b50b  lea     rcx, [rbp+arg_0]
0x18001b50f  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18001b514  mov     rbx, [rsp+40h+arg_10]
0x18001b51c  add     rsp, 40h
0x18001b520  pop     r15
0x18001b522  pop     r14
0x18001b524  pop     rdi
0x18001b525  pop     rsi
0x18001b526  pop     rbp
0x18001b527  retn
```
