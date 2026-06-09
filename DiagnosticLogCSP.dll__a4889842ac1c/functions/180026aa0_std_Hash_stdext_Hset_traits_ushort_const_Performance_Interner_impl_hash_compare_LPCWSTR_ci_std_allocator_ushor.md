# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)

- ea: `0x180026aa0`
- end: `0x180026b29`
- name: `??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z`
- size: `137`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180028904`
- `0x18002957c`

## callees

- `0x180026aa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026ae4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026b05`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026ae4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026b05`

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
0x180026aa0  push    rbx
0x180026aa2  push    rsi
0x180026aa3  push    rdi
0x180026aa4  push    r14
0x180026aa6  sub     rsp, 28h
0x180026aaa  mov     rax, [rcx+30h]
0x180026aae  mov     rbx, rdx
0x180026ab1  mov     rsi, [rcx+18h]
0x180026ab5  and     rax, r9
0x180026ab8  mov     rdx, [rcx+8]
0x180026abc  add     rax, rax
0x180026abf  mov     r14, r8
0x180026ac2  mov     rdi, [rsi+rax*8+8]
0x180026ac7  cmp     rdi, rdx
0x180026aca  jnz     short loc_180026AD9
0x180026acc  mov     [rbx], rdx
0x180026acf  mov     qword ptr [rbx+8], 0
0x180026ad7  jmp     short loc_180026B1C
0x180026ad9  mov     rsi, [rsi+rax*8]
0x180026add  mov     rdx, [rdi+10h]
0x180026ae1  mov     rcx, [r14]
0x180026ae4  call    cs:__imp__o__wcsicmp
0x180026aea  test    eax, eax
0x180026aec  jns     short loc_180026AFE
0x180026aee  cmp     rdi, rsi
0x180026af1  jz      short loc_180026AF9
0x180026af3  mov     rdi, [rdi+8]
0x180026af7  jmp     short loc_180026ADD
0x180026af9  mov     [rbx], rdi
0x180026afc  jmp     short loc_180026ACF
0x180026afe  mov     rdx, [r14]
0x180026b01  mov     rcx, [rdi+10h]
0x180026b05  call    cs:__imp__o__wcsicmp
0x180026b0b  mov     rcx, [rdi]
0x180026b0e  shr     eax, 1Fh
0x180026b11  mov     [rbx], rcx
0x180026b14  test    al, al
0x180026b16  jnz     short loc_180026ACF
0x180026b18  mov     [rbx+8], rdi
0x180026b1c  mov     rax, rbx
0x180026b1f  add     rsp, 28h
0x180026b23  pop     r14
0x180026b25  pop     rdi
0x180026b26  pop     rsi
0x180026b27  pop     rbx
0x180026b28  retn
```
