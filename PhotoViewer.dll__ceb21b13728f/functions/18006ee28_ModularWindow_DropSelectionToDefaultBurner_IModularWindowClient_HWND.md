# ModularWindow::DropSelectionToDefaultBurner(IModularWindowClient *,HWND__ *)

- ea: `0x18006ee28`
- end: `0x18006f071`
- name: `?DropSelectionToDefaultBurner@ModularWindow@@YAXPEAUIModularWindowClient@@PEAUHWND__@@@Z`
- size: `585`
- prototype: `void(ModularWindow *__hidden this, struct IModularWindowClient *, HWND)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180046df0`

## callees

- `0x1800037d8`
- `0x180004908`
- `0x18000cb74`
- `0x18003f800`
- `0x18006ee28`
- `0x18006f078`
- `0x18006f670`
- `0x18007602c`
- `0x180080010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18006ef20`
- `ole32!CoCreateInstance` at `0x18006ef20`
- `SHELL32!SHBindToObject` at `0x18006efa8`
- `SHELL32!SHBindToObject` at `0x18006efa8`
- `SHELL32!SHParseDisplayName` at `0x18006ef72`
- `SHELL32!SHParseDisplayName` at `0x18006ef72`
- `SHELL32!__imp_ILFree` at `0x18006f04b`
- `SHELL32!__imp_ILFree` at `0x18006f04b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ee54`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006eef3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ef2c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ef54`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ef7e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006efb4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006efe9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f004`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ee54`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006eef3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ef2c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ef54`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006ef7e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006efb4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006efe9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18006f004`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ModularWindow::DropSelectionToDefaultBurner(
        ModularWindow *this,
        struct IModularWindowClient *a2,
        HWND a3)
{
  bool HaveDefaultBurner; // al
  __int64 v6; // r8
  const unsigned __int16 *v7; // rbx
  UIControls **v8; // rax
  const unsigned __int16 *v9; // r8
  int v10; // eax
  int v11; // edx
  HRESULT v12; // eax
  int v13; // edx
  int v14; // eax
  int v15; // edx
  HRESULT v16; // eax
  int v17; // edx
  HRESULT v18; // eax
  int v19; // edx
  int v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  struct IDataObject *v24; // r8
  unsigned int v25; // r9d
  LPVOID *ppv; // [rsp+20h] [rbp-68h]
  int v27; // [rsp+28h] [rbp-60h]
  struct IDropTarget *v28; // [rsp+30h] [rbp-58h] BYREF
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp-50h] BYREF
  ModularWindow *v30; // [rsp+40h] [rbp-48h] BYREF
  void *v31; // [rsp+48h] [rbp-40h] BYREF
  LPVOID v32; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v33[8]; // [rsp+58h] [rbp-30h] BYREF
  _BYTE v34[8]; // [rsp+60h] [rbp-28h] BYREF
  WCHAR pszName; // [rsp+68h] [rbp-20h] BYREF

  if ( !this )
  {
    Base::Throw((Base *)0x80070057LL, (_DWORD)a2);
    __debugbreak();
  }
  ppidl = 0;
  HaveDefaultBurner = ModularWindow::HaveDefaultBurner(this);
  try
  {
    if ( HaveDefaultBurner )
    {
      v28 = 0;
      LOBYTE(v6) = 1;
      v10 = (*(__int64 (__fastcall **)(ModularWindow *, struct IDropTarget **, __int64))(*(_QWORD *)this + 104LL))(
              this,
              &v28,
              v6);
      if ( v10 == -2147287038 )
      {
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v28);
      }
      else
      {
        if ( v10 < 0 )
          Base::Throw((Base *)(unsigned int)v10, v11);
        v32 = 0;
        v12 = CoCreateInstance(&CLSID_CDBurn, 0, 0x17u, &GUID_3d73a659_e5d0_4d42_afc0_5121ba425c8d, &v32);
        if ( v12 < 0 )
          Base::Throw((Base *)(unsigned int)v12, v13);
        v14 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64))(*(_QWORD *)v32 + 24LL))(v32, &pszName, 4);
        if ( v14 < 0 )
          Base::Throw((Base *)(unsigned int)v14, v15);
        v16 = SHParseDisplayName(&pszName, 0, &ppidl, 0, 0);
        if ( v16 < 0 )
          Base::Throw((Base *)(unsigned int)v16, v17);
        v31 = 0;
        v18 = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &v31);
        if ( v18 < 0 )
          Base::Throw((Base *)(unsigned int)v18, v19);
        v30 = 0;
        v20 = (*(__int64 (__fastcall **)(void *, struct IModularWindowClient *, GUID *, ModularWindow **))(*(_QWORD *)v31 + 64LL))(
                v31,
                a2,
                &GUID_00000122_0000_0000_c000_000000000046,
                &v30);
        if ( v20 < 0 )
          Base::Throw((Base *)(unsigned int)v20, v21);
        v22 = (*(__int64 (__fastcall **)(ModularWindow *))(*(_QWORD *)this + 112LL))(this);
        if ( v22 < 0 )
          Base::Throw((Base *)(unsigned int)v22, v23);
        ModularWindow::SimulateDrop(v30, v28, v24, v25);
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v30);
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v31);
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v32);
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v28);
        ILFree(ppidl);
      }
    }
    else
    {
      v7 = *(const unsigned __int16 **)Base::ResourceString::ResourceString((Base::ResourceString *)v34, 0x1B66u);
      v8 = (UIControls **)Base::ResourceString::ResourceString((Base::ResourceString *)v33, 0x1B65u);
      UIControls::TaskDialogBox(*v8, v7, v9, (const unsigned __int16 *)a2, (HWND)ppv, v27, (unsigned __int16 *)v28);
      Base::String::~String((Base::String *)v33);
      Base::String::~String((Base::String *)v34);
    }
  }
  catch ( Base::Exception )
  {
    ILFree(ppidl);
    throw;
  }
}

```

