# ReparseRelativeIDListInternal(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_GUID const &,IShellFolder *,ReparseRelativeIdListFlags,IBindCtx *,_ITEMIDLIST_RELATIVE * *)

- ea: `0x18002f6e0`
- end: `0x18002fba5`
- name: `?ReparseRelativeIDListInternal@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@0W4ReparseRelativeIdListFlags@@PEAUIBindCtx@@PEAPEAU2@@Z`
- size: `1221`
- prototype: `int __high(struct IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, const struct _GUID *, struct IShellFolder *, enum ReparseRelativeIdListFlags, struct IBindCtx *, struct _ITEMIDLIST_RELATIVE **)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18002ef54`

## callees

- `0x180006c80`
- `0x180006d74`
- `0x180014498`
- `0x18002f6e0`
- `0x18002fbac`
- `0x18002fe18`
- `0x1800546c0`
- `0x180071df0`
- `0x180072cd0`
- `0x180072cf4`
- `0x180082e04`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18002faa2`
- `SHCORE!IUnknown_Set` at `0x18002fb11`
- `SHCORE!IUnknown_Set` at `0x18002fb77`
- `SHCORE!IUnknown_Set` at `0x18002faa2`
- `SHCORE!IUnknown_Set` at `0x18002fb11`
- `SHCORE!IUnknown_Set` at `0x18002fb77`
- `SHCORE!__imp_StrRetToStrW` at `0x18002f876`
- `SHCORE!__imp_StrRetToStrW` at `0x18002f876`
- `Windows.Storage!ILFree` at `0x18002f786`
- `Windows.Storage!ILFree` at `0x18002f8f4`
- `Windows.Storage!ILFree` at `0x18002fa2b`
- `Windows.Storage!ILFree` at `0x18002fa55`
- `Windows.Storage!ILFree` at `0x18002fa5e`
- `Windows.Storage!ILFree` at `0x18002f786`
- `Windows.Storage!ILFree` at `0x18002f8f4`
- `Windows.Storage!ILFree` at `0x18002fa2b`
- `Windows.Storage!ILFree` at `0x18002fa55`
- `Windows.Storage!ILFree` at `0x18002fa5e`
- `Windows.Storage!ILCombine` at `0x18002fa3c`
- `Windows.Storage!ILCombine` at `0x18002fa3c`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f81e`
- `Windows.Storage!SHBindToFolderIDListParent` at `0x18002f81e`
- `Windows.Storage!ILCloneFirst` at `0x18002f7d9`
- `Windows.Storage!ILCloneFirst` at `0x18002f7d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f8ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReparseRelativeIDListInternal(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, IShellFolder **),
        const ITEMIDLIST *a2,
        const ITEMIDLIST *a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, IUnknown **),
        __int64 a5,
        IUnknown *ppunk,
        LPITEMIDLIST a7)
{
  LPCITEMIDLIST *v9; // rsi
  HRESULT ParsingBindCtx; // ebx
  LPITEMIDLIST v12; // r12
  LPCITEMIDLIST v13; // rcx
  LPCITEMIDLIST v14; // r14
  IUnknown *v15; // rax
  CDummyUnknown *v16; // rbx
  __int64 v17; // rdx
  ITEMIDLIST *v18; // r14
  ITEMIDLIST *v19; // r15
  LPITEMIDLIST v20; // rax
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR ppsz; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *punk[2]; // [rsp+50h] [rbp-B0h] BYREF
  GUID Buf2; // [rsp+60h] [rbp-A0h] BYREF
  STRRET pstr; // [rsp+70h] [rbp-90h] BYREF
  IShellFolder *psfRoot; // [rsp+1C0h] [rbp+C0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+1D0h] [rbp+D0h] BYREF

  pidl = a3;
  v9 = (LPCITEMIDLIST *)a7;
  *(_QWORD *)&a7->mkid.cb = 0;
  psfRoot = 0;
  ParsingBindCtx = (**a1)(a1, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &psfRoot);
  if ( ParsingBindCtx >= 0 )
  {
    ppunk = 0;
    ParsingBindCtx = (**a4)(a4, &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1, &ppunk);
    if ( ParsingBindCtx >= 0 )
    {
      Buf2 = GUID_NULL;
      while ( a2 && a2->mkid.cb )
      {
        if ( ParsingBindCtx < 0 )
          goto LABEL_7;
        v12 = ILCloneFirst(a2);
        if ( v12 )
        {
          ppsz = 0;
          ppv = 0;
          pidl = 0;
          ParsingBindCtx = SHBindToFolderIDListParent(
                             psfRoot,
                             v12,
                             &GUID_000214e6_0000_0000_c000_000000000046,
                             &ppv,
                             &pidl);
          if ( ParsingBindCtx >= 0 )
          {
            memset_0(&pstr, 0, sizeof(pstr));
            ParsingBindCtx = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, __int64, STRRET *))(*(_QWORD *)ppv + 88LL))(
                               ppv,
                               pidl,
                               32769,
                               &pstr);
            if ( ParsingBindCtx >= 0 )
              ParsingBindCtx = StrRetToStrW(&pstr, pidl, &ppsz);
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          if ( ParsingBindCtx >= 0 )
          {
            pidl = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pidl);
            ParsingBindCtx = GetParsingBindCtx(
                               (struct IShellFolder2 *)psfRoot,
                               (const struct _ITEMID_CHILD *)v12,
                               0,
                               (struct IBindCtx **)&pidl);
            if ( ParsingBindCtx >= 0 )
            {
              v14 = pidl;
              v15 = (IUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
              punk[0] = v15;
              if ( v15 )
              {
                v16 = CDummyUnknown::CDummyUnknown((CDummyUnknown *)v15);
                if ( v16 )
                {
                  (*(void (__fastcall **)(LPCITEMIDLIST, const wchar_t *, CDummyUnknown *))(*(_QWORD *)&v14->mkid.cb
                                                                                          + 72LL))(
                    v14,
                    L"ValidateRegItems",
                    v16);
                  CDummyUnknown::Release(v16);
                }
              }
              if ( (unsigned int)ILIsChild((const struct _ITEMIDLIST_RELATIVE *)a2) )
              {
                if ( memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
                {
                  ppv = 0;
                  *(GUID *)punk = GUID_NULL;
                  if ( (int)_CreatePropertyBagBindCtx<_GUID>(
                              (struct IBindCtx *)pidl,
                              v17,
                              (const GUID *)punk,
                              (LPBC *)&ppv) >= 0 )
                  {
                    IUnknown_Set((IUnknown **)&pidl, (IUnknown *)ppv);
                    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                  }
                }
              }
              a7 = 0;
              ParsingBindCtx = ((__int64 (__fastcall *)(IUnknown *, _QWORD, LPCITEMIDLIST, LPWSTR, _QWORD, LPITEMIDLIST *, _QWORD))ppunk->lpVtbl[1].QueryInterface)(
                                 ppunk,
                                 0,
                                 pidl,
                                 ppsz,
                                 0,
                                 &a7,
                                 0);
              if ( ParsingBindCtx >= 0 )
              {
                if ( (unsigned int)ILIsChild((const struct _ITEMIDLIST_RELATIVE *)a2) )
                {
                  v18 = a7;
                  v19 = (ITEMIDLIST *)*v9;
                  if ( a7 && v19 )
                  {
                    v20 = ILCombine(*v9, a7);
                    *v9 = v20;
                    ParsingBindCtx = v20 == 0 ? 0x8007000E : 0;
                    ILFree(v19);
                    ILFree(v18);
                  }
                  else
                  {
                    ParsingBindCtx = 0;
                    if ( !v19 )
                    {
                      if ( a7 )
                        *v9 = a7;
                      else
                        ParsingBindCtx = -2147024809;
                    }
                  }
                  a7 = 0;
                }
                else
                {
                  punk[0] = 0;
                  ParsingBindCtx = ((__int64 (__fastcall *)(IUnknown *, LPITEMIDLIST, _QWORD, GUID *, IUnknown **))ppunk->lpVtbl[1].Release)(
                                     ppunk,
                                     a7,
                                     0,
                                     &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                                     punk);
                  if ( ParsingBindCtx >= 0 )
                  {
                    IUnknown_Set(&ppunk, punk[0]);
                    ParsingBindCtx = _ILCombineAndFree((LPITEMIDLIST)*v9, a7, (struct _ITEMIDLIST_RELATIVE **)v9);
                    a7 = 0;
                    if ( ParsingBindCtx >= 0 )
                    {
                      ppv = 0;
                      ParsingBindCtx = ((__int64 (__fastcall *)(IShellFolder *, LPITEMIDLIST, _QWORD, GUID *, void **))psfRoot->lpVtbl->BindToObject)(
                                         psfRoot,
                                         v12,
                                         0,
                                         &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                                         &ppv);
                      if ( ParsingBindCtx >= 0 )
                      {
                        IUnknown_Set((IUnknown **)&psfRoot, (IUnknown *)ppv);
                        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                      }
                    }
                    ((void (__fastcall *)(IUnknown *))punk[0]->lpVtbl->Release)(punk[0]);
                  }
                }
                ILFree(a7);
              }
            }
            CoTaskMemFree(ppsz);
            v13 = pidl;
            if ( pidl )
            {
              pidl = 0;
              (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&v13->mkid.cb + 16LL))(v13);
            }
          }
          ILFree(v12);
        }
        else
        {
          ParsingBindCtx = -2147024882;
        }
        a2 = (const ITEMIDLIST *)((char *)a2 + a2->mkid.cb);
      }
      if ( ParsingBindCtx < 0 )
      {
LABEL_7:
        ILFree((LPITEMIDLIST)*v9);
        *v9 = 0;
        goto LABEL_8;
      }
      if ( !*v9 )
        ParsingBindCtx = -2147467259;
LABEL_8:
      ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
    }
    ((void (__fastcall *)(IShellFolder *))psfRoot->lpVtbl->Release)(psfRoot);
  }
  return (unsigned int)ParsingBindCtx;
}

```

