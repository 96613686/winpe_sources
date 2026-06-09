# CRuntimeBroker::CreateLogoffWatcher(Windows::System::IUserWatcher * *,EventRegistrationToken *)

- ea: `0x140006580`
- end: `0x14000683b`
- name: `?CreateLogoffWatcher@CRuntimeBroker@@CAJPEAPEAUIUserWatcher@System@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(struct Windows::System::IUserWatcher **, struct EventRegistrationToken *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006260`

## callees

- `0x1400027ac`
- `0x140006580`
- `0x1400068e8`
- `0x140008c80`
- `0x14000a250`
- `0x14000bb9c`
- `0x14000c4d0`
- `0x140010010`

## import_xrefs

- `ntdll!RtlIsMultiSessionSku` at `0x1400065b0`
- `ntdll!RtlIsMultiSessionSku` at `0x1400065b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000664c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000664c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140006635`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140006635`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140006662`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140006662`

## string_xrefs

- `0x1400065f3`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x140006672`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x1400066dc`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x140006743`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x1400067a7`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::CreateLogoffWatcher(
        struct Windows::System::IUserWatcher **a1,
        struct EventRegistrationToken *a2)
{
  int IsDefaultUserProcess; // eax
  unsigned int v6; // edi
  HRESULT v7; // eax
  int ActivationFactory; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, struct Windows::System::IUserWatcher **); // rdi
  int v13; // eax
  __int64 v14; // rcx
  __int64 *v15; // rax
  __int64 v16; // rdi
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // esi
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // [rsp+20h] [rbp-50h] BYREF
  __int64 v23; // [rsp+28h] [rbp-48h] BYREF
  struct Windows::System::IUserWatcher *v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  __int64 v26; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  *a1 = 0;
  a2->value = 0;
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
    return 0;
  LOBYTE(v22) = 0;
  IsDefaultUserProcess = CRuntimeBroker::IsDefaultUserProcess((bool *)&v22);
  v6 = IsDefaultUserProcess;
  if ( IsDefaultUserProcess < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x428,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)(unsigned int)IsDefaultUserProcess,
      v22);
    return v6;
  }
  if ( (_BYTE)v22 )
    return 0;
  v24 = 0;
  v26 = 0;
  v23 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.System.User", 0x13u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    RaiseException(v7, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd, &v23);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42F,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v22);
    v10 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    return v9;
  }
  v11 = v23;
  v12 = *(__int64 (__fastcall **)(__int64, struct Windows::System::IUserWatcher **))(*(_QWORD *)v23 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v13 = v12(v11, &v24);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x430,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)(unsigned int)v13,
      v22);
    v14 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_11;
  }
  v15 = (__int64 *)Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_>(&v25);
  v16 = *v15;
  *v15 = 0;
  if ( v25 )
  {
    v25 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::Release();
  }
  if ( v16 )
  {
    v18 = (*(__int64 (__fastcall **)(struct Windows::System::IUserWatcher *, __int64, __int64 *))(*(_QWORD *)v24 + 88LL))(
            v24,
            v16,
            &v26);
    v19 = v18;
    if ( v18 >= 0 )
    {
      *a1 = v24;
      a2->value = v26;
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v21 = v23;
      if ( v23 )
      {
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44A,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)(unsigned int)v18,
      v22);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v20 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    return v19;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x446,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)0x8007000ELL,
      v22);
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140006580  mov     [rsp-28h+arg_10], rbx
0x140006585  push    rbp
0x140006586  push    rsi
0x140006587  push    rdi
0x140006588  push    r14
0x14000658a  push    r15
0x14000658c  mov     rbp, rsp
0x14000658f  sub     rsp, 70h
0x140006593  mov     rax, cs:__security_cookie
0x14000659a  xor     rax, rsp
0x14000659d  mov     [rbp+var_8], rax
0x1400065a1  xor     r15d, r15d
0x1400065a4  mov     rbx, rdx
0x1400065a7  mov     [rcx], r15
0x1400065aa  mov     r14, rcx
0x1400065ad  mov     [rdx], r15
0x1400065b0  call    cs:__imp_RtlIsMultiSessionSku
0x1400065b6  test    al, al
0x1400065b8  jz      short loc_1400065DC
0x1400065ba  xor     eax, eax
0x1400065bc  mov     rcx, [rbp+var_8]
0x1400065c0  xor     rcx, rsp; StackCookie
0x1400065c3  call    __security_check_cookie
0x1400065c8  mov     rbx, [rsp+70h+arg_10]
0x1400065d0  add     rsp, 70h
0x1400065d4  pop     r15
0x1400065d6  pop     r14
0x1400065d8  pop     rdi
0x1400065d9  pop     rsi
0x1400065da  pop     rbp
0x1400065db  retn
0x1400065dc  lea     rcx, [rbp+var_50]; bool *
0x1400065e0  mov     byte ptr [rbp+var_50], r15b
0x1400065e4  call    ?IsDefaultUserProcess@CRuntimeBroker@@SAJPEA_N@Z; CRuntimeBroker::IsDefaultUserProcess(bool *)
0x1400065e9  mov     edi, eax
0x1400065eb  test    eax, eax
0x1400065ed  jns     short loc_14000660B
0x1400065ef  mov     rcx, [rbp+28h]; this
0x1400065f3  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x1400065fa  mov     r9d, eax; char *
0x1400065fd  mov     edx, 428h; void *
0x140006602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006607  mov     eax, edi
0x140006609  jmp     short loc_1400065BC
0x14000660b  cmp     byte ptr [rbp+var_50], r15b
0x14000660f  jnz     short loc_1400065BA
0x140006611  lea     r9, [rbp+string]; string
0x140006615  mov     [rbp+var_40], r15
0x140006619  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000661d  mov     [rbp+var_30], r15
0x140006621  mov     edx, 13h; length
0x140006626  mov     [rbp+var_48], r15
0x14000662a  lea     rcx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x140006631  mov     [rbp+string], r15
0x140006635  call    cs:__imp_WindowsCreateStringReference
0x14000663b  test    eax, eax
0x14000663d  jns     short loc_140006653
0x14000663f  xor     r9d, r9d; lpArguments
0x140006642  xor     r8d, r8d; nNumberOfArguments
0x140006645  mov     edx, 1; dwExceptionFlags
0x14000664a  mov     ecx, eax; dwExceptionCode
0x14000664c  call    cs:__imp_RaiseException
0x140006652  int     3; Trap to Debugger
0x140006653  mov     rcx, [rbp+string]
0x140006657  lea     r8, [rbp+var_48]
0x14000665b  lea     rdx, _GUID_155eb23b_242a_45e0_a2e9_3171fc6a7fdd
0x140006662  call    cs:__imp_RoGetActivationFactory
0x140006668  mov     edi, eax
0x14000666a  test    eax, eax
0x14000666c  jns     short loc_1400066AF
0x14000666e  mov     rcx, [rbp+28h]; this
0x140006672  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x140006679  mov     r9d, eax; char *
0x14000667c  mov     edx, 42Fh; void *
0x140006681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006686  mov     rcx, [rbp+var_48]
0x14000668a  test    rcx, rcx
0x14000668d  jz      short loc_14000669F
0x14000668f  mov     [rbp+var_48], r15
0x140006693  mov     rax, [rcx]
0x140006696  mov     rax, [rax+10h]
0x14000669a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000669f  lea     rcx, [rbp+var_40]
0x1400066a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400066a8  mov     eax, edi
0x1400066aa  jmp     loc_1400065BC
0x1400066af  mov     rsi, [rbp+var_48]
0x1400066b3  lea     rcx, [rbp+var_40]
0x1400066b7  mov     rax, [rsi]
0x1400066ba  mov     rdi, [rax+30h]
0x1400066be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400066c3  lea     rdx, [rbp+var_40]
0x1400066c7  mov     rcx, rsi
0x1400066ca  mov     rax, rdi
0x1400066cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066d2  mov     edi, eax
0x1400066d4  test    eax, eax
0x1400066d6  jns     short loc_140006719
0x1400066d8  mov     rcx, [rbp+28h]; this
0x1400066dc  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x1400066e3  mov     r9d, eax; char *
0x1400066e6  mov     edx, 430h; void *
0x1400066eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400066f0  mov     rcx, [rbp+var_48]
0x1400066f4  test    rcx, rcx
0x1400066f7  jz      short loc_140006709
0x1400066f9  mov     [rbp+var_48], r15
0x1400066fd  mov     rax, [rcx]
0x140006700  mov     rax, [rax+10h]
0x140006704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006709  lea     rcx, [rbp+var_40]
0x14000670d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140006712  mov     eax, edi
0x140006714  jmp     loc_1400065BC
0x140006719  lea     rcx, [rbp+var_38]
0x14000671d  call    ??$Make@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@@12@$$QEAV_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>,_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_>(_lambda_ff67e1dbbd64ec80e0b69245dd48b71a_ &&)
0x140006722  mov     rdi, [rax]
0x140006725  mov     [rax], r15
0x140006728  mov     rcx, [rbp+var_38]
0x14000672c  test    rcx, rcx
0x14000672f  jz      short loc_14000673A
0x140006731  mov     [rbp+var_38], r15
0x140006735  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>>::Release(void)
0x14000673a  test    rdi, rdi
0x14000673d  jnz     short loc_140006786
0x14000673f  mov     rcx, [rbp+28h]; this
0x140006743  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x14000674a  mov     r9d, 8007000Eh; char *
0x140006750  mov     edx, 446h; void *
0x140006755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000675a  mov     rcx, [rbp+var_48]
0x14000675e  test    rcx, rcx
0x140006761  jz      short loc_140006773
0x140006763  mov     [rbp+var_48], r15
0x140006767  mov     rdx, [rcx]
0x14000676a  mov     rax, [rdx+10h]
0x14000676e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006773  lea     rcx, [rbp+var_40]
0x140006777  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000677c  mov     eax, 8007000Eh
0x140006781  jmp     loc_1400065BC
0x140006786  mov     rcx, [rbp+var_40]
0x14000678a  lea     r8, [rbp+var_30]
0x14000678e  mov     rdx, rdi
0x140006791  mov     rax, [rcx]
0x140006794  mov     rax, [rax+58h]
0x140006798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000679d  mov     esi, eax
0x14000679f  test    eax, eax
0x1400067a1  jns     short loc_1400067F3
0x1400067a3  mov     rcx, [rbp+28h]; this
0x1400067a7  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x1400067ae  mov     r9d, eax; char *
0x1400067b1  mov     edx, 44Ah; void *
0x1400067b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400067bb  mov     rdx, [rdi]
0x1400067be  mov     rcx, rdi
0x1400067c1  mov     rax, [rdx+10h]
0x1400067c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067ca  mov     rcx, [rbp+var_48]
0x1400067ce  test    rcx, rcx
0x1400067d1  jz      short loc_1400067E3
0x1400067d3  mov     [rbp+var_48], r15
0x1400067d7  mov     rax, [rcx]
0x1400067da  mov     rax, [rax+10h]
0x1400067de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400067e3  lea     rcx, [rbp+var_40]
0x1400067e7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400067ec  mov     eax, esi
0x1400067ee  jmp     loc_1400065BC
0x1400067f3  mov     rax, [rbp+var_40]
0x1400067f7  mov     rcx, rdi
0x1400067fa  mov     [r14], rax
0x1400067fd  mov     rax, [rbp+var_30]
0x140006801  mov     [rbx], rax
0x140006804  mov     [rbp+var_40], r15
0x140006808  mov     rax, [rdi]
0x14000680b  mov     rax, [rax+10h]
0x14000680f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006814  mov     rcx, [rbp+var_48]
0x140006818  test    rcx, rcx
0x14000681b  jz      short loc_14000682D
0x14000681d  mov     [rbp+var_48], r15
0x140006821  mov     rax, [rcx]
0x140006824  mov     rax, [rax+10h]
0x140006828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000682d  lea     rcx, [rbp+var_40]
0x140006831  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140006836  jmp     loc_1400065BA
```
