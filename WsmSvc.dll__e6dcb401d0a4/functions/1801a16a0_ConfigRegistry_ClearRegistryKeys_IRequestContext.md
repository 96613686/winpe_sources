# ConfigRegistry::ClearRegistryKeys(IRequestContext *)

- ea: `0x1801a16a0`
- end: `0x1801a1b3d`
- name: `?ClearRegistryKeys@ConfigRegistry@@IEAAHPEAVIRequestContext@@@Z`
- size: `1181`
- prototype: `__int64 __fastcall(ConfigRegistry *__hidden this, struct IRequestContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18019a8ac`

## callees

- `0x180005d10`
- `0x180071400`
- `0x1801123a8`
- `0x1801133b0`
- `0x18011a6d4`
- `0x18011fab0`
- `0x1801a14d0`
- `0x1801a16a0`
- `0x1801a1b50`
- `0x1801a2210`
- `0x1801a2440`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a180d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a188c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a180d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a188c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1af0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1a59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1a59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a1914`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a1914`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a17df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a17df`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a17f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a17f4`

## string_xrefs

- `0x1801a16de`: `onecore\admin\wmi\wmx\config\configregistry.cpp`
- `0x1801a1a89`: `onecore\admin\wmi\wmx\config\configregistry.cpp`
- `0x1801a1817`: `OpenThreadToken`
- `0x1801a1898`: `SeSecurityPrivilege`

## pseudocode

