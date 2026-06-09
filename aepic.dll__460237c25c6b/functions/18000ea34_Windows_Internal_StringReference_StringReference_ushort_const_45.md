# Windows::Internal::StringReference::StringReference(ushort const (&)[45])

- ea: `0x18000ea34`
- end: `0x18000ea78`
- name: `??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[45])`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cc80`
- `0x1800d5ab4`
- `0x1800da410`
- `0x1800dc88c`

## callees

- `0x18000ea34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ea69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ea69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ea50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ea50`

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
0x18000ea34  push    rbx
0x18000ea36  sub     rsp, 20h
0x18000ea3a  mov     rbx, rcx
0x18000ea3d  lea     r8, [rcx+8]; hstringHeader
0x18000ea41  mov     r9, rcx; string
0x18000ea44  mov     edx, 2Ch ; ','; length
0x18000ea49  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x18000ea50  call    cs:__imp_WindowsCreateStringReference
0x18000ea56  test    eax, eax
0x18000ea58  jns     short loc_18000EA6F
0x18000ea5a  xor     r9d, r9d; lpArguments
0x18000ea5d  xor     r8d, r8d; nNumberOfArguments
0x18000ea60  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000ea65  lea     edx, [r9+1]; dwExceptionFlags
0x18000ea69  call    cs:__imp_RaiseException
0x18000ea6f  mov     rax, rbx
0x18000ea72  add     rsp, 20h
0x18000ea76  pop     rbx
0x18000ea77  retn
```
