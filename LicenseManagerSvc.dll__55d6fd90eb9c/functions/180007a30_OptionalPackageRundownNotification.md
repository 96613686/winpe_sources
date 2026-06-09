# OptionalPackageRundownNotification

- ea: `0x180007a30`
- end: `0x180007a6e`
- name: `OptionalPackageRundownNotification`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180007a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007a60`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180007a60`
- `LicenseManager!ServiceOptionalPackageRundownNotification` at `0x180007a4a`
- `LicenseManager!ServiceOptionalPackageRundownNotification` at `0x180007a4a`

## pseudocode

```c
__int64 __fastcall OptionalPackageRundownNotification(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  signed int v5; // eax
  unsigned int v6; // ebx

  v5 = ServiceOptionalPackageRundownNotification(a2, a3, a4, a5);
  v6 = v5;
  if ( v5 < 0 )
    RaiseException(v5, 0, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x180007a30  push    rbx
0x180007a32  sub     rsp, 20h
0x180007a36  mov     rax, r9
0x180007a39  mov     r10d, r8d
0x180007a3c  mov     r9, [rsp+28h+arg_20]
0x180007a41  mov     rcx, rdx
0x180007a44  mov     r8, rax
0x180007a47  mov     edx, r10d
0x180007a4a  call    cs:__imp_ServiceOptionalPackageRundownNotification
0x180007a50  mov     ebx, eax
0x180007a52  test    eax, eax
0x180007a54  jns     short loc_180007A66
0x180007a56  xor     r9d, r9d; lpArguments
0x180007a59  xor     r8d, r8d; nNumberOfArguments
0x180007a5c  xor     edx, edx; dwExceptionFlags
0x180007a5e  mov     ecx, eax; dwExceptionCode
0x180007a60  call    cs:__imp_RaiseException
0x180007a66  mov     eax, ebx
0x180007a68  add     rsp, 20h
0x180007a6c  pop     rbx
0x180007a6d  retn
```
