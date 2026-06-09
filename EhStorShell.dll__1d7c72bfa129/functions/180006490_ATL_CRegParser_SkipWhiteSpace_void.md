# ATL::CRegParser::SkipWhiteSpace(void)

- ea: `0x180006490`
- end: `0x1800064c4`
- name: `?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ`
- size: `52`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006330`
- `0x18000662c`
- `0x180007f20`
- `0x180008e9c`

## callees

- `0x180006490`

## import_xrefs

- `USER32!CharNextW` at `0x1800064b3`
- `USER32!CharNextW` at `0x1800064b3`

## pseudocode

```c
void __fastcall ATL::CRegParser::SkipWhiteSpace(LPCWSTR *this)
{
  while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
    *this = CharNextW(*this);
}

```

## disassembly

```asm
0x180006490  push    rbx
0x180006492  sub     rsp, 20h
0x180006496  mov     rbx, rcx
0x180006499  mov     rcx, [rbx]; lpsz
0x18000649c  movzx   edx, word ptr [rcx]
0x18000649f  sub     edx, 9
0x1800064a2  jz      short loc_1800064B3
0x1800064a4  sub     edx, 1
0x1800064a7  jz      short loc_1800064B3
0x1800064a9  sub     edx, 3
0x1800064ac  jz      short loc_1800064B3
0x1800064ae  cmp     edx, 13h
0x1800064b1  jnz     short loc_1800064BE
0x1800064b3  call    cs:__imp_CharNextW
0x1800064b9  mov     [rbx], rax
0x1800064bc  jmp     short loc_180006499
0x1800064be  add     rsp, 20h
0x1800064c2  pop     rbx
0x1800064c3  retn
```
