# Int_FWLocalRpcBindingCreate

- ea: `0x18000e960`
- end: `0x18000ebce`
- name: `Int_FWLocalRpcBindingCreate`
- size: `622`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `45`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e6c0`
- `0x18000f1a0`
- `0x18000fac0`
- `0x18000fe30`
- `0x180010400`
- `0x180010820`
- `0x18001bc60`
- `0x18001d120`
- `0x18001f5b0`
- `0x180025620`
- `0x18004b4a0`
- `0x18004b800`
- `0x18004b970`
- `0x18004c410`
- `0x18004cc70`
- `0x18004cde0`
- `0x18004d1b0`
- `0x18004e550`
- `0x18004e690`
- `0x18004e820`
- `0x18004e9b0`
- `0x18004ed30`
- `0x18004ef90`
- `0x18004f0e0`
- `0x18004f240`
- `0x18004fad0`
- `0x180050400`
- `0x180050570`
- `0x180050ce0`
- `0x1800522f0`
- `0x180052460`
- `0x180052740`
- `0x180052ab0`
- `0x180052e90`
- `0x1800531a0`
- `0x180053410`
- `0x180053730`
- `0x180053a60`
- `0x180053b70`
- `0x180053d00`
- `0x180054110`
- `0x1800543d0`
- `0x180054540`
- `0x1800546e0`
- `0x180054b70`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180024c3c`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `RPCRT4!RpcStringBindingComposeW` at `0x18000ea00`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ea00`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ea18`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ea18`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000ea87`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000ea87`
- `RPCRT4!RpcStringFreeW` at `0x18000eaa8`
- `RPCRT4!RpcStringFreeW` at `0x18000eaa8`
- `RPCRT4!RpcBindingFree` at `0x18000eba8`
- `RPCRT4!RpcBindingFree` at `0x18000eba8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb3c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ea4d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18000ea4d`

## pseudocode

```c
__int64 __fastcall Int_FWLocalRpcBindingCreate(RPC_BINDING_HANDLE *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  FwPolicy2 *v7; // rcx
  __int64 v8; // rdx
  DWORD LastError; // eax
  unsigned int v10; // eax
  __int64 v11; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-59h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-51h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp-49h] BYREF
  __int128 v15; // [rsp+60h] [rbp-39h]
  _OWORD *v16; // [rsp+70h] [rbp-29h]
  DWORD cbSid; // [rsp+78h] [rbp-21h] BYREF
  _OWORD pSid[4]; // [rsp+80h] [rbp-19h] BYREF
  int v19; // [rsp+C0h] [rbp+27h]

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 357, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  cbSid = 68;
  v16 = 0;
  v19 = 0;
  String = 0;
  Binding = 0;
  SecurityQOS = 0;
  *a1 = 0;
  v15 = 0;
  memset(pSid, 0, sizeof(pSid));
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  v3 = v2;
  if ( v2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 358;
LABEL_27:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v2);
    }
LABEL_28:
    if ( Binding )
    {
      v10 = RpcBindingFree(&Binding);
      if ( v10 )
        MicrosoftTelemetryAssertTriggeredArgs(v11, v10);
    }
    goto LABEL_9;
  }
  v2 = RpcBindingFromStringBindingW(String, &Binding);
  v3 = v2;
  if ( v2 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 359;
      goto LABEL_27;
    }
    goto LABEL_28;
  }
  SecurityQOS.Version = 3;
  *(_QWORD *)&SecurityQOS.Capabilities = 1;
  SecurityQOS.ImpersonationType = 3;
  if ( CreateWellKnownSid(WinLocalServiceSid, 0, pSid, &cbSid) )
  {
    v16 = pSid;
    v2 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xFFFFFFFF, 0, 0, &SecurityQOS);
    v3 = v2;
    if ( !v2 )
    {
      *a1 = Binding;
      goto LABEL_9;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    v8 = 361;
    goto LABEL_27;
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 360, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, LastError);
  if ( v3 )
    goto LABEL_28;
LABEL_9:
  if ( String )
  {
    v4 = RpcStringFreeW(&String);
    if ( v4 )
      MicrosoftTelemetryAssertTriggeredArgs(v5, v4);
  }
  return v3;
}

