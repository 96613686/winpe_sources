# CDBFolder::_CreateBindCtxForDelegateParse(_ITEMID_CHILD const *,DELBIND_TYPE,_GUID const &,void * *)

- ea: `0x180006758`
- end: `0x180006c6b`
- name: `?_CreateBindCtxForDelegateParse@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@W4DELBIND_TYPE@@AEBU_GUID@@PEAPEAX@Z`
- size: `1299`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a350`

## callees

- `0x180006758`
- `0x180006c80`
- `0x180006ca8`
- `0x180006d74`
- `0x180006dc0`
- `0x180009a50`
- `0x18000a730`
- `0x180071dc0`
- `0x180071df0`
- `0x180072cf4`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!SHCreateItemWithParent` at `0x18000681d`
- `Windows.Storage!SHCreateItemWithParent` at `0x18000681d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800069f5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800069f5`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x1800069e4`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x1800069e4`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800068c0`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800068c0`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800067ba`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180006995`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800067ba`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x180006995`

## pseudocode

```c
__int64 __fastcall CDBFolder::_CreateBindCtxForDelegateParse(
        CDBFolder *a1,
        unsigned __int16 *a2,
        int a3,
        __int64 a4,
        _QWORD *a5)
{
  CDummyUnknown *v7; // r12
  HRESULT BindCtx; // ebx
  ULONG v9; // r15d
  const ITEMIDLIST *v10; // rcx
  unsigned int v11; // edi
  void *v12; // rcx
  struct IBindCtx *v13; // rdi
  unsigned int v14; // r14d
  CDBFolder *v16; // r13
  void *v17; // r13
  CDummyUnknown *v18; // r8
  CDummyUnknown *v19; // rax
  CDummyUnknown *v20; // rax
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-C8h] BYREF
  int v23; // [rsp+40h] [rbp-C0h]
  _QWORD *v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  void *ppvItem; // [rsp+58h] [rbp-A8h] BYREF
  void *v27; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  CDBFolder *v31; // [rsp+88h] [rbp-78h]
  __int128 v32; // [rsp+90h] [rbp-70h] BYREF
  _WIN32_FIND_DATAW v33; // [rsp+A0h] [rbp-60h] BYREF

  v31 = a1;
  v24 = a5;
  v23 = a3;
  *a5 = 0;
  v7 = 0;
  ppbc = 0;
  BindCtx = CreateBindCtx(0, &ppbc);
  if ( BindCtx < 0 )
    return (unsigned int)BindCtx;
  v9 = 1;
  *(_QWORD *)&v32 = 16;
  *((_QWORD *)&v32 + 1) = 1;
  BindCtx = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->SetBindOptions)(ppbc, &v32);
  if ( BindCtx < 0 )
  {
    SafeRelease<IShellItemArray>((__int64 *)&ppbc);
    return (unsigned int)BindCtx;
  }
  v10 = (const ITEMIDLIST *)*((_QWORD *)a1 + 28);
  ppvItem = 0;
  BindCtx = SHCreateItemWithParent(
              v10,
              (IShellFolder *)a1,
              (LPCITEMIDLIST)a2,
              &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
              &ppvItem);
  if ( BindCtx < 0 )
    goto LABEL_30;
  BindCtx = ((__int64 (__fastcall *)(LPBC, const wchar_t *, void *))ppbc->lpVtbl->RegisterObjectParam)(
              ppbc,
              L"ParseOriginalItem",
              ppvItem);
  if ( BindCtx < 0 )
    goto LABEL_29;
  BindCtx = -2147024809;
  if ( !a2 )
    goto LABEL_29;
  v25 = 0;
  if ( *a2 < 0x2Eu )
    goto LABEL_29;
  if ( *(_DWORD *)(a2 + 3) != 269752705 )
    goto LABEL_29;
  if ( *a2 < (unsigned __int64)a2[5] + 46 )
    goto LABEL_29;
  v11 = a2[5];
  if ( !(_WORD)v11 )
    goto LABEL_29;
  if ( a2 == (unsigned __int16 *)-46LL )
    goto LABEL_29;
  ppv = 0;
  BindCtx = PSCreateMemoryPropertyStore(&GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &ppv);
  if ( BindCtx < 0 )
    goto LABEL_29;
  BindCtx = (*(__int64 (__fastcall **)(void *, unsigned __int16 *, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, a2 + 23, v11);
  if ( BindCtx >= 0 )
  {
    BindCtx = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1);
    if ( BindCtx >= 0 )
      BindCtx = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                  ppv,
                  &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                  &v25);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( BindCtx < 0 )
    goto LABEL_29;
  v12 = ppbc;
  propvarIn[0] = L"Parse Prefer Folder Browsing";
  v13 = 0;
  propvarIn[1] = 0;
  v29 = L"ParseWithProperties";
  v14 = 0;
  v30 = v25;
  v27 = 0;
  while ( v14 < 2 )
  {
    ppv = v12;
    if ( v12 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 8LL))(v12);
    }
    else
    {
      BindCtx = CreateBindCtx(0, (LPBC *)&ppv);
      if ( BindCtx < 0 )
        goto LABEL_20;
    }
    v17 = ppv;
    v18 = (CDummyUnknown *)propvarIn[2 * v14 + 1];
    if ( !v18 )
    {
      v19 = (CDummyUnknown *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)&v32 = v19;
      if ( !v19 || (v20 = CDummyUnknown::CDummyUnknown(v19), (v7 = v20) == 0) )
      {
        BindCtx = -2147024882;
LABEL_49:
        SafeRelease<IShellItemArray>((__int64 *)&ppv);
LABEL_50:
        SafeRelease<IShellItemArray>((__int64 *)&v27);
        goto LABEL_28;
      }
      v18 = v20;
    }
    BindCtx = (*(__int64 (__fastcall **)(void *, PROPVARIANT, CDummyUnknown *))(*(_QWORD *)v17 + 72LL))(
                v17,
                propvarIn[2 * v14],
                v18);
    if ( v7 )
      CDummyUnknown::Release(v7);
    v7 = 0;
    if ( BindCtx < 0 )
      goto LABEL_49;
LABEL_20:
    if ( BindCtx < 0 )
      goto LABEL_50;
    v12 = ppv;
    if ( v14 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      v12 = ppv;
      ++v14;
    }
    else
    {
      v13 = (struct IBindCtx *)ppv;
      v27 = ppv;
      v14 = 1;
    }
  }
  if ( v23 != 1 )
    goto LABEL_26;
  v16 = v31;
  v29 = 0;
  *(_OWORD *)propvarIn = 0;
  if ( (int)CDBFolder::GetPropertyForItem((char *)v31 + 184, a2, &PKEY_SFGAOFlags, 0, propvarIn) < 0 )
    goto LABEL_34;
  if ( LOWORD(propvarIn[0]) >= 2u )
    v9 = PropVariantToUInt32WithDefault(propvarIn, 0x40000000u) & 0x40000000;
  PropVariantClear(propvarIn);
  if ( v9 )
  {
LABEL_34:
    memset_0(&v33, 0, sizeof(v33));
    CDBFolder::_FillFindData(v16, (const struct _ITEMID_CHILD *)a2, &v33);
    ppv = 0;
    BindCtx = _CreateFileSysBindCtx(v13, &v33, (struct IBindCtx **)&ppv);
    if ( BindCtx >= 0 )
    {
      v32 = 0x10u;
      BindCtx = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppv + 56LL))(ppv, &v32);
      if ( BindCtx < 0
        || (*(_QWORD *)((char *)&v32 + 4) = 0,
            BindCtx = (*(__int64 (__fastcall **)(void *, __int128 *))(*(_QWORD *)ppv + 48LL))(ppv, &v32),
            BindCtx < 0) )
      {
        SafeRelease<IShellItemArray>((__int64 *)&ppv);
      }
      else
      {
        BindCtx = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))ppv)(
                    ppv,
                    &GUID_0000000e_0000_0000_c000_000000000046,
                    v24);
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  else
  {
LABEL_26:
    BindCtx = ((__int64 (__fastcall *)(struct IBindCtx *, GUID *, _QWORD *))v13->lpVtbl->QueryInterface)(
                v13,
                &GUID_0000000e_0000_0000_c000_000000000046,
                v24);
  }
  ((void (__fastcall *)(struct IBindCtx *))v13->lpVtbl->Release)(v13);
LABEL_28:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_29:
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
LABEL_30:
  ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  return (unsigned int)BindCtx;
}

```

