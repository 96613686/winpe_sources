# UIItem::_UpdateVisualsForWindowsClassic(void)

- ea: `0x180031858`
- end: `0x180031910`
- name: `?_UpdateVisualsForWindowsClassic@UIItem@@IEAAXXZ`
- size: `184`
- prototype: `void __fastcall(UIItem *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180031980`
- `0x180032ff0`

## callees

- `0x180031858`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800318ad`
- `USER32!SystemParametersInfoW` at `0x1800318ad`
- `USER32!GetSysColor` at `0x1800318d9`
- `USER32!GetSysColor` at `0x1800318f4`
- `USER32!GetSysColor` at `0x1800318d9`
- `USER32!GetSysColor` at `0x1800318f4`
- `UxTheme!IsThemeActive` at `0x180031861`
- `UxTheme!IsThemeActive` at `0x180031861`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180031875`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180031875`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x18003188a`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800318bd`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800318bd`
- `DUI70!?GetWindowActive@Element@DirectUI@@QEAA_NXZ` at `0x1800318ca`
- `DUI70!?GetWindowActive@Element@DirectUI@@QEAA_NXZ` at `0x1800318ca`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800318e9`
- `DUI70!?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z` at `0x1800318e9`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18003186b`
- `DUI70!?SetForegroundColor@Element@DirectUI@@QEAAJK@Z` at `0x180031909`
- `DUI70!?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18003187b`

## pseudocode

```c
void __fastcall UIItem::_UpdateVisualsForWindowsClassic(UIItem *this)
{
  DWORD SysColor; // eax
  DWORD v3; // eax
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  if ( IsThemeActive()
    || (pvParam = 0, LODWORD(pvParam) = 16, SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0), (BYTE4(pvParam) & 1) != 0)
    || !DirectUI::Element::GetSelected(this)
    || DirectUI::Element::GetWindowActive(this) )
  {
    DirectUI::Element::RemoveLocalValue(
      this,
      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::BackgroundProp);
    DirectUI::Element::RemoveLocalValue(
      this,
      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ForegroundProp);
  }
  else
  {
    SysColor = GetSysColor(15);
    DirectUI::Element::SetBackgroundColor(this, SysColor | 0xFF000000);
    v3 = GetSysColor(18);
    DirectUI::Element::SetForegroundColor(this, v3 | 0xFF000000);
  }
}

```

## disassembly

```asm
0x180031858  push    rbx
0x18003185a  sub     rsp, 30h
0x18003185e  mov     rbx, rcx
0x180031861  call    cs:__imp_IsThemeActive
0x180031867  test    eax, eax
0x180031869  jz      short loc_180031891
0x18003186b  mov     rdx, cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x180031872  mov     rcx, rbx
0x180031875  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x18003187b  mov     rdx, cs:__imp_?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ForegroundProp(void)
0x180031882  mov     rcx, rbx
0x180031885  add     rsp, 30h
0x180031889  pop     rbx
0x18003188a  jmp     cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180031891  mov     edx, 10h; uiParam
0x180031896  lea     r8, [rsp+38h+pvParam]; pvParam
0x18003189b  xorps   xmm0, xmm0
0x18003189e  xor     r9d, r9d; fWinIni
0x1800318a1  movups  [rsp+38h+pvParam], xmm0
0x1800318a6  mov     dword ptr [rsp+38h+pvParam], edx
0x1800318aa  lea     ecx, [rdx+32h]; uiAction
0x1800318ad  call    cs:__imp_SystemParametersInfoW
0x1800318b3  test    byte ptr [rsp+38h+pvParam+4], 1
0x1800318b8  jnz     short loc_18003186B
0x1800318ba  mov     rcx, rbx
0x1800318bd  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800318c3  test    al, al
0x1800318c5  jz      short loc_18003186B
0x1800318c7  mov     rcx, rbx
0x1800318ca  call    cs:__imp_?GetWindowActive@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetWindowActive(void)
0x1800318d0  test    al, al
0x1800318d2  jnz     short loc_18003186B
0x1800318d4  mov     ecx, 0Fh; nIndex
0x1800318d9  call    cs:__imp_GetSysColor
0x1800318df  or      eax, 0FF000000h
0x1800318e4  mov     rcx, rbx
0x1800318e7  mov     edx, eax
0x1800318e9  call    cs:__imp_?SetBackgroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetBackgroundColor(ulong)
0x1800318ef  mov     ecx, 12h; nIndex
0x1800318f4  call    cs:__imp_GetSysColor
0x1800318fa  or      eax, 0FF000000h
0x1800318ff  mov     rcx, rbx
0x180031902  mov     edx, eax
0x180031904  add     rsp, 30h
0x180031908  pop     rbx
0x180031909  jmp     cs:__imp_?SetForegroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetForegroundColor(ulong)
```
