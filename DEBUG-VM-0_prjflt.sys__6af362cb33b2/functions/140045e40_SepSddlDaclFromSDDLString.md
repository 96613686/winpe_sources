# SepSddlDaclFromSDDLString

- ea: `0x140045e40`
- end: `0x140045f1d`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140046470`

## callees

- `0x140045e40`
- `0x140045f24`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140045ee8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045ee8`

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
0x140045e40  mov     rax, rsp
0x140045e43  mov     [rax+10h], rbx
0x140045e47  mov     [rax+20h], rbp
0x140045e4b  push    rsi
0x140045e4c  push    rdi
0x140045e4d  push    r14
0x140045e4f  sub     rsp, 20h
0x140045e53  xor     r14d, r14d
0x140045e56  mov     rdi, r9
0x140045e59  mov     [rax+8], r14
0x140045e5d  mov     rsi, r8
0x140045e60  mov     [rax+18h], r14
0x140045e64  mov     [r9], r14
0x140045e67  mov     [r8], r14d
0x140045e6a  jmp     short loc_140045E70
0x140045e6c  add     rcx, 2
0x140045e70  movzx   eax, word ptr [rcx]
0x140045e73  cmp     ax, 20h ; ' '
0x140045e77  jz      short loc_140045E6C
0x140045e79  cmp     ax, 44h ; 'D'
0x140045e7d  jnz     loc_140045F04
0x140045e83  lea     r9, [rcx+2]
0x140045e87  cmp     word ptr [r9], 3Ah ; ':'
0x140045e8c  jnz     short loc_140045F04
0x140045e8e  cmp     word ptr [r9+2], 50h ; 'P'
0x140045e94  lea     r8, [rsp+38h+arg_10]
0x140045e99  mov     edx, 8
0x140045e9e  mov     ebp, 1008h
0x140045ea3  cmovnz  r9, rcx
0x140045ea7  cmovnz  ebp, edx
0x140045eaa  lea     rdx, [rsp+38h+P]; int
0x140045eaf  lea     rcx, [r9+4]; Str1
0x140045eb3  call    SepSddlGetAclForString
0x140045eb8  mov     ebx, eax
0x140045eba  test    eax, eax
0x140045ebc  jnz     short loc_140045EDC
0x140045ebe  mov     rcx, [rsp+38h+arg_10]
0x140045ec3  jmp     short loc_140045EC9
0x140045ec5  lea     rcx, [rcx+2]
0x140045ec9  movzx   eax, word ptr [rcx]
0x140045ecc  cmp     ax, 20h ; ' '
0x140045ed0  jz      short loc_140045EC5
0x140045ed2  test    ax, ax
0x140045ed5  jz      short loc_140045EF8
0x140045ed7  mov     ebx, 0C000000Dh
0x140045edc  mov     rcx, [rsp+38h+P]; P
0x140045ee1  test    rcx, rcx
0x140045ee4  jz      short loc_140045EF4
0x140045ee6  xor     edx, edx; Tag
0x140045ee8  call    cs:__imp_ExFreePoolWithTag
0x140045eef  nop     dword ptr [rax+rax+00h]
0x140045ef4  mov     eax, ebx
0x140045ef6  jmp     short loc_140045F09
0x140045ef8  mov     rax, [rsp+38h+P]
0x140045efd  mov     [rdi], rax
0x140045f00  mov     [rsi], ebp
0x140045f02  jmp     short loc_140045EF4
0x140045f04  mov     eax, 0C000000Dh
0x140045f09  mov     rbx, [rsp+38h+arg_8]
0x140045f0e  mov     rbp, [rsp+38h+arg_18]
0x140045f13  add     rsp, 20h
0x140045f17  pop     r14
0x140045f19  pop     rdi
0x140045f1a  pop     rsi
0x140045f1b  retn
```
