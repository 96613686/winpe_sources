# EnumerateSubKey(void)

- ea: `0x1800127bc`
- end: `0x180012cf5`
- name: `?EnumerateSubKey@@YAXXZ`
- size: `1337`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1800127bc`
- `0x180014440`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x1800035c8`
- `0x1800126c0`
- `0x1800127bc`
- `0x180013acc`
- `0x180013e60`
- `0x180013fa4`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180012cd2`
- `ADVAPI32!RegCloseKey` at `0x180012cd2`
- `ADVAPI32!RegOpenKeyExW` at `0x180012a47`
- `ADVAPI32!RegOpenKeyExW` at `0x180012a47`
- `ADVAPI32!RegEnumValueW` at `0x180012a8b`
- `ADVAPI32!RegEnumValueW` at `0x180012aed`
- `ADVAPI32!RegEnumValueW` at `0x180012b8e`
- `ADVAPI32!RegEnumValueW` at `0x180012a8b`
- `ADVAPI32!RegEnumValueW` at `0x180012aed`
- `ADVAPI32!RegEnumValueW` at `0x180012b8e`
- `ADVAPI32!RegEnumKeyW` at `0x180012caa`
- `ADVAPI32!RegEnumKeyW` at `0x180012caa`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012a07`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012a1c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012c47`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012c56`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012a07`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012a1c`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012c47`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180012c56`

## pseudocode

