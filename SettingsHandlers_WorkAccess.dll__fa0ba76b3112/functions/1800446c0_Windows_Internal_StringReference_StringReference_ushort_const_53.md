# Windows::Internal::StringReference::StringReference(ushort const (&)[53])

- ea: `0x1800446c0`
- end: `0x180044711`
- name: `??$?0$0DF@@StringReference@Internal@Windows@@QEAA@AEAY0DF@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[53])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004cc34`

## callees

- `0x1800446c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800446fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800446fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800446dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800446dc`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[53])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Management.Provision.SessionManager",
         0x34u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800446c0  push    rbx
0x1800446c2  sub     rsp, 20h
0x1800446c6  mov     rbx, rcx
0x1800446c9  lea     r8, [rcx+8]; hstringHeader
0x1800446cd  mov     r9, rcx; string
0x1800446d0  mov     edx, 34h ; '4'; length
0x1800446d5  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Provision_SessionManager@@3QBGB; "Windows.Internal.Management.Provision.S"...
0x1800446dc  call    cs:__imp_WindowsCreateStringReference
0x1800446e3  nop     dword ptr [rax+rax+00h]
0x1800446e8  test    eax, eax
0x1800446ea  jns     short loc_180044707
0x1800446ec  xor     r9d, r9d; lpArguments
0x1800446ef  xor     r8d, r8d; nNumberOfArguments
0x1800446f2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800446f7  lea     edx, [r9+1]; dwExceptionFlags
0x1800446fb  call    cs:__imp_RaiseException
0x180044702  nop     dword ptr [rax+rax+00h]
0x180044707  mov     rax, rbx
0x18004470a  add     rsp, 20h
0x18004470e  pop     rbx
0x18004470f  retn
```
