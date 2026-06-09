# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)

- ea: `0x14000dc44`
- end: `0x14000dd0f`
- name: `?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z`
- size: `203`
- prototype: `char __fastcall(__int64, const void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14000cfc4`
- `0x14000d5b8`
- `0x14000fd68`

## callees

- `0x1400023f4`
- `0x14000db78`
- `0x14000dc44`
- `0x14001130c`
- `0x140011318`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
        __int64 a1,
        const void *a2,
        unsigned __int64 a3)
{
  _QWORD *v3; // r14
  char v7; // bp
  unsigned __int64 v8; // rax
  __int64 v9; // rbx
  _WORD *v10; // rcx
  char *v11; // rbx
  size_t v12; // r15
  void *v13; // rsi
  void *v15[9]; // [rsp+20h] [rbp-48h] BYREF

  v3 = (_QWORD *)(a1 + 16);
  v7 = 1;
  if ( *(_QWORD *)a1 == a1 + 16 )
    v8 = 7;
  else
    v8 = (__int64)(*v3 - *(_QWORD *)a1) >> 1;
  if ( a3 > v8 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(a1, v15);
    v11 = (char *)v15[0];
    if ( v15[0] )
    {
      v12 = 2 * a3;
      memcpy_0(v15[0], a2, v12);
      *(_WORD *)&v11[v12] = 0;
      v13 = v15[1];
      if ( *(_QWORD **)a1 != v3 )
        operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)a1 = v11;
      *(_QWORD *)(a1 + 8) = &v11[v12];
      *v3 = &v11[2 * ((__int64)v13 - 1)];
    }
    else
    {
      return 0;
    }
  }
  else
  {
    v9 = 2 * a3;
    memmove_0(*(void **)a1, a2, 2 * a3);
    v10 = (_WORD *)(v9 + *(_QWORD *)a1);
    *(_QWORD *)(a1 + 8) = v10;
    *v10 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x14000dc44  push    rbx
0x14000dc46  push    rbp
0x14000dc47  push    rsi
0x14000dc48  push    rdi
0x14000dc49  push    r12
0x14000dc4b  push    r14
0x14000dc4d  push    r15
0x14000dc4f  sub     rsp, 30h
0x14000dc53  lea     r14, [rcx+10h]
0x14000dc57  mov     r15, r8
0x14000dc5a  mov     r12, rdx
0x14000dc5d  mov     rdi, rcx
0x14000dc60  mov     bpl, 1
0x14000dc63  cmp     [rcx], r14
0x14000dc66  jnz     short loc_14000DC6F
0x14000dc68  mov     eax, 7
0x14000dc6d  jmp     short loc_14000DC78
0x14000dc6f  mov     rax, [r14]
0x14000dc72  sub     rax, [rcx]
0x14000dc75  sar     rax, 1
0x14000dc78  cmp     r15, rax
0x14000dc7b  ja      short loc_14000DC9D
0x14000dc7d  mov     rcx, [rcx]; void *
0x14000dc80  lea     rbx, [r8+r8]
0x14000dc84  mov     r8, rbx; Size
0x14000dc87  call    memmove_0
0x14000dc8c  mov     rcx, [rdi]
0x14000dc8f  add     rcx, rbx
0x14000dc92  xor     esi, esi
0x14000dc94  mov     [rdi+8], rcx
0x14000dc98  mov     [rcx], si
0x14000dc9b  jmp     short loc_14000DCFD
0x14000dc9d  lea     rdx, [rsp+68h+var_48]
0x14000dca2  call    ?_GrowAlloc@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA?AU?$pair@PEA_W_K@2@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(unsigned __int64)
0x14000dca7  mov     rbx, [rsp+68h+var_48]
0x14000dcac  xor     esi, esi
0x14000dcae  test    rbx, rbx
0x14000dcb1  jz      short loc_14000DCFA
0x14000dcb3  add     r15, r15
0x14000dcb6  mov     rdx, r12; Src
0x14000dcb9  mov     r8, r15; Size
0x14000dcbc  mov     rcx, rbx; void *
0x14000dcbf  call    memcpy_0
0x14000dcc4  mov     [r15+rbx], si
0x14000dcc9  mov     rsi, [rsp+68h+var_40]
0x14000dcce  cmp     [rdi], r14
0x14000dcd1  jz      short loc_14000DCE2
0x14000dcd3  mov     rcx, [rdi]; void *
0x14000dcd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dcdd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dce2  lea     rax, [r15+rbx]
0x14000dce6  mov     [rdi], rbx
0x14000dce9  mov     [rdi+8], rax
0x14000dced  lea     rax, [rsi-1]
0x14000dcf1  lea     rax, [rbx+rax*2]
0x14000dcf5  mov     [r14], rax
0x14000dcf8  jmp     short loc_14000DCFD
0x14000dcfa  mov     bpl, sil
0x14000dcfd  mov     al, bpl
0x14000dd00  add     rsp, 30h
0x14000dd04  pop     r15
0x14000dd06  pop     r14
0x14000dd08  pop     r12
0x14000dd0a  pop     rdi
0x14000dd0b  pop     rsi
0x14000dd0c  pop     rbp
0x14000dd0d  pop     rbx
0x14000dd0e  retn
```
