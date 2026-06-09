# FwDiagResolveAddProgramException

- ea: `0x180009310`
- end: `0x180009571`
- name: `FwDiagResolveAddProgramException`
- size: `609`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005990`

## callees

- `0x180009310`
- `0x18000c572`
- `0x18000c5b0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180009479`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180009479`
- `FirewallAPI!FWGetGlobalConfig` at `0x180009396`
- `FirewallAPI!FWGetGlobalConfig` at `0x180009396`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800093f7`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800093f7`
- `FirewallAPI!FWDeleteFirewallRule` at `0x1800094fc`
- `FirewallAPI!FWDeleteFirewallRule` at `0x1800094fc`
- `FirewallAPI!FWClosePolicyStore` at `0x180009514`
- `FirewallAPI!FWClosePolicyStore` at `0x180009514`
- `FirewallAPI!FWAddFirewallRule` at `0x180009492`
- `FirewallAPI!FWAddFirewallRule` at `0x1800094e6`
- `FirewallAPI!FWAddFirewallRule` at `0x180009492`
- `FirewallAPI!FWAddFirewallRule` at `0x1800094e6`
- `RPCRT4!UuidCreate` at `0x18000940e`
- `RPCRT4!UuidCreate` at `0x1800094a5`
- `RPCRT4!UuidCreate` at `0x18000940e`
- `RPCRT4!UuidCreate` at `0x1800094a5`
- `RPCRT4!UuidToStringW` at `0x18000942a`
- `RPCRT4!UuidToStringW` at `0x1800094bd`
- `RPCRT4!UuidToStringW` at `0x18000942a`
- `RPCRT4!UuidToStringW` at `0x1800094bd`
- `RPCRT4!RpcStringFreeW` at `0x180009526`
- `RPCRT4!RpcStringFreeW` at `0x180009538`
- `RPCRT4!RpcStringFreeW` at `0x180009526`
- `RPCRT4!RpcStringFreeW` at `0x180009538`

## pseudocode

