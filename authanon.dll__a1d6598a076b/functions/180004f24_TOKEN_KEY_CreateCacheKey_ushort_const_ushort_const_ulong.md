# TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x180004f24`
- end: `0x180004f9f`
- name: `?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z`
- size: `123`
- prototype: `int(TOKEN_KEY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800043b8`
- `0x180004e6c`

## callees

- `0x180004f24`
- `0x180004fa8`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180004f5b`
- `msvcrt!_wcsupr` at `0x180004f5b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004f52`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004f52`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004f41`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004f41`

## pseudocode

```c
int __fastcall TOKEN_KEY::CreateCacheKey(TOKEN_KEY *this, const unsigned __int16 *a2, const BYTE *a3, int a4)
{
  const unsigned __int16 *v7; // rbx
  int result; // eax
  wchar_t *Str; // rax
  TOKEN_KEY *v10; // rcx
  int i; // ecx
  unsigned __int16 v12; // ax

  v7 = a2;
  result = STRU::Copy((TOKEN_KEY *)((char *)this + 8), a2);
  if ( result >= 0 )
  {
    Str = STRU::QueryStr((TOKEN_KEY *)((char *)this + 8));
    _wcsupr(Str);
    result = TOKEN_KEY::GeneratePasswordHash(v10, a3, (TOKEN_KEY *)((char *)this + 64));
    if ( result >= 0 )
    {
      *((_DWORD *)this + 30) = a4;
      for ( i = 0; ; i = v12 + 101 * i )
      {
        v12 = *v7;
        if ( !*v7 )
          break;
        ++v7;
      }
      *((_DWORD *)this + 31) = i;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004f24  push    rbx
0x180004f26  push    rbp
0x180004f27  push    rsi
0x180004f28  push    rdi
0x180004f29  push    r14
0x180004f2b  push    r15
0x180004f2d  sub     rsp, 28h
0x180004f31  mov     rdi, rcx
0x180004f34  mov     esi, r9d
0x180004f37  add     rcx, 8
0x180004f3b  mov     r14, r8
0x180004f3e  mov     rbx, rdx
0x180004f41  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004f47  xor     r15d, r15d
0x180004f4a  test    eax, eax
0x180004f4c  js      short loc_180004F92
0x180004f4e  lea     rcx, [rdi+8]
0x180004f52  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004f58  mov     rcx, rax; String
0x180004f5b  call    cs:__imp__wcsupr
0x180004f61  lea     r8, [rdi+40h]; struct STRU *
0x180004f65  mov     rdx, r14; unsigned __int16 *
0x180004f68  call    ?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z; TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)
0x180004f6d  test    eax, eax
0x180004f6f  js      short loc_180004F92
0x180004f71  mov     [rdi+78h], esi
0x180004f74  mov     ecx, r15d
0x180004f77  jmp     short loc_180004F85
0x180004f79  imul    ecx, 65h ; 'e'
0x180004f7c  lea     rbx, [rbx+2]
0x180004f80  movzx   eax, ax
0x180004f83  add     ecx, eax
0x180004f85  movzx   eax, word ptr [rbx]
0x180004f88  test    ax, ax
0x180004f8b  jnz     short loc_180004F79
0x180004f8d  mov     [rdi+7Ch], ecx
0x180004f90  xor     eax, eax
0x180004f92  add     rsp, 28h
0x180004f96  pop     r15
0x180004f98  pop     r14
0x180004f9a  pop     rdi
0x180004f9b  pop     rsi
0x180004f9c  pop     rbp
0x180004f9d  pop     rbx
0x180004f9e  retn
```
