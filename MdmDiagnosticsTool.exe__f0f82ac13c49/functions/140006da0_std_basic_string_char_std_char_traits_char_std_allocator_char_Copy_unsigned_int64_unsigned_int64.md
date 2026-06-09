# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006da0`
- end: `0x140006e79`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140007018`

## callees

- `0x140001dd6`
- `0x140002d4c`
- `0x140006da0`
- `0x1400071a4`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // rsi
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // rdx
  const void **result; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v14 = &v15;
      LOBYTE(v14) = 1;
      std::string::_Tidy(Src, v14, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, v3);
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(v5, v12, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x140006da0  mov     [rsp+arg_10], r8
0x140006da5  mov     [rsp+arg_8], rdx
0x140006daa  mov     [rsp+arg_0], rcx
0x140006daf  push    rbx
0x140006db0  push    rsi
0x140006db1  push    rdi
0x140006db2  push    r14
0x140006db4  sub     rsp, 28h
0x140006db8  mov     rsi, r8
0x140006dbb  mov     rdi, rdx
0x140006dbe  mov     rbx, rcx
0x140006dc1  or      rdx, 0Fh
0x140006dc5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140006dcc  cmp     rdx, r9
0x140006dcf  ja      short loc_140006E05
0x140006dd1  mov     rdi, rdx
0x140006dd4  mov     r8, [rcx+18h]
0x140006dd8  mov     rcx, r8
0x140006ddb  shr     rcx, 1
0x140006dde  mov     rax, 0AAAAAAAAAAAAAAABh
0x140006de8  mul     rdx
0x140006deb  shr     rdx, 1
0x140006dee  cmp     rcx, rdx
0x140006df1  jbe     short loc_140006E05
0x140006df3  mov     rax, r9
0x140006df6  sub     rax, rcx
0x140006df9  cmp     r8, rax
0x140006dfc  lea     rdi, [rcx+r8]
0x140006e00  jbe     short loc_140006E05
0x140006e02  mov     rdi, r9
0x140006e05  lea     rcx, [rdi+1]
0x140006e09  xor     edx, edx
0x140006e0b  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x140006e10  mov     r14, rax
0x140006e13  jmp     short loc_140006E29
0x140006e15  mov     rbx, [rsp+48h+arg_0]
0x140006e1a  mov     rsi, [rsp+48h+arg_10]
0x140006e1f  mov     rdi, [rsp+48h+arg_8]
0x140006e24  mov     r14, [rsp+48h+arg_18]
0x140006e29  test    rsi, rsi
0x140006e2c  jz      short loc_140006E48
0x140006e2e  cmp     qword ptr [rbx+18h], 10h
0x140006e33  jb      short loc_140006E3A
0x140006e35  mov     rdx, [rbx]
0x140006e38  jmp     short loc_140006E3D
0x140006e3a  mov     rdx, rbx; Src
0x140006e3d  mov     r8, rsi; Size
0x140006e40  mov     rcx, r14; void *
0x140006e43  call    memcpy_0
0x140006e48  xor     r8d, r8d
0x140006e4b  mov     dl, 1
0x140006e4d  mov     rcx, rbx
0x140006e50  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140006e55  mov     [rbx], r14
0x140006e58  mov     [rbx+18h], rdi
0x140006e5c  mov     rax, rbx
0x140006e5f  cmp     rdi, 10h
0x140006e63  cmovnb  rax, r14
0x140006e67  mov     [rbx+10h], rsi
0x140006e6b  mov     byte ptr [rax+rsi], 0
0x140006e6f  add     rsp, 28h
0x140006e73  pop     r14
0x140006e75  pop     rdi
0x140006e76  pop     rsi
0x140006e77  pop     rbx
0x140006e78  retn
```
