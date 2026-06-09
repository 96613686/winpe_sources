# FwEnumRulesFromRuleGroup(void *,ulong,ushort,ushort *,ulong *,_tag_FW_RULE * *)

- ea: `0x180009340`
- end: `0x18000974e`
- name: `?FwEnumRulesFromRuleGroup@@YAJPEAXKGPEAGPEAKPEAPEAU_tag_FW_RULE@@@Z`
- size: `1038`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned int@<edx>, unsigned __int16@<r8w>, unsigned __int16 *@<r9>, unsigned int *, struct _tag_FW_RULE **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180015eb0`

## callees

- `0x180005954`
- `0x180006910`
- `0x180009080`
- `0x180009340`
- `0x180009fb0`
- `0x18000acd4`
- `0x18000b8c0`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800093a8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800093a8`
- `ntdll!EtwEventWrite` at `0x18000943b`
- `ntdll!EtwEventWrite` at `0x1800094e7`
- `ntdll!EtwEventWrite` at `0x18000943b`
- `ntdll!EtwEventWrite` at `0x1800094e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000945e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000945e`
- `fwbase!FwBaseFree` at `0x180009528`
- `fwbase!FwBaseFree` at `0x18000964d`
- `fwbase!FwBaseFree` at `0x180009728`
- `fwbase!FwBaseFree` at `0x180009528`
- `fwbase!FwBaseFree` at `0x18000964d`
- `fwbase!FwBaseFree` at `0x180009728`
- `fwbase!FwLoadIndirectString` at `0x1800095a5`
- `fwbase!FwLoadIndirectString` at `0x1800095a5`
- `fwbase!FwReportReturnError` at `0x18000962e`
- `fwbase!FwReportReturnError` at `0x18000965c`
- `fwbase!FwReportReturnError` at `0x1800096cf`
- `fwbase!FwReportReturnError` at `0x180009709`
- `fwbase!FwReportReturnError` at `0x18000962e`
- `fwbase!FwReportReturnError` at `0x18000965c`
- `fwbase!FwReportReturnError` at `0x1800096cf`
- `fwbase!FwReportReturnError` at `0x180009709`
- `fwbase!FwStringCopy` at `0x1800096e4`
- `fwbase!FwStringCopy` at `0x1800096fa`
- `fwbase!FwStringCopy` at `0x1800096e4`
- `fwbase!FwStringCopy` at `0x1800096fa`

## string_xrefs

- `0x180009395`: `@FirewallAPI.dll,-`

## pseudocode

