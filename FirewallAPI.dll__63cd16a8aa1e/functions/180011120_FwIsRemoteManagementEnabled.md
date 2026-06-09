# FwIsRemoteManagementEnabled

- ea: `0x180011120`
- end: `0x1800115f0`
- name: `FwIsRemoteManagementEnabled`
- size: `1232`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005954`
- `0x180009080`
- `0x18000c130`
- `0x18000c560`
- `0x18000cd90`
- `0x180011120`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001145a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001145a`
- `ntdll!EtwEventWrite` at `0x180011207`
- `ntdll!EtwEventWrite` at `0x18001140f`
- `ntdll!EtwEventWrite` at `0x180011207`
- `ntdll!EtwEventWrite` at `0x18001140f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001121d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001121d`
- `fwbase!FwReportErrorAsWinError` at `0x180011514`
- `fwbase!FwReportErrorAsWinError` at `0x180011576`
- `fwbase!FwReportErrorAsWinError` at `0x180011514`
- `fwbase!FwReportErrorAsWinError` at `0x180011576`
- `fwbase!FwReportReturnError` at `0x1800115e3`
- `fwbase!FwReportReturnError` at `0x1800115e3`

## string_xrefs

- `0x180011506`: `FWOpenPolicyStore`
- `0x18001142a`: `@FirewallAPI.dll,-30002`

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
      v8 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v14);
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v10);
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
0x180011120  push    rbp
0x180011122  push    rbx
0x180011123  push    rsi
0x180011124  push    r12
0x180011126  push    r13
0x180011128  push    r14
0x18001112a  push    r15
0x18001112c  lea     rbp, [rsp-0D0h]
0x180011134  sub     rsp, 1D0h
0x18001113b  mov     rax, cs:__security_cookie
0x180011142  xor     rax, rsp
0x180011145  mov     [rbp+100h+var_50], rax
0x18001114c  xor     r13d, r13d
0x18001114f  mov     rsi, r9
0x180011152  mov     [rsp+200h+var_1B0], r13
0x180011157  mov     r14, r8
0x18001115a  mov     [rsp+200h+var_1A8], r13
0x18001115f  mov     ebx, edx
0x180011161  mov     [rbp+100h+var_180], r13d
0x180011165  mov     r15, rcx
0x180011168  mov     rcx, cs:WPP_GLOBAL_Control
0x18001116f  lea     r12, WPP_GLOBAL_Control
0x180011176  cmp     rcx, r12
0x180011179  jnz     loc_1800114DF
0x18001117f  mov     [rsp+200h+var_38], rdi
0x180011187  test    r14, r14
0x18001118a  jz      loc_180011583
0x180011190  test    rsi, rsi
0x180011193  jz      loc_180011583
0x180011199  mov     [rsi], r13d
0x18001119c  mov     dword ptr [r14], 1
0x1800111a3  test    r15, r15
0x1800111a6  jnz     loc_180011534
0x1800111ac  lea     rax, [rsp+200h+var_1B0]
0x1800111b1  mov     ecx, 221h
0x1800111b6  mov     qword ptr [rsp+200h+cchCount2], rax
0x1800111bb  xor     edx, edx
0x1800111bd  mov     r9d, 1
0x1800111c3  mov     dword ptr [rsp+200h+lpString2], r13d
0x1800111c8  mov     r8d, 5
0x1800111ce  call    FWOpenPolicyStore
0x1800111d3  cmp     eax, 2
0x1800111d6  jz      loc_18001158D
0x1800111dc  test    eax, eax
0x1800111de  jnz     loc_180011503
0x1800111e4  mov     rdi, [rsp+200h+var_1B0]
0x1800111e9  mov     ebx, 80000000h
0x1800111ee  mov     rcx, cs:g_Provider
0x1800111f5  test    rcx, rcx
0x1800111f8  jz      short loc_18001120D
0x1800111fa  xor     r9d, r9d
0x1800111fd  lea     rdx, MPS_CLNT_API_Enter_EnumFirewallRules
0x180011204  xor     r8d, r8d
0x180011207  call    cs:__imp_EtwEventWrite
0x18001120d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011214  cmp     rcx, r12
0x180011217  jnz     loc_180011541
0x18001121d  call    cs:__imp_GetTickCount64
0x180011223  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18001122a  mov     [rsp+200h+var_190], 9
0x180011233  mov     [rbp+100h+var_170], rax
0x180011237  mov     r13d, 200h
0x18001123d  lea     rax, RPC_FWEnumFirewallRules2_10
0x180011244  mov     [rbp+100h+var_168], r13w
0x180011249  mov     [rbp+100h+var_160], rax
0x18001124d  mov     ecx, 21Fh
0x180011252  lea     rax, RPC_FWEnumFirewallRules2_20
0x180011259  mov     [rbp+100h+var_F8], cx
0x18001125d  mov     [rbp+100h+var_150], rax
0x180011261  mov     r9d, 219h
0x180011267  lea     rax, RPC_FWEnumFirewallRules2_24
0x18001126e  mov     [rbp+100h+var_68], cx
0x180011275  mov     [rbp+100h+var_140], rax
0x180011279  lea     rcx, [rsp+200h+var_1A8]
0x18001127e  lea     rax, RPC_FWEnumFirewallRules2_25
0x180011285  mov     [rbp+100h+var_D8], r13w
0x18001128a  mov     [rbp+100h+var_130], rax
0x18001128e  xor     r13d, r13d
0x180011291  mov     [rsp+200h+var_1B8], r13d
0x180011296  lea     rax, RPC_FWEnumFirewallRules2_26
0x18001129d  mov     [rbp+100h+var_120], rax
0x1800112a1  mov     r12d, 20Ah
0x1800112a7  mov     [rsp+200h+var_1C0], rcx
0x1800112ac  lea     rax, RPC_FWEnumFirewallRules2_27
0x1800112b3  mov     [rbp+100h+var_110], rax
0x1800112b7  lea     rcx, [rbp+100h+var_180]
0x1800112bb  lea     rax, RPC_FWEnumFirewallRules2_31
0x1800112c2  mov     [rsp+200h+var_1C8], rcx
0x1800112c7  mov     [rbp+100h+var_100], rax
0x1800112cb  mov     r11d, 214h
0x1800112d1  lea     rax, RPC_FWEnumFirewallRules2_33
0x1800112d8  mov     [rsp+200h+var_1D0], r13w
0x1800112de  mov     [rbp+100h+var_F0], rax
0x1800112e2  mov     r10d, 218h
0x1800112e8  mov     eax, 221h
0x1800112ed  mov     [rbp+100h+var_128], r9w
0x1800112f2  mov     [rbp+100h+var_E8], ax
0x1800112f6  mov     r8d, 21Ah
0x1800112fc  lea     rax, [rbp+100h+var_170]
0x180011300  mov     [rbp+100h+var_98], r9w
0x180011305  mov     [rsp+200h+var_188], rax
0x18001130a  mov     edx, 21Bh
0x18001130f  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180011316  mov     [rsp+200h+cchCount2], ebx
0x18001131a  mov     [rbp+100h+var_E0], rax
0x18001131e  mov     r9, rdi
0x180011321  lea     rax, RRPC_FWEnumFirewallRules2_10
0x180011328  mov     [rbp+100h+var_158], r12w
0x18001132d  mov     [rbp+100h+var_D0], rax
0x180011331  lea     rax, RRPC_FWEnumFirewallRules2_20
0x180011338  mov     [rbp+100h+var_C0], rax
0x18001133c  lea     rax, RRPC_FWEnumFirewallRules2_24
0x180011343  mov     [rbp+100h+var_B0], rax
0x180011347  lea     rax, RRPC_FWEnumFirewallRules2_25
0x18001134e  mov     [rbp+100h+var_A0], rax
0x180011352  lea     rax, RRPC_FWEnumFirewallRules2_26
0x180011359  mov     [rbp+100h+var_90], rax
0x18001135d  lea     rax, RRPC_FWEnumFirewallRules2_27
0x180011364  mov     [rbp+100h+var_80], rax
0x18001136b  lea     rax, RRPC_FWEnumFirewallRules2_31
0x180011372  mov     [rbp+100h+var_70], rax
0x180011379  lea     rax, RRPC_FWEnumFirewallRules2_33
0x180011380  mov     [rbp+100h+var_60], rax
0x180011387  mov     eax, 221h
0x18001138c  mov     [rbp+100h+var_58], ax
0x180011393  lea     rax, [rbp+100h+var_E0]
0x180011397  mov     [rsp+200h+var_198], rax
0x18001139c  mov     [rbp+100h+var_148], r11w
0x1800113a1  mov     [rbp+100h+var_138], r10w
0x1800113a6  mov     [rbp+100h+var_118], r8w
0x1800113ab  mov     [rbp+100h+var_108], dx
0x1800113af  mov     [rbp+100h+var_C8], r12w
0x1800113b4  mov     [rbp+100h+var_B8], r11w
0x1800113b9  mov     [rbp+100h+var_A8], r10w
0x1800113be  mov     [rbp+100h+var_88], r8w
0x1800113c3  mov     [rbp+100h+var_78], dx
0x1800113ca  mov     [rsp+200h+var_1A0], 9
0x1800113d3  mov     dword ptr [rsp+200h+lpString2], 30000h
0x1800113db  lea     r8, [rsp+200h+var_1A0]
0x1800113e0  xor     ecx, ecx
0x1800113e2  lea     rdx, [rsp+200h+var_190]
0x1800113e7  call    Int_FWEnumObject
0x1800113ec  mov     ebx, eax
0x1800113ee  test    eax, eax
0x1800113f0  jnz     loc_180011594
0x1800113f6  mov     rcx, cs:g_Provider
0x1800113fd  test    rcx, rcx
0x180011400  jz      short loc_180011415
0x180011402  xor     r9d, r9d
0x180011405  lea     rdx, MPS_CLNT_API_Exit_EnumFirewallRules
0x18001140c  xor     r8d, r8d
0x18001140f  call    cs:__imp_EtwEventWrite
0x180011415  test    ebx, ebx
0x180011417  jnz     loc_180011565
0x18001141d  mov     rbx, [rsp+200h+var_1A8]
0x180011422  mov     edi, r13d
0x180011425  test    rbx, rbx
0x180011428  jz      short loc_18001146D
0x18001142a  lea     r12, String2; "@FirewallAPI.dll,-30002"
0x180011431  mov     r8, [rbx+138h]; lpString1
0x180011438  test    r8, r8
0x18001143b  jz      short loc_180011465
0x18001143d  mov     [rsp+200h+cchCount2], 0FFFFFFFFh; cchCount2
0x180011445  mov     edx, 1; dwCmpFlags
0x18001144a  mov     ecx, 7Fh; Locale
0x18001144f  mov     [rsp+200h+lpString2], r12; lpString2
0x180011454  mov     r9d, 0FFFFFFFFh; cchCount1
0x18001145a  call    cs:__imp_CompareStringW
0x180011460  cmp     eax, 2
0x180011463  jz      short loc_1800114C2
0x180011465  mov     rbx, [rbx]
0x180011468  test    rbx, rbx
0x18001146b  jnz     short loc_180011431
0x18001146d  test    r15, r15
0x180011470  jz      loc_18001151C
0x180011476  mov     rcx, [rsp+200h+var_1A8]
0x18001147b  test    rcx, rcx
0x18001147e  jz      short loc_180011485
0x180011480  call    FWFreeFirewallRules
0x180011485  cmp     dword ptr [rsi], 0
0x180011488  jz      loc_1800115D2
0x18001148e  test    edi, edi
0x180011490  js      loc_1800115DA
0x180011496  mov     eax, edi
0x180011498  mov     rdi, [rsp+200h+var_38]
0x1800114a0  mov     rcx, [rbp+100h+var_50]
0x1800114a7  xor     rcx, rsp; StackCookie
0x1800114aa  call    __security_check_cookie
0x1800114af  add     rsp, 1D0h
0x1800114b6  pop     r15
0x1800114b8  pop     r14
0x1800114ba  pop     r13
0x1800114bc  pop     r12
0x1800114be  pop     rsi
0x1800114bf  pop     rbx
0x1800114c0  pop     rbp
0x1800114c1  retn
0x1800114c2  cmp     dword ptr [rbx+120h], 3
0x1800114c9  jnz     short loc_1800114D4
0x1800114cb  test    byte ptr [rbx+124h], 1
0x1800114d2  jnz     short loc_1800114D7
0x1800114d4  mov     [r14], r13d
0x1800114d7  mov     dword ptr [rsi], 1
0x1800114dd  jmp     short loc_180011465
0x1800114df  test    byte ptr [rcx+1Ch], 8
0x1800114e3  jz      loc_18001117F
0x1800114e9  mov     rcx, [rcx+10h]
0x1800114ed  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x1800114f4  mov     edx, 0Ah
0x1800114f9  call    WPP_SF_
0x1800114fe  jmp     loc_18001117F
0x180011503  mov     r8d, eax
0x180011506  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x18001150d  lea     rcx, aFwisremotemana_0; "FwIsRemoteManagementEnabled"
0x180011514  call    cs:__imp_FwReportErrorAsWinError
0x18001151a  mov     edi, eax
0x18001151c  mov     rcx, [rsp+200h+var_1B0]
0x180011521  test    rcx, rcx
0x180011524  jz      loc_180011476
0x18001152a  call    FWClosePolicyStore
0x18001152f  jmp     loc_180011476
0x180011534  mov     rdi, r15
0x180011537  mov     [rsp+200h+var_1B0], r15
0x18001153c  jmp     loc_1800111EE
0x180011541  test    byte ptr [rcx+1Ch], 8
0x180011545  jz      loc_18001121D
0x18001154b  mov     rcx, [rcx+10h]
0x18001154f  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180011556  mov     edx, 61h ; 'a'
0x18001155b  call    WPP_SF_
0x180011560  jmp     loc_18001121D
0x180011565  mov     r8d, ebx
0x180011568  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x18001156f  lea     rcx, aFwisremotemana_0; "FwIsRemoteManagementEnabled"
0x180011576  call    cs:__imp_FwReportErrorAsWinError
0x18001157c  mov     edi, eax
0x18001157e  jmp     loc_18001146D
0x180011583  mov     edi, 80070057h
0x180011588  jmp     loc_18001146D
0x18001158d  xor     eax, eax
0x18001158f  jmp     loc_180011498
0x180011594  mov     rcx, cs:WPP_GLOBAL_Control
0x18001159b  lea     rax, WPP_GLOBAL_Control
0x1800115a2  cmp     rcx, rax
0x1800115a5  jz      loc_1800113F6
0x1800115ab  test    byte ptr [rcx+1Ch], 1
0x1800115af  jz      loc_1800113F6
0x1800115b5  mov     rcx, [rcx+10h]
0x1800115b9  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800115c0  mov     edx, 62h ; 'b'
0x1800115c5  mov     r9d, ebx
0x1800115c8  call    WPP_SF_d
0x1800115cd  jmp     loc_1800113F6
0x1800115d2  mov     [r14], r13d
0x1800115d5  jmp     loc_18001148E
0x1800115da  mov     edx, edi
0x1800115dc  lea     rcx, aFwisremotemana_0; "FwIsRemoteManagementEnabled"
0x1800115e3  call    cs:__imp_FwReportReturnError
0x1800115e9  mov     edi, eax
0x1800115eb  jmp     loc_180011496
```
