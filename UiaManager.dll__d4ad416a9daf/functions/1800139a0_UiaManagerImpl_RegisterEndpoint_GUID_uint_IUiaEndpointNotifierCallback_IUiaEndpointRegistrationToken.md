# UiaManagerImpl::RegisterEndpoint(_GUID,uint,IUiaEndpointNotifierCallback *,IUiaEndpointRegistrationToken * *)

- ea: `0x1800139a0`
- end: `0x180013fd9`
- name: `?RegisterEndpoint@UiaManagerImpl@@UEAAJU_GUID@@IPEAUIUiaEndpointNotifierCallback@@PEAPEAUIUiaEndpointRegistrationToken@@@Z`
- size: `1593`
- prototype: `__int64 __fastcall(UiaManagerImpl *this, struct _GUID *, int, struct IUiaEndpointNotifierCallback *, struct IUiaEndpointRegistrationToken **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005610`
- `0x180006edc`
- `0x180008c70`
- `0x18000cbe8`
- `0x18000d69c`
- `0x18000e59c`
- `0x1800139a0`
- `0x180031540`
- `0x180043680`
- `0x180043a30`
- `0x180043ad0`
- `0x180044188`
- `0x180091010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180013b55`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180013b55`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180013b70`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180013b70`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013c6f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013c6f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013ba7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013ba7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180013aa8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180013aa8`

## string_xrefs

