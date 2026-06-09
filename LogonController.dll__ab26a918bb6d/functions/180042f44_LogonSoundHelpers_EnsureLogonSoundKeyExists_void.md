# LogonSoundHelpers::EnsureLogonSoundKeyExists(void)

- ea: `0x180042f44`
- end: `0x180043011`
- name: `?EnsureLogonSoundKeyExists@LogonSoundHelpers@@YAJXZ`
- size: `205`
- prototype: `__int64 __fastcall(LogonSoundHelpers *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180042c18`

## callees

- `0x180042f44`
- `0x180087638`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180043003`
- `KERNEL32!LocalFree` at `0x180043003`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042ff8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042ff8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042fd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042fd7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042f6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042f6e`

## pseudocode

```c
__int64 __fastcall LogonSoundHelpers::EnsureLogonSoundKeyExists(LogonSoundHelpers *this)
{
  signed int Error; // ebx
  LSTATUS v2; // eax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_OWORD *)&SecurityAttributes.lpSecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;CI;0x2001B;;;AU)",
         1u,
         &SecurityAttributes.lpSecurityDescriptor,
         0)
    || (Error = ResultFromLastError(), Error >= 0) )
  {
    hKey = 0;
    v2 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\LogonSoundPlayed",
           0,
           0,
           1u,
           1u,
           &SecurityAttributes,
           &hKey,
           0);
    Error = v2;
    if ( v2 > 0 )
      Error = (unsigned __int16)v2 | 0x80070000;
    if ( Error >= 0 )
      RegCloseKey(hKey);
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180042f44  push    rbx
0x180042f46  sub     rsp, 70h
0x180042f4a  xor     r9d, r9d; SecurityDescriptorSize
0x180042f4d  mov     qword ptr [rsp+78h+SecurityAttributes.nLength], 18h
0x180042f56  xorps   xmm0, xmm0
0x180042f59  lea     r8, [rsp+78h+SecurityAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x180042f5e  lea     rcx, aDACi0x2001bAu; "D:(A;CI;0x2001B;;;AU)"
0x180042f65  movups  xmmword ptr [rsp+78h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x180042f6a  lea     edx, [r9+1]; StringSDRevision
0x180042f6e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180042f74  test    eax, eax
0x180042f76  jnz     short loc_180042F87
0x180042f78  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180042f7d  mov     ebx, eax
0x180042f7f  test    eax, eax
0x180042f81  js      loc_180043009
0x180042f87  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180042f90  lea     rax, [rsp+78h+hKey]
0x180042f98  mov     [rsp+78h+phkResult], rax; phkResult
0x180042f9d  lea     rdx, aSoftwareMicros_16; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180042fa4  lea     rax, [rsp+78h+SecurityAttributes]
0x180042fa9  mov     [rsp+78h+hKey], 0
0x180042fb5  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180042fba  xor     r9d, r9d; lpClass
0x180042fbd  mov     [rsp+78h+samDesired], 1; samDesired
0x180042fc5  xor     r8d, r8d; Reserved
0x180042fc8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180042fcf  mov     [rsp+78h+dwOptions], 1; dwOptions
0x180042fd7  call    cs:__imp_RegCreateKeyExW
0x180042fdd  mov     ebx, eax
0x180042fdf  test    eax, eax
0x180042fe1  jle     short loc_180042FEC
0x180042fe3  movzx   ebx, ax
0x180042fe6  or      ebx, 80070000h
0x180042fec  test    ebx, ebx
0x180042fee  js      short loc_180042FFE
0x180042ff0  mov     rcx, [rsp+78h+hKey]; hKey
0x180042ff8  call    cs:__imp_RegCloseKey
0x180042ffe  mov     rcx, [rsp+78h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x180043003  call    cs:__imp_LocalFree
0x180043009  mov     eax, ebx
0x18004300b  add     rsp, 70h
0x18004300f  pop     rbx
0x180043010  retn
```
