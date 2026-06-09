# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000613c`
- end: `0x14000622c`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400062f0`
- `0x1400063e8`

## callees

- `0x140001e40`
- `0x140001fe8`
- `0x140002656`
- `0x14000613c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400061fa`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400061fa`

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
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
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
      v13 = &v14;
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
0x14000613c  mov     [rsp+arg_10], r8
0x140006141  mov     [rsp+arg_8], rdx
0x140006146  mov     [rsp+arg_0], rcx
0x14000614b  push    rbx
0x14000614c  push    rsi
0x14000614d  push    rdi
0x14000614e  push    r14
0x140006150  sub     rsp, 28h
0x140006154  mov     r14, r8
0x140006157  mov     rdi, rdx
0x14000615a  mov     rbx, rcx
0x14000615d  or      rdx, 0Fh
0x140006161  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140006168  cmp     rdx, r9
0x14000616b  ja      short loc_1400061A1
0x14000616d  mov     rdi, rdx
0x140006170  mov     r8, [rcx+18h]
0x140006174  mov     rcx, r8
0x140006177  shr     rcx, 1
0x14000617a  mov     rax, 0AAAAAAAAAAAAAAABh
0x140006184  mul     rdx
0x140006187  shr     rdx, 1
0x14000618a  cmp     rcx, rdx
0x14000618d  jbe     short loc_1400061A1
0x14000618f  mov     rax, r9
0x140006192  sub     rax, rcx
0x140006195  cmp     r8, rax
0x140006198  lea     rdi, [rcx+r8]
0x14000619c  jbe     short loc_1400061A1
0x14000619e  mov     rdi, r9
0x1400061a1  lea     rcx, [rdi+1]; Size
0x1400061a5  test    rcx, rcx
0x1400061a8  jz      short loc_1400061B9
0x1400061aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400061af  mov     rsi, rax
0x1400061b2  test    rax, rax
0x1400061b5  jz      short loc_140006225
0x1400061b7  jmp     short loc_1400061BB
0x1400061b9  xor     esi, esi
0x1400061bb  jmp     short loc_1400061D1
0x1400061bd  mov     rbx, [rsp+48h+arg_0]
0x1400061c2  mov     r14, [rsp+48h+arg_10]
0x1400061c7  mov     rdi, [rsp+48h+arg_8]
0x1400061cc  mov     rsi, [rsp+48h+arg_18]
0x1400061d1  test    r14, r14
0x1400061d4  jz      short loc_1400061F0
0x1400061d6  cmp     qword ptr [rbx+18h], 10h
0x1400061db  jb      short loc_1400061E2
0x1400061dd  mov     rdx, [rbx]
0x1400061e0  jmp     short loc_1400061E5
0x1400061e2  mov     rdx, rbx; Src
0x1400061e5  mov     r8, r14; Size
0x1400061e8  mov     rcx, rsi; void *
0x1400061eb  call    memcpy_0
0x1400061f0  cmp     qword ptr [rbx+18h], 10h
0x1400061f5  jb      short loc_140006200
0x1400061f7  mov     rcx, [rbx]
0x1400061fa  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006200  lea     rax, [rbx+10h]
0x140006204  mov     [rbx], rsi
0x140006207  mov     [rbx+18h], rdi
0x14000620b  cmp     rdi, 10h
0x14000620f  cmovnb  rbx, rsi
0x140006213  mov     [rax], r14
0x140006216  mov     byte ptr [rbx+r14], 0
0x14000621b  add     rsp, 28h
0x14000621f  pop     r14
0x140006221  pop     rdi
0x140006222  pop     rsi
0x140006223  pop     rbx
0x140006224  retn
0x140006225  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
