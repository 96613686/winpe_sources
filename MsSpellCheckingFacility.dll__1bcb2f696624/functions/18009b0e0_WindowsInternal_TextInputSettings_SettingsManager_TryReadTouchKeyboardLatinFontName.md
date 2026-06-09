# WindowsInternal::TextInputSettings::SettingsManager::TryReadTouchKeyboardLatinFontName

- ea: `0x18009b0e0`
- end: `0x18009b18b`
- name: `WindowsInternal::TextInputSettings::SettingsManager::TryReadTouchKeyboardLatinFontName`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18004d0b4`
- `0x180099754`
- `0x18009a8a4`
- `0x18009b0e0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b14d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b14d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b114`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b114`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009b173`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall WindowsInternal::TextInputSettings::SettingsManager::TryReadTouchKeyboardLatinFontName(
        __int64 a1,
        WindowsInternal::TextInputSettings::SettingsManager::SettingValue *a2)
{
  __int64 PenAndInkSettings; // rax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rax
  char result; // al
  HSTRING string; // [rsp+40h] [rbp+18h] BYREF
  char v9; // [rsp+48h] [rbp+20h] BYREF

  string = 0;
  PenAndInkSettings = WindowsInternal::TextInputSettings::SettingsManager::GetPenAndInkSettings(&v9);
  v4 = *(_QWORD *)PenAndInkSettings;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)PenAndInkSettings + 72LL);
  WindowsDeleteString(string);
  string = 0;
  LODWORD(v5) = v5(v4, &string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  if ( (int)v5 < 0 )
  {
LABEL_3:
    WindowsDeleteString(string);
    return 0;
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    try
    {
      WindowsInternal::TextInputSettings::SettingsManager::SettingValue::SetValue(a2, StringRawBuffer);
      WindowsDeleteString(string);
      result = 1;
    }
    catch ( ... )
    {
      goto LABEL_3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18009b0e0  mov     rax, rsp
0x18009b0e3  mov     [rax+8], rbx
0x18009b0e7  mov     [rax+10h], rsi
0x18009b0eb  push    rdi
0x18009b0ec  sub     rsp, 20h
0x18009b0f0  mov     rsi, rdx
0x18009b0f3  mov     qword ptr [rax+18h], 0
0x18009b0fb  lea     rcx, [rax+20h]
0x18009b0ff  call    WindowsInternal__TextInputSettings__SettingsManager__GetPenAndInkSettings
0x18009b104  nop
0x18009b105  mov     rdi, [rax]
0x18009b108  mov     rax, [rdi]
0x18009b10b  mov     rbx, [rax+48h]
0x18009b10f  mov     rcx, [rsp+28h+string]; string
0x18009b114  call    cs:__imp_WindowsDeleteString
0x18009b11a  mov     [rsp+28h+string], 0
0x18009b123  lea     rdx, [rsp+28h+string]
0x18009b128  mov     rcx, rdi
0x18009b12b  mov     rax, rbx
0x18009b12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b133  mov     ebx, eax
0x18009b135  lea     rcx, [rsp+28h+arg_18]
0x18009b13a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009b13f  shr     ebx, 1Fh
0x18009b142  test    bl, bl
0x18009b144  jnz     short loc_18009B16E
0x18009b146  xor     edx, edx; length
0x18009b148  mov     rcx, [rsp+28h+string]; string
0x18009b14d  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b153  mov     rdx, rax; wchar_t *
0x18009b156  mov     rcx, rsi; this
0x18009b159  call    ?SetValue@SettingValue@SettingsManager@TextInputSettings@WindowsInternal@@QEAAXPEB_W@Z; WindowsInternal::TextInputSettings::SettingsManager::SettingValue::SetValue(wchar_t const *)
0x18009b15e  nop
0x18009b15f  mov     rcx, [rsp+28h+string]; string
0x18009b164  call    cs:__imp_WindowsDeleteString
0x18009b16a  mov     al, 1
0x18009b16c  jmp     short loc_18009B17B
0x18009b16e  mov     rcx, [rsp+28h+string]; string
0x18009b173  call    cs:__imp_WindowsDeleteString
0x18009b179  xor     al, al
0x18009b17b  mov     rbx, [rsp+28h+arg_0]
0x18009b180  mov     rsi, [rsp+28h+arg_8]
0x18009b185  add     rsp, 20h
0x18009b189  pop     rdi
0x18009b18a  retn
```
