# SaferpCompareKeyStamp

- ea: `0x180015964`
- end: `0x180015a85`
- name: `SaferpCompareKeyStamp`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015864`

## callees

- `0x180015964`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlGetLastNtStatus` at `0x180015a61`
- `ntdll!RtlGetLastNtStatus` at `0x180015a61`
- `ntdll!NtQueryKey` at `0x1800159fd`
- `ntdll!NtQueryKey` at `0x1800159fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800159b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800159b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015a10`
- `KERNEL32!CompareFileTime` at `0x180015a2c`
- `KERNEL32!CompareFileTime` at `0x180015a2c`

## pseudocode

```c
NTSTATUS __fastcall SaferpCompareKeyStamp(HKEY a1, _DWORD *a2)
{
  LSTATUS v3; // eax
  NTSTATUS v4; // ebx
  NTSTATUS result; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-238h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-230h] BYREF
  FILETIME KeyInformation[66]; // [rsp+40h] [rbp-228h] BYREF

  *a2 = 0;
  hKey = 0;
  ResultLength = 0;
  v3 = RegOpenKeyExW(a1, L"Software\\Policies\\Microsoft\\Windows\\Safer\\CodeIdentifiers", 0, 0x20019u, &hKey);
  if ( (unsigned int)(v3 - 2) <= 1 || v3 == 1018 || v3 == 1168 )
    return 0;
  if ( v3 )
  {
    result = RtlGetLastNtStatus();
    if ( result >= 0 )
      return -1073741823;
  }
  else
  {
    v4 = NtQueryKey(hKey, KeyBasicInformation, KeyInformation, 0x208u, &ResultLength);
    RegCloseKey(hKey);
    if ( v4 >= 0 )
    {
      if ( CompareFileTime(&g_SaferPolicyTimeStamp, KeyInformation) == -1 )
        *a2 = 1;
      return 0;
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180015964  mov     [rsp+arg_10], rbx
0x180015969  push    rdi
0x18001596a  sub     rsp, 260h
0x180015971  mov     rax, cs:__security_cookie
0x180015978  xor     rax, rsp
0x18001597b  mov     [rsp+268h+var_18], rax
0x180015983  mov     rdi, rdx
0x180015986  mov     dword ptr [rdx], 0
0x18001598c  lea     rax, [rsp+268h+hKey]
0x180015991  mov     [rsp+268h+hKey], 0
0x18001599a  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x1800159a1  mov     [rsp+268h+phkResult], rax; phkResult
0x1800159a6  mov     r9d, 20019h; samDesired
0x1800159ac  mov     [rsp+268h+ResultLength], 0
0x1800159b4  xor     r8d, r8d; ulOptions
0x1800159b7  call    cs:__imp_RegOpenKeyExW
0x1800159be  nop     dword ptr [rax+rax+00h]
0x1800159c3  lea     ecx, [rax-2]
0x1800159c6  cmp     ecx, 1
0x1800159c9  jbe     short loc_180015A3D
0x1800159cb  cmp     eax, 3FAh
0x1800159d0  jz      short loc_180015A3D
0x1800159d2  cmp     eax, 490h
0x1800159d7  jz      short loc_180015A3D
0x1800159d9  test    eax, eax
0x1800159db  jnz     loc_180015A61
0x1800159e1  mov     rcx, [rsp+268h+hKey]; KeyHandle
0x1800159e6  lea     rax, [rsp+268h+ResultLength]
0x1800159eb  mov     r9d, 208h; Length
0x1800159f1  mov     [rsp+268h+phkResult], rax; ResultLength
0x1800159f6  lea     r8, [rsp+268h+KeyInformation]; KeyInformation
0x1800159fb  xor     edx, edx; KeyInformationClass
0x1800159fd  call    cs:__imp_NtQueryKey
0x180015a04  nop     dword ptr [rax+rax+00h]
0x180015a09  mov     rcx, [rsp+268h+hKey]; hKey
0x180015a0e  mov     ebx, eax
0x180015a10  call    cs:__imp_RegCloseKey
0x180015a17  nop     dword ptr [rax+rax+00h]
0x180015a1c  test    ebx, ebx
0x180015a1e  js      short loc_180015A79
0x180015a20  lea     rdx, [rsp+268h+KeyInformation]; lpFileTime2
0x180015a25  lea     rcx, g_SaferPolicyTimeStamp; lpFileTime1
0x180015a2c  call    cs:__imp_CompareFileTime
0x180015a33  nop     dword ptr [rax+rax+00h]
0x180015a38  cmp     eax, 0FFFFFFFFh
0x180015a3b  jz      short loc_180015A7D
0x180015a3d  xor     eax, eax
0x180015a3f  mov     rcx, [rsp+268h+var_18]
0x180015a47  xor     rcx, rsp; StackCookie
0x180015a4a  call    __security_check_cookie
0x180015a4f  mov     rbx, [rsp+268h+arg_10]
0x180015a57  add     rsp, 260h
0x180015a5e  pop     rdi
0x180015a5f  retn
0x180015a61  call    cs:__imp_RtlGetLastNtStatus
0x180015a68  nop     dword ptr [rax+rax+00h]
0x180015a6d  test    eax, eax
0x180015a6f  mov     ecx, 0C0000001h
0x180015a74  cmovns  eax, ecx
0x180015a77  jmp     short loc_180015A3F
0x180015a79  mov     eax, ebx
0x180015a7b  jmp     short loc_180015A3F
0x180015a7d  mov     dword ptr [rdi], 1
0x180015a83  jmp     short loc_180015A3D
```
