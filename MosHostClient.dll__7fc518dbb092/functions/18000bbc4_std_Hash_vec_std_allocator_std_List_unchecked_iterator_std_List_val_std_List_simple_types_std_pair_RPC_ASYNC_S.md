# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>)

- ea: `0x18000bbc4`
- end: `0x18000bce7`
- name: `?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU_RPC_ASYNC_STATE@@V?$unique_ptr@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@U?$default_delete@URPC_ASYNC_STATE_DATA@?$RpcAsyncHelper@URPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC@@@@@std@@@std@@@std@@@std@@@std@@@2@@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180001e50`
- `0x180001f10`
- `0x180001fd0`
- `0x180002090`
- `0x180008d44`
- `0x18000bec8`
- `0x18000dd80`

## callees

- `0x18000294c`
- `0x1800029b4`
- `0x18000bbc4`
- `0x18000c110`

## pseudocode

```c
__int64 __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_RPC_ASYNC_STATE * const,std::unique_ptr<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA,std::default_delete<RpcAsyncHelper<RPC_MAPSPACKAGE_ADD_MAP_PACKAGE_ASYNC>::RPC_ASYNC_STATE_DATA>>>>>>>>::_Assign_grow(
        __int64 a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rdi
  __int64 v6; // rcx
  __int64 result; // rax
  unsigned __int64 v8; // rsi
  unsigned __int64 *v9; // rdi
  void *v10; // rax
  char *v11; // rax
  __int64 v12; // rcx
  _BYTE *v13; // rcx
  unsigned __int64 v14; // rcx

  v3 = *(_QWORD *)(a1 + 8);
  v6 = v3 - *(_QWORD *)a1;
  result = v6 >> 3;
  if ( v6 >> 3 >= a2 )
  {
    v14 = (unsigned __int64)(v6 + 7) >> 3;
    if ( *(_QWORD *)a1 > v3 )
      v14 = 0;
    if ( v14 )
    {
      result = a3;
      memset64(*(void **)a1, a3, v14);
    }
    return result;
  }
  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_25;
  v8 = 8 * a2;
  if ( 8 * a2 )
  {
    if ( v8 < 0x1000 )
    {
      v9 = (unsigned __int64 *)operator new(8 * a2);
      goto LABEL_10;
    }
    if ( v8 + 39 >= v8 )
    {
      v10 = operator new(v8 + 39);
      if ( !v10 )
        goto LABEL_13;
      v9 = (unsigned __int64 *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v9 - 1) = (unsigned __int64)v10;
      goto LABEL_10;
    }
LABEL_25:
    __scrt_throw_std_bad_array_new_length();
  }
  v9 = 0;
LABEL_10:
  v11 = *(char **)a1;
  v12 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
  if ( v12 )
  {
    if ( (unsigned __int64)(8 * v12) < 0x1000 )
    {
      v13 = *(_BYTE **)a1;
    }
    else
    {
      v13 = (_BYTE *)*((_QWORD *)v11 - 1);
      if ( (unsigned __int64)(v11 - v13 - 8) > 0x1F )
LABEL_13:
        __fastfail(5u);
    }
    operator delete(v13);
  }
  result = (__int64)&v9[v8 / 8];
  *(_QWORD *)a1 = v9;
  *(_QWORD *)(a1 + 8) = &v9[v8 / 8];
  *(_QWORD *)(a1 + 16) = &v9[v8 / 8];
  while ( v9 != (unsigned __int64 *)result )
    *v9++ = a3;
  return result;
}

```

## disassembly

```asm
0x18000bbc4  push    rbx
0x18000bbc6  push    rbp
0x18000bbc7  push    rsi
0x18000bbc8  push    rdi
0x18000bbc9  push    r14
0x18000bbcb  sub     rsp, 20h
0x18000bbcf  mov     rdi, [rcx+8]
0x18000bbd3  mov     r14, rcx
0x18000bbd6  mov     rcx, rdi
0x18000bbd9  mov     rbx, r8
0x18000bbdc  sub     rcx, [r14]
0x18000bbdf  mov     rax, rcx
0x18000bbe2  sar     rax, 3
0x18000bbe6  cmp     rax, rdx
0x18000bbe9  jnb     loc_18000BCB7
0x18000bbef  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000bbf9  cmp     rdx, rax
0x18000bbfc  ja      loc_18000BCE1
0x18000bc02  lea     rsi, ds:0[rdx*8]
0x18000bc0a  xor     ebp, ebp
0x18000bc0c  test    rsi, rsi
0x18000bc0f  jnz     short loc_18000BC15
0x18000bc11  mov     edi, ebp
0x18000bc13  jmp     short loc_18000BC4E
0x18000bc15  cmp     rsi, 1000h
0x18000bc1c  jb      short loc_18000BC43
0x18000bc1e  lea     rcx, [rsi+27h]; Size
0x18000bc22  cmp     rcx, rsi
0x18000bc25  jbe     loc_18000BCE1
0x18000bc2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc30  test    rax, rax
0x18000bc33  jz      short loc_18000BC89
0x18000bc35  lea     rdi, [rax+27h]
0x18000bc39  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000bc3d  mov     [rdi-8], rax
0x18000bc41  jmp     short loc_18000BC4E
0x18000bc43  mov     rcx, rsi; Size
0x18000bc46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc4b  mov     rdi, rax
0x18000bc4e  mov     rax, [r14]
0x18000bc51  mov     rcx, [r14+10h]
0x18000bc55  sub     rcx, rax
0x18000bc58  sar     rcx, 3
0x18000bc5c  test    rcx, rcx
0x18000bc5f  jz      short loc_18000BC98
0x18000bc61  lea     rdx, ds:0[rcx*8]
0x18000bc69  cmp     rdx, 1000h
0x18000bc70  jb      short loc_18000BC90
0x18000bc72  mov     rcx, [rax-8]
0x18000bc76  sub     rax, rcx
0x18000bc79  sub     rax, 8
0x18000bc7d  cmp     rax, 1Fh
0x18000bc81  ja      short loc_18000BC89
0x18000bc83  add     rdx, 27h ; '''
0x18000bc87  jmp     short loc_18000BC93
0x18000bc89  mov     ecx, 5
0x18000bc8e  int     29h; Win8: RtlFailFast(ecx)
0x18000bc90  mov     rcx, rax; Block
0x18000bc93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bc98  lea     rax, [rsi+rdi]
0x18000bc9c  mov     [r14], rdi
0x18000bc9f  mov     [r14+8], rax
0x18000bca3  mov     [r14+10h], rax
0x18000bca7  jmp     short loc_18000BCB0
0x18000bca9  mov     [rdi], rbx
0x18000bcac  add     rdi, 8
0x18000bcb0  cmp     rdi, rax
0x18000bcb3  jnz     short loc_18000BCA9
0x18000bcb5  jmp     short loc_18000BCD6
0x18000bcb7  add     rcx, 7
0x18000bcbb  xor     ebp, ebp
0x18000bcbd  shr     rcx, 3
0x18000bcc1  cmp     [r14], rdi
0x18000bcc4  cmova   rcx, rbp
0x18000bcc8  test    rcx, rcx
0x18000bccb  jz      short loc_18000BCD6
0x18000bccd  mov     rdi, [r14]
0x18000bcd0  mov     rax, rbx
0x18000bcd3  rep stosq
0x18000bcd6  add     rsp, 20h
0x18000bcda  pop     r14
0x18000bcdc  pop     rdi
0x18000bcdd  pop     rsi
0x18000bcde  pop     rbp
0x18000bcdf  pop     rbx
0x18000bce0  retn
0x18000bce1  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
