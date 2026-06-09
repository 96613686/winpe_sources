# wistd::operator==<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> const &,std::nullptr_t)

- ea: `0x140006b5c`
- end: `0x140006b64`
- name: `??$?8XUprocess_heap_deleter@wil@@@wistd@@YA_NAEBV?$unique_ptr@XUprocess_heap_deleter@wil@@@0@$$T@Z`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400047c8`
- `0x14000492c`

## pseudocode

```c
bool __fastcall wistd::operator==<void,wil::process_heap_deleter>(_QWORD *a1)
{
  return *a1 == 0;
}

```

## disassembly

```asm
0x140006b5c  cmp     qword ptr [rcx], 0
0x140006b60  setz    al
0x140006b63  retn
```
