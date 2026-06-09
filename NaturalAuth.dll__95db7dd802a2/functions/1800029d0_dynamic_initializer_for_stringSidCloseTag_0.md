# _dynamic_initializer_for__stringSidCloseTag___0

- ea: `0x1800029d0`
- end: `0x1800029f7`
- name: `_dynamic_initializer_for__stringSidCloseTag___0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000452c`
- `0x180011a04`

## string_xrefs

- `0x1800029d4`: `</stringSID>`

## pseudocode

```c
int dynamic_initializer_for__stringSidCloseTag___0()
{
  std::string::string((__int64)qword_18005F880, (__int64)"</stringSID>");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__stringSidCloseTag___0);
}

```

## disassembly

```asm
0x1800029d0  sub     rsp, 28h
0x1800029d4  lea     rdx, aStringsid; "</stringSID>"
0x1800029db  lea     rcx, qword_18005F880
0x1800029e2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800029e7  lea     rcx, _dynamic_atexit_destructor_for__stringSidCloseTag___0
0x1800029ee  add     rsp, 28h
0x1800029f2  jmp     atexit
```
