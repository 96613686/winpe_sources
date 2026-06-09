# CLMString::GrowStringHelper(uint,uint,uint,wchar_t const *)

- ea: `0x18002a058`
- end: `0x18002a184`
- name: `?GrowStringHelper@CLMString@@IEAAXIIIPEB_W@Z`
- size: `300`
- prototype: `void(CLMString *__hidden this, unsigned int, unsigned int, unsigned int, const wchar_t *)`
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015ed0`
- `0x180015f00`
- `0x180015f30`
- `0x180015f60`
- `0x180015f90`
- `0x180015fc0`
- `0x18001efd0`
- `0x18001f000`

## callees

- `0x180003078`
- `0x180022670`
- `0x18002a058`
- `0x18003a0e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a14a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002a14a`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002a0db`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002a0db`

## string_xrefs

- `0x18002a082`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x18002a0ee`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

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
0x18002a058  mov     [rsp+arg_0], rbx
0x18002a05d  mov     [rsp+arg_10], rbp
0x18002a062  push    rsi
0x18002a063  push    rdi
0x18002a064  push    r14; unsigned int
0x18002a066  sub     rsp, 20h
0x18002a06a  mov     ebx, edx
0x18002a06c  mov     rdi, rcx
0x18002a06f  cmp     edx, [rcx+10h]
0x18002a072  jbe     loc_18002A134
0x18002a078  cmp     edx, r9d
0x18002a07b  jbe     short loc_18002A099
0x18002a07d  mov     rcx, [rsp+38h]; this
0x18002a082  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002a089  mov     r9d, 0CEh; char *
0x18002a08f  lea     edx, [r9+4Bh]; void *
0x18002a093  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002a099  cmp     [rcx+10h], r8d
0x18002a09d  mov     eax, ebx
0x18002a09f  cmovb   r8d, [rcx+10h]
0x18002a0a4  xor     edx, edx
0x18002a0a6  div     r8d
0x18002a0a9  test    edx, edx
0x18002a0ab  jz      short loc_18002A0B3
0x18002a0ad  sub     r8d, edx
0x18002a0b0  add     ebx, r8d
0x18002a0b3  mov     eax, ebx
0x18002a0b5  mov     r14d, 0FFFFFFFFh
0x18002a0bb  add     rax, rax
0x18002a0be  cmp     rax, r14
0x18002a0c1  ja      loc_18002A16A
0x18002a0c7  mov     rcx, [rcx+8]
0x18002a0cb  mov     rbp, [rsp+38h+Src]
0x18002a0d0  mov     edx, eax
0x18002a0d2  xor     eax, eax
0x18002a0d4  cmp     rcx, rbp
0x18002a0d7  cmovz   rcx, rax
0x18002a0db  call    cs:__imp__o_realloc
0x18002a0e1  mov     rsi, rax
0x18002a0e4  test    rax, rax
0x18002a0e7  jnz     short loc_18002A105
0x18002a0e9  mov     rcx, [rsp+38h]; this
0x18002a0ee  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002a0f5  mov     r9d, 0CEh; char *
0x18002a0fb  lea     edx, [r9+62h]; void *
0x18002a0ff  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002a105  mov     eax, [rdi+14h]
0x18002a108  lea     ecx, [rax+1]
0x18002a10b  cmp     ecx, eax
0x18002a10d  jb      short loc_18002A147
0x18002a10f  mov     eax, ecx
0x18002a111  add     rax, rax
0x18002a114  cmp     rax, r14
0x18002a117  ja      short loc_18002A147
0x18002a119  cmp     [rdi+8], rbp
0x18002a11d  jnz     short loc_18002A12D
0x18002a11f  mov     r8d, eax; Size
0x18002a122  mov     rdx, rbp; Src
0x18002a125  mov     rcx, rsi; void *
0x18002a128  call    memcpy_0
0x18002a12d  mov     [rdi+8], rsi
0x18002a131  mov     [rdi+10h], ebx
0x18002a134  mov     rbx, [rsp+38h+arg_0]
0x18002a139  mov     rbp, [rsp+38h+arg_10]
0x18002a13e  add     rsp, 20h
0x18002a142  pop     r14
0x18002a144  pop     rdi
0x18002a145  pop     rsi
0x18002a146  retn
0x18002a147  mov     rcx, rsi; Block
0x18002a14a  call    cs:__imp_free
0x18002a150  lea     rdx, _TI1J; pThrowInfo
0x18002a157  mov     [rsp+38h+pExceptionObject], 80070216h
0x18002a15f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a164  call    _CxxThrowException_0
0x18002a16a  lea     rdx, _TI1J; pThrowInfo
0x18002a171  mov     [rsp+38h+pExceptionObject], 80070216h
0x18002a179  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a17e  call    _CxxThrowException_0
```
