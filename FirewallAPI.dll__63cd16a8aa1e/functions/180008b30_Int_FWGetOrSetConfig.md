# Int_FWGetOrSetConfig

- ea: `0x180008b30`
- end: `0x18000907a`
- name: `Int_FWGetOrSetConfig`
- size: `1354`
- prototype: ``
- caller_count: `14`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003194`
- `0x180006394`
- `0x180006b40`
- `0x180006ea0`
- `0x180007130`
- `0x180007470`
- `0x180007880`
- `0x1800088d0`
- `0x180008a10`
- `0x18000a980`
- `0x18000b390`
- `0x180018ef0`
- `0x18001a4f0`
- `0x180027190`

## callees

- `0x180005954`
- `0x180008b30`
- `0x180009160`
- `0x18002514c`
- `0x18003104c`
- `0x1800516bc`
- `0x180051710`
- `0x180051cc0`
- `0x18005e010`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b7be`
- `RPCRT4!RpcExceptionFilter` at `0x18005b7be`
- `fwbase!FwHResultToWindowsError` at `0x180008f7f`
- `fwbase!FwHResultToWindowsError` at `0x180008fc0`
- `fwbase!FwHResultToWindowsError` at `0x180008f7f`
- `fwbase!FwHResultToWindowsError` at `0x180008fc0`
- `FWPolicyIOMgr!FwSetConfig` at `0x180008fb8`
- `FWPolicyIOMgr!FwSetConfig` at `0x180008fb8`
- `FWPolicyIOMgr!FwGetConfig` at `0x180008f77`
- `FWPolicyIOMgr!FwGetConfig` at `0x180008f77`

## pseudocode

```c
__int64 __fastcall Int_FWGetOrSetConfig(
        unsigned int a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        int *a7)
{
  __int64 v9; // rbx
  __int64 v10; // r8
  FwPolicy2 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r10
  __int64 v14; // r11
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 (__fastcall *v17)(int, int, int, int, __int64, int); // rax
  unsigned int v18; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int Config; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax

  v9 = a2;
  v10 = a1;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 278, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    v11 = WPP_GLOBAL_Control;
    v10 = a1;
  }
  v12 = 0;
  if ( v9 )
  {
    if ( a3 - 1 > 0x11 )
    {
      v16 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v20 = 280;
      goto LABEL_45;
    }
    if ( (a5 & 0xFFFFFFFE) != 0 )
    {
      v16 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v20 = 281;
      goto LABEL_45;
    }
    if ( !a7 )
    {
      v16 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v20 = 282;
      goto LABEL_45;
    }
    if ( !a6 && *a7 )
    {
      v16 = 87;
      if ( v11 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
        goto LABEL_41;
      v20 = 283;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v11 + 2), v20, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 87);
      v11 = WPP_GLOBAL_Control;
LABEL_41:
      v12 = 0;
      goto LABEL_27;
    }
    v12 = v9;
    a2 = 532;
    if ( *(_WORD *)(v9 + 2) >= 0x214u || (int)a3 < 18 )
    {
      a2 = *(unsigned int *)(v9 + 4);
      if ( (unsigned int)a2 > 1 )
      {
        if ( (_DWORD)a2 != 2 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v11, a2, v10);
        v23 = Int_FWOpenGPOPolicyStore(v9);
        v16 = v23;
        if ( v23 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_59;
          v21 = 289;
          v22 = v23;
          goto LABEL_57;
        }
        if ( !*(_QWORD *)(v9 + 56) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v24, a2, v10);
        if ( (a5 & 1) == 0 )
        {
          v25 = *(_QWORD *)(v9 + 56);
          if ( a1 )
          {
            Config = FwGetConfig(v25, a3, a4, a6, a7);
            v27 = FwHResultToWindowsError(Config);
            v16 = v27;
            if ( v27 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_59;
              }
              v21 = 291;
              v22 = v27;
              goto LABEL_57;
            }
          }
          else
          {
            v28 = FwSetConfig(v25, a3, a4, a6, *a7);
            v29 = FwHResultToWindowsError(v28);
            v16 = v29;
            if ( v29 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_59;
              }
              v21 = 292;
              v22 = v29;
              goto LABEL_57;
            }
          }
          v30 = Int_FWCloseGPOPolicyStore(v9, a1 == 0);
          v16 = v30;
          if ( !v30 )
            goto LABEL_58;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_59;
          v21 = 293;
          v22 = v30;
LABEL_57:
          WPP_SF_d(*((_QWORD *)v11 + 2), v21, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v22);
LABEL_58:
          v11 = WPP_GLOBAL_Control;
LABEL_59:
          v12 = v9;
          goto LABEL_27;
        }
        v16 = 87;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_59;
        v21 = 290;
LABEL_56:
        v22 = v16;
        goto LABEL_57;
      }
      v13 = *(_QWORD *)(v9 + 32);
      if ( v13 )
      {
        v14 = *(_QWORD *)(v9 + 40);
        if ( v14 )
        {
          if ( (_DWORD)v10 )
          {
            v15 = Int_FWCallRpcGetConfig(v9, a3, a4, a5, a6, (__int64)a7);
            v16 = v15;
            if ( v15 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 286, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v15);
                v11 = WPP_GLOBAL_Control;
              }
              v12 = v9;
              goto LABEL_27;
            }
          }
          else
          {
            v17 = RPC_FWSetConfig;
            if ( (_DWORD)a2 )
              v17 = RRPC_FWSetConfig;
            v18 = v17(v13, v14, a3, a4, a6, *a7);
            v16 = v18;
            if ( v18 )
            {
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 287, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v18);
                v11 = WPP_GLOBAL_Control;
              }
              v12 = v9;
              goto LABEL_27;
            }
          }
          v11 = WPP_GLOBAL_Control;
          v12 = v9;
          goto LABEL_27;
        }
      }
      v16 = 87;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v21 = 285;
        goto LABEL_56;
      }
    }
    else
    {
      v16 = 50;
      if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
      {
        v21 = 284;
        goto LABEL_56;
      }
    }
  }
  else
  {
    v16 = 87;
    if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    {
      v20 = 279;
      goto LABEL_45;
    }
  }
LABEL_27:
  if ( v16 && v12 && *(_DWORD *)(v12 + 4) == 2 && *(_DWORD *)(v12 + 24) != 1 )
  {
    Int_FWCleanupGPOPolicyStore(v12, a2, v10);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v11 + 2), 294, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  return v16;
}

```

