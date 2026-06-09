# _dynamic_initializer_for__c_locale__

- ea: `0x180001800`
- end: `0x18000181f`
- name: `_dynamic_initializer_for__c_locale__`
- size: `31`
- prototype: `_locale_t()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18000180d`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x18000180d`

## pseudocode

```c
_locale_t dynamic_initializer_for__c_locale__()
{
  _locale_t result; // rax

  result = _create_locale(0, "C");
  qword_180018E10 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x180001800  sub     rsp, 28h
0x180001804  lea     rdx, Locale; "C"
0x18000180b  xor     ecx, ecx; Category
0x18000180d  call    cs:__imp__create_locale
0x180001813  mov     cs:qword_180018E10, rax
0x18000181a  add     rsp, 28h
0x18000181e  retn
```
