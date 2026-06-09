# DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult(ushort * *)

- ea: `0x180089f80`
- end: `0x18008a4bc`
- name: `?DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult@@YA_KPEAPEAG@Z`
- size: `1340`
- prototype: `unsigned __int64 __fastcall(unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008a878`
- `0x18008b4f0`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18003c26c`
- `0x18007a9cf`
- `0x180089c5c`
- `0x180089e1c`
- `0x180089f80`
- `0x18008ba9c`
- `0x18008c120`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18008a180`
- `msvcrt!_wcsnicmp` at `0x18008a19f`
- `msvcrt!_wcsnicmp` at `0x18008a180`
- `msvcrt!_wcsnicmp` at `0x18008a19f`
- `msvcrt!wcsstr` at `0x18008a1bc`
- `msvcrt!wcsstr` at `0x18008a1bc`
- `msvcrt!_wcsicmp` at `0x18008a161`
- `msvcrt!_wcsicmp` at `0x18008a161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a2ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a2ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008a0da`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008a0da`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008a05e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008a05e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008a2e5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18008a2e5`

## string_xrefs

- `0x18008a1cb`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18008a29b`: `%%windir%%\appcompat\pca\ProcessLoadedDllList.%ws.txt`
- `0x18008a23f`: `ProcessLoadedDllDetectorLastRun`
- `0x18008a064`: `DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult`
- `0x18008a3ca`: `DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult`
- `0x18008a40a`: `DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult`
- `0x18008a203`: `StringCchPrintfW failed to build user AppCompatFlags key path [%d]`
- `0x18008a2b8`: `StringCchPrintfW failed to build user file path for user %ws`
- `0x18008a25f`: `PcaDumpRunningProcessesLoadedDllDetect task did not run for this user.`
- `0x18008a362`: `Found process DLL data file for user %ws, merging into consolidated list.`
- `0x18008a3bd`: `Exception occurred while merging user DLL list. Exception code: 0x%x`
- `0x18008a395`: `Failed to add DLL to consolidated list due to memory allocation failure`
- `0x18008a451`: `Failed to read DLL data file for user %ws or file does not exist.`
- `0x18008a442`: `User %ws file exists but contains no DLL data.`
- `0x18008a480`: `No DLL data found from any user.`
- `0x18008a135`: `Consolidated DLL data from %d users into final result.`

## pseudocode

```c
unsigned __int64 __fastcall DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult(unsigned __int16 **a1)
{
  unsigned __int64 v2; // r15
  struct _DLL_LIST_ENTRY *v3; // rsi
  LSTATUS v4; // eax
  DWORD v5; // r13d
  LSTATUS v6; // eax
  unsigned __int16 *v7; // rax
  int v8; // eax
  unsigned __int64 RegistryQWORD; // rax
  const char *v10; // r9
  int v11; // r8d
  int v12; // ecx
  int ExistingDllList; // eax
  const unsigned __int16 **v14; // r15
  LPDWORD lpcSubKeys; // [rsp+20h] [rbp-908h]
  LPDWORD lpcSubKeysa; // [rsp+20h] [rbp-908h]
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-900h]
  DWORD cSubKeys; // [rsp+60h] [rbp-8C8h] BYREF
  int v20; // [rsp+64h] [rbp-8C4h]
  DWORD cchName; // [rsp+68h] [rbp-8C0h] BYREF
  DWORD i; // [rsp+6Ch] [rbp-8BCh]
  PVOID P; // [rsp+70h] [rbp-8B8h] BYREF
  PVOID v24; // [rsp+78h] [rbp-8B0h] BYREF
  unsigned __int64 v25; // [rsp+80h] [rbp-8A8h]
  unsigned __int16 **v26; // [rsp+88h] [rbp-8A0h]
  unsigned __int64 v27; // [rsp+90h] [rbp-898h]
  unsigned __int16 **v28; // [rsp+98h] [rbp-890h]
  WCHAR Name[264]; // [rsp+A0h] [rbp-888h] BYREF
  unsigned __int16 v30[264]; // [rsp+2B0h] [rbp-678h] BYREF
  WCHAR Src[264]; // [rsp+4C0h] [rbp-468h] BYREF
  WCHAR Dst[264]; // [rsp+6D0h] [rbp-258h] BYREF

  v26 = a1;
  v28 = a1;
  memset_0(Name, 0, 0x208u);
  memset_0(v30, 0, 0x208u);
  memset_0(Src, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  cchName = 260;
  cSubKeys = 0;
  v2 = 0;
  v3 = 0;
  P = 0;
  v20 = 0;
  *a1 = 0;
  v4 = RegQueryInfoKeyW(HKEY_USERS, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    LODWORD(lpcSubKeys) = v4;
    AslLogCallPrintf(
      1,
      (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
      1866,
      (unsigned int)"RegQueryInfoKey failed to get subkey number of HKU [%d]",
      lpcSubKeys);
    cSubKeys = 20;
  }
  v5 = 0;
  for ( i = 0; v5 < cSubKeys; i = v5 )
  {
    cchName = 260;
    v6 = RegEnumKeyExW(HKEY_USERS, v5, Name, &cchName, 0, 0, 0, 0);
    if ( v6 == 259 )
      break;
    if ( v6 )
    {
      LODWORD(lpcSubKeys) = v6;
      AslLogCallPrintf(
        1,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
        1888,
        (unsigned int)"Error enumerating user key [%d]",
        lpcSubKeys);
      break;
    }
    if ( (!_wcsicmp(Name, L"S-1-5-18") || !_wcsnicmp(Name, L"S-1-5-21-", 9u) || !_wcsnicmp(Name, L"S-1-12-1-", 9u))
      && !wcsstr(Name, L"_Classes") )
    {
      v8 = StringCchPrintfW(
             v30,
             0x104u,
             L"%s\\%s",
             Name,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
      if ( v8 < 0 )
      {
        LODWORD(lpcSubKeysa) = v8;
        AslLogCallPrintf(
          1,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
          1916,
          (unsigned int)"StringCchPrintfW failed to build user AppCompatFlags key path [%d]",
          lpcSubKeysa);
        goto LABEL_35;
      }
      AslLogCallPrintf(
        3,
        (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
        1920,
        (unsigned int)"Looking at HKU\\%ws",
        v30);
      RegistryQWORD = PcaUtilityGetRegistryQWORD(HKEY_USERS, v30, L"ProcessLoadedDllDetectorLastRun", 0);
      if ( !RegistryQWORD )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
          1928,
          (unsigned int)"PcaDumpRunningProcessesLoadedDllDetect task did not run for this user.");
        goto LABEL_35;
      }
      if ( RegistryQWORD > v2 )
        v2 = RegistryQWORD;
      v25 = v2;
      v27 = v2;
      if ( StringCchPrintfW(Src, 0x104u, L"%%windir%%\\appcompat\\pca\\ProcessLoadedDllList.%ws.txt", Name) < 0 )
      {
        v10 = "StringCchPrintfW failed to build user file path for user %ws";
        v11 = 1943;
        v12 = 1;
LABEL_34:
        AslLogCallPrintf(
          v12,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
          v11,
          (_DWORD)v10,
          Name);
        goto LABEL_35;
      }
      if ( !ExpandEnvironmentStringsW(Src, Dst, 0x104u) )
      {
        LODWORD(lpcbMaxSubKeyLen) = GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
          1950,
          (unsigned int)"ExpandEnvironmentStringsW failed for user %ws [%d]",
          Name,
          lpcbMaxSubKeyLen);
        goto LABEL_35;
      }
      v24 = 0;
      ExistingDllList = ReadExistingDllList(Dst, (struct _DLL_LIST_ENTRY **)&v24);
      v12 = 3;
      if ( !ExistingDllList )
      {
        v10 = "Failed to read DLL data file for user %ws or file does not exist.";
        v11 = 1998;
        goto LABEL_34;
      }
      if ( v24 )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
          1960,
          (unsigned int)"Found process DLL data file for user %ws, merging into consolidated list.",
          Name);
        v14 = (const unsigned __int16 **)v24;
        while ( v14 )
        {
          if ( !(unsigned int)AddDllToList((struct _DLL_LIST_ENTRY **)&P, v14[1], v14[2]) )
            AslLogCallPrintf(
              1,
              (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
              1971,
              (unsigned int)"Failed to add DLL to consolidated list due to memory allocation failure");
          v14 = (const unsigned __int16 **)*v14;
          v3 = (struct _DLL_LIST_ENTRY *)P;
        }
        ++v20;
        FreeDllList(v24);
        v2 = v25;
      }
      else
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
          1993,
          (unsigned int)"User %ws file exists but contains no DLL data.",
          Name);
      }
    }
