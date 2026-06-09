# FirewallHelper::DeleteFirewallRule(ushort const *)

- ea: `0x18001d358`
- end: `0x18001d3dc`
- name: `?DeleteFirewallRule@FirewallHelper@@YAKPEBG@Z`
- size: `132`
- prototype: `int __fastcall(FirewallHelper *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001d2f0`

## callees

- `0x18001c080`
- `0x18001d358`

## import_xrefs

- `FirewallAPI!FWDeleteFirewallRule` at `0x18001d3be`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18001d3be`
- `FirewallAPI!FWOpenPolicyStore` at `0x18001d38e`
- `FirewallAPI!FWOpenPolicyStore` at `0x18001d38e`
- `FirewallAPI!FWClosePolicyStore` at `0x18001d3c9`
- `FirewallAPI!FWClosePolicyStore` at `0x18001d3c9`

## pseudocode

```c
int __fastcall FirewallHelper::DeleteFirewallRule(FirewallHelper *this, const unsigned __int16 *a2)
{
  unsigned int v3; // eax
  int v5; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = FWOpenPolicyStore(545, 0, 8, 2);
  if ( v3 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x10A,
             (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
             (const char *)v3,
             0);
  v5 = FWDeleteFirewallRule(0, this);
  FWClosePolicyStore(0);
  return v5;
}

```

## disassembly

```asm
0x18001d358  mov     r11, rsp
0x18001d35b  mov     [r11+8], rbx
0x18001d35f  push    rdi
0x18001d360  sub     rsp, 30h
0x18001d364  xor     edx, edx
0x18001d366  mov     qword ptr [r11+10h], 0
0x18001d36e  lea     rax, [r11+10h]
0x18001d372  mov     rbx, rcx
0x18001d375  mov     [r11-10h], rax
0x18001d379  mov     ecx, 221h
0x18001d37e  mov     [rsp+38h+var_18], 0; unsigned int
0x18001d386  lea     r9d, [rdx+2]
0x18001d38a  lea     r8d, [rdx+8]
0x18001d38e  call    cs:__imp_FWOpenPolicyStore
0x18001d394  test    eax, eax
0x18001d396  jz      short loc_18001D3B3
0x18001d398  mov     rcx, [rsp+38h]; this
0x18001d39d  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18001d3a4  mov     r9d, eax; char *
0x18001d3a7  mov     edx, 10Ah; void *
0x18001d3ac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d3b1  jmp     short loc_18001D3D1
0x18001d3b3  mov     rdi, [rsp+38h+arg_8]
0x18001d3b8  mov     rdx, rbx
0x18001d3bb  mov     rcx, rdi
0x18001d3be  call    cs:__imp_FWDeleteFirewallRule
0x18001d3c4  mov     rcx, rdi
0x18001d3c7  mov     ebx, eax
0x18001d3c9  call    cs:__imp_FWClosePolicyStore
0x18001d3cf  mov     eax, ebx
0x18001d3d1  mov     rbx, [rsp+38h+arg_0]
0x18001d3d6  add     rsp, 30h
0x18001d3da  pop     rdi
0x18001d3db  retn
```
