# AccessibilityCplCore::SetupWarnings(void)

- ea: `0x18001a340`
- end: `0x18001a447`
- name: `?SetupWarnings@AccessibilityCplCore@@AEAAXXZ`
- size: `263`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180007a70`
- `0x180018a28`
- `0x180018d80`
- `0x180019194`
- `0x180019fcc`

## callees

- `0x1800055c0`
- `0x180014828`
- `0x180014b34`
- `0x18001a340`

## import_xrefs

- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a3f5`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a428`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a3f5`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001a428`
- `DUI70!StrToID` at `0x18001a3d3`
- `DUI70!StrToID` at `0x18001a406`
- `DUI70!StrToID` at `0x18001a3d3`
- `DUI70!StrToID` at `0x18001a406`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001a3df`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001a412`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001a3df`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001a412`

## string_xrefs

- `0x18001a377`: `Control Panel\Accessibility`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupWarnings(AccessibilityCplCore *this)
{
  DirectUI::Element *v2; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // ax
  DirectUI::Element *v7; // rax
  _QWORD v8[4]; // [rsp+20h] [rbp-20h] BYREF
  unsigned int v9; // [rsp+58h] [rbp+18h] BYREF
  unsigned int v10; // [rsp+60h] [rbp+20h] BYREF

  memset(v8, 0, 24);
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v8,
                        HKEY_CURRENT_USER,
                        L"Control Panel\\Accessibility",
                        0x20019u) )
  {
    v10 = 1;
    v9 = 1;
    ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v8, L"Sound on Activation", &v10);
    ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)v8, L"Warning Sounds", &v9);
    v2 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v3 = StrToID(L"warningmessage");
    Descendent = DirectUI::Element::FindDescendent(v2, v3);
    if ( Descendent && v9 )
      DirectUI::Element::SetSelected(Descendent, 1);
    v5 = (DirectUI::Element *)*((_QWORD *)this + 12);
    v6 = StrToID(L"warningsound");
    v7 = DirectUI::Element::FindDescendent(v5, v6);
    if ( v7 && v10 )
      DirectUI::Element::SetSelected(v7, 1);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v8);
}

```

## disassembly

```asm
0x18001a340  mov     [rsp-8+arg_0], rbx
0x18001a345  mov     [rsp-8+arg_18], rdi
0x18001a34a  push    rbp
0x18001a34b  mov     rbp, rsp
0x18001a34e  sub     rsp, 40h
0x18001a352  mov     rdi, rcx
0x18001a355  mov     [rbp+var_20], 0
0x18001a35d  lea     rcx, [rbp+var_20]; this
0x18001a361  mov     [rbp+var_18], 0
0x18001a369  mov     r9d, 20019h; unsigned int
0x18001a36f  mov     [rbp+var_10], 0
0x18001a377  lea     r8, aControlPanelAc_1; "Control Panel\\Accessibility"
0x18001a37e  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18001a385  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a38a  test    eax, eax
0x18001a38c  jnz     loc_18001A42E
0x18001a392  lea     r8, [rbp+arg_10]; unsigned int *
0x18001a396  mov     [rbp+arg_10], 1
0x18001a39d  lea     rdx, aSoundOnActivat; "Sound on Activation"
0x18001a3a4  mov     [rbp+arg_8], 1
0x18001a3ab  lea     rcx, [rbp+var_20]; this
0x18001a3af  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001a3b4  lea     r8, [rbp+arg_8]; unsigned int *
0x18001a3b8  lea     rdx, aWarningSounds; "Warning Sounds"
0x18001a3bf  lea     rcx, [rbp+var_20]; this
0x18001a3c3  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001a3c8  mov     rbx, [rdi+60h]
0x18001a3cc  lea     rcx, aWarningmessage; "warningmessage"
0x18001a3d3  call    cs:__imp_StrToID
0x18001a3d9  movzx   edx, ax
0x18001a3dc  mov     rcx, rbx
0x18001a3df  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001a3e5  test    rax, rax
0x18001a3e8  jz      short loc_18001A3FB
0x18001a3ea  cmp     [rbp+arg_8], 0
0x18001a3ee  jz      short loc_18001A3FB
0x18001a3f0  mov     dl, 1
0x18001a3f2  mov     rcx, rax
0x18001a3f5  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001a3fb  mov     rbx, [rdi+60h]
0x18001a3ff  lea     rcx, aWarningsound; "warningsound"
0x18001a406  call    cs:__imp_StrToID
0x18001a40c  movzx   edx, ax
0x18001a40f  mov     rcx, rbx
0x18001a412  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001a418  test    rax, rax
0x18001a41b  jz      short loc_18001A42E
0x18001a41d  cmp     [rbp+arg_10], 0
0x18001a421  jz      short loc_18001A42E
0x18001a423  mov     dl, 1
0x18001a425  mov     rcx, rax
0x18001a428  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001a42e  lea     rcx, [rbp+var_20]; this
0x18001a432  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a437  mov     rbx, [rsp+40h+arg_0]
0x18001a43c  mov     rdi, [rsp+40h+arg_18]
0x18001a441  add     rsp, 40h
0x18001a445  pop     rbp
0x18001a446  retn
```
