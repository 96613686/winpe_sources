# SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode::SetValue(Windows::Foundation::IPropertyValue *)

- ea: `0x1800399a0`
- end: `0x180039bb0`
- name: `?SetValue@CDevicesPenHandwritingInvokeMode@PenSettings@SystemSettings@@UEAAJPEAUIPropertyValue@Foundation@Windows@@@Z`
- size: `528`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode *__hidden this, struct Windows::Foundation::IPropertyValue *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a2bc`
- `0x1800115d8`
- `0x1800134b8`
- `0x1800167f8`
- `0x180018954`
- `0x180019fcc`
- `0x18001a378`
- `0x18001a604`
- `0x1800326a4`
- `0x1800338d4`
- `0x180037958`
- `0x180038928`
- `0x1800389e0`
- `0x1800399a0`
- `0x18004c444`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039af5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800399dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039af5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039b82`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180039b15`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180039b15`

## string_xrefs

- `0x180039a0d`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`
- `0x180039ad3`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode::SetValue(
        SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode *this,
        struct Windows::Foundation::IPropertyValue *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Foundation::IPropertyValue *, HSTRING *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // esi
  __int64 HandwritingViewRegKeySDDLForCurrentContext; // rax
  unsigned int v10; // edi
  const unsigned __int16 *v11; // rbx
  SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode *v12; // rcx
  const unsigned __int16 *HandwritingSettingsRegKey; // rax
  HKEY v14; // rcx
  int v15; // eax
  const char *v16; // r9
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  __int64 v21; // rcx
  PenSettingsTelemetry *v22; // rcx
  unsigned int v23; // [rsp+20h] [rbp-88h]
  unsigned int v24; // [rsp+20h] [rbp-88h]
  HSTRING string; // [rsp+30h] [rbp-78h] BYREF
  int v26; // [rsp+38h] [rbp-70h] BYREF
  unsigned int v27; // [rsp+3Ch] [rbp-6Ch]
  _OWORD v28[2]; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v29[32]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

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
      (void *)0x33A,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
      (const char *)(unsigned int)v5,
      v23);
LABEL_13:
    WindowsDeleteString(string);
    return v6;
  }
  v7 = SystemSettings::PenSettings::FindEnumFromStringArray<enum SystemSettings::PenSettings::IhmDesktopPenInvoke,SystemSettings::PenSettings::InvokeTypeResourceMapping_>((SystemSettings::DataModel *)string);
  try
  {
    v8 = v7;
    v28[0] = 0;
    v28[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v28[0]) = 0;
    HandwritingViewRegKeySDDLForCurrentContext = Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContext(v29);
    std::wstring::operator=(v28, HandwritingViewRegKeySDDLForCurrentContext);
    std::wstring::_Tidy_deallocate(v29);
    if ( (unsigned __int8)anonymous_namespace_::IsDesktopSKU() )
    {
      v10 = 0;
      if ( v8 == 1 )
      {
        v10 = 1;
      }
      else if ( v8 == 2 )
      {
        v10 = 2;
      }
    }
    else
    {
      v10 = v8;
    }
    v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    HandwritingSettingsRegKey = SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode::GetHandwritingSettingsRegKey(v12);
    v15 = SHRegSetDWORDWithSSDL(v14, HandwritingSettingsRegKey, L"EnableDesktopModePenAutoInvoke", v11, v10);
  }
  catch ( ... )
  {
    v27 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x342,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
            v16);
    std::wstring::_Tidy_deallocate(v28);
    WindowsDeleteString(string);
    return v27;
  }
  v6 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35B,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
      (const char *)(unsigned int)v15,
      v24);
    std::wstring::_Tidy_deallocate(v28);
    goto LABEL_13;
  }
  SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"touch keyboard");
  v26 = 1;
  wil::wnf_publish<unsigned long>(v18, &v26);
  if ( PenSettingsTelemetry::IsEnabled(v20, v19) )
  {
    wil::details::static_lazy<PenSettingsTelemetry>::get(
      v21,
      _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_);
    PenSettingsTelemetry::HandwritingAutoInvokeValue_(v22, v8);
  }
  CloudDataPenSettings::SavePanelBehaviorAsync(
    (SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode *)((char *)this + 232),
    v10);
  std::wstring::_Tidy_deallocate(v28);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800399a0  mov     [rsp+arg_10], rbx
0x1800399a5  push    rsi
0x1800399a6  push    rdi
0x1800399a7  push    r14
0x1800399a9  sub     rsp, 90h
0x1800399b0  mov     rax, cs:__security_cookie
0x1800399b7  xor     rax, rsp
0x1800399ba  mov     [rsp+0A8h+var_28], rax
0x1800399c2  mov     rdi, rdx
0x1800399c5  mov     r14, rcx
0x1800399c8  mov     [rsp+0A8h+string], 0
0x1800399d1  mov     rax, [rdx]
0x1800399d4  mov     rbx, [rax+98h]
0x1800399db  xor     ecx, ecx; string
0x1800399dd  call    cs:__imp_WindowsDeleteString
0x1800399e3  mov     [rsp+0A8h+string], 0
0x1800399ec  lea     rdx, [rsp+0A8h+string]
0x1800399f1  mov     rcx, rdi
0x1800399f4  mov     rax, rbx
0x1800399f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399fc  mov     ebx, eax
0x1800399fe  test    eax, eax
0x180039a00  jns     short loc_180039A23
0x180039a02  mov     rcx, [rsp+0A8h]; this
0x180039a0a  mov     r9d, eax; char *
0x180039a0d  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180039a14  mov     edx, 33Ah; void *
0x180039a19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a1e  jmp     loc_180039AF0
0x180039a23  lea     rdx, [r14+0D0h]
0x180039a2a  mov     rcx, [rsp+0A8h+string]; this
0x180039a2f  call    ??$FindEnumFromStringArray@W4IhmDesktopPenInvoke@PenSettings@SystemSettings@@UInvokeTypeResourceMapping_@23@@PenSettings@SystemSettings@@YA?AW4IhmDesktopPenInvoke@01@PEAUHSTRING__@@AEBV?$vector@UInvokeTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UInvokeTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@@Z; SystemSettings::PenSettings::FindEnumFromStringArray<SystemSettings::PenSettings::IhmDesktopPenInvoke,SystemSettings::PenSettings::InvokeTypeResourceMapping_>(HSTRING__ *,std::vector<SystemSettings::PenSettings::InvokeTypeResourceMapping_> const &)
0x180039a34  mov     esi, eax
0x180039a36  xorps   xmm0, xmm0
0x180039a39  movups  [rsp+0A8h+var_68], xmm0
0x180039a3e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180039a46  movdqu  [rsp+0A8h+var_58], xmm1
0x180039a4c  xor     ecx, ecx
0x180039a4e  mov     word ptr [rsp+0A8h+var_68], cx
0x180039a53  lea     rcx, [rsp+0A8h+var_48]
0x180039a58  call    Helpers__PenAndInkSettingsInternal__GetHandwritingViewRegKeySDDLForCurrentContext
0x180039a5d  mov     rdx, rax
0x180039a60  lea     rcx, [rsp+0A8h+var_68]
0x180039a65  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180039a6a  lea     rcx, [rsp+0A8h+var_48]
0x180039a6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039a74  nop
0x180039a75  call    _anonymous_namespace___IsDesktopSKU
0x180039a7a  test    al, al
0x180039a7c  jz      short loc_180039A98
0x180039a7e  xor     edi, edi
0x180039a80  mov     ecx, esi
0x180039a82  sub     ecx, 1
0x180039a85  jz      short loc_180039A91
0x180039a87  sub     ecx, 1
0x180039a8a  jnz     short loc_180039A9A
0x180039a8c  lea     edi, [rcx+2]
0x180039a8f  jmp     short loc_180039A9A
0x180039a91  mov     edi, 1
0x180039a96  jmp     short loc_180039A9A
0x180039a98  mov     edi, esi
0x180039a9a  lea     rcx, [rsp+0A8h+var_68]
0x180039a9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039aa4  mov     rbx, rax
0x180039aa7  call    ?GetHandwritingSettingsRegKey@CDevicesPenHandwritingInvokeMode@PenSettings@SystemSettings@@AEAAPEBGXZ; SystemSettings::PenSettings::CDevicesPenHandwritingInvokeMode::GetHandwritingSettingsRegKey(void)
0x180039aac  mov     [rsp+0A8h+var_88], edi; int
0x180039ab0  mov     r9, rbx; unsigned __int16 *
0x180039ab3  lea     r8, aEnabledesktopm; "EnableDesktopModePenAutoInvoke"
0x180039aba  mov     rdx, rax; unsigned __int16 *
0x180039abd  call    ?SHRegSetDWORDWithSSDL@@YAJPEAUHKEY__@@PEBG11K@Z; SHRegSetDWORDWithSSDL(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)
0x180039ac2  mov     ebx, eax
0x180039ac4  test    eax, eax
0x180039ac6  jns     short loc_180039B02
0x180039ac8  mov     rcx, [rsp+0A8h]; this
0x180039ad0  mov     r9d, eax; char *
0x180039ad3  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180039ada  mov     edx, 35Bh; void *
0x180039adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ae4  nop
0x180039ae5  lea     rcx, [rsp+0A8h+var_68]
0x180039aea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039aef  nop
0x180039af0  mov     rcx, [rsp+0A8h+string]; string
0x180039af5  call    cs:__imp_WindowsDeleteString
0x180039afb  mov     eax, ebx
0x180039afd  jmp     loc_180039B8C
0x180039b02  lea     r9, lParam; "touch keyboard"
0x180039b09  xor     r8d, r8d; wParam
0x180039b0c  lea     edx, [r8+1Ah]; Msg
0x180039b10  mov     ecx, 0FFFFh; hWnd
0x180039b15  call    cs:__imp_SendNotifyMessageW
0x180039b1b  mov     [rsp+0A8h+var_70], 1
0x180039b23  lea     rdx, [rsp+0A8h+var_70]
0x180039b28  call    ??$wnf_publish@K@wil@@YAXAEBU_WNF_STATE_NAME@@AEBK@Z; wil::wnf_publish<ulong>(_WNF_STATE_NAME const &,ulong const &)
0x180039b2d  call    ?IsEnabled@PenSettingsTelemetry@@SA_NE_K@Z; PenSettingsTelemetry::IsEnabled(uchar,unsigned __int64)
0x180039b32  test    al, al
0x180039b34  jz      short loc_180039B49
0x180039b36  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8d9dd6361aec234160fdb7676f9b4750_@@CA@XZ; _lambda_8d9dd6361aec234160fdb7676f9b4750_::_lambda_invoker_cdecl_(void)
0x180039b3d  call    ?get@?$static_lazy@VPenSettingsTelemetry@@@details@wil@@QEAAPEAVPenSettingsTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PenSettingsTelemetry>::get(void (*)(void))
0x180039b42  mov     edx, esi; unsigned int
0x180039b44  call    ?HandwritingAutoInvokeValue_@PenSettingsTelemetry@@QEBAXI@Z; PenSettingsTelemetry::HandwritingAutoInvokeValue_(uint)
0x180039b49  lea     rcx, [r14+0E8h]; this
0x180039b50  mov     edx, edi; unsigned int
0x180039b52  call    ?SavePanelBehaviorAsync@CloudDataPenSettings@@QEAAXK@Z; CloudDataPenSettings::SavePanelBehaviorAsync(ulong)
0x180039b57  nop
0x180039b58  lea     rcx, [rsp+0A8h+var_68]
0x180039b5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039b62  nop
0x180039b63  mov     rcx, [rsp+0A8h+string]; string
0x180039b68  call    cs:__imp_WindowsDeleteString
0x180039b6e  xor     eax, eax
0x180039b70  jmp     short loc_180039B8C
0x180039b72  lea     rcx, [rsp+0A8h+var_68]
0x180039b77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039b7c  nop
0x180039b7d  mov     rcx, [rsp+0A8h+string]; string
0x180039b82  call    cs:__imp_WindowsDeleteString
0x180039b88  mov     eax, [rsp+0A8h+var_6C]
0x180039b8c  mov     rcx, [rsp+0A8h+var_28]
0x180039b94  xor     rcx, rsp; StackCookie
0x180039b97  call    __security_check_cookie
0x180039b9c  mov     rbx, [rsp+0A8h+arg_10]
0x180039ba4  add     rsp, 90h
0x180039bab  pop     r14
0x180039bad  pop     rdi
0x180039bae  pop     rsi
0x180039baf  retn
```
