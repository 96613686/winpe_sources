# ??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ

- ea: `0x1800085dc`
- end: `0x180008610`
- name: `??1?$vector@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops, service_task`

## callers

- `0x180022156`
- `0x1800221c6`
- `0x18002229a`
- `0x180022763`
- `0x180022799`
- `0x1800227bd`
- `0x1800227e3`
- `0x180022bd9`
- `0x180023133`
- `0x180023219`
- `0x18002323d`
- `0x1800232e3`
- `0x18002343a`

## callees

- `0x1800085dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800085ed`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800085ed`

## pseudocode

```c
void __fastcall __1__vector_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBW4FilterType__V__unique_ptr_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std__U__default_delete_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std___2__std___std___std___std___std__U___Wrap_alloc_V__allocator_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBW4FilterType__V__unique_ptr_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std__U__default_delete_V__vector_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std__V__allocator_V__unique_ptr_VFilterAgent__U__default_delete_VFilterAgent___std___std___2__std___2__std___std___std___std___std___std___2__std__QEAA_XZ(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800085dc  push    rbx
0x1800085de  sub     rsp, 20h
0x1800085e2  mov     rbx, rcx
0x1800085e5  mov     rcx, [rcx]
0x1800085e8  test    rcx, rcx
0x1800085eb  jz      short loc_18000860A
0x1800085ed  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800085f3  mov     qword ptr [rbx], 0
0x1800085fa  mov     qword ptr [rbx+8], 0
0x180008602  mov     qword ptr [rbx+10h], 0
0x18000860a  add     rsp, 20h
0x18000860e  pop     rbx
0x18000860f  retn
```
