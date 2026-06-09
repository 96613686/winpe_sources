# _RegGetAndDeleteUsernameFromSID

- ea: `0x180060f14`
- end: `0x18006104b`
- name: `_RegGetAndDeleteUsernameFromSID`
- size: `311`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180092080`

## callees

- `0x180060f14`
- `0x18006c000`
- `0x180087638`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180061018`
- `KERNEL32!LocalFree` at `0x180061018`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180060f79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180060f79`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061004`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061004`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180060fb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180060fb0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180060ff0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180060ff0`

## string_xrefs

- `0x180060f5c`: `DefaultSID`
- `0x180060ffa`: `DefaultSID`

## pseudocode

```c
__int64 __fastcall RegGetAndDeleteUsernameFromSID(HKEY hKey, __int64 a2, _WORD *pvData)
{
  int ValueW; // ebx
  bool v6; // sf
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName[3]; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName[4]; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+70h] [rbp-90h] BYREF

  cchName[0] = 256;
  pcbData = 512;
  ValueW = RegGetValueW(hKey, 0, L"DefaultSID", 2u, 0, pvData, &pcbData);
  if ( ValueW )
  {
    *pvData = 0;
    v6 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_5;
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  v6 = ValueW < 0;
LABEL_5:
  if ( !v6 )
  {
    Sid = 0;
    if ( ConvertStringSidToSidW(pvData, &Sid) )
    {
      cchReferencedDomainName[0] = 260;
      pcbData = 0;
      if ( LookupAccountSidLocalW(
             Sid,
             pvData,
             cchName,
             ReferencedDomainName,
             cchReferencedDomainName,
             (PSID_NAME_USE)&pcbData) )
      {
        RegDeleteValueW(hKey, L"DefaultSID");
      }
      else
      {
        ValueW = ResultFromLastError();
      }
      LocalFree(Sid);
    }
    else
    {
      return (unsigned int)ResultFromLastError();
    }
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180060f14  mov     [rsp-8+arg_8], rbx
0x180060f19  push    rbp
0x180060f1a  push    rsi
0x180060f1b  push    rdi
0x180060f1c  lea     rbp, [rsp-190h]
0x180060f24  sub     rsp, 290h
0x180060f2b  mov     rax, cs:__security_cookie
0x180060f32  xor     rax, rsp
0x180060f35  mov     [rbp+1A0h+var_20], rax
0x180060f3c  lea     rax, [rsp+2A0h+var_260]
0x180060f41  mov     [rsp+2A0h+cchName], 100h
0x180060f49  mov     [rsp+2A0h+pcbData], rax; pcbData
0x180060f4e  mov     rdi, r8
0x180060f51  mov     [rsp+2A0h+pvData], r8; pvData
0x180060f56  mov     r9d, 2; dwFlags
0x180060f5c  lea     r8, aDefaultsid; "DefaultSID"
0x180060f63  mov     [rsp+2A0h+var_260], 200h
0x180060f6b  xor     edx, edx; lpSubKey
0x180060f6d  mov     [rsp+2A0h+pdwType], 0; pdwType
0x180060f76  mov     rsi, rcx
0x180060f79  call    cs:__imp_RegGetValueW
0x180060f7f  mov     ebx, eax
0x180060f81  test    eax, eax
0x180060f83  jz      short loc_180060F97
0x180060f85  xor     eax, eax
0x180060f87  mov     [rdi], ax
0x180060f8a  test    ebx, ebx
0x180060f8c  jle     short loc_180060F99
0x180060f8e  movzx   ebx, bx
0x180060f91  or      ebx, 80070000h
0x180060f97  test    ebx, ebx
0x180060f99  js      loc_180061027
0x180060f9f  lea     rdx, [rsp+2A0h+Sid]; Sid
0x180060fa4  mov     [rsp+2A0h+Sid], 0
0x180060fad  mov     rcx, rdi; StringSid
0x180060fb0  call    cs:__imp_ConvertStringSidToSidW
0x180060fb6  test    eax, eax
0x180060fb8  jz      short loc_180061020
0x180060fba  mov     rcx, [rsp+2A0h+Sid]; Sid
0x180060fbf  lea     rax, [rsp+2A0h+var_260]
0x180060fc4  mov     [rsp+2A0h+pvData], rax; peUse
0x180060fc9  lea     r9, [rsp+2A0h+ReferencedDomainName]; ReferencedDomainName
0x180060fce  lea     rax, [rsp+2A0h+cchReferencedDomainName]
0x180060fd3  mov     [rsp+2A0h+cchReferencedDomainName], 104h
0x180060fdb  lea     r8, [rsp+2A0h+cchName]; cchName
0x180060fe0  mov     [rsp+2A0h+pdwType], rax; cchReferencedDomainName
0x180060fe5  mov     rdx, rdi; Name
0x180060fe8  mov     [rsp+2A0h+var_260], 0
0x180060ff0  call    cs:__imp_LookupAccountSidLocalW
0x180060ff6  test    eax, eax
0x180060ff8  jz      short loc_18006100C
0x180060ffa  lea     rdx, aDefaultsid; "DefaultSID"
0x180061001  mov     rcx, rsi; hKey
0x180061004  call    cs:__imp_RegDeleteValueW
0x18006100a  jmp     short loc_180061013
0x18006100c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180061011  mov     ebx, eax
0x180061013  mov     rcx, [rsp+2A0h+Sid]; hMem
0x180061018  call    cs:__imp_LocalFree
0x18006101e  jmp     short loc_180061027
0x180061020  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180061025  mov     ebx, eax
0x180061027  mov     eax, ebx
0x180061029  mov     rcx, [rbp+1A0h+var_20]
0x180061030  xor     rcx, rsp; StackCookie
0x180061033  call    __security_check_cookie
0x180061038  mov     rbx, [rsp+2A0h+arg_8]
0x180061040  add     rsp, 290h
0x180061047  pop     rdi
0x180061048  pop     rsi
0x180061049  pop     rbp
0x18006104a  retn
```
