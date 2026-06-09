# List<InvasivePtr<XPathNodeIteratorBase>>::Clear(void)

- ea: `0x180008000`
- end: `0x18000804e`
- name: `?Clear@?$List@V?$InvasivePtr@VXPathNodeIteratorBase@@@@@@QEAAXXZ`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800068a8`
- `0x18000cb64`

## callees

- `0x1800010b8`
- `0x180006918`
- `0x180008000`

## pseudocode

```c
void __fastcall List<InvasivePtr<XPathNodeIteratorBase>>::Clear(__int64 a1)
{
  _DWORD *v2; // rcx
  __int64 v3; // rcx

  v2 = *(_DWORD **)a1;
  if ( !v2 || *v2 == 1 )
  {
    operator delete(v2);
    v3 = *(_QWORD *)(a1 + 8);
    if ( v3 )
      InvasivePtr<XPathNodeIteratorBase>::`vector deleting destructor'(v3);
  }
  else
  {
    --*v2;
  }
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x180008000  push    rbx
0x180008002  sub     rsp, 20h
0x180008006  mov     rbx, rcx
0x180008009  mov     rcx, [rcx]; Block
0x18000800c  test    rcx, rcx
0x18000800f  jz      short loc_18000801E
0x180008011  mov     eax, [rcx]
0x180008013  cmp     eax, 1
0x180008016  jz      short loc_18000801E
0x180008018  dec     eax
0x18000801a  mov     [rcx], eax
0x18000801c  jmp     short loc_180008031
0x18000801e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008023  mov     rcx, [rbx+8]
0x180008027  test    rcx, rcx
0x18000802a  jz      short loc_180008031
0x18000802c  call    ??_E?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAPEAXI@Z; InvasivePtr<XPathNodeIteratorBase>::`vector deleting destructor'(uint)
0x180008031  mov     qword ptr [rbx], 0
0x180008038  mov     qword ptr [rbx+8], 0
0x180008040  mov     qword ptr [rbx+10h], 0
0x180008048  add     rsp, 20h
0x18000804c  pop     rbx
0x18000804d  retn
```
