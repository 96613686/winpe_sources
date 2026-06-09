# HubPage::TurnOffSelfScanning(void)

- ea: `0x18001ddcc`
- end: `0x18001de78`
- name: `?TurnOffSelfScanning@HubPage@@AEAAXXZ`
- size: `172`
- prototype: `void __fastcall(HubPage *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001cc70`
- `0x18001d280`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180018260`
- `0x18001ddcc`

## import_xrefs

- `USER32!KillTimer` at `0x18001dde1`
- `USER32!KillTimer` at `0x18001dde1`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001de62`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001de62`
- `DUI70!StrToID` at `0x18001de46`
- `DUI70!StrToID` at `0x18001de46`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001de52`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001de52`

## string_xrefs

- `0x18001ddf6`: `Software\Microsoft\Ease of Access`

## pseudocode

```c
void __fastcall HubPage::TurnOffSelfScanning(HWND *this)
{
  DirectUI::Element *v2; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  HKEY v5[5]; // [rsp+20h] [rbp-28h] BYREF

  KillTimer(this[41], 0x123u);
  memset(v5, 0, 24);
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v5,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Ease of Access",
                        0x20006u) )
    ATL::CRegKey::SetDWORDValue(v5, L"selfscan", 0);
  v2 = (DirectUI::Element *)this[32];
  v3 = StrToID(L"selfscan");
  Descendent = DirectUI::Element::FindDescendent(v2, v3);
  if ( Descendent )
    DirectUI::Element::SetSelected(Descendent, 0);
  ATL::CRegKey::Close((ATL::CRegKey *)v5);
}

```

## disassembly

```asm
0x18001ddcc  push    rbx
0x18001ddce  sub     rsp, 40h
0x18001ddd2  mov     rbx, rcx
0x18001ddd5  mov     edx, 123h; uIDEvent
0x18001ddda  mov     rcx, [rcx+148h]; hWnd
0x18001dde1  call    cs:__imp_KillTimer
0x18001dde7  mov     r9d, 20006h; unsigned int
0x18001dded  mov     [rsp+48h+var_28], 0
0x18001ddf6  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x18001ddfd  mov     [rsp+48h+var_20], 0
0x18001de06  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001de0d  mov     [rsp+48h+var_18], 0
0x18001de16  lea     rcx, [rsp+48h+var_28]; this
0x18001de1b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001de20  test    eax, eax
0x18001de22  jnz     short loc_18001DE38
0x18001de24  xor     r8d, r8d; unsigned int
0x18001de27  lea     rdx, aSelfscan; "selfscan"
0x18001de2e  lea     rcx, [rsp+48h+var_28]; this
0x18001de33  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001de38  mov     rbx, [rbx+100h]
0x18001de3f  lea     rcx, aSelfscan; "selfscan"
0x18001de46  call    cs:__imp_StrToID
0x18001de4c  movzx   edx, ax
0x18001de4f  mov     rcx, rbx
0x18001de52  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001de58  test    rax, rax
0x18001de5b  jz      short loc_18001DE68
0x18001de5d  xor     edx, edx
0x18001de5f  mov     rcx, rax
0x18001de62  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001de68  lea     rcx, [rsp+48h+var_28]; this
0x18001de6d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001de72  add     rsp, 40h
0x18001de76  pop     rbx
0x18001de77  retn
```
