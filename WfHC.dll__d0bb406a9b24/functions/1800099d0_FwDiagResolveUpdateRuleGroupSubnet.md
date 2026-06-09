# FwDiagResolveUpdateRuleGroupSubnet

- ea: `0x1800099d0`
- end: `0x180009a47`
- name: `FwDiagResolveUpdateRuleGroupSubnet`
- size: `119`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x1800099d0`
- `0x180009fb0`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x180009a1c`
- `FirewallAPI!FWGetGlobalConfig` at `0x180009a1c`

## pseudocode

```c
__int64 __fastcall FwDiagResolveUpdateRuleGroupSubnet(__int64 a1)
{
  __int64 result; // rax
  int v3; // [rsp+50h] [rbp+8h] BYREF
  int v4; // [rsp+58h] [rbp+10h] BYREF

  if ( !a1 || !*(_QWORD *)(a1 + 16) )
    return 87;
  v4 = 4;
  v3 = 0;
  result = FWGetGlobalConfig(545, 0, 5, 2, 0, &v3, &v4);
  if ( !(_DWORD)result )
    return FwDiagUpdateRuleGroupSubnet(*(PCNZWCH *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x1800099d0  push    rbx
0x1800099d2  sub     rsp, 40h
0x1800099d6  mov     rbx, rcx
0x1800099d9  test    rcx, rcx
0x1800099dc  jz      short loc_180009A3C
0x1800099de  cmp     qword ptr [rcx+10h], 0
0x1800099e3  jz      short loc_180009A3C
0x1800099e5  xor     edx, edx
0x1800099e7  mov     [rsp+48h+arg_8], 4
0x1800099ef  lea     rax, [rsp+48h+arg_8]
0x1800099f4  mov     [rsp+48h+arg_0], edx
0x1800099f8  mov     [rsp+48h+var_18], rax
0x1800099fd  mov     ecx, 221h
0x180009a02  lea     rax, [rsp+48h+arg_0]
0x180009a07  mov     r9d, 2
0x180009a0d  mov     [rsp+48h+var_20], rax
0x180009a12  mov     r8d, 5
0x180009a18  mov     [rsp+48h+var_28], edx
0x180009a1c  call    cs:__imp_FWGetGlobalConfig
0x180009a22  test    eax, eax
0x180009a24  jnz     short loc_180009A41
0x180009a26  mov     edx, [rsp+48h+arg_0]
0x180009a2a  lea     r8, [rbx+18h]
0x180009a2e  mov     rcx, [rbx+10h]; lpString2
0x180009a32  add     rsp, 40h
0x180009a36  pop     rbx
0x180009a37  jmp     FwDiagUpdateRuleGroupSubnet
0x180009a3c  mov     eax, 57h ; 'W'
0x180009a41  add     rsp, 40h
0x180009a45  pop     rbx
0x180009a46  retn
```
