# PackageRundownNotification

- ea: `0x1800016c0`
- end: `0x1800016f7`
- name: `PackageRundownNotification`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800016c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800016ed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800016ed`
- `LicenseManager!ServicePackageRundownNotification` at `0x1800016d1`
- `LicenseManager!ServicePackageRundownNotification` at `0x1800016d1`

## pseudocode

```c
__int64 __fastcall PackageRundownNotification(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 result; // rax
  unsigned int v5; // ebx

  result = ServicePackageRundownNotification(a2, a3, a4);
  v5 = result;
  if ( (int)result < 0 )
  {
    RaiseException(result, 0, 0, 0);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800016c0  push    rbx
0x1800016c2  sub     rsp, 20h
0x1800016c6  mov     eax, r8d
0x1800016c9  mov     rcx, rdx
0x1800016cc  mov     edx, eax
0x1800016ce  mov     r8, r9
0x1800016d1  call    cs:__imp_ServicePackageRundownNotification
0x1800016d7  mov     ebx, eax
0x1800016d9  test    eax, eax
0x1800016db  js      short loc_1800016E3
0x1800016dd  add     rsp, 20h
0x1800016e1  pop     rbx
0x1800016e2  retn
0x1800016e3  xor     r9d, r9d; lpArguments
0x1800016e6  xor     r8d, r8d; nNumberOfArguments
0x1800016e9  xor     edx, edx; dwExceptionFlags
0x1800016eb  mov     ecx, ebx; dwExceptionCode
0x1800016ed  call    cs:__imp_RaiseException
0x1800016f3  mov     eax, ebx
0x1800016f5  jmp     short loc_1800016DD
```
