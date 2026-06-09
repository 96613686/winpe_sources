# CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)

- ea: `0x180015590`
- end: `0x1800155f9`
- name: `?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z`
- size: `105`
- prototype: `const struct CSP_NODEMAP_ENTRY *__fastcall(const struct CspNodeMapBase *, struct IConfigManager2URI *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800075c0`
- `0x180008840`
- `0x18000c210`
- `0x180014ed0`
- `0x180015100`

## callees

- `0x180015590`
- `0x180015600`
- `0x180039010`

## pseudocode

```c
const struct CSP_NODEMAP_ENTRY *__fastcall CspGetNodeMapEntryForURI(
        const struct CspNodeMapBase *a1,
        struct IConfigManager2URI *a2)
{
  __int64 v4; // rsi
  unsigned int v5; // eax

  if ( a1
    && a2
    && (v4 = (*(__int64 (__fastcall **)(const struct CspNodeMapBase *))(*(_QWORD *)a1 + 8LL))(a1)) != 0
    && (v5 = (*(__int64 (__fastcall **)(const struct CspNodeMapBase *))(*(_QWORD *)a1 + 16LL))(a1), v5 != -1) )
  {
    return (const struct CSP_NODEMAP_ENTRY *)CspGetNodeMapEntryFromNodeMap(v4, v5, a2);
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180015590  mov     [rsp+arg_0], rbx
0x180015595  mov     [rsp+arg_8], rsi
0x18001559a  push    rdi
0x18001559b  sub     rsp, 20h
0x18001559f  mov     rdi, rdx
0x1800155a2  mov     rbx, rcx
0x1800155a5  test    rcx, rcx
0x1800155a8  jz      short loc_1800155E6
0x1800155aa  test    rdx, rdx
0x1800155ad  jz      short loc_1800155E6
0x1800155af  mov     rax, [rcx]
0x1800155b2  mov     rax, [rax+8]
0x1800155b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155bb  mov     rsi, rax
0x1800155be  test    rax, rax
0x1800155c1  jz      short loc_1800155E6
0x1800155c3  mov     rcx, [rbx]
0x1800155c6  mov     rax, [rcx+10h]
0x1800155ca  mov     rcx, rbx
0x1800155cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155d2  cmp     eax, 0FFFFFFFFh
0x1800155d5  jz      short loc_1800155E6
0x1800155d7  mov     r8, rdi
0x1800155da  mov     edx, eax
0x1800155dc  mov     rcx, rsi
0x1800155df  call    CspGetNodeMapEntryFromNodeMap
0x1800155e4  jmp     short loc_1800155E8
0x1800155e6  xor     eax, eax
0x1800155e8  mov     rbx, [rsp+28h+arg_0]
0x1800155ed  mov     rsi, [rsp+28h+arg_8]
0x1800155f2  add     rsp, 20h
0x1800155f6  pop     rdi
0x1800155f7  retn
```
