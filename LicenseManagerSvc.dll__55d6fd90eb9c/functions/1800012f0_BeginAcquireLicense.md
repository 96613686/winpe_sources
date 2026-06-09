# BeginAcquireLicense

- ea: `0x1800012f0`
- end: `0x18000131a`
- name: `BeginAcquireLicense`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800012f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000130c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000130c`
- `LicenseManager!ServiceBeginAcquireLicense` at `0x1800012f6`
- `LicenseManager!ServiceBeginAcquireLicense` at `0x1800012f6`

## pseudocode

```c
__int64 BeginAcquireLicense()
{
  __int64 result; // rax
  unsigned int v1; // ebx

  result = ServiceBeginAcquireLicense();
  v1 = result;
  if ( (int)result < 0 )
  {
    RaiseException(result, 0, 0, 0);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800012f0  push    rbx
0x1800012f2  sub     rsp, 20h
0x1800012f6  call    cs:__imp_ServiceBeginAcquireLicense
0x1800012fc  mov     ebx, eax
0x1800012fe  test    eax, eax
0x180001300  jns     short loc_180001314
0x180001302  xor     r9d, r9d; lpArguments
0x180001305  xor     r8d, r8d; nNumberOfArguments
0x180001308  xor     edx, edx; dwExceptionFlags
0x18000130a  mov     ecx, eax; dwExceptionCode
0x18000130c  call    cs:__imp_RaiseException
0x180001312  mov     eax, ebx
0x180001314  add     rsp, 20h
0x180001318  pop     rbx
0x180001319  retn
```
