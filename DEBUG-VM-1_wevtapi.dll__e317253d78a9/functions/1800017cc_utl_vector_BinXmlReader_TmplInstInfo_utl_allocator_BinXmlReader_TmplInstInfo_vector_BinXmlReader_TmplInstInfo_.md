# utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)

- ea: `0x1800017cc`
- end: `0x1800017df`
- name: `??0?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ`
- size: `19`
- prototype: ``
- caller_count: `17`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180003158`
- `0x180003dc0`
- `0x1800071b0`
- `0x180008fd4`
- `0x18000a978`
- `0x18000c55c`
- `0x18000e73c`
- `0x180015f0c`
- `0x18001a50c`
- `0x18001a570`
- `0x18001a600`
- `0x18001e614`
- `0x1800210b0`
- `0x180023250`
- `0x1800243cc`
- `0x18002e234`
- `0x180033258`

## pseudocode

```c
_QWORD *__fastcall utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(
        _QWORD *a1)
{
  *a1 = -1;
  a1[1] = -1;
  a1[2] = -1;
  return a1;
}

```

## disassembly

```asm
0x1800017cc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800017d0  mov     [rcx], rax
0x1800017d3  mov     [rcx+8], rax
0x1800017d7  mov     [rcx+10h], rax
0x1800017db  mov     rax, rcx
0x1800017de  retn
```
