# StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)

- ea: `0x180078da0`
- end: `0x180078f46`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z`
- size: `422`
- prototype: `int(StateRepository::Cache::Key_NoThrow *__hidden this, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180078f4c`
- `0x18007a4e4`

## callees

- `0x180007f42`
- `0x18000b064`
- `0x18000b9a4`
- `0x180078da0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078e9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180078e9b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180078e1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180078e1f`

## string_xrefs

- `0x180078e32`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180078e61`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180078ed9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        const wchar_t *a2)
{
  const wchar_t *v2; // rdi
  unsigned __int64 v4; // rsi
  __int64 v5; // r14
  const wchar_t *v6; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // rbp
  void *v9; // rax
  void *v10; // r15
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v14; // rcx
  wchar_t *v15; // rcx
  int v16; // eax
  unsigned int v17; // edi
  unsigned __int64 v18; // rdx
  wchar_t *i; // rcx
  int v20; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = a2;
  if ( a2 )
  {
    v4 = 0;
    v5 = 0;
    v6 = a2;
    if ( *a2 )
    {
      while ( ++v4 < 0x7FFFFFFF )
      {
        v7 = v5 + 1;
        if ( *v6 != 94 )
          v7 = v5;
        ++v6;
        v5 = v7;
        if ( !*v6 )
          goto LABEL_7;
      }
      v11 = -2147024809;
      v12 = 309;
      goto LABEL_11;
    }
LABEL_7:
    v8 = v5 + v4 + *((_QWORD *)this + 65) + 1LL;
    if ( v8 <= *((_QWORD *)this + 66) )
    {
      v8 = *((_QWORD *)this + 66);
    }
    else
    {
      v9 = (void *)SRCache_AllocStringBuffer((unsigned int)v8);
      v10 = v9;
      if ( !v9 )
      {
        v11 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          v20);
        v12 = 310;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)v11,
          v20);
        return v11;
      }
      memcpy_0(v9, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      v14 = *(_QWORD *)this;
      *(_QWORD *)this = v10;
      if ( v14 )
        SRCache_Free();
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v8;
    }
    v15 = (wchar_t *)*((_QWORD *)this + 67);
    if ( v5 )
    {
      v18 = 0;
      for ( i = &v15[*((_QWORD *)this + 65)]; v18 < v4; ++i )
      {
        if ( *v2 == 94 )
          *i++ = 94;
        ++v18;
        *i = *v2++;
      }
      *i = 0;
    }
    else
    {
      v16 = StringCchCatW(v15, v8, v2);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)(unsigned int)v16,
          v20);
        return v17;
      }
    }
    *((_QWORD *)this + 65) += v4;
  }
  return 0;
}

