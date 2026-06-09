# OSGetLanguageStatics

- ea: `0x180062714`
- end: `0x18006277f`
- name: `OSGetLanguageStatics`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180062668`

## callees

- `0x180062714`
- `0x180062788`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006272c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006276c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006272c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006276c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006274c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006274c`

## pseudocode

```c
__int64 __fastcall OSGetLanguageStatics(__int64 a1)
{
  unsigned int v2; // ebx
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v2 = WindowsCreateString(L"Windows.Globalization.Language", 0x1Eu, &string);
  if ( !v2 )
    v2 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(
           string,
           a1);
  WindowsDeleteString(string);
  return v2;
}

```

## disassembly

```asm
0x180062714  mov     [rsp+arg_0], rbx
0x180062719  push    rdi
0x18006271a  sub     rsp, 20h
0x18006271e  mov     rdi, rcx
0x180062721  mov     [rsp+28h+string], 0
0x18006272a  xor     ecx, ecx; string
0x18006272c  call    cs:__imp_WindowsDeleteString
0x180062732  lea     r8, [rsp+28h+string]; string
0x180062737  mov     [rsp+28h+string], 0
0x180062740  mov     edx, 1Eh; length
0x180062745  lea     rcx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x18006274c  call    cs:__imp_WindowsCreateString
0x180062752  mov     ebx, eax
0x180062754  test    eax, eax
0x180062756  jnz     short loc_180062767
0x180062758  mov     rcx, [rsp+28h+string]
0x18006275d  mov     rdx, rdi
0x180062760  call    ??$GetActivationFactory@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>)
0x180062765  mov     ebx, eax
0x180062767  mov     rcx, [rsp+28h+string]; string
0x18006276c  call    cs:__imp_WindowsDeleteString
0x180062772  mov     eax, ebx
0x180062774  mov     rbx, [rsp+28h+arg_0]
0x180062779  add     rsp, 20h
0x18006277d  pop     rdi
0x18006277e  retn
```
