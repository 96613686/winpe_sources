# ArgumentsRecursive__ArgumentsRecursive_Comma_Argument::Allocate(void)

- ea: `0x18000fa10`
- end: `0x18000fa61`
- name: `?Allocate@ArgumentsRecursive__ArgumentsRecursive_Comma_Argument@@SAPEAVNode@@XZ`
- size: `81`
- prototype: `struct Node *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f138`

## callees

- `0x180001078`
- `0x18000fa10`

## pseudocode

```c
struct Node *ArgumentsRecursive__ArgumentsRecursive_Comma_Argument::Allocate(void)
{
  struct Node *result; // rax

  result = (struct Node *)operator new(0x28u);
  if ( result )
  {
    result->lpVtbl = (struct NodeVtbl *)&Node::`vftable';
    result[1].lpVtbl = 0;
    result[2].lpVtbl = 0;
    LODWORD(result[3].lpVtbl) = 1;
    HIDWORD(result[3].lpVtbl) = 15;
    LODWORD(result[4].lpVtbl) = 3;
    result->lpVtbl = (struct NodeVtbl *)&ArgumentsRecursive__ArgumentsRecursive_Comma_Argument::`vftable';
  }
  return result;
}

```

## disassembly

```asm
0x18000fa10  sub     rsp, 28h
0x18000fa14  mov     ecx, 28h ; '('; Size
0x18000fa19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fa1e  test    rax, rax
0x18000fa21  jz      short loc_18000FA5C
0x18000fa23  lea     rcx, ??_7Node@@6B@; const Node::`vftable'
0x18000fa2a  mov     [rax], rcx
0x18000fa2d  lea     rcx, ??_7ArgumentsRecursive__ArgumentsRecursive_Comma_Argument@@6B@; const ArgumentsRecursive__ArgumentsRecursive_Comma_Argument::`vftable'
0x18000fa34  mov     qword ptr [rax+8], 0
0x18000fa3c  mov     qword ptr [rax+10h], 0
0x18000fa44  mov     dword ptr [rax+18h], 1
0x18000fa4b  mov     dword ptr [rax+1Ch], 0Fh
0x18000fa52  mov     dword ptr [rax+20h], 3
0x18000fa59  mov     [rax], rcx
0x18000fa5c  add     rsp, 28h
0x18000fa60  retn
```
