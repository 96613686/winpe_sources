# PrecacheLicenseForPackageResume

- ea: `0x180007ad0`
- end: `0x180007afa`
- name: `PrecacheLicenseForPackageResume`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180007ad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007aec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007aec`
- `LicenseManager!ServicePrecacheLicenseForPackageResume` at `0x180007ad6`
- `LicenseManager!ServicePrecacheLicenseForPackageResume` at `0x180007ad6`

## pseudocode

```c
__int64 PrecacheLicenseForPackageResume()
{
  signed int v0; // eax
  unsigned int v1; // ebx

  v0 = ServicePrecacheLicenseForPackageResume();
  v1 = v0;
  if ( v0 < 0 )
    RaiseException(v0, 0, 0, 0);
  return v1;
}

```

## disassembly

```asm
0x180007ad0  push    rbx
0x180007ad2  sub     rsp, 20h
0x180007ad6  call    cs:__imp_ServicePrecacheLicenseForPackageResume
0x180007adc  mov     ebx, eax
0x180007ade  test    eax, eax
0x180007ae0  jns     short loc_180007AF2
0x180007ae2  xor     r9d, r9d; lpArguments
0x180007ae5  xor     r8d, r8d; nNumberOfArguments
0x180007ae8  xor     edx, edx; dwExceptionFlags
0x180007aea  mov     ecx, eax; dwExceptionCode
0x180007aec  call    cs:__imp_RaiseException
0x180007af2  mov     eax, ebx
0x180007af4  add     rsp, 20h
0x180007af8  pop     rbx
0x180007af9  retn
```
