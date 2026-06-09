# GetUtf8EncodedCodeUnitCountForCodePoint

- ea: `0x180005ff0`
- end: `0x180006038`
- name: `GetUtf8EncodedCodeUnitCountForCodePoint`
- size: `72`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001830`
- `0x1800047b0`

## callees

- `0x180005ff0`

## pseudocode

```c
__int64 __fastcall GetUtf8EncodedCodeUnitCountForCodePoint(unsigned int a1, _BYTE *a2)
{
  if ( a1 < 0x80 )
  {
    *a2 = 1;
    return 0;
  }
  if ( a1 < 0x800 )
  {
    *a2 = 2;
    return 0;
  }
  if ( a1 >= 0x10000 )
  {
    if ( a1 <= 0x10FFFF )
    {
      *a2 = 4;
      return 0;
    }
  }
  else if ( a1 - 55296 > 0x7FF )
  {
    *a2 = 3;
    return 0;
  }
  return 582;
}

```

## disassembly

```asm
0x180005ff0  cmp     ecx, 80h
0x180005ff6  jnb     short loc_180005FFE
0x180005ff8  mov     byte ptr [rdx], 1
0x180005ffb  xor     eax, eax
0x180005ffd  retn
0x180005ffe  cmp     ecx, 800h
0x180006004  jnb     short loc_18000600B
0x180006006  mov     byte ptr [rdx], 2
0x180006009  jmp     short loc_180005FFB
0x18000600b  cmp     ecx, 10000h
0x180006011  jnb     short loc_180006025
0x180006013  lea     eax, [rcx-0D800h]
0x180006019  cmp     eax, 7FFh
0x18000601e  jbe     short loc_180006032
0x180006020  mov     byte ptr [rdx], 3
0x180006023  jmp     short loc_180005FFB
0x180006025  cmp     ecx, 10FFFFh
0x18000602b  ja      short loc_180006032
0x18000602d  mov     byte ptr [rdx], 4
0x180006030  jmp     short loc_180005FFB
0x180006032  mov     eax, 246h
0x180006037  retn
```
