# Pal::UserLanguageSettingsImplWindows::getLanguageFallbackList(void)

- ea: `0x180017ad8`
- end: `0x180017c9b`
- name: `?getLanguageFallbackList@UserLanguageSettingsImplWindows@Pal@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001efcc`

## callees

- `0x1800094a0`
- `0x18000b4b8`
- `0x18000ba50`
- `0x18000c3d0`
- `0x18000d5f0`
- `0x180012ca4`
- `0x180017ad8`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017bd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017bfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017bfa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017b65`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180017b65`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Pal::UserLanguageSettingsImplWindows::getLanguageFallbackList(__int64 a1)
{
  __int64 v2; // rbx
  unsigned int i; // r14d
  __int64 v4; // rdi
  void (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v12; // [rsp+20h] [rbp-60h] BYREF
  __int64 v13; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  __int64 v15; // [rsp+38h] [rbp-48h] BYREF
  int v16; // [rsp+40h] [rbp-40h]
  __int64 v17; // [rsp+48h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+68h] [rbp-18h]

  v17 = a1;
  v15 = 0;
  v13 = 0;
  std::wstring::wstring(a1);
  v16 = 1;
  v19 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.System.UserProfile.GlobalizationPreferences",
    0x34u,
    0x33u);
  v2 = v19;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  if ( (int)RoGetActivationFactory(v2, &GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158, &v15) >= 0
    && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 72LL))(v15, &v13) >= 0 )
  {
    v12 = 0;
    if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v13 + 56LL))(v13, &v12) >= 0 )
    {
      for ( i = 0; i < v12; ++i )
      {
        string = 0;
        v4 = v13;
        v5 = *(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v13 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v5(v4, i, &string);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v7 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
        std::wstring::_Append<unsigned short>(a1, v8, v7);
        v9 = std::_WChar_traits<unsigned short>::length(L";");
        std::wstring::_Append<unsigned short>(a1, L";", v9);
        WindowsDeleteString(string);
      }
    }
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return a1;
}

```

## disassembly

```asm
0x180017ad8  mov     [rsp-18h+arg_8], rbx
0x180017add  mov     [rsp-18h+arg_10], rsi
0x180017ae2  push    rbp
0x180017ae3  push    rdi
0x180017ae4  push    r14
0x180017ae6  mov     rbp, rsp
0x180017ae9  sub     rsp, 80h
0x180017af0  mov     rax, cs:__security_cookie
0x180017af7  xor     rax, rsp
0x180017afa  mov     [rbp+var_10], rax
0x180017afe  mov     rsi, rcx
0x180017b01  mov     [rbp+var_38], rcx
0x180017b05  mov     [rbp+var_40], 0
0x180017b0c  mov     [rbp+var_48], 0
0x180017b14  mov     [rbp+var_58], 0
0x180017b1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017b21  mov     [rbp+var_40], 1
0x180017b28  mov     [rbp+var_18], 0
0x180017b30  mov     r9d, 33h ; '3'; unsigned int
0x180017b36  lea     r8d, [r9+1]; unsigned int
0x180017b3a  lea     rdx, ?RuntimeClass_Windows_System_UserProfile_GlobalizationPreferences@@3QBGB; "Windows.System.UserProfile.Globalizatio"...
0x180017b41  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180017b45  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180017b4a  mov     rbx, [rbp+var_18]
0x180017b4e  lea     rcx, [rbp+var_48]
0x180017b52  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017b57  lea     r8, [rbp+var_48]
0x180017b5b  lea     rdx, _GUID_01bf4326_ed37_4e96_b0e9_c1340d1ea158
0x180017b62  mov     rcx, rbx
0x180017b65  call    cs:__imp_RoGetActivationFactory
0x180017b6b  test    eax, eax
0x180017b6d  js      loc_180017C4C
0x180017b73  mov     rcx, [rbp+var_48]
0x180017b77  mov     rax, [rcx]
0x180017b7a  lea     rdx, [rbp+var_58]
0x180017b7e  mov     rax, [rax+48h]
0x180017b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b87  test    eax, eax
0x180017b89  js      loc_180017C4C
0x180017b8f  mov     [rbp+var_60], 0
0x180017b96  mov     rcx, [rbp+var_58]
0x180017b9a  mov     rax, [rcx]
0x180017b9d  lea     rdx, [rbp+var_60]
0x180017ba1  mov     rax, [rax+38h]
0x180017ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017baa  test    eax, eax
0x180017bac  js      loc_180017C4C
0x180017bb2  xor     r14d, r14d
0x180017bb5  cmp     [rbp+var_60], r14d
0x180017bb9  jbe     loc_180017C4C
0x180017bbf  mov     [rbp+string], 0
0x180017bc7  mov     rdi, [rbp+var_58]
0x180017bcb  mov     rax, [rdi]
0x180017bce  mov     rbx, [rax+30h]
0x180017bd2  xor     ecx, ecx; string
0x180017bd4  call    cs:__imp_WindowsDeleteString
0x180017bda  mov     [rbp+string], 0
0x180017be2  lea     r8, [rbp+string]
0x180017be6  mov     edx, r14d
0x180017be9  mov     rcx, rdi
0x180017bec  mov     rax, rbx
0x180017bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bf4  xor     edx, edx; length
0x180017bf6  mov     rcx, [rbp+string]; string
0x180017bfa  call    cs:__imp_WindowsGetStringRawBuffer
0x180017c00  mov     rcx, rax
0x180017c03  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180017c08  mov     r8, rax
0x180017c0b  mov     rdx, rcx
0x180017c0e  mov     rcx, rsi
0x180017c11  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180017c16  lea     rcx, asc_180048758; ";"
0x180017c1d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180017c22  mov     r8, rax
0x180017c25  lea     rdx, asc_180048758; ";"
0x180017c2c  mov     rcx, rsi
0x180017c2f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180017c34  nop
0x180017c35  mov     rcx, [rbp+string]; string
0x180017c39  call    cs:__imp_WindowsDeleteString
0x180017c3f  inc     r14d
0x180017c42  cmp     r14d, [rbp+var_60]
0x180017c46  jb      loc_180017BBF
0x180017c4c  mov     rcx, [rbp+var_58]
0x180017c50  test    rcx, rcx
0x180017c53  jz      short loc_180017C6A
0x180017c55  mov     [rbp+var_58], 0
0x180017c5d  mov     rdx, [rcx]
0x180017c60  mov     rax, [rdx+10h]
0x180017c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c69  nop
0x180017c6a  lea     rcx, [rbp+var_48]
0x180017c6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017c73  mov     rax, rsi
0x180017c76  mov     rcx, [rbp+var_10]
0x180017c7a  xor     rcx, rsp; StackCookie
0x180017c7d  call    __security_check_cookie
0x180017c82  lea     r11, [rsp+80h+var_s0]
0x180017c8a  mov     rbx, [r11+28h]
0x180017c8e  mov     rsi, [r11+30h]
0x180017c92  mov     rsp, r11
0x180017c95  pop     r14
0x180017c97  pop     rdi
0x180017c98  pop     rbp
0x180017c99  retn
```
