# Int_FWGetOrSetGlobalConfig

- ea: `0x18000db60`
- end: `0x18000e6b8`
- name: `Int_FWGetOrSetGlobalConfig`
- size: `2904`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d850`
- `0x18000d9d0`
- `0x18000f920`
- `0x180050160`
- `0x1800502a0`

## callees

- `0x180005954`
- `0x18000d850`
- `0x18000db60`
- `0x18000e6c0`
- `0x180024c3c`
- `0x18002514c`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x1800516bc`
- `0x180051710`
- `0x180051cc0`
- `0x18005e010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b8ce`
- `RPCRT4!RpcExceptionFilter` at `0x18005b8ce`
- `RPCRT4!RpcBindingFree` at `0x18000e0ba`
- `RPCRT4!RpcBindingFree` at `0x18000e0ba`
- `fwbase!FwBaseFree` at `0x18000e0d0`
- `fwbase!FwBaseFree` at `0x18000e0d0`
- `fwbase!FwHResultToWindowsError` at `0x18000e4c0`
- `fwbase!FwHResultToWindowsError` at `0x18000e516`
- `fwbase!FwHResultToWindowsError` at `0x18000e4c0`
- `fwbase!FwHResultToWindowsError` at `0x18000e516`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18000e50e`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18000e50e`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18000e4b8`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18000e4b8`

## pseudocode

