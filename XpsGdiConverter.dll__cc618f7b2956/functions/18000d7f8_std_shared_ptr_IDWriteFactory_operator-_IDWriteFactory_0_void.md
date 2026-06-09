# std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)

- ea: `0x18000d7f8`
- end: `0x18000d7fc`
- name: `??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ`
- size: `4`
- prototype: ``
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x180013db4`
- `0x1800192f0`
- `0x180019f60`
- `0x18001dff0`
- `0x18001ec70`
- `0x180028338`
- `0x18002bcf0`
- `0x180031574`
- `0x1800328f4`
- `0x1800336ec`
- `0x180033a70`
- `0x18003426c`
- `0x180037e18`
- `0x180038418`
- `0x180038804`
- `0x18003890c`
- `0x180038e80`
- `0x1800393b4`
- `0x18003a18c`
- `0x18003aad8`
- `0x18003ac3c`
- `0x18003cd54`
- `0x18003ce80`
- `0x18003eca4`
- `0x1800415dc`
- `0x180044c48`
- `0x180045b18`
- `0x180046020`
- `0x1800478e9`

## pseudocode

```c
__int64 __fastcall std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x18000d7f8  mov     rax, [rcx]
0x18000d7fb  retn
```
