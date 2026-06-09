# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Inside(char const *)

- ea: `0x18000c8f0`
- end: `0x18000c929`
- name: `?_Inside@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA_NPEBD@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000d0dc`

## callees

- `0x18000c8f0`

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
0x18000c8f0  test    rdx, rdx
0x18000c8f3  jz      short loc_18000C926
0x18000c8f5  cmp     qword ptr [rcx+18h], 10h
0x18000c8fa  jb      short loc_18000C901
0x18000c8fc  mov     rax, [rcx]
0x18000c8ff  jmp     short loc_18000C904
0x18000c901  mov     rax, rcx
0x18000c904  cmp     rdx, rax
0x18000c907  jb      short loc_18000C926
0x18000c909  cmp     qword ptr [rcx+18h], 10h
0x18000c90e  jb      short loc_18000C915
0x18000c910  mov     r8, [rcx]
0x18000c913  jmp     short loc_18000C918
0x18000c915  mov     r8, rcx
0x18000c918  mov     rcx, [rcx+10h]
0x18000c91c  add     rcx, r8
0x18000c91f  cmp     rcx, rdx
0x18000c922  setnbe  al
0x18000c925  retn
0x18000c926  xor     al, al
0x18000c928  retn
```
