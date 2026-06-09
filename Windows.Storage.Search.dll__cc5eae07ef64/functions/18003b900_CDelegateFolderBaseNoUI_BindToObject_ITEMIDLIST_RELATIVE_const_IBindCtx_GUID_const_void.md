# CDelegateFolderBaseNoUI::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x18003b900`
- end: `0x18003bcc8`
- name: `?BindToObject@CDelegateFolderBaseNoUI@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `968`
- prototype: `int(CDelegateFolderBaseNoUI *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18003b5f0`
- `0x18003b900`
- `0x18003bcd0`
- `0x1800c1ff8`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILGetNext` at `0x18003b92d`
- `Windows.Storage!ILGetNext` at `0x18003b92d`
- `Windows.Storage!ILFree` at `0x18003baae`
- `Windows.Storage!ILFree` at `0x18003bcbb`
- `Windows.Storage!ILFree` at `0x18003baae`
- `Windows.Storage!ILFree` at `0x18003bcbb`
- `Windows.Storage!ILCombine` at `0x18003bb00`
- `Windows.Storage!ILCombine` at `0x18003bb00`
- `Windows.Storage!ILCloneFirst` at `0x18003b94c`
- `Windows.Storage!ILCloneFirst` at `0x18003b94c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003b9a1`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003bbdf`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003b9a1`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003bbdf`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18003bb9f`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18003bb9f`

## pseudocode

```c
__int64 __fastcall CDelegateFolderBaseNoUI::BindToObject(
        LPCITEMIDLIST *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **a5)
{
  void **v5; // r14
  LPITEMIDLIST v10; // rax
  LPITEMIDLIST v11; // rdi
  const struct _ITEMID_CHILD *v12; // rbx
  unsigned __int64 v14; // rdx
  __int64 v15; // rsi
  HRESULT v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  char *v19; // rdi
  ITEMIDLIST *v20; // r15
  struct IBindCtxVtbl *lpVtbl; // rax
  IPropertyBag *v22; // rsi
  int v23; // ebx
  __int64 v24; // rdx
  char *v25; // r14
  int v26; // esi
  DWORD value[2]; // [rsp+30h] [rbp-28h] BYREF
  void *ppv; // [rsp+38h] [rbp-20h] BYREF
  __int64 v29; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v30[2]; // [rsp+48h] [rbp-10h] BYREF

  v5 = a5;
  *a5 = 0;
  v10 = ILGetNext((LPCITEMIDLIST)a2);
  v11 = v10;
  if ( v10 && v10->mkid.cb )
  {
    v12 = (const struct _ITEMID_CHILD *)ILCloneFirst((LPCITEMIDLIST)a2);
    if ( v12 )
    {
      a5 = 0;
      v26 = CDelegateFolderBaseNoUI::_CreateAndInit(
              this - 1,
              v12,
              a3,
              &GUID_000214e6_0000_0000_c000_000000000046,
              (void **)&a5);
      if ( v26 >= 0 )
      {
        v26 = (*((__int64 (__fastcall **)(void **, LPITEMIDLIST, struct IBindCtx *, const struct _GUID *, void **))*a5
               + 5))(
                a5,
                v11,
                a3,
                a4,
                v5);
        (*((void (__fastcall **)(void **))*a5 + 2))(a5);
      }
      ILFree((LPITEMIDLIST)v12);
      return (unsigned int)v26;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    v18 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&IID_IPropertyBag.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&IID_IPropertyBag.Data1 )
      v18 = *(_QWORD *)a4->Data4 - *(_QWORD *)IID_IPropertyBag.Data4;
    if ( v18 )
    {
      v19 = (char *)(this - 1);
      v20 = ILCombine(this[5], (LPCITEMIDLIST)a2);
      if ( v20 )
      {
        ppv = 0;
        if ( !a2 )
          goto LABEL_9;
        v14 = *(unsigned __int16 *)a2;
        if ( (unsigned int)v14 < 0x12 )
          goto LABEL_9;
        if ( *(_DWORD *)((char *)a2 + 6) != 597942229 )
          goto LABEL_9;
        v15 = *((unsigned __int16 *)a2 + 5);
        if ( v14 < v15 + 18 )
          goto LABEL_9;
        if ( !(_WORD)v15 )
          goto LABEL_9;
        v25 = (char *)a2 + 18;
        if ( a2 == (const struct _ITEMIDLIST_RELATIVE *)-18LL )
          goto LABEL_9;
        *(_QWORD *)value = 0;
        v16 = PSCreateMemoryPropertyStore(&GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, (void **)value);
        if ( v16 >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**(_QWORD **)value + 32LL))(
                  *(_QWORD *)value,
                  v25,
                  (unsigned int)v15);
          if ( v16 >= 0 )
          {
            v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)value + 24LL))(*(_QWORD *)value, 1);
            if ( v16 >= 0 )
              v16 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))value)(
                      *(_QWORD *)value,
                      &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                      &ppv);
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)value + 16LL))(*(_QWORD *)value);
        }
        if ( v16 == -2147024809 )
