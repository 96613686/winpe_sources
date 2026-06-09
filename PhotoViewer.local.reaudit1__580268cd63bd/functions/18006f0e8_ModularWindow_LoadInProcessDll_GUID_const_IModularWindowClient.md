# ModularWindow::LoadInProcessDll(_GUID const &,IModularWindowClient *)

- ea: `0x18006f0e8`
- end: `0x18006f1bf`
- name: `?LoadInProcessDll@ModularWindow@@YAXAEBU_GUID@@PEAUIModularWindowClient@@@Z`
- size: `215`
- prototype: `void __fastcall(IID *rclsid, const struct _GUID *, struct IModularWindowClient *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180046df0`

## callees

- `0x18000cb74`
- `0x18006f0e8`
- `0x18006f670`
- `0x180080010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18006f17c`
- `ole32!CoCreateInstance` at `0x18006f17c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f102`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f136`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f152`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f188`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f102`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f136`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f152`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f188`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ModularWindow::LoadInProcessDll(IID *rclsid, const struct _GUID *a2, struct IModularWindowClient *a3)
{
  int v5; // eax
  int v6; // edx
  int v7; // eax
  int v8; // edx
  HRESULT Instance; // eax
  int v10; // edx
  struct IDataObject *v11; // r8
  unsigned int v12; // r9d
  struct IDropTarget *v13; // [rsp+48h] [rbp+10h] BYREF
  ModularWindow *ppv; // [rsp+50h] [rbp+18h] BYREF

  if ( !a2 )
  {
    Base::Throw((Base *)0x80070057LL, 0);
    __debugbreak();
  }
  v13 = 0;
  LOBYTE(a3) = 1;
  v5 = (*(__int64 (__fastcall **)(const struct _GUID *, struct IDropTarget **, struct IModularWindowClient *))(*(_QWORD *)&a2->Data1 + 104LL))(
         a2,
         &v13,
         a3);
  if ( v5 != -2147287038 )
  {
    if ( v5 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v5, v6);
      __debugbreak();
    }
    v7 = (*(__int64 (__fastcall **)(const struct _GUID *))(*(_QWORD *)&a2->Data1 + 112LL))(a2);
    if ( v7 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v7, v8);
      __debugbreak();
    }
    ppv = 0;
    Instance = CoCreateInstance(rclsid, 0, 1u, &IID_IDropTarget, (LPVOID *)&ppv);
    if ( Instance < 0 )
    {
      Base::Throw((Base *)(unsigned int)Instance, v10);
      __debugbreak();
    }
    ModularWindow::SimulateDrop(ppv, v13, v11, v12);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
  }
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v13);
}

```

## disassembly

```asm
0x18006f0e8  mov     [rsp+arg_0], rbx
0x18006f0ed  push    rdi
0x18006f0ee  sub     rsp, 30h
0x18006f0f2  mov     rbx, rdx
0x18006f0f5  mov     rdi, rcx
0x18006f0f8  test    rdx, rdx
0x18006f0fb  jnz     short loc_18006F109
0x18006f0fd  mov     ecx, 80070057h
0x18006f102  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f108  int     3; Trap to Debugger
0x18006f109  mov     [rsp+38h+arg_8], 0
0x18006f112  mov     rax, [rdx]
0x18006f115  mov     r8b, 1
0x18006f118  lea     rdx, [rsp+38h+arg_8]
0x18006f11d  mov     rcx, rbx
0x18006f120  mov     rax, [rax+68h]
0x18006f124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f129  cmp     eax, 80030002h
0x18006f12e  jz      short loc_18006F1AA
0x18006f130  test    eax, eax
0x18006f132  jns     short loc_18006F13D
0x18006f134  mov     ecx, eax
0x18006f136  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f13c  int     3; Trap to Debugger
0x18006f13d  mov     rax, [rbx]
0x18006f140  mov     rcx, rbx
0x18006f143  mov     rax, [rax+70h]
0x18006f147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f14c  test    eax, eax
0x18006f14e  jns     short loc_18006F159
0x18006f150  mov     ecx, eax
0x18006f152  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f158  int     3; Trap to Debugger
0x18006f159  mov     [rsp+38h+arg_10], 0
0x18006f162  lea     rax, [rsp+38h+arg_10]
0x18006f167  mov     [rsp+38h+ppv], rax; ppv
0x18006f16c  lea     r9, IID_IDropTarget; riid
0x18006f173  xor     edx, edx; pUnkOuter
0x18006f175  lea     r8d, [rdx+1]; dwClsContext
0x18006f179  mov     rcx, rdi; rclsid
0x18006f17c  call    cs:__imp_CoCreateInstance
0x18006f182  test    eax, eax
0x18006f184  jns     short loc_18006F18F
0x18006f186  mov     ecx, eax
0x18006f188  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f18e  int     3; Trap to Debugger
0x18006f18f  mov     rdx, [rsp+38h+arg_8]; struct IDropTarget *
0x18006f194  mov     rcx, [rsp+38h+arg_10]; this
0x18006f199  call    ?SimulateDrop@ModularWindow@@YAXPEAUIDropTarget@@PEAUIDataObject@@K@Z; ModularWindow::SimulateDrop(IDropTarget *,IDataObject *,ulong)
0x18006f19e  nop
0x18006f19f  lea     rcx, [rsp+38h+arg_10]
0x18006f1a4  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f1a9  nop
0x18006f1aa  lea     rcx, [rsp+38h+arg_8]
0x18006f1af  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f1b4  mov     rbx, [rsp+38h+arg_0]
0x18006f1b9  add     rsp, 30h
0x18006f1bd  pop     rdi
0x18006f1be  retn
```
