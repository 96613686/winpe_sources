# CNetworkExplorerFolder::~CNetworkExplorerFolder(void)

- ea: `0x180005b60`
- end: `0x180005c59`
- name: `??1CNetworkExplorerFolder@@EEAA@XZ`
- size: `249`
- prototype: `void __fastcall(CNetworkExplorerFolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005b10`

## callees

- `0x180005b60`
- `0x180010010`

## import_xrefs

- `SHLWAPI!__imp_SHWeakReleaseInterface` at `0x180005bf6`
- `SHLWAPI!__imp_SHWeakReleaseInterface` at `0x180005bf6`
- `SHELL32!__imp_ILFree` at `0x180005bdc`
- `SHELL32!__imp_ILFree` at `0x180005bdc`
- `GDI32!DeleteObject` at `0x180005c3a`
- `GDI32!DeleteObject` at `0x180005c3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNetworkExplorerFolder::~CNetworkExplorerFolder(CNetworkExplorerFolder *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CNetworkExplorerFolder::`vftable'{for `CAggregatedUnknown'};
  *((_QWORD *)this + 4) = &CNetworkExplorerFolder::`vftable'{for `IShellFolder2'};
  *((_QWORD *)this + 5) = &CNetworkExplorerFolder::`vftable'{for `IPersistFolder2'};
  *((_QWORD *)this + 6) = &CNetworkExplorerFolder::`vftable'{for `IContextMenuCB'};
  *((_QWORD *)this + 7) = &CNetworkExplorerFolder::`vftable'{for `IFolderType'};
  *((_QWORD *)this + 8) = &CNetworkExplorerFolder::`vftable'{for `IShellFolderPropertyInformation'};
  *((_QWORD *)this + 9) = &CNetworkExplorerFolder::`vftable'{for `IExplorerPaneVisibility'};
  *((_QWORD *)this + 10) = &CNetworkExplorerFolder::`vftable'{for `ISearchBoxSettings'};
  *((_QWORD *)this + 11) = &CNetworkExplorerFolder::`vftable'{for `CItemIDFactory<DSPROFILEITEM,999534523>'};
  v2 = (void *)*((_QWORD *)this + 15);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 15) = 0;
  }
  ILFree(*((LPITEMIDLIST *)this + 13));
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  SHWeakReleaseInterface((char *)this + 32, (char *)this + 128);
  _InterlockedDecrement(&g_cRefThisDll);
  *((_QWORD *)this + 11) = &CItemIDFactory<DSPROFILEITEM,999534523>::`vftable';
  v4 = *((_QWORD *)this + 12);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *(_QWORD *)this = &CAggregatedUnknown::`vftable';
}

```

## disassembly

```asm
0x180005b60  mov     [rsp+arg_0], rbx
0x180005b65  push    rdi
0x180005b66  sub     rsp, 20h
0x180005b6a  mov     rbx, rcx
0x180005b6d  lea     rax, ??_7CNetworkExplorerFolder@@6BCAggregatedUnknown@@@; const CNetworkExplorerFolder::`vftable'{for `CAggregatedUnknown'}
0x180005b74  mov     [rcx], rax
0x180005b77  lea     rax, ??_7CNetworkExplorerFolder@@6BIShellFolder2@@@; const CNetworkExplorerFolder::`vftable'{for `IShellFolder2'}
0x180005b7e  mov     [rcx+20h], rax
0x180005b82  lea     rax, ??_7CNetworkExplorerFolder@@6BIPersistFolder2@@@; const CNetworkExplorerFolder::`vftable'{for `IPersistFolder2'}
0x180005b89  mov     [rcx+28h], rax
0x180005b8d  lea     rax, ??_7CNetworkExplorerFolder@@6BIContextMenuCB@@@; const CNetworkExplorerFolder::`vftable'{for `IContextMenuCB'}
0x180005b94  mov     [rcx+30h], rax
0x180005b98  lea     rax, ??_7CNetworkExplorerFolder@@6BIFolderType@@@; const CNetworkExplorerFolder::`vftable'{for `IFolderType'}
0x180005b9f  mov     [rcx+38h], rax
0x180005ba3  lea     rax, ??_7CNetworkExplorerFolder@@6BIShellFolderPropertyInformation@@@; const CNetworkExplorerFolder::`vftable'{for `IShellFolderPropertyInformation'}
0x180005baa  mov     [rcx+40h], rax
0x180005bae  lea     rax, ??_7CNetworkExplorerFolder@@6BIExplorerPaneVisibility@@@; const CNetworkExplorerFolder::`vftable'{for `IExplorerPaneVisibility'}
0x180005bb5  mov     [rcx+48h], rax
0x180005bb9  lea     rax, ??_7CNetworkExplorerFolder@@6BISearchBoxSettings@@@; const CNetworkExplorerFolder::`vftable'{for `ISearchBoxSettings'}
0x180005bc0  mov     [rcx+50h], rax
0x180005bc4  lea     rax, ??_7CNetworkExplorerFolder@@6B?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@@; const CNetworkExplorerFolder::`vftable'{for `CItemIDFactory<DSPROFILEITEM,999534523>'}
0x180005bcb  mov     [rcx+58h], rax
0x180005bcf  mov     rcx, [rcx+78h]; ho
0x180005bd3  test    rcx, rcx
0x180005bd6  jnz     short loc_180005C3A
0x180005bd8  mov     rcx, [rbx+68h]; pidl
0x180005bdc  call    cs:__imp_ILFree
0x180005be2  mov     rcx, [rbx+70h]
0x180005be6  test    rcx, rcx
0x180005be9  jnz     short loc_180005C2C
0x180005beb  lea     rdx, [rbx+80h]
0x180005bf2  lea     rcx, [rbx+20h]
0x180005bf6  call    cs:__imp_SHWeakReleaseInterface
0x180005bfc  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180005c03  lea     rax, ??_7?$CItemIDFactory@UDSPROFILEITEM@@$0DLJDKPLL@@@6B@; const CItemIDFactory<DSPROFILEITEM,999534523>::`vftable'
0x180005c0a  mov     [rbx+58h], rax
0x180005c0e  mov     rcx, [rbx+60h]
0x180005c12  test    rcx, rcx
0x180005c15  jnz     short loc_180005C4A
0x180005c17  lea     rax, ??_7CAggregatedUnknown@@6B@; const CAggregatedUnknown::`vftable'
0x180005c1e  mov     [rbx], rax
0x180005c21  mov     rbx, [rsp+28h+arg_0]
0x180005c26  add     rsp, 20h
0x180005c2a  pop     rdi
0x180005c2b  retn
0x180005c2c  mov     rax, [rcx]
0x180005c2f  mov     rax, [rax+10h]
0x180005c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c38  jmp     short loc_180005BEB
0x180005c3a  call    cs:__imp_DeleteObject
0x180005c40  mov     qword ptr [rbx+78h], 0
0x180005c48  jmp     short loc_180005BD8
0x180005c4a  mov     rax, [rcx]
0x180005c4d  mov     rax, [rax+10h]
0x180005c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c56  jmp     short loc_180005C17
```
