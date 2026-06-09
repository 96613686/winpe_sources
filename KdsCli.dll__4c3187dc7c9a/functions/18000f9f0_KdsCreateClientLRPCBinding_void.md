# KdsCreateClientLRPCBinding(void * *)

- ea: `0x18000f9f0`
- end: `0x18000fc75`
- name: `?KdsCreateClientLRPCBinding@@YAJPEAPEAX@Z`
- size: `645`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019274`

## callees

- `0x18000f9f0`
- `0x18001a450`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000fb78`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000fb78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb82`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000fbe8`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000fbe8`
- `RPCRT4!RpcBindingSetOption` at `0x18000fc14`
- `RPCRT4!RpcBindingSetOption` at `0x18000fc14`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000fa4c`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000fb2d`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000fa4c`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000fb2d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000fa91`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000fb51`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000fa91`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000fb51`
- `RPCRT4!RpcEpResolveBinding` at `0x18000fab8`
- `RPCRT4!RpcEpResolveBinding` at `0x18000fab8`
- `RPCRT4!RpcStringFreeW` at `0x18000faea`
- `RPCRT4!RpcStringFreeW` at `0x18000fc5e`
- `RPCRT4!RpcStringFreeW` at `0x18000faea`
- `RPCRT4!RpcStringFreeW` at `0x18000fc5e`
- `RPCRT4!RpcBindingFree` at `0x18000fae0`
- `RPCRT4!RpcBindingFree` at `0x18000fc54`
- `RPCRT4!RpcBindingFree` at `0x18000fae0`
- `RPCRT4!RpcBindingFree` at `0x18000fc54`

## string_xrefs

- `0x18000fa58`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyrpccommon.cxx`

## pseudocode

```c
__int64 __fastcall KdsCreateClientLRPCBinding(void **a1)
{
  RPC_STATUS v2; // eax
  int v3; // ebx
  unsigned int v4; // r9d
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  unsigned int v7; // r9d
  RPC_STATUS v8; // eax
  RPC_STATUS v9; // eax
  signed int LastError; // eax
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-30h] BYREF
  RPC_SECURITY_QOS SecurityQOS[2]; // [rsp+48h] [rbp-28h] BYREF
  PSID v16; // [rsp+68h] [rbp-8h]
  RPC_BINDING_HANDLE hBinding; // [rsp+B0h] [rbp+40h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+B8h] [rbp+48h] BYREF
  RPC_WSTR String; // [rsp+C0h] [rbp+50h] BYREF
  PSID Sid; // [rsp+C8h] [rbp+58h] BYREF

  *a1 = 0;
  v16 = 0;
  Sid = 0;
  StringBinding = 0;
  hBinding = 0;
  memset(SecurityQOS, 0, sizeof(SecurityQOS));
  String = 0;
  Binding = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", 0, 0, 0, &String);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = 307;
LABEL_5:
    SidKeyDebugTraceError(v3, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v4);
    goto LABEL_15;
  }
  v5 = RpcBindingFromStringBindingW(String, &Binding);
  v3 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    v4 = 317;
    goto LABEL_5;
  }
  v6 = RpcEpResolveBinding(Binding, qword_18001C2F0);
  v3 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    v4 = 327;
    goto LABEL_5;
  }
  v3 = 0;
LABEL_15:
  if ( Binding )
    RpcBindingFree(&Binding);
  RpcStringFreeW(&String);
  if ( v3 < 0 )
  {
    v7 = 382;
LABEL_19:
    SidKeyDebugTraceError(v3, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyrpccommon.cxx", v7);
    goto LABEL_41;
  }
  v8 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"kdssvc_lrpc", 0, &StringBinding);
  v3 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    v7 = 397;
    goto LABEL_19;
  }
  v9 = RpcBindingFromStringBindingW(StringBinding, &hBinding);
  v3 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
    v7 = 407;
    goto LABEL_19;
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-18", &Sid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v7 = 418;
    goto LABEL_19;
  }
  *(_QWORD *)&SecurityQOS[0].Version = 0x100000003LL;
  *(_OWORD *)&SecurityQOS[0].ImpersonationType = 3u;
  v16 = Sid;
  SecurityQOS[1].ImpersonationType = 0;
  SecurityQOS[0].IdentityTracking = 1;
  v11 = RpcBindingSetAuthInfoExW(hBinding, 0, 6u, 0xAu, 0, 0, SecurityQOS);
  v3 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v3 = (unsigned __int16)v11 | 0x80070000;
    v7 = 441;
    goto LABEL_19;
  }
  v12 = RpcBindingSetOption(hBinding, 9u, 1u);
  v3 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v3 = (unsigned __int16)v12 | 0x80070000;
    v7 = 452;
    goto LABEL_19;
  }
  v3 = 0;
  *a1 = hBinding;
  hBinding = 0;
LABEL_41:
  LocalFree(Sid);
  if ( hBinding )
    RpcBindingFree(&hBinding);
  RpcStringFreeW(&StringBinding);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000f9f0  push    rbp