## disassembly

```asm
0x180008b30  mov     [rsp+arg_18], r9d
0x180008b35  mov     [rsp+arg_0], ecx
0x180008b39  push    rbx
0x180008b3a  push    rsi
0x180008b3b  push    rdi
0x180008b3c  push    r12
0x180008b3e  push    r13
0x180008b40  push    r14
0x180008b42  push    r15
0x180008b44  sub     rsp, 50h
0x180008b48  mov     edi, r9d
0x180008b4b  mov     r13d, r8d
0x180008b4e  mov     rbx, rdx
0x180008b51  mov     r8d, ecx
0x180008b54  lea     r12, WPP_GLOBAL_Control
0x180008b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b62  cmp     rcx, r12
0x180008b65  jz      short loc_180008B71
0x180008b67  test    byte ptr [rcx+1Ch], 8
0x180008b6b  jnz     loc_180008DF4
0x180008b71  xor     eax, eax
0x180008b73  mov     [rsp+88h+arg_8], rax
0x180008b7b  test    rbx, rbx
0x180008b7e  jz      loc_180008E1D
0x180008b84  lea     eax, [r13-1]
0x180008b88  cmp     eax, 11h
0x180008b8b  ja      loc_180008DD9
0x180008b91  mov     r15d, [rsp+88h+arg_20]
0x180008b99  test    r15d, 0FFFFFFFEh
0x180008ba0  jnz     loc_180008E5D
0x180008ba6  mov     rsi, [rsp+88h+arg_30]
0x180008bae  test    rsi, rsi
0x180008bb1  jz      loc_180008E78
0x180008bb7  mov     r14, [rsp+88h+arg_28]
0x180008bbf  test    r14, r14
0x180008bc2  jz      loc_180008D94
0x180008bc8  mov     rax, rbx
0x180008bcb  mov     [rsp+88h+arg_8], rbx
0x180008bd3  mov     [rsp+88h+arg_38], rbx
0x180008bdb  mov     edx, 214h
0x180008be0  cmp     [rbx+2], dx
0x180008be4  jb      loc_180008E97
0x180008bea  mov     edx, [rbx+4]
0x180008bed  cmp     edx, 1
0x180008bf0  ja      loc_180008EF1
0x180008bf6  mov     r10, [rbx+20h]
0x180008bfa  test    r10, r10
0x180008bfd  jz      loc_18000902F
0x180008c03  mov     r11, [rbx+28h]
0x180008c07  test    r11, r11
0x180008c0a  jz      loc_18000902F
0x180008c10  test    r8d, r8d
0x180008c13  jz      short loc_180008C7E
0x180008c15  mov     [rsp+88h+var_60], rsi
0x180008c1a  mov     [rsp+88h+var_68], r14
0x180008c1f  mov     r9d, r15d
0x180008c22  mov     r8d, edi
0x180008c25  mov     edx, r13d
0x180008c28  mov     rcx, rbx
0x180008c2b  call    Int_FWCallRpcGetConfig
0x180008c30  mov     edi, eax
0x180008c32  mov     [rsp+88h+var_48], eax
0x180008c36  test    eax, eax
0x180008c38  jz      loc_180008CF5
0x180008c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c45  cmp     rcx, r12
0x180008c48  jz      short loc_180008C50
0x180008c4a  test    byte ptr [rcx+1Ch], 1
0x180008c4e  jnz     short loc_180008C5D
0x180008c50  mov     rax, [rsp+88h+arg_8]
0x180008c58  jmp     loc_180008D6F
0x180008c5d  mov     edx, 11Eh
0x180008c62  mov     r9d, eax
0x180008c65  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008c6c  mov     rcx, [rcx+10h]
0x180008c70  call    WPP_SF_d
0x180008c75  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c7c  jmp     short loc_180008C50
0x180008c7e  lea     rax, RPC_FWSetConfig
0x180008c85  lea     rcx, RRPC_FWSetConfig
0x180008c8c  test    edx, edx
0x180008c8e  cmovnz  rax, rcx
0x180008c92  mov     r8d, [rsi]
0x180008c95  mov     dword ptr [rsp+88h+var_60], r8d
0x180008c9a  mov     [rsp+88h+var_68], r14
0x180008c9f  mov     r9d, edi
0x180008ca2  mov     r8d, r13d
0x180008ca5  mov     rdx, r11
0x180008ca8  mov     rcx, r10
0x180008cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb0  mov     edi, eax
0x180008cb2  mov     [rsp+88h+var_48], eax
0x180008cb6  test    eax, eax
0x180008cb8  jz      short loc_180008CF5
0x180008cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cc1  cmp     rcx, r12
0x180008cc4  jz      short loc_180008CEB
0x180008cc6  test    byte ptr [rcx+1Ch], 1
0x180008cca  jz      short loc_180008CEB
0x180008ccc  mov     edx, 11Fh
0x180008cd1  mov     r9d, eax
0x180008cd4  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008cdb  mov     rcx, [rcx+10h]
0x180008cdf  call    WPP_SF_d
0x180008ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ceb  mov     rax, [rsp+88h+arg_8]
0x180008cf3  jmp     short loc_180008D6F
0x180008cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cfc  mov     rax, [rsp+88h+arg_8]
0x180008d04  jmp     short loc_180008D6F
0x180008d06  mov     edi, eax
0x180008d08  mov     [rsp+88h+var_48], eax
0x180008d0c  test    eax, eax
0x180008d0e  jz      short loc_180008D59
0x180008d10  lea     rax, WPP_GLOBAL_Control
0x180008d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d1e  cmp     rcx, rax
0x180008d21  jz      short loc_180008D48
0x180008d23  test    byte ptr [rcx+1Ch], 1
0x180008d27  jz      short loc_180008D48
0x180008d29  mov     edx, 120h
0x180008d2e  mov     r9d, edi
0x180008d31  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008d38  mov     rcx, [rcx+10h]
0x180008d3c  call    WPP_SF_d
0x180008d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d48  lea     r12, WPP_GLOBAL_Control
0x180008d4f  mov     rax, [rsp+88h+arg_38]
0x180008d57  jmp     short loc_180008D6F
0x180008d59  lea     r12, WPP_GLOBAL_Control
0x180008d60  mov     rax, [rsp+88h+arg_38]
0x180008d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d6f  test    edi, edi
0x180008d71  jnz     short loc_180008DB7
0x180008d73  cmp     rcx, r12
0x180008d76  jz      short loc_180008D82
0x180008d78  test    byte ptr [rcx+1Ch], 8
0x180008d7c  jnz     loc_180009060
0x180008d82  mov     eax, edi
0x180008d84  add     rsp, 50h
0x180008d88  pop     r15
0x180008d8a  pop     r14
0x180008d8c  pop     r13
0x180008d8e  pop     r12
0x180008d90  pop     rdi
0x180008d91  pop     rsi
0x180008d92  pop     rbx
0x180008d93  retn
0x180008d94  cmp     dword ptr [rsi], 0
0x180008d97  jz      loc_180008BC8
0x180008d9d  mov     edi, 57h ; 'W'
0x180008da2  cmp     rcx, r12
0x180008da5  jz      short loc_180008DE7
0x180008da7  test    byte ptr [rcx+1Ch], 1
0x180008dab  jz      short loc_180008DE7
0x180008dad  mov     edx, 11Bh
0x180008db2  jmp     loc_180008E41
0x180008db7  test    rax, rax
0x180008dba  jz      short loc_180008D73
0x180008dbc  cmp     dword ptr [rax+4], 2
0x180008dc0  jnz     short loc_180008D73
0x180008dc2  cmp     dword ptr [rax+18h], 1
0x180008dc6  jz      short loc_180008D73
0x180008dc8  mov     rcx, rax
0x180008dcb  call    Int_FWCleanupGPOPolicyStore
0x180008dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dd7  jmp     short loc_180008D73
0x180008dd9  mov     edi, 57h ; 'W'
0x180008dde  cmp     rcx, r12
0x180008de1  jnz     loc_180009051
0x180008de7  mov     rax, [rsp+88h+arg_8]
0x180008def  jmp     loc_180008D6F
0x180008df4  mov     edx, 116h
0x180008df9  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008e00  mov     rcx, [rcx+10h]
0x180008e04  call    WPP_SF_
0x180008e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e10  mov     r8d, [rsp+88h+arg_0]
0x180008e18  jmp     loc_180008B71
0x180008e1d  mov     edi, 57h ; 'W'
0x180008e22  cmp     rcx, r12
0x180008e25  jz      loc_180008D6F
0x180008e2b  test    byte ptr [rcx+1Ch], 1
0x180008e2f  jz      loc_180008D6F
0x180008e35  mov     edx, 117h
0x180008e3a  jmp     short loc_180008E41
0x180008e3c  mov     edx, 118h
0x180008e41  mov     r9d, edi
0x180008e44  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008e4b  mov     rcx, [rcx+10h]
0x180008e4f  call    WPP_SF_d
0x180008e54  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e5b  jmp     short loc_180008DE7
0x180008e5d  mov     edi, 57h ; 'W'
0x180008e62  cmp     rcx, r12
0x180008e65  jz      short loc_180008DE7
0x180008e67  test    byte ptr [rcx+1Ch], 1
0x180008e6b  jz      loc_180008DE7
0x180008e71  mov     edx, 119h
0x180008e76  jmp     short loc_180008E41
0x180008e78  mov     edi, 57h ; 'W'
0x180008e7d  cmp     rcx, r12
0x180008e80  jz      loc_180008DE7
0x180008e86  test    byte ptr [rcx+1Ch], 1
0x180008e8a  jz      loc_180008DE7
0x180008e90  mov     edx, 11Ah
0x180008e95  jmp     short loc_180008E41
0x180008e97  cmp     r13d, 12h
0x180008e9b  jl      loc_180008BEA
0x180008ea1  mov     edi, 32h ; '2'
0x180008ea6  cmp     rcx, r12
0x180008ea9  jz      loc_180008D6F
0x180008eaf  test    byte ptr [rcx+1Ch], 1
0x180008eb3  jz      loc_180008D6F
0x180008eb9  mov     edx, 11Ch
0x180008ebe  jmp     short loc_180008EC5
0x180008ec0  mov     edx, 122h
0x180008ec5  mov     r9d, edi
0x180008ec8  jmp     short loc_180008ED2
0x180008eca  mov     edx, 125h
0x180008ecf  mov     r9d, eax
0x180008ed2  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180008ed9  mov     rcx, [rcx+10h]
0x180008edd  call    WPP_SF_d
0x180008ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee9  mov     rax, rbx
0x180008eec  jmp     loc_180008D6F
0x180008ef1  cmp     edx, 2
0x180008ef4  jz      short loc_180008EFB
0x180008ef6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008efb  mov     rcx, rbx
0x180008efe  call    Int_FWOpenGPOPolicyStore
0x180008f03  mov     edi, eax
0x180008f05  test    eax, eax
0x180008f07  jz      short loc_180008F25
0x180008f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f10  cmp     rcx, r12
0x180008f13  jz      short loc_180008EE9
0x180008f15  test    byte ptr [rcx+1Ch], 1
0x180008f19  jz      short loc_180008EE9
0x180008f1b  mov     edx, 121h
0x180008f20  mov     r9d, eax
0x180008f23  jmp     short loc_180008ED2
0x180008f25  cmp     qword ptr [rbx+38h], 0
0x180008f2a  jnz     short loc_180008F31
0x180008f2c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008f31  test    r15b, 1
0x180008f35  jz      short loc_180008F53
0x180008f37  mov     edi, 57h ; 'W'
0x180008f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f43  cmp     rcx, r12
0x180008f46  jz      short loc_180008EE9
0x180008f48  test    byte ptr [rcx+1Ch], 1
0x180008f4c  jz      short loc_180008EE9
0x180008f4e  jmp     loc_180008EC0
0x180008f53  mov     r15d, [rsp+88h+arg_0]
0x180008f5b  mov     r9, r14
0x180008f5e  mov     r8d, [rsp+88h+arg_18]
0x180008f66  mov     edx, r13d
0x180008f69  mov     rcx, [rbx+38h]
0x180008f6d  test    r15d, r15d
0x180008f70  jz      short loc_180008FB2
0x180008f72  mov     [rsp+88h+var_68], rsi
0x180008f77  call    cs:__imp_FwGetConfig
0x180008f7d  mov     ecx, eax
0x180008f7f  call    cs:__imp_FwHResultToWindowsError
0x180008f85  mov     edi, eax
0x180008f87  test    eax, eax
0x180008f89  jz      short loc_180008FF3
0x180008f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f92  cmp     rcx, r12
0x180008f95  jz      loc_180008EE9
0x180008f9b  test    byte ptr [rcx+1Ch], 1
0x180008f9f  jz      loc_180008EE9
0x180008fa5  mov     edx, 123h
0x180008faa  mov     r9d, eax
0x180008fad  jmp     loc_180008ED2
0x180008fb2  mov     eax, [rsi]
0x180008fb4  mov     dword ptr [rsp+88h+var_68], eax
0x180008fb8  call    cs:__imp_FwSetConfig
0x180008fbe  mov     ecx, eax
0x180008fc0  call    cs:__imp_FwHResultToWindowsError
0x180008fc6  mov     edi, eax
0x180008fc8  test    eax, eax
0x180008fca  jz      short loc_180008FF3
0x180008fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fd3  cmp     rcx, r12
0x180008fd6  jz      loc_180008EE9
0x180008fdc  test    byte ptr [rcx+1Ch], 1
0x180008fe0  jz      loc_180008EE9
0x180008fe6  mov     edx, 124h
0x180008feb  mov     r9d, eax
0x180008fee  jmp     loc_180008ED2
0x180008ff3  xor     edx, edx
0x180008ff5  test    r15d, r15d
0x180008ff8  setz    dl
0x180008ffb  xor     r8d, r8d
0x180008ffe  mov     rcx, rbx
0x180009001  call    Int_FWCloseGPOPolicyStore
0x180009006  mov     edi, eax
  ... truncated ...
```
