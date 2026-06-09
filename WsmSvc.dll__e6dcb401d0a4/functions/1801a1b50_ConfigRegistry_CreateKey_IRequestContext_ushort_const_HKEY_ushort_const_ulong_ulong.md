# ConfigRegistry::CreateKey(IRequestContext *,ushort const *,HKEY__ * *,ushort const *,ulong,ulong *)

- ea: `0x1801a1b50`
- end: `0x1801a1f1a`
- name: `?CreateKey@ConfigRegistry@@IEAAHPEAVIRequestContext@@PEBGPEAPEAUHKEY__@@1KPEAK@Z`
- size: `970`
- prototype: `__int64 __fastcall(ConfigRegistry *this, struct IRequestContext *, const unsigned __int16 *, HKEY *, const unsigned __int16 *lpSubKey, REGSAM samDesired, unsigned int *lpdwDisposition)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180194088`
- `0x180194548`
- `0x180194b58`
- `0x1801a16a0`

## callees

- `0x180005d10`
- `0x1800bac30`
- `0x1801123a8`
- `0x1801133b0`
- `0x18011a6d4`
- `0x1801a1b50`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801a1d16`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801a1d16`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a1ea3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801a1ea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1d75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1f01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1d75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801a1f01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a1c73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a1de2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a1c73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801a1de2`

## string_xrefs

- `0x1801a1bf0`: `onecore\admin\wmi\wmx\config\configregistry.cpp`

## pseudocode

```c
__int64 __fastcall ConfigRegistry::CreateKey(
        ConfigRegistry *this,
        struct IRequestContext *a2,
        const unsigned __int16 *a3,
        HKEY *a4,
        const unsigned __int16 *lpSubKey,
        REGSAM samDesired,
        unsigned int *lpdwDisposition)
{
  PVOID *v11; // rcx
  const unsigned __int16 *v13; // r14
  unsigned int v14; // eax
  unsigned int v15; // esi
  __int64 v16; // rax
  const unsigned __int16 *v17; // r14
  unsigned int v18; // r14d
  unsigned int v19; // r14d
  __int64 v20; // rdx
  signed __int64 v21; // rdi
  int v22; // ecx
  int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // edi
  HKEY phkResult; // [rsp+50h] [rbp-18h] BYREF
  HKEY v27; // [rsp+58h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+50h] BYREF

  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, a3);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x200000) != 0 )
      WPP_SF_q(v11[2], 47, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, this);
  }
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", 1316, L"1316", 0x54Fu, 0);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", 1317, L"1317", 0x54Fu, a2);
    return 0;
  }
  v13 = lpSubKey;
  if ( !lpSubKey )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", 1318, L"1318", 0x54Fu, a2);
    return 0;
  }
  if ( !a4 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configregistry.cpp", 1319, L"1319", 0x54Fu, a2);
    return 0;
  }
  hKey = 0;
  v27 = 0;
  v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x104u, &hKey);
  if ( v14 )
  {
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD, __int64))(*(_QWORD *)a2 + 64LL))(a2, v14, 1077134410);
LABEL_28:
    v15 = 0;
    goto LABEL_29;
  }
  v15 = 1;
  v16 = -1;
  do
    ++v16;
  while ( v13[v16] );
  v17 = &a3[v16];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, v17 + 1);
  v18 = RegCreateKeyExW(hKey, v17 + 1, 0, 0, 0, samDesired, 0, &v27, lpdwDisposition);
  if ( v18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, v18);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v18);
    goto LABEL_28;
  }
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  if ( !v15 )
  {
    if ( v27 )
      RegCloseKey(v27);
    return v15;
  }
  *a4 = v27;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, a3);
  phkResult = 0;
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x2011Bu, &phkResult);
  if ( v19 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, v19);
    v20 = v19;
  }
  else
  {
    v21 = (char *)a3 - (char *)this;
    do
    {
      v22 = *(unsigned __int16 *)((char *)this + v21);
      v23 = *(unsigned __int16 *)this - v22;
      if ( v23 )
        break;
      this = (ConfigRegistry *)((char *)this + 2);
    }
    while ( v22 );
    if ( v23 )
      goto LABEL_53;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids,
        L"StackVersion");
    v24 = RegSetValueExW(phkResult, L"StackVersion", 0, 1u, L"3.0", 8u);
    v25 = v24;
    if ( !v24 )
      goto LABEL_53;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids, v24);
    v20 = v25;
  }
  (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v20);
  v15 = 0;
