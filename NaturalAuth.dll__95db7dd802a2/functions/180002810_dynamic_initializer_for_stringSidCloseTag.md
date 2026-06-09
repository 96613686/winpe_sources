# _dynamic_initializer_for__stringSidCloseTag__

- ea: `0x180002810`
- end: `0x180002837`
- name: `_dynamic_initializer_for__stringSidCloseTag__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000452c`
- `0x180011a04`

## string_xrefs

- `0x180002814`: `</stringSID>`

## pseudocode

```c
int dynamic_initializer_for__stringSidCloseTag__()
{
  std::string::string((__int64)qword_18005F760, (__int64)"</stringSID>");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__stringSidCloseTag__);
}

```

## disassembly

```asm
0x180002810  sub     rsp, 28h
0x180002814  lea     rdx, aStringsid; "</stringSID>"
0x18000281b  lea     rcx, qword_18005F760
0x180002822  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002827  lea     rcx, _dynamic_atexit_destructor_for__stringSidCloseTag__
0x18000282e  add     rsp, 28h
0x180002832  jmp     atexit
```
