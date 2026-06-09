# ReplaceChars

- ea: `0x180010270`
- end: `0x1800102b7`
- name: `ReplaceChars`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089d0`

## callees

- `0x180010270`

## import_xrefs

- `KERNEL32!IsDBCSLeadByte` at `0x18001028a`
- `KERNEL32!IsDBCSLeadByte` at `0x18001028a`

## pseudocode

```c
__int64 __fastcall ReplaceChars(BYTE *a1, char a2, BYTE a3)
{
  BYTE v3; // al
  BYTE *v6; // rbx
  unsigned int v7; // edi

  v3 = *a1;
  v6 = a1;
  v7 = 0;
  while ( v3 )
  {
    if ( IsDBCSLeadByte(v3) )
    {
      ++v6;
    }
    else if ( *v6 == a2 )
    {
      *v6 = a3;
      ++v7;
    }
    v3 = *++v6;
  }
  return v7;
}

```

## disassembly

```asm
0x180010270  push    rbx
0x180010272  push    rbp
0x180010273  push    rsi
0x180010274  push    rdi
0x180010275  sub     rsp, 28h
0x180010279  mov     al, [rcx]
0x18001027b  mov     sil, r8b
0x18001027e  mov     bpl, dl
0x180010281  mov     rbx, rcx
0x180010284  xor     edi, edi
0x180010286  jmp     short loc_1800102A8
0x180010288  mov     cl, al; TestChar
0x18001028a  call    cs:__imp_IsDBCSLeadByte
0x180010290  test    eax, eax
0x180010292  jz      short loc_180010299
0x180010294  inc     rbx
0x180010297  jmp     short loc_1800102A3
0x180010299  cmp     [rbx], bpl
0x18001029c  jnz     short loc_1800102A3
0x18001029e  mov     [rbx], sil
0x1800102a1  inc     edi
0x1800102a3  inc     rbx
0x1800102a6  mov     al, [rbx]
0x1800102a8  test    al, al
0x1800102aa  jnz     short loc_180010288
0x1800102ac  mov     eax, edi
0x1800102ae  add     rsp, 28h
0x1800102b2  pop     rdi
0x1800102b3  pop     rsi
0x1800102b4  pop     rbp
0x1800102b5  pop     rbx
0x1800102b6  retn
```
