# Windows::Internal::StringReference::StringReference(ushort const (&)[46])

- ea: `0x180016400`
- end: `0x180016447`
- name: `??$?0$0CO@@StringReference@Internal@Windows@@QEAA@AEAY0CO@$$CBG@Z`
- size: `71`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[46])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e9b4`

## callees

- `0x180016400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001643f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001643f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001641c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001641c`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[46])
{
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_ApplicationModel_Core_CoreApplication,
         0x2Du,
         &this->_header,
         &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x180016400  push    rbx
0x180016402  sub     rsp, 20h
0x180016406  mov     rbx, this
0x180016409  lea     r8, [this+8]; hstringHeader
0x18001640d  mov     r9, this; string
0x180016410  mov     edx, 2Dh ; '-'; length
0x180016415  lea     this, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; sourceString
0x18001641c  call    cs:__imp_WindowsCreateStringReference
0x180016422  test    eax, eax
0x180016424  js      short loc_18001642F
0x180016426  mov     rax, rbx
0x180016429  add     rsp, 20h
0x18001642d  pop     rbx
0x18001642e  retn
0x18001642f  xor     r9d, r9d; lpArguments
0x180016432  xor     r8d, r8d; nNumberOfArguments
0x180016435  mov     edx, 1; dwExceptionFlags
0x18001643a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001643f  call    cs:__imp_RaiseException
0x180016445  jmp     short loc_180016426
```
