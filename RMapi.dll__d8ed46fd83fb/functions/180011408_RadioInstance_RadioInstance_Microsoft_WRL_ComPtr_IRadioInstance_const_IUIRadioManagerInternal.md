# RadioInstance::RadioInstance(Microsoft::WRL::ComPtr<IRadioInstance> const &,IUIRadioManagerInternal *)

- ea: `0x180011408`
- end: `0x180011735`
- name: `??0RadioInstance@@QEAA@AEBV?$ComPtr@UIRadioInstance@@@WRL@Microsoft@@PEAUIUIRadioManagerInternal@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(RadioInstance *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019acc`

## callees

- `0x1800042b0`
- `0x180006b98`
- `0x180007568`
- `0x180007f00`
- `0x180008640`
- `0x18000ad6c`
- `0x18000b814`
- `0x18000c1e0`
- `0x18000c640`
- `0x180011408`
- `0x18001691c`
- `0x180016940`
- `0x180023f50`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800115c3`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800115c3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800114b8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800114b8`

## string_xrefs

- `0x180011522`: `onecoreuap\net\mobility\radiomanagement\dll\radioinstance.cpp`
- `0x180011558`: `onecoreuap\net\mobility\radiomanagement\dll\radioinstance.cpp`
- `0x18001159e`: `onecoreuap\net\mobility\radiomanagement\dll\radioinstance.cpp`
- `0x180011666`: `onecoreuap\net\mobility\radiomanagement\dll\radioinstance.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
RadioInstance *__fastcall RadioInstance::RadioInstance(RadioInstance *this, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rsi
  const char **v7; // r15
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, char *); // rbx
  unsigned int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, char *); // rbx
  LCID UserDefaultLCID; // eax
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // edi
  const char **v20; // rax
  const char **v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  const char *v26; // [rsp+28h] [rbp-41h]
  const char *v27; // [rsp+28h] [rbp-41h]
  const char *v28; // [rsp+28h] [rbp-41h]
  const wchar_t *v29; // [rsp+60h] [rbp-9h] BYREF
  __int64 v30; // [rsp+68h] [rbp-1h] BYREF
  const wchar_t *v31; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  RadioInstance *v33; // [rsp+D0h] [rbp+67h] BYREF
  const wchar_t *v34; // [rsp+D8h] [rbp+6Fh] BYREF
  const char *v35; // [rsp+E0h] [rbp+77h] BYREF
  __int64 *v36; // [rsp+E8h] [rbp+7Fh] BYREF

  v33 = this;
  *((_QWORD *)this + 2) = &IUIRadioInstanceInternal::`vftable';
  *((_DWORD *)this + 7) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUIRadioInstance,IUIRadioInstance2,IUIRadioInstanceInternal>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUIRadioInstance,IUIRadioInstance2,IUIRadioInstanceInternal>::`vftable'{for `IUIRadioInstance2'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUIRadioInstance,IUIRadioInstance2,IUIRadioInstanceInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioInstanceInternal>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &RadioInstance::`vftable';
  *((_QWORD *)this + 1) = &RadioInstance::`vftable'{for `IUIRadioInstance2'};
  *((_QWORD *)this + 2) = &RadioInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioInstanceInternal>'};
  v6 = (_QWORD *)((char *)this + 32);
  *((_QWORD *)this + 4) = *a2;
  Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef((char *)this + 32);
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this + 1, 0, 0);
  *((_QWORD *)this + 10) = a3;
  *((_DWORD *)this + 22) = 0;
  *(_QWORD *)((char *)this + 92) = 0;
  *((_DWORD *)this + 25) = 0;
  *((_WORD *)this + 52) = 1;
  *((_BYTE *)this + 106) = 0;
  *((_QWORD *)this + 14) = 0;
  v7 = (const char **)((char *)this + 120);
  *((_QWORD *)this + 15) = 0;
  *((GUID *)this + 8) = GUID_NULL;
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 48LL))(*v6);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x13,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioinstance.cpp",
    (const char *)v8,
    (int)"IRadioInstance::GetRadioState",
    v26);
  v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v6 + 24LL))(*v6, (char *)this + 128);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x14,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioinstance.cpp",
    (const char *)v9,
    (int)"IRadioInstance::GetRadioManagerSignature",
    v27);
  v10 = *((_QWORD *)this + 4);
  v11 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v10 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    (char *)this + 112,
    0);
  v12 = v11(v10, (char *)this + 112);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x15,
    (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioinstance.cpp",
    (const char *)v12,
    (int)"IRadioInstance::GetInstanceSignature",
    v28);
  v13 = *((_QWORD *)this + 4);
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v13 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
    (char *)this + 120,
    0);
  UserDefaultLCID = GetUserDefaultLCID();
  v16 = v14(v13, UserDefaultLCID, (char *)this + 120);
  v19 = v16;
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v34) = v16;
      v35 = "GetFriendlyName failed, using default name";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)dword_180037050,
        (unsigned __int8 *)byte_18002E66B,
        v17,
        v18,
        (const wchar_t **)&v35,
        (__int64)&v34);
    }
    v20 = (const char **)RMAPI::LoadStringFromFile(&v34, 1000);
    v21 = v20;
    if ( v7 != v20 )
    {
      wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(
        (char *)this + 120,
        *v20);
      *v21 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v34);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,0>(
      (_DWORD)retaddr,
      29,
      (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radioinstance.cpp",
      -2147467259,
      (__int64)this + 120);
  }
  RadioInstance::_UpdateUIEnabled(this);
  RadioInstance::_UpdateDisplayRadioState(this);
  if ( (unsigned int)dword_180037050 > 4 )
  {
    LODWORD(v33) = v19;
    v34 = (const wchar_t *)RMToString((RadioInstance *)((char *)this + 88));
    v35 = *v7;
    v36 = (__int64 *)*((_QWORD *)this + 14);
    v29 = (const wchar_t *)RmGuidToMediaTypeString((const struct _GUID *)this + 8);
    v30 = (__int64)this + 128;
    v31 = (const wchar_t *)"Instantiated a new RadioInstance";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned __int8 *)byte_18002E5E3,
      v23,
      v24,
      &v31,
      &v30,
      &v29,
      &v36,
      (__int64 **)&v35,
      &v34,
      (__int64)&v33);
  }
  return this;
}

