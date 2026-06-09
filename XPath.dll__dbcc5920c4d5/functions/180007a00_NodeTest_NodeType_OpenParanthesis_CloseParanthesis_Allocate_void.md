# NodeTest__NodeType_OpenParanthesis_CloseParanthesis::Allocate(void)

- ea: `0x180007a00`
- end: `0x180007a51`
- name: `?Allocate@NodeTest__NodeType_OpenParanthesis_CloseParanthesis@@SAPEAVNode@@XZ`
- size: `81`
- prototype: `struct Node *(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b14`
- `0x18000f138`

## callees

- `0x180001078`
- `0x180007a00`

## pseudocode

```c
struct Node *NodeTest__NodeType_OpenParanthesis_CloseParanthesis::Allocate(void)
{
  struct Node *result; // rax

  result = (struct Node *)operator new(0x28u);
  if ( result )
  {
    result->lpVtbl = (struct NodeVtbl *)&Node::`vftable';
    result[1].lpVtbl = 0;
    result[2].lpVtbl = 0;
    LODWORD(result[3].lpVtbl) = 1;
    HIDWORD(result[3].lpVtbl) = 6;
    LODWORD(result[4].lpVtbl) = 3;
    result->lpVtbl = (struct NodeVtbl *)&NodeTest__NodeType_OpenParanthesis_CloseParanthesis::`vftable';
  }
  return result;
}

```

## disassembly

```asm
0x180007a00  sub     rsp, 28h
0x180007a04  mov     ecx, 28h ; '('; Size
0x180007a09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a0e  test    rax, rax
0x180007a11  jz      short loc_180007A4C
0x180007a13  lea     rcx, ??_7Node@@6B@; const Node::`vftable'
0x180007a1a  mov     [rax], rcx
0x180007a1d  lea     rcx, ??_7NodeTest__NodeType_OpenParanthesis_CloseParanthesis@@6B@; const NodeTest__NodeType_OpenParanthesis_CloseParanthesis::`vftable'
0x180007a24  mov     qword ptr [rax+8], 0
0x180007a2c  mov     qword ptr [rax+10h], 0
0x180007a34  mov     dword ptr [rax+18h], 1
0x180007a3b  mov     dword ptr [rax+1Ch], 6
0x180007a42  mov     dword ptr [rax+20h], 3
0x180007a49  mov     [rax], rcx
0x180007a4c  add     rsp, 28h
0x180007a50  retn
```
