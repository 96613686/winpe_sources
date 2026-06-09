# GetExtractIconW(IShellFolder *,_ITEMID_CHILD const *,uint,IExtractIconW * *)

- ea: `0x1800333b8`
- end: `0x1800336a4`
- name: `?GetExtractIconW@@YAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@IPEAPEAUIExtractIconW@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(IShellFolder *psfParent, LPCITEMIDLIST pidl, unsigned int, struct IExtractIconW **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800369b0`

## callees

- `0x180007f44`
- `0x18000d5e8`
- `0x180031470`
- `0x180031758`
- `0x1800333b8`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateItemWithParent` at `0x180033415`
- `SHELL32!SHCreateItemWithParent` at `0x180033415`
- `ole32!CreateBindCtx` at `0x18003343b`
- `ole32!CreateBindCtx` at `0x18003343b`

## pseudocode

```c
__int64 __fastcall GetExtractIconW(IShellFolder *psfParent, LPCITEMIDLIST pidl, __int16 a3, struct IExtractIconW **a4)
{
  LPBC v7; // rdx
  HRESULT v8; // ebx
  LPBC v9; // rbx
  CDummyUnknown *v10; // rax
  struct IShellFolderVtbl *lpVtbl; // rax
  struct IExtractIconW *v12; // rax
  struct IExtractIconW *v13; // rbx
  LPBC v14; // rcx
  struct IExtractIconW *v15; // rbx
  LPBC ppbc; // [rsp+40h] [rbp-40h] BYREF
  struct IExtractIconW *v18; // [rsp+48h] [rbp-38h] BYREF
  void *ppvItem; // [rsp+50h] [rbp-30h] BYREF
  LPCITEMIDLIST v20; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-20h] BYREF

  v20 = pidl;
  v18 = 0;
  if ( !pidl )
  {
    v8 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, _QWORD, _QWORD, GUID *, _QWORD, struct IExtractIconW **))psfParent->lpVtbl->GetUIObjectOf)(
           psfParent,
           0,
           0,
           0,
           &GUID_000214fa_0000_0000_c000_000000000046,
           0,
           &v18);
    goto LABEL_16;
  }
  ppvItem = 0;
  if ( SHCreateItemWithParent(0, psfParent, pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppvItem) >= 0 )
  {
    v7 = 0;
    ppbc = 0;
    if ( (a3 & 0x820) != 0 )
    {
      v8 = CreateBindCtx(0, &ppbc);
      if ( v8 < 0 )
      {
LABEL_14:
        SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)&ppbc);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
LABEL_16:
        if ( v8 >= 0 && v18 )
          goto LABEL_28;
        goto LABEL_18;
      }
      v21[0] = 16;
      v21[1] = 0;
      v8 = ((__int64 (__fastcall *)(LPBC, _QWORD *))ppbc->lpVtbl->SetBindOptions)(ppbc, v21);
      if ( v8 < 0 )
      {
        SafeRelease<ISyncMgrSyncItemContainer>((__int64 *)&ppbc);
        goto LABEL_14;
      }
      v9 = ppbc;
      v10 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v10 && (v21[0] = CDummyUnknown::CDummyUnknown(v10)) != 0 )
      {
        v8 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, _QWORD))v9->lpVtbl->RegisterObjectParam)(
               v9,
               L"GetAsyncHandler",
               v21[0]);
        SafeRelease<CDummyUnknown>(v21);
      }
      else
      {
        v8 = -2147024882;
      }
      if ( v8 < 0 )
        goto LABEL_14;
      v7 = ppbc;
    }
    v8 = (*(__int64 (__fastcall **)(void *, LPBC, const GUID *, GUID *, struct IExtractIconW **))(*(_QWORD *)ppvItem
                                                                                                + 24LL))(
           ppvItem,
           v7,
           &BHID_ThumbnailHandler,
           &GUID_000214fa_0000_0000_c000_000000000046,
           &v18);
    goto LABEL_14;
  }
LABEL_18:
  if ( v20 && (a3 & 0x20) != 0 )
  {
    v8 = -2147483638;
  }
  else
  {
    lpVtbl = psfParent->lpVtbl;
    ppbc = 0;
    v8 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, bool, unsigned __int64, GUID *, _QWORD, LPBC *))lpVtbl->GetUIObjectOf)(
           psfParent,
           0,
           v20 != 0,
           (unsigned __int64)&v20 & -(__int64)(v20 != 0),
           &GUID_000214eb_0000_0000_c000_000000000046,
           0,
           &ppbc);
    if ( v8 >= 0 )
    {
      if ( ppbc )
      {
        v12 = (struct IExtractIconW *)operator new(0x128u, (const struct std::nothrow_t *)&std::nothrow);
        v13 = v12;
        if ( v12 )
        {
          v14 = ppbc;
          v12->lpVtbl = (struct IExtractIconWVtbl *)&CExtractIconWForA::`vftable'{for `IExtractIconA'};
          v12[1].lpVtbl = (struct IExtractIconWVtbl *)&CExtractIconWForA::`vftable'{for `IExtractIconW'};
          LODWORD(v12[2].lpVtbl) = 1;
          v12[3].lpVtbl = (struct IExtractIconWVtbl *)v14;
          ((void (__fastcall *)(LPBC))v14->lpVtbl->AddRef)(v14);
          memset_0(&v13[4], 0, 0x104u);
          _InterlockedIncrement(&g_cRefThisDll);
          v15 = v13 + 1;
        }
        else
        {
          v15 = 0;
        }
        v18 = v15;
        v8 = v15 == 0 ? 0x8007000E : 0;
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      else
      {
        v8 = -2147467259;
      }
    }
  }