- `0x180013a14`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013a42`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013a70`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013e1e`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013eb2`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013fc6`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
__int64 __fastcall UiaManagerImpl::RegisterEndpoint(
        UiaManagerImpl *this,
        struct _GUID *a2,
        int a3,
        struct IUiaEndpointNotifierCallback *a4,
        struct IUiaEndpointRegistrationToken **a5)
{
  __int64 result; // rax
  ULONGLONG *v9; // rbx
  __int64 v10; // rcx
  char *v11; // rax
  char *v12; // rbx
  int v13; // edi
  char *v14; // r14
  struct _GUID v15; // xmm6
  struct IUiaEndpointNotifierCallback *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  const char *v19; // r9
  _QWORD *v20; // rcx
  int v21; // eax
  unsigned int v22; // ebx
  _QWORD *v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  ULONG UserDataCount; // [rsp+20h] [rbp-D8h]
  WINBOOL fPending; // [rsp+30h] [rbp-C8h] BYREF
  _QWORD *v29; // [rsp+38h] [rbp-C0h] BYREF
  int v30; // [rsp+40h] [rbp-B8h]
  EVENT_DESCRIPTOR Context; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-98h] BYREF
  GUID ProviderId; // [rsp+70h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-78h] BYREF
  char *v36; // [rsp+90h] [rbp-68h]
  int v37; // [rsp+98h] [rbp-60h]
  int v38; // [rsp+9Ch] [rbp-5Ch]
  struct _GUID *v39; // [rsp+A0h] [rbp-58h]
  __int64 v40; // [rsp+A8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v30 = a3;
  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x145,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  *(_QWORD *)&Context.Id = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         (LPVOID *)&Context)
    && fPending )
  {
    *(_QWORD *)&Context.Id = &qword_1800C4F30;
    qword_1800C4F38 = 0;
    byte_1800C4F40 = 0;
    dword_1800C4F44 = 0;
    qword_1800C4F30 = (__int64)&UiaManagerTraceLoggingProvider::`vftable';
    CallbackContext = &`UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_::_lambda_invoker_cdecl_);
    v9 = (ULONGLONG *)CallbackContext;
    qword_1800C4F38 = (__int64)CallbackContext;
    byte_1800C4F40 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v9[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v9, v9 + 4) )
      EventSetInformation(v9[4], 2, v9[1], *(unsigned __int16 *)v9[1]);
    dword_1800C4F44 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800C4F30 + 8))(&qword_1800C4F30);
    InitOnceComplete(&`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_1800C4F30);
  }
  v10 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
  if ( *(_DWORD *)v10 > 4u )
  {
    v39 = a2;
    v40 = 16;
    *(_QWORD *)&Context.Id = 0x40B000000LL;
    Context.Keyword = 0;
    UserData.Ptr = *(_QWORD *)(v10 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v36 = byte_1800AD925;
    v37 = 48;
    v38 = 1;
    fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v10 + 32), &Context, 0, 0, 3u, &UserData);
  }
  *a5 = 0;
  v29 = 0;
  v11 = (char *)operator new(0x80u, (const struct std::nothrow_t *)std::nothrow);
  try
  {
    v12 = v11;
    if ( v11 )
    {
      v14 = (char *)this - 48;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v11 + 8));
      *((_QWORD *)v12 + 10) = 1;
      *(_QWORD *)v12 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `IInspectable'};
      *((_QWORD *)v12 + 1) = &UiaEndpointRegistration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'};
      *((_QWORD *)v12 + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `IWeakReferenceSource'};
      *((_QWORD *)v12 + 6) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'};
      *((_QWORD *)v12 + 7) = &UiaEndpointRegistration::`vftable'{for `IUiaEndpointRegistrationToken'};
      *((_QWORD *)v12 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFastRundown>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v12 = &UiaEndpointRegistration::`vftable'{for `IInspectable'};
      *((_QWORD *)v12 + 1) = &UiaEndpointRegistration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'};
      *((_QWORD *)v12 + 5) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `IWeakReferenceSource'};
      *((_QWORD *)v12 + 6) = &UiaEndpointRegistration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'};
      *((_QWORD *)v12 + 7) = &UiaEndpointRegistration::`vftable'{for `IUiaEndpointRegistrationToken'};
      *((_QWORD *)v12 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFastRundown>'};
      *((_QWORD *)v12 + 11) = 0;
      *((_QWORD *)v12 + 12) = 0;
      *(GUID *)(v12 + 104) = GUID_NULL;
      *((_DWORD *)v12 + 30) = -1;
      v15 = *a2;
      v16 = 0;
      if ( this != (UiaManagerImpl *)48 )
      {
        (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))((char *)this - 48);
        v16 = (struct IUiaEndpointNotifierCallback *)*((_QWORD *)v12 + 12);
        v17 = *((_QWORD *)v12 + 11);
        *((_QWORD *)v12 + 11) = v14;
        if ( v17 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v16 = (struct IUiaEndpointNotifierCallback *)*((_QWORD *)v12 + 12);
        }
      }
      *(struct _GUID *)(v12 + 104) = v15;
      *((_DWORD *)v12 + 30) = v30;
      if ( v16 != a4 )
      {
        (*(void (__fastcall **)(struct IUiaEndpointNotifierCallback *))(*(_QWORD *)a4 + 8LL))(a4);
        v18 = *((_QWORD *)v12 + 12);
        *((_QWORD *)v12 + 12) = a4;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      v13 = (**(__int64 (__fastcall ***)(char *, GUID *, _QWORD **))v12)(
              v12,
              &GUID_ecbd746a_88b0_4887_ac8f_92e1407c78fb,
              &v29);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( v13 >= 0 )
      {
        wil::com_weak_query<IUiaWindowNotifierCallback * &>(&v33, &v29);
        ThreadSafeMap<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::Emplace<_GUID &,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>((UiaManagerImpl *)((char *)this + 184));
        ThreadSafeMap<_GUID,std::optional<ProviderEntrypointId>>::Emplace<_GUID &,std::nullopt_t const &>(
          (char *)this + 328,
          a2);
        v21 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IUiaEndpointRegistrationToken **))*v29)(
                v29,
                &GUID_aef4fcfa_4739_406b_9b41_3b5e84c8646a,
                a5);
        v22 = v21;
        if ( v21 >= 0 )
        {
          UiaManagerImpl::GetUiaManagerEndpointStateNotifier((char *)this - 48, &v32);
          ProviderId = *a2;
          v24 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v32 + 24LL))(v32, &ProviderId);
          if ( v24 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x160,
              (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
              (const char *)(unsigned int)v24,
              UserDataCount);
          v25 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          if ( v33 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          v26 = v29;
          if ( v29 )
          {
            v29 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
          }
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x15D,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
            (const char *)(unsigned int)v21,
            UserDataCount);
          if ( v33 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          v23 = v29;
          if ( v29 )
          {
            v29 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          }
          return v22;
        }
      }
    }
    else
    {
      v13 = -2147024882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v13,
      UserDataCount);
    v20 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v20 + 16LL))(v20, *v20);
    }
    result = (unsigned int)v13;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x164,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x1800139a0  mov     [rsp+arg_10], rbx
