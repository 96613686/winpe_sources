# FwDiagUpdateRuleSubnet

- ea: `0x18000a1e0`
- end: `0x18000a31d`
- name: `FwDiagUpdateRuleSubnet`
- size: `317`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180009c20`
- `0x180009e10`
- `0x180009fb0`

## callees

- `0x180002576`
- `0x18000a1e0`

## import_xrefs

- `FirewallAPI!FwFree` at `0x18000a27b`
- `FirewallAPI!FwFree` at `0x18000a2e3`
- `FirewallAPI!FwFree` at `0x18000a27b`
- `FirewallAPI!FwFree` at `0x18000a2e3`
- `FirewallAPI!FwAlloc` at `0x18000a249`
- `FirewallAPI!FwAlloc` at `0x18000a2a1`
- `FirewallAPI!FwAlloc` at `0x18000a249`
- `FirewallAPI!FwAlloc` at `0x18000a2a1`
- `FirewallAPI!FWSetFirewallRule` at `0x18000a2fc`
- `FirewallAPI!FWSetFirewallRule` at `0x18000a2fc`

## pseudocode

```c
__int64 __fastcall FwDiagUpdateRuleSubnet(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v7; // rbx
  _DWORD *v8; // rax
  _DWORD *v9; // rsi
  __int64 v10; // rbx
  char *v11; // rax
  char *v12; // rsi
  size_t v13; // rbx

  if ( !a1 || !a2 || (*(_BYTE *)(a2 + 176) & 1) == 0 && (*(_BYTE *)(a2 + 180) & 1) == 0 )
    return 87;
  if ( *(_WORD *)a3 == 23 )
  {
    v10 = *(unsigned int *)(a2 + 216);
    v11 = (char *)FwAlloc(20LL * (unsigned int)(v10 + 1));
    v12 = v11;
    if ( v11 )
    {
      v13 = 20 * v10;
      memcpy_0(v11, *(const void **)(a2 + 224), v13);
      *(_OWORD *)&v12[v13] = *(_OWORD *)(a3 + 8);
      FwFree(*(_QWORD *)(a2 + 224));
      ++*(_DWORD *)(a2 + 216);
      *(_QWORD *)(a2 + 224) = v12;
      return FWSetFirewallRule(a1, a2);
    }
    return 14;
  }
  v7 = *(unsigned int *)(a2 + 184);
  v8 = (_DWORD *)FwAlloc(8LL * (unsigned int)(v7 + 1));
  v9 = v8;
  if ( !v8 )
    return 14;
  memcpy_0(v8, *(const void **)(a2 + 192), 20 * v7);
  v9[2 * v7] = *(_DWORD *)(a3 + 4);
  FwFree(*(_QWORD *)(a2 + 192));
  ++*(_DWORD *)(a2 + 184);
  *(_QWORD *)(a2 + 192) = v9;
  return FWSetFirewallRule(a1, a2);
}

```

## disassembly

```asm
0x18000a1e0  mov     [rsp+arg_10], rbp
0x18000a1e5  mov     [rsp+arg_18], rdi
0x18000a1ea  push    r14
0x18000a1ec  sub     rsp, 20h
0x18000a1f0  mov     rbp, r8
0x18000a1f3  mov     rdi, rdx
0x18000a1f6  mov     r14, rcx
0x18000a1f9  test    rcx, rcx
0x18000a1fc  jz      short loc_18000A215
0x18000a1fe  test    rdx, rdx
0x18000a201  jz      short loc_18000A215
0x18000a203  test    byte ptr [rdx+0B0h], 1
0x18000a20a  jnz     short loc_18000A22B
0x18000a20c  test    byte ptr [rdx+0B4h], 1
0x18000a213  jnz     short loc_18000A22B
0x18000a215  mov     eax, 57h ; 'W'
0x18000a21a  mov     rbp, [rsp+28h+arg_10]
0x18000a21f  mov     rdi, [rsp+28h+arg_18]
0x18000a224  add     rsp, 20h
0x18000a228  pop     r14
0x18000a22a  retn
0x18000a22b  cmp     word ptr [r8], 17h
0x18000a230  mov     [rsp+28h+arg_0], rbx
0x18000a235  mov     [rsp+28h+arg_8], rsi
0x18000a23a  jz      short loc_18000A290
0x18000a23c  mov     ebx, [rdx+0B8h]
0x18000a242  lea     ecx, [rbx+1]
0x18000a245  shl     rcx, 3
0x18000a249  call    cs:__imp_FwAlloc
0x18000a24f  mov     rsi, rax
0x18000a252  test    rax, rax
0x18000a255  jz      short loc_18000A2AF
0x18000a257  mov     rdx, [rdi+0C0h]; Src
0x18000a25e  lea     r8, [rbx+rbx*4]
0x18000a262  shl     r8, 2; Size
0x18000a266  mov     rcx, rax; void *
0x18000a269  call    memcpy_0
0x18000a26e  mov     eax, [rbp+4]
0x18000a271  mov     [rsi+rbx*8], eax
0x18000a274  mov     rcx, [rdi+0C0h]
0x18000a27b  call    cs:__imp_FwFree
0x18000a281  inc     dword ptr [rdi+0B8h]
0x18000a287  mov     [rdi+0C0h], rsi
0x18000a28e  jmp     short loc_18000A2F6
0x18000a290  mov     ebx, [rdx+0D8h]
0x18000a296  lea     eax, [rbx+1]
0x18000a299  lea     rcx, [rax+rax*4]
0x18000a29d  shl     rcx, 2
0x18000a2a1  call    cs:__imp_FwAlloc
0x18000a2a7  mov     rsi, rax
0x18000a2aa  test    rax, rax
0x18000a2ad  jnz     short loc_18000A2B6
0x18000a2af  mov     eax, 0Eh
0x18000a2b4  jmp     short loc_18000A302
0x18000a2b6  mov     rdx, [rdi+0E0h]; Src
0x18000a2bd  lea     rcx, [rbx+rbx*4]
0x18000a2c1  lea     rbx, ds:0[rcx*4]
0x18000a2c9  mov     rcx, rsi; void *
0x18000a2cc  mov     r8, rbx; Size
0x18000a2cf  call    memcpy_0
0x18000a2d4  movups  xmm0, xmmword ptr [rbp+8]
0x18000a2d8  movups  xmmword ptr [rbx+rsi], xmm0
0x18000a2dc  mov     rcx, [rdi+0E0h]
0x18000a2e3  call    cs:__imp_FwFree
0x18000a2e9  inc     dword ptr [rdi+0D8h]
0x18000a2ef  mov     [rdi+0E0h], rsi
0x18000a2f6  mov     rdx, rdi
0x18000a2f9  mov     rcx, r14
0x18000a2fc  call    cs:__imp_FWSetFirewallRule
0x18000a302  mov     rbx, [rsp+28h+arg_0]
0x18000a307  mov     rsi, [rsp+28h+arg_8]
0x18000a30c  mov     rbp, [rsp+28h+arg_10]
0x18000a311  mov     rdi, [rsp+28h+arg_18]
0x18000a316  add     rsp, 20h
0x18000a31a  pop     r14
0x18000a31c  retn
```
