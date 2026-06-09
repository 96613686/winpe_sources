# CDBFolder::DelegateBindToParent(IShellItem *,_GUID const &,void * *,IShellItem * *)

- ea: `0x1800087d0`
- end: `0x180008a92`
- name: `?DelegateBindToParent@CDBFolder@@UEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAXPEAPEAU2@@Z`
- size: `706`
- prototype: `__int64 __fastcall(CDBFolder *__hidden this, struct IShellItem *, const struct _GUID *, void **, struct IShellItem **psfParent)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180084140`

## callees

- `0x1800087d0`
- `0x18000a350`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x180008979`
- `Windows.Storage!ILFree` at `0x180008983`
- `Windows.Storage!ILFree` at `0x180008a83`
- `Windows.Storage!ILFree` at `0x180008979`
- `Windows.Storage!ILFree` at `0x180008983`
- `Windows.Storage!ILFree` at `0x180008a83`
- `Windows.Storage!SHCreateItemWithParent` at `0x18000892d`
- `Windows.Storage!SHCreateItemWithParent` at `0x18000892d`
- `Windows.Storage!SHGetItemFromObject` at `0x180008a43`
- `Windows.Storage!SHGetItemFromObject` at `0x180008a43`
- `Windows.Storage!__imp_SHCreateTransferFallback` at `0x180008a5d`
- `Windows.Storage!__imp_SHCreateTransferFallback` at `0x180008a5d`

## pseudocode

```c
__int64 __fastcall CDBFolder::DelegateBindToParent(
        CDBFolder *this,
        struct IShellItem *a2,
        const struct _GUID *a3,
        void **a4,
        struct IShellItem **psfParent)
{
  struct IShellItem **v5; // r14
  struct IShellItemVtbl *lpVtbl; // rax
  HRESULT v10; // ebx
  bool v11; // zf
  __int64 v12; // rax
  __int64 v13; // r9
  void *v14; // rcx
  __int64 v16; // rax
  HRESULT v17; // eax
  __int64 v18; // rax
  void *ppvItem; // [rsp+40h] [rbp-20h] BYREF
  LPCITEMIDLIST pidl; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h] BYREF
  LPITEMIDLIST v22; // [rsp+98h] [rbp+38h] BYREF
  void *ppv; // [rsp+A8h] [rbp+48h] BYREF

  v5 = psfParent;
  *psfParent = 0;
  if ( a4 )
    *a4 = 0;
  lpVtbl = a2->lpVtbl;
  v22 = 0;
  v21 = 0;
  ppv = 0;
  v10 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, void **))lpVtbl->QueryInterface)(
          a2,
          &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
          &ppv);
  if ( v10 >= 0 )
  {
    psfParent = 0;
    v10 = (*(__int64 (__fastcall **)(void *, _QWORD, struct IShellItem ***, LPITEMIDLIST *))(*(_QWORD *)ppv + 32LL))(
            ppv,
            0,
            &psfParent,
            &v22);
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(struct IShellItem **, GUID *, __int64 *))(*psfParent)->lpVtbl)(
              psfParent,
              &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
              &v21);
      if ( v10 < 0 )
      {
        ILFree(v22);
        v22 = 0;
      }
      ((void (__fastcall *)(struct IShellItem **))(*psfParent)[2].lpVtbl)(psfParent);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v10 >= 0 )
    {
      v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferSource.Data1;
      v11 = *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferSource.Data1;
      psfParent = 0;
      pidl = 0;
      if ( v11 )
        v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferSource.Data4;
      if ( !v12 )
        goto LABEL_12;
      v13 = 0xFFFFFFFFLL;
      v16 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferSource2.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferSource2.Data1 )
        v16 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferSource2.Data4;
      if ( !v16 )
LABEL_12:
        v13 = 1;
      v10 = CDBFolder::DelegateBindToParent(
              (char *)this + 152,
              v22,
              1,
              v13,
              &GUID_000214e6_0000_0000_c000_000000000046,
              &psfParent,
              &pidl);
      if ( v10 < 0 )
        goto LABEL_19;
      ppvItem = 0;
      v10 = SHCreateItemWithParent(
              0,
              (IShellFolder *)psfParent,
              pidl,
              &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
              &ppvItem);
      if ( v10 < 0 )
      {
LABEL_18:
        ((void (__fastcall *)(struct IShellItem **))(*psfParent)[2].lpVtbl)(psfParent);
        ILFree((LPITEMIDLIST)pidl);
LABEL_19:
        ILFree(v22);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        return (unsigned int)v10;
      }
      if ( a4 )
      {
        v17 = ((__int64 (__fastcall *)(struct IShellItem **, _QWORD, const struct _GUID *, void **))(*psfParent)[8].lpVtbl)(
                psfParent,
                0,
                a3,
                a4);
        v10 = v17;
        if ( v17 == -2147467263 || v17 == -2147467262 )
        {
          v18 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferSource.Data1;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferSource.Data1 )
            v18 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferSource.Data4;
          if ( !v18 )
          {
            ppv = 0;
            v10 = SHGetItemFromObject((IUnknown *)psfParent, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
            if ( v10 < 0 )
              goto LABEL_17;
            v10 = SHCreateTransferFallback(ppv, a3, a4);
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        if ( v10 < 0 )
          goto LABEL_17;
      }
      v14 = ppvItem;
      *v5 = (struct IShellItem *)ppvItem;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 8LL))(v14);
