# CKernelReport::CheckForFullLiveReports(void)

- ea: `0x1400359ac`
- end: `0x140035d17`
- name: `?CheckForFullLiveReports@CKernelReport@@AEAAJXZ`
- size: `875`
- prototype: `__int64 __fastcall(CKernelReport *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140039230`

## callees

- `0x140002470`
- `0x140005468`
- `0x140034d9c`
- `0x1400359ac`
- `0x1400361e8`
- `0x14003902c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140035ab3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140035bcf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140035ab3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140035bcf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140035b3b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140035c58`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140035b3b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140035c58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035cbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035cd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035ce8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035cbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035cd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140035ce8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035a2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035a6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035b6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035a2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035a6d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140035b6f`

## string_xrefs

- `0x140035b82`: `Failed to open the sub key %ws while reporting for all kernel reports`

## pseudocode

```c
__int64 __fastcall CKernelReport::CheckForFullLiveReports(CKernelReport *this)
{
  HKEY *v2; // rax
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  bool v5; // cc
  HKEY *v6; // rax
  LSTATUS v7; // eax
  DWORD v8; // edi
  HKEY *v9; // rax
  LSTATUS v10; // eax
  __int64 v11; // rdx
  DWORD v12; // ebx
  LSTATUS v13; // eax
  wil::details *phkResult; // [rsp+20h] [rbp-E0h]
  wil::details *phkResulta; // [rsp+20h] [rbp-E0h]
  wil::details *phkResultb; // [rsp+20h] [rbp-E0h]
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  const char *lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v22; // [rsp+68h] [rbp-98h] BYREF
  HKEY v23; // [rsp+70h] [rbp-90h] BYREF
  HKEY v24; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[256]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v27[256]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v23 = 0;
  hKey = 0;
  cSubKeys = 0;
  v22 = 0;
  cchName = 0;
  v27[0] = 0;
  Name[0] = 0;
  v2 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, g_wszLiveKernelReportsQueueRoot, 0, 0xF003Fu, v2);
  v4 = v3;
  v5 = v3 <= 0;
  if ( !v3 )
  {
    v6 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v23);
    v3 = RegOpenKeyExW(hKey, L"FullLiveKernelReports", 0, 0xF003Fu, v6);
    v4 = v3;
    v5 = v3 <= 0;
    if ( !v3 )
    {
      v7 = RegQueryInfoKeyW(v23, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      v4 = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        LODWORD(phkResult) = v4;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x9FF,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::CheckForFullLiveReports",
          phkResult,
          (int)"Failed to enumerate the report types",
          lpcbMaxClassLen);
        goto LABEL_25;
      }
      v8 = cSubKeys;
      while ( 1 )
      {
        do
        {
          if ( !v8 )
          {
            v4 = 0;
            goto LABEL_25;
          }
          cchName = 256;
          Name[0] = 0;
          --v8;
        }
        while ( RegEnumKeyExW(v23, v8, Name, &cchName, 0, 0, 0, 0) );
        v24 = 0;
        v9 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
        v10 = RegOpenKeyExW(v23, Name, 0, 0xF003Fu, v9);
        if ( v10 )
        {
          lpcbMaxSubKeyLen = "Failed to open the sub key %ws while reporting for all kernel reports";
          v11 = 2603;
        }
        else
        {
          v10 = RegQueryInfoKeyW(v24, 0, 0, 0, &v22, 0, 0, 0, 0, 0, 0, 0);
          if ( !v10 )
          {
            v12 = v22;
            while ( v12 )
            {
              cchName = 256;
              v27[0] = 0;
              v13 = RegEnumKeyExW(v24, --v12, v27, &cchName, 0, 0, 0, 0);
              if ( v13 )
              {
                LODWORD(phkResultb) = v13;
                wil::details::in1diag4::Log_Win32Msg(
                  retaddr,
                  (void *)0xA55,
                  (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
                  "CKernelReport::CheckForFullLiveReports",
                  phkResultb,
                  (unsigned int)"Failed to enum the keys for full live kernel event %ws",
                  (const char *)Name);
              }
              else
              {
                CKernelReport::ConvertLiveDumpAndReport(this, Name, v27);
              }
            }
            goto LABEL_21;
          }
          lpcbMaxSubKeyLen = "Failed to query the report id count for %ws.";
          v11 = 2625;
        }
        LODWORD(phkResulta) = v10;
        wil::details::in1diag4::Log_Win32Msg(
          retaddr,
          (void *)v11,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kernelreport.cpp",
          "CKernelReport::CheckForFullLiveReports",
          phkResulta,
          (unsigned int)lpcbMaxSubKeyLen,
          (const char *)Name);
LABEL_21:
        if ( v24 )
          RegCloseKey(v24);
      }
    }
  }
  if ( !v5 )
    v4 = (unsigned __int16)v3 | 0x80070000;
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v23 )
    RegCloseKey(v23);
  return v4;
}

