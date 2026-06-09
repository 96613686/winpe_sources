# CDelegateFolderBaseNoUI::_CreateAndInit(_ITEMID_CHILD const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x18003b5f0`
- end: `0x18003b8f6`
- name: `?_CreateAndInit@CDelegateFolderBaseNoUI@@AEAAJPEFBU_ITEMID_CHILD@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `774`
- prototype: `__int64 __fastcall(CDelegateFolderBaseNoUI *__hidden this, const struct _ITEMID_CHILD *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003b470`
- `0x18003b900`

## callees

- `0x18003b5f0`
- `0x1800c1ff8`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x18003b77c`
- `Windows.Storage!ILFree` at `0x18003b77c`
- `Windows.Storage!ILCombine` at `0x18003b614`
- `Windows.Storage!ILCombine` at `0x18003b614`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003b66f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003b876`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003b66f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003b876`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18003b836`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x18003b836`

## pseudocode

```c
__int64 __fastcall CDelegateFolderBaseNoUI::_CreateAndInit(
        LPCITEMIDLIST *this,
        const struct _ITEMID_CHILD *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **a5)
{
  ITEMIDLIST *v9; // r15
  unsigned __int64 v10; // rdx
  __int64 v11; // rdi
  HRESULT v12; // ebx
  LPCITEMIDLIST v13; // rax
  struct IBindCtxVtbl *lpVtbl; // rax
  IPropertyBag *v16; // rdi
  int v17; // ebx
  __int64 v18; // rdx
  char *v19; // r14
  void *ppv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v21; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+40h] [rbp-10h] BYREF
  void *value; // [rsp+80h] [rbp+30h] BYREF

  v9 = ILCombine(this[6], (LPCITEMIDLIST)a2);
  if ( !v9 )
    return 2147942414LL;
  ppv = 0;
  if ( !a2 )
    goto LABEL_6;
  v10 = *(unsigned __int16 *)a2;
  if ( (unsigned int)v10 < 0x12 )
    goto LABEL_6;
  if ( *(_DWORD *)((char *)a2 + 6) != 597942229 )
    goto LABEL_6;
  v11 = *((unsigned __int16 *)a2 + 5);
  if ( v10 < v11 + 18 )
    goto LABEL_6;
  if ( !(_WORD)v11 )
    goto LABEL_6;
  v19 = (char *)a2 + 18;
  if ( a2 == (const struct _ITEMID_CHILD *)-18LL )
    goto LABEL_6;
  value = 0;
  v12 = PSCreateMemoryPropertyStore(&GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &value);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(void *, char *, _QWORD))(*(_QWORD *)value + 32LL))(value, v19, (unsigned int)v11);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)value + 24LL))(value, 1);
      if ( v12 >= 0 )
        v12 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))value)(
                value,
                &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                &ppv);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)value + 16LL))(value);
  }
  if ( v12 == -2147024809 )
LABEL_6:
    v12 = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
  if ( v12 >= 0 )
  {
    v12 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, void *, struct IBindCtx *))((char *)&(*this)[21].mkid.cb + 1))(
            this,
            ppv,
            a3);
    if ( v12 >= 0 )
    {
      if ( a3 )
      {
        lpVtbl = a3->lpVtbl;
        v16 = (IPropertyBag *)ppv;
        v22 = 0;
        value = 0;
        if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, void **))lpVtbl->GetObjectParam)(
               a3,
               L"ProgressAggregatorProvider",
               &value) >= 0 )
        {
          v17 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))value)(
                  value,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  &v22);
          (*(void (__fastcall **)(void *))(*(_QWORD *)value + 16LL))(value);
          if ( v17 >= 0 )
          {
            LODWORD(value) = 0;
            if ( (int)IUnknown_GetCookieFromProvider(v22, v18, &value) >= 0 )
              PSPropertyBag_WriteDWORD(v16, L"AggregatorCookie", (DWORD)value);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          }
        }
      }
      v13 = *this;
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(LPCITEMIDLIST *, void *, GUID *, __int64 *))v13[18].mkid.abID)(
              this,
              ppv,
              &GUID_37d84f60_42cb_11ce_8135_00aa004bb851,
              &v21);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v21 + 40LL))(v21, ppv, 0);
        if ( v12 >= 0 )
        {
          value = 0;
          v12 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v21)(
                  v21,
                  &GUID_000214ea_0000_0000_c000_000000000046,
                  &value);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(void *, ITEMIDLIST *))(*(_QWORD *)value + 32LL))(value, v9);
            if ( v12 >= 0 )
              v12 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v21)(v21, a4, a5);
            (*(void (__fastcall **)(void *))(*(_QWORD *)value + 16LL))(value);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  ILFree(v9);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18003b5f0  mov     [rsp-28h+arg_18], rbx
0x18003b5f5  push    rbp
0x18003b5f6  push    rsi
0x18003b5f7  push    r12
0x18003b5f9  push    r13
0x18003b5fb  push    r15
0x18003b5fd  mov     rbp, rsp
0x18003b600  sub     rsp, 50h
0x18003b604  mov     rsi, rcx
0x18003b607  mov     r13, r9
0x18003b60a  mov     rcx, [rcx+30h]; pidl1
0x18003b60e  mov     r12, r8
0x18003b611  mov     rbx, rdx
0x18003b614  call    cs:__imp_ILCombine
0x18003b61a  mov     r15, rax
0x18003b61d  test    rax, rax
0x18003b620  jz      loc_18003B7A9
0x18003b626  xor     r8d, r8d
0x18003b629  mov     [rsp+50h+arg_8], rdi
0x18003b631  mov     [rsp+50h+arg_10], r14
0x18003b639  mov     [rbp+ppv], r8
0x18003b63d  test    rbx, rbx
0x18003b640  jz      short loc_18003B664
0x18003b642  movzx   edx, word ptr [rbx]
0x18003b645  cmp     edx, 12h
0x18003b648  jb      short loc_18003B664
0x18003b64a  cmp     dword ptr [rbx+6], 23A3DFD5h
0x18003b651  jnz     short loc_18003B664
0x18003b653  movzx   edi, word ptr [rbx+0Ah]
0x18003b657  lea     rcx, [rdi+12h]
0x18003b65b  cmp     rdx, rcx
0x18003b65e  jnb     loc_18003B851
0x18003b664  lea     rdx, [rbp+ppv]; ppv
0x18003b668  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18003b66f  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003b675  mov     ebx, eax
0x18003b677  test    ebx, ebx
0x18003b679  js      loc_18003B779
0x18003b67f  mov     rax, [rsi]
0x18003b682  mov     r8, r12
0x18003b685  mov     rdx, [rbp+ppv]
0x18003b689  mov     rcx, rsi
0x18003b68c  mov     rax, [rax+40h]
0x18003b690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b695  mov     ebx, eax
0x18003b697  test    eax, eax
0x18003b699  js      loc_18003B769
0x18003b69f  xor     r14d, r14d
0x18003b6a2  test    r12, r12
0x18003b6a5  jnz     loc_18003B7B0
0x18003b6ab  mov     rax, [rsi]
0x18003b6ae  lea     r9, [rbp+var_18]
0x18003b6b2  mov     rdx, [rbp+ppv]
0x18003b6b6  lea     r8, _GUID_37d84f60_42cb_11ce_8135_00aa004bb851
0x18003b6bd  mov     rcx, rsi
0x18003b6c0  mov     [rbp+var_18], r14
0x18003b6c4  mov     rax, [rax+38h]
0x18003b6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6cd  mov     ebx, eax
0x18003b6cf  test    eax, eax
0x18003b6d1  js      loc_18003B769
0x18003b6d7  mov     rcx, [rbp+var_18]
0x18003b6db  xor     r8d, r8d
0x18003b6de  mov     rdx, [rbp+ppv]
0x18003b6e2  mov     rax, [rcx]
0x18003b6e5  mov     rax, [rax+28h]
0x18003b6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6ee  mov     ebx, eax
0x18003b6f0  test    eax, eax
0x18003b6f2  js      short loc_18003B759
0x18003b6f4  mov     rcx, [rbp+var_18]
0x18003b6f8  lea     r8, [rbp+value]
0x18003b6fc  mov     [rbp+value], r14
0x18003b700  lea     rdx, _GUID_000214ea_0000_0000_c000_000000000046
0x18003b707  mov     rax, [rcx]
0x18003b70a  mov     rax, [rax]
0x18003b70d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b712  mov     ebx, eax
0x18003b714  test    eax, eax
0x18003b716  js      short loc_18003B759
0x18003b718  mov     rcx, [rbp+value]
0x18003b71c  mov     rdx, r15
0x18003b71f  mov     rax, [rcx]
0x18003b722  mov     rax, [rax+20h]
0x18003b726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b72b  mov     ebx, eax
0x18003b72d  test    eax, eax
0x18003b72f  js      short loc_18003B749
0x18003b731  mov     rcx, [rbp+var_18]
0x18003b735  mov     rdx, r13
0x18003b738  mov     r8, [rbp+arg_20]
0x18003b73c  mov     rax, [rcx]
0x18003b73f  mov     rax, [rax]
0x18003b742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b747  mov     ebx, eax
0x18003b749  mov     rcx, [rbp+value]
0x18003b74d  mov     rax, [rcx]
0x18003b750  mov     rax, [rax+10h]
0x18003b754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b759  mov     rcx, [rbp+var_18]
0x18003b75d  mov     rax, [rcx]
0x18003b760  mov     rax, [rax+10h]
0x18003b764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b769  mov     rcx, [rbp+ppv]
0x18003b76d  mov     rax, [rcx]
0x18003b770  mov     rax, [rax+10h]
0x18003b774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b779  mov     rcx, r15; pidl
0x18003b77c  call    cs:__imp_ILFree
0x18003b782  mov     r14, [rsp+50h+arg_10]
0x18003b78a  mov     eax, ebx
0x18003b78c  mov     rdi, [rsp+50h+arg_8]
0x18003b794  mov     rbx, [rsp+50h+arg_18]
0x18003b79c  add     rsp, 50h
0x18003b7a0  pop     r15
0x18003b7a2  pop     r13
0x18003b7a4  pop     r12
0x18003b7a6  pop     rsi
0x18003b7a7  pop     rbp
0x18003b7a8  retn
0x18003b7a9  mov     eax, 8007000Eh
0x18003b7ae  jmp     short loc_18003B794
0x18003b7b0  mov     rax, [r12]
0x18003b7b4  lea     r8, [rbp+value]
0x18003b7b8  mov     rdi, [rbp+ppv]
0x18003b7bc  lea     rdx, aProgressaggreg; "ProgressAggregatorProvider"
0x18003b7c3  mov     rcx, r12
0x18003b7c6  mov     [rbp+var_10], r14
0x18003b7ca  mov     [rbp+value], r14
0x18003b7ce  mov     rax, [rax+50h]
0x18003b7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7d7  test    eax, eax
0x18003b7d9  js      loc_18003B6AB
0x18003b7df  mov     rcx, [rbp+value]
0x18003b7e3  lea     r8, [rbp+var_10]
0x18003b7e7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003b7ee  mov     rax, [rcx]
0x18003b7f1  mov     rax, [rax]
0x18003b7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7f9  mov     rcx, [rbp+value]
0x18003b7fd  mov     ebx, eax
0x18003b7ff  mov     rdx, [rcx]
0x18003b802  mov     rax, [rdx+10h]
0x18003b806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b80b  test    ebx, ebx
0x18003b80d  js      loc_18003B6AB
0x18003b813  mov     rcx, [rbp+var_10]
0x18003b817  lea     r8, [rbp+value]
0x18003b81b  mov     dword ptr [rbp+value], r14d
0x18003b81f  call    IUnknown_GetCookieFromProvider
0x18003b824  test    eax, eax
0x18003b826  js      short loc_18003B83C
0x18003b828  mov     r8d, dword ptr [rbp+value]; value
0x18003b82c  lea     rdx, aAggregatorcook; "AggregatorCookie"
0x18003b833  mov     rcx, rdi; propBag
0x18003b836  call    cs:__imp_PSPropertyBag_WriteDWORD
0x18003b83c  mov     rcx, [rbp+var_10]
0x18003b840  mov     rax, [rcx]
0x18003b843  mov     rax, [rax+10h]
0x18003b847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b84c  jmp     loc_18003B6AB
0x18003b851  test    di, di
0x18003b854  jz      loc_18003B664
0x18003b85a  lea     r14, [rbx+12h]
0x18003b85e  test    r14, r14
0x18003b861  jz      loc_18003B664
0x18003b867  lea     rdx, [rbp+value]; ppv
0x18003b86b  mov     [rbp+value], r8
0x18003b86f  lea     rcx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x18003b876  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003b87c  mov     ebx, eax
0x18003b87e  test    eax, eax
0x18003b880  js      short loc_18003B8E5
0x18003b882  mov     rcx, [rbp+value]
0x18003b886  mov     r8d, edi
0x18003b889  mov     rdx, r14
0x18003b88c  mov     rax, [rcx]
0x18003b88f  mov     rax, [rax+20h]
0x18003b893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b898  mov     ebx, eax
0x18003b89a  test    eax, eax
0x18003b89c  js      short loc_18003B8D5
0x18003b89e  mov     rcx, [rbp+value]
0x18003b8a2  mov     edx, 1
0x18003b8a7  mov     rax, [rcx]
0x18003b8aa  mov     rax, [rax+18h]
0x18003b8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8b3  mov     ebx, eax
0x18003b8b5  test    eax, eax
0x18003b8b7  js      short loc_18003B8D5
0x18003b8b9  mov     rcx, [rbp+value]
0x18003b8bd  lea     r8, [rbp+ppv]
0x18003b8c1  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18003b8c8  mov     rax, [rcx]
0x18003b8cb  mov     rax, [rax]
0x18003b8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8d3  mov     ebx, eax
0x18003b8d5  mov     rcx, [rbp+value]
0x18003b8d9  mov     rax, [rcx]
0x18003b8dc  mov     rax, [rax+10h]
0x18003b8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8e5  cmp     ebx, 80070057h
0x18003b8eb  jnz     loc_18003B677
0x18003b8f1  jmp     loc_18003B664
```
