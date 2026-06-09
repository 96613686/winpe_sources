# FwRulesEnum::Initialize(FwPolicyViewFlags,_tag_FW_QUERY *,ulong)

- ea: `0x18000b050`
- end: `0x18000b343`
- name: `?Initialize@FwRulesEnum@@AEAAJW4FwPolicyViewFlags@@PEAU_tag_FW_QUERY@@K@Z`
- size: `755`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c0e0`
- `0x18001c260`

## callees

- `0x180005954`
- `0x180009fb0`
- `0x18000b050`
- `0x18000c560`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000b180`
- `ntdll!EtwEventWrite` at `0x18000b221`
- `ntdll!EtwEventWrite` at `0x18000b180`
- `ntdll!EtwEventWrite` at `0x18000b221`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b19c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b19c`
- `fwbase!FwReportReturnError` at `0x18000b276`
- `fwbase!FwReportReturnError` at `0x18000b285`
- `fwbase!FwReportReturnError` at `0x18000b276`
- `fwbase!FwReportReturnError` at `0x18000b285`

## pseudocode

```c
__int64 __fastcall FwRulesEnum::Initialize(__int64 a1, int a2, int *a3, int a4)
{
  int v8; // eax
  signed int v9; // ebx
  __int64 v10; // rbx
  unsigned int v11; // eax
  bool v12; // sf
  __int64 result; // rax
  int v14; // eax
  _QWORD *v15; // [rsp+28h] [rbp-B0h]
  int v16; // [rsp+60h] [rbp-78h] BYREF
  int v17; // [rsp+64h] [rbp-74h]
  __int128 *v18; // [rsp+68h] [rbp-70h]
  __int64 v19; // [rsp+70h] [rbp-68h]
  __int128 v20; // [rsp+78h] [rbp-60h] BYREF
  __int64 v21; // [rsp+88h] [rbp-50h] BYREF
  int v22; // [rsp+90h] [rbp-48h]
  int v23; // [rsp+98h] [rbp-40h]

  v16 = 532;
  v17 = 1;
  v20 = 0;
  v18 = 0;
  v19 = 0x10000;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_098d31ae94223bbae5defc232583cd37_Traceguids);
  *(_QWORD *)(a1 + 80) = a3;
  if ( !a3 )
  {
    LODWORD(v20) = 1;
    *((_QWORD *)&v20 + 1) = &v21;
    a3 = &v16;
    v17 = 1;
    v18 = &v20;
    v21 = 1;
    v22 = 3;
    v23 = 196608;
  }
  *(_DWORD *)(a1 + 64) = a4;
  v15 = (_QWORD *)(a1 + 88);
  if ( (a2 & 1) != 0 )
  {
    v14 = FWOpenPolicyStore(0x221u, 0, 4u, 1u, 0, v15);
    v9 = v14;
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_20;
  }
  else
  {
    v8 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, v15);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_20;
  }
  v10 = *(_QWORD *)(a1 + 88);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v11 = Int_FWQueryObject(
          0,
          (unsigned int)FWVerifyFirewallRuleQuery,
          (unsigned int)RPC_FWQueryFirewallRules,
          (unsigned int)RRPC_FWQueryFirewallRules,
          (__int64)Int_RPC_FWEnumFirewallRules2_0,
          (__int64)Int_RRPC_FWEnumFirewallRules2_0,
          v10,
          (__int64)a3,
          7,
          a1 + 104,
          a1 + 96,
          0);
  v9 = v11;
  if ( v11 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v11);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  v12 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x80070000;
    v12 = v9 < 0;
  }
  if ( !v12 )
  {
    *(_QWORD *)(a1 + 112) = *(_QWORD *)(a1 + 96);
    result = (unsigned int)v9;
    *(_DWORD *)(a1 + 120) = 0;
    *(_DWORD *)(a1 + 72) = a2;
    return result;
  }
LABEL_20:
  FwReportReturnError("FwRulesEnum::Initialize", (unsigned int)v9);
  return FwReportReturnError("FwRulesEnum::Initialize", (unsigned int)v9);
}

