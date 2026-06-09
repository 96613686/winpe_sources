# HubPage::OnNavigateAway(void)

- ea: `0x18001d4c0`
- end: `0x18001d59b`
- name: `?OnNavigateAway@HubPage@@UEAAXXZ`
- size: `219`
- prototype: `void __fastcall(HubPage *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000466c`
- `0x18001d4c0`
- `0x180029c04`
- `0x18002e010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001d568`
- `OLEAUT32!__imp_VariantClear` at `0x18001d568`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001d507`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001d507`
- `USER32!KillTimer` at `0x18001d4e1`
- `USER32!KillTimer` at `0x18001d4e1`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001d527`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001d527`
- `DUI70!StrToID` at `0x18001d537`
- `DUI70!StrToID` at `0x18001d537`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18001d559`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18001d559`

## string_xrefs

- `0x18001d552`: `AccessibilityAdminObject`
- `0x18001d578`: `AccessibilityAdminObject`

## pseudocode

```c
void __fastcall HubPage::OnNavigateAway(HWND *this)
{
  IUnknown *v2; // rcx
  DirectUI::Element *v3; // rcx
  unsigned __int16 ID; // bx
  VARIANT var; // [rsp+20h] [rbp-28h] BYREF
  void *ppvOut; // [rsp+50h] [rbp+8h] BYREF

  DuiVoice::Off((DuiVoice *)(this + 33));
  KillTimer(this[41], 0x123u);
  v2 = (IUnknown *)this[2];
  ppvOut = 0;
  if ( IUnknown_QueryService(
         v2,
         &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut) >= 0 )
  {
    v3 = (DirectUI::Element *)this[32];
    memset(&var, 0, sizeof(var));
    ID = DirectUI::Element::GetID(v3);
    if ( ID == (unsigned __int16)StrToID(L"pageAdminSettings")
      && PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"AccessibilityAdminObject", &var, 0xDu) >= 0 )
    {
      VariantClear(&var);
      (*(void (__fastcall **)(void *, const WCHAR *, VARIANT *))(*(_QWORD *)ppvOut + 32LL))(
        ppvOut,
        L"AccessibilityAdminObject",
        &var);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvOut);
}

```

## disassembly

```asm
0x18001d4c0  push    rbx
0x18001d4c2  sub     rsp, 40h
0x18001d4c6  mov     rbx, rcx
0x18001d4c9  add     rcx, 108h; this
0x18001d4d0  call    ?Off@DuiVoice@@QEAAXXZ; DuiVoice::Off(void)
0x18001d4d5  mov     rcx, [rbx+148h]; hWnd
0x18001d4dc  mov     edx, 123h; uIDEvent
0x18001d4e1  call    cs:__imp_KillTimer
0x18001d4e7  mov     rcx, [rbx+10h]; punk
0x18001d4eb  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x18001d4f0  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001d4f7  mov     [rsp+48h+ppvOut], 0
0x18001d500  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x18001d507  call    cs:__imp_IUnknown_QueryService
0x18001d50d  test    eax, eax
0x18001d50f  js      short loc_18001D58B
0x18001d511  mov     rcx, [rbx+100h]
0x18001d518  xorps   xmm0, xmm0
0x18001d51b  xor     eax, eax
0x18001d51d  movups  xmmword ptr [rsp+48h+var], xmm0
0x18001d522  mov     qword ptr [rsp+48h+var+10h], rax
0x18001d527  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x18001d52d  lea     rcx, aPageadminsetti; "pageAdminSettings"
0x18001d534  movzx   ebx, ax
0x18001d537  call    cs:__imp_StrToID
0x18001d53d  cmp     bx, ax
0x18001d540  jnz     short loc_18001D58B
0x18001d542  mov     rcx, [rsp+48h+ppvOut]; propBag
0x18001d547  lea     r8, [rsp+48h+var]; var
0x18001d54c  mov     r9d, 0Dh; type
0x18001d552  lea     rdx, propName; "AccessibilityAdminObject"
0x18001d559  call    cs:__imp_PSPropertyBag_ReadType
0x18001d55f  test    eax, eax
0x18001d561  js      short loc_18001D58B
0x18001d563  lea     rcx, [rsp+48h+var]; pvarg
0x18001d568  call    cs:__imp_VariantClear
0x18001d56e  mov     rcx, [rsp+48h+ppvOut]
0x18001d573  lea     r8, [rsp+48h+var]
0x18001d578  lea     rdx, propName; "AccessibilityAdminObject"
0x18001d57f  mov     rax, [rcx]
0x18001d582  mov     rax, [rax+20h]
0x18001d586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d58b  lea     rcx, [rsp+48h+ppvOut]
0x18001d590  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d595  add     rsp, 40h
0x18001d599  pop     rbx
0x18001d59a  retn
```
