# JobHelper::GetJobs(std::list<_Job,std::allocator<_Job>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,JobFilter)

- ea: `0x14001984c`
- end: `0x140019ba0`
- name: `?GetJobs@JobHelper@@SAJAEAV?$list@U_Job@@V?$allocator@U_Job@@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@KW4JobFilter@@@Z`
- size: `852`
- prototype: `__int64 __fastcall(__int64, HKEY, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140004128`

## callees

- `0x1400036ac`
- `0x140003d00`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x140008e80`
- `0x140009598`
- `0x140011c90`
- `0x140011d58`
- `0x140019054`
- `0x14001984c`
- `0x14001a688`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001991e`
- `ADVAPI32!RegOpenKeyExW` at `0x14001991e`
- `ADVAPI32!RegCloseKey` at `0x140019b43`
- `ADVAPI32!RegCloseKey` at `0x140019b43`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400199c1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400199c1`
- `ADVAPI32!RegEnumKeyExW` at `0x140019a0d`
- `ADVAPI32!RegEnumKeyExW` at `0x140019a0d`
- `KERNEL32!LeaveCriticalSection` at `0x140019b50`
- `KERNEL32!LeaveCriticalSection` at `0x140019b50`
- `KERNEL32!EnterCriticalSection` at `0x1400198b8`
- `KERNEL32!EnterCriticalSection` at `0x1400198b8`

## string_xrefs

- `0x1400198e3`: `\MSI\`
- `0x140019965`: `RegOpenKeyExW for %1 failed with Status = %2!d!`
- `0x140019a2a`: `RegOpenKeyExW for %1 failed with Status = %2!d!`

## pseudocode

```c
__int64 __fastcall JobHelper::GetJobs(__int64 a1, HKEY a2, int a3)
{
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  int v8; // ebx
  HKEY v9; // rdx
  LPCWSTR *v10; // rdx
  DWORD i; // esi
  unsigned int v12; // eax
  LPCWSTR *v13; // rdx
  int Job; // r14d
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  HKEY v19; // rdx
  HKEY v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rdx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey[2]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v28; // [rsp+90h] [rbp-70h]
  _BYTE v29[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-20h] BYREF
  int v32; // [rsp+100h] [rbp+0h]
  int v33; // [rsp+154h] [rbp+54h]
  int v34; // [rsp+158h] [rbp+58h]
  WCHAR Name[256]; // [rsp+290h] [rbp+190h] BYREF

  hKey[1] = a2;
  hKey[0] = 0;
  cSubKeys = 0;
  cchName = 255;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Microsoft\\EnterpriseDesktopAppManagement");
  EnterCriticalSection(&JobHelper::m_critSec);
  std::wstring::append(lpSubKey, L"\\");
  std::wstring::append(lpSubKey, a2, 0, -1);
  std::wstring::append(lpSubKey, L"\\MSI\\");
  v6 = (const WCHAR *)lpSubKey;
  if ( v28 >= 8 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 == 2 )
    {
      if ( *((_QWORD *)a2 + 3) < 8u )
        v9 = a2;
      else
        v9 = *(HKEY *)a2;
      LogInfo(L"No jobs found for user %1.", v9);
      v8 = 0;
      goto LABEL_36;
    }
    goto LABEL_9;
  }
  v8 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v8 )
  {
LABEL_9:
    v10 = lpSubKey;
    if ( v28 >= 8 )
      v10 = (LPCWSTR *)lpSubKey[0];
    LogError(L"RegOpenKeyExW for %1 failed with Status = %2!d!", v10, (unsigned int)v8);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_36;
  }
  v8 = 0;
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 255;
    v12 = RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0);
    if ( v12 )
    {
      v13 = lpSubKey;
      if ( v28 >= 8 )
        v13 = (LPCWSTR *)lpSubKey[0];
      LogError(L"RegOpenKeyExW for %1 failed with Status = %2!d!", v13, v12);
    }
    else
    {
      _Job::_Job((_Job *)v30);
      std::wstring::wstring(v29, Name);
      Job = JobHelper::GetJob(v29, a2, v30);
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(v29, v15, 0);
      if ( Job >= 0 )
      {
        std::wstring::operator=(v31, a2);
        v32 = a3;
        v16 = (unsigned int)(v33 - 30);
        if ( (unsigned int)v16 > 0x28 || (v17 = 0x10040000001LL, !_bittest64(&v17, v16)) || !v34 )
          std::list<_Job>::push_back(a1, v30);
      }
      else
      {
        LogError(L"failed to get job for %1.  Error = 0x%2!x!", Name, (unsigned int)Job);
      }
      _Job::~_Job((_Job *)v30);
    }
  }
  v18 = *(_QWORD *)(a1 + 8);
  if ( v18 )
  {
    if ( *((_QWORD *)a2 + 3) < 8u )
      v20 = a2;
    else
      v20 = *(HKEY *)a2;
    LogInfo(L"Found %1!d! new jobs to process for user %2 with JobFilter = %3!d!.", v18, v20, 3);
  }
  else
  {
    if ( *((_QWORD *)a2 + 3) < 8u )
      v19 = a2;
    else
      v19 = *(HKEY *)a2;
    LogInfo(L"Found no new jobs to process for user %1 with JobFilter = %2!d!.", v19, 3);
  }
