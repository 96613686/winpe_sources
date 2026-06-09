# FWAddFirewallRule

- ea: `0x180014110`
- end: `0x1800143d2`
- name: `FWAddFirewallRule`
- size: `706`
- prototype: `__int64 __fastcall(__int64, void *Src)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800143d8`
- `0x180032840`
- `0x180045344`
- `0x1800484dc`
- `0x18005c844`

## callees

- `0x180005e0c`
- `0x180014110`
- `0x1800149f4`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001415f`
- `ntdll!EtwEventWrite` at `0x180014350`
- `ntdll!EtwEventWrite` at `0x18001415f`
- `ntdll!EtwEventWrite` at `0x180014350`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180014188`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180014188`

## pseudocode

```c
__int64 __fastcall FWAddFirewallRule(unsigned __int16 *a1, _OWORD *Src)
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
  v4 = Int_FWAddOrSetObject(0, 1, (__int64 (__fastcall *)(_QWORD, __int128 *))FWVerifyFirewallRule, v8, v7, a1, Src);
  v5 = v4;
  if ( v4 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_AddFirewallRule, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x180014110  mov     [rsp-8+arg_10], rbx
0x180014115  push    rbp
0x180014116  push    rsi
0x180014117  push    rdi
0x180014118  push    r12
0x18001411a  push    r13
0x18001411c  push    r14
0x18001411e  push    r15
0x180014120  lea     rbp, [rsp-90h]
0x180014128  sub     rsp, 190h
0x18001412f  mov     rax, cs:__security_cookie
0x180014136  xor     rax, rsp
0x180014139  mov     [rbp+0C0h+var_40], rax
0x180014140  mov     rbx, rcx
0x180014143  mov     rdi, rdx
0x180014146  mov     rcx, cs:g_Provider
0x18001414d  test    rcx, rcx
0x180014150  jz      short loc_18001416B
0x180014152  xor     r9d, r9d
0x180014155  lea     rdx, MPS_CLNT_API_Enter_AddFirewallRule
0x18001415c  xor     r8d, r8d
0x18001415f  call    cs:__imp_EtwEventWrite
0x180014166  nop     dword ptr [rax+rax+00h]
0x18001416b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014172  lea     r13, WPP_GLOBAL_Control
0x180014179  cmp     rcx, r13
0x18001417c  jz      short loc_180014188
0x18001417e  test    byte ptr [rcx+1Ch], 8
0x180014182  jnz     loc_180014389
0x180014188  call    cs:__imp_GetTickCount64
0x18001418f  nop     dword ptr [rax+rax+00h]
0x180014194  mov     r12d, 200h
0x18001419a  mov     [rsp+1C0h+Src], rdi; Src
0x18001419f  lea     rax, ?Int_RPC_FWAddFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RPC_FWAddFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x1800141a6  mov     [rsp+1C0h+var_198], rbx; __int64
0x1800141ab  mov     [rsp+1C0h+var_160], rax
0x1800141b0  xor     ecx, ecx; int
0x1800141b2  lea     rax, RPC_FWAddFirewallRule2_10
0x1800141b9  mov     [rsp+1C0h+var_158], r12w
0x1800141bf  mov     [rsp+1C0h+var_150], rax
0x1800141c4  lea     esi, [r12+18h]
0x1800141c9  lea     edx, [rsi+9]
0x1800141cc  mov     [rbp+0C0h+var_128], si
0x1800141d0  lea     rax, RPC_FWAddFirewallRule2_20
0x1800141d7  mov     [rbp+0C0h+var_D8], dx
0x1800141db  mov     [rbp+0C0h+var_140], rax
0x1800141df  lea     r9d, [r12+1Bh]
0x1800141e4  lea     rax, RPC_FWAddFirewallRule2_24
0x1800141eb  mov     [rbp+0C0h+var_F8], r9w
0x1800141f0  mov     [rbp+0C0h+var_130], rax
0x1800141f4  lea     r8d, [r12+1Fh]
0x1800141f9  lea     rax, RPC_FWAddFirewallRule2_25
0x180014200  mov     [rbp+0C0h+var_E8], r8w
0x180014205  mov     [rbp+0C0h+var_120], rax
0x180014209  lea     r11d, [r12+19h]
0x18001420e  lea     rax, RPC_FWAddFirewallRule2_26
0x180014215  mov     [rbp+0C0h+var_68], r9w
0x18001421a  mov     [rbp+0C0h+var_110], rax
0x18001421e  lea     r10d, [r12+1Ah]
0x180014223  lea     rax, RPC_FWAddFirewallRule2_27
0x18001422a  mov     [rbp+0C0h+var_58], r8w
0x18001422f  mov     [rbp+0C0h+var_100], rax
0x180014233  lea     r15d, [r12+0Ah]
0x180014238  lea     rax, RPC_FWAddFirewallRule2_31
0x18001423f  mov     [rbp+0C0h+var_48], dx
0x180014243  mov     [rbp+0C0h+var_F0], rax
0x180014247  lea     r14d, [r12+14h]
0x18001424c  lea     rax, RPC_FWAddFirewallRule2_33
0x180014253  mov     [rsp+1C0h+var_148], r15w
0x180014259  mov     [rbp+0C0h+var_E0], rax
0x18001425d  lea     r9, [rsp+1C0h+var_170]; int
0x180014262  lea     rax, [rsp+1C0h+var_160]
0x180014267  mov     [rbp+0C0h+var_138], r14w
0x18001426c  mov     [rsp+1C0h+var_168], rax
0x180014271  lea     r8, FWVerifyFirewallRule; int
0x180014278  lea     rax, ?Int_RRPC_FWAddFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RRPC_FWAddFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x18001427f  mov     [rbp+0C0h+var_118], r11w
0x180014284  mov     [rbp+0C0h+var_D0], rax
0x180014288  mov     edx, 1; int
0x18001428d  lea     rax, RRPC_FWAddFirewallRule2_10
0x180014294  mov     [rbp+0C0h+var_108], r10w
0x180014299  mov     [rbp+0C0h+var_C0], rax
0x18001429d  lea     rax, RRPC_FWAddFirewallRule2_20
0x1800142a4  mov     [rbp+0C0h+var_B0], rax
0x1800142a8  lea     rax, RRPC_FWAddFirewallRule2_24
0x1800142af  mov     [rbp+0C0h+var_A0], rax
0x1800142b3  lea     rax, RRPC_FWAddFirewallRule2_25
0x1800142ba  mov     [rbp+0C0h+var_90], rax
0x1800142be  lea     rax, RRPC_FWAddFirewallRule2_26
0x1800142c5  mov     [rbp+0C0h+var_80], rax
0x1800142c9  lea     rax, RRPC_FWAddFirewallRule2_27
0x1800142d0  mov     [rbp+0C0h+var_70], rax
0x1800142d4  lea     rax, RRPC_FWAddFirewallRule2_31
0x1800142db  mov     [rbp+0C0h+var_60], rax
0x1800142df  lea     rax, RRPC_FWAddFirewallRule2_33
0x1800142e6  mov     [rbp+0C0h+var_50], rax
0x1800142ea  lea     rax, [rbp+0C0h+var_D0]
0x1800142ee  mov     [rsp+1C0h+var_178], rax
0x1800142f3  lea     rax, [rsp+1C0h+var_180]
0x1800142f8  mov     [rsp+1C0h+var_1A0], rax; __int64
0x1800142fd  mov     qword ptr [rsp+1C0h+var_170], 9
0x180014306  mov     [rbp+0C0h+var_C8], r12w
0x18001430b  mov     [rbp+0C0h+var_B8], r15w
0x180014310  mov     [rbp+0C0h+var_A8], r14w
0x180014315  mov     [rbp+0C0h+var_98], si
0x180014319  mov     [rbp+0C0h+var_88], r11w
0x18001431e  mov     [rbp+0C0h+var_78], r10w
0x180014323  mov     [rsp+1C0h+var_180], 9
0x18001432c  call    Int_FWAddOrSetObject
0x180014331  mov     ebx, eax
0x180014333  test    eax, eax
0x180014335  jnz     short loc_1800143A3
0x180014337  mov     rcx, cs:g_Provider
0x18001433e  test    rcx, rcx
0x180014341  jz      short loc_18001435C
0x180014343  xor     r9d, r9d
0x180014346  lea     rdx, MPS_CLNT_API_Exit_AddFirewallRule
0x18001434d  xor     r8d, r8d
0x180014350  call    cs:__imp_EtwEventWrite
0x180014357  nop     dword ptr [rax+rax+00h]
0x18001435c  mov     eax, ebx
0x18001435e  mov     rcx, [rbp+0C0h+var_40]
0x180014365  xor     rcx, rsp; StackCookie
0x180014368  call    __security_check_cookie
0x18001436d  mov     rbx, [rsp+1C0h+arg_10]
0x180014375  add     rsp, 190h
0x18001437c  pop     r15
0x18001437e  pop     r14
0x180014380  pop     r13
0x180014382  pop     r12
0x180014384  pop     rdi
0x180014385  pop     rsi
0x180014386  pop     rbp
0x180014387  retn
0x180014389  mov     rcx, [rcx+10h]
0x18001438d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180014394  mov     edx, 58h ; 'X'
0x180014399  call    WPP_SF_
0x18001439e  jmp     loc_180014188
0x1800143a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143aa  cmp     rcx, r13
0x1800143ad  jz      short loc_180014337
0x1800143af  test    byte ptr [rcx+1Ch], 1
0x1800143b3  jz      short loc_180014337
0x1800143b5  mov     rcx, [rcx+10h]
0x1800143b9  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800143c0  mov     edx, 59h ; 'Y'
0x1800143c5  mov     r9d, ebx
0x1800143c8  call    WPP_SF_d
0x1800143cd  jmp     loc_180014337
```