```

## disassembly

```asm
0x18000b050  mov     [rsp+arg_8], rbx
0x18000b055  mov     [rsp+arg_18], rbp
0x18000b05a  push    rsi
0x18000b05b  push    rdi
0x18000b05c  push    r12
0x18000b05e  push    r14
0x18000b060  push    r15
0x18000b062  sub     rsp, 0B0h
0x18000b069  mov     rax, cs:__security_cookie
0x18000b070  xor     rax, rsp
0x18000b073  mov     [rsp+0D8h+var_38], rax
0x18000b07b  xorps   xmm0, xmm0
0x18000b07e  mov     [rsp+0D8h+var_78], 214h
0x18000b086  xor     r15d, r15d
0x18000b089  mov     [rsp+0D8h+var_74], 1
0x18000b091  movups  [rsp+0D8h+var_60], xmm0
0x18000b096  mov     [rsp+0D8h+var_70], r15
0x18000b09b  mov     ebx, r9d
0x18000b09e  mov     rsi, r8
0x18000b0a1  mov     [rsp+0D8h+var_68], 10000h
0x18000b0aa  mov     ebp, edx
0x18000b0ac  mov     rdi, rcx
0x18000b0af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0b6  lea     r12, WPP_GLOBAL_Control
0x18000b0bd  cmp     rcx, r12
0x18000b0c0  jnz     loc_18000B28D
0x18000b0c6  mov     [rdi+50h], rsi
0x18000b0ca  test    rsi, rsi
0x18000b0cd  jnz     short loc_18000B120
0x18000b0cf  lea     rax, [rsp+0D8h+var_50]
0x18000b0d7  mov     dword ptr [rsp+0D8h+var_60], 1
0x18000b0df  mov     qword ptr [rsp+0D8h+var_60+8], rax
0x18000b0e7  lea     rsi, [rsp+0D8h+var_78]
0x18000b0ec  lea     rax, [rsp+0D8h+var_60]
0x18000b0f1  mov     [rsp+0D8h+var_74], 1
0x18000b0f9  mov     [rsp+0D8h+var_70], rax
0x18000b0fe  mov     [rsp+0D8h+var_50], 1
0x18000b10a  mov     [rsp+0D8h+var_48], 3
0x18000b115  mov     [rsp+0D8h+var_40], 30000h
0x18000b120  lea     r14, [rdi+58h]
0x18000b124  mov     [rdi+40h], ebx
0x18000b127  xor     edx, edx
0x18000b129  mov     [rsp+0D8h+var_B0], r14
0x18000b12e  mov     r9d, 1
0x18000b134  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x18000b139  mov     ecx, 221h
0x18000b13e  test    r9b, bpl
0x18000b141  jnz     loc_18000B2CF
0x18000b147  mov     r8d, 2
0x18000b14d  call    FWOpenPolicyStore
0x18000b152  mov     ebx, eax
0x18000b154  test    eax, eax
0x18000b156  jg      loc_18000B2B1
0x18000b15c  test    ebx, ebx
0x18000b15e  js      loc_18000B26D
0x18000b164  mov     rcx, cs:g_Provider
0x18000b16b  mov     rbx, [r14]
0x18000b16e  test    rcx, rcx
0x18000b171  jz      short loc_18000B186
0x18000b173  xor     r9d, r9d
0x18000b176  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x18000b17d  xor     r8d, r8d
0x18000b180  call    cs:__imp_EtwEventWrite
0x18000b186  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b18d  cmp     rcx, r12
0x18000b190  jz      short loc_18000B19C
0x18000b192  test    byte ptr [rcx+1Ch], 8
0x18000b196  jnz     loc_18000B2F2
0x18000b19c  call    cs:__imp_GetTickCount64
0x18000b1a2  mov     [rsp+0D8h+var_80], r15d
0x18000b1a7  lea     rax, [rdi+68h]
0x18000b1ab  lea     r14, [rdi+60h]
0x18000b1af  xor     ecx, ecx
0x18000b1b1  mov     [rsp+0D8h+var_88], r14
0x18000b1b6  lea     r9, RRPC_FWQueryFirewallRules
0x18000b1bd  mov     [rsp+0D8h+var_90], rax
0x18000b1c2  lea     r8, RPC_FWQueryFirewallRules
0x18000b1c9  mov     [rsp+0D8h+var_98], 7
0x18000b1d0  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000b1d7  mov     [rsp+0D8h+var_A0], rsi
0x18000b1dc  lea     rdx, FWVerifyFirewallRuleQuery
0x18000b1e3  mov     [rsp+0D8h+var_A8], rbx
0x18000b1e8  mov     [rsp+0D8h+var_B0], rax
0x18000b1ed  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000b1f4  mov     [rsp+0D8h+var_B8], rax
0x18000b1f9  call    Int_FWQueryObject
0x18000b1fe  mov     ebx, eax
0x18000b200  test    eax, eax
0x18000b202  jnz     loc_18000B30C
0x18000b208  mov     rcx, cs:g_Provider
0x18000b20f  test    rcx, rcx
0x18000b212  jz      short loc_18000B227
0x18000b214  xor     r9d, r9d
0x18000b217  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x18000b21e  xor     r8d, r8d
0x18000b221  call    cs:__imp_EtwEventWrite
0x18000b227  test    ebx, ebx
0x18000b229  jg      loc_18000B2BF
0x18000b22f  js      short loc_18000B26D
0x18000b231  mov     rax, [r14]
0x18000b234  mov     [rdi+70h], rax
0x18000b238  mov     eax, ebx
0x18000b23a  mov     [rdi+78h], r15d
0x18000b23e  mov     [rdi+48h], ebp
0x18000b241  mov     rcx, [rsp+0D8h+var_38]
0x18000b249  xor     rcx, rsp; StackCookie
0x18000b24c  call    __security_check_cookie
0x18000b251  lea     r11, [rsp+0D8h+var_28]
0x18000b259  mov     rbx, [r11+38h]
0x18000b25d  mov     rbp, [r11+48h]
0x18000b261  mov     rsp, r11
0x18000b264  pop     r15
0x18000b266  pop     r14
0x18000b268  pop     r12
0x18000b26a  pop     rdi
0x18000b26b  pop     rsi
0x18000b26c  retn
0x18000b26d  mov     edx, ebx
0x18000b26f  lea     rcx, aFwrulesenumIni; "FwRulesEnum::Initialize"
0x18000b276  call    cs:__imp_FwReportReturnError
0x18000b27c  mov     edx, ebx
0x18000b27e  lea     rcx, aFwrulesenumIni; "FwRulesEnum::Initialize"
0x18000b285  call    cs:__imp_FwReportReturnError
0x18000b28b  jmp     short loc_18000B241
0x18000b28d  test    byte ptr [rcx+1Ch], 8
0x18000b291  jz      loc_18000B0C6
0x18000b297  mov     rcx, [rcx+10h]
0x18000b29b  lea     r8, WPP_098d31ae94223bbae5defc232583cd37_Traceguids
0x18000b2a2  mov     edx, 0Ch
0x18000b2a7  call    WPP_SF_
0x18000b2ac  jmp     loc_18000B0C6
0x18000b2b1  movzx   ebx, ax
0x18000b2b4  or      ebx, 80070000h
0x18000b2ba  jmp     loc_18000B15C
0x18000b2bf  movzx   ebx, bx
0x18000b2c2  or      ebx, 80070000h
0x18000b2c8  test    ebx, ebx
0x18000b2ca  jmp     loc_18000B22F
0x18000b2cf  mov     r8d, 4
0x18000b2d5  call    FWOpenPolicyStore
0x18000b2da  mov     ebx, eax
0x18000b2dc  test    eax, eax
0x18000b2de  jle     short loc_18000B2E9
0x18000b2e0  movzx   ebx, ax
0x18000b2e3  or      ebx, 80070000h
0x18000b2e9  test    ebx, ebx
0x18000b2eb  js      short loc_18000B26D
0x18000b2ed  jmp     loc_18000B164
0x18000b2f2  mov     rcx, [rcx+10h]
0x18000b2f6  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000b2fd  mov     edx, 0B7h
0x18000b302  call    WPP_SF_
0x18000b307  jmp     loc_18000B19C
0x18000b30c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b313  cmp     rcx, r12
0x18000b316  jz      loc_18000B208
0x18000b31c  test    byte ptr [rcx+1Ch], 1
0x18000b320  jz      loc_18000B208
0x18000b326  mov     rcx, [rcx+10h]
0x18000b32a  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000b331  mov     edx, 0B8h
0x18000b336  mov     r9d, ebx
0x18000b339  call    WPP_SF_d
0x18000b33e  jmp     loc_18000B208
```
