# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Inside(ushort const *)

- ea: `0x140008328`
- end: `0x140008362`
- name: `?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z`
- size: `58`
- prototype: `bool __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400084c0`
- `0x14000b5c4`

## callees

- `0x140008328`

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
0x140008328  test    rdx, rdx
0x14000832b  jz      short loc_14000835F
0x14000832d  cmp     qword ptr [rcx+18h], 8
0x140008332  jb      short loc_140008339
0x140008334  mov     rax, [rcx]
0x140008337  jmp     short loc_14000833C
0x140008339  mov     rax, rcx
0x14000833c  cmp     rdx, rax
0x14000833f  jb      short loc_14000835F
0x140008341  cmp     qword ptr [rcx+18h], 8
0x140008346  jb      short loc_14000834D
0x140008348  mov     r8, [rcx]
0x14000834b  jmp     short loc_140008350
0x14000834d  mov     r8, rcx
0x140008350  mov     rax, [rcx+10h]
0x140008354  lea     rcx, [r8+rax*2]
0x140008358  cmp     rcx, rdx
0x14000835b  setnbe  al
0x14000835e  retn
0x14000835f  xor     al, al
0x140008361  retn
```
