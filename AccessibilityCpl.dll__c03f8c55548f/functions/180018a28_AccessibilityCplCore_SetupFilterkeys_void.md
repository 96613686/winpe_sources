# AccessibilityCplCore::SetupFilterkeys(void)

- ea: `0x180018a28`
- end: `0x180018ce8`
- name: `?SetupFilterkeys@AccessibilityCplCore@@AEAAXXZ`
- size: `704`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007a70`
- `0x1800198f4`

## callees

- `0x180004f78`
- `0x1800052b0`
- `0x1800055c0`
- `0x18000616c`
- `0x180014828`
- `0x180014b34`
- `0x180018a28`
- `0x18001a340`
- `0x180020d64`
- `0x180020edc`
- `0x18002d220`

## import_xrefs

- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018ab6`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018b6d`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018b7e`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018c86`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018cb9`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018ab6`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018b6d`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018b7e`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018c86`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018cb9`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180018bb5`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x180018bb5`
- `DUI70!StrToID` at `0x180018a94`
- `DUI70!StrToID` at `0x180018acf`
- `DUI70!StrToID` at `0x180018b15`
- `DUI70!StrToID` at `0x180018b35`
- `DUI70!StrToID` at `0x180018b8f`
- `DUI70!StrToID` at `0x180018c64`
- `DUI70!StrToID` at `0x180018c97`
- `DUI70!StrToID` at `0x180018a94`
- `DUI70!StrToID` at `0x180018acf`
- `DUI70!StrToID` at `0x180018b15`
- `DUI70!StrToID` at `0x180018b35`
- `DUI70!StrToID` at `0x180018b8f`
- `DUI70!StrToID` at `0x180018c64`
- `DUI70!StrToID` at `0x180018c97`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018aa0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018adb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018b21`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018b41`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018b9b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018c70`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018ca3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018aa0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018adb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018b21`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018b41`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018b9b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018c70`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018ca3`

## string_xrefs

- `0x180018b88`: `repeatrateslowkeyssettingslink`
- `0x180018bc9`: `Control Panel\Accessibility\Keyboard Response`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupFilterkeys(AccessibilityCplCore *this)
{
  const wchar_t **v2; // rbx
  DirectUI::Element *v3; // rdi
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v6; // rdi
  unsigned __int16 v7; // ax
  struct DirectUI::Combobox *v8; // rax
  DirectUI::Element *v9; // rdi
  unsigned __int16 v10; // ax
  struct DirectUI::Element *v11; // rax
  DirectUI::Element *v12; // rdi
  DirectUI::Element *v13; // r15
  unsigned __int16 v14; // ax
  DirectUI::Element *v15; // rax
  DirectUI::Element *v16; // r14
  DirectUI::Element *v17; // rdi
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // rax
  DirectUI::Element *v20; // rdi
  unsigned __int16 v21; // ax
  DirectUI::Element *v22; // rax
  DirectUI::Element *v23; // rdi
  unsigned __int16 v24; // ax
  DirectUI::Element *v25; // rax
  unsigned int v26; // edx
  _QWORD v27[3]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v28; // [rsp+48h] [rbp-30h] BYREF
  AccessibilityCplCore *v29; // [rsp+58h] [rbp-20h]

  v2 = (const wchar_t **)Accommodation::Open(L"filterkeys");
  if ( v2 )
  {
    v28 = 0;
    v29 = 0;
    Accommodation::GetData(v2, &v28);
    Accommodation::GetData(v2, (_DWORD *)this + 51);
    v3 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v4 = StrToID(L"filterkeysShortcut");
    Descendent = DirectUI::Element::FindDescendent(v3, v4);
    if ( Descendent && (BYTE4(v28) & 4) != 0 )
      DirectUI::Element::SetSelected(Descendent, 1);
    AccessibilityCplCore::SetupWarnings(this);
    v6 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v7 = StrToID(L"bouncekeysdelay");
    v8 = DirectUI::Element::FindDescendent(v6, v7);
    if ( v8 )
      AccessibilityCplCore::FillAndSetCombo(
        (AccessibilityCplCore *)HIDWORD(v29),
        v8,
        &qword_180033860,
        5u,
        HIDWORD(v29),
        1);
    v9 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v10 = StrToID(L"bouncekeys");
    v11 = DirectUI::Element::FindDescendent(v9, v10);
    v12 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v13 = v11;
    v14 = StrToID(L"slowkeys");
    v15 = DirectUI::Element::FindDescendent(v12, v14);
    v16 = v15;
    if ( v13 && v15 )
    {
      if ( *((_QWORD *)&v28 + 1) )
        DirectUI::Element::SetSelected(v15, 1);
      if ( HIDWORD(v29) )
        DirectUI::Element::SetSelected(v13, 1);
      v17 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v18 = StrToID(L"repeatrateslowkeyssettingslink");
      v19 = DirectUI::Element::FindDescendent(v17, v18);
      if ( v19 && (*((_BYTE *)v16 + 148) & 0x10) == 0 )
        DirectUI::Element::SetEnabled(v19, 0);
      memset(v27, 0, sizeof(v27));
      if ( !(unsigned int)ATL::CRegKey::Open(
                            (ATL::CRegKey *)v27,
                            HKEY_CURRENT_USER,
                            L"Control Panel\\Accessibility\\Keyboard Response",
                            0x20019u) )
      {
        ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v27, L"Last BounceKey Setting", (unsigned int *)this + 62);
        ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v27, L"Last Valid Delay", (unsigned int *)this + 60);
        ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v27, L"Last Valid Repeat", (unsigned int *)this + 61);
        ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v27, L"Last Valid Wait", (unsigned int *)this + 59);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)v27);
    }
    v20 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v21 = StrToID(L"click");
    v22 = DirectUI::Element::FindDescendent(v20, v21);
    if ( v22 && (BYTE4(v28) & 0x40) != 0 )
      DirectUI::Element::SetSelected(v22, 1);
    v23 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v24 = StrToID(L"indicator");
    v25 = DirectUI::Element::FindDescendent(v23, v24);
    if ( v25 )
    {
      if ( (BYTE4(v28) & 0x20) != 0 )
        DirectUI::Element::SetSelected(v25, 1);
    }
    AccessibilityCplCore::AddA11yNameToFilterKeysTestElement(this);
    Accommodation::`scalar deleting destructor'((Accommodation *)v2, v26);
  }
}

```

