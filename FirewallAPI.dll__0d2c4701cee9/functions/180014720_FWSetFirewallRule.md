# FWSetFirewallRule

- ea: `0x180014720`
- end: `0x1800149eb`
- name: `FWSetFirewallRule`
- size: `715`
- prototype: `__int64 __fastcall(__int64, void *Src)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180003e5c`
- `0x1800143d8`
- `0x180015fb0`
- `0x180032840`
- `0x180045f40`
- `0x1800484dc`

## callees

- `0x180005e0c`
- `0x180014720`
- `0x1800149f4`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001476f`
- `ntdll!EtwEventWrite` at `0x180014957`
- `ntdll!EtwEventWrite` at `0x18001476f`
- `ntdll!EtwEventWrite` at `0x180014957`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180014792`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180014792`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_SetFirewallRule, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x180014720  mov     [rsp-8+arg_10], rbx
0x180014725  push    rbp
0x180014726  push    rsi
0x180014727  push    rdi
0x180014728  push    r12
0x18001472a  push    r13
0x18001472c  push    r14
0x18001472e  push    r15
0x180014730  lea     rbp, [rsp-90h]
0x180014738  sub     rsp, 190h
0x18001473f  mov     rax, cs:__security_cookie
0x180014746  xor     rax, rsp
0x180014749  mov     [rbp+0C0h+var_40], rax
0x180014750  mov     rbx, rcx
0x180014753  mov     rdi, rdx
0x180014756  mov     rcx, cs:g_Provider
0x18001475d  test    rcx, rcx
0x180014760  jz      short loc_18001477B
0x180014762  xor     r9d, r9d
0x180014765  lea     rdx, MPS_CLNT_API_Enter_SetFirewallRule
0x18001476c  xor     r8d, r8d
0x18001476f  call    cs:__imp_EtwEventWrite
0x180014776  nop     dword ptr [rax+rax+00h]
0x18001477b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014782  lea     r13, WPP_GLOBAL_Control
0x180014789  cmp     rcx, r13
0x18001478c  jnz     loc_180014990
0x180014792  call    cs:__imp_GetTickCount64
0x180014799  nop     dword ptr [rax+rax+00h]
0x18001479e  mov     r12d, 200h
0x1800147a4  mov     [rsp+1C0h+Src], rdi; Src
0x1800147a9  lea     rax, ?Int_RPC_FWSetFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RPC_FWSetFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x1800147b0  mov     [rsp+1C0h+var_198], rbx; __int64
0x1800147b5  mov     [rsp+1C0h+var_160], rax
0x1800147ba  xor     ecx, ecx; int
0x1800147bc  lea     rax, RPC_FWSetFirewallRule2_10
0x1800147c3  mov     [rsp+1C0h+var_158], r12w
0x1800147c9  mov     [rsp+1C0h+var_150], rax
0x1800147ce  lea     esi, [r12+18h]
0x1800147d3  lea     edx, [rsi+9]
0x1800147d6  mov     [rbp+0C0h+var_128], si
0x1800147da  lea     rax, RPC_FWSetFirewallRule2_20
0x1800147e1  mov     [rbp+0C0h+var_D8], dx
0x1800147e5  mov     [rbp+0C0h+var_140], rax
0x1800147e9  lea     r9d, [r12+1Bh]
0x1800147ee  lea     rax, RPC_FWSetFirewallRule2_24
0x1800147f5  mov     [rbp+0C0h+var_F8], r9w
0x1800147fa  mov     [rbp+0C0h+var_130], rax
0x1800147fe  lea     r8d, [r12+1Fh]
0x180014803  lea     rax, RPC_FWSetFirewallRule2_25
0x18001480a  mov     [rbp+0C0h+var_E8], r8w
0x18001480f  mov     [rbp+0C0h+var_120], rax
0x180014813  lea     r11d, [r12+19h]
0x180014818  lea     rax, RPC_FWSetFirewallRule2_26
0x18001481f  mov     [rbp+0C0h+var_68], r9w
0x180014824  mov     [rbp+0C0h+var_110], rax
0x180014828  lea     r10d, [r12+1Ah]
0x18001482d  lea     rax, RPC_FWSetFirewallRule2_27
0x180014834  mov     [rbp+0C0h+var_58], r8w
0x180014839  mov     [rbp+0C0h+var_100], rax
0x18001483d  lea     r15d, [r12+0Ah]
0x180014842  lea     rax, RPC_FWSetFirewallRule2_31
0x180014849  mov     [rbp+0C0h+var_48], dx
0x18001484d  mov     [rbp+0C0h+var_F0], rax
0x180014851  lea     r14d, [r12+14h]
0x180014856  lea     rax, RPC_FWSetFirewallRule2_33
0x18001485d  mov     [rsp+1C0h+var_148], r15w
0x180014863  mov     [rbp+0C0h+var_E0], rax
0x180014867  lea     r9, [rsp+1C0h+var_170]; int
0x18001486c  lea     rax, [rsp+1C0h+var_160]
0x180014871  mov     [rbp+0C0h+var_138], r14w
0x180014876  mov     [rsp+1C0h+var_168], rax
0x18001487b  lea     r8, FWVerifyFirewallRule; int
0x180014882  lea     rax, ?Int_RRPC_FWSetFirewallRule2_0@@YAKPEAX00PEAW4_tag_FW_RULE_STATUS@@@Z; Int_RRPC_FWSetFirewallRule2_0(void *,void *,void *,_tag_FW_RULE_STATUS *)
0x180014889  mov     [rbp+0C0h+var_118], r11w
0x18001488e  mov     [rbp+0C0h+var_D0], rax
0x180014892  xor     edx, edx; int
0x180014894  lea     rax, RRPC_FWSetFirewallRule2_10
0x18001489b  mov     [rbp+0C0h+var_108], r10w
0x1800148a0  mov     [rbp+0C0h+var_C0], rax
0x1800148a4  lea     rax, RRPC_FWSetFirewallRule2_20
0x1800148ab  mov     [rbp+0C0h+var_B0], rax
0x1800148af  lea     rax, RRPC_FWSetFirewallRule2_24
0x1800148b6  mov     [rbp+0C0h+var_A0], rax
0x1800148ba  lea     rax, RRPC_FWSetFirewallRule2_25
0x1800148c1  mov     [rbp+0C0h+var_90], rax
0x1800148c5  lea     rax, RRPC_FWSetFirewallRule2_26
0x1800148cc  mov     [rbp+0C0h+var_80], rax
0x1800148d0  lea     rax, RRPC_FWSetFirewallRule2_27
0x1800148d7  mov     [rbp+0C0h+var_70], rax
0x1800148db  lea     rax, RRPC_FWSetFirewallRule2_31
0x1800148e2  mov     [rbp+0C0h+var_60], rax
0x1800148e6  lea     rax, RRPC_FWSetFirewallRule2_33
0x1800148ed  mov     [rbp+0C0h+var_50], rax
0x1800148f1  lea     rax, [rbp+0C0h+var_D0]
0x1800148f5  mov     [rsp+1C0h+var_178], rax
0x1800148fa  lea     rax, [rsp+1C0h+var_180]
0x1800148ff  mov     [rsp+1C0h+var_1A0], rax; __int64
0x180014904  mov     qword ptr [rsp+1C0h+var_170], 9
0x18001490d  mov     [rbp+0C0h+var_C8], r12w
0x180014912  mov     [rbp+0C0h+var_B8], r15w
0x180014917  mov     [rbp+0C0h+var_A8], r14w
0x18001491c  mov     [rbp+0C0h+var_98], si
0x180014920  mov     [rbp+0C0h+var_88], r11w
0x180014925  mov     [rbp+0C0h+var_78], r10w
0x18001492a  mov     [rsp+1C0h+var_180], 9
0x180014933  call    Int_FWAddOrSetObject
0x180014938  mov     ebx, eax
0x18001493a  test    eax, eax
0x18001493c  jnz     short loc_1800149B4
0x18001493e  mov     rcx, cs:g_Provider
0x180014945  test    rcx, rcx
0x180014948  jz      short loc_180014963
0x18001494a  xor     r9d, r9d
0x18001494d  lea     rdx, MPS_CLNT_API_Exit_SetFirewallRule
0x180014954  xor     r8d, r8d
0x180014957  call    cs:__imp_EtwEventWrite
0x18001495e  nop     dword ptr [rax+rax+00h]
0x180014963  mov     eax, ebx
0x180014965  mov     rcx, [rbp+0C0h+var_40]
0x18001496c  xor     rcx, rsp; StackCookie
0x18001496f  call    __security_check_cookie
0x180014974  mov     rbx, [rsp+1C0h+arg_10]
0x18001497c  add     rsp, 190h
0x180014983  pop     r15
0x180014985  pop     r14
0x180014987  pop     r13
0x180014989  pop     r12
0x18001498b  pop     rdi
0x18001498c  pop     rsi
0x18001498d  pop     rbp
0x18001498e  retn
0x180014990  test    byte ptr [rcx+1Ch], 8
0x180014994  jz      loc_180014792
0x18001499a  mov     rcx, [rcx+10h]
0x18001499e  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800149a5  mov     edx, 5Ah ; 'Z'
0x1800149aa  call    WPP_SF_
0x1800149af  jmp     loc_180014792
0x1800149b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149bb  cmp     rcx, r13
0x1800149be  jz      loc_18001493E
0x1800149c4  test    byte ptr [rcx+1Ch], 1
0x1800149c8  jz      loc_18001493E
0x1800149ce  mov     rcx, [rcx+10h]
0x1800149d2  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800149d9  mov     edx, 5Bh ; '['
0x1800149de  mov     r9d, ebx
0x1800149e1  call    WPP_SF_d
0x1800149e6  jmp     loc_18001493E
```
