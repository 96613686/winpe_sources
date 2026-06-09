# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000bbe0`
- end: `0x18000bcfa`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z`
- size: `282`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180015b10`
- `0x180015c0c`
- `0x180015db0`
- `0x180015eb8`
- `0x180015fcc`
- `0x18001c7ec`

## callees

- `0x1800020c4`
- `0x1800022c8`
- `0x18000bbe0`
- `0x180026609`
- `0x180026796`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  _QWORD *v15; // rdx
  _QWORD v16[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v20; // [rsp+78h] [rbp+20h]

  v16[4] = -2;
  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000bbe0  mov     rax, rsp
0x18000bbe3  mov     [rax+18h], r8
0x18000bbe7  mov     [rax+10h], rdx
0x18000bbeb  mov     [rax+8], rcx
0x18000bbef  push    rbx
0x18000bbf0  push    rsi
0x18000bbf1  push    rdi
0x18000bbf2  push    r14
0x18000bbf4  push    r15
0x18000bbf6  sub     rsp, 30h
0x18000bbfa  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18000bc02  mov     r15, r8
0x18000bc05  mov     rdi, rdx
0x18000bc08  mov     rbx, rcx
0x18000bc0b  or      rdx, 7
0x18000bc0f  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000bc19  cmp     rdx, r9
0x18000bc1c  ja      short loc_18000BC52
0x18000bc1e  mov     rdi, rdx
0x18000bc21  mov     r8, [rcx+18h]
0x18000bc25  mov     rcx, r8
0x18000bc28  shr     rcx, 1
0x18000bc2b  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000bc35  mul     rdx
0x18000bc38  shr     rdx, 1
0x18000bc3b  cmp     rcx, rdx
0x18000bc3e  jbe     short loc_18000BC52
0x18000bc40  mov     rax, r9
0x18000bc43  sub     rax, rcx
0x18000bc46  cmp     r8, rax
0x18000bc49  lea     rdi, [rcx+r8]
0x18000bc4d  jbe     short loc_18000BC52
0x18000bc4f  mov     rdi, r9
0x18000bc52  lea     rcx, [rdi+1]
0x18000bc56  xor     esi, esi
0x18000bc58  test    rcx, rcx
0x18000bc5b  jz      short loc_18000BC82
0x18000bc5d  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000bc67  cmp     rcx, rax
0x18000bc6a  ja      loc_18000BCF3
0x18000bc70  add     rcx, rcx; Size
0x18000bc73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bc78  mov     r14, rax
0x18000bc7b  test    rax, rax
0x18000bc7e  jz      short loc_18000BCF3
0x18000bc80  jmp     short loc_18000BC85
0x18000bc82  mov     r14, rsi
0x18000bc85  jmp     short loc_18000BC9D
0x18000bc87  xor     esi, esi
0x18000bc89  mov     rbx, [rsp+58h+arg_0]
0x18000bc8e  mov     r15, [rsp+58h+arg_10]
0x18000bc93  mov     rdi, [rsp+58h+arg_8]
0x18000bc98  mov     r14, [rsp+58h+arg_18]
0x18000bc9d  test    r15, r15
0x18000bca0  jz      short loc_18000BCBD
0x18000bca2  cmp     qword ptr [rbx+18h], 8
0x18000bca7  jb      short loc_18000BCAE
0x18000bca9  mov     rdx, [rbx]
0x18000bcac  jmp     short loc_18000BCB1
0x18000bcae  mov     rdx, rbx; Src
0x18000bcb1  lea     r8, [r15+r15]; Size
0x18000bcb5  mov     rcx, r14; void *
0x18000bcb8  call    memcpy_0
0x18000bcbd  cmp     qword ptr [rbx+18h], 8
0x18000bcc2  jb      short loc_18000BCCC
0x18000bcc4  mov     rcx, [rbx]; void *
0x18000bcc7  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x18000bccc  lea     rax, [rbx+10h]
0x18000bcd0  mov     [rbx], r14
0x18000bcd3  mov     [rbx+18h], rdi
0x18000bcd7  cmp     rdi, 8
0x18000bcdb  cmovnb  rbx, r14
0x18000bcdf  mov     [rax], r15
0x18000bce2  mov     [rbx+r15*2], si
0x18000bce7  add     rsp, 30h
0x18000bceb  pop     r15
0x18000bced  pop     r14
0x18000bcef  pop     rdi
0x18000bcf0  pop     rsi
0x18000bcf1  pop     rbx
0x18000bcf2  retn
0x18000bcf3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
