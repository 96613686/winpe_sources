# Windows::Internal::StringReference::StringReference(ushort const (&)[75])

- ea: `0x180021f78`
- end: `0x180021fbc`
- name: `??$?0$0EL@@StringReference@Internal@Windows@@QEAA@AEAY0EL@$$CBG@Z`
- size: `68`
- prototype: `void __fastcall(Windows::Internal::StringReference *this, const wchar_t (*)[75])`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180029214`
- `0x1800294f4`
- `0x1800297e4`
- `0x18003f000`

## callees

- `0x180021f78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021fad`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021fad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021f94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180021f94`

## pseudocode

```c
void __fastcall Windows::Internal::StringReference::StringReference(
        Windows::Internal::StringReference *this,
        const wchar_t (*a2)[75])
{
  if ( WindowsCreateStringReference(
         RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerStateCreationInternal,
         0x4Au,
         &this->_header,
         &this->_hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x180021f78  push    rbx
0x180021f7a  sub     rsp, 20h
0x180021f7e  mov     rbx, this
0x180021f81  lea     r8, [this+8]; hstringHeader
0x180021f85  mov     r9, this; string
0x180021f88  mov     edx, 4Ah ; 'J'; length
0x180021f8d  lea     this, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerStateCreationInternal@@3QBGB; sourceString
0x180021f94  call    cs:__imp_WindowsCreateStringReference
0x180021f9a  test    eax, eax
0x180021f9c  jns     short loc_180021FB3
0x180021f9e  xor     r9d, r9d; lpArguments
0x180021fa1  xor     r8d, r8d; nNumberOfArguments
0x180021fa4  mov     ecx, 0C000000Dh; dwExceptionCode
0x180021fa9  lea     edx, [r9+1]; dwExceptionFlags
0x180021fad  call    cs:__imp_RaiseException
0x180021fb3  mov     rax, rbx
0x180021fb6  add     rsp, 20h
0x180021fba  pop     rbx
0x180021fbb  retn
```
