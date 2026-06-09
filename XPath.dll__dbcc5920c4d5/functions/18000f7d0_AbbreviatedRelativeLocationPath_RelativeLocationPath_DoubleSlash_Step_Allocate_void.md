# AbbreviatedRelativeLocationPath__RelativeLocationPath_DoubleSlash_Step::Allocate(void)

- ea: `0x18000f7d0`
- end: `0x18000f821`
- name: `?Allocate@AbbreviatedRelativeLocationPath__RelativeLocationPath_DoubleSlash_Step@@SAPEAVNode@@XZ`
- size: `81`
- prototype: `struct Node *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f138`

## callees

- `0x180001078`
- `0x18000f7d0`

## pseudocode

```c
struct Node *AbbreviatedRelativeLocationPath__RelativeLocationPath_DoubleSlash_Step::Allocate(void)
{
  struct Node *result; // rax

  result = (struct Node *)operator new(0x28u);
  if ( result )
  {
    result->lpVtbl = (struct NodeVtbl *)&Node::`vftable';
    result[1].lpVtbl = 0;
    result[2].lpVtbl = 0;
    LODWORD(result[3].lpVtbl) = 1;
    HIDWORD(result[3].lpVtbl) = 10;
    LODWORD(result[4].lpVtbl) = 3;
    result->lpVtbl = (struct NodeVtbl *)&AbbreviatedRelativeLocationPath__RelativeLocationPath_DoubleSlash_Step::`vftable';
  }
  return result;
}

```

## disassembly

```asm
0x18000f7d0  sub     rsp, 28h
0x18000f7d4  mov     ecx, 28h ; '('; Size
0x18000f7d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f7de  test    rax, rax
0x18000f7e1  jz      short loc_18000F81C
0x18000f7e3  lea     rcx, ??_7Node@@6B@; const Node::`vftable'
0x18000f7ea  mov     [rax], rcx
0x18000f7ed  lea     rcx, ??_7AbbreviatedRelativeLocationPath__RelativeLocationPath_DoubleSlash_Step@@6B@; const AbbreviatedRelativeLocationPath__RelativeLocationPath_DoubleSlash_Step::`vftable'
0x18000f7f4  mov     qword ptr [rax+8], 0
0x18000f7fc  mov     qword ptr [rax+10h], 0
0x18000f804  mov     dword ptr [rax+18h], 1
0x18000f80b  mov     dword ptr [rax+1Ch], 0Ah
0x18000f812  mov     dword ptr [rax+20h], 3
0x18000f819  mov     [rax], rcx
0x18000f81c  add     rsp, 28h
0x18000f820  retn
```