## disassembly

```asm
0x180006758  mov     [rsp-8+arg_10], rbx
0x18000675d  push    rbp
0x18000675e  push    rsi
0x18000675f  push    rdi
0x180006760  push    r12
0x180006762  push    r13
0x180006764  push    r14
0x180006766  push    r15
0x180006768  lea     rbp, [rsp-200h]
0x180006770  sub     rsp, 300h
0x180006777  mov     rax, cs:__security_cookie
0x18000677e  xor     rax, rsp
0x180006781  mov     [rbp+230h+var_40], rax
0x180006788  mov     r12, [rbp+230h+arg_20]
0x18000678f  mov     rsi, rdx
0x180006792  mov     r13, rcx
0x180006795  mov     [rbp+230h+var_2A8], rcx
0x180006799  mov     [rsp+330h+var_2E8], r12
0x18000679e  lea     rdx, [rsp+330h+ppbc]; ppbc
0x1800067a3  xor     ecx, ecx; reserved
0x1800067a5  mov     [rsp+330h+var_2F0], r8d
0x1800067aa  mov     qword ptr [r12], 0
0x1800067b2  xor     r12d, r12d
0x1800067b5  mov     [rsp+330h+ppbc], r12
0x1800067ba  call    cs:__imp_CreateBindCtx
0x1800067c0  mov     ebx, eax
0x1800067c2  test    eax, eax
0x1800067c4  js      loc_180006A62
0x1800067ca  mov     rcx, [rsp+330h+ppbc]
0x1800067cf  lea     r15d, [r12+1]
0x1800067d4  mov     [rbp+230h+var_2A0], 10h
0x1800067dc  lea     rdx, [rbp+230h+var_2A0]
0x1800067e0  mov     [rbp+230h+var_298], r15
0x1800067e4  mov     rax, [rcx]
0x1800067e7  mov     rax, [rax+30h]
0x1800067eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067f0  mov     ebx, eax
0x1800067f2  test    eax, eax
0x1800067f4  js      loc_180006C5C
0x1800067fa  mov     rcx, [r13+0E0h]; pidlParent
0x180006801  lea     rax, [rsp+330h+var_2D8]
0x180006806  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000680d  mov     [rsp+330h+ppvItem], rax; ppvItem
0x180006812  mov     r8, rsi; pidl
0x180006815  mov     [rsp+330h+var_2D8], r12
0x18000681a  mov     rdx, r13; psfParent
0x18000681d  call    cs:__imp_SHCreateItemWithParent
0x180006823  mov     ebx, eax
0x180006825  test    eax, eax
0x180006827  js      loc_180006A51
0x18000682d  mov     rcx, [rsp+330h+ppbc]
0x180006832  lea     rdx, aParseoriginali; "ParseOriginalItem"
0x180006839  mov     r8, [rsp+330h+var_2D8]
0x18000683e  mov     rax, [rcx]
0x180006841  mov     rax, [rax+48h]
0x180006845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000684a  mov     ebx, eax
0x18000684c  test    eax, eax
0x18000684e  js      loc_180006A40
0x180006854  mov     ebx, 80070057h
0x180006859  test    rsi, rsi
0x18000685c  jz      loc_180006A40
0x180006862  lea     eax, [r12+2Eh]
0x180006867  mov     [rsp+330h+var_2E0], r12
0x18000686c  cmp     [rsi], ax
0x18000686f  jb      loc_180006A40
0x180006875  cmp     dword ptr [rsi+6], 10141981h
0x18000687c  jnz     loc_180006A40
0x180006882  movzx   ecx, word ptr [rsi+0Ah]
0x180006886  add     rcx, rax
0x180006889  movzx   eax, word ptr [rsi]
0x18000688c  cmp     rax, rcx
0x18000688f  jb      loc_180006A40
0x180006895  movzx   edi, word ptr [rsi+0Ah]
0x180006899  test    di, di
0x18000689c  jz      loc_180006A40
0x1800068a2  lea     r14, [rsi+2Eh]
0x1800068a6  test    r14, r14
0x1800068a9  jz      loc_180006A40
0x1800068af  lea     rdx, [rsp+330h+ppv]; ppv
0x1800068b4  mov     [rsp+330h+ppv], r12
0x1800068b9  lea     rcx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x1800068c0  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800068c6  mov     ebx, eax
0x1800068c8  test    eax, eax
0x1800068ca  js      loc_180006A40
0x1800068d0  mov     rcx, [rsp+330h+ppv]
0x1800068d5  mov     r8d, edi
0x1800068d8  mov     rdx, r14
0x1800068db  mov     rax, [rcx]
0x1800068de  mov     rax, [rax+20h]
0x1800068e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068e7  mov     ebx, eax
0x1800068e9  test    eax, eax
0x1800068eb  js      short loc_180006925
0x1800068ed  mov     rcx, [rsp+330h+ppv]
0x1800068f2  mov     edx, r15d
0x1800068f5  mov     rax, [rcx]
0x1800068f8  mov     rax, [rax+18h]
0x1800068fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006901  mov     ebx, eax
0x180006903  test    eax, eax
0x180006905  js      short loc_180006925
0x180006907  mov     rcx, [rsp+330h+ppv]
0x18000690c  lea     r8, [rsp+330h+var_2E0]
0x180006911  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180006918  mov     rax, [rcx]
0x18000691b  mov     rax, [rax]
0x18000691e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006923  mov     ebx, eax
0x180006925  mov     rcx, [rsp+330h+ppv]
0x18000692a  mov     rax, [rcx]
0x18000692d  mov     rax, [rax+10h]
0x180006931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006936  test    ebx, ebx
0x180006938  js      loc_180006A40
0x18000693e  mov     rcx, [rsp+330h+ppbc]; reserved
0x180006943  lea     rax, aParsePreferFol; "Parse Prefer Folder Browsing"
0x18000694a  mov     [rsp+330h+propvarIn], rax
0x18000694f  mov     rdi, r12
0x180006952  lea     rax, aParsewithprope; "ParseWithProperties"
0x180006959  mov     [rsp+330h+propvarIn+8], r12
0x18000695e  mov     [rsp+330h+var_2B8], rax
0x180006963  mov     r14d, r12d
0x180006966  mov     rax, [rsp+330h+var_2E0]
0x18000696b  mov     [rbp+230h+var_2B0], rax
0x18000696f  mov     [rsp+330h+var_2D0], r12
0x180006974  mov     ebx, 2
0x180006979  cmp     r14d, ebx
0x18000697c  jnb     loc_180006A8E
0x180006982  mov     [rsp+330h+ppv], rcx
0x180006987  test    rcx, rcx
0x18000698a  jnz     loc_180006BA1
0x180006990  lea     rdx, [rsp+330h+ppv]; ppbc
0x180006995  call    cs:__imp_CreateBindCtx
0x18000699b  mov     ebx, eax
0x18000699d  test    eax, eax
0x18000699f  jns     loc_180006BAD
0x1800069a5  test    ebx, ebx
0x1800069a7  js      loc_180006C3E
0x1800069ad  mov     rcx, [rsp+330h+ppv]
0x1800069b2  test    r14d, r14d
0x1800069b5  jz      loc_180006C1F
0x1800069bb  mov     rax, [rcx]
0x1800069be  mov     rax, [rax+10h]
0x1800069c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c7  mov     rcx, [rsp+330h+ppv]
0x1800069cc  add     r14d, r15d
0x1800069cf  jmp     short loc_180006974
0x1800069d1  cmp     word ptr [rsp+330h+propvarIn], bx
0x1800069d6  jb      short loc_1800069F0
0x1800069d8  mov     ebx, 40000000h
0x1800069dd  lea     rcx, [rsp+330h+propvarIn]; propvarIn
0x1800069e2  mov     edx, ebx; ulDefault
0x1800069e4  call    cs:__imp_PropVariantToUInt32WithDefault
0x1800069ea  mov     r15d, eax
0x1800069ed  and     r15d, ebx
0x1800069f0  lea     rcx, [rsp+330h+propvarIn]; pvar
0x1800069f5  call    cs:__imp_PropVariantClear
0x1800069fb  test    r15d, r15d
0x1800069fe  jnz     loc_180006AD7
0x180006a04  mov     rax, [rdi]
0x180006a07  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x180006a0e  mov     r8, [rsp+330h+var_2E8]
0x180006a13  mov     rcx, rdi
0x180006a16  mov     rax, [rax]
0x180006a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1e  mov     ebx, eax
0x180006a20  mov     rax, [rdi]
0x180006a23  mov     rcx, rdi
0x180006a26  mov     rax, [rax+10h]
0x180006a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a2f  mov     rcx, [rsp+330h+var_2E0]
0x180006a34  mov     rax, [rcx]
0x180006a37  mov     rax, [rax+10h]
0x180006a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a40  mov     rcx, [rsp+330h+var_2D8]
0x180006a45  mov     rax, [rcx]
0x180006a48  mov     rax, [rax+10h]
0x180006a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a51  mov     rcx, [rsp+330h+ppbc]
0x180006a56  mov     rax, [rcx]
0x180006a59  mov     rax, [rax+10h]
0x180006a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a62  mov     eax, ebx
0x180006a64  mov     rcx, [rbp+230h+var_40]
0x180006a6b  xor     rcx, rsp; StackCookie
0x180006a6e  call    __security_check_cookie
0x180006a73  mov     rbx, [rsp+330h+arg_10]
0x180006a7b  add     rsp, 300h
0x180006a82  pop     r15
0x180006a84  pop     r14
0x180006a86  pop     r13
0x180006a88  pop     r12
0x180006a8a  pop     rdi
0x180006a8b  pop     rsi
0x180006a8c  pop     rbp
0x180006a8d  retn
0x180006a8e  cmp     [rsp+330h+var_2F0], r15d
0x180006a93  jnz     loc_180006A04
0x180006a99  mov     r13, [rbp+230h+var_2A8]
0x180006a9d  lea     r8, PKEY_SFGAOFlags
0x180006aa4  xor     eax, eax
0x180006aa6  xorps   xmm0, xmm0
0x180006aa9  mov     [rsp+330h+var_2B8], rax
0x180006aae  xor     r9d, r9d
0x180006ab1  lea     rax, [rsp+330h+propvarIn]
0x180006ab6  mov     rdx, rsi
0x180006ab9  lea     rcx, [r13+0B8h]
0x180006ac0  mov     [rsp+330h+ppvItem], rax
0x180006ac5  movups  xmmword ptr [rsp+330h+propvarIn], xmm0
0x180006aca  call    ?GetPropertyForItem@CDBFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@W4PROPERTY_GET_TYPE@@PEAUtagPROPVARIANT@@@Z; CDBFolder::GetPropertyForItem(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,PROPERTY_GET_TYPE,tagPROPVARIANT *)
0x180006acf  test    eax, eax
0x180006ad1  jns     loc_1800069D1
0x180006ad7  xor     edx, edx; Val
0x180006ad9  lea     rcx, [rbp+230h+var_290]; void *
0x180006add  mov     r8d, 250h; Size
0x180006ae3  call    memset_0
0x180006ae8  lea     r8, [rbp+230h+var_290]; struct _WIN32_FIND_DATAW *
0x180006aec  mov     rdx, rsi; struct _ITEMID_CHILD *
0x180006aef  mov     rcx, r13; this
0x180006af2  call    ?_FillFindData@CDBFolder@@AEAAXPEFBU_ITEMID_CHILD@@PEAU_WIN32_FIND_DATAW@@@Z; CDBFolder::_FillFindData(_ITEMID_CHILD const *,_WIN32_FIND_DATAW *)
0x180006af7  lea     r8, [rsp+330h+ppv]; struct IBindCtx **
0x180006afc  mov     [rsp+330h+ppv], r12
0x180006b01  lea     rdx, [rbp+230h+var_290]; struct _WIN32_FIND_DATAW *
0x180006b05  mov     rcx, rdi; struct IBindCtx *
0x180006b08  call    ?_CreateFileSysBindCtx@@YAJPEAUIBindCtx@@PEBU_WIN32_FIND_DATAW@@PEAPEAU1@@Z; _CreateFileSysBindCtx(IBindCtx *,_WIN32_FIND_DATAW const *,IBindCtx * *)
0x180006b0d  mov     ebx, eax
0x180006b0f  test    eax, eax
0x180006b11  js      loc_180006A20
0x180006b17  mov     rcx, [rsp+330h+ppv]
0x180006b1c  lea     rdx, [rbp+230h+var_2A0]
0x180006b20  xor     eax, eax
0x180006b22  mov     dword ptr [rbp+230h+var_2A0], 10h
0x180006b29  mov     [rbp+230h+var_2A0+4], rax
0x180006b2d  mov     dword ptr [rbp+230h+var_298+4], eax
0x180006b30  mov     rax, [rcx]
0x180006b33  mov     rax, [rax+38h]
0x180006b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b3c  mov     ebx, eax
0x180006b3e  test    eax, eax
0x180006b40  js      loc_180006C4D
0x180006b46  mov     rcx, [rsp+330h+ppv]
0x180006b4b  lea     rdx, [rbp+230h+var_2A0]
0x180006b4f  mov     [rbp+230h+var_2A0+4], 0
0x180006b57  mov     rax, [rcx]
0x180006b5a  mov     rax, [rax+30h]
0x180006b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b63  mov     ebx, eax
0x180006b65  test    eax, eax
0x180006b67  js      loc_180006C4D
0x180006b6d  mov     rcx, [rsp+330h+ppv]
0x180006b72  lea     rdx, _GUID_0000000e_0000_0000_c000_000000000046
0x180006b79  mov     r8, [rsp+330h+var_2E8]
0x180006b7e  mov     rax, [rcx]
0x180006b81  mov     rax, [rax]
0x180006b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b89  mov     rcx, [rsp+330h+ppv]
0x180006b8e  mov     ebx, eax
0x180006b90  mov     rax, [rcx]
0x180006b93  mov     rax, [rax+10h]
0x180006b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b9c  jmp     loc_180006A20
0x180006ba1  mov     rax, [rcx]
0x180006ba4  mov     rax, [rax+8]
0x180006ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bad  mov     r13, [rsp+330h+ppv]
0x180006bb2  mov     ebx, r14d
0x180006bb5  add     rbx, rbx
0x180006bb8  mov     r8, [rsp+rbx*8+330h+propvarIn+8]
0x180006bbd  test    r8, r8
0x180006bc0  jnz     short loc_180006BEE
0x180006bc2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006bc9  lea     ecx, [r8+40h]; unsigned __int64
0x180006bcd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006bd2  mov     [rbp+230h+var_2A0], rax
0x180006bd6  test    rax, rax
0x180006bd9  jz      short loc_180006C2F
0x180006bdb  mov     rcx, rax; this
0x180006bde  call    ??0CDummyUnknown@@QEAA@XZ; CDummyUnknown::CDummyUnknown(void)
0x180006be3  mov     r12, rax
0x180006be6  test    rax, rax
0x180006be9  jz      short loc_180006C2F
0x180006beb  mov     r8, rax
0x180006bee  mov     rax, [r13+0]
0x180006bf2  mov     rcx, r13
0x180006bf5  mov     rdx, [rsp+rbx*8+330h+propvarIn]
0x180006bfa  mov     rax, [rax+48h]
0x180006bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c03  mov     ebx, eax
0x180006c05  test    r12, r12
0x180006c08  jz      short loc_180006C12
0x180006c0a  mov     rcx, r12; this
0x180006c0d  call    ?Release@CDummyUnknown@@UEAAKXZ; CDummyUnknown::Release(void)
0x180006c12  xor     r12d, r12d
0x180006c15  test    ebx, ebx
0x180006c17  jns     loc_1800069A5
0x180006c1d  jmp     short loc_180006C34
0x180006c1f  mov     rdi, rcx
0x180006c22  mov     [rsp+330h+var_2D0], rcx
  ... truncated ...
```
