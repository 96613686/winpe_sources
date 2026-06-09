# Windows::Networking::UX::Internal::Profile::SetMacAddressRandomizationState(Windows::Networking::UX::Internal::MacAddressRandomizationState)

- ea: `0x180075bc8`
- end: `0x180075ecf`
- name: `?SetMacAddressRandomizationState@Profile@Internal@UX@Networking@Windows@@QEAAJW4MacAddressRandomizationState@2345@@Z`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18005d220`

## callees

- `0x18000de4c`
- `0x18001d3a4`
- `0x18001d4d4`
- `0x180075284`
- `0x180075bc8`
- `0x180075f78`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075e6b`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075e7a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075e6b`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180075e7a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180075e1a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanSetProfile` at `0x180075e1a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x180075c99`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfile` at `0x180075c99`
- `wlanapi!WpFreeProfile` at `0x180075e89`
- `wlanapi!WpFreeProfile` at `0x180075e89`
- `wlanapi!WpGenerateProfileXml` at `0x180075dcf`
- `wlanapi!WpGenerateProfileXml` at `0x180075dcf`
- `wlanapi!WpParseProfileXml` at `0x180075d1f`
- `wlanapi!WpParseProfileXml` at `0x180075d1f`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::Profile::SetMacAddressRandomizationState(
        __int64 a1,
        unsigned int a2)
{
  signed int v4; // ebx
  int MacAddressRandomizationFeatureState; // eax
  signed int Profile; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  _DWORD *v10; // rbx
  int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // eax
  int v15; // eax
  signed int v16; // eax
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR pstrProfileXml; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR strProfileXml; // [rsp+50h] [rbp-10h] BYREF
  time_t Time; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwFlags; // [rsp+98h] [rbp+38h] BYREF
  DWORD pdwGrantedAccess; // [rsp+A0h] [rbp+40h] BYREF
  DWORD pdwReasonCode; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_660af29b5b58392da31645ec246aada0_Traceguids);
  pstrProfileXml = 0;
  strProfileXml = 0;
  v18 = 0;
  dwFlags = 0;
  pdwGrantedAccess = 0;
  pdwReasonCode = 0;
  if ( a2 > 2 )
  {
    v4 = -2147024809;
    goto LABEL_48;
  }
  MacAddressRandomizationFeatureState = Windows::Networking::UX::Internal::Profile::GetMacAddressRandomizationFeatureState(a1);
  if ( MacAddressRandomizationFeatureState == 1 )
  {
    v4 = -2147024846;
    goto LABEL_42;
  }
  if ( MacAddressRandomizationFeatureState == 2 )
  {
    v4 = -2147023636;
    goto LABEL_42;
  }
  Profile = WlanGetProfile(
              *(HANDLE *)a1,
              (const GUID *)(a1 + 8),
              (LPCWSTR)(a1 + 24),
              0,
              &pstrProfileXml,
              &dwFlags,
              &pdwGrantedAccess);
  v4 = Profile;
  if ( Profile > 0 )
    v4 = (unsigned __int16)Profile | 0x80070000;
  if ( v4 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_42;
    v8 = 28;
    goto LABEL_16;
  }
  if ( (dwFlags & 1) == 0 && ((pdwGrantedAccess & 0x70023) == 458787 || (dwFlags & 2) != 0) )
  {
    v9 = WpParseProfileXml(pstrProfileXml, &v18, 0, 0);
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( v4 >= 0 )
    {
      if ( v18 && *(_DWORD *)(v18 + 536) == 5304833 )
      {
        v10 = *(_DWORD **)(v18 + 552);
        v11 = v10[6];
        if ( a2 )
        {
          v10[1] |= 8u;
          v12 = v11 & 0xFFFFFFEF;
          v13 = v11 & 0xFFFFFFCF | 0x20;
          v14 = v12 & 0xFFFFFFDF;
          if ( a2 != 2 )
            v13 = v14;
          v10[6] = v13;
          if ( !v10[16] )
          {
            Time = 0;
            time(&Time);
            v10[16] = Time;
          }
        }
        else
        {
          v10[6] = v11 & 0xFFFFFFCF | 0x10;
        }
        v15 = WpGenerateProfileXml(v18, &strProfileXml);
        v4 = v15;
        if ( v15 > 0 )
          v4 = (unsigned __int16)v15 | 0x80070000;
        if ( v4 >= 0 )
        {
          v16 = WlanSetProfile(*(HANDLE *)a1, (const GUID *)(a1 + 8), dwFlags, strProfileXml, 0, 1, 0, &pdwReasonCode);
          v4 = v16;
          if ( v16 > 0 )
            v4 = (unsigned __int16)v16 | 0x80070000;
          if ( v4 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              WPP_660af29b5b58392da31645ec246aada0_Traceguids,
              pdwReasonCode,
              v4);
        }
      }
      goto LABEL_42;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 29;
LABEL_16:
      WPP_SF_d(v7[2], v8, WPP_660af29b5b58392da31645ec246aada0_Traceguids, (unsigned int)v4);
    }
  }
LABEL_42:
  if ( pstrProfileXml )
    WlanFreeMemory(pstrProfileXml);
  if ( strProfileXml )
    WlanFreeMemory((PVOID)strProfileXml);
  if ( v18 )
    WpFreeProfile(v18);
LABEL_48:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_660af29b5b58392da31645ec246aada0_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180075bc8  mov     [rsp-28h+arg_0], rbx
0x180075bcd  push    rbp
0x180075bce  push    rsi
0x180075bcf  push    rdi
0x180075bd0  push    r13
0x180075bd2  push    r14
0x180075bd4  mov     rbp, rsp
0x180075bd7  sub     rsp, 60h
0x180075bdb  mov     esi, edx
0x180075bdd  mov     rdi, rcx
0x180075be0  mov     rcx, cs:WPP_GLOBAL_Control
0x180075be7  lea     r13, WPP_GLOBAL_Control
0x180075bee  cmp     rcx, r13
0x180075bf1  jz      short loc_180075C0E
0x180075bf3  test    byte ptr [rcx+1Ch], 40h
0x180075bf7  jz      short loc_180075C0E
0x180075bf9  mov     rcx, [rcx+10h]
0x180075bfd  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x180075c04  mov     edx, 1Bh
0x180075c09  call    WPP_SF_
0x180075c0e  mov     [rbp+var_18], 0
0x180075c16  mov     [rbp+strProfileXml], 0
0x180075c1e  mov     [rbp+var_20], 0
0x180075c26  mov     [rbp+dwFlags], 0
0x180075c2d  mov     [rbp+arg_10], 0
0x180075c34  mov     [rbp+arg_18], 0
0x180075c3b  cmp     esi, 2
0x180075c3e  jbe     short loc_180075C4A
0x180075c40  mov     ebx, 80070057h
0x180075c45  jmp     loc_180075E8F
0x180075c4a  mov     rcx, rdi
0x180075c4d  call    ?GetMacAddressRandomizationFeatureState@Profile@Internal@UX@Networking@Windows@@AEAA?AW4_DOT11_MAC_RANDOMIZATION_STATUS@@XZ; Windows::Networking::UX::Internal::Profile::GetMacAddressRandomizationFeatureState(void)
0x180075c52  cmp     eax, 1
0x180075c55  jnz     short loc_180075C61
0x180075c57  mov     ebx, 80070032h
0x180075c5c  jmp     loc_180075E62
0x180075c61  cmp     eax, 2
0x180075c64  jnz     short loc_180075C70
0x180075c66  mov     ebx, 800704ECh
0x180075c6b  jmp     loc_180075E62
0x180075c70  mov     rcx, [rdi]; hClientHandle
0x180075c73  lea     rax, [rbp+arg_10]
0x180075c77  mov     [rsp+60h+pdwGrantedAccess], rax; pdwGrantedAccess
0x180075c7c  lea     r8, [rdi+18h]; strProfileName
0x180075c80  lea     rax, [rbp+dwFlags]
0x180075c84  xor     r9d, r9d; pReserved
0x180075c87  mov     [rsp+60h+pdwFlags], rax; pdwFlags
0x180075c8c  lea     rdx, [rdi+8]; pInterfaceGuid
0x180075c90  lea     rax, [rbp+var_18]
0x180075c94  mov     [rsp+60h+pstrProfileXml], rax; pstrProfileXml
0x180075c99  call    cs:__imp_WlanGetProfile
0x180075c9f  mov     ebx, eax
0x180075ca1  test    eax, eax
0x180075ca3  jle     short loc_180075CAE
0x180075ca5  movzx   ebx, ax
0x180075ca8  or      ebx, 80070000h
0x180075cae  test    ebx, ebx
0x180075cb0  jns     short loc_180075CE9
0x180075cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180075cb9  cmp     rcx, r13
0x180075cbc  jz      loc_180075E62
0x180075cc2  test    byte ptr [rcx+1Ch], 2
0x180075cc6  jz      loc_180075E62
0x180075ccc  mov     edx, 1Ch
0x180075cd1  mov     rcx, [rcx+10h]
0x180075cd5  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x180075cdc  mov     r9d, ebx
0x180075cdf  call    WPP_SF_d
0x180075ce4  jmp     loc_180075E62
0x180075ce9  test    byte ptr [rbp+dwFlags], 1
0x180075ced  jnz     loc_180075E62
0x180075cf3  mov     eax, [rbp+arg_10]
0x180075cf6  mov     ecx, 70023h
0x180075cfb  and     eax, ecx
0x180075cfd  cmp     eax, ecx
0x180075cff  setnz   cl
0x180075d02  test    byte ptr [rbp+dwFlags], 2
0x180075d06  setz    al
0x180075d09  test    al, cl
0x180075d0b  jnz     loc_180075E62
0x180075d11  mov     rcx, [rbp+var_18]
0x180075d15  lea     rdx, [rbp+var_20]
0x180075d19  xor     r9d, r9d
0x180075d1c  xor     r8d, r8d
0x180075d1f  call    cs:__imp_WpParseProfileXml
0x180075d25  mov     ebx, eax
0x180075d27  test    eax, eax
0x180075d29  jle     short loc_180075D34
0x180075d2b  movzx   ebx, ax
0x180075d2e  or      ebx, 80070000h
0x180075d34  test    ebx, ebx
0x180075d36  jns     short loc_180075D5C
0x180075d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180075d3f  cmp     rcx, r13
0x180075d42  jz      loc_180075E62
0x180075d48  test    byte ptr [rcx+1Ch], 2
0x180075d4c  jz      loc_180075E62
0x180075d52  mov     edx, 1Dh
0x180075d57  jmp     loc_180075CD1
0x180075d5c  mov     rcx, [rbp+var_20]
0x180075d60  test    rcx, rcx
0x180075d63  jz      loc_180075E62
0x180075d69  cmp     dword ptr [rcx+218h], 50F201h
0x180075d73  jnz     loc_180075E62
0x180075d79  mov     rbx, [rcx+228h]
0x180075d80  mov     ecx, [rbx+18h]
0x180075d83  test    esi, esi
0x180075d85  jnz     short loc_180075D92
0x180075d87  and     ecx, 0FFFFFFDFh
0x180075d8a  or      ecx, 10h
0x180075d8d  mov     [rbx+18h], ecx
0x180075d90  jmp     short loc_180075DC7
0x180075d92  or      dword ptr [rbx+4], 8
0x180075d96  and     ecx, 0FFFFFFEFh
0x180075d99  mov     eax, ecx
0x180075d9b  or      ecx, 20h
0x180075d9e  and     eax, 0FFFFFFDFh
0x180075da1  cmp     esi, 2
0x180075da4  cmovnz  ecx, eax
0x180075da7  mov     [rbx+18h], ecx
0x180075daa  cmp     dword ptr [rbx+40h], 0
0x180075dae  jnz     short loc_180075DC7
0x180075db0  lea     rcx, [rbp+Time]; Time
0x180075db4  mov     [rbp+Time], 0
0x180075dbc  call    time
0x180075dc1  mov     eax, dword ptr [rbp+Time]
0x180075dc4  mov     [rbx+40h], eax
0x180075dc7  mov     rcx, [rbp+var_20]
0x180075dcb  lea     rdx, [rbp+strProfileXml]
0x180075dcf  call    cs:__imp_WpGenerateProfileXml
0x180075dd5  mov     ebx, eax
0x180075dd7  test    eax, eax
0x180075dd9  jle     short loc_180075DE4
0x180075ddb  movzx   ebx, ax
0x180075dde  or      ebx, 80070000h
0x180075de4  test    ebx, ebx
0x180075de6  js      short loc_180075E62
0x180075de8  mov     r9, [rbp+strProfileXml]; strProfileXml
0x180075dec  lea     rax, [rbp+arg_18]
0x180075df0  mov     r8d, [rbp+dwFlags]; dwFlags
0x180075df4  lea     rdx, [rdi+8]; pInterfaceGuid
0x180075df8  mov     rcx, [rdi]; hClientHandle
0x180075dfb  mov     [rsp+60h+pdwReasonCode], rax; pdwReasonCode
0x180075e00  mov     [rsp+60h+pdwGrantedAccess], 0; pReserved
0x180075e09  mov     dword ptr [rsp+60h+pdwFlags], 1; bOverwrite
0x180075e11  mov     [rsp+60h+pstrProfileXml], 0; strAllUserProfileSecurity
0x180075e1a  call    cs:__imp_WlanSetProfile
0x180075e20  mov     ebx, eax
0x180075e22  test    eax, eax
0x180075e24  jle     short loc_180075E2F
0x180075e26  movzx   ebx, ax
0x180075e29  or      ebx, 80070000h
0x180075e2f  test    ebx, ebx
0x180075e31  jns     short loc_180075E62
0x180075e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180075e3a  cmp     rcx, r13
0x180075e3d  jz      short loc_180075E62
0x180075e3f  test    byte ptr [rcx+1Ch], 2
0x180075e43  jz      short loc_180075E62
0x180075e45  mov     r9d, [rbp+arg_18]
0x180075e49  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x180075e50  mov     rcx, [rcx+10h]
0x180075e54  mov     edx, 1Eh
0x180075e59  mov     dword ptr [rsp+60h+pstrProfileXml], ebx
0x180075e5d  call    WPP_SF_Dd
0x180075e62  mov     rcx, [rbp+var_18]; pMemory
0x180075e66  test    rcx, rcx
0x180075e69  jz      short loc_180075E71
0x180075e6b  call    cs:__imp_WlanFreeMemory
0x180075e71  mov     rcx, [rbp+strProfileXml]; pMemory
0x180075e75  test    rcx, rcx
0x180075e78  jz      short loc_180075E80
0x180075e7a  call    cs:__imp_WlanFreeMemory
0x180075e80  mov     rcx, [rbp+var_20]
0x180075e84  test    rcx, rcx
0x180075e87  jz      short loc_180075E8F
0x180075e89  call    cs:__imp_WpFreeProfile
0x180075e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180075e96  cmp     rcx, r13
0x180075e99  jz      short loc_180075EB9
0x180075e9b  test    byte ptr [rcx+1Ch], 40h
0x180075e9f  jz      short loc_180075EB9
0x180075ea1  mov     rcx, [rcx+10h]
0x180075ea5  lea     r8, WPP_660af29b5b58392da31645ec246aada0_Traceguids
0x180075eac  mov     edx, 1Fh
0x180075eb1  mov     r9d, ebx
0x180075eb4  call    WPP_SF_d
0x180075eb9  mov     eax, ebx
0x180075ebb  mov     rbx, [rsp+60h+arg_0]
0x180075ec3  add     rsp, 60h
0x180075ec7  pop     r14
0x180075ec9  pop     r13
0x180075ecb  pop     rdi
0x180075ecc  pop     rsi
0x180075ecd  pop     rbp
0x180075ece  retn
```
