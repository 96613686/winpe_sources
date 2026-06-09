# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)

- ea: `0x180027c0c`
- end: `0x180027ca2`
- name: `??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180029af0`
- `0x18002a768`

## callees

- `0x180027c0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027c50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027c77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027c50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027c77`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi
  int v10; // eax

  v5 = a1[3];
  v6 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( (int)_o__wcsicmp(*a3, v8[2]) < 0 )
    {
      if ( v8 == v9 )
      {
        *a2 = v8;
        goto LABEL_3;
      }
      v8 = (_QWORD *)v8[1];
    }
    v10 = _o__wcsicmp(v8[2], *a3);
    *a2 = *v8;
    if ( v10 >= 0 )
    {
      a2[1] = v8;
      return a2;
    }
  }
LABEL_3:
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x180027c0c  push    rbx
0x180027c0e  push    rsi
0x180027c0f  push    rdi
0x180027c10  push    r14
0x180027c12  sub     rsp, 28h
0x180027c16  mov     rax, [rcx+30h]
0x180027c1a  mov     rbx, rdx
0x180027c1d  mov     rsi, [rcx+18h]
0x180027c21  and     rax, r9
0x180027c24  mov     rdx, [rcx+8]
0x180027c28  add     rax, rax
0x180027c2b  mov     r14, r8
0x180027c2e  mov     rdi, [rsi+rax*8+8]
0x180027c33  cmp     rdi, rdx
0x180027c36  jnz     short loc_180027C45
0x180027c38  mov     [rbx], rdx
0x180027c3b  mov     qword ptr [rbx+8], 0
0x180027c43  jmp     short loc_180027C94
0x180027c45  mov     rsi, [rsi+rax*8]
0x180027c49  mov     rdx, [rdi+10h]
0x180027c4d  mov     rcx, [r14]
0x180027c50  call    cs:__imp__o__wcsicmp
0x180027c57  nop     dword ptr [rax+rax+00h]
0x180027c5c  test    eax, eax
0x180027c5e  jns     short loc_180027C70
0x180027c60  cmp     rdi, rsi
0x180027c63  jz      short loc_180027C6B
0x180027c65  mov     rdi, [rdi+8]
0x180027c69  jmp     short loc_180027C49
0x180027c6b  mov     [rbx], rdi
0x180027c6e  jmp     short loc_180027C3B
0x180027c70  mov     rdx, [r14]
0x180027c73  mov     rcx, [rdi+10h]
0x180027c77  call    cs:__imp__o__wcsicmp
0x180027c7e  nop     dword ptr [rax+rax+00h]
0x180027c83  mov     rcx, [rdi]
0x180027c86  shr     eax, 1Fh
0x180027c89  mov     [rbx], rcx
0x180027c8c  test    al, al
0x180027c8e  jnz     short loc_180027C3B
0x180027c90  mov     [rbx+8], rdi
0x180027c94  mov     rax, rbx
0x180027c97  add     rsp, 28h
0x180027c9b  pop     r14
0x180027c9d  pop     rdi
0x180027c9e  pop     rsi
0x180027c9f  pop     rbx
0x180027ca0  retn
```
