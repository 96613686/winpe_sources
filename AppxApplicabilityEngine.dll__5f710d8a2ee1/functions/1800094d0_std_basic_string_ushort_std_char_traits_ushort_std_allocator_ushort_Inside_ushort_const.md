# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x1800094d0`
- end: `0x180009516`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180009288`
- `0x180009350`

## callees

- `0x1800094d0`

## pseudocode

```c
bool __fastcall std::wstring::_Inside(_QWORD *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rax
  _QWORD *v3; // r8
  unsigned __int64 v4; // rcx

  if ( !a2 )
    return 0;
  v2 = a1[3];
  v3 = v2 >= 8 ? (_QWORD *)*a1 : a1;
  if ( a2 < (unsigned __int64)v3 )
    return 0;
  if ( v2 >= 8 )
    v4 = *a1 + 2LL * a1[2];
  else
    v4 = (unsigned __int64)a1 + 2 * a1[2];
  return v4 > a2;
}

```

## disassembly

```asm
0x1800094d0  test    rdx, rdx
0x1800094d3  jz      short loc_180009513
0x1800094d5  mov     rax, [rcx+18h]
0x1800094d9  cmp     rax, 8
0x1800094dd  jnb     short loc_1800094FC
0x1800094df  mov     r8, rcx
0x1800094e2  cmp     rdx, r8
0x1800094e5  jb      short loc_180009513
0x1800094e7  cmp     rax, 8
0x1800094eb  jnb     short loc_180009501
0x1800094ed  mov     rax, [rcx+10h]
0x1800094f1  lea     rcx, [rcx+rax*2]
0x1800094f5  cmp     rcx, rdx
0x1800094f8  setnbe  al
0x1800094fb  retn
0x1800094fc  mov     r8, [rcx]
0x1800094ff  jmp     short loc_1800094E2
0x180009501  mov     rax, [rcx+10h]
0x180009505  mov     r8, [rcx]
0x180009508  lea     rcx, [r8+rax*2]
0x18000950c  cmp     rcx, rdx
0x18000950f  setnbe  al
0x180009512  retn
0x180009513  xor     al, al
0x180009515  retn
```
