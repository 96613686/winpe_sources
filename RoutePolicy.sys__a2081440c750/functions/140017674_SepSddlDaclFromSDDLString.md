# SepSddlDaclFromSDDLString

- ea: `0x140017674`
- end: `0x140017751`
- name: `SepSddlDaclFromSDDLString`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140017ca4`

## callees

- `0x140017674`
- `0x140017758`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001771c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001771c`

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
0x140017674  mov     rax, rsp
0x140017677  mov     [rax+10h], rbx
0x14001767b  mov     [rax+20h], rbp
0x14001767f  push    rsi
0x140017680  push    rdi
0x140017681  push    r14
0x140017683  sub     rsp, 20h
0x140017687  xor     r14d, r14d
0x14001768a  mov     rdi, r9
0x14001768d  mov     [rax+8], r14
0x140017691  mov     rsi, r8
0x140017694  mov     [rax+18h], r14
0x140017698  mov     [r9], r14
0x14001769b  mov     [r8], r14d
0x14001769e  jmp     short loc_1400176A4
0x1400176a0  add     rcx, 2
0x1400176a4  movzx   eax, word ptr [rcx]
0x1400176a7  cmp     ax, 20h ; ' '
0x1400176ab  jz      short loc_1400176A0
0x1400176ad  cmp     ax, 44h ; 'D'
0x1400176b1  jnz     loc_140017738
0x1400176b7  lea     r9, [rcx+2]
0x1400176bb  cmp     word ptr [r9], 3Ah ; ':'
0x1400176c0  jnz     short loc_140017738
0x1400176c2  cmp     word ptr [r9+2], 50h ; 'P'
0x1400176c8  lea     r8, [rsp+38h+arg_10]
0x1400176cd  mov     edx, 8
0x1400176d2  mov     ebp, 1008h
0x1400176d7  cmovnz  r9, rcx
0x1400176db  cmovnz  ebp, edx
0x1400176de  lea     rdx, [rsp+38h+P]; int
0x1400176e3  lea     rcx, [r9+4]; Str1
0x1400176e7  call    SepSddlGetAclForString
0x1400176ec  mov     ebx, eax
0x1400176ee  test    eax, eax
0x1400176f0  jnz     short loc_140017710
0x1400176f2  mov     rcx, [rsp+38h+arg_10]
0x1400176f7  jmp     short loc_1400176FD
0x1400176f9  lea     rcx, [rcx+2]
0x1400176fd  movzx   eax, word ptr [rcx]
0x140017700  cmp     ax, 20h ; ' '
0x140017704  jz      short loc_1400176F9
0x140017706  test    ax, ax
0x140017709  jz      short loc_14001772C
0x14001770b  mov     ebx, 0C000000Dh
0x140017710  mov     rcx, [rsp+38h+P]; P
0x140017715  test    rcx, rcx
0x140017718  jz      short loc_140017728
0x14001771a  xor     edx, edx; Tag
0x14001771c  call    cs:__imp_ExFreePoolWithTag
0x140017723  nop     dword ptr [rax+rax+00h]
0x140017728  mov     eax, ebx
0x14001772a  jmp     short loc_14001773D
0x14001772c  mov     rax, [rsp+38h+P]
0x140017731  mov     [rdi], rax
0x140017734  mov     [rsi], ebp
0x140017736  jmp     short loc_140017728
0x140017738  mov     eax, 0C000000Dh
0x14001773d  mov     rbx, [rsp+38h+arg_8]
0x140017742  mov     rbp, [rsp+38h+arg_18]
0x140017747  add     rsp, 20h
0x14001774b  pop     r14
0x14001774d  pop     rdi
0x14001774e  pop     rsi
0x14001774f  retn
```
