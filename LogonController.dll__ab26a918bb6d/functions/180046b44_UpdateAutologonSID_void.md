# _UpdateAutologonSID(void)

- ea: `0x180046b44`
- end: `0x180046d94`
- name: `?_UpdateAutologonSID@@YAXXZ`
- size: `592`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180038c34`

## callees

- `0x180046b44`
- `0x18006c000`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x180046cb9`
- `KERNEL32!LocalAlloc` at `0x180046cb9`
- `KERNEL32!LocalFree` at `0x180046d45`
- `KERNEL32!LocalFree` at `0x180046d4e`
- `KERNEL32!LocalFree` at `0x180046d45`
- `KERNEL32!LocalFree` at `0x180046d4e`
- `KERNEL32!CompareStringOrdinal` at `0x180046c4d`
- `KERNEL32!CompareStringOrdinal` at `0x180046c4d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046baa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046c13`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046baa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046c13`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180046d3a`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180046d6e`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180046d3a`
- `api-ms-win-stateseparation-helpers-l1-1-1!SetPersistedRegistryString` at `0x180046d6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180046d16`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180046d16`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180046c9b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180046cfb`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180046c9b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180046cfb`

## string_xrefs

- `0x180046d25`: `AutoLogonSID`

## pseudocode

```c
void _UpdateAutologonSID(void)
{
  LSTATUS ValueW; // eax
  bool v1; // sf
  LSTATUS v2; // eax
  bool v3; // sf
  HLOCAL v4; // rbx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String1[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String2[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+480h] [rbp+380h] BYREF

  pcbData = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
             L"DefaultUserName",
             2u,
             0,
             String1,
             &pcbData);
  v1 = ValueW < 0;
  if ( ValueW )
  {
    String1[0] = 0;
    v1 = ValueW < 0;
    if ( ValueW > 0 )
      v1 = 1;
  }
  if ( !v1 )
  {
    pcbData = 520;
    v2 = RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
           L"LastUsedUsername",
           2u,
           0,
           String2,
           &pcbData);
    v3 = v2 < 0;
    if ( v2 )
    {
      String2[0] = 0;
      v3 = v2 < 0;
      if ( v2 > 0 )
        v3 = 1;
    }
    if ( v3 || CompareStringOrdinal(String1, -1, String2, -1, 1) != 2 )
    {
      cbSid = 0;
      pcbData = 0;
      cchReferencedDomainName = 260;
      if ( !LookupAccountNameLocalW(
              String1,
              0,
              &cbSid,
              ReferencedDomainName,
              &cchReferencedDomainName,
              (PSID_NAME_USE)&pcbData) )
      {
        if ( cbSid )
        {
          v4 = LocalAlloc(0, cbSid);
          if ( v4 )
          {
            cchReferencedDomainName = 260;
            if ( LookupAccountNameLocalW(
                   String1,
                   v4,
                   &cbSid,
                   ReferencedDomainName,
                   &cchReferencedDomainName,
                   (PSID_NAME_USE)&pcbData) )
            {
              StringSid = 0;
              if ( ConvertSidToStringSidW(v4, &StringSid) )
              {
                SetPersistedRegistryString(
                  L"Winlogon",
                  L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
                  L"AutoLogonSID",
                  StringSid);
                LocalFree(StringSid);
              }
            }
            LocalFree(v4);
          }
        }
      }
      SetPersistedRegistryString(
        L"Winlogon",
        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
        L"LastUsedUsername",
        String1);
    }
  }
}

