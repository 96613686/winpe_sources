# EnsureLicenseForPackageActivation

- ea: `0x1800079b0`
- end: `0x1800079ec`
- name: `EnsureLicenseForPackageActivation`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800079b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800079de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800079de`
- `LicenseManager!ServiceEnsureLicenseForPackageActivation` at `0x1800079c8`
- `LicenseManager!ServiceEnsureLicenseForPackageActivation` at `0x1800079c8`

## pseudocode

```c
__int64 __fastcall EnsureLicenseForPackageActivation(__int64 a1, __int64 a2)
{
  signed int v2; // eax
  unsigned int v3; // ebx

  v2 = ServiceEnsureLicenseForPackageActivation(a1, a2);
  v3 = v2;
  if ( v2 < 0 )
    RaiseException(v2, 0, 0, 0);
  return v3;
}

```

## disassembly

```asm
0x1800079b0  push    rbx
0x1800079b2  sub     rsp, 30h
0x1800079b6  mov     rax, [rsp+38h+arg_28]
0x1800079bb  mov     [rsp+38h+var_10], rax
0x1800079c0  mov     eax, [rsp+38h+arg_20]
0x1800079c4  mov     [rsp+38h+var_18], eax
0x1800079c8  call    cs:__imp_ServiceEnsureLicenseForPackageActivation
0x1800079ce  mov     ebx, eax
0x1800079d0  test    eax, eax
0x1800079d2  jns     short loc_1800079E4
0x1800079d4  xor     r9d, r9d; lpArguments
0x1800079d7  xor     r8d, r8d; nNumberOfArguments
0x1800079da  xor     edx, edx; dwExceptionFlags
0x1800079dc  mov     ecx, eax; dwExceptionCode
0x1800079de  call    cs:__imp_RaiseException
0x1800079e4  mov     eax, ebx
0x1800079e6  add     rsp, 30h
0x1800079ea  pop     rbx
0x1800079eb  retn
```
