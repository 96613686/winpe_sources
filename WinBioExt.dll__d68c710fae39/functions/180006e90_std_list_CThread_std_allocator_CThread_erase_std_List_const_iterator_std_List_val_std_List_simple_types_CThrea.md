# std::list<CThread *,std::allocator<CThread *>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<CThread *>>>)

- ea: `0x180006e90`
- end: `0x180006ed4`
- name: `?erase@?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCThread@@@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCThread@@@std@@@std@@@2@@Z`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006c3c`

## callees

- `0x1800019e0`

## pseudocode

```c
_QWORD *__fastcall std::list<CThread *>::erase(__int64 a1, _QWORD *a2, __int64 *a3)
{
  __int64 v4; // rbx

  v4 = *a3;
  *(_QWORD *)a3[1] = *a3;
  *(_QWORD *)(*a3 + 8) = a3[1];
  --*(_QWORD *)(a1 + 8);
  operator delete(a3);
  *a2 = v4;
  return a2;
}

```

## disassembly

```asm
0x180006e90  mov     [rsp+arg_0], rbx
0x180006e95  push    rdi
0x180006e96  sub     rsp, 20h
0x180006e9a  mov     rax, [r8+8]
0x180006e9e  mov     rdi, rdx
0x180006ea1  mov     rbx, [r8]
0x180006ea4  mov     edx, 18h; unsigned __int64
0x180006ea9  mov     [rax], rbx
0x180006eac  mov     r9, [r8]
0x180006eaf  mov     rax, [r8+8]
0x180006eb3  mov     [r9+8], rax
0x180006eb7  dec     qword ptr [rcx+8]
0x180006ebb  mov     rcx, r8; void *
0x180006ebe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006ec3  mov     [rdi], rbx
0x180006ec6  mov     rax, rdi
0x180006ec9  mov     rbx, [rsp+28h+arg_0]
0x180006ece  add     rsp, 20h
0x180006ed2  pop     rdi
0x180006ed3  retn
```
