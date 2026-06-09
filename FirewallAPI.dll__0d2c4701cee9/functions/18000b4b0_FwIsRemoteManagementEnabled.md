# FwIsRemoteManagementEnabled

- ea: `0x18000b4b0`
- end: `0x18000b9ab`
- name: `FwIsRemoteManagementEnabled`
- size: `1275`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005e0c`
- `0x180009780`
- `0x18000b4b0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x18000d980`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b7fc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b7fc`
- `ntdll!EtwEventWrite` at `0x18000b597`
- `ntdll!EtwEventWrite` at `0x18000b7ab`
- `ntdll!EtwEventWrite` at `0x18000b597`
- `ntdll!EtwEventWrite` at `0x18000b7ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b5b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b5b3`
- `fwbase!FwReportErrorAsWinError` at `0x18000b8bd`
- `fwbase!FwReportErrorAsWinError` at `0x18000b925`
- `fwbase!FwReportErrorAsWinError` at `0x18000b8bd`
- `fwbase!FwReportErrorAsWinError` at `0x18000b925`
- `fwbase!FwReportReturnError` at `0x18000b998`
- `fwbase!FwReportReturnError` at `0x18000b998`

## string_xrefs

- `0x18000b8af`: `FWOpenPolicyStore`
- `0x18000b7cc`: `@FirewallAPI.dll,-30002`

## pseudocode

