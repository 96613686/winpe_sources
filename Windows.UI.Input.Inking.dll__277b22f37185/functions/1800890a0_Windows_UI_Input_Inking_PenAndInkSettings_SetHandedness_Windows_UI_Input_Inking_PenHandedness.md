# Windows::UI::Input::Inking::PenAndInkSettings::SetHandedness(Windows::UI::Input::Inking::PenHandedness *)

- ea: `0x1800890a0`
- end: `0x1800892cd`
- name: `?SetHandedness@PenAndInkSettings@Inking@Input@UI@Windows@@CAJPEAW4PenHandedness@2345@@Z`
- size: `557`
- prototype: `__int64 __fastcall(enum Windows::UI::Input::Inking::PenHandedness *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800892e0`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x18001332c`
- `0x180086f20`
- `0x18008793c`
- `0x180087ad4`
- `0x180088914`
- `0x180088ccc`
- `0x180088d70`
- `0x180089030`
- `0x1800890a0`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008920f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008920f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180089119`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180089119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800891f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800891f6`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800890c9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800890c9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180089142`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800892ab`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180089142`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800892ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::UI::Input::Inking::PenAndInkSettings::SetHandedness(
        enum Windows::UI::Input::Inking::PenHandedness *a1)
{
  char v2; // di
  HRESULT v3; // eax
  int LoggedOnUser; // ebx
  int v6; // eax
  __int64 v7; // rdx
  bool v8; // r14
  struct Windows::System::IUser *v9; // rsi
  int v10; // eax
  HSTRING v11; // rbx
  int (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v13)(_QWORD, GUID *, struct Windows::System::IUser **); // rsi
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-60h] BYREF
  struct Windows::System::IUser *v16; // [rsp+28h] [rbp-58h] BYREF
  int (__fastcall ***v17)(_QWORD, GUID *, struct Windows::System::IUser **); // [rsp+30h] [rbp-50h] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v2 = 1;
  BYTE1(v15) = 1;
  v3 = CoImpersonateClient();
  if ( v3 < 0 )
  {
    v2 = 0;
    BYTE1(v15) = 0;
    LoggedOnUser = 0;
    if ( v3 != -2147417833 )
      LoggedOnUser = v3;
    if ( LoggedOnUser < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\penandinksettings.cpp",
        (const char *)(unsigned int)LoggedOnUser,
        v15);
      return (unsigned int)LoggedOnUser;
    }
  }
  LOBYTE(v15) = 0;
  v6 = CapabilityCheck(0, L"Microsoft.windowsInkInputPreferences_8wekyb3d8bbwe", &v15);
  if ( v6 < 0 )
  {
    LoggedOnUser = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0xBD,
                     (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\penandinksettings.cpp",
                     (const char *)(unsigned int)v6,
                     v15);
    goto LABEL_9;
  }
  if ( !(_BYTE)v15 )
  {
    LoggedOnUser = -2147024891;
    v7 = 190;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\penandinksettings.cpp",
      (const char *)(unsigned int)LoggedOnUser,
      v15);
    goto LABEL_9;
  }
  v8 = *(_DWORD *)a1 == 0;
  v9 = 0;
  v16 = 0;
  if ( !Windows::UI::Input::Inking::PenAndInkSettings::IsDesktop() )
  {
    LoggedOnUser = Windows::UI::Input::Inking::PenAndInkSettings::GetLoggedOnUser(&v16);
    if ( LoggedOnUser < 0 )
    {
      v7 = 198;
      goto LABEL_13;
    }
    v9 = v16;
  }
  ConstrainedImpersonateLoggedOnUser::ConstrainedImpersonateLoggedOnUser((ConstrainedImpersonateLoggedOnUser *)v18, v9);
  v10 = ConstrainedImpersonateLoggedOnUser::Impersonate((ConstrainedImpersonateLoggedOnUser *)v18);
  LoggedOnUser = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\core\\penandinksettings.cpp",
      (const char *)(unsigned int)v10,
      v15);
    ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser((ConstrainedImpersonateLoggedOnUser *)v18);
