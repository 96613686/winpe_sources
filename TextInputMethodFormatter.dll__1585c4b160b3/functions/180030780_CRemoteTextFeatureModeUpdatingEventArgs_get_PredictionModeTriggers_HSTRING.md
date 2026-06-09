# CRemoteTextFeatureModeUpdatingEventArgs::get_PredictionModeTriggers(HSTRING__ * *)

- ea: `0x180030780`
- end: `0x1800307ef`
- name: `?get_PredictionModeTriggers@CRemoteTextFeatureModeUpdatingEventArgs@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(CRemoteTextFeatureModeUpdatingEventArgs *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180030780`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800307a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800307dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800307a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800307dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800307ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800307ba`

## pseudocode

```c
__int64 __fastcall CRemoteTextFeatureModeUpdatingEventArgs::get_PredictionModeTriggers(
        CRemoteTextFeatureModeUpdatingEventArgs *this,
        HSTRING *a2)
{
  HSTRING v3; // rbx
  HRESULT v4; // ebx
  HSTRING v5; // rdx
  HSTRING v6; // rcx
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = (HSTRING)*((_QWORD *)this + 12);
  newString = 0;
  WindowsDeleteString(0);
  newString = 0;
  v4 = WindowsDuplicateString(v3, &newString);
  if ( v4 < 0 )
  {
    v6 = newString;
  }
  else
  {
    v5 = newString;
    v6 = 0;
    newString = 0;
    *a2 = v5;
  }
  WindowsDeleteString(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030780  mov     [rsp+arg_8], rbx
0x180030785  push    rdi
0x180030786  sub     rsp, 20h
0x18003078a  mov     qword ptr [rdx], 0
0x180030791  mov     rdi, rdx
0x180030794  mov     rbx, [rcx+60h]
0x180030798  xor     ecx, ecx; string
0x18003079a  mov     [rsp+28h+newString], 0
0x1800307a3  call    cs:__imp_WindowsDeleteString
0x1800307a9  lea     rdx, [rsp+28h+newString]; newString
0x1800307ae  mov     [rsp+28h+newString], 0
0x1800307b7  mov     rcx, rbx; string
0x1800307ba  call    cs:__imp_WindowsDuplicateString
0x1800307c0  mov     ebx, eax
0x1800307c2  test    eax, eax
0x1800307c4  js      short loc_1800307D7
0x1800307c6  mov     rdx, [rsp+28h+newString]
0x1800307cb  xor     ecx, ecx
0x1800307cd  mov     [rsp+28h+newString], rcx
0x1800307d2  mov     [rdi], rdx
0x1800307d5  jmp     short loc_1800307DC
0x1800307d7  mov     rcx, [rsp+28h+newString]; string
0x1800307dc  call    cs:__imp_WindowsDeleteString
0x1800307e2  mov     eax, ebx
0x1800307e4  mov     rbx, [rsp+28h+arg_8]
0x1800307e9  add     rsp, 20h
0x1800307ed  pop     rdi
0x1800307ee  retn
```
