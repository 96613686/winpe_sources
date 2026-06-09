# FWSetFirewallRule

- ea: `0x180014690`
- end: `0x180014944`
- name: `FWSetFirewallRule`
- size: `692`
- prototype: `__int64 __fastcall(unsigned __int16 *, _OWORD *Src)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180003b4c`
- `0x180014368`
- `0x180015eb0`
- `0x18003063c`
- `0x180042b70`
- `0x180044eb0`

## callees

- `0x180005954`
- `0x180014690`
- `0x18001494c`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800146df`
- `ntdll!EtwEventWrite` at `0x1800148bb`
- `ntdll!EtwEventWrite` at `0x1800146df`
- `ntdll!EtwEventWrite` at `0x1800148bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800146fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800146fc`

## pseudocode

```c
__int64 __fastcall FWSetFirewallRule(unsigned __int16 *a1, _OWORD *Src)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 v7[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v8[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int (__fastcall **v9)(void *, void *, void *, enum _tag_FW_RULE_STATUS *); // [rsp+58h] [rbp-A8h]
  unsigned int (__fastcall *v10)(void *, void *, void *, enum _tag_FW_RULE_STATUS *); // [rsp+60h] [rbp-A0h] BYREF
  __int16 v11; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall *v12)(); // [rsp+70h] [rbp-90h]
  __int16 v13; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v14)(); // [rsp+80h] [rbp-80h]
  __int16 v15; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v16)(); // [rsp+90h] [rbp-70h]
  __int16 v17; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v18)(); // [rsp+A0h] [rbp-60h]
  __int16 v19; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v20)(); // [rsp+B0h] [rbp-50h]
  __int16 v21; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v22)(); // [rsp+C0h] [rbp-40h]
  __int16 v23; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v24)(); // [rsp+D0h] [rbp-30h]
  __int16 v25; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v26)(); // [rsp+E0h] [rbp-20h]
  __int16 v27; // [rsp+E8h] [rbp-18h]
  unsigned int (__fastcall *v28)(void *, void *, void *, enum _tag_FW_RULE_STATUS *); // [rsp+F0h] [rbp-10h] BYREF
  __int16 v29; // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v30)(); // [rsp+100h] [rbp+0h]
  __int16 v31; // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v32)(); // [rsp+110h] [rbp+10h]
  __int16 v33; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v34)(); // [rsp+120h] [rbp+20h]
  __int16 v35; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v36)(); // [rsp+130h] [rbp+30h]
  __int16 v37; // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v38)(); // [rsp+140h] [rbp+40h]
  __int16 v39; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v40)(); // [rsp+150h] [rbp+50h]
  __int16 v41; // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v42)(); // [rsp+160h] [rbp+60h]
  __int16 v43; // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v44)(); // [rsp+170h] [rbp+70h]
  __int16 v45; // [rsp+178h] [rbp+78h]

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_SetFirewallRule, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v10 = Int_RPC_FWSetFirewallRule2_0;
  v11 = 512;
  v12 = RPC_FWSetFirewallRule2_10;
  v17 = 536;
  v27 = 545;
  v14 = RPC_FWSetFirewallRule2_20;
  v23 = 539;
  v16 = RPC_FWSetFirewallRule2_24;
  v25 = 543;
  v18 = RPC_FWSetFirewallRule2_25;
  v41 = 539;
  v20 = RPC_FWSetFirewallRule2_26;
  v43 = 543;
  v22 = RPC_FWSetFirewallRule2_27;
  v45 = 545;
  v24 = RPC_FWSetFirewallRule2_31;
  v13 = 522;
  v26 = RPC_FWSetFirewallRule2_33;
  v15 = 532;
  v9 = &v10;
  v19 = 537;
  v28 = Int_RRPC_FWSetFirewallRule2_0;
  v21 = 538;
  v30 = RRPC_FWSetFirewallRule2_10;
  v32 = RRPC_FWSetFirewallRule2_20;
  v34 = RRPC_FWSetFirewallRule2_24;
  v36 = RRPC_FWSetFirewallRule2_25;
  v38 = RRPC_FWSetFirewallRule2_26;
  v40 = RRPC_FWSetFirewallRule2_27;
  v42 = RRPC_FWSetFirewallRule2_31;
  v44 = RRPC_FWSetFirewallRule2_33;
  v7[1] = (__int64)&v28;
  *(_QWORD *)v8 = 9;
  v29 = 512;
  v31 = 522;
  v33 = 532;
  v35 = 536;
  v37 = 537;
  v39 = 538;
  v7[0] = 9;
  v4 = Int_FWAddOrSetObject(0, 0, (__int64 (__fastcall *)(_QWORD, __int128 *))FWVerifyFirewallRule, v8, v7, a1, Src);
  v5 = v4;
  if ( v4 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_SetFirewallRule, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x180014690  mov     [rsp-8+arg_10], rbx
0x180014695  push    rbp
0x180014696  push    rsi
0x180014697  push    rdi
0x180014698  push    r12
0x18001469a  push    r13
0x18001469c  push    r14
0x18001469e  push    r15
0x1800146a0  lea     rbp, [rsp-90h]
0x1800146a8  sub     rsp, 190h
0x1800146af  mov     rax, cs:__security_cookie
0x1800146b6  xor     rax, rsp
0x1800146b9  mov     [rbp+0C0h+var_40], rax
0x1800146c0  mov     rbx, rcx
0x1800146c3  mov     rdi, rdx
0x1800146c6  mov     rcx, cs:g_Provider
0x1800146cd  test    rcx, rcx
0x1800146d0  jz      short loc_1800146E5
0x1800146d2  xor     r9d, r9d
0x1800146d5  lea     rdx, MPS_CLNT_API_Enter_SetFirewallRule
0x1800146dc  xor     r8d, r8d
0x1800146df  call    cs:__imp_EtwEventWrite
0x1800146e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146ec  lea     r13, WPP_GLOBAL_Control
0x1800146f3  cmp     rcx, r13
0x1800146f6  jnz     loc_1800148ED
0x1800146fc  call    cs:__imp_GetTickCount64
0x180014702  mov     r12d, 200h
0x180014708  mov     [rsp+1C0h+Src], rdi; Src
0x18001470d  lea     rax, ?Int_RPC_FWSetFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RPC_FWSetFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x180014714  mov     [rsp+1C0h+var_198], rbx; __int64
0x180014719  mov     [rsp+1C0h+var_160], rax
0x18001471e  xor     ecx, ecx; int
0x180014720  lea     rax, RPC_FWSetFirewallRule2_10
0x180014727  mov     [rsp+1C0h+var_158], r12w
0x18001472d  mov     [rsp+1C0h+var_150], rax
0x180014732  lea     esi, [r12+18h]
0x180014737  lea     edx, [rsi+9]
0x18001473a  mov     [rbp+0C0h+var_128], si
0x18001473e  lea     rax, RPC_FWSetFirewallRule2_20
0x180014745  mov     [rbp+0C0h+var_D8], dx
0x180014749  mov     [rbp+0C0h+var_140], rax
0x18001474d  lea     r9d, [r12+1Bh]
0x180014752  lea     rax, RPC_FWSetFirewallRule2_24
0x180014759  mov     [rbp+0C0h+var_F8], r9w
0x18001475e  mov     [rbp+0C0h+var_130], rax
0x180014762  lea     r8d, [r12+1Fh]
0x180014767  lea     rax, RPC_FWSetFirewallRule2_25
0x18001476e  mov     [rbp+0C0h+var_E8], r8w
0x180014773  mov     [rbp+0C0h+var_120], rax
0x180014777  lea     r11d, [r12+19h]
0x18001477c  lea     rax, RPC_FWSetFirewallRule2_26
0x180014783  mov     [rbp+0C0h+var_68], r9w
0x180014788  mov     [rbp+0C0h+var_110], rax
0x18001478c  lea     r10d, [r12+1Ah]
0x180014791  lea     rax, RPC_FWSetFirewallRule2_27
0x180014798  mov     [rbp+0C0h+var_58], r8w
0x18001479d  mov     [rbp+0C0h+var_100], rax
0x1800147a1  lea     r15d, [r12+0Ah]
0x1800147a6  lea     rax, RPC_FWSetFirewallRule2_31
0x1800147ad  mov     [rbp+0C0h+var_48], dx
0x1800147b1  mov     [rbp+0C0h+var_F0], rax
0x1800147b5  lea     r14d, [r12+14h]
0x1800147ba  lea     rax, RPC_FWSetFirewallRule2_33
0x1800147c1  mov     [rsp+1C0h+var_148], r15w
0x1800147c7  mov     [rbp+0C0h+var_E0], rax
0x1800147cb  lea     r9, [rsp+1C0h+var_170]; int
0x1800147d0  lea     rax, [rsp+1C0h+var_160]
0x1800147d5  mov     [rbp+0C0h+var_138], r14w
0x1800147da  mov     [rsp+1C0h+var_168], rax
0x1800147df  lea     r8, FWVerifyFirewallRule; int
0x1800147e6  lea     rax, ?Int_RRPC_FWSetFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RRPC_FWSetFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x1800147ed  mov     [rbp+0C0h+var_118], r11w
0x1800147f2  mov     [rbp+0C0h+var_D0], rax
0x1800147f6  xor     edx, edx; int
0x1800147f8  lea     rax, RRPC_FWSetFirewallRule2_10
0x1800147ff  mov     [rbp+0C0h+var_108], r10w
0x180014804  mov     [rbp+0C0h+var_C0], rax
0x180014808  lea     rax, RRPC_FWSetFirewallRule2_20
0x18001480f  mov     [rbp+0C0h+var_B0], rax
0x180014813  lea     rax, RRPC_FWSetFirewallRule2_24
0x18001481a  mov     [rbp+0C0h+var_A0], rax
0x18001481e  lea     rax, RRPC_FWSetFirewallRule2_25
0x180014825  mov     [rbp+0C0h+var_90], rax
0x180014829  lea     rax, RRPC_FWSetFirewallRule2_26
0x180014830  mov     [rbp+0C0h+var_80], rax
0x180014834  lea     rax, RRPC_FWSetFirewallRule2_27
0x18001483b  mov     [rbp+0C0h+var_70], rax
0x18001483f  lea     rax, RRPC_FWSetFirewallRule2_31
0x180014846  mov     [rbp+0C0h+var_60], rax
0x18001484a  lea     rax, RRPC_FWSetFirewallRule2_33
0x180014851  mov     [rbp+0C0h+var_50], rax
0x180014855  lea     rax, [rbp+0C0h+var_D0]
0x180014859  mov     [rsp+1C0h+var_178], rax
0x18001485e  lea     rax, [rsp+1C0h+var_180]
0x180014863  mov     [rsp+1C0h+var_1A0], rax; __int64
0x180014868  mov     qword ptr [rsp+1C0h+var_170], 9
0x180014871  mov     [rbp+0C0h+var_C8], r12w
0x180014876  mov     [rbp+0C0h+var_B8], r15w
0x18001487b  mov     [rbp+0C0h+var_A8], r14w
0x180014880  mov     [rbp+0C0h+var_98], si
0x180014884  mov     [rbp+0C0h+var_88], r11w
0x180014889  mov     [rbp+0C0h+var_78], r10w
0x18001488e  mov     [rsp+1C0h+var_180], 9
0x180014897  call    Int_FWAddOrSetObject
0x18001489c  mov     ebx, eax
0x18001489e  test    eax, eax
0x1800148a0  jnz     short loc_180014911
0x1800148a2  mov     rcx, cs:g_Provider
0x1800148a9  test    rcx, rcx
0x1800148ac  jz      short loc_1800148C1
0x1800148ae  xor     r9d, r9d
0x1800148b1  lea     rdx, MPS_CLNT_API_Exit_SetFirewallRule
0x1800148b8  xor     r8d, r8d
0x1800148bb  call    cs:__imp_EtwEventWrite
0x1800148c1  mov     eax, ebx
0x1800148c3  mov     rcx, [rbp+0C0h+var_40]
0x1800148ca  xor     rcx, rsp; StackCookie
0x1800148cd  call    __security_check_cookie
0x1800148d2  mov     rbx, [rsp+1C0h+arg_10]
0x1800148da  add     rsp, 190h
0x1800148e1  pop     r15
0x1800148e3  pop     r14
0x1800148e5  pop     r13
0x1800148e7  pop     r12
0x1800148e9  pop     rdi
0x1800148ea  pop     rsi
0x1800148eb  pop     rbp
0x1800148ec  retn
0x1800148ed  test    byte ptr [rcx+1Ch], 8
0x1800148f1  jz      loc_1800146FC
0x1800148f7  mov     rcx, [rcx+10h]
0x1800148fb  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180014902  mov     edx, 5Bh ; '['
0x180014907  call    WPP_SF_
0x18001490c  jmp     loc_1800146FC
0x180014911  mov     rcx, cs:WPP_GLOBAL_Control
0x180014918  cmp     rcx, r13
0x18001491b  jz      short loc_1800148A2
0x18001491d  test    byte ptr [rcx+1Ch], 1
0x180014921  jz      loc_1800148A2
0x180014927  mov     rcx, [rcx+10h]
0x18001492b  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180014932  mov     edx, 5Ch ; '\'
0x180014937  mov     r9d, ebx
0x18001493a  call    WPP_SF_d
0x18001493f  jmp     loc_1800148A2
```
