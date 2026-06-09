# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x180005bb4`
- end: `0x180005bef`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180005e18`
- `0x1800061f0`

## callees

- `0x180005bb4`

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
0x180005bb4  test    rdx, rdx
0x180005bb7  jz      short loc_180005BEC
0x180005bb9  cmp     qword ptr [rcx+18h], 8
0x180005bbe  jb      short loc_180005BC5
0x180005bc0  mov     rax, [rcx]
0x180005bc3  jmp     short loc_180005BC8
0x180005bc5  mov     rax, rcx
0x180005bc8  cmp     rdx, rax
0x180005bcb  jb      short loc_180005BEC
0x180005bcd  cmp     qword ptr [rcx+18h], 8
0x180005bd2  jb      short loc_180005BD9
0x180005bd4  mov     r8, [rcx]
0x180005bd7  jmp     short loc_180005BDC
0x180005bd9  mov     r8, rcx
0x180005bdc  mov     rax, [rcx+10h]
0x180005be0  lea     rcx, [r8+rax*2]
0x180005be4  cmp     rcx, rdx
0x180005be7  setnbe  al
0x180005bea  retn
0x180005bec  xor     al, al
0x180005bee  retn
```
