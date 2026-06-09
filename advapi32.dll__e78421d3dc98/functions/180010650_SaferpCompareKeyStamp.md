# SaferpCompareKeyStamp

- ea: `0x180010650`
- end: `0x18001074e`
- name: `SaferpCompareKeyStamp`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010564`

## callees

- `0x180010650`
- `0x180065090`

## import_xrefs

- `ntdll!RtlGetLastNtStatus` at `0x180010730`
- `ntdll!RtlGetLastNtStatus` at `0x180010730`
- `ntdll!NtQueryKey` at `0x1800106df`
- `ntdll!NtQueryKey` at `0x1800106df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800106a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800106a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800106ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800106ec`
- `KERNEL32!CompareFileTime` at `0x180010702`
- `KERNEL32!CompareFileTime` at `0x180010702`

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
0x180010650  mov     [rsp+arg_10], rbx
0x180010655  push    rdi
0x180010656  sub     rsp, 260h
0x18001065d  mov     rax, cs:__security_cookie
0x180010664  xor     rax, rsp
0x180010667  mov     [rsp+268h+var_18], rax
0x18001066f  mov     rdi, rdx
0x180010672  mov     dword ptr [rdx], 0
0x180010678  lea     rax, [rsp+268h+hKey]
0x18001067d  mov     [rsp+268h+hKey], 0
0x180010686  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x18001068d  mov     [rsp+268h+phkResult], rax; phkResult
0x180010692  mov     r9d, 20019h; samDesired
0x180010698  mov     [rsp+268h+ResultLength], 0
0x1800106a0  xor     r8d, r8d; ulOptions
0x1800106a3  call    cs:__imp_RegOpenKeyExW
0x1800106a9  lea     ecx, [rax-2]
0x1800106ac  cmp     ecx, 1
0x1800106af  jbe     short loc_18001070D
0x1800106b1  cmp     eax, 3FAh
0x1800106b6  jz      short loc_18001070D
0x1800106b8  cmp     eax, 490h
0x1800106bd  jz      short loc_18001070D
0x1800106bf  test    eax, eax
0x1800106c1  jnz     short loc_180010730
0x1800106c3  mov     rcx, [rsp+268h+hKey]; KeyHandle
0x1800106c8  lea     rax, [rsp+268h+ResultLength]
0x1800106cd  mov     r9d, 208h; Length
0x1800106d3  mov     [rsp+268h+phkResult], rax; ResultLength
0x1800106d8  lea     r8, [rsp+268h+KeyInformation]; KeyInformation
0x1800106dd  xor     edx, edx; KeyInformationClass
0x1800106df  call    cs:__imp_NtQueryKey
0x1800106e5  mov     rcx, [rsp+268h+hKey]; hKey
0x1800106ea  mov     ebx, eax
0x1800106ec  call    cs:__imp_RegCloseKey
0x1800106f2  test    ebx, ebx
0x1800106f4  js      short loc_180010742
0x1800106f6  lea     rdx, [rsp+268h+KeyInformation]; lpFileTime2
0x1800106fb  lea     rcx, g_SaferPolicyTimeStamp; lpFileTime1
0x180010702  call    cs:__imp_CompareFileTime
0x180010708  cmp     eax, 0FFFFFFFFh
0x18001070b  jz      short loc_180010746
0x18001070d  xor     eax, eax
0x18001070f  mov     rcx, [rsp+268h+var_18]
0x180010717  xor     rcx, rsp; StackCookie
0x18001071a  call    __security_check_cookie
0x18001071f  mov     rbx, [rsp+268h+arg_10]
0x180010727  add     rsp, 260h
0x18001072e  pop     rdi
0x18001072f  retn
0x180010730  call    cs:__imp_RtlGetLastNtStatus
0x180010736  test    eax, eax
0x180010738  mov     ecx, 0C0000001h
0x18001073d  cmovns  eax, ecx
0x180010740  jmp     short loc_18001070F
0x180010742  mov     eax, ebx
0x180010744  jmp     short loc_18001070F
0x180010746  mov     dword ptr [rdi], 1
0x18001074c  jmp     short loc_18001070D
```