```c
__int64 __fastcall Int_FWGetOrSetGlobalConfig(
        int a1,
        unsigned __int16 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        unsigned int a7,
        __int64 a8,
        int *a9,
        _DWORD *a10)
{
  FwPolicy2 *v12; // rsi
  __int64 v13; // r8
  _BYTE *v14; // rbx
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // edi
  unsigned int v20; // eax
  int v21; // eax
  __int64 (__fastcall *v22)(int, int, int, int, int, __int64, int, __int64, __int64); // r10
  __int64 (__fastcall *v23)(int, int, int, int, int, __int64, int, __int64, __int64, __int64); // r11
  int v24; // eax
  unsigned int v25; // eax
  _DWORD *v26; // rcx
  __int64 (__fastcall *v27)(int, int, int, int, __int64, int); // rax
  unsigned int v28; // eax
  __int64 v29; // rdx
  unsigned int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rcx
  bool v33; // zf
  __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned __int16 v37; // ax
  __int64 v38; // r9
  unsigned int v39; // eax
  __int64 v40; // r8
  unsigned int GlobalConfig; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  int v46; // [rsp+A8h] [rbp-B0h] BYREF
  int v47; // [rsp+ACh] [rbp-ACh] BYREF
  __int64 v48; // [rsp+B0h] [rbp-A8h] BYREF
  int v49; // [rsp+B8h] [rbp-A0h] BYREF
  int v50; // [rsp+BCh] [rbp-9Ch] BYREF
  _BYTE v51[4]; // [rsp+C0h] [rbp-98h] BYREF
  int v52; // [rsp+C4h] [rbp-94h]

  v48 = a3;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 254, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    v12 = WPP_GLOBAL_Control;
  }
  memset_0(v51, 0, 0x50u);
  v49 = 0;
  v46 = 0;
  v50 = 0;
  if ( a5 )
  {
    v14 = (_BYTE *)a5;
    a2 = *(_WORD *)(a5 + 2);
    a4 = *(_DWORD *)(a5 + 16);
  }
  else
  {
    v14 = v51;
  }
  v15 = 512;
  if ( (unsigned __int16)(a2 - 512) > 0x21u )
  {
    v19 = 1306;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 255;
LABEL_162:
    v38 = v19;
    goto LABEL_163;
  }
  if ( a4 - 1 > 0xB )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 256;
    goto LABEL_162;
  }
  v13 = a7;
  if ( a4 == 6 && (a7 & 1) != 0 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 257;
    goto LABEL_162;
  }
  if ( (unsigned int)(a6 - 1) > 0x11 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 258;
    goto LABEL_162;
  }
  if ( !a9 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 259;
    goto LABEL_162;
  }
  if ( !a8 && *a9 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 260;
    goto LABEL_162;
  }
  if ( (a7 & 0xFFFFFFFE) != 0 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 261;
    goto LABEL_162;
  }
  if ( a4 <= 0xB && (v16 = 2148, _bittest(&v16, a4)) )
  {
    if ( a6 == 1 )
      goto LABEL_80;
  }
  else if ( a6 == 1 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 262;
    goto LABEL_162;
  }
  if ( a6 != 11 )
  {
    v17 = a1;
    goto LABEL_16;
  }
LABEL_80:
  v17 = a1;
  if ( !a1 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 263;
    goto LABEL_162;
  }
LABEL_16:
  if ( !a5 )
  {
    v18 = Int_FWCreateConnectionHandle(a2, v48, a4, 2 - (unsigned int)(v17 != 0), 0, v14);
    v19 = v18;
    if ( v18 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_95;
      v35 = 264;
      v38 = v18;
      goto LABEL_163;
    }
    v12 = WPP_GLOBAL_Control;
    if ( a2 > 0x200u && *((_DWORD *)v14 + 1) <= 1u )
    {
      v49 = 4;
      v36 = FWGetGlobalConfig(512, v48, 5, 11, 0, (__int64)&v46, (__int64)&v49);
      v19 = v36;
      if ( v36 == 1783 || v36 == 87 )
      {
        v19 = 0;
        v37 = 512;
        v46 = 512;
      }
      else
      {
        v37 = v46;
      }
      if ( v19 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_95;
        v35 = 265;
        goto LABEL_162;
      }
      if ( a2 > v37 )
        a2 = v37;
      v12 = WPP_GLOBAL_Control;
    }
  }
  v15 = (unsigned int)a6;
  if ( a6 >= 12 && a2 < 0x20Au )
  {
    v19 = 50;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 266;
    goto LABEL_162;
  }
  if ( a6 >= 14 && a2 < 0x214u )
  {
    v19 = 50;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 267;
    goto LABEL_162;
  }
  v20 = *((_DWORD *)v14 + 1);
  if ( v20 > 1 )
  {
    if ( v20 != 2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v39 = Int_FWOpenGPOPolicyStore(v14);
    v19 = v39;
    if ( v39 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_95;
      v35 = 271;
      v38 = v39;
      goto LABEL_163;
    }
    if ( !*((_QWORD *)v14 + 6) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !*((_QWORD *)v14 + 5) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v40 = *((_QWORD *)v14 + 6);
    if ( a1 )
    {
      GlobalConfig = FwGetGlobalConfig(a2, a4, v40, (unsigned int)a6, a8, a9);
      v42 = FwHResultToWindowsError(GlobalConfig);
      v19 = v42;
      if ( v42 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_95;
        v35 = 272;
        v38 = v42;
        goto LABEL_163;
      }
    }
    else
    {
      v43 = FwSetGlobalConfig(a2, a4, v40, (unsigned int)a6, a8, *a9);
      v44 = FwHResultToWindowsError(v43);
      v19 = v44;
      if ( v44 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_95;
        v35 = 273;
        v38 = v44;
        goto LABEL_163;
      }
    }
    v45 = Int_FWCloseGPOPolicyStore(v14, a1 == 0);
    v19 = v45;
    if ( !v45 )
      goto LABEL_164;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 274;
    v38 = v45;
LABEL_163:
    WPP_SF_d(*((_QWORD *)v12 + 2), v35, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v38);
LABEL_164:
    v12 = WPP_GLOBAL_Control;
LABEL_95:
    v26 = a10;
    goto LABEL_57;
  }
  if ( !*((_QWORD *)v14 + 4) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    LODWORD(v15) = a6;
  }
  if ( a1 )
  {
    v47 = 0;
    LODWORD(v48) = 0;
    v21 = *((_DWORD *)v14 + 1);
    v22 = RPC_FWGetGlobalConfig;
    if ( v21 )
      v22 = RRPC_FWGetGlobalConfig;
    v23 = RPC_FWGetGlobalConfig2_10;
    if ( v21 )
      v23 = RRPC_FWGetGlobalConfig2_10;
    v24 = *a9;
    if ( a2 >= 0x20Au )
      v25 = v23(*((_QWORD *)v14 + 4), a2, a4, v15, a7, a8, v24, (__int64)&v47, (__int64)&v48, (__int64)&v50);
    else
      v25 = v22(*((_QWORD *)v14 + 4), a2, a4, v15, a7, a8, v24, (__int64)&v47, (__int64)&v48);
    v19 = v25;
    if ( !v25 )
    {
      *a9 = v47;
LABEL_33:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_34;
    }
    if ( v25 == 234 )
    {
      *a9 = v48;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v29 = 276;
LABEL_55:
        WPP_SF_d(*((_QWORD *)v12 + 2), v29, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v25);
        goto LABEL_33;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v29 = 277;
        goto LABEL_55;
      }
    }
LABEL_34:
    if ( v19 )
    {
      if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v12 + 2), 268, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v19);
        v12 = WPP_GLOBAL_Control;
      }
      v26 = a10;
      goto LABEL_57;
    }
LABEL_56:
    v26 = a10;
    goto LABEL_57;
  }
  v27 = RRPC_FWSetGlobalConfig;
  if ( !v52 )
    v27 = RPC_FWSetGlobalConfig;
  v28 = v27(*((_QWORD *)v14 + 4), a2, a4, v15, a8, *a9);
  v19 = v28;
  if ( !v28 )
  {
    v12 = WPP_GLOBAL_Control;
    goto LABEL_56;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v28);
    v12 = WPP_GLOBAL_Control;
  }
  v26 = a10;
LABEL_57:
  if ( v26 )
  {
    *v26 = v50;
    v12 = WPP_GLOBAL_Control;
  }
  if ( !a5 )
  {
    if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v12 + 2), 378, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
      v12 = WPP_GLOBAL_Control;
    }
    if ( v14 )
    {
      v30 = *((_DWORD *)v14 + 1);
      if ( v30 > 1 )
      {
        if ( v30 != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        Int_FWCleanupGPOPolicyStore(v14, v15, v13);
      }
      else if ( *((_QWORD *)v14 + 4) )
      {
        v31 = RpcBindingFree((RPC_BINDING_HANDLE *)v14 + 4);
        if ( v31 )
          MicrosoftTelemetryAssertTriggeredArgs(v32, v31);
        *((_QWORD *)v14 + 4) = 0;
      }
      FwBaseFree(*((_QWORD *)v14 + 1));
      *((_QWORD *)v14 + 1) = 0;
      v12 = WPP_GLOBAL_Control;
    }
  }
  v33 = a2 == 545;
  if ( a2 < 0x221u )
  {
    if ( v19 == 1783 && !a1 )
    {
      v19 = 50;
      goto LABEL_74;
    }
    v33 = a2 == 545;
  }
  if ( v33 && v19 == 1783 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v12 = WPP_GLOBAL_Control;
  }
LABEL_74:
  if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v12 + 2), 275, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  return v19;
}

```

