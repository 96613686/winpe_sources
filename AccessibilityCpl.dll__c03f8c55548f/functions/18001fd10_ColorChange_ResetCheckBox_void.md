# ColorChange::ResetCheckBox(void)

- ea: `0x18001fd10`
- end: `0x18001fd51`
- name: `?ResetCheckBox@ColorChange@@QEAAXXZ`
- size: `65`
- prototype: `void __fastcall(ColorChange *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001fca0`

## callees

- `0x18001fd10`

## import_xrefs

- `USER32!KillTimer` at `0x18001fd4a`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x18001fd31`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x18001fd31`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001fd24`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001fd24`

## pseudocode

```c
void __fastcall ColorChange::ResetCheckBox(ColorChange *this)
{
  DirectUI::Element *v2; // rcx

  v2 = (DirectUI::Element *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    DirectUI::Element::SetEnabled(v2, 1);
    DirectUI::Element::RemoveListener(*((DirectUI::Element **)this + 2), this);
    *((_QWORD *)this + 2) = 0;
  }
  KillTimer(0, *((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x18001fd10  push    rbx
0x18001fd12  sub     rsp, 20h
0x18001fd16  mov     rbx, rcx
0x18001fd19  mov     rcx, [rcx+10h]
0x18001fd1d  test    rcx, rcx
0x18001fd20  jz      short loc_18001FD3F
0x18001fd22  mov     dl, 1
0x18001fd24  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18001fd2a  mov     rcx, [rbx+10h]
0x18001fd2e  mov     rdx, rbx
0x18001fd31  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x18001fd37  mov     qword ptr [rbx+10h], 0
0x18001fd3f  mov     rdx, [rbx+8]
0x18001fd43  xor     ecx, ecx
0x18001fd45  add     rsp, 20h
0x18001fd49  pop     rbx
0x18001fd4a  jmp     cs:__imp_KillTimer
```