```

## disassembly

```asm
0x1400359ac  mov     [rsp-8+arg_8], rbx
0x1400359b1  mov     [rsp-8+arg_10], rsi
0x1400359b6  push    rbp
0x1400359b7  push    rdi
0x1400359b8  push    r14
0x1400359ba  lea     rbp, [rsp-3A0h]
0x1400359c2  sub     rsp, 4A0h
0x1400359c9  mov     rax, cs:__security_cookie
0x1400359d0  xor     rax, rsp
0x1400359d3  mov     [rbp+3B0h+var_20], rax
0x1400359da  mov     rsi, rcx
0x1400359dd  xor     r14d, r14d
0x1400359e0  mov     [rsp+4B0h+var_440], r14
0x1400359e5  mov     [rbp+3B0h+hKey], r14
0x1400359e9  mov     [rsp+4B0h+cSubKeys], r14d
0x1400359ee  mov     [rsp+4B0h+var_448], r14d
0x1400359f3  mov     [rsp+4B0h+cchName], r14d
0x1400359f8  mov     [rbp+3B0h+var_220], r14w
0x140035a00  mov     [rbp+3B0h+Name], r14w
0x140035a05  lea     rcx, [rbp+3B0h+hKey]
0x140035a09  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140035a0e  mov     [rsp+4B0h+phkResult], rax; phkResult
0x140035a13  mov     r9d, 0F003Fh; samDesired
0x140035a19  xor     r8d, r8d; ulOptions
0x140035a1c  lea     rdx, ?g_wszLiveKernelReportsQueueRoot@@3PA_WA; "System\\CurrentControlSet\\Control\\Cra"...
0x140035a23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140035a2a  call    cs:__imp_RegOpenKeyExW
0x140035a30  mov     ebx, eax
0x140035a32  test    eax, eax
0x140035a34  jz      short loc_140035A4A
0x140035a36  jle     loc_140035CCE
0x140035a3c  movzx   ebx, ax
0x140035a3f  or      ebx, 80070000h
0x140035a45  jmp     loc_140035CCE
0x140035a4a  lea     rcx, [rsp+4B0h+var_440]
0x140035a4f  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140035a54  mov     [rsp+4B0h+phkResult], rax; phkResult
0x140035a59  mov     r9d, 0F003Fh; samDesired
0x140035a5f  xor     r8d, r8d; ulOptions
0x140035a62  lea     rdx, aFulllivekernel; "FullLiveKernelReports"
0x140035a69  mov     rcx, [rbp+3B0h+hKey]; hKey
0x140035a6d  call    cs:__imp_RegOpenKeyExW
0x140035a73  mov     ebx, eax
0x140035a75  test    eax, eax
0x140035a77  jnz     short loc_140035A36
0x140035a79  mov     [rsp+4B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x140035a7e  mov     [rsp+4B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140035a83  mov     [rsp+4B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140035a88  mov     [rsp+4B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140035a8d  mov     [rsp+4B0h+lpcValues], r14; lpcValues
0x140035a92  mov     [rsp+4B0h+lpcbMaxClassLen], r14; char *
0x140035a97  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x140035a9c  lea     rax, [rsp+4B0h+cSubKeys]
0x140035aa1  mov     [rsp+4B0h+phkResult], rax; lpcSubKeys
0x140035aa6  xor     r9d, r9d; lpReserved
0x140035aa9  xor     r8d, r8d; lpcchClass
0x140035aac  xor     edx, edx; lpClass
0x140035aae  mov     rcx, [rsp+4B0h+var_440]; hKey
0x140035ab3  call    cs:__imp_RegQueryInfoKeyW
0x140035ab9  mov     ebx, eax
0x140035abb  test    eax, eax
0x140035abd  jz      short loc_140035AFE
0x140035abf  jle     short loc_140035ACA
0x140035ac1  movzx   ebx, ax
0x140035ac4  or      ebx, 80070000h
0x140035aca  mov     rcx, [rbp+3B8h]; this
0x140035ad1  lea     rax, aFailedToEnumer; "Failed to enumerate the report types"
0x140035ad8  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rax; int
0x140035add  mov     dword ptr [rsp+4B0h+phkResult], ebx; wil::details *
0x140035ae1  lea     r9, aCkernelreportC_3; "CKernelReport::CheckForFullLiveReports"
0x140035ae8  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140035aef  mov     edx, 9FFh; void *
0x140035af4  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140035af9  jmp     loc_140035CCE
0x140035afe  mov     edi, [rsp+4B0h+cSubKeys]
0x140035b02  jmp     loc_140035CC3
0x140035b07  mov     [rsp+4B0h+cchName], 100h
0x140035b0f  mov     [rbp+3B0h+Name], r14w
0x140035b14  lea     edx, [rdi-1]; dwIndex
0x140035b17  mov     edi, edx
0x140035b19  mov     [rsp+4B0h+lpcValues], r14; lpftLastWriteTime
0x140035b1e  mov     [rsp+4B0h+lpcbMaxClassLen], r14; lpcchClass
0x140035b23  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpClass
0x140035b28  mov     [rsp+4B0h+phkResult], r14; lpReserved
0x140035b2d  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x140035b32  lea     r8, [rbp+3B0h+Name]; lpName
0x140035b36  mov     rcx, [rsp+4B0h+var_440]; hKey
0x140035b3b  call    cs:__imp_RegEnumKeyExW
0x140035b41  test    eax, eax
0x140035b43  jnz     loc_140035CC3
0x140035b49  mov     [rsp+4B0h+var_438], r14
0x140035b4e  lea     rcx, [rsp+4B0h+var_438]
0x140035b53  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140035b58  mov     [rsp+4B0h+phkResult], rax; phkResult
0x140035b5d  mov     r9d, 0F003Fh; samDesired
0x140035b63  xor     r8d, r8d; ulOptions
0x140035b66  lea     rdx, [rbp+3B0h+Name]; lpSubKey
0x140035b6a  mov     rcx, [rsp+4B0h+var_440]; hKey
0x140035b6f  call    cs:__imp_RegOpenKeyExW
0x140035b75  test    eax, eax
0x140035b77  jz      short loc_140035B95
0x140035b79  lea     rdx, [rbp+3B0h+Name]
0x140035b7d  mov     [rsp+4B0h+lpcbMaxClassLen], rdx
0x140035b82  lea     rdx, aFailedToOpenTh; "Failed to open the sub key %ws while re"...
0x140035b89  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rdx
0x140035b8e  mov     edx, 0A2Bh
0x140035b93  jmp     short loc_140035BF3
0x140035b95  mov     [rsp+4B0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x140035b9a  mov     [rsp+4B0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140035b9f  mov     [rsp+4B0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140035ba4  mov     [rsp+4B0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140035ba9  mov     [rsp+4B0h+lpcValues], r14; lpcValues
0x140035bae  mov     [rsp+4B0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140035bb3  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x140035bb8  lea     rax, [rsp+4B0h+var_448]
0x140035bbd  mov     [rsp+4B0h+phkResult], rax; lpcSubKeys
0x140035bc2  xor     r9d, r9d; lpReserved
0x140035bc5  xor     r8d, r8d; lpcchClass
0x140035bc8  xor     edx, edx; lpClass
0x140035bca  mov     rcx, [rsp+4B0h+var_438]; hKey
0x140035bcf  call    cs:__imp_RegQueryInfoKeyW
0x140035bd5  test    eax, eax
0x140035bd7  jz      short loc_140035C16
0x140035bd9  lea     rdx, [rbp+3B0h+Name]
0x140035bdd  mov     [rsp+4B0h+lpcbMaxClassLen], rdx; char *
0x140035be2  lea     rdx, aFailedToQueryT; "Failed to query the report id count for"...
0x140035be9  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x140035bee  mov     edx, 0A41h; void *
0x140035bf3  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140035bfa  lea     r9, aCkernelreportC_3; "CKernelReport::CheckForFullLiveReports"
0x140035c01  mov     dword ptr [rsp+4B0h+phkResult], eax; wil::details *
0x140035c05  mov     rcx, [rbp+3B8h]; this
0x140035c0c  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140035c11  jmp     loc_140035CB3
0x140035c16  mov     ebx, [rsp+4B0h+var_448]
0x140035c1a  jmp     loc_140035CAB
0x140035c1f  mov     [rsp+4B0h+cchName], 100h
0x140035c27  mov     [rbp+3B0h+var_220], r14w
0x140035c2f  dec     ebx
0x140035c31  mov     [rsp+4B0h+lpcValues], r14; lpftLastWriteTime
0x140035c36  mov     [rsp+4B0h+lpcbMaxClassLen], r14; lpcchClass
0x140035c3b  mov     [rsp+4B0h+lpcbMaxSubKeyLen], r14; lpClass
0x140035c40  mov     [rsp+4B0h+phkResult], r14; lpReserved
0x140035c45  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x140035c4a  lea     r8, [rbp+3B0h+var_220]; lpName
0x140035c51  mov     edx, ebx; dwIndex
0x140035c53  mov     rcx, [rsp+4B0h+var_438]; hKey
0x140035c58  call    cs:__imp_RegEnumKeyExW
0x140035c5e  lea     rdx, [rbp+3B0h+Name]; wchar_t *
0x140035c62  test    eax, eax
0x140035c64  jz      short loc_140035C9C
0x140035c66  mov     rcx, [rbp+3B8h]; this
0x140035c6d  mov     [rsp+4B0h+lpcbMaxClassLen], rdx; char *
0x140035c72  lea     rdx, aFailedToEnumTh_0; "Failed to enum the keys for full live k"...
0x140035c79  mov     [rsp+4B0h+lpcbMaxSubKeyLen], rdx; unsigned int
0x140035c7e  mov     dword ptr [rsp+4B0h+phkResult], eax; wil::details *
0x140035c82  lea     r9, aCkernelreportC_3; "CKernelReport::CheckForFullLiveReports"
0x140035c89  lea     r8, aOnecoreWindows_4; "onecore\\windows\\feedback\\core\\werfa"...
0x140035c90  mov     edx, 0A55h; void *
0x140035c95  call    ?Log_Win32Msg@in1diag4@details@wil@@YAKPEAXIPEBD1K1ZZ; wil::details::in1diag4::Log_Win32Msg(void *,uint,char const *,char const *,ulong,char const *,...)
0x140035c9a  jmp     short loc_140035CAB
0x140035c9c  lea     r8, [rbp+3B0h+var_220]; wchar_t *
0x140035ca3  mov     rcx, rsi; this
0x140035ca6  call    ?ConvertLiveDumpAndReport@CKernelReport@@QEAAJPEB_W0@Z; CKernelReport::ConvertLiveDumpAndReport(wchar_t const *,wchar_t const *)
0x140035cab  test    ebx, ebx
0x140035cad  jnz     loc_140035C1F
0x140035cb3  mov     rcx, [rsp+4B0h+var_438]; hKey
0x140035cb8  test    rcx, rcx
0x140035cbb  jz      short loc_140035CC3
0x140035cbd  call    cs:__imp_RegCloseKey
0x140035cc3  test    edi, edi
0x140035cc5  jnz     loc_140035B07
0x140035ccb  mov     ebx, r14d
0x140035cce  mov     rcx, [rbp+3B0h+hKey]; hKey
0x140035cd2  test    rcx, rcx
0x140035cd5  jz      short loc_140035CDE
0x140035cd7  call    cs:__imp_RegCloseKey
0x140035cdd  nop
0x140035cde  mov     rcx, [rsp+4B0h+var_440]; hKey
0x140035ce3  test    rcx, rcx
0x140035ce6  jz      short loc_140035CEE
0x140035ce8  call    cs:__imp_RegCloseKey
0x140035cee  mov     eax, ebx
0x140035cf0  mov     rcx, [rbp+3B0h+var_20]
0x140035cf7  xor     rcx, rsp; StackCookie
0x140035cfa  call    __security_check_cookie
0x140035cff  lea     r11, [rsp+4B0h+var_10]
0x140035d07  mov     rbx, [r11+28h]
0x140035d0b  mov     rsi, [r11+30h]
0x140035d0f  mov     rsp, r11
0x140035d12  pop     r14
0x140035d14  pop     rdi
0x140035d15  pop     rbp
0x140035d16  retn
```
