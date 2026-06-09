# std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::~_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>(void)

- ea: `0x18000d44c`
- end: `0x18000d4c4`
- name: `??1?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ`
- size: `120`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d4cc`
- `0x18000d4d8`
- `0x18000f3f8`

## callees

- `0x18000d44c`
- `0x18000d6f8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d480`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d480`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d4bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::~_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>(
        void **a1)
{
  _QWORD *v2; // rsi
  _QWORD *i; // rdi

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  for ( i = v2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    operator delete(v2);
  }
  *((_QWORD *)*a1 + 1) = *a1;
  *(_QWORD *)*a1 = *a1;
  *((_QWORD *)*a1 + 2) = *a1;
  a1[1] = 0;
  operator delete(*a1);
}

```

## disassembly

```asm
0x18000d44c  mov     [rsp+arg_0], rbx
0x18000d451  mov     [rsp+arg_8], rsi
0x18000d456  push    rdi
0x18000d457  sub     rsp, 20h
0x18000d45b  mov     rbx, rcx
0x18000d45e  mov     rax, [rcx]
0x18000d461  mov     rsi, [rax+8]
0x18000d465  mov     rdi, rsi
0x18000d468  cmp     byte ptr [rsi+19h], 0
0x18000d46c  jnz     short loc_18000D48F
0x18000d46e  mov     rdx, [rdi+10h]
0x18000d472  mov     rcx, rbx
0x18000d475  call    ?_Erase@?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@QEAGUAttribute@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::_Erase(std::_Tree_node<std::pair<ushort * const,Attribute>,void *> *)
0x18000d47a  mov     rdi, [rdi]
0x18000d47d  mov     rcx, rsi
0x18000d480  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d486  mov     rsi, rdi
0x18000d489  cmp     byte ptr [rdi+19h], 0
0x18000d48d  jz      short loc_18000D46E
0x18000d48f  mov     rax, [rbx]
0x18000d492  mov     [rax+8], rax
0x18000d496  mov     rax, [rbx]
0x18000d499  mov     [rax], rax
0x18000d49c  mov     rax, [rbx]
0x18000d49f  mov     [rax+10h], rax
0x18000d4a3  mov     qword ptr [rbx+8], 0
0x18000d4ab  mov     rcx, [rbx]
0x18000d4ae  mov     rbx, [rsp+28h+arg_0]
0x18000d4b3  mov     rsi, [rsp+28h+arg_8]
0x18000d4b8  add     rsp, 20h
0x18000d4bc  pop     rdi
0x18000d4bd  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
