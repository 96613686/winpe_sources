# wistd::operator==<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> const &,std::nullptr_t)

- ea: `0x140002768`
- end: `0x140002770`
- name: `??$?8XUprocess_heap_deleter@wil@@@wistd@@YA_NAEBV?$unique_ptr@XUprocess_heap_deleter@wil@@@0@$$T@Z`
- size: `8`
- prototype: `bool __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1400046d4`

## pseudocode

```c
bool __fastcall wistd::operator==<void,wil::process_heap_deleter>(_QWORD *a1)
{
  return *a1 == 0;
}

```

## disassembly

```asm
0x140002768  cmp     qword ptr [rcx], 0
0x14000276c  setz    al
0x14000276f  retn
```
