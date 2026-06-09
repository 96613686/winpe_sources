# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x180011c80`
- end: `0x180011d4b`
- name: `?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z`
- size: `203`
- prototype: `char __fastcall(__int64, const void *, unsigned __int64)`
- caller_count: `12`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005280`
- `0x180005360`
- `0x18000687c`
- `0x180006c00`
- `0x180009494`
- `0x180009ec8`
- `0x18000a1c0`
- `0x18000a520`
- `0x18000b290`
- `0x18000ebf8`
- `0x18000ef08`
- `0x18000f418`

## callees

- `0x180001d06`
- `0x180001d12`
- `0x180002178`
- `0x1800114e8`
- `0x180011c80`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
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
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      a1,
      v15,
      a3);
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
0x180011c80  push    rbx
0x180011c82  push    rbp
0x180011c83  push    rsi
0x180011c84  push    rdi
0x180011c85  push    r12
0x180011c87  push    r14
0x180011c89  push    r15
0x180011c8b  sub     rsp, 30h
0x180011c8f  lea     r14, [rcx+10h]
0x180011c93  mov     r15, r8
0x180011c96  mov     r12, rdx
0x180011c99  mov     rdi, rcx
0x180011c9c  mov     bpl, 1
0x180011c9f  cmp     [rcx], r14
0x180011ca2  jnz     short loc_180011CAB
0x180011ca4  mov     eax, 7
0x180011ca9  jmp     short loc_180011CB4
0x180011cab  mov     rax, [r14]
0x180011cae  sub     rax, [rcx]
0x180011cb1  sar     rax, 1
0x180011cb4  cmp     r15, rax
0x180011cb7  ja      short loc_180011CD9
0x180011cb9  mov     rcx, [rcx]; void *
0x180011cbc  lea     rbx, [r8+r8]
0x180011cc0  mov     r8, rbx; Size
0x180011cc3  call    memmove_0
0x180011cc8  mov     rcx, [rdi]
0x180011ccb  add     rcx, rbx
0x180011cce  xor     esi, esi
0x180011cd0  mov     [rdi+8], rcx
0x180011cd4  mov     [rcx], si
0x180011cd7  jmp     short loc_180011D39
0x180011cd9  lea     rdx, [rsp+68h+var_48]
0x180011cde  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x180011ce3  mov     rbx, [rsp+68h+var_48]
0x180011ce8  xor     esi, esi
0x180011cea  test    rbx, rbx
0x180011ced  jz      short loc_180011D36
0x180011cef  add     r15, r15
0x180011cf2  mov     rdx, r12; Src
0x180011cf5  mov     r8, r15; Size
0x180011cf8  mov     rcx, rbx; void *
0x180011cfb  call    memcpy_0
0x180011d00  mov     [r15+rbx], si
0x180011d05  mov     rsi, [rsp+68h+var_40]
0x180011d0a  cmp     [rdi], r14
0x180011d0d  jz      short loc_180011D1E
0x180011d0f  mov     rcx, [rdi]; void *
0x180011d12  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011d19  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011d1e  lea     rax, [r15+rbx]
0x180011d22  mov     [rdi], rbx
0x180011d25  mov     [rdi+8], rax
0x180011d29  lea     rax, [rsi-1]
0x180011d2d  lea     rax, [rbx+rax*2]
0x180011d31  mov     [r14], rax
0x180011d34  jmp     short loc_180011D39
0x180011d36  mov     bpl, sil
0x180011d39  mov     al, bpl
0x180011d3c  add     rsp, 30h
0x180011d40  pop     r15
0x180011d42  pop     r14
0x180011d44  pop     r12
0x180011d46  pop     rdi
0x180011d47  pop     rsi
0x180011d48  pop     rbp
0x180011d49  pop     rbx
0x180011d4a  retn
```
