# SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x180039f20`
- end: `0x18003a0a5`
- name: `?SetValue@CDevicesPenSetHandednessConfiguration@PenSettings@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `389`
- prototype: `int(SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a29c`
- `0x18000a2bc`
- `0x1800167f8`
- `0x18001741c`
- `0x18001a604`
- `0x180038538`
- `0x180039f20`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039faa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039f42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a06d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a093`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039f42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a05b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a06d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a081`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a093`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180039fe6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180039fe6`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a036`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a036`

## string_xrefs

- `0x180039f6c`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`
- `0x180039fbd`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`
- `0x18003a044`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration::SetValue(
        SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v3)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v4; // eax
  unsigned int LastError; // ebx
  HRESULT v6; // eax
  HRESULT v7; // eax
  unsigned __int64 v8; // rdx
  unsigned __int8 v9; // cl
  unsigned int v10; // r8d
  __int64 v11; // rbx
  bool v12; // di
  __int64 v13; // rcx
  PenSettingsTelemetry *v14; // rcx
  const char *v15; // r9
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  INT32 result; // [rsp+48h] [rbp+28h] BYREF
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  HSTRING string1; // [rsp+58h] [rbp+38h] BYREF

  string1 = 0;
  v3 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string1 = 0;
  v4 = v3(a2, &string1);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
      (const char *)(unsigned int)v4,
      savedregs);
LABEL_14:
    WindowsDeleteString(string1);
    return LastError;
  }
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v6 = WindowsCreateString(L"SystemSettings_Devices_Pen_RightHanded_Rejuv", 0x2Cu, &string);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
      (const char *)(unsigned int)v6,
      savedregs);
LABEL_13:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_14;
  }
  result = 0;
  v7 = WindowsCompareStringOrdinal(string1, string, &result);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v10);
    JUMPOUT(0x18003A0A4LL);
  }
  if ( result )
  {
    v11 = 0;
    v12 = 0;
  }
  else
  {
    v11 = 1;
    v12 = 1;
  }
  if ( PenSettingsTelemetry::IsEnabled(v9, v8) )
  {
    wil::details::static_lazy<PenSettingsTelemetry>::get(
      v13,
      _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
    PenSettingsTelemetry::HandednessSettingChanged_(v14, v12);
  }
  if ( !SystemParametersInfoW(0x2025u, 0, (PVOID)v11, 3u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xBC,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
                  v15);
    goto LABEL_13;
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(string1);
  return 0;
}

```

## disassembly

```asm
0x180039f20  push    rbp
0x180039f22  push    rbx
0x180039f23  push    rdi; int
0x180039f24  mov     rbp, rsp
0x180039f27  sub     rsp, 20h
0x180039f2b  mov     rdi, rdx
0x180039f2e  mov     [rbp+string1], 0
0x180039f36  mov     rax, [rdx]
0x180039f39  mov     rbx, [rax+98h]
0x180039f40  xor     ecx, ecx; string
0x180039f42  call    cs:__imp_WindowsDeleteString
0x180039f48  mov     [rbp+string1], 0
0x180039f50  lea     rdx, [rbp+string1]
0x180039f54  mov     rcx, rdi
0x180039f57  mov     rax, rbx
0x180039f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f5f  mov     ebx, eax
0x180039f61  test    eax, eax
0x180039f63  jns     short loc_180039F82
0x180039f65  mov     rcx, [rbp+18h]; this
0x180039f69  mov     r9d, eax; char *
0x180039f6c  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180039f73  mov     edx, 0B0h; void *
0x180039f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f7d  jmp     loc_18003A069
0x180039f82  mov     [rbp+string], 0
0x180039f8a  xor     ecx, ecx; string
0x180039f8c  call    cs:__imp_WindowsDeleteString
0x180039f92  mov     [rbp+string], 0
0x180039f9a  lea     r8, [rbp+string]; string
0x180039f9e  mov     edx, 2Ch ; ','; length
0x180039fa3  lea     rcx, sourceString; "SystemSettings_Devices_Pen_RightHanded_"...
0x180039faa  call    cs:__imp_WindowsCreateString
0x180039fb0  mov     ebx, eax
0x180039fb2  test    eax, eax
0x180039fb4  jns     short loc_180039FD3
0x180039fb6  mov     rcx, [rbp+18h]; this
0x180039fba  mov     r9d, eax; char *
0x180039fbd  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180039fc4  mov     edx, 0B2h; void *
0x180039fc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039fce  jmp     loc_18003A057
0x180039fd3  mov     [rbp+result], 0
0x180039fda  lea     r8, [rbp+result]; result
0x180039fde  mov     rdx, [rbp+string]; string2
0x180039fe2  mov     rcx, [rbp+string1]; string1
0x180039fe6  call    cs:__imp_WindowsCompareStringOrdinal
0x180039fec  test    eax, eax
0x180039fee  js      loc_18003A09D
0x180039ff4  cmp     [rbp+result], 0
0x180039ff8  jnz     short loc_18003A004
0x180039ffa  mov     ebx, 1
0x180039fff  mov     dil, bl
0x18003a002  jmp     short loc_18003A009
0x18003a004  xor     ebx, ebx
0x18003a006  xor     dil, dil
0x18003a009  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18003a00e  test    al, al
0x18003a010  jz      short loc_18003A026
0x18003a012  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x18003a019  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x18003a01e  mov     dl, dil; bool
0x18003a021  call    ?HandednessSettingChanged_@PenSettingsTelemetry@@QEBAX_N@Z; PenSettingsTelemetry::HandednessSettingChanged_(bool)
0x18003a026  mov     r9d, 3; fWinIni
0x18003a02c  mov     r8, rbx; pvParam
0x18003a02f  xor     edx, edx; uiParam
0x18003a031  mov     ecx, 2025h; uiAction
0x18003a036  call    cs:__imp_SystemParametersInfoW
0x18003a03c  test    eax, eax
0x18003a03e  jnz     short loc_18003A07D
0x18003a040  mov     rcx, [rbp+18h]; this
0x18003a044  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x18003a04b  mov     edx, 0BCh; void *
0x18003a050  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a055  mov     ebx, eax
0x18003a057  mov     rcx, [rbp+string]; string
0x18003a05b  call    cs:__imp_WindowsDeleteString
0x18003a061  mov     [rbp+string], 0
0x18003a069  mov     rcx, [rbp+string1]; string
0x18003a06d  call    cs:__imp_WindowsDeleteString
0x18003a073  mov     eax, ebx
0x18003a075  add     rsp, 20h
0x18003a079  pop     rdi
0x18003a07a  pop     rbx
0x18003a07b  pop     rbp
0x18003a07c  retn
0x18003a07d  mov     rcx, [rbp+string]; string
0x18003a081  call    cs:__imp_WindowsDeleteString
0x18003a087  mov     [rbp+string], 0
0x18003a08f  mov     rcx, [rbp+string1]; string
0x18003a093  call    cs:__imp_WindowsDeleteString
0x18003a099  xor     eax, eax
0x18003a09b  jmp     short loc_18003A075
0x18003a09d  mov     ecx, eax; this
0x18003a09f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
