# FwRuleLookup(void *,ushort const *,int,_tag_FW_RULE * *)

- ea: `0x18001c4dc`
- end: `0x18001c76a`
- name: `?FwRuleLookup@@YAJPEAXPEBGHPEAPEAU_tag_FW_RULE@@@Z`
- size: `654`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, int, struct _tag_FW_RULE **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180003f80`
- `0x180004300`

## callees

- `0x180005954`
- `0x180009fb0`
- `0x18001c4dc`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001c5b8`
- `ntdll!EtwEventWrite` at `0x18001c65e`
- `ntdll!EtwEventWrite` at `0x18001c5b8`
- `ntdll!EtwEventWrite` at `0x18001c65e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c5d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c5d4`
- `fwbase!FwReportReturnError` at `0x18001c677`
- `fwbase!FwReportReturnError` at `0x18001c686`
- `fwbase!FwReportReturnError` at `0x18001c677`
- `fwbase!FwReportReturnError` at `0x18001c686`

## pseudocode

```c
__int64 __fastcall FwRuleLookup(__int64 a1, const unsigned __int16 *a2, int a3, struct _tag_FW_RULE **a4)
{
  FwPolicy2 *v8; // rcx
  __int16 v9; // bx
  unsigned int v10; // eax
  signed int v11; // ebx
  bool v12; // sf
  struct _tag_FW_RULE *v14; // [rsp+60h] [rbp-29h] BYREF
  int v15; // [rsp+68h] [rbp-21h] BYREF
  int v16; // [rsp+6Ch] [rbp-1Dh]
  __int128 *v17; // [rsp+70h] [rbp-19h]
  __int64 v18; // [rsp+78h] [rbp-11h]
  __int128 v19; // [rsp+80h] [rbp-9h] BYREF
  const unsigned __int16 *v20; // [rsp+90h] [rbp+7h]
  __int128 v21; // [rsp+98h] [rbp+Fh] BYREF
  int v22; // [rsp+A8h] [rbp+1Fh] BYREF

  v14 = 0;
  v22 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  v15 = 545;
  v16 = 1;
  v18 = 0x10000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  *(_QWORD *)&v19 = 2;
  DWORD2(v19) = 5;
  *((_QWORD *)&v21 + 1) = &v19;
  v20 = a2;
  v17 = &v21;
  v9 = a3 == 0 ? 7 : 0;
  LODWORD(v21) = 1;
  v16 = 1;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v8 + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v10 = Int_FWQueryObject(
          0,
          (unsigned int)FWVerifyFirewallRuleQuery,
          (unsigned int)RPC_FWQueryFirewallRules,
          (unsigned int)RRPC_FWQueryFirewallRules,
          (__int64)Int_RPC_FWEnumFirewallRules2_0,
          (__int64)Int_RRPC_FWEnumFirewallRules2_0,
          a1,
          (__int64)&v15,
          v9,
          (__int64)&v22,
          (__int64)&v14,
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
  {
    if ( v22 )
    {
      *a4 = v14;
      v14 = 0;
      return (unsigned int)v11;
    }
    *a4 = 0;
    v11 = -2147023728;
  }
  FwReportReturnError("FwRuleLookup", (unsigned int)v11);
  return (unsigned int)FwReportReturnError("FwRuleLookup", (unsigned int)v11);
}

```

## disassembly