LABEL_36:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  LeaveCriticalSection(&JobHelper::m_critSec);
  LOBYTE(v21) = 1;
  std::wstring::_Tidy(lpSubKey, v21, 0);
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(a2, v22, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001984c  mov     [rsp-8+arg_18], rbx
0x140019851  push    rbp
0x140019852  push    rsi
0x140019853  push    rdi
0x140019854  push    r12
0x140019856  push    r13
0x140019858  push    r14
0x14001985a  push    r15
0x14001985c  lea     rbp, [rsp-3A0h]
0x140019864  sub     rsp, 4A0h
0x14001986b  mov     rax, cs:__security_cookie
0x140019872  xor     rax, rsp
0x140019875  mov     [rbp+3D0h+var_40], rax
0x14001987c  mov     r12d, r8d
0x14001987f  mov     rdi, rdx
0x140019882  mov     r15, rcx
0x140019885  mov     [rsp+4D0h+var_460], rdx
0x14001988a  xor     r13d, r13d
0x14001988d  mov     [rsp+4D0h+hKey], r13
0x140019892  mov     [rsp+4D0h+cSubKeys], r13d
0x140019897  mov     [rsp+4D0h+cchName], 0FFh
0x14001989f  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\EnterpriseDesktopA"...
0x1400198a6  lea     rcx, [rsp+4D0h+lpSubKey]
0x1400198ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1400198b0  nop
0x1400198b1  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x1400198b8  call    cs:__imp_EnterCriticalSection
0x1400198be  lea     rdx, asc_140020C3C; "\\"
0x1400198c5  lea     rcx, [rsp+4D0h+lpSubKey]
0x1400198ca  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400198cf  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400198d3  xor     r8d, r8d
0x1400198d6  mov     rdx, rdi
0x1400198d9  lea     rcx, [rsp+4D0h+lpSubKey]
0x1400198de  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1400198e3  lea     rdx, aMsi_0; "\\MSI\\"
0x1400198ea  lea     rcx, [rsp+4D0h+lpSubKey]
0x1400198ef  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1400198f4  lea     rdx, [rsp+4D0h+lpSubKey]
0x1400198f9  cmp     [rbp+3D0h+var_440], 8
0x1400198fe  cmovnb  rdx, [rsp+4D0h+lpSubKey]; lpSubKey
0x140019904  lea     rax, [rsp+4D0h+hKey]
0x140019909  mov     [rsp+4D0h+phkResult], rax; phkResult
0x14001990e  mov     r9d, 20019h; samDesired
0x140019914  xor     r8d, r8d; ulOptions
0x140019917  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001991e  call    cs:__imp_RegOpenKeyExW
0x140019924  mov     ebx, eax
0x140019926  test    eax, eax
0x140019928  jz      short loc_140019987
0x14001992a  cmp     eax, 2
0x14001992d  jnz     short loc_140019952
0x14001992f  cmp     qword ptr [rdi+18h], 8
0x140019934  jb      short loc_14001993B
0x140019936  mov     rdx, [rdi]
0x140019939  jmp     short loc_14001993E
0x14001993b  mov     rdx, rdi
0x14001993e  lea     rcx, aNoJobsFoundFor; "No jobs found for user %1."
0x140019945  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14001994a  mov     ebx, r13d
0x14001994d  jmp     loc_140019B39
0x140019952  lea     rdx, [rsp+4D0h+lpSubKey]
0x140019957  cmp     [rbp+3D0h+var_440], 8
0x14001995c  cmovnb  rdx, [rsp+4D0h+lpSubKey]
0x140019962  mov     r8d, ebx
0x140019965  lea     rcx, aRegopenkeyexwF_0; "RegOpenKeyExW for %1 failed with Status"...
0x14001996c  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019971  test    ebx, ebx
0x140019973  jle     loc_140019B39
0x140019979  movzx   ebx, bx
0x14001997c  or      ebx, 80070000h
0x140019982  jmp     loc_140019B39
0x140019987  mov     [rsp+4D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x14001998c  mov     [rsp+4D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x140019991  mov     [rsp+4D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x140019996  mov     [rsp+4D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x14001999b  mov     [rsp+4D0h+lpcValues], r13; lpcValues
0x1400199a0  mov     [rsp+4D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1400199a5  mov     [rsp+4D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1400199aa  lea     rax, [rsp+4D0h+cSubKeys]
0x1400199af  mov     [rsp+4D0h+phkResult], rax; lpcSubKeys
0x1400199b4  xor     r9d, r9d; lpReserved
0x1400199b7  xor     r8d, r8d; lpcchClass
0x1400199ba  xor     edx, edx; lpClass
0x1400199bc  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1400199c1  call    cs:__imp_RegQueryInfoKeyW
0x1400199c7  mov     ebx, eax
0x1400199c9  test    eax, eax
0x1400199cb  jnz     short loc_140019952
0x1400199cd  mov     ebx, r13d
0x1400199d0  mov     esi, r13d
0x1400199d3  cmp     [rsp+4D0h+cSubKeys], r13d
0x1400199d8  jbe     loc_140019AEC
0x1400199de  mov     [rsp+4D0h+cchName], 0FFh
0x1400199e6  mov     [rsp+4D0h+lpcValues], r13; lpftLastWriteTime
0x1400199eb  mov     [rsp+4D0h+lpcbMaxClassLen], r13; lpcchClass
0x1400199f0  mov     [rsp+4D0h+lpcbMaxSubKeyLen], r13; lpClass
0x1400199f5  mov     [rsp+4D0h+phkResult], r13; lpReserved
0x1400199fa  lea     r9, [rsp+4D0h+cchName]; lpcchName
0x1400199ff  lea     r8, [rbp+3D0h+Name]; lpName
0x140019a06  mov     edx, esi; dwIndex
0x140019a08  mov     rcx, [rsp+4D0h+hKey]; hKey
0x140019a0d  call    cs:__imp_RegEnumKeyExW
0x140019a13  test    eax, eax
0x140019a15  jz      short loc_140019A3B
0x140019a17  lea     rdx, [rsp+4D0h+lpSubKey]
0x140019a1c  cmp     [rbp+3D0h+var_440], 8
0x140019a21  cmovnb  rdx, [rsp+4D0h+lpSubKey]
0x140019a27  mov     r8d, eax
0x140019a2a  lea     rcx, aRegopenkeyexwF_0; "RegOpenKeyExW for %1 failed with Status"...
0x140019a31  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019a36  jmp     loc_140019AE0
0x140019a3b  lea     rcx, [rbp+3D0h+var_410]; this
0x140019a3f  call    ??0_Job@@QEAA@XZ; _Job::_Job(void)
0x140019a44  nop
0x140019a45  lea     rdx, [rbp+3D0h+Name]
0x140019a4c  lea     rcx, [rbp+3D0h+var_438]
0x140019a50  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140019a55  nop
0x140019a56  lea     r8, [rbp+3D0h+var_410]
0x140019a5a  mov     rdx, rdi
0x140019a5d  lea     rcx, [rbp+3D0h+var_438]
0x140019a61  call    ?GetJob@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@AEAU_Job@@@Z; JobHelper::GetJob(std::wstring const &,std::wstring &,_Job &)
0x140019a66  mov     r14d, eax
0x140019a69  xor     r8d, r8d
0x140019a6c  mov     dl, 1
0x140019a6e  lea     rcx, [rbp+3D0h+var_438]
0x140019a72  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019a77  mov     eax, r14d
0x140019a7a  shr     eax, 1Fh
0x140019a7d  test    al, al
0x140019a7f  jz      short loc_140019A99
0x140019a81  mov     r8d, r14d
0x140019a84  lea     rdx, [rbp+3D0h+Name]
0x140019a8b  lea     rcx, aFailedToGetJob; "failed to get job for %1.  Error = 0x%2"...
0x140019a92  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140019a97  jmp     short loc_140019AD7
0x140019a99  mov     rdx, rdi
0x140019a9c  lea     rcx, [rbp+3D0h+var_3F0]
0x140019aa0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x140019aa5  mov     [rbp+3D0h+var_3D0], r12d
0x140019aa9  mov     eax, [rbp+3D0h+var_37C]
0x140019aac  add     eax, 0FFFFFFE2h
0x140019aaf  cmp     eax, 28h ; '('
0x140019ab2  ja      short loc_140019ACA
0x140019ab4  mov     rcx, 10040000001h
0x140019abe  bt      rcx, rax
0x140019ac2  jnb     short loc_140019ACA
0x140019ac4  cmp     [rbp+3D0h+var_378], r13d
0x140019ac8  jnz     short loc_140019AD7
0x140019aca  lea     rdx, [rbp+3D0h+var_410]
0x140019ace  mov     rcx, r15
0x140019ad1  call    ?push_back@?$list@U_Job@@V?$allocator@U_Job@@@std@@@std@@QEAAXAEBU_Job@@@Z; std::list<_Job>::push_back(_Job const &)
0x140019ad6  nop
0x140019ad7  lea     rcx, [rbp+3D0h+var_410]; this
0x140019adb  call    ??1_Job@@QEAA@XZ; _Job::~_Job(void)
0x140019ae0  inc     esi
0x140019ae2  cmp     esi, [rsp+4D0h+cSubKeys]
0x140019ae6  jb      loc_1400199DE
0x140019aec  mov     rdx, [r15+8]
0x140019af0  test    rdx, rdx
0x140019af3  jnz     short loc_140019B18
0x140019af5  cmp     qword ptr [rdi+18h], 8
0x140019afa  jb      short loc_140019B01
0x140019afc  mov     rdx, [rdi]
0x140019aff  jmp     short loc_140019B04
0x140019b01  mov     rdx, rdi
0x140019b04  mov     r8d, 3
0x140019b0a  lea     rcx, aFoundNoNewJobs; "Found no new jobs to process for user %"...
0x140019b11  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140019b16  jmp     short loc_140019B39
0x140019b18  cmp     qword ptr [rdi+18h], 8
0x140019b1d  jb      short loc_140019B24
0x140019b1f  mov     r8, [rdi]
0x140019b22  jmp     short loc_140019B27
0x140019b24  mov     r8, rdi
0x140019b27  mov     r9d, 3
0x140019b2d  lea     rcx, aFound1DNewJobs; "Found %1!d! new jobs to process for use"...
0x140019b34  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140019b39  mov     rcx, [rsp+4D0h+hKey]; hKey
0x140019b3e  test    rcx, rcx
0x140019b41  jz      short loc_140019B49
0x140019b43  call    cs:__imp_RegCloseKey
0x140019b49  lea     rcx, ?m_critSec@JobHelper@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x140019b50  call    cs:__imp_LeaveCriticalSection
0x140019b56  nop
0x140019b57  xor     r8d, r8d
0x140019b5a  mov     dl, 1
0x140019b5c  lea     rcx, [rsp+4D0h+lpSubKey]
0x140019b61  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019b66  nop
0x140019b67  xor     r8d, r8d
0x140019b6a  mov     dl, 1
0x140019b6c  mov     rcx, rdi
0x140019b6f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019b74  mov     eax, ebx
0x140019b76  mov     rcx, [rbp+3D0h+var_40]
0x140019b7d  xor     rcx, rsp; StackCookie
0x140019b80  call    __security_check_cookie
0x140019b85  mov     rbx, [rsp+4D0h+arg_18]
0x140019b8d  add     rsp, 4A0h
0x140019b94  pop     r15
0x140019b96  pop     r14
0x140019b98  pop     r13
0x140019b9a  pop     r12
0x140019b9c  pop     rdi
0x140019b9d  pop     rsi
0x140019b9e  pop     rbp
0x140019b9f  retn
```
