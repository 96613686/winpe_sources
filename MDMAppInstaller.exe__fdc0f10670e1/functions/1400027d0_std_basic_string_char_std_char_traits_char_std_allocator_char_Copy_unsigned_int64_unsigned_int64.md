# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1400027d0`
- end: `0x1400028ba`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `234`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400028c0`

## callees

- `0x140001ba8`
- `0x1400027d0`
- `0x140002920`
- `0x14001a892`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000284b`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000284b`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rbx
  const void **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  const void **result; // rax
  void *v12; // rax
  _BYTE *v13; // rdx
  _BYTE v14[72]; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( v9 )
        goto LABEL_29;
      std::_Xbad_alloc();
    }
    v9 = 0;
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v14;
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
LABEL_29:
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  LOBYTE(v6) = 1;
  std::string::_Tidy(v5, v6, 0);
  *v5 = v9;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v9;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1400027d0  mov     [rsp+arg_10], r8
0x1400027d5  mov     [rsp+arg_8], rdx
0x1400027da  mov     [rsp+arg_0], rcx
0x1400027df  push    rbx
0x1400027e0  push    rsi
0x1400027e1  push    rdi
0x1400027e2  push    r14
0x1400027e4  sub     rsp, 28h
0x1400027e8  mov     r14, r8
0x1400027eb  mov     rbx, rdx
0x1400027ee  mov     rdi, rcx
0x1400027f1  or      rdx, 0Fh
0x1400027f5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1400027fc  cmp     rdx, r9
0x1400027ff  ja      short loc_140002835
0x140002801  mov     rbx, rdx
0x140002804  mov     r8, [rcx+18h]
0x140002808  mov     rcx, r8
0x14000280b  shr     rcx, 1
0x14000280e  mov     rax, 0AAAAAAAAAAAAAAABh
0x140002818  mul     rdx
0x14000281b  shr     rdx, 1
0x14000281e  cmp     rcx, rdx
0x140002821  jbe     short loc_140002835
0x140002823  mov     rax, r9
0x140002826  sub     rax, rcx
0x140002829  cmp     r8, rax
0x14000282c  lea     rbx, [rcx+r8]
0x140002830  jbe     short loc_140002835
0x140002832  mov     rbx, r9
0x140002835  lea     rcx, [rbx+1]; Size
0x140002839  test    rcx, rcx
0x14000283c  jz      short loc_140002851
0x14000283e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002843  mov     rsi, rax
0x140002846  test    rax, rax
0x140002849  jnz     short loc_140002853
0x14000284b  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140002851  xor     esi, esi
0x140002853  jmp     short loc_140002869
0x140002855  mov     rdi, [rsp+48h+arg_0]
0x14000285a  mov     r14, [rsp+48h+arg_10]
0x14000285f  mov     rbx, [rsp+48h+arg_8]
0x140002864  mov     rsi, [rsp+48h+arg_18]
0x140002869  test    r14, r14
0x14000286c  jz      short loc_140002888
0x14000286e  cmp     qword ptr [rdi+18h], 10h
0x140002873  jb      short loc_14000287A
0x140002875  mov     rdx, [rdi]
0x140002878  jmp     short loc_14000287D
0x14000287a  mov     rdx, rdi; Src
0x14000287d  mov     r8, r14; Size
0x140002880  mov     rcx, rsi; void *
0x140002883  call    memcpy_0
0x140002888  xor     r8d, r8d
0x14000288b  mov     dl, 1
0x14000288d  mov     rcx, rdi
0x140002890  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140002895  mov     [rdi], rsi
0x140002898  mov     [rdi+18h], rbx
0x14000289c  mov     rax, rdi
0x14000289f  cmp     rbx, 10h
0x1400028a3  cmovnb  rax, rsi
0x1400028a7  mov     [rdi+10h], r14
0x1400028ab  mov     byte ptr [rax+r14], 0
0x1400028b0  add     rsp, 28h
0x1400028b4  pop     r14
0x1400028b6  pop     rdi
0x1400028b7  pop     rsi
0x1400028b8  pop     rbx
0x1400028b9  retn
```
