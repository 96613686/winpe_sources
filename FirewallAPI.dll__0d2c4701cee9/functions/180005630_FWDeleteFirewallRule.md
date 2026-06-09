# FWDeleteFirewallRule

- ea: `0x180005630`
- end: `0x18000573f`
- name: `FWDeleteFirewallRule`
- size: `271`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800022c0`
- `0x180003e5c`
- `0x1800042c0`
- `0x1800143d8`
- `0x180045814`

## callees

- `0x180005630`
- `0x180005748`
- `0x180005e0c`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000565e`
- `ntdll!EtwEventWrite` at `0x1800056d1`
- `ntdll!EtwEventWrite` at `0x18000565e`
- `ntdll!EtwEventWrite` at `0x1800056d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000567d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000567d`

## pseudocode

```c
__int64 __fastcall FWDeleteFirewallRule(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_DeleteFirewallRule, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v4 = Int_FWDeleteObject(
         0,
         0,
         (__int64 (__fastcall *)(__int64, __int64))RPC_FWDeleteFirewallRule,
         (__int64 (__fastcall *)(__int64, __int64))RRPC_FWDeleteFirewallRule,
         a1,
         a2,
         0);
  v5 = v4;
  if ( v4 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_DeleteFirewallRule, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x180005630  mov     [rsp+arg_10], rbx
0x180005635  mov     [rsp+arg_18], rsi
0x18000563a  push    rdi
0x18000563b  sub     rsp, 40h
0x18000563f  mov     rbx, rcx
0x180005642  mov     rdi, rdx
0x180005645  mov     rcx, cs:g_Provider
0x18000564c  test    rcx, rcx
0x18000564f  jz      short loc_18000566A
0x180005651  xor     r9d, r9d
0x180005654  lea     rdx, MPS_CLNT_API_Enter_DeleteFirewallRule
0x18000565b  xor     r8d, r8d
0x18000565e  call    cs:__imp_EtwEventWrite
0x180005665  nop     dword ptr [rax+rax+00h]
0x18000566a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005671  lea     rsi, WPP_GLOBAL_Control
0x180005678  cmp     rcx, rsi
0x18000567b  jnz     short loc_1800056F0
0x18000567d  call    cs:__imp_GetTickCount64
0x180005684  nop     dword ptr [rax+rax+00h]
0x180005689  mov     [rsp+48h+var_18], 0
0x180005691  lea     r9, RRPC_FWDeleteFirewallRule
0x180005698  mov     [rsp+48h+var_20], rdi
0x18000569d  lea     r8, RPC_FWDeleteFirewallRule
0x1800056a4  xor     edx, edx
0x1800056a6  mov     [rsp+48h+var_28], rbx
0x1800056ab  xor     ecx, ecx
0x1800056ad  call    Int_FWDeleteObject
0x1800056b2  mov     ebx, eax
0x1800056b4  test    eax, eax
0x1800056b6  jnz     short loc_180005710
0x1800056b8  mov     rcx, cs:g_Provider
0x1800056bf  test    rcx, rcx
0x1800056c2  jz      short loc_1800056DD
0x1800056c4  xor     r9d, r9d
0x1800056c7  lea     rdx, MPS_CLNT_API_Exit_DeleteFirewallRule
0x1800056ce  xor     r8d, r8d
0x1800056d1  call    cs:__imp_EtwEventWrite
0x1800056d8  nop     dword ptr [rax+rax+00h]
0x1800056dd  mov     rsi, [rsp+48h+arg_18]
0x1800056e2  mov     eax, ebx
0x1800056e4  mov     rbx, [rsp+48h+arg_10]
0x1800056e9  add     rsp, 40h
0x1800056ed  pop     rdi
0x1800056ee  retn
0x1800056f0  test    byte ptr [rcx+1Ch], 8
0x1800056f4  jz      short loc_18000567D
0x1800056f6  mov     rcx, [rcx+10h]
0x1800056fa  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180005701  mov     edx, 5Ch ; '\'
0x180005706  call    WPP_SF_
0x18000570b  jmp     loc_18000567D
0x180005710  mov     rcx, cs:WPP_GLOBAL_Control
0x180005717  cmp     rcx, rsi
0x18000571a  jz      short loc_1800056B8
0x18000571c  test    byte ptr [rcx+1Ch], 1
0x180005720  jz      short loc_1800056B8
0x180005722  mov     rcx, [rcx+10h]
0x180005726  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000572d  mov     edx, 5Dh ; ']'
0x180005732  mov     r9d, ebx
0x180005735  call    WPP_SF_d
0x18000573a  jmp     loc_1800056B8
```
