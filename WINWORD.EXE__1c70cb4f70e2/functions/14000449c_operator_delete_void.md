# operator delete(void *)

- ea: `0x14000449c`
- end: `0x1400044a9`
- name: `??3@YAXPEAX@Z`
- size: `13`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002720`

## callees

- `0x14000449c`

## import_xrefs

- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1400044a1`

## pseudocode

```c
void __fastcall operator delete(Mso::Memory *a1, void *a2)
{
  if ( a1 )
    Mso::Memory::Free(a1, a2);
}

```

## disassembly

```asm
0x14000449c  test    rcx, rcx
0x14000449f  jz      short locret_1400044A8
0x1400044a1  jmp     cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1400044a8  retn
```
