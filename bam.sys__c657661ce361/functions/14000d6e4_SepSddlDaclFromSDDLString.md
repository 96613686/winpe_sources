# SepSddlDaclFromSDDLString

- ea: `0x14000d6e4`
- end: `0x14000d7c1`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000dd04`

## callees

- `0x14000d6e4`
- `0x14000d7c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d78c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d78c`

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
0x14000d6e4  mov     rax, rsp
0x14000d6e7  mov     [rax+10h], rbx
0x14000d6eb  mov     [rax+20h], rbp
0x14000d6ef  push    rsi
0x14000d6f0  push    rdi
0x14000d6f1  push    r14
0x14000d6f3  sub     rsp, 20h
0x14000d6f7  xor     r14d, r14d
0x14000d6fa  mov     rdi, r9
0x14000d6fd  mov     [rax+8], r14
0x14000d701  mov     rsi, r8
0x14000d704  mov     [rax+18h], r14
0x14000d708  mov     [r9], r14
0x14000d70b  mov     [r8], r14d
0x14000d70e  jmp     short loc_14000D714
0x14000d710  add     rcx, 2
0x14000d714  movzx   eax, word ptr [rcx]
0x14000d717  cmp     ax, 20h ; ' '
0x14000d71b  jz      short loc_14000D710
0x14000d71d  cmp     ax, 44h ; 'D'
0x14000d721  jnz     loc_14000D7A8
0x14000d727  lea     r9, [rcx+2]
0x14000d72b  cmp     word ptr [r9], 3Ah ; ':'
0x14000d730  jnz     short loc_14000D7A8
0x14000d732  cmp     word ptr [r9+2], 50h ; 'P'
0x14000d738  lea     r8, [rsp+38h+arg_10]
0x14000d73d  mov     edx, 8
0x14000d742  mov     ebp, 1008h
0x14000d747  cmovnz  r9, rcx
0x14000d74b  cmovnz  ebp, edx
0x14000d74e  lea     rdx, [rsp+38h+P]; int
0x14000d753  lea     rcx, [r9+4]; Str1
0x14000d757  call    SepSddlGetAclForString
0x14000d75c  mov     ebx, eax
0x14000d75e  test    eax, eax
0x14000d760  jnz     short loc_14000D780
0x14000d762  mov     rcx, [rsp+38h+arg_10]
0x14000d767  jmp     short loc_14000D76D
0x14000d769  lea     rcx, [rcx+2]
0x14000d76d  movzx   eax, word ptr [rcx]
0x14000d770  cmp     ax, 20h ; ' '
0x14000d774  jz      short loc_14000D769
0x14000d776  test    ax, ax
0x14000d779  jz      short loc_14000D79C
0x14000d77b  mov     ebx, 0C000000Dh
0x14000d780  mov     rcx, [rsp+38h+P]; P
0x14000d785  test    rcx, rcx
0x14000d788  jz      short loc_14000D798
0x14000d78a  xor     edx, edx; Tag
0x14000d78c  call    cs:__imp_ExFreePoolWithTag
0x14000d793  nop     dword ptr [rax+rax+00h]
0x14000d798  mov     eax, ebx
0x14000d79a  jmp     short loc_14000D7AD
0x14000d79c  mov     rax, [rsp+38h+P]
0x14000d7a1  mov     [rdi], rax
0x14000d7a4  mov     [rsi], ebp
0x14000d7a6  jmp     short loc_14000D798
0x14000d7a8  mov     eax, 0C000000Dh
0x14000d7ad  mov     rbx, [rsp+38h+arg_8]
0x14000d7b2  mov     rbp, [rsp+38h+arg_18]
0x14000d7b7  add     rsp, 20h
0x14000d7bb  pop     r14
0x14000d7bd  pop     rdi
0x14000d7be  pop     rsi
0x14000d7bf  retn
```
