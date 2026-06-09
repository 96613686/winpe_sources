# PackageSuspendedNotification

- ea: `0x180007a80`
- end: `0x180007ac8`
- name: `PackageSuspendedNotification`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180007a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007aba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007aba`
- `LicenseManager!ServicePackageSuspendedNotification` at `0x180007aa4`
- `LicenseManager!ServicePackageSuspendedNotification` at `0x180007aa4`

## pseudocode

```c
__int64 __fastcall PackageSuspendedNotification(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  signed int v6; // eax
  unsigned int v7; // ebx

  v6 = ServicePackageSuspendedNotification(a2, a3, a4, a5, a6);
  v7 = v6;
  if ( v6 < 0 )
    RaiseException(v6, 0, 0, 0);
  return v7;
}

```

## disassembly

```asm
0x180007a80  push    rbx
0x180007a82  sub     rsp, 30h
0x180007a86  mov     rax, [rsp+38h+arg_28]
0x180007a8b  mov     r10, r9
0x180007a8e  mov     r9d, [rsp+38h+arg_20]
0x180007a93  mov     r11d, r8d
0x180007a96  mov     rcx, rdx
0x180007a99  mov     [rsp+38h+var_18], rax
0x180007a9e  mov     r8, r10
0x180007aa1  mov     edx, r11d
0x180007aa4  call    cs:__imp_ServicePackageSuspendedNotification
0x180007aaa  mov     ebx, eax
0x180007aac  test    eax, eax
0x180007aae  jns     short loc_180007AC0
0x180007ab0  xor     r9d, r9d; lpArguments
0x180007ab3  xor     r8d, r8d; nNumberOfArguments
0x180007ab6  xor     edx, edx; dwExceptionFlags
0x180007ab8  mov     ecx, eax; dwExceptionCode
0x180007aba  call    cs:__imp_RaiseException
0x180007ac0  mov     eax, ebx
0x180007ac2  add     rsp, 30h
0x180007ac6  pop     rbx
0x180007ac7  retn
```
