# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Inside(char const *)

- ea: `0x14000f894`
- end: `0x14000f8c7`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAA_NPEBD@Z`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000fb30`

## callees

- `0x14000f894`

## pseudocode

```c
bool __fastcall std::string::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *v3; // rax

  v2 = a1 + 1;
  if ( a1[4] < 0x10u )
    v3 = a1 + 1;
  else
    v3 = (_QWORD *)*v2;
  if ( a2 < (unsigned __int64)v3 )
    return 0;
  if ( a1[4] >= 0x10u )
    v2 = (_QWORD *)*v2;
  return (unsigned __int64)v2 + a1[3] > a2;
}

```

## disassembly

```asm
0x14000f894  cmp     qword ptr [rcx+20h], 10h
0x14000f899  lea     r8, [rcx+8]
0x14000f89d  jb      short loc_14000F8A4
0x14000f89f  mov     rax, [r8]
0x14000f8a2  jmp     short loc_14000F8A7
0x14000f8a4  mov     rax, r8
0x14000f8a7  cmp     rdx, rax
0x14000f8aa  jb      short loc_14000F8C4
0x14000f8ac  cmp     qword ptr [rcx+20h], 10h
0x14000f8b1  jb      short loc_14000F8B6
0x14000f8b3  mov     r8, [r8]
0x14000f8b6  mov     rcx, [rcx+18h]
0x14000f8ba  add     rcx, r8
0x14000f8bd  cmp     rcx, rdx
0x14000f8c0  setnbe  al
0x14000f8c3  retn
0x14000f8c4  xor     al, al
0x14000f8c6  retn
```
