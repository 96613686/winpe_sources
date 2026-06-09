# AccessibilityCplCore::OnNavigateAway(void)

- ea: `0x180014580`
- end: `0x180014682`
- name: `?OnNavigateAway@AccessibilityCplCore@@UEAAXXZ`
- size: `258`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000466c`
- `0x180014580`
- `0x18002e010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800145ea`
- `OLEAUT32!__imp_VariantClear` at `0x18001464d`
- `OLEAUT32!__imp_VariantClear` at `0x1800145ea`
- `OLEAUT32!__imp_VariantClear` at `0x18001464d`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800145ae`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800145ae`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001460f`
- `DUI70!?GetID@Element@DirectUI@@QEAAGXZ` at `0x18001460f`
- `DUI70!StrToID` at `0x18001461f`
- `DUI70!StrToID` at `0x18001461f`
- `PROPSYS!PSPropertyBag_ReadType` at `0x1800145dc`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18001463f`
- `PROPSYS!PSPropertyBag_ReadType` at `0x1800145dc`
- `PROPSYS!PSPropertyBag_ReadType` at `0x18001463f`

## string_xrefs

- `0x1800145c6`: `AccessibilityCplCore`
- `0x1800145f8`: `AccessibilityCplCore`
- `0x180014638`: `AccessibilityAdminObject`
- `0x18001465b`: `AccessibilityAdminObject`

## pseudocode

```c
void __fastcall AccessibilityCplCore::OnNavigateAway(AccessibilityCplCore *this)
{
  unsigned __int16 ID; // bx
  VARIANT var; // [rsp+20h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+50h] [rbp+10h] BYREF

  ppvOut = 0;
  if ( IUnknown_QueryService(
         *((IUnknown **)this + 2),
         &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut) >= 0 )
  {
    memset(&var, 0, sizeof(var));
    if ( PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"AccessibilityCplCore", &var, 0xDu) >= 0 )
    {
      VariantClear(&var);
      (*(void (__fastcall **)(void *, const WCHAR *, VARIANT *))(*(_QWORD *)ppvOut + 32LL))(
        ppvOut,
        L"AccessibilityCplCore",
        &var);
    }
    ID = DirectUI::Element::GetID(*((DirectUI::Element **)this + 12));
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
0x180014580  mov     [rsp-8+arg_8], rbx
0x180014585  push    rbp
0x180014586  mov     rbp, rsp
0x180014589  sub     rsp, 40h
0x18001458d  mov     rbx, rcx
0x180014590  mov     [rbp+ppvOut], 0
0x180014598  mov     rcx, [rcx+10h]; punk
0x18001459c  lea     r9, [rbp+ppvOut]; ppvOut
0x1800145a0  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800145a7  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x1800145ae  call    cs:__imp_IUnknown_QueryService
0x1800145b4  test    eax, eax
0x1800145b6  js      loc_18001466E
0x1800145bc  mov     rcx, [rbp+ppvOut]; propBag
0x1800145c0  lea     r8, [rbp+var]; var
0x1800145c4  xor     eax, eax
0x1800145c6  lea     rdx, aAccessibilityc_0; "AccessibilityCplCore"
0x1800145cd  xorps   xmm0, xmm0
0x1800145d0  mov     qword ptr [rbp+var+10h], rax
0x1800145d4  movups  xmmword ptr [rbp+var], xmm0
0x1800145d8  lea     r9d, [rax+0Dh]; type
0x1800145dc  call    cs:__imp_PSPropertyBag_ReadType
0x1800145e2  test    eax, eax
0x1800145e4  js      short loc_18001460B
0x1800145e6  lea     rcx, [rbp+var]; pvarg
0x1800145ea  call    cs:__imp_VariantClear
0x1800145f0  mov     rcx, [rbp+ppvOut]
0x1800145f4  lea     r8, [rbp+var]
0x1800145f8  lea     rdx, aAccessibilityc_0; "AccessibilityCplCore"
0x1800145ff  mov     rax, [rcx]
0x180014602  mov     rax, [rax+20h]
0x180014606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001460b  mov     rcx, [rbx+60h]
0x18001460f  call    cs:__imp_?GetID@Element@DirectUI@@QEAAGXZ; DirectUI::Element::GetID(void)
0x180014615  lea     rcx, aPageadminsetti; "pageAdminSettings"
0x18001461c  movzx   ebx, ax
0x18001461f  call    cs:__imp_StrToID
0x180014625  cmp     bx, ax
0x180014628  jnz     short loc_18001466E
0x18001462a  mov     rcx, [rbp+ppvOut]; propBag
0x18001462e  lea     r8, [rbp+var]; var
0x180014632  mov     r9d, 0Dh; type
0x180014638  lea     rdx, propName; "AccessibilityAdminObject"
0x18001463f  call    cs:__imp_PSPropertyBag_ReadType
0x180014645  test    eax, eax
0x180014647  js      short loc_18001466E
0x180014649  lea     rcx, [rbp+var]; pvarg
0x18001464d  call    cs:__imp_VariantClear
0x180014653  mov     rcx, [rbp+ppvOut]
0x180014657  lea     r8, [rbp+var]
0x18001465b  lea     rdx, propName; "AccessibilityAdminObject"
0x180014662  mov     rax, [rcx]
0x180014665  mov     rax, [rax+20h]
0x180014669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001466e  lea     rcx, [rbp+ppvOut]
0x180014672  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014677  mov     rbx, [rsp+40h+arg_8]
0x18001467c  add     rsp, 40h
0x180014680  pop     rbp
0x180014681  retn
```
