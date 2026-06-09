# AccessibilityCplCore::SetupHighContrast(void)

- ea: `0x180018d80`
- end: `0x180018e99`
- name: `?SetupHighContrast@AccessibilityCplCore@@AEAAXXZ`
- size: `281`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a70`
- `0x1800198f4`

## callees

- `0x180004f78`
- `0x18000829c`
- `0x180018d80`
- `0x18001a340`
- `0x180020d64`
- `0x180020edc`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018e54`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018e54`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180018e66`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180018e66`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018e02`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x180018e02`
- `DUI70!StrToID` at `0x180018de6`
- `DUI70!StrToID` at `0x180018e24`
- `DUI70!StrToID` at `0x180018de6`
- `DUI70!StrToID` at `0x180018e24`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018df2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018e30`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018df2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180018e30`

## pseudocode

```c
void __fastcall AccessibilityCplCore::SetupHighContrast(AccessibilityCplCore *this)
{
  const wchar_t **v2; // rax
  Accommodation *v3; // rbx
  DirectUI::Element *v4; // rdi
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  AccessibilityCplCore *v7; // rcx
  DirectUI::Element *v8; // rdi
  unsigned __int16 v9; // ax
  DirectUI::Element *v10; // rdi
  __int128 v11; // [rsp+20h] [rbp-128h] BYREF
  WCHAR Buffer[128]; // [rsp+30h] [rbp-118h] BYREF

  v2 = (const wchar_t **)Accommodation::Open(L"highcontrast");
  v3 = (Accommodation *)v2;
  if ( v2 )
  {
    v11 = 0;
    Accommodation::GetData(v2, &v11);
    if ( (BYTE4(v11) & 4) != 0 )
    {
      v4 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v5 = StrToID(L"highcontrastshortcut");
      Descendent = DirectUI::Element::FindDescendent(v4, v5);
      if ( Descendent )
        DirectUI::Element::SetSelected(Descendent, 1);
    }
    AccessibilityCplCore::SetupWarnings(this);
    if ( (unsigned __int8)AccessibilityCplCore::IsPersonalizationFeatureEnabled(v7) )
    {
      v8 = (DirectUI::Element *)*((_QWORD *)this + 12);
      v9 = StrToID(L"actionChangeHighContrastTheme");
      v10 = DirectUI::Element::FindDescendent(v8, v9);
      if ( v10 )
      {
        if ( LoadStringW(g_hinst, 0x46u, Buffer, 128) )
          DirectUI::Element::SetContentString(v10, Buffer);
      }
    }
    Accommodation::`scalar deleting destructor'(v3);
  }
}

```

## disassembly

```asm
0x180018d80  mov     [rsp+arg_8], rbx
0x180018d85  mov     [rsp+arg_10], rsi
0x180018d8a  push    rdi
0x180018d8b  sub     rsp, 140h
0x180018d92  mov     rax, cs:__security_cookie
0x180018d99  xor     rax, rsp
0x180018d9c  mov     [rsp+148h+var_18], rax
0x180018da4  mov     rsi, rcx
0x180018da7  lea     rcx, aHighcontrast; "highcontrast"
0x180018dae  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x180018db3  mov     rbx, rax
0x180018db6  test    rax, rax
0x180018db9  jz      loc_180018E74
0x180018dbf  xorps   xmm0, xmm0
0x180018dc2  lea     rdx, [rsp+148h+var_128]; void *
0x180018dc7  mov     rcx, rax; this
0x180018dca  movups  [rsp+148h+var_128], xmm0
0x180018dcf  call    ?GetData@Accommodation@@QEAAXPEAX@Z; Accommodation::GetData(void *)
0x180018dd4  test    byte ptr [rsp+148h+var_128+4], 4
0x180018dd9  jz      short loc_180018E08
0x180018ddb  mov     rdi, [rsi+60h]
0x180018ddf  lea     rcx, aHighcontrastsh; "highcontrastshortcut"
0x180018de6  call    cs:__imp_StrToID
0x180018dec  movzx   edx, ax
0x180018def  mov     rcx, rdi
0x180018df2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018df8  test    rax, rax
0x180018dfb  jz      short loc_180018E08
0x180018dfd  mov     dl, 1
0x180018dff  mov     rcx, rax
0x180018e02  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x180018e08  mov     rcx, rsi; this
0x180018e0b  call    ?SetupWarnings@AccessibilityCplCore@@AEAAXXZ; AccessibilityCplCore::SetupWarnings(void)
0x180018e10  call    ?IsPersonalizationFeatureEnabled@AccessibilityCplCore@@AEAA_NXZ; AccessibilityCplCore::IsPersonalizationFeatureEnabled(void)
0x180018e15  test    al, al
0x180018e17  jz      short loc_180018E6C
0x180018e19  mov     rdi, [rsi+60h]
0x180018e1d  lea     rcx, aActionchangehi; "actionChangeHighContrastTheme"
0x180018e24  call    cs:__imp_StrToID
0x180018e2a  movzx   edx, ax
0x180018e2d  mov     rcx, rdi
0x180018e30  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180018e36  mov     rdi, rax
0x180018e39  test    rax, rax
0x180018e3c  jz      short loc_180018E6C
0x180018e3e  mov     rcx, cs:g_hinst; hInstance
0x180018e45  lea     r8, [rsp+148h+Buffer]; lpBuffer
0x180018e4a  mov     r9d, 80h; cchBufferMax
0x180018e50  lea     edx, [r9-3Ah]; uID
0x180018e54  call    cs:__imp_LoadStringW
0x180018e5a  test    eax, eax
0x180018e5c  jz      short loc_180018E6C
0x180018e5e  lea     rdx, [rsp+148h+Buffer]
0x180018e63  mov     rcx, rdi
0x180018e66  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180018e6c  mov     rcx, rbx; this
0x180018e6f  call    ??_GAccommodation@@QEAAPEAXI@Z; Accommodation::`scalar deleting destructor'(uint)
0x180018e74  mov     rcx, [rsp+148h+var_18]
0x180018e7c  xor     rcx, rsp; StackCookie
0x180018e7f  call    __security_check_cookie
0x180018e84  lea     r11, [rsp+148h+var_8]
0x180018e8c  mov     rbx, [r11+18h]
0x180018e90  mov     rsi, [r11+20h]
0x180018e94  mov     rsp, r11
0x180018e97  pop     rdi
0x180018e98  retn
```
