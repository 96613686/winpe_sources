# Common::StringBuffer::SetCapacity(ulong)

- ea: `0x18010a418`
- end: `0x18010a5cb`
- name: `?SetCapacity@StringBuffer@Common@@QEAAJK@Z`
- size: `435`
- prototype: `__int64 __fastcall(Common::StringBuffer *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18010a5d4`
- `0x18010a650`
- `0x18010aa50`

## callees

- `0x180003430`
- `0x1800039c6`
- `0x180003a40`
- `0x1800e4c28`
- `0x1800e4dfe`
- `0x1800eabf4`
- `0x1800fb7b4`
- `0x18010a418`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010a52c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010a543`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010a52c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18010a543`

## string_xrefs

- `0x18010a443`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18010a4d2`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18010a56d`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetCapacity(Common::StringBuffer *this, unsigned int a2)
{
  __int64 v2; // rdi
  unsigned int v4; // ebx
  __int64 v5; // rdx
  void *v7; // rcx
  __int64 v8; // r14
  unsigned int v9; // r15d
  void *v10; // rbp
  unsigned __int64 v11; // rax
  _WORD *v12; // rax
  _WORD *v13; // rsi
  size_t v14; // r14
  size_t v15; // r12
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int *v19; // rax
  int v20; // ebx
  int v21; // [rsp+20h] [rbp-48h]
  char *v22; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2;
  if ( a2 > 0x3FFFFFFF )
  {
    v4 = -2147023613;
    v5 = 425;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v4,
      v21);
    return v4;
  }
  if ( !a2 )
  {
    v7 = (void *)*((_QWORD *)this + 1);
    if ( v7 )
    {
      operator delete(v7);
      *((_QWORD *)this + 1) = 0;
      *(_DWORD *)this = 0;
    }
    *((_DWORD *)this + 4) = 0;
    return 0;
  }
  v8 = *((unsigned int *)this + 4);
  v9 = a2 + 1;
  if ( a2 + 1 != (_DWORD)v8 )
  {
    v10 = (void *)*((_QWORD *)this + 1);
    if ( v9 <= (unsigned int)v8 )
    {
      v13 = (_WORD *)*((_QWORD *)this + 1);
LABEL_28:
      *((_DWORD *)this + 4) = v9;
      *((_QWORD *)this + 1) = v13;
      if ( *(_DWORD *)this <= (unsigned int)v2 )
      {
        if ( *(_DWORD *)this < (unsigned int)v2 && !*(_DWORD *)this )
          *v13 = 0;
      }
      else
      {
        *(_DWORD *)this = v2;
        v13[v2] = 0;
      }
      return 0;
    }
    v11 = 2LL * v9;
    if ( !is_mul_ok(v9, 2u) )
      v11 = -1;
    v12 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v12;
    if ( !v12 )
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x8007000ELL,
        v21);
LABEL_26:
      v5 = 452;
      goto LABEL_3;
    }
    v14 = 2 * v8;
    if ( !v14 )
    {
LABEL_18:
      operator delete(v10);
      goto LABEL_28;
    }
    v15 = 2LL * v9;
    if ( v10 && v15 >= v14 )
    {
      memcpy_0(v12, v10, v14);
      goto LABEL_18;
    }
    memset_0(v12, 0, v15);
    if ( v10 )
    {
      if ( v15 >= v14 )
      {
        v20 = 22;
        goto LABEL_25;
      }
      v19 = (int *)_o__errno(v17, v16, v18);
      v20 = 34;
    }
    else
    {
      v19 = (int *)_o__errno(v17, v16, v18);
      v20 = 22;
    }
    *v19 = v20;
    invalid_parameter_noinfo();
LABEL_25:
    operator delete(v13);
    LODWORD(v22) = v20;
    v4 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      (int)"0x%08lx",
      v22);
    goto LABEL_26;
  }
  return 0;
}

