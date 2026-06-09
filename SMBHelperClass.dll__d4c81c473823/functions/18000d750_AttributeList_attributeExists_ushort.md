# AttributeList::attributeExists(ushort *)

- ea: `0x18000d750`
- end: `0x18000d7a8`
- name: `?attributeExists@AttributeList@@QEAAHPEAG@Z`
- size: `88`
- prototype: `__int64 __fastcall(AttributeList *__hidden this, unsigned __int16 *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1800056a0`
- `0x180005830`
- `0x180005a20`
- `0x1800067d0`
- `0x180008440`
- `0x1800088e0`
- `0x18000a000`
- `0x18000a900`
- `0x18000c550`
- `0x18000c7a8`
- `0x18000def4`
- `0x18000e010`

## callees

- `0x18000d3d8`
- `0x18000dc68`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000d795`
- `KERNEL32!ReleaseMutex` at `0x18000d795`

## pseudocode

```c
__int64 __fastcall AttributeList::attributeExists(void **this, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int16 *v6; // [rsp+30h] [rbp+8h] BYREF
  HANDLE hMutex; // [rsp+38h] [rbp+10h] BYREF
  char v8; // [rsp+40h] [rbp+18h] BYREF

  AutoMutex::AutoMutex((AutoMutex *)&hMutex, this[2], a3);
  v6 = a2;
  LODWORD(a2) = *(_QWORD *)std::_Tree<std::_Tmap_traits<unsigned short *,Attribute,ltString,std::allocator<std::pair<unsigned short * const,Attribute>>,0>>::find(
                             this,
                             &v8,
                             &v6) != (_QWORD)*this;
  ReleaseMutex(hMutex);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x18000d750  mov     [rsp+arg_18], rbx
0x18000d755  push    rdi
0x18000d756  sub     rsp, 20h
0x18000d75a  mov     rbx, rdx
0x18000d75d  mov     rdi, rcx
0x18000d760  mov     rdx, [rcx+10h]; void *
0x18000d764  lea     rcx, [rsp+28h+hMutex]; this
0x18000d769  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000d76e  lea     r8, [rsp+28h+arg_0]
0x18000d773  mov     [rsp+28h+arg_0], rbx
0x18000d778  lea     rdx, [rsp+28h+arg_10]
0x18000d77d  mov     rcx, rdi
0x18000d780  call    ?find@?$_Tree@V?$_Tmap_traits@PEAGUAttribute@@UltString@@V?$allocator@U?$pair@QEAGUAttribute@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAGUAttribute@@@std@@@std@@@std@@@2@AEBQEAG@Z; std::_Tree<std::_Tmap_traits<ushort *,Attribute,ltString,std::allocator<std::pair<ushort * const,Attribute>>,0>>::find(ushort * const &)
0x18000d785  mov     rcx, [rdi]
0x18000d788  xor     ebx, ebx
0x18000d78a  cmp     [rax], rcx
0x18000d78d  mov     rcx, [rsp+28h+hMutex]; hMutex
0x18000d792  setnz   bl
0x18000d795  call    cs:__imp_ReleaseMutex
0x18000d79b  mov     eax, ebx
0x18000d79d  mov     rbx, [rsp+28h+arg_18]
0x18000d7a2  add     rsp, 20h
0x18000d7a6  pop     rdi
0x18000d7a7  retn
```
