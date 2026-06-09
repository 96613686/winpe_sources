# CTxtWinHost::TxViewChange(int)

- ea: `0x1800402d0`
- end: `0x18004030f`
- name: `?TxViewChange@CTxtWinHost@@UEAAXH@Z`
- size: `63`
- prototype: `void __fastcall(CTxtWinHost *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800402d0`

## import_xrefs

- `USER32!GetParent` at `0x1800402f0`
- `USER32!GetParent` at `0x1800402f0`
- `USER32!UpdateWindow` at `0x1800402f9`
- `USER32!UpdateWindow` at `0x180040303`
- `USER32!UpdateWindow` at `0x1800402f9`
- `USER32!UpdateWindow` at `0x180040303`

## pseudocode

```c
void __fastcall CTxtWinHost::TxViewChange(HWND *this, int a2)
{
  HWND Parent; // rax

  if ( (*((_DWORD *)this + 13) & 0x200) != 0 && a2 )
  {
    if ( ((_BYTE)this[6] & 0x20) != 0 )
    {
      Parent = GetParent(this[2]);
      UpdateWindow(Parent);
    }
    UpdateWindow(this[2]);
  }
}

```

## disassembly

```asm
0x1800402d0  push    rbx
0x1800402d2  sub     rsp, 20h
0x1800402d6  test    dword ptr [rcx+34h], 200h
0x1800402dd  mov     rbx, rcx
0x1800402e0  jz      short loc_180040309
0x1800402e2  test    edx, edx
0x1800402e4  jz      short loc_180040309
0x1800402e6  test    byte ptr [rcx+30h], 20h
0x1800402ea  jz      short loc_1800402FF
0x1800402ec  mov     rcx, [rcx+10h]; hWnd
0x1800402f0  call    cs:__imp_GetParent
0x1800402f6  mov     rcx, rax; hWnd
0x1800402f9  call    cs:__imp_UpdateWindow
0x1800402ff  mov     rcx, [rbx+10h]; hWnd
0x180040303  call    cs:__imp_UpdateWindow
0x180040309  add     rsp, 20h
0x18004030d  pop     rbx
0x18004030e  retn
```
