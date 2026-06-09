# WwanIsMBAEAppInAllowedList(int *)

- ea: `0x1800ae368`
- end: `0x1800ae7d3`
- name: `?WwanIsMBAEAppInAllowedList@@YAKPEAH@Z`
- size: `1131`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ac010`
- `0x1800ad000`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180016c50`
- `0x1800adb5c`
- `0x1800adc08`
- `0x1800add7c`
- `0x1800ade70`
- `0x1800ae22c`
- `0x1800ae368`
- `0x1800b6a40`
- `0x1800b6ac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae4ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae4ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ae59f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ae612`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ae68a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ae59f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ae612`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ae68a`

## string_xrefs

- `0x1800ae50e`: `RegOpenKeyEx failed, dwErr = 0x%8x`
- `0x1800ae517`: `OpenSubKey`
- `0x1800ae538`: `OpenSubKey`
- `0x1800ae580`: `CompletedTasks`
- `0x1800ae3f9`: `WwanIsMBAEAppInAllowedList failed with 0x%8x; assuming not privileged`
- `0x1800ae4cd`: `Opening sub key %ws`
- `0x1800ae480`: `Cannot open root key`
- `0x1800ae5d1`: `CompletedTasks = %d`
- `0x1800ae556`: `Cannot open sub key %ws`
- `0x1800ae5b5`: `RegGetValue for CompletedTasks failed, dwErr = 0x%8x`
- `0x1800ae777`: `Enumeration completed\n`

## pseudocode

