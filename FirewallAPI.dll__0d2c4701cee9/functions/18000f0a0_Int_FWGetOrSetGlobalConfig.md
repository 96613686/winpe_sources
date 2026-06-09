# Int_FWGetOrSetGlobalConfig

- ea: `0x18000f0a0`
- end: `0x18000fc1d`
- name: `Int_FWGetOrSetGlobalConfig`
- size: `2941`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ed70`
- `0x18000ef00`
- `0x180010990`
- `0x180053730`
- `0x180053880`

## callees

- `0x180005e0c`
- `0x18000e750`
- `0x18000ed70`
- `0x18000f0a0`
- `0x180026798`
- `0x180026c9c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x180054d58`
- `0x180054db8`
- `0x180055378`
- `0x180062010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fafe`
- `RPCRT4!RpcExceptionFilter` at `0x18005fafe`
- `RPCRT4!RpcBindingFree` at `0x18000f5fa`
- `RPCRT4!RpcBindingFree` at `0x18000f5fa`
- `fwbase!FwBaseFree` at `0x18000f616`
- `fwbase!FwBaseFree` at `0x18000f616`
- `fwbase!FwHResultToWindowsError` at `0x18000fa13`
- `fwbase!FwHResultToWindowsError` at `0x18000fa75`
- `fwbase!FwHResultToWindowsError` at `0x18000fa13`
- `fwbase!FwHResultToWindowsError` at `0x18000fa75`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18000fa67`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x18000fa67`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18000fa05`
- `FWPolicyIOMgr!FwGetGlobalConfig` at `0x18000fa05`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
    v35 = 254;
LABEL_162:
    v38 = v19;
    goto LABEL_163;
  }
  if ( a4 - 1 > 0xB )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 255;
    goto LABEL_162;
  }
  v13 = a7;
  if ( a4 == 6 && (a7 & 1) != 0 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 256;
    goto LABEL_162;
  }
  if ( (unsigned int)(a6 - 1) > 0x11 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 257;
    goto LABEL_162;
  }
  if ( !a9 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 258;
    goto LABEL_162;
  }
  if ( !a8 && *a9 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 259;
    goto LABEL_162;
  }
  if ( (a7 & 0xFFFFFFFE) != 0 )
  {
    v19 = 87;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 260;
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
    v35 = 261;
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
    v35 = 262;
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
      v35 = 263;
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
        v35 = 264;
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
    v35 = 265;
    goto LABEL_162;
  }
  if ( a6 >= 14 && a2 < 0x214u )
  {
    v19 = 50;
    if ( v12 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 1) == 0 )
      goto LABEL_95;
    v35 = 266;
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
      v35 = 270;
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
        v35 = 271;
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
        v35 = 272;
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
    v35 = 273;
    v38 = v45;
LABEL_163:
    WPP_SF_d(*((_QWORD *)v12 + 2), v35, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v38);
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
        v29 = 275;
LABEL_55:
        WPP_SF_d(*((_QWORD *)v12 + 2), v29, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v25);
        goto LABEL_33;
      }
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v29 = 276;
        goto LABEL_55;
      }
    }
