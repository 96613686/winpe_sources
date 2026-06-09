# CLMString::GrowStringHelper(uint,uint,uint,wchar_t const *)

- ea: `0x140029c50`
- end: `0x140029d7c`
- name: `?GrowStringHelper@CLMString@@IEAAXIIIPEB_W@Z`
- size: `300`
- prototype: `void(CLMString *__hidden this, unsigned int, unsigned int, unsigned int, const wchar_t *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140021310`
- `0x140021340`
- `0x140028470`
- `0x1400495b0`

## callees

- `0x140003c80`
- `0x140005205`
- `0x1400284e8`
- `0x140029c50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140029d42`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140029d42`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140029cd3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140029cd3`

## string_xrefs

- `0x140029c7a`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x140029ce6`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall CLMString::GrowStringHelper(
        CLMString *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        const wchar_t *Src)
{
  unsigned int v5; // ebx
  unsigned __int64 v7; // rax
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rbp
  void *v10; // rsi
  unsigned int v11; // eax
  unsigned __int64 v12; // rax
  unsigned int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  if ( a2 > *((_DWORD *)this + 4) )
  {
    if ( a2 > a4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v13);
    if ( *((_DWORD *)this + 4) < a3 )
      a3 = *((_DWORD *)this + 4);
    if ( a2 % a3 )
      v5 = a3 - a2 % a3 + a2;
    v7 = 2LL * v5;
    if ( v7 > 0xFFFFFFFF )
    {
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    v8 = (const wchar_t *)*((_QWORD *)this + 1);
    v9 = Src;
    if ( v8 == Src )
      v8 = 0;
    v10 = (void *)_o_realloc(v8, (unsigned int)v7);
    if ( !v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v13);
    v11 = *((_DWORD *)this + 5);
    if ( v11 + 1 < v11 || (v12 = 2LL * (v11 + 1), v12 > 0xFFFFFFFF) )
    {
      free(v10);
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    if ( *((const wchar_t **)this + 1) == v9 )
      memcpy_0(v10, v9, (unsigned int)v12);
    *((_QWORD *)this + 1) = v10;
    *((_DWORD *)this + 4) = v5;
  }
}

```

## disassembly

```asm
0x140029c50  mov     [rsp+arg_0], rbx
0x140029c55  mov     [rsp+arg_10], rbp
0x140029c5a  push    rsi
0x140029c5b  push    rdi
0x140029c5c  push    r14; unsigned int
0x140029c5e  sub     rsp, 20h
0x140029c62  mov     ebx, edx
0x140029c64  mov     rdi, rcx
0x140029c67  cmp     edx, [rcx+10h]
0x140029c6a  jbe     loc_140029D2C
0x140029c70  cmp     edx, r9d
0x140029c73  jbe     short loc_140029C91
0x140029c75  mov     rcx, [rsp+38h]; this
0x140029c7a  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x140029c81  mov     r9d, 0CEh; char *
0x140029c87  lea     edx, [r9+4Bh]; void *
0x140029c8b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140029c91  cmp     [rcx+10h], r8d
0x140029c95  mov     eax, ebx
0x140029c97  cmovb   r8d, [rcx+10h]
0x140029c9c  xor     edx, edx
0x140029c9e  div     r8d
0x140029ca1  test    edx, edx
0x140029ca3  jz      short loc_140029CAB
0x140029ca5  sub     r8d, edx
0x140029ca8  add     ebx, r8d
0x140029cab  mov     eax, ebx
0x140029cad  mov     r14d, 0FFFFFFFFh
0x140029cb3  add     rax, rax
0x140029cb6  cmp     rax, r14
0x140029cb9  ja      loc_140029D62
0x140029cbf  mov     rcx, [rcx+8]
0x140029cc3  mov     rbp, [rsp+38h+Src]
0x140029cc8  mov     edx, eax
0x140029cca  xor     eax, eax
0x140029ccc  cmp     rcx, rbp
0x140029ccf  cmovz   rcx, rax
0x140029cd3  call    cs:__imp__o_realloc
0x140029cd9  mov     rsi, rax
0x140029cdc  test    rax, rax
0x140029cdf  jnz     short loc_140029CFD
0x140029ce1  mov     rcx, [rsp+38h]; this
0x140029ce6  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x140029ced  mov     r9d, 0CEh; char *
0x140029cf3  lea     edx, [r9+62h]; void *
0x140029cf7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140029cfd  mov     eax, [rdi+14h]
0x140029d00  lea     ecx, [rax+1]
0x140029d03  cmp     ecx, eax
0x140029d05  jb      short loc_140029D3F
0x140029d07  mov     eax, ecx
0x140029d09  add     rax, rax
0x140029d0c  cmp     rax, r14
0x140029d0f  ja      short loc_140029D3F
0x140029d11  cmp     [rdi+8], rbp
0x140029d15  jnz     short loc_140029D25
0x140029d17  mov     r8d, eax; Size
0x140029d1a  mov     rdx, rbp; Src
0x140029d1d  mov     rcx, rsi; void *
0x140029d20  call    memcpy_0
0x140029d25  mov     [rdi+8], rsi
0x140029d29  mov     [rdi+10h], ebx
0x140029d2c  mov     rbx, [rsp+38h+arg_0]
0x140029d31  mov     rbp, [rsp+38h+arg_10]
0x140029d36  add     rsp, 20h
0x140029d3a  pop     r14
0x140029d3c  pop     rdi
0x140029d3d  pop     rsi
0x140029d3e  retn
0x140029d3f  mov     rcx, rsi; Block
0x140029d42  call    cs:__imp_free
0x140029d48  lea     rdx, _TI1J; pThrowInfo
0x140029d4f  mov     [rsp+38h+pExceptionObject], 80070216h
0x140029d57  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x140029d5c  call    _CxxThrowException_0
0x140029d62  lea     rdx, _TI1J; pThrowInfo
0x140029d69  mov     [rsp+38h+pExceptionObject], 80070216h
0x140029d71  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x140029d76  call    _CxxThrowException_0
```
