# CTxtWinHost::TxViewChange(int)

- ea: `0x18010a150`
- end: `0x18010a191`
- name: `?TxViewChange@CTxtWinHost@@UEAAXH@Z`
- size: `65`
- prototype: `void __fastcall(CTxtWinHost *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18010a150`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18010a180`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18010a180`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010a170`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010a189`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010a170`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010a189`

## pseudocode

```c
void __fastcall CTxtWinHost::TxViewChange(HWND *this, int a2)
{
  HWND Parent; // rax

  if ( (*((_DWORD *)this + 23) & 0x200) != 0 && a2 )
  {
    if ( ((_BYTE)this[11] & 0x20) != 0 )
    {
      Parent = GetParent(this[4]);
      UpdateWindow(Parent);
    }
    UpdateWindow(this[4]);
  }
}

```

## disassembly

```asm
0x18010a150  push    rbx
0x18010a152  sub     rsp, 20h
0x18010a156  test    dword ptr [rcx+5Ch], 200h
0x18010a15d  mov     rbx, rcx
0x18010a160  jz      short loc_18010A176
0x18010a162  test    edx, edx
0x18010a164  jz      short loc_18010A176
0x18010a166  test    byte ptr [rcx+58h], 20h
0x18010a16a  jnz     short loc_18010A17C
0x18010a16c  mov     rcx, [rbx+20h]; hWnd
0x18010a170  call    cs:__imp_UpdateWindow
0x18010a176  add     rsp, 20h
0x18010a17a  pop     rbx
0x18010a17b  retn
0x18010a17c  mov     rcx, [rcx+20h]; hWnd
0x18010a180  call    cs:__imp_GetParent
0x18010a186  mov     rcx, rax; hWnd
0x18010a189  call    cs:__imp_UpdateWindow
0x18010a18f  jmp     short loc_18010A16C
```
