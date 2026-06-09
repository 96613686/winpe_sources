# FWDeleteFirewallRule

- ea: `0x1800051c0`
- end: `0x1800052b9`
- name: `FWDeleteFirewallRule`
- size: `249`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800021f0`
- `0x180003b4c`
- `0x180003f80`
- `0x180014368`
- `0x180042484`

## callees

- `0x1800051c0`
- `0x1800052c0`
- `0x180005954`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800051ee`
- `ntdll!EtwEventWrite` at `0x180005255`
- `ntdll!EtwEventWrite` at `0x1800051ee`
- `ntdll!EtwEventWrite` at `0x180005255`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005207`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180005207`

## pseudocode

```c
__int64 __fastcall FWDeleteFirewallRule(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_DeleteFirewallRule, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v4);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_DeleteFirewallRule, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x1800051c0  mov     [rsp+arg_10], rbx
0x1800051c5  mov     [rsp+arg_18], rsi
0x1800051ca  push    rdi
0x1800051cb  sub     rsp, 40h
0x1800051cf  mov     rbx, rcx
0x1800051d2  mov     rdi, rdx
0x1800051d5  mov     rcx, cs:g_Provider
0x1800051dc  test    rcx, rcx
0x1800051df  jz      short loc_1800051F4
0x1800051e1  xor     r9d, r9d
0x1800051e4  lea     rdx, MPS_CLNT_API_Enter_DeleteFirewallRule
0x1800051eb  xor     r8d, r8d
0x1800051ee  call    cs:__imp_EtwEventWrite
0x1800051f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051fb  lea     rsi, WPP_GLOBAL_Control
0x180005202  cmp     rcx, rsi
0x180005205  jnz     short loc_18000526D
0x180005207  call    cs:__imp_GetTickCount64
0x18000520d  mov     [rsp+48h+var_18], 0
0x180005215  lea     r9, RRPC_FWDeleteFirewallRule
0x18000521c  mov     [rsp+48h+var_20], rdi
0x180005221  lea     r8, RPC_FWDeleteFirewallRule
0x180005228  xor     edx, edx
0x18000522a  mov     [rsp+48h+var_28], rbx
0x18000522f  xor     ecx, ecx
0x180005231  call    Int_FWDeleteObject
0x180005236  mov     ebx, eax
0x180005238  test    eax, eax
0x18000523a  jnz     short loc_18000528D
0x18000523c  mov     rcx, cs:g_Provider
0x180005243  test    rcx, rcx
0x180005246  jz      short loc_18000525B
0x180005248  xor     r9d, r9d
0x18000524b  lea     rdx, MPS_CLNT_API_Exit_DeleteFirewallRule
0x180005252  xor     r8d, r8d
0x180005255  call    cs:__imp_EtwEventWrite
0x18000525b  mov     rsi, [rsp+48h+arg_18]
0x180005260  mov     eax, ebx
0x180005262  mov     rbx, [rsp+48h+arg_10]
0x180005267  add     rsp, 40h
0x18000526b  pop     rdi
0x18000526c  retn
0x18000526d  test    byte ptr [rcx+1Ch], 8
0x180005271  jz      short loc_180005207
0x180005273  mov     rcx, [rcx+10h]
0x180005277  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000527e  mov     edx, 5Dh ; ']'
0x180005283  call    WPP_SF_
0x180005288  jmp     loc_180005207
0x18000528d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005294  cmp     rcx, rsi
0x180005297  jz      short loc_18000523C
0x180005299  test    byte ptr [rcx+1Ch], 1
0x18000529d  jz      short loc_18000523C
0x18000529f  mov     rcx, [rcx+10h]
0x1800052a3  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800052aa  mov     edx, 5Eh ; '^'
0x1800052af  mov     r9d, ebx
0x1800052b2  call    WPP_SF_d
0x1800052b7  jmp     short loc_18000523C
```
