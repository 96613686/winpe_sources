# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001b60`
- end: `0x180001b65`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `73`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004040`
- `0x180004080`
- `0x1800040c0`
- `0x180004100`
- `0x18000a384`
- `0x18000a418`
- `0x18000a6a0`
- `0x18000a6c4`
- `0x18000a820`
- `0x18000a850`
- `0x18000aab0`
- `0x18000aaf0`
- `0x18000ab30`
- `0x18000ba08`
- `0x18000c9d8`
- `0x18000ec0c`
- `0x18000f35c`
- `0x1800137dc`
- `0x180013970`
- `0x180013efc`
- `0x180013f88`
- `0x18001d274`
- `0x18001d298`
- `0x18001d324`
- `0x18001d3b0`
- `0x18001dddc`
- `0x18001e460`
- `0x18001e4bc`
- `0x18001e598`
- `0x18001e74c`
- `0x18001e960`
- `0x18001e9b0`
- `0x18001e9f0`
- `0x18001ea30`
- `0x18001ea70`
- `0x18001eab0`
- `0x18001eaf0`
- `0x18001eb30`
- `0x18001eb70`
- `0x18001ebb0`
- `0x18001ec40`
- `0x18001ecc0`
- `0x18001ed20`
- `0x18001f99c`
- `0x180020258`
- `0x1800204b0`
- `0x1800296fc`
- `0x180029758`
- `0x1800297b0`
- `0x1800297e0`

## callees

- `0x18000230c`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001b60  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
