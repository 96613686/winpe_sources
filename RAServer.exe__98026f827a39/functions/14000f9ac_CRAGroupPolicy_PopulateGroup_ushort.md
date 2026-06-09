# CRAGroupPolicy::PopulateGroup(ushort *)

- ea: `0x14000f9ac`
- end: `0x14000fc05`
- name: `?PopulateGroup@CRAGroupPolicy@@AEAAKPEAG@Z`
- size: `601`
- prototype: `__int64 __fastcall(CRAGroupPolicy *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000ff18`

## callees

- `0x14000f9ac`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000faa4`
- `ADVAPI32!RegOpenKeyExW` at `0x14000faa4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000fb12`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000fb12`
- `ADVAPI32!RegCloseKey` at `0x14000fbca`
- `ADVAPI32!RegCloseKey` at `0x14000fbca`
- `ADVAPI32!RegEnumValueW` at `0x14000fb67`
- `ADVAPI32!RegEnumValueW` at `0x14000fb67`
- `samcli!NetLocalGroupAddMembers` at `0x14000fbae`
- `samcli!NetLocalGroupAddMembers` at `0x14000fbae`
- `samcli!NetLocalGroupGetMembers` at `0x14000fa26`
- `samcli!NetLocalGroupGetMembers` at `0x14000fa26`
- `samcli!NetLocalGroupDelMembers` at `0x14000fa71`
- `samcli!NetLocalGroupDelMembers` at `0x14000fa71`
- `netutils!NetApiBufferFree` at `0x14000fbde`
- `netutils!NetApiBufferFree` at `0x14000fbde`

## string_xrefs

- `0x14000fa42`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000fac2`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000fb76`: `base\diagnosis\ra\dcom\src\gpsettings.cpp`
- `0x14000fa96`: `Software\Policies\Microsoft\Windows NT\Terminal Services\RAUnsolicit`

## pseudocode

```c
__int64 __fastcall CRAGroupPolicy::PopulateGroup(CRAGroupPolicy *this, unsigned __int16 *a2)
{
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  CEventLogger *v4; // rcx
  unsigned int v5; // r9d
  unsigned int v6; // edi
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  unsigned int v9; // r9d
  DWORD i; // esi
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  DWORD entriesread; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  DWORD totalentries; // [rsp+78h] [rbp-88h] BYREF
  LPBYTE bufptr; // [rsp+80h] [rbp-80h] BYREF
  BYTE buf[8]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR ValueName[264]; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)buf = 0;
  cValues = 0;
  cchValueName = 0;
  phkResult = 0;
  bufptr = 0;
  entriesread = 0;
  totalentries = 0;
  if ( NetLocalGroupGetMembers(0, a2, 0, &bufptr, 0xFFFFFFFF, &entriesread, &totalentries, 0) )
  {
    v5 = 1956;
LABEL_3:
    CEventLogger::LogError(
      v4,
      v3,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v5,
      L"CRAGroupPolicy::PopulateGroup",
      0);
    v6 = 12;
    goto LABEL_16;
  }
  if ( NetLocalGroupDelMembers(0, a2, 0, bufptr, entriesread) )
  {
    v5 = 1973;
    goto LABEL_3;
  }
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\RAUnsolicit",
         0,
         0x20019u,
         &phkResult);
  if ( v6 )
  {
    v9 = 1989;
LABEL_8:
    CEventLogger::LogError(
      v8,
      v7,
      L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
      v9,
      L"CRAGroupPolicy::PopulateGroup",
      0);
    goto LABEL_16;
  }
  v6 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  if ( v6 )
  {
    v9 = 2010;
    goto LABEL_8;
  }
  for ( i = 0; i < cValues; ++i )
  {
    cchValueName = 260;
    if ( RegEnumValueW(phkResult, i, ValueName, &cchValueName, 0, 0, 0, 0) )
    {
      CEventLogger::LogError(
        v12,
        v11,
        L"base\\diagnosis\\ra\\dcom\\src\\gpsettings.cpp",
        0x7EEu,
        L"CRAGroupPolicy::PopulateGroup",
        0);
    }
    else
    {
      *(_QWORD *)buf = ValueName;
      NetLocalGroupAddMembers(0, a2, 3u, buf, 1u);
    }
  }
LABEL_16:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v6;
}

```

## disassembly

