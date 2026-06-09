# operator delete(void *)

- ea: `0x1800109d0`
- end: `0x1800109f3`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `41`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800061f8`
- `0x18000ecb0`
- `0x18000f7b4`
- `0x18000f888`
- `0x18000f9d0`
- `0x18000fea4`
- `0x1800101ac`
- `0x18001039c`
- `0x18001237c`
- `0x180015910`
- `0x18001a454`
- `0x18001ada0`
- `0x180029100`
- `0x180029220`
- `0x1800292e0`
- `0x180029478`
- `0x180029e20`
- `0x180029f50`
- `0x18002d4e4`
- `0x180030b38`
- `0x180030bdc`
- `0x180031e00`
- `0x180031e10`
- `0x180033c90`
- `0x180033d20`
- `0x180034cb0`
- `0x180034de0`
- `0x1800355c4`
- `0x180035ccc`
- `0x180036b6c`
- `0x180037ff0`
- `0x180038c4c`
- `0x18003ce48`
- `0x18003f0d8`
- `0x18003f224`
- `0x1800478e4`
- `0x180047ce0`
- `0x180047dd0`
- `0x180047e00`
- `0x180048030`
- `0x180048060`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800109ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800109d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800109d9`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x1800109d0  push    rbx
0x1800109d2  sub     rsp, 20h
0x1800109d6  mov     rbx, rcx
0x1800109d9  call    cs:__imp_GetProcessHeap
0x1800109df  mov     r8, rbx
0x1800109e2  xor     edx, edx
0x1800109e4  mov     rcx, rax
0x1800109e7  add     rsp, 20h
0x1800109eb  pop     rbx
0x1800109ec  jmp     cs:__imp_HeapFree
```
