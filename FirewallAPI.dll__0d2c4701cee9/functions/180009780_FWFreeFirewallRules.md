# FWFreeFirewallRules

- ea: `0x180009780`
- end: `0x180009866`
- name: `FWFreeFirewallRules`
- size: `230`
- prototype: ``
- caller_count: `34`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001edc`
- `0x1800022c0`
- `0x180003080`
- `0x1800033a4`
- `0x180003840`
- `0x180003e5c`
- `0x180004140`
- `0x1800042c0`
- `0x180004680`
- `0x180007e30`
- `0x180009a50`
- `0x180009ed0`
- `0x18000b4b0`
- `0x180015fb0`
- `0x1800191e0`
- `0x18001ae24`
- `0x18001e960`
- `0x18001f8c4`
- `0x180021b60`
- `0x180027370`
- `0x180032ba8`
- `0x180034fe0`
- `0x180035500`
- `0x180035850`
- `0x18003bc1c`
- `0x180045814`
- `0x1800474c8`
- `0x180048d40`
- `0x180049330`
- `0x180049680`
- `0x180049c54`
- `0x18004adac`
- `0x18004b12c`
- `0x18004b5c8`

## callees

- `0x180005e0c`
- `0x180009780`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800097a6`
- `ntdll!EtwEventWrite` at `0x180009809`
- `ntdll!EtwEventWrite` at `0x1800097a6`
- `ntdll!EtwEventWrite` at `0x180009809`
- `fwbase!FwHResultToWindowsError` at `0x1800097de`
- `fwbase!FwHResultToWindowsError` at `0x1800097de`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800097d0`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800097d0`

## pseudocode

```c
__int64 __fastcall FWFreeFirewallRules(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, &MPS_CLNT_API_Enter_FreeFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  v2 = FwFreeRules(a1, 0);
  v3 = FwHResultToWindowsError(v2);
  v4 = v3;
  if ( v3 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v3);
  if ( g_Provider )
    EtwEventWrite(g_Provider, &MPS_CLNT_API_Exit_FreeFirewallRules, 0, 0);
  return v4;
}

```

## disassembly

```asm
0x180009780  mov     [rsp+arg_8], rbx
0x180009785  push    rdi
0x180009786  sub     rsp, 20h
0x18000978a  mov     rbx, rcx
0x18000978d  mov     rcx, cs:g_Provider
0x180009794  test    rcx, rcx
0x180009797  jz      short loc_1800097B2
0x180009799  xor     r9d, r9d
0x18000979c  lea     rdx, MPS_CLNT_API_Enter_FreeFirewallRules
0x1800097a3  xor     r8d, r8d
0x1800097a6  call    cs:__imp_EtwEventWrite
0x1800097ad  nop     dword ptr [rax+rax+00h]
0x1800097b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097b9  lea     rdi, WPP_GLOBAL_Control
0x1800097c0  cmp     rcx, rdi
0x1800097c3  jz      short loc_1800097CB
0x1800097c5  test    byte ptr [rcx+1Ch], 8
0x1800097c9  jnz     short loc_180009823
0x1800097cb  xor     edx, edx
0x1800097cd  mov     rcx, rbx
0x1800097d0  call    cs:__imp_FwFreeRules
0x1800097d7  nop     dword ptr [rax+rax+00h]
0x1800097dc  mov     ecx, eax
0x1800097de  call    cs:__imp_FwHResultToWindowsError
0x1800097e5  nop     dword ptr [rax+rax+00h]
0x1800097ea  mov     ebx, eax
0x1800097ec  test    eax, eax
0x1800097ee  jnz     short loc_18000983A
0x1800097f0  mov     rcx, cs:g_Provider
0x1800097f7  test    rcx, rcx
0x1800097fa  jz      short loc_180009815
0x1800097fc  xor     r9d, r9d
0x1800097ff  lea     rdx, MPS_CLNT_API_Exit_FreeFirewallRules
0x180009806  xor     r8d, r8d
0x180009809  call    cs:__imp_EtwEventWrite
0x180009810  nop     dword ptr [rax+rax+00h]
0x180009815  mov     eax, ebx
0x180009817  mov     rbx, [rsp+28h+arg_8]
0x18000981c  add     rsp, 20h
0x180009820  pop     rdi
0x180009821  retn
0x180009823  mov     rcx, [rcx+10h]
0x180009827  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000982e  mov     edx, 67h ; 'g'
0x180009833  call    WPP_SF_
0x180009838  jmp     short loc_1800097CB
0x18000983a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009841  cmp     rcx, rdi
0x180009844  jz      short loc_1800097F0
0x180009846  test    byte ptr [rcx+1Ch], 1
0x18000984a  jz      short loc_1800097F0
0x18000984c  mov     rcx, [rcx+10h]
0x180009850  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180009857  mov     edx, 68h ; 'h'
0x18000985c  mov     r9d, ebx
0x18000985f  call    WPP_SF_d
0x180009864  jmp     short loc_1800097F0
```