LABEL_9:
    if ( v2 )
      CoRevertToSelf();
    return (unsigned int)LoggedOnUser;
  }
  if ( WindowsCreateStringReference(
         L"Windows.UI.Input.Inking.Internal.PenAndInkSettingsPrivate",
         0x39u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v17 = 0;
  v11 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  if ( (int)Windows::Foundation::ActivateInstanceAsUser<IInspectable>(v11, v9, &v17) >= 0 )
  {
    v16 = 0;
    v12 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
    v13 = **v17;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
    if ( v13(v12, &GUID_632e93e3_a0f9_411a_ac2e_2c647d18c05d, &v16) >= 0 )
    {
      LOBYTE(v14) = v8;
      (*(void (__fastcall **)(struct Windows::System::IUser *, __int64))(*(_QWORD *)v16 + 64LL))(v16, v14);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser((ConstrainedImpersonateLoggedOnUser *)v18);
  if ( v2 )
    CoRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x1800890a0  push    rbp
0x1800890a2  push    rbx
0x1800890a3  push    rsi
0x1800890a4  push    rdi
0x1800890a5  push    r14
0x1800890a7  mov     rbp, rsp
0x1800890aa  sub     rsp, 80h
0x1800890b1  mov     rax, cs:__security_cookie
0x1800890b8  xor     rax, rsp
0x1800890bb  mov     [rbp+var_8], rax
0x1800890bf  mov     rsi, rcx
0x1800890c2  mov     dil, 1
0x1800890c5  mov     [rbp+var_5F], dil
0x1800890c9  call    cs:__imp_CoImpersonateClient
0x1800890cf  test    eax, eax
0x1800890d1  jns     short loc_180089108
0x1800890d3  xor     dil, dil
0x1800890d6  mov     [rbp+var_5F], dil
0x1800890da  xor     ebx, ebx
0x1800890dc  cmp     eax, 80010117h
0x1800890e1  cmovnz  ebx, eax
0x1800890e4  test    ebx, ebx
0x1800890e6  jns     short loc_180089108
0x1800890e8  mov     rcx, [rbp+28h]; this
0x1800890ec  mov     r9d, ebx; char *
0x1800890ef  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800890f6  mov     edx, 0B6h; void *
0x1800890fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089100  nop
0x180089101  mov     eax, ebx
0x180089103  jmp     loc_1800892B3
0x180089108  mov     [rbp+var_60], 0
0x18008910c  lea     r8, [rbp+var_60]
0x180089110  lea     rdx, aMicrosoftWindo; "Microsoft.windowsInkInputPreferences_8w"...
0x180089117  xor     ecx, ecx
0x180089119  call    cs:__imp_CapabilityCheck
0x18008911f  test    eax, eax
0x180089121  jns     short loc_18008914A
0x180089123  mov     rcx, [rbp+28h]; this
0x180089127  mov     r9d, eax; char *
0x18008912a  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180089131  mov     edx, 0BDh; void *
0x180089136  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008913b  mov     ebx, eax
0x18008913d  test    dil, dil
0x180089140  jz      short loc_180089101
0x180089142  call    cs:__imp_CoRevertToSelf
0x180089148  jmp     short loc_180089101
0x18008914a  cmp     [rbp+var_60], 0
0x18008914e  jnz     short loc_18008916F
0x180089150  mov     ebx, 80070005h
0x180089155  mov     edx, 0BEh; void *
0x18008915a  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180089161  mov     r9d, ebx; char *
0x180089164  mov     rcx, [rbp+28h]; this
0x180089168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008916d  jmp     short loc_18008913D
0x18008916f  cmp     dword ptr [rsi], 0
0x180089172  setz    r14b
0x180089176  xor     esi, esi
0x180089178  mov     [rbp+var_58], rsi
0x18008917c  call    ?IsDesktop@PenAndInkSettings@Inking@Input@UI@Windows@@CA_NXZ; Windows::UI::Input::Inking::PenAndInkSettings::IsDesktop(void)
0x180089181  test    al, al
0x180089183  jnz     short loc_18008919F
0x180089185  lea     rcx, [rbp+var_58]; struct Windows::System::IUser **
0x180089189  call    ?GetLoggedOnUser@PenAndInkSettings@Inking@Input@UI@Windows@@CAJPEAPEAUIUser@System@5@@Z; Windows::UI::Input::Inking::PenAndInkSettings::GetLoggedOnUser(Windows::System::IUser * *)
0x18008918e  mov     ebx, eax
0x180089190  test    eax, eax
0x180089192  jns     short loc_18008919B
0x180089194  mov     edx, 0C6h
0x180089199  jmp     short loc_18008915A
0x18008919b  mov     rsi, [rbp+var_58]
0x18008919f  mov     rdx, rsi; struct Windows::System::IUser *
0x1800891a2  lea     rcx, [rbp+var_48]; this
0x1800891a6  call    ??0ConstrainedImpersonateLoggedOnUser@@QEAA@PEAUIUser@System@Windows@@@Z; ConstrainedImpersonateLoggedOnUser::ConstrainedImpersonateLoggedOnUser(Windows::System::IUser *)
0x1800891ab  nop
0x1800891ac  lea     rcx, [rbp+var_48]; this
0x1800891b0  call    ?Impersonate@ConstrainedImpersonateLoggedOnUser@@QEAAJXZ; ConstrainedImpersonateLoggedOnUser::Impersonate(void)
0x1800891b5  mov     ebx, eax
0x1800891b7  test    eax, eax
0x1800891b9  jns     short loc_1800891E2
0x1800891bb  mov     rcx, [rbp+28h]; this
0x1800891bf  mov     r9d, eax; char *
0x1800891c2  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800891c9  mov     edx, 0CAh; void *
0x1800891ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800891d3  nop
0x1800891d4  lea     rcx, [rbp+var_48]; this
0x1800891d8  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x1800891dd  jmp     loc_18008913D
0x1800891e2  lea     r9, [rbp+string]; string
0x1800891e6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800891ea  mov     edx, 39h ; '9'; length
0x1800891ef  lea     rcx, ?RuntimeClass_Windows_UI_Input_Inking_Internal_PenAndInkSettingsPrivate@@3QBGB; "Windows.UI.Input.Inking.Internal.PenAnd"...
0x1800891f6  call    cs:__imp_WindowsCreateStringReference
0x1800891fc  test    eax, eax
0x1800891fe  jns     short loc_180089215
0x180089200  xor     r9d, r9d; lpArguments
0x180089203  xor     r8d, r8d; nNumberOfArguments
0x180089206  lea     edx, [r9+1]; dwExceptionFlags
0x18008920a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18008920f  call    cs:__imp_RaiseException
0x180089215  mov     [rbp+var_50], 0
0x18008921d  mov     rbx, [rbp+string]
0x180089221  lea     rcx, [rbp+var_50]
0x180089225  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008922a  lea     r8, [rbp+var_50]
0x18008922e  mov     rdx, rsi
0x180089231  mov     rcx, rbx
0x180089234  call    ??$ActivateInstanceAsUser@UIInspectable@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@PEAPEAUIInspectable@@@Z; Windows::Foundation::ActivateInstanceAsUser<IInspectable>(HSTRING__ *,Windows::System::IUser *,IInspectable * *)
0x180089239  nop
0x18008923a  test    eax, eax
0x18008923c  js      short loc_180089292
0x18008923e  mov     [rbp+var_58], 0
0x180089246  mov     rbx, [rbp+var_50]
0x18008924a  mov     rax, [rbx]
0x18008924d  mov     rsi, [rax]
0x180089250  lea     rcx, [rbp+var_58]
0x180089254  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180089259  lea     r8, [rbp+var_58]
0x18008925d  lea     rdx, _GUID_632e93e3_a0f9_411a_ac2e_2c647d18c05d
0x180089264  mov     rcx, rbx
0x180089267  mov     rax, rsi
0x18008926a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008926f  nop
0x180089270  test    eax, eax
0x180089272  js      short loc_180089288
0x180089274  mov     rcx, [rbp+var_58]
0x180089278  mov     rax, [rcx]
0x18008927b  mov     dl, r14b
0x18008927e  mov     rax, [rax+40h]
0x180089282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089287  nop
0x180089288  lea     rcx, [rbp+var_58]
0x18008928c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180089291  nop
0x180089292  lea     rcx, [rbp+var_50]
0x180089296  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008929b  nop
0x18008929c  lea     rcx, [rbp+var_48]; this
0x1800892a0  call    ??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ; ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)
0x1800892a5  nop
0x1800892a6  test    dil, dil
0x1800892a9  jz      short loc_1800892B1
0x1800892ab  call    cs:__imp_CoRevertToSelf
0x1800892b1  xor     eax, eax
0x1800892b3  mov     rcx, [rbp+var_8]
0x1800892b7  xor     rcx, rsp; StackCookie
0x1800892ba  call    __security_check_cookie
0x1800892bf  add     rsp, 80h
0x1800892c6  pop     r14
0x1800892c8  pop     rdi
0x1800892c9  pop     rsi
0x1800892ca  pop     rbx
0x1800892cb  pop     rbp
0x1800892cc  retn
```
