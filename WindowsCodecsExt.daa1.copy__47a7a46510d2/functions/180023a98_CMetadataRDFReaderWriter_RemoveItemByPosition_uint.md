# CMetadataRDFReaderWriter::RemoveItemByPosition(uint)

- ea: `0x180023a98`
- end: `0x180023ad3`
- name: `?RemoveItemByPosition@CMetadataRDFReaderWriter@@IEAAXI@Z`
- size: `59`
- prototype: `void __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001e950`
- `0x18001ea50`

## callees

- `0x180033010`

## pseudocode

```c
void __fastcall CMetadataRDFReaderWriter::RemoveItemByPosition(CMetadataRDFReaderWriter *this, unsigned int a2)
{
  __int64 v3; // r8

  v3 = *(_QWORD *)(*((_QWORD *)this + 26) + 8LL * a2);
  *(_DWORD *)(v3 + 8) |= 2u;
  (*(void (__fastcall **)(CMetadataRDFReaderWriter *, __int64))(*(_QWORD *)this + 128LL))(this, 1);
  --*((_DWORD *)this + 43);
}

```

## disassembly

```asm
0x180023a98  push    rbx
0x180023a9a  sub     rsp, 20h
0x180023a9e  mov     rax, [rcx+0D0h]
0x180023aa5  mov     rbx, rcx
0x180023aa8  mov     edx, edx
0x180023aaa  mov     r8, [rax+rdx*8]
0x180023aae  mov     edx, 1
0x180023ab3  or      dword ptr [r8+8], 2
0x180023ab8  mov     rax, [rcx]
0x180023abb  mov     rax, [rax+80h]
0x180023ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ac7  dec     dword ptr [rbx+0ACh]
0x180023acd  add     rsp, 20h
0x180023ad1  pop     rbx
0x180023ad2  retn
```
