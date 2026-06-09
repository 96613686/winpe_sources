# Microsoft::WRL::Wrappers::HStringReference::CreateReference(wchar_t const *,uint,uint)

- ea: `0x140048208`
- end: `0x140048249`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEB_WII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140047408`
- `0x140047874`

## callees

- `0x140048208`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004823d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14004823d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140048227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140048227`

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

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x140048208  sub     rsp, 28h
0x14004820c  mov     eax, r9d
0x14004820f  mov     r10, rdx
0x140048212  cmp     r9d, r8d
0x140048215  jb      short loc_14004821B
0x140048217  lea     eax, [r8-1]
0x14004821b  lea     r9, [rcx+18h]; string
0x14004821f  mov     r8, rcx; hstringHeader
0x140048222  mov     rcx, r10; sourceString
0x140048225  mov     edx, eax; length
0x140048227  call    cs:__imp_WindowsCreateStringReference
0x14004822d  test    eax, eax
0x14004822f  jns     short loc_140048244
0x140048231  xor     r9d, r9d; lpArguments
0x140048234  xor     r8d, r8d; nNumberOfArguments
0x140048237  mov     ecx, eax; dwExceptionCode
0x140048239  lea     edx, [r9+1]; dwExceptionFlags
0x14004823d  call    cs:__imp_RaiseException
0x140048243  int     3; Trap to Debugger
0x140048244  add     rsp, 28h
0x140048248  retn
```
