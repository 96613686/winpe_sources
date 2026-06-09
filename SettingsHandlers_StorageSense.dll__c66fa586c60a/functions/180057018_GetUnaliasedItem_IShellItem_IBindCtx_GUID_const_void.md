# GetUnaliasedItem(IShellItem *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180057018`
- end: `0x180057226`
- name: `?GetUnaliasedItem@@YAJPEAUIShellItem@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `526`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005421c`

## callees

- `0x1800550c8`
- `0x180057018`
- `0x1800cd378`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800571f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800571f7`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18005717d`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18005717d`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180057154`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180057154`

## pseudocode

```c
__int64 __fastcall GetUnaliasedItem(struct IShellItem *a1, ITEMIDLIST *a2, struct IShellFolder2 *a3, void **a4)
{
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT ParentAndChildIDListFromItem; // ebx
  struct IShellItemVtbl *v8; // rax
  __int64 v9; // rdx
  int v10; // r8d
  PCWSTR pszPath[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+70h] [rbp+28h] BYREF
  LPITEMIDLIST pidl; // [rsp+78h] [rbp+30h] BYREF
  struct IShellFolder2 *v15; // [rsp+80h] [rbp+38h] BYREF
  IBindCtx *pbc; // [rsp+88h] [rbp+40h] BYREF

  v15 = a3;
  pidl = a2;
  *a4 = 0;
  lpVtbl = a1->lpVtbl;
  v13 = 0;
  if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl->BindToHandler)(
         a1,
         0,
         &BHID_SFObject,
         &GUID_7d903fca_d6f9_4810_8332_946c0177e247,
         &v13) < 0 )
    goto LABEL_5;
  v15 = 0;
  ParentAndChildIDListFromItem = (*(__int64 (__fastcall **)(__int64, struct IShellFolder2 **))(*(_QWORD *)v13 + 32LL))(
                                   v13,
                                   &v15);
  if ( ParentAndChildIDListFromItem >= 0 )
  {
    ParentAndChildIDListFromItem = ((__int64 (__fastcall *)(struct IShellFolder2 *, GUID *, void **))v15->lpVtbl->QueryInterface)(
                                     v15,
                                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                     a4);
    ((void (__fastcall *)(struct IShellFolder2 *))v15->lpVtbl->Release)(v15);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  if ( ParentAndChildIDListFromItem < 0 )
  {
LABEL_5:
    v8 = a1->lpVtbl;
    pszPath[0] = 0;
    if ( ((int (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))v8->GetDisplayName)(a1, 2147844096LL, pszPath) < 0 )
      return ((unsigned int (__fastcall *)(struct IShellItem *, GUID *, void **))a1->lpVtbl->QueryInterface)(
               a1,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               a4);
    pbc = 0;
    v15 = 0;
    pidl = 0;
    ParentAndChildIDListFromItem = GetParentAndChildIDListFromItem(a1, v9, &v15, &pidl);
    if ( ParentAndChildIDListFromItem >= 0 )
    {
      ParentAndChildIDListFromItem = GetParsingBindCtx(v15, pidl, v10, &pbc);
      ((void (__fastcall *)(struct IShellFolder2 *))v15->lpVtbl->Release)(v15);
      ILFree(pidl);
      if ( ParentAndChildIDListFromItem >= 0 )
      {
        pidl = 0;
        ParentAndChildIDListFromItem = SHCreateItemFromParsingName(
                                         pszPath[0],
                                         pbc,
                                         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                         (void **)&pidl);
        if ( ParentAndChildIDListFromItem >= 0 )
        {
          LODWORD(v15) = 0;
          if ( (*(unsigned int (__fastcall **)(LPITEMIDLIST, struct IShellItem *, __int64, struct IShellFolder2 **))(*(_QWORD *)&pidl->mkid.cb + 56LL))(
                 pidl,
                 a1,
                 0x10000000,
                 &v15) )
          {
            ParentAndChildIDListFromItem = (**(__int64 (__fastcall ***)(LPITEMIDLIST, GUID *, void **))&pidl->mkid.cb)(
                                             pidl,
                                             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                             a4);
          }
          else
          {
            ParentAndChildIDListFromItem = -2147467259;
          }
          (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
        }
        ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
      }
    }
    CoTaskMemFree((LPVOID)pszPath[0]);
    if ( ParentAndChildIDListFromItem < 0 )
      return ((unsigned int (__fastcall *)(struct IShellItem *, GUID *, void **))a1->lpVtbl->QueryInterface)(
               a1,
               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
               a4);
  }
  return (unsigned int)ParentAndChildIDListFromItem;
}

```

## disassembly

```asm
0x180057018  mov     [rsp-20h+arg_10], r8
0x18005701d  mov     [rsp-20h+pidl], rdx
0x180057022  push    rbp
0x180057023  push    rbx
0x180057024  push    rsi
0x180057025  push    rdi
0x180057026  mov     rbp, rsp
0x180057029  sub     rsp, 48h
0x18005702d  mov     qword ptr [r9], 0
0x180057034  lea     r8, BHID_SFObject
0x18005703b  mov     rax, [rcx]
0x18005703e  mov     rdi, rcx
0x180057041  lea     rcx, [rbp+arg_0]
0x180057045  mov     [rbp+arg_0], 0
0x18005704d  mov     rsi, r9
0x180057050  mov     [rsp+48h+var_28], rcx
0x180057055  lea     r9, _GUID_7d903fca_d6f9_4810_8332_946c0177e247
0x18005705c  xor     edx, edx
0x18005705e  mov     rax, [rax+18h]
0x180057062  mov     rcx, rdi
0x180057065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005706a  test    eax, eax
0x18005706c  js      short loc_1800570D3
0x18005706e  mov     rcx, [rbp+arg_0]
0x180057072  lea     rdx, [rbp+arg_10]
0x180057076  mov     [rbp+arg_10], 0
0x18005707e  mov     rax, [rcx]
0x180057081  mov     rax, [rax+20h]
0x180057085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005708a  mov     ebx, eax
0x18005708c  test    eax, eax
0x18005708e  js      short loc_1800570BB
0x180057090  mov     rcx, [rbp+arg_10]
0x180057094  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18005709b  mov     r8, rsi
0x18005709e  mov     rax, [rcx]
0x1800570a1  mov     rax, [rax]
0x1800570a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570a9  mov     rcx, [rbp+arg_10]
0x1800570ad  mov     ebx, eax
0x1800570af  mov     rax, [rcx]
0x1800570b2  mov     rax, [rax+10h]
0x1800570b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570bb  mov     rcx, [rbp+arg_0]
0x1800570bf  mov     rax, [rcx]
0x1800570c2  mov     rax, [rax+10h]
0x1800570c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570cb  test    ebx, ebx
0x1800570cd  jns     loc_18005721B
0x1800570d3  mov     rax, [rdi]
0x1800570d6  lea     r8, [rbp+pszPath]
0x1800570da  mov     edx, 80058000h
0x1800570df  mov     [rbp+pszPath], 0
0x1800570e7  mov     rcx, rdi
0x1800570ea  mov     rax, [rax+28h]
0x1800570ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800570f3  test    eax, eax
0x1800570f5  js      loc_180057201
0x1800570fb  lea     r9, [rbp+pidl]
0x1800570ff  mov     [rbp+pbc], 0
0x180057107  lea     r8, [rbp+arg_10]
0x18005710b  mov     [rbp+arg_10], 0
0x180057113  mov     rcx, rdi
0x180057116  mov     [rbp+pidl], 0
0x18005711e  call    GetParentAndChildIDListFromItem
0x180057123  mov     ebx, eax
0x180057125  test    eax, eax
0x180057127  js      loc_1800571F3
0x18005712d  mov     rdx, [rbp+pidl]; struct _ITEMIDLIST *
0x180057131  lea     r9, [rbp+pbc]; struct IBindCtx **
0x180057135  mov     rcx, [rbp+arg_10]; struct IShellFolder2 *
0x180057139  call    ?GetParsingBindCtx@@YAJPEAUIShellFolder2@@PEFBU_ITEMIDLIST@@HPEAPEAUIBindCtx@@@Z; GetParsingBindCtx(IShellFolder2 *,_ITEMIDLIST const *,int,IBindCtx * *)
0x18005713e  mov     rcx, [rbp+arg_10]
0x180057142  mov     ebx, eax
0x180057144  mov     rax, [rcx]
0x180057147  mov     rax, [rax+10h]
0x18005714b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057150  mov     rcx, [rbp+pidl]; pidl
0x180057154  call    cs:__imp_ILFree
0x18005715a  test    ebx, ebx
0x18005715c  js      loc_1800571F3
0x180057162  mov     rdx, [rbp+pbc]; pbc
0x180057166  lea     r9, [rbp+pidl]; ppv
0x18005716a  mov     rcx, [rbp+pszPath]; pszPath
0x18005716e  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180057175  mov     [rbp+pidl], 0
0x18005717d  call    cs:__imp_SHCreateItemFromParsingName
0x180057183  mov     ebx, eax
0x180057185  test    eax, eax
0x180057187  js      short loc_1800571E3
0x180057189  mov     rcx, [rbp+pidl]
0x18005718d  lea     r9, [rbp+arg_10]
0x180057191  mov     dword ptr [rbp+arg_10], 0
0x180057198  mov     r8d, 10000000h
0x18005719e  mov     rdx, rdi
0x1800571a1  mov     rax, [rcx]
0x1800571a4  mov     rax, [rax+38h]
0x1800571a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571ad  test    eax, eax
0x1800571af  jnz     short loc_1800571B8
0x1800571b1  mov     ebx, 80004005h
0x1800571b6  jmp     short loc_1800571D3
0x1800571b8  mov     rcx, [rbp+pidl]
0x1800571bc  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800571c3  mov     r8, rsi
0x1800571c6  mov     rax, [rcx]
0x1800571c9  mov     rax, [rax]
0x1800571cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571d1  mov     ebx, eax
0x1800571d3  mov     rcx, [rbp+pidl]
0x1800571d7  mov     rax, [rcx]
0x1800571da  mov     rax, [rax+10h]
0x1800571de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571e3  mov     rcx, [rbp+pbc]
0x1800571e7  mov     rax, [rcx]
0x1800571ea  mov     rax, [rax+10h]
0x1800571ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571f3  mov     rcx, [rbp+pszPath]; pv
0x1800571f7  call    cs:__imp_CoTaskMemFree
0x1800571fd  test    ebx, ebx
0x1800571ff  jns     short loc_18005721B
0x180057201  mov     rax, [rdi]
0x180057204  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18005720b  mov     r8, rsi
0x18005720e  mov     rcx, rdi
0x180057211  mov     rax, [rax]
0x180057214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057219  mov     ebx, eax
0x18005721b  mov     eax, ebx
0x18005721d  add     rsp, 48h
0x180057221  pop     rdi
0x180057222  pop     rsi
0x180057223  pop     rbx
0x180057224  pop     rbp
0x180057225  retn
```
