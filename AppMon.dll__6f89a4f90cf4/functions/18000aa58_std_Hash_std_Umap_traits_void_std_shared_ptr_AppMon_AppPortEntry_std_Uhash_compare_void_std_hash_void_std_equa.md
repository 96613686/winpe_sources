# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(void * const &,unsigned __int64)

- ea: `0x18000aa58`
- end: `0x18000aab8`
- name: `??$_Find_last@PEAX@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@std@@@1@AEBQEAX_K@Z`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a900`
- `0x18000ac1c`
- `0x18000de20`

## callees

- `0x18000aa58`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Find_last<void *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  _QWORD *v4; // rcx

  v4 = *(_QWORD **)(qword_180016588 + 16 * (a4 & qword_1800165A0) + 8);
  if ( v4 == (_QWORD *)qword_180016578 )
  {
    *a2 = qword_180016578;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    while ( *a3 != v4[2] )
    {
      if ( v4 == *(_QWORD **)(qword_180016588 + 16 * (a4 & qword_1800165A0)) )
      {
        *a2 = v4;
        goto LABEL_3;
      }
      v4 = (_QWORD *)v4[1];
    }
    *a2 = *v4;
    a2[1] = v4;
  }
  return a2;
}

```

## disassembly

```asm
0x18000aa58  mov     rax, cs:qword_1800165A0
0x18000aa5f  mov     r10, r8
0x18000aa62  mov     r8, cs:qword_180016588
0x18000aa69  and     rax, r9
0x18000aa6c  mov     r9, cs:qword_180016578
0x18000aa73  add     rax, rax
0x18000aa76  mov     rcx, [r8+rax*8+8]
0x18000aa7b  cmp     rcx, r9
0x18000aa7e  jnz     short loc_18000AA8D
0x18000aa80  mov     [rdx], r9
0x18000aa83  mov     qword ptr [rdx+8], 0
0x18000aa8b  jmp     short loc_18000AAB4
0x18000aa8d  mov     r8, [r8+rax*8]
0x18000aa91  mov     rax, [r10]
0x18000aa94  cmp     rax, [rcx+10h]
0x18000aa98  jz      short loc_18000AAAA
0x18000aa9a  cmp     rcx, r8
0x18000aa9d  jz      short loc_18000AAA5
0x18000aa9f  mov     rcx, [rcx+8]
0x18000aaa3  jmp     short loc_18000AA94
0x18000aaa5  mov     [rdx], rcx
0x18000aaa8  jmp     short loc_18000AA83
0x18000aaaa  mov     rax, [rcx]
0x18000aaad  mov     [rdx], rax
0x18000aab0  mov     [rdx+8], rcx
0x18000aab4  mov     rax, rdx
0x18000aab7  retn
```
