# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x14000baf4`
- end: `0x14000bb2d`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000bd30`

## callees

- `0x14000baf4`

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
0x14000baf4  test    rdx, rdx
0x14000baf7  jz      short loc_14000BB2A
0x14000baf9  cmp     qword ptr [rcx+18h], 10h
0x14000bafe  jb      short loc_14000BB05
0x14000bb00  mov     rax, [rcx]
0x14000bb03  jmp     short loc_14000BB08
0x14000bb05  mov     rax, rcx
0x14000bb08  cmp     rdx, rax
0x14000bb0b  jb      short loc_14000BB2A
0x14000bb0d  cmp     qword ptr [rcx+18h], 10h
0x14000bb12  jb      short loc_14000BB19
0x14000bb14  mov     r8, [rcx]
0x14000bb17  jmp     short loc_14000BB1C
0x14000bb19  mov     r8, rcx
0x14000bb1c  mov     rcx, [rcx+10h]
0x14000bb20  add     rcx, r8
0x14000bb23  cmp     rcx, rdx
0x14000bb26  setnbe  al
0x14000bb29  retn
0x14000bb2a  xor     al, al
0x14000bb2c  retn
```
