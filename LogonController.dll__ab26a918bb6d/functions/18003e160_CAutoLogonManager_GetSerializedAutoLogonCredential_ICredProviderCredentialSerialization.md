# CAutoLogonManager::GetSerializedAutoLogonCredential(ICredProviderCredentialSerialization * *)

- ea: `0x18003e160`
- end: `0x18003e3bd`
- name: `?GetSerializedAutoLogonCredential@CAutoLogonManager@@UEAAJPEAPEAUICredProviderCredentialSerialization@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(CAutoLogonManager *__hidden this, struct ICredProviderCredentialSerialization **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000df10`
- `0x18003e160`
- `0x18003e3c4`
- `0x18005d488`
- `0x1800611bc`
- `0x18006a2a8`
- `0x18006c000`
- `0x1800919fc`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e391`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e391`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e1e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e269`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e2ac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e1e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e269`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e2ac`
- `SHCORE!SHDeleteValueW` at `0x18003e2c9`
- `SHCORE!SHDeleteValueW` at `0x18003e2e0`
- `SHCORE!SHDeleteValueW` at `0x18003e2c9`
- `SHCORE!SHDeleteValueW` at `0x18003e2e0`

## string_xrefs

- `0x18003e313`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003e349`: `onecoreuap\shell\auth\credprovcommon\autologon\autologonmanager.cpp`
- `0x18003e250`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18003e299`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
__int64 __fastcall CAutoLogonManager::GetSerializedAutoLogonCredential(
        CAutoLogonManager *this,
        struct ICredProviderCredentialSerialization **a2)
{
  LSTATUS ValueW; // eax
  CAutoLogonManager *v5; // rcx
  bool v6; // sf
  int SerializationConnectedAutoLogon; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int SerializationUnlockLogon; // eax
  int v11; // eax
  int pdwType; // [rsp+20h] [rbp-60h]
  DWORD pcbData; // [rsp+40h] [rbp-40h] BYREF
  DWORD v15; // [rsp+44h] [rbp-3Ch] BYREF
  struct ICredProviderCredentialSerialization *v16; // [rsp+48h] [rbp-38h] BYREF
  int pvData; // [rsp+50h] [rbp-30h] BYREF
  _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION v18; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *a2 = 0;
  pvData = 0;
  pcbData = 4;
  memset(&v18, 0, sizeof(v18));
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
             L"IsConnectedAutoLogon",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v6 = ValueW < 0;
  if ( ValueW > 0 )
    v6 = 1;
  if ( v6 || pvData != 1 )
  {
    SerializationUnlockLogon = CAutoLogonManager::_GetSerializationUnlockLogon(
                                 (CAutoLogonManager *)((char *)this - 8),
                                 &v18);
    SerializationConnectedAutoLogon = SerializationUnlockLogon;
    if ( SerializationUnlockLogon < 0 )
    {
      v8 = (unsigned int)SerializationUnlockLogon;
      v9 = 552;
      goto LABEL_14;
    }
  }
  else
  {
    SerializationConnectedAutoLogon = CAutoLogonManager::_GetSerializationConnectedAutoLogon(v5, &v18);
    if ( (*(unsigned int (__fastcall **)(CAutoLogonManager *))(*(_QWORD *)this + 56LL))(this) )
    {
      pcbData = 0;
      v15 = 4;
      if ( RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Enabled",
             0x10010u,
             0,
             &pcbData,
             &v15) )
      {
        v15 = 4;
        RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
          L"Enabled",
          0x20010010u,
          0,
          &pcbData,
          &v15);
      }
      if ( !pcbData )
      {
        SHDeleteValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          L"IsConnectedAutoLogon");
        SHDeleteValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
          L"ConnectedCredentials");
      }
    }
    if ( SerializationConnectedAutoLogon < 0 )
    {
      v8 = (unsigned int)SerializationConnectedAutoLogon;
      v9 = 548;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
        (const char *)v8,
        pdwType);
LABEL_17:
      CoTaskMemFree(0);
      lambda_7e33ee43c9274cbc15d91f13876c12df_::operator()();
      return (unsigned int)SerializationConnectedAutoLogon;
    }
  }
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v16);
  v11 = Microsoft::WRL::Details::MakeAndInitialize<CCredentialProviderSerialization,ICredProviderCredentialSerialization,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &>(
          &v16,
          (int *)&v18);
  SerializationConnectedAutoLogon = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecoreuap\\shell\\auth\\credprovcommon\\autologon\\autologonmanager.cpp",
      (const char *)(unsigned int)v11,
      pdwType);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v16);
    goto LABEL_17;
  }
  *a2 = v16;
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v16);
  CoTaskMemFree(0);
  return 0;
}

```

