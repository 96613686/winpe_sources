# TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x180004ef8`
- end: `0x180004f66`
- name: `?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z`
- size: `110`
- prototype: `int __fastcall(wchar_t **this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001da0`
- `0x180005aec`

## callees

- `0x180004ef8`
- `0x180005258`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180004f24`
- `msvcrt!_wcsupr` at `0x180004f24`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004f13`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004f13`

## pseudocode

```c
int __fastcall TOKEN_KEY::CreateCacheKey(
        wchar_t **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  const unsigned __int16 *v7; // rdi
  int result; // eax
  TOKEN_KEY *v9; // rcx
  int i; // ecx
  unsigned __int16 v11; // ax

  v7 = a2;
  result = STRU::Copy((STRU *)(this + 1), a2);
  if ( result >= 0 )
  {
    _wcsupr(this[5]);
    result = TOKEN_KEY::GeneratePasswordHash(v9, a3, (struct STRU *)(this + 8));
    if ( result >= 0 )
    {
      *((_DWORD *)this + 30) = a4;
      for ( i = 0; ; i = v11 + 101 * i )
      {
        v11 = *v7;
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
0x180004ef8  push    rbx
0x180004efa  push    rbp
0x180004efb  push    rsi
0x180004efc  push    rdi
0x180004efd  push    r14
0x180004eff  sub     rsp, 20h
0x180004f03  mov     rbx, rcx
0x180004f06  mov     esi, r9d
0x180004f09  add     rcx, 8
0x180004f0d  mov     rbp, r8
0x180004f10  mov     rdi, rdx
0x180004f13  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004f19  xor     r14d, r14d
0x180004f1c  test    eax, eax
0x180004f1e  js      short loc_180004F5B
0x180004f20  mov     rcx, [rbx+28h]; String
0x180004f24  call    cs:__imp__wcsupr
0x180004f2a  lea     r8, [rbx+40h]; struct STRU *
0x180004f2e  mov     rdx, rbp; unsigned __int16 *
0x180004f31  call    ?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z; TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)
0x180004f36  test    eax, eax
0x180004f38  js      short loc_180004F5B
0x180004f3a  mov     [rbx+78h], esi
0x180004f3d  mov     ecx, r14d
0x180004f40  jmp     short loc_180004F4E
0x180004f42  imul    ecx, 65h ; 'e'
0x180004f45  lea     rdi, [rdi+2]
0x180004f49  movzx   eax, ax
0x180004f4c  add     ecx, eax
0x180004f4e  movzx   eax, word ptr [rdi]
0x180004f51  test    ax, ax
0x180004f54  jnz     short loc_180004F42
0x180004f56  mov     [rbx+7Ch], ecx
0x180004f59  xor     eax, eax
0x180004f5b  add     rsp, 20h
0x180004f5f  pop     r14
0x180004f61  pop     rdi
0x180004f62  pop     rsi
0x180004f63  pop     rbp
0x180004f64  pop     rbx
0x180004f65  retn
```
