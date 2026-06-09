# OBJECT::Compare(OBJECT const *)

- ea: `0x1800047e0`
- end: `0x1800047e6`
- name: `?Compare@OBJECT@@UEBAJPEBV1@@Z_0`
- size: `6`
- prototype: `int(OBJECT *__hidden this, const struct OBJECT *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ulib!?Compare@OBJECT@@UEBAJPEBV1@@Z` at `0x1800047e0`

## pseudocode

```c
// attributes: thunk
int __fastcall OBJECT::Compare(OBJECT *this, const struct OBJECT *a2)
{
  return __imp_?Compare@OBJECT@@UEBAJPEBV1@@Z(this, a2);
}

```

## disassembly

```asm
0x1800047e0  jmp     cs:__imp_?Compare@OBJECT@@UEBAJPEBV1@@Z
```