```

## disassembly

```asm
0x180011408  mov     [rsp-8+arg_0], rcx
0x18001140d  push    rbp
0x18001140e  push    rbx
0x18001140f  push    rsi
0x180011410  push    rdi
0x180011411  push    r12
0x180011413  push    r13
0x180011415  push    r14
0x180011417  push    r15
0x180011419  lea     rbp, [rsp-1Fh]
0x18001141e  sub     rsp, 88h
0x180011425  mov     rbx, r8
0x180011428  mov     rdi, rdx
0x18001142b  mov     r14, rcx
0x18001142e  lea     rax, ??_7IUIRadioInstanceInternal@@6B@; const IUIRadioInstanceInternal::`vftable'
0x180011435  mov     [rcx+10h], rax
0x180011439  mov     dword ptr [rcx+1Ch], 1
0x180011440  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUIRadioInstance@@UIUIRadioInstance2@@UIUIRadioInstanceInternal@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUIRadioInstance,IUIRadioInstance2,IUIRadioInstanceInternal>::`vftable'
0x180011447  mov     [rcx], rax
0x18001144a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUIRadioInstance@@UIUIRadioInstance2@@UIUIRadioInstanceInternal@@@WRL@Microsoft@@6BIUIRadioInstance2@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUIRadioInstance,IUIRadioInstance2,IUIRadioInstanceInternal>::`vftable'{for `IUIRadioInstance2'}
0x180011451  mov     [rcx+8], rax
0x180011455  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUIRadioInstance@@UIUIRadioInstance2@@UIUIRadioInstanceInternal@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUIRadioInstanceInternal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUIRadioInstance,IUIRadioInstance2,IUIRadioInstanceInternal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioInstanceInternal>'}
0x18001145c  mov     [rcx+10h], rax
0x180011460  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180011467  xor     r12d, r12d
0x18001146a  test    rcx, rcx
0x18001146d  jz      short loc_18001147C
0x18001146f  mov     rax, [rcx]
0x180011472  mov     rax, [rax+8]
0x180011476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001147b  nop
0x18001147c  lea     rax, ??_7RadioInstance@@6B@; const RadioInstance::`vftable'
0x180011483  mov     [r14], rax
0x180011486  lea     rax, ??_7RadioInstance@@6BIUIRadioInstance2@@@; const RadioInstance::`vftable'{for `IUIRadioInstance2'}
0x18001148d  mov     [r14+8], rax
0x180011491  lea     rax, ??_7RadioInstance@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUIRadioInstanceInternal@@@Details@WRL@Microsoft@@@; const RadioInstance::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUIRadioInstanceInternal>'}
0x180011498  mov     [r14+10h], rax
0x18001149c  lea     rsi, [r14+20h]
0x1800114a0  mov     rax, [rdi]
0x1800114a3  mov     [rsi], rax
0x1800114a6  mov     rcx, rsi
0x1800114a9  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x1800114ae  nop
0x1800114af  lea     rcx, [r14+28h]; lpCriticalSection
0x1800114b3  xor     r8d, r8d; Flags
0x1800114b6  xor     edx, edx; dwSpinCount
0x1800114b8  call    cs:__imp_InitializeCriticalSectionEx
0x1800114be  nop
0x1800114bf  mov     [r14+50h], rbx
0x1800114c3  lea     rdx, [r14+58h]
0x1800114c7  mov     [rdx], r12d
0x1800114ca  mov     [r14+5Ch], r12
0x1800114ce  mov     [r14+64h], r12d
0x1800114d2  mov     word ptr [r14+68h], 1
0x1800114d9  mov     [r14+6Ah], r12b
0x1800114dd  lea     r13, [r14+70h]
0x1800114e1  mov     [r13+0], r12
0x1800114e5  lea     r15, [r14+78h]
0x1800114e9  mov     [r15], r12
0x1800114ec  lea     r12, [r14+80h]
0x1800114f3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800114fa  movdqu  xmmword ptr [r12], xmm0
0x180011500  mov     rcx, [rsi]
0x180011503  mov     rax, [rcx]
0x180011506  mov     rax, [rax+30h]
0x18001150a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001150f  mov     rcx, [rbp+5Fh]; this
0x180011513  lea     rdx, aIradioinstance_7; "IRadioInstance::GetRadioState"
0x18001151a  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x18001151f  mov     r9d, eax; char *
0x180011522  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180011529  mov     edx, 13h; void *
0x18001152e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011533  mov     rcx, [rsi]
0x180011536  mov     rax, [rcx]
0x180011539  mov     rdx, r12
0x18001153c  mov     rax, [rax+18h]
0x180011540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011545  mov     rcx, [rbp+5Fh]; this
0x180011549  lea     rdx, aIradioinstance_2; "IRadioInstance::GetRadioManagerSignatur"...
0x180011550  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x180011555  mov     r9d, eax; char *
0x180011558  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobility\\radiomanagem"...
0x18001155f  mov     edx, 14h; void *
0x180011564  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180011569  mov     rdi, [rsi]
0x18001156c  mov     rax, [rdi]
0x18001156f  mov     rbx, [rax+20h]
0x180011573  xor     edx, edx
0x180011575  mov     rcx, r13
0x180011578  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18001157d  mov     rdx, r13
0x180011580  mov     rcx, rdi
0x180011583  mov     rax, rbx
0x180011586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001158b  mov     rcx, [rbp+5Fh]; this
0x18001158f  lea     rdx, aIradioinstance_3; "IRadioInstance::GetInstanceSignature"
0x180011596  mov     qword ptr [rsp+0C0h+var_A0], rdx; int
0x18001159b  mov     r9d, eax; char *
0x18001159e  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobility\\radiomanagem"...
0x1800115a5  mov     edx, 15h; void *
0x1800115aa  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800115af  mov     rdi, [rsi]
0x1800115b2  mov     rax, [rdi]
0x1800115b5  mov     rbx, [rax+28h]
0x1800115b9  xor     edx, edx
0x1800115bb  mov     rcx, r15
0x1800115be  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x1800115c3  call    cs:__imp_GetUserDefaultLCID
0x1800115c9  mov     r8, r15
0x1800115cc  mov     edx, eax
0x1800115ce  mov     rcx, rdi
0x1800115d1  mov     rax, rbx
0x1800115d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d9  mov     edi, eax
0x1800115db  test    eax, eax
0x1800115dd  jns     loc_180011677
0x1800115e3  mov     ecx, cs:dword_180037050
0x1800115e9  cmp     ecx, 2
0x1800115ec  jbe     short loc_18001161A
0x1800115ee  mov     dword ptr [rbp+57h+arg_8], eax
0x1800115f1  lea     rax, aGetfriendlynam; "GetFriendlyName failed, using default n"...
0x1800115f8  mov     [rbp+57h+arg_10], rax
0x1800115fc  lea     rax, [rbp+57h+arg_8]
0x180011600  mov     [rsp+0C0h+var_98], rax
0x180011605  lea     rax, [rbp+57h+arg_10]
0x180011609  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18001160e  lea     rdx, byte_18002E66B
0x180011615  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001161a  mov     edx, 3E8h
0x18001161f  lea     rcx, [rbp+57h+arg_8]
0x180011623  call    ?LoadStringFromFile@RMAPI@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@I@Z; RMAPI::LoadStringFromFile(uint)
0x180011628  mov     rbx, rax
0x18001162b  cmp     r15, rax
0x18001162e  jz      short loc_180011642
0x180011630  mov     rdx, [rax]
0x180011633  mov     rcx, r15
0x180011636  call    ?reset@?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAAXPEA_W@Z; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::reset(wchar_t *)
0x18001163b  mov     qword ptr [rbx], 0
0x180011642  lea     rcx, [rbp+57h+arg_8]
0x180011646  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x18001164b  mov     rcx, [rbp+5Fh]
0x18001164f  lea     rax, aLoadstringfrom; "LoadStringFromFile"
0x180011656  mov     [rsp+0C0h+var_98], rax
0x18001165b  mov     qword ptr [rsp+0C0h+var_A0], r15
0x180011660  mov     r9d, 80004005h
0x180011666  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\mobility\\radiomanagem"...
0x18001166d  mov     edx, 1Dh
0x180011672  call    ??$Throw_HrIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,0>(void *,uint,char const *,long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> const &,char const *,...)
0x180011677  mov     rcx, r14; this
0x18001167a  call    ?_UpdateUIEnabled@RadioInstance@@AEAAXXZ; RadioInstance::_UpdateUIEnabled(void)
0x18001167f  mov     rcx, r14; this
0x180011682  call    ?_UpdateDisplayRadioState@RadioInstance@@AEAAXXZ; RadioInstance::_UpdateDisplayRadioState(void)
0x180011687  mov     r8d, cs:dword_180037050
0x18001168e  cmp     r8d, 4
0x180011692  jbe     loc_18001171E
0x180011698  mov     dword ptr [rbp+57h+arg_0], edi
0x18001169b  lea     rcx, [r14+58h]; enum _DEVICE_RADIO_STATE *
0x18001169f  call    ?RMToString@@YAPEBDAEBW4_DEVICE_RADIO_STATE@@@Z; RMToString(_DEVICE_RADIO_STATE const &)
0x1800116a4  mov     [rbp+57h+arg_8], rax
0x1800116a8  mov     rax, [r15]
0x1800116ab  mov     [rbp+57h+arg_10], rax
0x1800116af  mov     rax, [r13+0]
0x1800116b3  mov     [rbp+57h+arg_18], rax
0x1800116b7  mov     rcx, r12; struct _GUID *
0x1800116ba  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x1800116bf  mov     [rbp+57h+var_60], rax
0x1800116c3  mov     [rbp+57h+var_58], r12
0x1800116c7  lea     rax, aInstantiatedAN; "Instantiated a new RadioInstance"
0x1800116ce  mov     [rbp+57h+var_50], rax
0x1800116d2  lea     rax, [rbp+57h+arg_0]
0x1800116d6  mov     [rsp+0C0h+var_70], rax
0x1800116db  lea     rax, [rbp+57h+arg_8]
0x1800116df  mov     [rsp+0C0h+var_78], rax
0x1800116e4  lea     rax, [rbp+57h+arg_10]
0x1800116e8  mov     [rsp+0C0h+var_80], rax
0x1800116ed  lea     rax, [rbp+57h+arg_18]
0x1800116f1  mov     [rsp+0C0h+var_88], rax
0x1800116f6  lea     rax, [rbp+57h+var_60]
0x1800116fa  mov     [rsp+0C0h+var_90], rax
0x1800116ff  lea     rax, [rbp+57h+var_58]
0x180011703  mov     [rsp+0C0h+var_98], rax
0x180011708  lea     rax, [rbp+57h+var_50]
0x18001170c  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180011711  lea     rdx, byte_18002E5E3
0x180011718  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapSz@_W@@U3@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapSz@_W@@53AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001171d  nop
0x18001171e  mov     rax, r14
0x180011721  add     rsp, 88h
0x180011728  pop     r15
0x18001172a  pop     r14
0x18001172c  pop     r13
0x18001172e  pop     r12
0x180011730  pop     rdi
0x180011731  pop     rsi
0x180011732  pop     rbx
0x180011733  pop     rbp
0x180011734  retn
```
