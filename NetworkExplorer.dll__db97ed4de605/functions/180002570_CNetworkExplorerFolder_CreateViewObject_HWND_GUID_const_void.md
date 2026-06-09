# CNetworkExplorerFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180002570`
- end: `0x1800026db`
- name: `?CreateViewObject@CNetworkExplorerFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `363`
- prototype: `int(CNetworkExplorerFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002570`
- `0x180002874`
- `0x180002a90`
- `0x180008838`
- `0x180010010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x1800026d0`
- `SHELL32!SHCreateDefaultContextMenu` at `0x1800026d0`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18000264f`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18000264f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CNetworkExplorerFolder::CreateViewObject(
        IShellFolder *this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  __int64 v7; // rax
  HRESULT result; // eax
  struct CNetworkExplorerFolder *v9; // rsi
  IShellFolder *v10; // rax
  CNetworkExplorerFolderViewCB *v11; // rax
  struct INetworkItemFactory *v12; // rdi
  IShellFolderViewCB *v13; // rax
  HRESULT v14; // ebx
  IShellFolder *v15; // rax
  IShellFolder *v16; // rcx
  SFV_CREATE pcsfv; // [rsp+28h] [rbp-31h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+50h] [rbp-9h] BYREF
  struct INetworkItemFactory *v19; // [rsp+D8h] [rbp+7Fh] BYREF

  *a4 = 0;
  v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v6 )
  {
    v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( v7 )
    {
      return -2147467262;
    }
    else
    {
      pdcm.hwnd = a2;
      pdcm.pcmcb = 0;
      pdcm.pidlFolder = 0;
      v15 = this - 4;
      v16 = 0;
      if ( v15 )
        v16 = this;
      pdcm.psf = v16;
      memset(&pdcm.cidl, 0, 40);
      return SHCreateDefaultContextMenu(&pdcm, a3, a4);
    }
  }
  else
  {
    v19 = 0;
    v9 = (struct CNetworkExplorerFolder *)&this[-4];
    result = CNetworkExplorerFolder::GetFactory((CNetworkExplorerFolder *)&this[-4], &v19);
    if ( result >= 0 )
    {
      *(_QWORD *)&pcsfv.cbSize = 32;
      v10 = 0;
      memset(&pcsfv.pshf, 0, 24);
      if ( v9 )
        v10 = this;
      pcsfv.pshf = v10;
      v11 = (CNetworkExplorerFolderViewCB *)operator new(0x48u);
      v12 = v19;
      if ( v11 )
        v13 = (IShellFolderViewCB *)CNetworkExplorerFolderViewCB::CNetworkExplorerFolderViewCB(v11, v9, v19);
      else
        v13 = 0;
      pcsfv.psfvcb = v13;
      v14 = SHCreateShellFolderView(&pcsfv, (IShellView **)a4);
      if ( pcsfv.psfvcb )
        ((void (__fastcall *)(IShellFolderViewCB *))pcsfv.psfvcb->lpVtbl[2].MessageSFVCB)(pcsfv.psfvcb);
      (*(void (__fastcall **)(struct INetworkItemFactory *))(*(_QWORD *)v12 + 16LL))(v12);
      return v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002570  mov     [rsp-8+arg_0], rbx
0x180002575  mov     [rsp-8+arg_8], rsi
0x18000257a  push    rbp
0x18000257b  push    rdi
0x18000257c  push    r14
0x18000257e  lea     rbp, [rsp-47h]
0x180002583  sub     rsp, 0A0h
0x18000258a  mov     rbx, r9
0x18000258d  mov     r10, r8
0x180002590  mov     rdi, rcx
0x180002593  xor     r14d, r14d
0x180002596  mov     [r9], r14
0x180002599  mov     rax, [r8]
0x18000259c  sub     rax, qword ptr cs:IID_IShellView.Data1
0x1800025a3  jnz     short loc_1800025B0
0x1800025a5  mov     rax, [r8+8]
0x1800025a9  sub     rax, qword ptr cs:IID_IShellView.Data4
0x1800025b0  test    rax, rax
0x1800025b3  jz      short loc_1800025F2
0x1800025b5  mov     rax, [r8]
0x1800025b8  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800025bf  jnz     short loc_1800025CC
0x1800025c1  mov     rax, [r8+8]
0x1800025c5  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800025cc  test    rax, rax
0x1800025cf  jz      loc_180002694
0x1800025d5  mov     eax, 80004002h
0x1800025da  lea     r11, [rsp+0B0h+var_10]
0x1800025e2  mov     rbx, [r11+20h]
0x1800025e6  mov     rsi, [r11+28h]
0x1800025ea  mov     rsp, r11
0x1800025ed  pop     r14
0x1800025ef  pop     rdi
0x1800025f0  pop     rbp
0x1800025f1  retn
0x1800025f2  mov     [rbp+57h+arg_18], r14
0x1800025f6  lea     rsi, [rcx-20h]
0x1800025fa  lea     rdx, [rbp+57h+arg_18]; struct INetworkItemFactory **
0x1800025fe  mov     rcx, rsi; this
0x180002601  call    ?GetFactory@CNetworkExplorerFolder@@QEAAJPEAPEAUINetworkItemFactory@@@Z; CNetworkExplorerFolder::GetFactory(INetworkItemFactory * *)
0x180002606  test    eax, eax
0x180002608  js      short loc_1800025DA
0x18000260a  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x180002612  xorps   xmm0, xmm0
0x180002615  xor     eax, eax
0x180002617  movups  xmmword ptr [rbp+57h+pcsfv.pshf], xmm0
0x18000261b  mov     [rbp+57h+pcsfv.psfvcb], rax
0x18000261f  test    rsi, rsi
0x180002622  cmovnz  rax, rdi
0x180002626  mov     [rbp+57h+pcsfv.pshf], rax
0x18000262a  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000262f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002634  mov     [rbp+57h+var_90], rax
0x180002638  mov     rdi, [rbp+57h+arg_18]
0x18000263c  test    rax, rax
0x18000263f  jnz     short loc_180002676
0x180002641  mov     rax, r14
0x180002644  mov     [rbp+57h+pcsfv.psfvcb], rax
0x180002648  mov     rdx, rbx; ppsv
0x18000264b  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x18000264f  call    cs:__imp_SHCreateShellFolderView
0x180002655  mov     ebx, eax
0x180002657  mov     rcx, [rbp+57h+pcsfv.psfvcb]
0x18000265b  test    rcx, rcx
0x18000265e  jnz     short loc_180002686
0x180002660  mov     rdx, [rdi]
0x180002663  mov     rcx, rdi
0x180002666  mov     rax, [rdx+10h]
0x18000266a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000266f  mov     eax, ebx
0x180002671  jmp     loc_1800025DA
0x180002676  mov     r8, rdi; struct INetworkItemFactory *
0x180002679  mov     rdx, rsi; struct CNetworkExplorerFolder *
0x18000267c  mov     rcx, rax; this
0x18000267f  call    ??0CNetworkExplorerFolderViewCB@@QEAA@PEAVCNetworkExplorerFolder@@PEAUINetworkItemFactory@@@Z; CNetworkExplorerFolderViewCB::CNetworkExplorerFolderViewCB(CNetworkExplorerFolder *,INetworkItemFactory *)
0x180002684  jmp     short loc_180002644
0x180002686  mov     rdx, [rcx]
0x180002689  mov     rax, [rdx+10h]
0x18000268d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002692  jmp     short loc_180002660
0x180002694  mov     [rbp+57h+pdcm.hwnd], rdx
0x180002698  mov     [rbp+57h+pdcm.pcmcb], r14
0x18000269c  mov     [rbp+57h+pdcm.pidlFolder], r14
0x1800026a0  lea     rax, [rcx-20h]
0x1800026a4  mov     rcx, r14
0x1800026a7  test    rax, rax
0x1800026aa  cmovnz  rcx, rdi
0x1800026ae  mov     [rbp+57h+pdcm.psf], rcx
0x1800026b2  mov     qword ptr [rbp+57h+pdcm.cidl], r14
0x1800026b6  mov     [rbp+57h+pdcm.apidl], r14
0x1800026ba  mov     [rbp+57h+pdcm.punkAssociationInfo], r14
0x1800026be  mov     qword ptr [rbp+57h+pdcm.cKeys], r14
0x1800026c2  mov     [rbp+57h+pdcm.aKeys], r14
0x1800026c6  mov     r8, rbx; ppv
0x1800026c9  mov     rdx, r10; riid
0x1800026cc  lea     rcx, [rbp+57h+pdcm]; pdcm
0x1800026d0  call    cs:__imp_SHCreateDefaultContextMenu
0x1800026d6  jmp     loc_1800025DA
```