LABEL_9:
          v16 = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
        if ( v16 >= 0 )
        {
          v16 = (*(__int64 (__fastcall **)(char *, void *, struct IBindCtx *))(*(_QWORD *)v19 + 64LL))(v19, ppv, a3);
          if ( v16 >= 0 )
          {
            if ( a3 )
            {
              lpVtbl = a3->lpVtbl;
              v22 = (IPropertyBag *)ppv;
              v30[0] = 0;
              *(_QWORD *)value = 0;
              if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, DWORD *))lpVtbl->GetObjectParam)(
                     a3,
                     L"ProgressAggregatorProvider",
                     value) >= 0 )
              {
                v23 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))value)(
                        *(_QWORD *)value,
                        &GUID_00000000_0000_0000_c000_000000000046,
                        v30);
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)value + 16LL))(*(_QWORD *)value);
                if ( v23 >= 0 )
                {
                  value[0] = 0;
                  if ( (int)IUnknown_GetCookieFromProvider(v30[0], v24, value) >= 0 )
                    PSPropertyBag_WriteDWORD(v22, L"AggregatorCookie", value[0]);
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30[0] + 16LL))(v30[0]);
                }
              }
            }
            v17 = *(_QWORD *)v19;
            v29 = 0;
            v16 = (*(__int64 (__fastcall **)(char *, void *, GUID *, __int64 *))(v17 + 56))(
                    v19,
                    ppv,
                    &GUID_37d84f60_42cb_11ce_8135_00aa004bb851,
                    &v29);
            if ( v16 >= 0 )
            {
              v16 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v29 + 40LL))(v29, ppv, 0);
              if ( v16 >= 0 )
              {
                v30[0] = 0;
                v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v29)(
                        v29,
                        &GUID_000214ea_0000_0000_c000_000000000046,
                        v30);
                if ( v16 >= 0 )
                {
                  v16 = (*(__int64 (__fastcall **)(_QWORD, ITEMIDLIST *))(*(_QWORD *)v30[0] + 32LL))(v30[0], v20);
                  if ( v16 >= 0 )
                    v16 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v29)(v29, a4, a5);
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30[0] + 16LL))(v30[0]);
                }
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        ILFree(v20);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
      return (unsigned int)v16;
    }
    else
    {
      return CItemIDFactory<DELEGATEBASEITEM,597942229>::GetPropertyStorageFromIDList(a2, a4, v5);
    }
  }
}

