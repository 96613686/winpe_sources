# CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)

- ea: `0x180014aac`
- end: `0x180014b14`
- name: `?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z`
- size: `104`
- prototype: `const struct CSP_NODEMAP_ENTRY *__fastcall(const struct CspNodeMapBase *, struct IConfigManager2URI *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007460`
- `0x180008640`
- `0x18000bcc0`
- `0x180014410`
- `0x180014640`

## callees

- `0x180014aac`
- `0x180014b1c`
- `0x180037010`

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
0x180014aac  mov     [rsp+arg_0], rbx
0x180014ab1  mov     [rsp+arg_8], rsi
0x180014ab6  push    rdi
0x180014ab7  sub     rsp, 20h
0x180014abb  mov     rdi, rdx
0x180014abe  mov     rbx, rcx
0x180014ac1  test    rcx, rcx
0x180014ac4  jz      short loc_180014B02
0x180014ac6  test    rdx, rdx
0x180014ac9  jz      short loc_180014B02
0x180014acb  mov     rax, [rcx]
0x180014ace  mov     rax, [rax+8]
0x180014ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ad7  mov     rsi, rax
0x180014ada  test    rax, rax
0x180014add  jz      short loc_180014B02
0x180014adf  mov     rcx, [rbx]
0x180014ae2  mov     rax, [rcx+10h]
0x180014ae6  mov     rcx, rbx
0x180014ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014aee  cmp     eax, 0FFFFFFFFh
0x180014af1  jz      short loc_180014B02
0x180014af3  mov     r8, rdi
0x180014af6  mov     edx, eax
0x180014af8  mov     rcx, rsi
0x180014afb  call    CspGetNodeMapEntryFromNodeMap
0x180014b00  jmp     short loc_180014B04
0x180014b02  xor     eax, eax
0x180014b04  mov     rbx, [rsp+28h+arg_0]
0x180014b09  mov     rsi, [rsp+28h+arg_8]
0x180014b0e  add     rsp, 20h
0x180014b12  pop     rdi
0x180014b13  retn
```
