# Windows::Internal::StringReference::StringReference(ushort const (&)[26])

- ea: `0x1800159a8`
- end: `0x1800159ec`
- name: `??$?0$0BK@@StringReference@Internal@Windows@@QEAA@AEAY0BK@$$CBG@Z`
- size: `68`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[26])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ae0`

## callees

- `0x1800159a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800159dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800159dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800159c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800159c4`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[26])
{
  if ( WindowsCreateStringReference(L"Failed to allocate memory", 0x19u, &this->_header, &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800159a8  push    rbx
0x1800159aa  sub     rsp, 20h
0x1800159ae  mov     rbx, this
0x1800159b1  lea     r8, [this+8]; hstringHeader
0x1800159b5  mov     r9, this; string
0x1800159b8  mov     edx, 19h; length
0x1800159bd  lea     this, aFailedToAlloca; "Failed to allocate memory"
0x1800159c4  call    cs:__imp_WindowsCreateStringReference
0x1800159ca  test    eax, eax
0x1800159cc  jns     short loc_1800159E3
0x1800159ce  xor     r9d, r9d; lpArguments
0x1800159d1  xor     r8d, r8d; nNumberOfArguments
0x1800159d4  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800159d9  lea     edx, [r9+1]; dwExceptionFlags
0x1800159dd  call    cs:__imp_RaiseException
0x1800159e3  mov     rax, rbx
0x1800159e6  add     rsp, 20h
0x1800159ea  pop     rbx
0x1800159eb  retn
```
