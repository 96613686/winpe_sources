# CFilteredItemFactory::CreateItem(IShellItem *,ushort const *,ICondition *,_GUID const &,void * *)

- ea: `0x180022660`
- end: `0x1800228a6`
- name: `?CreateItem@CFilteredItemFactory@@UEAAJPEAUIShellItem@@PEBGPEAUICondition@@AEBU_GUID@@PEAPEAX@Z`
- size: `582`
- prototype: `int(CFilteredItemFactory *__hidden this, struct IShellItem *, const unsigned __int16 *, struct ICondition *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x180006900`
- `0x180022660`
- `0x180024410`
- `0x180024494`
- `0x180024684`
- `0x180024888`
- `0x18003efa0`
- `0x180040ef0`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180022758`
- `SHELL32!SHCreateItemFromIDList` at `0x180022758`
- `SHELL32!__imp_ILFree` at `0x180022764`
- `SHELL32!__imp_ILFree` at `0x18002283d`
- `SHELL32!__imp_ILFree` at `0x180022867`
- `SHELL32!__imp_ILFree` at `0x180022764`
- `SHELL32!__imp_ILFree` at `0x18002283d`
- `SHELL32!__imp_ILFree` at `0x180022867`

## pseudocode

```c
__int64 __fastcall CFilteredItemFactory::CreateItem(
        CFilteredItemFactory *this,
        IUnknown *a2,
        const unsigned __int16 *a3,
        struct ICondition *a4,
        const struct _GUID *riid,
        void **ppv)
{
  __int64 v9; // rdx
  int ConditionKey; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  __int64 v12; // rdx
  CFilteredItemFactory *v13; // rcx
  CFilteredItemFactory *v14; // rcx
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-49h] BYREF
  struct IFilterCondition *v17; // [rsp+48h] [rbp-41h] BYREF
  IShellFolder *psf; // [rsp+50h] [rbp-39h] BYREF
  LPITEMIDLIST v19; // [rsp+58h] [rbp-31h] BYREF
  void *v20; // [rsp+60h] [rbp-29h] BYREF
  struct IShellFolder *v21; // [rsp+68h] [rbp-21h] BYREF
  LPITEMIDLIST v22; // [rsp+70h] [rbp-19h] BYREF
  struct _tagpropertykey v23; // [rsp+78h] [rbp-11h] BYREF

  *ppv = 0;
  memset(&v23, 0, sizeof(v23));
  ConditionKey = CFilteredItemFactory::_GetConditionKey(this, a4, &v23);
  if ( ConditionKey >= 0 )
  {
    v17 = 0;
    ConditionKey = CFilterCondition::s_CreateInstance(
                     a3,
                     v9,
                     &v23,
                     0,
                     a4,
                     &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea,
                     &v17);
    if ( ConditionKey >= 0 )
    {
      lpVtbl = (struct IShellItemVtbl *)a2->lpVtbl;
      psf = 0;
      if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, IShellFolder **))lpVtbl->BindToHandler)(
             a2,
             0,
             &BHID_SFObject,
             &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
             &psf) < 0 )
      {
        v21 = 0;
        v22 = 0;
        ConditionKey = GetParentAndChildIDListFromItem(a2, v12, &v21, &v22);
        if ( ConditionKey >= 0 )
        {
          if ( v22 && v22->mkid.cb )
          {
            ConditionKey = CFilteredItemFactory::_AppendFilterAndCreateItem(
                             v13,
                             v21,
                             (const struct _ITEMID_CHILD *)v22,
                             v17,
                             riid,
                             ppv);
          }
          else
          {
            v20 = 0;
            ConditionKey = CFilteredItemFactory::_CreateSearchOnItem(v13, a2, (const struct _GUID *)v22, &v20);
            if ( ConditionKey >= 0 )
            {
              pidl = 0;
              v19 = 0;
              ConditionKey = (*(__int64 (__fastcall **)(void *, _QWORD, LPCITEMIDLIST *, LPITEMIDLIST *))(*(_QWORD *)v20 + 32LL))(
                               v20,
                               0,
                               &pidl,
                               &v19);
              if ( ConditionKey >= 0 )
              {
                ConditionKey = CFilteredItemFactory::_AppendFilterAndCreateItem(
                                 v14,
                                 (struct IShellFolder *)pidl,
                                 (const struct _ITEMID_CHILD *)v19,
                                 v17,
                                 riid,
                                 ppv);
                (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
                ILFree(v19);
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)v20 + 16LL))(v20);
            }
          }
          ((void (__fastcall *)(struct IShellFolder *))v21->lpVtbl->Release)(v21);
          ILFree(v22);
        }
      }
      else
      {
        pidl = 0;
        ConditionKey = SHCreateFilteredIDList(psf, (IUnknown *)&pidl);
        if ( ConditionKey >= 0 )
        {
          ConditionKey = SHCreateItemFromIDList(pidl, riid, ppv);
          ILFree((LPITEMIDLIST)pidl);
        }
        ((void (__fastcall *)(IShellFolder *))psf->lpVtbl->Release)(psf);
      }
      (*(void (__fastcall **)(struct IFilterCondition *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  return (unsigned int)ConditionKey;
}

```

## disassembly

```asm
0x180022660  mov     [rsp-8+arg_0], rbx
0x180022665  push    rbp
0x180022666  push    rsi
0x180022667  push    rdi
0x180022668  push    r12
0x18002266a  push    r13
0x18002266c  push    r14
0x18002266e  push    r15
0x180022670  lea     rbp, [rsp-17h]
0x180022675  sub     rsp, 0A0h
0x18002267c  mov     rax, cs:__security_cookie
0x180022683  xor     rax, rsp
0x180022686  mov     [rbp+47h+var_40], rax
0x18002268a  mov     rsi, [rbp+47h+ppv]
0x18002268e  mov     r12, r8
0x180022691  mov     r14, [rbp+47h+riid]
0x180022695  lea     r8, [rbp+47h+var_58]; struct _tagpropertykey *
0x180022699  mov     rdi, rdx
0x18002269c  xorps   xmm0, xmm0
0x18002269f  xor     eax, eax
0x1800226a1  xor     r13d, r13d
0x1800226a4  mov     rdx, r9; struct ICondition *
0x1800226a7  mov     [rsi], r13
0x1800226aa  mov     r15, r9
0x1800226ad  mov     [rbp+47h+var_58.pid], eax
0x1800226b0  movups  xmmword ptr [rbp+47h+var_58.fmtid.Data1], xmm0
0x1800226b4  call    ?_GetConditionKey@CFilteredItemFactory@@AEAAJPEAUICondition@@PEAU_tagpropertykey@@@Z; CFilteredItemFactory::_GetConditionKey(ICondition *,_tagpropertykey *)
0x1800226b9  mov     ebx, eax
0x1800226bb  test    eax, eax
0x1800226bd  js      loc_18002287D
0x1800226c3  lea     rax, [rbp+47h+var_88]
0x1800226c7  mov     [rbp+47h+var_88], r13
0x1800226cb  mov     [rsp+0D0h+var_A0], rax
0x1800226d0  lea     r8, [rbp+47h+var_58]
0x1800226d4  lea     rax, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea
0x1800226db  xor     r9d, r9d
0x1800226de  mov     [rsp+0D0h+var_A8], rax
0x1800226e3  mov     rcx, r12
0x1800226e6  mov     [rsp+0D0h+punk], r15
0x1800226eb  call    ?s_CreateInstance@CFilterCondition@@SAJPEBG0AEBU_tagpropertykey@@W4FC_FLAGS@@PEAUICondition@@AEBU_GUID@@PEAPEAX@Z; CFilterCondition::s_CreateInstance(ushort const *,ushort const *,_tagpropertykey const &,FC_FLAGS,ICondition *,_GUID const &,void * *)
0x1800226f0  mov     ebx, eax
0x1800226f2  test    eax, eax
0x1800226f4  js      loc_18002287D
0x1800226fa  mov     rax, [rdi]
0x1800226fd  lea     rcx, [rbp+47h+psf]
0x180022701  mov     [rsp+0D0h+punk], rcx
0x180022706  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x18002270d  lea     r8, BHID_SFObject
0x180022714  mov     [rbp+47h+psf], r13
0x180022718  xor     edx, edx
0x18002271a  mov     rcx, rdi
0x18002271d  mov     rax, [rax+18h]
0x180022721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022726  test    eax, eax
0x180022728  js      short loc_18002277F
0x18002272a  mov     rcx, [rbp+47h+psf]; psf
0x18002272e  lea     rax, [rbp+47h+pidl]
0x180022732  lea     r9d, [r13+1]
0x180022736  mov     [rsp+0D0h+punk], rax; punk
0x18002273b  lea     r8, [rbp+47h+var_88]
0x18002273f  mov     [rbp+47h+pidl], r13
0x180022743  call    SHCreateFilteredIDList
0x180022748  mov     ebx, eax
0x18002274a  test    eax, eax
0x18002274c  js      short loc_18002276A
0x18002274e  mov     rcx, [rbp+47h+pidl]; pidl
0x180022752  mov     r8, rsi; ppv
0x180022755  mov     rdx, r14; riid
0x180022758  call    cs:__imp_SHCreateItemFromIDList
0x18002275e  mov     rcx, [rbp+47h+pidl]; pidl
0x180022762  mov     ebx, eax
0x180022764  call    cs:__imp_ILFree
0x18002276a  mov     rcx, [rbp+47h+psf]
0x18002276e  mov     rax, [rcx]
0x180022771  mov     rax, [rax+10h]
0x180022775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002277a  jmp     loc_18002286D
0x18002277f  lea     r9, [rbp+47h+var_60]
0x180022783  mov     [rbp+47h+var_68], r13
0x180022787  lea     r8, [rbp+47h+var_68]
0x18002278b  mov     [rbp+47h+var_60], r13
0x18002278f  mov     rcx, rdi
0x180022792  call    GetParentAndChildIDListFromItem
0x180022797  mov     ebx, eax
0x180022799  test    eax, eax
0x18002279b  js      loc_18002286D
0x1800227a1  mov     r8, [rbp+47h+var_60]; struct _GUID *
0x1800227a5  test    r8, r8
0x1800227a8  jz      short loc_1800227CE
0x1800227aa  cmp     [r8], r13w
0x1800227ae  jz      short loc_1800227CE
0x1800227b0  mov     r9, [rbp+47h+var_88]; struct IFilterCondition *
0x1800227b4  mov     rdx, [rbp+47h+var_68]; struct IShellFolder *
0x1800227b8  mov     [rsp+0D0h+var_A8], rsi; void **
0x1800227bd  mov     [rsp+0D0h+punk], r14; struct _GUID *
0x1800227c2  call    ?_AppendFilterAndCreateItem@CFilteredItemFactory@@AEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAUIFilterCondition@@AEBU_GUID@@PEAPEAX@Z; CFilteredItemFactory::_AppendFilterAndCreateItem(IShellFolder *,_ITEMID_CHILD const *,IFilterCondition *,_GUID const &,void * *)
0x1800227c7  mov     ebx, eax
0x1800227c9  jmp     loc_180022853
0x1800227ce  lea     r9, [rbp+47h+var_70]; void **
0x1800227d2  mov     [rbp+47h+var_70], r13
0x1800227d6  mov     rdx, rdi; struct IShellItem *
0x1800227d9  call    ?_CreateSearchOnItem@CFilteredItemFactory@@AEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; CFilteredItemFactory::_CreateSearchOnItem(IShellItem *,_GUID const &,void * *)
0x1800227de  mov     ebx, eax
0x1800227e0  test    eax, eax
0x1800227e2  js      short loc_180022853
0x1800227e4  mov     rcx, [rbp+47h+var_70]
0x1800227e8  lea     r9, [rbp+47h+var_78]
0x1800227ec  mov     [rbp+47h+pidl], r13
0x1800227f0  lea     r8, [rbp+47h+pidl]
0x1800227f4  mov     [rbp+47h+var_78], r13
0x1800227f8  xor     edx, edx
0x1800227fa  mov     rax, [rcx]
0x1800227fd  mov     rax, [rax+20h]
0x180022801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022806  mov     ebx, eax
0x180022808  test    eax, eax
0x18002280a  js      short loc_180022843
0x18002280c  mov     r9, [rbp+47h+var_88]; struct IFilterCondition *
0x180022810  mov     r8, [rbp+47h+var_78]; struct _ITEMID_CHILD *
0x180022814  mov     rdx, [rbp+47h+pidl]; struct IShellFolder *
0x180022818  mov     [rsp+0D0h+var_A8], rsi; void **
0x18002281d  mov     [rsp+0D0h+punk], r14; struct _GUID *
0x180022822  call    ?_AppendFilterAndCreateItem@CFilteredItemFactory@@AEAAJPEAUIShellFolder@@PEBU_ITEMID_CHILD@@PEAUIFilterCondition@@AEBU_GUID@@PEAPEAX@Z; CFilteredItemFactory::_AppendFilterAndCreateItem(IShellFolder *,_ITEMID_CHILD const *,IFilterCondition *,_GUID const &,void * *)
0x180022827  mov     rcx, [rbp+47h+pidl]
0x18002282b  mov     ebx, eax
0x18002282d  mov     rax, [rcx]
0x180022830  mov     rax, [rax+10h]
0x180022834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022839  mov     rcx, [rbp+47h+var_78]; pidl
0x18002283d  call    cs:__imp_ILFree
0x180022843  mov     rcx, [rbp+47h+var_70]
0x180022847  mov     rax, [rcx]
0x18002284a  mov     rax, [rax+10h]
0x18002284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022853  mov     rcx, [rbp+47h+var_68]
0x180022857  mov     rax, [rcx]
0x18002285a  mov     rax, [rax+10h]
0x18002285e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022863  mov     rcx, [rbp+47h+var_60]; pidl
0x180022867  call    cs:__imp_ILFree
0x18002286d  mov     rcx, [rbp+47h+var_88]
0x180022871  mov     rax, [rcx]
0x180022874  mov     rax, [rax+10h]
0x180022878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002287d  mov     eax, ebx
0x18002287f  mov     rcx, [rbp+47h+var_40]
0x180022883  xor     rcx, rsp; StackCookie
0x180022886  call    __security_check_cookie
0x18002288b  mov     rbx, [rsp+0D0h+arg_0]
0x180022893  add     rsp, 0A0h
0x18002289a  pop     r15
0x18002289c  pop     r14
0x18002289e  pop     r13
0x1800228a0  pop     r12
0x1800228a2  pop     rdi
0x1800228a3  pop     rsi
0x1800228a4  pop     rbp
0x1800228a5  retn
```
