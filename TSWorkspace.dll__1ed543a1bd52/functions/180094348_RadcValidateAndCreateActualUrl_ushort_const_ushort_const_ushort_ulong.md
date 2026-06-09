# RadcValidateAndCreateActualUrl(ushort const *,ushort const *,ushort *,ulong)

- ea: `0x180094348`
- end: `0x18009473f`
- name: `?RadcValidateAndCreateActualUrl@@YAJPEBG0PEAGK@Z`
- size: `1015`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180090580`

## callees

- `0x1800044bf`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001a008`
- `0x180094148`
- `0x1800941c4`
- `0x180094348`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800946dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800946dc`
- `WINHTTP!WinHttpCrackUrl` at `0x180094566`
- `WINHTTP!WinHttpCrackUrl` at `0x180094566`
- `WINHTTP!WinHttpCreateUrl` at `0x1800946d2`
- `WINHTTP!WinHttpCreateUrl` at `0x1800946d2`

## string_xrefs

- `0x18009452a`: `RadcCombineUrl failed`

## pseudocode

```c
__int64 __fastcall RadcValidateAndCreateActualUrl(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  unsigned int ActivityIdPrefix; // eax
  __int64 v9; // rdx
  int LastError; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  DWORD pdwUrlLength[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pwszUrl[2088]; // [rsp+B0h] [rbp-50h] BYREF

  pdwUrlLength[0] = 2084;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v6, v7);
    v9 = 14;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids,
      ActivityIdPrefix,
      -2147024809);
    return (unsigned int)-2147024809;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v6, v7);
    v9 = 15;
    goto LABEL_6;
  }
  LastError = CheckUrlLength(a1);
  if ( LastError < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v11, v12);
      v14 = 17;
      v15 = "CheckUrlLength(base URL) failed";
LABEL_18:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids,
        v13,
        (__int64)v15,
        LastError,
        *(_QWORD *)pdwUrlLength);
      return (unsigned int)LastError;
    }
    return (unsigned int)LastError;
  }
  if ( !a2 || (LastError = CheckUrlLength(a2), LastError >= 0) )
  {
    LastError = RadcCombineUrl(a1, a2, pwszUrl);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v18, v19);
        v14 = 19;
        v15 = "RadcCombineUrl failed";
        goto LABEL_18;
      }
      return (unsigned int)LastError;
    }
    UrlComponents.dwStructSize = 104;
    UrlComponents.dwSchemeLength = 1;
    UrlComponents.dwHostNameLength = 1;
    UrlComponents.dwUserNameLength = 1;
    UrlComponents.dwPasswordLength = 1;
    UrlComponents.dwUrlPathLength = 1;
    UrlComponents.dwExtraInfoLength = 1;
    if ( !WinHttpCrackUrl(pwszUrl, 0, 0, &UrlComponents) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v24 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v22, v23);
      v25 = 20;
      goto LABEL_35;
    }
    if ( UrlComponents.lpszHostName )
    {
      if ( UrlComponents.dwHostNameLength )
      {
        if ( UrlComponents.nScheme != INTERNET_SCHEME_GOPHER )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v28 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v20, v21);
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids,
              v28,
              -2147220735);
          }
          return (unsigned int)-2147220735;
        }
        if ( WinHttpCreateUrl(&UrlComponents, 0, a3, pdwUrlLength) )
          return 0;
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_36:
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          if ( LastError >= 0 )
            return (unsigned int)-2147467259;
          return (unsigned int)LastError;
        }
        v24 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v29, v30);
        v25 = 24;
LABEL_35:
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25,
          WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids,
          v24,
          LastError);
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147012891;
      }
      v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v20, v21);
      v27 = 22;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)-2147012891;
      }
      v26 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v20, v21);
      v27 = 21;
    }
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v27,
      WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids,
      v26,
      -2147012891);
    return (unsigned int)-2147012891;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v16, v17);
    v14 = 18;
    v15 = "CheckUrlLength failed";
    goto LABEL_18;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180094348  push    rbp
