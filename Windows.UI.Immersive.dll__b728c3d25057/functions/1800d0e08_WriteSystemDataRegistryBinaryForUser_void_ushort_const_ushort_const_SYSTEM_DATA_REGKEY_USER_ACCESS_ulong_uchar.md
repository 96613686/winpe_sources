# WriteSystemDataRegistryBinaryForUser(void *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,ulong,uchar *)

- ea: `0x1800d0e08`
- end: `0x1800d0f28`
- name: `?WriteSystemDataRegistryBinaryForUser@@YAJPEAXPEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@KPEAE@Z`
- size: `288`
- prototype: `int __high(void *, const unsigned __int16 *, const unsigned __int16 *, enum SYSTEM_DATA_REGKEY_USER_ACCESS, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f690`

## callees

- `0x18000d2b8`
- `0x18003aa84`
- `0x180050ba0`
- `0x1800d0e08`
- `0x1800d0f30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d0efd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d0efd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ef2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d0ef2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d0ee5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d0ee5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d0e45`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800d0e45`

## string_xrefs

- `0x1800d0e63`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall WriteSystemDataRegistryBinaryForUser(
        void *a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        DWORD cbData,
        BYTE *lpData)
{
  LSTATUS RegKeyWithSDDL; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  LPWSTR StringSid; // [rsp+48h] [rbp-240h] BYREF
  unsigned __int16 v13[264]; // [rsp+50h] [rbp-238h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (RegKeyWithSDDL = ResultFromKnownLastError(), RegKeyWithSDDL >= 0) )
  {
    RegKeyWithSDDL = StringCchPrintfW(
                       v13,
                       0x104u,
                       L"%s\\%s\\%s\\%s",
                       L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
                       StringSid,
                       L"AnyoneRead",
                       a2);
    if ( RegKeyWithSDDL >= 0 )
    {
      RegKeyWithSDDL = _CreateRegKeyWithSDDL(v10, v9, v13);
      if ( RegKeyWithSDDL >= 0 )
      {
        RegKeyWithSDDL = RegSetValueExW(0, a3, 0, 3u, lpData, cbData);
        RegCloseKey(0);
      }
    }
    LocalFree(StringSid);
  }
  return (unsigned int)RegKeyWithSDDL;
}

```

## disassembly

```asm
0x1800d0e08  mov     [rsp+arg_18], rbx
0x1800d0e0d  push    rbp
0x1800d0e0e  push    rsi
0x1800d0e0f  push    rdi
0x1800d0e10  sub     rsp, 270h
0x1800d0e17  mov     rax, cs:__security_cookie
0x1800d0e1e  xor     rax, rsp
0x1800d0e21  mov     [rsp+288h+var_28], rax
0x1800d0e29  mov     rbp, [rsp+288h+arg_28]
0x1800d0e31  mov     rdi, rdx
0x1800d0e34  lea     rdx, [rsp+288h+StringSid]; StringSid
0x1800d0e39  mov     [rsp+288h+StringSid], 0
0x1800d0e42  mov     rsi, r8
0x1800d0e45  call    cs:__imp_ConvertSidToStringSidW
0x1800d0e4b  test    eax, eax
0x1800d0e4d  jnz     short loc_1800D0E5E
0x1800d0e4f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800d0e54  mov     ebx, eax
0x1800d0e56  test    eax, eax
0x1800d0e58  js      loc_1800D0F03
0x1800d0e5e  mov     rcx, [rsp+288h+StringSid]
0x1800d0e63  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800d0e6a  mov     rax, cs:off_1800E67F8; "AnyoneRead"
0x1800d0e71  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800d0e78  mov     [rsp+288h+var_258], rdi
0x1800d0e7d  mov     edx, 104h; unsigned __int64
0x1800d0e82  mov     qword ptr [rsp+288h+cbData], rax
0x1800d0e87  mov     [rsp+288h+lpData], rcx
0x1800d0e8c  lea     rcx, [rsp+288h+var_238]; unsigned __int16 *
0x1800d0e91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d0e96  mov     ebx, eax
0x1800d0e98  test    eax, eax
0x1800d0e9a  js      short loc_1800D0EF8
0x1800d0e9c  lea     rax, [rsp+288h+hKey]
0x1800d0ea1  mov     [rsp+288h+hKey], 0
0x1800d0eaa  mov     qword ptr [rsp+288h+cbData], rax
0x1800d0eaf  lea     r8, [rsp+288h+var_238]
0x1800d0eb4  mov     byte ptr [rsp+288h+lpData], 0
0x1800d0eb9  call    ?_CreateRegKeyWithSDDL@@YAJPEAUHKEY__@@PEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@_NPEAPEAU1@@Z; _CreateRegKeyWithSDDL(HKEY__ *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,bool,HKEY__ * *)
0x1800d0ebe  mov     ebx, eax
0x1800d0ec0  test    eax, eax
0x1800d0ec2  js      short loc_1800D0EF8
0x1800d0ec4  mov     eax, [rsp+288h+arg_20]
0x1800d0ecb  mov     r9d, 3; dwType
0x1800d0ed1  mov     rcx, [rsp+288h+hKey]; hKey
0x1800d0ed6  xor     r8d, r8d; Reserved
0x1800d0ed9  mov     [rsp+288h+cbData], eax; cbData
0x1800d0edd  mov     rdx, rsi; lpValueName
0x1800d0ee0  mov     [rsp+288h+lpData], rbp; lpData
0x1800d0ee5  call    cs:__imp_RegSetValueExW
0x1800d0eeb  mov     rcx, [rsp+288h+hKey]; hKey
0x1800d0ef0  mov     ebx, eax
0x1800d0ef2  call    cs:__imp_RegCloseKey
0x1800d0ef8  mov     rcx, [rsp+288h+StringSid]; hMem
0x1800d0efd  call    cs:__imp_LocalFree
0x1800d0f03  mov     eax, ebx
0x1800d0f05  mov     rcx, [rsp+288h+var_28]
0x1800d0f0d  xor     rcx, rsp; StackCookie
0x1800d0f10  call    __security_check_cookie
0x1800d0f15  mov     rbx, [rsp+288h+arg_18]
0x1800d0f1d  add     rsp, 270h
0x1800d0f24  pop     rdi
0x1800d0f25  pop     rsi
0x1800d0f26  pop     rbp
0x1800d0f27  retn
```
