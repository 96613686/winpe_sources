# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x140006440`
- end: `0x14000647a`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `58`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140006604`
- `0x140011d80`

## callees

- `0x140006440`

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
0x140006440  test    rdx, rdx
0x140006443  jz      short loc_140006477
0x140006445  cmp     qword ptr [rcx+18h], 8
0x14000644a  jb      short loc_140006451
0x14000644c  mov     rax, [rcx]
0x14000644f  jmp     short loc_140006454
0x140006451  mov     rax, rcx
0x140006454  cmp     rdx, rax
0x140006457  jb      short loc_140006477
0x140006459  cmp     qword ptr [rcx+18h], 8
0x14000645e  jb      short loc_140006465
0x140006460  mov     r8, [rcx]
0x140006463  jmp     short loc_140006468
0x140006465  mov     r8, rcx
0x140006468  mov     rax, [rcx+10h]
0x14000646c  lea     rcx, [r8+rax*2]
0x140006470  cmp     rcx, rdx
0x140006473  setnbe  al
0x140006476  retn
0x140006477  xor     al, al
0x140006479  retn
```
