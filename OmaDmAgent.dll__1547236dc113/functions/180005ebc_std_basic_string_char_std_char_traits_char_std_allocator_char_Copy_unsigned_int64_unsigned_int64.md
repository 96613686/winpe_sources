# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180005ebc`
- end: `0x180005fad`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `241`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006124`

## callees

- `0x1800015e0`
- `0x180005ebc`
- `0x180006244`
- `0x18001f3c2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005f37`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005f37`

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
0x180005ebc  mov     [rsp+arg_10], r8
0x180005ec1  mov     [rsp+arg_8], rdx
0x180005ec6  mov     [rsp+arg_0], rcx
0x180005ecb  push    rbx
0x180005ecc  push    rsi
0x180005ecd  push    rdi
0x180005ece  push    r14
0x180005ed0  sub     rsp, 28h
0x180005ed4  mov     r14, r8
0x180005ed7  mov     rbx, rdx
0x180005eda  mov     rdi, rcx
0x180005edd  or      rdx, 0Fh
0x180005ee1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180005ee8  cmp     rdx, r9
0x180005eeb  ja      short loc_180005F21
0x180005eed  mov     rbx, rdx
0x180005ef0  mov     r8, [rcx+18h]
0x180005ef4  mov     rcx, r8
0x180005ef7  shr     rcx, 1
0x180005efa  mov     rax, 0AAAAAAAAAAAAAAABh
0x180005f04  mul     rdx
0x180005f07  shr     rdx, 1
0x180005f0a  cmp     rcx, rdx
0x180005f0d  jbe     short loc_180005F21
0x180005f0f  mov     rax, r9
0x180005f12  sub     rax, rcx
0x180005f15  cmp     r8, rax
0x180005f18  lea     rbx, [rcx+r8]
0x180005f1c  jbe     short loc_180005F21
0x180005f1e  mov     rbx, r9
0x180005f21  lea     rcx, [rbx+1]; Size
0x180005f25  test    rcx, rcx
0x180005f28  jz      short loc_180005F43
0x180005f2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f2f  mov     rsi, rax
0x180005f32  test    rax, rax
0x180005f35  jnz     short loc_180005F45
0x180005f37  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180005f3e  nop     dword ptr [rax+rax+00h]
0x180005f43  xor     esi, esi
0x180005f45  jmp     short loc_180005F5B
0x180005f47  mov     rdi, [rsp+48h+arg_0]
0x180005f4c  mov     r14, [rsp+48h+arg_10]
0x180005f51  mov     rbx, [rsp+48h+arg_8]
0x180005f56  mov     rsi, [rsp+48h+arg_18]
0x180005f5b  test    r14, r14
0x180005f5e  jz      short loc_180005F7A
0x180005f60  cmp     qword ptr [rdi+18h], 10h
0x180005f65  jb      short loc_180005F6C
0x180005f67  mov     rdx, [rdi]
0x180005f6a  jmp     short loc_180005F6F
0x180005f6c  mov     rdx, rdi; Src
0x180005f6f  mov     r8, r14; Size
0x180005f72  mov     rcx, rsi; void *
0x180005f75  call    memcpy_0
0x180005f7a  xor     r8d, r8d
0x180005f7d  mov     dl, 1
0x180005f7f  mov     rcx, rdi
0x180005f82  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180005f87  mov     [rdi], rsi
0x180005f8a  mov     [rdi+18h], rbx
0x180005f8e  mov     rax, rdi
0x180005f91  cmp     rbx, 10h
0x180005f95  cmovnb  rax, rsi
0x180005f99  mov     [rdi+10h], r14
0x180005f9d  mov     byte ptr [rax+r14], 0
0x180005fa2  add     rsp, 28h
0x180005fa6  pop     r14
0x180005fa8  pop     rdi
0x180005fa9  pop     rsi
0x180005faa  pop     rbx
0x180005fab  retn
```
