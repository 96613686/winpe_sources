# ModularWindow::OrderPrintSelectionOnline(IModularWindowClient *,bool)

- ea: `0x18006f1c8`
- end: `0x18006f32a`
- name: `?OrderPrintSelectionOnline@ModularWindow@@YAXPEAUIModularWindowClient@@_N@Z`
- size: `354`
- prototype: `void __fastcall(ModularWindow *__hidden this, struct IModularWindowClient *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046df0`

## callees

- `0x18000cb74`
- `0x18006f1c8`
- `0x18006f670`
- `0x180080010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18006f242`
- `ole32!CoCreateInstance` at `0x18006f242`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f1e3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f216`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f24e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f294`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f2d5`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f2fa`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f1e3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f216`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f24e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f294`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f2d5`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f2fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ModularWindow::OrderPrintSelectionOnline(
        ModularWindow *this,
        struct IModularWindowClient *a2,
        __int64 a3)
{
  char v3; // di
  int v5; // eax
  char v6; // dl
  HRESULT Instance; // eax
  char v8; // dl
  __int64 v9; // rcx
  int v10; // eax
  char v11; // dl
  int v12; // eax
  char v13; // dl
  struct IDataObject *v14; // r8
  unsigned int v15; // r9d
  __int128 v16; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h]
  ModularWindow *ppv; // [rsp+70h] [rbp+20h] BYREF
  struct IDropTarget *v19; // [rsp+80h] [rbp+30h] BYREF
  __int64 v20; // [rsp+88h] [rbp+38h] BYREF

  v3 = (char)a2;
  if ( !this )
  {
    Base::Throw((Base *)0x80070057LL, (_BYTE)a2);
    __debugbreak();
  }
  v19 = 0;
  LOBYTE(a3) = 1;
  v5 = (*(__int64 (__fastcall **)(ModularWindow *, struct IDropTarget **, __int64))(*(_QWORD *)this + 104LL))(
         this,
         &v19,
         a3);
  if ( v5 != -2147287038 )
  {
    if ( v5 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v5, v6);
      __debugbreak();
    }
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_PublishDropTarget,
                 0,
                 1u,
                 &GUID_00000122_0000_0000_c000_000000000046,
                 (LPVOID *)&ppv);
    if ( Instance < 0 )
    {
      Base::Throw((Base *)(unsigned int)Instance, v8);
      __debugbreak();
    }
    if ( v3 )
    {
      v9 = 0;
      v20 = 0;
      if ( ppv )
      {
        (**(void (__fastcall ***)(ModularWindow *, GUID *, __int64 *))ppv)(
          ppv,
          &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
          &v20);
        v9 = v20;
      }
      if ( !v9 )
      {
        Base::Throw((Base *)0x80004002LL, v8);
        __debugbreak();
      }
      v16 = 0;
      v17 = 0;
      LOWORD(v16) = 11;
      WORD4(v16) = -1;
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)v9 + 32LL))(
              v9,
              L"UseMRU",
              &v16);
      if ( v10 < 0 )
        Base::Throw((Base *)(unsigned int)v10, v11);
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v20);
    }
    v12 = (*(__int64 (__fastcall **)(ModularWindow *))(*(_QWORD *)this + 112LL))(this);
    if ( v12 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v12, v13);
      __debugbreak();
    }
    ModularWindow::SimulateDrop(ppv, v19, v14, v15);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
  }
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v19);
}

```

## disassembly

