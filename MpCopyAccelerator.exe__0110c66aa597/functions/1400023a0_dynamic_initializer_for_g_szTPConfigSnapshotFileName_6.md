# _dynamic_initializer_for__g_szTPConfigSnapshotFileName___6

- ea: `0x1400023a0`
- end: `0x1400023cd`
- name: `_dynamic_initializer_for__g_szTPConfigSnapshotFileName___6`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006010`
- `0x140021e84`

## string_xrefs

- `0x1400023aa`: `TPConfigSnapshot.snp`

## pseudocode

```c
int dynamic_initializer_for__g_szTPConfigSnapshotFileName___6()
{
  std::string::_Construct<1,char const *>(qword_14003DAD0, "TPConfigSnapshot.snp", 20);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName___6);
}

```

## disassembly

```asm
0x1400023a0  sub     rsp, 28h
0x1400023a4  mov     r8d, 14h
0x1400023aa  lea     rdx, aTpconfigsnapsh; "TPConfigSnapshot.snp"
0x1400023b1  lea     rcx, qword_14003DAD0
0x1400023b8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400023bd  lea     rcx, _dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName___6
0x1400023c4  add     rsp, 28h
0x1400023c8  jmp     atexit
```
