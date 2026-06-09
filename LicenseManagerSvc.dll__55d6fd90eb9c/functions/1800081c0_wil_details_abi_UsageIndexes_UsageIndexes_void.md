# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800081c0`
- end: `0x180008217`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008090`
- `0x180009738`
- `0x180009e0c`
- `0x1800178c7`

## callees

- `0x180002744`
- `0x1800081c0`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v2 )
    MemoryFree(v2);
  v3 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v3 )
    MemoryFree(v3);
  v4 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v4 )
    MemoryFree(v4);
}

```

## disassembly

```asm
0x1800081c0  push    rbx
0x1800081c2  sub     rsp, 20h
0x1800081c6  mov     rbx, rcx
0x1800081c9  mov     rcx, [rcx+0B0h]; void *
0x1800081d0  mov     qword ptr [rbx+0B0h], 0
0x1800081db  test    rcx, rcx
0x1800081de  jz      short loc_1800081E5
0x1800081e0  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800081e5  mov     rcx, [rbx+70h]; void *
0x1800081e9  mov     qword ptr [rbx+70h], 0
0x1800081f1  test    rcx, rcx
0x1800081f4  jz      short loc_1800081FB
0x1800081f6  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800081fb  mov     rcx, [rbx+30h]; void *
0x1800081ff  mov     qword ptr [rbx+30h], 0
0x180008207  test    rcx, rcx
0x18000820a  jz      short loc_180008211
0x18000820c  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180008211  add     rsp, 20h
0x180008215  pop     rbx
0x180008216  retn
```
