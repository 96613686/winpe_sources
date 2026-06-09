# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x18000b478`
- end: `0x18000b4b1`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000b658`

## callees

- `0x18000b478`

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
0x18000b478  test    rdx, rdx
0x18000b47b  jz      short loc_18000B4AE
0x18000b47d  cmp     qword ptr [rcx+18h], 10h
0x18000b482  jb      short loc_18000B489
0x18000b484  mov     rax, [rcx]
0x18000b487  jmp     short loc_18000B48C
0x18000b489  mov     rax, rcx
0x18000b48c  cmp     rdx, rax
0x18000b48f  jb      short loc_18000B4AE
0x18000b491  cmp     qword ptr [rcx+18h], 10h
0x18000b496  jb      short loc_18000B49D
0x18000b498  mov     r8, [rcx]
0x18000b49b  jmp     short loc_18000B4A0
0x18000b49d  mov     r8, rcx
0x18000b4a0  mov     rcx, [rcx+10h]
0x18000b4a4  add     rcx, r8
0x18000b4a7  cmp     rcx, rdx
0x18000b4aa  setnbe  al
0x18000b4ad  retn
0x18000b4ae  xor     al, al
0x18000b4b0  retn
```
