# memset

- ea: `0x18007b9de`
- end: `0x18007b9e4`
- name: `memset`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `42`
- callee_count: `0`
- tags: ``

## callers

- `0x180006040`
- `0x18000694c`
- `0x18000dbe4`
- `0x1800160a0`
- `0x180027c70`
- `0x180030f90`
- `0x1800406d0`
- `0x1800445c8`
- `0x1800473e8`
- `0x180048784`
- `0x180048d84`
- `0x1800495f0`
- `0x1800498b0`
- `0x18004a2f0`
- `0x18004c7a0`
- `0x1800503e4`
- `0x180050d68`
- `0x18005161c`
- `0x180052d60`
- `0x180053550`
- `0x180056c90`
- `0x180057030`
- `0x180057b78`
- `0x180057f08`
- `0x1800581d8`
- `0x1800583dc`
- `0x180058be0`
- `0x180058e2c`
- `0x18005ab78`
- `0x18005ba68`
- `0x18005f370`
- `0x180060b50`
- `0x180063a24`
- `0x180073de4`
- `0x180074730`
- `0x180074994`
- `0x1800767e0`
- `0x180076bb8`
- `0x180076fe4`
- `0x1800770b0`
- `0x18007949c`
- `0x18007b540`

## import_xrefs

- `VCRUNTIME140!memset` at `0x18007b9de`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset(void *a1, int Val, size_t Size)
{
  return __imp_memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18007b9de  jmp     cs:__imp_memset
```