## disassembly

```asm
0x18000db60  mov     [rsp+arg_0], ecx
0x18000db64  push    rbx
0x18000db65  push    rsi
0x18000db66  push    rdi
0x18000db67  push    r12
0x18000db69  push    r13
0x18000db6b  push    r14
0x18000db6d  push    r15
0x18000db6f  sub     rsp, 120h
0x18000db76  mov     rax, cs:__security_cookie
0x18000db7d  xor     rax, rsp
0x18000db80  mov     [rsp+158h+var_48], rax
0x18000db88  mov     r13d, r9d
0x18000db8b  mov     [rsp+158h+var_A8], r8
0x18000db93  movzx   r14d, dx
0x18000db97  mov     [rsp+158h+var_F0], dx
0x18000db9c  mov     r12, [rsp+158h+arg_20]
0x18000dba4  mov     [rsp+158h+var_C0], r12
0x18000dbac  mov     rax, [rsp+158h+arg_38]
0x18000dbb4  mov     [rsp+158h+var_E0], rax
0x18000dbb9  mov     rdi, [rsp+158h+arg_40]
0x18000dbc1  mov     [rsp+158h+var_D0], rdi
0x18000dbc9  mov     rax, [rsp+158h+arg_48]
0x18000dbd1  mov     [rsp+158h+var_F8], rax
0x18000dbd6  mov     [rsp+158h+var_B8], rax
0x18000dbde  lea     rax, WPP_GLOBAL_Control
0x18000dbe5  mov     rsi, cs:WPP_GLOBAL_Control
0x18000dbec  cmp     rsi, rax
0x18000dbef  jnz     loc_18000E136
0x18000dbf5  xor     edx, edx; Val
0x18000dbf7  mov     r8d, 50h ; 'P'; Size
0x18000dbfd  lea     rcx, [rsp+158h+var_98]; void *
0x18000dc05  call    memset_0
0x18000dc0a  xor     r15d, r15d
0x18000dc0d  mov     [rsp+158h+var_A0], r15d
0x18000dc15  mov     [rsp+158h+var_B0], r15d
0x18000dc1d  mov     [rsp+158h+var_9C], r15d
0x18000dc25  test    r12, r12
0x18000dc28  jnz     loc_18000E2BA
0x18000dc2e  lea     rbx, [rsp+158h+var_98]
0x18000dc36  mov     [rsp+158h+var_C8], rbx
0x18000dc3e  mov     edx, 200h
0x18000dc43  movzx   eax, r14w
0x18000dc47  sub     ax, dx
0x18000dc4a  cmp     ax, 21h ; '!'
0x18000dc4e  ja      loc_18000E20C
0x18000dc54  lea     eax, [r13-1]
0x18000dc58  cmp     eax, 0Bh
0x18000dc5b  ja      loc_18000E5D9
0x18000dc61  mov     r8d, [rsp+158h+arg_30]
0x18000dc69  cmp     r13d, 6
0x18000dc6d  jz      loc_18000E2D3
0x18000dc73  mov     ecx, [rsp+158h+arg_28]
0x18000dc7a  lea     eax, [rcx-1]
0x18000dc7d  cmp     eax, 11h
0x18000dc80  ja      loc_18000E5B3
0x18000dc86  test    rdi, rdi
0x18000dc89  jz      loc_18000E306
0x18000dc8f  cmp     [rsp+158h+var_E0], r15
0x18000dc94  jz      loc_18000E32F
0x18000dc9a  test    r8d, 0FFFFFFFEh
0x18000dca1  jnz     loc_18000E361
0x18000dca7  cmp     r13d, 0Bh
0x18000dcab  ja      loc_18000E38A
0x18000dcb1  mov     eax, 864h
0x18000dcb6  bt      eax, r13d
0x18000dcba  jnb     loc_18000E38A
0x18000dcc0  cmp     ecx, 1
0x18000dcc3  jz      loc_18000E161
0x18000dcc9  cmp     ecx, 0Bh
0x18000dccc  jz      loc_18000E161
0x18000dcd2  mov     eax, [rsp+158h+arg_0]
0x18000dcd9  test    r12, r12
0x18000dcdc  jnz     short loc_18000DD2A
0x18000dcde  neg     eax
0x18000dce0  sbb     r9d, r9d
0x18000dce3  add     r9d, 2
0x18000dce7  mov     [rsp+158h+var_130], rbx
0x18000dcec  mov     dword ptr [rsp+158h+var_138], r15d
0x18000dcf1  mov     r8d, r13d
0x18000dcf4  mov     rdx, [rsp+158h+var_A8]
0x18000dcfc  movzx   ecx, r14w
0x18000dd00  call    Int_FWCreateConnectionHandle
0x18000dd05  mov     edi, eax
0x18000dd07  test    eax, eax
0x18000dd09  jnz     loc_18000E3BB
0x18000dd0f  mov     rsi, cs:WPP_GLOBAL_Control
0x18000dd16  mov     edx, 200h
0x18000dd1b  test    r12, r12
0x18000dd1e  jnz     short loc_18000DD2A
0x18000dd20  cmp     r14w, dx
0x18000dd24  ja      loc_18000E22B
0x18000dd2a  mov     edi, 20Ah
0x18000dd2f  mov     edx, [rsp+158h+arg_28]
0x18000dd36  cmp     edx, 0Ch
0x18000dd39  jge     loc_18000E1E1
0x18000dd3f  mov     eax, 214h
0x18000dd44  cmp     edx, 0Eh
0x18000dd47  jge     loc_18000E1B6
0x18000dd4d  mov     eax, [rbx+4]
0x18000dd50  cmp     eax, 1
0x18000dd53  ja      loc_18000E428
0x18000dd59  cmp     [rbx+20h], r15
0x18000dd5d  jz      loc_18000E5A2
0x18000dd63  mov     rsi, [rsp+158h+var_D0]
0x18000dd6b  mov     r9d, edx
0x18000dd6e  mov     r8d, r13d
0x18000dd71  movzx   edx, r14w
0x18000dd75  cmp     [rsp+158h+arg_0], 0
0x18000dd7d  jz      loc_18000DE74
0x18000dd83  mov     [rsp+158h+var_E8], r15d
0x18000dd88  mov     [rsp+158h+var_AC], r15d
0x18000dd90  mov     dword ptr [rsp+158h+var_A8], r15d
0x18000dd98  mov     eax, [rbx+4]
0x18000dd9b  lea     r10, RPC_FWGetGlobalConfig
0x18000dda2  lea     rcx, RRPC_FWGetGlobalConfig
0x18000dda9  test    eax, eax
0x18000ddab  cmovnz  r10, rcx
0x18000ddaf  lea     r11, RPC_FWGetGlobalConfig2_10
0x18000ddb6  lea     rcx, RRPC_FWGetGlobalConfig2_10
0x18000ddbd  cmovnz  r11, rcx
0x18000ddc1  mov     eax, [rsi]
0x18000ddc3  cmp     r14w, di
0x18000ddc7  jnb     loc_18000DF09
0x18000ddcd  lea     rcx, [rsp+158h+var_A8]
0x18000ddd5  mov     [rsp+158h+var_118], rcx
0x18000ddda  lea     rcx, [rsp+158h+var_AC]
0x18000dde2  mov     [rsp+158h+var_120], rcx
0x18000dde7  mov     dword ptr [rsp+158h+var_128], eax
0x18000ddeb  mov     rax, [rsp+158h+var_E0]
0x18000ddf0  mov     [rsp+158h+var_130], rax
0x18000ddf5  mov     eax, [rsp+158h+arg_30]
0x18000ddfc  mov     dword ptr [rsp+158h+var_138], eax
0x18000de00  mov     rcx, [rbx+20h]
0x18000de04  mov     rax, r10
0x18000de07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0c  mov     [rsp+158h+var_E8], eax
0x18000de10  mov     edi, eax
0x18000de12  test    eax, eax
0x18000de14  jnz     loc_18000DF5A
0x18000de1a  mov     eax, [rsp+158h+var_AC]
0x18000de21  mov     [rsi], eax
0x18000de23  lea     r13, WPP_GLOBAL_Control
0x18000de2a  mov     rsi, cs:WPP_GLOBAL_Control
0x18000de31  mov     [rsp+158h+var_D8], edi
0x18000de38  test    edi, edi
0x18000de3a  jz      loc_18000DFD9
0x18000de40  cmp     rsi, r13
0x18000de43  jz      short loc_18000DE6A
0x18000de45  test    byte ptr [rsi+1Ch], 1
0x18000de49  jz      short loc_18000DE6A
0x18000de4b  mov     edx, 10Ch
0x18000de50  mov     r9d, edi
0x18000de53  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000de5a  mov     rcx, [rsi+10h]
0x18000de5e  call    WPP_SF_d
0x18000de63  mov     rsi, cs:WPP_GLOBAL_Control
0x18000de6a  mov     rcx, [rsp+158h+var_F8]
0x18000de6f  jmp     loc_18000E081
0x18000de74  lea     rax, RRPC_FWSetGlobalConfig
0x18000de7b  lea     rcx, RPC_FWSetGlobalConfig
0x18000de82  cmp     [rsp+158h+var_94], 0
0x18000de8a  cmovz   rax, rcx
0x18000de8e  mov     ecx, [rsi]
0x18000de90  mov     dword ptr [rsp+158h+var_130], ecx
0x18000de94  mov     rcx, [rsp+158h+var_E0]
0x18000de99  mov     [rsp+158h+var_138], rcx
0x18000de9e  mov     rcx, [rbx+20h]
0x18000dea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dea7  mov     edi, eax
0x18000dea9  mov     [rsp+158h+var_D8], eax
0x18000deb0  test    eax, eax
0x18000deb2  jz      short loc_18000DEF6
0x18000deb4  mov     rsi, cs:WPP_GLOBAL_Control
0x18000debb  lea     r13, WPP_GLOBAL_Control
0x18000dec2  cmp     rsi, r13
0x18000dec5  jz      short loc_18000DEEC
0x18000dec7  test    byte ptr [rsi+1Ch], 1
0x18000decb  jz      short loc_18000DEEC
0x18000decd  mov     edx, 10Dh
0x18000ded2  mov     r9d, eax
0x18000ded5  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000dedc  mov     rcx, [rsi+10h]
0x18000dee0  call    WPP_SF_d
0x18000dee5  mov     rsi, cs:WPP_GLOBAL_Control
0x18000deec  mov     rcx, [rsp+158h+var_F8]
0x18000def1  jmp     loc_18000E081
0x18000def6  mov     rsi, cs:WPP_GLOBAL_Control
0x18000defd  lea     r13, WPP_GLOBAL_Control
0x18000df04  jmp     loc_18000DFD9
0x18000df09  lea     rcx, [rsp+158h+var_9C]
0x18000df11  mov     [rsp+158h+var_110], rcx
0x18000df16  lea     rcx, [rsp+158h+var_A8]
0x18000df1e  mov     [rsp+158h+var_118], rcx
0x18000df23  lea     rcx, [rsp+158h+var_AC]
0x18000df2b  mov     [rsp+158h+var_120], rcx
0x18000df30  mov     dword ptr [rsp+158h+var_128], eax
0x18000df34  mov     rax, [rsp+158h+var_E0]
0x18000df39  mov     [rsp+158h+var_130], rax
0x18000df3e  mov     eax, [rsp+158h+arg_30]
0x18000df45  mov     dword ptr [rsp+158h+var_138], eax
0x18000df49  mov     rcx, [rbx+20h]
0x18000df4d  mov     rax, r11
0x18000df50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df55  jmp     loc_18000DE0C
0x18000df5a  cmp     edi, 0EAh
0x18000df60  jnz     short loc_18000DF97
0x18000df62  mov     eax, dword ptr [rsp+158h+var_A8]
0x18000df69  mov     [rsi], eax
0x18000df6b  mov     [rsp+158h+var_E8], edi
0x18000df6f  mov     rsi, cs:WPP_GLOBAL_Control
0x18000df76  lea     r13, WPP_GLOBAL_Control
0x18000df7d  cmp     rsi, r13
0x18000df80  jz      loc_18000DE31
0x18000df86  test    byte ptr [rsi+1Ch], 1
0x18000df8a  jz      loc_18000DE31
0x18000df90  mov     edx, 114h
0x18000df95  jmp     short loc_18000DFC1
0x18000df97  mov     [rsp+158h+var_E8], edi
0x18000df9b  mov     rsi, cs:WPP_GLOBAL_Control
0x18000dfa2  lea     r13, WPP_GLOBAL_Control
0x18000dfa9  cmp     rsi, r13
0x18000dfac  jz      loc_18000DE31
0x18000dfb2  test    byte ptr [rsi+1Ch], 1
0x18000dfb6  jz      loc_18000DE31
0x18000dfbc  mov     edx, 115h
0x18000dfc1  mov     r9d, edi
0x18000dfc4  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000dfcb  mov     rcx, [rsi+10h]
0x18000dfcf  call    WPP_SF_d
0x18000dfd4  jmp     loc_18000DE2A
0x18000dfd9  mov     rcx, [rsp+158h+var_F8]
0x18000dfde  jmp     loc_18000E081
0x18000dfe3  mov     edi, eax
0x18000dfe5  mov     [rsp+158h+var_D8], eax
0x18000dfec  test    eax, eax
0x18000dfee  jz      short loc_18000E052
0x18000dff0  lea     rax, WPP_GLOBAL_Control
0x18000dff7  mov     rsi, cs:WPP_GLOBAL_Control
0x18000dffe  cmp     rsi, rax
0x18000e001  jz      short loc_18000E028
0x18000e003  test    byte ptr [rsi+1Ch], 1
0x18000e007  jz      short loc_18000E028
0x18000e009  mov     edx, 10Eh
0x18000e00e  mov     r9d, edi
0x18000e011  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000e018  mov     rcx, [rsi+10h]
0x18000e01c  call    WPP_SF_d
0x18000e021  mov     rsi, cs:WPP_GLOBAL_Control
0x18000e028  lea     r13, WPP_GLOBAL_Control
0x18000e02f  xor     r15d, r15d
0x18000e032  mov     rbx, [rsp+158h+var_C8]
0x18000e03a  movzx   r14d, [rsp+158h+var_F0]
0x18000e040  mov     r12, [rsp+158h+var_C0]
0x18000e048  mov     rcx, [rsp+158h+var_B8]
0x18000e050  jmp     short loc_18000E081
0x18000e052  lea     r13, WPP_GLOBAL_Control
0x18000e059  xor     r15d, r15d
0x18000e05c  mov     rbx, [rsp+158h+var_C8]
0x18000e064  movzx   r14d, [rsp+158h+var_F0]
0x18000e06a  mov     r12, [rsp+158h+var_C0]
0x18000e072  mov     rsi, cs:WPP_GLOBAL_Control
0x18000e079  mov     rcx, [rsp+158h+var_B8]
0x18000e081  test    rcx, rcx
0x18000e084  jnz     loc_18000E62D
0x18000e08a  test    r12, r12
0x18000e08d  jnz     short loc_18000E0E1
0x18000e08f  cmp     rsi, r13
0x18000e092  jz      short loc_18000E09E
0x18000e094  test    byte ptr [rsi+1Ch], 8
0x18000e098  jnz     loc_18000E642
0x18000e09e  test    rbx, rbx
0x18000e0a1  jz      short loc_18000E0E1
0x18000e0a3  mov     eax, [rbx+4]
0x18000e0a6  cmp     eax, 1
0x18000e0a9  ja      loc_18000E663
0x18000e0af  cmp     qword ptr [rbx+20h], 0
0x18000e0b4  jz      short loc_18000E0CC
0x18000e0b6  lea     rcx, [rbx+20h]; Binding
0x18000e0ba  call    cs:__imp_RpcBindingFree
0x18000e0c0  test    eax, eax
0x18000e0c2  jnz     loc_18000E67A
0x18000e0c8  mov     [rbx+20h], r15
0x18000e0cc  mov     rcx, [rbx+8]
0x18000e0d0  call    cs:__imp_FwBaseFree
0x18000e0d6  mov     [rbx+8], r15
0x18000e0da  mov     rsi, cs:WPP_GLOBAL_Control
0x18000e0e1  mov     eax, 221h
0x18000e0e6  cmp     r14w, ax
0x18000e0ea  jnb     short loc_18000E0FC
0x18000e0ec  cmp     edi, 6F7h
0x18000e0f2  jz      loc_18000E686
0x18000e0f8  cmp     r14w, ax
0x18000e0fc  jz      loc_18000E199
0x18000e102  cmp     rsi, r13
0x18000e105  jz      short loc_18000E111
0x18000e107  test    byte ptr [rsi+1Ch], 8
0x18000e10b  jnz     loc_18000E69E
0x18000e111  mov     eax, edi
0x18000e113  mov     rcx, [rsp+158h+var_48]
  ... truncated ...
```
