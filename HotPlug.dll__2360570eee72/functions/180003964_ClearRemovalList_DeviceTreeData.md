# ClearRemovalList(_DeviceTreeData *)

- ea: `0x180003964`
- end: `0x1800039af`
- name: `?ClearRemovalList@@YAXPEAU_DeviceTreeData@@@Z`
- size: `75`
- prototype: `void __fastcall(struct _DeviceTreeData *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d70`
- `0x180004664`
- `0x180006514`

## callees

- `0x180003964`
- `0x180006124`

## pseudocode

```c
void __fastcall ClearRemovalList(struct _DeviceTreeData *a1)
{
  __int64 v1; // rdx
  __int64 v3; // rbx

  v1 = *((_QWORD *)a1 + 6);
  if ( v1 )
  {
    do
    {
      v3 = *(_QWORD *)(v1 + 80);
      *(_QWORD *)(v1 + 80) = 0;
      InvalidateTreeItemRect(*((HWND *)a1 + 1), *(struct _TREEITEM **)(v1 + 88));
      v1 = v3;
    }
    while ( v3 != *((_QWORD *)a1 + 6) );
    *((_QWORD *)a1 + 6) = 0;
  }
}

```

## disassembly

```asm
0x180003964  mov     [rsp+arg_0], rbx
0x180003969  push    rdi
0x18000396a  sub     rsp, 20h
0x18000396e  mov     rdx, [rcx+30h]
0x180003972  mov     rdi, rcx
0x180003975  test    rdx, rdx
0x180003978  jz      short loc_1800039A4
0x18000397a  mov     rbx, [rdx+50h]
0x18000397e  mov     qword ptr [rdx+50h], 0
0x180003986  mov     rdx, [rdx+58h]; struct _TREEITEM *
0x18000398a  mov     rcx, [rdi+8]; hWnd
0x18000398e  call    ?InvalidateTreeItemRect@@YAXPEAUHWND__@@PEAU_TREEITEM@@@Z; InvalidateTreeItemRect(HWND__ *,_TREEITEM *)
0x180003993  mov     rdx, rbx
0x180003996  cmp     rbx, [rdi+30h]
0x18000399a  jnz     short loc_18000397A
0x18000399c  mov     qword ptr [rdi+30h], 0
0x1800039a4  mov     rbx, [rsp+28h+arg_0]
0x1800039a9  add     rsp, 20h
0x1800039ad  pop     rdi
0x1800039ae  retn
```
