# FwQueryRulesInRuleGroup(void *,ulong,ushort,ushort *,ulong *,_tag_FW_RULE * *)

- ea: `0x18000acd4`
- end: `0x18000aec9`
- name: `?FwQueryRulesInRuleGroup@@YAJPEAXKGPEAGPEAKPEAPEAU_tag_FW_RULE@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned __int16, unsigned __int16 *, unsigned int *, struct _tag_FW_RULE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180007880`
- `0x180009340`

## callees

- `0x180005954`
- `0x180009fb0`
- `0x18000acd4`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000ad89`
- `ntdll!EtwEventWrite` at `0x18000ae2a`
- `ntdll!EtwEventWrite` at `0x18000ad89`
- `ntdll!EtwEventWrite` at `0x18000ae2a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000adac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000adac`
- `fwbase!FwReportReturnError` at `0x18000aebe`
- `fwbase!FwReportReturnError` at `0x18000aebe`

## pseudocode

```c
__int64 __fastcall FwQueryRulesInRuleGroup(
        __int64 a1,
        int a2,
        __int16 a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _tag_FW_RULE **a6)
{
  unsigned int v8; // eax
  signed int v9; // ebx
  bool v10; // sf
  _DWORD v12[2]; // [rsp+60h] [rbp-69h] BYREF
  int *v13; // [rsp+68h] [rbp-61h]
  __int64 v14; // [rsp+70h] [rbp-59h]
  int v15; // [rsp+78h] [rbp-51h] BYREF
  __int64 *v16; // [rsp+80h] [rbp-49h]
  __int64 v17; // [rsp+90h] [rbp-39h] BYREF
  int v18; // [rsp+98h] [rbp-31h]
  int v19; // [rsp+A0h] [rbp-29h]
  __int64 v20; // [rsp+A8h] [rbp-21h]
  int v21; // [rsp+B0h] [rbp-19h]
  int v22; // [rsp+B8h] [rbp-11h]
  int v23; // [rsp+C0h] [rbp-9h]
  int v24; // [rsp+C4h] [rbp-5h]
  int v25; // [rsp+C8h] [rbp-1h]
  unsigned __int16 *v26; // [rsp+D0h] [rbp+7h]

  v16 = &v17;
  v15 = 3;
  v18 = 3;
  v21 = 3;
  v12[0] = 545;
  v12[1] = 1;
  v13 = &v15;
  v14 = 0x10000;
  v17 = 0;
  v19 = a2;
  v20 = 1;
  v22 = 196608;
  v23 = 8;
  v24 = 1;
  v25 = 5;
  v26 = a4;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v8 = Int_FWQueryObject(
         0,
         (unsigned int)FWVerifyFirewallRuleQuery,
         (unsigned int)RPC_FWQueryFirewallRules,
         (unsigned int)RRPC_FWQueryFirewallRules,
         (__int64)Int_RPC_FWEnumFirewallRules2_0,
         (__int64)Int_RRPC_FWEnumFirewallRules2_0,
         a1,
         (__int64)v12,
         a3,
         (__int64)a5,
         (__int64)a6,
         0);
  v9 = v8;
  if ( v8 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v8);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  v10 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x80070000;
    v10 = v9 < 0;
  }
  if ( v10 )
    FwReportReturnError("FwQueryRulesInRuleGroup", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000acd4  mov     [rsp-8+arg_8], rbx
0x18000acd9  push    rbp
0x18000acda  push    rsi
0x18000acdb  push    rdi
0x18000acdc  push    r12
0x18000acde  push    r14
0x18000ace0  lea     rbp, [rsp-27h]
0x18000ace5  sub     rsp, 0F0h
0x18000acec  mov     rax, cs:__security_cookie
0x18000acf3  xor     rax, rsp
0x18000acf6  mov     [rbp+47h+var_30], rax
0x18000acfa  mov     rsi, [rbp+47h+arg_20]
0x18000acfe  lea     rax, [rbp+47h+var_80]
0x18000ad02  mov     r14, [rbp+47h+arg_28]
0x18000ad06  mov     rbx, rcx
0x18000ad09  mov     ecx, 3
0x18000ad0e  mov     [rbp+47h+var_90], rax
0x18000ad12  mov     [rbp+47h+var_98], ecx
0x18000ad15  lea     rax, [rbp+47h+var_98]
0x18000ad19  mov     [rbp+47h+var_78], ecx
0x18000ad1c  movzx   edi, r8w
0x18000ad20  mov     [rbp+47h+var_60], ecx
0x18000ad23  mov     rcx, cs:g_Provider
0x18000ad2a  mov     [rbp+47h+var_B0], 221h
0x18000ad31  mov     [rbp+47h+var_AC], 1
0x18000ad38  mov     [rbp+47h+var_A8], rax
0x18000ad3c  mov     [rbp+47h+var_A0], 10000h
0x18000ad44  mov     [rbp+47h+var_80], 0
0x18000ad4c  mov     [rbp+47h+var_70], edx
0x18000ad4f  mov     [rbp+47h+var_68], 1
0x18000ad57  mov     [rbp+47h+var_58], 30000h
0x18000ad5e  mov     [rbp+47h+var_50], 8
0x18000ad65  mov     [rbp+47h+var_4C], 1
0x18000ad6c  mov     [rbp+47h+var_48], 5
0x18000ad73  mov     [rbp+47h+var_40], r9
0x18000ad77  test    rcx, rcx
0x18000ad7a  jz      short loc_18000AD8F
0x18000ad7c  xor     r9d, r9d
0x18000ad7f  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x18000ad86  xor     r8d, r8d
0x18000ad89  call    cs:__imp_EtwEventWrite
0x18000ad8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad96  lea     r12, WPP_GLOBAL_Control
0x18000ad9d  cmp     rcx, r12
0x18000ada0  jz      short loc_18000ADAC
0x18000ada2  test    byte ptr [rcx+1Ch], 8
0x18000ada6  jnz     loc_18000AE68
0x18000adac  call    cs:__imp_GetTickCount64
0x18000adb2  mov     [rsp+110h+var_B8], 0
0x18000adba  lea     rax, [rbp+47h+var_B0]
0x18000adbe  mov     [rsp+110h+var_C0], r14
0x18000adc3  lea     r9, RRPC_FWQueryFirewallRules
0x18000adca  mov     [rsp+110h+var_C8], rsi
0x18000adcf  lea     r8, RPC_FWQueryFirewallRules
0x18000add6  mov     [rsp+110h+var_D0], di
0x18000addb  lea     rdx, FWVerifyFirewallRuleQuery
0x18000ade2  mov     [rsp+110h+var_D8], rax
0x18000ade7  xor     ecx, ecx
0x18000ade9  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000adf0  mov     [rsp+110h+var_E0], rbx
0x18000adf5  mov     [rsp+110h+var_E8], rax
0x18000adfa  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000ae01  mov     [rsp+110h+var_F0], rax
0x18000ae06  call    Int_FWQueryObject
0x18000ae0b  mov     ebx, eax
0x18000ae0d  test    eax, eax
0x18000ae0f  jnz     short loc_18000AE82
0x18000ae11  mov     rcx, cs:g_Provider
0x18000ae18  test    rcx, rcx
0x18000ae1b  jz      short loc_18000AE30
0x18000ae1d  xor     r9d, r9d
0x18000ae20  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x18000ae27  xor     r8d, r8d
0x18000ae2a  call    cs:__imp_EtwEventWrite
0x18000ae30  test    ebx, ebx
0x18000ae32  jg      short loc_18000AE5B
0x18000ae34  js      short loc_18000AEB5
0x18000ae36  mov     eax, ebx
0x18000ae38  mov     rcx, [rbp+47h+var_30]
0x18000ae3c  xor     rcx, rsp; StackCookie
0x18000ae3f  call    __security_check_cookie
0x18000ae44  mov     rbx, [rsp+110h+arg_8]
0x18000ae4c  add     rsp, 0F0h
0x18000ae53  pop     r14
0x18000ae55  pop     r12
0x18000ae57  pop     rdi
0x18000ae58  pop     rsi
0x18000ae59  pop     rbp
0x18000ae5a  retn
0x18000ae5b  movzx   ebx, bx
0x18000ae5e  or      ebx, 80070000h
0x18000ae64  test    ebx, ebx
0x18000ae66  jmp     short loc_18000AE34
0x18000ae68  mov     rcx, [rcx+10h]
0x18000ae6c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000ae73  mov     edx, 0B7h
0x18000ae78  call    WPP_SF_
0x18000ae7d  jmp     loc_18000ADAC
0x18000ae82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae89  cmp     rcx, r12
0x18000ae8c  jz      short loc_18000AE11
0x18000ae8e  test    byte ptr [rcx+1Ch], 1
0x18000ae92  jz      loc_18000AE11
0x18000ae98  mov     rcx, [rcx+10h]
0x18000ae9c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000aea3  mov     edx, 0B8h
0x18000aea8  mov     r9d, ebx
0x18000aeab  call    WPP_SF_d
0x18000aeb0  jmp     loc_18000AE11
0x18000aeb5  mov     edx, ebx
0x18000aeb7  lea     rcx, aFwqueryrulesin; "FwQueryRulesInRuleGroup"
0x18000aebe  call    cs:__imp_FwReportReturnError
0x18000aec4  jmp     loc_18000AE36
```
