# CDBFolder::_RenameItem(HWND__ *,_ITEMID_CHILD const *,ushort const *,ulong,_ITEMID_CHILD * *)

- ea: `0x18008cd6c`
- end: `0x18008cf9b`
- name: `?_RenameItem@CDBFolder@@AEAAJPEAUHWND__@@PEFBU_ITEMID_CHILD@@PEBGKPEAPEAU3@@Z`
- size: `559`
- prototype: `__int64 __usercall@<rax>(IShellFolder *psfParent@<rcx>, HWND@<rdx>, const struct _ITEMID_CHILD *@<r8>, const unsigned __int16 *@<r9>, unsigned int, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180089d40`

## callees

- `0x18000a350`
- `0x18008a260`
- `0x18008b6ec`
- `0x18008cd6c`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x18008cf40`
- `Windows.Storage!ILFree` at `0x18008cf7a`
- `Windows.Storage!ILFree` at `0x18008cf40`
- `Windows.Storage!ILFree` at `0x18008cf7a`
- `Windows.Storage!SHCreateItemWithParent` at `0x18008ce3e`
- `Windows.Storage!SHCreateItemWithParent` at `0x18008ce3e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008ce0e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008ce0e`

## pseudocode

```c
__int64 __fastcall CDBFolder::_RenameItem(
        IShellFolder *psfParent,
        HWND a2,
        const ITEMIDLIST *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        struct IShellFolder *a6)
{
  struct _ITEMID_CHILD **v6; // rsi
  HRESULT Instance; // ebx
  void *ppvItem; // [rsp+40h] [rbp-20h] BYREF
  struct IFileOperationProgressSink *ppv; // [rsp+48h] [rbp-18h] BYREF
  LPITEMIDLIST v15; // [rsp+50h] [rbp-10h] BYREF
  __int64 v16; // [rsp+58h] [rbp-8h] BYREF
  LPITEMIDLIST pidl; // [rsp+90h] [rbp+30h] BYREF

  v6 = (struct _ITEMID_CHILD **)a6;
  a6 = 0;
  v15 = 0;
  *v6 = 0;
  Instance = CDBFolder::DelegateBindToParent(
               &psfParent[23],
               a3,
               1,
               0xFFFFFFFFLL,
               &GUID_000214e6_0000_0000_c000_000000000046,
               &a6,
               &v15);
  if ( Instance >= 0 )
  {
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_CopyUndoHandler,
                 0,
                 1u,
                 &GUID_04b0f1a7_9490_44bc_96e1_4296a31252e2,
                 (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      ppvItem = 0;
      Instance = SHCreateItemWithParent(0, psfParent, a3, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppvItem);
      if ( Instance >= 0 )
      {
        Instance = ((__int64 (__fastcall *)(struct IFileOperationProgressSink *, _QWORD, void *, _QWORD))ppv->lpVtbl->PreRenameItem)(
                     ppv,
                     0,
                     ppvItem,
                     0);
        if ( Instance >= 0 )
        {
          pidl = 0;
          v16 = 0;
          if ( ((__int64 (__fastcall *)(struct IShellFolder *, GUID *, __int64 *))a6->lpVtbl->QueryInterface)(
                 a6,
                 &GUID_c51e78b5_566b_4cb0_b6ed_784e18797e23,
                 &v16) < 0 )
          {
            Instance = ((__int64 (__fastcall *)(struct IShellFolder *, HWND, LPITEMIDLIST, const unsigned __int16 *, unsigned int, LPITEMIDLIST *))a6->lpVtbl->SetNameOf)(
                         a6,
                         a2,
                         v15,
                         a4,
                         a5,
                         &pidl);
          }
          else
          {
            Instance = (*(__int64 (__fastcall **)(__int64, HWND, LPITEMIDLIST, const unsigned __int16 *, unsigned int, int, LPITEMIDLIST *))(*(_QWORD *)v16 + 24LL))(
                         v16,
                         a2,
                         v15,
                         a4,
                         a5,
                         4,
                         &pidl);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          if ( Instance >= 0 )
          {
            Instance = CDBFolder::UpdateIDListOnRename(
                         (CDBFolder *)&psfParent[4],
                         (const struct _ITEMID_CHILD *)a3,
                         a6,
                         (const struct _ITEMID_CHILD *)pidl,
                         v6);
            if ( Instance >= 0 )
              CDBFolder::_CreateUndoRecordOnRename(psfParent, (struct IShellItem *)ppvItem, *v6, ppv);
            ILFree(pidl);
          }
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
      }
      ((void (__fastcall *)(struct IFileOperationProgressSink *))ppv->lpVtbl->Release)(ppv);
    }
    ((void (__fastcall *)(struct IShellFolder *))a6->lpVtbl->Release)(a6);
    ILFree(v15);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18008cd6c  mov     r11, rsp
0x18008cd6f  mov     [r11+10h], rbx
0x18008cd73  mov     [r11+18h], rsi
0x18008cd77  push    rbp
0x18008cd78  push    rdi
0x18008cd79  push    r12
0x18008cd7b  push    r14
0x18008cd7d  push    r15
0x18008cd7f  mov     rbp, rsp
0x18008cd82  sub     rsp, 60h
0x18008cd86  mov     rsi, [rbp+arg_28]
0x18008cd8a  lea     rax, [rbp+var_10]
0x18008cd8e  mov     [r11-58h], rax
0x18008cd92  mov     r14, r8
0x18008cd95  mov     r15, r9
0x18008cd98  mov     [rbp+arg_28], 0
0x18008cda0  or      r9d, 0FFFFFFFFh
0x18008cda4  mov     [rbp+var_10], 0
0x18008cdac  lea     rax, [rbp+arg_28]
0x18008cdb0  mov     qword ptr [rsi], 0
0x18008cdb7  mov     [r11-60h], rax
0x18008cdbb  mov     r12, rdx
0x18008cdbe  lea     rax, _GUID_000214e6_0000_0000_c000_000000000046
0x18008cdc5  mov     rdi, rcx
0x18008cdc8  add     rcx, 0B8h
0x18008cdcf  mov     [r11-68h], rax
0x18008cdd3  lea     r8d, [r9+2]
0x18008cdd7  mov     rdx, r14
0x18008cdda  call    ?DelegateBindToParent@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@W4DELBIND_TYPE@@W4DELEGATION_FLAGS@@AEBU_GUID@@PEAPEAXPEAPEAU2@@Z; CDBFolder::DelegateBindToParent(_ITEMID_CHILD const *,DELBIND_TYPE,DELEGATION_FLAGS,_GUID const &,void * *,_ITEMID_CHILD * *)
0x18008cddf  mov     ebx, eax
0x18008cde1  test    eax, eax
0x18008cde3  js      loc_18008CF80
0x18008cde9  xor     edx, edx; pUnkOuter
0x18008cdeb  mov     [rbp+var_18], 0
0x18008cdf3  lea     rax, [rbp+var_18]
0x18008cdf7  lea     r9, _GUID_04b0f1a7_9490_44bc_96e1_4296a31252e2; riid
0x18008cdfe  mov     [rsp+60h+ppv], rax; ppv
0x18008ce03  lea     rcx, CLSID_CopyUndoHandler; rclsid
0x18008ce0a  lea     r8d, [rdx+1]; dwClsContext
0x18008ce0e  call    cs:__imp_CoCreateInstance
0x18008ce14  mov     ebx, eax
0x18008ce16  test    eax, eax
0x18008ce18  js      loc_18008CF66
0x18008ce1e  lea     rax, [rbp+ppvItem]
0x18008ce22  mov     [rbp+ppvItem], 0
0x18008ce2a  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18008ce31  mov     [rsp+60h+ppv], rax; ppvItem
0x18008ce36  mov     r8, r14; pidl
0x18008ce39  mov     rdx, rdi; psfParent
0x18008ce3c  xor     ecx, ecx; pidlParent
0x18008ce3e  call    cs:__imp_SHCreateItemWithParent
0x18008ce44  mov     ebx, eax
0x18008ce46  test    eax, eax
0x18008ce48  js      loc_18008CF56
0x18008ce4e  mov     rcx, [rbp+var_18]
0x18008ce52  xor     r9d, r9d
0x18008ce55  mov     r8, [rbp+ppvItem]
0x18008ce59  xor     edx, edx
0x18008ce5b  mov     rax, [rcx]
0x18008ce5e  mov     rax, [rax+28h]
0x18008ce62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ce67  mov     ebx, eax
0x18008ce69  test    eax, eax
0x18008ce6b  js      loc_18008CF46
0x18008ce71  mov     rcx, [rbp+arg_28]
0x18008ce75  lea     r8, [rbp+var_8]
0x18008ce79  mov     [rbp+pidl], 0
0x18008ce81  lea     rdx, _GUID_c51e78b5_566b_4cb0_b6ed_784e18797e23
0x18008ce88  mov     [rbp+var_8], 0
0x18008ce90  mov     rax, [rcx]
0x18008ce93  mov     rax, [rax]
0x18008ce96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ce9b  mov     r8, [rbp+var_10]
0x18008ce9f  lea     rdx, [rbp+pidl]
0x18008cea3  mov     r9, r15
0x18008cea6  test    eax, eax
0x18008cea8  js      short loc_18008CEE5
0x18008ceaa  mov     rcx, [rbp+var_8]
0x18008ceae  mov     [rsp+60h+var_30], rdx
0x18008ceb3  mov     edx, [rbp+arg_20]
0x18008ceb6  mov     dword ptr [rsp+60h+var_38], 4
0x18008cebe  mov     rax, [rcx]
0x18008cec1  mov     dword ptr [rsp+60h+ppv], edx
0x18008cec5  mov     rdx, r12
0x18008cec8  mov     rax, [rax+18h]
0x18008cecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ced1  mov     rcx, [rbp+var_8]
0x18008ced5  mov     ebx, eax
0x18008ced7  mov     rax, [rcx]
0x18008ceda  mov     rax, [rax+10h]
0x18008cede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cee3  jmp     short loc_18008CF06
0x18008cee5  mov     rcx, [rbp+arg_28]
0x18008cee9  mov     [rsp+60h+var_38], rdx
0x18008ceee  mov     edx, [rbp+arg_20]
0x18008cef1  mov     dword ptr [rsp+60h+ppv], edx
0x18008cef5  mov     rdx, r12
0x18008cef8  mov     rax, [rcx]
0x18008cefb  mov     rax, [rax+60h]
0x18008ceff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf04  mov     ebx, eax
0x18008cf06  test    ebx, ebx
0x18008cf08  js      short loc_18008CF46
0x18008cf0a  mov     r9, [rbp+pidl]; struct _ITEMID_CHILD *
0x18008cf0e  lea     rcx, [rdi+20h]; this
0x18008cf12  mov     r8, [rbp+arg_28]; struct IShellFolder *
0x18008cf16  mov     rdx, r14; struct _ITEMID_CHILD *
0x18008cf19  mov     [rsp+60h+ppv], rsi; struct _ITEMID_CHILD **
0x18008cf1e  call    ?UpdateIDListOnRename@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEAUIShellFolder@@PEBU2@PEAPEAU2@@Z; CDBFolder::UpdateIDListOnRename(_ITEMID_CHILD const *,IShellFolder *,_ITEMID_CHILD const *,_ITEMID_CHILD * *)
0x18008cf23  mov     ebx, eax
0x18008cf25  test    eax, eax
0x18008cf27  js      short loc_18008CF3C
0x18008cf29  mov     r9, [rbp+var_18]; struct IFileOperationProgressSink *
0x18008cf2d  mov     rcx, rdi; psfParent
0x18008cf30  mov     r8, [rsi]; struct _ITEMID_CHILD *
0x18008cf33  mov     rdx, [rbp+ppvItem]; struct IShellItem *
0x18008cf37  call    ?_CreateUndoRecordOnRename@CDBFolder@@AEAAXPEAUIShellItem@@PEBU_ITEMID_CHILD@@PEAUIFileOperationProgressSink@@@Z; CDBFolder::_CreateUndoRecordOnRename(IShellItem *,_ITEMID_CHILD const *,IFileOperationProgressSink *)
0x18008cf3c  mov     rcx, [rbp+pidl]; pidl
0x18008cf40  call    cs:__imp_ILFree
0x18008cf46  mov     rcx, [rbp+ppvItem]
0x18008cf4a  mov     rax, [rcx]
0x18008cf4d  mov     rax, [rax+10h]
0x18008cf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf56  mov     rcx, [rbp+var_18]
0x18008cf5a  mov     rax, [rcx]
0x18008cf5d  mov     rax, [rax+10h]
0x18008cf61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf66  mov     rcx, [rbp+arg_28]
0x18008cf6a  mov     rax, [rcx]
0x18008cf6d  mov     rax, [rax+10h]
0x18008cf71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008cf76  mov     rcx, [rbp+var_10]; pidl
0x18008cf7a  call    cs:__imp_ILFree
0x18008cf80  lea     r11, [rsp+60h+var_s0]
0x18008cf85  mov     eax, ebx
0x18008cf87  mov     rbx, [r11+38h]
0x18008cf8b  mov     rsi, [r11+40h]
0x18008cf8f  mov     rsp, r11
0x18008cf92  pop     r15
0x18008cf94  pop     r14
0x18008cf96  pop     r12
0x18008cf98  pop     rdi
0x18008cf99  pop     rbp
0x18008cf9a  retn
```
