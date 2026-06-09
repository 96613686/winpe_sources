# std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Lower_bound_duplicate<CPolicyEntry *>(std::_Tree_node<CPolicyEntry *,void *> * const,CPolicyEntry * const &)

- ea: `0x180002978`
- end: `0x1800029a0`
- name: `??$_Lower_bound_duplicate@PEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@1@AEBQEAVCPolicyEntry@@@Z`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027b4`
- `0x1800038dc`

## callees

- `0x180002978`
- `0x180002ca8`

## pseudocode

```c
bool __fastcall std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Lower_bound_duplicate<CPolicyEntry *>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  return !*(_BYTE *)(a2 + 25) && !CPolicyEntryCompare::operator()(a1, a3, a2 + 32);
}

```

## disassembly

```asm
0x180002978  sub     rsp, 28h
0x18000297c  cmp     byte ptr [rdx+19h], 0
0x180002980  mov     rax, r8
0x180002983  jnz     short loc_180002999
0x180002985  lea     r8, [rdx+20h]
0x180002989  mov     rdx, rax
0x18000298c  call    ??RCPolicyEntryCompare@@QEBA_NAEBQEAVCPolicyEntry@@0@Z; CPolicyEntryCompare::operator()(CPolicyEntry * const &,CPolicyEntry * const &)
0x180002991  test    al, al
0x180002993  jnz     short loc_180002999
0x180002995  mov     al, 1
0x180002997  jmp     short loc_18000299B
0x180002999  xor     al, al
0x18000299b  add     rsp, 28h
0x18000299f  retn
```
