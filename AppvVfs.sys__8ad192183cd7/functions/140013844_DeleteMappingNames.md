# DeleteMappingNames

- ea: `0x140013844`
- end: `0x1400138da`
- name: `DeleteMappingNames`
- size: `150`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009368`
- `0x14001376c`

## callees

- `0x140013844`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001385a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001387b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001389d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001385a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001387b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001389d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138bf`

## pseudocode

```c
void __fastcall DeleteMappingNames(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0x6E464656u);
    *(_QWORD *)a1 = 0;
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0x6E464656u);
    *(_QWORD *)(a1 + 8) = 0;
  }
  v4 = *(void **)(a1 + 16);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0x6E464656u);
    *(_QWORD *)(a1 + 16) = 0;
  }
  v5 = *(void **)(a1 + 24);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x6E464656u);
    *(_QWORD *)(a1 + 24) = 0;
  }
}

```

## disassembly

```asm
0x140013844  push    rbx
0x140013846  sub     rsp, 20h
0x14001384a  mov     rbx, rcx
0x14001384d  mov     rcx, [rcx]; P
0x140013850  test    rcx, rcx
0x140013853  jz      short loc_14001386D
0x140013855  mov     edx, 6E464656h; Tag
0x14001385a  call    cs:__imp_ExFreePoolWithTag
0x140013861  nop     dword ptr [rax+rax+00h]
0x140013866  mov     qword ptr [rbx], 0
0x14001386d  mov     rcx, [rbx+8]; P
0x140013871  test    rcx, rcx
0x140013874  jz      short loc_14001388F
0x140013876  mov     edx, 6E464656h; Tag
0x14001387b  call    cs:__imp_ExFreePoolWithTag
0x140013882  nop     dword ptr [rax+rax+00h]
0x140013887  mov     qword ptr [rbx+8], 0
0x14001388f  mov     rcx, [rbx+10h]; P
0x140013893  test    rcx, rcx
0x140013896  jz      short loc_1400138B1
0x140013898  mov     edx, 6E464656h; Tag
0x14001389d  call    cs:__imp_ExFreePoolWithTag
0x1400138a4  nop     dword ptr [rax+rax+00h]
0x1400138a9  mov     qword ptr [rbx+10h], 0
0x1400138b1  mov     rcx, [rbx+18h]; P
0x1400138b5  test    rcx, rcx
0x1400138b8  jz      short loc_1400138D3
0x1400138ba  mov     edx, 6E464656h; Tag
0x1400138bf  call    cs:__imp_ExFreePoolWithTag
0x1400138c6  nop     dword ptr [rax+rax+00h]
0x1400138cb  mov     qword ptr [rbx+18h], 0
0x1400138d3  add     rsp, 20h
0x1400138d7  pop     rbx
0x1400138d8  retn
```
