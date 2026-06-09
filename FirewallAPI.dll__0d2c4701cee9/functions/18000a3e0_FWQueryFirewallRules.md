# FWQueryFirewallRules

- ea: `0x18000a3e0`
- end: `0x18000a526`
- name: `FWQueryFirewallRules`
- size: `326`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009ed0`
- `0x1800191e0`
- `0x18001d578`

## callees

- `0x180005e0c`
- `0x18000a3e0`
- `0x18000a530`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000a41b`
- `ntdll!EtwEventWrite` at `0x18000a4c4`
- `ntdll!EtwEventWrite` at `0x18000a41b`
- `ntdll!EtwEventWrite` at `0x18000a4c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a444`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000a444`

## pseudocode

```c
__int64 __fastcall FWQueryFirewallRules(__int64 a1, __int64 a2, __int16 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v9 = Int_FWQueryObject(
         0,
         (unsigned int)FWVerifyFirewallRuleQuery,
         (unsigned int)RPC_FWQueryFirewallRules,
         (unsigned int)RRPC_FWQueryFirewallRules,
         (__int64)Int_RPC_FWEnumFirewallRules2_0,
         (__int64)Int_RRPC_FWEnumFirewallRules2_0,
         a1,
         a2,
         a3,
         a4,
         a5,
         0);
  v10 = v9;
  if ( v9 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v9);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x18000a3e0  push    rbx
0x18000a3e2  push    rbp
0x18000a3e3  push    rsi
0x18000a3e4  push    rdi
0x18000a3e5  push    r14
0x18000a3e7  push    r15
0x18000a3e9  sub     rsp, 68h
0x18000a3ed  mov     r14, [rsp+98h+arg_20]
0x18000a3f5  mov     rbx, rcx
0x18000a3f8  mov     rcx, cs:g_Provider
0x18000a3ff  mov     rbp, r9
0x18000a402  movzx   esi, r8w
0x18000a406  mov     rdi, rdx
0x18000a409  test    rcx, rcx
0x18000a40c  jz      short loc_18000A427
0x18000a40e  xor     r9d, r9d
0x18000a411  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x18000a418  xor     r8d, r8d
0x18000a41b  call    cs:__imp_EtwEventWrite
0x18000a422  nop     dword ptr [rax+rax+00h]
0x18000a427  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a42e  lea     r15, WPP_GLOBAL_Control
0x18000a435  cmp     rcx, r15
0x18000a438  jz      short loc_18000A444
0x18000a43a  test    byte ptr [rcx+1Ch], 8
0x18000a43e  jnz     loc_18000A4E0
0x18000a444  call    cs:__imp_GetTickCount64
0x18000a44b  nop     dword ptr [rax+rax+00h]
0x18000a450  mov     [rsp+98h+var_40], 0
0x18000a458  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000a45f  mov     [rsp+98h+var_48], r14
0x18000a464  lea     r9, RRPC_FWQueryFirewallRules
0x18000a46b  mov     [rsp+98h+var_50], rbp
0x18000a470  lea     r8, RPC_FWQueryFirewallRules
0x18000a477  mov     [rsp+98h+var_58], si
0x18000a47c  lea     rdx, FWVerifyFirewallRuleQuery
0x18000a483  mov     [rsp+98h+var_60], rdi
0x18000a488  xor     ecx, ecx
0x18000a48a  mov     [rsp+98h+var_68], rbx
0x18000a48f  mov     [rsp+98h+var_70], rax
0x18000a494  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000a49b  mov     [rsp+98h+var_78], rax
0x18000a4a0  call    Int_FWQueryObject
0x18000a4a5  mov     ebx, eax
0x18000a4a7  test    eax, eax
0x18000a4a9  jnz     short loc_18000A4FA
0x18000a4ab  mov     rcx, cs:g_Provider
0x18000a4b2  test    rcx, rcx
0x18000a4b5  jz      short loc_18000A4D0
0x18000a4b7  xor     r9d, r9d
0x18000a4ba  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x18000a4c1  xor     r8d, r8d
0x18000a4c4  call    cs:__imp_EtwEventWrite
0x18000a4cb  nop     dword ptr [rax+rax+00h]
0x18000a4d0  mov     eax, ebx
0x18000a4d2  add     rsp, 68h
0x18000a4d6  pop     r15
0x18000a4d8  pop     r14
0x18000a4da  pop     rdi
0x18000a4db  pop     rsi
0x18000a4dc  pop     rbp
0x18000a4dd  pop     rbx
0x18000a4de  retn
0x18000a4e0  mov     rcx, [rcx+10h]
0x18000a4e4  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000a4eb  mov     edx, 0B6h
0x18000a4f0  call    WPP_SF_
0x18000a4f5  jmp     loc_18000A444
0x18000a4fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a501  cmp     rcx, r15
0x18000a504  jz      short loc_18000A4AB
0x18000a506  test    byte ptr [rcx+1Ch], 1
0x18000a50a  jz      short loc_18000A4AB
0x18000a50c  mov     rcx, [rcx+10h]
0x18000a510  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000a517  mov     edx, 0B7h
0x18000a51c  mov     r9d, ebx
0x18000a51f  call    WPP_SF_d
0x18000a524  jmp     short loc_18000A4AB
```
