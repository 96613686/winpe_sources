# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x180012340`
- end: `0x180012379`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180012544`

## callees

- `0x180012340`

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
0x180012340  test    rdx, rdx
0x180012343  jz      short loc_180012376
0x180012345  cmp     qword ptr [rcx+18h], 10h
0x18001234a  jb      short loc_180012351
0x18001234c  mov     rax, [rcx]
0x18001234f  jmp     short loc_180012354
0x180012351  mov     rax, rcx
0x180012354  cmp     rdx, rax
0x180012357  jb      short loc_180012376
0x180012359  cmp     qword ptr [rcx+18h], 10h
0x18001235e  jb      short loc_180012365
0x180012360  mov     r8, [rcx]
0x180012363  jmp     short loc_180012368
0x180012365  mov     r8, rcx
0x180012368  mov     rcx, [rcx+10h]
0x18001236c  add     rcx, r8
0x18001236f  cmp     rcx, rdx
0x180012372  setnbe  al
0x180012375  retn
0x180012376  xor     al, al
0x180012378  retn
```
