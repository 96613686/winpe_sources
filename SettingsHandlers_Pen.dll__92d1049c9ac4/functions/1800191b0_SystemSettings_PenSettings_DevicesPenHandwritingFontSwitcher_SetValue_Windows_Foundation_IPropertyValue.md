# SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x1800191b0`
- end: `0x18001938b`
- name: `?SetValue@DevicesPenHandwritingFontSwitcher@PenSettings@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a2bc`
- `0x18001033c`
- `0x1800115d8`
- `0x1800134b8`
- `0x180015520`
- `0x1800167f8`
- `0x18001899c`
- `0x1800191b0`
- `0x180019fcc`
- `0x18001a378`
- `0x18001a604`
- `0x18004c21c`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800192e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001930f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800192e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001930f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800191ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800192ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001935c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800191ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800192ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001935c`

## string_xrefs

- `0x18001921f`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x1800192ac`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher::SetValue(
        SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 HandwritingViewRegKeySDDLForCurrentContext; // rax
  const unsigned __int16 *v8; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v10; // rdx
  HKEY v11; // rcx
  const unsigned __int16 *v12; // r8
  int v13; // eax
  const char *v14; // r9
  const unsigned __int16 *v16; // rbx
  unsigned __int64 v17; // rdx
  unsigned __int8 v18; // cl
  __int64 v19; // rcx
  PenSettingsTelemetry *v20; // rcx
  PCWSTR v21; // rdx
  int v22; // [rsp+20h] [rbp-78h]
  int v23; // [rsp+20h] [rbp-78h]
  HSTRING string; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-60h]
  _OWORD v26[2]; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  string = 0;
  v4 = *(__int64 (__fastcall **)(struct Windows::Foundation::IPropertyValue *, HSTRING *))(*(_QWORD *)a2 + 152LL);
  WindowsDeleteString(0);
  string = 0;
  v5 = v4(a2, &string);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
      (const char *)(unsigned int)v5,
      v22);
LABEL_5:
    WindowsDeleteString(string);
    return v6;
  }
  try
  {
    v26[0] = 0;
    v26[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v26[0]) = 0;
    HandwritingViewRegKeySDDLForCurrentContext = Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContext(v27);
    std::wstring::operator=(v26, HandwritingViewRegKeySDDLForCurrentContext);
    std::wstring::_Tidy_deallocate(v27);
    v8 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = SHRegSetStringWithSSDL(v11, v10, v12, StringRawBuffer, v8);
  }
  catch ( ... )
  {
    v25 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x136,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
            v14);
    std::wstring::_Tidy_deallocate(v26);
    WindowsDeleteString(string);
    return v25;
  }
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
      (const char *)(unsigned int)v13,
      v23);
    std::wstring::_Tidy_deallocate(v26);
    goto LABEL_5;
  }
  v16 = WindowsGetStringRawBuffer(string, 0);
  if ( PenSettingsTelemetry::IsEnabled(v18, v17) )
  {
    wil::details::static_lazy<PenSettingsTelemetry>::get(
      v19,
      _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
    PenSettingsTelemetry::HandwritingFontSwitched_(v20, v16);
  }
  v21 = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v27, v21);
  CloudDataPenSettings::SaveFontAsync((SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher *)((char *)this + 216));
  std::wstring::_Tidy_deallocate(v26);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800191b0  mov     [rsp+arg_10], rbx
