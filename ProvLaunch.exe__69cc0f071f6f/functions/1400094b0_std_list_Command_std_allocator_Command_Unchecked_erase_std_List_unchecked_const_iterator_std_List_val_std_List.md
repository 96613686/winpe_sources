# std::list<Command,std::allocator<Command>>::_Unchecked_erase(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>)

- ea: `0x1400094b0`
- end: `0x1400094fb`
- name: `?_Unchecked_erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@2@@Z`
- size: `75`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000abca`

## callees

- `0x1400094b0`
- `0x14000a190`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400094e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400094e6`

## pseudocode

```c
void __fastcall std::list<Command>::_Unchecked_erase(void **a1, void *a2)
{
  if ( a2 != *a1 )
  {
    **((_QWORD **)a2 + 1) = *(_QWORD *)a2;
    *(_QWORD *)(*(_QWORD *)a2 + 8LL) = *((_QWORD *)a2 + 1);
    Command::~Command((void **)a2 + 2);
    operator delete(a2);
    a1[1] = (char *)a1[1] - 1;
  }
}

```

## disassembly

```asm
0x1400094b0  mov     [rsp+arg_0], rbx
0x1400094b5  push    rdi
0x1400094b6  sub     rsp, 20h
0x1400094ba  mov     rbx, rdx
0x1400094bd  mov     rdi, rcx
0x1400094c0  cmp     rdx, [rcx]
0x1400094c3  jz      short loc_1400094F0
0x1400094c5  mov     rdx, [rdx+8]
0x1400094c9  lea     rcx, [rbx+10h]; this
0x1400094cd  mov     rax, [rbx]
0x1400094d0  mov     [rdx], rax
0x1400094d3  mov     rdx, [rbx]
0x1400094d6  mov     rax, [rbx+8]
0x1400094da  mov     [rdx+8], rax
0x1400094de  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x1400094e3  mov     rcx, rbx
0x1400094e6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400094ec  dec     qword ptr [rdi+8]
0x1400094f0  mov     rbx, [rsp+28h+arg_0]
0x1400094f5  add     rsp, 20h
0x1400094f9  pop     rdi
0x1400094fa  retn
```
