# InitThemeData(HWND__ *)

- ea: `0x18010e6b0`
- end: `0x18010e70a`
- name: `?InitThemeData@@YAXPEAUHWND__@@@Z`
- size: `90`
- prototype: `void __fastcall(HWND hwnd)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18011f920`
- `0x1801f8e40`

## callees

- `0x18010e6b0`
- `0x18012ac78`

## import_xrefs

- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010e6d6`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010e6f7`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010e6d6`
- `ext-ms-win-uxtheme-themes-l1-1-0!OpenThemeData` at `0x18010e6f7`

## string_xrefs

- `0x18010e6cc`: `ComboBox`

## pseudocode

```c
void __fastcall InitThemeData(HWND hwnd)
{
  if ( (unsigned int)FIsThemeActive() )
  {
    if ( !vhThemeComboBox )
      vhThemeComboBox = OpenThemeData(hwnd, L"ComboBox");
    if ( !vhThemeEdit )
      vhThemeEdit = OpenThemeData(hwnd, L"Edit");
  }
}

```

## disassembly

```asm
0x18010e6b0  push    rbx
0x18010e6b2  sub     rsp, 20h
0x18010e6b6  mov     rbx, rcx
0x18010e6b9  call    ?FIsThemeActive@@YAHXZ; FIsThemeActive(void)
0x18010e6be  test    eax, eax
0x18010e6c0  jz      short loc_18010E704
0x18010e6c2  cmp     cs:?vhThemeComboBox@@3PEAXEA, 0; void * vhThemeComboBox
0x18010e6ca  jnz     short loc_18010E6E3
0x18010e6cc  lea     rdx, pszClassList; "ComboBox"
0x18010e6d3  mov     rcx, rbx; hwnd
0x18010e6d6  call    cs:__imp_OpenThemeData
0x18010e6dc  mov     cs:?vhThemeComboBox@@3PEAXEA, rax; void * vhThemeComboBox
0x18010e6e3  cmp     cs:?vhThemeEdit@@3PEAXEA, 0; void * vhThemeEdit
0x18010e6eb  jnz     short loc_18010E704
0x18010e6ed  lea     rdx, aEdit; "Edit"
0x18010e6f4  mov     rcx, rbx; hwnd
0x18010e6f7  call    cs:__imp_OpenThemeData
0x18010e6fd  mov     cs:?vhThemeEdit@@3PEAXEA, rax; void * vhThemeEdit
0x18010e704  add     rsp, 20h
0x18010e708  pop     rbx
0x18010e709  retn
```
