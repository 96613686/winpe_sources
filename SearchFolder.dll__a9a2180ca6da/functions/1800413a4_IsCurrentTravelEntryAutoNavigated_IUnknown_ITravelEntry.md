# IsCurrentTravelEntryAutoNavigated(IUnknown *,ITravelEntry * *)

- ea: `0x1800413a4`
- end: `0x18004148d`
- name: `?IsCurrentTravelEntryAutoNavigated@@YAHPEAUIUnknown@@PEAPEAUITravelEntry@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct IUnknown *, struct ITravelEntry **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003dc40`

## callees

- `0x18003e764`
- `0x1800413a4`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800413ce`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x1800413ce`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18004144f`
- `PROPSYS!PSPropertyBag_ReadBOOL` at `0x18004144f`

## pseudocode

```c
__int64 __fastcall IsCurrentTravelEntryAutoNavigated(struct IUnknown *a1, struct ITravelEntry **a2)
{
  unsigned int v2; // ebx
  int (__fastcall ***v4)(_QWORD, GUID *, IPropertyBag **); // [rsp+30h] [rbp-10h] BYREF
  __int64 v5; // [rsp+38h] [rbp-8h] BYREF
  struct ITravelEntry **value; // [rsp+58h] [rbp+18h] BYREF
  void *ppvOut; // [rsp+60h] [rbp+20h] BYREF
  IPropertyBag *propBag; // [rsp+68h] [rbp+28h] BYREF

  value = a2;
  v2 = 0;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         a1,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_dfbc7e30_f9e5_455f_88f8_fa98c1e494ca,
         &ppvOut) >= 0 )
  {
    v5 = 0;
    if ( (*(int (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvOut + 32LL))(ppvOut, &v5) >= 0 )
    {
      v4 = 0;
      if ( (*(int (__fastcall **)(__int64, void *, _QWORD, int (__fastcall ****)(_QWORD, GUID *, IPropertyBag **)))(*(_QWORD *)v5 + 56LL))(
             v5,
             ppvOut,
             0,
             &v4) >= 0 )
      {
        propBag = 0;
        if ( (**v4)(v4, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, &propBag) >= 0 )
        {
          LODWORD(value) = 0;
          if ( PSPropertyBag_ReadBOOL(propBag, L"AutoNavigated", (BOOL *)&value) >= 0 )
            v2 = (unsigned int)value;
        }
        ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>((__int64 *)&propBag);
      }
      ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>((__int64 *)&v4);
    }
    ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>(&v5);
  }
  ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>((__int64 *)&ppvOut);
  return v2;
}

```

## disassembly

```asm
0x1800413a4  mov     [rsp-8+arg_0], rbx
0x1800413a9  mov     [rsp-8+value], rdx
0x1800413ae  push    rbp
0x1800413af  mov     rbp, rsp
0x1800413b2  sub     rsp, 40h
0x1800413b6  xor     ebx, ebx
0x1800413b8  lea     r9, [rbp+ppvOut]; ppvOut
0x1800413bc  lea     r8, _GUID_dfbc7e30_f9e5_455f_88f8_fa98c1e494ca; riid
0x1800413c3  mov     [rbp+ppvOut], rbx
0x1800413c7  lea     rdx, SID_STopLevelBrowser; guidService
0x1800413ce  call    cs:__imp_IUnknown_QueryService
0x1800413d4  test    eax, eax
0x1800413d6  js      loc_180041477
0x1800413dc  mov     rcx, [rbp+ppvOut]
0x1800413e0  lea     rdx, [rbp+var_8]
0x1800413e4  mov     [rbp+var_8], rbx
0x1800413e8  mov     rax, [rcx]
0x1800413eb  mov     rax, [rax+20h]
0x1800413ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413f4  test    eax, eax
0x1800413f6  js      short loc_18004146E
0x1800413f8  mov     rcx, [rbp+var_8]
0x1800413fc  lea     r9, [rbp+var_10]
0x180041400  mov     rdx, [rbp+ppvOut]
0x180041404  xor     r8d, r8d
0x180041407  mov     [rbp+var_10], rbx
0x18004140b  mov     rax, [rcx]
0x18004140e  mov     rax, [rax+38h]
0x180041412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041417  test    eax, eax
0x180041419  js      short loc_180041465
0x18004141b  mov     rcx, [rbp+var_10]
0x18004141f  lea     r8, [rbp+propBag]
0x180041423  mov     [rbp+propBag], rbx
0x180041427  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18004142e  mov     rax, [rcx]
0x180041431  mov     rax, [rax]
0x180041434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041439  test    eax, eax
0x18004143b  js      short loc_18004145C
0x18004143d  mov     rcx, [rbp+propBag]; propBag
0x180041441  lea     r8, [rbp+value]; value
0x180041445  lea     rdx, aAutonavigated; "AutoNavigated"
0x18004144c  mov     dword ptr [rbp+value], ebx
0x18004144f  call    cs:__imp_PSPropertyBag_ReadBOOL
0x180041455  test    eax, eax
0x180041457  js      short loc_18004145C
0x180041459  mov     ebx, dword ptr [rbp+value]
0x18004145c  lea     rcx, [rbp+propBag]
0x180041460  call    ??1?$CComPtrBase@UIInfoBarHost@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>(void)
0x180041465  lea     rcx, [rbp+var_10]
0x180041469  call    ??1?$CComPtrBase@UIInfoBarHost@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>(void)
0x18004146e  lea     rcx, [rbp+var_8]
0x180041472  call    ??1?$CComPtrBase@UIInfoBarHost@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>(void)
0x180041477  lea     rcx, [rbp+ppvOut]
0x18004147b  call    ??1?$CComPtrBase@UIInfoBarHost@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IInfoBarHost>::~CComPtrBase<IInfoBarHost>(void)
0x180041480  mov     eax, ebx
0x180041482  mov     rbx, [rsp+40h+arg_0]
0x180041487  add     rsp, 40h
0x18004148b  pop     rbp
0x18004148c  retn
```
