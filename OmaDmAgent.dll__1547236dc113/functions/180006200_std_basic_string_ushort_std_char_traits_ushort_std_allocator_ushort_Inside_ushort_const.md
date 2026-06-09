# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x180006200`
- end: `0x18000623b`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180006620`
- `0x180009e48`

## callees

- `0x180006200`

## pseudocode

```c
bool __fastcall std::wstring::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v2; // rax
  _QWORD *v3; // r8

  if ( !a2 )
    return 0;
  v2 = a1[3] < 8u ? a1 : (_QWORD *)*a1;
  if ( a2 < (unsigned __int64)v2 )
    return 0;
  if ( a1[3] < 8u )
    v3 = a1;
  else
    v3 = (_QWORD *)*a1;
  return (unsigned __int64)v3 + 2 * a1[2] > a2;
}

```

## disassembly

```asm
0x180006200  test    rdx, rdx
0x180006203  jz      short loc_180006238
0x180006205  cmp     qword ptr [rcx+18h], 8
0x18000620a  jb      short loc_180006211
0x18000620c  mov     rax, [rcx]
0x18000620f  jmp     short loc_180006214
0x180006211  mov     rax, rcx
0x180006214  cmp     rdx, rax
0x180006217  jb      short loc_180006238
0x180006219  cmp     qword ptr [rcx+18h], 8
0x18000621e  jb      short loc_180006225
0x180006220  mov     r8, [rcx]
0x180006223  jmp     short loc_180006228
0x180006225  mov     r8, rcx
0x180006228  mov     rax, [rcx+10h]
0x18000622c  lea     rcx, [r8+rax*2]
0x180006230  cmp     rcx, rdx
0x180006233  setnbe  al
0x180006236  retn
0x180006238  xor     al, al
0x18000623a  retn
```