```asm
0x14000f9ac  push    rbp
0x14000f9ae  push    rbx
0x14000f9af  push    rsi
0x14000f9b0  push    rdi
0x14000f9b1  push    r14
0x14000f9b3  push    r15
0x14000f9b5  lea     rbp, [rsp-1B8h]
0x14000f9bd  sub     rsp, 2B8h
0x14000f9c4  mov     rax, cs:__security_cookie
0x14000f9cb  xor     rax, rsp
0x14000f9ce  mov     [rbp+1E0h+var_40], rax
0x14000f9d5  xor     r15d, r15d
0x14000f9d8  lea     rax, [rsp+2E0h+var_268]
0x14000f9dd  mov     [rsp+2E0h+resumehandle], r15; resumehandle
0x14000f9e2  lea     r9, [rbp+1E0h+bufptr]; bufptr
0x14000f9e6  mov     [rsp+2E0h+totalentries], rax; totalentries
0x14000f9eb  xor     r8d, r8d; level
0x14000f9ee  lea     rax, [rsp+2E0h+var_27C]
0x14000f9f3  mov     qword ptr [rbp+1E0h+buf], r15
0x14000f9f7  mov     [rsp+2E0h+entriesread], rax; entriesread
0x14000f9fc  xor     ecx, ecx; servername
0x14000f9fe  mov     [rsp+2E0h+prefmaxlen], 0FFFFFFFFh; prefmaxlen
0x14000fa06  mov     r14, rdx
0x14000fa09  mov     [rsp+2E0h+cValues], r15d
0x14000fa0e  mov     [rsp+2E0h+cchValueName], r15d
0x14000fa13  mov     [rsp+2E0h+phkResult], r15
0x14000fa18  mov     [rbp+1E0h+bufptr], r15
0x14000fa1c  mov     [rsp+2E0h+var_27C], r15d
0x14000fa21  mov     [rsp+2E0h+var_268], r15d
0x14000fa26  call    cs:__imp_NetLocalGroupGetMembers
0x14000fa2c  test    eax, eax
0x14000fa2e  jz      short loc_14000FA5D
0x14000fa30  mov     r9d, 7A4h; unsigned int
0x14000fa36  lea     rbx, aCragrouppolicy_6; "CRAGroupPolicy::PopulateGroup"
0x14000fa3d  mov     dword ptr [rsp+2E0h+entriesread], r15d; unsigned int
0x14000fa42  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fa49  mov     qword ptr [rsp+2E0h+prefmaxlen], rbx; unsigned __int16 *
0x14000fa4e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fa53  mov     edi, 0Ch
0x14000fa58  jmp     loc_14000FBC0
0x14000fa5d  mov     eax, [rsp+2E0h+var_27C]
0x14000fa61  xor     r8d, r8d; level
0x14000fa64  mov     r9, [rbp+1E0h+bufptr]; buf
0x14000fa68  mov     rdx, r14; groupname
0x14000fa6b  xor     ecx, ecx; servername
0x14000fa6d  mov     [rsp+2E0h+prefmaxlen], eax; totalentries
0x14000fa71  call    cs:__imp_NetLocalGroupDelMembers
0x14000fa77  test    eax, eax
0x14000fa79  jz      short loc_14000FA83
0x14000fa7b  mov     r9d, 7B5h
0x14000fa81  jmp     short loc_14000FA36
0x14000fa83  lea     rax, [rsp+2E0h+phkResult]
0x14000fa88  mov     r9d, 20019h; samDesired
0x14000fa8e  xor     r8d, r8d; ulOptions
0x14000fa91  mov     qword ptr [rsp+2E0h+prefmaxlen], rax; phkResult
0x14000fa96  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x14000fa9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000faa4  call    cs:__imp_RegOpenKeyExW
0x14000faaa  mov     edi, eax
0x14000faac  test    eax, eax
0x14000faae  jz      short loc_14000FAD8
0x14000fab0  mov     r9d, 7C5h; unsigned int
0x14000fab6  lea     rbx, aCragrouppolicy_6; "CRAGroupPolicy::PopulateGroup"
0x14000fabd  mov     dword ptr [rsp+2E0h+entriesread], r15d; unsigned int
0x14000fac2  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fac9  mov     qword ptr [rsp+2E0h+prefmaxlen], rbx; unsigned __int16 *
0x14000face  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fad3  jmp     loc_14000FBC0
0x14000fad8  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x14000fadd  lea     rax, [rsp+2E0h+cValues]
0x14000fae2  mov     [rsp+2E0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14000fae7  xor     r9d, r9d; lpReserved
0x14000faea  mov     [rsp+2E0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14000faef  xor     r8d, r8d; lpcchClass
0x14000faf2  mov     [rsp+2E0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14000faf7  xor     edx, edx; lpClass
0x14000faf9  mov     [rsp+2E0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14000fafe  mov     [rsp+2E0h+resumehandle], rax; lpcValues
0x14000fb03  mov     [rsp+2E0h+totalentries], r15; lpcbMaxClassLen
0x14000fb08  mov     [rsp+2E0h+entriesread], r15; lpcbMaxSubKeyLen
0x14000fb0d  mov     qword ptr [rsp+2E0h+prefmaxlen], r15; lpcSubKeys
0x14000fb12  call    cs:__imp_RegQueryInfoKeyW
0x14000fb18  mov     edi, eax
0x14000fb1a  test    eax, eax
0x14000fb1c  jz      short loc_14000FB26
0x14000fb1e  mov     r9d, 7DAh
0x14000fb24  jmp     short loc_14000FAB6
0x14000fb26  mov     esi, r15d
0x14000fb29  cmp     [rsp+2E0h+cValues], r15d
0x14000fb2e  jbe     loc_14000FBC0
0x14000fb34  lea     rbx, aCragrouppolicy_6; "CRAGroupPolicy::PopulateGroup"
0x14000fb3b  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x14000fb40  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x14000fb45  mov     [rsp+2E0h+resumehandle], r15; lpcbData
0x14000fb4a  lea     r8, [rbp+1E0h+ValueName]; lpValueName
0x14000fb4e  mov     [rsp+2E0h+totalentries], r15; lpData
0x14000fb53  mov     edx, esi; dwIndex
0x14000fb55  mov     [rsp+2E0h+entriesread], r15; lpType
0x14000fb5a  mov     qword ptr [rsp+2E0h+prefmaxlen], r15; lpReserved
0x14000fb5f  mov     [rsp+2E0h+cchValueName], 104h
0x14000fb67  call    cs:__imp_RegEnumValueW
0x14000fb6d  test    eax, eax
0x14000fb6f  jz      short loc_14000FB8F
0x14000fb71  mov     dword ptr [rsp+2E0h+entriesread], r15d; unsigned int
0x14000fb76  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\dcom\\src\\gpsetti"...
0x14000fb7d  mov     r9d, 7EEh; unsigned int
0x14000fb83  mov     qword ptr [rsp+2E0h+prefmaxlen], rbx; unsigned __int16 *
0x14000fb88  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14000fb8d  jmp     short loc_14000FBB4
0x14000fb8f  lea     rax, [rbp+1E0h+ValueName]
0x14000fb93  mov     [rsp+2E0h+prefmaxlen], 1; totalentries
0x14000fb9b  lea     r9, [rbp+1E0h+buf]; buf
0x14000fb9f  mov     qword ptr [rbp+1E0h+buf], rax
0x14000fba3  mov     r8d, 3; level
0x14000fba9  mov     rdx, r14; groupname
0x14000fbac  xor     ecx, ecx; servername
0x14000fbae  call    cs:__imp_NetLocalGroupAddMembers
0x14000fbb4  inc     esi
0x14000fbb6  cmp     esi, [rsp+2E0h+cValues]
0x14000fbba  jb      loc_14000FB3B
0x14000fbc0  mov     rcx, [rsp+2E0h+phkResult]; hKey
0x14000fbc5  test    rcx, rcx
0x14000fbc8  jz      short loc_14000FBD5
0x14000fbca  call    cs:__imp_RegCloseKey
0x14000fbd0  mov     [rsp+2E0h+phkResult], r15
0x14000fbd5  mov     rcx, [rbp+1E0h+bufptr]; Buffer
0x14000fbd9  test    rcx, rcx
0x14000fbdc  jz      short loc_14000FBE4
0x14000fbde  call    cs:__imp_NetApiBufferFree
0x14000fbe4  mov     eax, edi
0x14000fbe6  mov     rcx, [rbp+1E0h+var_40]
0x14000fbed  xor     rcx, rsp; StackCookie
0x14000fbf0  call    __security_check_cookie
0x14000fbf5  add     rsp, 2B8h
0x14000fbfc  pop     r15
0x14000fbfe  pop     r14
0x14000fc00  pop     rdi
0x14000fc01  pop     rsi
0x14000fc02  pop     rbx
0x14000fc03  pop     rbp
0x14000fc04  retn
```
