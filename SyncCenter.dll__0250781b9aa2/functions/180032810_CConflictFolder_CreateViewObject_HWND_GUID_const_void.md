# CConflictFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180032810`
- end: `0x180032a1c`
- name: `?CreateViewObject@CConflictFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `524`
- prototype: `int(CConflictFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000a5e4`
- `0x180032810`
- `0x180036f30`
- `0x180047140`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180032926`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180032926`
- `SHELL32!__imp_ILFree` at `0x1800329fc`
- `SHELL32!__imp_ILFree` at `0x1800329fc`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800329e0`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x1800329e0`

## pseudocode

```c
__int64 __fastcall CConflictFolder::CreateViewObject(unsigned __int64 this, HWND a2, const struct _GUID *a3, void **a4)
{
  __int64 v5; // rax
  __int64 v6; // rax
  HRESULT UnfilteredSelfIDList; // ebx
  __int64 v8; // rax
  struct CConflictFolder *v9; // rdi
  const struct _ITEMIDLIST_ABSOLUTE *v10; // r14
  CConflictFolderViewCB *v11; // rax
  CConflictFolderViewCB *v12; // rax
  CConflictFolderViewCB *v13; // rdi
  SFV_CREATE pcsfv; // [rsp+20h] [rbp-29h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-9h] BYREF
  LPITEMIDLIST pidl; // [rsp+C8h] [rbp+7Fh] BYREF

  *a4 = 0;
  v5 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v5 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v5 )
  {
    v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( v6 )
    {
      UnfilteredSelfIDList = -2147024809;
      v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IFrameLayoutDefinition.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFrameLayoutDefinition.Data1 )
        v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IFrameLayoutDefinition.Data4;
      if ( !v8 )
      {
        pidl = 0;
        UnfilteredSelfIDList = (**(__int64 (__fastcall ***)(char *, GUID *, LPITEMIDLIST *))(this - 16))(
                                 (char *)(this - 16),
                                 &GUID_176c11b1_4302_4164_8430_d5a9f0eeacdb,
                                 &pidl);
        if ( UnfilteredSelfIDList >= 0 )
          *a4 = pidl;
      }
    }
    else
    {
      pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 64);
      pdcm.hwnd = a2;
      pdcm.pcmcb = 0;
      memset(&pdcm.cidl, 0, 40);
      pdcm.psf = (IShellFolder *)(this & -(__int64)(this != 16));
      return (unsigned int)SHCreateDefaultContextMenu(&pdcm, a3, a4);
    }
  }
  else
  {
    v9 = (struct CConflictFolder *)(this - 16);
    *(_QWORD *)&pcsfv.cbSize = 32;
    pidl = 0;
    *(_OWORD *)&pcsfv.psvOuter = 0;
    pcsfv.pshf = (IShellFolder *)(this & -(__int64)(this != 16));
    UnfilteredSelfIDList = CConflictFolder::_GetUnfilteredSelfIDList(
                             (CConflictFolder *)(this - 16),
                             (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
    if ( UnfilteredSelfIDList >= 0 )
    {
      v10 = (const struct _ITEMIDLIST_ABSOLUTE *)pidl;
      pcsfv.psfvcb = 0;
      UnfilteredSelfIDList = -2147024882;
      v11 = (CConflictFolderViewCB *)operator new(0x118u);
      if ( v11 )
      {
        v12 = CConflictFolderViewCB::CConflictFolderViewCB(v11, v10, v9);
        v13 = v12;
        if ( v12 )
        {
          UnfilteredSelfIDList = (**(__int64 (__fastcall ***)(CConflictFolderViewCB *, GUID *, IShellFolderViewCB **))v12)(
                                   v12,
                                   &GUID_2047e320_f2a9_11ce_ae65_08002b2e1262,
                                   &pcsfv.psfvcb);
          (*(void (__fastcall **)(CConflictFolderViewCB *))(*(_QWORD *)v13 + 16LL))(v13);
          if ( UnfilteredSelfIDList >= 0 )
          {
            UnfilteredSelfIDList = SHCreateShellFolderView(&pcsfv, (IShellView **)a4);
            ((void (__fastcall *)(IShellFolderViewCB *))pcsfv.psfvcb->lpVtbl[2].MessageSFVCB)(pcsfv.psfvcb);
          }
        }
      }
      ILFree(pidl);
    }
  }
  return (unsigned int)UnfilteredSelfIDList;
}

```

## disassembly

```asm
0x180032810  mov     [rsp-8+arg_0], rbx
0x180032815  mov     [rsp-8+arg_8], rsi
0x18003281a  push    rbp
0x18003281b  push    rdi
0x18003281c  push    r14
0x18003281e  lea     rbp, [rsp-47h]
0x180032823  sub     rsp, 90h
0x18003282a  mov     r10, r8
0x18003282d  mov     qword ptr [r9], 0
0x180032834  mov     rsi, r9
0x180032837  mov     r8, rcx
0x18003283a  mov     rax, [r10]
0x18003283d  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180032844  jnz     short loc_180032851
0x180032846  mov     rax, [r10+8]
0x18003284a  sub     rax, qword ptr cs:IID_IShellView.Data4
0x180032851  test    rax, rax
0x180032854  jz      loc_180032933
0x18003285a  mov     rax, [r10]
0x18003285d  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180032864  jnz     short loc_180032871
0x180032866  mov     rax, [r10+8]
0x18003286a  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180032871  test    rax, rax
0x180032874  jz      short loc_1800328CF
0x180032876  mov     rax, [r10]
0x180032879  mov     ebx, 80070057h
0x18003287e  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x180032885  jnz     short loc_180032892
0x180032887  mov     rax, [r10+8]
0x18003288b  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x180032892  test    rax, rax
0x180032895  jnz     loc_180032A02
0x18003289b  mov     [rbp+57h+pidl], rax
0x18003289f  lea     r8, [rbp+57h+pidl]
0x1800328a3  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800328a7  lea     rdx, _GUID_176c11b1_4302_4164_8430_d5a9f0eeacdb
0x1800328ae  mov     rax, [rcx]
0x1800328b1  mov     rax, [rax]
0x1800328b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328b9  mov     ebx, eax
0x1800328bb  test    eax, eax
0x1800328bd  js      loc_180032A02
0x1800328c3  mov     rcx, [rbp+57h+pidl]
0x1800328c7  mov     [rsi], rcx
0x1800328ca  jmp     loc_180032A02
0x1800328cf  mov     rax, [rcx+40h]
0x1800328d3  mov     [rbp+57h+pdcm.pidlFolder], rax
0x1800328d7  lea     rax, [rcx-10h]
0x1800328db  neg     rax
0x1800328de  mov     [rbp+57h+pdcm.hwnd], rdx
0x1800328e2  mov     rdx, r10; riid
0x1800328e5  mov     [rbp+57h+pdcm.pcmcb], 0
0x1800328ed  sbb     rcx, rcx
0x1800328f0  mov     qword ptr [rbp+57h+pdcm.cidl], 0
0x1800328f8  and     rcx, r8
0x1800328fb  mov     [rbp+57h+pdcm.apidl], 0
0x180032903  mov     [rbp+57h+pdcm.psf], rcx
0x180032907  mov     r8, rsi; ppv
0x18003290a  lea     rcx, [rbp+57h+pdcm]; pdcm
0x18003290e  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x180032916  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x18003291e  mov     [rbp+57h+pdcm.aKeys], 0
0x180032926  call    cs:__imp_SHCreateDefaultContextMenu
0x18003292c  mov     ebx, eax
0x18003292e  jmp     loc_180032A02
0x180032933  lea     rdi, [rcx-10h]
0x180032937  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x18003293f  xorps   xmm0, xmm0
0x180032942  mov     [rbp+57h+pidl], 0
0x18003294a  mov     rax, rdi
0x18003294d  lea     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180032951  neg     rax
0x180032954  movdqu  xmmword ptr [rbp+57h+pcsfv.psvOuter], xmm0
0x180032959  sbb     rcx, rcx
0x18003295c  and     rcx, r8
0x18003295f  mov     [rbp+57h+pcsfv.pshf], rcx
0x180032963  mov     rcx, rdi; this
0x180032966  call    ?_GetUnfilteredSelfIDList@CConflictFolder@@AEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CConflictFolder::_GetUnfilteredSelfIDList(_ITEMIDLIST_ABSOLUTE * *)
0x18003296b  mov     ebx, eax
0x18003296d  test    eax, eax
0x18003296f  js      loc_180032A02
0x180032975  mov     r14, [rbp+57h+pidl]
0x180032979  mov     ecx, 118h; unsigned __int64
0x18003297e  mov     [rbp+57h+pcsfv.psfvcb], 0
0x180032986  mov     ebx, 8007000Eh
0x18003298b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032990  test    rax, rax
0x180032993  jz      short loc_1800329F8
0x180032995  mov     r8, rdi; struct CConflictFolder *
0x180032998  mov     rdx, r14; struct _ITEMIDLIST_ABSOLUTE *
0x18003299b  mov     rcx, rax; this
0x18003299e  call    ??0CConflictFolderViewCB@@QEAA@PEBU_ITEMIDLIST_ABSOLUTE@@PEAVCConflictFolder@@@Z; CConflictFolderViewCB::CConflictFolderViewCB(_ITEMIDLIST_ABSOLUTE const *,CConflictFolder *)
0x1800329a3  mov     rdi, rax
0x1800329a6  test    rax, rax
0x1800329a9  jz      short loc_1800329F8
0x1800329ab  mov     rcx, [rax]
0x1800329ae  lea     r8, [rbp+57h+pcsfv.psfvcb]
0x1800329b2  lea     rdx, _GUID_2047e320_f2a9_11ce_ae65_08002b2e1262
0x1800329b9  mov     rax, [rcx]
0x1800329bc  mov     rcx, rdi
0x1800329bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329c4  mov     rcx, [rdi]
0x1800329c7  mov     ebx, eax
0x1800329c9  mov     rax, [rcx+10h]
0x1800329cd  mov     rcx, rdi
0x1800329d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329d5  test    ebx, ebx
0x1800329d7  js      short loc_1800329F8
0x1800329d9  mov     rdx, rsi; ppsv
0x1800329dc  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x1800329e0  call    cs:__imp_SHCreateShellFolderView
0x1800329e6  mov     rcx, [rbp+57h+pcsfv.psfvcb]
0x1800329ea  mov     ebx, eax
0x1800329ec  mov     rax, [rcx]
0x1800329ef  mov     rax, [rax+10h]
0x1800329f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329f8  mov     rcx, [rbp+57h+pidl]; pidl
0x1800329fc  call    cs:__imp_ILFree
0x180032a02  lea     r11, [rsp+0A0h+var_10]
0x180032a0a  mov     eax, ebx
0x180032a0c  mov     rbx, [r11+20h]
0x180032a10  mov     rsi, [r11+28h]
0x180032a14  mov     rsp, r11
0x180032a17  pop     r14
0x180032a19  pop     rdi
0x180032a1a  pop     rbp
0x180032a1b  retn
```