```c
__int64 __fastcall FwEnumRulesFromRuleGroup(
        void *a1,
        unsigned int a2,
        unsigned __int16 a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _tag_FW_RULE **a6)
{
  unsigned int v10; // eax
  signed int v11; // ebx
  bool v12; // sf
  int v14; // eax
  int v15; // eax
  struct _tag_FW_RULE *v16; // rdi
  struct _tag_FW_RULE **v17; // rsi
  __int64 v18; // rdx
  unsigned int v19; // eax
  struct _tag_FW_RULE *v20; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v21; // [rsp+68h] [rbp-98h] BYREF
  struct _tag_FW_RULE *v22; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v23[2]; // [rsp+78h] [rbp-88h] BYREF
  int *v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  unsigned int v26; // [rsp+90h] [rbp-70h] BYREF
  int v27; // [rsp+94h] [rbp-6Ch] BYREF
  int v28; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+B0h] [rbp-50h] BYREF
  int v31; // [rsp+B8h] [rbp-48h]
  unsigned int v32; // [rsp+C0h] [rbp-40h]
  __int64 v33; // [rsp+C8h] [rbp-38h]
  int v34; // [rsp+D0h] [rbp-30h]
  int v35; // [rsp+D8h] [rbp-28h]
  int v36; // [rsp+E0h] [rbp-20h]
  int v37; // [rsp+E4h] [rbp-1Ch]
  int v38; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v39; // [rsp+F0h] [rbp-10h]

  v21 = 0;
  v22 = 0;
  v20 = 0;
  v27 = 0;
  v26 = 0;
  if ( !(unsigned int)_o__wcsnicmp(a4, L"@FirewallAPI.dll,-", 18) )
  {
    v29 = &v30;
    v24 = &v28;
    v28 = 3;
    v23[0] = 545;
    v23[1] = 1;
    v25 = 0x10000;
    v30 = 0;
    v31 = 3;
    v32 = a2;
    v33 = 1;
    v34 = 3;
    v35 = 196608;
    v36 = 8;
    v37 = 1;
    v38 = 5;
    v39 = a4;
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    GetTickCount64();
    v10 = Int_FWQueryObject(
            0,
            (unsigned int)FWVerifyFirewallRuleQuery,
            (unsigned int)RPC_FWQueryFirewallRules,
            (unsigned int)RRPC_FWQueryFirewallRules,
            (__int64)Int_RPC_FWEnumFirewallRules2_0,
            (__int64)Int_RRPC_FWEnumFirewallRules2_0,
            (__int64)a1,
            (__int64)v23,
            a3,
            (__int64)&v26,
            (__int64)&v20,
            0);
    v11 = v10;
    if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v10);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
    v12 = v11 < 0;
    if ( v11 > 0 )
    {
      v11 = (unsigned __int16)v11 | 0x80070000;
      v12 = v11 < 0;
    }
    if ( !v12 )
      goto LABEL_13;
    FwReportReturnError("FwQueryRulesInRuleGroup", (unsigned int)v11);
    goto LABEL_33;
  }
  v14 = FwQueryRulesInRuleGroup(a1, a2, a3, a4, &v26, &v20);
  v11 = v14;
  if ( v14 < 0 )
  {
    v18 = (unsigned int)v14;
LABEL_27:
    FwReportReturnError("FwEnumRulesFromRuleGroup", v18);
    FWFreeFirewallRules(v22);
    FWFreeFirewallRules(v20);
    FwBaseFree(v21);
    return FwReportReturnError("FwEnumRulesFromRuleGroup", (unsigned int)v11);
  }
  if ( v26 )
    goto LABEL_13;
  if ( (int)FwLoadIndirectString(a4, &v21) < 0 && (int)FwStringCopy(a4, &v21) < 0 )
  {
    v19 = FwStringCopy(a4, &v21);
    FwReportReturnError("FwEnumRulesFromRuleGroup", v19);
    FWFreeFirewallRules(v22);
    FWFreeFirewallRules(v20);
    FwBaseFree(v21);
    return (unsigned int)v11;
  }
  v15 = FWEnumFirewallRules((_DWORD)a1, 196608, a2, a3, (__int64)&v27, (__int64)&v22);
  v11 = v15;
  if ( v15 > 0 )
    v11 = (unsigned __int16)v15 | 0x80070000;
  if ( v11 < 0 )
  {
LABEL_33:
    v18 = (unsigned int)v11;
    goto LABEL_27;
  }
  v16 = v22;
  v17 = &v22;
  if ( v22 )
  {
    do
    {
      if ( FwRuleInGroup(v16, v21) )
      {
        *v17 = *(struct _tag_FW_RULE **)v16;
        *(_QWORD *)v16 = v20;
        ++v26;
        v20 = v16;
      }
      else
      {
        v17 = (struct _tag_FW_RULE **)v16;
      }
      v16 = *v17;
    }
    while ( *v17 );
  }
LABEL_13:
  *a6 = v20;
  *a5 = v26;
  v26 = 0;
  v20 = 0;
  FWFreeFirewallRules(v22);
  FWFreeFirewallRules(v20);
  FwBaseFree(v21);
  if ( v11 >= 0 )
    return (unsigned int)v11;
  return FwReportReturnError("FwEnumRulesFromRuleGroup", (unsigned int)v11);
}

```

## disassembly