```c
__int64 __fastcall FwDiagResolveAddProgramException(__int64 a1)
{
  const WCHAR *v2; // rdi
  __int64 result; // rax
  int v4; // esi
  unsigned int v5; // ebx
  __int64 v6; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v7; // [rsp+50h] [rbp-B8h] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-B0h] BYREF
  RPC_WSTR String; // [rsp+60h] [rbp-A8h] BYREF
  _WORD v10[8]; // [rsp+68h] [rbp-A0h] BYREF
  RPC_WSTR v11; // [rsp+78h] [rbp-90h]
  LPWSTR FileNameW; // [rsp+80h] [rbp-88h]
  int v13; // [rsp+90h] [rbp-78h]
  int v14; // [rsp+94h] [rbp-74h]
  __int16 v15; // [rsp+98h] [rbp-70h]
  const WCHAR *v16; // [rsp+178h] [rbp+70h]
  int v17; // [rsp+188h] [rbp+80h]
  __int16 v18; // [rsp+18Ch] [rbp+84h]
  UUID Uuid; // [rsp+268h] [rbp+160h] BYREF

  if ( !a1 )
    return 87;
  v2 = *(const WCHAR **)(a1 + 16);
  if ( !v2 )
    return 87;
  LODWORD(v6) = 4;
  LODWORD(v7) = 0;
  result = FWGetGlobalConfig(545, 0, 5, 2, 0, &v7, &v6);
  if ( !(_DWORD)result )
  {
    v4 = *(_DWORD *)(a1 + 8);
    v6 = 0;
    StringUuid = 0;
    Uuid = 0;
    String = 0;
    memset_0(v10, 0, 0x1F8u);
    v5 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v6);
    if ( !v5 )
    {
      v5 = UuidCreate(&Uuid);
      if ( !v5 )
      {
        v5 = UuidToStringW(&Uuid, &StringUuid);
        if ( !v5 )
        {
          v13 = v7;
          v10[4] = 545;
          v18 |= 1u;
          v14 = 2 - (v4 != 0);
          v15 = 6;
          v11 = StringUuid;
          v17 = 3;
          FileNameW = PathFindFileNameW(v2);
          v16 = v2;
          v5 = FWAddFirewallRule(v6, v10);
          if ( !v5 )
          {
            v5 = UuidCreate(&Uuid);
            if ( !v5 )
            {
              v5 = UuidToStringW(&Uuid, &String);
              if ( !v5 )
              {
                v15 = 17;
                v11 = String;
                v5 = FWAddFirewallRule(v6, v10);
                if ( v5 )
                  FWDeleteFirewallRule(v6, StringUuid);
              }
            }
          }
        }
      }
    }
    if ( v6 )
      FWClosePolicyStore();
    if ( String )
      RpcStringFreeW(&String);
    if ( StringUuid )
      RpcStringFreeW(&StringUuid);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180009310  mov     r11, rsp
0x180009313  push    rbp
0x180009314  push    rbx
0x180009315  push    rdi
0x180009316  lea     rbp, [r11-198h]
0x18000931d  sub     rsp, 280h
0x180009324  mov     rax, cs:__security_cookie
0x18000932b  xor     rax, rsp
0x18000932e  mov     [rbp+190h+var_20], rax
0x180009335  mov     rbx, rcx
0x180009338  test    rcx, rcx
0x18000933b  jz      loc_18000956A
0x180009341  mov     rdi, [rcx+10h]
0x180009345  test    rdi, rdi
0x180009348  jz      loc_18000956A
0x18000934e  mov     [r11+18h], r14
0x180009352  lea     rax, [rsp+290h+var_250]
0x180009357  mov     [rsp+30h], rax
0x18000935c  xor     r14d, r14d
0x18000935f  mov     [r11+20h], r15
0x180009363  lea     rax, [rsp+290h+var_248]
0x180009368  mov     [rsp+290h+var_268], rax
0x18000936d  mov     r15d, 221h
0x180009373  mov     ecx, r15d
0x180009376  mov     dword ptr [rsp+290h+var_270], r14d
0x18000937b  xor     edx, edx
0x18000937d  mov     dword ptr [rsp+290h+var_250], 4
0x180009385  mov     r9d, 2
0x18000938b  mov     dword ptr [rsp+290h+var_248], r14d
0x180009390  mov     r8d, 5
0x180009396  call    cs:__imp_FWGetGlobalConfig
0x18000939c  test    eax, eax
0x18000939e  jnz     loc_180009540
0x1800093a4  xorps   xmm0, xmm0
0x1800093a7  mov     [rsp+290h+arg_8], rsi
0x1800093af  mov     esi, [rbx+8]
0x1800093b2  lea     rcx, [rsp+290h+var_230]; void *
0x1800093b7  xor     edx, edx; Val
0x1800093b9  mov     [rsp+290h+var_250], r14
0x1800093be  mov     r8d, 1F8h; Size
0x1800093c4  mov     [rsp+290h+StringUuid], r14
0x1800093c9  movups  xmmword ptr [rbp+190h+Uuid.Data1], xmm0
0x1800093d0  mov     [rsp+290h+String], r14
0x1800093d5  call    memset_0
0x1800093da  lea     rax, [rsp+290h+var_250]
0x1800093df  mov     r9d, 2
0x1800093e5  mov     [rsp+290h+var_268], rax
0x1800093ea  mov     r8d, r9d
0x1800093ed  mov     ecx, r15d
0x1800093f0  mov     dword ptr [rsp+290h+var_270], r14d
0x1800093f5  xor     edx, edx
0x1800093f7  call    cs:__imp_FWOpenPolicyStore
0x1800093fd  mov     ebx, eax
0x1800093ff  test    eax, eax
0x180009401  jnz     loc_180009502
0x180009407  lea     rcx, [rbp+190h+Uuid]; Uuid
0x18000940e  call    cs:__imp_UuidCreate
0x180009414  mov     ebx, eax
0x180009416  test    eax, eax
0x180009418  jnz     loc_180009502
0x18000941e  lea     rdx, [rsp+290h+StringUuid]; StringUuid
0x180009423  lea     rcx, [rbp+190h+Uuid]; Uuid
0x18000942a  call    cs:__imp_UuidToStringW
0x180009430  mov     ebx, eax
0x180009432  test    eax, eax
0x180009434  jnz     loc_180009502
0x18000943a  mov     ecx, dword ptr [rsp+290h+var_248]
0x18000943e  neg     esi
0x180009440  mov     [rbp+190h+var_208], ecx
0x180009443  mov     rcx, rdi; pszPath
0x180009446  sbb     eax, eax
0x180009448  mov     word ptr [rsp+290h+var_228], r15w
0x18000944e  or      [rbp+190h+var_10C], 1
0x180009456  add     eax, 2
0x180009459  mov     [rbp+190h+var_204], eax
0x18000945c  mov     eax, 6
0x180009461  mov     [rbp+190h+var_200], ax
0x180009465  mov     rax, [rsp+290h+StringUuid]
0x18000946a  mov     [rsp+290h+var_220], rax
0x18000946f  mov     [rbp+190h+var_110], 3
0x180009479  call    cs:__imp_PathFindFileNameW
0x18000947f  mov     rcx, [rsp+290h+var_250]
0x180009484  lea     rdx, [rsp+290h+var_230]
0x180009489  mov     [rsp+290h+var_218], rax
0x18000948e  mov     [rbp+190h+var_120], rdi
0x180009492  call    cs:__imp_FWAddFirewallRule
0x180009498  mov     ebx, eax
0x18000949a  test    eax, eax
0x18000949c  jnz     short loc_180009502
0x18000949e  lea     rcx, [rbp+190h+Uuid]; Uuid
0x1800094a5  call    cs:__imp_UuidCreate
0x1800094ab  mov     ebx, eax
0x1800094ad  test    eax, eax
0x1800094af  jnz     short loc_180009502
0x1800094b1  lea     rdx, [rsp+290h+String]; StringUuid
0x1800094b6  lea     rcx, [rbp+190h+Uuid]; Uuid
0x1800094bd  call    cs:__imp_UuidToStringW
0x1800094c3  mov     ebx, eax
0x1800094c5  test    eax, eax
0x1800094c7  jnz     short loc_180009502
0x1800094c9  mov     rcx, [rsp+290h+var_250]
0x1800094ce  lea     rdx, [rsp+290h+var_230]
0x1800094d3  mov     eax, 11h
0x1800094d8  mov     [rbp+190h+var_200], ax
0x1800094dc  mov     rax, [rsp+290h+String]
0x1800094e1  mov     [rsp+290h+var_220], rax
0x1800094e6  call    cs:__imp_FWAddFirewallRule
0x1800094ec  mov     ebx, eax
0x1800094ee  test    eax, eax
0x1800094f0  jz      short loc_180009502
0x1800094f2  mov     rdx, [rsp+290h+StringUuid]
0x1800094f7  mov     rcx, [rsp+290h+var_250]
0x1800094fc  call    cs:__imp_FWDeleteFirewallRule
0x180009502  mov     rcx, [rsp+290h+var_250]
0x180009507  mov     rsi, [rsp+290h+arg_8]
0x18000950f  test    rcx, rcx
0x180009512  jz      short loc_18000951A
0x180009514  call    cs:__imp_FWClosePolicyStore
0x18000951a  cmp     [rsp+290h+String], r14
0x18000951f  jz      short loc_18000952C
0x180009521  lea     rcx, [rsp+290h+String]; String
0x180009526  call    cs:__imp_RpcStringFreeW
0x18000952c  cmp     [rsp+290h+StringUuid], r14
0x180009531  jz      short loc_18000953E
0x180009533  lea     rcx, [rsp+290h+StringUuid]; String
0x180009538  call    cs:__imp_RpcStringFreeW
0x18000953e  mov     eax, ebx
0x180009540  mov     r14, [rsp+290h+arg_10]
0x180009548  mov     r15, [rsp+290h+arg_18]
0x180009550  mov     rcx, [rbp+190h+var_20]
0x180009557  xor     rcx, rsp; StackCookie
0x18000955a  call    __security_check_cookie
0x18000955f  add     rsp, 280h
0x180009566  pop     rdi
0x180009567  pop     rbx
0x180009568  pop     rbp
0x180009569  retn
0x18000956a  mov     eax, 57h ; 'W'
0x18000956f  jmp     short loc_180009550
```
