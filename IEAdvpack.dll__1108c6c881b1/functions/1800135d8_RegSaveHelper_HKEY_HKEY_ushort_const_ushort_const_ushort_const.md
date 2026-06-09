# RegSaveHelper(HKEY__ *,HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800135d8`
- end: `0x180013ac3`
- name: `?RegSaveHelper@@YAHPEAUHKEY__@@0PEBG11@Z`
- size: `1259`
- prototype: `__int64 __fastcall(HKEY, HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180013acc`

## callees

- `0x1800022bc`
- `0x180003218`
- `0x180008a6c`
- `0x180012cfc`
- `0x1800135d8`
- `0x180013b88`
- `0x180013fa4`
- `0x180014148`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180013a4d`
- `KERNEL32!LocalFree` at `0x180013a5b`
- `KERNEL32!LocalFree` at `0x180013a8f`
- `KERNEL32!LocalFree` at `0x180013a98`
- `KERNEL32!LocalFree` at `0x180013a4d`
- `KERNEL32!LocalFree` at `0x180013a5b`
- `KERNEL32!LocalFree` at `0x180013a8f`
- `KERNEL32!LocalFree` at `0x180013a98`
- `KERNEL32!LocalAlloc` at `0x18001367e`
- `KERNEL32!LocalAlloc` at `0x180013885`
- `KERNEL32!LocalAlloc` at `0x18001367e`
- `KERNEL32!LocalAlloc` at `0x180013885`
- `KERNEL32!CompareStringW` at `0x1800137a1`
- `KERNEL32!CompareStringW` at `0x1800137a1`
- `KERNEL32!GetVersionExW` at `0x1800137f0`
- `KERNEL32!GetVersionExW` at `0x1800137f0`
- `ADVAPI32!RegQueryValueExW` at `0x180013833`
- `ADVAPI32!RegQueryValueExW` at `0x180013868`
- `ADVAPI32!RegQueryValueExW` at `0x1800139ee`
- `ADVAPI32!RegQueryValueExW` at `0x180013833`
- `ADVAPI32!RegQueryValueExW` at `0x180013868`
- `ADVAPI32!RegQueryValueExW` at `0x1800139ee`
- `ADVAPI32!RegCloseKey` at `0x180013a3f`
- `ADVAPI32!RegCloseKey` at `0x180013a86`
- `ADVAPI32!RegCloseKey` at `0x180013a3f`
- `ADVAPI32!RegCloseKey` at `0x180013a86`
- `ADVAPI32!RegOpenKeyExW` at `0x1800136c8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800136c8`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800136d9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800136d9`

## pseudocode

