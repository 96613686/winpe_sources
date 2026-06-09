# JobHelper::GetJobs(std::list<_SwJob,std::allocator<_SwJob>> &)

- ea: `0x18000fa44`
- end: `0x18000fdf0`
- name: `?GetJobs@JobHelper@@QEAAJAEAV?$list@U_SwJob@@V?$allocator@U_SwJob@@@std@@@std@@@Z`
- size: `940`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000da10`
- `0x180010700`

## callees

- `0x180002a50`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a3c0`
- `0x18000a6a4`
- `0x18000b8b4`
- `0x18000bae8`
- `0x18000bd00`
- `0x18000ea88`
- `0x18000fa44`
- `0x18000fdf8`
- `0x180012a88`
- `0x180012ee0`
- `0x18001f420`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000fd1b`
- `ADVAPI32!RegCloseKey` at `0x18000fd1b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000fc10`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000fc10`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fb28`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fb28`
- `ADVAPI32!RegEnumKeyExW` at `0x18000fc9f`
- `ADVAPI32!RegEnumKeyExW` at `0x18000fc9f`
- `KERNEL32!GetLastError` at `0x18000fb99`
- `KERNEL32!GetLastError` at `0x18000fc44`
- `KERNEL32!GetLastError` at `0x18000fcc8`
- `KERNEL32!GetLastError` at `0x18000fb99`
- `KERNEL32!GetLastError` at `0x18000fc44`
- `KERNEL32!GetLastError` at `0x18000fcc8`
- `KERNEL32!EnterCriticalSection` at `0x18000faf5`
- `KERNEL32!EnterCriticalSection` at `0x18000faf5`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd2a`
- `KERNEL32!LeaveCriticalSection` at `0x18000fd2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobHelper::GetJobs(__int64 a1, __int64 a2)
{
  int Key; // eax
  unsigned int v5; // esi
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  LSTATUS v7; // eax
  char v8; // r14
  char LastError; // al
  int v10; // edx
  LSTATUS v11; // eax
  DWORD i; // r14d
  LSTATUS v13; // eax
  char v14; // r12
  char v15; // al
  _QWORD *v17; // rax
  int Job; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v23; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v24[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[320]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[256]; // [rsp+1E0h] [rbp+E0h] BYREF

  phkResult = 0;
  cSubKeys = 0;
  cchName = 255;
  v23 = 0;
  hKey = 0;
  Key = CurrentUserRegKeyHelper::GetKey(&v23, &hKey);
  v5 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        &WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
        (unsigned int)Key);
    v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
    goto LABEL_26;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 128));
  std::list<_SwJob>::clear(a2);
  v7 = RegOpenKeyExW(hKey, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\JobDB", 0, 0x20019u, &phkResult);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 == 2 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
      v5 = 0;
      goto LABEL_26;
    }
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_26;
    LastError = GetLastError();
    v10 = 77;
LABEL_15:
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\JobDB",
      v8,
      LastError);
    goto LABEL_26;
  }
  v11 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v8 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_26;
    LastError = GetLastError();
    v10 = 78;
    goto LABEL_15;
  }
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 255;
    v13 = RegEnumKeyExW(phkResult, i, Name, &cchName, 0, 0, 0, 0);
    v14 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v15 = GetLastError();
        WPP_SF_SdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\JobDB",
          v14,
          v15);
      }
    }
    else
    {
      _SwJob::_SwJob((_SwJob *)v25);
      v17 = (_QWORD *)std::wstring::wstring(v24, Name);
      Job = JobHelper::GetJob(a1, v17, (__int64)v25);
      v5 = Job;
      if ( Job >= 0 )
      {
        std::list<_SwJob>::push_back(a2, v25);
      }
      else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          (unsigned int)&WPP_9f155fbe94773387205a22e9edb85311_Traceguids,
          (unsigned int)Name,
          Job);
      }
      _SwJob::~_SwJob((_SwJob *)v25);
    }
  }
LABEL_26:
  if ( phkResult )
    RegCloseKey(phkResult);
  LeaveCriticalSection(v6);
  CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper((CurrentUserRegKeyHelper *)&v23);
  return v5;
}