LABEL_28:
  *a4 = v18;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800333b8  push    rbp
0x1800333ba  push    rbx
0x1800333bb  push    rsi
0x1800333bc  push    rdi
0x1800333bd  push    r14
0x1800333bf  mov     rbp, rsp
0x1800333c2  sub     rsp, 80h
0x1800333c9  mov     rax, cs:__security_cookie
0x1800333d0  xor     rax, rsp
0x1800333d3  mov     [rbp+var_10], rax
0x1800333d7  mov     [rbp+var_28], rdx
0x1800333db  mov     r14, r9
0x1800333de  mov     [rbp+var_38], 0
0x1800333e6  mov     esi, r8d
0x1800333e9  mov     rdi, rcx
0x1800333ec  test    rdx, rdx
0x1800333ef  jz      loc_180033528
0x1800333f5  mov     r8, rdx; pidl
0x1800333f8  mov     [rbp+var_30], 0
0x180033400  mov     rdx, rcx; psfParent
0x180033403  lea     rax, [rbp+var_30]
0x180033407  xor     ecx, ecx; pidlParent
0x180033409  mov     [rsp+80h+ppvItem], rax; ppvItem
0x18003340e  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180033415  call    cs:__imp_SHCreateItemWithParent
0x18003341b  test    eax, eax
0x18003341d  js      loc_18003356E
0x180033423  xor     edx, edx
0x180033425  mov     [rbp+ppbc], rdx
0x180033429  test    esi, 820h
0x18003342f  jz      loc_1800334E1
0x180033435  lea     rdx, [rbp+ppbc]; ppbc
0x180033439  xor     ecx, ecx; reserved
0x18003343b  call    cs:__imp_CreateBindCtx
0x180033441  mov     ebx, eax
0x180033443  test    eax, eax
0x180033445  js      loc_18003350A
0x18003344b  mov     rcx, [rbp+ppbc]
0x18003344f  lea     rdx, [rbp+var_20]
0x180033453  mov     [rbp+var_20], 10h
0x18003345b  mov     [rbp+var_18], 0
0x180033463  mov     rax, [rcx]
0x180033466  mov     rax, [rax+30h]
0x18003346a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003346f  mov     ebx, eax
0x180033471  test    eax, eax
0x180033473  jns     short loc_180033483
0x180033475  lea     rcx, [rbp+ppbc]
0x180033479  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x18003347e  jmp     loc_18003350A
0x180033483  mov     rbx, [rbp+ppbc]
0x180033487  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003348e  mov     ecx, 40h ; '@'; unsigned __int64
0x180033493  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033498  test    rax, rax
0x18003349b  jz      short loc_1800334D4
0x18003349d  mov     rcx, rax; this
0x1800334a0  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x1800334a5  mov     [rbp+var_20], rax
0x1800334a9  mov     r8, rax
0x1800334ac  test    rax, rax
0x1800334af  jz      short loc_1800334D4
0x1800334b1  mov     rcx, [rbx]
0x1800334b4  lea     rdx, aGetasynchandle; "GetAsyncHandler"
0x1800334bb  mov     rax, [rcx+48h]
0x1800334bf  mov     rcx, rbx
0x1800334c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800334c7  lea     rcx, [rbp+var_20]
0x1800334cb  mov     ebx, eax
0x1800334cd  call    ??$SafeRelease@VCDummyUnknown@@@@YAXPEAPEAVCDummyUnknown@@@Z; SafeRelease<CDummyUnknown>(CDummyUnknown * *)
0x1800334d2  jmp     short loc_1800334D9
0x1800334d4  mov     ebx, 8007000Eh
0x1800334d9  test    ebx, ebx
0x1800334db  js      short loc_18003350A
0x1800334dd  mov     rdx, [rbp+ppbc]
0x1800334e1  mov     rcx, [rbp+var_30]
0x1800334e5  lea     r8, [rbp+var_38]
0x1800334e9  mov     [rsp+80h+ppvItem], r8
0x1800334ee  lea     r9, _GUID_000214fa_0000_0000_c000_000000000046
0x1800334f5  lea     r8, BHID_ThumbnailHandler
0x1800334fc  mov     rax, [rcx]
0x1800334ff  mov     rax, [rax+18h]
0x180033503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033508  mov     ebx, eax
0x18003350a  lea     rcx, [rbp+ppbc]
0x18003350e  call    ??$SafeRelease@UISyncMgrSyncItemContainer@@@@YAXPEAPEAUISyncMgrSyncItemContainer@@@Z; SafeRelease<ISyncMgrSyncItemContainer>(ISyncMgrSyncItemContainer * *)
0x180033513  mov     rdx, [rbp+var_30]
0x180033517  mov     rcx, [rdx]
0x18003351a  mov     rax, [rcx+10h]
0x18003351e  mov     rcx, rdx
0x180033521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033526  jmp     short loc_18003355F
0x180033528  mov     rax, [rcx]
0x18003352b  lea     r8, _GUID_000214fa_0000_0000_c000_000000000046
0x180033532  lea     rcx, [rbp+var_38]
0x180033536  xor     r9d, r9d
0x180033539  mov     [rsp+80h+var_50], rcx
0x18003353e  xor     edx, edx
0x180033540  mov     [rsp+80h+var_58], 0
0x180033549  mov     rcx, rdi
0x18003354c  mov     rax, [rax+50h]
0x180033550  mov     [rsp+80h+ppvItem], r8
0x180033555  xor     r8d, r8d
0x180033558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003355d  mov     ebx, eax
0x18003355f  test    ebx, ebx
0x180033561  js      short loc_18003356E
0x180033563  cmp     [rbp+var_38], 0
0x180033568  jnz     loc_180033681
0x18003356e  mov     rcx, [rbp+var_28]
0x180033572  test    rcx, rcx
0x180033575  jz      short loc_180033587
0x180033577  test    sil, 20h
0x18003357b  jz      short loc_180033587
0x18003357d  mov     ebx, 8000000Ah
0x180033582  jmp     loc_180033681
0x180033587  mov     rax, [rdi]
0x18003358a  mov     [rbp+ppbc], 0
0x180033592  mov     r10, [rax+50h]
0x180033596  mov     rax, rcx
0x180033599  neg     rax
0x18003359c  lea     rax, [rbp+var_28]
0x1800335a0  sbb     r9, r9
0x1800335a3  xor     r8d, r8d
0x1800335a6  and     r9, rax
0x1800335a9  lea     rax, [rbp+ppbc]
0x1800335ad  mov     [rsp+80h+var_50], rax
0x1800335b2  test    rcx, rcx
0x1800335b5  lea     rax, _GUID_000214eb_0000_0000_c000_000000000046
0x1800335bc  mov     [rsp+80h+var_58], 0
0x1800335c5  mov     [rsp+80h+ppvItem], rax
0x1800335ca  setnz   r8b
0x1800335ce  mov     rax, r10
0x1800335d1  xor     edx, edx
0x1800335d3  mov     rcx, rdi
0x1800335d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335db  mov     ebx, eax
0x1800335dd  test    eax, eax
0x1800335df  js      loc_180033681
0x1800335e5  cmp     [rbp+ppbc], 0
0x1800335ea  jz      loc_18003367C
0x1800335f0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800335f7  mov     ecx, 128h; unsigned __int64
0x1800335fc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180033601  mov     rbx, rax
0x180033604  test    rax, rax
0x180033607  jz      short loc_180033657
0x180033609  mov     rcx, [rbp+ppbc]
0x18003360d  lea     rax, ??_7CExtractIconWForA@@6BIExtractIconA@@@; const CExtractIconWForA::`vftable'{for `IExtractIconA'}
0x180033614  mov     [rbx], rax
0x180033617  lea     rax, ??_7CExtractIconWForA@@6BIExtractIconW@@@; const CExtractIconWForA::`vftable'{for `IExtractIconW'}
0x18003361e  mov     [rbx+8], rax
0x180033622  mov     dword ptr [rbx+10h], 1
0x180033629  mov     [rbx+18h], rcx
0x18003362d  mov     rdx, [rcx]
0x180033630  mov     rax, [rdx+8]
0x180033634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033639  lea     rcx, [rbx+20h]; void *
0x18003363d  xor     edx, edx; Val
0x18003363f  mov     r8d, 104h; Size
0x180033645  call    memset_0
0x18003364a  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180033651  add     rbx, 8
0x180033655  jmp     short loc_180033659
0x180033657  xor     ebx, ebx
0x180033659  mov     rcx, [rbp+ppbc]
0x18003365d  mov     [rbp+var_38], rbx
0x180033661  neg     rbx
0x180033664  sbb     ebx, ebx
0x180033666  mov     rax, [rcx]
0x180033669  not     ebx
0x18003366b  and     ebx, 8007000Eh
0x180033671  mov     rax, [rax+10h]
0x180033675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003367a  jmp     short loc_180033681
0x18003367c  mov     ebx, 80004005h
0x180033681  mov     rax, [rbp+var_38]
0x180033685  mov     [r14], rax
0x180033688  mov     eax, ebx
0x18003368a  mov     rcx, [rbp+var_10]
0x18003368e  xor     rcx, rsp; StackCookie
0x180033691  call    __security_check_cookie
0x180033696  add     rsp, 80h
0x18003369d  pop     r14
0x18003369f  pop     rdi
0x1800336a0  pop     rsi
0x1800336a1  pop     rbx
0x1800336a2  pop     rbp
0x1800336a3  retn
```
