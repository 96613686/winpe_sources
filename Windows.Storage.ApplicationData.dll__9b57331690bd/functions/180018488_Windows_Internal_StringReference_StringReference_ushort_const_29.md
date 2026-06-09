# Windows::Internal::StringReference::StringReference(ushort const (&)[29])

- ea: `0x180018488`
- end: `0x1800184ce`
- name: `??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z`
- size: `70`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[29])`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18002111c`
- `0x180036358`
- `0x180036c9c`
- `0x18003e5f4`

## callees

- `0x180018488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800184c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800184c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800184a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800184a4`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[29])
{
  if ( WindowsCreateStringReference(RuntimeClass_Windows_Storage_KnownFolders, 0x1Cu, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x180018488  push    rbx
0x18001848a  sub     rsp, 20h
0x18001848e  mov     rbx, this
0x180018491  lea     r8, [this+8]; hstringHeader
0x180018495  mov     r9, this; string
0x180018498  mov     edx, 1Ch; length
0x18001849d  lea     this, ?RuntimeClass_Windows_Storage_KnownFolders@@3QBGB; sourceString
0x1800184a4  call    cs:__imp_WindowsCreateStringReference
0x1800184aa  test    eax, eax
0x1800184ac  js      short loc_1800184B7
0x1800184ae  mov     rax, rbx
0x1800184b1  add     rsp, 20h
0x1800184b5  pop     rbx
0x1800184b6  retn
0x1800184b7  xor     r9d, r9d; lpArguments
0x1800184ba  xor     r8d, r8d; nNumberOfArguments
0x1800184bd  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800184c2  lea     edx, [r9+1]; dwExceptionFlags
0x1800184c6  call    cs:__imp_RaiseException
0x1800184cc  jmp     short loc_1800184AE
```