0x18009434a  push    rbx
0x18009434b  push    rsi
0x18009434c  push    rdi
0x18009434d  push    r14
0x18009434f  lea     rbp, [rsp-1010h]
0x180094357  mov     eax, 1110h
0x18009435c  call    _alloca_probe
0x180094361  sub     rsp, rax
0x180094364  mov     rax, cs:__security_cookie
0x18009436b  xor     rax, rsp
0x18009436e  mov     [rbp+1030h+var_30], rax
0x180094375  mov     rdi, rdx
0x180094378  mov     [rsp+1130h+pdwUrlLength], 824h
0x180094380  xor     edx, edx; Val
0x180094382  mov     r14, r8
0x180094385  mov     rsi, rcx
0x180094388  lea     rcx, [rsp+1130h+UrlComponents]; void *
0x18009438d  lea     r8d, [rdx+68h]; Size
0x180094391  call    memset_0
0x180094396  test    rsi, rsi
0x180094399  jnz     short loc_1800943EE
0x18009439b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800943a2  lea     rax, WPP_GLOBAL_Control
0x1800943a9  cmp     rcx, rax
0x1800943ac  jz      short loc_1800943E4
0x1800943ae  test    byte ptr [rcx+1Ch], 8
0x1800943b2  jz      short loc_1800943E4
0x1800943b4  cmp     byte ptr [rcx+19h], 2
0x1800943b8  jb      short loc_1800943E4
0x1800943ba  call    RdpX_GetActivityIdPrefix
0x1800943bf  lea     edx, [rsi+0Eh]
0x1800943c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800943c9  lea     r8, WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids
0x1800943d0  mov     r9d, eax
0x1800943d3  mov     dword ptr [rsp+1130h+var_1110], 80070057h
0x1800943db  mov     rcx, [rcx+10h]
0x1800943df  call    WPP_SF_Dd
0x1800943e4  mov     ebx, 80070057h
0x1800943e9  jmp     loc_180094720
0x1800943ee  test    r14, r14
0x1800943f1  jnz     short loc_18009441D
0x1800943f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800943fa  lea     rax, WPP_GLOBAL_Control
0x180094401  cmp     rcx, rax
0x180094404  jz      short loc_1800943E4
0x180094406  test    byte ptr [rcx+1Ch], 8
0x18009440a  jz      short loc_1800943E4
0x18009440c  cmp     byte ptr [rcx+19h], 2
0x180094410  jb      short loc_1800943E4
0x180094412  call    RdpX_GetActivityIdPrefix
0x180094417  lea     edx, [r14+0Fh]
0x18009441b  jmp     short loc_1800943C2
0x18009441d  mov     rcx, rsi; unsigned __int16 *
0x180094420  call    ?CheckUrlLength@@YAJPEBG@Z; CheckUrlLength(ushort const *)
0x180094425  mov     ebx, eax
0x180094427  test    eax, eax
0x180094429  jns     short loc_18009448F
0x18009442b  mov     rcx, cs:WPP_GLOBAL_Control
0x180094432  lea     rax, WPP_GLOBAL_Control
0x180094439  cmp     rcx, rax
0x18009443c  jz      loc_180094720
0x180094442  test    byte ptr [rcx+1Ch], 8
0x180094446  jz      loc_180094720
0x18009444c  cmp     byte ptr [rcx+19h], 2
0x180094450  jb      loc_180094720
0x180094456  call    RdpX_GetActivityIdPrefix
0x18009445b  mov     edx, 11h
0x180094460  lea     rcx, aCheckurllength_0; "CheckUrlLength(base URL) failed"
0x180094467  mov     [rsp+1130h+var_1108], ebx
0x18009446b  lea     r8, WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids
0x180094472  mov     [rsp+1130h+var_1110], rcx
0x180094477  mov     r9d, eax
0x18009447a  mov     rcx, cs:WPP_GLOBAL_Control
0x180094481  mov     rcx, [rcx+10h]
0x180094485  call    WPP_SF_DsD
0x18009448a  jmp     loc_180094720
0x18009448f  test    rdi, rdi
0x180094492  jz      short loc_1800944E0
0x180094494  mov     rcx, rdi; unsigned __int16 *
0x180094497  call    ?CheckUrlLength@@YAJPEBG@Z; CheckUrlLength(ushort const *)
0x18009449c  mov     ebx, eax
0x18009449e  test    eax, eax
0x1800944a0  jns     short loc_1800944E0
0x1800944a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800944a9  lea     rax, WPP_GLOBAL_Control
0x1800944b0  cmp     rcx, rax
0x1800944b3  jz      loc_180094720
0x1800944b9  test    byte ptr [rcx+1Ch], 8
0x1800944bd  jz      loc_180094720
0x1800944c3  cmp     byte ptr [rcx+19h], 2
0x1800944c7  jb      loc_180094720
0x1800944cd  call    RdpX_GetActivityIdPrefix
0x1800944d2  mov     edx, 12h
0x1800944d7  lea     rcx, aCheckurllength; "CheckUrlLength failed"
0x1800944de  jmp     short loc_180094467
0x1800944e0  lea     r8, [rbp+1030h+pwszUrl]; unsigned __int16 *
0x1800944e4  mov     rdx, rdi; unsigned __int16 *
0x1800944e7  mov     rcx, rsi; unsigned __int16 *
0x1800944ea  call    ?RadcCombineUrl@@YAJPEBG0PEAGK@Z; RadcCombineUrl(ushort const *,ushort const *,ushort *,ulong)
0x1800944ef  mov     ebx, eax
0x1800944f1  test    eax, eax
0x1800944f3  jns     short loc_180094536
0x1800944f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800944fc  lea     rax, WPP_GLOBAL_Control
0x180094503  cmp     rcx, rax
0x180094506  jz      loc_180094720
0x18009450c  test    byte ptr [rcx+1Ch], 8
0x180094510  jz      loc_180094720
0x180094516  cmp     byte ptr [rcx+19h], 2
0x18009451a  jb      loc_180094720
0x180094520  call    RdpX_GetActivityIdPrefix
0x180094525  mov     edx, 13h
0x18009452a  lea     rcx, aRadccombineurl; "RadcCombineUrl failed"
0x180094531  jmp     loc_180094467
0x180094536  mov     eax, 1
0x18009453b  mov     [rsp+1130h+UrlComponents.dwStructSize], 68h ; 'h'
0x180094543  lea     r9, [rsp+1130h+UrlComponents]; lpUrlComponents
0x180094548  mov     [rsp+1130h+UrlComponents.dwSchemeLength], eax
0x18009454c  xor     r8d, r8d; dwFlags
0x18009454f  mov     [rsp+1130h+UrlComponents.dwHostNameLength], eax
0x180094553  xor     edx, edx; dwUrlLength
0x180094555  mov     [rsp+1130h+UrlComponents.dwUserNameLength], eax
0x180094559  lea     rcx, [rbp+1030h+pwszUrl]; pwszUrl
0x18009455d  mov     [rbp+1030h+UrlComponents.dwPasswordLength], eax
0x180094560  mov     [rbp+1030h+UrlComponents.dwUrlPathLength], eax
0x180094563  mov     [rbp+1030h+UrlComponents.dwExtraInfoLength], eax
0x180094566  call    cs:__imp_WinHttpCrackUrl
0x18009456c  test    eax, eax
0x18009456e  jnz     short loc_1800945DB
0x180094570  call    cs:__imp_GetLastError
0x180094576  mov     ebx, eax
0x180094578  mov     rcx, cs:WPP_GLOBAL_Control
0x18009457f  lea     rax, WPP_GLOBAL_Control
0x180094586  cmp     rcx, rax
0x180094589  jz      short loc_1800945BF
0x18009458b  test    byte ptr [rcx+1Ch], 8
0x18009458f  jz      short loc_1800945BF
0x180094591  cmp     byte ptr [rcx+19h], 2
0x180094595  jb      short loc_1800945BF
0x180094597  call    RdpX_GetActivityIdPrefix
0x18009459c  mov     edx, 14h
0x1800945a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800945a8  lea     r8, WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids
0x1800945af  mov     r9d, eax
0x1800945b2  mov     dword ptr [rsp+1130h+var_1110], ebx
0x1800945b6  mov     rcx, [rcx+10h]
0x1800945ba  call    WPP_SF_Dd
0x1800945bf  test    ebx, ebx
0x1800945c1  jle     short loc_1800945CC
0x1800945c3  movzx   ebx, bx
0x1800945c6  or      ebx, 80070000h
0x1800945cc  test    ebx, ebx
0x1800945ce  mov     eax, 80004005h
0x1800945d3  cmovns  ebx, eax
0x1800945d6  jmp     loc_180094720
0x1800945db  cmp     [rsp+1130h+UrlComponents.lpszHostName], 0
0x1800945e1  jnz     short loc_180094638
0x1800945e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800945ea  lea     rax, WPP_GLOBAL_Control
0x1800945f1  cmp     rcx, rax
0x1800945f4  jz      short loc_18009462E
0x1800945f6  test    byte ptr [rcx+1Ch], 8
0x1800945fa  jz      short loc_18009462E
0x1800945fc  cmp     byte ptr [rcx+19h], 2
0x180094600  jb      short loc_18009462E
0x180094602  call    RdpX_GetActivityIdPrefix
0x180094607  mov     edx, 15h
0x18009460c  mov     rcx, cs:WPP_GLOBAL_Control
0x180094613  lea     r8, WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids
0x18009461a  mov     r9d, eax
0x18009461d  mov     dword ptr [rsp+1130h+var_1110], 80072EE5h
0x180094625  mov     rcx, [rcx+10h]
0x180094629  call    WPP_SF_Dd
0x18009462e  mov     ebx, 80072EE5h
0x180094633  jmp     loc_180094720
0x180094638  cmp     [rsp+1130h+UrlComponents.dwHostNameLength], 0
0x18009463d  ja      short loc_18009466A
0x18009463f  mov     rcx, cs:WPP_GLOBAL_Control
0x180094646  lea     rax, WPP_GLOBAL_Control
0x18009464d  cmp     rcx, rax
0x180094650  jz      short loc_18009462E
0x180094652  test    byte ptr [rcx+1Ch], 8
0x180094656  jz      short loc_18009462E
0x180094658  cmp     byte ptr [rcx+19h], 2
0x18009465c  jb      short loc_18009462E
0x18009465e  call    RdpX_GetActivityIdPrefix
0x180094663  mov     edx, 16h
0x180094668  jmp     short loc_18009460C
0x18009466a  cmp     [rsp+1130h+UrlComponents.nScheme], 2
0x18009466f  jz      short loc_1800946C3
0x180094671  mov     rcx, cs:WPP_GLOBAL_Control
0x180094678  lea     rax, WPP_GLOBAL_Control
0x18009467f  cmp     rcx, rax
0x180094682  jz      short loc_1800946BC
0x180094684  test    byte ptr [rcx+1Ch], 8
0x180094688  jz      short loc_1800946BC
0x18009468a  cmp     byte ptr [rcx+19h], 2
0x18009468e  jb      short loc_1800946BC
0x180094690  call    RdpX_GetActivityIdPrefix
0x180094695  mov     rcx, cs:WPP_GLOBAL_Control
0x18009469c  lea     r8, WPP_835e04ea44c03c1b6a011e7f508d53be_Traceguids
0x1800946a3  mov     edx, 17h
0x1800946a8  mov     dword ptr [rsp+1130h+var_1110], 80040301h
0x1800946b0  mov     r9d, eax
0x1800946b3  mov     rcx, [rcx+10h]
0x1800946b7  call    WPP_SF_Dd
0x1800946bc  mov     ebx, 80040301h
0x1800946c1  jmp     short loc_180094720
0x1800946c3  lea     r9, [rsp+1130h+pdwUrlLength]; pdwUrlLength
0x1800946c8  mov     r8, r14; pwszUrl
0x1800946cb  xor     edx, edx; dwFlags
0x1800946cd  lea     rcx, [rsp+1130h+UrlComponents]; lpUrlComponents
0x1800946d2  call    cs:__imp_WinHttpCreateUrl
0x1800946d8  test    eax, eax
0x1800946da  jnz     short loc_18009471E
0x1800946dc  call    cs:__imp_GetLastError
0x1800946e2  mov     ebx, eax
0x1800946e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800946eb  lea     rax, WPP_GLOBAL_Control
0x1800946f2  cmp     rcx, rax
0x1800946f5  jz      loc_1800945BF
0x1800946fb  test    byte ptr [rcx+1Ch], 8
0x1800946ff  jz      loc_1800945BF
0x180094705  cmp     byte ptr [rcx+19h], 2
0x180094709  jb      loc_1800945BF
0x18009470f  call    RdpX_GetActivityIdPrefix
0x180094714  mov     edx, 18h
0x180094719  jmp     loc_1800945A1
0x18009471e  xor     ebx, ebx
0x180094720  mov     eax, ebx
0x180094722  mov     rcx, [rbp+1030h+var_30]
0x180094729  xor     rcx, rsp; StackCookie
0x18009472c  call    __security_check_cookie
0x180094731  add     rsp, 1110h
0x180094738  pop     r14
0x18009473a  pop     rdi
0x18009473b  pop     rsi
0x18009473c  pop     rbx
0x18009473d  pop     rbp
0x18009473e  retn
```
