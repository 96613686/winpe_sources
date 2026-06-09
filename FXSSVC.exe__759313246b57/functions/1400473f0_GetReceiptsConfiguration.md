# GetReceiptsConfiguration

- ea: `0x1400473f0`
- end: `0x140047917`
- name: `GetReceiptsConfiguration`
- size: `1319`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140068fdc`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x1400472d0`
- `0x1400473f0`
- `0x1400698ec`
- `0x14006af2c`
- `0x140074f18`
- `0x14008249c`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140047898`
- `ADVAPI32!RegCloseKey` at `0x140047898`
- `ADVAPI32!LogonUserW` at `0x1400477bd`
- `ADVAPI32!LogonUserW` at `0x1400477bd`
- `ADVAPI32!DuplicateToken` at `0x140047822`
- `ADVAPI32!DuplicateToken` at `0x140047822`
- `KERNEL32!GetLastError` at `0x14004761a`
- `KERNEL32!GetLastError` at `0x1400477cd`
- `KERNEL32!GetLastError` at `0x140047832`
- `KERNEL32!GetLastError` at `0x14004761a`
- `KERNEL32!GetLastError` at `0x1400477cd`
- `KERNEL32!GetLastError` at `0x140047832`
- `KERNEL32!EnterCriticalSection` at `0x1400474bf`
- `KERNEL32!EnterCriticalSection` at `0x1400474bf`
- `KERNEL32!LeaveCriticalSection` at `0x140047884`
- `KERNEL32!LeaveCriticalSection` at `0x140047884`
- `credui!CredUIParseUserNameW` at `0x14004773e`
- `credui!CredUIParseUserNameW` at `0x14004773e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetReceiptsConfiguration(_QWORD *a1, int a2)
{
  void *v4; // rax
  void *v5; // rsi
  HKEY v7; // r15
  unsigned __int16 *v8; // rax
  unsigned int v9; // ebx
  CMapDeviceId *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rax
  HKEY v14; // rax
  DWORD LastError; // eax
  __int64 RegistrySecureString; // rax
  HANDLE v17; // rcx
  DWORD v18; // eax
  CMapDeviceId *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // eax
  HANDLE ExistingTokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  void *DuplicateTokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR domain[344]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR user[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
  }
  v4 = (void *)pMemAlloc(0x50u);
  v5 = v4;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
    }
    return 8;
  }
  v7 = 0;
  memset_0(v4, 0, 0x50u);
  EnterCriticalSection(&g_CsConfig);
  *(_DWORD *)v5 = 80;
  *((_DWORD *)v5 + 16) = dword_1400A7680;
  *((_DWORD *)v5 + 8) = *(_DWORD *)&dword_1400A7660;
  *((_DWORD *)v5 + 1) = dword_1400A7644;
  *((_DWORD *)v5 + 2) = dword_1400A7648;
  *((_QWORD *)v5 + 2) = 0;
  if ( qword_1400A7658 )
  {
    v8 = StringDup(qword_1400A7658);
    *((_QWORD *)v5 + 3) = v8;
    if ( !v8 )
    {
      v9 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v11 = 48;
      goto LABEL_17;
    }
  }
  if ( qword_1400A7668 )
  {
    v12 = StringDup(qword_1400A7668);
    *((_QWORD *)v5 + 5) = v12;
    if ( !v12 )
    {
      v9 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v11 = 49;
      goto LABEL_17;
    }
  }
  if ( UserName )
  {
    v13 = StringDup((unsigned __int16 *)UserName);
    *((_QWORD *)v5 + 6) = v13;
    if ( !v13 )
    {
      v9 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v11 = 50;
      goto LABEL_17;
    }
  }
  v14 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax\\Receipts", 0, 131103);
  v7 = v14;
  if ( !v14 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, LastError);
    }
    goto LABEL_62;
  }
  RegistrySecureString = GetRegistrySecureString(v14, 0);
  *((_QWORD *)v5 + 7) = RegistrySecureString;
  if ( !RegistrySecureString )
  {
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_62;
    }
    v11 = 52;
