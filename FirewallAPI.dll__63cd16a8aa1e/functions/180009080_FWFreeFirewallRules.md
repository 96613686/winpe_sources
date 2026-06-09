# FWFreeFirewallRules

- ea: `0x180009080`
- end: `0x18000914d`
- name: `FWFreeFirewallRules`
- size: `205`
- prototype: ``
- caller_count: `34`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001e58`
- `0x1800021f0`
- `0x180002e3c`
- `0x18000311c`
- `0x180003580`
- `0x180003b4c`
- `0x180003e10`
- `0x180003f80`
- `0x180004300`
- `0x180007880`
- `0x180009340`
- `0x180009760`
- `0x180011120`
- `0x180015eb0`
- `0x180018ef0`
- `0x18001c344`
- `0x18001d554`
- `0x18001e068`
- `0x180020370`
- `0x180025744`
- `0x1800308f8`
- `0x180032ac0`
- `0x180032f90`
- `0x1800332c0`
- `0x180039168`
- `0x180042484`
- `0x180043fc8`
- `0x1800456b0`
- `0x180045c50`
- `0x180045f54`
- `0x1800464e4`
- `0x1800474dc`
- `0x180047840`
- `0x180047c7c`

## callees

- `0x180005954`
- `0x180009080`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800090a6`
- `ntdll!EtwEventWrite` at `0x1800090f7`
- `ntdll!EtwEventWrite` at `0x1800090a6`
- `ntdll!EtwEventWrite` at `0x1800090f7`
- `fwbase!FwHResultToWindowsError` at `0x1800090d2`
- `fwbase!FwHResultToWindowsError` at `0x1800090d2`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800090ca`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800090ca`

## pseudocode

```c
__int64 __fastcall FWFreeFirewallRules(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, &MPS_CLNT_API_Enter_FreeFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  v4 = FwFreeRules(a1, 0, a3);
  v5 = FwHResultToWindowsError(v4);
  v6 = v5;
  if ( v5 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v5);
  if ( g_Provider )
    EtwEventWrite(g_Provider, &MPS_CLNT_API_Exit_FreeFirewallRules, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x180009080  mov     [rsp+arg_8], rbx
0x180009085  push    rdi
0x180009086  sub     rsp, 20h
0x18000908a  mov     rbx, rcx
0x18000908d  mov     rcx, cs:g_Provider
0x180009094  test    rcx, rcx
0x180009097  jz      short loc_1800090AC
0x180009099  xor     r9d, r9d
0x18000909c  lea     rdx, MPS_CLNT_API_Enter_FreeFirewallRules
0x1800090a3  xor     r8d, r8d
0x1800090a6  call    cs:__imp_EtwEventWrite
0x1800090ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090b3  lea     rdi, WPP_GLOBAL_Control
0x1800090ba  cmp     rcx, rdi
0x1800090bd  jz      short loc_1800090C5
0x1800090bf  test    byte ptr [rcx+1Ch], 8
0x1800090c3  jnz     short loc_18000910A
0x1800090c5  xor     edx, edx
0x1800090c7  mov     rcx, rbx
0x1800090ca  call    cs:__imp_FwFreeRules
0x1800090d0  mov     ecx, eax
0x1800090d2  call    cs:__imp_FwHResultToWindowsError
0x1800090d8  mov     ebx, eax
0x1800090da  test    eax, eax
0x1800090dc  jnz     short loc_180009121
0x1800090de  mov     rcx, cs:g_Provider
0x1800090e5  test    rcx, rcx
0x1800090e8  jz      short loc_1800090FD
0x1800090ea  xor     r9d, r9d
0x1800090ed  lea     rdx, MPS_CLNT_API_Exit_FreeFirewallRules
0x1800090f4  xor     r8d, r8d
0x1800090f7  call    cs:__imp_EtwEventWrite
0x1800090fd  mov     eax, ebx
0x1800090ff  mov     rbx, [rsp+28h+arg_8]
0x180009104  add     rsp, 20h
0x180009108  pop     rdi
0x180009109  retn
0x18000910a  mov     rcx, [rcx+10h]
0x18000910e  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180009115  mov     edx, 68h ; 'h'
0x18000911a  call    WPP_SF_
0x18000911f  jmp     short loc_1800090C5
0x180009121  mov     rcx, cs:WPP_GLOBAL_Control
0x180009128  cmp     rcx, rdi
0x18000912b  jz      short loc_1800090DE
0x18000912d  test    byte ptr [rcx+1Ch], 1
0x180009131  jz      short loc_1800090DE
0x180009133  mov     rcx, [rcx+10h]
0x180009137  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000913e  mov     edx, 69h ; 'i'
0x180009143  mov     r9d, ebx
0x180009146  call    WPP_SF_d
0x18000914b  jmp     short loc_1800090DE
```
