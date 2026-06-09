# EnsureLicenseForOptionalPackageUsage

- ea: `0x180007950`
- end: `0x18000799c`
- name: `EnsureLicenseForOptionalPackageUsage`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180007950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000798e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000798e`
- `LicenseManager!ServiceEnsureLicenseForOptionalPackageUsage` at `0x180007978`
- `LicenseManager!ServiceEnsureLicenseForOptionalPackageUsage` at `0x180007978`

## pseudocode

```c
__int64 __fastcall EnsureLicenseForOptionalPackageUsage(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  signed int v4; // eax
  unsigned int v5; // ebx

  v4 = ServiceEnsureLicenseForOptionalPackageUsage(a1, a2, a3, a4);
  v5 = v4;
  if ( v4 < 0 )
    RaiseException(v4, 0, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x180007950  push    rbx
0x180007952  sub     rsp, 40h
0x180007956  mov     rax, [rsp+48h+arg_28]
0x18000795b  movups  xmm0, xmmword ptr [rax]
0x18000795e  lea     rax, [rsp+48h+var_18]
0x180007963  mov     [rsp+48h+var_20], rax
0x180007968  mov     rax, [rsp+48h+arg_20]
0x18000796d  mov     [rsp+48h+var_28], rax
0x180007972  movdqu  [rsp+48h+var_18], xmm0
0x180007978  call    cs:__imp_ServiceEnsureLicenseForOptionalPackageUsage
0x18000797e  mov     ebx, eax
0x180007980  test    eax, eax
0x180007982  jns     short loc_180007994
0x180007984  xor     r9d, r9d; lpArguments
0x180007987  xor     r8d, r8d; nNumberOfArguments
0x18000798a  xor     edx, edx; dwExceptionFlags
0x18000798c  mov     ecx, eax; dwExceptionCode
0x18000798e  call    cs:__imp_RaiseException
0x180007994  mov     eax, ebx
0x180007996  add     rsp, 40h
0x18000799a  pop     rbx
0x18000799b  retn
```