```c
__int64 __fastcall WwanIsMBAEAppInAllowedList(int *a1)
{
  int v2; // r14d
  unsigned int CallerPackageFamilyName; // ebx
  unsigned int IsLowBoxMBAEClient; // eax
  HKEY v5; // r13
  DWORD i; // r12d
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // edi
  HKEY v10; // rsi
  void *v11; // rax
  void *v12; // rdi
  _WORD *v13; // rcx
  unsigned int j; // esi
  __int64 v15; // rax
  const unsigned __int16 *k; // rbx
  __int64 v17; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int pvData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 packageFamilyNameLength[3]; // [rsp+54h] [rbp-ACh] BYREF
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+F0h] [rbp-10h] BYREF

  LODWORD(hkey) = 0;
  v2 = 0;
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength[0] = 65;
  memset_0(SubKey, 0, 0x208u);
  cchName = 0;
  pvData = 0;
  pcbData = 0;
  if ( a1 )
  {
    *a1 = 0;
    IsLowBoxMBAEClient = WwanIsLowBoxMBAEClient((int *)&hkey);
    if ( IsLowBoxMBAEClient )
    {
      WwanLog::Error(
        "WwanIsMBAEAppInAllowedList",
        0,
        L"WwanIsMBAEAppInAllowedList failed with 0x%8x; assuming not privileged",
        IsLowBoxMBAEClient);
      CallerPackageFamilyName = 5;
    }
    else if ( (_DWORD)hkey )
    {
      CallerPackageFamilyName = GetCallerPackageFamilyName(packageFamilyNameLength, packageFamilyName);
      if ( !CallerPackageFamilyName )
      {
        WwanLog::Verbose("WwanIsMBAEAppInAllowedList", 0, L"Package family name = %ws", packageFamilyName);
        v5 = (HKEY)OpenRootKey();
        if ( v5 )
        {
          for ( i = 0; ; ++i )
          {
            cchName = 260;
            v7 = EnumerateKey(v5, i, SubKey, &cchName);
            CallerPackageFamilyName = v7;
            if ( v7 )
              break;
            WwanLog::Verbose("WwanIsMBAEAppInAllowedList", 0, L"Opening sub key %ws", SubKey);
            hkey = 0;
            v8 = RegOpenKeyExW(v5, SubKey, 0, 0x20019u, &hkey);
            v9 = v8;
            if ( v8 )
            {
              WwanLog::Error("OpenSubKey", 0, L"RegOpenKeyEx failed, dwErr = 0x%8x", v8);
              hkey = 0;
            }
            WwanLog::Verbose("OpenSubKey", 0, L"dwErr = 0x%8x", v9);
            v10 = hkey;
            if ( hkey )
            {
              pcbData = 4;
              RegGetValueW(hkey, 0, L"CompletedTasks", 0x20000010u, 0, &pvData, &pcbData);
              if ( pcbData == 4 )
              {
                WwanLog::Verbose("WwanIsMBAEAppInAllowedList", 0, L"CompletedTasks = %d", pvData);
                if ( (pvData & 1) != 0 )
                {
                  pcbData = 0;
                  RegGetValueW(v10, 0, L"AppsAccountIsVisibleTo", 0x20u, 0, 0, &pcbData);
                  if ( pcbData <= 0x4000 )
                  {
                    if ( pcbData )
                    {
                      v11 = (void *)WwanMemAlloc(pcbData);
                      v12 = v11;
                      if ( v11 )
                      {
                        memset_0(v11, 0, pcbData);
                        RegGetValueW(v10, 0, L"AppsAccountIsVisibleTo", 0x20000020u, 0, v12, &pcbData);
                        v13 = v12;
                        for ( j = 0; *v13; v13 += v15 + 1 )
                        {
                          ++j;
                          v15 = -1;
                          do
                            ++v15;
                          while ( v13[v15] );
                        }
                        WwanLog::Verbose("WwanIsMBAEAppInAllowedList", 0, L"Apps count = %d", j);
                        if ( j == 1 && (unsigned int)StringsEqualCaseInsensitive((const unsigned __int16 *)v12, L"*") )
                        {
                          WwanLog::Verbose("WwanIsMBAEAppInAllowedList", 0, L"App package family name = %ws\n", v12);
                          v2 = 1;
                          goto LABEL_42;
                        }
                        if ( !v2 )
                        {
                          for ( k = (const unsigned __int16 *)v12; *k; k += v17 + 1 )
                          {
                            WwanLog::Verbose("WwanIsMBAEAppInAllowedList", 0, L"App package family name = %ws\n", k);
                            if ( (unsigned int)StringsEqualCaseInsensitive(k, packageFamilyName) )
                            {
                              v2 = 1;
                              break;
                            }
                            v17 = -1;
                            do
                              ++v17;
                            while ( k[v17] );
                          }
                        }
                        WwanMemFree(v12);
                      }
                    }
                  }
                  else
                  {
                    WwanLog::Error(
                      "WwanIsMBAEAppInAllowedList",
                      0,
                      L"RegGetValue for AppsAccountIsVisibleTo failed, dwErr = 0x%8x",
                      13);
                  }
                }
              }
              else
              {
                WwanLog::Error(
                  "WwanIsMBAEAppInAllowedList",
                  0,
                  L"RegGetValue for CompletedTasks failed, dwErr = 0x%8x",
                  13);
              }
            }
            else
            {
              WwanLog::Error("WwanIsMBAEAppInAllowedList", 0, L"Cannot open sub key %ws", SubKey);
            }
          }
          if ( v7 == 259 )
          {
            WwanLog::Verbose("WwanIsMBAEAppInAllowedList", 0, L"Enumeration completed\n");
            CallerPackageFamilyName = 0;
          }
        }
        else
        {
          WwanLog::Error("WwanIsMBAEAppInAllowedList", 0, L"Cannot open root key");
          CallerPackageFamilyName = 6;
        }
      }
    }
    else
    {
      CallerPackageFamilyName = 5;
      WwanLog::Error("WwanIsMBAEAppInAllowedList", 0, L"Calling App is lowbox but not MBAE; failing with 0x%8x", 5);
    }
  }
  else
  {
    CallerPackageFamilyName = 87;
  }
LABEL_42:
  *a1 = v2;
  LODWORD(phkResult) = v2;
  WwanLog::Verbose(
    "WwanIsMBAEAppInAllowedList",
    0,
    L"dwErr = 0x%8x, AppInAllowedList = %d",
    CallerPackageFamilyName,
    phkResult);
  return CallerPackageFamilyName;
}

```

## disassembly

