# CDBFolderUI::_GetResultsContextMenu(HWND__ *,_ITEMID_CHILD const *,IContextMenu * *)

- ea: `0x18001fa84`
- end: `0x18001fba1`
- name: `?_GetResultsContextMenu@CDBFolderUI@@AEAAJPEAUHWND__@@PEFBU_ITEMID_CHILD@@PEAPEAUIContextMenu@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(CDBFolderUI *this, HWND, const struct _ITEMID_CHILD *, struct IContextMenu **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001fd38`

## callees

- `0x1800033d0`
- `0x180004a10`
- `0x180011910`
- `0x18001fa84`
- `0x180051010`

## import_xrefs

- `SHELL32!AssocCreateForClasses` at `0x18001fb50`
- `SHELL32!AssocCreateForClasses` at `0x18001fb50`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18001fb6a`
- `SHELL32!SHCreateDefaultContextMenu` at `0x18001fb6a`

## pseudocode

```c
__int64 __fastcall CDBFolderUI::_GetResultsContextMenu(
        CDBFolderUI *this,
        HWND a2,
        const struct _ITEMID_CHILD *a3,
        struct IContextMenu **a4)
{
  int v6; // eax
  HRESULT v7; // ebx
  ASSOCIATIONELEMENT rgClasses; // [rsp+20h] [rbp-29h] BYREF
  DEFCONTEXTMENU pdcm; // [rsp+40h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  IShellFolder *v12; // [rsp+B0h] [rbp+67h] BYREF
  const struct _ITEMID_CHILD *v13; // [rsp+C0h] [rbp+77h] BYREF

  v13 = a3;
  *a4 = 0;
  v12 = 0;
  v6 = Microsoft::WRL::ComPtr<IShellFolder3>::As<IShellFolder>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 3,
         (__int64)&v12);
  v7 = v6;
  if ( v6 >= 0 )
  {
    pdcm.hwnd = a2;
    pdcm.pcmcb = 0;
    pdcm.pidlFolder = 0;
    pdcm.psf = v12;
    *(_QWORD *)&pdcm.cidl = 1;
    pdcm.apidl = (LPCITEMIDLIST *)&v13;
    memset(&pdcm.punkAssociationInfo, 0, 24);
    rgClasses.ac = ASSOCCLASS_PROGID_STR;
    rgClasses.hkClass = 0;
    rgClasses.pszClass = L"Results";
    v7 = AssocCreateForClasses(
           &rgClasses,
           1u,
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)&pdcm.punkAssociationInfo);
    if ( v7 >= 0 )
    {
      v7 = SHCreateDefaultContextMenu(&pdcm, &GUID_000214e4_0000_0000_c000_000000000046, (void **)a4);
      ((void (__fastcall *)(IUnknown *))pdcm.punkAssociationInfo->lpVtbl->Release)(pdcm.punkAssociationInfo);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x609,
      (unsigned int)"shell\\searchfolder\\dbfolder_ui.cpp",
      (const char *)(unsigned int)v6,
      rgClasses.ac);
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001fa84  mov     [rsp-8+arg_8], rbx
0x18001fa89  mov     [rsp-8+arg_10], r8
0x18001fa8e  push    rbp
0x18001fa8f  push    rsi
0x18001fa90  push    rdi
0x18001fa91  lea     rbp, [rsp-47h]
0x18001fa96  sub     rsp, 90h
0x18001fa9d  mov     rdi, r9
0x18001faa0  mov     rsi, rdx
0x18001faa3  mov     qword ptr [r9], 0
0x18001faaa  mov     [rbp+57h+arg_0], 0
0x18001fab2  add     rcx, 18h
0x18001fab6  lea     rdx, [rbp+57h+arg_0]
0x18001faba  call    ??$As@UIShellFolder@@@?$ComPtr@UIShellFolder3@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIShellFolder@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IShellFolder3>::As<IShellFolder>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IShellFolder>>)
0x18001fabf  mov     ebx, eax
0x18001fac1  test    eax, eax
0x18001fac3  jns     short loc_18001FAE2
0x18001fac5  mov     rcx, [rbp+5Fh]; this
0x18001fac9  mov     r9d, eax; char *
0x18001facc  lea     r8, aShellSearchfol_0; "shell\\searchfolder\\dbfolder_ui.cpp"
0x18001fad3  mov     edx, 609h; void *
0x18001fad8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fadd  jmp     loc_18001FB83
0x18001fae2  mov     [rbp+57h+pdcm.hwnd], rsi
0x18001fae6  mov     [rbp+57h+pdcm.pcmcb], 0
0x18001faee  mov     [rbp+57h+pdcm.pidlFolder], 0
0x18001faf6  mov     rax, [rbp+57h+arg_0]
0x18001fafa  mov     [rbp+57h+pdcm.psf], rax
0x18001fafe  mov     edx, 1; cClasses
0x18001fb03  mov     qword ptr [rbp+57h+pdcm.cidl], rdx
0x18001fb07  lea     rax, [rbp+57h+arg_10]
0x18001fb0b  mov     [rbp+57h+pdcm.apidl], rax
0x18001fb0f  mov     [rbp+57h+pdcm.punkAssociationInfo], 0
0x18001fb17  mov     qword ptr [rbp+57h+pdcm.cKeys], 0
0x18001fb1f  mov     [rbp+57h+pdcm.aKeys], 0
0x18001fb27  mov     [rbp+57h+rgClasses.ac], 2
0x18001fb2e  mov     [rbp+57h+rgClasses.hkClass], 0
0x18001fb36  lea     rax, aResults; "Results"
0x18001fb3d  mov     [rbp+57h+rgClasses.pszClass], rax
0x18001fb41  lea     r9, [rbp+57h+pdcm.punkAssociationInfo]; ppv
0x18001fb45  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18001fb4c  lea     rcx, [rbp+57h+rgClasses]; rgClasses
0x18001fb50  call    cs:__imp_AssocCreateForClasses
0x18001fb56  mov     ebx, eax
0x18001fb58  test    eax, eax
0x18001fb5a  js      short loc_18001FB83
0x18001fb5c  mov     r8, rdi; ppv
0x18001fb5f  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046; riid
0x18001fb66  lea     rcx, [rbp+57h+pdcm]; pdcm
0x18001fb6a  call    cs:__imp_SHCreateDefaultContextMenu
0x18001fb70  mov     ebx, eax
0x18001fb72  mov     rcx, [rbp+57h+pdcm.punkAssociationInfo]
0x18001fb76  mov     rax, [rcx]
0x18001fb79  mov     rax, [rax+10h]
0x18001fb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb82  nop
0x18001fb83  lea     rcx, [rbp+57h+arg_0]
0x18001fb87  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001fb8c  mov     eax, ebx
0x18001fb8e  mov     rbx, [rsp+0A0h+arg_8]
0x18001fb96  add     rsp, 90h
0x18001fb9d  pop     rdi
0x18001fb9e  pop     rsi
0x18001fb9f  pop     rbp
0x18001fba0  retn
```