0x1800139a5  mov     [rsp+arg_18], rsi
0x1800139aa  push    rdi
0x1800139ab  push    r12
0x1800139ad  push    r13
0x1800139af  push    r14
0x1800139b1  push    r15
0x1800139b3  sub     rsp, 0D0h
0x1800139ba  movaps  [rsp+0F8h+var_38], xmm6
0x1800139c2  mov     rax, cs:__security_cookie
0x1800139c9  xor     rax, rsp
0x1800139cc  mov     [rsp+0F8h+var_48], rax
0x1800139d4  mov     rdi, r9
0x1800139d7  mov     [rsp+0F8h+var_B8], r8d
0x1800139dc  mov     rsi, rdx
0x1800139df  mov     r13, rcx
0x1800139e2  mov     r12, [rsp+0F8h+arg_20]
0x1800139ea  xor     r15d, r15d
0x1800139ed  mov     r8d, 10h; Size
0x1800139f3  lea     rdx, GUID_NULL; Buf2
0x1800139fa  mov     rcx, rsi; Buf1
0x1800139fd  call    memcmp_0
0x180013a02  test    eax, eax
0x180013a04  jnz     short loc_180013A2F
0x180013a06  mov     rcx, [rsp+0F8h]; this
0x180013a0e  mov     r9d, 80070057h; char *
0x180013a14  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013a1b  mov     edx, 145h; void *
0x180013a20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a25  mov     eax, 80070057h
0x180013a2a  jmp     loc_180013F89
0x180013a2f  test    rdi, rdi
0x180013a32  jnz     short loc_180013A5D
0x180013a34  mov     rcx, [rsp+0F8h]; this
0x180013a3c  mov     r9d, 80070057h; char *
0x180013a42  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013a49  mov     edx, 146h; void *
0x180013a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a53  mov     eax, 80070057h
0x180013a58  jmp     loc_180013F89
0x180013a5d  test    r12, r12
0x180013a60  jnz     short loc_180013A8B
0x180013a62  mov     rcx, [rsp+0F8h]; this
0x180013a6a  mov     r9d, 80070057h; char *
0x180013a70  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013a77  mov     edx, 147h; void *
0x180013a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013a81  mov     eax, 80070057h
0x180013a86  jmp     loc_180013F89
0x180013a8b  mov     [rsp+0F8h+Context], r15
0x180013a90  mov     [rsp+0F8h+fPending], r15d
0x180013a95  lea     r9, [rsp+0F8h+Context]; lpContext
0x180013a9a  lea     r8, [rsp+0F8h+fPending]; fPending
0x180013a9f  xor     edx, edx; dwFlags
0x180013aa1  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180013aa8  call    cs:__imp___std_init_once_begin_initialize
0x180013aae  test    eax, eax
0x180013ab0  jz      loc_180013BAD
0x180013ab6  cmp     [rsp+0F8h+fPending], 0
0x180013abb  jz      loc_180013BAD
0x180013ac1  lea     rax, qword_1800C4F30
0x180013ac8  mov     [rsp+0F8h+Context], rax
0x180013acd  mov     cs:qword_1800C4F38, r15
0x180013ad4  mov     cs:byte_1800C4F40, 0
0x180013adb  mov     cs:dword_1800C4F44, r15d
0x180013ae2  lea     rax, ??_7UiaManagerTraceLoggingProvider@@6B@; const UiaManagerTraceLoggingProvider::`vftable'
0x180013ae9  mov     cs:qword_1800C4F30, rax
0x180013af0  lea     rax, ?__hInner@?1???0StaticHandle@UiaManagerTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180013af7  mov     cs:CallbackContext, rax
0x180013afe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_@@CA@XZ; void (__cdecl *)()
0x180013b05  call    atexit
0x180013b0a  mov     rbx, cs:CallbackContext
0x180013b11  mov     cs:qword_1800C4F38, rbx
0x180013b18  mov     cs:byte_1800C4F40, 1
0x180013b1f  mov     rax, [rbx+8]
0x180013b23  movups  xmm0, xmmword ptr [rax-10h]
0x180013b27  movups  xmmword ptr [rsp+0F8h+ProviderId.Data1], xmm0
0x180013b2c  cmp     qword ptr [rbx+20h], 0
0x180013b31  jz      short loc_180013B3A
0x180013b33  mov     ecx, 5
0x180013b38  int     29h; Win8: RtlFailFast(ecx)
0x180013b3a  mov     [rbx+28h], r15
0x180013b3e  mov     [rbx+30h], r15
0x180013b42  lea     r9, [rbx+20h]; RegHandle
0x180013b46  mov     r8, rbx; CallbackContext
0x180013b49  lea     rdx, _tlgEnableCallback; EnableCallback
0x180013b50  lea     rcx, [rsp+0F8h+ProviderId]; ProviderId
0x180013b55  call    cs:__imp_EventRegister
0x180013b5b  test    eax, eax
0x180013b5d  jnz     short loc_180013B76
0x180013b5f  mov     r8, [rbx+8]
0x180013b63  movzx   r9d, word ptr [r8]
0x180013b67  mov     edx, 2
0x180013b6c  mov     rcx, [rbx+20h]
0x180013b70  call    cs:__imp_EventSetInformation
0x180013b76  mov     cs:dword_1800C4F44, 1
0x180013b80  mov     rax, cs:qword_1800C4F30
0x180013b87  lea     rcx, qword_1800C4F30
0x180013b8e  mov     rax, [rax+8]
0x180013b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b97  lea     r8, qword_1800C4F30; lpContext
0x180013b9e  xor     edx, edx; dwFlags
0x180013ba0  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180013ba7  call    cs:__imp_InitOnceComplete
0x180013bad  mov     rax, [rsp+0F8h+Context]
0x180013bb2  mov     rcx, [rax+8]
0x180013bb6  mov     eax, [rcx]
0x180013bb8  cmp     eax, 4
0x180013bbb  jbe     loc_180013C75
0x180013bc1  mov     [rsp+0F8h+var_58], rsi
0x180013bc9  mov     [rsp+0F8h+var_50], 10h
0x180013bd5  mov     dword ptr [rsp+0F8h+Context], 0B000000h
0x180013bdd  movzx   eax, cs:word_1800AD91B
0x180013be4  mov     dword ptr [rsp+0F8h+Context+4], eax
0x180013be8  mov     [rsp+0F8h+var_A8], r15
0x180013bed  mov     rax, [rcx+8]
0x180013bf1  mov     [rsp+0F8h+var_78.Ptr], rax
0x180013bf9  movzx   eax, word ptr [rax]
0x180013bfc  mov     [rsp+0F8h+var_78.Size], eax
0x180013c03  mov     dword ptr [rsp+0F8h+var_78.0Ch], 2
0x180013c0e  lea     rax, byte_1800AD925
0x180013c15  mov     [rsp+0F8h+var_68], rax
0x180013c1d  mov     [rsp+0F8h+var_60], 30h ; '0'
0x180013c28  mov     [rsp+0F8h+var_5C], 1
0x180013c33  lea     rax, _TraceLoggingMetadataEnd
0x180013c3a  lea     rdx, _TraceLoggingMetadata
0x180013c41  sub     eax, edx
0x180013c43  mov     [rsp+0F8h+fPending], eax
0x180013c47  mov     eax, [rsp+0F8h+fPending]
0x180013c4b  lea     rax, [rsp+0F8h+var_78]
0x180013c53  mov     [rsp+0F8h+UserData], rax; UserData
0x180013c58  mov     [rsp+0F8h+UserDataCount], 3; int
0x180013c60  xor     r9d, r9d; RelatedActivityId
0x180013c63  xor     r8d, r8d; ActivityId
0x180013c66  lea     rdx, [rsp+0F8h+Context]; EventDescriptor
0x180013c6b  mov     rcx, [rcx+20h]; RegHandle
0x180013c6f  call    cs:__imp_EventWriteTransfer
0x180013c75  mov     [r12], r15
0x180013c79  mov     [rsp+0F8h+var_C0], r15
0x180013c7e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013c85  mov     ecx, 80h; unsigned __int64
0x180013c8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180013c8f  mov     rbx, rax
0x180013c92  test    rax, rax
0x180013c95  jnz     short loc_180013CA1
0x180013c97  mov     edi, 8007000Eh
0x180013c9c  jmp     loc_180013E13
0x180013ca1  lea     r14, [r13-30h]
0x180013ca5  lea     rcx, [rax+8]; this
0x180013ca9  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180013cae  mov     qword ptr [rbx+50h], 1
0x180013cb6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@WRL@Microsoft@@6BIInspectable@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `IInspectable'}
0x180013cbd  mov     [rbx], rax
0x180013cc0  lea     rax, ??_7UiaEndpointRegistration@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@Details@WRL@Microsoft@@@; const UiaEndpointRegistration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'}
0x180013cc7  mov     [rbx+8], rax
0x180013ccb  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `IWeakReferenceSource'}
0x180013cd2  mov     [rbx+28h], rax
0x180013cd6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'}
0x180013cdd  mov     [rbx+30h], rax
0x180013ce1  lea     rax, ??_7UiaEndpointRegistration@@6BIUiaEndpointRegistrationToken@@@; const UiaEndpointRegistration::`vftable'{for `IUiaEndpointRegistrationToken'}
0x180013ce8  mov     [rbx+38h], rax
0x180013cec  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFastRundown>'}
0x180013cf3  mov     [rbx+40h], rax
0x180013cf7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180013cfe  test    rcx, rcx
0x180013d01  jz      short loc_180013D10
0x180013d03  mov     rax, [rcx]
0x180013d06  mov     rax, [rax+8]
0x180013d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d0f  nop
0x180013d10  lea     rax, ??_7UiaEndpointRegistration@@6BIInspectable@@@; const UiaEndpointRegistration::`vftable'{for `IInspectable'}
0x180013d17  mov     [rbx], rax
0x180013d1a  lea     rax, ??_7UiaEndpointRegistration@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIWeakReferenceSource@@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@Details@WRL@Microsoft@@@; const UiaEndpointRegistration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,IWeakReferenceSource,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'}
0x180013d21  mov     [rbx+8], rax
0x180013d25  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `IWeakReferenceSource'}
0x180013d2c  mov     [rbx+28h], rax
0x180013d30  lea     rax, ??_7UiaEndpointRegistration@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@Details@WRL@Microsoft@@@; const UiaEndpointRegistration::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>'}
0x180013d37  mov     [rbx+30h], rax
0x180013d3b  lea     rax, ??_7UiaEndpointRegistration@@6BIUiaEndpointRegistrationToken@@@; const UiaEndpointRegistration::`vftable'{for `IUiaEndpointRegistrationToken'}
0x180013d42  mov     [rbx+38h], rax
0x180013d46  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VFtmBase@23@UIUiaEndpointRegistration@@UIUiaEndpointRegistrationToken@@UIFastRundown@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIFastRundown@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::FtmBase,IUiaEndpointRegistration,IUiaEndpointRegistrationToken,IFastRundown>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFastRundown>'}
0x180013d4d  mov     [rbx+40h], rax
0x180013d51  xor     r15d, r15d
0x180013d54  mov     [rbx+58h], r15
0x180013d58  mov     [rbx+60h], r15
0x180013d5c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180013d63  movups  xmmword ptr [rbx+68h], xmm0
0x180013d67  mov     dword ptr [rbx+78h], 0FFFFFFFFh
0x180013d6e  movups  xmm6, xmmword ptr [rsi]
0x180013d71  mov     eax, r15d
0x180013d74  test    r14, r14
0x180013d77  jz      short loc_180013DA9
0x180013d79  mov     rax, [r14]
0x180013d7c  mov     rcx, r14
0x180013d7f  mov     rax, [rax+8]
0x180013d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d88  mov     rax, [rbx+60h]
0x180013d8c  mov     rcx, [rbx+58h]
0x180013d90  mov     [rbx+58h], r14
0x180013d94  test    rcx, rcx
0x180013d97  jz      short loc_180013DA9
0x180013d99  mov     rax, [rcx]
0x180013d9c  mov     rax, [rax+10h]
0x180013da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da5  mov     rax, [rbx+60h]
0x180013da9  movups  xmmword ptr [rbx+68h], xmm6
0x180013dad  mov     ecx, [rsp+0F8h+var_B8]
0x180013db1  mov     [rbx+78h], ecx
0x180013db4  cmp     rax, rdi
0x180013db7  jz      short loc_180013DE3
0x180013db9  mov     rax, [rdi]
0x180013dbc  mov     rcx, rdi
0x180013dbf  mov     rax, [rax+8]
0x180013dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dc8  nop
0x180013dc9  mov     rcx, [rbx+60h]
0x180013dcd  mov     [rbx+60h], rdi
0x180013dd1  test    rcx, rcx
0x180013dd4  jz      short loc_180013DE3
0x180013dd6  mov     rax, [rcx]
0x180013dd9  mov     rax, [rax+10h]
0x180013ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013de2  nop
0x180013de3  mov     rax, [rbx]
0x180013de6  lea     r8, [rsp+0F8h+var_C0]
0x180013deb  lea     rdx, _GUID_ecbd746a_88b0_4887_ac8f_92e1407c78fb
0x180013df2  mov     rcx, rbx
0x180013df5  mov     rax, [rax]
0x180013df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dfd  mov     edi, eax
0x180013dff  mov     rax, [rbx]
0x180013e02  mov     rcx, rbx
0x180013e05  mov     rax, [rax+10h]
0x180013e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e0e  nop
0x180013e0f  test    edi, edi
0x180013e11  jns     short loc_180013E53
0x180013e13  mov     rcx, [rsp+0F8h]; this
0x180013e1b  mov     r9d, edi; char *
0x180013e1e  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013e25  mov     edx, 154h; void *
0x180013e2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e2f  nop
0x180013e30  mov     rcx, [rsp+0F8h+var_C0]
0x180013e35  test    rcx, rcx
0x180013e38  jz      short loc_180013E4C
0x180013e3a  mov     [rsp+0F8h+var_C0], r15
0x180013e3f  mov     rdx, [rcx]
0x180013e42  mov     rax, [rdx+10h]
0x180013e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e4b  nop
0x180013e4c  mov     eax, edi
0x180013e4e  jmp     loc_180013F89
0x180013e53  lea     rdx, [rsp+0F8h+var_C0]
0x180013e58  lea     rcx, [rsp+0F8h+var_98]
0x180013e5d  call    ??$com_weak_query@AEAPEAUIUiaWindowNotifierCallback@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@AEAPEAUIUiaWindowNotifierCallback@@@Z; wil::com_weak_query<IUiaWindowNotifierCallback * &>(IUiaWindowNotifierCallback * &)
0x180013e62  nop
0x180013e63  lea     rcx, [r13+0B8h]; this
0x180013e6a  lea     r8, [rsp+0F8h+var_98]
0x180013e6f  mov     rdx, rsi
0x180013e72  call    ??$Emplace@AEAU_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@?$ThreadSafeMap@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@QEAAXAEAU_GUID@@$$QEAV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@Z; ThreadSafeMap<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::Emplace<_GUID &,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>(_GUID &,wil::com_ptr_t<IWeakReference,wil::err_exception_policy> &&)
0x180013e77  lea     rcx, [r13+148h]
0x180013e7e  mov     rdx, rsi
0x180013e81  call    ??$Emplace@AEAU_GUID@@AEBUnullopt_t@std@@@?$ThreadSafeMap@U_GUID@@V?$optional@VProviderEntrypointId@@@std@@@@QEAAXAEAU_GUID@@AEBUnullopt_t@std@@@Z; ThreadSafeMap<_GUID,std::optional<ProviderEntrypointId>>::Emplace<_GUID &,std::nullopt_t const &>(_GUID &,std::nullopt_t const &)
0x180013e86  nop
0x180013e87  mov     rcx, [rsp+0F8h+var_C0]
0x180013e8c  mov     rax, [rcx]
0x180013e8f  mov     r8, r12
0x180013e92  lea     rdx, _GUID_aef4fcfa_4739_406b_9b41_3b5e84c8646a
0x180013e99  mov     rax, [rax]
0x180013e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ea1  mov     ebx, eax
0x180013ea3  test    eax, eax
0x180013ea5  jns     short loc_180013EFE
0x180013ea7  mov     rcx, [rsp+0F8h]; this
0x180013eaf  mov     r9d, eax; char *
0x180013eb2  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013eb9  mov     edx, 15Dh; void *
0x180013ebe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ec3  nop
0x180013ec4  mov     rcx, [rsp+0F8h+var_98]
0x180013ec9  test    rcx, rcx
0x180013ecc  jz      short loc_180013EDB
0x180013ece  mov     rax, [rcx]
0x180013ed1  mov     rax, [rax+10h]
0x180013ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eda  nop
0x180013edb  mov     rcx, [rsp+0F8h+var_C0]
0x180013ee0  test    rcx, rcx
0x180013ee3  jz      short loc_180013EF7
0x180013ee5  mov     [rsp+0F8h+var_C0], r15
0x180013eea  mov     rax, [rcx]
0x180013eed  mov     rax, [rax+10h]
0x180013ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ef6  nop
0x180013ef7  mov     eax, ebx
0x180013ef9  jmp     loc_180013F89
0x180013efe  lea     rdx, [rsp+0F8h+var_A0]
0x180013f03  mov     rcx, r14
0x180013f06  call    ?GetUiaManagerEndpointStateNotifier@UiaManagerImpl@@AEAA?AV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@XZ; UiaManagerImpl::GetUiaManagerEndpointStateNotifier(void)
  ... truncated ...
```
