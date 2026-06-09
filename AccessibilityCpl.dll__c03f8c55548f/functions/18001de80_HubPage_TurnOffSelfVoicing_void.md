# HubPage::TurnOffSelfVoicing(void)

- ea: `0x18001de80`
- end: `0x18001df26`
- name: `?TurnOffSelfVoicing@HubPage@@AEAAXXZ`
- size: `166`
- prototype: `void __fastcall(HubPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001cc70`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180018260`
- `0x18001de80`
- `0x180029c04`

## import_xrefs

- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001df10`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001df10`
- `DUI70!StrToID` at `0x18001def4`
- `DUI70!StrToID` at `0x18001def4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001df00`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001df00`

## string_xrefs

- `0x18001dea4`: `Software\Microsoft\Ease of Access`

## pseudocode

```c
void __fastcall HubPage::TurnOffSelfVoicing(HubPage *this)
{
  DirectUI::Element *v2; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  HKEY v5[5]; // [rsp+20h] [rbp-28h] BYREF

  DuiVoice::Off((HubPage *)((char *)this + 264));
  memset(v5, 0, 24);
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v5,
                        HKEY_CURRENT_USER,
                        L"Software\\Microsoft\\Ease of Access",
                        0x20006u) )
    ATL::CRegKey::SetDWORDValue(v5, L"selfvoice", 0);
  v2 = (DirectUI::Element *)*((_QWORD *)this + 32);
  v3 = StrToID(L"selfvoice");
  Descendent = DirectUI::Element::FindDescendent(v2, v3);
  if ( Descendent )
    DirectUI::Element::SetSelected(Descendent, 0);
  ATL::CRegKey::Close((ATL::CRegKey *)v5);
}

```

## disassembly

```asm
0x18001de80  push    rbx
0x18001de82  sub     rsp, 40h
0x18001de86  mov     rbx, rcx
0x18001de89  add     rcx, 108h; this
0x18001de90  call    ?Off@DuiVoice@@QEAAXXZ; DuiVoice::Off(void)
0x18001de95  mov     r9d, 20006h; unsigned int
0x18001de9b  mov     [rsp+48h+var_28], 0
0x18001dea4  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Ease of Access"
0x18001deab  mov     [rsp+48h+var_20], 0
0x18001deb4  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001debb  mov     [rsp+48h+var_18], 0
0x18001dec4  lea     rcx, [rsp+48h+var_28]; this
0x18001dec9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001dece  test    eax, eax
0x18001ded0  jnz     short loc_18001DEE6
0x18001ded2  xor     r8d, r8d; unsigned int
0x18001ded5  lea     rdx, aSelfvoice; "selfvoice"
0x18001dedc  lea     rcx, [rsp+48h+var_28]; this
0x18001dee1  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001dee6  mov     rbx, [rbx+100h]
0x18001deed  lea     rcx, aSelfvoice; "selfvoice"
0x18001def4  call    cs:__imp_StrToID
0x18001defa  movzx   edx, ax
0x18001defd  mov     rcx, rbx
0x18001df00  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001df06  test    rax, rax
0x18001df09  jz      short loc_18001DF16
0x18001df0b  xor     edx, edx
0x18001df0d  mov     rcx, rax
0x18001df10  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001df16  lea     rcx, [rsp+48h+var_28]; this
0x18001df1b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001df20  add     rsp, 40h
0x18001df24  pop     rbx
0x18001df25  retn
```