```c
__int64 __fastcall ConfigRegistry::ClearRegistryKeys(ConfigRegistry *this, struct IRequestContext *a2)
{
  HANDLE CurrentThread; // rax
  const unsigned __int16 *v6; // rcx
  void (__fastcall *v7)(struct IRequestContext *, __int64, __int64, const wchar_t *, DWORD); // rdi
  DWORD LastError; // ebx
  DWORD v9; // eax
  const wchar_t *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rcx
  unsigned int v14; // ebx
  DWORD v15; // eax
  __int64 i; // r15
  const WCHAR *v17; // r14
  unsigned int v18; // eax
  __int64 v19; // r9
  unsigned __int16 *v20; // rax
  int v21; // ecx
  int v22; // edx
  unsigned __int16 *v23; // rax
  int v24; // ecx
  int v25; // edx
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // r10
  unsigned __int16 *v28; // rax
  int v29; // ecx
  int v30; // edx
  unsigned __int16 *v31; // rax
  int v32; // ecx
  int v33; // edx
  __int64 v34; // rdx
  DWORD v35; // eax
  DWORD phkResult; // [rsp+20h] [rbp-A9h]
  void *TokenHandle[2]; // [rsp+40h] [rbp-89h] BYREF
  LPCWSTR lpSubKey[10]; // [rsp+50h] [rbp-79h]
  unsigned __int16 *v39[16]; // [rsp+A0h] [rbp-29h]
  int v40; // [rsp+138h] [rbp+6Fh] BYREF
  int v41; // [rsp+140h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+148h] [rbp+7Fh] BYREF

  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", 0x426u, L"1062", 0x54Fu, 0);
    return 0;
  }
  if ( !*((_DWORD *)this + 2817) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", 0x427u, L"1063", 0x54Fu, a2);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, this);
  lpSubKey[0] = (LPCWSTR)this;
  lpSubKey[1] = (LPCWSTR)((char *)this + 1024);
  lpSubKey[2] = (LPCWSTR)((char *)this + 2048);
  lpSubKey[3] = (LPCWSTR)((char *)this + 3072);
  lpSubKey[4] = (LPCWSTR)((char *)this + 6144);
  lpSubKey[5] = (LPCWSTR)((char *)this + 7168);
  lpSubKey[6] = (LPCWSTR)((char *)this + 0x2000);
  lpSubKey[7] = (LPCWSTR)((char *)this + 9216);
  lpSubKey[8] = (LPCWSTR)((char *)this + 10240);
  v39[0] = L"D:P(A;CI;GA;;;BA)(A;CI;GR;;;WD)S:P(AU;CISAFA;GW;;;WD)";
  v39[1] = L"D:P(A;CI;GA;;;BA)(A;CI;GR;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;CI;GR;;;S-1-5-80"
            "-4059739203-877974739-1245631912-527174227-2996563517)S:P(AU;CISAFA;GW;;;WD)";
  v39[2] = L"D:P(A;CI;GA;;;BA)(A;CI;GR;;;WD)S:P(AU;CISAFA;GW;;;WD)";
  v39[3] = L"D:P(A;CI;GA;;;BA)(A;CI;GR;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;CI;GR;;;S-1-5-80"
            "-4059739203-877974739-1245631912-527174227-2996563517)S:P(AU;CISAFA;GW;;;WD)";
  v39[4] = L"D:P(A;CI;GA;;;BA)(A;CI;GR;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;CI;GR;;;S-1-5-80"
            "-4059739203-877974739-1245631912-527174227-2996563517)S:P(AU;CISAFA;GW;;;WD)";
  v39[5] = L"D:P(A;CI;GA;;;BA)(A;CI;GR;;;WD)S:P(AU;CISAFA;GW;;;WD)";
  v39[6] = L"D:P(A;CI;GA;;;BA)(A;CI;GR;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;CI;GR;;;S-1-5-80"
            "-4059739203-877974739-1245631912-527174227-2996563517)S:P(AU;CISAFA;GW;;;WD)";
  v39[7] = L"D:P(A;CI;GA;;;BA)(A;CI;GA;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;CI;GR;;;S-1-5-80"
            "-4059739203-877974739-1245631912-527174227-2996563517)S:P(AU;CISAFA;GW;;;WD)";
  v39[8] = L"D:P(A;CI;GA;;;BA)(A;CI;GA;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;CI;GR;;;S-1-5-80"
            "-4059739203-877974739-1245631912-527174227-2996563517)S:P(AU;CISAFA;GW;;;WD)";
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 0, TokenHandle) )
  {
    v7 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, DWORD))(*(_QWORD *)a2 + 64LL);
    LastError = GetLastError();
    v9 = GetLastError();
    phkResult = LastError;
    v10 = L"OpenThreadToken";
    v11 = 1077134176;
    v12 = v9;
LABEL_11:
    v7(a2, v12, v11, v10, phkResult);
    AutoCleanup<AutoHandle,void *>::ReleasePtr(TokenHandle);
    return 0;
  }
  v40 = 0;
  v14 = EnablePrivilegeOnToken(v6, 1, TokenHandle[0], &v40);
  if ( !v14 )
  {
    v15 = GetLastError();
    v7 = *(void (__fastcall **)(struct IRequestContext *, __int64, __int64, const wchar_t *, DWORD))(*(_QWORD *)a2 + 64LL);
    if ( v15 == 1300 )
    {
      phkResult = GetLastError();
      v12 = v14 + 5;
    }
    else
    {
      phkResult = GetLastError();
      v12 = GetLastError();
    }
    v10 = L"SeSecurityPrivilege";
    v11 = 1077134220;
    goto LABEL_11;
  }
  for ( i = 0; (unsigned int)i < 9; i = (unsigned int)(i + 1) )
  {
    hKey = 0;
    v17 = lpSubKey[i];
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, lpSubKey[i]);
    v18 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v17, 0, 0x104010Bu, &hKey);
    v19 = v18;
    if ( v18 == 5 )
    {
      v34 = 5;
      v19 = 5;
      goto LABEL_56;
    }
    if ( v18 )
    {
      if ( v18 != 2 )
      {
        v34 = 1359;
LABEL_56:
        (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64))(*(_QWORD *)a2 + 64LL))(
          a2,
          v34,
          1077134221,
          v19);
        v14 = 0;
        break;
      }
      v14 = ConfigRegistry::CreateKey(
              this,
              a2,
              v17,
              &hKey,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion",
              0x106011Bu,
              0);
    }
    else
    {
      v20 = (unsigned __int16 *)((char *)this + 9216);
      do
      {
        v21 = *(unsigned __int16 *)((char *)v20 + (char *)v17 - ((char *)this + 9216));
        v22 = *v20 - v21;
        if ( v22 )
          break;
        ++v20;
      }
      while ( v21 );
      if ( v22 )
        v14 = ConfigRegistry::DeleteValues(a2, hKey);
      v23 = (unsigned __int16 *)((char *)this + 3072);
      do
      {
        v24 = *(unsigned __int16 *)((char *)v23 + (char *)v17 - ((char *)this + 3072));
        v25 = *v23 - v24;
        if ( v25 )
          break;
        ++v23;
      }
      while ( v24 );
      if ( !v25 )
      {
        v26 = (const unsigned __int16 *)((char *)this + 3072);
LABEL_45:
        ConfigRegistry::DeleteSubkeys(a2, hKey, v26, 0, 0);
        goto LABEL_46;
      }
      v27 = (const unsigned __int16 *)((char *)this + 6144);
      v28 = (unsigned __int16 *)((char *)this + 6144);
      do
      {
        v29 = *(unsigned __int16 *)((char *)v28 + (char *)v17 - ((char *)this + 6144));
        v30 = *v28 - v29;
        if ( v30 )
          break;
        ++v28;
      }
      while ( v29 );
      if ( !v30 )
        goto LABEL_44;
      v27 = (const unsigned __int16 *)((char *)this + 7168);
      v31 = (unsigned __int16 *)((char *)this + 7168);
      do
      {
        v32 = *(unsigned __int16 *)((char *)v31 + (char *)v17 - ((char *)this + 7168));
        v33 = *v31 - v32;
        if ( v33 )
          break;
        ++v31;
      }
      while ( v32 );
      if ( !v33 )
      {
LABEL_44:
        v26 = v27;
        goto LABEL_45;
      }
    }
LABEL_46:
    if ( v14 )
    {
      if ( !hKey )
      {
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", 0x4AFu, L"1199", 0x54Fu, a2);
        v14 = 0;
        goto LABEL_61;
      }
      v14 = ConfigRegistry::ApplySecurity(this, a2, hKey, v39[i], v17);
    }
    v13 = (const unsigned __int16 *)hKey;
    if ( hKey )
      RegCloseKey(hKey);
    if ( !v14 )
      break;
  }
  v41 = 0;
  if ( !EnablePrivilegeOnToken(v13, v40, TokenHandle[0], &v41)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    v35 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, v35);
  }
LABEL_61:
  AutoCleanup<AutoHandle,void *>::ReleasePtr(TokenHandle);
  return v14;
}

```

