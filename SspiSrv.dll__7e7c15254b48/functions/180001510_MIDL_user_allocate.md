# MIDL_user_allocate

- ea: `0x180001510`
- end: `0x18000152e`
- name: `MIDL_user_allocate`
- size: `30`
- prototype: `void *__stdcall(size_t size)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002d60`
- `0x180002fb0`

## callees

- `0x180001510`
- `0x180004010`

## pseudocode

```c
void *__stdcall MIDL_user_allocate(size_t size)
{
  if ( gLsapSspiExtension && *(_QWORD *)gLsapSspiExtension )
    return (void *)(*(__int64 (__fastcall **)(size_t))gLsapSspiExtension)(size);
  else
    return 0;
}

```

## disassembly

```asm
0x180001510  mov     rax, cs:gLsapSspiExtension
0x180001517  test    rax, rax
0x18000151a  jz      short loc_18000152A
0x18000151c  mov     rax, [rax]
0x18000151f  test    rax, rax
0x180001522  jz      short loc_18000152A
0x180001524  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001529  retn
0x18000152a  xor     eax, eax
0x18000152c  jmp     short locret_180001529
```
