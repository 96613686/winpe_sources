# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x180009800`
- end: `0x18000983a`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `58`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180009970`

## callees

- `0x180009800`

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
0x180009800  test    rdx, rdx
0x180009803  jz      short loc_180009837
0x180009805  cmp     qword ptr [rcx+18h], 8
0x18000980a  jb      short loc_180009811
0x18000980c  mov     rax, [rcx]
0x18000980f  jmp     short loc_180009814
0x180009811  mov     rax, rcx
0x180009814  cmp     rdx, rax
0x180009817  jb      short loc_180009837
0x180009819  cmp     qword ptr [rcx+18h], 8
0x18000981e  jb      short loc_180009825
0x180009820  mov     r8, [rcx]
0x180009823  jmp     short loc_180009828
0x180009825  mov     r8, rcx
0x180009828  mov     rax, [rcx+10h]
0x18000982c  lea     rcx, [r8+rax*2]
0x180009830  cmp     rcx, rdx
0x180009833  setnbe  al
0x180009836  retn
0x180009837  xor     al, al
0x180009839  retn
```
