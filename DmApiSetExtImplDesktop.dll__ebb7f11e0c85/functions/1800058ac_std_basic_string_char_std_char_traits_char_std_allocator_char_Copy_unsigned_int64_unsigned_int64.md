# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800058ac`
- end: `0x18000599d`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `241`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005ae8`

## callees

- `0x180001184`
- `0x1800058ac`
- `0x180005bf8`
- `0x180009ee6`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005927`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005927`

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
0x1800058ac  mov     [rsp+arg_10], r8
0x1800058b1  mov     [rsp+arg_8], rdx
0x1800058b6  mov     [rsp+arg_0], rcx
0x1800058bb  push    rbx
0x1800058bc  push    rsi
0x1800058bd  push    rdi
0x1800058be  push    r14
0x1800058c0  sub     rsp, 28h
0x1800058c4  mov     r14, r8
0x1800058c7  mov     rbx, rdx
0x1800058ca  mov     rdi, rcx
0x1800058cd  or      rdx, 0Fh
0x1800058d1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800058d8  cmp     rdx, r9
0x1800058db  ja      short loc_180005911
0x1800058dd  mov     rbx, rdx
0x1800058e0  mov     r8, [rcx+18h]
0x1800058e4  mov     rcx, r8
0x1800058e7  shr     rcx, 1
0x1800058ea  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800058f4  mul     rdx
0x1800058f7  shr     rdx, 1
0x1800058fa  cmp     rcx, rdx
0x1800058fd  jbe     short loc_180005911
0x1800058ff  mov     rax, r9
0x180005902  sub     rax, rcx
0x180005905  cmp     r8, rax
0x180005908  lea     rbx, [rcx+r8]
0x18000590c  jbe     short loc_180005911
0x18000590e  mov     rbx, r9
0x180005911  lea     rcx, [rbx+1]; Size
0x180005915  test    rcx, rcx
0x180005918  jz      short loc_180005933
0x18000591a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000591f  mov     rsi, rax
0x180005922  test    rax, rax
0x180005925  jnz     short loc_180005935
0x180005927  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000592e  nop     dword ptr [rax+rax+00h]
0x180005933  xor     esi, esi
0x180005935  jmp     short loc_18000594B
0x180005937  mov     rdi, [rsp+48h+arg_0]
0x18000593c  mov     r14, [rsp+48h+arg_10]
0x180005941  mov     rbx, [rsp+48h+arg_8]
0x180005946  mov     rsi, [rsp+48h+arg_18]
0x18000594b  test    r14, r14
0x18000594e  jz      short loc_18000596A
0x180005950  cmp     qword ptr [rdi+18h], 10h
0x180005955  jb      short loc_18000595C
0x180005957  mov     rdx, [rdi]
0x18000595a  jmp     short loc_18000595F
0x18000595c  mov     rdx, rdi; Src
0x18000595f  mov     r8, r14; Size
0x180005962  mov     rcx, rsi; void *
0x180005965  call    memcpy_0
0x18000596a  xor     r8d, r8d
0x18000596d  mov     dl, 1
0x18000596f  mov     rcx, rdi
0x180005972  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180005977  mov     [rdi], rsi
0x18000597a  mov     [rdi+18h], rbx
0x18000597e  mov     rax, rdi
0x180005981  cmp     rbx, 10h
0x180005985  cmovnb  rax, rsi
0x180005989  mov     [rdi+10h], r14
0x18000598d  mov     byte ptr [rax+r14], 0
0x180005992  add     rsp, 28h
0x180005996  pop     r14
0x180005998  pop     rdi
0x180005999  pop     rsi
0x18000599a  pop     rbx
0x18000599b  retn
```