```

## disassembly

```asm
0x180046b44  mov     [rsp-8+arg_0], rbx
0x180046b49  push    rbp
0x180046b4a  lea     rbp, [rsp-5A0h]
0x180046b52  sub     rsp, 6A0h
0x180046b59  mov     rax, cs:__security_cookie
0x180046b60  xor     rax, rsp
0x180046b63  mov     [rbp+5A0h+var_10], rax
0x180046b6a  lea     rax, [rsp+6A0h+var_660]
0x180046b6f  mov     [rsp+6A0h+var_660], 208h
0x180046b77  mov     [rsp+6A0h+pcbData], rax; pcbData
0x180046b7c  lea     r8, aDefaultusernam; "DefaultUserName"
0x180046b83  lea     rax, [rsp+6A0h+String1]
0x180046b88  mov     r9d, 2; dwFlags
0x180046b8e  mov     [rsp+6A0h+pvData], rax; pvData
0x180046b93  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x180046b9a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180046ba1  mov     [rsp+6A0h+pdwType], 0; pdwType
0x180046baa  call    cs:__imp_RegGetValueW
0x180046bb0  mov     ebx, 80070000h
0x180046bb5  test    eax, eax
0x180046bb7  jz      short loc_180046BCB
0x180046bb9  xor     ecx, ecx
0x180046bbb  mov     [rsp+6A0h+String1], cx
0x180046bc0  test    eax, eax
0x180046bc2  jle     short loc_180046BCB
0x180046bc4  movzx   eax, ax
0x180046bc7  or      eax, ebx
0x180046bc9  test    eax, eax
0x180046bcb  js      loc_180046D74
0x180046bd1  lea     rax, [rsp+6A0h+var_660]
0x180046bd6  mov     [rsp+6A0h+var_660], 208h
0x180046bde  mov     [rsp+6A0h+pcbData], rax; pcbData
0x180046be3  lea     r8, aLastuseduserna; "LastUsedUsername"
0x180046bea  lea     rax, [rbp+5A0h+String2]
0x180046bf1  mov     r9d, 2; dwFlags
0x180046bf7  mov     [rsp+6A0h+pvData], rax; pvData
0x180046bfc  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x180046c03  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180046c0a  mov     [rsp+6A0h+pdwType], 0; pdwType
0x180046c13  call    cs:__imp_RegGetValueW
0x180046c19  test    eax, eax
0x180046c1b  jz      short loc_180046C31
0x180046c1d  xor     ecx, ecx
0x180046c1f  mov     [rbp+5A0h+String2], cx
0x180046c26  test    eax, eax
0x180046c28  jle     short loc_180046C31
0x180046c2a  movzx   eax, ax
0x180046c2d  or      eax, ebx
0x180046c2f  test    eax, eax
0x180046c31  js      short loc_180046C5C
0x180046c33  or      edx, 0FFFFFFFFh; cchCount1
0x180046c36  mov     dword ptr [rsp+6A0h+pdwType], 1; bIgnoreCase
0x180046c3e  mov     r9d, edx; cchCount2
0x180046c41  lea     r8, [rbp+5A0h+String2]; lpString2
0x180046c48  lea     rcx, [rsp+6A0h+String1]; lpString1
0x180046c4d  call    cs:__imp_CompareStringOrdinal
0x180046c53  cmp     eax, 2
0x180046c56  jz      loc_180046D74
0x180046c5c  lea     rax, [rsp+6A0h+var_660]
0x180046c61  mov     [rsp+6A0h+cbSid], 0
0x180046c69  mov     [rsp+6A0h+pvData], rax; peUse
0x180046c6e  lea     r9, [rbp+5A0h+ReferencedDomainName]; ReferencedDomainName
0x180046c75  lea     rax, [rsp+6A0h+cchReferencedDomainName]
0x180046c7a  mov     [rsp+6A0h+var_660], 0
0x180046c82  lea     r8, [rsp+6A0h+cbSid]; cbSid
0x180046c87  mov     [rsp+6A0h+pdwType], rax; cchReferencedDomainName
0x180046c8c  xor     edx, edx; Sid
0x180046c8e  mov     [rsp+6A0h+cchReferencedDomainName], 104h
0x180046c96  lea     rcx, [rsp+6A0h+String1]; lpAccountName
0x180046c9b  call    cs:__imp_LookupAccountNameLocalW
0x180046ca1  test    eax, eax
0x180046ca3  jnz     loc_180046D54
0x180046ca9  mov     eax, [rsp+6A0h+cbSid]
0x180046cad  test    eax, eax
0x180046caf  jz      loc_180046D54
0x180046cb5  mov     edx, eax; uBytes
0x180046cb7  xor     ecx, ecx; uFlags
0x180046cb9  call    cs:__imp_LocalAlloc
0x180046cbf  mov     rbx, rax
0x180046cc2  test    rax, rax
0x180046cc5  jz      loc_180046D54
0x180046ccb  lea     rax, [rsp+6A0h+var_660]
0x180046cd0  mov     [rsp+6A0h+cchReferencedDomainName], 104h
0x180046cd8  mov     [rsp+6A0h+pvData], rax; peUse
0x180046cdd  lea     r9, [rbp+5A0h+ReferencedDomainName]; ReferencedDomainName
0x180046ce4  lea     rax, [rsp+6A0h+cchReferencedDomainName]
0x180046ce9  mov     rdx, rbx; Sid
0x180046cec  lea     r8, [rsp+6A0h+cbSid]; cbSid
0x180046cf1  mov     [rsp+6A0h+pdwType], rax; cchReferencedDomainName
0x180046cf6  lea     rcx, [rsp+6A0h+String1]; lpAccountName
0x180046cfb  call    cs:__imp_LookupAccountNameLocalW
0x180046d01  test    eax, eax
0x180046d03  jz      short loc_180046D4B
0x180046d05  lea     rdx, [rsp+6A0h+StringSid]; StringSid
0x180046d0a  mov     [rsp+6A0h+StringSid], 0
0x180046d13  mov     rcx, rbx; Sid
0x180046d16  call    cs:__imp_ConvertSidToStringSidW
0x180046d1c  test    eax, eax
0x180046d1e  jz      short loc_180046D4B
0x180046d20  mov     r9, [rsp+6A0h+StringSid]
0x180046d25  lea     r8, aAutologonsid; "AutoLogonSID"
0x180046d2c  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x180046d33  lea     rcx, aWinlogon; "Winlogon"
0x180046d3a  call    cs:__imp_SetPersistedRegistryString
0x180046d40  mov     rcx, [rsp+6A0h+StringSid]; hMem
0x180046d45  call    cs:__imp_LocalFree
0x180046d4b  mov     rcx, rbx; hMem
0x180046d4e  call    cs:__imp_LocalFree
0x180046d54  lea     r9, [rsp+6A0h+String1]
0x180046d59  lea     r8, aLastuseduserna; "LastUsedUsername"
0x180046d60  lea     rdx, aSoftwareMicros_33; "Software\\Microsoft\\Windows NT\\Curren"...
0x180046d67  lea     rcx, aWinlogon; "Winlogon"
0x180046d6e  call    cs:__imp_SetPersistedRegistryString
0x180046d74  mov     rcx, [rbp+5A0h+var_10]
0x180046d7b  xor     rcx, rsp; StackCookie
0x180046d7e  call    __security_check_cookie
0x180046d83  mov     rbx, [rsp+6A0h+arg_0]
0x180046d8b  add     rsp, 6A0h
0x180046d92  pop     rbp
0x180046d93  retn
```
