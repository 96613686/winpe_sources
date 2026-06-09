# operator delete(void *,unsigned __int64)

- ea: `0x180001450`
- end: `0x180001455`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `27`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002388`
- `0x180002858`
- `0x1800029a0`
- `0x1800029d8`
- `0x180002f08`
- `0x180003d80`
- `0x180004620`
- `0x180004810`
- `0x1800050bc`
- `0x1800060e0`
- `0x180007440`
- `0x1800078c0`
- `0x180008410`
- `0x1800091b0`
- `0x1800091f4`
- `0x180009b88`
- `0x180009dd0`
- `0x180012cf0`
- `0x180012d34`
- `0x180014360`
- `0x18001e900`
- `0x18001e950`
- `0x18001eb2c`
- `0x18001f07c`
- `0x18001fc6c`
- `0x18001fd04`
- `0x18001fdc8`

## callees

- `0x1800014a8`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001450  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
