# Windows::Internal::StringReference::StringReference(ushort const (&)[20])

- ea: `0x18002ecdc`
- end: `0x18002ed20`
- name: `??$?0$0BE@@StringReference@Internal@Windows@@QEAA@AEAY0BE@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[20])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002fd20`

## callees

- `0x18002ecdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ed11`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ed11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ecf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ecf8`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[20])
{
  if ( WindowsCreateStringReference(L"Windows.System.User", 0x13u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002ecdc  push    rbx
0x18002ecde  sub     rsp, 20h
0x18002ece2  mov     rbx, rcx
0x18002ece5  lea     r8, [rcx+8]; hstringHeader
0x18002ece9  mov     r9, rcx; string
0x18002ecec  mov     edx, 13h; length
0x18002ecf1  lea     rcx, ?RuntimeClass_Windows_System_User@@3QBGB; "Windows.System.User"
0x18002ecf8  call    cs:__imp_WindowsCreateStringReference
0x18002ecfe  test    eax, eax
0x18002ed00  jns     short loc_18002ED17
0x18002ed02  xor     r9d, r9d; lpArguments
0x18002ed05  xor     r8d, r8d; nNumberOfArguments
0x18002ed08  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002ed0d  lea     edx, [r9+1]; dwExceptionFlags
0x18002ed11  call    cs:__imp_RaiseException
0x18002ed17  mov     rax, rbx
0x18002ed1a  add     rsp, 20h
0x18002ed1e  pop     rbx
0x18002ed1f  retn
```