```

## disassembly

```asm
0x18000e960  mov     [rsp-8+arg_8], rbx
0x18000e965  mov     [rsp-8+arg_10], rsi
0x18000e96a  push    rbp
0x18000e96b  push    rdi
0x18000e96c  push    r14
0x18000e96e  lea     rbp, [rsp-47h]
0x18000e973  sub     rsp, 0E0h
0x18000e97a  mov     rax, cs:__security_cookie
0x18000e981  xor     rax, rsp
0x18000e984  mov     [rbp+57h+var_20], rax
0x18000e988  mov     rdi, rcx
0x18000e98b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e992  lea     r14, WPP_GLOBAL_Control
0x18000e999  cmp     rcx, r14
0x18000e99c  jz      short loc_18000E9A8
0x18000e99e  test    byte ptr [rcx+1Ch], 8
0x18000e9a2  jnz     loc_18000EB09
0x18000e9a8  xorps   xmm1, xmm1
0x18000e9ab  mov     [rbp+57h+cbSid], 44h ; 'D'
0x18000e9b2  xor     eax, eax
0x18000e9b4  lea     rdx, ProtSeq; "ncalrpc"
0x18000e9bb  xor     esi, esi
0x18000e9bd  mov     [rbp+57h+var_80], rax
0x18000e9c1  xorps   xmm0, xmm0
0x18000e9c4  mov     [rbp+57h+var_30], eax
0x18000e9c7  lea     rax, [rbp+57h+String]
0x18000e9cb  mov     [rbp+57h+String], rsi
0x18000e9cf  mov     [rsp+0F0h+StringBinding], rax; StringBinding
0x18000e9d4  xor     r9d, r9d; Endpoint
0x18000e9d7  xor     r8d, r8d; NetworkAddr
0x18000e9da  mov     [rsp+0F0h+Options], rsi; Options
0x18000e9df  xor     ecx, ecx; ObjUuid
0x18000e9e1  mov     [rbp+57h+Binding], rsi
0x18000e9e5  movups  xmmword ptr [rbp+57h+var_A0.Version], xmm0
0x18000e9e9  mov     [rdi], rsi
0x18000e9ec  movups  [rbp+57h+var_90], xmm0
0x18000e9f0  movups  [rbp+57h+pSid], xmm1
0x18000e9f4  movups  [rbp+57h+var_60], xmm1
0x18000e9f8  movups  [rbp+57h+var_50], xmm1
0x18000e9fc  movups  [rbp+57h+var_40], xmm1
0x18000ea00  call    cs:__imp_RpcStringBindingComposeW
0x18000ea06  mov     ebx, eax
0x18000ea08  test    eax, eax
0x18000ea0a  jnz     loc_18000EADC
0x18000ea10  mov     rcx, [rbp+57h+String]; StringBinding
0x18000ea14  lea     rdx, [rbp+57h+Binding]; Binding
0x18000ea18  call    cs:__imp_RpcBindingFromStringBindingW
0x18000ea1e  mov     ebx, eax
0x18000ea20  test    eax, eax
0x18000ea22  jnz     loc_18000EB23
0x18000ea28  lea     r9, [rbp+57h+cbSid]; cbSid
0x18000ea2c  mov     [rbp+57h+var_A0.Version], 3
0x18000ea33  lea     r8, [rbp+57h+pSid]; pSid
0x18000ea37  mov     qword ptr [rbp+57h+var_A0.Capabilities], 1
0x18000ea3f  xor     edx, edx; DomainSid
0x18000ea41  mov     [rbp+57h+var_A0.ImpersonationType], 3
0x18000ea48  mov     ecx, 17h; WellKnownSidType
0x18000ea4d  call    cs:__imp_CreateWellKnownSid
0x18000ea53  test    eax, eax
0x18000ea55  jz      loc_18000EB3C
0x18000ea5b  mov     rcx, [rbp+57h+Binding]; Binding
0x18000ea5f  lea     rax, [rbp+57h+pSid]
0x18000ea63  mov     [rbp+57h+var_80], rax
0x18000ea67  xor     edx, edx; ServerPrincName
0x18000ea69  lea     rax, [rbp+57h+var_A0]
0x18000ea6d  mov     r9d, 0FFFFFFFFh; AuthnSvc
0x18000ea73  mov     [rsp+0F0h+SecurityQOS], rax; SecurityQOS
0x18000ea78  mov     r8d, 6; AuthnLevel
0x18000ea7e  mov     dword ptr [rsp+0F0h+StringBinding], esi; AuthzSvc
0x18000ea82  mov     [rsp+0F0h+Options], rsi; AuthIdentity
0x18000ea87  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000ea8d  mov     ebx, eax
0x18000ea8f  test    eax, eax
0x18000ea91  jnz     loc_18000EB70
0x18000ea97  mov     rax, [rbp+57h+Binding]
0x18000ea9b  mov     [rdi], rax
0x18000ea9e  cmp     [rbp+57h+String], rsi
0x18000eaa2  jz      short loc_18000EAB6
0x18000eaa4  lea     rcx, [rbp+57h+String]; String
0x18000eaa8  call    cs:__imp_RpcStringFreeW
0x18000eaae  test    eax, eax
0x18000eab0  jnz     loc_18000EBC2
0x18000eab6  mov     eax, ebx
0x18000eab8  mov     rcx, [rbp+57h+var_20]
0x18000eabc  xor     rcx, rsp; StackCookie
0x18000eabf  call    __security_check_cookie
0x18000eac4  lea     r11, [rsp+0F0h+var_10]
0x18000eacc  mov     rbx, [r11+28h]
0x18000ead0  mov     rsi, [r11+30h]
0x18000ead4  mov     rsp, r11
0x18000ead7  pop     r14
0x18000ead9  pop     rdi
0x18000eada  pop     rbp
0x18000eadb  retn
0x18000eadc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eae3  cmp     rcx, r14
0x18000eae6  jz      loc_18000EB9A
0x18000eaec  test    byte ptr [rcx+1Ch], 1
0x18000eaf0  jz      loc_18000EB9A
0x18000eaf6  mov     edx, 166h
0x18000eafb  jmp     loc_18000EB87
0x18000eb00  test    ebx, ebx
0x18000eb02  jz      short loc_18000EA9E
0x18000eb04  jmp     loc_18000EB9A
0x18000eb09  mov     rcx, [rcx+10h]
0x18000eb0d  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000eb14  mov     edx, 165h
0x18000eb19  call    WPP_SF_
0x18000eb1e  jmp     loc_18000E9A8
0x18000eb23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb2a  cmp     rcx, r14
0x18000eb2d  jz      short loc_18000EB9A
0x18000eb2f  test    byte ptr [rcx+1Ch], 1
0x18000eb33  jz      short loc_18000EB9A
0x18000eb35  mov     edx, 167h
0x18000eb3a  jmp     short loc_18000EB87
0x18000eb3c  call    cs:__imp_GetLastError
0x18000eb42  mov     ebx, eax
0x18000eb44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb4b  cmp     rcx, r14
0x18000eb4e  jz      short loc_18000EB00
0x18000eb50  test    byte ptr [rcx+1Ch], 1
0x18000eb54  jz      short loc_18000EB00
0x18000eb56  mov     rcx, [rcx+10h]
0x18000eb5a  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000eb61  mov     edx, 168h
0x18000eb66  mov     r9d, eax
0x18000eb69  call    WPP_SF_d
0x18000eb6e  jmp     short loc_18000EB00
0x18000eb70  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb77  cmp     rcx, r14
0x18000eb7a  jz      short loc_18000EB9A
0x18000eb7c  test    byte ptr [rcx+1Ch], 1
0x18000eb80  jz      short loc_18000EB9A
0x18000eb82  mov     edx, 169h
0x18000eb87  mov     rcx, [rcx+10h]
0x18000eb8b  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000eb92  mov     r9d, eax
0x18000eb95  call    WPP_SF_d
0x18000eb9a  cmp     [rbp+57h+Binding], rsi
0x18000eb9e  jz      loc_18000EA9E
0x18000eba4  lea     rcx, [rbp+57h+Binding]; Binding
0x18000eba8  call    cs:__imp_RpcBindingFree
0x18000ebae  test    eax, eax
0x18000ebb0  jz      loc_18000EA9E
0x18000ebb6  mov     edx, eax
0x18000ebb8  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000ebbd  jmp     loc_18000EA9E
0x18000ebc2  mov     edx, eax
0x18000ebc4  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000ebc9  jmp     loc_18000EAB6
```
