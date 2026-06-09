# Windows::Internal::StringReference::StringReference(ushort const (&)[36])

- ea: `0x18001c6d0`
- end: `0x18001c716`
- name: `??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z`
- size: `70`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[36])`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001fd04`
- `0x180029ad8`
- `0x180029bfc`
- `0x18003f524`

## callees

- `0x18001c6d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c70e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c70e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c6ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c6ec`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[36])
{
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_System_Internal_UserManager,
         0x23u,
         &this->_header,
         &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x18001c6d0  push    rbx
0x18001c6d2  sub     rsp, 20h
0x18001c6d6  mov     rbx, this
0x18001c6d9  lea     r8, [this+8]; hstringHeader
0x18001c6dd  mov     r9, this; string
0x18001c6e0  mov     edx, 23h ; '#'; length
0x18001c6e5  lea     this, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; sourceString
0x18001c6ec  call    cs:__imp_WindowsCreateStringReference
0x18001c6f2  test    eax, eax
0x18001c6f4  js      short loc_18001C6FF
0x18001c6f6  mov     rax, rbx
0x18001c6f9  add     rsp, 20h
0x18001c6fd  pop     rbx
0x18001c6fe  retn
0x18001c6ff  xor     r9d, r9d; lpArguments
0x18001c702  xor     r8d, r8d; nNumberOfArguments
0x18001c705  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001c70a  lea     edx, [r9+1]; dwExceptionFlags
0x18001c70e  call    cs:__imp_RaiseException
0x18001c714  jmp     short loc_18001C6F6
```
