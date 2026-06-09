# s_Repaint(HWND__ *,uint,unsigned __int64,ulong)

- ea: `0x1800100e0`
- end: `0x180010155`
- name: `?s_Repaint@@YAXPEAUHWND__@@I_KK@Z`
- size: `117`
- prototype: `void __stdcall(HWND, UINT, UINT_PTR, DWORD)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800100e0`

## import_xrefs

- `USER32!KillTimer` at `0x1800100ec`
- `USER32!KillTimer` at `0x1800100ec`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180010149`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180010149`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001012a`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001012a`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x180010108`
- `DUI70!?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z` at `0x180010108`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001013c`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001013c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001011c`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18001011c`

## pseudocode

```c
void __fastcall s_Repaint(HWND a1, __int64 a2, DirectUI::Element *a3)
{
  struct DirectUI::Element *v4; // [rsp+40h] [rbp+18h] BYREF

  KillTimer(a1, (UINT_PTR)a3);
  v4 = 0;
  if ( (int)DirectUI::Element::Create(0, a3, 0, &v4) >= 0 )
  {
    DirectUI::Element::SetLayoutPos(v4, 4);
    if ( (int)DirectUI::Element::Add(a3, v4) >= 0 )
      DirectUI::Element::Remove(a3, v4);
    DirectUI::Element::Destroy(v4, 1);
  }
}

```

## disassembly

```asm
0x1800100e0  push    rbx
0x1800100e2  sub     rsp, 20h
0x1800100e6  mov     rdx, r8; uIDEvent
0x1800100e9  mov     rbx, r8
0x1800100ec  call    cs:__imp_KillTimer
0x1800100f2  lea     r9, [rsp+28h+arg_10]
0x1800100f7  mov     [rsp+28h+arg_10], 0
0x180010100  xor     r8d, r8d
0x180010103  mov     rdx, rbx
0x180010106  xor     ecx, ecx
0x180010108  call    cs:__imp_?Create@Element@DirectUI@@SAJIPEAV12@PEAKPEAPEAV12@@Z; DirectUI::Element::Create(uint,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18001010e  test    eax, eax
0x180010110  js      short loc_18001014F
0x180010112  mov     rcx, [rsp+28h+arg_10]
0x180010117  mov     edx, 4
0x18001011c  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180010122  mov     rdx, [rsp+28h+arg_10]
0x180010127  mov     rcx, rbx
0x18001012a  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180010130  test    eax, eax
0x180010132  js      short loc_180010142
0x180010134  mov     rdx, [rsp+28h+arg_10]
0x180010139  mov     rcx, rbx
0x18001013c  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x180010142  mov     rcx, [rsp+28h+arg_10]
0x180010147  mov     dl, 1
0x180010149  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18001014f  add     rsp, 20h
0x180010153  pop     rbx
0x180010154  retn
```
