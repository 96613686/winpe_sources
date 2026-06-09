# OpenSystemDataRegistryPathForCurrentUser(ushort const *,HKEY__ * *)

- ea: `0x180009c84`
- end: `0x180009d9f`
- name: `?OpenSystemDataRegistryPathForCurrentUser@@YAJPEBGPEAPEAUHKEY__@@@Z`
- size: `283`
- prototype: `int(const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009a88`

## callees

- `0x180009bf8`
- `0x180009c84`
- `0x180009da8`
- `0x180016cc8`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009d51`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009d6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009d76`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009d6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180009d76`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009cdd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009cdd`

## string_xrefs

- `0x180009d03`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall OpenSystemDataRegistryPathForCurrentUser(const unsigned __int16 *a1, HKEY *a2)
{
  signed int CurrentUserSid; // ebx
  LSTATUS v4; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-238h] BYREF
  PSID Sid; // [rsp+48h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  *a2 = 0;
  Sid = 0;
  CurrentUserSid = GetCurrentUserSid(&Sid);
  if ( CurrentUserSid >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) || (CurrentUserSid = ResultFromKnownLastError(), CurrentUserSid >= 0) )
    {
      CurrentUserSid = StringCchPrintfW(
                         SubKey,
                         0x104u,
                         L"%s\\%s\\%s\\%s",
                         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                         StringSid,
                         L"AnyoneRead",
                         L"ScaleFactors");
      if ( CurrentUserSid >= 0 )
      {
        v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, a2);
        CurrentUserSid = v4;
        if ( v4 > 0 )
          CurrentUserSid = (unsigned __int16)v4 | 0x80070000;
      }
      LocalFree(StringSid);
    }
    LocalFree(Sid);
  }
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x180009c84  mov     [rsp+arg_0], rbx
0x180009c89  push    rdi
0x180009c8a  sub     rsp, 270h
0x180009c91  mov     rax, cs:__security_cookie
0x180009c98  xor     rax, rsp
0x180009c9b  mov     [rsp+278h+var_18], rax
0x180009ca3  lea     rcx, [rsp+278h+Sid]; void **
0x180009ca8  mov     qword ptr [rdx], 0
0x180009caf  mov     rdi, rdx
0x180009cb2  mov     [rsp+278h+Sid], 0
0x180009cbb  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x180009cc0  mov     ebx, eax
0x180009cc2  test    eax, eax
0x180009cc4  js      loc_180009D7C
0x180009cca  mov     rcx, [rsp+278h+Sid]; Sid
0x180009ccf  lea     rdx, [rsp+278h+StringSid]; StringSid
0x180009cd4  mov     [rsp+278h+StringSid], 0
0x180009cdd  call    cs:__imp_ConvertSidToStringSidW
0x180009ce3  test    eax, eax
0x180009ce5  jnz     short loc_180009CF2
0x180009ce7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180009cec  mov     ebx, eax
0x180009cee  test    eax, eax
0x180009cf0  js      short loc_180009D71
0x180009cf2  mov     rcx, [rsp+278h+StringSid]
0x180009cf7  lea     rax, ValueName; "ScaleFactors"
0x180009cfe  mov     [rsp+278h+var_248], rax
0x180009d03  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009d0a  mov     rax, cs:off_180026238; "AnyoneRead"
0x180009d11  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180009d18  mov     [rsp+278h+var_250], rax
0x180009d1d  mov     edx, 104h; unsigned __int64
0x180009d22  mov     [rsp+278h+phkResult], rcx
0x180009d27  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x180009d2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009d31  mov     ebx, eax
0x180009d33  test    eax, eax
0x180009d35  js      short loc_180009D66
0x180009d37  mov     r9d, 20019h; samDesired
0x180009d3d  mov     [rsp+278h+phkResult], rdi; phkResult
0x180009d42  xor     r8d, r8d; ulOptions
0x180009d45  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x180009d4a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009d51  call    cs:__imp_RegOpenKeyExW
0x180009d57  mov     ebx, eax
0x180009d59  test    eax, eax
0x180009d5b  jle     short loc_180009D66
0x180009d5d  movzx   ebx, ax
0x180009d60  or      ebx, 80070000h
0x180009d66  mov     rcx, [rsp+278h+StringSid]; hMem
0x180009d6b  call    cs:__imp_LocalFree
0x180009d71  mov     rcx, [rsp+278h+Sid]; hMem
0x180009d76  call    cs:__imp_LocalFree
0x180009d7c  mov     eax, ebx
0x180009d7e  mov     rcx, [rsp+278h+var_18]
0x180009d86  xor     rcx, rsp; StackCookie
0x180009d89  call    __security_check_cookie
0x180009d8e  mov     rbx, [rsp+278h+arg_0]
0x180009d96  add     rsp, 270h
0x180009d9d  pop     rdi
0x180009d9e  retn
```
