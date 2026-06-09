# operator delete(void *)

- ea: `0x140023ae0`
- end: `0x140023b00`
- name: `??3@YAXPEAX@Z`
- size: `32`
- prototype: `void __fastcall(void *)`
- caller_count: `294`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400020a8`
- `0x140003a78`
- `0x140004c3c`
- `0x140004f70`
- `0x140005ec8`
- `0x140010480`
- `0x14001275c`
- `0x14001a96c`
- `0x14001aedc`
- `0x14001b058`
- `0x14001ba38`
- `0x14001bb70`
- `0x14001c2c4`
- `0x14001c334`
- `0x14001c3a4`
- `0x14001c5a0`
- `0x14001c618`
- `0x14001c68c`
- `0x14001c9e0`
- `0x14001d764`
- `0x14001d9a4`
- `0x14001dcb4`
- `0x14001e910`
- `0x14001e9a4`
- `0x14001ea38`
- `0x14001eacc`
- `0x14001ee3c`
- `0x14001efb8`
- `0x14001f100`
- `0x14001f170`
- `0x14001f1e8`
- `0x14001f334`
- `0x14001f3cc`
- `0x14001fbf0`
- `0x14001fd60`
- `0x14001fea8`
- `0x14002035c`
- `0x1400203f0`
- `0x1400218e8`
- `0x1400223d0`
- `0x140023440`
- `0x1400234b0`
- `0x14002357c`
- `0x1400235ec`
- `0x1400236f4`
- `0x140023800`
- `0x140023904`
- `0x140023a0c`
- `0x140023a4c`
- `0x140023b80`

## callees

- `0x140023ae0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140023aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023aee`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    ExFreePoolWithTag(a1, 0x47696457u);
}

```

## disassembly

```asm
0x140023ae0  sub     rsp, 28h
0x140023ae4  test    rcx, rcx
0x140023ae7  jz      short loc_140023AFA
0x140023ae9  mov     edx, 47696457h; Tag
0x140023aee  call    cs:__imp_ExFreePoolWithTag
0x140023af5  nop     dword ptr [rax+rax+00h]
0x140023afa  add     rsp, 28h
0x140023afe  retn
```
