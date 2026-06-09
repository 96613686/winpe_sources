# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x140007104`
- end: `0x14000713d`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400073dc`
- `0x14000773c`

## callees

- `0x140007104`

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
0x140007104  test    rdx, rdx
0x140007107  jz      short loc_14000713A
0x140007109  cmp     qword ptr [rcx+18h], 10h
0x14000710e  jb      short loc_140007115
0x140007110  mov     rax, [rcx]
0x140007113  jmp     short loc_140007118
0x140007115  mov     rax, rcx
0x140007118  cmp     rdx, rax
0x14000711b  jb      short loc_14000713A
0x14000711d  cmp     qword ptr [rcx+18h], 10h
0x140007122  jb      short loc_140007129
0x140007124  mov     r8, [rcx]
0x140007127  jmp     short loc_14000712C
0x140007129  mov     r8, rcx
0x14000712c  mov     rcx, [rcx+10h]
0x140007130  add     rcx, r8
0x140007133  cmp     rcx, rdx
0x140007136  setnbe  al
0x140007139  retn
0x14000713a  xor     al, al
0x14000713c  retn
```
