# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::RuntimeClassInitialize(unsigned __int64)

- ea: `0x180016198`
- end: `0x180016431`
- name: `?RuntimeClassInitialize@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@QEAAJ_K@Z`
- size: `665`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009414`

## callees

- `0x180006eac`
- `0x180007fe8`
- `0x180008128`
- `0x180008778`
- `0x18000c2ac`
- `0x18000e87c`
- `0x180011ffc`
- `0x180015fd4`
- `0x180016198`
- `0x180019e0c`
- `0x180040384`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800163a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800163a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800163bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800163bb`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180016350`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180016350`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016304`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180016304`

## string_xrefs

- `0x1800162db`: `Windows.Internal.ApplicationModel.Sync.TokenBrokerHelper`
- `0x180016209`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800163e5`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::RuntimeClassInitialize(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        __int64 a2)
{
  int ActivationFactory; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rbx
  HRESULT v8; // eax
  HANDLE CurrentThread; // rax
  __int64 v10; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v13 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AccountsControl", 0x10u, 0xFu);
  ActivationFactory = ViewOperationBase::Initialize((char *)this + 32, v13, 0, a2);
  if ( ActivationFactory >= 0 )
  {
    v13 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.UI.ApplicationSettings.AccountsControlData",
      0x3Cu,
      0x3Bu);
    ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsControlData>>(
                          v13,
                          (char *)this + 624);
    if ( ActivationFactory < 0 )
    {
      v5 = 75;
      goto LABEL_3;
    }
    v13 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.PropertySet",
      0x2Bu,
      0x2Au);
    ActivationFactory = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
                          v13,
                          (char *)this + 1008);
    if ( ActivationFactory < 0 )
    {
      v5 = 78;
      goto LABEL_3;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1024);
    ActivationFactory = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::UI::ApplicationSettings::BubbleHeadData,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>,0>>(
                          v6,
                          (char *)this + 1024);
    if ( ActivationFactory < 0 )
    {
      v5 = 79;
      goto LABEL_3;
    }
    v13 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.ApplicationModel.Sync.TokenBrokerHelper",
      0x39u,
      0x38u);
    v7 = v13;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 1032);
    ActivationFactory = RoGetActivationFactory(v7, &GUID_ffdc74d2_20a3_47d4_9a79_4fc26fb0fca4, (char *)this + 1032);
    if ( ActivationFactory < 0 )
    {
      v5 = 82;
      goto LABEL_3;
    }
    *((_QWORD *)this + 79) = a2;
    *((GUID *)this + 62) = GUID_NULL;
    hstringHeader.Reserved.Reserved2[0] = 0;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
    v8 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, (void **)&hstringHeader.Reserved.Reserved2[8]);
    ActivationFactory = v8;
    if ( v8 == -2147417833 )
      goto LABEL_17;
    if ( v8 )
    {
      if ( v8 >= 0 )
      {
LABEL_17:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 1040,
          0);
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0xCu, 1, (PHANDLE)this + 130)
          || (ActivationFactory = ResultFromKnownLastError(), (int)(ActivationFactory + 0x80000000) < 0)
          || ActivationFactory == -2147023888 )
        {
          ActivationFactory = 0;
          goto LABEL_25;
        }
        v10 = 93;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)ActivationFactory,
          (int)hstringHeader.Reserved.Reserved1);
LABEL_25:
        CImpersonateCaller::~CImpersonateCaller((CImpersonateCaller *)&hstringHeader);
        return (unsigned int)ActivationFactory;
      }
    }
    else
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)&hstringHeader.Reserved.Reserved2[8] + 48LL))(*(_QWORD *)&hstringHeader.Reserved.Reserved2[8]) )
        goto LABEL_17;
      ActivationFactory = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&hstringHeader.Reserved.Reserved2[8] + 32LL))(*(_QWORD *)&hstringHeader.Reserved.Reserved2[8]);
      if ( ActivationFactory >= 0 )
      {
        hstringHeader.Reserved.Reserved2[0] = 1;
        goto LABEL_17;
      }
    }
    v10 = 89;
    goto LABEL_21;
  }
  v5 = 72;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)(unsigned int)ActivationFactory,
    (int)hstringHeader.Reserved.Reserved1);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180016198  mov     [rsp-18h+arg_10], rbx
0x18001619d  mov     [rsp-18h+arg_18], rsi
0x1800161a2  push    rbp
0x1800161a3  push    rdi
0x1800161a4  push    r14
0x1800161a6  mov     rbp, rsp
0x1800161a9  sub     rsp, 50h
0x1800161ad  mov     rax, cs:__security_cookie
0x1800161b4  xor     rax, rsp
0x1800161b7  mov     [rbp+var_10], rax
0x1800161bb  mov     r14, rdx
0x1800161be  mov     rsi, rcx
0x1800161c1  mov     [rbp+var_18], 0
0x1800161c9  mov     r9d, 0Fh; unsigned int
0x1800161cf  lea     r8d, [r9+1]; unsigned int
0x1800161d3  lea     rdx, aAccountscontro_0; "AccountsControl"
0x1800161da  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800161de  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800161e3  nop
0x1800161e4  lea     rcx, [rsi+20h]
0x1800161e8  mov     r9, r14
0x1800161eb  xor     r8d, r8d
0x1800161ee  mov     rdx, [rbp+var_18]
0x1800161f2  call    ?Initialize@ViewOperationBase@@IEAAJPEAUHSTRING__@@W4AccountsControlContextType@ApplicationSettings@UI@Internal@Windows@@_K@Z; ViewOperationBase::Initialize(HSTRING__ *,Windows::Internal::UI::ApplicationSettings::AccountsControlContextType,unsigned __int64)
0x1800161f7  mov     ebx, eax
0x1800161f9  test    eax, eax
0x1800161fb  jns     short loc_18001621A
0x1800161fd  mov     edx, 48h ; 'H'; void *
0x180016202  mov     rcx, [rbp+18h]; this
0x180016206  mov     r9d, ebx; char *
0x180016209  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180016210  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016215  jmp     loc_18001640E
0x18001621a  mov     [rbp+var_18], 0
0x180016222  mov     r9d, 3Bh ; ';'; unsigned int
0x180016228  lea     r8d, [r9+1]; unsigned int
0x18001622c  lea     rdx, ?RuntimeClass_Windows_Internal_UI_ApplicationSettings_AccountsControlData@@3QBGB; "Windows.Internal.UI.ApplicationSettings"...
0x180016233  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180016237  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001623c  lea     rdx, [rsi+270h]
0x180016243  mov     rcx, [rbp+var_18]
0x180016247  call    ??$ActivateInstance@V?$ComPtr@UIAccountsControlData@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAccountsControlData@ApplicationSettings@UI@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsControlData>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::ApplicationSettings::IAccountsControlData>>)
0x18001624c  mov     ebx, eax
0x18001624e  test    eax, eax
0x180016250  jns     short loc_180016259
0x180016252  mov     edx, 4Bh ; 'K'
0x180016257  jmp     short loc_180016202
0x180016259  mov     [rbp+var_18], 0
0x180016261  mov     r9d, 2Ah ; '*'; unsigned int
0x180016267  lea     r8d, [r9+1]; unsigned int
0x18001626b  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180016272  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180016276  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001627b  lea     rdx, [rsi+3F0h]
0x180016282  mov     rcx, [rbp+var_18]
0x180016286  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18001628b  mov     ebx, eax
0x18001628d  test    eax, eax
0x18001628f  jns     short loc_18001629B
0x180016291  mov     edx, 4Eh ; 'N'
0x180016296  jmp     loc_180016202
0x18001629b  lea     rbx, [rsi+400h]
0x1800162a2  mov     rcx, rbx
0x1800162a5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800162aa  mov     rdx, rbx
0x1800162ad  call    ??$CreateExternalObjectVector@VBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@V?$AgileVector@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVBubbleHeadData@ApplicationSettings@UI@Internal@Windows@@@4785@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::UI::ApplicationSettings::BubbleHeadData,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::UI::ApplicationSettings::BubbleHeadData *>,0> * *)
0x1800162b2  mov     ebx, eax
0x1800162b4  test    eax, eax
0x1800162b6  jns     short loc_1800162C2
0x1800162b8  mov     edx, 4Fh ; 'O'
0x1800162bd  jmp     loc_180016202
0x1800162c2  lea     rdi, [rsi+408h]
0x1800162c9  mov     [rbp+var_18], 0
0x1800162d1  mov     r9d, 38h ; '8'; unsigned int
0x1800162d7  lea     r8d, [r9+1]; unsigned int
0x1800162db  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationModel_Sync_TokenBrokerHelper@@3QBGB; "Windows.Internal.ApplicationModel.Sync."...
0x1800162e2  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800162e6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800162eb  mov     rbx, [rbp+var_18]
0x1800162ef  mov     rcx, rdi
0x1800162f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800162f7  mov     r8, rdi
0x1800162fa  lea     rdx, _GUID_ffdc74d2_20a3_47d4_9a79_4fc26fb0fca4
0x180016301  mov     rcx, rbx
0x180016304  call    cs:__imp_RoGetActivationFactory
0x18001630a  mov     ebx, eax
0x18001630c  test    eax, eax
0x18001630e  jns     short loc_18001631A
0x180016310  mov     edx, 52h ; 'R'
0x180016315  jmp     loc_180016202
0x18001631a  mov     [rsi+278h], r14
0x180016321  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180016328  movdqu  xmmword ptr [rsi+3E0h], xmm0
0x180016330  mov     byte ptr [rbp+hstringHeader.Reserved], 0
0x180016334  mov     qword ptr [rbp+hstringHeader.Reserved+8], 0
0x18001633c  lea     rcx, [rbp+hstringHeader.Reserved+8]
0x180016340  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180016345  lea     rdx, [rbp+hstringHeader.Reserved+8]; ppInterface
0x180016349  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x180016350  call    cs:__imp_CoGetCallContext
0x180016356  mov     ebx, eax
0x180016358  cmp     eax, 80010117h
0x18001635d  jz      short loc_180016395
0x18001635f  test    eax, eax
0x180016361  jnz     loc_1800163FA
0x180016367  mov     rcx, qword ptr [rbp+hstringHeader.Reserved+8]
0x18001636b  mov     rax, [rcx]
0x18001636e  mov     rax, [rax+30h]
0x180016372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016377  test    eax, eax
0x180016379  jnz     short loc_180016395
0x18001637b  mov     rcx, qword ptr [rbp+hstringHeader.Reserved+8]
0x18001637f  mov     rax, [rcx]
0x180016382  mov     rax, [rax+20h]
0x180016386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001638b  mov     ebx, eax
0x18001638d  test    eax, eax
0x18001638f  js      short loc_1800163FC
0x180016391  mov     byte ptr [rbp+hstringHeader.Reserved], 1
0x180016395  lea     rbx, [rsi+410h]
0x18001639c  xor     edx, edx
0x18001639e  mov     rcx, rbx
0x1800163a1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800163a6  call    cs:__imp_GetCurrentThread
0x1800163ac  mov     r9, rbx; TokenHandle
0x1800163af  mov     edx, 0Ch; DesiredAccess
0x1800163b4  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x1800163b8  mov     rcx, rax; ThreadHandle
0x1800163bb  call    cs:__imp_OpenThreadToken
0x1800163c1  test    eax, eax
0x1800163c3  jnz     short loc_180016403
0x1800163c5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800163ca  mov     ebx, eax
0x1800163cc  mov     eax, 80000000h
0x1800163d1  lea     ecx, [rbx+rax]
0x1800163d4  test    eax, ecx
0x1800163d6  jnz     short loc_180016403
0x1800163d8  cmp     ebx, 800703F0h
0x1800163de  jz      short loc_180016403
0x1800163e0  mov     edx, 5Dh ; ']'; void *
0x1800163e5  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800163ec  mov     r9d, ebx; char *
0x1800163ef  mov     rcx, [rbp+18h]; this
0x1800163f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163f8  jmp     short loc_180016405
0x1800163fa  jns     short loc_180016395
0x1800163fc  mov     edx, 59h ; 'Y'
0x180016401  jmp     short loc_1800163E5
0x180016403  xor     ebx, ebx
0x180016405  lea     rcx, [rbp+hstringHeader]; this
0x180016409  call    ??1CImpersonateCaller@@QEAA@XZ; CImpersonateCaller::~CImpersonateCaller(void)
0x18001640e  mov     eax, ebx
0x180016410  mov     rcx, [rbp+var_10]
0x180016414  xor     rcx, rsp; StackCookie
0x180016417  call    __security_check_cookie
0x18001641c  lea     r11, [rsp+50h+var_s0]
0x180016421  mov     rbx, [r11+30h]
0x180016425  mov     rsi, [r11+38h]
0x180016429  mov     rsp, r11
0x18001642c  pop     r14
0x18001642e  pop     rdi
0x18001642f  pop     rbp
0x180016430  retn
```
