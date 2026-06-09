# SepSddlDaclFromSDDLString

- ea: `0x18002b5d4`
- end: `0x18002b6b1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: `__int64 __fastcall(_WORD *, __int64, int *, PVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002bc04`

## callees

- `0x18002b5d4`
- `0x18002b6b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18002b67c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002b67c`

## pseudocode

```c
__int64 __fastcall SepSddlDaclFromSDDLString(_WORD *a1, __int64 a2, int *a3, PVOID *a4)
{
  _WORD *v6; // r9
  int v7; // ebp
  unsigned int AclForString; // ebx
  _WORD *i; // rcx
  PVOID P; // [rsp+40h] [rbp+8h] BYREF
  _WORD *v12; // [rsp+50h] [rbp+18h]

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
      AclForString = SepSddlGetAclForString(v6 + 2, (int)&P);
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
0x18002b5d4  mov     rax, rsp
0x18002b5d7  mov     [rax+10h], rbx
0x18002b5db  mov     [rax+20h], rbp
0x18002b5df  push    rsi
0x18002b5e0  push    rdi
0x18002b5e1  push    r14
0x18002b5e3  sub     rsp, 20h
0x18002b5e7  xor     r14d, r14d
0x18002b5ea  mov     rdi, r9
0x18002b5ed  mov     [rax+8], r14
0x18002b5f1  mov     rsi, r8
0x18002b5f4  mov     [rax+18h], r14
0x18002b5f8  mov     [r9], r14
0x18002b5fb  mov     [r8], r14d
0x18002b5fe  jmp     short loc_18002B604
0x18002b600  add     rcx, 2
0x18002b604  movzx   eax, word ptr [rcx]
0x18002b607  cmp     ax, 20h ; ' '
0x18002b60b  jz      short loc_18002B600
0x18002b60d  cmp     ax, 44h ; 'D'
0x18002b611  jnz     loc_18002B698
0x18002b617  lea     r9, [rcx+2]
0x18002b61b  cmp     word ptr [r9], 3Ah ; ':'
0x18002b620  jnz     short loc_18002B698
0x18002b622  cmp     word ptr [r9+2], 50h ; 'P'
0x18002b628  lea     r8, [rsp+38h+arg_10]
0x18002b62d  mov     edx, 8
0x18002b632  mov     ebp, 1008h
0x18002b637  cmovnz  r9, rcx
0x18002b63b  cmovnz  ebp, edx
0x18002b63e  lea     rdx, [rsp+38h+P]; int
0x18002b643  lea     rcx, [r9+4]; Str1
0x18002b647  call    SepSddlGetAclForString
0x18002b64c  mov     ebx, eax
0x18002b64e  test    eax, eax
0x18002b650  jnz     short loc_18002B670
0x18002b652  mov     rcx, [rsp+38h+arg_10]
0x18002b657  jmp     short loc_18002B65D
0x18002b659  lea     rcx, [rcx+2]
0x18002b65d  movzx   eax, word ptr [rcx]
0x18002b660  cmp     ax, 20h ; ' '
0x18002b664  jz      short loc_18002B659
0x18002b666  test    ax, ax
0x18002b669  jz      short loc_18002B68C
0x18002b66b  mov     ebx, 0C000000Dh
0x18002b670  mov     rcx, [rsp+38h+P]; P
0x18002b675  test    rcx, rcx
0x18002b678  jz      short loc_18002B688
0x18002b67a  xor     edx, edx; Tag
0x18002b67c  call    cs:__imp_ExFreePoolWithTag
0x18002b683  nop     dword ptr [rax+rax+00h]
0x18002b688  mov     eax, ebx
0x18002b68a  jmp     short loc_18002B69D
0x18002b68c  mov     rax, [rsp+38h+P]
0x18002b691  mov     [rdi], rax
0x18002b694  mov     [rsi], ebp
0x18002b696  jmp     short loc_18002B688
0x18002b698  mov     eax, 0C000000Dh
0x18002b69d  mov     rbx, [rsp+38h+arg_8]
0x18002b6a2  mov     rbp, [rsp+38h+arg_18]
0x18002b6a7  add     rsp, 20h
0x18002b6ab  pop     r14
0x18002b6ad  pop     rdi
0x18002b6ae  pop     rsi
0x18002b6af  retn
```
