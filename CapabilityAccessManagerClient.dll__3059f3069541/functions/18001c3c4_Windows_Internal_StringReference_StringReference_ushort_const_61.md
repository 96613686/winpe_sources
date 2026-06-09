# Windows::Internal::StringReference::StringReference(ushort const (&)[61])

- ea: `0x18001c3c4`
- end: `0x18001c408`
- name: `??$?0$0DN@@StringReference@Internal@Windows@@QEAA@AEAY0DN@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[61])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e4a0`

## callees

- `0x18001c3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c3f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c3f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c3e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c3e0`

## string_xrefs

- `0x18001c3d9`: `Windows.Internal.CapabilityAccess.Management.CapabilityUsage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[61])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityUsage",
         0x3Cu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001c3c4  push    rbx
0x18001c3c6  sub     rsp, 20h
0x18001c3ca  mov     rbx, rcx
0x18001c3cd  lea     r8, [rcx+8]; hstringHeader
0x18001c3d1  mov     r9, rcx; string
0x18001c3d4  mov     edx, 3Ch ; '<'; length
0x18001c3d9  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x18001c3e0  call    cs:__imp_WindowsCreateStringReference
0x18001c3e6  test    eax, eax
0x18001c3e8  jns     short loc_18001C3FF
0x18001c3ea  xor     r9d, r9d; lpArguments
0x18001c3ed  xor     r8d, r8d; nNumberOfArguments
0x18001c3f0  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001c3f5  lea     edx, [r9+1]; dwExceptionFlags
0x18001c3f9  call    cs:__imp_RaiseException
0x18001c3ff  mov     rax, rbx
0x18001c402  add     rsp, 20h
0x18001c406  pop     rbx
0x18001c407  retn
```