```

## disassembly

```asm
0x18003b900  push    rbp
0x18003b902  push    rbx
0x18003b903  push    rsi
0x18003b904  push    rdi
0x18003b905  push    r12
0x18003b907  push    r13
0x18003b909  push    r14
0x18003b90b  push    r15
0x18003b90d  mov     rbp, rsp
0x18003b910  sub     rsp, 58h
0x18003b914  mov     r14, [rbp+arg_20]
0x18003b918  mov     rsi, rcx
0x18003b91b  xor     r15d, r15d
0x18003b91e  mov     rcx, rdx; pidl
0x18003b921  mov     r12, r9
0x18003b924  mov     r13, r8
0x18003b927  mov     rbx, rdx
0x18003b92a  mov     [r14], r15
0x18003b92d  call    cs:__imp_ILGetNext
0x18003b933  mov     rdi, rax
0x18003b936  test    rax, rax
0x18003b939  jz      loc_18003BAC7
0x18003b93f  cmp     [rax], r15w
0x18003b943  jz      loc_18003BAC7
0x18003b949  mov     rcx, rbx; pidl
0x18003b94c  call    cs:__imp_ILCloneFirst
0x18003b952  mov     rbx, rax
0x18003b955  test    rax, rax
0x18003b958  jnz     loc_18003BC5F
0x18003b95e  mov     eax, 8007000Eh
0x18003b963  jmp     loc_18003BAB6
0x18003b968  xor     r8d, r8d
0x18003b96b  mov     [rbp+ppv], r8
0x18003b96f  test    rbx, rbx
0x18003b972  jz      short loc_18003B996
0x18003b974  movzx   edx, word ptr [rbx]
0x18003b977  cmp     edx, 12h
0x18003b97a  jb      short loc_18003B996
0x18003b97c  cmp     dword ptr [rbx+6], 23A3DFD5h
0x18003b983  jnz     short loc_18003B996
0x18003b985  movzx   esi, word ptr [rbx+0Ah]
0x18003b989  lea     rcx, [rsi+12h]
0x18003b98d  cmp     rdx, rcx
0x18003b990  jnb     loc_18003BBBA
0x18003b996  lea     rdx, [rbp+ppv]; ppv
0x18003b99a  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18003b9a1  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003b9a7  mov     ebx, eax
0x18003b9a9  test    ebx, ebx
0x18003b9ab  js      loc_18003BAAB
0x18003b9b1  mov     rax, [rdi]
0x18003b9b4  mov     r8, r13
0x18003b9b7  mov     rdx, [rbp+ppv]
0x18003b9bb  mov     rcx, rdi
0x18003b9be  mov     rax, [rax+40h]
0x18003b9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9c7  mov     ebx, eax
0x18003b9c9  test    eax, eax
0x18003b9cb  js      loc_18003BA9B
0x18003b9d1  xor     r14d, r14d
0x18003b9d4  test    r13, r13
0x18003b9d7  jnz     loc_18003BB19
0x18003b9dd  mov     rax, [rdi]
0x18003b9e0  lea     r9, [rbp+var_18]
0x18003b9e4  mov     rdx, [rbp+ppv]
0x18003b9e8  lea     r8, _GUID_37d84f60_42cb_11ce_8135_00aa004bb851
0x18003b9ef  mov     rcx, rdi
0x18003b9f2  mov     [rbp+var_18], r14
0x18003b9f6  mov     rax, [rax+38h]
0x18003b9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9ff  mov     ebx, eax
0x18003ba01  test    eax, eax
0x18003ba03  js      loc_18003BA9B
0x18003ba09  mov     rcx, [rbp+var_18]
0x18003ba0d  xor     r8d, r8d
0x18003ba10  mov     rdx, [rbp+ppv]
0x18003ba14  mov     rax, [rcx]
0x18003ba17  mov     rax, [rax+28h]
0x18003ba1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba20  mov     ebx, eax
0x18003ba22  test    eax, eax
0x18003ba24  js      short loc_18003BA8B
0x18003ba26  mov     rcx, [rbp+var_18]
0x18003ba2a  lea     r8, [rbp+var_10]
0x18003ba2e  mov     [rbp+var_10], r14
0x18003ba32  lea     rdx, _GUID_000214ea_0000_0000_c000_000000000046
0x18003ba39  mov     rax, [rcx]
0x18003ba3c  mov     rax, [rax]
0x18003ba3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba44  mov     ebx, eax
0x18003ba46  test    eax, eax
0x18003ba48  js      short loc_18003BA8B
0x18003ba4a  mov     rcx, [rbp+var_10]
0x18003ba4e  mov     rdx, r15
0x18003ba51  mov     rax, [rcx]
0x18003ba54  mov     rax, [rax+20h]
0x18003ba58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba5d  mov     ebx, eax
0x18003ba5f  test    eax, eax
0x18003ba61  js      short loc_18003BA7B
0x18003ba63  mov     rcx, [rbp+var_18]
0x18003ba67  mov     rdx, r12
0x18003ba6a  mov     r8, [rbp+arg_20]
0x18003ba6e  mov     rax, [rcx]
0x18003ba71  mov     rax, [rax]
0x18003ba74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba79  mov     ebx, eax
0x18003ba7b  mov     rcx, [rbp+var_10]
0x18003ba7f  mov     rax, [rcx]
0x18003ba82  mov     rax, [rax+10h]
0x18003ba86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba8b  mov     rcx, [rbp+var_18]
0x18003ba8f  mov     rax, [rcx]
0x18003ba92  mov     rax, [rax+10h]
0x18003ba96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba9b  mov     rcx, [rbp+ppv]
0x18003ba9f  mov     rax, [rcx]
0x18003baa2  mov     rax, [rax+10h]
0x18003baa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baab  mov     rcx, r15; pidl
0x18003baae  call    cs:__imp_ILFree
0x18003bab4  mov     eax, ebx
0x18003bab6  add     rsp, 58h
0x18003baba  pop     r15
0x18003babc  pop     r14
0x18003babe  pop     r13
0x18003bac0  pop     r12
0x18003bac2  pop     rdi
0x18003bac3  pop     rsi
0x18003bac4  pop     rbx
0x18003bac5  pop     rbp
0x18003bac6  retn
0x18003bac7  mov     rax, [r12]
0x18003bacb  sub     rax, qword ptr cs:IID_IPropertyBag.Data1
0x18003bad2  jnz     short loc_18003BAE0
0x18003bad4  mov     rax, [r12+8]
0x18003bad9  sub     rax, qword ptr cs:IID_IPropertyBag.Data4
0x18003bae0  test    rax, rax
0x18003bae3  jnz     short loc_18003BAF5
0x18003bae5  mov     r8, r14
0x18003bae8  mov     rdx, r12
0x18003baeb  mov     rcx, rbx
0x18003baee  call    ?GetPropertyStorageFromIDList@?$CItemIDFactory@UDELEGATEBASEITEM@@$0CDKDNPNF@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CItemIDFactory<DELEGATEBASEITEM,597942229>::GetPropertyStorageFromIDList(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x18003baf3  jmp     short loc_18003BAB6
0x18003baf5  mov     rcx, [rsi+28h]; pidl1
0x18003baf9  lea     rdi, [rsi-8]
0x18003bafd  mov     rdx, rbx; pidl2
0x18003bb00  call    cs:__imp_ILCombine
0x18003bb06  mov     r15, rax
0x18003bb09  test    rax, rax
0x18003bb0c  jnz     loc_18003B968
0x18003bb12  mov     ebx, 8007000Eh
0x18003bb17  jmp     short loc_18003BAB4
0x18003bb19  mov     rax, [r13+0]
0x18003bb1d  lea     r8, [rbp+value]
0x18003bb21  mov     rsi, [rbp+ppv]
0x18003bb25  lea     rdx, aProgressaggreg; "ProgressAggregatorProvider"
0x18003bb2c  mov     rcx, r13
0x18003bb2f  mov     [rbp+var_10], r14
0x18003bb33  mov     qword ptr [rbp+value], r14
0x18003bb37  mov     rax, [rax+50h]
0x18003bb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb40  test    eax, eax
0x18003bb42  js      loc_18003B9DD
0x18003bb48  mov     rcx, qword ptr [rbp+value]
0x18003bb4c  lea     r8, [rbp+var_10]
0x18003bb50  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003bb57  mov     rax, [rcx]
0x18003bb5a  mov     rax, [rax]
0x18003bb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb62  mov     rcx, qword ptr [rbp+value]
0x18003bb66  mov     ebx, eax
0x18003bb68  mov     rdx, [rcx]
0x18003bb6b  mov     rax, [rdx+10h]
0x18003bb6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb74  test    ebx, ebx
0x18003bb76  js      loc_18003B9DD
0x18003bb7c  mov     rcx, [rbp+var_10]
0x18003bb80  lea     r8, [rbp+value]
0x18003bb84  mov     [rbp+value], r14d
0x18003bb88  call    IUnknown_GetCookieFromProvider
0x18003bb8d  test    eax, eax
0x18003bb8f  js      short loc_18003BBA5
0x18003bb91  mov     r8d, [rbp+value]; value
0x18003bb95  lea     rdx, aAggregatorcook; "AggregatorCookie"
0x18003bb9c  mov     rcx, rsi; propBag
0x18003bb9f  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18003bba5  mov     rcx, [rbp+var_10]
0x18003bba9  mov     rax, [rcx]
0x18003bbac  mov     rax, [rax+10h]
0x18003bbb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbb5  jmp     loc_18003B9DD
0x18003bbba  test    si, si
0x18003bbbd  jz      loc_18003B996
0x18003bbc3  lea     r14, [rbx+12h]
0x18003bbc7  test    r14, r14
0x18003bbca  jz      loc_18003B996
0x18003bbd0  lea     rdx, [rbp+value]; ppv
0x18003bbd4  mov     qword ptr [rbp+value], r8
0x18003bbd8  lea     rcx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x18003bbdf  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003bbe5  mov     ebx, eax
0x18003bbe7  test    eax, eax
0x18003bbe9  js      short loc_18003BC4E
0x18003bbeb  mov     rcx, qword ptr [rbp+value]
0x18003bbef  mov     r8d, esi
0x18003bbf2  mov     rdx, r14
0x18003bbf5  mov     rax, [rcx]
0x18003bbf8  mov     rax, [rax+20h]
0x18003bbfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc01  mov     ebx, eax
0x18003bc03  test    eax, eax
0x18003bc05  js      short loc_18003BC3E
0x18003bc07  mov     rcx, qword ptr [rbp+value]
0x18003bc0b  mov     edx, 1
0x18003bc10  mov     rax, [rcx]
0x18003bc13  mov     rax, [rax+18h]
0x18003bc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc1c  mov     ebx, eax
0x18003bc1e  test    eax, eax
0x18003bc20  js      short loc_18003BC3E
0x18003bc22  mov     rcx, qword ptr [rbp+value]
0x18003bc26  lea     r8, [rbp+ppv]
0x18003bc2a  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18003bc31  mov     rax, [rcx]
0x18003bc34  mov     rax, [rax]
0x18003bc37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc3c  mov     ebx, eax
0x18003bc3e  mov     rcx, qword ptr [rbp+value]
0x18003bc42  mov     rax, [rcx]
0x18003bc45  mov     rax, [rax+10h]
0x18003bc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc4e  cmp     ebx, 80070057h
0x18003bc54  jnz     loc_18003B9A9
0x18003bc5a  jmp     loc_18003B996
0x18003bc5f  lea     rax, [rbp+arg_20]
0x18003bc63  mov     [rbp+arg_20], r15
0x18003bc67  lea     rcx, [rsi-8]; this
0x18003bc6b  mov     [rsp+58h+var_38], rax; void **
0x18003bc70  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; struct _GUID *
0x18003bc77  mov     r8, r13; struct IBindCtx *
0x18003bc7a  mov     rdx, rbx; struct _ITEMID_CHILD *
0x18003bc7d  call    ?_CreateAndInit@CDelegateFolderBaseNoUI@@AEAAJPEFBU_ITEMID_CHILD@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z; CDelegateFolderBaseNoUI::_CreateAndInit(_ITEMID_CHILD const *,IBindCtx *,_GUID const &,void * *)
0x18003bc82  mov     esi, eax
0x18003bc84  test    eax, eax
0x18003bc86  js      short loc_18003BCB8
0x18003bc88  mov     rcx, [rbp+arg_20]
0x18003bc8c  mov     r9, r12
0x18003bc8f  mov     r8, r13
0x18003bc92  mov     [rsp+58h+var_38], r14
0x18003bc97  mov     rdx, rdi
0x18003bc9a  mov     rax, [rcx]
0x18003bc9d  mov     rax, [rax+28h]
0x18003bca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bca6  mov     rcx, [rbp+arg_20]
0x18003bcaa  mov     esi, eax
0x18003bcac  mov     rax, [rcx]
0x18003bcaf  mov     rax, [rax+10h]
0x18003bcb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcb8  mov     rcx, rbx; pidl
0x18003bcbb  call    cs:__imp_ILFree
0x18003bcc1  mov     eax, esi
0x18003bcc3  jmp     loc_18003BAB6
```
