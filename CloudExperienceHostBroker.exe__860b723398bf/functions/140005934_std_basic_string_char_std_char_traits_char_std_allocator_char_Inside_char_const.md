# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x140005934`
- end: `0x14000596d`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140005b44`

## callees

- `0x140005934`

## pseudocode

```c
bool __fastcall std::string::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8

  if ( !a2 )
    return 0;
  v2 = a1[3] < 0x10u ? a1 : (_QWORD *)*a1;
  if ( a2 < (unsigned __int64)v2 )
    return 0;
  if ( a1[3] < 0x10u )
    v3 = a1;
  else
    v3 = (_QWORD *)*a1;
  return (unsigned __int64)v3 + a1[2] > a2;
}

```

## disassembly

```asm
0x140005934  test    rdx, rdx
0x140005937  jz      short loc_14000596A
0x140005939  cmp     qword ptr [rcx+18h], 10h
0x14000593e  jb      short loc_140005945
0x140005940  mov     rax, [rcx]
0x140005943  jmp     short loc_140005948
0x140005945  mov     rax, rcx
0x140005948  cmp     rdx, rax
0x14000594b  jb      short loc_14000596A
0x14000594d  cmp     qword ptr [rcx+18h], 10h
0x140005952  jb      short loc_140005959
0x140005954  mov     r8, [rcx]
0x140005957  jmp     short loc_14000595C
0x140005959  mov     r8, rcx
0x14000595c  mov     rcx, [rcx+10h]
0x140005960  add     rcx, r8
0x140005963  cmp     rcx, rdx
0x140005966  setnbe  al
0x140005969  retn
0x14000596a  xor     al, al
0x14000596c  retn
```