LABEL_17:
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
      goto LABEL_18;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800087d0  mov     [rsp-28h+arg_0], rbx
0x1800087d5  mov     [rsp-28h+arg_10], rsi
0x1800087da  push    rbp
0x1800087db  push    rdi
0x1800087dc  push    r12
0x1800087de  push    r14
0x1800087e0  push    r15
0x1800087e2  mov     rbp, rsp
0x1800087e5  sub     rsp, 60h
0x1800087e9  mov     r14, [rbp+psfParent]
0x1800087ed  xor     r12d, r12d
0x1800087f0  mov     rsi, r9
0x1800087f3  mov     rdi, r8
0x1800087f6  mov     r10, rdx
0x1800087f9  mov     r15, rcx
0x1800087fc  mov     [r14], r12
0x1800087ff  test    r9, r9
0x180008802  jnz     loc_180008A77
0x180008808  mov     rax, [rdx]
0x18000880b  lea     r8, [rbp+ppv]
0x18000880f  lea     rdx, _GUID_b3a4b685_b685_4805_99d9_5dead2873236
0x180008816  mov     [rbp+arg_8], r12
0x18000881a  mov     rcx, r10
0x18000881d  mov     [rbp+var_10], r12
0x180008821  mov     [rbp+ppv], r12
0x180008825  mov     rax, [rax]
0x180008828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882d  mov     ebx, eax
0x18000882f  test    eax, eax
0x180008831  js      loc_180008999
0x180008837  mov     rcx, [rbp+ppv]
0x18000883b  lea     r9, [rbp+arg_8]
0x18000883f  mov     [rbp+psfParent], r12
0x180008843  lea     r8, [rbp+psfParent]
0x180008847  xor     edx, edx
0x180008849  mov     rax, [rcx]
0x18000884c  mov     rax, [rax+20h]
0x180008850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008855  mov     ebx, eax
0x180008857  test    eax, eax
0x180008859  js      short loc_18000888F
0x18000885b  mov     rcx, [rbp+psfParent]
0x18000885f  lea     r8, [rbp+var_10]
0x180008863  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18000886a  mov     rax, [rcx]
0x18000886d  mov     rax, [rax]
0x180008870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008875  mov     ebx, eax
0x180008877  test    eax, eax
0x180008879  js      loc_180008A7F
0x18000887f  mov     rcx, [rbp+psfParent]
0x180008883  mov     rax, [rcx]
0x180008886  mov     rax, [rax+10h]
0x18000888a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000888f  mov     rcx, [rbp+ppv]
0x180008893  mov     rax, [rcx]
0x180008896  mov     rax, [rax+10h]
0x18000889a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000889f  test    ebx, ebx
0x1800088a1  js      loc_180008999
0x1800088a7  mov     rax, [rdi]
0x1800088aa  sub     rax, qword ptr cs:IID_ITransferSource.Data1
0x1800088b1  mov     [rbp+psfParent], r12
0x1800088b5  mov     [rbp+pidl], r12
0x1800088b9  jnz     short loc_1800088C6
0x1800088bb  mov     rax, [rdi+8]
0x1800088bf  sub     rax, qword ptr cs:IID_ITransferSource.Data4
0x1800088c6  test    rax, rax
0x1800088c9  jnz     loc_1800089B4
0x1800088cf  mov     r9d, 1
0x1800088d5  mov     rdx, [rbp+arg_8]
0x1800088d9  lea     rax, [rbp+pidl]
0x1800088dd  mov     [rsp+60h+var_30], rax
0x1800088e2  lea     rcx, [r15+98h]
0x1800088e9  lea     rax, [rbp+psfParent]
0x1800088ed  mov     r8d, 1
0x1800088f3  mov     [rsp+60h+var_38], rax
0x1800088f8  lea     rax, _GUID_000214e6_0000_0000_c000_000000000046
0x1800088ff  mov     [rsp+60h+ppvItem], rax
0x180008904  call    ?DelegateBindToParent@CDBFolder@@UEAAJPEFBU_ITEMID_CHILD@@W4DELBIND_TYPE@@W4DELEGATION_FLAGS@@AEBU_GUID@@PEAPEAXPEAPEAU2@@Z; CDBFolder::DelegateBindToParent(_ITEMID_CHILD const *,DELBIND_TYPE,DELEGATION_FLAGS,_GUID const &,void * *,_ITEMID_CHILD * *)
0x180008909  mov     ebx, eax
0x18000890b  test    eax, eax
0x18000890d  js      short loc_18000897F
0x18000890f  mov     r8, [rbp+pidl]; pidl
0x180008913  lea     rax, [rbp+var_20]
0x180008917  mov     rdx, [rbp+psfParent]; psfParent
0x18000891b  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180008922  xor     ecx, ecx; pidlParent
0x180008924  mov     [rsp+60h+ppvItem], rax; ppvItem
0x180008929  mov     [rbp+var_20], r12
0x18000892d  call    cs:__imp_SHCreateItemWithParent
0x180008933  mov     ebx, eax
0x180008935  test    eax, eax
0x180008937  js      short loc_180008965
0x180008939  test    rsi, rsi
0x18000893c  jnz     loc_1800089DF
0x180008942  mov     rcx, [rbp+var_20]
0x180008946  mov     [r14], rcx
0x180008949  mov     rax, [rcx]
0x18000894c  mov     rax, [rax+8]
0x180008950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008955  mov     rcx, [rbp+var_20]
0x180008959  mov     rax, [rcx]
0x18000895c  mov     rax, [rax+10h]
0x180008960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008965  mov     rcx, [rbp+psfParent]
0x180008969  mov     rax, [rcx]
0x18000896c  mov     rax, [rax+10h]
0x180008970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008975  mov     rcx, [rbp+pidl]; pidl
0x180008979  call    cs:__imp_ILFree
0x18000897f  mov     rcx, [rbp+arg_8]; pidl
0x180008983  call    cs:__imp_ILFree
0x180008989  mov     rcx, [rbp+var_10]
0x18000898d  mov     rax, [rcx]
0x180008990  mov     rax, [rax+10h]
0x180008994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008999  lea     r11, [rsp+60h+var_s0]
0x18000899e  mov     eax, ebx
0x1800089a0  mov     rbx, [r11+30h]
0x1800089a4  mov     rsi, [r11+40h]
0x1800089a8  mov     rsp, r11
0x1800089ab  pop     r15
0x1800089ad  pop     r14
0x1800089af  pop     r12
0x1800089b1  pop     rdi
0x1800089b2  pop     rbp
0x1800089b3  retn
0x1800089b4  mov     rax, [rdi]
0x1800089b7  mov     r9d, 0FFFFFFFFh
0x1800089bd  sub     rax, qword ptr cs:IID_ITransferSource2.Data1
0x1800089c4  jnz     short loc_1800089D1
0x1800089c6  mov     rax, [rdi+8]
0x1800089ca  sub     rax, qword ptr cs:IID_ITransferSource2.Data4
0x1800089d1  test    rax, rax
0x1800089d4  jnz     loc_1800088D5
0x1800089da  jmp     loc_1800088CF
0x1800089df  mov     rcx, [rbp+psfParent]
0x1800089e3  mov     r9, rsi
0x1800089e6  mov     r8, rdi
0x1800089e9  xor     edx, edx
0x1800089eb  mov     rax, [rcx]
0x1800089ee  mov     rax, [rax+40h]
0x1800089f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089f7  mov     ebx, eax
0x1800089f9  cmp     eax, 80004001h
0x1800089fe  jz      short loc_180008A14
0x180008a00  cmp     eax, 80004002h
0x180008a05  jz      short loc_180008A14
0x180008a07  test    ebx, ebx
0x180008a09  jns     loc_180008942
0x180008a0f  jmp     loc_180008955
0x180008a14  mov     rax, [rdi]
0x180008a17  sub     rax, qword ptr cs:IID_ITransferSource.Data1
0x180008a1e  jnz     short loc_180008A2B
0x180008a20  mov     rax, [rdi+8]
0x180008a24  sub     rax, qword ptr cs:IID_ITransferSource.Data4
0x180008a2b  test    rax, rax
0x180008a2e  jnz     short loc_180008A07
0x180008a30  mov     rcx, [rbp+psfParent]; punk
0x180008a34  lea     r8, [rbp+ppv]; ppv
0x180008a38  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180008a3f  mov     [rbp+ppv], r12
0x180008a43  call    cs:__imp_SHGetItemFromObject
0x180008a49  mov     ebx, eax
0x180008a4b  test    eax, eax
0x180008a4d  js      loc_180008955
0x180008a53  mov     rcx, [rbp+ppv]
0x180008a57  mov     r8, rsi
0x180008a5a  mov     rdx, rdi
0x180008a5d  call    cs:__imp_SHCreateTransferFallback
0x180008a63  mov     rcx, [rbp+ppv]
0x180008a67  mov     ebx, eax
0x180008a69  mov     rax, [rcx]
0x180008a6c  mov     rax, [rax+10h]
0x180008a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a75  jmp     short loc_180008A07
0x180008a77  mov     [r9], r12
0x180008a7a  jmp     loc_180008808
0x180008a7f  mov     rcx, [rbp+arg_8]; pidl
0x180008a83  call    cs:__imp_ILFree
0x180008a89  mov     [rbp+arg_8], r12
0x180008a8d  jmp     loc_18000887F
```
