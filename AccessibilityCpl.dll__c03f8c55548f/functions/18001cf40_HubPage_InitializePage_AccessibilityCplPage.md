# HubPage::InitializePage(AccessibilityCplPage *)

- ea: `0x18001cf40`
- end: `0x18001d068`
- name: `?InitializePage@HubPage@@UEAAJPEAVAccessibilityCplPage@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(HubPage *__hidden this, struct AccessibilityCplPage *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180003a60`
- `0x18001cde4`
- `0x18001cf40`
- `0x18001d6dc`
- `0x18001d978`
- `0x18002b930`
- `0x18002e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18001cf86`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18001cf86`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001d025`
- `DUI70!?SetActive@Element@DirectUI@@QEAAJH@Z` at `0x18001d025`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001cfdc`
- `DUI70!?SetSelected@Element@DirectUI@@QEAAJ_N@Z` at `0x18001cfdc`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18001cf9d`
- `DUI70!?SetAccessible@Element@DirectUI@@QEAAJ_N@Z` at `0x18001cf9d`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001cfe7`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18001cfe7`
- `DUI70!StrToID` at `0x18001cfbd`
- `DUI70!StrToID` at `0x18001d003`
- `DUI70!StrToID` at `0x18001cfbd`
- `DUI70!StrToID` at `0x18001d003`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001cfc9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d00f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001cfc9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001d00f`

## pseudocode

```c
HRESULT __fastcall HubPage::InitializePage(HubPage *this, struct AccessibilityCplPage *a2)
{
  void **v2; // rsi
  HRESULT result; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned __int16 *v7; // r9
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v11; // rbx
  DirectUI::Element *v12; // rbx
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  DirectUI::Element *v15; // rbx
  unsigned __int64 v16; // rdx

  v2 = (void **)((char *)this + 16);
  *((_QWORD *)this + 32) = a2;
  IUnknown_SafeReleaseAndNullPtr<IUnknown>((char *)this + 16);
  result = IUnknown_GetSite(
             (IUnknown *)((*((_QWORD *)this + 32) + 208LL) & -(__int64)(*((_QWORD *)this + 32) != 0)),
             &GUID_00000000_0000_0000_c000_000000000046,
             v2);
  if ( result >= 0 )
  {
    DirectUI::Element::SetAccessible(*((DirectUI::Element **)this + 32), 1);
    if ( (int)HubPage::SetUpSelfVoicing(this) < 0 )
    {
      v8 = (DirectUI::Element *)*((_QWORD *)this + 32);
      v9 = StrToID(L"selfvoice");
      Descendent = DirectUI::Element::FindDescendent(v8, v9);
      v11 = Descendent;
      if ( Descendent )
      {
        DirectUI::Element::SetSelected(Descendent, 0);
        DirectUI::Element::SetEnabled(v11, 0);
      }
    }
    HubPage::SetUpScanning(this, v5, v6, v7);
    v12 = (DirectUI::Element *)*((_QWORD *)this + 32);
    v13 = StrToID(L"selfscan");
    v14 = DirectUI::Element::FindDescendent(v12, v13);
    v15 = v14;
    if ( v14 )
    {
      DirectUI::Element::SetActive(v14, 3);
      (*(void (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v15 + 168LL))(v15);
    }
    DUI_WalkIUnknownElements(
      *((struct DirectUI::Element **)this + 12),
      (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown,
      (__int64)*v2);
    return HubPage::InitNavPane((IUnknown **)this, v16);
  }
  return result;
}

```

## disassembly

```asm
0x18001cf40  mov     [rsp+arg_0], rbx
0x18001cf45  mov     [rsp+arg_8], rsi
0x18001cf4a  push    rdi
0x18001cf4b  sub     rsp, 20h
0x18001cf4f  lea     rsi, [rcx+10h]
0x18001cf53  mov     [rcx+100h], rdx
0x18001cf5a  mov     rdi, rcx
0x18001cf5d  mov     rcx, rsi
0x18001cf60  call    ??$IUnknown_SafeReleaseAndNullPtr@UIUnknown@@@@YAXAEAPEAUIUnknown@@@Z; IUnknown_SafeReleaseAndNullPtr<IUnknown>(IUnknown * &)
0x18001cf65  mov     rax, [rdi+100h]
0x18001cf6c  mov     r8, rsi; ppv
0x18001cf6f  lea     rdx, [rax+0D0h]
0x18001cf76  neg     rax
0x18001cf79  sbb     rcx, rcx
0x18001cf7c  and     rcx, rdx; punk
0x18001cf7f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001cf86  call    cs:__imp_IUnknown_GetSite
0x18001cf8c  test    eax, eax
0x18001cf8e  js      loc_18001D058
0x18001cf94  mov     rcx, [rdi+100h]
0x18001cf9b  mov     dl, 1
0x18001cf9d  call    cs:__imp_?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x18001cfa3  mov     rcx, rdi; this
0x18001cfa6  call    ?SetUpSelfVoicing@HubPage@@AEAAJXZ; HubPage::SetUpSelfVoicing(void)
0x18001cfab  test    eax, eax
0x18001cfad  jns     short loc_18001CFED
0x18001cfaf  mov     rbx, [rdi+100h]
0x18001cfb6  lea     rcx, aSelfvoice; "selfvoice"
0x18001cfbd  call    cs:__imp_StrToID
0x18001cfc3  movzx   edx, ax
0x18001cfc6  mov     rcx, rbx
0x18001cfc9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001cfcf  mov     rbx, rax
0x18001cfd2  test    rax, rax
0x18001cfd5  jz      short loc_18001CFED
0x18001cfd7  xor     edx, edx
0x18001cfd9  mov     rcx, rax
0x18001cfdc  call    cs:__imp_?SetSelected@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetSelected(bool)
0x18001cfe2  xor     edx, edx
0x18001cfe4  mov     rcx, rbx
0x18001cfe7  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18001cfed  mov     rcx, rdi; this
0x18001cff0  call    ?SetUpScanning@HubPage@@AEAAJXZ; HubPage::SetUpScanning(void)
0x18001cff5  mov     rbx, [rdi+100h]
0x18001cffc  lea     rcx, aSelfscan; "selfscan"
0x18001d003  call    cs:__imp_StrToID
0x18001d009  movzx   edx, ax
0x18001d00c  mov     rcx, rbx
0x18001d00f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001d015  mov     rbx, rax
0x18001d018  test    rax, rax
0x18001d01b  jz      short loc_18001D03D
0x18001d01d  mov     edx, 3
0x18001d022  mov     rcx, rax
0x18001d025  call    cs:__imp_?SetActive@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetActive(int)
0x18001d02b  mov     rcx, [rbx]
0x18001d02e  mov     rax, [rcx+0A8h]
0x18001d035  mov     rcx, rbx
0x18001d038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d03d  mov     r8, [rsi]; __int64
0x18001d040  lea     rdx, ?DUI_SetSiteOnUnknown@@YAXPEAUIUnknown@@_J@Z; void (*)(struct IUnknown *, __int64)
0x18001d047  mov     rcx, [rdi+60h]; struct DirectUI::Element *
0x18001d04b  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x18001d050  mov     rcx, rdi; this
0x18001d053  call    ?InitNavPane@HubPage@@AEAAJXZ; HubPage::InitNavPane(void)
0x18001d058  mov     rbx, [rsp+28h+arg_0]
0x18001d05d  mov     rsi, [rsp+28h+arg_8]
0x18001d062  add     rsp, 20h
0x18001d066  pop     rdi
0x18001d067  retn
```