```asm
0x18006f1c8  push    rbp
0x18006f1ca  push    rbx
0x18006f1cb  push    rdi
0x18006f1cc  mov     rbp, rsp
0x18006f1cf  sub     rsp, 50h
0x18006f1d3  mov     dil, dl
0x18006f1d6  mov     rbx, rcx
0x18006f1d9  test    rcx, rcx
0x18006f1dc  jnz     short loc_18006F1EA
0x18006f1de  mov     ecx, 80070057h
0x18006f1e3  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f1e9  int     3; Trap to Debugger
0x18006f1ea  mov     [rbp+arg_10], 0
0x18006f1f2  mov     rax, [rcx]
0x18006f1f5  mov     r8b, 1
0x18006f1f8  lea     rdx, [rbp+arg_10]
0x18006f1fc  mov     rax, [rax+68h]
0x18006f200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f205  cmp     eax, 80030002h
0x18006f20a  jz      loc_18006F319
0x18006f210  test    eax, eax
0x18006f212  jns     short loc_18006F21D
0x18006f214  mov     ecx, eax
0x18006f216  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f21c  int     3; Trap to Debugger
0x18006f21d  mov     [rbp+arg_0], 0
0x18006f225  lea     rax, [rbp+arg_0]
0x18006f229  mov     [rsp+50h+ppv], rax; ppv
0x18006f22e  lea     r9, _GUID_00000122_0000_0000_c000_000000000046; riid
0x18006f235  xor     edx, edx; pUnkOuter
0x18006f237  lea     r8d, [rdx+1]; dwClsContext
0x18006f23b  lea     rcx, CLSID_PublishDropTarget; rclsid
0x18006f242  call    cs:__imp_CoCreateInstance
0x18006f248  test    eax, eax
0x18006f24a  jns     short loc_18006F255
0x18006f24c  mov     ecx, eax
0x18006f24e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f254  int     3; Trap to Debugger
0x18006f255  test    dil, dil
0x18006f258  jz      loc_18006F2E5
0x18006f25e  mov     r9, [rbp+arg_0]
0x18006f262  xor     ecx, ecx
0x18006f264  mov     [rbp+arg_18], rcx
0x18006f268  test    r9, r9
0x18006f26b  jz      short loc_18006F28A
0x18006f26d  mov     rax, [r9]
0x18006f270  lea     r8, [rbp+arg_18]
0x18006f274  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18006f27b  mov     rcx, r9
0x18006f27e  mov     rax, [rax]
0x18006f281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f286  mov     rcx, [rbp+arg_18]
0x18006f28a  test    rcx, rcx
0x18006f28d  jnz     short loc_18006F29B
0x18006f28f  mov     ecx, 80004002h
0x18006f294  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f29a  int     3; Trap to Debugger
0x18006f29b  xorps   xmm0, xmm0
0x18006f29e  xor     eax, eax
0x18006f2a0  movups  [rbp+var_20], xmm0
0x18006f2a4  mov     [rbp+var_10], rax
0x18006f2a8  mov     eax, 0Bh
0x18006f2ad  mov     word ptr [rbp+var_20], ax
0x18006f2b1  or      eax, 0FFFFFFFFh
0x18006f2b4  mov     word ptr [rbp+var_20+8], ax
0x18006f2b8  mov     rax, [rcx]
0x18006f2bb  lea     r8, [rbp+var_20]
0x18006f2bf  lea     rdx, aUsemru; "UseMRU"
0x18006f2c6  mov     rax, [rax+20h]
0x18006f2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f2cf  test    eax, eax
0x18006f2d1  jns     short loc_18006F2DC
0x18006f2d3  mov     ecx, eax
0x18006f2d5  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f2db  nop
0x18006f2dc  lea     rcx, [rbp+arg_18]
0x18006f2e0  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f2e5  mov     rax, [rbx]
0x18006f2e8  mov     rcx, rbx
0x18006f2eb  mov     rax, [rax+70h]
0x18006f2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f2f4  test    eax, eax
0x18006f2f6  jns     short loc_18006F301
0x18006f2f8  mov     ecx, eax
0x18006f2fa  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f300  int     3; Trap to Debugger
0x18006f301  mov     rdx, [rbp+arg_10]; struct IDropTarget *
0x18006f305  mov     rcx, [rbp+arg_0]; this
0x18006f309  call    ?SimulateDrop@ModularWindow@@YAXPEAUIDropTarget@@PEAUIDataObject@@K@Z; ModularWindow::SimulateDrop(IDropTarget *,IDataObject *,ulong)
0x18006f30e  nop
0x18006f30f  lea     rcx, [rbp+arg_0]
0x18006f313  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f318  nop
0x18006f319  lea     rcx, [rbp+arg_10]
0x18006f31d  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f322  add     rsp, 50h
0x18006f326  pop     rdi
0x18006f327  pop     rbx
0x18006f328  pop     rbp
0x18006f329  retn
```
