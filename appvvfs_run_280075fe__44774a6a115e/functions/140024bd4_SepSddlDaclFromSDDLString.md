# SepSddlDaclFromSDDLString

- ea: `0x140024bd4`
- end: `0x140024cb1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140025204`

## callees

- `0x140024bd4`
- `0x140024cb8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024c7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024c7c`

## pseudocode

```c
__int64 __fastcall SepSddlDaclFromSDDLString(_WORD *a1, __int64 a2, int *a3, PVOID *a4)
{
  _WORD *v6; // r9
  int v7; // ebp
  unsigned int AclForString; // ebx
  wchar_t *i; // rcx
  PVOID P; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *v12; // [rsp+50h] [rbp+18h] BYREF

  P = 0;
  v12 = 0;
  *a4 = 0;
  *a3 = 0;
  while ( *a1 == 32 )
    ++a1;
  if ( *a1 == 68 )
  {
    v6 = a1 + 1;
    if ( a1[1] == 58 )
    {
      v7 = 4104;
      if ( a1[2] != 80 )
      {
        v6 = a1;
        v7 = 8;
      }
      AclForString = SepSddlGetAclForString(v6 + 2, &P, &v12);
      if ( !AclForString )
      {
        for ( i = v12; *i == 32; ++i )
          ;
        if ( !*i )
        {
          *a4 = P;
          *a3 = v7;
          return AclForString;
        }
        AclForString = -1073741811;
      }
      if ( P )
        ExFreePoolWithTag(P, 0);
      return AclForString;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140024bd4  mov     rax, rsp
0x140024bd7  mov     [rax+10h], rbx
0x140024bdb  mov     [rax+20h], rbp
0x140024bdf  push    rsi
0x140024be0  push    rdi
0x140024be1  push    r14
0x140024be3  sub     rsp, 20h
0x140024be7  xor     r14d, r14d
0x140024bea  mov     rdi, r9
0x140024bed  mov     [rax+8], r14
0x140024bf1  mov     rsi, r8
0x140024bf4  mov     [rax+18h], r14
0x140024bf8  mov     [r9], r14
0x140024bfb  mov     [r8], r14d
0x140024bfe  jmp     short loc_140024C04
0x140024c00  add     rcx, 2
0x140024c04  movzx   eax, word ptr [rcx]
0x140024c07  cmp     ax, 20h ; ' '
0x140024c0b  jz      short loc_140024C00
0x140024c0d  cmp     ax, 44h ; 'D'
0x140024c11  jnz     loc_140024C98
0x140024c17  lea     r9, [rcx+2]
0x140024c1b  cmp     word ptr [r9], 3Ah ; ':'
0x140024c20  jnz     short loc_140024C98
0x140024c22  cmp     word ptr [r9+2], 50h ; 'P'
0x140024c28  lea     r8, [rsp+38h+arg_10]
0x140024c2d  mov     edx, 8
0x140024c32  mov     ebp, 1008h
0x140024c37  cmovnz  r9, rcx
0x140024c3b  cmovnz  ebp, edx
0x140024c3e  lea     rdx, [rsp+38h+P]; int
0x140024c43  lea     rcx, [r9+4]; Str1
0x140024c47  call    SepSddlGetAclForString
0x140024c4c  mov     ebx, eax
0x140024c4e  test    eax, eax
0x140024c50  jnz     short loc_140024C70
0x140024c52  mov     rcx, [rsp+38h+arg_10]
0x140024c57  jmp     short loc_140024C5D
0x140024c59  lea     rcx, [rcx+2]
0x140024c5d  movzx   eax, word ptr [rcx]
0x140024c60  cmp     ax, 20h ; ' '
0x140024c64  jz      short loc_140024C59
0x140024c66  test    ax, ax
0x140024c69  jz      short loc_140024C8C
0x140024c6b  mov     ebx, 0C000000Dh
0x140024c70  mov     rcx, [rsp+38h+P]; P
0x140024c75  test    rcx, rcx
0x140024c78  jz      short loc_140024C88
0x140024c7a  xor     edx, edx; Tag
0x140024c7c  call    cs:__imp_ExFreePoolWithTag
0x140024c83  nop     dword ptr [rax+rax+00h]
0x140024c88  mov     eax, ebx
0x140024c8a  jmp     short loc_140024C9D
0x140024c8c  mov     rax, [rsp+38h+P]
0x140024c91  mov     [rdi], rax
0x140024c94  mov     [rsi], ebp
0x140024c96  jmp     short loc_140024C88
0x140024c98  mov     eax, 0C000000Dh
0x140024c9d  mov     rbx, [rsp+38h+arg_8]
0x140024ca2  mov     rbp, [rsp+38h+arg_18]
0x140024ca7  add     rsp, 20h
0x140024cab  pop     r14
0x140024cad  pop     rdi
0x140024cae  pop     rsi
0x140024caf  retn
```
