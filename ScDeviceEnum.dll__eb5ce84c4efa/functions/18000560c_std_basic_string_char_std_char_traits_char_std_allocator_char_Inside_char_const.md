# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x18000560c`
- end: `0x180005645`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800057ec`

## callees

- `0x18000560c`

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
0x18000560c  test    rdx, rdx
0x18000560f  jz      short loc_180005642
0x180005611  cmp     qword ptr [rcx+18h], 10h
0x180005616  jb      short loc_18000561D
0x180005618  mov     rax, [rcx]
0x18000561b  jmp     short loc_180005620
0x18000561d  mov     rax, rcx
0x180005620  cmp     rdx, rax
0x180005623  jb      short loc_180005642
0x180005625  cmp     qword ptr [rcx+18h], 10h
0x18000562a  jb      short loc_180005631
0x18000562c  mov     r8, [rcx]
0x18000562f  jmp     short loc_180005634
0x180005631  mov     r8, rcx
0x180005634  mov     rcx, [rcx+10h]
0x180005638  add     rcx, r8
0x18000563b  cmp     rcx, rdx
0x18000563e  setnbe  al
0x180005641  retn
0x180005642  xor     al, al
0x180005644  retn
```
