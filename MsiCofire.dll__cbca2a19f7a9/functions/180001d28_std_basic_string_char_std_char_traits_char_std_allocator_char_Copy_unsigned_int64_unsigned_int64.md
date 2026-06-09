# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001d28`
- end: `0x180001e1f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001f38`
- `0x180002030`

## callees

- `0x180001b48`
- `0x180001d28`
- `0x180001e88`
- `0x1800024ae`
- `0x180002576`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  _QWORD *v13; // rdx
  _QWORD v14[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v18; // [rsp+78h] [rbp+20h]

  v14[4] = -2;
  v3 = a3;
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
  try
  {
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
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
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180001d28  mov     rax, rsp
0x180001d2b  mov     [rax+18h], r8
0x180001d2f  mov     [rax+10h], rdx
0x180001d33  mov     [rax+8], rcx
0x180001d37  push    rbx
0x180001d38  push    rsi
0x180001d39  push    rdi
0x180001d3a  push    r14
0x180001d3c  sub     rsp, 38h
0x180001d40  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001d48  mov     r14, r8
0x180001d4b  mov     rdi, rdx
0x180001d4e  mov     rbx, rcx
0x180001d51  or      rdx, 0Fh
0x180001d55  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180001d5c  cmp     rdx, r9
0x180001d5f  ja      short loc_180001D95
0x180001d61  mov     rdi, rdx
0x180001d64  mov     r8, [rcx+18h]
0x180001d68  mov     rcx, r8
0x180001d6b  shr     rcx, 1
0x180001d6e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001d78  mul     rdx
0x180001d7b  shr     rdx, 1
0x180001d7e  cmp     rcx, rdx
0x180001d81  jbe     short loc_180001D95
0x180001d83  mov     rax, r9
0x180001d86  sub     rax, rcx
0x180001d89  cmp     r8, rax
0x180001d8c  lea     rdi, [rcx+r8]
0x180001d90  jbe     short loc_180001D95
0x180001d92  mov     rdi, r9
0x180001d95  lea     rcx, [rdi+1]; Size
0x180001d99  test    rcx, rcx
0x180001d9c  jz      short loc_180001DAD
0x180001d9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001da3  mov     rsi, rax
0x180001da6  test    rax, rax
0x180001da9  jz      short loc_180001E18
0x180001dab  jmp     short loc_180001DAF
0x180001dad  xor     esi, esi
0x180001daf  jmp     short loc_180001DC5
0x180001db1  mov     rbx, [rsp+58h+arg_0]
0x180001db6  mov     r14, [rsp+58h+arg_10]
0x180001dbb  mov     rdi, [rsp+58h+arg_8]
0x180001dc0  mov     rsi, [rsp+58h+arg_18]
0x180001dc5  test    r14, r14
0x180001dc8  jz      short loc_180001DE4
0x180001dca  cmp     qword ptr [rbx+18h], 10h
0x180001dcf  jb      short loc_180001DD6
0x180001dd1  mov     rdx, [rbx]
0x180001dd4  jmp     short loc_180001DD9
0x180001dd6  mov     rdx, rbx; Src
0x180001dd9  mov     r8, r14; Size
0x180001ddc  mov     rcx, rsi; void *
0x180001ddf  call    memcpy_0
0x180001de4  cmp     qword ptr [rbx+18h], 10h
0x180001de9  jb      short loc_180001DF3
0x180001deb  mov     rcx, [rbx]; void *
0x180001dee  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001df3  lea     rax, [rbx+10h]
0x180001df7  mov     [rbx], rsi
0x180001dfa  mov     [rbx+18h], rdi
0x180001dfe  cmp     rdi, 10h
0x180001e02  cmovnb  rbx, rsi
0x180001e06  mov     [rax], r14
0x180001e09  mov     byte ptr [rbx+r14], 0
0x180001e0e  add     rsp, 38h
0x180001e12  pop     r14
0x180001e14  pop     rdi
0x180001e15  pop     rsi
0x180001e16  pop     rbx
0x180001e17  retn
0x180001e18  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
