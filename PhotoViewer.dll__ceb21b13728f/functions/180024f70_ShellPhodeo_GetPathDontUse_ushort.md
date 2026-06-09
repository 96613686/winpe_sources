# ShellPhodeo::GetPathDontUse(ushort * *)

- ea: `0x180024f70`
- end: `0x18002514e`
- name: `?GetPathDontUse@ShellPhodeo@@IEAAJPEAPEAG@Z`
- size: `478`
- prototype: `__int64 __fastcall(ShellPhodeo *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180047ad0`

## callees

- `0x18000cb74`
- `0x180024f70`
- `0x180080010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800250fd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800250fd`
- `ole32!CoTaskMemFree` at `0x180025021`
- `ole32!CoTaskMemFree` at `0x180025060`
- `ole32!CoTaskMemFree` at `0x1800250d9`
- `ole32!CoTaskMemFree` at `0x18002510a`
- `ole32!CoTaskMemFree` at `0x180025021`
- `ole32!CoTaskMemFree` at `0x180025060`
- `ole32!CoTaskMemFree` at `0x1800250d9`
- `ole32!CoTaskMemFree` at `0x18002510a`
- `SHELL32!SHCreateItemFromIDList` at `0x18002504d`
- `SHELL32!SHCreateItemFromIDList` at `0x18002504d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellPhodeo::GetPathDontUse(ShellPhodeo *this, unsigned __int16 **a2)
{
  HRESULT v4; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, void **); // rbx
  void *v6; // rcx
  __int64 v7; // [rsp+30h] [rbp-10h] BYREF
  __int64 (__fastcall ***v8)(_QWORD, GUID *, void **); // [rsp+38h] [rbp-8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+20h] BYREF
  OLECHAR *psz; // [rsp+70h] [rbp+30h] BYREF
  void *ppv; // [rsp+78h] [rbp+38h] BYREF

  if ( *((_DWORD *)this + 13) != 1 )
    return 2147500037LL;
  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD *))(**((_QWORD **)this + 13) + 24LL))(
         *((_QWORD *)this + 13),
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v8);
  if ( v4 < 0 )
    goto LABEL_17;
  v5 = v8;
  ppv = 0;
  v7 = 0;
  if ( ((int (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, void **), _QWORD, const GUID *, GUID *, __int64 *))(*v8)[3])(
         v8,
         0,
         &BHID_SFUIObject,
         &GUID_000214f9_0000_0000_c000_000000000046,
         &v7) < 0 )
  {
    v4 = (**v5)(v5, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  else
  {
    pv = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v7 + 32LL))(v7, &pv);
    v6 = pv;
    if ( v4 < 0 )
    {
      CoTaskMemFree(pv);
      pv = 0;
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v7);
LABEL_16:
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
LABEL_17:
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v8);
      return (unsigned int)v4;
    }
    if ( pv )
    {
      v4 = SHCreateItemFromIDList((LPCITEMIDLIST)pv, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      v6 = pv;
    }
    else
    {
      v4 = -2147467259;
    }
    CoTaskMemFree(v6);
    pv = 0;
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v7);
  }
  if ( v4 < 0 )
    goto LABEL_16;
  psz = 0;
  v4 = (*(__int64 (__fastcall **)(void *, __int64, OLECHAR **))(*(_QWORD *)ppv + 40LL))(ppv, 2147844096LL, &psz);
  if ( v4 < 0 )
  {
    CoTaskMemFree(psz);
    psz = 0;
    goto LABEL_16;
  }
  *a2 = SysAllocString(psz);
  CoTaskMemFree(psz);
  psz = 0;
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, void **)))(*v8)[2])(v8);
  return 0;
}

```

## disassembly

