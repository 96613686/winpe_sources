# ShellEasel::GetCurrentSelection(Base::Path *)

- ea: `0x18002ef10`
- end: `0x18002efe3`
- name: `?GetCurrentSelection@ShellEasel@@AEAAXPEAVPath@Base@@@Z`
- size: `211`
- prototype: `void __fastcall(ShellEasel *__hidden this, struct Path *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002df38`

## callees

- `0x180004e88`
- `0x18000cb74`
- `0x18002ef10`
- `0x180080010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002efb7`
- `ole32!CoTaskMemFree` at `0x18002efb7`
- `SHELL32!SHGetItemFromDataObject` at `0x18002ef65`
- `SHELL32!SHGetItemFromDataObject` at `0x18002ef65`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ef45`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ef71`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ef9f`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ef45`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ef71`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002ef9f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ShellEasel::GetCurrentSelection(ShellEasel *this, struct Path *a2)
{
  int v3; // eax
  int v4; // edx
  HRESULT v5; // eax
  int v6; // edx
  int v7; // eax
  int v8; // edx
  LPVOID pv; // [rsp+30h] [rbp+10h] BYREF
  void *ppv; // [rsp+40h] [rbp+20h] BYREF
  IDataObject *pdtobj; // [rsp+48h] [rbp+28h] BYREF

  pdtobj = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, IDataObject **, _QWORD))(**((_QWORD **)this + 15) + 104LL))(
         *((_QWORD *)this + 15),
         &pdtobj,
         0);
  if ( v3 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v3, v4);
    __debugbreak();
  }
  ppv = 0;
  v5 = SHGetItemFromDataObject(pdtobj, DOGIF_DEFAULT, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  if ( v5 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v5, v6);
    __debugbreak();
  }
  pv = 0;
  v7 = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)ppv + 40LL))(ppv, 2147844096LL, &pv);
  if ( v7 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v7, v8);
    __debugbreak();
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, pv);
  CoTaskMemFree(pv);
  pv = 0;
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&pdtobj);
}

```

## disassembly

```asm
0x18002ef10  mov     [rsp-8+arg_8], rbx
0x18002ef15  push    rbp
0x18002ef16  mov     rbp, rsp
0x18002ef19  sub     rsp, 20h
0x18002ef1d  mov     rbx, rdx
0x18002ef20  mov     [rbp+pdtobj], 0
0x18002ef28  mov     rcx, [rcx+78h]
0x18002ef2c  mov     rax, [rcx]
0x18002ef2f  xor     r8d, r8d
0x18002ef32  lea     rdx, [rbp+pdtobj]
0x18002ef36  mov     rax, [rax+68h]
0x18002ef3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef3f  test    eax, eax
0x18002ef41  jns     short loc_18002EF4C
0x18002ef43  mov     ecx, eax
0x18002ef45  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002ef4b  int     3; Trap to Debugger
0x18002ef4c  mov     [rbp+ppv], 0
0x18002ef54  lea     r9, [rbp+ppv]; ppv
0x18002ef58  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002ef5f  xor     edx, edx; dwFlags
0x18002ef61  mov     rcx, [rbp+pdtobj]; pdtobj
0x18002ef65  call    cs:__imp_SHGetItemFromDataObject
0x18002ef6b  test    eax, eax
0x18002ef6d  jns     short loc_18002EF78
0x18002ef6f  mov     ecx, eax
0x18002ef71  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002ef77  int     3; Trap to Debugger
0x18002ef78  mov     [rbp+pv], 0
0x18002ef80  mov     rcx, [rbp+ppv]
0x18002ef84  mov     rax, [rcx]
0x18002ef87  lea     r8, [rbp+pv]
0x18002ef8b  mov     edx, 80058000h
0x18002ef90  mov     rax, [rax+28h]
0x18002ef94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef99  test    eax, eax
0x18002ef9b  jns     short loc_18002EFA6
0x18002ef9d  mov     ecx, eax
0x18002ef9f  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002efa5  int     3; Trap to Debugger
0x18002efa6  mov     rdx, [rbp+pv]
0x18002efaa  mov     rcx, rbx
0x18002efad  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002efb2  nop
0x18002efb3  mov     rcx, [rbp+pv]; pv
0x18002efb7  call    cs:__imp_CoTaskMemFree
0x18002efbd  mov     [rbp+pv], 0
0x18002efc5  lea     rcx, [rbp+ppv]
0x18002efc9  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002efce  nop
0x18002efcf  lea     rcx, [rbp+pdtobj]
0x18002efd3  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002efd8  mov     rbx, [rsp+20h+arg_8]
0x18002efdd  add     rsp, 20h
0x18002efe1  pop     rbp
0x18002efe2  retn
```
