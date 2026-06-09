# Windows::Internal::StringReference::StringReference(ushort const (&)[45])

- ea: `0x180029e4c`
- end: `0x180029e9d`
- name: `??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[45])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180034d08`

## callees

- `0x180029e4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029e87`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180029e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029e68`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[45])
{
  if ( WindowsCreateStringReference(
         L"Windows.Management.Deployment.PackageManager",
         0x2Cu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180029e4c  push    rbx
0x180029e4e  sub     rsp, 20h
0x180029e52  mov     rbx, rcx
0x180029e55  lea     r8, [rcx+8]; hstringHeader
0x180029e59  mov     r9, rcx; string
0x180029e5c  mov     edx, 2Ch ; ','; length
0x180029e61  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x180029e68  call    cs:__imp_WindowsCreateStringReference
0x180029e6f  nop     dword ptr [rax+rax+00h]
0x180029e74  test    eax, eax
0x180029e76  jns     short loc_180029E93
0x180029e78  xor     r9d, r9d; lpArguments
0x180029e7b  xor     r8d, r8d; nNumberOfArguments
0x180029e7e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180029e83  lea     edx, [r9+1]; dwExceptionFlags
0x180029e87  call    cs:__imp_RaiseException
0x180029e8e  nop     dword ptr [rax+rax+00h]
0x180029e93  mov     rax, rbx
0x180029e96  add     rsp, 20h
0x180029e9a  pop     rbx
0x180029e9b  retn
```