```asm
0x18001c4dc  mov     [rsp-8+arg_10], rbx
0x18001c4e1  push    rbp
0x18001c4e2  push    rsi
0x18001c4e3  push    rdi
0x18001c4e4  push    r13
0x18001c4e6  push    r14
0x18001c4e8  lea     rbp, [rsp-37h]
0x18001c4ed  sub     rsp, 0C0h
0x18001c4f4  mov     rax, cs:__security_cookie
0x18001c4fb  xor     rax, rsp
0x18001c4fe  mov     [rbp+57h+var_30], rax
0x18001c502  xorps   xmm0, xmm0
0x18001c505  mov     [rbp+57h+var_80], 0
0x18001c50d  xor     eax, eax
0x18001c50f  mov     [rbp+57h+var_38], 0
0x18001c516  movups  [rbp+57h+var_60], xmm0
0x18001c51a  mov     [rbp+57h+var_50], rax
0x18001c51e  mov     rdi, r9
0x18001c521  movups  [rbp+57h+var_48], xmm0
0x18001c525  mov     [rbp+57h+var_70], rax
0x18001c529  mov     ebx, r8d
0x18001c52c  mov     rsi, rdx
0x18001c52f  mov     [rbp+57h+var_78], 221h
0x18001c536  mov     r14, rcx
0x18001c539  mov     [rbp+57h+var_74], 1
0x18001c540  mov     [rbp+57h+var_68], 10000h
0x18001c548  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c54f  lea     r13, WPP_GLOBAL_Control
0x18001c556  cmp     rcx, r13
0x18001c559  jnz     loc_18001C6B3
0x18001c55f  neg     ebx
0x18001c561  mov     qword ptr [rbp+57h+var_60], 2
0x18001c569  lea     rax, [rbp+57h+var_60]
0x18001c56d  mov     dword ptr [rbp+57h+var_60+8], 5
0x18001c574  sbb     bx, bx
0x18001c577  mov     qword ptr [rbp+57h+var_48+8], rax
0x18001c57b  lea     rax, [rbp+57h+var_48]
0x18001c57f  mov     [rbp+57h+var_50], rsi
0x18001c583  not     bx
0x18001c586  mov     [rbp+57h+var_70], rax
0x18001c58a  mov     rax, cs:g_Provider
0x18001c591  and     bx, 7
0x18001c595  mov     dword ptr [rbp+57h+var_48], 1
0x18001c59c  mov     [rbp+57h+var_74], 1
0x18001c5a3  test    rax, rax
0x18001c5a6  jz      short loc_18001C5C5
0x18001c5a8  xor     r9d, r9d
0x18001c5ab  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x18001c5b2  xor     r8d, r8d
0x18001c5b5  mov     rcx, rax
0x18001c5b8  call    cs:__imp_EtwEventWrite
0x18001c5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5c5  cmp     rcx, r13
0x18001c5c8  jz      short loc_18001C5D4
0x18001c5ca  test    byte ptr [rcx+1Ch], 8
0x18001c5ce  jnz     loc_18001C705
0x18001c5d4  call    cs:__imp_GetTickCount64
0x18001c5da  mov     [rsp+0E0h+var_88], 0
0x18001c5e2  lea     rax, [rbp+57h+var_80]
0x18001c5e6  mov     [rsp+0E0h+var_90], rax
0x18001c5eb  lea     r9, RRPC_FWQueryFirewallRules
0x18001c5f2  lea     rax, [rbp+57h+var_38]
0x18001c5f6  xor     ecx, ecx
0x18001c5f8  mov     [rsp+0E0h+var_98], rax
0x18001c5fd  lea     r8, RPC_FWQueryFirewallRules
0x18001c604  mov     [rsp+0E0h+var_A0], bx
0x18001c609  lea     rax, [rbp+57h+var_78]
0x18001c60d  mov     [rsp+0E0h+var_A8], rax
0x18001c612  lea     rdx, FWVerifyFirewallRuleQuery
0x18001c619  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18001c620  mov     [rsp+0E0h+var_B0], r14
0x18001c625  mov     [rsp+0E0h+var_B8], rax
0x18001c62a  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18001c631  mov     [rsp+0E0h+var_C0], rax
0x18001c636  call    Int_FWQueryObject
0x18001c63b  mov     ebx, eax
0x18001c63d  test    eax, eax
0x18001c63f  jnz     loc_18001C71F
0x18001c645  mov     rcx, cs:g_Provider
0x18001c64c  test    rcx, rcx
0x18001c64f  jz      short loc_18001C664
0x18001c651  xor     r9d, r9d
0x18001c654  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x18001c65b  xor     r8d, r8d
0x18001c65e  call    cs:__imp_EtwEventWrite
0x18001c664  test    ebx, ebx
0x18001c666  jg      loc_18001C6F5
0x18001c66c  jns     short loc_18001C6DE
0x18001c66e  mov     edx, ebx
0x18001c670  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x18001c677  call    cs:__imp_FwReportReturnError
0x18001c67d  mov     edx, ebx
0x18001c67f  lea     rcx, aFwrulelookup; "FwRuleLookup"
0x18001c686  call    cs:__imp_FwReportReturnError
0x18001c68c  mov     ebx, eax
0x18001c68e  mov     eax, ebx
0x18001c690  mov     rcx, [rbp+57h+var_30]
0x18001c694  xor     rcx, rsp; StackCookie
0x18001c697  call    __security_check_cookie
0x18001c69c  mov     rbx, [rsp+0E0h+arg_10]
0x18001c6a4  add     rsp, 0C0h
0x18001c6ab  pop     r14
0x18001c6ad  pop     r13
0x18001c6af  pop     rdi
0x18001c6b0  pop     rsi
0x18001c6b1  pop     rbp
0x18001c6b2  retn
0x18001c6b3  test    byte ptr [rcx+1Ch], 8
0x18001c6b7  jz      loc_18001C55F
0x18001c6bd  mov     rcx, [rcx+10h]
0x18001c6c1  lea     r8, WPP_a6cbafa53f3d3248427edec9c64d88dc_Traceguids
0x18001c6c8  mov     edx, 3Ch ; '<'
0x18001c6cd  call    WPP_SF_
0x18001c6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6d9  jmp     loc_18001C55F
0x18001c6de  cmp     [rbp+57h+var_38], 0
0x18001c6e2  ja      short loc_18001C756
0x18001c6e4  mov     qword ptr [rdi], 0
0x18001c6eb  mov     ebx, 80070490h
0x18001c6f0  jmp     loc_18001C66E
0x18001c6f5  movzx   ebx, bx
0x18001c6f8  or      ebx, 80070000h
0x18001c6fe  test    ebx, ebx
0x18001c700  jmp     loc_18001C66C
0x18001c705  mov     rcx, [rcx+10h]
0x18001c709  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001c710  mov     edx, 0B7h
0x18001c715  call    WPP_SF_
0x18001c71a  jmp     loc_18001C5D4
0x18001c71f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c726  cmp     rcx, r13
0x18001c729  jz      loc_18001C645
0x18001c72f  test    byte ptr [rcx+1Ch], 1
0x18001c733  jz      loc_18001C645
0x18001c739  mov     rcx, [rcx+10h]
0x18001c73d  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001c744  mov     edx, 0B8h
0x18001c749  mov     r9d, ebx
0x18001c74c  call    WPP_SF_d
0x18001c751  jmp     loc_18001C645
0x18001c756  mov     rax, [rbp+57h+var_80]
0x18001c75a  mov     [rdi], rax
0x18001c75d  mov     [rbp+57h+var_80], 0
0x18001c765  jmp     loc_18001C68E
```
