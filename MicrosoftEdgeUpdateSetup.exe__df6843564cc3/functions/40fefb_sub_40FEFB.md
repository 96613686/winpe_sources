# sub_40FEFB

- ea: `0x40fefb`
- end: `0x40ffd5`
- name: `sub_40FEFB`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40fefb`

## pseudocode

```c
int __usercall sub_40FEFB@<eax>(char a1@<al>)
{
  int v1; // ecx
  int v2; // edx
  int v4; // [esp+8h] [ebp-8h]

  __asm { fnclex }
  if ( dword_426964 < 1 )
    JUMPOUT(0xFC868A7E);
  v1 = 0;
  v2 = 0;
  if ( (a1 & 0x3F) != 0 )
  {
    v2 = 16 * (a1 & 1);
    if ( (a1 & 4) != 0 )
      v2 |= 8u;
    if ( (a1 & 8) != 0 )
      v2 |= 4u;
    if ( (a1 & 0x10) != 0 )
      v2 |= 2u;
    if ( (a1 & 0x20) != 0 )
      v2 |= 1u;
    if ( (a1 & 2) != 0 )
      v2 |= 0x80000u;
  }
  v4 = _mm_getcsr();
  _mm_setcsr(v4 & 0xFFFFFFC0);
  if ( (v4 & 0x3F) != 0 )
  {
    v1 = 16 * (v4 & 1);
    if ( (v4 & 4) != 0 )
      v1 |= 8u;
    if ( (v4 & 8) != 0 )
      v1 |= 4u;
    if ( (v4 & 0x10) != 0 )
      v1 |= 2u;
    if ( (v4 & 0x20) != 0 )
      v1 |= 1u;
    if ( (v4 & 2) != 0 )
      v1 |= 0x80000u;
  }
  return v2 | v1;
}

```

## disassembly

```asm
0x40fefb  mov     edi, edi
0x40fefd  push    ebp
0x40fefe  mov     ebp, esp
0x40ff00  sub     esp, 0Ch
0x40ff03  push    esi
0x40ff04  fnstsw  [ebp+var_4]
0x40ff07  fnclex
0x40ff09  xor     esi, esi
0x40ff0b  inc     esi
0x40ff0c  cmp     dword_426964, esi
0x40ff12  jl      near ptr 0FC868A7Eh
0x40ff18  xor     ecx, ecx
0x40ff1a  mov     edx, ecx
0x40ff1c  push    edi
0x40ff1d  mov     edi, 80000h
0x40ff22  test    al, 3Fh
0x40ff24  jz      short loc_40FF4F
0x40ff26  movzx   edx, ax
0x40ff29  and     edx, esi
0x40ff2b  shl     edx, 4
0x40ff2e  test    al, 4
0x40ff30  jz      short loc_40FF35
0x40ff32  or      edx, 8
0x40ff35  test    al, 8
0x40ff37  jz      short loc_40FF3C
0x40ff39  or      edx, 4
0x40ff3c  test    al, 10h
0x40ff3e  jz      short loc_40FF43
0x40ff40  or      edx, 2
0x40ff43  test    al, 20h
0x40ff45  jz      short loc_40FF49
0x40ff47  or      edx, esi
0x40ff49  test    al, 2
0x40ff4b  jz      short loc_40FF4F
0x40ff4d  or      edx, edi
0x40ff4f  stmxcsr [ebp+var_8]
0x40ff53  mov     eax, [ebp+var_8]
0x40ff56  and     eax, 0FFFFFFC0h
0x40ff59  mov     [ebp+var_C], eax
0x40ff5c  ldmxcsr [ebp+var_C]
0x40ff60  mov     eax, [ebp+var_8]
0x40ff63  test    al, 3Fh
0x40ff65  jz      short loc_40FF8F
0x40ff67  mov     ecx, eax
0x40ff69  and     ecx, esi
0x40ff6b  shl     ecx, 4
0x40ff6e  test    al, 4
0x40ff70  jz      short loc_40FF75
0x40ff72  or      ecx, 8
0x40ff75  test    al, 8
0x40ff77  jz      short loc_40FF7C
0x40ff79  or      ecx, 4
0x40ff7c  test    al, 10h
0x40ff7e  jz      short loc_40FF83
0x40ff80  or      ecx, 2
0x40ff83  test    al, 20h
0x40ff85  jz      short loc_40FF89
0x40ff87  or      ecx, esi
0x40ff89  test    al, 2
0x40ff8b  jz      short loc_40FF8F
0x40ff8d  or      ecx, edi
0x40ff8f  or      ecx, edx
0x40ff91  mov     eax, ecx
0x40ff93  pop     edi
0x40ff94  jmp     short loc_40FFD2
0x40ff96  mov     cx, [ebp+var_4]
0x40ff9a  xor     eax, eax
0x40ff9c  test    cl, 3Fh
0x40ff9f  jz      short loc_40FFD2
0x40ffa1  movzx   eax, cx
0x40ffa4  and     eax, esi
0x40ffa6  shl     eax, 4
0x40ffa9  test    cl, 4
0x40ffac  jz      short loc_40FFB1
0x40ffae  or      eax, 8
0x40ffb1  test    cl, 8
0x40ffb4  jz      short loc_40FFB9
0x40ffb6  or      eax, 4
0x40ffb9  test    cl, 10h
0x40ffbc  jz      short loc_40FFC1
0x40ffbe  or      eax, 2
0x40ffc1  test    cl, 20h
0x40ffc4  jz      short loc_40FFC8
0x40ffc6  or      eax, esi
0x40ffc8  test    cl, 2
0x40ffcb  jz      short loc_40FFD2
0x40ffcd  or      eax, 80000h
0x40ffd2  pop     esi
0x40ffd3  leave
0x40ffd4  retn
```