0x1800191b5  mov     [rsp+arg_18], rsi
0x1800191ba  push    rdi
0x1800191bb  sub     rsp, 90h
0x1800191c2  mov     rax, cs:__security_cookie
0x1800191c9  xor     rax, rsp
0x1800191cc  mov     [rsp+98h+var_18], rax
0x1800191d4  mov     rdi, rdx
0x1800191d7  mov     rsi, rcx
0x1800191da  mov     [rsp+98h+string], 0
0x1800191e3  mov     rax, [rdx]
0x1800191e6  mov     rbx, [rax+98h]
0x1800191ed  xor     ecx, ecx; string
0x1800191ef  call    cs:__imp_WindowsDeleteString
0x1800191f5  mov     [rsp+98h+string], 0
0x1800191fe  lea     rdx, [rsp+98h+string]
0x180019203  mov     rcx, rdi
0x180019206  mov     rax, rbx
0x180019209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001920e  mov     ebx, eax
0x180019210  test    eax, eax
0x180019212  jns     short loc_180019235
0x180019214  mov     rcx, [rsp+98h]; this
0x18001921c  mov     r9d, eax; char *
0x18001921f  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x180019226  mov     edx, 12Fh; void *
0x18001922b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019230  jmp     loc_1800192C9
0x180019235  xorps   xmm0, xmm0
0x180019238  movups  [rsp+98h+var_58], xmm0
0x18001923d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180019245  movdqu  [rsp+98h+var_48], xmm1
0x18001924b  xor     eax, eax
0x18001924d  mov     word ptr [rsp+98h+var_58], ax
0x180019252  lea     rcx, [rsp+98h+var_38]
0x180019257  call    Helpers__PenAndInkSettingsInternal__GetHandwritingViewRegKeySDDLForCurrentContext
0x18001925c  mov     rdx, rax
0x18001925f  lea     rcx, [rsp+98h+var_58]
0x180019264  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180019269  lea     rcx, [rsp+98h+var_38]
0x18001926e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019273  nop
0x180019274  lea     rcx, [rsp+98h+var_58]
0x180019279  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001927e  mov     rbx, rax
0x180019281  xor     edx, edx; length
0x180019283  mov     rcx, [rsp+98h+string]; string
0x180019288  call    cs:__imp_WindowsGetStringRawBuffer
0x18001928e  mov     qword ptr [rsp+98h+var_78], rbx; int
0x180019293  mov     r9, rax; unsigned __int16 *
0x180019296  call    ?SHRegSetStringWithSSDL@@YAJPEAUHKEY__@@PEBG111@Z; SHRegSetStringWithSSDL(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18001929b  mov     ebx, eax
0x18001929d  test    eax, eax
0x18001929f  jns     short loc_1800192DB
0x1800192a1  mov     rcx, [rsp+98h]; this
0x1800192a9  mov     r9d, eax; char *
0x1800192ac  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x1800192b3  mov     edx, 139h; void *
0x1800192b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800192bd  nop
0x1800192be  lea     rcx, [rsp+98h+var_58]
0x1800192c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800192c8  nop
0x1800192c9  mov     rcx, [rsp+98h+string]; string
0x1800192ce  call    cs:__imp_WindowsDeleteString
0x1800192d4  mov     eax, ebx
0x1800192d6  jmp     loc_180019366
0x1800192db  xor     edx, edx; length
0x1800192dd  mov     rcx, [rsp+98h+string]; string
0x1800192e2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800192e8  mov     rbx, rax
0x1800192eb  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800192f0  test    al, al
0x1800192f2  jz      short loc_180019308
0x1800192f4  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x1800192fb  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x180019300  mov     rdx, rbx; unsigned __int16 *
0x180019303  call    ?HandwritingFontSwitched_@PenSettingsTelemetry@@QEBAXPEBG@Z; PenSettingsTelemetry::HandwritingFontSwitched_(ushort const *)
0x180019308  xor     edx, edx; length
0x18001930a  mov     rcx, [rsp+98h+string]; string
0x18001930f  call    cs:__imp_WindowsGetStringRawBuffer
0x180019315  mov     rdx, rax
0x180019318  lea     rcx, [rsp+98h+var_38]
0x18001931d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180019322  lea     rcx, [rsi+0D8h]; struct wil::cloud_store *
0x180019329  mov     rdx, rax
0x18001932c  call    ?SaveFontAsync@CloudDataPenSettings@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CloudDataPenSettings::SaveFontAsync(std::wstring)
0x180019331  nop
0x180019332  lea     rcx, [rsp+98h+var_58]
0x180019337  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001933c  nop
0x18001933d  mov     rcx, [rsp+98h+string]; string
0x180019342  call    cs:__imp_WindowsDeleteString
0x180019348  xor     eax, eax
0x18001934a  jmp     short loc_180019366
0x18001934c  lea     rcx, [rsp+98h+var_58]
0x180019351  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019356  nop
0x180019357  mov     rcx, [rsp+98h+string]; string
0x18001935c  call    cs:__imp_WindowsDeleteString
0x180019362  mov     eax, [rsp+98h+var_60]
0x180019366  mov     rcx, [rsp+98h+var_18]
0x18001936e  xor     rcx, rsp; StackCookie
0x180019371  call    __security_check_cookie
0x180019376  lea     r11, [rsp+98h+var_8]
0x18001937e  mov     rbx, [r11+20h]
0x180019382  mov     rsi, [r11+28h]
0x180019386  mov     rsp, r11
0x180019389  pop     rdi
0x18001938a  retn
```
