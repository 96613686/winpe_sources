# StateRepository::Text::Set(ushort const *,unsigned __int64)

- ea: `0x1800148ec`
- end: `0x1800149eb`
- name: `?Set@Text@StateRepository@@QEAAJPEBG_K@Z`
- size: `255`
- prototype: `__int64 __fastcall(StateRepository::Text *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `11`
- callee_count: `7`
- tags: ``

## callers

- `0x18000e85c`
- `0x18000e99c`
- `0x18000eae4`
- `0x1800115d0`
- `0x1800154e0`
- `0x18001b40c`
- `0x18001be40`
- `0x18001c950`
- `0x18001dc98`
- `0x18001e958`
- `0x1800208a4`

## callees

- `0x18000a3c0`
- `0x18000a77c`
- `0x180014814`
- `0x1800148b8`
- `0x1800148ec`
- `0x180014b90`
- `0x180014ca0`

## string_xrefs

- `0x180014933`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x18001495f`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180014998`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x1800149d6`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Text::Set(StateRepository::Text *this, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned __int64 v5; // r11
  unsigned int v6; // edi
  unsigned __int64 v8; // rdi
  int v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int64 v14; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    v14 = 0;
    v4 = StringCchLengthW(a2, 0x1DCD6500u, &v14);
    v6 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)(unsigned int)v4,
        v12);
      return v6;
    }
    if ( v5 && v14 > v5 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)0x80070057LL,
        v12);
      return 2147942487LL;
    }
    v8 = v14 + 1;
    v9 = StateRepository::Text::EnsureCapacity(this, v14 + 1, 0);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)(unsigned int)v9,
        v12);
      return v10;
    }
    v11 = StringCchCopyW(*(unsigned __int16 **)this, v8, a2);
    if ( v11 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)(unsigned int)v11,
        v12);
    *((_QWORD *)this + 1) = v8;
  }
  else
  {
    StateRepository::Text::Reset(this);
  }
  return 0;
}

```

## disassembly

```asm
0x1800148ec  push    rbx
0x1800148ee  push    rbp
0x1800148ef  push    rsi
0x1800148f0  push    rdi
0x1800148f1  sub     rsp, 28h
0x1800148f5  mov     r11, r8
0x1800148f8  mov     rbp, rdx
0x1800148fb  mov     rbx, rcx
0x1800148fe  test    rdx, rdx
0x180014901  jnz     short loc_18001490D
0x180014903  call    ?Reset@Text@StateRepository@@QEAAXXZ; StateRepository::Text::Reset(void)
0x180014908  jmp     loc_1800149C6
0x18001490d  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x180014912  mov     [rsp+48h+arg_8], 0
0x18001491b  mov     edx, 1DCD6500h; unsigned __int64
0x180014920  mov     rcx, rbp; unsigned __int16 *
0x180014923  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014928  mov     edi, eax
0x18001492a  test    eax, eax
0x18001492c  jns     short loc_18001494B
0x18001492e  mov     rcx, [rsp+48h]; this
0x180014933  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x18001493a  mov     r9d, eax; char *
0x18001493d  mov     edx, 1Bh; void *
0x180014942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014947  mov     eax, edi
0x180014949  jmp     short loc_1800149C8
0x18001494b  mov     rdi, [rsp+48h+arg_8]
0x180014950  test    r11, r11
0x180014953  jz      short loc_18001497C
0x180014955  cmp     rdi, r11
0x180014958  jbe     short loc_18001497C
0x18001495a  mov     rcx, [rsp+48h]; this
0x18001495f  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x180014966  mov     ebx, 80070057h
0x18001496b  mov     edx, 1Ch; void *
0x180014970  mov     r9d, ebx; char *
0x180014973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014978  mov     eax, ebx
0x18001497a  jmp     short loc_1800149C8
0x18001497c  inc     rdi
0x18001497f  xor     r8d, r8d; bool
0x180014982  mov     rdx, rdi; unsigned __int64
0x180014985  mov     rcx, rbx; this
0x180014988  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x18001498d  mov     esi, eax
0x18001498f  test    eax, eax
0x180014991  jns     short loc_1800149B0
0x180014993  mov     rcx, [rsp+48h]; this
0x180014998  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x18001499f  mov     r9d, eax; char *
0x1800149a2  mov     edx, 1Dh; void *
0x1800149a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149ac  mov     eax, esi
0x1800149ae  jmp     short loc_1800149C8
0x1800149b0  mov     rcx, [rbx]; unsigned __int16 *
0x1800149b3  mov     r8, rbp; unsigned __int16 *
0x1800149b6  mov     rdx, rdi; unsigned __int64
0x1800149b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800149be  test    eax, eax
0x1800149c0  js      short loc_1800149D1
0x1800149c2  mov     [rbx+8], rdi
0x1800149c6  xor     eax, eax
0x1800149c8  add     rsp, 28h
0x1800149cc  pop     rdi
0x1800149cd  pop     rsi
0x1800149ce  pop     rbp
0x1800149cf  pop     rbx
0x1800149d0  retn
0x1800149d1  mov     rcx, [rsp+48h]; this
0x1800149d6  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x1800149dd  mov     r9d, eax; char *
0x1800149e0  mov     edx, 1Eh; void *
0x1800149e5  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
