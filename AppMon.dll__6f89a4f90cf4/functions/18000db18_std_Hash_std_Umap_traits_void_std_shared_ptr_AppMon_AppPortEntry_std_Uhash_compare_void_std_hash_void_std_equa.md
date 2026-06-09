# std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> * const,std::_List_node<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>,void *> * const)

- ea: `0x18000db18`
- end: `0x18000db73`
- name: `?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@PEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@V?$_Uhash_compare@PEAXU?$hash@PEAX@std@@U?$equal_to@PEAX@2@@2@V?$allocator@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@QEAXV?$shared_ptr@VAppPortEntry@AppMon@@@std@@@std@@PEAX@2@_KQEAU32@1@Z`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ac1c`

## callees

- `0x18000db18`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<void *,std::shared_ptr<AppMon::AppPortEntry>,std::_Uhash_compare<void *,std::hash<void *>,std::equal_to<void *>>,std::allocator<std::pair<void * const,std::shared_ptr<AppMon::AppPortEntry>>>,0>>::_Insert_new_node_before(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v4; // r10
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdx

  v4 = *(_QWORD **)(a3 + 8);
  ++qword_180016580;
  *a4 = a3;
  a4[1] = v4;
  *v4 = a4;
  *(_QWORD *)(a3 + 8) = a4;
  v5 = qword_180016588;
  v6 = 2 * (a2 & qword_1800165A0);
  v7 = *(_QWORD *)(qword_180016588 + 16 * (a2 & qword_1800165A0));
  if ( v7 == qword_180016578 )
  {
    *(_QWORD *)(qword_180016588 + 8 * v6) = a4;
LABEL_6:
    *(_QWORD *)(v5 + 8 * v6 + 8) = a4;
    return a4;
  }
  if ( v7 == a3 )
  {
    *(_QWORD *)(qword_180016588 + 8 * v6) = a4;
  }
  else if ( *(_QWORD **)(qword_180016588 + 8 * v6 + 8) == v4 )
  {
    goto LABEL_6;
  }
  return a4;
}

```

## disassembly

```asm
0x18000db18  mov     r10, [r8+8]
0x18000db1c  inc     cs:qword_180016580
0x18000db23  mov     [r9], r8
0x18000db26  mov     [r9+8], r10
0x18000db2a  mov     [r10], r9
0x18000db2d  mov     [r8+8], r9
0x18000db31  mov     rax, cs:qword_1800165A0
0x18000db38  mov     rcx, cs:qword_180016588
0x18000db3f  and     rax, rdx
0x18000db42  add     rax, rax
0x18000db45  mov     rdx, [rcx+rax*8]
0x18000db49  cmp     rdx, cs:qword_180016578
0x18000db50  jnz     short loc_18000DB58
0x18000db52  mov     [rcx+rax*8], r9
0x18000db56  jmp     short loc_18000DB6A
0x18000db58  cmp     rdx, r8
0x18000db5b  jnz     short loc_18000DB63
0x18000db5d  mov     [rcx+rax*8], r9
0x18000db61  jmp     short loc_18000DB6F
0x18000db63  cmp     [rcx+rax*8+8], r10
0x18000db68  jnz     short loc_18000DB6F
0x18000db6a  mov     [rcx+rax*8+8], r9
0x18000db6f  mov     rax, r9
0x18000db72  retn
```
