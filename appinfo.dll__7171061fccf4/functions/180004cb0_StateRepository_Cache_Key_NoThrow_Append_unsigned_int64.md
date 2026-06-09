# StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)

- ea: `0x180004cb0`
- end: `0x180004f54`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z`
- size: `676`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *this, unsigned __int64)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800047f4`
- `0x180004a70`
- `0x1800058b0`
- `0x18001d56c`
- `0x18001d7f0`
- `0x18001ddf0`
- `0x18001e0b0`

## callees

- `0x180004cb0`
- `0x18000720c`
- `0x18001a2d8`
- `0x180046e02`
- `0x180046e50`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180004cdf`
- `msvcrt!_ui64tow_s` at `0x180004cdf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004eef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180004eef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180004ea5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180004ea5`

## string_xrefs

- `0x180004dd3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004e24`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004e82`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004eb8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180004ed6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        unsigned __int64 a2)
{
  size_t *v3; // r8
  wchar_t *v4; // rax
  unsigned __int64 v5; // rbx
  __int64 v6; // rbp
  size_t v7; // rsi
  _WORD *v8; // rdx
  size_t v9; // rcx
  _WORD *v10; // rax
  unsigned int v11; // edi
  __int64 v13; // rcx
  void *v14; // rax
  void *v15; // rdi
  unsigned __int64 v16; // r8
  _WORD *v17; // rcx
  wchar_t *i; // rdx
  size_t v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+20h] [rbp-58h]
  wchar_t Buffer[20]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !_ui64tow_s(a2, Buffer, 0x11u, 16) )
  {
    v4 = Buffer;
    v5 = 0;
    v6 = 0;
    while ( *v4 )
    {
      if ( ++v5 >= 0x7FFFFFFF )
      {
        v11 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x80070057LL,
          v19);
        return v11;
      }
      if ( *v4 == 94 )
        ++v6;
      ++v4;
    }
    v7 = v5 + v6 + *((_QWORD *)this + 65) + 1LL;
    if ( v7 > *((_QWORD *)this + 66) )
    {
      v14 = (void *)SRCache_AllocStringBuffer((unsigned int)v7);
      v15 = v14;
      if ( !v14 )
      {
        v11 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          v19);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x136,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          v20);
        return v11;
      }
      memcpy_0(v14, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      v13 = *(_QWORD *)this;
      *(_QWORD *)this = v15;
      if ( v13 )
        SRCache_Free(v13);
      v8 = *(_WORD **)this;
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v7;
    }
    else
    {
      v8 = (_WORD *)*((_QWORD *)this + 67);
      v7 = *((_QWORD *)this + 66);
    }
    if ( v6 )
    {
      v16 = 0;
      v17 = &v8[*((_QWORD *)this + 65)];
      for ( i = Buffer; v16 < v5; ++v17 )
      {
        if ( *i == 94 )
          *v17++ = 94;
        ++v16;
        *v17 = *i++;
      }
      *v17 = 0;
    }
    else
    {
      if ( v7 - 1 > 0x7FFFFFFE )
      {
        v11 = -2147024809;
LABEL_17:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)v11,
          v19);
        return v11;
      }
      v9 = v7;
      v10 = v8;
      do
      {
        if ( !*v10 )
          break;
        ++v10;
        --v9;
      }
      while ( v9 );
      v11 = -2147024809;
      if ( !v9 )
        goto LABEL_17;
      v11 = StringCopyWorkerW(&v8[v7 - v9], v9, v3, Buffer, v19);
      if ( (v11 & 0x80000000) != 0 )
        goto LABEL_17;
    }
    *((_QWORD *)this + 65) += v5;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x166,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8000FFFFLL,
    v19);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180004cb0  push    r14