```c
__int64 __fastcall RegSaveHelper(
        HKEY a1,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  const unsigned __int16 *v6; // r12
  HKEY v7; // r13
  __int64 v9; // r15
  HLOCAL v10; // r14
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int16 *v13; // rax
  WCHAR *v14; // rdi
  UINT v15; // edx
  const unsigned __int16 *v16; // r8
  BOOL v17; // esi
  unsigned int v18; // r12d
  __int64 v19; // r12
  unsigned __int16 Separator; // r13
  int v21; // eax
  unsigned __int64 v22; // rax
  STRSAFE_LPWSTR v23; // rdx
  LPCWSTR v24; // rbx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[2]; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v27; // [rsp+36h] [rbp-CAh]
  STRSAFE_LPWSTR pszDest; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpValueName; // [rsp+58h] [rbp-A8h]
  HKEY v33; // [rsp+60h] [rbp-A0h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF

  v6 = g_pszSubKey;
  v7 = g_hkRootKey;
  lpValueName = a5;
  v33 = g_hkBckupKey;
  hKey = 0;
  cbData = 0;
  Type = 0;
  if ( (unsigned int)ValueDataHelper(g_hkBckupKey, a5, 0, 0, 1u) )
    return 1;
  v9 = -1;
  v10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( v6[v11] );
  v12 = (unsigned int)(v11 + 1);
  v13 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v12);
  v14 = v13;
  if ( !v13 )
    goto LABEL_6;
  StringCchCopyW(v13, v12, v6);
  v17 = 1;
  while ( RegOpenKeyExW(v7, v14, 0, 0x20019u, &hKey) )
  {
    v17 = PathRemoveFileSpecW(v14);
    if ( !v17 )
      goto LABEL_10;
  }
  if ( CompareStringW(0x7Fu, 1u, v6, -1, v14, -1) != 2 )
  {
LABEL_10:
    a4 = 0;
    goto LABEL_11;
  }
  if ( a4 )
  {
    if ( *a4 )
      goto LABEL_53;
    v21 = dword_1800251A0;
    if ( dword_1800251A0 == 2 )
    {
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
      VersionInformation.dwOSVersionInfoSize = 276;
      GetVersionExW(&VersionInformation);
      v21 = VersionInformation.dwPlatformId == 2;
      dword_1800251A0 = v21;
    }
    if ( v21 )
    {
LABEL_53:
      if ( RegQueryValueExW(hKey, a4, 0, &Type, 0, &cbData) )
        a4 = 0;
    }
    else
    {
      cbData = 0;
      if ( (RegQueryValueExW(hKey, a4, 0, &Type, Data, &cbData) & 0xFFFFFFFD) == 0 )
        goto LABEL_10;
    }
  }
LABEL_11:
  WriteToLog(L"BckupSubKey = ");
  v18 = 2;
  if ( v17 )
  {
    WriteToLog(L"%1", v14);
    v19 = -1;
    do
      ++v19;
    while ( v14[v19] );
    v18 = v19 + 3;
    if ( a4 )
    {
      WriteToLog(L", BckupValueName = %1", a4);
      do
        ++v9;
      while ( a4[v9] );
      v18 += v9 + (cbData >> 1) + 6;
    }
  }
  WriteToLog(L"\r\n");
  Separator = FindSeparator((const unsigned __int16 *)((unsigned __int64)v14 & -(__int64)v17), a4);
  if ( !Separator )
  {
    v16 = 0;
    v15 = 1152;
    goto LABEL_41;
  }
  v10 = LocalAlloc(0x40u, 2LL * v18);
  if ( !v10 )
  {
LABEL_6:
    v15 = 1102;
    v16 = 0;
LABEL_41:
    MsgBox2Param(hWnd, v15, v16, 0, 0x10u, 0);
    if ( hKey )
      RegCloseKey(hKey);
    if ( v14 )
      LocalFree(v14);
    if ( v10 )
      LocalFree(v10);
    return 0;
  }
  *(_WORD *)Data = Separator;
  v27 = 0;
  pszDest = (STRSAFE_LPWSTR)v10;
  v29 = v18;
  StringCchCopyExW((STRSAFE_LPWSTR)v10, v18, (const unsigned __int16 *)Data, &pszDest, &v29, 0x200u);
  if ( v17 )
  {
    StringCchCopyExW(pszDest, v29, v14, &pszDest, &v29, 0x200u);
    StringCchCopyExW(pszDest, v29, (const unsigned __int16 *)Data, &pszDest, &v29, 0x200u);
    if ( a4 )
    {
      StringCchCopyExW(pszDest, v29, a4, &pszDest, &v29, 0x200u);
      StringCchCopyExW(pszDest, v29, (const unsigned __int16 *)Data, &pszDest, &v29, 0x200u);
      v22 = cbData + 2LL;
      v23 = pszDest;
      if ( v22 < 4 )
        v22 = 4;
      v16 = 0;
      if ( 2 * v29 - 2 < v22 + 2 )
      {
        v15 = 1169;
        goto LABEL_41;
      }
      *(_DWORD *)(pszDest + 1) = Type;
      *((_DWORD *)v23 + 1) = cbData;
      RegQueryValueExW(hKey, a4, 0, &Type, (LPBYTE)v23 + 6, &cbData);
    }
  }
  v24 = lpValueName;
  if ( !(unsigned int)SetValueData(v33, lpValueName, (BYTE *)v10, 2 * v18) )
  {
    v16 = v24;
    v15 = 1153;
    goto LABEL_41;
  }
  WriteToLog(L"Value backed-up\r\n");
  g_fAtleastOneRegSaved = 1;
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v14);
  LocalFree(v10);
  return 1;
}

```

## disassembly