```

## disassembly

```asm
0x180078da0  push    rbx
0x180078da2  push    rbp
0x180078da3  push    rsi
0x180078da4  push    rdi
0x180078da5  push    r12
0x180078da7  push    r13
0x180078da9  push    r14
0x180078dab  push    r15
0x180078dad  sub     rsp, 28h
0x180078db1  xor     r12d, r12d
0x180078db4  mov     rdi, rdx
0x180078db7  mov     rbx, rcx
0x180078dba  test    rdx, rdx
0x180078dbd  jz      loc_180078F33
0x180078dc3  lea     r13d, [r12+5Eh]
0x180078dc8  mov     esi, r12d
0x180078dcb  mov     r14d, r12d
0x180078dce  mov     rcx, rdx
0x180078dd1  cmp     [rdx], r12w
0x180078dd5  jz      short loc_180078DFC
0x180078dd7  inc     rsi
0x180078dda  cmp     rsi, 7FFFFFFFh
0x180078de1  jnb     short loc_180078E52
0x180078de3  cmp     [rcx], r13w
0x180078de7  lea     rax, [r14+1]
0x180078deb  cmovnz  rax, r14
0x180078def  add     rcx, 2
0x180078df3  mov     r14, rax
0x180078df6  cmp     [rcx], r12w
0x180078dfa  jnz     short loc_180078DD7
0x180078dfc  mov     rbp, [rbx+208h]
0x180078e03  lea     rcx, [r14+rsi]
0x180078e07  mov     rax, [rbx+210h]
0x180078e0e  inc     rbp
0x180078e11  add     rbp, rcx
0x180078e14  cmp     rbp, rax
0x180078e17  jbe     loc_180078EB4
0x180078e1d  mov     ecx, ebp
0x180078e1f  call    cs:__imp_SRCache_AllocStringBuffer
0x180078e25  mov     r15, rax
0x180078e28  test    rax, rax
0x180078e2b  jnz     short loc_180078E77
0x180078e2d  mov     rcx, [rsp+68h]; this
0x180078e32  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078e39  mov     ebx, 8007000Eh
0x180078e3e  mov     edx, 193h; void *
0x180078e43  mov     r9d, ebx; char *
0x180078e46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078e4b  mov     edx, 136h
0x180078e50  jmp     short loc_180078E5C
0x180078e52  mov     ebx, 80070057h
0x180078e57  mov     edx, 135h; void *
0x180078e5c  mov     rcx, [rsp+68h]; this
0x180078e61  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078e68  mov     r9d, ebx; char *
0x180078e6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078e70  mov     eax, ebx
0x180078e72  jmp     loc_180078F35
0x180078e77  mov     r8, [rbx+210h]
0x180078e7e  mov     rcx, r15; void *
0x180078e81  mov     rdx, [rbx+218h]; Src
0x180078e88  add     r8, r8; Size
0x180078e8b  call    memcpy_0
0x180078e90  mov     rcx, [rbx]
0x180078e93  mov     [rbx], r15
0x180078e96  test    rcx, rcx
0x180078e99  jz      short loc_180078EA1
0x180078e9b  call    cs:__imp_SRCache_Free
0x180078ea1  mov     rax, [rbx]
0x180078ea4  mov     [rbx+218h], rax
0x180078eab  mov     [rbx+210h], rbp
0x180078eb2  jmp     short loc_180078EB7
0x180078eb4  mov     rbp, rax
0x180078eb7  mov     rcx, [rbx+218h]; wchar_t *
0x180078ebe  test    r14, r14
0x180078ec1  jnz     short loc_180078EF1
0x180078ec3  mov     r8, rdi; wchar_t *
0x180078ec6  mov     rdx, rbp; unsigned __int64
0x180078ec9  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180078ece  mov     edi, eax
0x180078ed0  test    eax, eax
0x180078ed2  jns     short loc_180078F2C
0x180078ed4  mov     rcx, [rsp+68h]; this
0x180078ed9  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180078ee0  mov     r9d, eax; char *
0x180078ee3  mov     edx, 139h; void *
0x180078ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078eed  mov     eax, edi
0x180078eef  jmp     short loc_180078F35
0x180078ef1  mov     rax, [rbx+208h]
0x180078ef8  mov     rdx, r12
0x180078efb  lea     rcx, [rcx+rax*2]
0x180078eff  test    rsi, rsi
0x180078f02  jz      short loc_180078F28
0x180078f04  cmp     [rdi], r13w
0x180078f08  jnz     short loc_180078F12
0x180078f0a  mov     [rcx], r13w
0x180078f0e  add     rcx, 2
0x180078f12  movzx   eax, word ptr [rdi]
0x180078f15  inc     rdx
0x180078f18  mov     [rcx], ax
0x180078f1b  add     rdi, 2
0x180078f1f  add     rcx, 2
0x180078f23  cmp     rdx, rsi
0x180078f26  jb      short loc_180078F04
0x180078f28  mov     [rcx], r12w
0x180078f2c  add     [rbx+208h], rsi
0x180078f33  xor     eax, eax
0x180078f35  add     rsp, 28h
0x180078f39  pop     r15
0x180078f3b  pop     r14
0x180078f3d  pop     r13
0x180078f3f  pop     r12
0x180078f41  pop     rdi
0x180078f42  pop     rsi
0x180078f43  pop     rbp
0x180078f44  pop     rbx
0x180078f45  retn
```
