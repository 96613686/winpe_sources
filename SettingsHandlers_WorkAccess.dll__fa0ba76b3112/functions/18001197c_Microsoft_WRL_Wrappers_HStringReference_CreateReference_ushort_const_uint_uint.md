# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001197c`
- end: `0x1800119b9`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `61`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c970`
- `0x18000fc74`
- `0x180013374`
- `0x180013b40`
- `0x1800178dc`
- `0x180018c94`
- `0x18001c00c`
- `0x18001d104`
- `0x18001d5c0`
- `0x1800201e0`
- `0x180024f44`
- `0x18002581c`
- `0x180026244`
- `0x180027bd8`
- `0x1800292c0`
- `0x180029360`
- `0x1800297d0`
- `0x18003a340`
- `0x180041620`
- `0x180041dc0`
- `0x180042640`
- `0x180042b8c`

## callees

- `0x18001197c`
- `0x180015c84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001199b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001199b`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  HRESULT StringReference; // eax
  int v6; // edx
  unsigned int v7; // r8d

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v6, v7);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x18001197c  sub     rsp, 28h
0x180011980  mov     eax, r9d
0x180011983  mov     r10, rdx
0x180011986  cmp     r9d, r8d
0x180011989  jb      short loc_18001198F
0x18001198b  lea     eax, [r8-1]
0x18001198f  lea     r9, [rcx+18h]; string
0x180011993  mov     r8, rcx; hstringHeader
0x180011996  mov     rcx, r10; sourceString
0x180011999  mov     edx, eax; length
0x18001199b  call    cs:__imp_WindowsCreateStringReference
0x1800119a2  nop     dword ptr [rax+rax+00h]
0x1800119a7  test    eax, eax
0x1800119a9  jns     short loc_1800119B3
0x1800119ab  mov     ecx, eax; this
0x1800119ad  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800119b2  int     3; Trap to Debugger
0x1800119b3  add     rsp, 28h
0x1800119b7  retn
```
