# CHString::Compare(ushort const *)

- ea: `0x1400108b0`
- end: `0x1400108d1`
- name: `?Compare@CHString@@QEBAHPEBG@Z`
- size: `33`
- prototype: `__int64 __fastcall(unsigned __int16 **this, char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400108b0`

## pseudocode

```c
__int64 __fastcall CHString::Compare(unsigned __int16 **this, char *a2)
{
  unsigned __int16 *v2; // rax
  char *v3; // rdx
  unsigned __int16 v4; // cx

  v2 = *this;
  v3 = (char *)(a2 - (char *)*this);
  while ( 1 )
  {
    v4 = *v2;
    if ( *v2 != *(_WORD *)&v3[(_QWORD)v2] )
      break;
    ++v2;
    if ( !v4 )
      return 0;
  }
  return v4 < *(_WORD *)&v3[(_QWORD)v2] ? -1 : 1;
}

```

## disassembly

```asm
0x1400108b0  mov     rax, [rcx]
0x1400108b3  sub     rdx, rax
0x1400108b6  movzx   ecx, word ptr [rax]
0x1400108b9  cmp     cx, [rax+rdx]
0x1400108bd  jnz     short loc_1400108CB
0x1400108bf  add     rax, 2
0x1400108c3  test    cx, cx
0x1400108c6  jnz     short loc_1400108B6
0x1400108c8  xor     eax, eax
0x1400108ca  retn
0x1400108cb  sbb     eax, eax
0x1400108cd  or      eax, 1
0x1400108d0  retn
```
