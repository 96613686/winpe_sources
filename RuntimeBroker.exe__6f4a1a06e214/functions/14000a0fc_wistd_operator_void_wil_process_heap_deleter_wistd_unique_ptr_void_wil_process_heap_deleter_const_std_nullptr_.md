# wistd::operator==<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> const &,std::nullptr_t)

- ea: `0x14000a0fc`
- end: `0x14000a104`
- name: `??$?8XUprocess_heap_deleter@wil@@@wistd@@YA_NAEBV?$unique_ptr@XUprocess_heap_deleter@wil@@@0@$$T@Z`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140008668`
- `0x1400087cc`

## pseudocode

```c
bool __fastcall wistd::operator==<void,wil::process_heap_deleter>(_QWORD *a1)
{
  return *a1 == 0;
}

```

## disassembly

```asm
0x14000a0fc  cmp     qword ptr [rcx], 0
0x14000a100  setz    al
0x14000a103  retn
```
