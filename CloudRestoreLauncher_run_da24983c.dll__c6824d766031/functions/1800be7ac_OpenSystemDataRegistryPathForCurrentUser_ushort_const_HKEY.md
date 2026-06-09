# OpenSystemDataRegistryPathForCurrentUser(ushort const *,HKEY__ * *)

- ea: `0x1800be7ac`
- end: `0x1800be8c7`
- name: `?OpenSystemDataRegistryPathForCurrentUser@@YAJPEBGPEAPEAUHKEY__@@@Z`
- size: `283`
- prototype: `int(const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bed9c`

## callees

- `0x18000c6e0`
- `0x1800124b4`
- `0x1800bdb98`
- `0x1800be7ac`
- `0x1800beb8c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800be893`
- `KERNEL32!LocalFree` at `0x1800be89e`
- `KERNEL32!LocalFree` at `0x1800be893`
- `KERNEL32!LocalFree` at `0x1800be89e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800be879`
- `ADVAPI32!RegOpenKeyExW` at `0x1800be879`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800be805`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800be805`

## string_xrefs

- `0x1800be82b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

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
                         &word_1801382A0);
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
0x1800be7ac  mov     [rsp+arg_0], rbx
0x1800be7b1  push    rdi
0x1800be7b2  sub     rsp, 270h
0x1800be7b9  mov     rax, cs:__security_cookie
0x1800be7c0  xor     rax, rsp
0x1800be7c3  mov     [rsp+278h+var_18], rax
0x1800be7cb  lea     rcx, [rsp+278h+Sid]; void **
0x1800be7d0  mov     qword ptr [rdx], 0
0x1800be7d7  mov     rdi, rdx
0x1800be7da  mov     [rsp+278h+Sid], 0
0x1800be7e3  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x1800be7e8  mov     ebx, eax
0x1800be7ea  test    eax, eax
0x1800be7ec  js      loc_1800BE8A4
0x1800be7f2  mov     rcx, [rsp+278h+Sid]; Sid
0x1800be7f7  lea     rdx, [rsp+278h+StringSid]; StringSid
0x1800be7fc  mov     [rsp+278h+StringSid], 0
0x1800be805  call    cs:__imp_ConvertSidToStringSidW
0x1800be80b  test    eax, eax
0x1800be80d  jnz     short loc_1800BE81A
0x1800be80f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800be814  mov     ebx, eax
0x1800be816  test    eax, eax
0x1800be818  js      short loc_1800BE899
0x1800be81a  mov     rcx, [rsp+278h+StringSid]
0x1800be81f  lea     rax, word_1801382A0
0x1800be826  mov     [rsp+278h+var_248], rax
0x1800be82b  lea     r9, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800be832  mov     rax, cs:off_1801328C0; "AnyoneRead"
0x1800be839  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800be840  mov     [rsp+278h+var_250], rax
0x1800be845  mov     edx, 104h; unsigned __int64
0x1800be84a  mov     [rsp+278h+phkResult], rcx
0x1800be84f  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x1800be854  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800be859  mov     ebx, eax
0x1800be85b  test    eax, eax
0x1800be85d  js      short loc_1800BE88E
0x1800be85f  mov     r9d, 20019h; samDesired
0x1800be865  mov     [rsp+278h+phkResult], rdi; phkResult
0x1800be86a  xor     r8d, r8d; ulOptions
0x1800be86d  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x1800be872  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800be879  call    cs:__imp_RegOpenKeyExW
0x1800be87f  mov     ebx, eax
0x1800be881  test    eax, eax
0x1800be883  jle     short loc_1800BE88E
0x1800be885  movzx   ebx, ax
0x1800be888  or      ebx, 80070000h
0x1800be88e  mov     rcx, [rsp+278h+StringSid]; hMem
0x1800be893  call    cs:__imp_LocalFree
0x1800be899  mov     rcx, [rsp+278h+Sid]; hMem
0x1800be89e  call    cs:__imp_LocalFree
0x1800be8a4  mov     eax, ebx
0x1800be8a6  mov     rcx, [rsp+278h+var_18]
0x1800be8ae  xor     rcx, rsp; StackCookie
0x1800be8b1  call    __security_check_cookie
0x1800be8b6  mov     rbx, [rsp+278h+arg_0]
0x1800be8be  add     rsp, 270h
0x1800be8c5  pop     rdi
0x1800be8c6  retn
```
