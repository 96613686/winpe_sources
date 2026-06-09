# GetAirplaneModeFromRegistry

- ea: `0x180005750`
- end: `0x180005a67`
- name: `GetAirplaneModeFromRegistry`
- size: `791`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003d50`
- `0x180005750`
- `0x180005a70`
- `0x180005aec`
- `0x18000d2a0`
- `0x18000df4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180005986`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180005986`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800059a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800059a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a5c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800058f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800058f8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800057e3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800057e3`

## pseudocode

```c
_BOOL8 GetAirplaneModeFromRegistry()
{
  HKEY v0; // rdi
  bool v1; // bp
  int PersistedRegistryLocationW; // eax
  HKEY v3; // rdx
  wchar_t *v4; // r8
  unsigned int v5; // r9d
  unsigned __int64 v6; // r15
  __int64 v7; // r14
  unsigned __int64 v8; // rbx
  unsigned __int64 i; // rsi
  unsigned __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // r15
  _QWORD v15[3]; // [rsp+30h] [rbp-278h] BYREF
  DWORD Type; // [rsp+48h] [rbp-260h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-25Ch] BYREF
  DWORD cbData[4]; // [rsp+50h] [rbp-258h] BYREF
  wchar_t v19[264]; // [rsp+60h] [rbp-248h] BYREF

  v0 = 0;
  memset(v15, 0, sizeof(v15));
  v1 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 110, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
  }
  memset_0(v19, 0, 0x208u);
  Type = 0;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"RmSvcRoot",
                                 L"SYSTEM\\CurrentControlSet\\Control\\RadioManagement\\SystemRadioState",
                                 v19,
                                 520,
                                 &Type);
  v6 = (unsigned __int64)Type >> 1;
  if ( !PersistedRegistryLocationW )
  {
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( v19[v8] );
    for ( i = 0; i < v8; ++i )
    {
      if ( !(unsigned int)_o__wcsnicmp(
                            &v19[i],
                            L"SYSTEM\\CurrentControlSet\\Control\\RadioManagement\\SystemRadioState",
                            v8 - i) )
        break;
    }
    v10 = v8 - i;
    if ( v10 - 1 > 0x3F )
      goto LABEL_7;
    v4 = &aSystemCurrentc[v10];
    do
      ++v7;
    while ( v4[v7] );
    v14 = v7 + v6;
    if ( v14 <= 0x104 )
    {
      PersistedRegistryLocationW = _o_wcscat_s(v19, v14);
      if ( !PersistedRegistryLocationW )
      {
LABEL_7:
        PersistedRegistryLocationW = ATL::CRegKey::Open((ATL::CRegKey *)v15, v3, v19, v5);
        v0 = (HKEY)v15[0];
      }
    }
    else
    {
      PersistedRegistryLocationW = 234;
    }
  }
  if ( PersistedRegistryLocationW )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_10;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 4u )
      goto LABEL_27;
    v13 = 112;
    goto LABEL_40;
  }
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData[0] = 4;
  if ( !RegQueryValueExW(v0, 0, 0, &Type, Data, cbData) && Type == 4 )
  {
    v1 = *(_DWORD *)Data == 1;
LABEL_26:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v11 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_10;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    v13 = 111;
LABEL_40:
    WPP_SF_(*(_QWORD *)(v11 + 16), v13, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
    goto LABEL_26;
  }
LABEL_27:
  if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_BYTE *)(v11 + 28) & 1) != 0 && *(_BYTE *)(v11 + 25) >= 4u )
    WPP_SF_l(*(_QWORD *)(v11 + 16), v3, v4, v1);
LABEL_10:
  if ( v0 )
    RegCloseKey(v0);
  return v1;
}

