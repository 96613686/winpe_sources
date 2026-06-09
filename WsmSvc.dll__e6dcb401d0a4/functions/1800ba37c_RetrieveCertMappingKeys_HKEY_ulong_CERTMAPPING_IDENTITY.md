# RetrieveCertMappingKeys(HKEY__ *,ulong,CERTMAPPING_IDENTITY *)

- ea: `0x1800ba37c`
- end: `0x1800ba8fd`
- name: `?RetrieveCertMappingKeys@@YAHPEAUHKEY__@@KPEAVCERTMAPPING_IDENTITY@@@Z`
- size: `1409`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD dwIndex, struct CERTMAPPING_IDENTITY *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040ee0`
- `0x180196308`

## callees

- `0x180005d10`
- `0x180008920`
- `0x1800621e0`
- `0x1800ba37c`
- `0x1800bac30`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18012a93c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba4f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba59d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba6a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba7ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba4f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba59d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba6a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba7ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ba891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba50f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba50f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ba470`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ba470`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ba542`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ba63d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ba743`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ba849`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ba63d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ba743`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ba849`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ba4b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ba4b9`

## string_xrefs

- `0x1800ba3ba`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800ba43f`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800ba5dc`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800ba6db`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800ba7e1`: `onecore\admin\wmi\wmx\config\configutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RetrieveCertMappingKeys(HKEY hKey, DWORD dwIndex, WCHAR *a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdx
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  DWORD v11; // ecx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD LastError; // eax
  HKEY v15; // rcx
  BYTE *v16; // r15
  DWORD v17; // ecx
  HKEY v18; // rbx
  LSTATUS v19; // eax
  BYTE *v20; // rsi
  DWORD v21; // ecx
  HKEY v22; // rbx
  LSTATUS v23; // eax
  BYTE *v24; // rbx
  HKEY v25; // r14
  LSTATUS v26; // eax
  unsigned int v27; // ebx
  HKEY phkResult; // [rsp+40h] [rbp-20h] BYREF
  BYTE *v29; // [rsp+48h] [rbp-18h] BYREF
  BYTE *v30; // [rsp+50h] [rbp-10h] BYREF
  BYTE *v31; // [rsp+58h] [rbp-8h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+58h] BYREF

  if ( !hKey )
  {
    v6 = L"2488";
    v7 = 2488;
LABEL_3:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", v7, v6, 0x54Fu, 0);
    return 0;
  }
  if ( !a3 )
  {
    v6 = L"2489";
    v7 = 2489;
    goto LABEL_3;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_56614427bb63350db5b96d546a520a16_Traceguids);
  phkResult = 0;
  cchName = 256;
  if ( a3 == (WCHAR *)-44LL )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 2431, L"2431", 0x54Fu, 0);
    goto LABEL_24;
  }
  v9 = RegEnumKeyExW(hKey, dwIndex, a3 + 22, &cchName, 0, 0, 0, 0);
  v10 = v9;
  v11 = 259;
  if ( v9 == 259 )
  {
LABEL_23:
    SetLastError(v11);
LABEL_24:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, LastError);
    }
    v15 = phkResult;
    phkResult = 0;
    if ( v15 )
      RegCloseKey(v15);
    return 0;
  }
  if ( v9 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_22;
    v13 = 63;
LABEL_21:
    WPP_SF_d(v12[2], v13, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, v10);
LABEL_22:
    v11 = v10;
    goto LABEL_23;
  }
  v10 = RegOpenKeyExW(hKey, a3 + 22, 0, 0x109u, &phkResult);
  if ( v10 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
      goto LABEL_22;
    v13 = 64;
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, a3 + 22);
  Type = 0;
  v16 = (BYTE *)WSManMemory::Alloc(20480, 0, 0);
  v29 = v16;
  if ( !v16 )
  {
    v17 = 14;
LABEL_34:
    SetLastError(v17);
LABEL_35:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
    return 0;
  }
  v18 = phkResult;
  if ( !phkResult )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 508, L"508", 0x54Fu, 0);
LABEL_45:
    v17 = -2144108539;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, L"Uri");
  cchName = 20480;
  v19 = RegQueryValueExW(v18, L"Uri", 0, &Type, v16, &cchName);
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
        v19,
        (__int64)L"Uri");
    goto LABEL_45;
  }
  v20 = (BYTE *)WSManMemory::Alloc(20480, 0, 0);
  v30 = v20;
  if ( !v20 )
  {
    v21 = 14;
LABEL_48:
    SetLastError(v21);
LABEL_49:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v30);
    goto LABEL_35;
  }
  v22 = phkResult;
  if ( !phkResult )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 508, L"508", 0x54Fu, 0);
