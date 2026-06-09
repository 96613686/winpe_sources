# FWQueryFirewallRules

- ea: `0x180009e70`
- end: `0x180009fa3`
- name: `FWQueryFirewallRules`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180018ef0`

## callees

- `0x180005954`
- `0x180009e70`
- `0x180009fb0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180009eab`
- `ntdll!EtwEventWrite` at `0x180009f48`
- `ntdll!EtwEventWrite` at `0x180009eab`
- `ntdll!EtwEventWrite` at `0x180009f48`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009ece`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009ece`

## pseudocode

```c
__int64 __fastcall FWQueryFirewallRules(__int64 a1, __int64 a2, __int16 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v9);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x180009e70  push    rbx
0x180009e72  push    rbp
0x180009e73  push    rsi
0x180009e74  push    rdi
0x180009e75  push    r14
0x180009e77  push    r15
0x180009e79  sub     rsp, 68h
0x180009e7d  mov     r14, [rsp+98h+arg_20]
0x180009e85  mov     rbx, rcx
0x180009e88  mov     rcx, cs:g_Provider
0x180009e8f  mov     rbp, r9
0x180009e92  movzx   esi, r8w
0x180009e96  mov     rdi, rdx
0x180009e99  test    rcx, rcx
0x180009e9c  jz      short loc_180009EB1
0x180009e9e  xor     r9d, r9d
0x180009ea1  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x180009ea8  xor     r8d, r8d
0x180009eab  call    cs:__imp_EtwEventWrite
0x180009eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb8  lea     r15, WPP_GLOBAL_Control
0x180009ebf  cmp     rcx, r15
0x180009ec2  jz      short loc_180009ECE
0x180009ec4  test    byte ptr [rcx+1Ch], 8
0x180009ec8  jnz     loc_180009F5D
0x180009ece  call    cs:__imp_GetTickCount64
0x180009ed4  mov     [rsp+98h+var_40], 0
0x180009edc  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180009ee3  mov     [rsp+98h+var_48], r14
0x180009ee8  lea     r9, RRPC_FWQueryFirewallRules
0x180009eef  mov     [rsp+98h+var_50], rbp
0x180009ef4  lea     r8, RPC_FWQueryFirewallRules
0x180009efb  mov     [rsp+98h+var_58], si
0x180009f00  lea     rdx, FWVerifyFirewallRuleQuery
0x180009f07  mov     [rsp+98h+var_60], rdi
0x180009f0c  xor     ecx, ecx
0x180009f0e  mov     [rsp+98h+var_68], rbx
0x180009f13  mov     [rsp+98h+var_70], rax
0x180009f18  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180009f1f  mov     [rsp+98h+var_78], rax
0x180009f24  call    Int_FWQueryObject
0x180009f29  mov     ebx, eax
0x180009f2b  test    eax, eax
0x180009f2d  jnz     short loc_180009F77
0x180009f2f  mov     rcx, cs:g_Provider
0x180009f36  test    rcx, rcx
0x180009f39  jz      short loc_180009F4E
0x180009f3b  xor     r9d, r9d
0x180009f3e  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x180009f45  xor     r8d, r8d
0x180009f48  call    cs:__imp_EtwEventWrite
0x180009f4e  mov     eax, ebx
0x180009f50  add     rsp, 68h
0x180009f54  pop     r15
0x180009f56  pop     r14
0x180009f58  pop     rdi
0x180009f59  pop     rsi
0x180009f5a  pop     rbp
0x180009f5b  pop     rbx
0x180009f5c  retn
0x180009f5d  mov     rcx, [rcx+10h]
0x180009f61  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180009f68  mov     edx, 0B7h
0x180009f6d  call    WPP_SF_
0x180009f72  jmp     loc_180009ECE
0x180009f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f7e  cmp     rcx, r15
0x180009f81  jz      short loc_180009F2F
0x180009f83  test    byte ptr [rcx+1Ch], 1
0x180009f87  jz      short loc_180009F2F
0x180009f89  mov     rcx, [rcx+10h]
0x180009f8d  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180009f94  mov     edx, 0B8h
0x180009f99  mov     r9d, ebx
0x180009f9c  call    WPP_SF_d
0x180009fa1  jmp     short loc_180009F2F
```