## disassembly

```asm
0x1801a16a0  mov     [rsp-8+arg_0], rbx
0x1801a16a5  push    rbp
0x1801a16a6  push    rsi
0x1801a16a7  push    rdi
0x1801a16a8  push    r12
0x1801a16aa  push    r13
0x1801a16ac  push    r14
0x1801a16ae  push    r15
0x1801a16b0  lea     rbp, [rsp-27h]
0x1801a16b5  sub     rsp, 0F0h
0x1801a16bc  mov     rsi, rdx
0x1801a16bf  mov     rdi, rcx
0x1801a16c2  test    rdx, rdx
0x1801a16c5  jnz     short loc_1801A16F1
0x1801a16c7  mov     [rsp+120h+phkResult], rdx; struct IRequestContext *
0x1801a16cc  lea     r8, a1062; "1062"
0x1801a16d3  mov     edx, 426h; unsigned int
0x1801a16d8  mov     r9d, 54Fh; unsigned int
0x1801a16de  lea     rcx, aOnecoreAdminWm_29; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1801a16e5  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a16ea  xor     eax, eax
0x1801a16ec  jmp     loc_1801A1B22
0x1801a16f1  cmp     dword ptr [rcx+2C04h], 0
0x1801a16f8  jnz     short loc_1801A170D
0x1801a16fa  mov     [rsp+120h+phkResult], rsi
0x1801a16ff  lea     r8, a1063; "1063"
0x1801a1706  mov     edx, 427h
0x1801a170b  jmp     short loc_1801A16D8
0x1801a170d  lea     r14, WPP_GLOBAL_Control
0x1801a1714  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a171b  cmp     rcx, r14
0x1801a171e  jz      short loc_1801A1741
0x1801a1720  test    dword ptr [rcx+1Ch], 200000h
0x1801a1727  jz      short loc_1801A1741
0x1801a1729  mov     edx, 27h ; '''
0x1801a172e  mov     r9, rdi
0x1801a1731  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1738  mov     rcx, [rcx+10h]
0x1801a173c  call    WPP_SF_q
0x1801a1741  mov     [rbp+57h+lpSubKey], rdi
0x1801a1745  lea     rax, [rdi+400h]
0x1801a174c  mov     [rbp+57h+var_C8], rax
0x1801a1750  lea     rax, [rdi+800h]
0x1801a1757  mov     [rbp+57h+var_C0], rax
0x1801a175b  lea     r13, [rdi+0C00h]
0x1801a1762  mov     [rbp+57h+var_B8], r13
0x1801a1766  lea     rax, [rdi+1800h]
0x1801a176d  mov     [rbp+57h+var_B0], rax
0x1801a1771  lea     rax, [rdi+1C00h]
0x1801a1778  mov     [rbp+57h+var_A8], rax
0x1801a177c  lea     rax, [rdi+2000h]
0x1801a1783  mov     [rbp+57h+var_A0], rax
0x1801a1787  lea     rax, [rdi+2400h]
0x1801a178e  mov     [rbp+57h+var_98], rax
0x1801a1792  lea     rax, [rdi+2800h]
0x1801a1799  mov     [rbp+57h+var_90], rax
0x1801a179d  lea     rcx, aDPACiGaBaACiGr; "D:P(A;CI;GA;;;BA)(A;CI;GR;;;WD)S:P(AU;C"...
0x1801a17a4  mov     [rbp+57h+var_80], rcx
0x1801a17a8  lea     rax, aDPACiGaBaACiGr_0; "D:P(A;CI;GA;;;BA)(A;CI;GR;;;S-1-5-80-56"...
0x1801a17af  mov     [rbp+57h+var_78], rax
0x1801a17b3  mov     [rbp+57h+var_70], rcx
0x1801a17b7  mov     [rbp+57h+var_68], rax
0x1801a17bb  mov     [rbp+57h+var_60], rax
0x1801a17bf  mov     [rbp+57h+var_58], rcx
0x1801a17c3  mov     [rbp+57h+var_50], rax
0x1801a17c7  lea     rax, aDPACiGaBaACiGa; "D:P(A;CI;GA;;;BA)(A;CI;GA;;;S-1-5-80-56"...
0x1801a17ce  mov     [rbp+57h+var_48], rax
0x1801a17d2  mov     [rbp+57h+var_40], rax
0x1801a17d6  mov     [rsp+120h+TokenHandle], 0
0x1801a17df  call    cs:__imp_GetCurrentThread
0x1801a17e5  lea     r9, [rsp+120h+TokenHandle]; TokenHandle
0x1801a17ea  xor     r8d, r8d; OpenAsSelf
0x1801a17ed  lea     edx, [r8+28h]; DesiredAccess
0x1801a17f1  mov     rcx, rax; ThreadHandle
0x1801a17f4  call    cs:__imp_OpenThreadToken
0x1801a17fa  test    eax, eax
0x1801a17fc  jnz     short loc_1801A1841
0x1801a17fe  mov     rax, [rsi]
0x1801a1801  mov     rdi, [rax+40h]
0x1801a1805  call    cs:__imp_GetLastError
0x1801a180b  mov     ebx, eax
0x1801a180d  call    cs:__imp_GetLastError
0x1801a1813  mov     dword ptr [rsp+120h+phkResult], ebx
0x1801a1817  lea     r9, aOpenthreadtoke; "OpenThreadToken"
0x1801a181e  mov     r8d, 4033C360h
0x1801a1824  mov     edx, eax
0x1801a1826  mov     rcx, rsi
0x1801a1829  mov     rax, rdi
0x1801a182c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1831  nop
0x1801a1832  lea     rcx, [rsp+120h+TokenHandle]
0x1801a1837  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801a183c  jmp     loc_1801A16EA
0x1801a1841  mov     [rbp+57h+arg_8], 0
0x1801a1848  lea     r9, [rbp+57h+arg_8]; int *
0x1801a184c  mov     r8, [rsp+120h+TokenHandle]; void *
0x1801a1851  mov     edx, 1; int
0x1801a1856  call    ?EnablePrivilegeOnToken@@YAHPEBGHPEAXPEAH@Z; EnablePrivilegeOnToken(ushort const *,int,void *,int *)
0x1801a185b  mov     ebx, eax
0x1801a185d  test    eax, eax
0x1801a185f  jnz     short loc_1801A18AA
0x1801a1861  call    cs:__imp_GetLastError
0x1801a1867  mov     rcx, [rsi]
0x1801a186a  mov     rdi, [rcx+40h]
0x1801a186e  cmp     eax, 514h
0x1801a1873  jnz     short loc_1801A1884
0x1801a1875  call    cs:__imp_GetLastError
0x1801a187b  mov     dword ptr [rsp+120h+phkResult], eax
0x1801a187f  lea     edx, [rbx+5]
0x1801a1882  jmp     short loc_1801A1898
0x1801a1884  call    cs:__imp_GetLastError
0x1801a188a  mov     ebx, eax
0x1801a188c  call    cs:__imp_GetLastError
0x1801a1892  mov     dword ptr [rsp+120h+phkResult], ebx
0x1801a1896  mov     edx, eax
0x1801a1898  lea     r9, aSesecuritypriv; "SeSecurityPrivilege"
0x1801a189f  mov     r8d, 4033C38Ch
0x1801a18a5  jmp     loc_1801A1826
0x1801a18aa  xor     r15d, r15d
0x1801a18ad  cmp     r15d, 9
0x1801a18b1  jnb     loc_1801A1AB8
0x1801a18b7  mov     [rbp+57h+hKey], 0
0x1801a18bf  mov     r14, [rbp+r15*8+57h+lpSubKey]
0x1801a18c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a18cb  lea     rax, WPP_GLOBAL_Control
0x1801a18d2  cmp     rcx, rax
0x1801a18d5  jz      short loc_1801A18F8
0x1801a18d7  test    dword ptr [rcx+1Ch], 200000h
0x1801a18de  jz      short loc_1801A18F8
0x1801a18e0  mov     edx, 28h ; '('
0x1801a18e5  mov     r9, r14
0x1801a18e8  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a18ef  mov     rcx, [rcx+10h]
0x1801a18f3  call    WPP_SF_S
0x1801a18f8  lea     rax, [rbp+57h+hKey]
0x1801a18fc  mov     [rsp+120h+phkResult], rax; phkResult
0x1801a1901  mov     r9d, 104010Bh; samDesired
0x1801a1907  xor     r8d, r8d; ulOptions
0x1801a190a  mov     rdx, r14; lpSubKey
0x1801a190d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a1914  call    cs:__imp_RegOpenKeyExW
0x1801a191a  mov     r9d, eax
0x1801a191d  cmp     eax, 5
0x1801a1920  jz      loc_1801A1A99
0x1801a1926  test    eax, eax
0x1801a1928  jz      short loc_1801A1969
0x1801a192a  cmp     eax, 2
0x1801a192d  jnz     loc_1801A1A6B
0x1801a1933  mov     [rsp+120h+var_F0], 0; unsigned int *
0x1801a193c  mov     [rsp+120h+var_F8], 106011Bh; unsigned int
0x1801a1944  lea     rax, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801a194b  mov     [rsp+120h+phkResult], rax; unsigned __int16 *
0x1801a1950  lea     r9, [rbp+57h+hKey]; HKEY *
0x1801a1954  mov     r8, r14; unsigned __int16 *
0x1801a1957  mov     rdx, rsi; struct IRequestContext *
0x1801a195a  mov     rcx, rdi; this
0x1801a195d  call    ?CreateKey@ConfigRegistry@@IEAAHPEAVIRequestContext@@PEBGPEAPEAUHKEY__@@1KPEAK@Z; ConfigRegistry::CreateKey(IRequestContext *,ushort const *,HKEY__ * *,ushort const *,ulong,ulong *)
0x1801a1962  mov     ebx, eax
0x1801a1964  jmp     loc_1801A1A2C
0x1801a1969  lea     rax, [rdi+2400h]
0x1801a1970  mov     r8, r14
0x1801a1973  sub     r8, rax
0x1801a1976  movzx   edx, word ptr [rax]
0x1801a1979  movzx   ecx, word ptr [rax+r8]
0x1801a197e  sub     edx, ecx
0x1801a1980  jnz     short loc_1801A198A
0x1801a1982  add     rax, 2
0x1801a1986  test    ecx, ecx
0x1801a1988  jnz     short loc_1801A1976
0x1801a198a  test    edx, edx
0x1801a198c  jz      short loc_1801A199C
0x1801a198e  mov     rdx, [rbp+57h+hKey]; hKey
0x1801a1992  mov     rcx, rsi; struct IRequestContext *
0x1801a1995  call    ?DeleteValues@ConfigRegistry@@KAHPEAVIRequestContext@@PEAUHKEY__@@@Z; ConfigRegistry::DeleteValues(IRequestContext *,HKEY__ *)
0x1801a199a  mov     ebx, eax
0x1801a199c  mov     rax, r13
0x1801a199f  mov     r8, r14
0x1801a19a2  sub     r8, r13
0x1801a19a5  movzx   edx, word ptr [rax]
0x1801a19a8  movzx   ecx, word ptr [rax+r8]
0x1801a19ad  sub     edx, ecx
0x1801a19af  jnz     short loc_1801A19B9
0x1801a19b1  add     rax, 2
0x1801a19b5  test    ecx, ecx
0x1801a19b7  jnz     short loc_1801A19A5
0x1801a19b9  test    edx, edx
0x1801a19bb  jnz     short loc_1801A19C2
0x1801a19bd  mov     r8, r13
0x1801a19c0  jmp     short loc_1801A1A15
0x1801a19c2  lea     r10, [rdi+1800h]
0x1801a19c9  mov     rax, r10
0x1801a19cc  mov     r8, r14
0x1801a19cf  sub     r8, r10
0x1801a19d2  movzx   edx, word ptr [rax]
0x1801a19d5  movzx   ecx, word ptr [rax+r8]
0x1801a19da  sub     edx, ecx
0x1801a19dc  jnz     short loc_1801A19E6
0x1801a19de  add     rax, 2
0x1801a19e2  test    ecx, ecx
0x1801a19e4  jnz     short loc_1801A19D2
0x1801a19e6  test    edx, edx
0x1801a19e8  jz      short loc_1801A1A12
0x1801a19ea  lea     r10, [rdi+1C00h]
0x1801a19f1  mov     rax, r10
0x1801a19f4  mov     r8, r14
0x1801a19f7  sub     r8, r10
0x1801a19fa  movzx   edx, word ptr [rax]
0x1801a19fd  movzx   ecx, word ptr [rax+r8]
0x1801a1a02  sub     edx, ecx
0x1801a1a04  jnz     short loc_1801A1A0E
0x1801a1a06  add     rax, 2
0x1801a1a0a  test    ecx, ecx
0x1801a1a0c  jnz     short loc_1801A19FA
0x1801a1a0e  test    edx, edx
0x1801a1a10  jnz     short loc_1801A1A2C
0x1801a1a12  mov     r8, r10; unsigned __int16 *
0x1801a1a15  mov     dword ptr [rsp+120h+phkResult], 0; int
0x1801a1a1d  xor     r9d, r9d; int
0x1801a1a20  mov     rdx, [rbp+57h+hKey]; hKey
0x1801a1a24  mov     rcx, rsi; struct IRequestContext *
0x1801a1a27  call    ?DeleteSubkeys@ConfigRegistry@@KAHPEAVIRequestContext@@PEAUHKEY__@@PEBGHH@Z; ConfigRegistry::DeleteSubkeys(IRequestContext *,HKEY__ *,ushort const *,int,int)
0x1801a1a2c  test    ebx, ebx
0x1801a1a2e  jz      short loc_1801A1A50
0x1801a1a30  mov     r8, [rbp+57h+hKey]; HKEY
0x1801a1a34  test    r8, r8
0x1801a1a37  jz      short loc_1801A1A72
0x1801a1a39  mov     [rsp+120h+phkResult], r14; unsigned __int16 *
0x1801a1a3e  mov     r9, [rbp+r15*8+57h+var_80]; unsigned __int16 *
0x1801a1a43  mov     rdx, rsi; struct IRequestContext *
0x1801a1a46  mov     rcx, rdi; this
0x1801a1a49  call    ?ApplySecurity@ConfigRegistry@@IEAAHPEAVIRequestContext@@PEAUHKEY__@@PEBG2@Z; ConfigRegistry::ApplySecurity(IRequestContext *,HKEY__ *,ushort const *,ushort const *)
0x1801a1a4e  mov     ebx, eax
0x1801a1a50  mov     rcx, [rbp+57h+hKey]; hKey
0x1801a1a54  test    rcx, rcx
0x1801a1a57  jz      short loc_1801A1A5F
0x1801a1a59  call    cs:__imp_RegCloseKey
0x1801a1a5f  test    ebx, ebx
0x1801a1a61  jz      short loc_1801A1AB8
0x1801a1a63  inc     r15d
0x1801a1a66  jmp     loc_1801A18AD
0x1801a1a6b  mov     edx, 54Fh
0x1801a1a70  jmp     short loc_1801A1AA1
0x1801a1a72  mov     [rsp+120h+phkResult], rsi; struct IRequestContext *
0x1801a1a77  mov     r9d, 54Fh; unsigned int
0x1801a1a7d  lea     r8, a1199; "1199"
0x1801a1a84  mov     edx, 4AFh; unsigned int
0x1801a1a89  lea     rcx, aOnecoreAdminWm_29; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1801a1a90  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a1a95  xor     ebx, ebx
0x1801a1a97  jmp     short loc_1801A1B16
0x1801a1a99  mov     edx, 5
0x1801a1a9e  mov     r9d, edx
0x1801a1aa1  mov     rax, [rsi]
0x1801a1aa4  mov     r8d, 4033C38Dh
0x1801a1aaa  mov     rcx, rsi
0x1801a1aad  mov     rax, [rax+40h]
0x1801a1ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1ab6  xor     ebx, ebx
0x1801a1ab8  mov     [rbp+57h+arg_10], 0
0x1801a1abf  lea     r9, [rbp+57h+arg_10]; int *
0x1801a1ac3  mov     r8, [rsp+120h+TokenHandle]; void *
0x1801a1ac8  mov     edx, [rbp+57h+arg_8]; int
0x1801a1acb  call    ?EnablePrivilegeOnToken@@YAHPEBGHPEAXPEAH@Z; EnablePrivilegeOnToken(ushort const *,int,void *,int *)
0x1801a1ad0  test    eax, eax
0x1801a1ad2  jnz     short loc_1801A1B16
0x1801a1ad4  mov     rax, cs:WPP_GLOBAL_Control
0x1801a1adb  lea     rcx, WPP_GLOBAL_Control
0x1801a1ae2  cmp     rax, rcx
0x1801a1ae5  jz      short loc_1801A1B16
0x1801a1ae7  test    dword ptr [rax+1Ch], 400000h
0x1801a1aee  jz      short loc_1801A1B16
0x1801a1af0  call    cs:__imp_GetLastError
0x1801a1af6  mov     edx, 29h ; ')'
0x1801a1afb  mov     r9d, eax
0x1801a1afe  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1b05  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1b0c  mov     rcx, [rcx+10h]
0x1801a1b10  call    WPP_SF_d
0x1801a1b15  nop
0x1801a1b16  lea     rcx, [rsp+120h+TokenHandle]
0x1801a1b1b  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801a1b20  mov     eax, ebx
0x1801a1b22  mov     rbx, [rsp+120h+arg_0]
0x1801a1b2a  add     rsp, 0F0h
0x1801a1b31  pop     r15
0x1801a1b33  pop     r14
0x1801a1b35  pop     r13
0x1801a1b37  pop     r12
0x1801a1b39  pop     rdi
0x1801a1b3a  pop     rsi
0x1801a1b3b  pop     rbp
0x1801a1b3c  retn
```
