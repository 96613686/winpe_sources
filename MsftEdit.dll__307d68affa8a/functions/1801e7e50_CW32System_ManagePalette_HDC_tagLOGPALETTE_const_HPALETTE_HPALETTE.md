# CW32System::ManagePalette(HDC__ *,tagLOGPALETTE const *,HPALETTE__ * &,HPALETTE__ * &)

- ea: `0x1801e7e50`
- end: `0x1801e7ecc`
- name: `?ManagePalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEBUtagLOGPALETTE@@AEAPEAU2@2@Z`
- size: `124`
- prototype: `HPALETTE __fastcall(HDC, LOGPALETTE *plpal, HPALETTE *, HPALETTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800afff0`

## callees

- `0x1801e7e50`
- `0x1801e7ed4`
- `0x1801e7ee8`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!CreatePalette` at `0x1801e7e71`
- `ext-ms-win-gdi-dc-l1-2-0!CreatePalette` at `0x1801e7e71`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e7ead`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e7ead`

## pseudocode

```c
HPALETTE __fastcall CW32System::ManagePalette(HDC a1, LOGPALETTE *plpal, HPALETTE *a3, HPALETTE *a4)
{
  HPALETTE Palette; // rax
  int v8; // r8d

  if ( *a4 )
  {
    CW32System::SelectPalette(a1, *a3, (int)a3);
    CW32System::RealizePalette(a1);
    DeleteObject(*a4);
    *a4 = 0;
  }
  else
  {
    Palette = CreatePalette(plpal);
    *a4 = Palette;
    if ( Palette )
    {
      *a3 = CW32System::SelectPalette(a1, Palette, v8);
      CW32System::RealizePalette(a1);
      return *a4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801e7e50  mov     [rsp+arg_0], rbx
0x1801e7e55  mov     [rsp+arg_8], rsi
0x1801e7e5a  push    rdi
0x1801e7e5b  sub     rsp, 20h
0x1801e7e5f  cmp     qword ptr [r9], 0
0x1801e7e63  mov     rbx, r9
0x1801e7e66  mov     rsi, r8
0x1801e7e69  mov     rdi, rcx
0x1801e7e6c  jnz     short loc_1801E7E9A
0x1801e7e6e  mov     rcx, rdx; plpal
0x1801e7e71  call    cs:__imp_CreatePalette
0x1801e7e77  mov     [rbx], rax
0x1801e7e7a  test    rax, rax
0x1801e7e7d  jz      short loc_1801E7EBA
0x1801e7e7f  mov     rdx, rax; HPALETTE
0x1801e7e82  mov     rcx, rdi; HDC
0x1801e7e85  call    ?SelectPalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAU2@H@Z; CW32System::SelectPalette(HDC__ *,HPALETTE__ *,int)
0x1801e7e8a  mov     rcx, rdi; HDC
0x1801e7e8d  mov     [rsi], rax
0x1801e7e90  call    ?RealizePalette@CW32System@@SAIPEAUHDC__@@@Z; CW32System::RealizePalette(HDC__ *)
0x1801e7e95  mov     rax, [rbx]
0x1801e7e98  jmp     short loc_1801E7EBC
0x1801e7e9a  mov     rdx, [r8]; HPALETTE
0x1801e7e9d  call    ?SelectPalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAU2@H@Z; CW32System::SelectPalette(HDC__ *,HPALETTE__ *,int)
0x1801e7ea2  mov     rcx, rdi; HDC
0x1801e7ea5  call    ?RealizePalette@CW32System@@SAIPEAUHDC__@@@Z; CW32System::RealizePalette(HDC__ *)
0x1801e7eaa  mov     rcx, [rbx]; ho
0x1801e7ead  call    cs:__imp_DeleteObject
0x1801e7eb3  mov     qword ptr [rbx], 0
0x1801e7eba  xor     eax, eax
0x1801e7ebc  mov     rbx, [rsp+28h+arg_0]
0x1801e7ec1  mov     rsi, [rsp+28h+arg_8]
0x1801e7ec6  add     rsp, 20h
0x1801e7eca  pop     rdi
0x1801e7ecb  retn
```