```asm
0x1800135d8  push    rbp
0x1800135da  push    rbx
0x1800135db  push    rsi
0x1800135dc  push    rdi
0x1800135dd  push    r12
0x1800135df  push    r13
0x1800135e1  push    r14
0x1800135e3  push    r15
0x1800135e5  lea     rbp, [rsp-0A8h]
0x1800135ed  sub     rsp, 1A8h
0x1800135f4  mov     rax, cs:__security_cookie
0x1800135fb  xor     rax, rsp
0x1800135fe  mov     [rbp+0E0h+var_50], rax
0x180013605  mov     rax, [rbp+0E0h+arg_20]
0x18001360c  xor     edi, edi
0x18001360e  mov     rcx, cs:?g_hkBckupKey@@3PEAUHKEY__@@EA; hKey
0x180013615  mov     rbx, r9
0x180013618  mov     r12, cs:?g_pszSubKey@@3PEAGEA; ushort * g_pszSubKey
0x18001361f  xor     r9d, r9d; unsigned int *
0x180013622  mov     r13, cs:?g_hkRootKey@@3PEAUHKEY__@@EA; HKEY__ * g_hkRootKey
0x180013629  xor     r8d, r8d; unsigned __int8 **
0x18001362c  lea     esi, [rdi+1]
0x18001362f  mov     [rsp+1E0h+lpValueName], rax
0x180013634  mov     rdx, rax; lpValueName
0x180013637  mov     dword ptr [rsp+1E0h+phkResult], esi; unsigned int
0x18001363b  mov     [rsp+1E0h+var_180], rcx
0x180013640  mov     [rsp+1E0h+hKey], rdi
0x180013645  mov     [rsp+1E0h+cbData], edi
0x180013649  mov     [rsp+1E0h+Type], edi
0x18001364d  call    ?ValueDataHelper@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAKK@Z; ValueDataHelper(HKEY__ *,ushort const *,uchar * *,ulong *,ulong)
0x180013652  test    eax, eax
0x180013654  jz      short loc_18001365D
0x180013656  mov     eax, esi
0x180013658  jmp     loc_180013AA0
0x18001365d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180013661  mov     r14, rdi
0x180013664  mov     rax, r15
0x180013667  inc     rax
0x18001366a  cmp     [r12+rax*2], di
0x18001366f  jnz     short loc_180013667
0x180013671  inc     eax
0x180013673  mov     ecx, 40h ; '@'; uFlags
0x180013678  mov     esi, eax
0x18001367a  lea     rdx, [rax+rax]; uBytes
0x18001367e  call    cs:__imp_LocalAlloc
0x180013684  mov     rdi, rax
0x180013687  test    rax, rax
0x18001368a  jnz     short loc_18001369C
0x18001368c  xor     r15d, r15d
0x18001368f  mov     edx, 44Eh
0x180013694  xor     r8d, r8d
0x180013697  jmp     loc_180013A19
0x18001369c  mov     r8, r12; unsigned __int16 *
0x18001369f  mov     rdx, rsi; unsigned __int64
0x1800136a2  mov     rcx, rdi; unsigned __int16 *
0x1800136a5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800136aa  mov     esi, 1
0x1800136af  lea     rax, [rsp+1E0h+hKey]
0x1800136b4  mov     r9d, 20019h; samDesired
0x1800136ba  xor     r8d, r8d; ulOptions
0x1800136bd  mov     [rsp+1E0h+phkResult], rax; phkResult
0x1800136c2  mov     rdx, rdi; lpSubKey
0x1800136c5  mov     rcx, r13; hKey
0x1800136c8  call    cs:__imp_RegOpenKeyExW
0x1800136ce  test    eax, eax
0x1800136d0  jz      loc_180013789
0x1800136d6  mov     rcx, rdi; pszPath
0x1800136d9  call    cs:__imp_PathRemoveFileSpecW
0x1800136df  mov     esi, eax
0x1800136e1  test    eax, eax
0x1800136e3  jnz     short loc_1800136AF
0x1800136e5  xor     r13d, r13d
0x1800136e8  mov     rbx, r13
0x1800136eb  lea     rcx, aBckupsubkey; "BckupSubKey = "
0x1800136f2  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x1800136f7  mov     r12d, 2
0x1800136fd  test    esi, esi
0x1800136ff  jz      short loc_18001374E
0x180013701  mov     rdx, rdi
0x180013704  lea     rcx, a1_0; "%1"
0x18001370b  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x180013710  mov     r12, r15
0x180013713  inc     r12
0x180013716  cmp     [rdi+r12*2], r13w
0x18001371b  jnz     short loc_180013713
0x18001371d  add     r12d, 3
0x180013721  test    rbx, rbx
0x180013724  jz      short loc_18001374E
0x180013726  mov     rdx, rbx
0x180013729  lea     rcx, aBckupvaluename; ", BckupValueName = %1"
0x180013730  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x180013735  inc     r15
0x180013738  cmp     [rbx+r15*2], r13w
0x18001373d  jnz     short loc_180013735
0x18001373f  mov     eax, [rsp+1E0h+cbData]
0x180013743  shr     eax, 1
0x180013745  add     eax, 6
0x180013748  add     r12d, eax
0x18001374b  add     r12d, r15d
0x18001374e  lea     rcx, asc_18002076C; "\r\n"
0x180013755  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x18001375a  mov     eax, esi
0x18001375c  mov     rdx, rbx; unsigned __int16 *
0x18001375f  neg     eax
0x180013761  sbb     rcx, rcx
0x180013764  and     rcx, rdi; unsigned __int16 *
0x180013767  call    ?FindSeparator@@YAGPEBG0@Z; FindSeparator(ushort const *,ushort const *)
0x18001376c  xor     r15d, r15d
0x18001376f  movzx   r13d, ax
0x180013773  test    ax, ax
0x180013776  jnz     loc_180013879
0x18001377c  xor     r8d, r8d
0x18001377f  mov     edx, 480h
0x180013784  jmp     loc_180013A19
0x180013789  mov     edx, 1; dwCmpFlags
0x18001378e  mov     [rsp+1E0h+cchCount2], r15d; cchCount2
0x180013793  mov     r9d, r15d; cchCount1
0x180013796  mov     [rsp+1E0h+phkResult], rdi; lpString2
0x18001379b  mov     r8, r12; lpString1
0x18001379e  lea     ecx, [rdx+7Eh]; Locale
0x1800137a1  call    cs:__imp_CompareStringW
0x1800137a7  cmp     eax, 2
0x1800137aa  jnz     loc_1800136E5
0x1800137b0  xor     r13d, r13d
0x1800137b3  test    rbx, rbx
0x1800137b6  jz      loc_1800136EB
0x1800137bc  cmp     [rbx], r13w
0x1800137c0  jnz     loc_180013849
0x1800137c6  mov     eax, cs:dword_1800251A0
0x1800137cc  cmp     eax, 2
0x1800137cf  jnz     short loc_180013806
0x1800137d1  xor     edx, edx; Val
0x1800137d3  lea     rcx, [rsp+1E0h+VersionInformation.dwMajorVersion]; void *
0x1800137d8  mov     r8d, 110h; Size
0x1800137de  call    memset_0
0x1800137e3  lea     rcx, [rsp+1E0h+VersionInformation]; lpVersionInformation
0x1800137e8  mov     [rsp+1E0h+VersionInformation.dwOSVersionInfoSize], 114h
0x1800137f0  call    cs:__imp_GetVersionExW
0x1800137f6  cmp     [rbp+0E0h+VersionInformation.dwPlatformId], 2
0x1800137fa  mov     eax, r13d
0x1800137fd  setz    al
0x180013800  mov     cs:dword_1800251A0, eax
0x180013806  test    eax, eax
0x180013808  jnz     short loc_180013849
0x18001380a  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001380f  lea     rax, [rsp+1E0h+cbData]
0x180013814  mov     qword ptr [rsp+1E0h+cchCount2], rax; lpcbData
0x180013819  lea     r9, [rsp+1E0h+Type]; lpType
0x18001381e  lea     rax, [rsp+1E0h+Data]
0x180013823  mov     [rsp+1E0h+cbData], r13d
0x180013828  xor     r8d, r8d; lpReserved
0x18001382b  mov     [rsp+1E0h+phkResult], rax; lpData
0x180013830  mov     rdx, rbx; lpValueName
0x180013833  call    cs:__imp_RegQueryValueExW
0x180013839  test    eax, 0FFFFFFFDh
0x18001383e  jnz     loc_1800136EB
0x180013844  jmp     loc_1800136E8
0x180013849  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18001384e  lea     rax, [rsp+1E0h+cbData]
0x180013853  mov     qword ptr [rsp+1E0h+cchCount2], rax; lpcbData
0x180013858  lea     r9, [rsp+1E0h+Type]; lpType
0x18001385d  xor     r8d, r8d; lpReserved
0x180013860  mov     [rsp+1E0h+phkResult], r13; lpData
0x180013865  mov     rdx, rbx; lpValueName
0x180013868  call    cs:__imp_RegQueryValueExW
0x18001386e  test    eax, eax
0x180013870  cmovnz  rbx, r13
0x180013874  jmp     loc_1800136EB
0x180013879  mov     r15d, r12d
0x18001387c  mov     ecx, 40h ; '@'; uFlags
0x180013881  lea     rdx, [r15+r15]; uBytes
0x180013885  call    cs:__imp_LocalAlloc
0x18001388b  mov     r14, rax
0x18001388e  xor     eax, eax
0x180013890  test    r14, r14
0x180013893  jz      loc_18001368C
0x180013899  mov     word ptr [rsp+1E0h+Data], r13w
0x18001389f  lea     r9, [rsp+1E0h+pszDest]; unsigned __int16 **
0x1800138a4  mov     [rsp+1E0h+var_1AA], ax
0x1800138a9  lea     r8, [rsp+1E0h+Data]; unsigned __int16 *
0x1800138ae  lea     rax, [rsp+1E0h+var_1A0]
0x1800138b3  mov     [rsp+1E0h+pszDest], r14
0x1800138b8  mov     r13d, 200h
0x1800138be  mov     [rsp+1E0h+var_1A0], r15
0x1800138c3  mov     [rsp+1E0h+cchCount2], r13d; unsigned int
0x1800138c8  mov     edx, r15d; unsigned __int64
0x1800138cb  mov     rcx, r14; pszDest
0x1800138ce  mov     [rsp+1E0h+phkResult], rax; unsigned __int64 *
0x1800138d3  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800138d8  xor     r15d, r15d
0x1800138db  test    esi, esi
0x1800138dd  jz      loc_1800139F4
0x1800138e3  mov     rdx, [rsp+1E0h+var_1A0]; unsigned __int64
0x1800138e8  lea     rax, [rsp+1E0h+var_1A0]
0x1800138ed  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x1800138f2  lea     r9, [rsp+1E0h+pszDest]; unsigned __int16 **
0x1800138f7  mov     [rsp+1E0h+cchCount2], r13d; unsigned int
0x1800138fc  mov     r8, rdi; unsigned __int16 *
0x1800138ff  mov     [rsp+1E0h+phkResult], rax; unsigned __int64 *
0x180013904  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180013909  mov     rdx, [rsp+1E0h+var_1A0]; unsigned __int64
0x18001390e  lea     rax, [rsp+1E0h+var_1A0]
0x180013913  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x180013918  lea     r9, [rsp+1E0h+pszDest]; unsigned __int16 **
0x18001391d  mov     [rsp+1E0h+cchCount2], r13d; unsigned int
0x180013922  lea     r8, [rsp+1E0h+Data]; unsigned __int16 *
0x180013927  mov     [rsp+1E0h+phkResult], rax; unsigned __int64 *
0x18001392c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180013931  test    rbx, rbx
0x180013934  jz      loc_1800139F4
0x18001393a  mov     rdx, [rsp+1E0h+var_1A0]; unsigned __int64
0x18001393f  lea     rax, [rsp+1E0h+var_1A0]
0x180013944  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x180013949  lea     r9, [rsp+1E0h+pszDest]; unsigned __int16 **
0x18001394e  mov     [rsp+1E0h+cchCount2], r13d; unsigned int
0x180013953  mov     r8, rbx; unsigned __int16 *
0x180013956  mov     [rsp+1E0h+phkResult], rax; unsigned __int64 *
0x18001395b  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180013960  mov     rdx, [rsp+1E0h+var_1A0]; unsigned __int64
0x180013965  lea     rax, [rsp+1E0h+var_1A0]
0x18001396a  mov     rcx, [rsp+1E0h+pszDest]; pszDest
0x18001396f  lea     r9, [rsp+1E0h+pszDest]; unsigned __int16 **
0x180013974  mov     [rsp+1E0h+cchCount2], r13d; unsigned int
0x180013979  lea     r8, [rsp+1E0h+Data]; unsigned __int16 *
0x18001397e  mov     [rsp+1E0h+phkResult], rax; unsigned __int64 *
0x180013983  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180013988  mov     eax, [rsp+1E0h+cbData]
0x18001398c  lea     r8d, [r15+4]
0x180013990  mov     rcx, [rsp+1E0h+var_1A0]
0x180013995  add     rax, 2
0x180013999  mov     rdx, [rsp+1E0h+pszDest]
0x18001399e  cmp     rax, r8
0x1800139a1  cmovb   rax, r8
0x1800139a5  xor     r8d, r8d; lpReserved
0x1800139a8  add     rax, 2
0x1800139ac  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x1800139b4  cmp     rcx, rax
0x1800139b7  jnb     short loc_1800139C0
0x1800139b9  mov     edx, 491h
0x1800139be  jmp     short loc_180013A19
0x1800139c0  mov     eax, [rsp+1E0h+Type]
0x1800139c4  lea     r9, [rsp+1E0h+Type]; lpType
0x1800139c9  mov     [rdx+2], eax
0x1800139cc  mov     eax, [rsp+1E0h+cbData]
0x1800139d0  mov     [rdx+4], eax
0x1800139d3  lea     rax, [rdx+6]
0x1800139d7  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800139dc  lea     rdx, [rsp+1E0h+cbData]
0x1800139e1  mov     qword ptr [rsp+1E0h+cchCount2], rdx; lpcbData
0x1800139e6  mov     rdx, rbx; lpValueName
0x1800139e9  mov     [rsp+1E0h+phkResult], rax; lpData
0x1800139ee  call    cs:__imp_RegQueryValueExW
0x1800139f4  mov     rbx, [rsp+1E0h+lpValueName]
0x1800139f9  lea     r9d, [r12+r12]; cbData
0x1800139fd  mov     rcx, [rsp+1E0h+var_180]; hKey
0x180013a02  mov     rdx, rbx; lpValueName
0x180013a05  mov     r8, r14; lpData
0x180013a08  call    ?SetValueData@@YAHPEAUHKEY__@@PEBGPEBEK@Z; SetValueData(HKEY__ *,ushort const *,uchar const *,ulong)
0x180013a0d  test    eax, eax
0x180013a0f  jnz     short loc_180013A65
0x180013a11  mov     r8, rbx; unsigned __int16 *
0x180013a14  mov     edx, 481h; uID
0x180013a19  mov     rcx, cs:hWnd; hWnd
0x180013a20  xor     r9d, r9d; unsigned __int16 *
0x180013a23  mov     [rsp+1E0h+cchCount2], r15d; unsigned int
0x180013a28  mov     dword ptr [rsp+1E0h+phkResult], 10h; unsigned int
0x180013a30  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180013a35  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180013a3a  test    rcx, rcx
0x180013a3d  jz      short loc_180013A45
0x180013a3f  call    cs:__imp_RegCloseKey
0x180013a45  test    rdi, rdi
0x180013a48  jz      short loc_180013A53
0x180013a4a  mov     rcx, rdi; hMem
0x180013a4d  call    cs:__imp_LocalFree
0x180013a53  test    r14, r14
0x180013a56  jz      short loc_180013A61
0x180013a58  mov     rcx, r14; hMem
0x180013a5b  call    cs:__imp_LocalFree
0x180013a61  xor     eax, eax
0x180013a63  jmp     short loc_180013AA0
0x180013a65  lea     rcx, aValueBackedUp; "Value backed-up\r\n"
0x180013a6c  call    ?WriteToLog@@YAXPEBGZZ; WriteToLog(ushort const *,...)
0x180013a71  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180013a76  mov     ebx, 1
0x180013a7b  mov     cs:?g_fAtleastOneRegSaved@@3HA, ebx; int g_fAtleastOneRegSaved
0x180013a81  test    rcx, rcx
0x180013a84  jz      short loc_180013A8C
0x180013a86  call    cs:__imp_RegCloseKey
0x180013a8c  mov     rcx, rdi; hMem
0x180013a8f  call    cs:__imp_LocalFree
0x180013a95  mov     rcx, r14; hMem
0x180013a98  call    cs:__imp_LocalFree
0x180013a9e  mov     eax, ebx
0x180013aa0  mov     rcx, [rbp+0E0h+var_50]
0x180013aa7  xor     rcx, rsp; StackCookie
0x180013aaa  call    __security_check_cookie
0x180013aaf  add     rsp, 1A8h
0x180013ab6  pop     r15
0x180013ab8  pop     r14
  ... truncated ...
```
