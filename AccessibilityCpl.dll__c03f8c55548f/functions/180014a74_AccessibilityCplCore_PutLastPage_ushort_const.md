# AccessibilityCplCore::PutLastPage(ushort const *)

- ea: `0x180014a74`
- end: `0x180014b2c`
- name: `?PutLastPage@AccessibilityCplCore@@IEAAXPEBG@Z`
- size: `184`
- prototype: `void(AccessibilityCplCore *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x18000466c`
- `0x180014a74`
- `0x18002e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180014aee`
- `OLEAUT32!__imp_SysAllocString` at `0x180014aee`
- `OLEAUT32!__imp_VariantClear` at `0x180014ae1`
- `OLEAUT32!__imp_VariantClear` at `0x180014ae1`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180014aa7`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180014aa7`
- `PROPSYS!PSPropertyBag_ReadType` at `0x180014ad3`
- `PROPSYS!PSPropertyBag_ReadType` at `0x180014ad3`

## string_xrefs

- `0x180014abb`: `AccessibilityLastPage`
- `0x180014b00`: `AccessibilityLastPage`

## pseudocode

```c
void __fastcall AccessibilityCplCore::PutLastPage(AccessibilityCplCore *this, const unsigned __int16 *a2)
{
  IUnknown *v2; // rcx
  VARIANT var; // [rsp+20h] [rbp-20h] BYREF
  void *ppvOut; // [rsp+50h] [rbp+10h] BYREF

  v2 = (IUnknown *)*((_QWORD *)this + 2);
  ppvOut = 0;
  if ( IUnknown_QueryService(
         v2,
         &GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1,
         &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
         &ppvOut) >= 0 )
  {
    memset(&var, 0, sizeof(var));
    if ( PSPropertyBag_ReadType((IPropertyBag *)ppvOut, L"AccessibilityLastPage", &var, 8u) >= 0 )
      VariantClear(&var);
    var.vt = 8;
    var.llVal = (LONGLONG)SysAllocString(a2);
    (*(void (__fastcall **)(void *, const WCHAR *, VARIANT *))(*(_QWORD *)ppvOut + 32LL))(
      ppvOut,
      L"AccessibilityLastPage",
      &var);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvOut);
}

```

## disassembly

```asm
0x180014a74  mov     [rsp-8+arg_8], rbx
0x180014a79  mov     [rsp-8+arg_10], rdi
0x180014a7e  push    rbp
0x180014a7f  mov     rbp, rsp
0x180014a82  sub     rsp, 40h
0x180014a86  mov     rcx, [rcx+10h]; punk
0x180014a8a  lea     r9, [rbp+ppvOut]; ppvOut
0x180014a8e  mov     rbx, rdx
0x180014a91  mov     [rbp+ppvOut], 0
0x180014a99  lea     rdx, _GUID_a3b24a0a_7b68_448d_9979_c700059c3ad1; guidService
0x180014aa0  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x180014aa7  call    cs:__imp_IUnknown_QueryService
0x180014aad  test    eax, eax
0x180014aaf  js      short loc_180014B13
0x180014ab1  mov     rcx, [rbp+ppvOut]; propBag
0x180014ab5  lea     r8, [rbp+var]; var
0x180014ab9  xor     eax, eax
0x180014abb  lea     rdx, aAccessibilityl; "AccessibilityLastPage"
0x180014ac2  xorps   xmm0, xmm0
0x180014ac5  mov     qword ptr [rbp+var+10h], rax
0x180014ac9  movups  xmmword ptr [rbp+var], xmm0
0x180014acd  lea     edi, [rax+8]
0x180014ad0  mov     r9d, edi; type
0x180014ad3  call    cs:__imp_PSPropertyBag_ReadType
0x180014ad9  test    eax, eax
0x180014adb  js      short loc_180014AE7
0x180014add  lea     rcx, [rbp+var]; pvarg
0x180014ae1  call    cs:__imp_VariantClear
0x180014ae7  mov     rcx, rbx; psz
0x180014aea  mov     word ptr [rbp+var], di
0x180014aee  call    cs:__imp_SysAllocString
0x180014af4  mov     rcx, [rbp+ppvOut]
0x180014af8  lea     r8, [rbp+var]
0x180014afc  mov     qword ptr [rbp+var+8], rax
0x180014b00  lea     rdx, aAccessibilityl; "AccessibilityLastPage"
0x180014b07  mov     rax, [rcx]
0x180014b0a  mov     rax, [rax+20h]
0x180014b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b13  lea     rcx, [rbp+ppvOut]
0x180014b17  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180014b1c  mov     rbx, [rsp+40h+arg_8]
0x180014b21  mov     rdi, [rsp+40h+arg_10]
0x180014b26  add     rsp, 40h
0x180014b2a  pop     rbp
0x180014b2b  retn
```
