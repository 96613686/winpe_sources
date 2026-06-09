# FwRuleUnlocalize(void *,_tag_FW_RULE *)

- ea: `0x180009760`
- end: `0x180009e5d`
- name: `?FwRuleUnlocalize@@YAJPEAXPEAU_tag_FW_RULE@@@Z`
- size: `1789`
- prototype: `__int64 __fastcall(void *, struct _tag_FW_RULE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180014368`

## callees

- `0x180005954`
- `0x180009080`
- `0x180009760`
- `0x180009fb0`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180009831`
- `ntdll!EtwEventWrite` at `0x1800098e0`
- `ntdll!EtwEventWrite` at `0x1800099cf`
- `ntdll!EtwEventWrite` at `0x180009a7a`
- `ntdll!EtwEventWrite` at `0x180009831`
- `ntdll!EtwEventWrite` at `0x1800098e0`
- `ntdll!EtwEventWrite` at `0x1800099cf`
- `ntdll!EtwEventWrite` at `0x180009a7a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000984d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800099f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000984d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800099f2`
- `fwbase!FwBaseFree` at `0x180009caf`
- `fwbase!FwBaseFree` at `0x180009cf2`
- `fwbase!FwBaseFree` at `0x180009e17`
- `fwbase!FwBaseFree` at `0x180009caf`
- `fwbase!FwBaseFree` at `0x180009cf2`
- `fwbase!FwBaseFree` at `0x180009e17`
- `fwbase!FwReportReturnError` at `0x18000990e`
- `fwbase!FwReportReturnError` at `0x18000991d`
- `fwbase!FwReportReturnError` at `0x180009a97`
- `fwbase!FwReportReturnError` at `0x180009aa6`
- `fwbase!FwReportReturnError` at `0x18000990e`
- `fwbase!FwReportReturnError` at `0x18000991d`
- `fwbase!FwReportReturnError` at `0x180009a97`
- `fwbase!FwReportReturnError` at `0x180009aa6`
- `fwbase!FwStringCopy` at `0x180009cc1`
- `fwbase!FwStringCopy` at `0x180009d0d`
- `fwbase!FwStringCopy` at `0x180009e29`
- `fwbase!FwStringCopy` at `0x180009cc1`
- `fwbase!FwStringCopy` at `0x180009d0d`
- `fwbase!FwStringCopy` at `0x180009e29`

## pseudocode

```c
__int64 __fastcall FwRuleUnlocalize(__int64 a1, struct _tag_FW_RULE *a2)
{
  __int64 v2; // rbx
  _QWORD *v5; // r14
  FwPolicy2 *v6; // rcx
  unsigned int v7; // eax
  signed int v8; // ebx
  FwPolicy2 *v9; // rcx
  __int64 v10; // rax
  bool v11; // sf
  _QWORD *v12; // rsi
  int v13; // eax
  signed int v14; // edi
  __int64 v15; // rbx
  unsigned int v16; // eax
  bool v17; // sf
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r10
  unsigned __int16 *v21; // rax
  __int64 v22; // r10
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rcx
  __int64 v26; // r10
  unsigned __int16 *v27; // rax
  __int64 v28; // r10
  int v29; // r8d
  int v30; // r9d
  unsigned int v31; // ebx
  FwPolicy2 *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  unsigned __int16 *v36; // rax
  __int64 v37; // r9
  int v38; // edx
  int v39; // r8d
  _QWORD *v40; // [rsp+60h] [rbp-79h] BYREF
  _QWORD *v41; // [rsp+68h] [rbp-71h] BYREF
  int v42; // [rsp+70h] [rbp-69h] BYREF
  int v43; // [rsp+74h] [rbp-65h]
  __int128 *v44; // [rsp+78h] [rbp-61h]
  __int64 v45; // [rsp+80h] [rbp-59h]
  int v46; // [rsp+88h] [rbp-51h] BYREF
  int v47; // [rsp+8Ch] [rbp-4Dh]
  __int128 *v48; // [rsp+90h] [rbp-49h]
  __int64 v49; // [rsp+98h] [rbp-41h]
  __int128 v50; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-29h]
  __int128 v52; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v53; // [rsp+C8h] [rbp-11h]
  __int128 v54; // [rsp+D0h] [rbp-9h] BYREF
  __int128 v55; // [rsp+E0h] [rbp+7h] BYREF
  int v56; // [rsp+F0h] [rbp+17h] BYREF
  int v57; // [rsp+F4h] [rbp+1Bh] BYREF

  v2 = *((_QWORD *)a2 + 2);
  v40 = 0;
  v56 = 0;
  v51 = 0;
  v42 = 545;
  v5 = 0;
  v43 = 1;
  v50 = 0;
  v44 = 0;
  v54 = 0;
  v45 = 0x10000;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  *(_QWORD *)&v50 = 2;
  *((_QWORD *)&v54 + 1) = &v50;
  v44 = &v54;
  DWORD2(v50) = 5;
  v51 = v2;
  LODWORD(v54) = 1;
  v43 = 1;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v6 + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v7 = Int_FWQueryObject(
         0,
         (unsigned int)FWVerifyFirewallRuleQuery,
         (unsigned int)RPC_FWQueryFirewallRules,
         (unsigned int)RRPC_FWQueryFirewallRules,
         (__int64)Int_RPC_FWEnumFirewallRules2_0,
         (__int64)Int_RRPC_FWEnumFirewallRules2_0,
         a1,
         (__int64)&v42,
         7,
         (__int64)&v56,
         (__int64)&v40,
         0);
  v8 = v7;
  if ( !v7 )
    goto LABEL_8;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v7);