```

## disassembly

```asm
0x18010a418  push    rbx
0x18010a41a  push    rbp
0x18010a41b  push    rsi
0x18010a41c  push    rdi
0x18010a41d  push    r12
0x18010a41f  push    r14
0x18010a421  push    r15
0x18010a423  sub     rsp, 30h
0x18010a427  mov     edi, edx
0x18010a429  mov     rbx, rcx
0x18010a42c  cmp     edx, 3FFFFFFFh
0x18010a432  jbe     short loc_18010A459
0x18010a434  mov     ebx, 80070503h
0x18010a439  mov     edx, 1A9h; void *
0x18010a43e  mov     rcx, [rsp+68h]; this
0x18010a443  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\common\\widest"...
0x18010a44a  mov     r9d, ebx; char *
0x18010a44d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a452  mov     eax, ebx
0x18010a454  jmp     loc_18010A5BC
0x18010a459  test    edx, edx
0x18010a45b  jnz     short loc_18010A485
0x18010a45d  mov     rcx, [rcx+8]; void *
0x18010a461  test    rcx, rcx
0x18010a464  jz      short loc_18010A479
0x18010a466  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010a46b  mov     qword ptr [rbx+8], 0
0x18010a473  mov     dword ptr [rbx], 0
0x18010a479  mov     dword ptr [rbx+10h], 0
0x18010a480  jmp     loc_18010A5BA
0x18010a485  mov     r14d, [rcx+10h]
0x18010a489  lea     r15d, [rdi+1]
0x18010a48d  cmp     r15d, r14d
0x18010a490  jz      loc_18010A5BA
0x18010a496  mov     rbp, [rcx+8]
0x18010a49a  jbe     loc_18010A595
0x18010a4a0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18010a4a7  mov     r12d, r15d
0x18010a4aa  mov     eax, 2
0x18010a4af  mul     r12
0x18010a4b2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010a4b9  cmovb   rax, rcx
0x18010a4bd  mov     rcx, rax; unsigned __int64
0x18010a4c0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18010a4c5  mov     rsi, rax
0x18010a4c8  test    rax, rax
0x18010a4cb  jnz     short loc_18010A4F0
0x18010a4cd  mov     rcx, [rsp+68h]; this
0x18010a4d2  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\common\\widest"...
0x18010a4d9  mov     ebx, 8007000Eh
0x18010a4de  mov     edx, 193h; void *
0x18010a4e3  mov     r9d, ebx; char *
0x18010a4e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a4eb  jmp     loc_18010A58B
0x18010a4f0  add     r14, r14
0x18010a4f3  jz      short loc_18010A510
0x18010a4f5  add     r12, r12
0x18010a4f8  test    rbp, rbp
0x18010a4fb  jz      short loc_18010A51A
0x18010a4fd  cmp     r12, r14
0x18010a500  jb      short loc_18010A51A
0x18010a502  mov     r8, r14; Size
0x18010a505  mov     rdx, rbp; Src
0x18010a508  mov     rcx, rsi; void *
0x18010a50b  call    memcpy_0
0x18010a510  mov     rcx, rbp; void *
0x18010a513  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010a518  jmp     short loc_18010A598
0x18010a51a  mov     r8, r12; Size
0x18010a51d  xor     edx, edx; Val
0x18010a51f  mov     rcx, rsi; void *
0x18010a522  call    memset_0
0x18010a527  test    rbp, rbp
0x18010a52a  jnz     short loc_18010A53E
0x18010a52c  call    cs:__imp__o__errno
0x18010a532  lea     ebx, [rbp+16h]
0x18010a535  mov     [rax], ebx
0x18010a537  call    _invalid_parameter_noinfo
0x18010a53c  jmp     short loc_18010A555
0x18010a53e  cmp     r12, r14
0x18010a541  jnb     short loc_18010A550
0x18010a543  call    cs:__imp__o__errno
0x18010a549  mov     ebx, 22h ; '"'
0x18010a54e  jmp     short loc_18010A535
0x18010a550  mov     ebx, 16h
0x18010a555  mov     rcx, rsi; void *
0x18010a558  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010a55d  mov     rcx, [rsp+68h]; this
0x18010a562  lea     rax, a0x08lx; "0x%08lx"
0x18010a569  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x18010a56d  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\common\\widest"...
0x18010a574  mov     ebx, 80070057h
0x18010a579  mov     qword ptr [rsp+68h+var_48], rax; int
0x18010a57e  mov     r9d, ebx; char *
0x18010a581  mov     edx, 198h; void *
0x18010a586  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18010a58b  mov     edx, 1C4h
0x18010a590  jmp     loc_18010A43E
0x18010a595  mov     rsi, rbp
0x18010a598  mov     [rbx+10h], r15d
0x18010a59c  mov     [rbx+8], rsi
0x18010a5a0  cmp     [rbx], edi
0x18010a5a2  jbe     short loc_18010A5AE
0x18010a5a4  xor     eax, eax
0x18010a5a6  mov     [rbx], edi
0x18010a5a8  mov     [rsi+rdi*2], ax
0x18010a5ac  jmp     short loc_18010A5BA
0x18010a5ae  jnb     short loc_18010A5BA
0x18010a5b0  cmp     dword ptr [rbx], 0
0x18010a5b3  jnz     short loc_18010A5BA
0x18010a5b5  xor     eax, eax
0x18010a5b7  mov     [rsi], ax
0x18010a5ba  xor     eax, eax
0x18010a5bc  add     rsp, 30h
0x18010a5c0  pop     r15
0x18010a5c2  pop     r14
0x18010a5c4  pop     r12
0x18010a5c6  pop     rdi
0x18010a5c7  pop     rsi
0x18010a5c8  pop     rbp
0x18010a5c9  pop     rbx
0x18010a5ca  retn
```
