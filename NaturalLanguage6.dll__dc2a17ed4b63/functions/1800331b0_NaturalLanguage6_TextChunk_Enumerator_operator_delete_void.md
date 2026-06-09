# NaturalLanguage6::TextChunk::Enumerator::operator delete(void *)

- ea: `0x1800331b0`
- end: `0x1800331b7`
- name: `??3Enumerator@TextChunk@NaturalLanguage6@@SAXPEAX@Z`
- size: `7`
- prototype: `void __fastcall(void *)`
- caller_count: `20`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18009e980`
- `0x18009ef50`
- `0x18009ef70`
- `0x18009f232`
- `0x18009f98e`
- `0x18009fc05`
- `0x18009fe4e`
- `0x1800a00b0`
- `0x1800a01ab`
- `0x1800a0aa0`
- `0x1800a112f`
- `0x1800a1eff`
- `0x1800a3c1b`
- `0x1800a5289`
- `0x1800a8893`
- `0x1800a926f`
- `0x1800a9293`
- `0x1800a9f66`
- `0x1800ace65`
- `0x1800ace89`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800331b0`

## pseudocode

```c
// attributes: thunk
void __fastcall NaturalLanguage6::TextChunk::Enumerator::operator delete(void *a1)
{
  operator delete(a1);
}

```

## disassembly

```asm
0x1800331b0  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