LABEL_8:
    v9 = WPP_GLOBAL_Control;
  }
  v10 = g_Provider;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
    v9 = WPP_GLOBAL_Control;
    v10 = g_Provider;
  }
  v11 = v8 < 0;
  if ( v8 > 0 )
  {
    v8 = (unsigned __int16)v8 | 0x80070000;
    v11 = v8 < 0;
  }
  if ( !v11 )
  {
    if ( v56 )
    {
      v12 = v40;
      v40 = 0;
      goto LABEL_16;
    }
    v8 = -2147023728;
  }
  v12 = 0;
  FwReportReturnError("FwRuleLookup", (unsigned int)v8);
  v13 = FwReportReturnError("FwRuleLookup", (unsigned int)v8);
  v14 = v13;
  if ( v13 < 0 )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_42;
    v34 = 61;
    goto LABEL_72;
  }
  v9 = WPP_GLOBAL_Control;
  v10 = g_Provider;
LABEL_16:
  v15 = *((_QWORD *)a2 + 2);
  v41 = 0;
  v52 = 0;
  v53 = 0;
  v55 = 0;
  v57 = 0;
  v46 = 545;
  v47 = 1;
  v48 = 0;
  v49 = 0x10000;
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)v9 + 2), 60, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids);
    v9 = WPP_GLOBAL_Control;
    v10 = g_Provider;
  }
  *(_QWORD *)&v52 = 2;
  *((_QWORD *)&v55 + 1) = &v52;
  v48 = &v55;
  DWORD2(v52) = 5;
  v53 = v15;
  LODWORD(v55) = 1;
  v47 = 1;
  if ( v10 )
  {
    EtwEventWrite(v10, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v9 + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v16 = Int_FWQueryObject(
          0,
          (unsigned int)FWVerifyFirewallRuleQuery,
          (unsigned int)RPC_FWQueryFirewallRules,
          (unsigned int)RRPC_FWQueryFirewallRules,
          (__int64)Int_RPC_FWEnumFirewallRules2_0,
          (__int64)Int_RRPC_FWEnumFirewallRules2_0,
          a1,
          (__int64)&v46,
          0,
          (__int64)&v57,
          (__int64)&v41,
          0);
  v14 = v16;
  if ( v16 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v16);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  v17 = v14 < 0;
  if ( v14 > 0 )
  {
    v14 = (unsigned __int16)v14 | 0x80070000;
    v17 = v14 < 0;
  }
  if ( v17 )
    goto LABEL_28;
  if ( !v57 )
  {
    v14 = -2147023728;
LABEL_28:
    FwReportReturnError("FwRuleLookup", (unsigned int)v14);
    v13 = FwReportReturnError("FwRuleLookup", (unsigned int)v14);
    v14 = v13;
    if ( v13 >= 0 )
      goto LABEL_29;
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_42;
    v34 = 62;
LABEL_72:
    WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids, (unsigned int)v13);
    goto LABEL_42;
  }
  v5 = v41;
  v41 = 0;
LABEL_29:
  v18 = *((_QWORD *)a2 + 3);
  if ( !v18 )
    goto LABEL_30;
  v35 = v12[3];
  if ( !v35 )
    goto LABEL_30;
  v36 = (unsigned __int16 *)*((_QWORD *)a2 + 3);
  v37 = v35 - v18;
  do
  {
    v38 = *(unsigned __int16 *)((char *)v36 + v37);
    v39 = *v36 - v38;
    if ( v39 )
      break;
    ++v36;
  }
  while ( v38 );
  if ( !v39
    && (FwBaseFree(v18), *((_QWORD *)a2 + 3) = 0, v13 = FwStringCopy(v5[3], (char *)a2 + 24), v14 = v13, v13 < 0) )
  {
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v34 = 63;
      goto LABEL_72;
    }
  }
  else
  {
LABEL_30:
    v19 = *((_QWORD *)a2 + 4);
    if ( !v19 )
      goto LABEL_36;
    v20 = v12[4];
    if ( !v20 )
      goto LABEL_36;
    v21 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
    v22 = v20 - v19;
    do
    {
      v23 = *(unsigned __int16 *)((char *)v21 + v22);
      v24 = *v21 - v23;
      if ( v24 )
        break;
      ++v21;
    }
    while ( v23 );
    if ( v24
      || (FwBaseFree(v19), *((_QWORD *)a2 + 4) = 0, v13 = FwStringCopy(v5[4], (char *)a2 + 32), v14 = v13, v13 >= 0) )
    {
LABEL_36:
      v25 = *((_QWORD *)a2 + 39);
      if ( !v25 )
        goto LABEL_42;
      v26 = v12[39];
      if ( !v26 )
        goto LABEL_42;
      v27 = (unsigned __int16 *)*((_QWORD *)a2 + 39);
      v28 = v26 - v25;
      do
      {
        v29 = *(unsigned __int16 *)((char *)v27 + v28);
        v30 = *v27 - v29;
        if ( v30 )
          break;
        ++v27;
      }
      while ( v29 );
      if ( v30 )
        goto LABEL_42;
      FwBaseFree(v25);
      *((_QWORD *)a2 + 39) = 0;
      v13 = FwStringCopy(v5[39], (char *)a2 + 312);
      v14 = v13;
      if ( v13 >= 0 )
        goto LABEL_42;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_42;
      v34 = 65;
      goto LABEL_72;
    }
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v34 = 64;
      goto LABEL_72;
    }
  }
