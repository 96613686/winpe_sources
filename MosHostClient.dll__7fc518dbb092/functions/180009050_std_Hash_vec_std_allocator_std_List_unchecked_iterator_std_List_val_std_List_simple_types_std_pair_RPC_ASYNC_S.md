# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>(void)

- ea: `0x180009050`
- end: `0x1800090ba`
- name: `??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_ODML_FIND_NEARBY_PACKAGES_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: `void __fastcall(char **)`
- caller_count: `10`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800092dc`
- `0x18000cc14`
- `0x180011391`
- `0x180011549`
- `0x1800116f0`
- `0x180011730`
- `0x180011770`
- `0x1800117b0`
- `0x1800117f0`
- `0x180011830`

## callees

- `0x1800029b4`
- `0x180009050`

## pseudocode

```c
void __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_ODML_FIND_NEARBY_PACKAGES_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>(
        char **a1)
{
  char *v1; // rdx
  char *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    if ( ((a1[2] - v1) & 0xFFFFFFFFFFFFFFF8uLL) < 0x1000 )
    {
      v3 = *a1;
    }
    else
    {
      v3 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v3 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180009050  push    rbx
0x180009052  sub     rsp, 20h
0x180009056  mov     rdx, [rcx]
0x180009059  mov     rbx, rcx
0x18000905c  test    rdx, rdx
0x18000905f  jz      short loc_1800090B4
0x180009061  mov     rax, [rcx+10h]
0x180009065  sub     rax, rdx
0x180009068  and     rax, 0FFFFFFFFFFFFFFF8h
0x18000906c  cmp     rax, 1000h
0x180009072  jb      short loc_180009092
0x180009074  mov     rcx, [rdx-8]
0x180009078  sub     rdx, rcx
0x18000907b  sub     rdx, 8
0x18000907f  cmp     rdx, 1Fh
0x180009083  ja      short loc_18000908B
0x180009085  add     rax, 27h ; '''
0x180009089  jmp     short loc_180009095
0x18000908b  mov     ecx, 5
0x180009090  int     29h; Win8: RtlFailFast(ecx)
0x180009092  mov     rcx, rdx; Block
0x180009095  mov     rdx, rax
0x180009098  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000909d  mov     qword ptr [rbx], 0
0x1800090a4  mov     qword ptr [rbx+8], 0
0x1800090ac  mov     qword ptr [rbx+10h], 0
0x1800090b4  add     rsp, 20h
0x1800090b8  pop     rbx
0x1800090b9  retn
```
