# OnDelete0<void (*)(void),&CoUninitialize(void)>::~OnDelete0<void (*)(void),&CoUninitialize(void)>(void)

- ea: `0x140004cc4`
- end: `0x140004cd4`
- name: `??1?$OnDelete0@P6AXXZ$1?CoUninitialize@@YAXXZ@@QEAA@XZ`
- size: `16`
- prototype: `void()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140015214`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004cc8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004cc8`

## pseudocode

```c
void OnDelete0<void (*)(void),&void CoUninitialize(void)>::~OnDelete0<void (*)(void),&void CoUninitialize(void)>()
{
  CoUninitialize();
}

```

## disassembly

```asm
0x140004cc4  sub     rsp, 28h
0x140004cc8  call    cs:__imp_CoUninitialize
0x140004cce  nop
0x140004ccf  add     rsp, 28h
0x140004cd3  retn
```