## disassembly

```asm
0x18006ee28  mov     [rsp+arg_10], rbx
0x18006ee2d  push    rdi
0x18006ee2e  sub     rsp, 80h
0x18006ee35  mov     rax, cs:__security_cookie
0x18006ee3c  xor     rax, rsp
0x18006ee3f  mov     [rsp+88h+var_18], rax
0x18006ee44  mov     rdi, rdx
0x18006ee47  mov     rbx, rcx
0x18006ee4a  test    rcx, rcx
0x18006ee4d  jnz     short loc_18006EE5B
0x18006ee4f  mov     ecx, 80070057h
0x18006ee54  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006ee5a  int     3; Trap to Debugger
0x18006ee5b  mov     [rsp+88h+ppidl], 0
0x18006ee64  call    ?HaveDefaultBurner@ModularWindow@@YA_NXZ; ModularWindow::HaveDefaultBurner(void)
0x18006ee69  test    al, al
0x18006ee6b  jnz     short loc_18006EEB7
0x18006ee6d  mov     edx, 1B66h; unsigned int
0x18006ee72  lea     rcx, [rsp+88h+var_28]; this
0x18006ee77  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x18006ee7c  nop
0x18006ee7d  mov     rbx, [rax]
0x18006ee80  mov     edx, 1B65h; unsigned int
0x18006ee85  lea     rcx, [rsp+88h+var_30]; this
0x18006ee8a  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x18006ee8f  mov     r9, rdi; unsigned __int16 *
0x18006ee92  mov     rdx, rbx; unsigned __int16 *
0x18006ee95  mov     rcx, [rax]; this
0x18006ee98  call    ?TaskDialogBox@UIControls@@YAHPEBG00PEAUHWND__@@HPEAG@Z; UIControls::TaskDialogBox(ushort const *,ushort const *,ushort const *,HWND__ *,int,ushort *)
0x18006ee9d  lea     rcx, [rsp+88h+var_30]; this
0x18006eea2  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18006eea7  nop
0x18006eea8  lea     rcx, [rsp+88h+var_28]; this
0x18006eead  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18006eeb2  jmp     loc_18006F052
0x18006eeb7  mov     [rsp+88h+var_58], 0
0x18006eec0  mov     rax, [rbx]
0x18006eec3  mov     r8b, 1
0x18006eec6  lea     rdx, [rsp+88h+var_58]
0x18006eecb  mov     rcx, rbx
0x18006eece  mov     rax, [rax+68h]
0x18006eed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eed7  cmp     eax, 80030002h
0x18006eedc  jnz     short loc_18006EEED
0x18006eede  lea     rcx, [rsp+88h+var_58]
0x18006eee3  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006eee8  jmp     loc_18006F052
0x18006eeed  test    eax, eax
0x18006eeef  jns     short loc_18006EEF9
0x18006eef1  mov     ecx, eax
0x18006eef3  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006eef9  mov     [rsp+88h+var_38], 0
0x18006ef02  lea     rax, [rsp+88h+var_38]
0x18006ef07  mov     [rsp+88h+ppv], rax; ppv
0x18006ef0c  lea     r9, _GUID_3d73a659_e5d0_4d42_afc0_5121ba425c8d; riid
0x18006ef13  xor     edx, edx; pUnkOuter
0x18006ef15  lea     r8d, [rdx+17h]; dwClsContext
0x18006ef19  lea     rcx, CLSID_CDBurn; rclsid
0x18006ef20  call    cs:__imp_CoCreateInstance
0x18006ef26  test    eax, eax
0x18006ef28  jns     short loc_18006EF32
0x18006ef2a  mov     ecx, eax
0x18006ef2c  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006ef32  mov     rcx, [rsp+88h+var_38]
0x18006ef37  mov     rax, [rcx]
0x18006ef3a  mov     r8d, 4
0x18006ef40  lea     rdx, [rsp+88h+pszName]
0x18006ef45  mov     rax, [rax+18h]
0x18006ef49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ef4e  test    eax, eax
0x18006ef50  jns     short loc_18006EF5A
0x18006ef52  mov     ecx, eax
0x18006ef54  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006ef5a  mov     [rsp+88h+ppv], 0; psfgaoOut
0x18006ef63  xor     r9d, r9d; sfgaoIn
0x18006ef66  lea     r8, [rsp+88h+ppidl]; ppidl
0x18006ef6b  xor     edx, edx; pbc
0x18006ef6d  lea     rcx, [rsp+88h+pszName]; pszName
0x18006ef72  call    cs:__imp_SHParseDisplayName
0x18006ef78  test    eax, eax
0x18006ef7a  jns     short loc_18006EF84
0x18006ef7c  mov     ecx, eax
0x18006ef7e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006ef84  mov     [rsp+88h+var_40], 0
0x18006ef8d  lea     rax, [rsp+88h+var_40]
0x18006ef92  mov     [rsp+88h+ppv], rax; ppv
0x18006ef97  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18006ef9e  xor     r8d, r8d; pbc
0x18006efa1  mov     rdx, [rsp+88h+ppidl]; pidl
0x18006efa6  xor     ecx, ecx; psf
0x18006efa8  call    cs:__imp_SHBindToObject
0x18006efae  test    eax, eax
0x18006efb0  jns     short loc_18006EFBA
0x18006efb2  mov     ecx, eax
0x18006efb4  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006efba  mov     [rsp+88h+var_48], 0
0x18006efc3  mov     rcx, [rsp+88h+var_40]
0x18006efc8  mov     rax, [rcx]
0x18006efcb  lea     r9, [rsp+88h+var_48]
0x18006efd0  lea     r8, _GUID_00000122_0000_0000_c000_000000000046
0x18006efd7  mov     rdx, rdi
0x18006efda  mov     rax, [rax+40h]
0x18006efde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006efe3  test    eax, eax
0x18006efe5  jns     short loc_18006EFEF
0x18006efe7  mov     ecx, eax
0x18006efe9  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006efef  mov     rax, [rbx]
0x18006eff2  mov     rcx, rbx
0x18006eff5  mov     rax, [rax+70h]
0x18006eff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006effe  test    eax, eax
0x18006f000  jns     short loc_18006F00A
0x18006f002  mov     ecx, eax
0x18006f004  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18006f00a  mov     rdx, [rsp+88h+var_58]; struct IDropTarget *
0x18006f00f  mov     rcx, [rsp+88h+var_48]; this
0x18006f014  call    ?SimulateDrop@ModularWindow@@YAXPEAUIDropTarget@@PEAUIDataObject@@K@Z; ModularWindow::SimulateDrop(IDropTarget *,IDataObject *,ulong)
0x18006f019  nop
0x18006f01a  lea     rcx, [rsp+88h+var_48]
0x18006f01f  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f024  nop
0x18006f025  lea     rcx, [rsp+88h+var_40]
0x18006f02a  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f02f  nop
0x18006f030  lea     rcx, [rsp+88h+var_38]
0x18006f035  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f03a  nop
0x18006f03b  lea     rcx, [rsp+88h+var_58]
0x18006f040  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18006f045  nop
0x18006f046  mov     rcx, [rsp+88h+ppidl]; pidl
0x18006f04b  call    cs:__imp_ILFree
0x18006f051  nop
0x18006f052  mov     rcx, [rsp+88h+var_18]
0x18006f057  xor     rcx, rsp; StackCookie
0x18006f05a  call    __security_check_cookie
0x18006f05f  mov     rbx, [rsp+88h+arg_10]
0x18006f067  add     rsp, 80h
0x18006f06e  pop     rdi
0x18006f06f  retn
```