LABEL_17:
    WPP_SF_(*((_QWORD *)v10 + 2), v11, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
    goto LABEL_62;
  }
  v9 = 0;
  if ( a2 && dword_1400A7648 == 2 )
  {
    v17 = hObject;
    DuplicateTokenHandle = 0;
    if ( !hObject )
    {
      ExistingTokenHandle = 0;
      memset_0(user, 0, 0x402u);
      memset_0(domain, 0, 0x2A2u);
      v18 = CredUIParseUserNameW(UserName, user, 0x201u, domain, 0x151u);
      v9 = v18;
      if ( v18 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v20 = 53;
        goto LABEL_48;
      }
      if ( !LogonUserW(user, domain, *((LPCWSTR *)v5 + 7), 2u, 0, &ExistingTokenHandle) )
      {
        v18 = GetLastError();
        v9 = v18;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v20 = 54;
        goto LABEL_48;
      }
      v17 = ExistingTokenHandle;
      hObject = ExistingTokenHandle;
    }
    if ( !DuplicateToken(v17, SecurityDelegation, &DuplicateTokenHandle) )
    {
      v18 = GetLastError();
      v9 = v18;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v20 = 55;
LABEL_48:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v18);
      goto LABEL_62;
    }
    *((_QWORD *)v5 + 9) = DuplicateTokenHandle;
  }
  *a1 = v5;
LABEL_62:
  LeaveCriticalSection(&g_CsConfig);
  if ( v7 )
  {
    v21 = RegCloseKey(v7);
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v21);
      }
    }
  }
  if ( v9 )
    FreeReceiptsConfiguration(v5);
  return v9;
}

