# ShellEaselDropTarget::RunEaselOnSameThread(void)

- ea: `0x180049d6c`
- end: `0x180049e62`
- name: `?RunEaselOnSameThread@ShellEaselDropTarget@@AEAAXXZ`
- size: `246`
- prototype: `void __fastcall(ShellEaselDropTarget *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180047070`

## callees

- `0x18000cb74`
- `0x18000d850`
- `0x180025988`
- `0x180031df8`
- `0x18003f824`
- `0x180045cec`
- `0x180049d6c`
- `0x180049e68`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180049dd5`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180049dd5`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180049d80`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180049d80`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049df7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049e2b`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049df7`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180049e2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ShellEaselDropTarget::RunEaselOnSameThread(ShellEaselDropTarget *this, unsigned __int64 a2, bool a3)
{
  ShellEaselRunHelper *v4; // rbx
  int v5; // eax
  struct IUnknown *v6; // rdx
  int v7; // eax
  int v8; // edx
  int v9; // eax
  int v10; // edx
  void *ppvOut; // [rsp+38h] [rbp+10h] BYREF
  ShellEaselRunHelper *v12; // [rsp+40h] [rbp+18h]

  LOBYTE(a2) = 1;
  v4 = (ShellEaselRunHelper *)BasePrivate::New((BasePrivate *)0x18, a2, a3);
  if ( v4 )
  {
    v5 = *((_DWORD *)this + 20);
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *(_DWORD *)v4 = v5;
  }
  else
  {
    v4 = 0;
  }
  v12 = v4;
  if ( v4 )
  {
    ppvOut = 0;
    IUnknown_QueryService(
      *((IUnknown **)this + 12),
      &IID_IFolderView,
      &GUID_cde725b0_ccc9_4519_917e_325d72fab4ce,
      &ppvOut);
    v6 = (struct IUnknown *)ppvOut;
    if ( !ppvOut )
      v6 = (struct IUnknown *)*((_QWORD *)this + 11);
    v7 = ShellEaselRunHelper::PopulateShellList(v4, v6);
    if ( v7 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v7, v8);
      __debugbreak();
    }
    ATL::CComPtr<IModularWindow>::operator=((char *)this + 88, 0);
    if ( ppvOut )
      ATL::AtlComPtrAssign((struct IUnknown **)&ppvOut, 0);
    v9 = ShellEaselRunHelper::RunShellEasel(v4);
    if ( v9 < 0 )
      Base::Throw((Base *)(unsigned int)v9, v10);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppvOut);
  }
  if ( v4 )
  {
    ShellEaselRunHelper::~ShellEaselRunHelper(v4);
    operator delete(v4, 0x18u);
  }
}

```

## disassembly

```asm
0x180049d6c  mov     [rsp+arg_0], rbx
0x180049d71  push    rdi
0x180049d72  sub     rsp, 20h
0x180049d76  mov     rdi, rcx
0x180049d79  mov     dl, 1
0x180049d7b  mov     ecx, 18h
0x180049d80  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180049d86  mov     rbx, rax
0x180049d89  test    rax, rax
0x180049d8c  jz      short loc_180049DA5
0x180049d8e  mov     eax, [rdi+50h]
0x180049d91  mov     qword ptr [rbx+8], 0
0x180049d99  mov     qword ptr [rbx+10h], 0
0x180049da1  mov     [rbx], eax
0x180049da3  jmp     short loc_180049DA7
0x180049da5  xor     ebx, ebx
0x180049da7  mov     [rsp+28h+arg_10], rbx
0x180049dac  test    rbx, rbx
0x180049daf  jz      loc_180049E3D
0x180049db5  mov     [rsp+28h+ppvOut], 0
0x180049dbe  lea     r9, [rsp+28h+ppvOut]; ppvOut
0x180049dc3  lea     r8, _GUID_cde725b0_ccc9_4519_917e_325d72fab4ce; riid
0x180049dca  lea     rdx, IID_IFolderView; guidService
0x180049dd1  mov     rcx, [rdi+60h]; punk
0x180049dd5  call    cs:__imp_IUnknown_QueryService
0x180049ddb  mov     rdx, [rsp+28h+ppvOut]
0x180049de0  test    rdx, rdx
0x180049de3  jnz     short loc_180049DE9
0x180049de5  mov     rdx, [rdi+58h]; struct IUnknown *
0x180049de9  mov     rcx, rbx; this
0x180049dec  call    ?PopulateShellList@ShellEaselRunHelper@@QEAAJPEAUIUnknown@@@Z; ShellEaselRunHelper::PopulateShellList(IUnknown *)
0x180049df1  test    eax, eax
0x180049df3  jns     short loc_180049DFE
0x180049df5  mov     ecx, eax
0x180049df7  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180049dfd  int     3; Trap to Debugger
0x180049dfe  xor     edx, edx
0x180049e00  lea     rcx, [rdi+58h]
0x180049e04  call    ??4?$CComPtr@UIModularWindow@@@ATL@@QEAAPEAUIModularWindow@@PEAU2@@Z; ATL::CComPtr<IModularWindow>::operator=(IModularWindow *)
0x180049e09  cmp     [rsp+28h+ppvOut], 0
0x180049e0f  jz      short loc_180049E1D
0x180049e11  xor     edx, edx; struct IUnknown *
0x180049e13  lea     rcx, [rsp+28h+ppvOut]; struct IUnknown **
0x180049e18  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180049e1d  mov     rcx, rbx; this
0x180049e20  call    ?RunShellEasel@ShellEaselRunHelper@@QEAAJXZ; ShellEaselRunHelper::RunShellEasel(void)
0x180049e25  test    eax, eax
0x180049e27  jns     short loc_180049E32
0x180049e29  mov     ecx, eax
0x180049e2b  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180049e31  nop
0x180049e32  lea     rcx, [rsp+28h+ppvOut]
0x180049e37  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180049e3c  nop
0x180049e3d  test    rbx, rbx
0x180049e40  jz      short loc_180049E57
0x180049e42  mov     rcx, rbx; this
0x180049e45  call    ??1ShellEaselRunHelper@@QEAA@XZ; ShellEaselRunHelper::~ShellEaselRunHelper(void)
0x180049e4a  mov     edx, 18h; unsigned __int64
0x180049e4f  mov     rcx, rbx; void *
0x180049e52  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049e57  mov     rbx, [rsp+28h+arg_0]
0x180049e5c  add     rsp, 20h
0x180049e60  pop     rdi
0x180049e61  retn
```
