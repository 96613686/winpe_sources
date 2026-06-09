# FWAddFirewallRule

- ea: `0x1800140b0`
- end: `0x18001435f`
- name: `FWAddFirewallRule`
- size: `687`
- prototype: `__int64 __fastcall(__int64, void *Src)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180014368`
- `0x18003063c`
- `0x180042004`
- `0x180044eb0`
- `0x1800587a0`

## callees

- `0x180005954`
- `0x1800140b0`
- `0x18001494c`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800140ff`
- `ntdll!EtwEventWrite` at `0x1800142e4`
- `ntdll!EtwEventWrite` at `0x1800140ff`
- `ntdll!EtwEventWrite` at `0x1800142e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180014122`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180014122`

## pseudocode

```c
__int64 __fastcall FWAddFirewallRule(__int64 a1, void *Src)
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
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_AddFirewallRule, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v10 = Int_RPC_FWAddFirewallRule2_0;
  v11 = 512;
  v12 = RPC_FWAddFirewallRule2_10;
  v17 = 536;
  v27 = 545;
  v14 = RPC_FWAddFirewallRule2_20;
  v23 = 539;
  v16 = RPC_FWAddFirewallRule2_24;
  v25 = 543;
  v18 = RPC_FWAddFirewallRule2_25;
  v41 = 539;
  v20 = RPC_FWAddFirewallRule2_26;
  v43 = 543;
  v22 = RPC_FWAddFirewallRule2_27;
  v45 = 545;
  v24 = RPC_FWAddFirewallRule2_31;
  v13 = 522;
  v26 = RPC_FWAddFirewallRule2_33;
  v15 = 532;
  v9 = &v10;
  v19 = 537;
  v28 = Int_RRPC_FWAddFirewallRule2_0;
  v21 = 538;
  v30 = RRPC_FWAddFirewallRule2_10;
  v32 = RRPC_FWAddFirewallRule2_20;
  v34 = RRPC_FWAddFirewallRule2_24;
  v36 = RRPC_FWAddFirewallRule2_25;
  v38 = RRPC_FWAddFirewallRule2_26;
  v40 = RRPC_FWAddFirewallRule2_27;
  v42 = RRPC_FWAddFirewallRule2_31;
  v44 = RRPC_FWAddFirewallRule2_33;
  v7[1] = (__int64)&v28;
  *(_QWORD *)v8 = 9;
  v29 = 512;
  v31 = 522;
  v33 = 532;
  v35 = 536;
  v37 = 537;
  v39 = 538;
  v7[0] = 9;
  v4 = Int_FWAddOrSetObject(0, 1, (int)FWVerifyFirewallRule, (int)v8, (__int64)v7, a1, Src);
  v5 = v4;
  if ( v4 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_AddFirewallRule, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x1800140b0  mov     [rsp-8+arg_10], rbx
0x1800140b5  push    rbp
0x1800140b6  push    rsi
0x1800140b7  push    rdi
0x1800140b8  push    r12
0x1800140ba  push    r13
0x1800140bc  push    r14
0x1800140be  push    r15
0x1800140c0  lea     rbp, [rsp-90h]
0x1800140c8  sub     rsp, 190h
0x1800140cf  mov     rax, cs:__security_cookie
0x1800140d6  xor     rax, rsp
0x1800140d9  mov     [rbp+0C0h+var_40], rax
0x1800140e0  mov     rbx, rcx
0x1800140e3  mov     rdi, rdx
0x1800140e6  mov     rcx, cs:g_Provider
0x1800140ed  test    rcx, rcx
0x1800140f0  jz      short loc_180014105
0x1800140f2  xor     r9d, r9d
0x1800140f5  lea     rdx, MPS_CLNT_API_Enter_AddFirewallRule
0x1800140fc  xor     r8d, r8d
0x1800140ff  call    cs:__imp_EtwEventWrite
0x180014105  mov     rcx, cs:WPP_GLOBAL_Control
0x18001410c  lea     r13, WPP_GLOBAL_Control
0x180014113  cmp     rcx, r13
0x180014116  jz      short loc_180014122
0x180014118  test    byte ptr [rcx+1Ch], 8
0x18001411c  jnz     loc_180014316
0x180014122  call    cs:__imp_GetTickCount64
0x180014128  mov     r12d, 200h
0x18001412e  mov     [rsp+1C0h+Src], rdi; Src
0x180014133  lea     rax, ?Int_RPC_FWAddFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RPC_FWAddFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x18001413a  mov     [rsp+1C0h+var_198], rbx; __int64
0x18001413f  mov     [rsp+1C0h+var_160], rax
0x180014144  xor     ecx, ecx; int
0x180014146  lea     rax, RPC_FWAddFirewallRule2_10
0x18001414d  mov     [rsp+1C0h+var_158], r12w
0x180014153  mov     [rsp+1C0h+var_150], rax
0x180014158  lea     esi, [r12+18h]
0x18001415d  lea     edx, [rsi+9]
0x180014160  mov     [rbp+0C0h+var_128], si
0x180014164  lea     rax, RPC_FWAddFirewallRule2_20
0x18001416b  mov     [rbp+0C0h+var_D8], dx
0x18001416f  mov     [rbp+0C0h+var_140], rax
0x180014173  lea     r9d, [r12+1Bh]
0x180014178  lea     rax, RPC_FWAddFirewallRule2_24
0x18001417f  mov     [rbp+0C0h+var_F8], r9w
0x180014184  mov     [rbp+0C0h+var_130], rax
0x180014188  lea     r8d, [r12+1Fh]
0x18001418d  lea     rax, RPC_FWAddFirewallRule2_25
0x180014194  mov     [rbp+0C0h+var_E8], r8w
0x180014199  mov     [rbp+0C0h+var_120], rax
0x18001419d  lea     r11d, [r12+19h]
0x1800141a2  lea     rax, RPC_FWAddFirewallRule2_26
0x1800141a9  mov     [rbp+0C0h+var_68], r9w
0x1800141ae  mov     [rbp+0C0h+var_110], rax
0x1800141b2  lea     r10d, [r12+1Ah]
0x1800141b7  lea     rax, RPC_FWAddFirewallRule2_27
0x1800141be  mov     [rbp+0C0h+var_58], r8w
0x1800141c3  mov     [rbp+0C0h+var_100], rax
0x1800141c7  lea     r15d, [r12+0Ah]
0x1800141cc  lea     rax, RPC_FWAddFirewallRule2_31
0x1800141d3  mov     [rbp+0C0h+var_48], dx
0x1800141d7  mov     [rbp+0C0h+var_F0], rax
0x1800141db  lea     r14d, [r12+14h]
0x1800141e0  lea     rax, RPC_FWAddFirewallRule2_33
0x1800141e7  mov     [rsp+1C0h+var_148], r15w
0x1800141ed  mov     [rbp+0C0h+var_E0], rax
0x1800141f1  lea     r9, [rsp+1C0h+var_170]; int
0x1800141f6  lea     rax, [rsp+1C0h+var_160]
0x1800141fb  mov     [rbp+0C0h+var_138], r14w
0x180014200  mov     [rsp+1C0h+var_168], rax
0x180014205  lea     r8, FWVerifyFirewallRule; int
0x18001420c  lea     rax, ?Int_RRPC_FWAddFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RRPC_FWAddFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x180014213  mov     [rbp+0C0h+var_118], r11w
0x180014218  mov     [rbp+0C0h+var_D0], rax
0x18001421c  mov     edx, 1; int
0x180014221  lea     rax, RRPC_FWAddFirewallRule2_10
0x180014228  mov     [rbp+0C0h+var_108], r10w
0x18001422d  mov     [rbp+0C0h+var_C0], rax
0x180014231  lea     rax, RRPC_FWAddFirewallRule2_20
0x180014238  mov     [rbp+0C0h+var_B0], rax
0x18001423c  lea     rax, RRPC_FWAddFirewallRule2_24
0x180014243  mov     [rbp+0C0h+var_A0], rax
0x180014247  lea     rax, RRPC_FWAddFirewallRule2_25
0x18001424e  mov     [rbp+0C0h+var_90], rax
0x180014252  lea     rax, RRPC_FWAddFirewallRule2_26
0x180014259  mov     [rbp+0C0h+var_80], rax
0x18001425d  lea     rax, RRPC_FWAddFirewallRule2_27
0x180014264  mov     [rbp+0C0h+var_70], rax
0x180014268  lea     rax, RRPC_FWAddFirewallRule2_31
0x18001426f  mov     [rbp+0C0h+var_60], rax
0x180014273  lea     rax, RRPC_FWAddFirewallRule2_33
0x18001427a  mov     [rbp+0C0h+var_50], rax
0x18001427e  lea     rax, [rbp+0C0h+var_D0]
0x180014282  mov     [rsp+1C0h+var_178], rax
0x180014287  lea     rax, [rsp+1C0h+var_180]
0x18001428c  mov     [rsp+1C0h+var_1A0], rax; __int64
0x180014291  mov     qword ptr [rsp+1C0h+var_170], 9
0x18001429a  mov     [rbp+0C0h+var_C8], r12w
0x18001429f  mov     [rbp+0C0h+var_B8], r15w
0x1800142a4  mov     [rbp+0C0h+var_A8], r14w
0x1800142a9  mov     [rbp+0C0h+var_98], si
0x1800142ad  mov     [rbp+0C0h+var_88], r11w
0x1800142b2  mov     [rbp+0C0h+var_78], r10w
0x1800142b7  mov     [rsp+1C0h+var_180], 9
0x1800142c0  call    Int_FWAddOrSetObject
0x1800142c5  mov     ebx, eax
0x1800142c7  test    eax, eax
0x1800142c9  jnz     short loc_180014330
0x1800142cb  mov     rcx, cs:g_Provider
0x1800142d2  test    rcx, rcx
0x1800142d5  jz      short loc_1800142EA
0x1800142d7  xor     r9d, r9d
0x1800142da  lea     rdx, MPS_CLNT_API_Exit_AddFirewallRule
0x1800142e1  xor     r8d, r8d
0x1800142e4  call    cs:__imp_EtwEventWrite
0x1800142ea  mov     eax, ebx
0x1800142ec  mov     rcx, [rbp+0C0h+var_40]
0x1800142f3  xor     rcx, rsp; StackCookie
0x1800142f6  call    __security_check_cookie
0x1800142fb  mov     rbx, [rsp+1C0h+arg_10]
0x180014303  add     rsp, 190h
0x18001430a  pop     r15
0x18001430c  pop     r14
0x18001430e  pop     r13
0x180014310  pop     r12
0x180014312  pop     rdi
0x180014313  pop     rsi
0x180014314  pop     rbp
0x180014315  retn
0x180014316  mov     rcx, [rcx+10h]
0x18001431a  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180014321  mov     edx, 59h ; 'Y'
0x180014326  call    WPP_SF_
0x18001432b  jmp     loc_180014122
0x180014330  mov     rcx, cs:WPP_GLOBAL_Control
0x180014337  cmp     rcx, r13
0x18001433a  jz      short loc_1800142CB
0x18001433c  test    byte ptr [rcx+1Ch], 1
0x180014340  jz      short loc_1800142CB
0x180014342  mov     rcx, [rcx+10h]
0x180014346  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001434d  mov     edx, 5Ah ; 'Z'
0x180014352  mov     r9d, ebx
0x180014355  call    WPP_SF_d
0x18001435a  jmp     loc_1800142CB
```
