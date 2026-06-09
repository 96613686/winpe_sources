# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180019798`
- end: `0x1800198c8`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `304`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a4c0`

## callees

- `0x180011a64`
- `0x180013294`
- `0x1800132b6`
- `0x180019798`
- `0x18001ac24`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180019830`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180019830`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall std::string::_Copy(char **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rbx
  char **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  char *v9; // rsi
  const void *v10; // rdx
  char *result; // rax
  const char *v12; // rax
  _QWORD *v13; // rdx
  _QWORD v14[5]; // [rsp+0h] [rbp-88h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v16[9]; // [rsp+40h] [rbp-48h] BYREF
  const char *v18; // [rsp+98h] [rbp+10h] BYREF
  size_t v19; // [rsp+A0h] [rbp+18h]
  char *v20; // [rsp+A8h] [rbp+20h] BYREF

  v19 = a3;
  v18 = (const char *)a2;
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
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = (char *)operator new(v4 + 1);
      if ( !v9 )
      {
        v20 = 0;
        exception::exception((exception *)pExceptionObject, (const char *const *)&v20);
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
    }
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v14;
    try
    {
      v12 = 0;
      if ( v18 != (const char *)-1LL )
      {
        v12 = (const char *)operator new((size_t)(v18 + 1));
        if ( !v12 )
        {
          exception::exception((exception *)v16, &v18);
          v16[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)v16;
        }
      }
      v20 = (char *)v12;
    }
    catch ( ... )
    {
      v13 = v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = v19;
    v4 = (unsigned __int64)v18;
    v9 = v20;
  }
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
  v5[3] = (char *)v4;
  result = (char *)v5;
  if ( v4 >= 0x10 )
    result = v9;
  v5[2] = (char *)v3;
  result[v3] = 0;
  return result;
}

```

## disassembly

```asm
0x180019798  mov     rax, rsp
0x18001979b  mov     [rax+18h], r8
0x18001979f  mov     [rax+10h], rdx
0x1800197a3  mov     [rax+8], rcx
0x1800197a7  push    rbx
0x1800197a8  push    rsi
0x1800197a9  push    rdi
0x1800197aa  push    r14
0x1800197ac  sub     rsp, 68h
0x1800197b0  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x1800197b8  mov     r14, r8
0x1800197bb  mov     rbx, rdx
0x1800197be  mov     rdi, rcx
0x1800197c1  or      rdx, 0Fh
0x1800197c5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800197cc  cmp     rdx, r9
0x1800197cf  ja      short loc_180019805
0x1800197d1  mov     rbx, rdx
0x1800197d4  mov     r8, [rcx+18h]
0x1800197d8  mov     rcx, r8
0x1800197db  shr     rcx, 1
0x1800197de  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800197e8  mul     rdx
0x1800197eb  shr     rdx, 1
0x1800197ee  cmp     rcx, rdx
0x1800197f1  jbe     short loc_180019805
0x1800197f3  mov     rax, r9
0x1800197f6  sub     rax, rcx
0x1800197f9  cmp     r8, rax
0x1800197fc  lea     rbx, [rcx+r8]
0x180019800  jbe     short loc_180019805
0x180019802  mov     rbx, r9
0x180019805  lea     rcx, [rbx+1]; Size
0x180019809  test    rcx, rcx
0x18001980c  jz      short loc_180019853
0x18001980e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019813  mov     rsi, rax
0x180019816  test    rax, rax
0x180019819  jnz     short loc_180019855
0x18001981b  mov     [rsp+88h+arg_18], rax
0x180019823  lea     rdx, [rsp+88h+arg_18]
0x18001982b  lea     rcx, [rsp+88h+pExceptionObject]
0x180019830  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180019836  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001983d  mov     [rsp+88h+pExceptionObject], rax
0x180019842  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180019849  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001984e  call    _CxxThrowException_0
0x180019853  xor     esi, esi
0x180019855  jmp     short loc_180019877
0x180019857  mov     rdi, [rsp+88h+arg_0]
0x18001985f  mov     r14, [rsp+88h+arg_10]
0x180019867  mov     rbx, [rsp+88h+arg_8]
0x18001986f  mov     rsi, [rsp+88h+arg_18]
0x180019877  test    r14, r14
0x18001987a  jz      short loc_180019896
0x18001987c  cmp     qword ptr [rdi+18h], 10h
0x180019881  jb      short loc_180019888
0x180019883  mov     rdx, [rdi]
0x180019886  jmp     short loc_18001988B
0x180019888  mov     rdx, rdi; Src
0x18001988b  mov     r8, r14; Size
0x18001988e  mov     rcx, rsi; void *
0x180019891  call    memcpy_0
0x180019896  xor     r8d, r8d
0x180019899  mov     dl, 1
0x18001989b  mov     rcx, rdi
0x18001989e  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x1800198a3  mov     [rdi], rsi
0x1800198a6  mov     [rdi+18h], rbx
0x1800198aa  mov     rax, rdi
0x1800198ad  cmp     rbx, 10h
0x1800198b1  cmovnb  rax, rsi
0x1800198b5  mov     [rdi+10h], r14
0x1800198b9  mov     byte ptr [rax+r14], 0
0x1800198be  add     rsp, 68h
0x1800198c2  pop     r14
0x1800198c4  pop     rdi
0x1800198c5  pop     rsi
0x1800198c6  pop     rbx
0x1800198c7  retn
```
