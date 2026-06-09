# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180017ed4`
- end: `0x180018017`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `323`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180018070`

## callees

- `0x1800014dc`
- `0x1800020de`
- `0x18000a766`
- `0x18000b7a4`
- `0x180017ed4`
- `0x18001856c`

## pseudocode

```c
const void **__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, const void *a3)
{
  const void *v3; // r15
  unsigned __int64 v4; // rbx
  const void **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // r12
  const void **result; // rax
  void *v14; // rax
  unsigned __int64 v15; // rcx
  _BYTE *v16; // rdx
  _BYTE v17[32]; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v19[80]; // [rsp+38h] [rbp-50h] BYREF
  void *v23; // [rsp+A8h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
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
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, (const char *)v6);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v17;
    try
    {
      v14 = 0;
      v15 = a2 + 1;
      if ( a2 != -1 && (v15 > 0x7FFFFFFFFFFFFFFFLL || (v14 = operator new(2 * v15)) == 0) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)v19, (const char *)v6);
        throw (std::bad_alloc *)v19;
      }
      v23 = v14;
    }
    catch ( ... )
    {
      v16 = v17;
      LOBYTE(v16) = 1;
      std::wstring::_Tidy(Src, v16, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    v12 = 2LL * (_QWORD)v3;
    memcpy_0(v10, v11, 2LL * (_QWORD)v3);
  }
  else
  {
    v12 = 0;
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 8 )
    result = (const void **)v10;
  v5[2] = v3;
  *(_WORD *)((char *)result + v12) = 0;
  return result;
}

```

## disassembly

```asm
0x180017ed4  mov     [rsp+arg_10], r8
0x180017ed9  mov     [rsp+arg_8], rdx
0x180017ede  mov     [rsp+arg_0], rcx
0x180017ee3  push    rbx
0x180017ee4  push    rsi
0x180017ee5  push    rdi
0x180017ee6  push    r12
0x180017ee8  push    r14
0x180017eea  push    r15
0x180017eec  sub     rsp, 58h
0x180017ef0  mov     r15, r8
0x180017ef3  mov     rbx, rdx
0x180017ef6  mov     rdi, rcx
0x180017ef9  or      rdx, 7
0x180017efd  mov     r9, 7FFFFFFFFFFFFFFEh
0x180017f07  cmp     rdx, r9
0x180017f0a  ja      short loc_180017F40
0x180017f0c  mov     rbx, rdx
0x180017f0f  mov     r8, [rcx+18h]
0x180017f13  mov     rcx, r8
0x180017f16  shr     rcx, 1
0x180017f19  mov     rax, 0AAAAAAAAAAAAAAABh
0x180017f23  mul     rdx
0x180017f26  shr     rdx, 1; char *
0x180017f29  cmp     rcx, rdx
0x180017f2c  jbe     short loc_180017F40
0x180017f2e  mov     rax, r9
0x180017f31  sub     rax, rcx
0x180017f34  cmp     r8, rax
0x180017f37  lea     rbx, [rcx+r8]
0x180017f3b  jbe     short loc_180017F40
0x180017f3d  mov     rbx, r9
0x180017f40  lea     rcx, [rbx+1]
0x180017f44  xor     esi, esi
0x180017f46  test    rcx, rcx
0x180017f49  jz      short loc_180017F74
0x180017f4b  mov     rax, 7FFFFFFFFFFFFFFFh
0x180017f55  cmp     rcx, rax
0x180017f58  ja      loc_180017FFA
0x180017f5e  add     rcx, rcx; Size
0x180017f61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f66  mov     r14, rax
0x180017f69  test    rax, rax
0x180017f6c  jz      loc_180017FFA
0x180017f72  jmp     short loc_180017F77
0x180017f74  mov     r14, rsi
0x180017f77  jmp     short loc_180017F9B
0x180017f79  xor     esi, esi
0x180017f7b  mov     rdi, [rsp+88h+arg_0]
0x180017f83  mov     r15, [rsp+88h+arg_10]
0x180017f8b  mov     rbx, [rsp+88h+arg_8]
0x180017f93  mov     r14, [rsp+88h+arg_18]
0x180017f9b  test    r15, r15
0x180017f9e  jz      short loc_180017FC0
0x180017fa0  cmp     qword ptr [rdi+18h], 8
0x180017fa5  jb      short loc_180017FAC
0x180017fa7  mov     rdx, [rdi]
0x180017faa  jmp     short loc_180017FAF
0x180017fac  mov     rdx, rdi; Src
0x180017faf  lea     r12, [r15+r15]
0x180017fb3  mov     r8, r12; Size
0x180017fb6  mov     rcx, r14; void *
0x180017fb9  call    memcpy_0
0x180017fbe  jmp     short loc_180017FC4
0x180017fc0  lea     r12, [r15+r15]
0x180017fc4  xor     r8d, r8d
0x180017fc7  mov     dl, 1
0x180017fc9  mov     rcx, rdi
0x180017fcc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180017fd1  mov     [rdi], r14
0x180017fd4  mov     [rdi+18h], rbx
0x180017fd8  mov     rax, rdi
0x180017fdb  cmp     rbx, 8
0x180017fdf  cmovnb  rax, r14
0x180017fe3  mov     [rdi+10h], r15
0x180017fe7  mov     [r12+rax], si
0x180017fec  add     rsp, 58h
0x180017ff0  pop     r15
0x180017ff2  pop     r14
0x180017ff4  pop     r12
0x180017ff6  pop     rdi
0x180017ff7  pop     rsi
0x180017ff8  pop     rbx
0x180017ff9  retn
0x180017ffa  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180017fff  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180018004  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001800b  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180018010  call    _CxxThrowException_0
```
