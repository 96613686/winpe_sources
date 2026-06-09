# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800025f8`
- end: `0x18000271e`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `294`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800021ec`
- `0x180002720`
- `0x18000da64`
- `0x18000ff9c`

## callees

- `0x18000252c`
- `0x1800025f8`
- `0x18002687c`
- `0x1800268f4`
- `0x180026f66`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800026e0`
- `msvcrt!memcpy_s` at `0x1800026e0`

## pseudocode

```c
_BYTE *__fastcall std::string::_Copy(_QWORD *a1, unsigned __int64 a2, rsize_t a3)
{
  rsize_t v3; // rsi
  _QWORD *v4; // rdi
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rcx
  size_t v8; // rcx
  void *v9; // r14
  const void *v10; // r8
  _BYTE *result; // rax
  size_t v12; // rcx
  _QWORD *v13; // rdx
  _QWORD v14[5]; // [rsp+0h] [rbp-88h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v16[72]; // [rsp+40h] [rbp-48h] BYREF
  void *v24; // [rsp+A8h] [rbp+20h]

  v14[4] = -2;
  v3 = a3;
  v4 = a1;
  v5 = a2 | 0xF;
  if ( (a2 | 0xF) == 0xFFFFFFFFFFFFFFFFuLL )
  {
    v5 = a2;
  }
  else
  {
    v6 = a1[4];
    v7 = v6 >> 1;
    if ( v5 / 3 < v6 >> 1 && v6 <= -2LL - v7 )
      v5 = v7 + v6;
  }
  try
  {
    v8 = v5 + 1;
    if ( v5 != -1 && !(0xFFFFFFFFFFFFFFFFuLL / v8) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v9 = operator new(v8);
  }
  catch ( ... )
  {
    try
    {
      v12 = a2 + 1;
      if ( a2 != -1 && !(0xFFFFFFFFFFFFFFFFuLL / v12) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)v16, 0);
        throw (std::bad_alloc *)v16;
      }
      v24 = operator new(v12);
    }
    catch ( ... )
    {
      v13 = v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(a1, v13, 0);
      throw;
    }
    v4 = a1;
    v3 = a3;
    v5 = a2;
    v9 = v24;
  }
  if ( v3 )
  {
    if ( v4[4] < 0x10u )
      v10 = v4 + 1;
    else
      v10 = (const void *)v4[1];
    memcpy_s(v9, v5 + 1, v10, v3);
  }
  if ( v4[4] >= 0x10u )
    operator delete((void *)v4[1]);
  result = v4 + 1;
  *((_BYTE *)v4 + 8) = 0;
  v4[1] = v9;
  v4[4] = v5;
  v4[3] = v3;
  if ( v5 >= 0x10 )
    result = v9;
  result[v3] = 0;
  return result;
}

```

## disassembly

```asm
0x1800025f8  mov     rax, rsp
0x1800025fb  mov     [rax+18h], r8
0x1800025ff  mov     [rax+10h], rdx
0x180002603  mov     [rax+8], rcx
0x180002607  push    rbx
0x180002608  push    rsi
0x180002609  push    rdi
0x18000260a  push    r14
0x18000260c  sub     rsp, 68h
0x180002610  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x180002618  mov     rsi, r8
0x18000261b  mov     rdi, rcx
0x18000261e  mov     rbx, rdx
0x180002621  or      rbx, 0Fh
0x180002625  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000262c  cmp     rbx, r9
0x18000262f  jbe     short loc_180002636
0x180002631  mov     rbx, rdx
0x180002634  jmp     short loc_180002661
0x180002636  mov     r8, [rcx+20h]
0x18000263a  mov     rcx, r8
0x18000263d  shr     rcx, 1
0x180002640  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000264a  mul     rbx
0x18000264d  shr     rdx, 1
0x180002650  cmp     rdx, rcx
0x180002653  jnb     short loc_180002661
0x180002655  sub     r9, rcx
0x180002658  cmp     r8, r9
0x18000265b  ja      short loc_180002661
0x18000265d  lea     rbx, [rcx+r8]
0x180002661  lea     rcx, [rbx+1]; Size
0x180002665  test    rcx, rcx
0x180002668  jz      short loc_180002696
0x18000266a  xor     edx, edx
0x18000266c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002670  div     rcx
0x180002673  cmp     rax, 1
0x180002677  jnb     short loc_180002696
0x180002679  xor     edx, edx; char *
0x18000267b  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180002680  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180002685  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000268c  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180002691  call    _CxxThrowException_0
0x180002696  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000269b  mov     r14, rax
0x18000269e  jmp     short loc_1800026C0
0x1800026a0  mov     rdi, [rsp+88h+arg_0]
0x1800026a8  mov     rsi, [rsp+88h+arg_10]
0x1800026b0  mov     rbx, [rsp+88h+arg_8]
0x1800026b8  mov     r14, [rsp+88h+arg_18]
0x1800026c0  test    rsi, rsi
0x1800026c3  jz      short loc_1800026E6
0x1800026c5  cmp     qword ptr [rdi+20h], 10h
0x1800026ca  jb      short loc_1800026D2
0x1800026cc  mov     r8, [rdi+8]
0x1800026d0  jmp     short loc_1800026D6
0x1800026d2  lea     r8, [rdi+8]; Source
0x1800026d6  lea     rdx, [rbx+1]; DestinationSize
0x1800026da  mov     r9, rsi; SourceSize
0x1800026dd  mov     rcx, r14; Destination
0x1800026e0  call    cs:__imp_memcpy_s
0x1800026e6  cmp     qword ptr [rdi+20h], 10h
0x1800026eb  jb      short loc_1800026F6
0x1800026ed  mov     rcx, [rdi+8]; Block
0x1800026f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800026f6  lea     rax, [rdi+8]
0x1800026fa  mov     byte ptr [rax], 0
0x1800026fd  mov     [rax], r14
0x180002700  mov     [rdi+20h], rbx
0x180002704  mov     [rdi+18h], rsi
0x180002708  cmp     rbx, 10h
0x18000270c  cmovnb  rax, r14
0x180002710  mov     byte ptr [rax+rsi], 0
0x180002714  add     rsp, 68h
0x180002718  pop     r14
0x18000271a  pop     rdi
0x18000271b  pop     rsi
0x18000271c  pop     rbx
0x18000271d  retn
```
