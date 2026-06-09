# InitializeCNG

- ea: `0x18000a768`
- end: `0x18000a865`
- name: `InitializeCNG`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a4e0`

## callees

- `0x180007a7c`
- `0x180009764`
- `0x18000a768`
- `0x18000a978`
- `0x18000ab58`
- `0x18000b094`
- `0x1800129ac`
- `0x180016068`

## string_xrefs

- `0x18000a7fc`: `onecore\ds\security\cryptoapi\ncrypt\crypt\bcrypt\init.c`

## pseudocode

```c
__int64 InitializeCNG()
{
  char TrustedEnvironment; // al
  int v1; // edx
  unsigned int v2; // ebx
  int v3; // r8d
  int v4; // edx
  int v5; // r8d
  int v6; // edx
  int v7; // r8d

  SymCryptInitEnvWindowsUsermodeWin8_1nLater();
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 0x18) != 0 )
    goto LABEL_8;
  v2 = InitializeLoader();
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v1,
        v3,
        (unsigned int)"Status",
        v2,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\bcrypt\\init.c",
        153);
    goto LABEL_13;
  }
  dword_180024A88 |= 2u;
  v2 = InitializeConfig();
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v5,
        (unsigned int)"Status",
        v2,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\bcrypt\\init.c",
        162);
    goto LABEL_13;
  }
  dword_180024A88 |= 4u;
  v2 = InitializeSystemPreferredCache();
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        (unsigned int)"Status",
        v2,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\bcrypt\\init.c",
        171);
LABEL_13:
    UninitializeCNG();
    return v2;
  }
  dword_180024A88 |= 8u;
LABEL_8:
  g_fLoadCNGDone = 1;
  return 0;
}

```

## disassembly

```asm
0x18000a768  push    rbx
0x18000a76a  sub     rsp, 40h
0x18000a76e  call    SymCryptInitEnvWindowsUsermodeWin8_1nLater
0x18000a773  mov     eax, cs:g_TrustedEnvironment
0x18000a779  test    eax, eax
0x18000a77b  jz      short loc_18000A7D0
0x18000a77d  test    al, 18h
0x18000a77f  jnz     short loc_18000A7BB
0x18000a781  call    InitializeLoader
0x18000a786  mov     ebx, eax
0x18000a788  test    eax, eax
0x18000a78a  jnz     loc_18000A842
0x18000a790  or      cs:dword_180024A88, 2
0x18000a797  call    InitializeConfig
0x18000a79c  mov     ebx, eax
0x18000a79e  test    eax, eax
0x18000a7a0  jnz     short loc_18000A81F
0x18000a7a2  or      cs:dword_180024A88, 4
0x18000a7a9  call    InitializeSystemPreferredCache
0x18000a7ae  mov     ebx, eax
0x18000a7b0  test    eax, eax
0x18000a7b2  jnz     short loc_18000A7D7
0x18000a7b4  or      cs:dword_180024A88, 8
0x18000a7bb  mov     cs:g_fLoadCNGDone, 1
0x18000a7c5  xor     ebx, ebx
0x18000a7c7  mov     eax, ebx
0x18000a7c9  add     rsp, 40h
0x18000a7cd  pop     rbx
0x18000a7ce  retn
0x18000a7d0  call    GetTrustedEnvironment
0x18000a7d5  jmp     short loc_18000A77D
0x18000a7d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7de  lea     rax, WPP_GLOBAL_Control
0x18000a7e5  cmp     rcx, rax
0x18000a7e8  jz      short loc_18000A818
0x18000a7ea  test    byte ptr [rcx+1Ch], 1
0x18000a7ee  jz      short loc_18000A818
0x18000a7f0  mov     [rsp+48h+var_18], 0ABh
0x18000a7f8  mov     rcx, [rcx+10h]
0x18000a7fc  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a803  mov     [rsp+48h+var_20], rax
0x18000a808  lea     r9, aStatus; "Status"
0x18000a80f  mov     [rsp+48h+var_28], ebx
0x18000a813  call    WPP_SF_sDsd
0x18000a818  call    UninitializeCNG
0x18000a81d  jmp     short loc_18000A7C7
0x18000a81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a826  lea     rax, WPP_GLOBAL_Control
0x18000a82d  cmp     rcx, rax
0x18000a830  jz      short loc_18000A818
0x18000a832  test    byte ptr [rcx+1Ch], 1
0x18000a836  jz      short loc_18000A818
0x18000a838  mov     [rsp+48h+var_18], 0A2h
0x18000a840  jmp     short loc_18000A7F8
0x18000a842  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a849  lea     rax, WPP_GLOBAL_Control
0x18000a850  cmp     rcx, rax
0x18000a853  jz      short loc_18000A818
0x18000a855  test    byte ptr [rcx+1Ch], 1
0x18000a859  jz      short loc_18000A818
0x18000a85b  mov     [rsp+48h+var_18], 99h
0x18000a863  jmp     short loc_18000A7F8
```
