# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Inside(wchar_t const *)

- ea: `0x18000eb38`
- end: `0x18000eb72`
- name: `?_Inside@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA_NPEB_W@Z`
- size: `58`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180007528`
- `0x180007eb0`

## callees

- `0x18000eb38`

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
0x18000eb38  test    rdx, rdx
0x18000eb3b  jz      short loc_18000EB6F
0x18000eb3d  cmp     qword ptr [rcx+18h], 8
0x18000eb42  jb      short loc_18000EB49
0x18000eb44  mov     rax, [rcx]
0x18000eb47  jmp     short loc_18000EB4C
0x18000eb49  mov     rax, rcx
0x18000eb4c  cmp     rdx, rax
0x18000eb4f  jb      short loc_18000EB6F
0x18000eb51  cmp     qword ptr [rcx+18h], 8
0x18000eb56  jb      short loc_18000EB5D
0x18000eb58  mov     r8, [rcx]
0x18000eb5b  jmp     short loc_18000EB60
0x18000eb5d  mov     r8, rcx
0x18000eb60  mov     rax, [rcx+10h]
0x18000eb64  lea     rcx, [r8+rax*2]
0x18000eb68  cmp     rcx, rdx
0x18000eb6b  setnbe  al
0x18000eb6e  retn
0x18000eb6f  xor     al, al
0x18000eb71  retn
```