```asm
0x180024f70  push    rbp
0x180024f72  push    rbx
0x180024f73  push    rdi
0x180024f74  mov     rbp, rsp
0x180024f77  sub     rsp, 40h
0x180024f7b  mov     rdi, rdx
0x180024f7e  cmp     dword ptr [rcx+34h], 1
0x180024f82  jz      short loc_180024F8E
0x180024f84  mov     eax, 80004005h
0x180024f89  jmp     loc_180025146
0x180024f8e  mov     [rbp+var_8], 0
0x180024f96  mov     rcx, [rcx+68h]
0x180024f9a  mov     rax, [rcx]
0x180024f9d  lea     r8, [rbp+var_8]
0x180024fa1  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180024fa8  mov     rax, [rax+18h]
0x180024fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fb1  mov     ebx, eax
0x180024fb3  test    eax, eax
0x180024fb5  js      loc_1800250F0
0x180024fbb  mov     rbx, [rbp+var_8]
0x180024fbf  mov     [rbp+ppv], 0
0x180024fc7  mov     [rbp+var_10], 0
0x180024fcf  mov     rax, [rbx]
0x180024fd2  lea     rcx, [rbp+var_10]
0x180024fd6  mov     [rsp+40h+var_20], rcx
0x180024fdb  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x180024fe2  lea     r8, BHID_SFUIObject
0x180024fe9  xor     edx, edx
0x180024feb  mov     rcx, rbx
0x180024fee  mov     rax, [rax+18h]
0x180024ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ff7  test    eax, eax
0x180024ff9  js      short loc_180025079
0x180024ffb  mov     [rbp+pv], 0
0x180025003  mov     rcx, [rbp+var_10]
0x180025007  mov     rax, [rcx]
0x18002500a  lea     rdx, [rbp+pv]
0x18002500e  mov     rax, [rax+20h]
0x180025012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025017  mov     ebx, eax
0x180025019  mov     rcx, [rbp+pv]; pv
0x18002501d  test    eax, eax
0x18002501f  jns     short loc_18002503D
0x180025021  call    cs:__imp_CoTaskMemFree
0x180025027  mov     [rbp+pv], 0
0x18002502f  lea     rcx, [rbp+var_10]
0x180025033  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180025038  jmp     loc_1800250E7
0x18002503d  test    rcx, rcx
0x180025040  jz      short loc_18002505B
0x180025042  lea     r8, [rbp+ppv]; ppv
0x180025046  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002504d  call    cs:__imp_SHCreateItemFromIDList
0x180025053  mov     ebx, eax
0x180025055  mov     rcx, [rbp+pv]
0x180025059  jmp     short loc_180025060
0x18002505b  mov     ebx, 80004005h
0x180025060  call    cs:__imp_CoTaskMemFree
0x180025066  mov     [rbp+pv], 0
0x18002506e  lea     rcx, [rbp+var_10]
0x180025072  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180025077  jmp     short loc_1800250AA
0x180025079  mov     rax, [rbx]
0x18002507c  lea     r8, [rbp+ppv]
0x180025080  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180025087  mov     rcx, rbx
0x18002508a  mov     rax, [rax]
0x18002508d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025092  mov     ebx, eax
0x180025094  mov     rcx, [rbp+var_10]
0x180025098  test    rcx, rcx
0x18002509b  jz      short loc_1800250AA
0x18002509d  mov     rax, [rcx]
0x1800250a0  mov     rax, [rax+10h]
0x1800250a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250a9  nop
0x1800250aa  test    ebx, ebx
0x1800250ac  js      short loc_1800250E7
0x1800250ae  mov     [rbp+psz], 0
0x1800250b6  mov     rcx, [rbp+ppv]
0x1800250ba  mov     rax, [rcx]
0x1800250bd  lea     r8, [rbp+psz]
0x1800250c1  mov     edx, 80058000h
0x1800250c6  mov     rax, [rax+28h]
0x1800250ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250cf  mov     ebx, eax
0x1800250d1  mov     rcx, [rbp+psz]; psz
0x1800250d5  test    eax, eax
0x1800250d7  jns     short loc_1800250FD
0x1800250d9  call    cs:__imp_CoTaskMemFree
0x1800250df  mov     [rbp+psz], 0
0x1800250e7  lea     rcx, [rbp+ppv]
0x1800250eb  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x1800250f0  lea     rcx, [rbp+var_8]
0x1800250f4  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x1800250f9  mov     eax, ebx
0x1800250fb  jmp     short loc_180025146
0x1800250fd  call    cs:__imp_SysAllocString
0x180025103  mov     [rdi], rax
0x180025106  mov     rcx, [rbp+psz]; pv
0x18002510a  call    cs:__imp_CoTaskMemFree
0x180025110  mov     [rbp+psz], 0
0x180025118  mov     rcx, [rbp+ppv]
0x18002511c  test    rcx, rcx
0x18002511f  jz      short loc_18002512E
0x180025121  mov     rax, [rcx]
0x180025124  mov     rax, [rax+10h]
0x180025128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002512d  nop
0x18002512e  mov     rcx, [rbp+var_8]
0x180025132  test    rcx, rcx
0x180025135  jz      short loc_180025144
0x180025137  mov     rax, [rcx]
0x18002513a  mov     rax, [rax+10h]
0x18002513e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025143  nop
0x180025144  xor     eax, eax
0x180025146  add     rsp, 40h
0x18002514a  pop     rdi
0x18002514b  pop     rbx
0x18002514c  pop     rbp
0x18002514d  retn
```
