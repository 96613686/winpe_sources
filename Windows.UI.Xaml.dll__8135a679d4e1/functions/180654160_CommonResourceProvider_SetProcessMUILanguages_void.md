# CommonResourceProvider::SetProcessMUILanguages(void)

- ea: `0x180654160`
- end: `0x18065424c`
- name: `?SetProcessMUILanguages@CommonResourceProvider@@UEAAJXZ`
- size: `236`
- prototype: `HRESULT __fastcall(CommonResourceProvider *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18066aa70`

## callees

- `0x180004bc0`
- `0x180654160`
- `0x1806c06e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1806541f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1806541f5`
- `api-ms-win-core-localization-l1-2-0!SetProcessPreferredUILanguages` at `0x1806541eb`
- `api-ms-win-core-localization-l1-2-0!SetProcessPreferredUILanguages` at `0x1806541eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18065417a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806541aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18065422e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18065423e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18065417a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1806541aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18065422e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18065423e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806541db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1806541db`
- `Bcp47Langs!GetApplicationLanguages` at `0x180654197`
- `Bcp47Langs!GetApplicationLanguages` at `0x180654197`
- `Bcp47Langs!LanguageListAsMuiForm` at `0x1806541c8`
- `Bcp47Langs!LanguageListAsMuiForm` at `0x1806541c8`

## pseudocode

```c
__int64 __fastcall CommonResourceProvider::SetProcessMUILanguages(CommonResourceProvider *this)
{
  HRESULT v1; // ebx
  HRESULT v2; // eax
  const wchar_t *StringRawBuffer; // rax
  signed int LastError; // eax
  Windows::Internal::String languagesAsMui; // [rsp+38h] [rbp+10h] BYREF
  Windows::Internal::String languages; // [rsp+40h] [rbp+18h] BYREF

  languages._hstring = 0;
  languagesAsMui._hstring = 0;
  WindowsDeleteString(0);
  languages._hstring = 0;
  if ( (int)GetApplicationLanguages(0, 59, &languages) >= 0 )
  {
    WindowsDeleteString(languagesAsMui._hstring);
    languagesAsMui._hstring = 0;
    v2 = LanguageListAsMuiForm(59, languages._hstring, 0, &languagesAsMui);
    v1 = v2;
    if ( v2 < 0 )
    {
      OnFailure_2990_(v2);
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(languagesAsMui._hstring, 0);
      if ( !SetProcessPreferredUILanguages(8u, StringRawBuffer, 0) )
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        if ( v1 >= 0 )
          v1 = -2147467259;
        OnNewFailure_3049_(v1);
      }
    }
  }
  else
  {
    v1 = 0;
  }
  if ( languagesAsMui._hstring )
    WindowsDeleteString(languagesAsMui._hstring);
  if ( languages._hstring )
    WindowsDeleteString(languages._hstring);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180654160  push    rbx
0x180654162  sub     rsp, 20h
0x180654166  xor     ecx, ecx; string
0x180654168  mov     [rsp+28h+languages._hstring], 0
0x180654171  mov     [rsp+28h+languagesAsMui._hstring], 0
0x18065417a  call    cs:__imp_WindowsDeleteString
0x180654180  mov     ebx, 3Bh ; ';'
0x180654185  mov     [rsp+28h+languages._hstring], 0
0x18065418e  mov     edx, ebx
0x180654190  lea     r8, [rsp+28h+languages]
0x180654195  xor     ecx, ecx
0x180654197  call    cs:__imp_GetApplicationLanguages
0x18065419d  test    eax, eax
0x18065419f  jns     short loc_1806541A5
0x1806541a1  xor     ebx, ebx
0x1806541a3  jmp     short $Cleanup_5826
0x1806541a5  mov     this, [rsp+28h+languagesAsMui._hstring]; string
0x1806541aa  call    cs:__imp_WindowsDeleteString
0x1806541b0  mov     rdx, [rsp+28h+languages._hstring]
0x1806541b5  lea     r9, [rsp+28h+languagesAsMui]
0x1806541ba  xor     r8d, r8d
0x1806541bd  mov     [rsp+28h+languagesAsMui._hstring], 0
0x1806541c6  mov     ecx, ebx
0x1806541c8  call    cs:__imp_LanguageListAsMuiForm
0x1806541ce  mov     ebx, eax
0x1806541d0  test    eax, eax
0x1806541d2  js      short loc_18065421D
0x1806541d4  mov     this, [rsp+28h+languagesAsMui._hstring]; string
0x1806541d9  xor     edx, edx; length
0x1806541db  call    cs:__imp_WindowsGetStringRawBuffer
0x1806541e1  xor     r8d, r8d; pulNumLanguages
0x1806541e4  mov     rdx, rax; pwszLanguagesBuffer
0x1806541e7  lea     ecx, [r8+8]; dwFlags
0x1806541eb  call    cs:__imp_SetProcessPreferredUILanguages
0x1806541f1  test    eax, eax
0x1806541f3  jnz     short $Cleanup_5826
0x1806541f5  call    cs:__imp_GetLastError
0x1806541fb  mov     ebx, eax
0x1806541fd  test    eax, eax
0x1806541ff  jle     short loc_18065420A
0x180654201  movzx   ebx, ax
0x180654204  or      ebx, 80070000h
0x18065420a  test    ebx, ebx
0x18065420c  mov     eax, 80004005h
0x180654211  cmovns  ebx, eax
0x180654214  mov     ecx, ebx; failedFrameHR
0x180654216  call    OnNewFailure_3049_
0x18065421b  jmp     short $Cleanup_5826
0x18065421d  mov     ecx, eax; failedFrameHR
0x18065421f  call    OnFailure_2990_
0x180654224  mov     this, [rsp+28h+languagesAsMui._hstring]; string
0x180654229  test    this, this
0x18065422c  jz      short loc_180654234
0x18065422e  call    cs:__imp_WindowsDeleteString
0x180654234  mov     this, [rsp+28h+languages._hstring]; string
0x180654239  test    this, this
0x18065423c  jz      short loc_180654244
0x18065423e  call    cs:__imp_WindowsDeleteString
0x180654244  mov     eax, ebx
0x180654246  add     rsp, 20h
0x18065424a  pop     rbx
0x18065424b  retn
```