LABEL_42:
  v31 = 0;
  if ( v14 != -2147023728 )
    v31 = v14;
  FWFreeFirewallRules(v12);
  FWFreeFirewallRules(v5);
  return v31;
}

```

## disassembly

```asm
0x180009760  mov     [rsp-8+arg_10], rbx
0x180009765  push    rbp
0x180009766  push    rsi
0x180009767  push    rdi
0x180009768  push    r12
0x18000976a  push    r13
0x18000976c  push    r14
0x18000976e  push    r15
0x180009770  lea     rbp, [rsp-27h]
0x180009775  sub     rsp, 100h
0x18000977c  mov     rax, cs:__security_cookie
0x180009783  xor     rax, rsp
0x180009786  mov     [rbp+57h+var_38], rax
0x18000978a  mov     rbx, [rdx+10h]
0x18000978e  xor     r13d, r13d
0x180009791  xorps   xmm0, xmm0
0x180009794  mov     [rbp+57h+var_D0], r13
0x180009798  xor     eax, eax
0x18000979a  mov     [rbp+57h+var_40], r13d
0x18000979e  mov     [rbp+57h+var_80], rax
0x1800097a2  mov     r15, rdx
0x1800097a5  mov     r12, rcx
0x1800097a8  mov     [rbp+57h+var_C0], 221h
0x1800097af  mov     r14d, r13d
0x1800097b2  mov     [rbp+57h+var_BC], 1
0x1800097b9  movups  [rbp+57h+var_90], xmm0
0x1800097bd  mov     [rbp+57h+var_B8], r13
0x1800097c1  movups  [rbp+57h+var_60], xmm0
0x1800097c5  mov     [rbp+57h+var_B0], 10000h
0x1800097cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097d4  lea     rsi, WPP_GLOBAL_Control
0x1800097db  cmp     rcx, rsi
0x1800097de  jnz     loc_180009B85
0x1800097e4  lea     rax, [rbp+57h+var_90]
0x1800097e8  mov     qword ptr [rbp+57h+var_90], 2
0x1800097f0  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800097f4  lea     rax, [rbp+57h+var_60]
0x1800097f8  mov     [rbp+57h+var_B8], rax
0x1800097fc  mov     rax, cs:g_Provider
0x180009803  mov     dword ptr [rbp+57h+var_90+8], 5
0x18000980a  mov     [rbp+57h+var_80], rbx
0x18000980e  mov     dword ptr [rbp+57h+var_60], 1
0x180009815  mov     [rbp+57h+var_BC], 1
0x18000981c  test    rax, rax
0x18000981f  jz      short loc_18000983E
0x180009821  xor     r9d, r9d
0x180009824  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x18000982b  xor     r8d, r8d
0x18000982e  mov     rcx, rax
0x180009831  call    cs:__imp_EtwEventWrite
0x180009837  mov     rcx, cs:WPP_GLOBAL_Control
0x18000983e  cmp     rcx, rsi
0x180009841  jz      short loc_18000984D
0x180009843  test    byte ptr [rcx+1Ch], 8
0x180009847  jnz     loc_180009D54
0x18000984d  call    cs:__imp_GetTickCount64
0x180009853  mov     [rsp+130h+var_D8], r13d
0x180009858  lea     rax, [rbp+57h+var_D0]
0x18000985c  mov     [rsp+130h+var_E0], rax
0x180009861  lea     rdi, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180009868  lea     rax, [rbp+57h+var_40]
0x18000986c  xor     ecx, ecx
0x18000986e  mov     [rsp+130h+var_E8], rax
0x180009873  lea     r9, RRPC_FWQueryFirewallRules
0x18000987a  mov     [rsp+130h+var_F0], 7
0x180009881  lea     rax, [rbp+57h+var_C0]
0x180009885  mov     [rsp+130h+var_F8], rax
0x18000988a  lea     r8, RPC_FWQueryFirewallRules
0x180009891  mov     [rsp+130h+var_100], r12
0x180009896  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000989d  mov     [rsp+130h+var_108], rdi
0x1800098a2  lea     rdx, FWVerifyFirewallRuleQuery
0x1800098a9  mov     [rsp+130h+var_110], rax
0x1800098ae  call    Int_FWQueryObject
0x1800098b3  mov     ebx, eax
0x1800098b5  test    eax, eax
0x1800098b7  jnz     loc_180009D6E
0x1800098bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098c4  mov     rax, cs:g_Provider
0x1800098cb  test    rax, rax
0x1800098ce  jz      short loc_1800098F4
0x1800098d0  xor     r9d, r9d
0x1800098d3  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x1800098da  xor     r8d, r8d
0x1800098dd  mov     rcx, rax
0x1800098e0  call    cs:__imp_EtwEventWrite
0x1800098e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098ed  mov     rax, cs:g_Provider
0x1800098f4  test    ebx, ebx
0x1800098f6  jg      loc_180009C0A
0x1800098fc  jns     loc_180009BE2
0x180009902  mov     edx, ebx
0x180009904  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x18000990b  mov     rsi, r13
0x18000990e  call    cs:__imp_FwReportReturnError
0x180009914  mov     edx, ebx
0x180009916  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x18000991d  call    cs:__imp_FwReportReturnError
0x180009923  mov     edi, eax
0x180009925  test    eax, eax
0x180009927  js      loc_180009C2A
0x18000992d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009934  lea     rdi, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000993b  mov     rax, cs:g_Provider
0x180009942  mov     rbx, [r15+10h]
0x180009946  xorps   xmm0, xmm0
0x180009949  xor     edx, edx
0x18000994b  mov     [rbp+57h+var_C8], r13
0x18000994f  movups  [rbp+57h+var_78], xmm0
0x180009953  mov     [rbp+57h+var_68], rdx
0x180009957  movups  [rbp+57h+var_50], xmm0
0x18000995b  mov     [rbp+57h+var_3C], r13d
0x18000995f  mov     [rbp+57h+var_A8], 221h
0x180009966  mov     [rbp+57h+var_A4], 1
0x18000996d  mov     [rbp+57h+var_A0], r13
0x180009971  mov     [rbp+57h+var_98], 10000h
0x180009979  lea     rdx, WPP_GLOBAL_Control
0x180009980  cmp     rcx, rdx
0x180009983  jnz     loc_180009BB0
0x180009989  mov     qword ptr [rbp+57h+var_78], 2
0x180009991  lea     r8, [rbp+57h+var_78]
0x180009995  mov     qword ptr [rbp+57h+var_50+8], r8
0x180009999  lea     r8, [rbp+57h+var_50]
0x18000999d  mov     [rbp+57h+var_A0], r8
0x1800099a1  mov     dword ptr [rbp+57h+var_78+8], 5
0x1800099a8  mov     [rbp+57h+var_68], rbx
0x1800099ac  mov     dword ptr [rbp+57h+var_50], 1
0x1800099b3  mov     [rbp+57h+var_A4], 1
0x1800099ba  test    rax, rax
0x1800099bd  jz      short loc_1800099DC
0x1800099bf  xor     r9d, r9d
0x1800099c2  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x1800099c9  xor     r8d, r8d
0x1800099cc  mov     rcx, rax
0x1800099cf  call    cs:__imp_EtwEventWrite
0x1800099d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099dc  lea     rax, WPP_GLOBAL_Control
0x1800099e3  cmp     rcx, rax
0x1800099e6  jz      short loc_1800099F2
0x1800099e8  test    byte ptr [rcx+1Ch], 8
0x1800099ec  jnz     loc_180009DB2
0x1800099f2  call    cs:__imp_GetTickCount64
0x1800099f8  mov     [rsp+130h+var_D8], r13d
0x1800099fd  lea     rcx, [rbp+57h+var_C8]
0x180009a01  mov     [rsp+130h+var_E0], rcx
0x180009a06  lea     rax, [rbp+57h+var_A8]
0x180009a0a  lea     rcx, [rbp+57h+var_3C]
0x180009a0e  mov     [rsp+130h+var_E8], rcx
0x180009a13  lea     r9, RRPC_FWQueryFirewallRules
0x180009a1a  mov     [rsp+130h+var_F0], r13w
0x180009a20  lea     r8, RPC_FWQueryFirewallRules
0x180009a27  mov     [rsp+130h+var_F8], rax
0x180009a2c  lea     rdx, FWVerifyFirewallRuleQuery
0x180009a33  mov     [rsp+130h+var_100], r12
0x180009a38  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180009a3f  mov     [rsp+130h+var_108], rdi
0x180009a44  xor     ecx, ecx
0x180009a46  mov     [rsp+130h+var_110], rax
0x180009a4b  call    Int_FWQueryObject
0x180009a50  mov     edi, eax
0x180009a52  test    eax, eax
0x180009a54  jnz     loc_180009DCC
0x180009a5a  lea     r12, WPP_GLOBAL_Control
0x180009a61  mov     rcx, cs:g_Provider
0x180009a68  test    rcx, rcx
0x180009a6b  jz      short loc_180009A80
0x180009a6d  xor     r9d, r9d
0x180009a70  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x180009a77  xor     r8d, r8d
0x180009a7a  call    cs:__imp_EtwEventWrite
0x180009a80  test    edi, edi
0x180009a82  jg      loc_180009C1A
0x180009a88  jns     loc_180009BF6
0x180009a8e  mov     edx, edi
0x180009a90  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x180009a97  call    cs:__imp_FwReportReturnError
0x180009a9d  mov     edx, edi
0x180009a9f  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x180009aa6  call    cs:__imp_FwReportReturnError
0x180009aac  mov     edi, eax
0x180009aae  test    eax, eax
0x180009ab0  js      loc_180009C55
0x180009ab6  mov     rcx, [r15+18h]
0x180009aba  test    rcx, rcx
0x180009abd  jnz     loc_180009C79
0x180009ac3  mov     rcx, [r15+20h]
0x180009ac7  test    rcx, rcx
0x180009aca  jz      short loc_180009B00
0x180009acc  mov     r10, [rsi+20h]
0x180009ad0  test    r10, r10
0x180009ad3  jz      short loc_180009B00
0x180009ad5  mov     rax, rcx
0x180009ad8  sub     r10, rcx
0x180009adb  nop     dword ptr [rax+rax+00h]
0x180009ae0  movzx   r9d, word ptr [rax]
0x180009ae4  movzx   r8d, word ptr [rax+r10]
0x180009ae9  sub     r9d, r8d
0x180009aec  jnz     short loc_180009AF7
0x180009aee  add     rax, 2
0x180009af2  test    r8d, r8d
0x180009af5  jnz     short loc_180009AE0
0x180009af7  test    r9d, r9d
0x180009afa  jz      loc_180009E17
0x180009b00  mov     rcx, [r15+138h]
0x180009b07  test    rcx, rcx
0x180009b0a  jz      short loc_180009B40
0x180009b0c  mov     r10, [rsi+138h]
0x180009b13  test    r10, r10
0x180009b16  jz      short loc_180009B40
0x180009b18  mov     rax, rcx
0x180009b1b  sub     r10, rcx
0x180009b1e  xchg    ax, ax
0x180009b20  movzx   r9d, word ptr [rax]
0x180009b24  movzx   r8d, word ptr [rax+r10]
0x180009b29  sub     r9d, r8d
0x180009b2c  jnz     short loc_180009B37
0x180009b2e  add     rax, 2
0x180009b32  test    r8d, r8d
0x180009b35  jnz     short loc_180009B20
0x180009b37  test    r9d, r9d
0x180009b3a  jz      loc_180009CF2
0x180009b40  cmp     edi, 80070490h
0x180009b46  mov     ebx, r13d
0x180009b49  mov     rcx, rsi
0x180009b4c  cmovnz  ebx, edi
0x180009b4f  call    FWFreeFirewallRules
0x180009b54  mov     rcx, r14
0x180009b57  call    FWFreeFirewallRules
0x180009b5c  mov     eax, ebx
0x180009b5e  mov     rcx, [rbp+57h+var_38]
0x180009b62  xor     rcx, rsp; StackCookie
0x180009b65  call    __security_check_cookie
0x180009b6a  mov     rbx, [rsp+130h+arg_10]
0x180009b72  add     rsp, 100h
0x180009b79  pop     r15
0x180009b7b  pop     r14
0x180009b7d  pop     r13
0x180009b7f  pop     r12
0x180009b81  pop     rdi
0x180009b82  pop     rsi
0x180009b83  pop     rbp
0x180009b84  retn
0x180009b85  test    byte ptr [rcx+1Ch], 8
0x180009b89  jz      loc_1800097E4
0x180009b8f  mov     rcx, [rcx+10h]
0x180009b93  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180009b9a  mov     edx, 3Ch ; '<'
0x180009b9f  call    WPP_SF_
0x180009ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bab  jmp     loc_1800097E4
0x180009bb0  test    byte ptr [rcx+1Ch], 8
0x180009bb4  jz      loc_180009989
0x180009bba  mov     rcx, [rcx+10h]
0x180009bbe  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x180009bc5  mov     edx, 3Ch ; '<'
0x180009bca  call    WPP_SF_
0x180009bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bd6  mov     rax, cs:g_Provider
0x180009bdd  jmp     loc_180009989
0x180009be2  cmp     [rbp+57h+var_40], r13d
0x180009be6  ja      loc_180009DA5
0x180009bec  mov     ebx, 80070490h
0x180009bf1  jmp     loc_180009902
0x180009bf6  cmp     [rbp+57h+var_3C], r13d
0x180009bfa  ja      loc_180009E0A
0x180009c00  mov     edi, 80070490h
0x180009c05  jmp     loc_180009A8E
0x180009c0a  movzx   ebx, bx
0x180009c0d  or      ebx, 80070000h
0x180009c13  test    ebx, ebx
0x180009c15  jmp     loc_1800098FC
0x180009c1a  movzx   edi, di
0x180009c1d  or      edi, 80070000h
0x180009c23  test    edi, edi
0x180009c25  jmp     loc_180009A88
0x180009c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c31  lea     rdx, WPP_GLOBAL_Control
0x180009c38  cmp     rcx, rdx
0x180009c3b  jz      loc_180009B40
0x180009c41  test    byte ptr [rcx+1Ch], 1
0x180009c45  jz      loc_180009B40
0x180009c4b  mov     edx, 3Dh ; '='
0x180009c50  jmp     loc_180009D3C
0x180009c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c5c  cmp     rcx, r12
0x180009c5f  jz      loc_180009B40
0x180009c65  test    byte ptr [rcx+1Ch], 1
0x180009c69  jz      loc_180009B40
0x180009c6f  mov     edx, 3Eh ; '>'
0x180009c74  jmp     loc_180009D3C
0x180009c79  mov     r9, [rsi+18h]
0x180009c7d  test    r9, r9
0x180009c80  jz      loc_180009AC3
0x180009c86  mov     rax, rcx
0x180009c89  sub     r9, rcx
0x180009c8c  nop     dword ptr [rax+00h]
0x180009c90  movzx   r8d, word ptr [rax]
0x180009c94  movzx   edx, word ptr [rax+r9]
0x180009c99  sub     r8d, edx
0x180009c9c  jnz     short loc_180009CA6
  ... truncated ...
```
