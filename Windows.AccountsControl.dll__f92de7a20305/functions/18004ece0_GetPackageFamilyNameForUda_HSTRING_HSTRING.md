# GetPackageFamilyNameForUda(HSTRING__ *,HSTRING__ * *)

- ea: `0x18004ece0`
- end: `0x18004ef94`
- name: `?GetPackageFamilyNameForUda@@YAJPEAUHSTRING__@@PEAPEAU1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f028`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x18004e2d0`
- `0x18004e460`
- `0x18004ece0`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ed55`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ed55`

## string_xrefs

- `0x18004ed68`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004edb8`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004ee61`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004eee7`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`
- `0x18004ef43`: `onecoreuap\shell\accountscontrol\api\mailcontactscalendarsyncuiapilib\appextensionhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetPackageFamilyNameForUda(HSTRING a1, HSTRING *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // rdi
  int v14; // eax
  __int64 v15; // rdi
  int v16; // eax
  unsigned __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v20; // [rsp+20h] [rbp-50h] BYREF
  __int64 v21; // [rsp+28h] [rbp-48h] BYREF
  __int64 v22; // [rsp+30h] [rbp-40h] BYREF
  __int64 v23; // [rsp+38h] [rbp-38h] BYREF
  __int64 v24; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v26; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a2 = 0;
  v24 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.UserDataAccounts.UserDataAccountManager",
    0x41u,
    0x40u);
  v4 = v26;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_0d9b89ea_1928_4a20_86d5_3c737f7dc3b0, &v24);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v20 = 0;
    v7 = v24;
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v9 = v8(v7, 0, &v20);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
        (const char *)(unsigned int)v9,
        v20);
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      goto LABEL_24;
    }
    v21 = 0;
    v10 = v20;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(v10);
    if ( v6 < 0 || (v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 64LL))(v10, &v21), v6 < 0) )
    {
      v12 = 120;
    }
    else
    {
      v11 = v21;
      if ( v21 )
      {
        v22 = 0;
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v21 + 56LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        v14 = v13(v11, a1, &v22);
        v6 = v14;
        if ( v14 >= 0 )
        {
          v23 = 0;
          v15 = v22;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
          v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccount *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccount *>>(v15);
          if ( v6 < 0
            || (v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, &v23), v6 < 0) )
          {
            v17 = (unsigned int)v6;
            v18 = 129;
          }
          else
          {
            if ( !v23
              || (v16 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 104LL))(v23, a2),
                  v6 = v16,
                  v16 >= 0) )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
              v6 = 0;
              goto LABEL_24;
            }
            v17 = (unsigned int)v16;
            v18 = 132;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
            (const char *)v17,
            v20);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7E,
            (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
            (const char *)(unsigned int)v14,
            v20);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        goto LABEL_22;
      }
      v6 = -2147024891;
      v12 = 123;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
      (const char *)(unsigned int)v6,
      v20);