LABEL_59:
    v21 = -2144108539;
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, L"Subject");
  cchName = 20480;
  v23 = RegQueryValueExW(v22, L"Subject", 0, &Type, v20, &cchName);
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
        v23,
        (__int64)L"Subject");
    goto LABEL_59;
  }
  v24 = (BYTE *)WSManMemory::Alloc(20480, 0, 0);
  v31 = v24;
  if ( !v24 )
  {
    SetLastError(0xEu);
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v31);
    goto LABEL_49;
  }
  v25 = phkResult;
  if ( phkResult )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, L"Thumbprint");
    cchName = 20480;
    v26 = RegQueryValueExW(v25, L"Thumbprint", 0, &Type, v24, &cchName);
    if ( !v26 )
    {
      v31 = 0;
      *((_QWORD *)a3 + 4) = v24;
      v30 = 0;
      *((_QWORD *)a3 + 3) = v20;
      v29 = 0;
      *((_QWORD *)a3 + 2) = v16;
      v27 = 1;
      *((_DWORD *)a3 + 10) = 1;
      goto LABEL_73;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
        v26,
        (__int64)L"Thumbprint");
  }
  else
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 508, L"508", 0x54Fu, 0);
  }
  SetLastError(0x80338005);
  v27 = 0;
LABEL_73:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v31);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v30);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v29);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
  return v27;
}

