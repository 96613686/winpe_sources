# StateRepository::Cache::Key_NoThrow::Append(ushort const *)

- ea: `0x180006ddc`
- end: `0x180006f73`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `407`
- prototype: `int(StateRepository::Cache::Key_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800073e8`
- `0x18000e71c`

## callees

- `0x1800029d3`
- `0x1800052a8`
- `0x180005b90`
- `0x180006ddc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006ecd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180006ecd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180006e5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180006e5b`

## string_xrefs

- `0x180006e6e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180006e93`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180006f09`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        const unsigned __int16 *a2,
        __int64 a3,
        int a4)
{
  const unsigned __int16 *v4; // rdi
  unsigned __int64 v6; // rsi
  __int64 v7; // r14
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rbp
  void *v11; // rax
  int v12; // r9d
  void *v13; // r15
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v17; // rcx
  unsigned __int16 *v18; // rcx
  int v19; // eax
  int v20; // r9d
  unsigned int v21; // edi
  unsigned __int64 v22; // rdx
  unsigned __int16 *i; // rcx

  v4 = a2;
  if ( a2 )
  {
    v6 = 0;
    v7 = 0;
    v8 = a2;
    if ( *a2 )
    {
      while ( ++v6 < 0x7FFFFFFF )
      {
        v9 = v7 + 1;
        if ( *v8 != 94 )
          v9 = v7;
        ++v8;
        v7 = v9;
        if ( !*v8 )
          goto LABEL_7;
      }
      v14 = -2147024809;
      v15 = 309;
      goto LABEL_11;
    }
LABEL_7:
    v10 = v7 + v6 + *((_QWORD *)this + 65) + 1LL;
    if ( v10 <= *((_QWORD *)this + 66) )
    {
      v10 = *((_QWORD *)this + 66);
    }
    else
    {
      v11 = (void *)SRCache_AllocStringBuffer((unsigned int)v10);
      v13 = v11;
      if ( !v11 )
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          (wil::details::in1diag3 *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (wil::details *)0x8007000ELL,
          v12);
        v15 = 310;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          (wil::details::in1diag3 *)v15,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (wil::details *)v14,
          a4);
        return v14;
      }
      memcpy_0(v11, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      v17 = *(_QWORD *)this;
      *(_QWORD *)this = v13;
      if ( v17 )
        SRCache_Free();
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v10;
    }
    v18 = (unsigned __int16 *)*((_QWORD *)this + 67);
    if ( v7 )
    {
      v22 = 0;
      for ( i = &v18[*((_QWORD *)this + 65)]; v22 < v6; ++i )
      {
        if ( *v4 == 94 )
          *i++ = 94;
        ++v22;
        *i = *v4++;
      }
      *i = 0;
    }
    else
    {
      v19 = StringCchCatW(v18, v10, v4);
      v21 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          (wil::details::in1diag3 *)0x139,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (wil::details *)(unsigned int)v19,
          v20);
        return v21;
      }
    }
    *((_QWORD *)this + 65) += v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180006ddc  push    rbx
0x180006dde  push    rbp
0x180006ddf  push    rsi
0x180006de0  push    rdi
0x180006de1  push    r12
0x180006de3  push    r13
0x180006de5  push    r14
0x180006de7  push    r15
0x180006de9  sub     rsp, 28h
0x180006ded  xor     r12d, r12d
0x180006df0  mov     rdi, rdx
0x180006df3  mov     rbx, rcx
0x180006df6  test    rdx, rdx
0x180006df9  jz      loc_180006F60
0x180006dff  lea     r13d, [r12+5Eh]
0x180006e04  mov     esi, r12d
0x180006e07  mov     r14d, r12d
0x180006e0a  mov     rcx, rdx
0x180006e0d  cmp     [rdx], r12w
0x180006e11  jz      short loc_180006E38
0x180006e13  inc     rsi
0x180006e16  cmp     rsi, 7FFFFFFFh
0x180006e1d  jnb     short loc_180006E89
0x180006e1f  cmp     [rcx], r13w
0x180006e23  lea     rax, [r14+1]
0x180006e27  cmovnz  rax, r14
0x180006e2b  add     rcx, 2
0x180006e2f  mov     r14, rax
0x180006e32  cmp     [rcx], r12w
0x180006e36  jnz     short loc_180006E13
0x180006e38  mov     rbp, [rbx+208h]
0x180006e3f  lea     rcx, [r14+rsi]
0x180006e43  mov     rax, [rbx+210h]
0x180006e4a  inc     rbp
0x180006e4d  add     rbp, rcx
0x180006e50  cmp     rbp, rax
0x180006e53  jbe     loc_180006EE6
0x180006e59  mov     ecx, ebp
0x180006e5b  call    cs:__imp_SRCache_AllocStringBuffer
0x180006e61  mov     r15, rax
0x180006e64  test    rax, rax
0x180006e67  jnz     short loc_180006EA9
0x180006e69  mov     ebx, 8007000Eh
0x180006e6e  lea     rdx, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006e75  mov     r8d, ebx; wil::details *
0x180006e78  mov     ecx, 193h; this
0x180006e7d  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180006e82  mov     ecx, 136h
0x180006e87  jmp     short loc_180006E93
0x180006e89  mov     ebx, 80070057h
0x180006e8e  mov     ecx, 135h; this
0x180006e93  lea     rdx, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006e9a  mov     r8d, ebx; wil::details *
0x180006e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180006ea2  mov     eax, ebx
0x180006ea4  jmp     loc_180006F62
0x180006ea9  mov     r8, [rbx+210h]
0x180006eb0  mov     rcx, r15; void *
0x180006eb3  mov     rdx, [rbx+218h]; Src
0x180006eba  add     r8, r8; Size
0x180006ebd  call    memcpy_0
0x180006ec2  mov     rcx, [rbx]
0x180006ec5  mov     [rbx], r15
0x180006ec8  test    rcx, rcx
0x180006ecb  jz      short loc_180006ED3
0x180006ecd  call    cs:__imp_SRCache_Free
0x180006ed3  mov     rax, [rbx]
0x180006ed6  mov     [rbx+218h], rax
0x180006edd  mov     [rbx+210h], rbp
0x180006ee4  jmp     short loc_180006EE9
0x180006ee6  mov     rbp, rax
0x180006ee9  mov     rcx, [rbx+218h]; unsigned __int16 *
0x180006ef0  test    r14, r14
0x180006ef3  jnz     short loc_180006F1E
0x180006ef5  mov     r8, rdi; unsigned __int16 *
0x180006ef8  mov     rdx, rbp; unsigned __int64
0x180006efb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f00  mov     edi, eax
0x180006f02  test    eax, eax
0x180006f04  jns     short loc_180006F59
0x180006f06  mov     r8d, eax; wil::details *
0x180006f09  lea     rdx, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006f10  mov     ecx, 139h; this
0x180006f15  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180006f1a  mov     eax, edi
0x180006f1c  jmp     short loc_180006F62
0x180006f1e  mov     rax, [rbx+208h]
0x180006f25  mov     rdx, r12
0x180006f28  lea     rcx, [rcx+rax*2]
0x180006f2c  test    rsi, rsi
0x180006f2f  jz      short loc_180006F55
0x180006f31  cmp     [rdi], r13w
0x180006f35  jnz     short loc_180006F3F
0x180006f37  mov     [rcx], r13w
0x180006f3b  add     rcx, 2
0x180006f3f  movzx   eax, word ptr [rdi]
0x180006f42  inc     rdx
0x180006f45  mov     [rcx], ax
0x180006f48  add     rdi, 2
0x180006f4c  add     rcx, 2
0x180006f50  cmp     rdx, rsi
0x180006f53  jb      short loc_180006F31
0x180006f55  mov     [rcx], r12w
0x180006f59  add     [rbx+208h], rsi
0x180006f60  xor     eax, eax
0x180006f62  add     rsp, 28h
0x180006f66  pop     r15
0x180006f68  pop     r14
0x180006f6a  pop     r13
0x180006f6c  pop     r12
0x180006f6e  pop     rdi
0x180006f6f  pop     rsi
0x180006f70  pop     rbp
0x180006f71  pop     rbx
0x180006f72  retn
```