```c
__int64 __fastcall FwIsRemoteManagementEnabled(__int64 a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  WCHAR *v5; // r14
  unsigned int v6; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdi
  unsigned int v10; // ebx
  __int64 *v11; // rbx
  int i; // edi
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v17[2]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v18[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int (__fastcall *v19)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+90h] [rbp-70h] BYREF
  __int16 v20; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v21)(int, int, int, int, __int16, __int64, __int64); // [rsp+A0h] [rbp-60h]
  __int16 v22; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v23)(int, int, int, int, __int16, __int64, __int64); // [rsp+B0h] [rbp-50h]
  __int16 v24; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v25)(int, int, int, int, __int16, __int64, __int64); // [rsp+C0h] [rbp-40h]
  __int16 v26; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v27)(int, int, int, int, __int16, __int64, __int64); // [rsp+D0h] [rbp-30h]
  __int16 v28; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v29)(int, int, int, int, __int16, __int64, __int64); // [rsp+E0h] [rbp-20h]
  __int16 v30; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v31)(int, int, int, int, __int16, __int64, __int64); // [rsp+F0h] [rbp-10h]
  __int16 v32; // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v33)(int, int, int, int, __int16, __int64, __int64); // [rsp+100h] [rbp+0h]
  __int16 v34; // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v35)(int, int, int, int, __int16, __int64, __int64); // [rsp+110h] [rbp+10h]
  __int16 v36; // [rsp+118h] [rbp+18h]
  unsigned int (__fastcall *v37)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+120h] [rbp+20h] BYREF
  __int16 v38; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v39)(int, int, int, int, __int16, __int64, __int64); // [rsp+130h] [rbp+30h]
  __int16 v40; // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v41)(int, int, int, int, __int16, __int64, __int64); // [rsp+140h] [rbp+40h]
  __int16 v42; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v43)(int, int, int, int, __int16, __int64, __int64); // [rsp+150h] [rbp+50h]
  __int16 v44; // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v45)(int, int, int, int, __int16, __int64, __int64); // [rsp+160h] [rbp+60h]
  __int16 v46; // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v47)(int, int, int, int, __int16, __int64, __int64); // [rsp+170h] [rbp+70h]
  __int16 v48; // [rsp+178h] [rbp+78h]
  __int64 (__fastcall *v49)(int, int, int, int, __int16, __int64, __int64); // [rsp+180h] [rbp+80h]
  __int16 v50; // [rsp+188h] [rbp+88h]
  __int64 (__fastcall *v51)(int, int, int, int, __int16, __int64, __int64); // [rsp+190h] [rbp+90h]
  __int16 v52; // [rsp+198h] [rbp+98h]
  __int64 (__fastcall *v53)(int, int, int, int, __int16, __int64, __int64); // [rsp+1A0h] [rbp+A0h]
  __int16 v54; // [rsp+1A8h] [rbp+A8h]

  v14 = 0;
  v5 = (WCHAR *)a3;
  v15 = 0;
  v6 = a2;
  v18[0] = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( v5 && a4 )
  {
    *a4 = 0;
    *(_DWORD *)v5 = 1;
    if ( a1 )
    {
      v9 = a1;
      v14 = a1;
    }
    else
    {
      v8 = FWOpenPolicyStore(545, 0, 5, 1, 0, (__int64)&v14);
      if ( v8 == 2 )
        return 0;
      if ( v8 )
      {
        i = FwReportErrorAsWinError("FwIsRemoteManagementEnabled", "FWOpenPolicyStore", v8);
LABEL_34:
        if ( v14 )
          FWClosePolicyStore(v14, a2, a3, a4);
        goto LABEL_20;
      }
      v9 = v14;
      v6 = 0x80000000;
    }
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_EnumFirewallRules, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    GetTickCount64();
    v17[0] = 9;
    v19 = Int_RPC_FWEnumFirewallRules2_0;
    v20 = 512;
    v21 = RPC_FWEnumFirewallRules2_10;
    v34 = 543;
    v23 = RPC_FWEnumFirewallRules2_20;
    v52 = 543;
    v25 = RPC_FWEnumFirewallRules2_24;
    v38 = 512;
    v27 = RPC_FWEnumFirewallRules2_25;
    v29 = RPC_FWEnumFirewallRules2_26;
    v31 = RPC_FWEnumFirewallRules2_27;
    v33 = RPC_FWEnumFirewallRules2_31;
    v35 = RPC_FWEnumFirewallRules2_33;
    v28 = 537;
    v36 = 545;
    v46 = 537;
    v17[1] = &v19;
    v37 = Int_RRPC_FWEnumFirewallRules2_0;
    v22 = 522;
    v39 = RRPC_FWEnumFirewallRules2_10;
    v41 = RRPC_FWEnumFirewallRules2_20;
    v43 = RRPC_FWEnumFirewallRules2_24;
    v45 = RRPC_FWEnumFirewallRules2_25;
    v47 = RRPC_FWEnumFirewallRules2_26;
    v49 = RRPC_FWEnumFirewallRules2_27;
    v51 = RRPC_FWEnumFirewallRules2_31;
    v53 = RRPC_FWEnumFirewallRules2_33;
    v54 = 545;
    v16[1] = &v37;
    v24 = 532;
    v26 = 536;
    v30 = 538;
    v32 = 539;
    v40 = 522;
    v42 = 532;
    v44 = 536;
    v48 = 538;
    v50 = 539;
    v16[0] = 9;
    v10 = Int_FWEnumObject(0, v17, v16, v9, 196608, v6, 0, v18, &v15, 0);
    if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v10);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_EnumFirewallRules, 0, 0);
    if ( v10 )
    {
      i = FwReportErrorAsWinError("FwIsRemoteManagementEnabled", "FWEnumFirewallRules", v10);
    }
    else
    {
      v11 = v15;
      for ( i = 0; v11; v11 = (__int64 *)*v11 )
      {
        a3 = (const WCHAR *)v11[39];
        if ( a3 && CompareStringW(0x7Fu, 1u, a3, -1, L"@FirewallAPI.dll,-30002", -1) == 2 )
        {
          if ( *((_DWORD *)v11 + 72) != 3 || (*((_BYTE *)v11 + 292) & 1) == 0 )
            *(_DWORD *)v5 = 0;
          *a4 = 1;
        }
      }
    }
  }
  else
  {
    i = -2147024809;
  }
  if ( !a1 )
    goto LABEL_34;
LABEL_20:
  if ( v15 )
    FWFreeFirewallRules(v15);
  if ( !*a4 )
    *(_DWORD *)v5 = 0;
  if ( i < 0 )
    return (unsigned int)FwReportReturnError("FwIsRemoteManagementEnabled", (unsigned int)i);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x18000b4b0  push    rbp
0x18000b4b2  push    rbx
0x18000b4b3  push    rsi
0x18000b4b4  push    r12
0x18000b4b6  push    r13
0x18000b4b8  push    r14
0x18000b4ba  push    r15
0x18000b4bc  lea     rbp, [rsp-0D0h]
0x18000b4c4  sub     rsp, 1D0h
0x18000b4cb  mov     rax, cs:__security_cookie
0x18000b4d2  xor     rax, rsp
0x18000b4d5  mov     [rbp+100h+var_50], rax
0x18000b4dc  xor     r13d, r13d
0x18000b4df  mov     rsi, r9
0x18000b4e2  mov     [rsp+200h+var_1B0], r13
0x18000b4e7  mov     r14, r8
0x18000b4ea  mov     [rsp+200h+var_1A8], r13
0x18000b4ef  mov     ebx, edx
0x18000b4f1  mov     [rbp+100h+var_180], r13d
0x18000b4f5  mov     r15, rcx
0x18000b4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4ff  lea     r12, WPP_GLOBAL_Control
0x18000b506  cmp     rcx, r12
0x18000b509  jnz     loc_18000B888
0x18000b50f  mov     [rsp+200h+var_38], rdi
0x18000b517  test    r14, r14
0x18000b51a  jz      loc_18000B938
0x18000b520  test    rsi, rsi
0x18000b523  jz      loc_18000B938
0x18000b529  mov     [rsi], r13d
0x18000b52c  mov     dword ptr [r14], 1
0x18000b533  test    r15, r15
0x18000b536  jnz     loc_18000B8E3
0x18000b53c  lea     rax, [rsp+200h+var_1B0]
0x18000b541  mov     ecx, 221h
0x18000b546  mov     qword ptr [rsp+200h+cchCount2], rax
0x18000b54b  xor     edx, edx
0x18000b54d  mov     r9d, 1
0x18000b553  mov     dword ptr [rsp+200h+lpString2], r13d
0x18000b558  mov     r8d, 5
0x18000b55e  call    FWOpenPolicyStore
0x18000b563  cmp     eax, 2
0x18000b566  jz      loc_18000B942
0x18000b56c  test    eax, eax
0x18000b56e  jnz     loc_18000B8AC
0x18000b574  mov     rdi, [rsp+200h+var_1B0]
0x18000b579  mov     ebx, 80000000h
0x18000b57e  mov     rcx, cs:g_Provider
0x18000b585  test    rcx, rcx
0x18000b588  jz      short loc_18000B5A3
0x18000b58a  xor     r9d, r9d
0x18000b58d  lea     rdx, MPS_CLNT_API_Enter_EnumFirewallRules
0x18000b594  xor     r8d, r8d
0x18000b597  call    cs:__imp_EtwEventWrite
0x18000b59e  nop     dword ptr [rax+rax+00h]
0x18000b5a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5aa  cmp     rcx, r12
0x18000b5ad  jnz     loc_18000B8F0
0x18000b5b3  call    cs:__imp_GetTickCount64
0x18000b5ba  nop     dword ptr [rax+rax+00h]
0x18000b5bf  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000b5c6  mov     [rsp+200h+var_190], 9
0x18000b5cf  mov     [rbp+100h+var_170], rax
0x18000b5d3  mov     r13d, 200h
0x18000b5d9  lea     rax, RPC_FWEnumFirewallRules2_10
0x18000b5e0  mov     [rbp+100h+var_168], r13w
0x18000b5e5  mov     [rbp+100h+var_160], rax
0x18000b5e9  mov     ecx, 21Fh
0x18000b5ee  lea     rax, RPC_FWEnumFirewallRules2_20
0x18000b5f5  mov     [rbp+100h+var_F8], cx
0x18000b5f9  mov     [rbp+100h+var_150], rax
0x18000b5fd  mov     r9d, 219h
0x18000b603  lea     rax, RPC_FWEnumFirewallRules2_24
0x18000b60a  mov     [rbp+100h+var_68], cx
0x18000b611  mov     [rbp+100h+var_140], rax
0x18000b615  lea     rcx, [rsp+200h+var_1A8]
0x18000b61a  lea     rax, RPC_FWEnumFirewallRules2_25
0x18000b621  mov     [rbp+100h+var_D8], r13w
0x18000b626  mov     [rbp+100h+var_130], rax
0x18000b62a  xor     r13d, r13d
0x18000b62d  mov     [rsp+200h+var_1B8], r13d
0x18000b632  lea     rax, RPC_FWEnumFirewallRules2_26
0x18000b639  mov     [rbp+100h+var_120], rax
0x18000b63d  mov     r12d, 20Ah
0x18000b643  mov     [rsp+200h+var_1C0], rcx
0x18000b648  lea     rax, RPC_FWEnumFirewallRules2_27
0x18000b64f  mov     [rbp+100h+var_110], rax
0x18000b653  lea     rcx, [rbp+100h+var_180]
0x18000b657  lea     rax, RPC_FWEnumFirewallRules2_31
0x18000b65e  mov     [rsp+200h+var_1C8], rcx
0x18000b663  mov     [rbp+100h+var_100], rax
0x18000b667  mov     r11d, 214h
0x18000b66d  lea     rax, RPC_FWEnumFirewallRules2_33
0x18000b674  mov     [rsp+200h+var_1D0], r13w
0x18000b67a  mov     [rbp+100h+var_F0], rax
0x18000b67e  mov     r10d, 218h
0x18000b684  mov     eax, 221h
0x18000b689  mov     [rbp+100h+var_128], r9w
0x18000b68e  mov     [rbp+100h+var_E8], ax
0x18000b692  mov     r8d, 21Ah
0x18000b698  lea     rax, [rbp+100h+var_170]
0x18000b69c  mov     [rbp+100h+var_98], r9w
0x18000b6a1  mov     [rsp+200h+var_188], rax
0x18000b6a6  mov     edx, 21Bh
0x18000b6ab  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000b6b2  mov     [rsp+200h+cchCount2], ebx
0x18000b6b6  mov     [rbp+100h+var_E0], rax
0x18000b6ba  mov     r9, rdi
0x18000b6bd  lea     rax, RRPC_FWEnumFirewallRules2_10
0x18000b6c4  mov     [rbp+100h+var_158], r12w
0x18000b6c9  mov     [rbp+100h+var_D0], rax
0x18000b6cd  lea     rax, RRPC_FWEnumFirewallRules2_20
0x18000b6d4  mov     [rbp+100h+var_C0], rax
0x18000b6d8  lea     rax, RRPC_FWEnumFirewallRules2_24
0x18000b6df  mov     [rbp+100h+var_B0], rax
0x18000b6e3  lea     rax, RRPC_FWEnumFirewallRules2_25
0x18000b6ea  mov     [rbp+100h+var_A0], rax
0x18000b6ee  lea     rax, RRPC_FWEnumFirewallRules2_26
0x18000b6f5  mov     [rbp+100h+var_90], rax
0x18000b6f9  lea     rax, RRPC_FWEnumFirewallRules2_27
0x18000b700  mov     [rbp+100h+var_80], rax
0x18000b707  lea     rax, RRPC_FWEnumFirewallRules2_31
0x18000b70e  mov     [rbp+100h+var_70], rax
0x18000b715  lea     rax, RRPC_FWEnumFirewallRules2_33
0x18000b71c  mov     [rbp+100h+var_60], rax
0x18000b723  mov     eax, 221h
0x18000b728  mov     [rbp+100h+var_58], ax
0x18000b72f  lea     rax, [rbp+100h+var_E0]
0x18000b733  mov     [rsp+200h+var_198], rax
0x18000b738  mov     [rbp+100h+var_148], r11w
0x18000b73d  mov     [rbp+100h+var_138], r10w
0x18000b742  mov     [rbp+100h+var_118], r8w
0x18000b747  mov     [rbp+100h+var_108], dx
0x18000b74b  mov     [rbp+100h+var_C8], r12w
0x18000b750  mov     [rbp+100h+var_B8], r11w
0x18000b755  mov     [rbp+100h+var_A8], r10w
0x18000b75a  mov     [rbp+100h+var_88], r8w
0x18000b75f  mov     [rbp+100h+var_78], dx
0x18000b766  mov     [rsp+200h+var_1A0], 9
0x18000b76f  mov     dword ptr [rsp+200h+lpString2], 30000h
0x18000b777  lea     r8, [rsp+200h+var_1A0]
0x18000b77c  xor     ecx, ecx
0x18000b77e  lea     rdx, [rsp+200h+var_190]
0x18000b783  call    Int_FWEnumObject
0x18000b788  mov     ebx, eax
0x18000b78a  test    eax, eax
0x18000b78c  jnz     loc_18000B949
0x18000b792  mov     rcx, cs:g_Provider
0x18000b799  test    rcx, rcx
0x18000b79c  jz      short loc_18000B7B7
0x18000b79e  xor     r9d, r9d
0x18000b7a1  lea     rdx, MPS_CLNT_API_Exit_EnumFirewallRules
0x18000b7a8  xor     r8d, r8d
0x18000b7ab  call    cs:__imp_EtwEventWrite
0x18000b7b2  nop     dword ptr [rax+rax+00h]
0x18000b7b7  test    ebx, ebx
0x18000b7b9  jnz     loc_18000B914
0x18000b7bf  mov     rbx, [rsp+200h+var_1A8]
0x18000b7c4  mov     edi, r13d
0x18000b7c7  test    rbx, rbx
0x18000b7ca  jz      short loc_18000B815
0x18000b7cc  lea     r12, String2; "@FirewallAPI.dll,-30002"
0x18000b7d3  mov     r8, [rbx+138h]; lpString1
0x18000b7da  test    r8, r8
0x18000b7dd  jz      short loc_18000B80D
0x18000b7df  mov     [rsp+200h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000b7e7  mov     edx, 1; dwCmpFlags
0x18000b7ec  mov     ecx, 7Fh; Locale
0x18000b7f1  mov     [rsp+200h+lpString2], r12; lpString2
0x18000b7f6  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000b7fc  call    cs:__imp_CompareStringW
0x18000b803  nop     dword ptr [rax+rax+00h]
0x18000b808  cmp     eax, 2
0x18000b80b  jz      short loc_18000B86B
0x18000b80d  mov     rbx, [rbx]
0x18000b810  test    rbx, rbx
0x18000b813  jnz     short loc_18000B7D3
0x18000b815  test    r15, r15
0x18000b818  jz      loc_18000B8CB
0x18000b81e  mov     rcx, [rsp+200h+var_1A8]
0x18000b823  test    rcx, rcx
0x18000b826  jz      short loc_18000B82D
0x18000b828  call    FWFreeFirewallRules
0x18000b82d  cmp     dword ptr [rsi], 0
0x18000b830  jz      loc_18000B987
0x18000b836  test    edi, edi
0x18000b838  js      loc_18000B98F
0x18000b83e  mov     eax, edi
0x18000b840  mov     rdi, [rsp+200h+var_38]
0x18000b848  mov     rcx, [rbp+100h+var_50]
0x18000b84f  xor     rcx, rsp; StackCookie
0x18000b852  call    __security_check_cookie
0x18000b857  add     rsp, 1D0h
0x18000b85e  pop     r15
0x18000b860  pop     r14
0x18000b862  pop     r13
0x18000b864  pop     r12
0x18000b866  pop     rsi
0x18000b867  pop     rbx
0x18000b868  pop     rbp
0x18000b869  retn
0x18000b86b  cmp     dword ptr [rbx+120h], 3
0x18000b872  jnz     short loc_18000B87D
0x18000b874  test    byte ptr [rbx+124h], 1
0x18000b87b  jnz     short loc_18000B880
0x18000b87d  mov     [r14], r13d
0x18000b880  mov     dword ptr [rsi], 1
0x18000b886  jmp     short loc_18000B80D
0x18000b888  test    byte ptr [rcx+1Ch], 8
0x18000b88c  jz      loc_18000B50F
0x18000b892  mov     rcx, [rcx+10h]
0x18000b896  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18000b89d  mov     edx, 0Ah
0x18000b8a2  call    WPP_SF_
0x18000b8a7  jmp     loc_18000B50F
0x18000b8ac  mov     r8d, eax
0x18000b8af  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x18000b8b6  lea     rcx, aFwisremotemana_0; "FwIsRemoteManagementEnabled"
0x18000b8bd  call    cs:__imp_FwReportErrorAsWinError
0x18000b8c4  nop     dword ptr [rax+rax+00h]
0x18000b8c9  mov     edi, eax
0x18000b8cb  mov     rcx, [rsp+200h+var_1B0]
0x18000b8d0  test    rcx, rcx
0x18000b8d3  jz      loc_18000B81E
0x18000b8d9  call    FWClosePolicyStore
0x18000b8de  jmp     loc_18000B81E
0x18000b8e3  mov     rdi, r15
0x18000b8e6  mov     [rsp+200h+var_1B0], r15
0x18000b8eb  jmp     loc_18000B57E
0x18000b8f0  test    byte ptr [rcx+1Ch], 8
0x18000b8f4  jz      loc_18000B5B3
0x18000b8fa  mov     rcx, [rcx+10h]
0x18000b8fe  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000b905  mov     edx, 60h ; '`'
0x18000b90a  call    WPP_SF_
0x18000b90f  jmp     loc_18000B5B3
0x18000b914  mov     r8d, ebx
0x18000b917  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x18000b91e  lea     rcx, aFwisremotemana_0; "FwIsRemoteManagementEnabled"
0x18000b925  call    cs:__imp_FwReportErrorAsWinError
0x18000b92c  nop     dword ptr [rax+rax+00h]
0x18000b931  mov     edi, eax
0x18000b933  jmp     loc_18000B815
0x18000b938  mov     edi, 80070057h
0x18000b93d  jmp     loc_18000B815
0x18000b942  xor     eax, eax
0x18000b944  jmp     loc_18000B840
0x18000b949  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b950  lea     rax, WPP_GLOBAL_Control
0x18000b957  cmp     rcx, rax
0x18000b95a  jz      loc_18000B792
0x18000b960  test    byte ptr [rcx+1Ch], 1
0x18000b964  jz      loc_18000B792
0x18000b96a  mov     rcx, [rcx+10h]
0x18000b96e  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000b975  mov     edx, 61h ; 'a'
0x18000b97a  mov     r9d, ebx
0x18000b97d  call    WPP_SF_d
0x18000b982  jmp     loc_18000B792
0x18000b987  mov     [r14], r13d
0x18000b98a  jmp     loc_18000B836
0x18000b98f  mov     edx, edi
0x18000b991  lea     rcx, aFwisremotemana_0; "FwIsRemoteManagementEnabled"
0x18000b998  call    cs:__imp_FwReportReturnError
0x18000b99f  nop     dword ptr [rax+rax+00h]
0x18000b9a4  mov     edi, eax
0x18000b9a6  jmp     loc_18000B83E
```
