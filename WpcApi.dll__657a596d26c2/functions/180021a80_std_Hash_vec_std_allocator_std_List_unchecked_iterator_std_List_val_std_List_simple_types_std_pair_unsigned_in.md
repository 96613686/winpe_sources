# std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>)

- ea: `0x180021a80`
- end: `0x180021ba3`
- name: `?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@std@@@std@@@2@@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180020f84`
- `0x180021c30`

## callees

- `0x1800032c4`
- `0x1800036e4`
- `0x18000a970`
- `0x180021a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Private::ThreadInfo *>>>>>>::_Assign_grow(
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
0x180021a80  push    rbx
0x180021a82  push    rbp
0x180021a83  push    rsi
0x180021a84  push    rdi
0x180021a85  push    r14
0x180021a87  sub     rsp, 20h
0x180021a8b  mov     rdi, [rcx+8]
0x180021a8f  mov     r14, rcx
0x180021a92  mov     rcx, rdi
0x180021a95  mov     rbx, r8
0x180021a98  sub     rcx, [r14]
0x180021a9b  mov     rax, rcx
0x180021a9e  sar     rax, 3
0x180021aa2  cmp     rax, rdx
0x180021aa5  jnb     loc_180021B73
0x180021aab  mov     rax, 1FFFFFFFFFFFFFFFh
0x180021ab5  cmp     rdx, rax
0x180021ab8  ja      loc_180021B9D
0x180021abe  lea     rsi, ds:0[rdx*8]
0x180021ac6  xor     ebp, ebp
0x180021ac8  test    rsi, rsi
0x180021acb  jnz     short loc_180021AD1
0x180021acd  mov     edi, ebp
0x180021acf  jmp     short loc_180021B0A
0x180021ad1  cmp     rsi, 1000h
0x180021ad8  jb      short loc_180021AFF
0x180021ada  lea     rcx, [rsi+27h]; Size
0x180021ade  cmp     rcx, rsi
0x180021ae1  jbe     loc_180021B9D
0x180021ae7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021aec  test    rax, rax
0x180021aef  jz      short loc_180021B45
0x180021af1  lea     rdi, [rax+27h]
0x180021af5  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180021af9  mov     [rdi-8], rax
0x180021afd  jmp     short loc_180021B0A
0x180021aff  mov     rcx, rsi; Size
0x180021b02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021b07  mov     rdi, rax
0x180021b0a  mov     rax, [r14]
0x180021b0d  mov     rcx, [r14+10h]
0x180021b11  sub     rcx, rax
0x180021b14  sar     rcx, 3
0x180021b18  test    rcx, rcx
0x180021b1b  jz      short loc_180021B54
0x180021b1d  lea     rdx, ds:0[rcx*8]
0x180021b25  cmp     rdx, 1000h
0x180021b2c  jb      short loc_180021B4C
0x180021b2e  mov     rcx, [rax-8]
0x180021b32  sub     rax, rcx
0x180021b35  sub     rax, 8
0x180021b39  cmp     rax, 1Fh
0x180021b3d  ja      short loc_180021B45
0x180021b3f  add     rdx, 27h ; '''
0x180021b43  jmp     short loc_180021B4F
0x180021b45  mov     ecx, 5
0x180021b4a  int     29h; Win8: RtlFailFast(ecx)
0x180021b4c  mov     rcx, rax; Block
0x180021b4f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021b54  lea     rax, [rsi+rdi]
0x180021b58  mov     [r14], rdi
0x180021b5b  mov     [r14+8], rax
0x180021b5f  mov     [r14+10h], rax
0x180021b63  jmp     short loc_180021B6C
0x180021b65  mov     [rdi], rbx
0x180021b68  add     rdi, 8
0x180021b6c  cmp     rdi, rax
0x180021b6f  jnz     short loc_180021B65
0x180021b71  jmp     short loc_180021B92
0x180021b73  add     rcx, 7
0x180021b77  xor     ebp, ebp
0x180021b79  shr     rcx, 3
0x180021b7d  cmp     [r14], rdi
0x180021b80  cmova   rcx, rbp
0x180021b84  test    rcx, rcx
0x180021b87  jz      short loc_180021B92
0x180021b89  mov     rdi, [r14]
0x180021b8c  mov     rax, rbx
0x180021b8f  rep stosq
0x180021b92  add     rsp, 20h
0x180021b96  pop     r14
0x180021b98  pop     rdi
0x180021b99  pop     rsi
0x180021b9a  pop     rbp
0x180021b9b  pop     rbx
0x180021b9c  retn
0x180021b9d  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
