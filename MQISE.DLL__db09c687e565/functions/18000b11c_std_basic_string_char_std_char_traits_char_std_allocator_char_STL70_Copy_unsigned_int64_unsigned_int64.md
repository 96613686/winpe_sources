# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000b11c`
- end: `0x18000b24c`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `304`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d0c`
- `0x18000bf0c`
- `0x18000c000`
- `0x18000c0e8`

## callees

- `0x180001c0c`
- `0x18000310c`
- `0x18000b11c`
- `0x18000e61c`

## import_xrefs

- `msvcrt!free` at `0x18000b1f7`
- `msvcrt!free` at `0x18000b1f7`
- `msvcrt!memcpy_s` at `0x18000b1e7`
- `msvcrt!memcpy_s` at `0x18000b1e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::string::_Copy(__int64 a1, unsigned __int64 a2, rsize_t a3)
{
  rsize_t v3; // r14
  unsigned __int64 v4; // rdi
  __int64 v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r15
  void **v11; // rsi
  void *v12; // r8
  __int64 *v13; // rbp
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-78h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v18[64]; // [rsp+38h] [rbp-40h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 >> 1;
    if ( v6 / 3 < v7 >> 1 && v7 <= -2LL - v8 )
      v4 = v8 + v7;
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 != -1 && !(0xFFFFFFFFFFFFFFFFuLL / v9) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
      throw (std::bad_alloc *)pExceptionObject;
    }
    v10 = MmAllocate(v9);
  }
  catch ( ... )
  {
    v14 = a2 + 1;
    if ( a2 != -1 && !(0xFFFFFFFFFFFFFFFFuLL / v14) )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)v18, 0);
      try
      {
        throw (std::bad_alloc *)v18;
      }
      catch ( ... )
      {
        v15 = &v16;
        v13 = v15;
        LOBYTE(v15) = 1;
        std::string::_Tidy(v13[16], v15, 0);
        throw;
      }
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = MmAllocate(v14);
  }
  v11 = (void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 0x10u )
      v12 = (void *)(v5 + 8);
    else
      v12 = *v11;
    memcpy_s(v10, v4 + 1, v12, v3);
  }
  if ( *(_QWORD *)(v5 + 32) >= 0x10u )
    free(*v11);
  *(_QWORD *)(v5 + 32) = 15;
  *(_BYTE *)v11 = 0;
  *v11 = v10;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 0x10 )
    v11 = (void **)v10;
  *(_QWORD *)(v5 + 24) = v3;
  *((_BYTE *)v11 + v3) = 0;
}

```

## disassembly

```asm
0x18000b11c  mov     [rsp+arg_10], r8
0x18000b121  mov     [rsp+arg_8], rdx
0x18000b126  mov     [rsp+arg_0], rcx
0x18000b12b  push    rbx
0x18000b12c  push    rsi
0x18000b12d  push    rdi
0x18000b12e  push    r14
0x18000b130  push    r15
0x18000b132  sub     rsp, 50h
0x18000b136  mov     r14, r8
0x18000b139  mov     rdi, rdx
0x18000b13c  mov     rbx, rcx
0x18000b13f  or      rdx, 0Fh
0x18000b143  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000b14a  cmp     rdx, r9
0x18000b14d  ja      short loc_18000B17D
0x18000b14f  mov     rdi, rdx
0x18000b152  mov     r8, [rcx+20h]
0x18000b156  mov     rcx, r8
0x18000b159  shr     rcx, 1
0x18000b15c  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000b166  mul     rdx
0x18000b169  shr     rdx, 1
0x18000b16c  cmp     rdx, rcx
0x18000b16f  jnb     short loc_18000B17D
0x18000b171  sub     r9, rcx
0x18000b174  cmp     r8, r9
0x18000b177  ja      short loc_18000B17D
0x18000b179  lea     rdi, [rcx+r8]
0x18000b17d  lea     rcx, [rdi+1]; unsigned __int64
0x18000b181  test    rcx, rcx
0x18000b184  jnz     short loc_18000B190
0x18000b186  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000b18b  mov     r15, rax
0x18000b18e  jmp     short loc_18000B1C5
0x18000b190  xor     edx, edx
0x18000b192  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b196  div     rcx
0x18000b199  cmp     rax, 1
0x18000b19d  jb      loc_18000B22D
0x18000b1a3  jmp     short loc_18000B186
0x18000b1a5  mov     rbx, [rsp+78h+arg_0]
0x18000b1ad  mov     r14, [rsp+78h+arg_10]
0x18000b1b5  mov     rdi, [rsp+78h+arg_8]
0x18000b1bd  mov     r15, [rsp+78h+arg_18]
0x18000b1c5  lea     rsi, [rbx+8]
0x18000b1c9  test    r14, r14
0x18000b1cc  jz      short loc_18000B1ED
0x18000b1ce  cmp     qword ptr [rbx+20h], 10h
0x18000b1d3  jb      short loc_18000B1DA
0x18000b1d5  mov     r8, [rsi]
0x18000b1d8  jmp     short loc_18000B1DD
0x18000b1da  mov     r8, rsi; Source
0x18000b1dd  lea     rdx, [rdi+1]; DestinationSize
0x18000b1e1  mov     r9, r14; SourceSize
0x18000b1e4  mov     rcx, r15; Destination
0x18000b1e7  call    cs:__imp_memcpy_s
0x18000b1ed  cmp     qword ptr [rbx+20h], 10h
0x18000b1f2  jb      short loc_18000B1FE
0x18000b1f4  mov     rcx, [rsi]; Block
0x18000b1f7  call    cs:__imp_free
0x18000b1fd  nop
0x18000b1fe  mov     qword ptr [rbx+20h], 0Fh
0x18000b206  mov     byte ptr [rsi], 0
0x18000b209  mov     [rsi], r15
0x18000b20c  mov     [rbx+20h], rdi
0x18000b210  cmp     rdi, 10h
0x18000b214  cmovnb  rsi, r15
0x18000b218  mov     [rbx+18h], r14
0x18000b21c  mov     byte ptr [rsi+r14], 0
0x18000b221  add     rsp, 50h
0x18000b225  pop     r15
0x18000b227  pop     r14
0x18000b229  pop     rdi
0x18000b22a  pop     rsi
0x18000b22b  pop     rbx
0x18000b22c  retn
0x18000b22d  xor     edx, edx; char *
0x18000b22f  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18000b234  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000b239  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000b240  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000b245  call    _CxxThrowException_0
```
