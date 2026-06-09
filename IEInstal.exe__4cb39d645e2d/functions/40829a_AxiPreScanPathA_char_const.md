# AxiPreScanPathA(char const *)

- ea: `0x40829a`
- end: `0x4082fb`
- name: `?AxiPreScanPathA@@YGJPBD@Z`
- size: `97`
- prototype: `int __thiscall(_BYTE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x40707d`

## callees

- `0x408235`
- `0x40829a`

## import_xrefs

- `msvcrt!iscntrl` at `0x4082de`
- `msvcrt!iscntrl` at `0x4082de`

## pseudocode

```c
int __thiscall AxiPreScanPathA(_BYTE *this)
{
  int result; // eax
  int i; // esi
  char v4; // cl
  int v5; // eax

  result = 0;
  if ( this )
  {
    for ( i = 0; ; ++i )
    {
      v4 = this[i];
      result = 0;
      if ( !v4 )
        return result;
      if ( v4 == 34 || v4 == 42 || v4 == 60 || v4 == 62 || v4 == 63 || v4 == 124 )
      {
        v5 = FilenameDisallowCharacter();
      }
      else
      {
        if ( (unsigned int)v4 >= 0x80 )
          continue;
        v5 = _iscntrl(v4);
      }
      if ( v5 )
        return -2147024809;
    }
  }
  return result;
}

```

## disassembly

```asm
0x40829a  mov     edi, edi
0x40829c  push    edi
0x40829d  mov     edi, ecx
0x40829f  xor     eax, eax
0x4082a1  test    edi, edi
0x4082a3  jz      short loc_4082F9
0x4082a5  push    esi
0x4082a6  xor     esi, esi
0x4082a8  mov     cl, [edi+esi]
0x4082ab  xor     eax, eax
0x4082ad  test    cl, cl
0x4082af  jz      short loc_4082F8
0x4082b1  movsx   ecx, cl
0x4082b4  mov     eax, ecx
0x4082b6  sub     eax, 22h ; '"'
0x4082b9  jz      short loc_4082E7
0x4082bb  sub     eax, 8
0x4082be  jz      short loc_4082E7
0x4082c0  sub     eax, 12h
0x4082c3  jz      short loc_4082E7
0x4082c5  dec     eax
0x4082c6  sub     eax, 1
0x4082c9  jz      short loc_4082E7
0x4082cb  sub     eax, 1
0x4082ce  jz      short loc_4082E7
0x4082d0  sub     eax, 3Dh ; '='
0x4082d3  jz      short loc_4082E7
0x4082d5  cmp     ecx, 80h
0x4082db  jnb     short loc_4082F0
0x4082dd  push    ecx; C
0x4082de  call    ds:__imp__iscntrl
0x4082e4  pop     ecx
0x4082e5  jmp     short loc_4082EC
0x4082e7  call    FilenameDisallowCharacter
0x4082ec  test    eax, eax
0x4082ee  jnz     short loc_4082F3
0x4082f0  inc     esi
0x4082f1  jmp     short loc_4082A8
0x4082f3  mov     eax, 80070057h
0x4082f8  pop     esi
0x4082f9  pop     edi
0x4082fa  retn
```
