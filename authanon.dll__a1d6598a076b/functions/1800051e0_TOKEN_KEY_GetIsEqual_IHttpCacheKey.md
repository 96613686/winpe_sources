# TOKEN_KEY::GetIsEqual(IHttpCacheKey *)

- ea: `0x1800051e0`
- end: `0x180005254`
- name: `?GetIsEqual@TOKEN_KEY@@UEBA_NPEAVIHttpCacheKey@@@Z`
- size: `116`
- prototype: `bool __fastcall(TOKEN_KEY *__hidden this, struct IHttpCacheKey *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800051e0`
- `0x180006010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000520b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18000520b`

## pseudocode

```c
bool __fastcall TOKEN_KEY::GetIsEqual(TOKEN_KEY *this, struct IHttpCacheKey *a2)
{
  __int64 v4; // rdi
  const unsigned __int16 *Str; // rax
  __int64 v6; // rdi
  int v7; // edx
  int v8; // ecx

  v4 = (*(__int64 (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 40LL))(a2);
  Str = STRU::QueryStr((TOKEN_KEY *)((char *)this + 8));
  v6 = v4 - (_QWORD)Str;
  do
  {
    v7 = *(const unsigned __int16 *)((char *)Str + v6);
    v8 = *Str - v7;
    if ( v8 )
      break;
    ++Str;
  }
  while ( v7 );
  return !v8
      && *((_DWORD *)this + 30) == (*(unsigned int (__fastcall **)(struct IHttpCacheKey *))(*(_QWORD *)a2 + 56LL))(a2);
}

```

## disassembly

```asm
0x1800051e0  mov     [rsp+arg_0], rbx
0x1800051e5  mov     [rsp+arg_8], rsi
0x1800051ea  push    rdi
0x1800051eb  sub     rsp, 20h
0x1800051ef  mov     rax, [rdx]
0x1800051f2  mov     rsi, rcx
0x1800051f5  mov     rcx, rdx
0x1800051f8  mov     rbx, rdx
0x1800051fb  mov     rax, [rax+28h]
0x1800051ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005204  lea     rcx, [rsi+8]
0x180005208  mov     rdi, rax
0x18000520b  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180005211  sub     rdi, rax
0x180005214  movzx   ecx, word ptr [rax]
0x180005217  movzx   edx, word ptr [rax+rdi]
0x18000521b  sub     ecx, edx
0x18000521d  jnz     short loc_180005227
0x18000521f  add     rax, 2
0x180005223  test    edx, edx
0x180005225  jnz     short loc_180005214
0x180005227  test    ecx, ecx
0x180005229  jnz     short loc_180005242
0x18000522b  mov     rax, [rbx]
0x18000522e  mov     rcx, rbx
0x180005231  mov     rax, [rax+38h]
0x180005235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000523a  cmp     [rsi+78h], eax
0x18000523d  setz    al
0x180005240  jmp     short loc_180005244
0x180005242  xor     al, al
0x180005244  mov     rbx, [rsp+28h+arg_0]
0x180005249  mov     rsi, [rsp+28h+arg_8]
0x18000524e  add     rsp, 20h
0x180005252  pop     rdi
0x180005253  retn
```
