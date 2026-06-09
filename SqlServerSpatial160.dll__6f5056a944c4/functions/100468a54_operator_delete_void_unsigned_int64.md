# operator delete(void *,unsigned __int64)

- ea: `0x100468a54`
- end: `0x100468a59`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `179`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1004013f0`
- `0x100401440`
- `0x100401550`
- `0x100401690`
- `0x1004016e0`
- `0x100401750`
- `0x100401800`
- `0x100401980`
- `0x100401a10`
- `0x100401a70`
- `0x100401ad0`
- `0x100401d50`
- `0x100401de0`
- `0x100401ed0`
- `0x100401fd0`
- `0x1004020e0`
- `0x100402160`
- `0x100402280`
- `0x100402390`
- `0x100402730`
- `0x100402820`
- `0x100402910`
- `0x100402a90`
- `0x100402b80`
- `0x100402c20`
- `0x100402c80`
- `0x1004030a0`
- `0x100403170`
- `0x1004032a0`
- `0x100403550`
- `0x1004036d0`
- `0x100403840`
- `0x100403b10`
- `0x100403e80`
- `0x100404240`
- `0x1004042f0`
- `0x100404680`
- `0x100404700`
- `0x100404760`
- `0x100404870`
- `0x1004048d0`
- `0x100404c70`
- `0x100404dc0`
- `0x100404e40`
- `0x100404ef0`
- `0x100404fd0`
- `0x1004050b0`
- `0x100405190`
- `0x100405280`
- `0x1004053c0`

## callees

- `0x100426c30`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x100468a54  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