LABEL_53:
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
  return v15;
}

```

## disassembly

```asm
0x1801a1b50  push    rbp
0x1801a1b52  push    rbx
0x1801a1b53  push    rsi
0x1801a1b54  push    rdi
0x1801a1b55  push    r12
0x1801a1b57  push    r13
0x1801a1b59  push    r14
0x1801a1b5b  push    r15
0x1801a1b5d  mov     rbp, rsp
0x1801a1b60  sub     rsp, 68h
0x1801a1b64  mov     r12, r9
0x1801a1b67  mov     rdi, r8
0x1801a1b6a  mov     rbx, rdx
0x1801a1b6d  mov     r15, rcx
0x1801a1b70  lea     rsi, WPP_GLOBAL_Control
0x1801a1b77  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1b7e  cmp     rcx, rsi
0x1801a1b81  jz      short loc_1801A1BD1
0x1801a1b83  test    dword ptr [rcx+1Ch], 200000h
0x1801a1b8a  jz      short loc_1801A1BAB
0x1801a1b8c  mov     edx, 2Eh ; '.'
0x1801a1b91  mov     r9, r8
0x1801a1b94  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1b9b  mov     rcx, [rcx+10h]
0x1801a1b9f  call    WPP_SF_S
0x1801a1ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1bab  cmp     rcx, rsi
0x1801a1bae  jz      short loc_1801A1BD1
0x1801a1bb0  test    dword ptr [rcx+1Ch], 200000h
0x1801a1bb7  jz      short loc_1801A1BD1
0x1801a1bb9  mov     edx, 2Fh ; '/'
0x1801a1bbe  mov     r9, r15
0x1801a1bc1  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1bc8  mov     rcx, [rcx+10h]
0x1801a1bcc  call    WPP_SF_q
0x1801a1bd1  xor     r13d, r13d
0x1801a1bd4  test    rbx, rbx
0x1801a1bd7  jnz     short loc_1801A1C03
0x1801a1bd9  mov     [rsp+68h+phkResult], r13; struct IRequestContext *
0x1801a1bde  lea     r8, a1316; "1316"
0x1801a1be5  mov     edx, 524h; unsigned int
0x1801a1bea  mov     r9d, 54Fh; unsigned int
0x1801a1bf0  lea     rcx, aOnecoreAdminWm_29; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1801a1bf7  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801a1bfc  xor     eax, eax
0x1801a1bfe  jmp     loc_1801A1F09
0x1801a1c03  test    rdi, rdi
0x1801a1c06  jnz     short loc_1801A1C1B
0x1801a1c08  mov     [rsp+68h+phkResult], rbx
0x1801a1c0d  lea     r8, a1317; "1317"
0x1801a1c14  mov     edx, 525h
0x1801a1c19  jmp     short loc_1801A1BEA
0x1801a1c1b  mov     r14, [rbp+lpSubKey]
0x1801a1c1f  test    r14, r14
0x1801a1c22  jnz     short loc_1801A1C37
0x1801a1c24  mov     [rsp+68h+phkResult], rbx
0x1801a1c29  lea     r8, a1318; "1318"
0x1801a1c30  mov     edx, 526h
0x1801a1c35  jmp     short loc_1801A1BEA
0x1801a1c37  test    r12, r12
0x1801a1c3a  jnz     short loc_1801A1C4F
0x1801a1c3c  mov     [rsp+68h+phkResult], rbx
0x1801a1c41  lea     r8, a1319; "1319"
0x1801a1c48  mov     edx, 527h
0x1801a1c4d  jmp     short loc_1801A1BEA
0x1801a1c4f  mov     [rbp+hKey], r13
0x1801a1c53  mov     [rbp+var_10], r13
0x1801a1c57  lea     rax, [rbp+hKey]
0x1801a1c5b  mov     [rsp+68h+phkResult], rax; phkResult
0x1801a1c60  mov     r9d, 104h; samDesired
0x1801a1c66  xor     r8d, r8d; ulOptions
0x1801a1c69  mov     rdx, r14; lpSubKey
0x1801a1c6c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a1c73  call    cs:__imp_RegOpenKeyExW
0x1801a1c79  mov     edx, eax
0x1801a1c7b  test    eax, eax
0x1801a1c7d  jz      short loc_1801A1C99
0x1801a1c7f  mov     rcx, [rbx]
0x1801a1c82  mov     rax, [rcx+40h]
0x1801a1c86  mov     r8d, 4033C44Ah
0x1801a1c8c  mov     rcx, rbx
0x1801a1c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1c94  jmp     loc_1801A1D69
0x1801a1c99  mov     esi, 1
0x1801a1c9e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a1ca2  inc     rax
0x1801a1ca5  cmp     [r14+rax*2], r13w
0x1801a1caa  jnz     short loc_1801A1CA2
0x1801a1cac  lea     r14, [rdi+rax*2]
0x1801a1cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1cb7  lea     rax, WPP_GLOBAL_Control
0x1801a1cbe  cmp     rcx, rax
0x1801a1cc1  jz      short loc_1801A1CE5
0x1801a1cc3  test    dword ptr [rcx+1Ch], 200000h
0x1801a1cca  jz      short loc_1801A1CE5
0x1801a1ccc  mov     edx, 30h ; '0'
0x1801a1cd1  lea     r9, [r14+2]
0x1801a1cd5  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1cdc  mov     rcx, [rcx+10h]
0x1801a1ce0  call    WPP_SF_S
0x1801a1ce5  mov     rax, [rbp+arg_30]
0x1801a1ce9  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x1801a1cee  lea     rax, [rbp+var_10]
0x1801a1cf2  mov     [rsp+68h+var_30], rax; phkResult
0x1801a1cf7  mov     [rsp+68h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1801a1cfc  mov     eax, [rbp+arg_28]
0x1801a1cff  mov     [rsp+68h+samDesired], eax; samDesired
0x1801a1d03  mov     dword ptr [rsp+68h+phkResult], r13d; dwOptions
0x1801a1d08  xor     r9d, r9d; lpClass
0x1801a1d0b  xor     r8d, r8d; Reserved
0x1801a1d0e  lea     rdx, [r14+2]; lpSubKey
0x1801a1d12  mov     rcx, [rbp+hKey]; hKey
0x1801a1d16  call    cs:__imp_RegCreateKeyExW
0x1801a1d1c  mov     r14d, eax
0x1801a1d1f  test    eax, eax
0x1801a1d21  jz      short loc_1801A1D6C
0x1801a1d23  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1d2a  lea     rax, WPP_GLOBAL_Control
0x1801a1d31  cmp     rcx, rax
0x1801a1d34  jz      short loc_1801A1D57
0x1801a1d36  test    dword ptr [rcx+1Ch], 200000h
0x1801a1d3d  jz      short loc_1801A1D57
0x1801a1d3f  mov     edx, 31h ; '1'
0x1801a1d44  mov     r9d, r14d
0x1801a1d47  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1d4e  mov     rcx, [rcx+10h]
0x1801a1d52  call    WPP_SF_d
0x1801a1d57  mov     rax, [rbx]
0x1801a1d5a  mov     edx, r14d
0x1801a1d5d  mov     rcx, rbx
0x1801a1d60  mov     rax, [rax+48h]
0x1801a1d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1d69  mov     esi, r13d
0x1801a1d6c  mov     rcx, [rbp+hKey]; hKey
0x1801a1d70  test    rcx, rcx
0x1801a1d73  jz      short loc_1801A1D7B
0x1801a1d75  call    cs:__imp_RegCloseKey
0x1801a1d7b  test    esi, esi
0x1801a1d7d  jz      loc_1801A1EF8
0x1801a1d83  mov     rax, [rbp+var_10]
0x1801a1d87  mov     [r12], rax
0x1801a1d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1d92  lea     rax, WPP_GLOBAL_Control
0x1801a1d99  mov     r12d, 200000h
0x1801a1d9f  cmp     rcx, rax
0x1801a1da2  jz      short loc_1801A1DC2
0x1801a1da4  test    [rcx+1Ch], r12d
0x1801a1da8  jz      short loc_1801A1DC2
0x1801a1daa  mov     edx, 32h ; '2'
0x1801a1daf  mov     r9, rdi
0x1801a1db2  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1db9  mov     rcx, [rcx+10h]
0x1801a1dbd  call    WPP_SF_S
0x1801a1dc2  mov     [rbp+var_18], r13
0x1801a1dc6  lea     rax, [rbp+var_18]
0x1801a1dca  mov     [rsp+68h+phkResult], rax; phkResult
0x1801a1dcf  mov     r9d, 2011Bh; samDesired
0x1801a1dd5  xor     r8d, r8d; ulOptions
0x1801a1dd8  mov     rdx, rdi; lpSubKey
0x1801a1ddb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a1de2  call    cs:__imp_RegOpenKeyExW
0x1801a1de8  mov     r14d, eax
0x1801a1deb  test    eax, eax
0x1801a1ded  jz      short loc_1801A1E28
0x1801a1def  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1df6  lea     rax, WPP_GLOBAL_Control
0x1801a1dfd  cmp     rcx, rax
0x1801a1e00  jz      short loc_1801A1E20
0x1801a1e02  test    [rcx+1Ch], r12d
0x1801a1e06  jz      short loc_1801A1E20
0x1801a1e08  mov     edx, 33h ; '3'
0x1801a1e0d  mov     r9d, r14d
0x1801a1e10  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1e17  mov     rcx, [rcx+10h]
0x1801a1e1b  call    WPP_SF_d
0x1801a1e20  mov     edx, r14d
0x1801a1e23  jmp     loc_1801A1EDB
0x1801a1e28  sub     rdi, r15
0x1801a1e2b  movzx   eax, word ptr [r15]
0x1801a1e2f  movzx   ecx, word ptr [r15+rdi]
0x1801a1e34  sub     eax, ecx
0x1801a1e36  jnz     short loc_1801A1E40
0x1801a1e38  add     r15, 2
0x1801a1e3c  test    ecx, ecx
0x1801a1e3e  jnz     short loc_1801A1E2B
0x1801a1e40  test    eax, eax
0x1801a1e42  jnz     loc_1801A1EED
0x1801a1e48  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1e4f  lea     r14, WPP_GLOBAL_Control
0x1801a1e56  cmp     rcx, r14
0x1801a1e59  jz      short loc_1801A1E7B
0x1801a1e5b  test    [rcx+1Ch], r12d
0x1801a1e5f  jz      short loc_1801A1E7B
0x1801a1e61  lea     edx, [rax+34h]
0x1801a1e64  lea     r9, aStackversion; "StackVersion"
0x1801a1e6b  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1e72  mov     rcx, [rcx+10h]
0x1801a1e76  call    WPP_SF_S
0x1801a1e7b  mov     [rsp+68h+samDesired], 8; cbData
0x1801a1e83  lea     rax, Data; "3.0"
0x1801a1e8a  mov     [rsp+68h+phkResult], rax; lpData
0x1801a1e8f  mov     r9d, 1; dwType
0x1801a1e95  xor     r8d, r8d; Reserved
0x1801a1e98  lea     rdx, aStackversion; "StackVersion"
0x1801a1e9f  mov     rcx, [rbp+var_18]; hKey
0x1801a1ea3  call    cs:__imp_RegSetValueExW
0x1801a1ea9  mov     edi, eax
0x1801a1eab  test    eax, eax
0x1801a1ead  jz      short loc_1801A1EED
0x1801a1eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a1eb6  cmp     rcx, r14
0x1801a1eb9  jz      short loc_1801A1ED9
0x1801a1ebb  test    [rcx+1Ch], r12d
0x1801a1ebf  jz      short loc_1801A1ED9
0x1801a1ec1  mov     edx, 35h ; '5'
0x1801a1ec6  mov     r9d, eax
0x1801a1ec9  lea     r8, WPP_4b28c62a3bac3166b59a1fed4343dd94_Traceguids
0x1801a1ed0  mov     rcx, [rcx+10h]
0x1801a1ed4  call    WPP_SF_d
0x1801a1ed9  mov     edx, edi
0x1801a1edb  mov     rax, [rbx]
0x1801a1ede  mov     rcx, rbx
0x1801a1ee1  mov     rax, [rax+48h]
0x1801a1ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1eea  mov     esi, r13d
0x1801a1eed  lea     rcx, [rbp+var_18]
0x1801a1ef1  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x1801a1ef6  jmp     short loc_1801A1F07
0x1801a1ef8  mov     rcx, [rbp+var_10]; hKey
0x1801a1efc  test    rcx, rcx
0x1801a1eff  jz      short loc_1801A1F07
0x1801a1f01  call    cs:__imp_RegCloseKey
0x1801a1f07  mov     eax, esi
0x1801a1f09  add     rsp, 68h
0x1801a1f0d  pop     r15
0x1801a1f0f  pop     r14
0x1801a1f11  pop     r13
0x1801a1f13  pop     r12
0x1801a1f15  pop     rdi
0x1801a1f16  pop     rsi
0x1801a1f17  pop     rbx
0x1801a1f18  pop     rbp
0x1801a1f19  retn
```
