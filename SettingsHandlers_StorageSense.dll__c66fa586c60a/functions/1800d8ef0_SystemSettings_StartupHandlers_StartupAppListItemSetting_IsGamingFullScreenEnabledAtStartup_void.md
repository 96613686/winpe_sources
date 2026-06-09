# SystemSettings::StartupHandlers::StartupAppListItemSetting::IsGamingFullScreenEnabledAtStartup(void)

- ea: `0x1800d8ef0`
- end: `0x1800d9047`
- name: `?IsGamingFullScreenEnabledAtStartup@StartupAppListItemSetting@StartupHandlers@SystemSettings@@AEAA_NXZ`
- size: `343`
- prototype: `bool __fastcall(SystemSettings::StartupHandlers::StartupAppListItemSetting *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d80a0`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x180019fa8`
- `0x180034cd8`
- `0x1800d8ef0`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d8fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d8fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d9018`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d8f6b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d8f6b`
- `api-ms-win-gaming-experience-l1-1-0!IsGamingFullScreenExperienceSupported` at `0x1800d8ff6`
- `api-ms-win-gaming-experience-l1-1-0!IsGamingFullScreenExperienceSupported` at `0x1800d8ff6`

## string_xrefs

- `0x1800d8f37`: `Windows.Internal.GamingExperiences.Posture.GamingPostureConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall SystemSettings::StartupHandlers::StartupAppListItemSetting::IsGamingFullScreenEnabledAtStartup(
        SystemSettings::StartupHandlers::StartupAppListItemSetting *this)
{
  char v1; // si
  __int64 v2; // rbx
  int ActivationFactory; // eax
  wil::details::in1diag3 *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  char v8; // al
  int v9; // eax
  HSTRING v10; // rcx
  int v12; // [rsp+20h] [rbp-58h] BYREF
  HSTRING string; // [rsp+28h] [rbp-50h] BYREF
  __int64 v14; // [rsp+30h] [rbp-48h] BYREF
  int v15; // [rsp+38h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v14 = 0;
  LOBYTE(v12) = 0;
  string = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.GamingExperiences.Posture.GamingPostureConfiguration",
    0x46u,
    0x45u);
  v1 = 1;
  v15 = 1;
  v2 = v17;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v14);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_9a16c995_5526_5bcc_ab74_70b0a886261e, &v14);
  v4 = retaddr;
  if ( ActivationFactory < 0 )
  {
    v5 = 438;
LABEL_7:
    wil::details::in1diag3::_Log_Hr(
      v4,
      (void *)v5,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startupapplistitemsetting.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v12);
    v8 = 0;
    goto LABEL_9;
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 48LL))(v14, &v12);
  v4 = retaddr;
  if ( ActivationFactory < 0 )
  {
    v5 = 439;
    goto LABEL_7;
  }
  v6 = v14;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 80LL);
  WindowsDeleteString(string);
  string = 0;
  ActivationFactory = v7(v6, &string);
  v4 = retaddr;
  if ( ActivationFactory < 0 )
  {
    v5 = 440;
    goto LABEL_7;
  }
  v8 = 1;
LABEL_9:
  if ( !v8 )
  {
    v10 = string;
LABEL_15:
    v1 = 0;
    goto LABEL_16;
  }
  v9 = IsGamingFullScreenExperienceSupported();
  v10 = string;
  if ( !v9 || !(_BYTE)v12 || !string )
    goto LABEL_15;
LABEL_16:
  WindowsDeleteString(v10);
  string = 0;
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v14);
  return v1;
}