## disassembly

```asm
0x18002f6e0  mov     [rsp-8+arg_8], rbx
0x18002f6e5  mov     [rsp-8+pidl], r8
0x18002f6ea  push    rbp
0x18002f6eb  push    rsi
0x18002f6ec  push    rdi
0x18002f6ed  push    r12
0x18002f6ef  push    r13
0x18002f6f1  push    r14
0x18002f6f3  push    r15
0x18002f6f5  lea     rbp, [rsp-80h]
0x18002f6fa  sub     rsp, 180h
0x18002f701  mov     r14, r9
0x18002f704  mov     rdi, rdx
0x18002f707  xor     r13d, r13d
0x18002f70a  mov     rsi, [rbp+0B0h+arg_30]
0x18002f711  mov     [rsi], r13
0x18002f714  mov     [rbp+0B0h+psfRoot], r13
0x18002f71b  mov     rax, [rcx]
0x18002f71e  lea     r8, [rbp+0B0h+psfRoot]
0x18002f725  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18002f72c  mov     rax, [rax]
0x18002f72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f734  mov     ebx, eax
0x18002f736  test    eax, eax
0x18002f738  js      short loc_18002F7B5
0x18002f73a  mov     [rbp+0B0h+ppunk], r13
0x18002f741  mov     rax, [r14]
0x18002f744  lea     r8, [rbp+0B0h+ppunk]
0x18002f74b  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18002f752  mov     rcx, r14
0x18002f755  mov     rax, [rax]
0x18002f758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f75d  mov     ebx, eax
0x18002f75f  test    eax, eax
0x18002f761  js      short loc_18002F7A2
0x18002f763  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002f76a  movdqu  [rsp+1B0h+Buf2], xmm0
0x18002f770  test    rdi, rdi
0x18002f773  jz      short loc_18002F77B
0x18002f775  cmp     [rdi], r13w
0x18002f779  jnz     short loc_18002F7D2
0x18002f77b  test    ebx, ebx
0x18002f77d  jns     loc_18002F90C
0x18002f783  mov     rcx, [rsi]; pidl
0x18002f786  call    cs:__imp_ILFree
0x18002f78c  mov     [rsi], r13
0x18002f78f  mov     rcx, [rbp+0B0h+ppunk]
0x18002f796  mov     rax, [rcx]
0x18002f799  mov     rax, [rax+10h]
0x18002f79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7a2  mov     rcx, [rbp+0B0h+psfRoot]
0x18002f7a9  mov     rax, [rcx]
0x18002f7ac  mov     rax, [rax+10h]
0x18002f7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7b5  mov     eax, ebx
0x18002f7b7  mov     rbx, [rsp+1B0h+arg_8]
0x18002f7bf  add     rsp, 180h
0x18002f7c6  pop     r15
0x18002f7c8  pop     r14
0x18002f7ca  pop     r13
0x18002f7cc  pop     r12
0x18002f7ce  pop     rdi
0x18002f7cf  pop     rsi
0x18002f7d0  pop     rbp
0x18002f7d1  retn
0x18002f7d2  test    ebx, ebx
0x18002f7d4  js      short loc_18002F783
0x18002f7d6  mov     rcx, rdi; pidl
0x18002f7d9  call    cs:__imp_ILCloneFirst
0x18002f7df  mov     r12, rax
0x18002f7e2  test    rax, rax
0x18002f7e5  jz      loc_18002F905
0x18002f7eb  mov     [rsp+1B0h+ppsz], r13
0x18002f7f0  mov     [rsp+1B0h+ppv], r13
0x18002f7f5  mov     [rbp+0B0h+pidl], r13
0x18002f7fc  lea     rax, [rbp+0B0h+pidl]
0x18002f803  mov     [rsp+1B0h+ppidlLast], rax; ppidlLast
0x18002f808  lea     r9, [rsp+1B0h+ppv]; ppv
0x18002f80d  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002f814  mov     rdx, r12; pidl
0x18002f817  mov     rcx, [rbp+0B0h+psfRoot]; psfRoot
0x18002f81e  call    cs:__imp_SHBindToFolderIDListParent
0x18002f824  mov     ebx, eax
0x18002f826  test    eax, eax
0x18002f828  js      short loc_18002F88F
0x18002f82a  xor     edx, edx; Val
0x18002f82c  mov     r8d, 110h; Size
0x18002f832  lea     rcx, [rsp+1B0h+pstr]; void *
0x18002f837  call    memset_0
0x18002f83c  mov     rcx, [rsp+1B0h+ppv]
0x18002f841  mov     rax, [rcx]
0x18002f844  lea     r9, [rsp+1B0h+pstr]
0x18002f849  mov     r8d, 8001h
0x18002f84f  mov     rdx, [rbp+0B0h+pidl]
0x18002f856  mov     rax, [rax+58h]
0x18002f85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f85f  mov     ebx, eax
0x18002f861  test    eax, eax
0x18002f863  js      short loc_18002F87E
0x18002f865  lea     r8, [rsp+1B0h+ppsz]; ppsz
0x18002f86a  mov     rdx, [rbp+0B0h+pidl]; pidl
0x18002f871  lea     rcx, [rsp+1B0h+pstr]; pstr
0x18002f876  call    cs:__imp_StrRetToStrW
0x18002f87c  mov     ebx, eax
0x18002f87e  mov     rcx, [rsp+1B0h+ppv]
0x18002f883  mov     rax, [rcx]
0x18002f886  mov     rax, [rax+10h]
0x18002f88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f88f  test    ebx, ebx
0x18002f891  js      short loc_18002F8F1
0x18002f893  mov     [rbp+0B0h+pidl], r13
0x18002f89a  lea     rcx, [rbp+0B0h+pidl]
0x18002f8a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f8a6  lea     r9, [rbp+0B0h+pidl]; struct IBindCtx **
0x18002f8ad  xor     r8d, r8d; int
0x18002f8b0  mov     rdx, r12; struct _ITEMID_CHILD *
0x18002f8b3  mov     rcx, [rbp+0B0h+psfRoot]; struct IShellFolder2 *
0x18002f8ba  call    ?GetParsingBindCtx@@YAJPEAUIShellFolder2@@PEFBU_ITEMID_CHILD@@HPEAPEAUIBindCtx@@@Z; GetParsingBindCtx(IShellFolder2 *,_ITEMID_CHILD const *,int,IBindCtx * *)
0x18002f8bf  mov     ebx, eax
0x18002f8c1  test    eax, eax
0x18002f8c3  jns     short loc_18002F91F
0x18002f8c5  mov     rcx, [rsp+1B0h+ppsz]; pv
0x18002f8ca  call    cs:__imp_CoTaskMemFree
0x18002f8d0  nop
0x18002f8d1  mov     rcx, [rbp+0B0h+pidl]
0x18002f8d8  test    rcx, rcx
0x18002f8db  jz      short loc_18002F8F1
0x18002f8dd  mov     [rbp+0B0h+pidl], r13
0x18002f8e4  mov     rax, [rcx]
0x18002f8e7  mov     rax, [rax+10h]
0x18002f8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8f0  nop
0x18002f8f1  mov     rcx, r12; pidl
0x18002f8f4  call    cs:__imp_ILFree
0x18002f8fa  movzx   eax, word ptr [rdi]
0x18002f8fd  add     rdi, rax
0x18002f900  jmp     loc_18002F770
0x18002f905  mov     ebx, 8007000Eh
0x18002f90a  jmp     short loc_18002F8FA
0x18002f90c  cmp     [rsi], r13
0x18002f90f  jnz     loc_18002F78F
0x18002f915  mov     ebx, 80004005h
0x18002f91a  jmp     loc_18002F78F
0x18002f91f  mov     r14, [rbp+0B0h+pidl]
0x18002f926  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f92d  mov     ecx, 40h ; '@'; unsigned __int64
0x18002f932  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002f937  mov     [rsp+1B0h+punk], rax
0x18002f93c  test    rax, rax
0x18002f93f  jz      short loc_18002F972
0x18002f941  mov     rcx, rax; this
0x18002f944  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x18002f949  mov     rbx, rax
0x18002f94c  test    rax, rax
0x18002f94f  jz      short loc_18002F972
0x18002f951  mov     rdx, [r14]
0x18002f954  mov     rax, [rdx+48h]
0x18002f958  mov     r8, rbx
0x18002f95b  lea     rdx, aValidateregite; "ValidateRegItems"
0x18002f962  mov     rcx, r14
0x18002f965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f96a  mov     rcx, rbx; this
0x18002f96d  call    ?Release@CDummyUnknown@@UEAAKXZ; CDummyUnknown::Release(void)
0x18002f972  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x18002f975  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x18002f97a  test    eax, eax
0x18002f97c  jz      short loc_18002F99D
0x18002f97e  mov     r8d, 10h; Size
0x18002f984  lea     rdx, [rsp+1B0h+Buf2]; Buf2
0x18002f989  lea     rcx, GUID_NULL; Buf1
0x18002f990  call    memcmp_0
0x18002f995  test    eax, eax
0x18002f997  jnz     loc_18002FA66
0x18002f99d  mov     [rbp+0B0h+arg_30], r13
0x18002f9a4  mov     rcx, [rbp+0B0h+ppunk]
0x18002f9ab  mov     rax, [rcx]
0x18002f9ae  mov     [rsp+1B0h+var_180], r13
0x18002f9b3  lea     rdx, [rbp+0B0h+arg_30]
0x18002f9ba  mov     [rsp+1B0h+var_188], rdx
0x18002f9bf  mov     [rsp+1B0h+ppidlLast], r13
0x18002f9c4  mov     r9, [rsp+1B0h+ppsz]
0x18002f9c9  mov     r8, [rbp+0B0h+pidl]
0x18002f9d0  xor     edx, edx
0x18002f9d2  mov     rax, [rax+18h]
0x18002f9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9db  mov     ebx, eax
0x18002f9dd  test    eax, eax
0x18002f9df  js      loc_18002F8C5
0x18002f9e5  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x18002f9e8  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x18002f9ed  test    eax, eax
0x18002f9ef  jz      loc_18002FAC8
0x18002f9f5  mov     r14, [rbp+0B0h+arg_30]
0x18002f9fc  mov     r15, [rsi]
0x18002f9ff  test    r14, r14
0x18002fa02  jz      short loc_18002FA09
0x18002fa04  test    r15, r15
0x18002fa07  jnz     short loc_18002FA36
0x18002fa09  mov     ebx, r13d
0x18002fa0c  test    r15, r15
0x18002fa0f  jnz     short loc_18002FA1D
0x18002fa11  test    r14, r14
0x18002fa14  jz      loc_18002FABE
0x18002fa1a  mov     [rsi], r14
0x18002fa1d  mov     [rbp+0B0h+arg_30], r13
0x18002fa24  mov     rcx, [rbp+0B0h+arg_30]; pidl
0x18002fa2b  call    cs:__imp_ILFree
0x18002fa31  jmp     loc_18002F8C5
0x18002fa36  mov     rdx, r14; pidl2
0x18002fa39  mov     rcx, r15; pidl1
0x18002fa3c  call    cs:__imp_ILCombine
0x18002fa42  mov     [rsi], rax
0x18002fa45  neg     rax
0x18002fa48  sbb     ebx, ebx
0x18002fa4a  not     ebx
0x18002fa4c  and     ebx, 8007000Eh
0x18002fa52  mov     rcx, r15; pidl
0x18002fa55  call    cs:__imp_ILFree
0x18002fa5b  mov     rcx, r14; pidl
0x18002fa5e  call    cs:__imp_ILFree
0x18002fa64  jmp     short loc_18002FA1D
0x18002fa66  mov     [rsp+1B0h+ppv], r13
0x18002fa6b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002fa72  movdqu  xmmword ptr [rsp+1B0h+punk], xmm0
0x18002fa78  lea     r9, [rsp+1B0h+ppv]
0x18002fa7d  lea     r8, [rsp+1B0h+punk]
0x18002fa82  mov     rcx, [rbp+0B0h+pidl]; struct IBindCtx *
0x18002fa89  call    ??$_CreatePropertyBagBindCtx@U_GUID@@@@YAJPEAUIBindCtx@@PEBGU_GUID@@PEAPEAU0@@Z; _CreatePropertyBagBindCtx<_GUID>(IBindCtx *,ushort const *,_GUID,IBindCtx * *)
0x18002fa8e  test    eax, eax
0x18002fa90  js      loc_18002F99D
0x18002fa96  mov     rdx, [rsp+1B0h+ppv]; punk
0x18002fa9b  lea     rcx, [rbp+0B0h+pidl]; ppunk
0x18002faa2  call    cs:__imp_IUnknown_Set
0x18002faa8  mov     rcx, [rsp+1B0h+ppv]
0x18002faad  mov     rax, [rcx]
0x18002fab0  mov     rax, [rax+10h]
0x18002fab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fab9  jmp     loc_18002F99D
0x18002fabe  mov     ebx, 80070057h
0x18002fac3  jmp     loc_18002FA1D
0x18002fac8  mov     [rsp+1B0h+punk], r13
0x18002facd  mov     rcx, [rbp+0B0h+ppunk]
0x18002fad4  mov     rax, [rcx]
0x18002fad7  lea     rdx, [rsp+1B0h+punk]
0x18002fadc  mov     [rsp+1B0h+ppidlLast], rdx
0x18002fae1  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18002fae8  xor     r8d, r8d
0x18002faeb  mov     rdx, [rbp+0B0h+arg_30]
0x18002faf2  mov     rax, [rax+28h]
0x18002faf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fafb  mov     ebx, eax
0x18002fafd  test    eax, eax
0x18002faff  js      loc_18002FA24
0x18002fb05  mov     rdx, [rsp+1B0h+punk]; punk
0x18002fb0a  lea     rcx, [rbp+0B0h+ppunk]; ppunk
0x18002fb11  call    cs:__imp_IUnknown_Set
0x18002fb17  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE **
0x18002fb1a  mov     rdx, [rbp+0B0h+arg_30]; LPITEMIDLIST
0x18002fb21  mov     rcx, [rsi]; pidl
0x18002fb24  call    ?_ILCombineAndFree@@YAJPEAU_ITEMIDLIST_RELATIVE@@0PEAPEAU1@@Z; _ILCombineAndFree(_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE *,_ITEMIDLIST_RELATIVE * *)
0x18002fb29  mov     ebx, eax
0x18002fb2b  mov     [rbp+0B0h+arg_30], r13
0x18002fb32  test    eax, eax
0x18002fb34  js      short loc_18002FB8E
0x18002fb36  mov     [rsp+1B0h+ppv], r13
0x18002fb3b  mov     rcx, [rbp+0B0h+psfRoot]
0x18002fb42  mov     rax, [rcx]
0x18002fb45  lea     rdx, [rsp+1B0h+ppv]
0x18002fb4a  mov     [rsp+1B0h+ppidlLast], rdx
0x18002fb4f  lea     r9, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x18002fb56  xor     r8d, r8d
0x18002fb59  mov     rdx, r12
0x18002fb5c  mov     rax, [rax+28h]
0x18002fb60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb65  mov     ebx, eax
0x18002fb67  test    eax, eax
0x18002fb69  js      short loc_18002FB8E
0x18002fb6b  mov     rdx, [rsp+1B0h+ppv]; punk
0x18002fb70  lea     rcx, [rbp+0B0h+psfRoot]; ppunk
0x18002fb77  call    cs:__imp_IUnknown_Set
0x18002fb7d  mov     rcx, [rsp+1B0h+ppv]
0x18002fb82  mov     rax, [rcx]
0x18002fb85  mov     rax, [rax+10h]
0x18002fb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb8e  mov     rcx, [rsp+1B0h+punk]
0x18002fb93  mov     rax, [rcx]
0x18002fb96  mov     rax, [rax+10h]
0x18002fb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb9f  jmp     loc_18002FA24
```
