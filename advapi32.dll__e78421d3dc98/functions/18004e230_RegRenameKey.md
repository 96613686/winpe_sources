# RegRenameKey

- ea: `0x18004e230`
- end: `0x18004e2b1`
- name: `RegRenameKey`
- size: `129`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKeyName, LPCWSTR lpNewKeyName)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18004e230`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18004e276`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004e276`
- `ntdll!NtRenameKey` at `0x18004e286`
- `ntdll!NtRenameKey` at `0x18004e286`
- `ntdll!RtlNtStatusToDosError` at `0x18004e2a0`
- `ntdll!RtlNtStatusToDosError` at `0x18004e2a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e264`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004e264`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e298`

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
0x18004e230  mov     rax, rsp
0x18004e233  mov     [rax+10h], rbx
0x18004e237  push    rdi
0x18004e238  sub     rsp, 40h
0x18004e23c  mov     [rax+8], rcx
0x18004e240  xorps   xmm0, xmm0
0x18004e243  mov     rdi, r8
0x18004e246  mov     rbx, rcx
0x18004e249  movups  xmmword ptr [rax-18h], xmm0
0x18004e24d  test    rdx, rdx
0x18004e250  jz      short loc_18004E26E
0x18004e252  lea     rax, [rax+8]
0x18004e256  mov     r9d, 20006h; samDesired
0x18004e25c  xor     r8d, r8d; ulOptions
0x18004e25f  mov     [rsp+48h+phkResult], rax; phkResult
0x18004e264  call    cs:__imp_RegOpenKeyExW
0x18004e26a  test    eax, eax
0x18004e26c  jnz     short loc_18004E2A6
0x18004e26e  mov     rdx, rdi; SourceString
0x18004e271  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18004e276  call    cs:__imp_RtlInitUnicodeStringEx
0x18004e27c  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x18004e281  lea     rdx, [rsp+48h+DestinationString]; NewName
0x18004e286  call    cs:__imp_NtRenameKey
0x18004e28c  mov     rcx, [rsp+48h+KeyHandle]; hKey
0x18004e291  mov     edi, eax
0x18004e293  cmp     rcx, rbx
0x18004e296  jz      short loc_18004E29E
0x18004e298  call    cs:__imp_RegCloseKey
0x18004e29e  mov     ecx, edi; Status
0x18004e2a0  call    cs:__imp_RtlNtStatusToDosError
0x18004e2a6  mov     rbx, [rsp+48h+arg_8]
0x18004e2ab  add     rsp, 40h
0x18004e2af  pop     rdi
0x18004e2b0  retn
```
