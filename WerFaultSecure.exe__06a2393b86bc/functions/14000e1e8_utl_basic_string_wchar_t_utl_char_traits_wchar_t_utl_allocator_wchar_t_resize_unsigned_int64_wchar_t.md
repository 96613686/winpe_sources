# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)

- ea: `0x14000e1e8`
- end: `0x14000e2a0`
- name: `?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z`
- size: `184`
- prototype: `char __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000cb38`
- `0x14000cc0c`
- `0x14000d5b8`

## callees

- `0x140007350`
- `0x14000e1e8`

## pseudocode

```c
char __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v4; // rdi
  char v5; // bp
  _QWORD *v6; // rdx
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  _WORD *v11; // rdi
  char result; // al
  _WORD *v13; // rdx

  v2 = a2;
  v4 = (__int64)(a1[1] - *a1) >> 1;
  v5 = 1;
  if ( v4 < a2 )
  {
    v6 = a1 + 2;
    v7 = 7;
    if ( (_QWORD *)*a1 == a1 + 2 )
      v8 = 7;
    else
      v8 = (__int64)(*v6 - *a1) >> 1;
    if ( v2 <= v8 )
      goto LABEL_15;
    if ( (_QWORD *)*a1 != v6 )
      v7 = (__int64)(*v6 - *a1) >> 1;
    v9 = 2 * v7 + 1;
    if ( v9 < v2 )
      v9 = v2;
    if ( v9 > 0x3FFFFFFFFFFFFFF7LL )
      v9 = 0x3FFFFFFFFFFFFFF7LL;
    if ( v2 <= v9
      && utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo((__int64)a1, v9) )
    {
LABEL_15:
      v10 = v2 - v4;
      if ( v2 != v4 )
      {
        v11 = (_WORD *)a1[1];
        while ( v10 )
        {
          *v11++ = 0;
          --v10;
        }
      }
    }
    else
    {
      v5 = 0;
      v2 = v4;
    }
  }
  result = v5;
  v13 = (_WORD *)(*a1 + 2 * v2);
  a1[1] = v13;
  *v13 = 0;
  return result;
}

```

## disassembly

```asm
0x14000e1e8  push    rbx
0x14000e1ea  push    rbp
0x14000e1eb  push    rsi
0x14000e1ec  push    rdi
0x14000e1ed  sub     rsp, 28h
0x14000e1f1  mov     rdi, [rcx+8]
0x14000e1f5  mov     rsi, rdx
0x14000e1f8  sub     rdi, [rcx]
0x14000e1fb  mov     rbx, rcx
0x14000e1fe  sar     rdi, 1
0x14000e201  mov     bpl, 1
0x14000e204  cmp     rdi, rdx
0x14000e207  jnb     short loc_14000E284
0x14000e209  lea     rdx, [rcx+10h]
0x14000e20d  mov     eax, 7
0x14000e212  cmp     [rcx], rdx
0x14000e215  jnz     short loc_14000E21B
0x14000e217  mov     ecx, eax
0x14000e219  jmp     short loc_14000E224
0x14000e21b  mov     rcx, [rdx]
0x14000e21e  sub     rcx, [rbx]
0x14000e221  sar     rcx, 1
0x14000e224  cmp     rsi, rcx
0x14000e227  jbe     short loc_14000E270
0x14000e229  cmp     [rbx], rdx
0x14000e22c  jz      short loc_14000E237
0x14000e22e  mov     rax, [rdx]
0x14000e231  sub     rax, [rbx]
0x14000e234  sar     rax, 1
0x14000e237  lea     rdx, ds:1[rax*2]
0x14000e23f  mov     rax, 3FFFFFFFFFFFFFF7h
0x14000e249  cmp     rdx, rsi
0x14000e24c  cmovb   rdx, rsi
0x14000e250  cmp     rdx, rax
0x14000e253  cmova   rdx, rax
0x14000e257  cmp     rsi, rdx
0x14000e25a  ja      short loc_14000E268
0x14000e25c  mov     rcx, rbx
0x14000e25f  call    ?_GrowTo@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@AEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_GrowTo(unsigned __int64)
0x14000e264  test    al, al
0x14000e266  jnz     short loc_14000E270
0x14000e268  xor     bpl, bpl
0x14000e26b  mov     rsi, rdi
0x14000e26e  jmp     short loc_14000E284
0x14000e270  mov     rcx, rsi
0x14000e273  sub     rcx, rdi
0x14000e276  jz      short loc_14000E284
0x14000e278  mov     rdi, [rbx+8]
0x14000e27c  xor     edx, edx
0x14000e27e  movzx   eax, dx
0x14000e281  rep stosw
0x14000e284  mov     rcx, [rbx]
0x14000e287  mov     al, bpl
0x14000e28a  lea     rdx, [rcx+rsi*2]
0x14000e28e  xor     ecx, ecx
0x14000e290  mov     [rbx+8], rdx
0x14000e294  mov     [rdx], cx
0x14000e297  add     rsp, 28h
0x14000e29b  pop     rdi
0x14000e29c  pop     rsi
0x14000e29d  pop     rbp
0x14000e29e  pop     rbx
0x14000e29f  retn
```