```asm
0x180009340  push    rbp
0x180009342  push    rbx
0x180009343  push    rsi
0x180009344  push    rdi
0x180009345  push    r12
0x180009347  push    r13
0x180009349  push    r14
0x18000934b  push    r15
0x18000934d  lea     rbp, [rsp-18h]
0x180009352  sub     rsp, 118h
0x180009359  mov     rax, cs:__security_cookie
0x180009360  xor     rax, rsp
0x180009363  mov     [rbp+50h+var_50], rax
0x180009367  mov     r14, [rbp+50h+arg_20]
0x18000936e  xor     ebx, ebx
0x180009370  mov     r15, [rbp+50h+arg_28]
0x180009377  movzx   r13d, r8w
0x18000937b  mov     esi, edx
0x18000937d  mov     [rsp+150h+var_E8], rbx
0x180009382  mov     r12, rcx
0x180009385  mov     [rsp+150h+var_E0], rbx
0x18000938a  mov     r8d, 12h
0x180009390  mov     [rsp+150h+var_F0], rbx
0x180009395  lea     rdx, aFirewallapiDll_14; "@FirewallAPI.dll,-"
0x18000939c  mov     [rbp+50h+var_BC], ebx
0x18000939f  mov     rcx, r9
0x1800093a2  mov     [rbp+50h+var_C0], ebx
0x1800093a5  mov     rdi, r9
0x1800093a8  call    cs:__imp__o__wcsnicmp
0x1800093ae  test    eax, eax
0x1800093b0  jnz     loc_180009565
0x1800093b6  mov     rcx, cs:g_Provider
0x1800093bd  lea     rax, [rbp+50h+var_A0]
0x1800093c1  mov     [rbp+50h+var_B0], rax
0x1800093c5  lea     rax, [rbp+50h+var_B8]
0x1800093c9  mov     [rbp+50h+var_D0], rax
0x1800093cd  mov     [rbp+50h+var_B8], 3
0x1800093d4  mov     [rsp+150h+var_D8], 221h
0x1800093dc  mov     [rsp+150h+var_D4], 1
0x1800093e4  mov     [rbp+50h+var_C8], 10000h
0x1800093ec  mov     [rbp+50h+var_A0], rbx
0x1800093f0  mov     [rbp+50h+var_98], 3
0x1800093f7  mov     [rbp+50h+var_90], esi
0x1800093fa  mov     [rbp+50h+var_88], 1
0x180009402  mov     [rbp+50h+var_80], 3
0x180009409  mov     [rbp+50h+var_78], 30000h
0x180009410  mov     [rbp+50h+var_70], 8
0x180009417  mov     [rbp+50h+var_6C], 1
0x18000941e  mov     [rbp+50h+var_68], 5
0x180009425  mov     [rbp+50h+var_60], rdi
0x180009429  test    rcx, rcx
0x18000942c  jz      short loc_180009441
0x18000942e  xor     r9d, r9d
0x180009431  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x180009438  xor     r8d, r8d
0x18000943b  call    cs:__imp_EtwEventWrite
0x180009441  mov     rcx, cs:WPP_GLOBAL_Control
0x180009448  lea     rdi, WPP_GLOBAL_Control
0x18000944f  cmp     rcx, rdi
0x180009452  jz      short loc_18000945E
0x180009454  test    byte ptr [rcx+1Ch], 8
0x180009458  jnz     loc_180009675
0x18000945e  call    cs:__imp_GetTickCount64
0x180009464  mov     [rsp+150h+var_F8], ebx
0x180009468  lea     rax, [rsp+150h+var_F0]
0x18000946d  mov     [rsp+150h+var_100], rax
0x180009472  lea     r9, RRPC_FWQueryFirewallRules
0x180009479  lea     rax, [rbp+50h+var_C0]
0x18000947d  xor     ecx, ecx
0x18000947f  mov     [rsp+150h+var_108], rax
0x180009484  lea     r8, RPC_FWQueryFirewallRules
0x18000948b  mov     [rsp+150h+var_110], r13w
0x180009491  lea     rax, [rsp+150h+var_D8]
0x180009496  mov     [rsp+150h+var_118], rax
0x18000949b  lea     rdx, FWVerifyFirewallRuleQuery
0x1800094a2  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800094a9  mov     [rsp+150h+var_120], r12
0x1800094ae  mov     [rsp+150h+var_128], rax
0x1800094b3  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800094ba  mov     [rsp+150h+var_130], rax
0x1800094bf  call    Int_FWQueryObject
0x1800094c4  mov     ebx, eax
0x1800094c6  test    eax, eax
0x1800094c8  jnz     loc_18000968F
0x1800094ce  mov     rcx, cs:g_Provider
0x1800094d5  test    rcx, rcx
0x1800094d8  jz      short loc_1800094ED
0x1800094da  xor     r9d, r9d
0x1800094dd  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x1800094e4  xor     r8d, r8d
0x1800094e7  call    cs:__imp_EtwEventWrite
0x1800094ed  test    ebx, ebx
0x1800094ef  jg      short loc_180009558
0x1800094f1  js      loc_1800096C6
0x1800094f7  mov     rax, [rsp+150h+var_F0]
0x1800094fc  xor     ecx, ecx
0x1800094fe  mov     [r15], rax
0x180009501  mov     eax, [rbp+50h+var_C0]
0x180009504  mov     [r14], eax
0x180009507  mov     [rbp+50h+var_C0], ecx
0x18000950a  mov     [rsp+150h+var_F0], rcx
0x18000950f  mov     rcx, [rsp+150h+var_E0]
0x180009514  call    FWFreeFirewallRules
0x180009519  mov     rcx, [rsp+150h+var_F0]
0x18000951e  call    FWFreeFirewallRules
0x180009523  mov     rcx, [rsp+150h+var_E8]
0x180009528  call    cs:__imp_FwBaseFree
0x18000952e  test    ebx, ebx
0x180009530  js      loc_180009653
0x180009536  mov     eax, ebx
0x180009538  mov     rcx, [rbp+50h+var_50]
0x18000953c  xor     rcx, rsp; StackCookie
0x18000953f  call    __security_check_cookie
0x180009544  add     rsp, 118h
0x18000954b  pop     r15
0x18000954d  pop     r14
0x18000954f  pop     r13
0x180009551  pop     r12
0x180009553  pop     rdi
0x180009554  pop     rsi
0x180009555  pop     rbx
0x180009556  pop     rbp
0x180009557  retn
0x180009558  movzx   ebx, bx
0x18000955b  or      ebx, 80070000h
0x180009561  test    ebx, ebx
0x180009563  jmp     short loc_1800094F1
0x180009565  lea     rax, [rsp+150h+var_F0]
0x18000956a  mov     r9, rdi; unsigned __int16 *
0x18000956d  mov     [rsp+150h+var_128], rax; struct _tag_FW_RULE **
0x180009572  movzx   r8d, r13w; unsigned __int16
0x180009576  lea     rax, [rbp+50h+var_C0]
0x18000957a  mov     edx, esi; unsigned int
0x18000957c  mov     rcx, r12; void *
0x18000957f  mov     [rsp+150h+var_130], rax; unsigned int *
0x180009584  call    ?FwQueryRulesInRuleGroup@@YAJPEAXKGPEAGPEAKPEAPEAU_tag_FW_RULE@@@Z; FwQueryRulesInRuleGroup(void *,ulong,ushort,ushort *,ulong *,_tag_FW_RULE * *)
0x180009589  mov     ebx, eax
0x18000958b  test    eax, eax
0x18000958d  js      loc_180009625
0x180009593  cmp     [rbp+50h+var_C0], 0
0x180009597  jnz     loc_1800094F7
0x18000959d  lea     rdx, [rsp+150h+var_E8]
0x1800095a2  mov     rcx, rdi
0x1800095a5  call    cs:__imp_FwLoadIndirectString
0x1800095ab  test    eax, eax
0x1800095ad  js      loc_1800096DC
0x1800095b3  lea     rax, [rsp+150h+var_E0]
0x1800095b8  movzx   r9d, r13w
0x1800095bc  mov     [rsp+150h+var_128], rax
0x1800095c1  mov     r8d, esi
0x1800095c4  lea     rax, [rbp+50h+var_BC]
0x1800095c8  mov     edx, 30000h
0x1800095cd  mov     rcx, r12
0x1800095d0  mov     [rsp+150h+var_130], rax
0x1800095d5  call    FWEnumFirewallRules
0x1800095da  mov     ebx, eax
0x1800095dc  test    eax, eax
0x1800095de  jg      loc_180009667
0x1800095e4  test    ebx, ebx
0x1800095e6  js      loc_1800096D5
0x1800095ec  mov     rdi, [rsp+150h+var_E0]
0x1800095f1  lea     rsi, [rsp+150h+var_E0]
0x1800095f6  test    rdi, rdi
0x1800095f9  jz      loc_1800094F7
0x1800095ff  nop
0x180009600  mov     rdx, [rsp+150h+var_E8]; unsigned __int16 *
0x180009605  mov     rcx, rdi; struct _tag_FW_RULE *
0x180009608  call    ?FwRuleInGroup@@YAHPEBU_tag_FW_RULE@@PEBG@Z; FwRuleInGroup(_tag_FW_RULE const *,ushort const *)
0x18000960d  test    eax, eax
0x18000960f  jnz     loc_180009733
0x180009615  mov     rsi, rdi
0x180009618  mov     rdi, [rsi]
0x18000961b  test    rdi, rdi
0x18000961e  jnz     short loc_180009600
0x180009620  jmp     loc_1800094F7
0x180009625  mov     edx, eax
0x180009627  lea     rcx, aFwenumrulesfro; "FwEnumRulesFromRuleGroup"
0x18000962e  call    cs:__imp_FwReportReturnError
0x180009634  mov     rcx, [rsp+150h+var_E0]
0x180009639  call    FWFreeFirewallRules
0x18000963e  mov     rcx, [rsp+150h+var_F0]
0x180009643  call    FWFreeFirewallRules
0x180009648  mov     rcx, [rsp+150h+var_E8]
0x18000964d  call    cs:__imp_FwBaseFree
0x180009653  mov     edx, ebx
0x180009655  lea     rcx, aFwenumrulesfro; "FwEnumRulesFromRuleGroup"
0x18000965c  call    cs:__imp_FwReportReturnError
0x180009662  jmp     loc_180009538
0x180009667  movzx   ebx, ax
0x18000966a  or      ebx, 80070000h
0x180009670  jmp     loc_1800095E4
0x180009675  mov     rcx, [rcx+10h]
0x180009679  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180009680  mov     edx, 0B7h
0x180009685  call    WPP_SF_
0x18000968a  jmp     loc_18000945E
0x18000968f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009696  cmp     rcx, rdi
0x180009699  jz      loc_1800094CE
0x18000969f  test    byte ptr [rcx+1Ch], 1
0x1800096a3  jz      loc_1800094CE
0x1800096a9  mov     rcx, [rcx+10h]
0x1800096ad  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800096b4  mov     edx, 0B8h
0x1800096b9  mov     r9d, ebx
0x1800096bc  call    WPP_SF_d
0x1800096c1  jmp     loc_1800094CE
0x1800096c6  mov     edx, ebx
0x1800096c8  lea     rcx, aFwqueryrulesin; "FwQueryRulesInRuleGroup"
0x1800096cf  call    cs:__imp_FwReportReturnError
0x1800096d5  mov     edx, ebx
0x1800096d7  jmp     loc_180009627
0x1800096dc  lea     rdx, [rsp+150h+var_E8]
0x1800096e1  mov     rcx, rdi
0x1800096e4  call    cs:__imp_FwStringCopy
0x1800096ea  test    eax, eax
0x1800096ec  jns     loc_1800095B3
0x1800096f2  lea     rdx, [rsp+150h+var_E8]
0x1800096f7  mov     rcx, rdi
0x1800096fa  call    cs:__imp_FwStringCopy
0x180009700  mov     edx, eax
0x180009702  lea     rcx, aFwenumrulesfro; "FwEnumRulesFromRuleGroup"
0x180009709  call    cs:__imp_FwReportReturnError
0x18000970f  mov     rcx, [rsp+150h+var_E0]
0x180009714  call    FWFreeFirewallRules
0x180009719  mov     rcx, [rsp+150h+var_F0]
0x18000971e  call    FWFreeFirewallRules
0x180009723  mov     rcx, [rsp+150h+var_E8]
0x180009728  call    cs:__imp_FwBaseFree
0x18000972e  jmp     loc_180009536
0x180009733  mov     rax, [rdi]
0x180009736  mov     [rsi], rax
0x180009739  mov     rax, [rsp+150h+var_F0]
0x18000973e  mov     [rdi], rax
0x180009741  inc     [rbp+50h+var_C0]
0x180009744  mov     [rsp+150h+var_F0], rdi
0x180009749  jmp     loc_180009618
```