0x18000f9f2  push    rbx
0x18000f9f3  push    rsi
0x18000f9f4  push    rdi
0x18000f9f5  push    r12
0x18000f9f7  push    r14
0x18000f9f9  push    r15
0x18000f9fb  mov     rbp, rsp
0x18000f9fe  sub     rsp, 70h
0x18000fa02  xor     esi, esi
0x18000fa04  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18000fa0b  xor     eax, eax
0x18000fa0d  mov     [rcx], rsi
0x18000fa10  xorps   xmm0, xmm0
0x18000fa13  mov     [rbp+var_8], rax
0x18000fa17  lea     rax, [rbp+String]
0x18000fa1b  mov     [rbp+Sid], rsi
0x18000fa1f  mov     rdi, rcx
0x18000fa22  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18000fa27  xor     r9d, r9d; Endpoint
0x18000fa2a  mov     [rsp+70h+Options], rsi; Options
0x18000fa2f  xor     r8d, r8d; NetworkAddr
0x18000fa32  mov     [rbp+var_30], rsi
0x18000fa36  xor     ecx, ecx; ObjUuid
0x18000fa38  mov     [rbp+hBinding], rsi
0x18000fa3c  movups  xmmword ptr [rbp+var_28.Version], xmm0
0x18000fa40  mov     [rbp+String], rsi
0x18000fa44  movups  [rbp+var_18], xmm0
0x18000fa48  mov     [rbp+Binding], rsi
0x18000fa4c  call    cs:__imp_RpcStringBindingComposeW
0x18000fa52  mov     r14d, 80070000h
0x18000fa58  lea     r15, aOnecoreDsSecur_0; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000fa5f  lea     r12, aHr; "hr"
0x18000fa66  mov     ebx, eax
0x18000fa68  test    eax, eax
0x18000fa6a  jz      short loc_18000FA89
0x18000fa6c  jle     short loc_18000FA74
0x18000fa6e  movzx   ebx, ax
0x18000fa71  or      ebx, r14d
0x18000fa74  mov     r9d, 133h; unsigned int
0x18000fa7a  mov     r8, r15; char *
0x18000fa7d  mov     rdx, r12; char *
0x18000fa80  mov     ecx, ebx; unsigned int
0x18000fa82  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000fa87  jmp     short loc_18000FAD6
0x18000fa89  mov     rcx, [rbp+String]; StringBinding
0x18000fa8d  lea     rdx, [rbp+Binding]; Binding
0x18000fa91  call    cs:__imp_RpcBindingFromStringBindingW
0x18000fa97  mov     ebx, eax
0x18000fa99  test    eax, eax
0x18000fa9b  jz      short loc_18000FAAD
0x18000fa9d  jle     short loc_18000FAA5
0x18000fa9f  movzx   ebx, ax
0x18000faa2  or      ebx, r14d
0x18000faa5  mov     r9d, 13Dh
0x18000faab  jmp     short loc_18000FA7A
0x18000faad  mov     rcx, [rbp+Binding]; Binding
0x18000fab1  lea     rdx, qword_18001C2F0; IfSpec
0x18000fab8  call    cs:__imp_RpcEpResolveBinding
0x18000fabe  mov     ebx, eax
0x18000fac0  test    eax, eax
0x18000fac2  jz      short loc_18000FAD4
0x18000fac4  jle     short loc_18000FACC
0x18000fac6  movzx   ebx, ax
0x18000fac9  or      ebx, r14d
0x18000facc  mov     r9d, 147h
0x18000fad2  jmp     short loc_18000FA7A
0x18000fad4  mov     ebx, esi
0x18000fad6  cmp     [rbp+Binding], rsi
0x18000fada  jz      short loc_18000FAE6
0x18000fadc  lea     rcx, [rbp+Binding]; Binding
0x18000fae0  call    cs:__imp_RpcBindingFree
0x18000fae6  lea     rcx, [rbp+String]; String
0x18000faea  call    cs:__imp_RpcStringFreeW
0x18000faf0  test    ebx, ebx
0x18000faf2  jns     short loc_18000FB0C
0x18000faf4  mov     r9d, 17Eh; unsigned int
0x18000fafa  mov     r8, r15; char *
0x18000fafd  mov     rdx, r12; char *
0x18000fb00  mov     ecx, ebx; unsigned int
0x18000fb02  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000fb07  jmp     loc_18000FC40
0x18000fb0c  lea     rax, [rbp+var_30]
0x18000fb10  xor     r8d, r8d; NetworkAddr
0x18000fb13  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18000fb18  lea     r9, Endpoint; "kdssvc_lrpc"
0x18000fb1f  lea     rdx, aNcalrpc; "ncalrpc"
0x18000fb26  mov     [rsp+70h+Options], rsi; Options
0x18000fb2b  xor     ecx, ecx; ObjUuid
0x18000fb2d  call    cs:__imp_RpcStringBindingComposeW
0x18000fb33  mov     ebx, eax
0x18000fb35  test    eax, eax
0x18000fb37  jz      short loc_18000FB49
0x18000fb39  jle     short loc_18000FB41
0x18000fb3b  movzx   ebx, ax
0x18000fb3e  or      ebx, r14d
0x18000fb41  mov     r9d, 18Dh
0x18000fb47  jmp     short loc_18000FAFA
0x18000fb49  mov     rcx, [rbp+var_30]; StringBinding
0x18000fb4d  lea     rdx, [rbp+hBinding]; Binding
0x18000fb51  call    cs:__imp_RpcBindingFromStringBindingW
0x18000fb57  mov     ebx, eax
0x18000fb59  test    eax, eax
0x18000fb5b  jz      short loc_18000FB6D
0x18000fb5d  jle     short loc_18000FB65
0x18000fb5f  movzx   ebx, ax
0x18000fb62  or      ebx, r14d
0x18000fb65  mov     r9d, 197h
0x18000fb6b  jmp     short loc_18000FAFA
0x18000fb6d  lea     rdx, [rbp+Sid]; Sid
0x18000fb71  lea     rcx, StringSid; "S-1-5-18"
0x18000fb78  call    cs:__imp_ConvertStringSidToSidW
0x18000fb7e  test    eax, eax
0x18000fb80  jnz     short loc_18000FB9F
0x18000fb82  call    cs:__imp_GetLastError
0x18000fb88  mov     ebx, eax
0x18000fb8a  test    eax, eax
0x18000fb8c  jle     short loc_18000FB94
0x18000fb8e  movzx   ebx, ax
0x18000fb91  or      ebx, r14d
0x18000fb94  mov     r9d, 1A2h
0x18000fb9a  jmp     loc_18000FAFA
0x18000fb9f  mov     rcx, [rbp+hBinding]; Binding
0x18000fba3  mov     eax, 3
0x18000fba8  mov     [rbp+var_28.Version], eax
0x18000fbab  xor     edx, edx; ServerPrincName
0x18000fbad  mov     qword ptr [rbp+var_28.ImpersonationType], rax
0x18000fbb1  mov     rax, [rbp+Sid]
0x18000fbb5  mov     [rbp+var_8], rax
0x18000fbb9  lea     rax, [rbp+var_28]
0x18000fbbd  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x18000fbc2  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18000fbc6  mov     dword ptr [rsp+70h+StringBinding], esi; AuthzSvc
0x18000fbca  lea     r8d, [rdx+6]; AuthnLevel
0x18000fbce  mov     [rsp+70h+Options], rsi; AuthIdentity
0x18000fbd3  mov     qword ptr [rbp+var_18+4], rsi
0x18000fbd7  mov     dword ptr [rbp+var_18+0Ch], esi
0x18000fbda  mov     [rbp+var_28.Capabilities], 1
0x18000fbe1  mov     [rbp+var_28.IdentityTracking], 1
0x18000fbe8  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000fbee  mov     ebx, eax
0x18000fbf0  test    eax, eax
0x18000fbf2  jz      short loc_18000FC07
0x18000fbf4  jle     short loc_18000FBFC
0x18000fbf6  movzx   ebx, ax
0x18000fbf9  or      ebx, r14d
0x18000fbfc  mov     r9d, 1B9h
0x18000fc02  jmp     loc_18000FAFA
0x18000fc07  mov     rcx, [rbp+hBinding]; hBinding
0x18000fc0b  mov     edx, 9; option
0x18000fc10  lea     r8d, [rdx-8]; optionValue
0x18000fc14  call    cs:__imp_RpcBindingSetOption
0x18000fc1a  mov     ebx, eax
0x18000fc1c  test    eax, eax
0x18000fc1e  jz      short loc_18000FC33
0x18000fc20  jle     short loc_18000FC28
0x18000fc22  movzx   ebx, ax
0x18000fc25  or      ebx, r14d
0x18000fc28  mov     r9d, 1C4h
0x18000fc2e  jmp     loc_18000FAFA
0x18000fc33  mov     rax, [rbp+hBinding]
0x18000fc37  mov     ebx, esi
0x18000fc39  mov     [rdi], rax
0x18000fc3c  mov     [rbp+hBinding], rsi
0x18000fc40  mov     rcx, [rbp+Sid]; hMem
0x18000fc44  call    cs:__imp_LocalFree
0x18000fc4a  cmp     [rbp+hBinding], rsi
0x18000fc4e  jz      short loc_18000FC5A
0x18000fc50  lea     rcx, [rbp+hBinding]; Binding
0x18000fc54  call    cs:__imp_RpcBindingFree
0x18000fc5a  lea     rcx, [rbp+var_30]; String
0x18000fc5e  call    cs:__imp_RpcStringFreeW
0x18000fc64  mov     eax, ebx
0x18000fc66  add     rsp, 70h
0x18000fc6a  pop     r15
0x18000fc6c  pop     r14
0x18000fc6e  pop     r12
0x18000fc70  pop     rdi
0x18000fc71  pop     rsi
0x18000fc72  pop     rbx
0x18000fc73  pop     rbp
0x18000fc74  retn
```
