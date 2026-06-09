# _dynamic_initializer_for__stringSidOpenTag___0

- ea: `0x180002a40`
- end: `0x180002a67`
- name: `_dynamic_initializer_for__stringSidOpenTag___0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000452c`
- `0x180011a04`

## string_xrefs

- `0x180002a44`: `<stringSID>`

## pseudocode

```c
int dynamic_initializer_for__stringSidOpenTag___0()
{
  std::string::string((__int64)qword_18005F8E0, (__int64)"<stringSID>");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__stringSidOpenTag___0);
}

```

## disassembly

```asm
0x180002a40  sub     rsp, 28h
0x180002a44  lea     rdx, aStringsid_0; "<stringSID>"
0x180002a4b  lea     rcx, qword_18005F8E0
0x180002a52  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180002a57  lea     rcx, _dynamic_atexit_destructor_for__stringSidOpenTag___0
0x180002a5e  add     rsp, 28h
0x180002a62  jmp     atexit
```
