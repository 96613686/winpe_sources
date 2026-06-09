# RegRenameKey

- ea: `0x180054570`
- end: `0x180054610`
- name: `RegRenameKey`
- size: `160`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKeyName, LPCWSTR lpNewKeyName)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180054570`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1800545bc`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800545bc`
- `ntdll!NtRenameKey` at `0x1800545d2`
- `ntdll!NtRenameKey` at `0x1800545d2`
- `ntdll!RtlNtStatusToDosError` at `0x1800545f8`
- `ntdll!RtlNtStatusToDosError` at `0x1800545f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800545a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800545a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800545ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800545ea`

## pseudocode

```c
LSTATUS __stdcall RegRenameKey(HKEY hKey, LPCWSTR lpSubKeyName, LPCWSTR lpNewKeyName)
{
  LSTATUS result; // eax
  NTSTATUS v6; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp+8h] BYREF

  KeyHandle = hKey;
  DestinationString = 0;
  if ( !lpSubKeyName || (result = RegOpenKeyExW(hKey, lpSubKeyName, 0, 0x20006u, (PHKEY)&KeyHandle)) == 0 )
  {
    RtlInitUnicodeStringEx(&DestinationString, lpNewKeyName);
    v6 = NtRenameKey(KeyHandle, &DestinationString);
    if ( KeyHandle != hKey )
      RegCloseKey((HKEY)KeyHandle);
    return RtlNtStatusToDosError(v6);
  }
  return result;
}

```

## disassembly

```asm
0x180054570  mov     rax, rsp
0x180054573  mov     [rax+10h], rbx
0x180054577  push    rdi
0x180054578  sub     rsp, 40h
0x18005457c  mov     [rax+8], rcx
0x180054580  xorps   xmm0, xmm0
0x180054583  mov     rdi, r8
0x180054586  mov     rbx, rcx
0x180054589  movups  xmmword ptr [rax-18h], xmm0
0x18005458d  test    rdx, rdx
0x180054590  jz      short loc_1800545B4
0x180054592  lea     rax, [rax+8]
0x180054596  mov     r9d, 20006h; samDesired
0x18005459c  xor     r8d, r8d; ulOptions
0x18005459f  mov     [rsp+48h+phkResult], rax; phkResult
0x1800545a4  call    cs:__imp_RegOpenKeyExW
0x1800545ab  nop     dword ptr [rax+rax+00h]
0x1800545b0  test    eax, eax
0x1800545b2  jnz     short loc_180054604
0x1800545b4  mov     rdx, rdi; SourceString
0x1800545b7  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1800545bc  call    cs:__imp_RtlInitUnicodeStringEx
0x1800545c3  nop     dword ptr [rax+rax+00h]
0x1800545c8  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x1800545cd  lea     rdx, [rsp+48h+DestinationString]; NewName
0x1800545d2  call    cs:__imp_NtRenameKey
0x1800545d9  nop     dword ptr [rax+rax+00h]
0x1800545de  mov     rcx, [rsp+48h+KeyHandle]; hKey
0x1800545e3  mov     edi, eax
0x1800545e5  cmp     rcx, rbx
0x1800545e8  jz      short loc_1800545F6
0x1800545ea  call    cs:__imp_RegCloseKey
0x1800545f1  nop     dword ptr [rax+rax+00h]
0x1800545f6  mov     ecx, edi; Status
0x1800545f8  call    cs:__imp_RtlNtStatusToDosError
0x1800545ff  nop     dword ptr [rax+rax+00h]
0x180054604  mov     rbx, [rsp+48h+arg_8]
0x180054609  add     rsp, 40h
0x18005460d  pop     rdi
0x18005460e  retn
```