```c
void EnumerateSubKey(void)
{
  int v0; // eax
  unsigned int v1; // r15d
  int v2; // eax
  unsigned int i; // r14d
  const unsigned __int16 *v4; // r8
  unsigned __int16 **v5; // r9
  bool v6; // zf
  int v7; // eax
  DWORD v8; // r15d
  int v9; // eax
  __int64 v10; // rax
  int v11; // ebx
  DWORD v12; // esi
  DWORD j; // edx
  __int64 v14; // rax
  WCHAR *v15; // r10
  __int64 v16; // rax
  const unsigned __int16 *v17; // r8
  unsigned __int16 **v18; // r9
  __int64 v19; // rax
  unsigned __int64 *phkResult; // [rsp+20h] [rbp-58h]
  unsigned __int64 *phkResulta; // [rsp+20h] [rbp-58h]
  unsigned int lpType; // [rsp+28h] [rbp-50h]
  unsigned int lpTypea; // [rsp+28h] [rbp-50h]
  HKEY hKey; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 v25[12]; // [rsp+48h] [rbp-30h] BYREF

  hKey = 0;
  if ( g_fRestore )
  {
    Convert2CRC(g_pcszRootKey, g_pszCRCSubKey, 0, &qword_180032AD0, 0x104u);
    if ( (unsigned int)ValueDataHelper(g_hkBckupKey, &qword_180032AD0, 0, 0, 1u) )
    {
      if ( !(unsigned int)RegSaveRestoreHelperWrapper(0, 0) || (v0 = 1, !g_bRet) )
        v0 = 0;
      g_bRet = v0;
    }
    else
    {
      v1 = 0;
      StringCchPrintfW(v25, 0xCu, L"%lu", 0);
      while ( 1 )
      {
        StringCchCopyW(&word_180032CE0, 0x104u, L"_$Val#");
        StringCchCatW(&word_180032CE0, 0x104u, v25);
        Convert2CRC(g_pcszRootKey, g_pszCRCSubKey, &word_180032CE0, &qword_180032AD0, 0x104u);
        if ( !(unsigned int)ValueDataHelper(g_hkBckupKey, &qword_180032AD0, 0, 0, 1u) )
          break;
        if ( !(unsigned int)RegSaveRestoreHelperWrapper(0, &word_180032CE0) || (v2 = 1, !g_bRet) )
          v2 = 0;
        ++v1;
        g_bRet = v2;
        StringCchPrintfW(v25, 0xCu, L"%lu", v1);
      }
    }
    for ( i = 0; ; ++i )
    {
      StringCchPrintfW(v25, 0xCu, L"%lu", i);
      StringCchCatW(g_pszCRCSubKey, (unsigned int)g_cchCRCSubKey, L"\\");
      StringCchCatW(g_pszCRCSubKey, (unsigned int)g_cchCRCSubKey, L"_$Sub#");
      StringCchCatW(g_pszCRCSubKey, (unsigned int)g_cchCRCSubKey, v25);
      Convert2CRC(g_pcszRootKey, g_pszCRCSubKey, 0, &qword_180032AD0, 0x104u);
      if ( !(unsigned int)ValueDataHelper(g_hkBckupKey, &qword_180032AD0, 0, 0, 1u) )
      {
        Convert2CRC(g_pcszRootKey, g_pszCRCSubKey, L"_$Val#0", &qword_180032AD0, 0x104u);
        if ( !(unsigned int)ValueDataHelper(g_hkBckupKey, &qword_180032AD0, 0, 0, 1u) )
          break;
      }
      EnumerateSubKey();
      PathRemoveFileSpecW(g_pszCRCSubKey);
    }
    PathRemoveFileSpecW(g_pszCRCSubKey);
  }
  else if ( !RegOpenKeyExW(g_hkRootKey, g_pszSubKey, 0, 0x20019u, &hKey) )
  {
    cchValueName = 260;
    if ( RegEnumValueW(hKey, 0, &word_180032CE0, &cchValueName, 0, 0, 0, 0) )
    {
      if ( !g_bRet || (v6 = (unsigned int)RegSaveRestoreHelperWrapper(0, 0) == 0, v7 = 1, v6) )
        v7 = 0;
      g_bRet = v7;
    }
    else
    {
      v8 = 0;
      cchValueName = 260;
      if ( !RegEnumValueW(hKey, 0, &word_180032CE0, &cchValueName, 0, 0, 0, 0) )
      {
        do
        {
          StringCchPrintfW(v25, 0xCu, L"%lu", v8);
          StringCchCopyW(&qword_180032AD0, 0x104u, L"_$Val#");
          StringCchCatW(&qword_180032AD0, 0x104u, v25);
          if ( !g_bRet
            || (v6 = (unsigned int)RegSaveRestoreHelperWrapper(&word_180032CE0, &qword_180032AD0) == 0, v9 = 1, v6) )
          {
            v9 = 0;
          }
          ++v8;
          g_bRet = v9;
          cchValueName = 260;
        }
        while ( !RegEnumValueW(hKey, v8, &word_180032CE0, &cchValueName, 0, 0, 0, 0) );
      }
    }
    v10 = -1;
    do
      ++v10;
    while ( g_pszSubKey[v10] );
    v11 = g_cchCRCSubKey;
    cchValueName = v10;
    psz = (LPWSTR)&g_pszSubKey[(unsigned int)v10];
    if ( (unsigned int)g_cchCRCSubKey > (unsigned int)v10 )
    {
      v12 = 0;
      StringCchCatExW(
        (unsigned __int16 *)(unsigned int)v10,
        (unsigned int)(g_cchCRCSubKey - v10),
        v4,
        v5,
        phkResult,
        lpType);
      for ( j = 0; !RegEnumKeyW(hKey, j, psz, v11 - cchValueName - 1); j = v12 )
      {
        v14 = -1;
        do
          ++v14;
        while ( g_pszCRCSubKey[v14] );
        v15 = &g_pszCRCSubKey[v14];
        v16 = -1;
        psz = v15;
        do
          ++v16;
        while ( g_pszCRCSubKey[v16] );
        if ( (unsigned int)g_cchCRCSubKey > (unsigned int)v16 )
        {
          LODWORD(phkResulta) = v12;
          StringCchPrintfW(v15, (unsigned int)g_cchCRCSubKey - v16, L"\\%s%lu", L"_$Sub#");
          EnumerateSubKey();
          PathRemoveFileSpecW(g_pszCRCSubKey);
          ++v12;
        }
        PathRemoveFileSpecW((LPWSTR)g_pszSubKey);
        v19 = -1;
        do
          ++v19;
        while ( g_pszSubKey[v19] );
        v11 = g_cchCRCSubKey;
        cchValueName = v19;
        psz = (LPWSTR)&g_pszSubKey[(unsigned int)v19];
        StringCchCatExW(
          (unsigned __int16 *)(unsigned int)v19,
          (unsigned int)(g_cchCRCSubKey - v19),
          v17,
          v18,
          phkResulta,
          lpTypea);
      }
      *--psz = 0;
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x1800127bc  push    rbp
0x1800127be  push    rbx
0x1800127bf  push    rsi
0x1800127c0  push    rdi
0x1800127c1  push    r12
0x1800127c3  push    r13
0x1800127c5  push    r14
0x1800127c7  push    r15
0x1800127c9  mov     rbp, rsp
0x1800127cc  sub     rsp, 78h
0x1800127d0  mov     rax, cs:__security_cookie
0x1800127d7  xor     rax, rsp
0x1800127da  mov     [rbp+var_18], rax
0x1800127de  xor     r13d, r13d
0x1800127e1  cmp     cs:?g_fRestore@@3HA, r13d; int g_fRestore
0x1800127e8  mov     [rbp+hKey], r13
0x1800127ec  jz      loc_180012A27
0x1800127f2  mov     rdx, cs:?g_pszCRCSubKey@@3PEAGEA; unsigned __int16 *
0x1800127f9  lea     rsi, qword_180032AD0
0x180012800  mov     rcx, cs:?g_pcszRootKey@@3PEBGEB; unsigned __int16 *
0x180012807  mov     ebx, 104h
0x18001280c  mov     r9, rsi; unsigned __int16 *
0x18001280f  mov     dword ptr [rsp+78h+phkResult], ebx; unsigned int
0x180012813  xor     r8d, r8d; unsigned __int16 *
0x180012816  call    ?Convert2CRC@@YAXPEBG00PEAGK@Z; Convert2CRC(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x18001281b  mov     rcx, cs:?g_hkBckupKey@@3PEAUHKEY__@@EA; hKey
0x180012822  lea     edi, [r13+1]
0x180012826  xor     r9d, r9d; unsigned int *
0x180012829  mov     dword ptr [rsp+78h+phkResult], edi; unsigned int
0x18001282d  xor     r8d, r8d; unsigned __int8 **
0x180012830  mov     rdx, rsi; lpValueName
0x180012833  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x180012838  lea     r12d, [r13+0Ch]
0x18001283c  test    eax, eax
0x18001283e  jz      short loc_180012866
0x180012840  xor     edx, edx; unsigned __int16 *
0x180012842  xor     ecx, ecx; unsigned __int16 *
0x180012844  call    ?RegSaveRestoreHelperWrapper@@YAHPEBG0@Z; RegSaveRestoreHelperWrapper(ushort const *,ushort const *)
0x180012849  test    eax, eax
0x18001284b  jz      short loc_180012858
0x18001284d  cmp     cs:?g_bRet@@3HA, r13d; int g_bRet
0x180012854  mov     eax, edi
0x180012856  jnz     short loc_18001285B
0x180012858  mov     eax, r13d
0x18001285b  mov     cs:?g_bRet@@3HA, eax; int g_bRet
0x180012861  jmp     loc_180012922
0x180012866  xor     r9d, r9d
0x180012869  lea     r8, aLu; "%lu"
0x180012870  mov     rdx, r12; unsigned __int64
0x180012873  lea     rcx, [rbp+var_30]; unsigned __int16 *
0x180012877  mov     r15d, r13d
0x18001287a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001287f  lea     r14, word_180032CE0
0x180012886  jmp     short loc_1800128C3
0x180012888  mov     rdx, r14; unsigned __int16 *
0x18001288b  xor     ecx, ecx; unsigned __int16 *
0x18001288d  call    ?RegSaveRestoreHelperWrapper@@YAHPEBG0@Z; RegSaveRestoreHelperWrapper(ushort const *,ushort const *)
0x180012892  test    eax, eax
0x180012894  jz      short loc_1800128A1
0x180012896  cmp     cs:?g_bRet@@3HA, r13d; int g_bRet
0x18001289d  mov     eax, edi
0x18001289f  jnz     short loc_1800128A4
0x1800128a1  mov     eax, r13d
0x1800128a4  add     r15d, edi
0x1800128a7  mov     cs:?g_bRet@@3HA, eax; int g_bRet
0x1800128ad  mov     r9d, r15d
0x1800128b0  lea     r8, aLu; "%lu"
0x1800128b7  mov     rdx, r12; unsigned __int64
0x1800128ba  lea     rcx, [rbp+var_30]; unsigned __int16 *
0x1800128be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800128c3  lea     r8, aVal; "_$Val#"
0x1800128ca  mov     rdx, rbx; unsigned __int64
0x1800128cd  mov     rcx, r14; unsigned __int16 *
0x1800128d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800128d5  lea     r8, [rbp+var_30]; unsigned __int16 *
0x1800128d9  mov     rdx, rbx; unsigned __int64
0x1800128dc  mov     rcx, r14; unsigned __int16 *
0x1800128df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800128e4  mov     rdx, cs:?g_pszCRCSubKey@@3PEAGEA; unsigned __int16 *
0x1800128eb  mov     r9, rsi; unsigned __int16 *
0x1800128ee  mov     rcx, cs:?g_pcszRootKey@@3PEBGEB; unsigned __int16 *
0x1800128f5  mov     r8, r14; unsigned __int16 *
0x1800128f8  mov     dword ptr [rsp+78h+phkResult], ebx; unsigned int
0x1800128fc  call    ?Convert2CRC@@YAXPEBG00PEAGK@Z; Convert2CRC(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x180012901  mov     rcx, cs:?g_hkBckupKey@@3PEAUHKEY__@@EA; hKey
0x180012908  xor     r9d, r9d; unsigned int *
0x18001290b  xor     r8d, r8d; unsigned __int8 **
0x18001290e  mov     dword ptr [rsp+78h+phkResult], edi; unsigned int
0x180012912  mov     rdx, rsi; lpValueName
0x180012915  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x18001291a  test    eax, eax
0x18001291c  jnz     loc_180012888
0x180012922  mov     r14d, r13d
0x180012925  mov     r9d, r14d
0x180012928  lea     r8, aLu; "%lu"
0x18001292f  mov     rdx, r12; unsigned __int64
0x180012932  lea     rcx, [rbp+var_30]; unsigned __int16 *
0x180012936  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001293b  mov     edx, cs:?g_cchCRCSubKey@@3IA; unsigned __int64
0x180012941  lea     r8, SubBlock; "\\"
0x180012948  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; unsigned __int16 *
0x18001294f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012954  mov     edx, cs:?g_cchCRCSubKey@@3IA; unsigned __int64
0x18001295a  lea     r8, aSub; "_$Sub#"
0x180012961  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; unsigned __int16 *
0x180012968  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001296d  mov     edx, cs:?g_cchCRCSubKey@@3IA; unsigned __int64
0x180012973  lea     r8, [rbp+var_30]; unsigned __int16 *
0x180012977  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; unsigned __int16 *
0x18001297e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012983  mov     rdx, cs:?g_pszCRCSubKey@@3PEAGEA; unsigned __int16 *
0x18001298a  mov     r9, rsi; unsigned __int16 *
0x18001298d  mov     rcx, cs:?g_pcszRootKey@@3PEBGEB; unsigned __int16 *
0x180012994  xor     r8d, r8d; unsigned __int16 *
0x180012997  mov     dword ptr [rsp+78h+phkResult], ebx; unsigned int
0x18001299b  call    ?Convert2CRC@@YAXPEBG00PEAGK@Z; Convert2CRC(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x1800129a0  mov     rcx, cs:?g_hkBckupKey@@3PEAUHKEY__@@EA; hKey
0x1800129a7  xor     r9d, r9d; unsigned int *
0x1800129aa  xor     r8d, r8d; unsigned __int8 **
0x1800129ad  mov     dword ptr [rsp+78h+phkResult], edi; unsigned int
0x1800129b1  mov     rdx, rsi; lpValueName
0x1800129b4  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x1800129b9  test    eax, eax
0x1800129bb  jnz     short loc_1800129FB
0x1800129bd  mov     rdx, cs:?g_pszCRCSubKey@@3PEAGEA; unsigned __int16 *
0x1800129c4  lea     r8, aVal0; "_$Val#0"
0x1800129cb  mov     rcx, cs:?g_pcszRootKey@@3PEBGEB; unsigned __int16 *
0x1800129d2  mov     r9, rsi; unsigned __int16 *
0x1800129d5  mov     dword ptr [rsp+78h+phkResult], ebx; unsigned int
0x1800129d9  call    ?Convert2CRC@@YAXPEBG00PEAGK@Z; Convert2CRC(ushort const *,ushort const *,ushort const *,ushort *,ulong)
0x1800129de  mov     rcx, cs:?g_hkBckupKey@@3PEAUHKEY__@@EA; hKey
0x1800129e5  xor     r9d, r9d; unsigned int *
0x1800129e8  xor     r8d, r8d; unsigned __int8 **
0x1800129eb  mov     dword ptr [rsp+78h+phkResult], edi; unsigned int
0x1800129ef  mov     rdx, rsi; lpValueName
0x1800129f2  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x1800129f7  test    eax, eax
0x1800129f9  jz      short loc_180012A15
0x1800129fb  call    ?EnumerateSubKey@@YAXXZ; EnumerateSubKey(void)
0x180012a00  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; pszPath
0x180012a07  call    cs:__imp_PathRemoveFileSpecW
0x180012a0d  add     r14d, edi
0x180012a10  jmp     loc_180012925
0x180012a15  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; pszPath
0x180012a1c  call    cs:__imp_PathRemoveFileSpecW
0x180012a22  jmp     loc_180012CD8
0x180012a27  mov     rdx, cs:?g_pszSubKey@@3PEAGEA; lpSubKey
0x180012a2e  lea     rax, [rbp+hKey]
0x180012a32  mov     rcx, cs:?g_hkRootKey@@3PEAUHKEY__@@EA; hKey
0x180012a39  mov     r9d, 20019h; samDesired
0x180012a3f  xor     r8d, r8d; ulOptions
0x180012a42  mov     [rsp+78h+phkResult], rax; phkResult
0x180012a47  call    cs:__imp_RegOpenKeyExW
0x180012a4d  test    eax, eax
0x180012a4f  jnz     loc_180012CD8
0x180012a55  mov     rcx, [rbp+hKey]; hKey
0x180012a59  lea     r14, word_180032CE0
0x180012a60  mov     [rsp+78h+lpcbData], r13; lpcbData
0x180012a65  lea     r9, cchValueName; lpcchValueName
0x180012a6c  mov     [rsp+78h+lpData], r13; lpData
0x180012a71  mov     ebx, 104h
0x180012a76  mov     [rsp+78h+lpType], r13; lpType
0x180012a7b  mov     r8, r14; lpValueName
0x180012a7e  xor     edx, edx; dwIndex
0x180012a80  mov     [rsp+78h+phkResult], r13; lpReserved
0x180012a85  mov     cs:cchValueName, ebx
0x180012a8b  call    cs:__imp_RegEnumValueW
0x180012a91  mov     edi, 1
0x180012a96  test    eax, eax
0x180012a98  jz      short loc_180012AC0
0x180012a9a  cmp     cs:?g_bRet@@3HA, r13d; int g_bRet
0x180012aa1  jz      short loc_180012AB2
0x180012aa3  xor     edx, edx; unsigned __int16 *
0x180012aa5  xor     ecx, ecx; unsigned __int16 *
0x180012aa7  call    ?RegSaveRestoreHelperWrapper@@YAHPEBG0@Z; RegSaveRestoreHelperWrapper(ushort const *,ushort const *)
0x180012aac  test    eax, eax
0x180012aae  mov     eax, edi
0x180012ab0  jnz     short loc_180012AB5
0x180012ab2  mov     eax, r13d
0x180012ab5  mov     cs:?g_bRet@@3HA, eax; int g_bRet
0x180012abb  jmp     loc_180012B9C
0x180012ac0  mov     rcx, [rbp+hKey]; hKey
0x180012ac4  lea     r9, cchValueName; lpcchValueName
0x180012acb  mov     [rsp+78h+lpcbData], r13; lpcbData
0x180012ad0  mov     r8, r14; lpValueName
0x180012ad3  mov     [rsp+78h+lpData], r13; lpData
0x180012ad8  xor     edx, edx; dwIndex
0x180012ada  mov     [rsp+78h+lpType], r13; lpType
0x180012adf  mov     r15d, r13d
0x180012ae2  mov     [rsp+78h+phkResult], r13; lpReserved
0x180012ae7  mov     cs:cchValueName, ebx
0x180012aed  call    cs:__imp_RegEnumValueW
0x180012af3  test    eax, eax
0x180012af5  jnz     loc_180012B9C
0x180012afb  lea     rsi, qword_180032AD0
0x180012b02  lea     r12d, [rax+0Ch]
0x180012b06  mov     r9d, r15d
0x180012b09  lea     r8, aLu; "%lu"
0x180012b10  mov     rdx, r12; unsigned __int64
0x180012b13  lea     rcx, [rbp+var_30]; unsigned __int16 *
0x180012b17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012b1c  lea     r8, aVal; "_$Val#"
0x180012b23  mov     rdx, rbx; unsigned __int64
0x180012b26  mov     rcx, rsi; unsigned __int16 *
0x180012b29  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012b2e  lea     r8, [rbp+var_30]; unsigned __int16 *
0x180012b32  mov     rdx, rbx; unsigned __int64
0x180012b35  mov     rcx, rsi; unsigned __int16 *
0x180012b38  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012b3d  cmp     cs:?g_bRet@@3HA, r13d; int g_bRet
0x180012b44  jz      short loc_180012B57
0x180012b46  mov     rdx, rsi; unsigned __int16 *
0x180012b49  mov     rcx, r14; unsigned __int16 *
0x180012b4c  call    ?RegSaveRestoreHelperWrapper@@YAHPEBG0@Z; RegSaveRestoreHelperWrapper(ushort const *,ushort const *)
0x180012b51  test    eax, eax
0x180012b53  mov     eax, edi
0x180012b55  jnz     short loc_180012B5A
0x180012b57  mov     eax, r13d
0x180012b5a  mov     rcx, [rbp+hKey]; hKey
0x180012b5e  lea     r9, cchValueName; lpcchValueName
0x180012b65  mov     [rsp+78h+lpcbData], r13; lpcbData
0x180012b6a  add     r15d, edi
0x180012b6d  mov     [rsp+78h+lpData], r13; lpData
0x180012b72  mov     edx, r15d; dwIndex
0x180012b75  mov     [rsp+78h+lpType], r13; unsigned int
0x180012b7a  mov     r8, r14; lpValueName
0x180012b7d  mov     [rsp+78h+phkResult], r13; unsigned __int64 *
0x180012b82  mov     cs:?g_bRet@@3HA, eax; int g_bRet
0x180012b88  mov     cs:cchValueName, ebx
0x180012b8e  call    cs:__imp_RegEnumValueW
0x180012b94  test    eax, eax
0x180012b96  jz      loc_180012B06
0x180012b9c  mov     rdx, cs:?g_pszSubKey@@3PEAGEA; ushort * g_pszSubKey
0x180012ba3  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012ba7  mov     rax, r14
0x180012baa  inc     rax
0x180012bad  cmp     [rdx+rax*2], r13w
0x180012bb2  jnz     short loc_180012BAA
0x180012bb4  mov     ebx, cs:?g_cchCRCSubKey@@3IA; uint g_cchCRCSubKey
0x180012bba  mov     ecx, eax; unsigned __int16 *
0x180012bbc  mov     cs:cchValueName, ecx
0x180012bc2  lea     rax, [rdx+rcx*2]
0x180012bc6  mov     cs:psz, rax
0x180012bcd  cmp     ebx, ecx
0x180012bcf  jbe     loc_180012CCE
0x180012bd5  mov     edx, ebx
0x180012bd7  mov     esi, r13d
0x180012bda  sub     edx, ecx; unsigned __int64
0x180012bdc  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180012be1  xor     edx, edx
0x180012be3  jmp     loc_180012C94
0x180012be8  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; ushort * g_pszCRCSubKey
0x180012bef  mov     rax, r14
0x180012bf2  inc     rax
0x180012bf5  cmp     [rcx+rax*2], r13w
0x180012bfa  jnz     short loc_180012BF2
0x180012bfc  lea     r10, [rcx+rax*2]
0x180012c00  mov     rax, r14
0x180012c03  mov     cs:psz, r10
0x180012c0a  inc     rax
0x180012c0d  cmp     [rcx+rax*2], r13w
0x180012c12  jnz     short loc_180012C0A
0x180012c14  mov     edx, cs:?g_cchCRCSubKey@@3IA; uint g_cchCRCSubKey
0x180012c1a  cmp     edx, eax
0x180012c1c  jbe     short loc_180012C4F
0x180012c1e  sub     rdx, rax; unsigned __int64
0x180012c21  mov     dword ptr [rsp+78h+phkResult], esi; unsigned __int64 *
0x180012c25  lea     r9, aSub; "_$Sub#"
0x180012c2c  mov     rcx, r10; unsigned __int16 *
0x180012c2f  lea     r8, aSLu; "\\%s%lu"
0x180012c36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012c3b  call    ?EnumerateSubKey@@YAXXZ; EnumerateSubKey(void)
0x180012c40  mov     rcx, cs:?g_pszCRCSubKey@@3PEAGEA; pszPath
0x180012c47  call    cs:__imp_PathRemoveFileSpecW
0x180012c4d  add     esi, edi
0x180012c4f  mov     rcx, cs:?g_pszSubKey@@3PEAGEA; pszPath
0x180012c56  call    cs:__imp_PathRemoveFileSpecW
0x180012c5c  mov     rdx, cs:?g_pszSubKey@@3PEAGEA; ushort * g_pszSubKey
0x180012c63  mov     rax, r14
0x180012c66  inc     rax
0x180012c69  cmp     [rdx+rax*2], r13w
0x180012c6e  jnz     short loc_180012C66
0x180012c70  mov     ebx, cs:?g_cchCRCSubKey@@3IA; uint g_cchCRCSubKey
0x180012c76  mov     ecx, eax; unsigned __int16 *
0x180012c78  mov     cs:cchValueName, ecx
0x180012c7e  lea     rax, [rdx+rcx*2]
0x180012c82  mov     edx, ebx
0x180012c84  sub     edx, ecx; unsigned __int64
0x180012c86  mov     cs:psz, rax
0x180012c8d  call    ?StringCchCatExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCatExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180012c92  mov     edx, esi; dwIndex
0x180012c94  sub     ebx, cs:cchValueName
0x180012c9a  mov     r8, cs:psz; lpName
0x180012ca1  sub     ebx, edi
0x180012ca3  mov     rcx, [rbp+hKey]; hKey
0x180012ca7  mov     r9d, ebx; cchName
0x180012caa  call    cs:__imp_RegEnumKeyW
0x180012cb0  test    eax, eax
0x180012cb2  jz      loc_180012BE8
0x180012cb8  mov     rcx, cs:psz
  ... truncated ...
```