```

## disassembly

```asm
0x1800ba37c  mov     [rsp-38h+arg_8], rbx
0x1800ba381  push    rbp
0x1800ba382  push    rsi
0x1800ba383  push    rdi
0x1800ba384  push    r12
0x1800ba386  push    r13
0x1800ba388  push    r14
0x1800ba38a  push    r15
0x1800ba38c  mov     rbp, rsp
0x1800ba38f  sub     rsp, 60h
0x1800ba393  mov     rdi, r8
0x1800ba396  mov     ebx, edx
0x1800ba398  mov     r14, rcx
0x1800ba39b  xor     r12d, r12d
0x1800ba39e  test    rcx, rcx
0x1800ba3a1  jnz     short loc_1800BA3CD
0x1800ba3a3  lea     r8, a2488; "2488"
0x1800ba3aa  mov     edx, 9B8h; unsigned int
0x1800ba3af  mov     r9d, 54Fh; unsigned int
0x1800ba3b5  mov     [rsp+60h+lpReserved], r12; struct IRequestContext *
0x1800ba3ba  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800ba3c1  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800ba3c6  xor     eax, eax
0x1800ba3c8  jmp     loc_1800BA8E5
0x1800ba3cd  test    rdi, rdi
0x1800ba3d0  jnz     short loc_1800BA3E0
0x1800ba3d2  lea     r8, a2489; "2489"
0x1800ba3d9  mov     edx, 9B9h
0x1800ba3de  jmp     short loc_1800BA3AF
0x1800ba3e0  lea     r13, WPP_GLOBAL_Control
0x1800ba3e7  lea     r15, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800ba3ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba3f5  cmp     rcx, r13
0x1800ba3f8  jz      short loc_1800BA414
0x1800ba3fa  test    dword ptr [rcx+1Ch], 200000h
0x1800ba401  jz      short loc_1800BA414
0x1800ba403  mov     edx, 41h ; 'A'
0x1800ba408  mov     r8, r15
0x1800ba40b  mov     rcx, [rcx+10h]
0x1800ba40f  call    WPP_SF_
0x1800ba414  mov     [rbp+phkResult], r12
0x1800ba418  lea     rsi, [rdi+2Ch]
0x1800ba41c  mov     [rbp+cchName], 100h
0x1800ba423  test    rsi, rsi
0x1800ba426  jnz     short loc_1800BA450
0x1800ba428  mov     [rsp+60h+lpReserved], r12; struct IRequestContext *
0x1800ba42d  mov     r9d, 54Fh; unsigned int
0x1800ba433  lea     r8, a2431; "2431"
0x1800ba43a  mov     edx, 97Fh; unsigned int
0x1800ba43f  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800ba446  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800ba44b  jmp     loc_1800BA4FA
0x1800ba450  mov     [rsp+60h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800ba455  mov     [rsp+60h+lpcchClass], r12; lpcchClass
0x1800ba45a  mov     [rsp+60h+lpClass], r12; lpClass
0x1800ba45f  mov     [rsp+60h+lpReserved], r12; lpReserved
0x1800ba464  lea     r9, [rbp+cchName]; lpcchName
0x1800ba468  mov     r8, rsi; lpName
0x1800ba46b  mov     edx, ebx; dwIndex
0x1800ba46d  mov     rcx, r14; hKey
0x1800ba470  call    cs:__imp_RegEnumKeyExW
0x1800ba476  mov     ebx, eax
0x1800ba478  mov     ecx, 103h
0x1800ba47d  cmp     eax, ecx
0x1800ba47f  jz      short loc_1800BA4F4
0x1800ba481  test    eax, eax
0x1800ba483  jz      short loc_1800BA4A1
0x1800ba485  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba48c  cmp     rcx, r13
0x1800ba48f  jz      short loc_1800BA4F2
0x1800ba491  test    dword ptr [rcx+1Ch], 400000h
0x1800ba498  jz      short loc_1800BA4F2
0x1800ba49a  mov     edx, 3Fh ; '?'
0x1800ba49f  jmp     short loc_1800BA4E3
0x1800ba4a1  lea     rax, [rbp+phkResult]
0x1800ba4a5  mov     [rsp+60h+lpReserved], rax; phkResult
0x1800ba4aa  mov     r9d, 109h; samDesired
0x1800ba4b0  xor     r8d, r8d; ulOptions
0x1800ba4b3  mov     rdx, rsi; lpSubKey
0x1800ba4b6  mov     rcx, r14; hKey
0x1800ba4b9  call    cs:__imp_RegOpenKeyExW
0x1800ba4bf  mov     ebx, eax
0x1800ba4c1  test    eax, eax
0x1800ba4c3  jz      loc_1800BA54D
0x1800ba4c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba4d0  cmp     rcx, r13
0x1800ba4d3  jz      short loc_1800BA4F2
0x1800ba4d5  test    dword ptr [rcx+1Ch], 400000h
0x1800ba4dc  jz      short loc_1800BA4F2
0x1800ba4de  mov     edx, 40h ; '@'
0x1800ba4e3  mov     r9d, ebx
0x1800ba4e6  mov     r8, r15
0x1800ba4e9  mov     rcx, [rcx+10h]
0x1800ba4ed  call    WPP_SF_d
0x1800ba4f2  mov     ecx, ebx; dwErrCode
0x1800ba4f4  call    cs:__imp_SetLastError
0x1800ba4fa  mov     rax, cs:WPP_GLOBAL_Control
0x1800ba501  cmp     rax, r13
0x1800ba504  jz      short loc_1800BA531
0x1800ba506  test    dword ptr [rax+1Ch], 200000h
0x1800ba50d  jz      short loc_1800BA531
0x1800ba50f  call    cs:__imp_GetLastError
0x1800ba515  mov     edx, 42h ; 'B'
0x1800ba51a  mov     r9d, eax
0x1800ba51d  mov     r8, r15
0x1800ba520  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba527  mov     rcx, [rcx+10h]
0x1800ba52b  call    WPP_SF_d
0x1800ba530  nop
0x1800ba531  mov     rcx, [rbp+phkResult]; hKey
0x1800ba535  mov     [rbp+phkResult], r12
0x1800ba539  test    rcx, rcx
0x1800ba53c  jz      loc_1800BA3C6
0x1800ba542  call    cs:__imp_RegCloseKey
0x1800ba548  jmp     loc_1800BA3C6
0x1800ba54d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba554  mov     r14d, 200000h
0x1800ba55a  cmp     rcx, r13
0x1800ba55d  jz      short loc_1800BA579
0x1800ba55f  test    [rcx+1Ch], r14d
0x1800ba563  jz      short loc_1800BA579
0x1800ba565  mov     edx, 43h ; 'C'
0x1800ba56a  mov     r9, rsi
0x1800ba56d  mov     r8, r15
0x1800ba570  mov     rcx, [rcx+10h]
0x1800ba574  call    WPP_SF_S
0x1800ba579  mov     [rbp+Type], r12d
0x1800ba57d  xor     r8d, r8d
0x1800ba580  xor     edx, edx
0x1800ba582  mov     esi, 5000h
0x1800ba587  mov     ecx, esi
0x1800ba589  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800ba58e  mov     r15, rax
0x1800ba591  mov     [rbp+var_18], rax
0x1800ba595  test    rax, rax
0x1800ba598  jnz     short loc_1800BA5BC
0x1800ba59a  lea     ecx, [rax+0Eh]; dwErrCode
0x1800ba59d  call    cs:__imp_SetLastError
0x1800ba5a3  nop
0x1800ba5a4  lea     rcx, [rbp+var_18]
0x1800ba5a8  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800ba5ad  nop
0x1800ba5ae  lea     rcx, [rbp+phkResult]
0x1800ba5b2  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x1800ba5b7  jmp     loc_1800BA3C6
0x1800ba5bc  mov     rbx, [rbp+phkResult]
0x1800ba5c0  test    rbx, rbx
0x1800ba5c3  jnz     short loc_1800BA5ED
0x1800ba5c5  mov     [rsp+60h+lpReserved], r12; struct IRequestContext *
0x1800ba5ca  mov     r9d, 54Fh; unsigned int
0x1800ba5d0  lea     r8, a508; "508"
0x1800ba5d7  mov     edx, 1FCh; unsigned int
0x1800ba5dc  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800ba5e3  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800ba5e8  jmp     loc_1800BA680
0x1800ba5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba5f4  cmp     rcx, r13
0x1800ba5f7  jz      short loc_1800BA61B
0x1800ba5f9  test    [rcx+1Ch], r14d
0x1800ba5fd  jz      short loc_1800BA61B
0x1800ba5ff  mov     edx, 1Dh
0x1800ba604  lea     r9, aUri_0; "Uri"
0x1800ba60b  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800ba612  mov     rcx, [rcx+10h]
0x1800ba616  call    WPP_SF_S
0x1800ba61b  mov     [rbp+cchName], esi
0x1800ba61e  lea     rax, [rbp+cchName]
0x1800ba622  mov     [rsp+60h+lpClass], rax; lpcbData
0x1800ba627  mov     [rsp+60h+lpReserved], r15; lpData
0x1800ba62c  lea     r9, [rbp+Type]; lpType
0x1800ba630  xor     r8d, r8d; lpReserved
0x1800ba633  lea     rdx, aUri_0; "Uri"
0x1800ba63a  mov     rcx, rbx; hKey
0x1800ba63d  call    cs:__imp_RegQueryValueExW
0x1800ba643  test    eax, eax
0x1800ba645  jz      short loc_1800BA68A
0x1800ba647  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba64e  cmp     rcx, r13
0x1800ba651  jz      short loc_1800BA680
0x1800ba653  test    dword ptr [rcx+1Ch], 400000h
0x1800ba65a  jz      short loc_1800BA680
0x1800ba65c  mov     edx, 1Fh
0x1800ba661  lea     r8, aUri_0; "Uri"
0x1800ba668  mov     [rsp+60h+lpReserved], r8
0x1800ba66d  mov     r9d, eax
0x1800ba670  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800ba677  mov     rcx, [rcx+10h]
0x1800ba67b  call    WPP_SF_dS
0x1800ba680  mov     ecx, 80338005h
0x1800ba685  jmp     loc_1800BA59D
0x1800ba68a  xor     r8d, r8d
0x1800ba68d  xor     edx, edx
0x1800ba68f  mov     rcx, rsi
0x1800ba692  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800ba697  mov     rsi, rax
0x1800ba69a  mov     [rbp+var_10], rax
0x1800ba69e  test    rax, rax
0x1800ba6a1  jnz     short loc_1800BA6BB
0x1800ba6a3  lea     ecx, [rax+0Eh]; dwErrCode
0x1800ba6a6  call    cs:__imp_SetLastError
0x1800ba6ac  nop
0x1800ba6ad  lea     rcx, [rbp+var_10]
0x1800ba6b1  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800ba6b6  jmp     loc_1800BA5A4
0x1800ba6bb  mov     rbx, [rbp+phkResult]
0x1800ba6bf  test    rbx, rbx
0x1800ba6c2  jnz     short loc_1800BA6EC
0x1800ba6c4  mov     [rsp+60h+lpReserved], r12; struct IRequestContext *
0x1800ba6c9  mov     r9d, 54Fh; unsigned int
0x1800ba6cf  lea     r8, a508; "508"
0x1800ba6d6  mov     edx, 1FCh; unsigned int
0x1800ba6db  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800ba6e2  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800ba6e7  jmp     loc_1800BA786
0x1800ba6ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba6f3  cmp     rcx, r13
0x1800ba6f6  jz      short loc_1800BA71A
0x1800ba6f8  test    [rcx+1Ch], r14d
0x1800ba6fc  jz      short loc_1800BA71A
0x1800ba6fe  mov     edx, 1Dh
0x1800ba703  lea     r9, aSubject; "Subject"
0x1800ba70a  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800ba711  mov     rcx, [rcx+10h]
0x1800ba715  call    WPP_SF_S
0x1800ba71a  mov     r14d, 5000h
0x1800ba720  mov     [rbp+cchName], r14d
0x1800ba724  lea     rax, [rbp+cchName]
0x1800ba728  mov     [rsp+60h+lpClass], rax; lpcbData
0x1800ba72d  mov     [rsp+60h+lpReserved], rsi; lpData
0x1800ba732  lea     r9, [rbp+Type]; lpType
0x1800ba736  xor     r8d, r8d; lpReserved
0x1800ba739  lea     rdx, aSubject; "Subject"
0x1800ba740  mov     rcx, rbx; hKey
0x1800ba743  call    cs:__imp_RegQueryValueExW
0x1800ba749  test    eax, eax
0x1800ba74b  jz      short loc_1800BA790
0x1800ba74d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba754  cmp     rcx, r13
0x1800ba757  jz      short loc_1800BA786
0x1800ba759  test    dword ptr [rcx+1Ch], 400000h
0x1800ba760  jz      short loc_1800BA786
0x1800ba762  mov     edx, 1Fh
0x1800ba767  lea     r8, aSubject; "Subject"
0x1800ba76e  mov     [rsp+60h+lpReserved], r8
0x1800ba773  mov     r9d, eax
0x1800ba776  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800ba77d  mov     rcx, [rcx+10h]
0x1800ba781  call    WPP_SF_dS
0x1800ba786  mov     ecx, 80338005h
0x1800ba78b  jmp     loc_1800BA6A6
0x1800ba790  xor     r8d, r8d
0x1800ba793  xor     edx, edx
0x1800ba795  mov     rcx, r14
0x1800ba798  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1800ba79d  mov     rbx, rax
0x1800ba7a0  mov     [rbp+var_8], rax
0x1800ba7a4  test    rax, rax
0x1800ba7a7  jnz     short loc_1800BA7C1
0x1800ba7a9  lea     ecx, [rax+0Eh]; dwErrCode
0x1800ba7ac  call    cs:__imp_SetLastError
0x1800ba7b2  nop
0x1800ba7b3  lea     rcx, [rbp+var_8]
0x1800ba7b7  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1800ba7bc  jmp     loc_1800BA6AD
0x1800ba7c1  mov     r14, [rbp+phkResult]
0x1800ba7c5  test    r14, r14
0x1800ba7c8  jnz     short loc_1800BA7F2
0x1800ba7ca  mov     [rsp+60h+lpReserved], r12; struct IRequestContext *
0x1800ba7cf  mov     r9d, 54Fh; unsigned int
0x1800ba7d5  lea     r8, a508; "508"
0x1800ba7dc  mov     edx, 1FCh; unsigned int
0x1800ba7e1  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800ba7e8  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800ba7ed  jmp     loc_1800BA88C
0x1800ba7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba7f9  cmp     rcx, r13
0x1800ba7fc  jz      short loc_1800BA823
0x1800ba7fe  test    dword ptr [rcx+1Ch], 200000h
0x1800ba805  jz      short loc_1800BA823
0x1800ba807  mov     edx, 1Dh
0x1800ba80c  lea     r9, aThumbprint; "Thumbprint"
0x1800ba813  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800ba81a  mov     rcx, [rcx+10h]
0x1800ba81e  call    WPP_SF_S
0x1800ba823  mov     [rbp+cchName], 5000h
0x1800ba82a  lea     rax, [rbp+cchName]
0x1800ba82e  mov     [rsp+60h+lpClass], rax; lpcbData
0x1800ba833  mov     [rsp+60h+lpReserved], rbx; lpData
0x1800ba838  lea     r9, [rbp+Type]; lpType
0x1800ba83c  xor     r8d, r8d; lpReserved
0x1800ba83f  lea     rdx, aThumbprint; "Thumbprint"
0x1800ba846  mov     rcx, r14; hKey
0x1800ba849  call    cs:__imp_RegQueryValueExW
0x1800ba84f  test    eax, eax
0x1800ba851  jz      short loc_1800BA89C
0x1800ba853  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba85a  cmp     rcx, r13
0x1800ba85d  jz      short loc_1800BA88C
0x1800ba85f  test    dword ptr [rcx+1Ch], 400000h
0x1800ba866  jz      short loc_1800BA88C
  ... truncated ...
```
