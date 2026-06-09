# Windows::Internal::StringReference::StringReference(ushort const (&)[36])

- ea: `0x18002ed28`
- end: `0x18002ed6c`
- name: `??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[36])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ffe0`
- `0x180030138`

## callees

- `0x18002ed28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ed5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ed5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ed44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ed44`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[36])
{
  if ( WindowsCreateStringReference(
         L"Windows.System.Internal.UserManager",
         0x23u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002ed28  push    rbx
0x18002ed2a  sub     rsp, 20h
0x18002ed2e  mov     rbx, rcx
0x18002ed31  lea     r8, [rcx+8]; hstringHeader
0x18002ed35  mov     r9, rcx; string
0x18002ed38  mov     edx, 23h ; '#'; length
0x18002ed3d  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18002ed44  call    cs:__imp_WindowsCreateStringReference
0x18002ed4a  test    eax, eax
0x18002ed4c  jns     short loc_18002ED63
0x18002ed4e  xor     r9d, r9d; lpArguments
0x18002ed51  xor     r8d, r8d; nNumberOfArguments
0x18002ed54  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002ed59  lea     edx, [r9+1]; dwExceptionFlags
0x18002ed5d  call    cs:__imp_RaiseException
0x18002ed63  mov     rax, rbx
0x18002ed66  add     rsp, 20h
0x18002ed6a  pop     rbx
0x18002ed6b  retn
```
