# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001dbc`
- end: `0x180001ea9`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001f40`
- `0x180002038`

## callees

- `0x180001218`
- `0x180001916`
- `0x180001dbc`
- `0x1800070c8`
- `0x1800070f4`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  _BYTE *v12; // rbp
  __int64 v13; // rcx
  void *v14; // rax
  unsigned __int64 v15; // rcx
  _BYTE *v16; // rdx
  _BYTE *v17; // rdx
  _BYTE v18[72]; // [rsp+0h] [rbp-48h] BYREF
  const void **v19; // [rsp+50h] [rbp+8h]
  __int64 v20; // [rsp+50h] [rbp+8h]
  unsigned __int64 v21; // [rsp+58h] [rbp+10h]
  size_t v22; // [rsp+60h] [rbp+18h]
  void *v23; // [rsp+68h] [rbp+20h]

  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  v9 = 0;
  if ( v4 != -1 )
  {
    v9 = operator new(v4 + 1);
    if ( !v9 )
    {
      try
      {
        std::_Xbad_alloc();
      }
      catch ( ... )
      {
        v17 = v18;
        v12 = v17;
        v13 = *((_QWORD *)v17 + 11);
        *((_QWORD *)v17 + 11) = v13;
        v14 = 0;
        v15 = v13 + 1;
        if ( !v15 || (v14 = operator new(v15)) != 0 )
        {
          *((_QWORD *)v12 + 13) = v14;
          v5 = v19;
          a3 = v22;
          v4 = v21;
          v9 = v23;
          goto LABEL_7;
        }
        try
        {
          std::_Xbad_alloc();
        }
        catch ( ... )
        {
          v16 = v18;
          LOBYTE(v16) = 1;
          std::string::_Tidy(v20, v16, 0);
          throw;
        }
      }
    }
  }
LABEL_7:
  if ( a3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, a3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = a3;
  *((_BYTE *)v5 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180001dbc  mov     [rsp+arg_10], r8
0x180001dc1  mov     [rsp+arg_8], rdx
0x180001dc6  mov     [rsp+arg_0], rcx
0x180001dcb  push    rbx
0x180001dcc  push    rsi
0x180001dcd  push    rdi
0x180001dce  push    r14
0x180001dd0  sub     rsp, 28h
0x180001dd4  mov     r14, r8
0x180001dd7  mov     rdi, rdx
0x180001dda  mov     rbx, rcx
0x180001ddd  or      rdx, 0Fh
0x180001de1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001de8  cmp     rdx, r9
0x180001deb  ja      short loc_180001E21
0x180001ded  mov     rdi, rdx
0x180001df0  mov     r8, [rcx+18h]
0x180001df4  mov     rcx, r8
0x180001df7  shr     rcx, 1
0x180001dfa  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001e04  mul     rdx
0x180001e07  shr     rdx, 1
0x180001e0a  cmp     rcx, rdx
0x180001e0d  jbe     short loc_180001E21
0x180001e0f  mov     rax, r9
0x180001e12  sub     rax, rcx
0x180001e15  cmp     r8, rax
0x180001e18  lea     rdi, [rcx+r8]
0x180001e1c  jbe     short loc_180001E21
0x180001e1e  mov     rdi, r9
0x180001e21  lea     rcx, [rdi+1]; unsigned __int64
0x180001e25  xor     esi, esi
0x180001e27  test    rcx, rcx
0x180001e2a  jz      short loc_180001E39
0x180001e2c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e31  mov     rsi, rax
0x180001e34  test    rax, rax
0x180001e37  jz      short loc_180001EA2
0x180001e39  jmp     short loc_180001E4F
0x180001e3b  mov     rbx, [rsp+48h+arg_0]
0x180001e40  mov     r14, [rsp+48h+arg_10]
0x180001e45  mov     rdi, [rsp+48h+arg_8]
0x180001e4a  mov     rsi, [rsp+48h+arg_18]
0x180001e4f  test    r14, r14
0x180001e52  jz      short loc_180001E6E
0x180001e54  cmp     qword ptr [rbx+18h], 10h
0x180001e59  jb      short loc_180001E60
0x180001e5b  mov     rdx, [rbx]
0x180001e5e  jmp     short loc_180001E63
0x180001e60  mov     rdx, rbx; Src
0x180001e63  mov     r8, r14; Size
0x180001e66  mov     rcx, rsi; void *
0x180001e69  call    memcpy_0
0x180001e6e  cmp     qword ptr [rbx+18h], 10h
0x180001e73  jb      short loc_180001E7D
0x180001e75  mov     rcx, [rbx]; lpMem
0x180001e78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001e7d  lea     rax, [rbx+10h]
0x180001e81  mov     [rbx], rsi
0x180001e84  mov     [rbx+18h], rdi
0x180001e88  cmp     rdi, 10h
0x180001e8c  cmovnb  rbx, rsi
0x180001e90  mov     [rax], r14
0x180001e93  mov     byte ptr [rbx+r14], 0
0x180001e98  add     rsp, 28h
0x180001e9c  pop     r14
0x180001e9e  pop     rdi
0x180001e9f  pop     rsi
0x180001ea0  pop     rbx
0x180001ea1  retn
0x180001ea2  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
