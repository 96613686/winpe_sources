# TOKEN_KEY::CreateCacheKey(ushort const *,ushort const *,ulong)

- ea: `0x180003c68`
- end: `0x180003cd6`
- name: `?CreateCacheKey@TOKEN_KEY@@QEAAJPEBG0K@Z`
- size: `110`
- prototype: `int __fastcall(wchar_t **this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001c70`
- `0x18000485c`

## callees

- `0x180003c68`
- `0x180003fc8`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180003c94`
- `msvcrt!_wcsupr` at `0x180003c94`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003c83`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003c83`

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
0x180003c68  push    rbx
0x180003c6a  push    rbp
0x180003c6b  push    rsi
0x180003c6c  push    rdi
0x180003c6d  push    r14
0x180003c6f  sub     rsp, 20h
0x180003c73  mov     rbx, rcx
0x180003c76  mov     esi, r9d
0x180003c79  add     rcx, 8
0x180003c7d  mov     rbp, r8
0x180003c80  mov     rdi, rdx
0x180003c83  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003c89  xor     r14d, r14d
0x180003c8c  test    eax, eax
0x180003c8e  js      short loc_180003CCB
0x180003c90  mov     rcx, [rbx+28h]; String
0x180003c94  call    cs:__imp__wcsupr
0x180003c9a  lea     r8, [rbx+40h]; struct STRU *
0x180003c9e  mov     rdx, rbp; unsigned __int16 *
0x180003ca1  call    ?GeneratePasswordHash@TOKEN_KEY@@QEAAJPEBGPEAVSTRU@@@Z; TOKEN_KEY::GeneratePasswordHash(ushort const *,STRU *)
0x180003ca6  test    eax, eax
0x180003ca8  js      short loc_180003CCB
0x180003caa  mov     [rbx+78h], esi
0x180003cad  mov     ecx, r14d
0x180003cb0  jmp     short loc_180003CBE
0x180003cb2  imul    ecx, 65h ; 'e'
0x180003cb5  lea     rdi, [rdi+2]
0x180003cb9  movzx   eax, ax
0x180003cbc  add     ecx, eax
0x180003cbe  movzx   eax, word ptr [rdi]
0x180003cc1  test    ax, ax
0x180003cc4  jnz     short loc_180003CB2
0x180003cc6  mov     [rbx+7Ch], ecx
0x180003cc9  xor     eax, eax
0x180003ccb  add     rsp, 20h
0x180003ccf  pop     r14
0x180003cd1  pop     rdi
0x180003cd2  pop     rsi
0x180003cd3  pop     rbp
0x180003cd4  pop     rbx
0x180003cd5  retn
```
