# ReleaseOutlineBitmaps(void)

- ea: `0x180107514`
- end: `0x180107570`
- name: `?ReleaseOutlineBitmaps@@YAXXZ`
- size: `92`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800d9f8c`

## callees

- `0x180107514`

## import_xrefs

- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010754d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180107555`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010755d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010754d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180107555`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010755d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180107569`

## pseudocode

```c
void ReleaseOutlineBitmaps(void)
{
  if ( h )
    DeleteObject(h);
  if ( qword_1802DF578 )
    DeleteObject(qword_1802DF578);
  if ( qword_1802DF570 )
    DeleteObject(qword_1802DF570);
  if ( qword_1802DF568 )
    DeleteObject((HGDIOBJ)qword_1802DF568);
}

```

## disassembly

```asm
0x180107514  sub     rsp, 28h
0x180107518  mov     rcx, cs:h; ho
0x18010751f  test    rcx, rcx
0x180107522  jnz     short loc_18010754D
0x180107524  mov     rcx, cs:qword_1802DF578; ho
0x18010752b  test    rcx, rcx
0x18010752e  jnz     short loc_180107555
0x180107530  mov     rcx, cs:qword_1802DF570; ho
0x180107537  test    rcx, rcx
0x18010753a  jnz     short loc_18010755D
0x18010753c  mov     rcx, cs:qword_1802DF568
0x180107543  test    rcx, rcx
0x180107546  jnz     short loc_180107565
0x180107548  add     rsp, 28h
0x18010754c  retn
0x18010754d  call    cs:__imp_DeleteObject
0x180107553  jmp     short loc_180107524
0x180107555  call    cs:__imp_DeleteObject
0x18010755b  jmp     short loc_180107530
0x18010755d  call    cs:__imp_DeleteObject
0x180107563  jmp     short loc_18010753C
0x180107565  add     rsp, 28h
0x180107569  jmp     cs:__imp_DeleteObject
```
