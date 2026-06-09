# AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath::Allocate(void)

- ea: `0x18000f710`
- end: `0x18000f761`
- name: `?Allocate@AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath@@SAPEAVNode@@XZ`
- size: `81`
- prototype: `struct Node *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f138`

## callees

- `0x180001078`
- `0x18000f710`

## pseudocode

```c
struct Node *AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath::Allocate(void)
{
  struct Node *result; // rax

  result = (struct Node *)operator new(0x28u);
  if ( result )
  {
    result->lpVtbl = (struct NodeVtbl *)&Node::`vftable';
    result[1].lpVtbl = 0;
    result[2].lpVtbl = 0;
    LODWORD(result[3].lpVtbl) = 1;
    HIDWORD(result[3].lpVtbl) = 9;
    LODWORD(result[4].lpVtbl) = 2;
    result->lpVtbl = (struct NodeVtbl *)&AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath::`vftable';
  }
  return result;
}

```

## disassembly

```asm
0x18000f710  sub     rsp, 28h
0x18000f714  mov     ecx, 28h ; '('; Size
0x18000f719  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f71e  test    rax, rax
0x18000f721  jz      short loc_18000F75C
0x18000f723  lea     rcx, ??_7Node@@6B@; const Node::`vftable'
0x18000f72a  mov     [rax], rcx
0x18000f72d  lea     rcx, ??_7AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath@@6B@; const AbbreviatedAbsoluteLocationPath__DoubleSlash_RelativeLocationPath::`vftable'
0x18000f734  mov     qword ptr [rax+8], 0
0x18000f73c  mov     qword ptr [rax+10h], 0
0x18000f744  mov     dword ptr [rax+18h], 1
0x18000f74b  mov     dword ptr [rax+1Ch], 9
0x18000f752  mov     dword ptr [rax+20h], 2
0x18000f759  mov     [rax], rcx
0x18000f75c  add     rsp, 28h
0x18000f760  retn
```
