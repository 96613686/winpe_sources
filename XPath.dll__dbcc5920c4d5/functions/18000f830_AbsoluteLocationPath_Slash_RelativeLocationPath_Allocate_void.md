# AbsoluteLocationPath__Slash_RelativeLocationPath::Allocate(void)

- ea: `0x18000f830`
- end: `0x18000f87e`
- name: `?Allocate@AbsoluteLocationPath__Slash_RelativeLocationPath@@SAPEAVNode@@XZ`
- size: `78`
- prototype: `struct Node *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f138`

## callees

- `0x180001078`
- `0x18000f830`

## pseudocode

```c
struct Node *AbsoluteLocationPath__Slash_RelativeLocationPath::Allocate(void)
{
  struct Node *result; // rax

  result = (struct Node *)operator new(0x28u);
  if ( result )
  {
    result->lpVtbl = (struct NodeVtbl *)&Node::`vftable';
    result[1].lpVtbl = 0;
    result[2].lpVtbl = 0;
    LODWORD(result[3].lpVtbl) = 1;
    HIDWORD(result[3].lpVtbl) = 1;
    result->lpVtbl = (struct NodeVtbl *)&AbsoluteLocationPath__Slash_RelativeLocationPath::`vftable';
    LODWORD(result[4].lpVtbl) = 2;
  }
  return result;
}

```

## disassembly

```asm
0x18000f830  sub     rsp, 28h
0x18000f834  mov     ecx, 28h ; '('; Size
0x18000f839  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f83e  test    rax, rax
0x18000f841  jz      short loc_18000F879
0x18000f843  lea     rcx, ??_7Node@@6B@; const Node::`vftable'
0x18000f84a  mov     [rax], rcx
0x18000f84d  mov     ecx, 1
0x18000f852  mov     qword ptr [rax+8], 0
0x18000f85a  mov     qword ptr [rax+10h], 0
0x18000f862  mov     [rax+18h], ecx
0x18000f865  mov     [rax+1Ch], ecx
0x18000f868  lea     rcx, ??_7AbsoluteLocationPath__Slash_RelativeLocationPath@@6B@; const AbsoluteLocationPath__Slash_RelativeLocationPath::`vftable'
0x18000f86f  mov     [rax], rcx
0x18000f872  mov     dword ptr [rax+20h], 2
0x18000f879  add     rsp, 28h
0x18000f87d  retn
```