```

## disassembly

```asm
0x180005750  mov     r11, rsp
0x180005753  push    rbp
0x180005754  push    rdi
0x180005755  sub     rsp, 298h
0x18000575c  mov     rax, cs:__security_cookie
0x180005763  xor     rax, rsp
0x180005766  mov     [rsp+2A8h+var_38], rax
0x18000576e  mov     [r11+18h], r12
0x180005772  xor     r12d, r12d
0x180005775  mov     [r11-18h], r13
0x180005779  mov     edi, r12d
0x18000577c  mov     [rsp+2A8h+var_278], r12
0x180005781  xor     bpl, bpl
0x180005784  mov     [rsp+2A8h+var_270], r12
0x180005789  mov     [rsp+2A8h+var_268], r12
0x18000578e  mov     [r11-28h], r15
0x180005792  mov     rcx, cs:WPP_GLOBAL_Control
0x180005799  lea     r13, WPP_GLOBAL_Control
0x1800057a0  cmp     rcx, r13
0x1800057a3  jnz     loc_180005934
0x1800057a9  xor     edx, edx; Val
0x1800057ab  lea     rcx, [rsp+2A8h+var_248]; void *
0x1800057b0  mov     r8d, 208h; Size
0x1800057b6  call    memset_0
0x1800057bb  lea     rax, [rsp+2A8h+Type]
0x1800057c0  mov     [rsp+2A8h+Type], r12d
0x1800057c5  mov     r9d, 208h
0x1800057cb  mov     [rsp+2A8h+lpData], rax
0x1800057d0  lea     r8, [rsp+2A8h+var_248]
0x1800057d5  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Rad"...
0x1800057dc  lea     rcx, aRmsvcroot; "RmSvcRoot"
0x1800057e3  call    cs:__imp_GetPersistedRegistryLocationW
0x1800057e9  mov     r15d, [rsp+2A8h+Type]
0x1800057ee  shr     r15, 1
0x1800057f1  test    eax, eax
0x1800057f3  jnz     short loc_180005872
0x1800057f5  mov     [rsp+2A8h+arg_0], rbx
0x1800057fd  lea     rax, [rsp+2A8h+var_248]
0x180005802  mov     [rsp+2A8h+arg_8], rsi
0x18000580a  mov     [rsp+2A8h+var_20], r14
0x180005812  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180005819  mov     rbx, r14
0x18000581c  nop     dword ptr [rax+00h]
0x180005820  inc     rbx
0x180005823  cmp     [rax+rbx*2], di
0x180005827  jnz     short loc_180005820
0x180005829  mov     rsi, r12
0x18000582c  test    rbx, rbx
0x18000582f  jnz     loc_180005970
0x180005835  sub     rbx, rsi
0x180005838  mov     rsi, [rsp+2A8h+arg_8]
0x180005840  lea     rax, [rbx-1]
0x180005844  cmp     rax, 3Fh ; '?'
0x180005848  jbe     loc_1800059F2
0x18000584e  lea     r8, [rsp+2A8h+var_248]; wchar_t *
0x180005853  lea     rcx, [rsp+2A8h+var_278]; this
0x180005858  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000585d  mov     rdi, [rsp+2A8h+var_278]
0x180005862  mov     rbx, [rsp+2A8h+arg_0]
0x18000586a  mov     r14, [rsp+2A8h+var_20]
0x180005872  mov     r15, [rsp+2A8h+var_28]
0x18000587a  test    eax, eax
0x18000587c  jz      short loc_1800058C5
0x18000587e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005885  cmp     rcx, r13
0x180005888  jnz     loc_180005A33
0x18000588e  mov     r13, [rsp+2A8h+var_18]
0x180005896  mov     r12, [rsp+2A8h+arg_10]
0x18000589e  test    rdi, rdi
0x1800058a1  jnz     loc_180005A59
0x1800058a7  movzx   eax, bpl
0x1800058ab  mov     rcx, [rsp+2A8h+var_38]
0x1800058b3  xor     rcx, rsp; StackCookie
0x1800058b6  call    __security_check_cookie
0x1800058bb  add     rsp, 298h
0x1800058c2  pop     rdi
0x1800058c3  pop     rbp
0x1800058c4  retn
0x1800058c5  lea     rax, [rsp+2A8h+cbData]
0x1800058ca  mov     dword ptr [rsp+2A8h+Data], r12d
0x1800058cf  mov     [rsp+2A8h+lpcbData], rax; lpcbData
0x1800058d4  lea     r9, [rsp+2A8h+Type]; lpType
0x1800058d9  lea     rax, [rsp+2A8h+Data]
0x1800058de  mov     [rsp+2A8h+Type], r12d
0x1800058e3  xor     r8d, r8d; lpReserved
0x1800058e6  mov     [rsp+2A8h+lpData], rax; lpData
0x1800058eb  xor     edx, edx; lpValueName
0x1800058ed  mov     [rsp+2A8h+cbData], 4
0x1800058f5  mov     rcx, rdi; hKey
0x1800058f8  call    cs:__imp_RegQueryValueExW
0x1800058fe  test    eax, eax
0x180005900  jz      loc_180005A1D
0x180005906  mov     rcx, cs:WPP_GLOBAL_Control
0x18000590d  cmp     rcx, r13
0x180005910  jz      loc_18000588E
0x180005916  test    byte ptr [rcx+1Ch], 1
0x18000591a  jz      loc_1800059C3
0x180005920  cmp     byte ptr [rcx+19h], 4
0x180005924  jb      loc_1800059C3
0x18000592a  mov     edx, 6Fh ; 'o'
0x18000592f  jmp     loc_180005A44
0x180005934  test    byte ptr [rcx+1Ch], 1
0x180005938  jz      loc_1800057A9
0x18000593e  cmp     byte ptr [rcx+19h], 4
0x180005942  jb      loc_1800057A9
0x180005948  mov     rcx, [rcx+10h]
0x18000594c  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180005953  mov     edx, 6Eh ; 'n'
0x180005958  call    WPP_SF_
0x18000595d  jmp     loc_1800057A9
0x180005970  mov     r8, rbx
0x180005973  lea     rcx, [rsp+2A8h+var_248]
0x180005978  sub     r8, rsi
0x18000597b  lea     rcx, [rcx+rsi*2]
0x18000597f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Rad"...
0x180005986  call    cs:__imp__o__wcsnicmp
0x18000598c  test    eax, eax
0x18000598e  jz      loc_180005835
0x180005994  inc     rsi
0x180005997  cmp     rsi, rbx
0x18000599a  jb      short loc_180005970
0x18000599c  jmp     loc_180005835
0x1800059a1  mov     rdx, r15
0x1800059a4  lea     rcx, [rsp+2A8h+var_248]
0x1800059a9  call    cs:__imp__o_wcscat_s
0x1800059af  test    eax, eax
0x1800059b1  jnz     loc_180005862
0x1800059b7  jmp     loc_18000584E
0x1800059bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059c3  cmp     rcx, r13
0x1800059c6  jz      loc_18000588E
0x1800059cc  test    byte ptr [rcx+1Ch], 1
0x1800059d0  jz      loc_18000588E
0x1800059d6  cmp     byte ptr [rcx+19h], 4
0x1800059da  jb      loc_18000588E
0x1800059e0  mov     rcx, [rcx+10h]
0x1800059e4  movzx   r9d, bpl
0x1800059e8  call    WPP_SF_l
0x1800059ed  jmp     loc_18000588E
0x1800059f2  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Rad"...
0x1800059f9  lea     r8, [rax+rbx*2]
0x1800059fd  inc     r14
0x180005a00  cmp     [r8+r14*2], di
0x180005a05  jnz     short loc_1800059FD
0x180005a07  add     r15, r14
0x180005a0a  cmp     r15, 104h
0x180005a11  jbe     short loc_1800059A1
0x180005a13  mov     eax, 0EAh
0x180005a18  jmp     loc_180005862
0x180005a1d  cmp     [rsp+2A8h+Type], 4
0x180005a22  jnz     loc_180005906
0x180005a28  cmp     dword ptr [rsp+2A8h+Data], 1
0x180005a2d  setz    bpl
0x180005a31  jmp     short loc_1800059BC
0x180005a33  test    byte ptr [rcx+1Ch], 1
0x180005a37  jz      short loc_1800059C3
0x180005a39  cmp     byte ptr [rcx+19h], 4
0x180005a3d  jb      short loc_1800059C3
0x180005a3f  mov     edx, 70h ; 'p'
0x180005a44  mov     rcx, [rcx+10h]
0x180005a48  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180005a4f  call    WPP_SF_
0x180005a54  jmp     loc_1800059BC
0x180005a59  mov     rcx, rdi; hKey
0x180005a5c  call    cs:__imp_RegCloseKey
0x180005a62  jmp     loc_1800058A7
```
