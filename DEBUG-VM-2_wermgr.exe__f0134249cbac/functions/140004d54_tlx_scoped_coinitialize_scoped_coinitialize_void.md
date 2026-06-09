# tlx::scoped_coinitialize::~scoped_coinitialize(void)

- ea: `0x140004d54`
- end: `0x140004d68`
- name: `??1scoped_coinitialize@tlx@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(tlx::scoped_coinitialize *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001cc17`
- `0x14001cd13`
- `0x14001cdeb`
- `0x14001cec5`
- `0x14001cee9`

## callees

- `0x140004d54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004d5d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004d5d`

## pseudocode

```c
void __fastcall tlx::scoped_coinitialize::~scoped_coinitialize(tlx::scoped_coinitialize *this)
{
  if ( *(int *)this >= 0 )
    CoUninitialize();
}

```

## disassembly

```asm
0x140004d54  sub     rsp, 28h
0x140004d58  cmp     dword ptr [rcx], 0
0x140004d5b  jl      short loc_140004D63
0x140004d5d  call    cs:__imp_CoUninitialize
0x140004d63  add     rsp, 28h
0x140004d67  retn
```
