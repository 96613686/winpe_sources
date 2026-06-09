# WinStoreAuth::AuthenticationInternal::SetPromptBeforePurchaseState(bool,bool,Windows::System::IUser *)

- ea: `0x180043ddc`
- end: `0x180043f36`
- name: `?SetPromptBeforePurchaseState@AuthenticationInternal@WinStoreAuth@@YAX_N0PEAUIUser@System@Windows@@@Z`
- size: `346`
- prototype: `void __fastcall(WinStoreAuth::AuthenticationInternal *this, __int64, __int64, struct Windows::System::IUser *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042768`

## callees

- `0x1800026b0`
- `0x18002fbb4`
- `0x180038110`
- `0x180039a58`
- `0x1800400c0`
- `0x18004215c`
- `0x180042640`
- `0x180043ddc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043e42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043e42`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180043f0c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180043f0c`

## string_xrefs

- `0x180043e3b`: `Windows.ApplicationModel.Store.Internal.AuthenticationExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WinStoreAuth::AuthenticationInternal::SetPromptBeforePurchaseState(
        WinStoreAuth::AuthenticationInternal *this,
        __int64 a2,
        __int64 a3,
        struct Windows::System::IUser *a4)
{
  struct Windows::System::IUser **v4; // rdx
  __int64 v5; // rcx
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  __int64 v9; // rcx
  __int64 Data; // [rsp+30h] [rbp-40h] BYREF
  __int64 v11; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF

  if ( WinStoreAuth::AuthenticationInternal::IsPlatformXbox(this) )
  {
    Data = 0;
    WinStoreAuth::AuthenticationInternal::GetCurrentIUser((WinStoreAuth::AuthenticationInternal *)&Data, v4);
    v5 = Data;
    if ( Data )
    {
      v11 = 0;
      string = 0;
      v6 = WindowsCreateStringReference(
             L"Windows.ApplicationModel.Store.Internal.AuthenticationExtension",
             0x3Fu,
             &hstringHeader,
             &string);
      if ( v6 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
        JUMPOUT(0x180043F35LL);
      }
      if ( (int)Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Internal::IAuthenticationExtension>>(
                  string,
                  &v11) >= 0 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v11 + 56LL))(v11, Data, 1);
      v9 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      v5 = Data;
    }
    if ( v5 )
    {
      Data = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
  }
  else
  {
    hstringHeader.Reserved.Reserved2[0] = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    string = 0;
    if ( (int)ConstrainedImpersonateLoggedOnUser::Impersonate((ConstrainedImpersonateLoggedOnUser *)&hstringHeader) >= 0 )
    {
      LODWORD(Data) = 0;
      RegSetKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Store\\CurrentIdentity",
        L"AlwaysPromptBeforePurchase",
        4u,
        &Data,
        4u);
    }
    ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser((ConstrainedImpersonateLoggedOnUser *)&hstringHeader);
  }
}

```

## disassembly

```asm
0x180043ddc  push    rbp
0x180043dde  mov     rbp, rsp
0x180043de1  sub     rsp, 70h
0x180043de5  mov     rax, cs:__security_cookie
0x180043dec  xor     rax, rsp
0x180043def  mov     [rbp+var_10], rax
0x180043df3  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x180043df8  test    al, al
0x180043dfa  jz      loc_180043EBB
0x180043e00  mov     [rbp+Data], 0
0x180043e08  lea     rcx, [rbp+Data]; this
0x180043e0c  call    ?GetCurrentIUser@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIUser@System@Windows@@@Z; WinStoreAuth::AuthenticationInternal::GetCurrentIUser(Windows::System::IUser * *)
0x180043e11  mov     rcx, [rbp+Data]
0x180043e15  test    rcx, rcx
0x180043e18  jz      loc_180043E9F
0x180043e1e  mov     [rbp+var_38], 0
0x180043e26  mov     [rbp+string], 0
0x180043e2e  lea     r9, [rbp+string]; string
0x180043e32  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180043e36  mov     edx, 3Fh ; '?'; length
0x180043e3b  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Store_Internal_AuthenticationExtension@@3QBGB; "Windows.ApplicationModel.Store.Internal"...
0x180043e42  call    cs:__imp_WindowsCreateStringReference
0x180043e48  test    eax, eax
0x180043e4a  js      loc_180043F2E
0x180043e50  lea     rdx, [rbp+var_38]
0x180043e54  mov     rcx, [rbp+string]
0x180043e58  call    ??$ActivateInstance@V?$ComPtr@UIAuthenticationExtension@Internal@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAuthenticationExtension@Internal@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Internal::IAuthenticationExtension>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Internal::IAuthenticationExtension>>)
0x180043e5d  test    eax, eax
0x180043e5f  js      short loc_180043E7D
0x180043e61  mov     rcx, [rbp+var_38]
0x180043e65  mov     rax, [rcx]
0x180043e68  xor     r9d, r9d
0x180043e6b  lea     r8d, [r9+1]
0x180043e6f  mov     rdx, [rbp+Data]
0x180043e73  mov     rax, [rax+38h]
0x180043e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e7c  nop
0x180043e7d  mov     rcx, [rbp+var_38]
0x180043e81  test    rcx, rcx
0x180043e84  jz      short loc_180043E9B
0x180043e86  mov     [rbp+var_38], 0
0x180043e8e  mov     rax, [rcx]
0x180043e91  mov     rax, [rax+10h]
0x180043e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e9a  nop
0x180043e9b  mov     rcx, [rbp+Data]
0x180043e9f  test    rcx, rcx
0x180043ea2  jz      short loc_180043EB9
0x180043ea4  mov     [rbp+Data], 0
0x180043eac  mov     rax, [rcx]
0x180043eaf  mov     rax, [rax+10h]
0x180043eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043eb8  nop
0x180043eb9  jmp     short loc_180043F1C
0x180043ebb  mov     byte ptr [rbp+hstringHeader.Reserved], 0
0x180043ebf  xorps   xmm0, xmm0
0x180043ec2  movdqu  xmmword ptr [rbp+hstringHeader.Reserved+8], xmm0
0x180043ec7  mov     [rbp+string], 0
0x180043ecf  lea     rcx, [rbp+hstringHeader]; this
0x180043ed3  call    ?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ; ConstrainedImpersonateLoggedOnUser::Impersonate(void)
0x180043ed8  test    eax, eax
0x180043eda  js      short loc_180043F13
0x180043edc  mov     dword ptr [rbp+Data], 0
0x180043ee3  mov     r9d, 4; dwType
0x180043ee9  mov     [rsp+70h+cbData], r9d; cbData
0x180043eee  lea     rax, [rbp+Data]
0x180043ef2  mov     [rsp+70h+lpData], rax; lpData
0x180043ef7  lea     r8, ValueName; "AlwaysPromptBeforePurchase"
0x180043efe  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180043f05  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180043f0c  call    cs:__imp_RegSetKeyValueW
0x180043f12  nop
0x180043f13  lea     rcx, [rbp+hstringHeader]; this
0x180043f17  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x180043f1c  mov     rcx, [rbp+var_10]
0x180043f20  xor     rcx, rsp; StackCookie
0x180043f23  call    __security_check_cookie
0x180043f28  add     rsp, 70h
0x180043f2c  pop     rbp
0x180043f2d  retn
0x180043f2e  mov     ecx, eax; this
0x180043f30  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
