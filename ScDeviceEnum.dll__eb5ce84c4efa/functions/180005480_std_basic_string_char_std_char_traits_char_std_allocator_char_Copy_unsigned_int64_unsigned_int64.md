# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180005480`
- end: `0x180005559`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000558c`

## callees

- `0x180001f26`
- `0x180002cf8`
- `0x180005480`
- `0x18000564c`

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
0x180005480  mov     [rsp+arg_10], r8
0x180005485  mov     [rsp+arg_8], rdx
0x18000548a  mov     [rsp+arg_0], rcx
0x18000548f  push    rbx
0x180005490  push    rsi
0x180005491  push    rdi
0x180005492  push    r14
0x180005494  sub     rsp, 28h
0x180005498  mov     rsi, r8
0x18000549b  mov     rdi, rdx
0x18000549e  mov     rbx, rcx
0x1800054a1  or      rdx, 0Fh
0x1800054a5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800054ac  cmp     rdx, r9
0x1800054af  ja      short loc_1800054E5
0x1800054b1  mov     rdi, rdx
0x1800054b4  mov     r8, [rcx+18h]
0x1800054b8  mov     rcx, r8
0x1800054bb  shr     rcx, 1
0x1800054be  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800054c8  mul     rdx
0x1800054cb  shr     rdx, 1
0x1800054ce  cmp     rcx, rdx
0x1800054d1  jbe     short loc_1800054E5
0x1800054d3  mov     rax, r9
0x1800054d6  sub     rax, rcx
0x1800054d9  cmp     r8, rax
0x1800054dc  lea     rdi, [rcx+r8]
0x1800054e0  jbe     short loc_1800054E5
0x1800054e2  mov     rdi, r9
0x1800054e5  lea     rcx, [rdi+1]
0x1800054e9  xor     edx, edx
0x1800054eb  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x1800054f0  mov     r14, rax
0x1800054f3  jmp     short loc_180005509
0x1800054f5  mov     rbx, [rsp+48h+arg_0]
0x1800054fa  mov     rsi, [rsp+48h+arg_10]
0x1800054ff  mov     rdi, [rsp+48h+arg_8]
0x180005504  mov     r14, [rsp+48h+arg_18]
0x180005509  test    rsi, rsi
0x18000550c  jz      short loc_180005528
0x18000550e  cmp     qword ptr [rbx+18h], 10h
0x180005513  jb      short loc_18000551A
0x180005515  mov     rdx, [rbx]
0x180005518  jmp     short loc_18000551D
0x18000551a  mov     rdx, rbx; Src
0x18000551d  mov     r8, rsi; Size
0x180005520  mov     rcx, r14; void *
0x180005523  call    memcpy_0
0x180005528  xor     r8d, r8d
0x18000552b  mov     dl, 1
0x18000552d  mov     rcx, rbx
0x180005530  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180005535  mov     [rbx], r14
0x180005538  mov     [rbx+18h], rdi
0x18000553c  mov     rax, rbx
0x18000553f  cmp     rdi, 10h
0x180005543  cmovnb  rax, r14
0x180005547  mov     [rbx+10h], rsi
0x18000554b  mov     byte ptr [rax+rsi], 0
0x18000554f  add     rsp, 28h
0x180005553  pop     r14
0x180005555  pop     rdi
0x180005556  pop     rsi
0x180005557  pop     rbx
0x180005558  retn
```
