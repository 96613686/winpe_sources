# Common::EnsureBufferCapacity

- ea: `0x14000e2c8`
- end: `0x14000e3a5`
- name: `Common::EnsureBufferCapacity`
- size: `221`
- prototype: `__int64 __fastcall(void *, unsigned int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000e3ec`

## callees

- `0x140003644`
- `0x1400036c0`
- `0x140006c24`
- `0x140007b40`
- `0x14000e2c8`
- `0x14000e3ac`

## string_xrefs

- `0x14000e317`: `onecore\base\appmodel\common\widestring.cpp`
- `0x14000e374`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::EnsureBufferCapacity(void *a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  __int64 v4; // rsi
  __int64 v7; // r15
  unsigned __int64 v8; // rax
  void *v9; // rax
  void *v10; // rbx
  unsigned int v11; // ebx
  errno_t v13; // esi
  char *v14; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a2;
  if ( a2 >= a3 )
  {
    v10 = a1;
  }
  else
  {
    v7 = a3;
    v8 = 2LL * a3;
    if ( !is_mul_ok(a3, 2u) )
      v8 = -1;
    v9 = operator new[](v8, (const struct std::nothrow_t *)std::nothrow);
    v10 = v9;
    if ( !v9 )
    {
      v11 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x193,
        (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x8007000ELL);
      return v11;
    }
    v13 = memcpy_s(v9, 2 * v7, a1, 2 * v4);
    if ( v13 )
    {
      operator delete(v10);
      v11 = -2147024809;
      LODWORD(v14) = v13;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x198,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070057LL,
        (int)"0x%08lx",
        v14);
      return v11;
    }
    operator delete(a1);
  }
  *a4 = v10;
  return 0;
}

```

## disassembly

```asm
0x14000e2c8  push    rbx
0x14000e2ca  push    rsi
0x14000e2cb  push    rdi
0x14000e2cc  push    r14
0x14000e2ce  push    r15
0x14000e2d0  sub     rsp, 30h
0x14000e2d4  mov     esi, edx
0x14000e2d6  mov     r14, r9
0x14000e2d9  mov     rdi, rcx
0x14000e2dc  cmp     edx, r8d
0x14000e2df  jnb     loc_14000E391
0x14000e2e5  mov     r15d, r8d
0x14000e2e8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e2ef  mov     eax, 2
0x14000e2f4  mul     r15
0x14000e2f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e2fe  cmovb   rax, rcx
0x14000e302  mov     rcx, rax; unsigned __int64
0x14000e305  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000e30a  mov     rbx, rax
0x14000e30d  test    rax, rax
0x14000e310  jnz     short loc_14000E334
0x14000e312  mov     rcx, [rsp+58h]; this
0x14000e317  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e31e  mov     ebx, 8007000Eh
0x14000e323  mov     edx, 193h; void *
0x14000e328  mov     r9d, ebx; char *
0x14000e32b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e330  mov     eax, ebx
0x14000e332  jmp     short loc_14000E399
0x14000e334  mov     r9, rsi
0x14000e337  lea     rdx, [r15+r15]; DestinationSize
0x14000e33b  add     r9, r9; SourceSize
0x14000e33e  mov     r8, rdi; Source
0x14000e341  mov     rcx, rbx; Destination
0x14000e344  call    memcpy_s
0x14000e349  mov     esi, eax
0x14000e34b  test    eax, eax
0x14000e34d  jz      short loc_14000E387
0x14000e34f  mov     rcx, rbx; void *
0x14000e352  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e357  mov     rcx, [rsp+58h]; this
0x14000e35c  lea     rax, a0x08lx; "0x%08lx"
0x14000e363  mov     ebx, 80070057h
0x14000e368  mov     dword ptr [rsp+58h+var_30], esi; char *
0x14000e36c  mov     r9d, ebx; char *
0x14000e36f  mov     qword ptr [rsp+58h+var_38], rax; int
0x14000e374  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e37b  mov     edx, 198h; void *
0x14000e380  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000e385  jmp     short loc_14000E330
0x14000e387  mov     rcx, rdi; void *
0x14000e38a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e38f  jmp     short loc_14000E394
0x14000e391  mov     rbx, rdi
0x14000e394  mov     [r14], rbx
0x14000e397  xor     eax, eax
0x14000e399  add     rsp, 30h
0x14000e39d  pop     r15
0x14000e39f  pop     r14
0x14000e3a1  pop     rdi
0x14000e3a2  pop     rsi
0x14000e3a3  pop     rbx
0x14000e3a4  retn
```
