# ShellEaselDropTarget::RunEaselOnNewThread(void)

- ea: `0x180049c5c`
- end: `0x180049d65`
- name: `?RunEaselOnNewThread@ShellEaselDropTarget@@AEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ShellEaselDropTarget *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180047070`

## callees

- `0x18000cb74`
- `0x180045724`
- `0x180049c5c`
- `0x180080010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180049d13`
- `SHLWAPI!__imp_SHCreateThread` at `0x180049d32`
- `SHLWAPI!__imp_SHCreateThread` at `0x180049d13`
- `SHLWAPI!__imp_SHCreateThread` at `0x180049d32`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180049c87`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180049c87`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180049ca1`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x180049ca1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ShellEaselDropTarget::RunEaselOnNewThread(ShellEaselDropTarget *this)
{
  VerbThreadProc *v2; // rbx
  unsigned __int64 v3; // rdx
  bool v4; // r8
  VerbThreadProc *v5; // rdi
  int v6; // ebx
  int v7; // [rsp+50h] [rbp+8h] BYREF
  void *ppvOut; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h]

  ppvOut = 0;
  IUnknown_QueryService(
    *((IUnknown **)this + 12),
    &IID_IFolderView,
    &GUID_cde725b0_ccc9_4519_917e_325d72fab4ce,
    &ppvOut);
  v7 = 0;
  v2 = 0;
  v9 = 0;
  LOBYTE(v3) = 1;
  v5 = (VerbThreadProc *)BasePrivate::New((BasePrivate *)0x60, v3, v4);
  if ( v5 )
  {
    v6 = *((_DWORD *)this + 20);
    VerbThreadProc::VerbThreadProc(
      v5,
      *((struct IDataObject **)this + 11),
      *((struct IUnknown **)this + 13),
      (struct IFolderView *)ppvOut,
      &v7);
    *(_QWORD *)v5 = &OpenThreadProc::`vftable';
    *((_QWORD *)v5 + 10) = 0;
    *((_QWORD *)v5 + 11) = 0;
    *((_DWORD *)v5 + 18) = v6;
    v2 = v5;
    if ( v7 >= 0
      && (SHCreateThread(VerbThreadProc::ThreadProcWithThreadRef, v5, 0x4Eu, VerbThreadProc::ThreadProcWithThreadRefCB)
       || SHCreateThread(
            VerbThreadProc::ThreadProcWithoutThreadRef,
            v5,
            0x48u,
            VerbThreadProc::ThreadProcWithoutThreadRefCB)) )
    {
      v2 = 0;
    }
  }
  if ( v2 )
    (*(void (__fastcall **)(VerbThreadProc *))(*(_QWORD *)v2 + 8LL))(v2);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppvOut);
}

```

## disassembly

```asm
0x180049c5c  push    rbx
0x180049c5e  push    rsi
0x180049c5f  push    rdi
0x180049c60  sub     rsp, 30h
0x180049c64  mov     rsi, rcx
0x180049c67  mov     [rsp+48h+ppvOut], 0
0x180049c70  lea     r9, [rsp+48h+ppvOut]; ppvOut
0x180049c75  lea     r8, _GUID_cde725b0_ccc9_4519_917e_325d72fab4ce; riid
0x180049c7c  lea     rdx, IID_IFolderView; guidService
0x180049c83  mov     rcx, [rcx+60h]; punk
0x180049c87  call    cs:__imp_IUnknown_QueryService
0x180049c8d  mov     [rsp+48h+arg_0], 0
0x180049c95  xor     ebx, ebx
0x180049c97  mov     [rsp+48h+arg_10], rbx
0x180049c9c  mov     dl, 1
0x180049c9e  lea     ecx, [rbx+60h]
0x180049ca1  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180049ca7  mov     rdi, rax
0x180049caa  test    rax, rax
0x180049cad  jz      loc_180049D3E
0x180049cb3  mov     ebx, [rsi+50h]
0x180049cb6  lea     rax, [rsp+48h+arg_0]
0x180049cbb  mov     [rsp+48h+var_28], rax; int *
0x180049cc0  mov     r9, [rsp+48h+ppvOut]; struct IFolderView *
0x180049cc5  mov     r8, [rsi+68h]; struct IUnknown *
0x180049cc9  mov     rdx, [rsi+58h]; struct IDataObject *
0x180049ccd  mov     rcx, rdi; this
0x180049cd0  call    ??0VerbThreadProc@@QEAA@PEAUIDataObject@@PEAUIUnknown@@PEAUIFolderView@@PEAJ@Z; VerbThreadProc::VerbThreadProc(IDataObject *,IUnknown *,IFolderView *,long *)
0x180049cd5  lea     rax, ??_7OpenThreadProc@@6B@; const OpenThreadProc::`vftable'
0x180049cdc  mov     [rdi], rax
0x180049cdf  mov     qword ptr [rdi+50h], 0
0x180049ce7  mov     qword ptr [rdi+58h], 0
0x180049cef  mov     [rdi+48h], ebx
0x180049cf2  mov     rbx, rdi
0x180049cf5  cmp     [rsp+48h+arg_0], 0
0x180049cfa  jl      short loc_180049D3E
0x180049cfc  lea     r9, ?ThreadProcWithThreadRefCB@VerbThreadProc@@CAKPEAX@Z; pfnCallback
0x180049d03  mov     r8d, 4Eh ; 'N'; flags
0x180049d09  mov     rdx, rdi; pData
0x180049d0c  lea     rcx, ?ThreadProcWithThreadRef@VerbThreadProc@@CAKPEAX@Z; pfnThreadProc
0x180049d13  call    cs:__imp_SHCreateThread
0x180049d19  test    eax, eax
0x180049d1b  jnz     short loc_180049D3C
0x180049d1d  lea     r9, ?ThreadProcWithoutThreadRefCB@VerbThreadProc@@CAKPEAX@Z; pfnCallback
0x180049d24  lea     r8d, [rax+48h]; flags
0x180049d28  mov     rdx, rdi; pData
0x180049d2b  lea     rcx, ?ThreadProcWithoutThreadRef@VerbThreadProc@@CAKPEAX@Z; pfnThreadProc
0x180049d32  call    cs:__imp_SHCreateThread
0x180049d38  test    eax, eax
0x180049d3a  jz      short loc_180049D3E
0x180049d3c  xor     ebx, ebx
0x180049d3e  test    rbx, rbx
0x180049d41  jz      short loc_180049D53
0x180049d43  mov     rax, [rbx]
0x180049d46  mov     rcx, rbx
0x180049d49  mov     rax, [rax+8]
0x180049d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d52  nop
0x180049d53  lea     rcx, [rsp+48h+ppvOut]
0x180049d58  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180049d5d  add     rsp, 30h
0x180049d61  pop     rdi
0x180049d62  pop     rsi
0x180049d63  pop     rbx
0x180049d64  retn
```
