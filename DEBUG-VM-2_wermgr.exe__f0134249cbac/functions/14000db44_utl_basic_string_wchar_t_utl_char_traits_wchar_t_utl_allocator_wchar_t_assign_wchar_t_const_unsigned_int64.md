# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)

- ea: `0x14000db44`
- end: `0x14000dc0f`
- name: `?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z`
- size: `203`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140007c50`
- `0x14000b70c`
- `0x14000c488`
- `0x14000c798`
- `0x140017de4`
- `0x14001817c`
- `0x140018c4c`
- `0x1400192b0`
- `0x140019e3c`
- `0x14001c23c`

## callees

- `0x140003224`
- `0x14000d7d8`
- `0x14000db44`
- `0x14001c9a8`
- `0x14001c9b4`

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
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(a1, v15, a3);
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
0x14000db44  push    rbx
0x14000db46  push    rbp
0x14000db47  push    rsi
0x14000db48  push    rdi
0x14000db49  push    r12
0x14000db4b  push    r14
0x14000db4d  push    r15
0x14000db4f  sub     rsp, 30h
0x14000db53  lea     r14, [rcx+10h]
0x14000db57  mov     r15, r8
0x14000db5a  mov     r12, rdx
0x14000db5d  mov     rdi, rcx
0x14000db60  mov     bpl, 1
0x14000db63  cmp     [rcx], r14
0x14000db66  jnz     short loc_14000DB6F
0x14000db68  mov     eax, 7
0x14000db6d  jmp     short loc_14000DB78
0x14000db6f  mov     rax, [r14]
0x14000db72  sub     rax, [rcx]
0x14000db75  sar     rax, 1
0x14000db78  cmp     r15, rax
0x14000db7b  ja      short loc_14000DB9D
0x14000db7d  mov     rcx, [rcx]; void *
0x14000db80  lea     rbx, [r8+r8]
0x14000db84  mov     r8, rbx; Size
0x14000db87  call    memmove_0
0x14000db8c  mov     rcx, [rdi]
0x14000db8f  add     rcx, rbx
0x14000db92  xor     esi, esi
0x14000db94  mov     [rdi+8], rcx
0x14000db98  mov     [rcx], si
0x14000db9b  jmp     short loc_14000DBFD
0x14000db9d  lea     rdx, [rsp+68h+var_48]
0x14000dba2  call    ?_GrowAlloc@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA?AU?$pair@PEA_W_K@2@_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowAlloc(unsigned __int64)
0x14000dba7  mov     rbx, [rsp+68h+var_48]
0x14000dbac  xor     esi, esi
0x14000dbae  test    rbx, rbx
0x14000dbb1  jz      short loc_14000DBFA
0x14000dbb3  add     r15, r15
0x14000dbb6  mov     rdx, r12; Src
0x14000dbb9  mov     r8, r15; Size
0x14000dbbc  mov     rcx, rbx; void *
0x14000dbbf  call    memcpy_0
0x14000dbc4  mov     [r15+rbx], si
0x14000dbc9  mov     rsi, [rsp+68h+var_40]
0x14000dbce  cmp     [rdi], r14
0x14000dbd1  jz      short loc_14000DBE2
0x14000dbd3  mov     rcx, [rdi]; void *
0x14000dbd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000dbdd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000dbe2  lea     rax, [r15+rbx]
0x14000dbe6  mov     [rdi], rbx
0x14000dbe9  mov     [rdi+8], rax
0x14000dbed  lea     rax, [rsi-1]
0x14000dbf1  lea     rax, [rbx+rax*2]
0x14000dbf5  mov     [r14], rax
0x14000dbf8  jmp     short loc_14000DBFD
0x14000dbfa  mov     bpl, sil
0x14000dbfd  mov     al, bpl
0x14000dc00  add     rsp, 30h
0x14000dc04  pop     r15
0x14000dc06  pop     r14
0x14000dc08  pop     r12
0x14000dc0a  pop     rdi
0x14000dc0b  pop     rsi
0x14000dc0c  pop     rbp
0x14000dc0d  pop     rbx
0x14000dc0e  retn
```
