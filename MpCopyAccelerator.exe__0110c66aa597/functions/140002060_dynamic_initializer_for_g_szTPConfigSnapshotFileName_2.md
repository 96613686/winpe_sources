# _dynamic_initializer_for__g_szTPConfigSnapshotFileName___2

- ea: `0x140002060`
- end: `0x14000208d`
- name: `_dynamic_initializer_for__g_szTPConfigSnapshotFileName___2`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140006010`
- `0x140021e84`

## string_xrefs

- `0x14000206a`: `TPConfigSnapshot.snp`

## pseudocode

```c
int dynamic_initializer_for__g_szTPConfigSnapshotFileName___2()
{
  std::string::_Construct<1,char const *>(qword_14003D9F0, "TPConfigSnapshot.snp", 20);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName___2);
}

```

## disassembly

```asm
0x140002060  sub     rsp, 28h
0x140002064  mov     r8d, 14h
0x14000206a  lea     rdx, aTpconfigsnapsh; "TPConfigSnapshot.snp"
0x140002071  lea     rcx, qword_14003D9F0
0x140002078  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14000207d  lea     rcx, _dynamic_atexit_destructor_for__g_szTPConfigSnapshotFileName___2
0x140002084  add     rsp, 28h
0x140002088  jmp     atexit
```