```

## disassembly

```asm
0x18000fa44  mov     [rsp-8+arg_10], rbx
0x18000fa49  push    rbp
0x18000fa4a  push    rsi
0x18000fa4b  push    rdi
0x18000fa4c  push    r12
0x18000fa4e  push    r13
0x18000fa50  push    r14
0x18000fa52  push    r15
0x18000fa54  lea     rbp, [rsp-2F0h]
0x18000fa5c  sub     rsp, 3F0h
0x18000fa63  mov     rax, cs:__security_cookie
0x18000fa6a  xor     rax, rsp
0x18000fa6d  mov     [rbp+320h+var_40], rax
0x18000fa74  mov     r13, rdx
0x18000fa77  mov     r15, rcx
0x18000fa7a  xor     r12d, r12d
0x18000fa7d  mov     [rsp+420h+var_3B8], r12
0x18000fa82  mov     [rsp+420h+cSubKeys], r12d
0x18000fa87  mov     [rsp+420h+cchName], 0FFh
0x18000fa8f  mov     [rsp+420h+var_3A8], r12
0x18000fa94  mov     [rsp+420h+hKey], r12
0x18000fa99  lea     rdx, [rsp+420h+hKey]; HKEY *
0x18000fa9e  lea     rcx, [rsp+420h+var_3A8]; phkResult
0x18000faa3  call    ?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z; CurrentUserRegKeyHelper::GetKey(HKEY__ * &)
0x18000faa8  mov     esi, eax
0x18000faaa  test    eax, eax
0x18000faac  jns     short loc_18000FAEB
0x18000faae  lea     rdi, WPP_GLOBAL_Control
0x18000fab5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fabc  cmp     rcx, rdi
0x18000fabf  jz      short loc_18000FADF
0x18000fac1  test    byte ptr [rcx+1Ch], 4
0x18000fac5  jz      short loc_18000FADF
0x18000fac7  lea     edx, [r12+4Bh]
0x18000facc  mov     r9d, eax
0x18000facf  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000fad6  mov     rcx, [rcx+10h]
0x18000fada  call    WPP_SF_d
0x18000fadf  lea     rbx, [r15+80h]
0x18000fae6  jmp     loc_18000FD11
0x18000faeb  lea     rbx, [r15+80h]
0x18000faf2  mov     rcx, rbx; lpCriticalSection
0x18000faf5  call    cs:__imp_EnterCriticalSection
0x18000fafc  nop     dword ptr [rax+rax+00h]
0x18000fb01  mov     rcx, r13
0x18000fb04  call    ?clear@?$list@U_SwJob@@V?$allocator@U_SwJob@@@std@@@std@@QEAAXXZ; std::list<_SwJob>::clear(void)
0x18000fb09  lea     rax, [rsp+420h+var_3B8]
0x18000fb0e  mov     [rsp+420h+phkResult], rax; phkResult
0x18000fb13  mov     r9d, 20019h; samDesired
0x18000fb19  xor     r8d, r8d; ulOptions
0x18000fb1c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000fb23  mov     rcx, [rsp+420h+hKey]; hKey
0x18000fb28  call    cs:__imp_RegOpenKeyExW
0x18000fb2f  nop     dword ptr [rax+rax+00h]
0x18000fb34  mov     r14d, eax
0x18000fb37  test    eax, eax
0x18000fb39  jz      loc_18000FBD6
0x18000fb3f  cmp     eax, 2
0x18000fb42  jnz     short loc_18000FB78
0x18000fb44  lea     rdi, WPP_GLOBAL_Control
0x18000fb4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb52  cmp     rcx, rdi
0x18000fb55  jz      short loc_18000FB70
0x18000fb57  test    byte ptr [rcx+1Ch], 1
0x18000fb5b  jz      short loc_18000FB70
0x18000fb5d  lea     edx, [rax+4Ah]
0x18000fb60  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000fb67  mov     rcx, [rcx+10h]
0x18000fb6b  call    WPP_SF_
0x18000fb70  mov     esi, r12d
0x18000fb73  jmp     loc_18000FD11
0x18000fb78  lea     rdi, WPP_GLOBAL_Control
0x18000fb7f  mov     rax, cs:WPP_GLOBAL_Control
0x18000fb86  cmp     rax, rdi
0x18000fb89  jz      loc_18000FD11
0x18000fb8f  test    byte ptr [rax+1Ch], 4
0x18000fb93  jz      loc_18000FD11
0x18000fb99  call    cs:__imp_GetLastError
0x18000fba0  nop     dword ptr [rax+rax+00h]
0x18000fba5  mov     edx, 4Dh ; 'M'
0x18000fbaa  mov     dword ptr [rsp+420h+lpcbMaxSubKeyLen], eax
0x18000fbae  mov     dword ptr [rsp+420h+phkResult], r14d
0x18000fbb3  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000fbba  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000fbc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbc8  mov     rcx, [rcx+10h]
0x18000fbcc  call    WPP_SF_SdD
0x18000fbd1  jmp     loc_18000FD11
0x18000fbd6  mov     [rsp+420h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18000fbdb  mov     [rsp+420h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000fbe0  mov     [rsp+420h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18000fbe5  mov     [rsp+420h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18000fbea  mov     [rsp+420h+lpcValues], r12; lpcValues
0x18000fbef  mov     [rsp+420h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18000fbf4  mov     [rsp+420h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18000fbf9  lea     rax, [rsp+420h+cSubKeys]
0x18000fbfe  mov     [rsp+420h+phkResult], rax; lpcSubKeys
0x18000fc03  xor     r9d, r9d; lpReserved
0x18000fc06  xor     r8d, r8d; lpcchClass
0x18000fc09  xor     edx, edx; lpClass
0x18000fc0b  mov     rcx, [rsp+420h+var_3B8]; hKey
0x18000fc10  call    cs:__imp_RegQueryInfoKeyW
0x18000fc17  nop     dword ptr [rax+rax+00h]
0x18000fc1c  mov     r14d, eax
0x18000fc1f  test    eax, eax
0x18000fc21  jz      short loc_18000FC5A
0x18000fc23  lea     rdi, WPP_GLOBAL_Control
0x18000fc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc31  cmp     rcx, rdi
0x18000fc34  jz      loc_18000FD11
0x18000fc3a  test    byte ptr [rcx+1Ch], 4
0x18000fc3e  jz      loc_18000FD11
0x18000fc44  call    cs:__imp_GetLastError
0x18000fc4b  nop     dword ptr [rax+rax+00h]
0x18000fc50  mov     edx, 4Eh ; 'N'
0x18000fc55  jmp     loc_18000FBAA
0x18000fc5a  mov     r14d, r12d
0x18000fc5d  cmp     [rsp+420h+cSubKeys], r12d
0x18000fc62  jbe     loc_18000FD11
0x18000fc68  lea     rdi, WPP_GLOBAL_Control
0x18000fc6f  mov     [rsp+420h+cchName], 0FFh
0x18000fc77  mov     [rsp+420h+lpcValues], r12; lpftLastWriteTime
0x18000fc7c  mov     [rsp+420h+lpcbMaxClassLen], r12; lpcchClass
0x18000fc81  mov     [rsp+420h+lpcbMaxSubKeyLen], r12; lpClass
0x18000fc86  mov     [rsp+420h+phkResult], r12; lpReserved
0x18000fc8b  lea     r9, [rsp+420h+cchName]; lpcchName
0x18000fc90  lea     r8, [rbp+320h+Name]; lpName
0x18000fc97  mov     edx, r14d; dwIndex
0x18000fc9a  mov     rcx, [rsp+420h+var_3B8]; hKey
0x18000fc9f  call    cs:__imp_RegEnumKeyExW
0x18000fca6  nop     dword ptr [rax+rax+00h]
0x18000fcab  mov     r12d, eax
0x18000fcae  test    eax, eax
0x18000fcb0  jz      loc_18000FD6E
0x18000fcb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcbd  cmp     rcx, rdi
0x18000fcc0  jz      short loc_18000FD00
0x18000fcc2  test    byte ptr [rcx+1Ch], 4
0x18000fcc6  jz      short loc_18000FD00
0x18000fcc8  call    cs:__imp_GetLastError
0x18000fccf  nop     dword ptr [rax+rax+00h]
0x18000fcd4  mov     edx, 4Fh ; 'O'
0x18000fcd9  mov     dword ptr [rsp+420h+lpcbMaxSubKeyLen], eax
0x18000fcdd  mov     dword ptr [rsp+420h+phkResult], r12d
0x18000fce2  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000fce9  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000fcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcf7  mov     rcx, [rcx+10h]
0x18000fcfb  call    WPP_SF_SdD
0x18000fd00  xor     r12d, r12d
0x18000fd03  inc     r14d
0x18000fd06  cmp     r14d, [rsp+420h+cSubKeys]
0x18000fd0b  jb      loc_18000FC6F
0x18000fd11  mov     rcx, [rsp+420h+var_3B8]; hKey
0x18000fd16  test    rcx, rcx
0x18000fd19  jz      short loc_18000FD27
0x18000fd1b  call    cs:__imp_RegCloseKey
0x18000fd22  nop     dword ptr [rax+rax+00h]
0x18000fd27  mov     rcx, rbx; lpCriticalSection
0x18000fd2a  call    cs:__imp_LeaveCriticalSection
0x18000fd31  nop     dword ptr [rax+rax+00h]
0x18000fd36  nop
0x18000fd37  lea     rcx, [rsp+420h+var_3A8]; this
0x18000fd3c  call    ??1CurrentUserRegKeyHelper@@QEAA@XZ; CurrentUserRegKeyHelper::~CurrentUserRegKeyHelper(void)
0x18000fd41  mov     eax, esi
0x18000fd43  mov     rcx, [rbp+320h+var_40]
0x18000fd4a  xor     rcx, rsp; StackCookie
0x18000fd4d  call    __security_check_cookie
0x18000fd52  mov     rbx, [rsp+420h+arg_10]
0x18000fd5a  add     rsp, 3F0h
0x18000fd61  pop     r15
0x18000fd63  pop     r14
0x18000fd65  pop     r13
0x18000fd67  pop     r12
0x18000fd69  pop     rdi
0x18000fd6a  pop     rsi
0x18000fd6b  pop     rbp
0x18000fd6c  retn
0x18000fd6e  lea     rcx, [rbp+320h+var_380]; this
0x18000fd72  call    ??0_SwJob@@QEAA@XZ; _SwJob::_SwJob(void)
0x18000fd77  nop
0x18000fd78  lea     rdx, [rbp+320h+Name]
0x18000fd7f  lea     rcx, [rbp+320h+var_3A0]
0x18000fd83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000fd88  lea     r8, [rbp+320h+var_380]
0x18000fd8c  mov     rdx, rax
0x18000fd8f  mov     rcx, r15
0x18000fd92  call    ?GetJob@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SwJob@@@Z; JobHelper::GetJob(std::wstring,_SwJob &)
0x18000fd97  mov     esi, eax
0x18000fd99  xor     r12d, r12d
0x18000fd9c  test    eax, eax
0x18000fd9e  jns     short loc_18000FDE1
0x18000fda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fda7  cmp     rcx, rdi
0x18000fdaa  jz      short loc_18000FDD3
0x18000fdac  test    byte ptr [rcx+1Ch], 4
0x18000fdb0  jz      short loc_18000FDD3
0x18000fdb2  lea     edx, [r12+50h]
0x18000fdb7  mov     dword ptr [rsp+420h+phkResult], eax
0x18000fdbb  lea     r9, [rbp+320h+Name]
0x18000fdc2  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x18000fdc9  mov     rcx, [rcx+10h]
0x18000fdcd  call    WPP_SF_Sd
0x18000fdd2  nop
0x18000fdd3  lea     rcx, [rbp+320h+var_380]; this
0x18000fdd7  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x18000fddc  jmp     loc_18000FD03
0x18000fde1  lea     rdx, [rbp+320h+var_380]
0x18000fde5  mov     rcx, r13
0x18000fde8  call    ?push_back@?$list@U_SwJob@@V?$allocator@U_SwJob@@@std@@@std@@QEAAXAEBU_SwJob@@@Z; std::list<_SwJob>::push_back(_SwJob const &)
0x18000fded  jmp     short loc_18000FDD3
```