LABEL_22:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\appextensionhelpers.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v20);
LABEL_24:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004ece0  mov     [rsp-18h+arg_10], rbx
0x18004ece5  mov     [rsp-18h+arg_18], rsi
0x18004ecea  push    rbp
0x18004eceb  push    rdi
0x18004ecec  push    r14
0x18004ecee  mov     rbp, rsp
0x18004ecf1  sub     rsp, 70h
0x18004ecf5  mov     rax, cs:__security_cookie
0x18004ecfc  xor     rax, rsp
0x18004ecff  mov     [rbp+var_8], rax
0x18004ed03  mov     rsi, rdx
0x18004ed06  mov     r14, rcx
0x18004ed09  mov     qword ptr [rdx], 0
0x18004ed10  mov     [rbp+var_30], 0
0x18004ed18  mov     [rbp+var_10], 0
0x18004ed20  mov     r9d, 40h ; '@'; unsigned int
0x18004ed26  lea     r8d, [r9+1]; unsigned int
0x18004ed2a  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_UserDataAccounts_UserDataAccountManager@@3QBGB; "Windows.ApplicationModel.UserDataAccoun"...
0x18004ed31  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004ed35  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004ed3a  mov     rbx, [rbp+var_10]
0x18004ed3e  lea     rcx, [rbp+var_30]
0x18004ed42  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ed47  lea     r8, [rbp+var_30]
0x18004ed4b  lea     rdx, _GUID_0d9b89ea_1928_4a20_86d5_3c737f7dc3b0
0x18004ed52  mov     rcx, rbx
0x18004ed55  call    cs:__imp_RoGetActivationFactory
0x18004ed5b  mov     ebx, eax
0x18004ed5d  test    eax, eax
0x18004ed5f  jns     short loc_18004ED7E
0x18004ed61  mov     rcx, [rbp+18h]; this
0x18004ed65  mov     r9d, eax; char *
0x18004ed68  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004ed6f  mov     edx, 72h ; 'r'; void *
0x18004ed74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ed79  jmp     loc_18004EF68
0x18004ed7e  mov     [rbp+var_50], 0
0x18004ed86  mov     rdi, [rbp+var_30]
0x18004ed8a  mov     rax, [rdi]
0x18004ed8d  mov     rbx, [rax+30h]
0x18004ed91  lea     rcx, [rbp+var_50]
0x18004ed95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ed9a  lea     r8, [rbp+var_50]
0x18004ed9e  xor     edx, edx
0x18004eda0  mov     rcx, rdi
0x18004eda3  mov     rax, rbx
0x18004eda6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004edab  mov     ebx, eax
0x18004edad  test    eax, eax
0x18004edaf  jns     short loc_18004EDCE
0x18004edb1  mov     rcx, [rbp+18h]; this
0x18004edb5  mov     r9d, eax; char *
0x18004edb8  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004edbf  mov     edx, 75h ; 'u'; void *
0x18004edc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004edc9  jmp     loc_18004EF5E
0x18004edce  mov     [rbp+var_48], 0
0x18004edd6  mov     rdi, [rbp+var_50]
0x18004edda  lea     rcx, [rbp+var_48]
0x18004edde  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ede3  mov     rcx, rdi
0x18004ede6  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserDataAccountStore@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccountStore *> *,tagCOWAIT_FLAGS,void *)
0x18004edeb  mov     ebx, eax
0x18004eded  test    eax, eax
0x18004edef  js      loc_18004EF3B
0x18004edf5  mov     rax, [rdi]
0x18004edf8  lea     rdx, [rbp+var_48]
0x18004edfc  mov     rcx, rdi
0x18004edff  mov     rax, [rax+40h]
0x18004ee03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee08  mov     ebx, eax
0x18004ee0a  test    eax, eax
0x18004ee0c  js      loc_18004EF3B
0x18004ee12  mov     rbx, [rbp+var_48]
0x18004ee16  test    rbx, rbx
0x18004ee19  jnz     short loc_18004EE2A
0x18004ee1b  mov     ebx, 80070005h
0x18004ee20  mov     edx, 7Bh ; '{'
0x18004ee25  jmp     loc_18004EF40
0x18004ee2a  mov     [rbp+var_40], 0
0x18004ee32  mov     rax, [rbx]
0x18004ee35  mov     rdi, [rax+38h]
0x18004ee39  lea     rcx, [rbp+var_40]
0x18004ee3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ee42  lea     r8, [rbp+var_40]
0x18004ee46  mov     rdx, r14
0x18004ee49  mov     rcx, rbx
0x18004ee4c  mov     rax, rdi
0x18004ee4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee54  mov     ebx, eax
0x18004ee56  test    eax, eax
0x18004ee58  jns     short loc_18004EE81
0x18004ee5a  mov     rcx, [rbp+18h]; this
0x18004ee5e  mov     r9d, eax; char *
0x18004ee61  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004ee68  mov     edx, 7Eh ; '~'; void *
0x18004ee6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ee72  nop
0x18004ee73  lea     rcx, [rbp+var_40]
0x18004ee77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ee7c  jmp     loc_18004EF54
0x18004ee81  mov     [rbp+var_38], 0
0x18004ee89  mov     rdi, [rbp+var_40]
0x18004ee8d  lea     rcx, [rbp+var_38]
0x18004ee91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ee96  mov     rcx, rdi
0x18004ee99  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVUserDataAccount@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVUserDataAccount@UserDataAccounts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVUserDataAccount@UserDataAccounts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::UserDataAccounts::UserDataAccount *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccount *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::UserDataAccounts::UserDataAccount *> *,tagCOWAIT_FLAGS,void *)
0x18004ee9e  mov     ebx, eax
0x18004eea0  test    eax, eax
0x18004eea2  js      loc_18004EF31
0x18004eea8  mov     rax, [rdi]
0x18004eeab  lea     rdx, [rbp+var_38]
0x18004eeaf  mov     rcx, rdi
0x18004eeb2  mov     rax, [rax+40h]
0x18004eeb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eebb  mov     ebx, eax
0x18004eebd  test    eax, eax
0x18004eebf  js      short loc_18004EF31
0x18004eec1  mov     rcx, [rbp+var_38]
0x18004eec5  test    rcx, rcx
0x18004eec8  jz      short loc_18004EF06
0x18004eeca  mov     rax, [rcx]
0x18004eecd  mov     rdx, rsi
0x18004eed0  mov     rax, [rax+68h]
0x18004eed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eed9  mov     ebx, eax
0x18004eedb  test    eax, eax
0x18004eedd  jns     short loc_18004EF06
0x18004eedf  mov     r9d, eax; char *
0x18004eee2  mov     edx, 84h; void *
0x18004eee7  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004eeee  mov     rcx, [rbp+18h]; this
0x18004eef2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eef7  nop
0x18004eef8  lea     rcx, [rbp+var_38]
0x18004eefc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef01  jmp     loc_18004EE73
0x18004ef06  lea     rcx, [rbp+var_38]
0x18004ef0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef0f  nop
0x18004ef10  lea     rcx, [rbp+var_40]
0x18004ef14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef19  nop
0x18004ef1a  lea     rcx, [rbp+var_48]
0x18004ef1e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef23  nop
0x18004ef24  lea     rcx, [rbp+var_50]
0x18004ef28  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef2d  xor     ebx, ebx
0x18004ef2f  jmp     short loc_18004EF68
0x18004ef31  mov     r9d, ebx
0x18004ef34  mov     edx, 81h
0x18004ef39  jmp     short loc_18004EEE7
0x18004ef3b  mov     edx, 78h ; 'x'; void *
0x18004ef40  mov     r9d, ebx; char *
0x18004ef43  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004ef4a  mov     rcx, [rbp+18h]; this
0x18004ef4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef53  nop
0x18004ef54  lea     rcx, [rbp+var_48]
0x18004ef58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef5d  nop
0x18004ef5e  lea     rcx, [rbp+var_50]
0x18004ef62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef67  nop
0x18004ef68  lea     rcx, [rbp+var_30]
0x18004ef6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004ef71  mov     eax, ebx
0x18004ef73  mov     rcx, [rbp+var_8]
0x18004ef77  xor     rcx, rsp; StackCookie
0x18004ef7a  call    __security_check_cookie
0x18004ef7f  lea     r11, [rsp+70h+var_s0]
0x18004ef84  mov     rbx, [r11+30h]
0x18004ef88  mov     rsi, [r11+38h]
0x18004ef8c  mov     rsp, r11
0x18004ef8f  pop     r14
0x18004ef91  pop     rdi
0x18004ef92  pop     rbp
0x18004ef93  retn
```
