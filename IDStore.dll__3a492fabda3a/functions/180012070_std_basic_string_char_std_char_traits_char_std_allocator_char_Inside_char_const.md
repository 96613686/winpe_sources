# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x180012070`
- end: `0x1800120a9`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800121fc`

## callees

- `0x180012070`

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
0x180012070  test    rdx, rdx
0x180012073  jz      short loc_1800120A6
0x180012075  cmp     qword ptr [rcx+18h], 10h
0x18001207a  jb      short loc_180012081
0x18001207c  mov     rax, [rcx]
0x18001207f  jmp     short loc_180012084
0x180012081  mov     rax, rcx
0x180012084  cmp     rdx, rax
0x180012087  jb      short loc_1800120A6
0x180012089  cmp     qword ptr [rcx+18h], 10h
0x18001208e  jb      short loc_180012095
0x180012090  mov     r8, [rcx]
0x180012093  jmp     short loc_180012098
0x180012095  mov     r8, rcx
0x180012098  mov     rcx, [rcx+10h]
0x18001209c  add     rcx, r8
0x18001209f  cmp     rcx, rdx
0x1800120a2  setnbe  al
0x1800120a5  retn
0x1800120a6  xor     al, al
0x1800120a8  retn
```
