# IsActiveXControl

- ea: `0x180045180`
- end: `0x180045571`
- name: `IsActiveXControl`
- size: `1009`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044e1c`

## callees

- `0x180004dd0`
- `0x180044b84`
- `0x180045180`
- `0x18008c070`
- `0x1800a2718`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180045227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004525a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180045227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004525a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800453b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180045471`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800453b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180045471`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180045291`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800452ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180045371`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180045291`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800452ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180045371`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800453f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800454fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004550c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004551c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004552c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004553c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800453f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800454fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004550c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004551c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004552c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004553c`

## string_xrefs

- `0x180045275`: `CLSID`
- `0x180045355`: `CLSID`
- `0x18004542b`: `CLSID`
- `0x1800454e0`: `clsid:%s`
- `0x18004548c`: `CLSID\%s\Control`

## pseudocode

```c
_BOOL8 __fastcall IsActiveXControl(char *a1, __int64 a2, const CHAR *a3, const char *a4)
{
  LSTATUS ValueA; // ebx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  __int64 v11; // rax
  HKEY v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // r9d
  unsigned int v15; // r8d
  unsigned int v16; // r9d
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v19; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v22; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v23; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data; // [rsp+70h] [rbp-90h] BYREF
  char v25[271]; // [rsp+71h] [rbp-8Fh] BYREF
  CHAR pvData[272]; // [rsp+180h] [rbp+80h] BYREF
  CHAR SubKey[272]; // [rsp+290h] [rbp+190h] BYREF
  CHAR v28[272]; // [rsp+3A0h] [rbp+2A0h] BYREF

  hKey = 0;
  hkey = 0;
  ValueA = 0;
  v19 = 0;
  v22 = 0;
  cbData = 0;
  v23 = 0;
  if ( a4 && *a4 )
  {
    StringCchPrintfA(SubKey, 0x104u, "MIME\\Database\\Content Type\\%s", a4);
    ValueA = RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
    if ( (unsigned int)IsInternetExplorerApp() && ValueA == 2 )
      ValueA = RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x20219u, &hKey);
    if ( !ValueA )
    {
      cbData = 260;
      ValueA = RegQueryValueExA(hKey, "CLSID", 0, 0, &Data, &cbData);
      if ( !ValueA )
        goto LABEL_25;
    }
  }
  if ( a3 )
  {
    if ( *a3 )
    {
      ValueA = _RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, a3, (unsigned int)a3, (unsigned int)a4, &hkey);
      if ( !ValueA )
      {
        cbData = 260;
        if ( !RegQueryValueExA(hkey, "Content Type", 0, 0, (LPBYTE)pvData, &cbData) )
        {
          if ( cbData )
          {
            StringCchPrintfA((char *)&Data, 0x104u, "MIME\\Database\\Content Type\\%s", pvData);
            if ( !(unsigned int)_RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, (LPCSTR)&Data, v7, v8, &v19) )
            {
              cbData = 260;
              if ( !RegQueryValueExA(v19, "CLSID", 0, 0, &Data, &cbData) )
              {
                if ( cbData )
                  goto LABEL_25;
              }
            }
          }
        }
        cbData = 260;
        ValueA = RegGetValueA(hkey, 0, 0, 0x10000006u, 0, pvData, &cbData);
        if ( !ValueA )
        {
          if ( cbData )
          {
            v11 = cbData - 1;
            if ( (unsigned int)v11 >= 0x104uLL )
              goto LABEL_40;
            v12 = v19;
            pvData[v11] = 0;
            if ( v12 )
            {
              RegCloseKey(v12);
              v19 = 0;
            }
            ValueA = _RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, pvData, v9, v10, &v19);
            if ( !ValueA )
            {
              ValueA = _RegOpenKeyWithWow6432Fallback(v19, "CLSID", v13, v14, &v22);
              if ( !ValueA )
              {
                cbData = 260;
                ValueA = RegGetValueA(v22, 0, 0, 0x10000006u, 0, &Data, &cbData);
                if ( !ValueA )
                {
                  if ( cbData )
                  {
LABEL_25:
                    StringCchPrintfA(v28, 0x104u, "CLSID\\%s\\Control", (const char *)&Data);
                    ValueA = _RegOpenKeyWithWow6432Fallback(HKEY_CLASSES_ROOT, v28, v15, v16, &v23);
                    if ( !ValueA && a1 )
                    {
                      if ( cbData - 2 < 0x104uLL )
                      {
                        *(&Data + cbData - 2) = 0;
                        StringCchPrintfA(a1, 0x104u, "clsid:%s", v25);
                        goto LABEL_29;
                      }
LABEL_40:
                      _report_rangecheckfailure();
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_29:
  if ( v23 )
    RegCloseKey(v23);
  if ( v22 )
    RegCloseKey(v22);
  if ( v19 )
    RegCloseKey(v19);
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  return ValueA == 0;
}

```

