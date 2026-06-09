# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x140007144`
- end: `0x14000717e`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `58`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000758c`
- `0x1400078b0`

## callees

- `0x140007144`

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
0x140007144  test    rdx, rdx
0x140007147  jz      short loc_14000717B
0x140007149  cmp     qword ptr [rcx+18h], 8
0x14000714e  jb      short loc_140007155
0x140007150  mov     rax, [rcx]
0x140007153  jmp     short loc_140007158
0x140007155  mov     rax, rcx
0x140007158  cmp     rdx, rax
0x14000715b  jb      short loc_14000717B
0x14000715d  cmp     qword ptr [rcx+18h], 8
0x140007162  jb      short loc_140007169
0x140007164  mov     r8, [rcx]
0x140007167  jmp     short loc_14000716C
0x140007169  mov     r8, rcx
0x14000716c  mov     rax, [rcx+10h]
0x140007170  lea     rcx, [r8+rax*2]
0x140007174  cmp     rcx, rdx
0x140007177  setnbe  al
0x14000717a  retn
0x14000717b  xor     al, al
0x14000717d  retn
```
