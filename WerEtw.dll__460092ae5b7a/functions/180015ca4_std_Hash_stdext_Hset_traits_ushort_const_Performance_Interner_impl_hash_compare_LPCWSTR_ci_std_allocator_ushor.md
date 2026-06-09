# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)

- ea: `0x180015ca4`
- end: `0x180015d2d`
- name: `??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z`
- size: `137`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017afc`
- `0x18001877c`

## callees

- `0x180015ca4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015ce8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015d09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015ce8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180015d09`

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
0x180015ca4  push    rbx
0x180015ca6  push    rsi
0x180015ca7  push    rdi
0x180015ca8  push    r14
0x180015caa  sub     rsp, 28h
0x180015cae  mov     rax, [rcx+30h]
0x180015cb2  mov     rbx, rdx
0x180015cb5  mov     rsi, [rcx+18h]
0x180015cb9  and     rax, r9
0x180015cbc  mov     rdx, [rcx+8]
0x180015cc0  add     rax, rax
0x180015cc3  mov     r14, r8
0x180015cc6  mov     rdi, [rsi+rax*8+8]
0x180015ccb  cmp     rdi, rdx
0x180015cce  jnz     short loc_180015CDD
0x180015cd0  mov     [rbx], rdx
0x180015cd3  mov     qword ptr [rbx+8], 0
0x180015cdb  jmp     short loc_180015D20
0x180015cdd  mov     rsi, [rsi+rax*8]
0x180015ce1  mov     rdx, [rdi+10h]
0x180015ce5  mov     rcx, [r14]
0x180015ce8  call    cs:__imp__o__wcsicmp
0x180015cee  test    eax, eax
0x180015cf0  jns     short loc_180015D02
0x180015cf2  cmp     rdi, rsi
0x180015cf5  jz      short loc_180015CFD
0x180015cf7  mov     rdi, [rdi+8]
0x180015cfb  jmp     short loc_180015CE1
0x180015cfd  mov     [rbx], rdi
0x180015d00  jmp     short loc_180015CD3
0x180015d02  mov     rdx, [r14]
0x180015d05  mov     rcx, [rdi+10h]
0x180015d09  call    cs:__imp__o__wcsicmp
0x180015d0f  mov     rcx, [rdi]
0x180015d12  shr     eax, 1Fh
0x180015d15  mov     [rbx], rcx
0x180015d18  test    al, al
0x180015d1a  jnz     short loc_180015CD3
0x180015d1c  mov     [rbx+8], rdi
0x180015d20  mov     rax, rbx
0x180015d23  add     rsp, 28h
0x180015d27  pop     r14
0x180015d29  pop     rdi
0x180015d2a  pop     rsi
0x180015d2b  pop     rbx
0x180015d2c  retn
```
