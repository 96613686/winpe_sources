# CSyncHandlerFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180044190`
- end: `0x1800443af`
- name: `?CreateViewObject@CSyncHandlerFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `543`
- prototype: `int(CSyncHandlerFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000a5e4`
- `0x180042634`
- `0x180044190`
- `0x18004d93c`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x1800442e6`
- `SHELL32!SHCreateDefaultContextMenu` at `0x1800442e6`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180044385`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180044385`

## pseudocode

```c
__int64 __fastcall CSyncHandlerFolder::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  HRESULT v10; // edi
  __int64 v11; // rax
  __int64 v12; // rax
  const struct _ITEMIDLIST_ABSOLUTE *v13; // r15
  CSyncHandlerViewCB *v14; // rax
  CSyncHandlerViewCB *v15; // rax
  CSyncHandlerViewCB *v16; // rbx
  void **v18; // [rsp+20h] [rbp-59h]
  SFV_CREATE pcsfv; // [rsp+30h] [rbp-49h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+50h] [rbp-29h] BYREF

  *a4 = 0;
  v5 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v5 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v5 )
  {
    v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( !v7 )
    {
      pdcm.pidlFolder = *(LPCITEMIDLIST *)(this + 64);
      pdcm.hwnd = a2;
      pdcm.pcmcb = 0;
      memset(&pdcm.cidl, 0, 40);
      pdcm.psf = (IShellFolder *)(this & -(__int64)(this != 16));
      return (unsigned int)SHCreateDefaultContextMenu(&pdcm, a3, a4);
    }
    v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IFrameLayoutDefinition.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFrameLayoutDefinition.Data1 )
      v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IFrameLayoutDefinition.Data4;
    if ( !v8 )
      return (unsigned int)(**(__int64 (__fastcall ***)(char *, const struct _GUID *, void **))(this - 16))(
                             (char *)(this - 16),
                             a3,
                             a4);
    v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IExtractIconA.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IExtractIconA.Data1 )
      v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IExtractIconA.Data4;
    if ( !v11 )
      return (unsigned int)CSyncFolderBase::GetHandlerExtractIconInterface(
                             (CSyncFolderBase *)(this - 16),
                             (const struct _GUID *)(this + 172),
                             (const unsigned __int16 *)(this + 188),
                             a3,
                             a4);
    v10 = -2147467262;
    v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IExtractIconW.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IExtractIconW.Data1 )
      v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IExtractIconW.Data4;
    if ( !v12 )
      return (unsigned int)CSyncFolderBase::GetHandlerExtractIconInterface(
                             (CSyncFolderBase *)(this - 16),
                             (const struct _GUID *)(this + 172),
                             (const unsigned __int16 *)(this + 188),
                             a3,
                             a4);
  }
  else
  {
    v13 = *(const struct _ITEMIDLIST_ABSOLUTE **)(this + 64);
    *(_QWORD *)&pcsfv.cbSize = 32;
    pcsfv.psvOuter = 0;
    v10 = -2147024882;
    pcsfv.psfvcb = 0;
    pcsfv.pshf = (IShellFolder *)(this & -(__int64)(this != 16));
    v14 = (CSyncHandlerViewCB *)operator new(0x128u);
    if ( v14 )
    {
      v15 = CSyncHandlerViewCB::CSyncHandlerViewCB(
              v14,
              v13,
              (struct CSyncFolderBase *)(this - 16),
              (const unsigned __int16 *)(this + 188),
              (const struct _tagpropertykey *)v18);
      v16 = v15;
      if ( v15 )
      {
        v10 = (**(__int64 (__fastcall ***)(CSyncHandlerViewCB *, GUID *, IShellFolderViewCB **))v15)(
                v15,
                &GUID_2047e320_f2a9_11ce_ae65_08002b2e1262,
                &pcsfv.psfvcb);
        (*(void (__fastcall **)(CSyncHandlerViewCB *))(*(_QWORD *)v16 + 16LL))(v16);
        if ( v10 >= 0 )
        {
          v10 = SHCreateShellFolderView(&pcsfv, (IShellView **)a4);
          ((void (__fastcall *)(IShellFolderViewCB *))pcsfv.psfvcb->lpVtbl[2].MessageSFVCB)(pcsfv.psfvcb);
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180044190  push    rbp
0x180044192  push    rbx
0x180044193  push    rsi
0x180044194  push    rdi
0x180044195  push    r14
0x180044197  push    r15
0x180044199  lea     rbp, [rsp-2Fh]
0x18004419e  sub     rsp, 0A8h
0x1800441a5  mov     qword ptr [r9], 0
0x1800441ac  mov     r14, r9
0x1800441af  mov     rax, [r8]
0x1800441b2  mov     r10, r8
0x1800441b5  sub     rax, qword ptr cs:IID_IShellView.Data1
0x1800441bc  mov     rbx, rcx
0x1800441bf  jnz     short loc_1800441CC
0x1800441c1  mov     rax, [r8+8]
0x1800441c5  sub     rax, qword ptr cs:IID_IShellView.Data4
0x1800441cc  test    rax, rax
0x1800441cf  jz      loc_1800442F1
0x1800441d5  mov     rax, [r8]
0x1800441d8  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800441df  jnz     short loc_1800441EC
0x1800441e1  mov     rax, [r8+8]
0x1800441e5  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800441ec  test    rax, rax
0x1800441ef  jz      loc_18004428F
0x1800441f5  mov     rax, [r8]
0x1800441f8  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x1800441ff  jnz     short loc_18004420C
0x180044201  mov     rax, [r8+8]
0x180044205  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x18004420c  test    rax, rax
0x18004420f  jnz     short loc_18004422D
0x180044211  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180044215  mov     r8, r14
0x180044218  mov     rdx, r10
0x18004421b  mov     rax, [rcx]
0x18004421e  mov     rax, [rax]
0x180044221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044226  mov     edi, eax
0x180044228  jmp     loc_18004439D
0x18004422d  mov     rax, [r8]
0x180044230  sub     rax, qword ptr cs:IID_IExtractIconA.Data1
0x180044237  jnz     short loc_180044244
0x180044239  mov     rax, [r8+8]
0x18004423d  sub     rax, qword ptr cs:IID_IExtractIconA.Data4
0x180044244  test    rax, rax
0x180044247  jz      short loc_18004426E
0x180044249  mov     rax, [r8]
0x18004424c  mov     edi, 80004002h
0x180044251  sub     rax, qword ptr cs:IID_IExtractIconW.Data1
0x180044258  jnz     short loc_180044265
0x18004425a  mov     rax, [r8+8]
0x18004425e  sub     rax, qword ptr cs:IID_IExtractIconW.Data4
0x180044265  test    rax, rax
0x180044268  jnz     loc_18004439D
0x18004426e  lea     r8, [rcx+0BCh]; unsigned __int16 *
0x180044275  mov     [rsp+0D0h+var_B0], r14; void **
0x18004427a  lea     rdx, [rcx+0ACh]; struct _GUID *
0x180044281  mov     r9, r10; struct _GUID *
0x180044284  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180044288  call    ?GetHandlerExtractIconInterface@CSyncFolderBase@@IEAAJPEBU_GUID@@PEBGAEBU2@PEAPEAX@Z; CSyncFolderBase::GetHandlerExtractIconInterface(_GUID const *,ushort const *,_GUID const &,void * *)
0x18004428d  jmp     short loc_180044226
0x18004428f  mov     rax, [rcx+40h]
0x180044293  mov     r8, r14; ppv
0x180044296  mov     [rbp+57h+pdcm.pidlFolder], rax
0x18004429a  lea     rax, [rcx-10h]
0x18004429e  neg     rax
0x1800442a1  mov     [rbp+57h+pdcm.hwnd], rdx
0x1800442a5  mov     rdx, r10; riid
0x1800442a8  mov     [rbp+57h+pdcm.pcmcb], 0
0x1800442b0  sbb     rcx, rcx
0x1800442b3  mov     qword ptr [rbp+57h+pdcm.cidl], 0
0x1800442bb  and     rcx, rbx
0x1800442be  mov     [rbp+57h+pdcm.apidl], 0
0x1800442c6  mov     [rbp+57h+pdcm.psf], rcx
0x1800442ca  lea     rcx, [rbp+57h+pdcm]; pdcm
0x1800442ce  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x1800442d6  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x1800442de  mov     [rbp+57h+pdcm.aKeys], 0
0x1800442e6  call    cs:__imp_SHCreateDefaultContextMenu
0x1800442ec  jmp     loc_180044226
0x1800442f1  mov     r15, [rbx+40h]
0x1800442f5  lea     rax, [rcx-10h]
0x1800442f9  neg     rax
0x1800442fc  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x180044304  mov     [rbp+57h+pcsfv.psvOuter], 0
0x18004430c  mov     edi, 8007000Eh
0x180044311  sbb     rcx, rcx
0x180044314  mov     [rbp+57h+pcsfv.psfvcb], 0
0x18004431c  and     rcx, rbx
0x18004431f  mov     [rbp+57h+pcsfv.pshf], rcx
0x180044323  mov     ecx, 128h; unsigned __int64
0x180044328  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004432d  test    rax, rax
0x180044330  jz      short loc_18004439D
0x180044332  lea     r9, [rbx+0BCh]; unsigned __int16 *
0x180044339  mov     rdx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x18004433c  lea     r8, [rbx-10h]; struct CSyncFolderBase *
0x180044340  mov     rcx, rax; this
0x180044343  call    ??0CSyncHandlerViewCB@@QEAA@PEBU_ITEMIDLIST_ABSOLUTE@@PEAVCSyncFolderBase@@PEBGAEBU_tagpropertykey@@@Z; CSyncHandlerViewCB::CSyncHandlerViewCB(_ITEMIDLIST_ABSOLUTE const *,CSyncFolderBase *,ushort const *,_tagpropertykey const &)
0x180044348  mov     rbx, rax
0x18004434b  test    rax, rax
0x18004434e  jz      short loc_18004439D
0x180044350  mov     rcx, [rax]
0x180044353  lea     r8, [rbp+57h+pcsfv.psfvcb]
0x180044357  lea     rdx, _GUID_2047e320_f2a9_11ce_ae65_08002b2e1262
0x18004435e  mov     rax, [rcx]
0x180044361  mov     rcx, rbx
0x180044364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044369  mov     rcx, [rbx]
0x18004436c  mov     edi, eax
0x18004436e  mov     rax, [rcx+10h]
0x180044372  mov     rcx, rbx
0x180044375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004437a  test    edi, edi
0x18004437c  js      short loc_18004439D
0x18004437e  mov     rdx, r14; ppsv
0x180044381  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x180044385  call    cs:__imp_SHCreateShellFolderView
0x18004438b  mov     rcx, [rbp+57h+pcsfv.psfvcb]
0x18004438f  mov     edi, eax
0x180044391  mov     rax, [rcx]
0x180044394  mov     rax, [rax+10h]
0x180044398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004439d  mov     eax, edi
0x18004439f  add     rsp, 0A8h
0x1800443a6  pop     r15
0x1800443a8  pop     r14
0x1800443aa  pop     rdi
0x1800443ab  pop     rsi
0x1800443ac  pop     rbx
0x1800443ad  pop     rbp
0x1800443ae  retn
```
