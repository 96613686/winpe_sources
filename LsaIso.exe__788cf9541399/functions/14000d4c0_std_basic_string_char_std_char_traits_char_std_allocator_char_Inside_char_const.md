# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x14000d4c0`
- end: `0x14000d4f9`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000d6c4`

## callees

- `0x14000d4c0`

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
0x14000d4c0  test    rdx, rdx
0x14000d4c3  jz      short loc_14000D4F6
0x14000d4c5  cmp     qword ptr [rcx+18h], 10h
0x14000d4ca  jb      short loc_14000D4D1
0x14000d4cc  mov     rax, [rcx]
0x14000d4cf  jmp     short loc_14000D4D4
0x14000d4d1  mov     rax, rcx
0x14000d4d4  cmp     rdx, rax
0x14000d4d7  jb      short loc_14000D4F6
0x14000d4d9  cmp     qword ptr [rcx+18h], 10h
0x14000d4de  jb      short loc_14000D4E5
0x14000d4e0  mov     r8, [rcx]
0x14000d4e3  jmp     short loc_14000D4E8
0x14000d4e5  mov     r8, rcx
0x14000d4e8  mov     rcx, [rcx+10h]
0x14000d4ec  add     rcx, r8
0x14000d4ef  cmp     rcx, rdx
0x14000d4f2  setnbe  al
0x14000d4f5  retn
0x14000d4f6  xor     al, al
0x14000d4f8  retn
```