```

## disassembly

```asm
0x1400473f0  mov     [rsp-8+arg_8], rbx
0x1400473f5  mov     [rsp-8+arg_10], rsi
0x1400473fa  push    rbp
0x1400473fb  push    rdi
0x1400473fc  push    r12
0x1400473fe  push    r14
0x140047400  push    r15
0x140047402  lea     rbp, [rsp-610h]
0x14004740a  sub     rsp, 710h
0x140047411  mov     rax, cs:__security_cookie
0x140047418  xor     rax, rsp
0x14004741b  mov     [rbp+630h+var_30], rax
0x140047422  mov     r14d, edx
0x140047425  mov     r12, rcx
0x140047428  mov     rcx, cs:WPP_GLOBAL_Control
0x14004742f  lea     rbx, WPP_GLOBAL_Control
0x140047436  cmp     rcx, rbx
0x140047439  jz      short loc_14004745C
0x14004743b  test    byte ptr [rcx+1Ch], 4
0x14004743f  jz      short loc_14004745C
0x140047441  cmp     byte ptr [rcx+19h], 5
0x140047445  jb      short loc_14004745C
0x140047447  mov     rcx, [rcx+10h]
0x14004744b  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140047452  mov     edx, 2Eh ; '.'
0x140047457  call    WPP_SF_
0x14004745c  mov     edi, 50h ; 'P'
0x140047461  mov     ecx, edi; dwBytes
0x140047463  call    pMemAlloc
0x140047468  mov     rsi, rax
0x14004746b  test    rax, rax
0x14004746e  jnz     short loc_1400474A8
0x140047470  mov     rcx, cs:WPP_GLOBAL_Control
0x140047477  cmp     rcx, rbx
0x14004747a  jz      short loc_14004749E
0x14004747c  test    byte ptr [rcx+1Ch], 4
0x140047480  jz      short loc_14004749E
0x140047482  lea     edi, [rax+2]
0x140047485  cmp     [rcx+19h], dil
0x140047489  jb      short loc_14004749E
0x14004748b  mov     rcx, [rcx+10h]
0x14004748f  lea     edx, [rax+2Fh]
0x140047492  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140047499  call    WPP_SF_
0x14004749e  mov     eax, 8
0x1400474a3  jmp     loc_1400478EB
0x1400474a8  mov     r8, rdi; Size
0x1400474ab  xor     edx, edx; Val
0x1400474ad  mov     rcx, rsi; void *
0x1400474b0  xor     r15d, r15d
0x1400474b3  call    memset_0
0x1400474b8  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400474bf  call    cs:__imp_EnterCriticalSection
0x1400474c6  nop     dword ptr [rax+rax+00h]
0x1400474cb  mov     [rsi], edi
0x1400474cd  lea     edi, [r15+2]
0x1400474d1  mov     eax, cs:dword_1400A7680
0x1400474d7  mov     [rsi+40h], eax
0x1400474da  mov     eax, cs:dword_1400A7660
0x1400474e0  mov     [rsi+20h], eax
0x1400474e3  mov     eax, cs:dword_1400A7644
0x1400474e9  mov     [rsi+4], eax
0x1400474ec  mov     eax, cs:dword_1400A7648
0x1400474f2  mov     [rsi+8], eax
0x1400474f5  mov     [rsi+10h], r15
0x1400474f9  mov     rcx, cs:qword_1400A7658; unsigned __int16 *
0x140047500  test    rcx, rcx
0x140047503  jz      short loc_140047559
0x140047505  call    StringDup
0x14004750a  mov     [rsi+18h], rax
0x14004750e  test    rax, rax
0x140047511  jnz     short loc_140047559
0x140047513  lea     ebx, [rdi+6]
0x140047516  mov     rcx, cs:WPP_GLOBAL_Control
0x14004751d  lea     r14, WPP_GLOBAL_Control
0x140047524  cmp     rcx, r14
0x140047527  jz      loc_14004787D
0x14004752d  test    byte ptr [rcx+1Ch], 4
0x140047531  jz      loc_14004787D
0x140047537  cmp     [rcx+19h], dil
0x14004753b  jb      loc_14004787D
0x140047541  lea     edx, [rdi+2Eh]
0x140047544  mov     rcx, [rcx+10h]
0x140047548  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x14004754f  call    WPP_SF_
0x140047554  jmp     loc_14004787D
0x140047559  mov     rcx, cs:qword_1400A7668; unsigned __int16 *
0x140047560  test    rcx, rcx
0x140047563  jz      short loc_1400475A6
0x140047565  call    StringDup
0x14004756a  mov     [rsi+28h], rax
0x14004756e  test    rax, rax
0x140047571  jnz     short loc_1400475A6
0x140047573  lea     ebx, [rax+8]
0x140047576  mov     rcx, cs:WPP_GLOBAL_Control
0x14004757d  lea     r14, WPP_GLOBAL_Control
0x140047584  cmp     rcx, r14
0x140047587  jz      loc_14004787D
0x14004758d  test    byte ptr [rcx+1Ch], 4
0x140047591  jz      loc_14004787D
0x140047597  cmp     [rcx+19h], dil
0x14004759b  jb      loc_14004787D
0x1400475a1  lea     edx, [rax+31h]
0x1400475a4  jmp     short loc_140047544
0x1400475a6  mov     rcx, cs:UserName; unsigned __int16 *
0x1400475ad  test    rcx, rcx
0x1400475b0  jz      short loc_1400475F6
0x1400475b2  call    StringDup
0x1400475b7  mov     [rsi+30h], rax
0x1400475bb  test    rax, rax
0x1400475be  jnz     short loc_1400475F6
0x1400475c0  lea     ebx, [rax+8]
0x1400475c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400475ca  lea     r14, WPP_GLOBAL_Control
0x1400475d1  cmp     rcx, r14
0x1400475d4  jz      loc_14004787D
0x1400475da  test    byte ptr [rcx+1Ch], 4
0x1400475de  jz      loc_14004787D
0x1400475e4  cmp     [rcx+19h], dil
0x1400475e8  jb      loc_14004787D
0x1400475ee  lea     edx, [rax+32h]
0x1400475f1  jmp     loc_140047544
0x1400475f6  mov     r9d, 2001Fh
0x1400475fc  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax\\Receipts"
0x140047603  xor     r8d, r8d
0x140047606  mov     rcx, 0FFFFFFFF80000002h
0x14004760d  call    OpenRegistryKey
0x140047612  mov     r15, rax
0x140047615  test    rax, rax
0x140047618  jnz     short loc_14004766F
0x14004761a  call    cs:__imp_GetLastError
0x140047621  nop     dword ptr [rax+rax+00h]
0x140047626  mov     ebx, eax
0x140047628  mov     rcx, cs:WPP_GLOBAL_Control
0x14004762f  lea     r14, WPP_GLOBAL_Control
0x140047636  cmp     rcx, r14
0x140047639  jz      loc_14004787D
0x14004763f  test    byte ptr [rcx+1Ch], 4
0x140047643  jz      loc_14004787D
0x140047649  cmp     [rcx+19h], dil
0x14004764d  jb      loc_14004787D
0x140047653  mov     rcx, [rcx+10h]
0x140047657  lea     edx, [r15+33h]
0x14004765b  mov     r9d, eax
0x14004765e  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140047665  call    WPP_SF_d
0x14004766a  jmp     loc_14004787D
0x14004766f  lea     r8, Class
0x140047676  mov     qword ptr [rsp+730h+domainBufferSize], 0; __int64
0x14004767f  mov     rcx, rax; hKey
0x140047682  call    GetRegistrySecureString
0x140047687  mov     [rsi+38h], rax
0x14004768b  test    rax, rax
0x14004768e  jnz     short loc_1400476C6
0x140047690  lea     ebx, [rax+8]
0x140047693  mov     rcx, cs:WPP_GLOBAL_Control
0x14004769a  lea     r14, WPP_GLOBAL_Control
0x1400476a1  cmp     rcx, r14
0x1400476a4  jz      loc_14004787D
0x1400476aa  test    byte ptr [rcx+1Ch], 4
0x1400476ae  jz      loc_14004787D
0x1400476b4  cmp     [rcx+19h], dil
0x1400476b8  jb      loc_14004787D
0x1400476be  lea     edx, [rax+34h]
0x1400476c1  jmp     loc_140047544
0x1400476c6  xor     ebx, ebx
0x1400476c8  test    r14d, r14d
0x1400476cb  jz      loc_140047872
0x1400476d1  cmp     cs:dword_1400A7648, edi
0x1400476d7  jnz     loc_140047872
0x1400476dd  mov     rcx, cs:hObject
0x1400476e4  mov     [rsp+730h+DuplicateTokenHandle], rbx
0x1400476e9  test    rcx, rcx
0x1400476ec  jnz     loc_140047818
0x1400476f2  xor     edx, edx; Val
0x1400476f4  mov     [rsp+730h+ExistingTokenHandle], rbx
0x1400476f9  mov     r8d, 402h; Size
0x1400476ff  lea     rcx, [rbp+630h+user]; void *
0x140047706  call    memset_0
0x14004770b  xor     edx, edx; Val
0x14004770d  lea     rcx, [rsp+730h+domain]; void *
0x140047712  mov     r8d, 2A2h; Size
0x140047718  call    memset_0
0x14004771d  mov     rcx, cs:UserName; UserName
0x140047724  lea     r9, [rsp+730h+domain]; domain
0x140047729  mov     r8d, 201h; userBufferSize
0x14004772f  mov     [rsp+730h+domainBufferSize], 151h; domainBufferSize
0x140047737  lea     rdx, [rbp+630h+user]; user
0x14004773e  call    cs:__imp_CredUIParseUserNameW
0x140047745  nop     dword ptr [rax+rax+00h]
0x14004774a  mov     ebx, eax
0x14004774c  test    eax, eax
0x14004774e  jz      short loc_140047798
0x140047750  mov     rcx, cs:WPP_GLOBAL_Control
0x140047757  lea     r14, WPP_GLOBAL_Control
0x14004775e  cmp     rcx, r14
0x140047761  jz      loc_14004787D
0x140047767  test    byte ptr [rcx+1Ch], 4
0x14004776b  jz      loc_14004787D
0x140047771  cmp     [rcx+19h], dil
0x140047775  jb      loc_14004787D
0x14004777b  mov     edx, 35h ; '5'
0x140047780  mov     rcx, [rcx+10h]
0x140047784  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x14004778b  mov     r9d, eax
0x14004778e  call    WPP_SF_d
0x140047793  jmp     loc_14004787D
0x140047798  mov     r8, [rsi+38h]; lpszPassword
0x14004779c  lea     rax, [rsp+730h+ExistingTokenHandle]
0x1400477a1  mov     [rsp+730h+phToken], rax; phToken
0x1400477a6  lea     rdx, [rsp+730h+domain]; lpszDomain
0x1400477ab  mov     r9d, edi; dwLogonType
0x1400477ae  mov     [rsp+730h+domainBufferSize], 0; dwLogonProvider
0x1400477b6  lea     rcx, [rbp+630h+user]; lpszUsername
0x1400477bd  call    cs:__imp_LogonUserW
0x1400477c4  nop     dword ptr [rax+rax+00h]
0x1400477c9  test    eax, eax
0x1400477cb  jnz     short loc_14004780C
0x1400477cd  call    cs:__imp_GetLastError
0x1400477d4  nop     dword ptr [rax+rax+00h]
0x1400477d9  mov     ebx, eax
0x1400477db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400477e2  lea     r14, WPP_GLOBAL_Control
0x1400477e9  cmp     rcx, r14
0x1400477ec  jz      loc_14004787D
0x1400477f2  test    byte ptr [rcx+1Ch], 4
0x1400477f6  jz      loc_14004787D
0x1400477fc  cmp     [rcx+19h], dil
0x140047800  jb      short loc_14004787D
0x140047802  mov     edx, 36h ; '6'
0x140047807  jmp     loc_140047780
0x14004780c  mov     rcx, [rsp+730h+ExistingTokenHandle]; ExistingTokenHandle
0x140047811  mov     cs:hObject, rcx
0x140047818  lea     r8, [rsp+730h+DuplicateTokenHandle]; DuplicateTokenHandle
0x14004781d  mov     edx, 3; ImpersonationLevel
0x140047822  call    cs:__imp_DuplicateToken
0x140047829  nop     dword ptr [rax+rax+00h]
0x14004782e  test    eax, eax
0x140047830  jnz     short loc_140047869
0x140047832  call    cs:__imp_GetLastError
0x140047839  nop     dword ptr [rax+rax+00h]
0x14004783e  mov     ebx, eax
0x140047840  mov     rcx, cs:WPP_GLOBAL_Control
0x140047847  lea     r14, WPP_GLOBAL_Control
0x14004784e  cmp     rcx, r14
0x140047851  jz      short loc_14004787D
0x140047853  test    byte ptr [rcx+1Ch], 4
0x140047857  jz      short loc_14004787D
0x140047859  cmp     [rcx+19h], dil
0x14004785d  jb      short loc_14004787D
0x14004785f  mov     edx, 37h ; '7'
0x140047864  jmp     loc_140047780
0x140047869  mov     rax, [rsp+730h+DuplicateTokenHandle]
0x14004786e  mov     [rsi+48h], rax
0x140047872  mov     [r12], rsi
0x140047876  lea     r14, WPP_GLOBAL_Control
0x14004787d  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140047884  call    cs:__imp_LeaveCriticalSection
0x14004788b  nop     dword ptr [rax+rax+00h]
0x140047890  test    r15, r15
0x140047893  jz      short loc_1400478D8
0x140047895  mov     rcx, r15; hKey
0x140047898  call    cs:__imp_RegCloseKey
0x14004789f  nop     dword ptr [rax+rax+00h]
0x1400478a4  test    eax, eax
0x1400478a6  jz      short loc_1400478D8
0x1400478a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400478af  cmp     rcx, r14
0x1400478b2  jz      short loc_1400478D8
0x1400478b4  test    byte ptr [rcx+1Ch], 4
0x1400478b8  jz      short loc_1400478D8
0x1400478ba  cmp     [rcx+19h], dil
0x1400478be  jb      short loc_1400478D8
0x1400478c0  mov     rcx, [rcx+10h]
0x1400478c4  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x1400478cb  mov     edx, 38h ; '8'
0x1400478d0  mov     r9d, eax
0x1400478d3  call    WPP_SF_d
0x1400478d8  test    ebx, ebx
0x1400478da  jz      short loc_1400478E9
0x1400478dc  mov     edx, 1
0x1400478e1  mov     rcx, rsi; lpMem
0x1400478e4  call    FreeReceiptsConfiguration
0x1400478e9  mov     eax, ebx
0x1400478eb  mov     rcx, [rbp+630h+var_30]
0x1400478f2  xor     rcx, rsp; StackCookie
0x1400478f5  call    __security_check_cookie
0x1400478fa  lea     r11, [rsp+730h+var_20]
0x140047902  mov     rbx, [r11+38h]
0x140047906  mov     rsi, [r11+40h]
0x14004790a  mov     rsp, r11
0x14004790d  pop     r15
0x14004790f  pop     r14
0x140047911  pop     r12
0x140047913  pop     rdi
0x140047914  pop     rbp
0x140047915  retn
```
