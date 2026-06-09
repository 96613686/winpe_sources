# CSyncResultsFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180039340`
- end: `0x18003954c`
- name: `?CreateViewObject@CSyncResultsFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `524`
- prototype: `int(CSyncResultsFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000a5e4`
- `0x180039340`
- `0x18003ac0c`
- `0x18004b778`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180039456`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180039456`
- `SHELL32!__imp_ILFree` at `0x18003952c`
- `SHELL32!__imp_ILFree` at `0x18003952c`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180039510`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180039510`

## pseudocode

```c
__int64 __fastcall CSyncResultsFolder::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rax
  __int64 v6; // rax
  HRESULT UnfilteredSelfIDList; // ebx
  __int64 v8; // rax
  struct CSyncResultsFolder *v9; // rdi
  const struct _ITEMIDLIST_ABSOLUTE *v10; // r14
  CSyncResultsViewCB *v11; // rax
  CSyncResultsViewCB *v12; // rax
  CSyncResultsViewCB *v13; // rdi
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
    v9 = (struct CSyncResultsFolder *)(this - 16);
    *(_QWORD *)&pcsfv.cbSize = 32;
    pidl = 0;
    *(_OWORD *)&pcsfv.psvOuter = 0;
    pcsfv.pshf = (IShellFolder *)(this & -(__int64)(this != 16));
    UnfilteredSelfIDList = CSyncResultsFolder::_GetUnfilteredSelfIDList(
                             (CSyncResultsFolder *)(this - 16),
                             (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
    if ( UnfilteredSelfIDList >= 0 )
    {
      v10 = (const struct _ITEMIDLIST_ABSOLUTE *)pidl;
      pcsfv.psfvcb = 0;
      UnfilteredSelfIDList = -2147024882;
      v11 = (CSyncResultsViewCB *)operator new(0x118u);
      if ( v11 )
      {
        v12 = CSyncResultsViewCB::CSyncResultsViewCB(v11, v10, v9);
        v13 = v12;
        if ( v12 )
        {
          UnfilteredSelfIDList = (**(__int64 (__fastcall ***)(CSyncResultsViewCB *, GUID *, IShellFolderViewCB **))v12)(
                                   v12,
                                   &GUID_2047e320_f2a9_11ce_ae65_08002b2e1262,
                                   &pcsfv.psfvcb);
          (*(void (__fastcall **)(CSyncResultsViewCB *))(*(_QWORD *)v13 + 16LL))(v13);
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
0x180039340  mov     [rsp-8+arg_0], rbx
0x180039345  mov     [rsp-8+arg_8], rsi
0x18003934a  push    rbp
0x18003934b  push    rdi
0x18003934c  push    r14
0x18003934e  lea     rbp, [rsp-47h]
0x180039353  sub     rsp, 90h
0x18003935a  mov     r10, r8
0x18003935d  mov     qword ptr [r9], 0
0x180039364  mov     rsi, r9
0x180039367  mov     r8, rcx
0x18003936a  mov     rax, [r10]
0x18003936d  sub     rax, qword ptr cs:IID_IShellView.Data1
0x180039374  jnz     short loc_180039381
0x180039376  mov     rax, [r10+8]
0x18003937a  sub     rax, qword ptr cs:IID_IShellView.Data4
0x180039381  test    rax, rax
0x180039384  jz      loc_180039463
0x18003938a  mov     rax, [r10]
0x18003938d  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180039394  jnz     short loc_1800393A1
0x180039396  mov     rax, [r10+8]
0x18003939a  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800393a1  test    rax, rax
0x1800393a4  jz      short loc_1800393FF
0x1800393a6  mov     rax, [r10]
0x1800393a9  mov     ebx, 80070057h
0x1800393ae  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x1800393b5  jnz     short loc_1800393C2
0x1800393b7  mov     rax, [r10+8]
0x1800393bb  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x1800393c2  test    rax, rax
0x1800393c5  jnz     loc_180039532
0x1800393cb  mov     [rbp+57h+pidl], rax
0x1800393cf  lea     r8, [rbp+57h+pidl]
0x1800393d3  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1800393d7  lea     rdx, _GUID_176c11b1_4302_4164_8430_d5a9f0eeacdb
0x1800393de  mov     rax, [rcx]
0x1800393e1  mov     rax, [rax]
0x1800393e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393e9  mov     ebx, eax
0x1800393eb  test    eax, eax
0x1800393ed  js      loc_180039532
0x1800393f3  mov     rcx, [rbp+57h+pidl]
0x1800393f7  mov     [rsi], rcx
0x1800393fa  jmp     loc_180039532
0x1800393ff  mov     rax, [rcx+40h]
0x180039403  mov     [rbp+57h+pdcm.pidlFolder], rax
0x180039407  lea     rax, [rcx-10h]
0x18003940b  neg     rax
0x18003940e  mov     [rbp+57h+pdcm.hwnd], rdx
0x180039412  mov     rdx, r10; riid
0x180039415  mov     [rbp+57h+pdcm.pcmcb], 0
0x18003941d  sbb     rcx, rcx
0x180039420  mov     qword ptr [rbp+57h+pdcm.cidl], 0
0x180039428  and     rcx, r8
0x18003942b  mov     [rbp+57h+pdcm.apidl], 0
0x180039433  mov     [rbp+57h+pdcm.psf], rcx
0x180039437  mov     r8, rsi; ppv
0x18003943a  lea     rcx, [rbp+57h+pdcm]; pdcm
0x18003943e  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x180039446  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x18003944e  mov     [rbp+57h+pdcm.aKeys], 0
0x180039456  call    cs:__imp_SHCreateDefaultContextMenu
0x18003945c  mov     ebx, eax
0x18003945e  jmp     loc_180039532
0x180039463  lea     rdi, [rcx-10h]
0x180039467  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x18003946f  xorps   xmm0, xmm0
0x180039472  mov     [rbp+57h+pidl], 0
0x18003947a  mov     rax, rdi
0x18003947d  lea     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180039481  neg     rax
0x180039484  movdqu  xmmword ptr [rbp+57h+pcsfv.psvOuter], xmm0
0x180039489  sbb     rcx, rcx
0x18003948c  and     rcx, r8
0x18003948f  mov     [rbp+57h+pcsfv.pshf], rcx
0x180039493  mov     rcx, rdi; this
0x180039496  call    ?_GetUnfilteredSelfIDList@CSyncResultsFolder@@AEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CSyncResultsFolder::_GetUnfilteredSelfIDList(_ITEMIDLIST_ABSOLUTE * *)
0x18003949b  mov     ebx, eax
0x18003949d  test    eax, eax
0x18003949f  js      loc_180039532
0x1800394a5  mov     r14, [rbp+57h+pidl]
0x1800394a9  mov     ecx, 118h; unsigned __int64
0x1800394ae  mov     [rbp+57h+pcsfv.psfvcb], 0
0x1800394b6  mov     ebx, 8007000Eh
0x1800394bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800394c0  test    rax, rax
0x1800394c3  jz      short loc_180039528
0x1800394c5  mov     r8, rdi; struct CSyncResultsFolder *
0x1800394c8  mov     rdx, r14; struct _ITEMIDLIST_ABSOLUTE *
0x1800394cb  mov     rcx, rax; this
0x1800394ce  call    ??0CSyncResultsViewCB@@QEAA@PEBU_ITEMIDLIST_ABSOLUTE@@PEAVCSyncResultsFolder@@@Z; CSyncResultsViewCB::CSyncResultsViewCB(_ITEMIDLIST_ABSOLUTE const *,CSyncResultsFolder *)
0x1800394d3  mov     rdi, rax
0x1800394d6  test    rax, rax
0x1800394d9  jz      short loc_180039528
0x1800394db  mov     rcx, [rax]
0x1800394de  lea     r8, [rbp+57h+pcsfv.psfvcb]
0x1800394e2  lea     rdx, _GUID_2047e320_f2a9_11ce_ae65_08002b2e1262
0x1800394e9  mov     rax, [rcx]
0x1800394ec  mov     rcx, rdi
0x1800394ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394f4  mov     rcx, [rdi]
0x1800394f7  mov     ebx, eax
0x1800394f9  mov     rax, [rcx+10h]
0x1800394fd  mov     rcx, rdi
0x180039500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039505  test    ebx, ebx
0x180039507  js      short loc_180039528
0x180039509  mov     rdx, rsi; ppsv
0x18003950c  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x180039510  call    cs:__imp_SHCreateShellFolderView
0x180039516  mov     rcx, [rbp+57h+pcsfv.psfvcb]
0x18003951a  mov     ebx, eax
0x18003951c  mov     rax, [rcx]
0x18003951f  mov     rax, [rax+10h]
0x180039523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039528  mov     rcx, [rbp+57h+pidl]; pidl
0x18003952c  call    cs:__imp_ILFree
0x180039532  lea     r11, [rsp+0A0h+var_10]
0x18003953a  mov     eax, ebx
0x18003953c  mov     rbx, [r11+20h]
0x180039540  mov     rsi, [r11+28h]
0x180039544  mov     rsp, r11
0x180039547  pop     r14
0x180039549  pop     rdi
0x18003954a  pop     rbp
0x18003954b  retn
```
