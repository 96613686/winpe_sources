# AddDelMapping(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800121d8`
- end: `0x1800126b7`
- name: `?AddDelMapping@@YAHPEAUHKEY__@@PEBG11K@Z`
- size: `1247`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014440`

## callees

- `0x180003218`
- `0x1800035c8`
- `0x180008a6c`
- `0x1800121d8`
- `0x1800126c0`
- `0x180012cfc`
- `0x18001b980`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800122a3`
- `KERNEL32!CompareStringW` at `0x1800122a3`
- `ADVAPI32!RegCreateKeyExW` at `0x180012381`
- `ADVAPI32!RegCreateKeyExW` at `0x18001262d`
- `ADVAPI32!RegCreateKeyExW` at `0x180012381`
- `ADVAPI32!RegCreateKeyExW` at `0x18001262d`
- `ADVAPI32!RegQueryValueExW` at `0x1800122eb`
- `ADVAPI32!RegQueryValueExW` at `0x1800122eb`
- `ADVAPI32!RegCloseKey` at `0x1800122fa`
- `ADVAPI32!RegCloseKey` at `0x1800125d9`
- `ADVAPI32!RegCloseKey` at `0x18001268f`
- `ADVAPI32!RegCloseKey` at `0x1800122fa`
- `ADVAPI32!RegCloseKey` at `0x1800125d9`
- `ADVAPI32!RegCloseKey` at `0x18001268f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800122c8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800122c8`
- `ADVAPI32!RegSetValueExW` at `0x1800125c6`
- `ADVAPI32!RegSetValueExW` at `0x18001266a`
- `ADVAPI32!RegSetValueExW` at `0x1800125c6`
- `ADVAPI32!RegSetValueExW` at `0x18001266a`
- `ADVAPI32!RegDeleteValueW` at `0x18001232a`
- `ADVAPI32!RegDeleteValueW` at `0x18001232a`
- `ADVAPI32!RegEnumKeyW` at `0x18001225c`
- `ADVAPI32!RegEnumKeyW` at `0x18001225c`
- `SHLWAPI!StrChrW` at `0x180012271`
- `SHLWAPI!StrChrW` at `0x180012271`

## pseudocode

```c
__int64 __fastcall AddDelMapping(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  const unsigned __int16 *v5; // r14
  const unsigned __int16 *v6; // r15
  HKEY v7; // rsi
  DWORD i; // edi
  unsigned int v9; // ebx
  const WCHAR *v10; // rax
  wchar_t *v11; // r12
  unsigned __int16 Separator; // r13
  unsigned int v13; // edi
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v19[4]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v21; // [rsp+70h] [rbp-90h]
  WCHAR Name[32]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[32]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = g_pcszValueName;
  v6 = g_pszSubKey;
  v7 = g_hkBckupKey;
  v21 = g_pcszRootKey;
  phkResult = 0;
  Convert2CRC(g_pcszRootKey, g_pszSubKey, g_pcszValueName, ValueName, 0x20u);
  for ( i = 0; ; ++i )
  {
    v9 = 0;
    if ( RegEnumKeyW(v7, i, Name, 0x20u) )
      break;
    v10 = StrChrW(Name, 0x2Eu);
    if ( v10
      && CompareStringW(0x7Fu, 1u, v10, -1, L".map", -1) == 2
      && !RegOpenKeyExW(v7, Name, 0, 0x2001Fu, &phkResult) )
    {
      if ( !RegQueryValueExW(phkResult, ValueName, 0, 0, 0, 0) )
      {
        v9 = 1;
        break;
      }
      RegCloseKey(phkResult);
      phkResult = 0;
    }
  }
  if ( g_fRestore )
  {
    if ( v9 )
      RegDeleteValueW(phkResult, ValueName);
  }
  else if ( !v9 )
  {
    StringCchPrintfW(Name, 0x20u, L"%lu.map", 0);
    if ( !RegCreateKeyExW(v7, Name, 0, 0, 0, 0x20006u, 0, &phkResult, 0) )
    {
      v11 = (wchar_t *)g_pszCRCTempBuf;
      pszDest = (STRSAFE_LPWSTR)g_pszCRCTempBuf;
      v17 = 1536;
      Separator = FindSeparator(v6, v5);
      if ( Separator )
      {
        v13 = 0;
        StringCchPrintfW(Name, 0x20u, L"%lu", a5 & 0xFFFFFFFC | 1);
        v19[0] = Separator;
        v19[1] = 0;
        StringCchCopyExW(v11, 0x600u, v19, &pszDest, &v17, 0x200u);
        StringCchCopyExW(pszDest, v17, Name, &pszDest, &v17, 0x200u);
        StringCchCopyExW(pszDest, v17, v19, &pszDest, &v17, 0x200u);
        StringCchCopyExW(pszDest, v17, v21, &pszDest, &v17, 0x200u);
        StringCchCopyExW(pszDest, v17, v19, &pszDest, &v17, 0x200u);
        StringCchCopyExW(pszDest, v17, v6, &pszDest, &v17, 0x200u);
        StringCchCopyExW(pszDest, v17, v19, &pszDest, &v17, 0x200u);
        if ( v5 )
        {
          StringCchCopyExW(pszDest, v17, v5, &pszDest, &v17, 0x200u);
          StringCchCopyExW(pszDest, v17, v19, &pszDest, &v17, 0x200u);
        }
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)g_pszCRCTempBuf + v14) );
        if ( RegSetValueExW(phkResult, ValueName, 0, 1u, (const BYTE *)g_pszCRCTempBuf, 2 * v14 + 2) )
        {
          while ( 1 )
          {
            RegCloseKey(phkResult);
            ++v13;
            phkResult = 0;
            StringCchPrintfW(Name, 0x20u, L"%lu.map", v13);
            if ( !RegCreateKeyExW(v7, Name, 0, 0, 0, 0x20006u, 0, &phkResult, 0) )
            {
              v15 = -1;
              do
                ++v15;
              while ( *((_WORD *)g_pszCRCTempBuf + v15) );
              if ( !RegSetValueExW(phkResult, ValueName, 0, 1u, (const BYTE *)g_pszCRCTempBuf, 2 * v15 + 2) )
                break;
              v9 = 0;
            }
            if ( v13 >= 0x40 )
              goto LABEL_30;
          }
        }
        v9 = 1;
      }
      else
      {
        MsgBox2Param(hWnd, 0x480u, 0, 0, 0x10u, 0);
      }
    }
  }
LABEL_30:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v9;
}

```