```asm
0x1800ae368  push    rbp
0x1800ae36a  push    rbx
0x1800ae36b  push    rsi
0x1800ae36c  push    rdi
0x1800ae36d  push    r12
0x1800ae36f  push    r13
0x1800ae371  push    r14
0x1800ae373  push    r15
0x1800ae375  lea     rbp, [rsp-218h]
0x1800ae37d  sub     rsp, 318h
0x1800ae384  mov     rax, cs:__security_cookie
0x1800ae38b  xor     rax, rsp
0x1800ae38e  mov     [rbp+250h+var_50], rax
0x1800ae395  mov     r15, rcx
0x1800ae398  xor     edi, edi
0x1800ae39a  lea     rcx, [rsp+350h+packageFamilyName]; void *
0x1800ae39f  mov     dword ptr [rsp+350h+hkey], edi
0x1800ae3a3  xor     edx, edx; Val
0x1800ae3a5  mov     r8d, 82h; Size
0x1800ae3ab  mov     r14d, edi
0x1800ae3ae  call    memset_0
0x1800ae3b3  xor     edx, edx; Val
0x1800ae3b5  mov     [rsp+350h+packageFamilyNameLength], 41h ; 'A'
0x1800ae3bd  mov     r8d, 208h; Size
0x1800ae3c3  lea     rcx, [rbp+250h+SubKey]; void *
0x1800ae3c7  call    memset_0
0x1800ae3cc  mov     [rsp+350h+cchName], edi
0x1800ae3d0  mov     [rsp+350h+var_30C], edi
0x1800ae3d4  mov     [rsp+350h+var_310], edi
0x1800ae3d8  test    r15, r15
0x1800ae3db  jnz     short loc_1800AE3E5
0x1800ae3dd  lea     ebx, [rdi+57h]
0x1800ae3e0  jmp     loc_1800AE78E
0x1800ae3e5  lea     rcx, [rsp+350h+hkey]; int *
0x1800ae3ea  mov     [r15], edi
0x1800ae3ed  call    ?WwanIsLowBoxMBAEClient@@YAKPEAH@Z; WwanIsLowBoxMBAEClient(int *)
0x1800ae3f2  test    eax, eax
0x1800ae3f4  jz      short loc_1800AE418
0x1800ae3f6  mov     r9d, eax
0x1800ae3f9  lea     r8, aWwanismbaeappi_0; "WwanIsMBAEAppInAllowedList failed with "...
0x1800ae400  xor     edx, edx; struct _GUID *
0x1800ae402  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae409  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae40e  mov     ebx, 5
0x1800ae413  jmp     loc_1800AE78E
0x1800ae418  cmp     dword ptr [rsp+350h+hkey], edi
0x1800ae41c  jnz     short loc_1800AE440
0x1800ae41e  mov     ebx, 5
0x1800ae423  lea     r8, aCallingAppIsLo_1; "Calling App is lowbox but not MBAE; fai"...
0x1800ae42a  mov     r9d, ebx
0x1800ae42d  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae434  xor     edx, edx; struct _GUID *
0x1800ae436  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae43b  jmp     loc_1800AE78E
0x1800ae440  lea     rdx, [rsp+350h+packageFamilyName]; packageFamilyName
0x1800ae445  lea     rcx, [rsp+350h+packageFamilyNameLength]; packageFamilyNameLength
0x1800ae44a  call    ?GetCallerPackageFamilyName@@YAKPEAIPEAG@Z; GetCallerPackageFamilyName(uint *,ushort *)
0x1800ae44f  mov     ebx, eax
0x1800ae451  test    eax, eax
0x1800ae453  jnz     loc_1800AE78E
0x1800ae459  lea     r9, [rsp+350h+packageFamilyName]
0x1800ae45e  xor     edx, edx; struct _GUID *
0x1800ae460  lea     r8, aPackageFamilyN; "Package family name = %ws"
0x1800ae467  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae46e  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae473  call    ?OpenRootKey@@YAPEAXXZ; OpenRootKey(void)
0x1800ae478  mov     r13, rax
0x1800ae47b  test    rax, rax
0x1800ae47e  jnz     short loc_1800AE49E
0x1800ae480  lea     r8, aCannotOpenRoot; "Cannot open root key"
0x1800ae487  xor     edx, edx; struct _GUID *
0x1800ae489  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae490  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae495  lea     ebx, [r13+6]
0x1800ae499  jmp     loc_1800AE78E
0x1800ae49e  mov     r12d, edi
0x1800ae4a1  lea     r9, [rsp+350h+cchName]; lpcchName
0x1800ae4a6  mov     [rsp+350h+cchName], 104h
0x1800ae4ae  lea     r8, [rbp+250h+SubKey]; lpName
0x1800ae4b2  mov     edx, r12d; dwIndex
0x1800ae4b5  mov     rcx, r13; hKey
0x1800ae4b8  call    ?EnumerateKey@@YAKPEAXIPEAGPEAK@Z; EnumerateKey(void *,uint,ushort *,ulong *)
0x1800ae4bd  mov     ebx, eax
0x1800ae4bf  test    eax, eax
0x1800ae4c1  jnz     loc_1800AE770
0x1800ae4c7  lea     r9, [rbp+250h+SubKey]
0x1800ae4cb  xor     edx, edx; struct _GUID *
0x1800ae4cd  lea     r8, aOpeningSubKeyW; "Opening sub key %ws"
0x1800ae4d4  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae4db  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae4e0  lea     rax, [rsp+350h+hkey]
0x1800ae4e5  mov     [rsp+350h+hkey], rdi
0x1800ae4ea  mov     r9d, 20019h; samDesired
0x1800ae4f0  mov     [rsp+350h+phkResult], rax; phkResult
0x1800ae4f5  xor     r8d, r8d; ulOptions
0x1800ae4f8  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x1800ae4fc  mov     rcx, r13; hKey
0x1800ae4ff  call    cs:__imp_RegOpenKeyExW
0x1800ae505  mov     edi, eax
0x1800ae507  test    eax, eax
0x1800ae509  jz      short loc_1800AE52C
0x1800ae50b  mov     r9d, eax
0x1800ae50e  lea     r8, aRegopenkeyexFa; "RegOpenKeyEx failed, dwErr = 0x%8x"
0x1800ae515  xor     edx, edx; struct _GUID *
0x1800ae517  lea     rcx, aOpensubkey; "OpenSubKey"
0x1800ae51e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae523  mov     [rsp+350h+hkey], 0
0x1800ae52c  mov     r9d, edi
0x1800ae52f  lea     r8, aDwerr0x8x_0; "dwErr = 0x%8x"
0x1800ae536  xor     edx, edx; struct _GUID *
0x1800ae538  lea     rcx, aOpensubkey; "OpenSubKey"
0x1800ae53f  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae544  mov     rsi, [rsp+350h+hkey]
0x1800ae549  xor     edx, edx; struct _GUID *
0x1800ae54b  xor     edi, edi
0x1800ae54d  test    rsi, rsi
0x1800ae550  jnz     short loc_1800AE56E
0x1800ae552  lea     r9, [rbp+250h+SubKey]
0x1800ae556  lea     r8, aCannotOpenSubK; "Cannot open sub key %ws"
0x1800ae55d  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae564  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae569  jmp     loc_1800AE768
0x1800ae56e  lea     rax, [rsp+350h+var_310]
0x1800ae573  mov     [rsp+350h+var_310], 4
0x1800ae57b  mov     [rsp+350h+pcbData], rax; pcbData
0x1800ae580  lea     r8, aCompletedtasks_0; "CompletedTasks"
0x1800ae587  lea     rax, [rsp+350h+var_30C]
0x1800ae58c  mov     r9d, 20000010h; dwFlags
0x1800ae592  mov     [rsp+350h+pvData], rax; pvData
0x1800ae597  mov     rcx, rsi; hkey
0x1800ae59a  mov     [rsp+350h+phkResult], rdi; pdwType
0x1800ae59f  call    cs:__imp_RegGetValueW
0x1800ae5a5  xor     edx, edx; struct _GUID *
0x1800ae5a7  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae5ae  cmp     [rsp+350h+var_310], 4
0x1800ae5b3  jz      short loc_1800AE5CC
0x1800ae5b5  lea     r8, aReggetvalueFor_0; "RegGetValue for CompletedTasks failed, "...
0x1800ae5bc  mov     r9d, 0Dh
0x1800ae5c2  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ae5c7  jmp     loc_1800AE768
0x1800ae5cc  mov     r9d, [rsp+350h+var_30C]
0x1800ae5d1  lea     r8, aCompletedtasks; "CompletedTasks = %d"
0x1800ae5d8  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae5dd  test    byte ptr [rsp+350h+var_30C], 1
0x1800ae5e2  jz      loc_1800AE768
0x1800ae5e8  lea     rax, [rsp+350h+var_310]
0x1800ae5ed  mov     [rsp+350h+var_310], edi
0x1800ae5f1  mov     [rsp+350h+pcbData], rax; pcbData
0x1800ae5f6  lea     r8, aAppsaccountisv; "AppsAccountIsVisibleTo"
0x1800ae5fd  mov     [rsp+350h+pvData], rdi; pvData
0x1800ae602  mov     r9d, 20h ; ' '; dwFlags
0x1800ae608  xor     edx, edx; lpSubKey
0x1800ae60a  mov     [rsp+350h+phkResult], rdi; pdwType
0x1800ae60f  mov     rcx, rsi; hkey
0x1800ae612  call    cs:__imp_RegGetValueW
0x1800ae618  mov     eax, [rsp+350h+var_310]
0x1800ae61c  cmp     eax, 4000h
0x1800ae621  jbe     short loc_1800AE635
0x1800ae623  lea     r8, aReggetvalueFor; "RegGetValue for AppsAccountIsVisibleTo "...
0x1800ae62a  xor     edx, edx
0x1800ae62c  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae633  jmp     short loc_1800AE5BC
0x1800ae635  test    eax, eax
0x1800ae637  jz      loc_1800AE768
0x1800ae63d  mov     rcx, rax; Size
0x1800ae640  call    WwanMemAlloc
0x1800ae645  mov     rdi, rax
0x1800ae648  test    rax, rax
0x1800ae64b  jz      loc_1800AE766
0x1800ae651  mov     r8d, [rsp+350h+var_310]; Size
0x1800ae656  xor     edx, edx; Val
0x1800ae658  mov     rcx, rax; void *
0x1800ae65b  call    memset_0
0x1800ae660  lea     rax, [rsp+350h+var_310]
0x1800ae665  mov     r9d, 20000020h; dwFlags
0x1800ae66b  mov     [rsp+350h+pcbData], rax; pcbData
0x1800ae670  lea     r8, aAppsaccountisv; "AppsAccountIsVisibleTo"
0x1800ae677  mov     [rsp+350h+pvData], rdi; pvData
0x1800ae67c  xor     edx, edx; lpSubKey
0x1800ae67e  mov     rcx, rsi; hkey
0x1800ae681  mov     [rsp+350h+phkResult], 0; pdwType
0x1800ae68a  call    cs:__imp_RegGetValueW
0x1800ae690  xor     edx, edx; struct _GUID *
0x1800ae692  mov     rcx, rdi
0x1800ae695  mov     esi, edx
0x1800ae697  cmp     dx, [rdi]
0x1800ae69a  jz      short loc_1800AE6B8
0x1800ae69c  inc     esi
0x1800ae69e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ae6a2  inc     rax
0x1800ae6a5  cmp     [rcx+rax*2], dx
0x1800ae6a9  jnz     short loc_1800AE6A2
0x1800ae6ab  lea     rcx, [rcx+rax*2]
0x1800ae6af  add     rcx, 2
0x1800ae6b3  cmp     dx, [rcx]
0x1800ae6b6  jnz     short loc_1800AE69C
0x1800ae6b8  mov     r9d, esi
0x1800ae6bb  lea     r8, aAppsCountD; "Apps count = %d"
0x1800ae6c2  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae6c9  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae6ce  cmp     esi, 1
0x1800ae6d1  jnz     short loc_1800AE709
0x1800ae6d3  lea     rdx, asc_1801330A4; "*"
0x1800ae6da  mov     rcx, rdi; unsigned __int16 *
0x1800ae6dd  call    ?StringsEqualCaseInsensitive@@YAHPEBG0@Z; StringsEqualCaseInsensitive(ushort const *,ushort const *)
0x1800ae6e2  xor     esi, esi
0x1800ae6e4  test    eax, eax
0x1800ae6e6  jz      short loc_1800AE70B
0x1800ae6e8  mov     r9, rdi
0x1800ae6eb  lea     r8, aAppPackageFami; "App package family name = %ws\n"
0x1800ae6f2  xor     edx, edx; struct _GUID *
0x1800ae6f4  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae6fb  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae700  lea     r14d, [rsi+1]
0x1800ae704  jmp     loc_1800AE78E
0x1800ae709  xor     esi, esi
0x1800ae70b  test    r14d, r14d
0x1800ae70e  jnz     short loc_1800AE75E
0x1800ae710  mov     rbx, rdi
0x1800ae713  cmp     si, [rbx]
0x1800ae716  jz      short loc_1800AE75E
0x1800ae718  mov     r9, rbx
0x1800ae71b  lea     r8, aAppPackageFami; "App package family name = %ws\n"
0x1800ae722  xor     edx, edx; struct _GUID *
0x1800ae724  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae72b  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae730  lea     rdx, [rsp+350h+packageFamilyName]; unsigned __int16 *
0x1800ae735  mov     rcx, rbx; unsigned __int16 *
0x1800ae738  call    ?StringsEqualCaseInsensitive@@YAHPEBG0@Z; StringsEqualCaseInsensitive(ushort const *,ushort const *)
0x1800ae73d  test    eax, eax
0x1800ae73f  jnz     short loc_1800AE758
0x1800ae741  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ae745  inc     rax
0x1800ae748  cmp     [rbx+rax*2], si
0x1800ae74c  jnz     short loc_1800AE745
0x1800ae74e  lea     rbx, [rbx+rax*2]
0x1800ae752  add     rbx, 2
0x1800ae756  jmp     short loc_1800AE713
0x1800ae758  mov     r14d, 1
0x1800ae75e  mov     rcx, rdi
0x1800ae761  call    WwanMemFree
0x1800ae766  xor     edi, edi
0x1800ae768  inc     r12d
0x1800ae76b  jmp     loc_1800AE4A1
0x1800ae770  cmp     eax, 103h
0x1800ae775  jnz     short loc_1800AE78E
0x1800ae777  lea     r8, aEnumerationCom; "Enumeration completed\n"
0x1800ae77e  xor     edx, edx; struct _GUID *
0x1800ae780  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae787  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae78c  mov     ebx, edi
0x1800ae78e  mov     r9d, ebx
0x1800ae791  mov     [r15], r14d
0x1800ae794  lea     r8, aDwerr0x8xAppin; "dwErr = 0x%8x, AppInAllowedList = %d"
0x1800ae79b  mov     dword ptr [rsp+350h+phkResult], r14d
0x1800ae7a0  xor     edx, edx; struct _GUID *
0x1800ae7a2  lea     rcx, aWwanismbaeappi_1; "WwanIsMBAEAppInAllowedList"
0x1800ae7a9  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ae7ae  mov     eax, ebx
0x1800ae7b0  mov     rcx, [rbp+250h+var_50]
0x1800ae7b7  xor     rcx, rsp; StackCookie
0x1800ae7ba  call    __security_check_cookie
0x1800ae7bf  add     rsp, 318h
0x1800ae7c6  pop     r15
0x1800ae7c8  pop     r14
0x1800ae7ca  pop     r13
0x1800ae7cc  pop     r12
0x1800ae7ce  pop     rdi
0x1800ae7cf  pop     rsi
0x1800ae7d0  pop     rbx
0x1800ae7d1  pop     rbp
0x1800ae7d2  retn
```
