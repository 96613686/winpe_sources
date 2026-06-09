# std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)

- ea: `0x18000e7c8`
- end: `0x18000e7f6`
- name: `??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z`
- size: `46`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ec60`
- `0x18000eccc`
- `0x18000f8d4`
- `0x180010290`
- `0x1800109f4`
- `0x180010c08`
- `0x18001391c`
- `0x180013be0`
- `0x180014760`
- `0x180014a14`
- `0x1800152f4`
- `0x1800159d0`
- `0x180015de4`
- `0x180016cc8`
- `0x180018aa0`
- `0x180018e10`
- `0x180018fb0`
- `0x1800199e0`
- `0x180019db0`
- `0x18001a854`

## callees

- `0x18000e7c8`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x18000e7c8  mov     qword ptr [rcx], 0
0x18000e7cf  mov     qword ptr [rcx+8], 0
0x18000e7d7  mov     rax, [rdx+8]
0x18000e7db  test    rax, rax
0x18000e7de  jz      short loc_18000E7E4
0x18000e7e0  lock inc dword ptr [rax+8]
0x18000e7e4  mov     rax, [rdx]
0x18000e7e7  mov     [rcx], rax
0x18000e7ea  mov     rax, [rdx+8]
0x18000e7ee  mov     [rcx+8], rax
0x18000e7f2  mov     rax, rcx
0x18000e7f5  retn
```