## disassembly

```asm
0x1800121d8  push    rbp
0x1800121da  push    rbx
0x1800121db  push    rsi
0x1800121dc  push    rdi
0x1800121dd  push    r12
0x1800121df  push    r13
0x1800121e1  push    r14
0x1800121e3  push    r15
0x1800121e5  lea     rbp, [rsp-18h]
0x1800121ea  sub     rsp, 118h
0x1800121f1  mov     rax, cs:__security_cookie
0x1800121f8  xor     rax, rsp
0x1800121fb  mov     [rbp+50h+var_50], rax
0x1800121ff  mov     rax, cs:?g_pcszRootKey@@3PEBGEB; ushort const * const g_pcszRootKey
0x180012206  lea     r9, [rbp+50h+ValueName]; unsigned __int16 *
0x18001220a  mov     r14, cs:?g_pcszValueName@@3PEBGEB; ushort const * const g_pcszValueName
0x180012211  xor     r12d, r12d
0x180012214  mov     r15, cs:?g_pszSubKey@@3PEAGEA; ushort * g_pszSubKey
0x18001221b  mov     r8, r14; unsigned __int16 *
0x18001221e  mov     rsi, cs:?g_hkBckupKey@@3PEAUHKEY__@@EA; HKEY__ * g_hkBckupKey
0x180012225  mov     rdx, r15; unsigned __int16 *
0x180012228  mov     rcx, rax; unsigned __int16 *
0x18001222b  mov     [rsp+150h+var_E0], rax
0x180012230  mov     [rsp+150h+phkResult], r12
0x180012235  mov     dword ptr [rsp+150h+lpString2], 20h ; ' '; unsigned int
0x18001223d  call    ?Convert2CRC@@YAXPEBG00PEAGK@Z; Convert2CRC(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x180012242  mov     edi, r12d
0x180012245  lea     r13d, [r12+1]
0x18001224a  mov     r9d, 20h ; ' '; cchName
0x180012250  lea     r8, [rbp+50h+Name]; lpName
0x180012254  mov     edx, edi; dwIndex
0x180012256  mov     rcx, rsi; hKey
0x180012259  mov     ebx, r12d
0x18001225c  call    cs:__imp_RegEnumKeyW
0x180012262  test    eax, eax
0x180012264  jnz     loc_180012310
0x18001226a  lea     edx, [rax+2Eh]; wMatch
0x18001226d  lea     rcx, [rbp+50h+Name]; pszStart
0x180012271  call    cs:__imp_StrChrW
0x180012277  test    rax, rax
0x18001227a  jz      loc_180012305
0x180012280  lea     rcx, aMap; ".map"
0x180012287  mov     [rsp+150h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001228f  mov     [rsp+150h+lpString2], rcx; lpString2
0x180012294  or      r9d, 0FFFFFFFFh; cchCount1
0x180012298  mov     ecx, 7Fh; Locale
0x18001229d  mov     r8, rax; lpString1
0x1800122a0  mov     edx, r13d; dwCmpFlags
0x1800122a3  call    cs:__imp_CompareStringW
0x1800122a9  cmp     eax, 2
0x1800122ac  jnz     short loc_180012305
0x1800122ae  lea     rax, [rsp+150h+phkResult]
0x1800122b3  mov     r9d, 2001Fh; samDesired
0x1800122b9  xor     r8d, r8d; ulOptions
0x1800122bc  mov     [rsp+150h+lpString2], rax; phkResult
0x1800122c1  lea     rdx, [rbp+50h+Name]; lpSubKey
0x1800122c5  mov     rcx, rsi; hKey
0x1800122c8  call    cs:__imp_RegOpenKeyExW
0x1800122ce  test    eax, eax
0x1800122d0  jnz     short loc_180012305
0x1800122d2  mov     rcx, [rsp+150h+phkResult]; hKey
0x1800122d7  lea     rdx, [rbp+50h+ValueName]; lpValueName
0x1800122db  mov     qword ptr [rsp+150h+cchCount2], r12; lpcbData
0x1800122e0  xor     r9d, r9d; lpType
0x1800122e3  xor     r8d, r8d; lpReserved
0x1800122e6  mov     [rsp+150h+lpString2], r12; lpData
0x1800122eb  call    cs:__imp_RegQueryValueExW
0x1800122f1  test    eax, eax
0x1800122f3  jz      short loc_18001230D
0x1800122f5  mov     rcx, [rsp+150h+phkResult]; hKey
0x1800122fa  call    cs:__imp_RegCloseKey
0x180012300  mov     [rsp+150h+phkResult], r12
0x180012305  add     edi, r13d
0x180012308  jmp     loc_18001224A
0x18001230d  mov     ebx, r13d
0x180012310  cmp     cs:?g_fRestore@@3HA, r12d; int g_fRestore
0x180012317  jz      short loc_180012335
0x180012319  test    ebx, ebx
0x18001231b  jz      loc_180012685
0x180012321  mov     rcx, [rsp+150h+phkResult]; hKey
0x180012326  lea     rdx, [rbp+50h+ValueName]; lpValueName
0x18001232a  call    cs:__imp_RegDeleteValueW
0x180012330  jmp     loc_180012685
0x180012335  test    ebx, ebx
0x180012337  jnz     loc_180012685
0x18001233d  xor     r9d, r9d
0x180012340  lea     r8, aLuMap; "%lu.map"
0x180012347  lea     edx, [rbx+20h]; unsigned __int64
0x18001234a  lea     rcx, [rbp+50h+Name]; unsigned __int16 *
0x18001234e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012353  mov     [rsp+150h+lpdwDisposition], r12; lpdwDisposition
0x180012358  lea     rax, [rsp+150h+phkResult]
0x18001235d  mov     [rsp+150h+var_118], rax; phkResult
0x180012362  lea     rdx, [rbp+50h+Name]; lpSubKey
0x180012366  mov     [rsp+150h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18001236b  xor     r9d, r9d; lpClass
0x18001236e  mov     [rsp+150h+cchCount2], 20006h; samDesired
0x180012376  xor     r8d, r8d; Reserved
0x180012379  mov     rcx, rsi; hKey
0x18001237c  mov     dword ptr [rsp+150h+lpString2], r12d; dwOptions
0x180012381  call    cs:__imp_RegCreateKeyExW
0x180012387  test    eax, eax
0x180012389  jnz     loc_180012685
0x18001238f  mov     r12, cs:?g_pszCRCTempBuf@@3PEAGEA; ushort * g_pszCRCTempBuf
0x180012396  mov     rdx, r14; unsigned __int16 *
0x180012399  mov     rcx, r15; unsigned __int16 *
0x18001239c  mov     [rsp+150h+pszDest], r12
0x1800123a1  mov     [rsp+150h+var_100], 600h
0x1800123aa  call    ?FindSeparator@@YAGPEBG0@Z; FindSeparator(ushort const *,ushort const *)
0x1800123af  movzx   r13d, ax
0x1800123b3  xor     eax, eax
0x1800123b5  test    r13w, r13w
0x1800123b9  jnz     short loc_1800123E7
0x1800123bb  mov     rcx, cs:hWnd; hWnd
0x1800123c2  xor     r12d, r12d
0x1800123c5  mov     [rsp+150h+cchCount2], r12d; unsigned int
0x1800123ca  xor     r9d, r9d; unsigned __int16 *
0x1800123cd  xor     r8d, r8d; unsigned __int16 *
0x1800123d0  mov     dword ptr [rsp+150h+lpString2], 10h; unsigned int
0x1800123d8  mov     edx, 480h; uID
0x1800123dd  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800123e2  jmp     loc_180012685
0x1800123e7  mov     r9d, [rbp+50h+arg_20]
0x1800123ee  lea     r8, aLu; "%lu"
0x1800123f5  and     r9d, 0FFFFFFFDh
0x1800123f9  lea     rcx, [rbp+50h+Name]; unsigned __int16 *
0x1800123fd  or      r9d, 1
0x180012401  mov     edx, 20h ; ' '; unsigned __int64
0x180012406  mov     edi, eax
0x180012408  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001240d  xor     eax, eax
0x18001240f  mov     [rsp+150h+var_F0], r13w
0x180012415  mov     [rsp+150h+var_EE], ax
0x18001241a  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x18001241f  lea     rax, [rsp+150h+var_100]
0x180012424  mov     r13d, 200h
0x18001242a  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x18001242f  lea     r8, [rsp+150h+var_F0]; unsigned __int16 *
0x180012434  mov     edx, 600h; unsigned __int64
0x180012439  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x18001243e  mov     rcx, r12; pszDest
0x180012441  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180012446  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x18001244b  lea     rax, [rsp+150h+var_100]
0x180012450  mov     rcx, [rsp+150h+pszDest]; pszDest
0x180012455  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x18001245a  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x18001245f  lea     r8, [rbp+50h+Name]; unsigned __int16 *
0x180012463  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x180012468  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001246d  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x180012472  lea     rax, [rsp+150h+var_100]
0x180012477  mov     rcx, [rsp+150h+pszDest]; pszDest
0x18001247c  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x180012481  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x180012486  lea     r8, [rsp+150h+var_F0]; unsigned __int16 *
0x18001248b  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x180012490  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180012495  mov     r8, [rsp+150h+var_E0]; unsigned __int16 *
0x18001249a  lea     rax, [rsp+150h+var_100]
0x18001249f  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x1800124a4  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x1800124a9  mov     rcx, [rsp+150h+pszDest]; pszDest
0x1800124ae  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x1800124b3  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x1800124b8  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800124bd  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x1800124c2  lea     rax, [rsp+150h+var_100]
0x1800124c7  mov     rcx, [rsp+150h+pszDest]; pszDest
0x1800124cc  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x1800124d1  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x1800124d6  lea     r8, [rsp+150h+var_F0]; unsigned __int16 *
0x1800124db  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x1800124e0  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800124e5  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x1800124ea  lea     rax, [rsp+150h+var_100]
0x1800124ef  mov     rcx, [rsp+150h+pszDest]; pszDest
0x1800124f4  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x1800124f9  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x1800124fe  mov     r8, r15; unsigned __int16 *
0x180012501  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x180012506  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18001250b  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x180012510  lea     rax, [rsp+150h+var_100]
0x180012515  mov     rcx, [rsp+150h+pszDest]; pszDest
0x18001251a  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x18001251f  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x180012524  lea     r8, [rsp+150h+var_F0]; unsigned __int16 *
0x180012529  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x18001252e  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180012533  xor     r12d, r12d
0x180012536  test    r14, r14
0x180012539  jz      short loc_180012589
0x18001253b  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x180012540  lea     rax, [rsp+150h+var_100]
0x180012545  mov     rcx, [rsp+150h+pszDest]; pszDest
0x18001254a  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x18001254f  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x180012554  mov     r8, r14; unsigned __int16 *
0x180012557  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x18001255c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180012561  mov     rdx, [rsp+150h+var_100]; unsigned __int64
0x180012566  lea     rax, [rsp+150h+var_100]
0x18001256b  mov     rcx, [rsp+150h+pszDest]; pszDest
0x180012570  lea     r9, [rsp+150h+pszDest]; unsigned __int16 **
0x180012575  mov     [rsp+150h+cchCount2], r13d; unsigned int
0x18001257a  lea     r8, [rsp+150h+var_F0]; unsigned __int16 *
0x18001257f  mov     [rsp+150h+lpString2], rax; unsigned __int64 *
0x180012584  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180012589  mov     rcx, cs:?g_pszCRCTempBuf@@3PEAGEA; ushort * g_pszCRCTempBuf
0x180012590  or      r15, 0FFFFFFFFFFFFFFFFh
0x180012594  mov     rax, r15
0x180012597  inc     rax
0x18001259a  cmp     [rcx+rax*2], r12w
0x18001259f  jnz     short loc_180012597
0x1800125a1  lea     eax, ds:2[rax*2]
0x1800125a8  mov     r14d, 1
0x1800125ae  mov     [rsp+150h+cchCount2], eax; cbData
0x1800125b2  lea     rdx, [rbp+50h+ValueName]; lpValueName
0x1800125b6  mov     [rsp+150h+lpString2], rcx; lpData
0x1800125bb  mov     r9d, r14d; dwType
0x1800125be  mov     rcx, [rsp+150h+phkResult]; hKey
0x1800125c3  xor     r8d, r8d; Reserved
0x1800125c6  call    cs:__imp_RegSetValueExW
0x1800125cc  test    eax, eax
0x1800125ce  jz      loc_180012682
0x1800125d4  mov     rcx, [rsp+150h+phkResult]; hKey
0x1800125d9  call    cs:__imp_RegCloseKey
0x1800125df  add     edi, r14d
0x1800125e2  mov     [rsp+150h+phkResult], r12
0x1800125e7  mov     r9d, edi
0x1800125ea  lea     r8, aLuMap; "%lu.map"
0x1800125f1  mov     edx, 20h ; ' '; unsigned __int64
0x1800125f6  lea     rcx, [rbp+50h+Name]; unsigned __int16 *
0x1800125fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800125ff  mov     [rsp+150h+lpdwDisposition], r12; lpdwDisposition
0x180012604  lea     rax, [rsp+150h+phkResult]
0x180012609  mov     [rsp+150h+var_118], rax; phkResult
0x18001260e  lea     rdx, [rbp+50h+Name]; lpSubKey
0x180012612  mov     [rsp+150h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180012617  xor     r9d, r9d; lpClass
0x18001261a  mov     [rsp+150h+cchCount2], 20006h; samDesired
0x180012622  xor     r8d, r8d; Reserved
0x180012625  mov     rcx, rsi; hKey
0x180012628  mov     dword ptr [rsp+150h+lpString2], r12d; dwOptions
0x18001262d  call    cs:__imp_RegCreateKeyExW
0x180012633  test    eax, eax
0x180012635  jnz     short loc_180012677
0x180012637  mov     rcx, cs:?g_pszCRCTempBuf@@3PEAGEA; ushort * g_pszCRCTempBuf
0x18001263e  mov     rax, r15
0x180012641  inc     rax
0x180012644  cmp     [rcx+rax*2], r12w
0x180012649  jnz     short loc_180012641
0x18001264b  lea     eax, ds:2[rax*2]
0x180012652  mov     r9d, r14d; dwType
0x180012655  mov     [rsp+150h+cchCount2], eax; cbData
0x180012659  lea     rdx, [rbp+50h+ValueName]; lpValueName
0x18001265d  mov     [rsp+150h+lpString2], rcx; lpData
0x180012662  xor     r8d, r8d; Reserved
0x180012665  mov     rcx, [rsp+150h+phkResult]; hKey
0x18001266a  call    cs:__imp_RegSetValueExW
0x180012670  test    eax, eax
0x180012672  jz      short loc_180012682
0x180012674  mov     ebx, r12d
0x180012677  cmp     edi, 40h ; '@'
0x18001267a  jb      loc_1800125D4
0x180012680  jmp     short loc_180012685
0x180012682  mov     ebx, r14d
0x180012685  mov     rcx, [rsp+150h+phkResult]; hKey
0x18001268a  test    rcx, rcx
0x18001268d  jz      short loc_180012695
0x18001268f  call    cs:__imp_RegCloseKey
0x180012695  mov     eax, ebx
0x180012697  mov     rcx, [rbp+50h+var_50]
0x18001269b  xor     rcx, rsp; StackCookie
0x18001269e  call    __security_check_cookie
0x1800126a3  add     rsp, 118h
0x1800126aa  pop     r15
0x1800126ac  pop     r14
0x1800126ae  pop     r13
0x1800126b0  pop     r12
0x1800126b2  pop     rdi
0x1800126b3  pop     rsi
0x1800126b4  pop     rbx
0x1800126b5  pop     rbp
0x1800126b6  retn
```