LABEL_35:
    ++v5;
  }
  if ( v3 )
  {
    v7 = ConvertDllListToString(v3);
    *v26 = v7;
    FreeDllList(v3);
    LODWORD(lpcSubKeys) = v20;
    AslLogCallPrintf(
      3,
      (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
      2008,
      (unsigned int)"Consolidated DLL data from %d users into final result.",
      lpcSubKeys);
  }
  else
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"DumpRunningProcessesLoadedDllDetector_CheckUserTaskResult",
      2012,
      (unsigned int)"No DLL data found from any user.");
  }
  return v2;
}

```

## disassembly

```asm
0x180089f80  push    rbx
0x180089f82  push    rsi
0x180089f83  push    rdi
0x180089f84  push    r12
0x180089f86  push    r13
0x180089f88  push    r15
0x180089f8a  sub     rsp, 8F8h
0x180089f91  mov     rax, cs:__security_cookie
0x180089f98  xor     rax, rsp
0x180089f9b  mov     [rsp+928h+var_48], rax
0x180089fa3  mov     rdi, rcx
0x180089fa6  mov     [rsp+928h+var_8A0], rcx
0x180089fae  mov     [rsp+928h+var_890], rcx
0x180089fb6  mov     ebx, 208h
0x180089fbb  mov     r8d, ebx; Size
0x180089fbe  xor     edx, edx; Val
0x180089fc0  lea     rcx, [rsp+928h+Name]; void *
0x180089fc8  call    memset_0
0x180089fcd  mov     r8d, ebx; Size
0x180089fd0  xor     edx, edx; Val
0x180089fd2  lea     rcx, [rsp+928h+var_678]; void *
0x180089fda  call    memset_0
0x180089fdf  mov     r8d, ebx; Size
0x180089fe2  xor     edx, edx; Val
0x180089fe4  lea     rcx, [rsp+928h+Src]; void *
0x180089fec  call    memset_0
0x180089ff1  mov     r8d, ebx; Size
0x180089ff4  xor     edx, edx; Val
0x180089ff6  lea     rcx, [rsp+928h+Dst]; void *
0x180089ffe  call    memset_0
0x18008a003  mov     [rsp+928h+cchName], 104h
0x18008a00b  xor     ebx, ebx
0x18008a00d  mov     [rsp+928h+cSubKeys], ebx
0x18008a011  mov     r15d, ebx
0x18008a014  mov     esi, ebx
0x18008a016  mov     [rsp+928h+P], rbx
0x18008a01b  mov     [rsp+928h+var_8C4], ebx
0x18008a01f  mov     [rdi], rbx
0x18008a022  mov     [rsp+928h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x18008a027  mov     [rsp+928h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18008a02c  mov     [rsp+928h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x18008a031  mov     [rsp+928h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18008a036  mov     [rsp+928h+lpcValues], rbx; lpcValues
0x18008a03b  mov     [rsp+928h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x18008a040  mov     [rsp+928h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x18008a045  lea     rax, [rsp+928h+cSubKeys]
0x18008a04a  mov     [rsp+928h+lpcSubKeys], rax; lpcSubKeys
0x18008a04f  xor     r9d, r9d; lpReserved
0x18008a052  xor     r8d, r8d; lpcchClass
0x18008a055  xor     edx, edx; lpClass
0x18008a057  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18008a05e  call    cs:__imp_RegQueryInfoKeyW
0x18008a064  lea     rdi, aDumprunningpro_1; "DumpRunningProcessesLoadedDllDetector_C"...
0x18008a06b  test    eax, eax
0x18008a06d  jz      short loc_18008A093
0x18008a06f  mov     dword ptr [rsp+928h+lpcSubKeys], eax
0x18008a073  lea     r9, aRegqueryinfoke; "RegQueryInfoKey failed to get subkey nu"...
0x18008a07a  mov     r8d, 74Ah
0x18008a080  mov     rdx, rdi
0x18008a083  lea     ecx, [rbx+1]
0x18008a086  call    AslLogCallPrintf
0x18008a08b  mov     [rsp+928h+cSubKeys], 14h
0x18008a093  mov     r13d, ebx
0x18008a096  mov     [rsp+928h+var_8BC], ebx
0x18008a09a  mov     r12d, 3
0x18008a0a0  cmp     r13d, [rsp+928h+cSubKeys]
0x18008a0a5  jnb     short loc_18008A109
0x18008a0a7  mov     [rsp+928h+cchName], 104h
0x18008a0af  mov     [rsp+928h+lpcValues], rbx; lpftLastWriteTime
0x18008a0b4  mov     [rsp+928h+lpcbMaxClassLen], rbx; lpcchClass
0x18008a0b9  mov     [rsp+928h+lpcbMaxSubKeyLen], rbx; lpClass
0x18008a0be  mov     [rsp+928h+lpcSubKeys], rbx; lpReserved
0x18008a0c3  lea     r9, [rsp+928h+cchName]; lpcchName
0x18008a0c8  lea     r8, [rsp+928h+Name]; lpName
0x18008a0d0  mov     edx, r13d; dwIndex
0x18008a0d3  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18008a0da  call    cs:__imp_RegEnumKeyExW
0x18008a0e0  cmp     eax, 103h
0x18008a0e5  jz      short loc_18008A109
0x18008a0e7  test    eax, eax
0x18008a0e9  jz      short loc_18008A152
0x18008a0eb  mov     dword ptr [rsp+928h+lpcSubKeys], eax
0x18008a0ef  lea     r9, aErrorEnumerati; "Error enumerating user key [%d]"
0x18008a0f6  mov     r8d, 760h
0x18008a0fc  mov     rdx, rdi
0x18008a0ff  mov     ecx, 1
0x18008a104  call    AslLogCallPrintf
0x18008a109  test    rsi, rsi
0x18008a10c  jz      loc_18008A480
0x18008a112  mov     rcx, rsi; struct _DLL_LIST_ENTRY *
0x18008a115  call    ?ConvertDllListToString@@YAPEAGPEAU_DLL_LIST_ENTRY@@@Z; ConvertDllListToString(_DLL_LIST_ENTRY *)
0x18008a11a  mov     rcx, [rsp+928h+var_8A0]
0x18008a122  mov     [rcx], rax
0x18008a125  mov     rcx, rsi; P
0x18008a128  call    ?FreeDllList@@YAXPEAU_DLL_LIST_ENTRY@@@Z; FreeDllList(_DLL_LIST_ENTRY *)
0x18008a12d  mov     eax, [rsp+928h+var_8C4]
0x18008a131  mov     dword ptr [rsp+928h+lpcSubKeys], eax
0x18008a135  lea     r9, aConsolidatedDl; "Consolidated DLL data from %d users int"...
0x18008a13c  mov     r8d, 7D8h
0x18008a142  mov     rdx, rdi
0x18008a145  mov     ecx, r12d
0x18008a148  call    AslLogCallPrintf
0x18008a14d  jmp     loc_18008A498
0x18008a152  lea     rdx, aS1518_0; "S-1-5-18"
0x18008a159  lea     rcx, [rsp+928h+Name]; String1
0x18008a161  call    cs:__imp__wcsicmp
0x18008a167  test    eax, eax
0x18008a169  jz      short loc_18008A1AD
0x18008a16b  mov     r8d, 9; MaxCount
0x18008a171  lea     rdx, aS1521; "S-1-5-21-"
0x18008a178  lea     rcx, [rsp+928h+Name]; String1
0x18008a180  call    cs:__imp__wcsnicmp
0x18008a186  test    eax, eax
0x18008a188  jz      short loc_18008A1AD
0x18008a18a  mov     r8d, 9; MaxCount
0x18008a190  lea     rdx, aS1121; "S-1-12-1-"
0x18008a197  lea     rcx, [rsp+928h+Name]; String1
0x18008a19f  call    cs:__imp__wcsnicmp
0x18008a1a5  test    eax, eax
0x18008a1a7  jnz     loc_18008A473
0x18008a1ad  lea     rdx, aClasses; "_Classes"
0x18008a1b4  lea     rcx, [rsp+928h+Name]; Str
0x18008a1bc  call    cs:__imp_wcsstr
0x18008a1c2  test    rax, rax
0x18008a1c5  jnz     loc_18008A473
0x18008a1cb  lea     rax, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18008a1d2  mov     [rsp+928h+lpcSubKeys], rax
0x18008a1d7  lea     r9, [rsp+928h+Name]
0x18008a1df  lea     r8, aSS_0; "%s\\%s"
0x18008a1e6  mov     edx, 104h; unsigned __int64
0x18008a1eb  lea     rcx, [rsp+928h+var_678]; unsigned __int16 *
0x18008a1f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008a1f8  mov     rdx, rdi
0x18008a1fb  test    eax, eax
0x18008a1fd  jns     short loc_18008A21A
0x18008a1ff  mov     dword ptr [rsp+928h+lpcSubKeys], eax
0x18008a203  lea     r9, aStringcchprint_1; "StringCchPrintfW failed to build user A"...
0x18008a20a  mov     r8d, 77Ch
0x18008a210  mov     ecx, 1
0x18008a215  jmp     loc_18008A46E
0x18008a21a  lea     rax, [rsp+928h+var_678]
0x18008a222  mov     [rsp+928h+lpcSubKeys], rax
0x18008a227  lea     r9, aLookingAtHkuWs; "Looking at HKU\\%ws"
0x18008a22e  mov     r8d, 780h
0x18008a234  mov     ecx, r12d
0x18008a237  call    AslLogCallPrintf
0x18008a23c  xor     r9d, r9d; unsigned __int64
0x18008a23f  lea     r8, aProcessloadedd_1; "ProcessLoadedDllDetectorLastRun"
0x18008a246  lea     rdx, [rsp+928h+var_678]; unsigned __int16 *
0x18008a24e  mov     rcx, 0FFFFFFFF80000003h; HKEY
0x18008a255  call    ?PcaUtilityGetRegistryQWORD@@YA_KPEAUHKEY__@@PEBG1_K@Z; PcaUtilityGetRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)
0x18008a25a  test    rax, rax
0x18008a25d  jnz     short loc_18008A27C
0x18008a25f  lea     r9, aPcadumprunning_0; "PcaDumpRunningProcessesLoadedDllDetect "...
0x18008a266  mov     r8d, 788h
0x18008a26c  mov     rdx, rdi
0x18008a26f  mov     ecx, r12d
0x18008a272  call    AslLogCallPrintf
0x18008a277  jmp     loc_18008A473
0x18008a27c  cmp     rax, r15
0x18008a27f  cmova   r15, rax
0x18008a283  mov     [rsp+928h+var_8A8], r15
0x18008a28b  mov     [rsp+928h+var_898], r15
0x18008a293  lea     r9, [rsp+928h+Name]
0x18008a29b  lea     r8, aWindirAppcompa; "%%windir%%\\appcompat\\pca\\ProcessLoad"...
0x18008a2a2  mov     edx, 104h; unsigned __int64
0x18008a2a7  lea     rcx, [rsp+928h+Src]; unsigned __int16 *
0x18008a2af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008a2b4  test    eax, eax
0x18008a2b6  jns     short loc_18008A2CF
0x18008a2b8  lea     r9, aStringcchprint_3; "StringCchPrintfW failed to build user f"...
0x18008a2bf  mov     r8d, 797h
0x18008a2c5  mov     ecx, 1
0x18008a2ca  jmp     loc_18008A45E
0x18008a2cf  mov     r8d, 104h; nSize
0x18008a2d5  lea     rdx, [rsp+928h+Dst]; lpDst
0x18008a2dd  lea     rcx, [rsp+928h+Src]; lpSrc
0x18008a2e5  call    cs:__imp_ExpandEnvironmentStringsW
0x18008a2eb  test    eax, eax
0x18008a2ed  jnz     short loc_18008A325
0x18008a2ef  call    cs:__imp_GetLastError
0x18008a2f5  mov     dword ptr [rsp+928h+lpcbMaxSubKeyLen], eax
0x18008a2f9  lea     rax, [rsp+928h+Name]
0x18008a301  mov     [rsp+928h+lpcSubKeys], rax
0x18008a306  lea     r9, aExpandenvironm_3; "ExpandEnvironmentStringsW failed for us"...
0x18008a30d  mov     r8d, 79Eh
0x18008a313  mov     rdx, rdi
0x18008a316  mov     ecx, 1
0x18008a31b  call    AslLogCallPrintf
0x18008a320  jmp     loc_18008A473
0x18008a325  mov     [rsp+928h+var_8B0], rbx
0x18008a32a  lea     rdx, [rsp+928h+var_8B0]; struct _DLL_LIST_ENTRY **
0x18008a32f  lea     rcx, [rsp+928h+Dst]; unsigned __int16 *
0x18008a337  call    ?ReadExistingDllList@@YAHPEBGPEAPEAU_DLL_LIST_ENTRY@@@Z; ReadExistingDllList(ushort const *,_DLL_LIST_ENTRY * *)
0x18008a33c  mov     ecx, r12d
0x18008a33f  test    eax, eax
0x18008a341  jz      loc_18008A451
0x18008a347  lea     rax, [rsp+928h+Name]
0x18008a34f  mov     rdx, rdi
0x18008a352  mov     [rsp+928h+lpcSubKeys], rax
0x18008a357  cmp     [rsp+928h+var_8B0], rbx
0x18008a35c  jz      loc_18008A442
0x18008a362  lea     r9, aFoundProcessDl; "Found process DLL data file for user %w"...
0x18008a369  mov     r8d, 7A8h
0x18008a36f  call    AslLogCallPrintf
0x18008a374  nop
0x18008a375  mov     r15, [rsp+928h+var_8B0]
0x18008a37a  test    r15, r15
0x18008a37d  jz      short loc_18008A3B7
0x18008a37f  mov     r8, [r15+10h]; unsigned __int16 *
0x18008a383  mov     rdx, [r15+8]; unsigned __int16 *
0x18008a387  lea     rcx, [rsp+928h+P]; struct _DLL_LIST_ENTRY **
0x18008a38c  call    ?AddDllToList@@YAHPEAPEAU_DLL_LIST_ENTRY@@PEBG1@Z; AddDllToList(_DLL_LIST_ENTRY * *,ushort const *,ushort const *)
0x18008a391  test    eax, eax
0x18008a393  jnz     short loc_18008A3AD
0x18008a395  lea     r9, aFailedToAddDll_0; "Failed to add DLL to consolidated list "...
0x18008a39c  mov     r8d, 7B3h
0x18008a3a2  mov     rdx, rdi
0x18008a3a5  lea     ecx, [rax+1]
0x18008a3a8  call    AslLogCallPrintf
0x18008a3ad  mov     r15, [r15]
0x18008a3b0  mov     rsi, [rsp+928h+P]
0x18008a3b5  jmp     short loc_18008A37A
0x18008a3b7  jmp     short loc_18008A42A
0x18008a3b9  mov     dword ptr [rsp+928h+lpcSubKeys], eax
0x18008a3bd  lea     r9, aExceptionOccur; "Exception occurred while merging user D"...
0x18008a3c4  mov     r8d, 7BBh
0x18008a3ca  lea     rdx, aDumprunningpro_1; "DumpRunningProcessesLoadedDllDetector_C"...
0x18008a3d1  mov     ecx, 1
0x18008a3d6  call    AslLogCallPrintf
0x18008a3db  mov     rsi, [rsp+928h+P]
0x18008a3e0  test    rsi, rsi
0x18008a3e3  jz      short loc_18008A3F8
0x18008a3e5  mov     rcx, rsi; P
0x18008a3e8  call    ?FreeDllList@@YAXPEAU_DLL_LIST_ENTRY@@@Z; FreeDllList(_DLL_LIST_ENTRY *)
0x18008a3ed  xor     esi, esi
0x18008a3ef  mov     [rsp+928h+P], rsi
0x18008a3f4  xor     eax, eax
0x18008a3f6  jmp     short loc_18008A400
0x18008a3f8  mov     rax, [rsp+928h+var_898]
0x18008a400  mov     [rsp+928h+var_8A8], rax
0x18008a408  xor     ebx, ebx
0x18008a40a  lea     rdi, aDumprunningpro_1; "DumpRunningProcessesLoadedDllDetector_C"...
0x18008a411  lea     r12d, [rbx+3]
0x18008a415  mov     r13d, [rsp+928h+var_8BC]
0x18008a41a  mov     rax, [rsp+928h+var_890]
0x18008a422  mov     [rsp+928h+var_8A0], rax
0x18008a42a  inc     [rsp+928h+var_8C4]
0x18008a42e  mov     rcx, [rsp+928h+var_8B0]; P
0x18008a433  call    ?FreeDllList@@YAXPEAU_DLL_LIST_ENTRY@@@Z; FreeDllList(_DLL_LIST_ENTRY *)
0x18008a438  mov     r15, [rsp+928h+var_8A8]
0x18008a440  jmp     short loc_18008A473
0x18008a442  lea     r9, aUserWsFileExis; "User %ws file exists but contains no DL"...
0x18008a449  mov     r8d, 7C9h
0x18008a44f  jmp     short loc_18008A46E
0x18008a451  lea     r9, aFailedToReadDl_0; "Failed to read DLL data file for user %"...
0x18008a458  mov     r8d, 7CEh
0x18008a45e  lea     rax, [rsp+928h+Name]
0x18008a466  mov     rdx, rdi
0x18008a469  mov     [rsp+928h+lpcSubKeys], rax
0x18008a46e  call    AslLogCallPrintf
0x18008a473  inc     r13d
0x18008a476  mov     [rsp+928h+var_8BC], r13d
0x18008a47b  jmp     loc_18008A0A0
0x18008a480  lea     r9, aNoDllDataFound; "No DLL data found from any user."
0x18008a487  mov     r8d, 7DCh
0x18008a48d  mov     rdx, rdi
0x18008a490  mov     ecx, r12d
0x18008a493  call    AslLogCallPrintf
0x18008a498  mov     rax, r15
0x18008a49b  mov     rcx, [rsp+928h+var_48]
0x18008a4a3  xor     rcx, rsp; StackCookie
0x18008a4a6  call    __security_check_cookie
0x18008a4ab  add     rsp, 8F8h
0x18008a4b2  pop     r15
0x18008a4b4  pop     r13
0x18008a4b6  pop     r12
0x18008a4b8  pop     rdi
0x18008a4b9  pop     rsi
0x18008a4ba  pop     rbx
0x18008a4bb  retn
```