## disassembly

```asm
0x180018a28  push    rbp
0x180018a2a  push    rbx
0x180018a2b  push    rsi
0x180018a2c  push    rdi
0x180018a2d  push    r14
0x180018a2f  push    r15
0x180018a31  mov     rbp, rsp
0x180018a34  sub     rsp, 78h
0x180018a38  mov     rax, cs:__security_cookie
0x180018a3f  xor     rax, rsp
0x180018a42  mov     [rbp+var_18], rax
0x180018a46  mov     rsi, rcx
0x180018a49  lea     rcx, aFilterkeys; "filterkeys"
0x180018a50  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180018a55  mov     rbx, rax
0x180018a58  test    rax, rax
0x180018a5b  jz      loc_180018CCF
0x180018a61  xorps   xmm0, xmm0
0x180018a64  lea     rdx, [rbp+var_30]; void *
0x180018a68  xor     eax, eax
0x180018a6a  mov     rcx, rbx; this
0x180018a6d  movups  [rbp+var_30], xmm0
0x180018a71  mov     [rbp+var_20], rax
0x180018a75  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180018a7a  lea     rdx, [rsi+0CCh]; void *
0x180018a81  mov     rcx, rbx; this
0x180018a84  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180018a89  mov     rdi, [rsi+60h]
0x180018a8d  lea     rcx, aFilterkeysshor; "filterkeysShortcut"
0x180018a94  call    cs:__imp_StrToID
0x180018a9a  movzx   edx, ax
0x180018a9d  mov     rcx, rdi
0x180018aa0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018aa6  test    rax, rax
0x180018aa9  jz      short loc_180018ABC
0x180018aab  test    byte ptr [rbp+var_30+4], 4
0x180018aaf  jz      short loc_180018ABC
0x180018ab1  mov     dl, 1
0x180018ab3  mov     rcx, rax
0x180018ab6  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180018abc  mov     rcx, rsi; this
0x180018abf  call    ?SetupWarnings@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupWarnings(void)
0x180018ac4  mov     rdi, [rsi+60h]
0x180018ac8  lea     rcx, aBouncekeysdela; "bouncekeysdelay"
0x180018acf  call    cs:__imp_StrToID
0x180018ad5  movzx   edx, ax
0x180018ad8  mov     rcx, rdi
0x180018adb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018ae1  test    rax, rax
0x180018ae4  jz      short loc_180018B0A
0x180018ae6  mov     ecx, dword ptr [rbp+var_20+4]; this
0x180018ae9  lea     r8, qword_180033860; unsigned int *
0x180018af0  mov     [rsp+78h+var_50], 1; int
0x180018af8  mov     r9d, 5; unsigned int
0x180018afe  mov     rdx, rax; struct DirectUI::Combobox *
0x180018b01  mov     [rsp+78h+var_58], ecx; unsigned int
0x180018b05  call    ?FillAndSetCombo@AccessibilityCplCore@@AEAAXPEAVCombobox@DirectUI@@PEBIIIH@Z; AccessibilityCplCore::FillAndSetCombo(DirectUI::Combobox *,uint const *,uint,uint,int)
0x180018b0a  mov     rdi, [rsi+60h]
0x180018b0e  lea     rcx, aBouncekeys; "bouncekeys"
0x180018b15  call    cs:__imp_StrToID
0x180018b1b  movzx   edx, ax
0x180018b1e  mov     rcx, rdi
0x180018b21  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018b27  mov     rdi, [rsi+60h]
0x180018b2b  lea     rcx, aSlowkeys; "slowkeys"
0x180018b32  mov     r15, rax
0x180018b35  call    cs:__imp_StrToID
0x180018b3b  movzx   edx, ax
0x180018b3e  mov     rcx, rdi
0x180018b41  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018b47  mov     r14, rax
0x180018b4a  test    r15, r15
0x180018b4d  jz      loc_180018C59
0x180018b53  test    rax, rax
0x180018b56  jz      loc_180018C59
0x180018b5c  cmp     dword ptr [rbp+var_30+0Ch], 0
0x180018b60  jnz     short loc_180018B68
0x180018b62  cmp     dword ptr [rbp+var_30+8], 0
0x180018b66  jz      short loc_180018B73
0x180018b68  mov     dl, 1
0x180018b6a  mov     rcx, r14
0x180018b6d  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180018b73  cmp     dword ptr [rbp+var_20+4], 0
0x180018b77  jz      short loc_180018B84
0x180018b79  mov     dl, 1
0x180018b7b  mov     rcx, r15
0x180018b7e  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180018b84  mov     rdi, [rsi+60h]
0x180018b88  lea     rcx, aRepeatrateslow; "repeatrateslowkeyssettingslink"
0x180018b8f  call    cs:__imp_StrToID
0x180018b95  movzx   edx, ax
0x180018b98  mov     rcx, rdi
0x180018b9b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018ba1  test    rax, rax
0x180018ba4  jz      short loc_180018BBB
0x180018ba6  test    byte ptr [r14+94h], 10h
0x180018bae  jnz     short loc_180018BBB
0x180018bb0  xor     edx, edx
0x180018bb2  mov     rcx, rax
0x180018bb5  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x180018bbb  mov     r9d, 20019h; unsigned int
0x180018bc1  mov     [rbp+var_48], 0
0x180018bc9  lea     r8, aControlPanelAc; "Control Panel\\Accessibility\\Keyboard "...
0x180018bd0  mov     [rbp+var_40], 0
0x180018bd8  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180018bdf  mov     [rbp+var_38], 0
0x180018be7  lea     rcx, [rbp+var_48]; this
0x180018beb  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180018bf0  test    eax, eax
0x180018bf2  jnz     short loc_180018C50
0x180018bf4  lea     r8, [rsi+0F8h]; unsigned int *
0x180018bfb  lea     rdx, aLastBouncekeyS; "Last BounceKey Setting"
0x180018c02  lea     rcx, [rbp+var_48]; this
0x180018c06  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180018c0b  lea     r8, [rsi+0F0h]; unsigned int *
0x180018c12  lea     rdx, aLastValidDelay; "Last Valid Delay"
0x180018c19  lea     rcx, [rbp+var_48]; this
0x180018c1d  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180018c22  lea     r8, [rsi+0F4h]; unsigned int *
0x180018c29  lea     rdx, aLastValidRepea; "Last Valid Repeat"
0x180018c30  lea     rcx, [rbp+var_48]; this
0x180018c34  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180018c39  lea     r8, [rsi+0ECh]; unsigned int *
0x180018c40  lea     rdx, aLastValidWait; "Last Valid Wait"
0x180018c47  lea     rcx, [rbp+var_48]; this
0x180018c4b  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180018c50  lea     rcx, [rbp+var_48]; this
0x180018c54  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018c59  mov     rdi, [rsi+60h]
0x180018c5d  lea     rcx, aClick; "click"
0x180018c64  call    cs:__imp_StrToID
0x180018c6a  movzx   edx, ax
0x180018c6d  mov     rcx, rdi
0x180018c70  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018c76  test    rax, rax
0x180018c79  jz      short loc_180018C8C
0x180018c7b  test    byte ptr [rbp+var_30+4], 40h
0x180018c7f  jz      short loc_180018C8C
0x180018c81  mov     dl, 1
0x180018c83  mov     rcx, rax
0x180018c86  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180018c8c  mov     rdi, [rsi+60h]
0x180018c90  lea     rcx, aIndicator; "indicator"
0x180018c97  call    cs:__imp_StrToID
0x180018c9d  movzx   edx, ax
0x180018ca0  mov     rcx, rdi
0x180018ca3  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018ca9  test    rax, rax
0x180018cac  jz      short loc_180018CBF
0x180018cae  test    byte ptr [rbp+var_30+4], 20h
0x180018cb2  jz      short loc_180018CBF
0x180018cb4  mov     dl, 1
0x180018cb6  mov     rcx, rax
0x180018cb9  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180018cbf  mov     rcx, rsi; this
0x180018cc2  call    ?AddA11yNameToFilterKeysTestElement@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::AddA11yNameToFilterKeysTestElement(void)
0x180018cc7  mov     rcx, rbx; this
0x180018cca  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180018ccf  mov     rcx, [rbp+var_18]
0x180018cd3  xor     rcx, rsp; StackCookie
0x180018cd6  call    __security_check_cookie
0x180018cdb  add     rsp, 78h
0x180018cdf  pop     r15
0x180018ce1  pop     r14
0x180018ce3  pop     rdi
0x180018ce4  pop     rsi
0x180018ce5  pop     rbx
0x180018ce6  pop     rbp
0x180018ce7  retn
```
