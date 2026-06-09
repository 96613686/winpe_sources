# _WriteSystemDataRegistryDWORDForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,bool)

- ea: `0x180014d24`
- end: `0x180014f4d`
- name: `?_WriteSystemDataRegistryDWORDForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@K_N@Z`
- size: `553`
- prototype: `int __high(void *, const unsigned __int16 *, const unsigned __int16 *, enum SYSTEM_DATA_REGKEY_USER_ACCESS, unsigned int, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014798`
- `0x18001a780`
- `0x18003bb6c`

## callees

- `0x180004b70`
- `0x180004c00`
- `0x180014d24`
- `0x18003bec0`
- `0x18006c000`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180014e18`
- `KERNEL32!LocalFree` at `0x180014ee0`
- `KERNEL32!LocalFree` at `0x180014e18`
- `KERNEL32!LocalFree` at `0x180014ee0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014f2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014f18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180014f18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014ec5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014ec5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014d62`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014d62`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014e5c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014e5c`

## string_xrefs

- `0x180014d81`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall _WriteSystemDataRegistryDWORDForUser(void *a1, __int64 a2, const WCHAR *a3, __int64 a4, int a5)
{
  __int64 v6; // rdi
  signed int Error; // ebx
  const wchar_t *v8; // rcx
  WCHAR *v9; // rdx
  __int64 v10; // rax
  WCHAR *v11; // rcx
  BOOL v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-98h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+290h] [rbp+190h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v6 = 260;
    Error = StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s\\%s\\%s",
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
              StringSid,
              L"AnyoneRead",
              L"Colors");
    if ( Error >= 0 )
    {
      v8 = L"D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CIOI;KR;;;WD)";
      v9 = StringSecurityDescriptor;
      hKey = 0;
      v10 = 2147483646;
      do
      {
        if ( !v10 )
          break;
        if ( !*v8 )
          break;
        *v9++ = *v8++;
        --v10;
        --v6;
      }
      while ( v6 );
      v11 = v9 - 1;
      Error = v6 == 0 ? 0x8007007A : 0;
      if ( v6 )
        v11 = v9;
      *v11 = 0;
      if ( v6 )
      {
        SecurityDescriptor = 0;
        v13 = ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0);
        Error = ResultFromWin32Bool(v13);
        if ( Error >= 0 )
        {
          SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
          *(_QWORD *)&SecurityAttributes.nLength = 24;
          *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
          v14 = RegCreateKeyExW(
                  HKEY_LOCAL_MACHINE,
                  SubKey,
                  0,
                  (LPWSTR)&sourceString,
                  0,
                  0x2001Fu,
                  &SecurityAttributes,
                  &hKey,
                  0);
          Error = v14;
          if ( v14 > 0 )
            Error = (unsigned __int16)v14 | 0x80070000;
          LocalFree(SecurityDescriptor);
          if ( Error >= 0 )
          {
            LODWORD(SecurityDescriptor) = a5;
            v15 = RegSetValueExW(hKey, a3, 0, 4u, (const BYTE *)&SecurityDescriptor, 4u);
            Error = v15;
            if ( v15 > 0 )
              Error = (unsigned __int16)v15 | 0x80070000;
            RegCloseKey(hKey);
          }
        }
      }
    }
    LocalFree(StringSid);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180014d24  mov     [rsp-8+arg_8], rbx
0x180014d29  mov     [rsp-8+arg_18], rsi
0x180014d2e  push    rbp
0x180014d2f  push    rdi
0x180014d30  push    r14
0x180014d32  lea     rbp, [rsp-3B0h]
0x180014d3a  sub     rsp, 4B0h
0x180014d41  mov     rax, cs:__security_cookie
0x180014d48  xor     rax, rsp
0x180014d4b  mov     [rbp+3C0h+var_20], rax
0x180014d52  xor     r14d, r14d
0x180014d55  lea     rdx, [rsp+4C0h+StringSid]; StringSid
0x180014d5a  mov     [rsp+4C0h+StringSid], r14
0x180014d5f  mov     rsi, r8
0x180014d62  call    cs:__imp_ConvertSidToStringSidW
0x180014d68  test    eax, eax
0x180014d6a  jz      loc_180014F39
0x180014d70  mov     rcx, [rsp+4C0h+StringSid]
0x180014d75  lea     rax, aColors; "Colors"
0x180014d7c  mov     [rsp+4C0h+lpSecurityAttributes], rax
0x180014d81  lea     r9, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180014d88  mov     rax, cs:off_18009E008; "AnyoneRead"
0x180014d8f  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180014d96  mov     qword ptr [rsp+4C0h+samDesired], rax
0x180014d9b  mov     edi, 104h
0x180014da0  mov     qword ptr [rsp+4C0h+dwOptions], rcx
0x180014da5  mov     edx, edi; unsigned __int64
0x180014da7  lea     rcx, [rbp+3C0h+SubKey]; unsigned __int16 *
0x180014dae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014db3  mov     ebx, eax
0x180014db5  test    eax, eax
0x180014db7  js      short loc_180014E13
0x180014db9  mov     rcx, cs:off_1800A07D8; "D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CI"...
0x180014dc0  lea     rdx, [rbp+3C0h+StringSecurityDescriptor]
0x180014dc4  mov     [rsp+4C0h+hKey], r14
0x180014dc9  mov     eax, 7FFFFFFEh
0x180014dce  test    rax, rax
0x180014dd1  jz      short loc_180014DF2
0x180014dd3  movzx   r8d, word ptr [rcx]
0x180014dd7  test    r8w, r8w
0x180014ddb  jz      short loc_180014DF2
0x180014ddd  mov     [rdx], r8w
0x180014de1  add     rcx, 2
0x180014de5  add     rdx, 2
0x180014de9  dec     rax
0x180014dec  sub     rdi, 1
0x180014df0  jnz     short loc_180014DCE
0x180014df2  mov     rax, rdi
0x180014df5  lea     rcx, [rdx-2]
0x180014df9  neg     rax
0x180014dfc  sbb     ebx, ebx
0x180014dfe  not     ebx
0x180014e00  and     ebx, 8007007Ah
0x180014e06  test    rdi, rdi
0x180014e09  cmovnz  rcx, rdx
0x180014e0d  mov     [rcx], r14w
0x180014e11  jnz     short loc_180014E47
0x180014e13  mov     rcx, [rsp+4C0h+StringSid]; hMem
0x180014e18  call    cs:__imp_LocalFree
0x180014e1e  mov     eax, ebx
0x180014e20  mov     rcx, [rbp+3C0h+var_20]
0x180014e27  xor     rcx, rsp; StackCookie
0x180014e2a  call    __security_check_cookie
0x180014e2f  lea     r11, [rsp+4C0h+var_10]
0x180014e37  mov     rbx, [r11+28h]
0x180014e3b  mov     rsi, [r11+38h]
0x180014e3f  mov     rsp, r11
0x180014e42  pop     r14
0x180014e44  pop     rdi
0x180014e45  pop     rbp
0x180014e46  retn
0x180014e47  xor     r9d, r9d; SecurityDescriptorSize
0x180014e4a  mov     [rsp+4C0h+SecurityDescriptor], r14
0x180014e4f  lea     r8, [rsp+4C0h+SecurityDescriptor]; SecurityDescriptor
0x180014e54  lea     rcx, [rbp+3C0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180014e58  lea     edx, [r9+1]; StringSDRevision
0x180014e5c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180014e62  mov     ecx, eax; int
0x180014e64  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180014e69  mov     ebx, eax
0x180014e6b  test    eax, eax
0x180014e6d  js      short loc_180014E13
0x180014e6f  mov     rax, [rsp+4C0h+SecurityDescriptor]
0x180014e74  lea     r9, sourceString; lpClass
0x180014e7b  mov     [rsp+4C0h+lpdwDisposition], r14; lpdwDisposition
0x180014e80  lea     rdx, [rbp+3C0h+SubKey]; lpSubKey
0x180014e87  mov     [rsp+4C0h+SecurityAttributes.lpSecurityDescriptor], rax
0x180014e8c  xor     r8d, r8d; Reserved
0x180014e8f  lea     rax, [rsp+4C0h+hKey]
0x180014e94  mov     qword ptr [rsp+4C0h+SecurityAttributes.nLength], 18h
0x180014e9d  mov     [rsp+4C0h+phkResult], rax; phkResult
0x180014ea2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014ea9  lea     rax, [rsp+4C0h+SecurityAttributes]
0x180014eae  mov     qword ptr [rsp+4C0h+SecurityAttributes.bInheritHandle], r14
0x180014eb3  mov     [rsp+4C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180014eb8  mov     [rsp+4C0h+samDesired], 2001Fh; samDesired
0x180014ec0  mov     [rsp+4C0h+dwOptions], r14d; dwOptions
0x180014ec5  call    cs:__imp_RegCreateKeyExW
0x180014ecb  mov     ebx, eax
0x180014ecd  mov     edi, 80070000h
0x180014ed2  test    eax, eax
0x180014ed4  jle     short loc_180014EDB
0x180014ed6  movzx   ebx, ax
0x180014ed9  or      ebx, edi
0x180014edb  mov     rcx, [rsp+4C0h+SecurityDescriptor]; hMem
0x180014ee0  call    cs:__imp_LocalFree
0x180014ee6  test    ebx, ebx
0x180014ee8  js      loc_180014E13
0x180014eee  mov     eax, [rbp+3C0h+arg_20]
0x180014ef4  mov     r9d, 4; dwType
0x180014efa  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180014eff  xor     r8d, r8d; Reserved
0x180014f02  mov     dword ptr [rsp+4C0h+SecurityDescriptor], eax
0x180014f06  mov     rdx, rsi; lpValueName
0x180014f09  lea     rax, [rsp+4C0h+SecurityDescriptor]
0x180014f0e  mov     [rsp+4C0h+samDesired], r9d; cbData
0x180014f13  mov     qword ptr [rsp+4C0h+dwOptions], rax; lpData
0x180014f18  call    cs:__imp_RegSetValueExW
0x180014f1e  mov     ebx, eax
0x180014f20  test    eax, eax
0x180014f22  jle     short loc_180014F29
0x180014f24  movzx   ebx, ax
0x180014f27  or      ebx, edi
0x180014f29  mov     rcx, [rsp+4C0h+hKey]; hKey
0x180014f2e  call    cs:__imp_RegCloseKey
0x180014f34  jmp     loc_180014E13
0x180014f39  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180014f3e  mov     ebx, eax
0x180014f40  test    eax, eax
0x180014f42  jns     loc_180014D70
0x180014f48  jmp     loc_180014E1E
```