## disassembly

```asm
0x18003e160  mov     r11, rsp
0x18003e163  mov     [r11+18h], rbx
0x18003e167  mov     [r11+20h], rsi
0x18003e16b  push    rbp
0x18003e16c  push    rdi
0x18003e16d  push    r15
0x18003e16f  mov     rbp, rsp
0x18003e172  sub     rsp, 80h
0x18003e179  mov     rax, cs:__security_cookie
0x18003e180  xor     rax, rsp
0x18003e183  mov     [rbp+var_8], rax
0x18003e187  xorps   xmm0, xmm0
0x18003e18a  mov     qword ptr [rdx], 0
0x18003e191  lea     rax, [rbp+var_40]
0x18003e195  mov     [rbp+var_30], 0
0x18003e19c  mov     [r11-68h], rax
0x18003e1a0  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x18003e1a7  lea     rax, [rbp+var_30]
0x18003e1ab  mov     [rbp+var_40], 4
0x18003e1b2  mov     rsi, rdx
0x18003e1b5  mov     [r11-70h], rax
0x18003e1b9  mov     rdi, rcx
0x18003e1bc  mov     qword ptr [r11-78h], 0
0x18003e1c4  mov     r15, 0FFFFFFFF80000002h
0x18003e1cb  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003e1d2  mov     r9d, 10h; dwFlags
0x18003e1d8  mov     rcx, r15; hkey
0x18003e1db  movups  xmmword ptr [rbp+var_28.ulAuthenticationPackage], xmm0
0x18003e1df  movups  xmmword ptr [rbp+var_28.clsidCredentialProvider.Data4+4], xmm0
0x18003e1e3  call    cs:__imp_RegGetValueW
0x18003e1e9  test    eax, eax
0x18003e1eb  jle     short loc_18003E1F7
0x18003e1ed  movzx   eax, ax
0x18003e1f0  or      eax, 80070000h
0x18003e1f5  test    eax, eax
0x18003e1f7  js      loc_18003E2F4
0x18003e1fd  cmp     [rbp+var_30], 1
0x18003e201  jnz     loc_18003E2F4
0x18003e207  lea     rdx, [rbp+var_28]; struct _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *
0x18003e20b  call    ?_GetSerializationConnectedAutoLogon@CAutoLogonManager@@AEAAJPEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z; CAutoLogonManager::_GetSerializationConnectedAutoLogon(_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)
0x18003e210  mov     rdx, [rdi]
0x18003e213  mov     ebx, eax
0x18003e215  mov     rcx, rdi
0x18003e218  mov     rax, [rdx+38h]
0x18003e21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e221  test    eax, eax
0x18003e223  jz      loc_18003E2E6
0x18003e229  lea     rax, [rbp+var_3C]
0x18003e22d  mov     [rbp+var_40], 0
0x18003e234  mov     [rsp+80h+pcbData], rax; pcbData
0x18003e239  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18003e240  lea     rax, [rbp+var_40]
0x18003e244  mov     [rbp+var_3C], 4
0x18003e24b  mov     [rsp+80h+pvData], rax; pvData
0x18003e250  lea     rdx, aOsdataSoftware; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x18003e257  mov     r9d, 10010h; dwFlags
0x18003e25d  mov     [rsp+80h+pdwType], 0; pdwType
0x18003e266  mov     rcx, r15; hkey
0x18003e269  call    cs:__imp_RegGetValueW
0x18003e26f  test    eax, eax
0x18003e271  jz      short loc_18003E2B2
0x18003e273  lea     rax, [rbp+var_3C]
0x18003e277  mov     [rbp+var_3C], 4
0x18003e27e  mov     [rsp+80h+pcbData], rax; pcbData
0x18003e283  lea     r8, ?c_retailDemoValueEnabled@@3QBGB; "Enabled"
0x18003e28a  lea     rax, [rbp+var_40]
0x18003e28e  mov     r9d, 20010010h; dwFlags
0x18003e294  mov     [rsp+80h+pvData], rax; pvData
0x18003e299  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e2a0  mov     rcx, r15; hkey
0x18003e2a3  mov     [rsp+80h+pdwType], 0; int
0x18003e2ac  call    cs:__imp_RegGetValueW
0x18003e2b2  cmp     [rbp+var_40], 0
0x18003e2b6  jnz     short loc_18003E2E6
0x18003e2b8  lea     r8, aIsconnectedaut; "IsConnectedAutoLogon"
0x18003e2bf  mov     rcx, r15; hkey
0x18003e2c2  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003e2c9  call    cs:__imp_SHDeleteValueW
0x18003e2cf  lea     r8, aConnectedcrede; "ConnectedCredentials"
0x18003e2d6  mov     rcx, r15; hkey
0x18003e2d9  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x18003e2e0  call    cs:__imp_SHDeleteValueW
0x18003e2e6  test    ebx, ebx
0x18003e2e8  jns     short loc_18003E321
0x18003e2ea  mov     r9d, ebx
0x18003e2ed  mov     edx, 224h
0x18003e2f2  jmp     short loc_18003E30F
0x18003e2f4  lea     rcx, [rdi-8]; this
0x18003e2f8  lea     rdx, [rbp+var_28]; struct _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *
0x18003e2fc  call    ?_GetSerializationUnlockLogon@CAutoLogonManager@@AEAAJPEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z; CAutoLogonManager::_GetSerializationUnlockLogon(_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)
0x18003e301  mov     ebx, eax
0x18003e303  test    eax, eax
0x18003e305  jns     short loc_18003E321
0x18003e307  mov     r9d, eax; char *
0x18003e30a  mov     edx, 228h; void *
0x18003e30f  mov     rcx, [rbp+18h]; this
0x18003e313  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003e31a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e31f  jmp     short loc_18003E366
0x18003e321  lea     rcx, [rbp+var_38]
0x18003e325  mov     [rbp+var_38], 0
0x18003e32d  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003e332  lea     rdx, [rbp+var_28]
0x18003e336  lea     rcx, [rbp+var_38]
0x18003e33a  call    ??$MakeAndInitialize@VCCredentialProviderSerialization@@UICredProviderCredentialSerialization@@AEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Details@WRL@Microsoft@@YAJPEAPEAUICredProviderCredentialSerialization@@AEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCredentialProviderSerialization,ICredProviderCredentialSerialization,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &>(ICredProviderCredentialSerialization * *,_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION &)
0x18003e33f  mov     ebx, eax
0x18003e341  test    eax, eax
0x18003e343  jns     short loc_18003E377
0x18003e345  mov     rcx, [rbp+18h]; this
0x18003e349  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\auth\\credprovcommon"...
0x18003e350  mov     r9d, eax; char *
0x18003e353  mov     edx, 22Ch; void *
0x18003e358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e35d  lea     rcx, [rbp+var_38]
0x18003e361  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003e366  xor     ecx, ecx; pv
0x18003e368  call    cs:__imp_CoTaskMemFree
0x18003e36e  call    _lambda_7e33ee43c9274cbc15d91f13876c12df___operator__
0x18003e373  mov     eax, ebx
0x18003e375  jmp     short loc_18003E399
0x18003e377  mov     rax, [rbp+var_38]
0x18003e37b  lea     rcx, [rbp+var_38]
0x18003e37f  mov     [rsi], rax
0x18003e382  mov     [rbp+var_38], 0
0x18003e38a  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003e38f  xor     ecx, ecx; pv
0x18003e391  call    cs:__imp_CoTaskMemFree
0x18003e397  xor     eax, eax
0x18003e399  mov     rcx, [rbp+var_8]
0x18003e39d  xor     rcx, rsp; StackCookie
0x18003e3a0  call    __security_check_cookie
0x18003e3a5  lea     r11, [rsp+80h+var_s0]
0x18003e3ad  mov     rbx, [r11+30h]
0x18003e3b1  mov     rsi, [r11+38h]
0x18003e3b5  mov     rsp, r11
0x18003e3b8  pop     r15
0x18003e3ba  pop     rdi
0x18003e3bb  pop     rbp
0x18003e3bc  retn
```
