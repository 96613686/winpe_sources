# _dynamic_initializer_for__stringSidOpenTag__

- ea: `0x180002880`
- end: `0x1800028a7`
- name: `_dynamic_initializer_for__stringSidOpenTag__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000452c`
- `0x180011a04`

## string_xrefs

- `0x180002884`: `<stringSID>`

## pseudocode

```c
int dynamic_initializer_for__stringSidOpenTag__()
{
  std::string::string((__int64)qword_18005F7C0, (__int64)"<stringSID>");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__stringSidOpenTag__);
}

```

## disassembly

```asm
0x180002880  sub     rsp, 28h
0x180002884  lea     rdx, aStringsid_0; "<stringSID>"
0x18000288b  lea     rcx, qword_18005F7C0
0x180002892  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002897  lea     rcx, _dynamic_atexit_destructor_for__stringSidOpenTag__
0x18000289e  add     rsp, 28h
0x1800028a2  jmp     atexit
```