LABEL_34:
    if ( v19 )
    {
      if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)v12 + 2), 267, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v19);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v28);
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
      WPP_SF_(*((_QWORD *)v12 + 2), 377, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
    WPP_SF_(*((_QWORD *)v12 + 2), 274, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  return v19;
}

```

## disassembly

```asm
0x18000f0a0  mov     [rsp+arg_0], ecx
0x18000f0a4  push    rbx
0x18000f0a5  push    rsi
0x18000f0a6  push    rdi
0x18000f0a7  push    r12
0x18000f0a9  push    r13
0x18000f0ab  push    r14
0x18000f0ad  push    r15
0x18000f0af  sub     rsp, 120h
0x18000f0b6  mov     rax, cs:__security_cookie
0x18000f0bd  xor     rax, rsp
0x18000f0c0  mov     [rsp+158h+var_48], rax
0x18000f0c8  mov     r13d, r9d
0x18000f0cb  mov     [rsp+158h+var_A8], r8
0x18000f0d3  movzx   r14d, dx
0x18000f0d7  mov     [rsp+158h+var_F0], dx
0x18000f0dc  mov     r12, [rsp+158h+arg_20]
0x18000f0e4  mov     [rsp+158h+var_C0], r12
0x18000f0ec  mov     rax, [rsp+158h+arg_38]
0x18000f0f4  mov     [rsp+158h+var_E0], rax
0x18000f0f9  mov     rdi, [rsp+158h+arg_40]
0x18000f101  mov     [rsp+158h+var_D0], rdi
0x18000f109  mov     rax, [rsp+158h+arg_48]
0x18000f111  mov     [rsp+158h+var_F8], rax
0x18000f116  mov     [rsp+158h+var_B8], rax
0x18000f11e  lea     rax, WPP_GLOBAL_Control
0x18000f125  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f12c  cmp     rsi, rax
0x18000f12f  jnz     loc_18000F683
0x18000f135  xor     edx, edx; Val
0x18000f137  mov     r8d, 50h ; 'P'; Size
0x18000f13d  lea     rcx, [rsp+158h+var_98]; void *
0x18000f145  call    memset_0
0x18000f14a  xor     r15d, r15d
0x18000f14d  mov     [rsp+158h+var_A0], r15d
0x18000f155  mov     [rsp+158h+var_B0], r15d
0x18000f15d  mov     [rsp+158h+var_9C], r15d
0x18000f165  test    r12, r12
0x18000f168  jnz     loc_18000F807
0x18000f16e  lea     rbx, [rsp+158h+var_98]
0x18000f176  mov     [rsp+158h+var_C8], rbx
0x18000f17e  mov     edx, 200h
0x18000f183  movzx   eax, r14w
0x18000f187  sub     ax, dx
0x18000f18a  cmp     ax, 21h ; '!'
0x18000f18e  ja      loc_18000F759
0x18000f194  lea     eax, [r13-1]
0x18000f198  cmp     eax, 0Bh
0x18000f19b  ja      loc_18000FB3E
0x18000f1a1  mov     r8d, [rsp+158h+arg_30]
0x18000f1a9  cmp     r13d, 6
0x18000f1ad  jz      loc_18000F820
0x18000f1b3  mov     ecx, [rsp+158h+arg_28]
0x18000f1ba  lea     eax, [rcx-1]
0x18000f1bd  cmp     eax, 11h
0x18000f1c0  ja      loc_18000FB18
0x18000f1c6  test    rdi, rdi
0x18000f1c9  jz      loc_18000F853
0x18000f1cf  cmp     [rsp+158h+var_E0], r15
0x18000f1d4  jz      loc_18000F87C
0x18000f1da  test    r8d, 0FFFFFFFEh
0x18000f1e1  jnz     loc_18000F8AE
0x18000f1e7  cmp     r13d, 0Bh
0x18000f1eb  ja      loc_18000F8D7
0x18000f1f1  mov     eax, 864h
0x18000f1f6  bt      eax, r13d
0x18000f1fa  jnb     loc_18000F8D7
0x18000f200  cmp     ecx, 1
0x18000f203  jz      loc_18000F6AE
0x18000f209  cmp     ecx, 0Bh
0x18000f20c  jz      loc_18000F6AE
0x18000f212  mov     eax, [rsp+158h+arg_0]
0x18000f219  test    r12, r12
0x18000f21c  jnz     short loc_18000F26A
0x18000f21e  neg     eax
0x18000f220  sbb     r9d, r9d
0x18000f223  add     r9d, 2
0x18000f227  mov     [rsp+158h+var_130], rbx
0x18000f22c  mov     dword ptr [rsp+158h+var_138], r15d
0x18000f231  mov     r8d, r13d
0x18000f234  mov     rdx, [rsp+158h+var_A8]
0x18000f23c  movzx   ecx, r14w
0x18000f240  call    Int_FWCreateConnectionHandle
0x18000f245  mov     edi, eax
0x18000f247  test    eax, eax
0x18000f249  jnz     loc_18000F908
0x18000f24f  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f256  mov     edx, 200h
0x18000f25b  test    r12, r12
0x18000f25e  jnz     short loc_18000F26A
0x18000f260  cmp     r14w, dx
0x18000f264  ja      loc_18000F778
0x18000f26a  mov     edi, 20Ah
0x18000f26f  mov     edx, [rsp+158h+arg_28]
0x18000f276  cmp     edx, 0Ch
0x18000f279  jge     loc_18000F72E
0x18000f27f  mov     eax, 214h
0x18000f284  cmp     edx, 0Eh
0x18000f287  jge     loc_18000F703
0x18000f28d  mov     eax, [rbx+4]
0x18000f290  cmp     eax, 1
0x18000f293  ja      loc_18000F975
0x18000f299  cmp     [rbx+20h], r15
0x18000f29d  jz      loc_18000FB07
0x18000f2a3  mov     rsi, [rsp+158h+var_D0]
0x18000f2ab  mov     r9d, edx
0x18000f2ae  mov     r8d, r13d
0x18000f2b1  movzx   edx, r14w
0x18000f2b5  cmp     [rsp+158h+arg_0], 0
0x18000f2bd  jz      loc_18000F3B4
0x18000f2c3  mov     [rsp+158h+var_E8], r15d
0x18000f2c8  mov     [rsp+158h+var_AC], r15d
0x18000f2d0  mov     dword ptr [rsp+158h+var_A8], r15d
0x18000f2d8  mov     eax, [rbx+4]
0x18000f2db  lea     r10, RPC_FWGetGlobalConfig
0x18000f2e2  lea     rcx, RRPC_FWGetGlobalConfig
0x18000f2e9  test    eax, eax
0x18000f2eb  cmovnz  r10, rcx
0x18000f2ef  lea     r11, RPC_FWGetGlobalConfig2_10
0x18000f2f6  lea     rcx, RRPC_FWGetGlobalConfig2_10
0x18000f2fd  cmovnz  r11, rcx
0x18000f301  mov     eax, [rsi]
0x18000f303  cmp     r14w, di
0x18000f307  jnb     loc_18000F449
0x18000f30d  lea     rcx, [rsp+158h+var_A8]
0x18000f315  mov     [rsp+158h+var_118], rcx
0x18000f31a  lea     rcx, [rsp+158h+var_AC]
0x18000f322  mov     [rsp+158h+var_120], rcx
0x18000f327  mov     dword ptr [rsp+158h+var_128], eax
0x18000f32b  mov     rax, [rsp+158h+var_E0]
0x18000f330  mov     [rsp+158h+var_130], rax
0x18000f335  mov     eax, [rsp+158h+arg_30]
0x18000f33c  mov     dword ptr [rsp+158h+var_138], eax
0x18000f340  mov     rcx, [rbx+20h]
0x18000f344  mov     rax, r10
0x18000f347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f34c  mov     [rsp+158h+var_E8], eax
0x18000f350  mov     edi, eax
0x18000f352  test    eax, eax
0x18000f354  jnz     loc_18000F49A
0x18000f35a  mov     eax, [rsp+158h+var_AC]
0x18000f361  mov     [rsi], eax
0x18000f363  lea     r13, WPP_GLOBAL_Control
0x18000f36a  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f371  mov     [rsp+158h+var_D8], edi
0x18000f378  test    edi, edi
0x18000f37a  jz      loc_18000F519
0x18000f380  cmp     rsi, r13
0x18000f383  jz      short loc_18000F3AA
0x18000f385  test    byte ptr [rsi+1Ch], 1
0x18000f389  jz      short loc_18000F3AA
0x18000f38b  mov     edx, 10Bh
0x18000f390  mov     r9d, edi
0x18000f393  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f39a  mov     rcx, [rsi+10h]
0x18000f39e  call    WPP_SF_d
0x18000f3a3  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f3aa  mov     rcx, [rsp+158h+var_F8]
0x18000f3af  jmp     loc_18000F5C1
0x18000f3b4  lea     rax, RRPC_FWSetGlobalConfig
0x18000f3bb  lea     rcx, RPC_FWSetGlobalConfig
0x18000f3c2  cmp     [rsp+158h+var_94], 0
0x18000f3ca  cmovz   rax, rcx
0x18000f3ce  mov     ecx, [rsi]
0x18000f3d0  mov     dword ptr [rsp+158h+var_130], ecx
0x18000f3d4  mov     rcx, [rsp+158h+var_E0]
0x18000f3d9  mov     [rsp+158h+var_138], rcx
0x18000f3de  mov     rcx, [rbx+20h]
0x18000f3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3e7  mov     edi, eax
0x18000f3e9  mov     [rsp+158h+var_D8], eax
0x18000f3f0  test    eax, eax
0x18000f3f2  jz      short loc_18000F436
0x18000f3f4  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f3fb  lea     r13, WPP_GLOBAL_Control
0x18000f402  cmp     rsi, r13
0x18000f405  jz      short loc_18000F42C
0x18000f407  test    byte ptr [rsi+1Ch], 1
0x18000f40b  jz      short loc_18000F42C
0x18000f40d  mov     edx, 10Ch
0x18000f412  mov     r9d, eax
0x18000f415  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f41c  mov     rcx, [rsi+10h]
0x18000f420  call    WPP_SF_d
0x18000f425  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f42c  mov     rcx, [rsp+158h+var_F8]
0x18000f431  jmp     loc_18000F5C1
0x18000f436  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f43d  lea     r13, WPP_GLOBAL_Control
0x18000f444  jmp     loc_18000F519
0x18000f449  lea     rcx, [rsp+158h+var_9C]
0x18000f451  mov     [rsp+158h+var_110], rcx
0x18000f456  lea     rcx, [rsp+158h+var_A8]
0x18000f45e  mov     [rsp+158h+var_118], rcx
0x18000f463  lea     rcx, [rsp+158h+var_AC]
0x18000f46b  mov     [rsp+158h+var_120], rcx
0x18000f470  mov     dword ptr [rsp+158h+var_128], eax
0x18000f474  mov     rax, [rsp+158h+var_E0]
0x18000f479  mov     [rsp+158h+var_130], rax
0x18000f47e  mov     eax, [rsp+158h+arg_30]
0x18000f485  mov     dword ptr [rsp+158h+var_138], eax
0x18000f489  mov     rcx, [rbx+20h]
0x18000f48d  mov     rax, r11
0x18000f490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f495  jmp     loc_18000F34C
0x18000f49a  cmp     edi, 0EAh
0x18000f4a0  jnz     short loc_18000F4D7
0x18000f4a2  mov     eax, dword ptr [rsp+158h+var_A8]
0x18000f4a9  mov     [rsi], eax
0x18000f4ab  mov     [rsp+158h+var_E8], edi
0x18000f4af  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f4b6  lea     r13, WPP_GLOBAL_Control
0x18000f4bd  cmp     rsi, r13
0x18000f4c0  jz      loc_18000F371
0x18000f4c6  test    byte ptr [rsi+1Ch], 1
0x18000f4ca  jz      loc_18000F371
0x18000f4d0  mov     edx, 113h
0x18000f4d5  jmp     short loc_18000F501
0x18000f4d7  mov     [rsp+158h+var_E8], edi
0x18000f4db  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f4e2  lea     r13, WPP_GLOBAL_Control
0x18000f4e9  cmp     rsi, r13
0x18000f4ec  jz      loc_18000F371
0x18000f4f2  test    byte ptr [rsi+1Ch], 1
0x18000f4f6  jz      loc_18000F371
0x18000f4fc  mov     edx, 114h
0x18000f501  mov     r9d, edi
0x18000f504  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f50b  mov     rcx, [rsi+10h]
0x18000f50f  call    WPP_SF_d
0x18000f514  jmp     loc_18000F36A
0x18000f519  mov     rcx, [rsp+158h+var_F8]
0x18000f51e  jmp     loc_18000F5C1
0x18000f523  mov     edi, eax
0x18000f525  mov     [rsp+158h+var_D8], eax
0x18000f52c  test    eax, eax
0x18000f52e  jz      short loc_18000F592
0x18000f530  lea     rax, WPP_GLOBAL_Control
0x18000f537  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f53e  cmp     rsi, rax
0x18000f541  jz      short loc_18000F568
0x18000f543  test    byte ptr [rsi+1Ch], 1
0x18000f547  jz      short loc_18000F568
0x18000f549  mov     edx, 10Dh
0x18000f54e  mov     r9d, edi
0x18000f551  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000f558  mov     rcx, [rsi+10h]
0x18000f55c  call    WPP_SF_d
0x18000f561  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f568  lea     r13, WPP_GLOBAL_Control
0x18000f56f  xor     r15d, r15d
0x18000f572  mov     rbx, [rsp+158h+var_C8]
0x18000f57a  movzx   r14d, [rsp+158h+var_F0]
0x18000f580  mov     r12, [rsp+158h+var_C0]
0x18000f588  mov     rcx, [rsp+158h+var_B8]
0x18000f590  jmp     short loc_18000F5C1
0x18000f592  lea     r13, WPP_GLOBAL_Control
0x18000f599  xor     r15d, r15d
0x18000f59c  mov     rbx, [rsp+158h+var_C8]
0x18000f5a4  movzx   r14d, [rsp+158h+var_F0]
0x18000f5aa  mov     r12, [rsp+158h+var_C0]
0x18000f5b2  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f5b9  mov     rcx, [rsp+158h+var_B8]
0x18000f5c1  test    rcx, rcx
0x18000f5c4  jnz     loc_18000FB92
0x18000f5ca  test    r12, r12
0x18000f5cd  jnz     short loc_18000F62D
0x18000f5cf  cmp     rsi, r13
0x18000f5d2  jz      short loc_18000F5DE
0x18000f5d4  test    byte ptr [rsi+1Ch], 8
0x18000f5d8  jnz     loc_18000FBA7
0x18000f5de  test    rbx, rbx
0x18000f5e1  jz      short loc_18000F62D
0x18000f5e3  mov     eax, [rbx+4]
0x18000f5e6  cmp     eax, 1
0x18000f5e9  ja      loc_18000FBC8
0x18000f5ef  cmp     qword ptr [rbx+20h], 0
0x18000f5f4  jz      short loc_18000F612
0x18000f5f6  lea     rcx, [rbx+20h]; Binding
0x18000f5fa  call    cs:__imp_RpcBindingFree
0x18000f601  nop     dword ptr [rax+rax+00h]
0x18000f606  test    eax, eax
0x18000f608  jnz     loc_18000FBDF
0x18000f60e  mov     [rbx+20h], r15
0x18000f612  mov     rcx, [rbx+8]
0x18000f616  call    cs:__imp_FwBaseFree
0x18000f61d  nop     dword ptr [rax+rax+00h]
0x18000f622  mov     [rbx+8], r15
0x18000f626  mov     rsi, cs:WPP_GLOBAL_Control
0x18000f62d  mov     eax, 221h
0x18000f632  cmp     r14w, ax
0x18000f636  jnb     short loc_18000F648
0x18000f638  cmp     edi, 6F7h
0x18000f63e  jz      loc_18000FBEB
0x18000f644  cmp     r14w, ax
0x18000f648  jz      loc_18000F6E6
0x18000f64e  cmp     rsi, r13
0x18000f651  jz      short loc_18000F65D
0x18000f653  test    byte ptr [rsi+1Ch], 8
0x18000f657  jnz     loc_18000FC03
  ... truncated ...
```
