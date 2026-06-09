# CPubFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x180042810`
- end: `0x180042a09`
- name: `?CreateViewObject@CPubFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `505`
- prototype: `__int64 __fastcall(CPubFolder *__hidden this, HWND, const struct _GUID *, void **ppv)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000b2dc`
- `0x18001b5b8`
- `0x180042270`
- `0x180042810`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x1800429e5`
- `SHELL32!SHCreateDefaultContextMenu` at `0x1800429e5`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180042909`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180042909`

## pseudocode

```c
__int64 __fastcall CPubFolder::CreateViewObject(CPubFolder *this, HWND a2, const struct _GUID *a3, IShellView **ppv)
{
  __int64 v7; // rax
  HRESULT v8; // ebx
  CPubFolderViewCB *v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  CPubFolderViewCB *v13; // rax
  CPubFolderViewCB *v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rax
  IShellFolderViewCB *v19; // [rsp+30h] [rbp-59h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-49h] BYREF
  SFV_CREATE pcsfv; // [rsp+90h] [rbp+7h] BYREF

  *ppv = 0;
  v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( !v7 )
  {
    if ( (Microsoft_Windows_Shell_AppWizCplEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        (int)this,
        (int)&AppWizCpl_SoftwareExplorer_Open_Start,
        (int)a3,
        (int)a3,
        (PEVENT_DATA_DESCRIPTOR)&pcsfv);
    v19 = 0;
    v8 = -2147024882;
    v9 = (CPubFolderViewCB *)DirectUI::HAllocAndZero((DirectUI *)0x68, (unsigned __int64)a2);
    if ( v9 )
    {
      v13 = CPubFolderViewCB::CPubFolderViewCB(v9, this, a2);
      v14 = v13;
      if ( v13 )
      {
        v8 = (**(__int64 (__fastcall ***)(CPubFolderViewCB *, GUID *, IShellFolderViewCB **))v13)(
               v13,
               &GUID_2047e320_f2a9_11ce_ae65_08002b2e1262,
               &v19);
        (*(void (__fastcall **)(CPubFolderViewCB *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v8 >= 0 )
        {
          pcsfv.psfvcb = v19;
          *(_QWORD *)&pcsfv.cbSize = 32;
          pcsfv.psvOuter = 0;
          pcsfv.pshf = (IShellFolder *)this;
          v8 = SHCreateShellFolderView(&pcsfv, ppv);
          ((void (__fastcall *)(IShellFolderViewCB *))v19->lpVtbl[2].MessageSFVCB)(v19);
        }
      }
    }
    if ( (Microsoft_Windows_Shell_AppWizCplEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v10,
        (int)&AppWizCpl_SoftwareExplorer_Open_Stop,
        v11,
        v12,
        (PEVENT_DATA_DESCRIPTOR)&pcsfv);
    return (unsigned int)v8;
  }
  v15 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v15 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v15 )
  {
    pdcm.hwnd = a2;
    pdcm.pcmcb = 0;
    pdcm.pidlFolder = 0;
    pdcm.psf = (IShellFolder *)this;
    memset(&pdcm.cidl, 0, 40);
    return (unsigned int)SHCreateDefaultContextMenu(&pdcm, a3, (void **)ppv);
  }
  v8 = -2147467262;
  v16 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IFrameLayoutDefinition.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFrameLayoutDefinition.Data1 )
    v16 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IFrameLayoutDefinition.Data4;
  if ( !v16 )
    return (unsigned int)(**(__int64 (__fastcall ***)(CPubFolder *, const struct _GUID *, IShellView **))this)(
                           this,
                           a3,
                           ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180042810  push    rbp
0x180042812  push    rbx
0x180042813  push    rsi
0x180042814  push    rdi
0x180042815  push    r14
0x180042817  lea     rbp, [rsp-37h]
0x18004281c  sub     rsp, 0C0h
0x180042823  mov     rax, cs:__security_cookie
0x18004282a  xor     rax, rsp
0x18004282d  mov     [rbp+57h+var_30], rax
0x180042831  mov     r14, r9
0x180042834  mov     rsi, rdx
0x180042837  mov     r9, r8; int
0x18004283a  mov     rdi, rcx
0x18004283d  mov     qword ptr [r14], 0
0x180042844  mov     rax, [r8]
0x180042847  sub     rax, qword ptr cs:IID_IShellView.Data1
0x18004284e  jnz     short loc_18004285B
0x180042850  mov     rax, [r8+8]
0x180042854  sub     rax, qword ptr cs:IID_IShellView.Data4
0x18004285b  test    rax, rax
0x18004285e  jnz     loc_18004294B
0x180042864  test    cs:Microsoft_Windows_Shell_AppWizCplEnableBits, 1
0x18004286b  jz      short loc_180042882
0x18004286d  lea     rax, [rbp+57h+pcsfv]
0x180042871  lea     rdx, AppWizCpl_SoftwareExplorer_Open_Start; int
0x180042878  mov     [rsp+0E0h+var_C0], rax; PEVENT_DATA_DESCRIPTOR
0x18004287d  call    McGenEventWrite_EventWriteTransfer
0x180042882  mov     ecx, 68h ; 'h'; this
0x180042887  mov     [rbp+57h+var_B0], 0
0x18004288f  mov     ebx, 8007000Eh
0x180042894  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180042899  test    rax, rax
0x18004289c  jz      loc_180042924
0x1800428a2  mov     r8, rsi; HWND
0x1800428a5  mov     rdx, rdi; struct CPubFolder *
0x1800428a8  mov     rcx, rax; this
0x1800428ab  call    ??0CPubFolderViewCB@@QEAA@PEAVCPubFolder@@PEAUHWND__@@@Z; CPubFolderViewCB::CPubFolderViewCB(CPubFolder *,HWND__ *)
0x1800428b0  mov     rsi, rax
0x1800428b3  test    rax, rax
0x1800428b6  jz      short loc_180042924
0x1800428b8  mov     rcx, [rax]
0x1800428bb  lea     r8, [rbp+57h+var_B0]
0x1800428bf  lea     rdx, _GUID_2047e320_f2a9_11ce_ae65_08002b2e1262
0x1800428c6  mov     rax, [rcx]
0x1800428c9  mov     rcx, rsi
0x1800428cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428d1  mov     rcx, [rsi]
0x1800428d4  mov     ebx, eax
0x1800428d6  mov     rax, [rcx+10h]
0x1800428da  mov     rcx, rsi
0x1800428dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428e2  test    ebx, ebx
0x1800428e4  js      short loc_180042924
0x1800428e6  mov     rax, [rbp+57h+var_B0]
0x1800428ea  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x1800428ee  mov     rdx, r14; ppsv
0x1800428f1  mov     [rbp+57h+pcsfv.psfvcb], rax
0x1800428f5  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x1800428fd  mov     [rbp+57h+pcsfv.psvOuter], 0
0x180042905  mov     [rbp+57h+pcsfv.pshf], rdi
0x180042909  call    cs:__imp_SHCreateShellFolderView
0x18004290f  mov     rdx, [rbp+57h+var_B0]
0x180042913  mov     ebx, eax
0x180042915  mov     rcx, [rdx]
0x180042918  mov     rax, [rcx+10h]
0x18004291c  mov     rcx, rdx
0x18004291f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042924  test    cs:Microsoft_Windows_Shell_AppWizCplEnableBits, 1
0x18004292b  jz      loc_1800429ED
0x180042931  lea     rax, [rbp+57h+pcsfv]
0x180042935  lea     rdx, AppWizCpl_SoftwareExplorer_Open_Stop; int
0x18004293c  mov     [rsp+0E0h+var_C0], rax; PEVENT_DATA_DESCRIPTOR
0x180042941  call    McGenEventWrite_EventWriteTransfer
0x180042946  jmp     loc_1800429ED
0x18004294b  mov     rax, [r8]
0x18004294e  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180042955  jnz     short loc_180042962
0x180042957  mov     rax, [r8+8]
0x18004295b  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180042962  test    rax, rax
0x180042965  jz      short loc_18004299B
0x180042967  mov     rax, [r8]
0x18004296a  mov     ebx, 80004002h
0x18004296f  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x180042976  jnz     short loc_180042983
0x180042978  mov     rax, [r8+8]
0x18004297c  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x180042983  test    rax, rax
0x180042986  jnz     short loc_1800429ED
0x180042988  mov     rax, [rcx]
0x18004298b  mov     r8, r14
0x18004298e  mov     rdx, r9
0x180042991  mov     rax, [rax]
0x180042994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042999  jmp     short loc_1800429EB
0x18004299b  mov     r8, r14; ppv
0x18004299e  mov     [rbp+57h+pdcm.hwnd], rsi
0x1800429a2  mov     rdx, r9; riid
0x1800429a5  mov     [rbp+57h+pdcm.pcmcb], 0
0x1800429ad  lea     rcx, [rbp+57h+pdcm]; pdcm
0x1800429b1  mov     [rbp+57h+pdcm.pidlFolder], 0
0x1800429b9  mov     [rbp+57h+pdcm.psf], rdi
0x1800429bd  mov     qword ptr [rbp+57h+pdcm.cidl], 0
0x1800429c5  mov     [rbp+57h+pdcm.apidl], 0
0x1800429cd  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x1800429d5  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x1800429dd  mov     [rbp+57h+pdcm.aKeys], 0
0x1800429e5  call    cs:__imp_SHCreateDefaultContextMenu
0x1800429eb  mov     ebx, eax
0x1800429ed  mov     eax, ebx
0x1800429ef  mov     rcx, [rbp+57h+var_30]
0x1800429f3  xor     rcx, rsp; StackCookie
0x1800429f6  call    __security_check_cookie
0x1800429fb  add     rsp, 0C0h
0x180042a02  pop     r14
0x180042a04  pop     rdi
0x180042a05  pop     rsi
0x180042a06  pop     rbx
0x180042a07  pop     rbp
0x180042a08  retn
```