```

## disassembly

```asm
0x1800d8ef0  push    rbp
0x1800d8ef2  push    rbx
0x1800d8ef3  push    rsi
0x1800d8ef4  push    rdi
0x1800d8ef5  mov     rbp, rsp
0x1800d8ef8  sub     rsp, 78h
0x1800d8efc  mov     rax, cs:__security_cookie
0x1800d8f03  xor     rax, rsp
0x1800d8f06  mov     [rbp+var_18], rax
0x1800d8f0a  mov     [rbp+var_40], 0
0x1800d8f11  mov     [rbp+var_48], 0
0x1800d8f19  mov     byte ptr [rbp+var_58], 0
0x1800d8f1d  mov     [rbp+string], 0
0x1800d8f25  mov     [rbp+var_20], 0
0x1800d8f2d  mov     r9d, 45h ; 'E'; unsigned int
0x1800d8f33  lea     r8d, [r9+1]; unsigned int
0x1800d8f37  lea     rdx, ?RuntimeClass_Windows_Internal_GamingExperiences_Posture_GamingPostureConfiguration@@3QBGB; "Windows.Internal.GamingExperiences.Post"...
0x1800d8f3e  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800d8f42  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d8f47  nop
0x1800d8f48  mov     esi, 1
0x1800d8f4d  mov     [rbp+var_40], esi
0x1800d8f50  mov     rbx, [rbp+var_20]
0x1800d8f54  lea     rcx, [rbp+var_48]
0x1800d8f58  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800d8f5d  lea     r8, [rbp+var_48]
0x1800d8f61  lea     rdx, _GUID_9a16c995_5526_5bcc_ab74_70b0a886261e
0x1800d8f68  mov     rcx, rbx
0x1800d8f6b  call    cs:__imp_RoGetActivationFactory
0x1800d8f71  mov     rcx, [rbp+20h]
0x1800d8f75  test    eax, eax
0x1800d8f77  jns     short loc_1800D8F80
0x1800d8f79  mov     edx, 1B6h
0x1800d8f7e  jmp     short loc_1800D8FDC
0x1800d8f80  mov     rcx, [rbp+var_48]
0x1800d8f84  mov     rax, [rcx]
0x1800d8f87  lea     rdx, [rbp+var_58]
0x1800d8f8b  mov     rax, [rax+30h]
0x1800d8f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8f94  mov     rcx, [rbp+20h]
0x1800d8f98  test    eax, eax
0x1800d8f9a  jns     short loc_1800D8FA3
0x1800d8f9c  mov     edx, 1B7h
0x1800d8fa1  jmp     short loc_1800D8FDC
0x1800d8fa3  mov     rdi, [rbp+var_48]
0x1800d8fa7  mov     rax, [rdi]
0x1800d8faa  mov     rbx, [rax+50h]
0x1800d8fae  mov     rcx, [rbp+string]; string
0x1800d8fb2  call    cs:__imp_WindowsDeleteString
0x1800d8fb8  mov     [rbp+string], 0
0x1800d8fc0  lea     rdx, [rbp+string]
0x1800d8fc4  mov     rcx, rdi
0x1800d8fc7  mov     rax, rbx
0x1800d8fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8fcf  mov     rcx, [rbp+20h]; this
0x1800d8fd3  test    eax, eax
0x1800d8fd5  jns     short loc_1800D8FEF
0x1800d8fd7  mov     edx, 1B8h; void *
0x1800d8fdc  lea     r8, aOnecoreuapShel_24; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d8fe3  mov     r9d, eax; char *
0x1800d8fe6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d8feb  xor     al, al
0x1800d8fed  jmp     short loc_1800D8FF2
0x1800d8fef  mov     al, sil
0x1800d8ff2  test    al, al
0x1800d8ff4  jz      short loc_1800D9011
0x1800d8ff6  call    cs:__imp_IsGamingFullScreenExperienceSupported
0x1800d8ffc  mov     rcx, [rbp+string]
0x1800d9000  test    eax, eax
0x1800d9002  jz      short loc_1800D9015
0x1800d9004  cmp     byte ptr [rbp+var_58], 0
0x1800d9008  jz      short loc_1800D9015
0x1800d900a  test    rcx, rcx
0x1800d900d  jnz     short loc_1800D9018
0x1800d900f  jmp     short loc_1800D9015
0x1800d9011  mov     rcx, [rbp+string]; string
0x1800d9015  xor     sil, sil
0x1800d9018  call    cs:__imp_WindowsDeleteString
0x1800d901e  mov     [rbp+string], 0
0x1800d9026  lea     rcx, [rbp+var_48]
0x1800d902a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800d902f  mov     al, sil
0x1800d9032  mov     rcx, [rbp+var_18]
0x1800d9036  xor     rcx, rsp; StackCookie
0x1800d9039  call    __security_check_cookie
0x1800d903e  add     rsp, 78h
0x1800d9042  pop     rdi
0x1800d9043  pop     rsi
0x1800d9044  pop     rbx
0x1800d9045  pop     rbp
0x1800d9046  retn
```