## disassembly

```asm
0x180045180  push    rbp
0x180045182  push    rbx
0x180045183  push    rsi
0x180045184  push    rdi
0x180045185  push    r12
0x180045187  push    r14
0x180045189  push    r15
0x18004518b  lea     rbp, [rsp-3C0h]
0x180045193  sub     rsp, 4C0h
0x18004519a  mov     rax, cs:__security_cookie
0x1800451a1  xor     rax, rsp
0x1800451a4  mov     [rbp+3F0h+var_40], rax
0x1800451ab  xor     r14d, r14d
0x1800451ae  mov     rdi, r8
0x1800451b1  mov     [rsp+4F0h+hKey], r14
0x1800451b6  mov     rsi, rcx
0x1800451b9  mov     [rsp+4F0h+hkey], r14
0x1800451be  mov     ebx, r14d
0x1800451c1  mov     [rsp+4F0h+var_4A8], r14
0x1800451c6  mov     r15d, 104h
0x1800451cc  mov     [rsp+4F0h+var_490], r14
0x1800451d1  mov     r12, 0FFFFFFFF80000000h
0x1800451d8  mov     [rsp+4F0h+cbData], r14d
0x1800451dd  mov     [rsp+4F0h+var_488], r14
0x1800451e2  test    r9, r9
0x1800451e5  jz      loc_1800452A1
0x1800451eb  cmp     [r9], r14b
0x1800451ee  jz      loc_1800452A1
0x1800451f4  lea     r8, aMimeDatabaseCo; "MIME\\Database\\Content Type\\%s"
0x1800451fb  mov     edx, r15d; unsigned __int64
0x1800451fe  lea     rcx, [rbp+3F0h+SubKey]; char *
0x180045205  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18004520a  lea     rax, [rsp+4F0h+hKey]
0x18004520f  mov     r9d, 20019h; samDesired
0x180045215  xor     r8d, r8d; ulOptions
0x180045218  mov     [rsp+4F0h+phkResult], rax; phkResult
0x18004521d  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180045224  mov     rcx, r12; hKey
0x180045227  call    cs:__imp_RegOpenKeyExA
0x18004522d  mov     ebx, eax
0x18004522f  call    ?IsInternetExplorerApp@@YAHXZ; IsInternetExplorerApp(void)
0x180045234  test    eax, eax
0x180045236  jz      short loc_180045262
0x180045238  cmp     ebx, 2
0x18004523b  jnz     short loc_180045262
0x18004523d  lea     rax, [rsp+4F0h+hKey]
0x180045242  mov     r9d, 20219h; samDesired
0x180045248  xor     r8d, r8d; ulOptions
0x18004524b  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180045250  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180045257  mov     rcx, r12; hKey
0x18004525a  call    cs:__imp_RegOpenKeyExA
0x180045260  mov     ebx, eax
0x180045262  test    ebx, ebx
0x180045264  jnz     short loc_1800452A1
0x180045266  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18004526b  lea     rax, [rsp+4F0h+cbData]
0x180045270  mov     [rsp+4F0h+lpcbData], rax; lpcbData
0x180045275  lea     rdx, aClsid_3; "CLSID"
0x18004527c  lea     rax, [rsp+4F0h+Data]
0x180045281  mov     [rsp+4F0h+cbData], r15d
0x180045286  xor     r9d, r9d; lpType
0x180045289  mov     [rsp+4F0h+phkResult], rax; lpData
0x18004528e  xor     r8d, r8d; lpReserved
0x180045291  call    cs:__imp_RegQueryValueExA
0x180045297  mov     ebx, eax
0x180045299  test    eax, eax
0x18004529b  jz      loc_180045484
0x1800452a1  test    rdi, rdi
0x1800452a4  jz      loc_1800454F2
0x1800452aa  cmp     [rdi], r14b
0x1800452ad  jz      loc_1800454F2
0x1800452b3  lea     rax, [rsp+4F0h+hkey]
0x1800452b8  mov     rdx, rdi; lpSubKey
0x1800452bb  mov     rcx, r12; hKey
0x1800452be  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x1800452c3  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x1800452c8  mov     ebx, eax
0x1800452ca  test    eax, eax
0x1800452cc  jnz     loc_1800454F2
0x1800452d2  mov     rcx, [rsp+4F0h+hkey]; hKey
0x1800452d7  lea     rax, [rsp+4F0h+cbData]
0x1800452dc  mov     [rsp+4F0h+lpcbData], rax; lpcbData
0x1800452e1  lea     rdx, aContentType_0; "Content Type"
0x1800452e8  lea     rax, [rbp+3F0h+pvData]
0x1800452ef  mov     [rsp+4F0h+cbData], r15d
0x1800452f4  xor     r9d, r9d; lpType
0x1800452f7  mov     [rsp+4F0h+phkResult], rax; lpData
0x1800452fc  xor     r8d, r8d; lpReserved
0x1800452ff  call    cs:__imp_RegQueryValueExA
0x180045305  test    eax, eax
0x180045307  jnz     short loc_180045386
0x180045309  cmp     [rsp+4F0h+cbData], r14d
0x18004530e  jbe     short loc_180045386
0x180045310  lea     r9, [rbp+3F0h+pvData]
0x180045317  mov     rdx, r15; unsigned __int64
0x18004531a  lea     r8, aMimeDatabaseCo; "MIME\\Database\\Content Type\\%s"
0x180045321  lea     rcx, [rsp+4F0h+Data]; char *
0x180045326  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18004532b  lea     rax, [rsp+4F0h+var_4A8]
0x180045330  mov     rcx, r12; hKey
0x180045333  lea     rdx, [rsp+4F0h+Data]; lpSubKey
0x180045338  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x18004533d  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x180045342  test    eax, eax
0x180045344  jnz     short loc_180045386
0x180045346  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x18004534b  lea     rax, [rsp+4F0h+cbData]
0x180045350  mov     [rsp+4F0h+lpcbData], rax; lpcbData
0x180045355  lea     rdx, aClsid_3; "CLSID"
0x18004535c  lea     rax, [rsp+4F0h+Data]
0x180045361  mov     [rsp+4F0h+cbData], r15d
0x180045366  xor     r9d, r9d; lpType
0x180045369  mov     [rsp+4F0h+phkResult], rax; lpData
0x18004536e  xor     r8d, r8d; lpReserved
0x180045371  call    cs:__imp_RegQueryValueExA
0x180045377  test    eax, eax
0x180045379  jnz     short loc_180045386
0x18004537b  cmp     [rsp+4F0h+cbData], r14d
0x180045380  ja      loc_180045484
0x180045386  mov     rcx, [rsp+4F0h+hkey]; hkey
0x18004538b  lea     rax, [rsp+4F0h+cbData]
0x180045390  mov     [rsp+4F0h+pcbData], rax; pcbData
0x180045395  mov     edi, 10000006h
0x18004539a  lea     rax, [rbp+3F0h+pvData]
0x1800453a1  mov     [rsp+4F0h+cbData], r15d
0x1800453a6  mov     [rsp+4F0h+lpcbData], rax; pvData
0x1800453ab  mov     r9d, edi; dwFlags
0x1800453ae  xor     r8d, r8d; lpValue
0x1800453b1  mov     [rsp+4F0h+phkResult], r14; pdwType
0x1800453b6  xor     edx, edx; lpSubKey
0x1800453b8  call    cs:__imp_RegGetValueA
0x1800453be  mov     ebx, eax
0x1800453c0  test    eax, eax
0x1800453c2  jnz     loc_1800454F2
0x1800453c8  mov     eax, [rsp+4F0h+cbData]
0x1800453cc  test    eax, eax
0x1800453ce  jz      loc_1800454F2
0x1800453d4  dec     eax
0x1800453d6  mov     ecx, eax
0x1800453d8  cmp     rcx, r15
0x1800453db  jnb     loc_18004556B
0x1800453e1  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x1800453e6  mov     [rbp+rax+3F0h+pvData], r14b
0x1800453ee  test    rcx, rcx
0x1800453f1  jz      short loc_1800453FE
0x1800453f3  call    cs:__imp_RegCloseKey
0x1800453f9  mov     [rsp+4F0h+var_4A8], r14
0x1800453fe  lea     rax, [rsp+4F0h+var_4A8]
0x180045403  mov     rcx, r12; hKey
0x180045406  lea     rdx, [rbp+3F0h+pvData]; lpSubKey
0x18004540d  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x180045412  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x180045417  mov     ebx, eax
0x180045419  test    eax, eax
0x18004541b  jnz     loc_1800454F2
0x180045421  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x180045426  lea     rax, [rsp+4F0h+var_490]
0x18004542b  lea     rdx, aClsid_3; "CLSID"
0x180045432  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x180045437  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x18004543c  mov     ebx, eax
0x18004543e  test    eax, eax
0x180045440  jnz     loc_1800454F2
0x180045446  mov     rcx, [rsp+4F0h+var_490]; hkey
0x18004544b  lea     rax, [rsp+4F0h+cbData]
0x180045450  mov     [rsp+4F0h+pcbData], rax; pcbData
0x180045455  mov     r9d, edi; dwFlags
0x180045458  lea     rax, [rsp+4F0h+Data]
0x18004545d  mov     [rsp+4F0h+cbData], r15d
0x180045462  mov     [rsp+4F0h+lpcbData], rax; pvData
0x180045467  xor     r8d, r8d; lpValue
0x18004546a  xor     edx, edx; lpSubKey
0x18004546c  mov     [rsp+4F0h+phkResult], r14; pdwType
0x180045471  call    cs:__imp_RegGetValueA
0x180045477  mov     ebx, eax
0x180045479  test    eax, eax
0x18004547b  jnz     short loc_1800454F2
0x18004547d  cmp     [rsp+4F0h+cbData], r14d
0x180045482  jbe     short loc_1800454F2
0x180045484  lea     r9, [rsp+4F0h+Data]
0x180045489  mov     rdx, r15; unsigned __int64
0x18004548c  lea     r8, aClsidSControl; "CLSID\\%s\\Control"
0x180045493  lea     rcx, [rbp+3F0h+var_150]; char *
0x18004549a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18004549f  lea     rax, [rsp+4F0h+var_488]
0x1800454a4  mov     rcx, r12; hKey
0x1800454a7  lea     rdx, [rbp+3F0h+var_150]; lpSubKey
0x1800454ae  mov     [rsp+4F0h+phkResult], rax; HKEY *
0x1800454b3  call    ?_RegOpenKeyWithWow6432Fallback@@YAJPEAUHKEY__@@PEBDKKPEAPEAU1@@Z; _RegOpenKeyWithWow6432Fallback(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x1800454b8  mov     ebx, eax
0x1800454ba  test    eax, eax
0x1800454bc  jnz     short loc_1800454F2
0x1800454be  test    rsi, rsi
0x1800454c1  jz      short loc_1800454F2
0x1800454c3  mov     eax, [rsp+4F0h+cbData]
0x1800454c7  add     eax, 0FFFFFFFEh
0x1800454ca  mov     r8d, eax
0x1800454cd  cmp     r8, r15
0x1800454d0  jnb     loc_18004556B
0x1800454d6  lea     r9, [rsp+4F0h+var_47F]
0x1800454db  mov     [rsp+rax+4F0h+Data], r14b
0x1800454e0  lea     r8, aClsidS_1; "clsid:%s"
0x1800454e7  mov     rdx, r15; unsigned __int64
0x1800454ea  mov     rcx, rsi; char *
0x1800454ed  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800454f2  mov     rcx, [rsp+4F0h+var_488]; hKey
0x1800454f7  test    rcx, rcx
0x1800454fa  jz      short loc_180045502
0x1800454fc  call    cs:__imp_RegCloseKey
0x180045502  mov     rcx, [rsp+4F0h+var_490]; hKey
0x180045507  test    rcx, rcx
0x18004550a  jz      short loc_180045512
0x18004550c  call    cs:__imp_RegCloseKey
0x180045512  mov     rcx, [rsp+4F0h+var_4A8]; hKey
0x180045517  test    rcx, rcx
0x18004551a  jz      short loc_180045522
0x18004551c  call    cs:__imp_RegCloseKey
0x180045522  mov     rcx, [rsp+4F0h+hkey]; hKey
0x180045527  test    rcx, rcx
0x18004552a  jz      short loc_180045532
0x18004552c  call    cs:__imp_RegCloseKey
0x180045532  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180045537  test    rcx, rcx
0x18004553a  jz      short loc_180045542
0x18004553c  call    cs:__imp_RegCloseKey
0x180045542  test    ebx, ebx
0x180045544  mov     eax, r14d
0x180045547  setz    al
0x18004554a  mov     rcx, [rbp+3F0h+var_40]
0x180045551  xor     rcx, rsp; StackCookie
0x180045554  call    __security_check_cookie
0x180045559  add     rsp, 4C0h
0x180045560  pop     r15
0x180045562  pop     r14
0x180045564  pop     r12
0x180045566  pop     rdi
0x180045567  pop     rsi
0x180045568  pop     rbx
0x180045569  pop     rbp
0x18004556a  retn
0x18004556b  call    __report_rangecheckfailure
```
