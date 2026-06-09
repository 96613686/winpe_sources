# CARPFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x1800125e0`
- end: `0x18001278b`
- name: `?CreateViewObject@CARPFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `427`
- prototype: `__int64 __fastcall(CARPFolder *__hidden this, HWND, const struct _GUID *, void **ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800125e0`
- `0x18001b3a4`
- `0x18001b5b8`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHELL32!SHCreateDefaultContextMenu` at `0x180012769`
- `SHELL32!SHCreateDefaultContextMenu` at `0x180012769`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180012690`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180012690`

## pseudocode

```c
__int64 __fastcall CARPFolder::CreateViewObject(CARPFolder *this, HWND a2, const struct _GUID *a3, IShellView **ppv)
{
  __int64 v7; // rax
  int v8; // ecx
  HRESULT Instance; // ebx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // rax
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
    Instance = CARPFolderViewCB_CreateInstance(this, a2);
    if ( Instance >= 0 )
    {
      pcsfv.psfvcb = 0;
      *(_QWORD *)&pcsfv.cbSize = 32;
      pcsfv.psvOuter = 0;
      pcsfv.pshf = (IShellFolder *)this;
      Instance = SHCreateShellFolderView(&pcsfv, ppv);
      (*(void (__fastcall **)(_QWORD))(MEMORY[0] + 16LL))(0);
    }
    if ( (Microsoft_Windows_Shell_AppWizCplEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v8,
        (int)&AppWizCpl_SoftwareExplorer_Open_Stop,
        v10,
        v11,
        (PEVENT_DATA_DESCRIPTOR)&pcsfv);
    return (unsigned int)Instance;
  }
  v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v12 )
  {
    pdcm.hwnd = a2;
    pdcm.pcmcb = 0;
    pdcm.pidlFolder = 0;
    pdcm.psf = (IShellFolder *)this;
    memset(&pdcm.cidl, 0, 40);
    return (unsigned int)SHCreateDefaultContextMenu(&pdcm, a3, (void **)ppv);
  }
  Instance = -2147467262;
  v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IFrameLayoutDefinition.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IFrameLayoutDefinition.Data1 )
    v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IFrameLayoutDefinition.Data4;
  if ( !v13 )
    return (unsigned int)(**(__int64 (__fastcall ***)(CARPFolder *, const struct _GUID *, IShellView **))this)(
                           this,
                           a3,
                           ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800125e0  push    rbp
0x1800125e2  push    rbx
0x1800125e3  push    rsi
0x1800125e4  push    rdi
0x1800125e5  lea     rbp, [rsp-3Fh]
0x1800125ea  sub     rsp, 0C8h
0x1800125f1  mov     rax, cs:__security_cookie
0x1800125f8  xor     rax, rsp
0x1800125fb  mov     [rbp+57h+var_30], rax
0x1800125ff  mov     rsi, r9
0x180012602  mov     rbx, rdx
0x180012605  mov     r9, r8; int
0x180012608  mov     rdi, rcx
0x18001260b  mov     qword ptr [rsi], 0
0x180012612  mov     rax, [r8]
0x180012615  sub     rax, qword ptr cs:IID_IShellView.Data1
0x18001261c  jnz     short loc_180012629
0x18001261e  mov     rax, [r8+8]
0x180012622  sub     rax, qword ptr cs:IID_IShellView.Data4
0x180012629  test    rax, rax
0x18001262c  jnz     loc_1800126CF
0x180012632  test    cs:Microsoft_Windows_Shell_AppWizCplEnableBits, 1
0x180012639  jz      short loc_180012650
0x18001263b  lea     rax, [rbp+57h+pcsfv]
0x18001263f  lea     rdx, AppWizCpl_SoftwareExplorer_Open_Start; int
0x180012646  mov     [rsp+0E0h+var_C0], rax; PEVENT_DATA_DESCRIPTOR
0x18001264b  call    McGenEventWrite_EventWriteTransfer
0x180012650  lea     r9, [rbp+57h+var_B0]
0x180012654  mov     [rbp+57h+var_B0], 0
0x18001265c  mov     rdx, rbx; HWND
0x18001265f  mov     rcx, rdi; struct CARPFolder *
0x180012662  call    CARPFolderViewCB_CreateInstance
0x180012667  mov     ebx, eax
0x180012669  test    eax, eax
0x18001266b  js      short loc_1800126A8
0x18001266d  mov     rax, [rbp+57h+var_B0]
0x180012671  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x180012675  mov     rdx, rsi; ppsv
0x180012678  mov     [rbp+57h+pcsfv.psfvcb], rax
0x18001267c  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x180012684  mov     [rbp+57h+pcsfv.psvOuter], 0
0x18001268c  mov     [rbp+57h+pcsfv.pshf], rdi
0x180012690  call    cs:__imp_SHCreateShellFolderView
0x180012696  mov     rcx, [rbp+57h+var_B0]
0x18001269a  mov     ebx, eax
0x18001269c  mov     rax, [rcx]
0x18001269f  mov     rax, [rax+10h]
0x1800126a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126a8  test    cs:Microsoft_Windows_Shell_AppWizCplEnableBits, 1
0x1800126af  jz      loc_180012771
0x1800126b5  lea     rax, [rbp+57h+pcsfv]
0x1800126b9  lea     rdx, AppWizCpl_SoftwareExplorer_Open_Stop; int
0x1800126c0  mov     [rsp+0E0h+var_C0], rax; PEVENT_DATA_DESCRIPTOR
0x1800126c5  call    McGenEventWrite_EventWriteTransfer
0x1800126ca  jmp     loc_180012771
0x1800126cf  mov     rax, [r8]
0x1800126d2  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x1800126d9  jnz     short loc_1800126E6
0x1800126db  mov     rax, [r8+8]
0x1800126df  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800126e6  test    rax, rax
0x1800126e9  jz      short loc_18001271F
0x1800126eb  mov     rax, [r8]
0x1800126ee  mov     ebx, 80004002h
0x1800126f3  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data1
0x1800126fa  jnz     short loc_180012707
0x1800126fc  mov     rax, [r8+8]
0x180012700  sub     rax, qword ptr cs:IID_IFrameLayoutDefinition.Data4
0x180012707  test    rax, rax
0x18001270a  jnz     short loc_180012771
0x18001270c  mov     rax, [rcx]
0x18001270f  mov     r8, rsi
0x180012712  mov     rdx, r9
0x180012715  mov     rax, [rax]
0x180012718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001271d  jmp     short loc_18001276F
0x18001271f  mov     r8, rsi; ppv
0x180012722  mov     [rbp+57h+pdcm.hwnd], rbx
0x180012726  mov     rdx, r9; riid
0x180012729  mov     [rbp+57h+pdcm.pcmcb], 0
0x180012731  lea     rcx, [rbp+57h+pdcm]; pdcm
0x180012735  mov     [rbp+57h+pdcm.pidlFolder], 0
0x18001273d  mov     [rbp+57h+pdcm.psf], rdi
0x180012741  mov     qword ptr [rbp+57h+pdcm.cidl], 0
0x180012749  mov     [rbp+57h+pdcm.apidl], 0
0x180012751  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x180012759  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x180012761  mov     [rbp+57h+pdcm.aKeys], 0
0x180012769  call    cs:__imp_SHCreateDefaultContextMenu
0x18001276f  mov     ebx, eax
0x180012771  mov     eax, ebx
0x180012773  mov     rcx, [rbp+57h+var_30]
0x180012777  xor     rcx, rsp; StackCookie
0x18001277a  call    __security_check_cookie
0x18001277f  add     rsp, 0C8h
0x180012786  pop     rdi
0x180012787  pop     rsi
0x180012788  pop     rbx
0x180012789  pop     rbp
0x18001278a  retn
```
