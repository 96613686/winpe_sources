# _dynamic_initializer_for__g_szTPConfigSnapshotFileName___1

- ea: `0x140001f90`
- end: `0x140001fbd`
- name: `_dynamic_initializer_for__g_szTPConfigSnapshotFileName___1`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006010`
- `0x140021e84`

## string_xrefs

- `0x140001f9a`: `TPConfigSnapshot.snp`

## pseudocode

```c
int dynamic_initializer_for__g_szTPConfigSnapshotFileName___1()
{
  std::string::_Construct<1,char const *>(qword_14003D9B8, "TPConfigSnapshot.snp", 20);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName___1);
}

```

## disassembly

```asm
0x140001f90  sub     rsp, 28h
0x140001f94  mov     r8d, 14h
0x140001f9a  lea     rdx, aTpconfigsnapsh; "TPConfigSnapshot.snp"
0x140001fa1  lea     rcx, qword_14003D9B8
0x140001fa8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140001fad  lea     rcx, _dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName___1
0x140001fb4  add     rsp, 28h
0x140001fb8  jmp     atexit
```
