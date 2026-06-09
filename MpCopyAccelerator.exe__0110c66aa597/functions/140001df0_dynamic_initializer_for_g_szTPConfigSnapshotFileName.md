# _dynamic_initializer_for__g_szTPConfigSnapshotFileName__

- ea: `0x140001df0`
- end: `0x140001e1d`
- name: `_dynamic_initializer_for__g_szTPConfigSnapshotFileName__`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006010`
- `0x140021e84`

## string_xrefs

- `0x140001dfa`: `TPConfigSnapshot.snp`

## pseudocode

```c
int dynamic_initializer_for__g_szTPConfigSnapshotFileName__()
{
  std::string::_Construct<1,char const *>(qword_14003D948, "TPConfigSnapshot.snp", 20);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName__);
}

```

## disassembly

```asm
0x140001df0  sub     rsp, 28h
0x140001df4  mov     r8d, 14h
0x140001dfa  lea     rdx, aTpconfigsnapsh; "TPConfigSnapshot.snp"
0x140001e01  lea     rcx, qword_14003D948
0x140001e08  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140001e0d  lea     rcx, _dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName__
0x140001e14  add     rsp, 28h
0x140001e18  jmp     atexit
```
