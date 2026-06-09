# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x140007500`
- end: `0x14000753a`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400077f0`
- `0x140007b54`

## callees

- `0x140007500`

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
0x140007500  test    rdx, rdx
0x140007503  jz      short loc_140007537
0x140007505  cmp     qword ptr [rcx+18h], 10h
0x14000750a  jb      short loc_140007511
0x14000750c  mov     rax, [rcx]
0x14000750f  jmp     short loc_140007514
0x140007511  mov     rax, rcx
0x140007514  cmp     rdx, rax
0x140007517  jb      short loc_140007537
0x140007519  cmp     qword ptr [rcx+18h], 10h
0x14000751e  jb      short loc_140007525
0x140007520  mov     r8, [rcx]
0x140007523  jmp     short loc_140007528
0x140007525  mov     r8, rcx
0x140007528  mov     rcx, [rcx+10h]
0x14000752c  add     rcx, r8
0x14000752f  cmp     rcx, rdx
0x140007532  setnbe  al
0x140007535  retn
0x140007537  xor     al, al
0x140007539  retn
```