0x180004cb2  sub     rsp, 70h
0x180004cb6  mov     rax, cs:__security_cookie
0x180004cbd  xor     rax, rsp
0x180004cc0  mov     [rsp+78h+var_20], rax
0x180004cc5  mov     rax, rdx
0x180004cc8  mov     r14, rcx
0x180004ccb  mov     rcx, rax; Value
0x180004cce  lea     rdx, [rsp+78h+Buffer]; Buffer
0x180004cd3  mov     r9d, 10h; Radix
0x180004cd9  mov     r8d, 11h; BufferCount
0x180004cdf  call    cs:__imp__ui64tow_s
0x180004ce5  test    eax, eax
0x180004ce7  jnz     loc_180004E7D
0x180004ced  mov     [rsp+78h+arg_10], rbx
0x180004cf5  lea     rax, [rsp+78h+Buffer]
0x180004cfa  mov     [rsp+78h+arg_18], rbp
0x180004d02  xor     ebx, ebx
0x180004d04  xor     ebp, ebp
0x180004d06  mov     [rsp+78h+var_18], rdi
0x180004d0b  nop     dword ptr [rax+rax+00h]
0x180004d10  movzx   ecx, word ptr [rax]
0x180004d13  test    cx, cx
0x180004d16  jz      short loc_180004D38
0x180004d18  inc     rbx
0x180004d1b  cmp     rbx, 7FFFFFFFh
0x180004d22  jnb     loc_180004E1F
0x180004d28  cmp     cx, 5Eh ; '^'
0x180004d2c  jz      loc_180004E17
0x180004d32  add     rax, 2
0x180004d36  jmp     short loc_180004D10
0x180004d38  mov     rax, [r14+210h]
0x180004d3f  mov     [rsp+78h+var_10], rsi
0x180004d44  mov     rsi, [r14+208h]
0x180004d4b  inc     rsi
0x180004d4e  add     rsi, rbp
0x180004d51  add     rsi, rbx
0x180004d54  cmp     rsi, rax
0x180004d57  ja      loc_180004EA3
0x180004d5d  mov     rdx, [r14+218h]
0x180004d64  mov     rsi, rax
0x180004d67  test    rbp, rbp
0x180004d6a  jnz     loc_180004F04
0x180004d70  lea     rax, [rsi-1]
0x180004d74  cmp     rax, 7FFFFFFEh
0x180004d7a  ja      loc_180004EFA
0x180004d80  mov     rcx, rsi
0x180004d83  mov     rax, rdx
0x180004d86  cmp     word ptr [rax], 0
0x180004d8a  jz      short loc_180004D96
0x180004d8c  add     rax, 2
0x180004d90  sub     rcx, 1
0x180004d94  jnz     short loc_180004D86
0x180004d96  xor     eax, eax
0x180004d98  mov     edi, 80070057h
0x180004d9d  test    rcx, rcx
0x180004da0  cmovnz  edi, eax
0x180004da3  jz      short loc_180004DCE
0x180004da5  mov     rax, rsi
0x180004da8  sub     rax, rcx
0x180004dab  test    rcx, rcx
0x180004dae  jz      short loc_180004DCE
0x180004db0  sub     rsi, rax
0x180004db3  lea     rcx, [rdx+rax*2]; pszDest
0x180004db7  mov     rdx, rsi; cchDest
0x180004dba  lea     r9, [rsp+78h+Buffer]; pszSrc
0x180004dbf  call    StringCopyWorkerW
0x180004dc4  mov     edi, eax
0x180004dc6  test    eax, eax
0x180004dc8  jns     loc_180004F46
0x180004dce  mov     rcx, [rsp+78h]; this
0x180004dd3  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004dda  mov     r9d, edi; char *
0x180004ddd  mov     edx, 139h; void *
0x180004de2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004de7  mov     rsi, [rsp+78h+var_10]
0x180004dec  mov     rbp, [rsp+78h+arg_18]
0x180004df4  mov     eax, edi
0x180004df6  mov     rdi, [rsp+78h+var_18]
0x180004dfb  mov     rbx, [rsp+78h+arg_10]
0x180004e03  mov     rcx, [rsp+78h+var_20]
0x180004e08  xor     rcx, rsp; StackCookie
0x180004e0b  call    __security_check_cookie
0x180004e10  add     rsp, 70h
0x180004e14  pop     r14
0x180004e16  retn
0x180004e17  inc     rbp
0x180004e1a  jmp     loc_180004D32
0x180004e1f  mov     rcx, [rsp+78h]; this
0x180004e24  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004e2b  mov     edi, 80070057h
0x180004e30  mov     edx, 135h; void *
0x180004e35  mov     r9d, edi; char *
0x180004e38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e3d  jmp     short loc_180004DEC
0x180004e3f  mov     r8, [r14+210h]
0x180004e46  mov     rcx, rdi; void *
0x180004e49  mov     rdx, [r14+218h]; Src
0x180004e50  add     r8, r8; Size
0x180004e53  call    memcpy_0
0x180004e58  mov     rcx, [r14]
0x180004e5b  mov     [r14], rdi
0x180004e5e  test    rcx, rcx
0x180004e61  jnz     loc_180004EEF
0x180004e67  mov     rdx, [r14]
0x180004e6a  mov     [r14+218h], rdx
0x180004e71  mov     [r14+210h], rsi
0x180004e78  jmp     loc_180004D67
0x180004e7d  mov     rcx, [rsp+78h]; this
0x180004e82  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004e89  mov     r9d, 8000FFFFh; char *
0x180004e8f  mov     edx, 166h; void *
0x180004e94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004e99  mov     eax, 8000FFFFh
0x180004e9e  jmp     loc_180004E03
0x180004ea3  mov     ecx, esi
0x180004ea5  call    cs:__imp_SRCache_AllocStringBuffer
0x180004eab  mov     rdi, rax
0x180004eae  test    rax, rax
0x180004eb1  jnz     short loc_180004E3F
0x180004eb3  mov     rcx, [rsp+78h]; this
0x180004eb8  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004ebf  mov     edi, 8007000Eh
0x180004ec4  mov     edx, 193h; void *
0x180004ec9  mov     r9d, edi; char *
0x180004ecc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ed1  mov     rcx, [rsp+78h]; this
0x180004ed6  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004edd  mov     r9d, edi; char *
0x180004ee0  mov     edx, 136h; void *
0x180004ee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004eea  jmp     loc_180004DE7
0x180004eef  call    cs:__imp_SRCache_Free
0x180004ef5  jmp     loc_180004E67
0x180004efa  mov     edi, 80070057h
0x180004eff  jmp     loc_180004DCE
0x180004f04  mov     rax, [r14+208h]
0x180004f0b  xor     r8d, r8d
0x180004f0e  lea     rcx, [rdx+rax*2]
0x180004f12  lea     rdx, [rsp+78h+Buffer]
0x180004f17  test    rbx, rbx
0x180004f1a  jz      short loc_180004F41
0x180004f1c  cmp     word ptr [rdx], 5Eh ; '^'
0x180004f20  jnz     short loc_180004F2B
0x180004f22  mov     word ptr [rcx], 5Eh ; '^'
0x180004f27  add     rcx, 2
0x180004f2b  movzx   eax, word ptr [rdx]
0x180004f2e  inc     r8
0x180004f31  mov     [rcx], ax
0x180004f34  add     rdx, 2
0x180004f38  add     rcx, 2
0x180004f3c  cmp     r8, rbx
0x180004f3f  jb      short loc_180004F1C
0x180004f41  xor     eax, eax
0x180004f43  mov     [rcx], ax
0x180004f46  add     [r14+208h], rbx
0x180004f4d  xor     edi, edi
0x180004f4f  jmp     loc_180004DE7
```
