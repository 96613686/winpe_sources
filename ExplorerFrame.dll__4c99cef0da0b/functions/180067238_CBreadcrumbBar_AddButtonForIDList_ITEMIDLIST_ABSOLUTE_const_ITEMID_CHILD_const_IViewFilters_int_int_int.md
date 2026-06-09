# CBreadcrumbBar::_AddButtonForIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const *,IViewFilters *,int,int,int *)

- ea: `0x180067238`
- end: `0x1800679db`
- name: `?_AddButtonForIDList@CBreadcrumbBar@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMID_CHILD@@PEAUIViewFilters@@HHPEAH@Z`
- size: `1955`
- prototype: `__int64 __usercall@<rax>(CBreadcrumbBar *__hidden this@<rcx>, const struct _ITEMIDLIST_ABSOLUTE *@<rdx>, const struct _ITEMID_CHILD *@<r8>, struct IViewFilters *@<r9>, int, int, int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043b20`
- `0x180069024`

## callees

- `0x1800471dc`
- `0x180067238`
- `0x18006863c`
- `0x1800688b0`
- `0x180068938`
- `0x18008ec88`
- `0x1800941dc`
- `0x1800b08f8`
- `0x1800d123c`
- `0x1800ebc00`
- `0x18012b614`
- `0x18012f180`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x180067568`
- `SHCORE!IUnknown_SetSite` at `0x180067568`
- `SHELL32!SHCreateItemWithParent` at `0x1800672cf`
- `SHELL32!SHCreateItemWithParent` at `0x1800672cf`
- `SHELL32!SHGetKnownFolderIDList` at `0x1800675af`
- `SHELL32!SHGetKnownFolderIDList` at `0x1800675af`
- `SHELL32!SHBindToParent` at `0x180067291`
- `SHELL32!SHBindToParent` at `0x1800677d7`
- `SHELL32!SHBindToParent` at `0x180067291`
- `SHELL32!SHBindToParent` at `0x1800677d7`
- `SHELL32!SHCreateItemFromIDList` at `0x1800679a0`
- `SHELL32!SHCreateItemFromIDList` at `0x1800679a0`
- `SHELL32!__imp_ILFindLastID` at `0x18006794a`
- `SHELL32!__imp_ILFindLastID` at `0x18006794a`
- `SHELL32!__imp_ILIsEqual` at `0x1800675d9`
- `SHELL32!__imp_ILIsEqual` at `0x180067907`
- `SHELL32!__imp_ILIsEqual` at `0x1800675d9`
- `SHELL32!__imp_ILIsEqual` at `0x180067907`
- `SHELL32!__imp_SHGetSetSettings` at `0x180067583`
- `SHELL32!__imp_SHGetSetSettings` at `0x180067583`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180067543`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180067543`
- `SHELL32!__imp_ILFree` at `0x1800675ee`
- `SHELL32!__imp_ILFree` at `0x1800678e8`
- `SHELL32!__imp_ILFree` at `0x1800675ee`
- `SHELL32!__imp_ILFree` at `0x1800678e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067853`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180067853`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800676c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006774f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800676c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006774f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800673de`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800673de`
- `USER32!SendMessageW` at `0x180067507`
- `USER32!SendMessageW` at `0x180067507`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBreadcrumbBar::_AddButtonForIDList(
        CBreadcrumbBar *this,
        const ITEMIDLIST *a2,
        const struct _ITEMID_CHILD *a3,
        struct IViewFilters *a4,
        int a5,
        unsigned int a6,
        int *a7)
{
  HRESULT DisplayNameForPidl; // edi
  const struct _ITEMID_CHILD *v11; // rbx
  unsigned int v12; // r12d
  void *v13; // rbx
  void (__fastcall *v14)(void *, __int64, LPCWCH *); // r15
  WCHAR *v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rdi
  unsigned __int16 *v18; // rbx
  unsigned __int16 *v19; // rax
  LPITEMIDLIST v20; // rcx
  char v21; // al
  unsigned int v22; // edi
  const ITEMIDLIST *v23; // rdx
  struct IShellFolder3 *v24; // rcx
  WCHAR *v26; // rax
  int v27; // ebx
  LPCWCH v28; // rdi
  __int64 v29; // rsi
  FARPROC ProcAddress; // rax
  HMODULE v31; // rcx
  ITEMIDLIST *v32; // rbx
  int v33; // ebx
  LPITEMIDLIST ID; // rax
  LPITEMIDLIST ppidl; // [rsp+50h] [rbp-A1h] BYREF
  LPCWCH lpString1; // [rsp+58h] [rbp-99h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-91h] BYREF
  struct IShellFolder3 *ppvItem; // [rsp+68h] [rbp-89h] BYREF
  int v39; // [rsp+70h] [rbp-81h] BYREF
  LPCWCH lpString2; // [rsp+78h] [rbp-79h] BYREF
  void *ppv; // [rsp+80h] [rbp-71h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+88h] [rbp-69h] BYREF
  unsigned __int16 *v43; // [rsp+90h] [rbp-61h] BYREF
  int *v44; // [rsp+98h] [rbp-59h]
  struct IViewFilters *v45; // [rsp+A0h] [rbp-51h]
  _QWORD lParam[4]; // [rsp+A8h] [rbp-49h] BYREF
  struct $D321FDA48A4D82B6F6ABB6499405B63E v47; // [rsp+C8h] [rbp-29h] BYREF

  v45 = a4;
  v44 = a7;
  ppv = 0;
  ppidlLast = 0;
  DisplayNameForPidl = SHBindToParent(a2, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
  if ( DisplayNameForPidl >= 0 )
  {
    if ( a3 )
    {
      ppidl = 0;
      if ( (*(int (__fastcall **)(void *, LPCITEMIDLIST, _QWORD, GUID *, LPITEMIDLIST *))(*(_QWORD *)ppv + 40LL))(
             ppv,
             ppidlLast,
             0,
             &GUID_000214e6_0000_0000_c000_000000000046,
             &ppidl) >= 0 )
      {
        v27 = 0;
        ppvItem = 0;
        if ( (**(int (__fastcall ***)(LPITEMIDLIST, GUID *, struct IShellFolder3 **))&ppidl->mkid.cb)(
               ppidl,
               &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
               &ppvItem) >= 0 )
        {
          v27 = IsWordWheelIDList(ppvItem, a3);
          (*(void (__fastcall **)(struct IShellFolder3 *))(*(_QWORD *)ppvItem + 16LL))(ppvItem);
        }
        (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
        if ( v27 )
          goto LABEL_47;
      }
    }
    pv = 0;
    ppvItem = 0;
    SHCreateItemWithParent(
      0,
      (IShellFolder *)ppv,
      ppidlLast,
      &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
      (void **)&ppvItem);
    v11 = (const struct _ITEMID_CHILD *)ppidlLast;
    ppidl = 0;
    v12 = 1;
    if ( (**(int (__fastcall ***)(void *, GUID *, LPITEMIDLIST *))ppv)(
           ppv,
           &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
           &ppidl) >= 0 )
    {
      v33 = IsWordWheelIDList((struct IShellFolder3 *)ppidl, v11);
      (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
      if ( v33 )
      {
        v32 = (ITEMIDLIST *)ILCloneParent((const struct _ITEMIDLIST_RELATIVE *)a2);
        if ( v32 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &pv,
            0);
          DisplayNameForPidl = CBreadcrumbBar::_GetDisplayNameForPidl(this, v32, 0, (unsigned __int16 **)&pv);
          ILFree(v32);
        }
        else
        {
          DisplayNameForPidl = -2147024882;
        }
        goto LABEL_29;
      }
    }
    if ( pv )
      wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(pv);
    pv = 0;
    v13 = ppvItem;
    if ( *((_DWORD *)this + 85) && ILIsEqual(a2, *((LPCITEMIDLIST *)this + 29)) && ILFindHiddenIDOn(a2, 3203334160LL) )
    {
      ppidl = 0;
      DisplayNameForPidl = CBreadcrumbBar::_GetViewFilters(this, (struct IViewFilters **)&ppidl);
      if ( DisplayNameForPidl < 0 )
        goto LABEL_29;
      ID = ILFindLastID(a2);
      v39 = 0;
      DisplayNameForPidl = (*(__int64 (__fastcall **)(LPITEMIDLIST, _QWORD, LPITEMIDLIST, __int64, LPVOID *, int *))(*(_QWORD *)&ppidl->mkid.cb + 32LL))(
                             ppidl,
                             0,
                             ID,
                             16385,
                             &pv,
                             &v39);
      v20 = ppidl;
      goto LABEL_28;
    }
    ppidl = 0;
    if ( !v13 )
    {
      DisplayNameForPidl = SHCreateItemFromIDList(a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&ppidl);
      if ( DisplayNameForPidl < 0 )
        goto LABEL_27;
      v13 = ppidl;
    }
    lpString1 = 0;
    DisplayNameForPidl = (*(__int64 (__fastcall **)(void *, __int64, LPCWCH *))(*(_QWORD *)v13 + 40LL))(
                           v13,
                           2148089857LL,
                           &lpString1);
    if ( DisplayNameForPidl < 0 )
    {
LABEL_25:
      if ( lpString1 )
        CoTaskMemFree((LPVOID)lpString1);
LABEL_27:
      v20 = ppidl;
      ppidl = 0;
      if ( !v20 )
      {
LABEL_29:
        if ( DisplayNameForPidl >= 0 )
        {
          memset((char *)lParam + 4, 0, 20);
          LODWORD(lParam[0]) = -2;
          lParam[3] = pv;
          if ( !a2 || !a2->mkid.cb )
          {
            ppidl = 0;
            lpString1 = 0;
            if ( SHBindToParent(
                   *((LPCITEMIDLIST *)this + 29),
                   &GUID_000214e6_0000_0000_c000_000000000046,
                   (void **)&ppidl,
                   (LPCITEMIDLIST *)&lpString1) >= 0 )
            {
              LODWORD(lParam[0]) = CBreadcrumbBar::ComputeIconIndexForPidl(
                                     this,
                                     (struct IShellFolder *)ppidl,
                                     (const struct _ITEMID_CHILD *)lpString1);
              (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&ppidl->mkid.cb + 16LL))(ppidl);
            }
          }
          HIDWORD(lParam[0]) = a6 + 1280;
          LOBYTE(lParam[1]) = 4;
          v21 = 112;
          if ( a5 )
            v21 = 120;
          BYTE1(lParam[1]) = v21;
          lParam[2] = (int)a6;
          if ( SendMessageW(*((HWND *)this + 34), 0x443u, (int)a6, (LPARAM)lParam) )
          {
            *v44 = a6 + 1;
            lpString1 = 0;
            DisplayNameForPidl = SHCoCreateInstance(
                                   0,
                                   &CLSID_ShellFolderSet,
                                   0,
                                   &GUID_5c718a08_6ca1_4ae9_a9cc_7caf009f41b1,
                                   (void **)&lpString1);
            if ( DisplayNameForPidl >= 0 )
            {
              IUnknown_SetSite(
                (IUnknown *)lpString1,
                (IUnknown *)(((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
              memset(&v47, 0, sizeof(v47));
              SHGetSetSettings(&v47, 1u, 0);
              v22 = ((*(_BYTE *)&v47 & 1) << 7) | 0x20;
              ppidl = 0;
              if ( SHGetKnownFolderIDList(&FOLDERID_ComputerFolder, 0, 0, &ppidl) >= 0 )
              {
                v23 = (const ITEMIDLIST *)*((_QWORD *)this + 29);
                if ( !v23 || !v23->mkid.cb || ILIsEqual(ppidl, v23) )
                  v12 = 0;
                ILFree(ppidl);
              }
              DisplayNameForPidl = (*(__int64 (__fastcall **)(LPCWCH, _QWORD, _QWORD, unsigned __int64, const ITEMIDLIST *, const struct _ITEMID_CHILD *, struct IViewFilters *, _QWORD))(*(_QWORD *)lpString1 + 24LL))(
                                     lpString1,
                                     v22,
                                     v12,
                                     ((unsigned __int64)this + 48) & -(__int64)(this != 0),
                                     a2,
                                     a3,
                                     v45,
                                     (int)a6);
              if ( DisplayNameForPidl >= 0 )
              {
                v28 = lpString1;
                v29 = *((_QWORD *)this + 32);
                ProcAddress = (FARPROC)qword_180291248;
                if ( qword_180291248 == -1 )
                {
                  v31 = g_hinstCC;
                  if ( g_hinstCC || (DelayLoadCC(), (v31 = g_hinstCC) != 0) )
                    ProcAddress = GetProcAddress(v31, (LPCSTR)0x14E);
                  else
                    ProcAddress = 0;
                  qword_180291248 = (__int64)ProcAddress;
                }
                if ( !ProcAddress
                  || ((unsigned int (__fastcall *)(__int64, _QWORD, LPCWCH))ProcAddress)(v29, a6, v28) == -1 )
                {
                  DisplayNameForPidl = -2147024882;
                }
                else
                {
                  DisplayNameForPidl = 0;
                  (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)lpString1 + 8LL))(lpString1);
                }
              }
              (*(void (__fastcall **)(LPCWCH))(*(_QWORD *)lpString1 + 16LL))(lpString1);
            }
          }
          else
          {
            DisplayNameForPidl = -2147467259;
          }
        }
        v24 = ppvItem;
        ppvItem = 0;
        if ( v24 )
          (*(void (__fastcall **)(struct IShellFolder3 *))(*(_QWORD *)v24 + 16LL))(v24);
        if ( pv )
          CoTaskMemFree(pv);
LABEL_47:
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        return (unsigned int)DisplayNameForPidl;
      }
LABEL_28:
      (*(void (__fastcall **)(LPITEMIDLIST))(*(_QWORD *)&v20->mkid.cb + 16LL))(v20);
      goto LABEL_29;
    }
    lpString2 = 0;
    v39 = 0;
    if ( !(*(unsigned int (__fastcall **)(void *, __int64, int *))(*(_QWORD *)v13 + 48LL))(v13, 0x40000000, &v39) )
    {
      v14 = *(void (__fastcall **)(void *, __int64, LPCWCH *))(*(_QWORD *)v13 + 40LL);
      if ( lpString2 )
        wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset((LPVOID)lpString2);
      lpString2 = 0;
      v14(v13, 2147581953LL, &lpString2);
    }
    v15 = (WCHAR *)lpString2;
    if ( lpString2 )
    {
      if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 1) == 2 )
      {
        v16 = -1;
        do
          ++v16;
        while ( lpString1[v16] );
        v17 = v16 + 2;
        wil::make_cotaskmem_string_nothrow((wil *)&v43, 0, v16 + 2);
        v18 = v43;
        if ( v43 )
        {
          DisplayNameForPidl = StringCchPrintfW(v43, v17, L"%s%s", &dword_180236F64, lpString1);
          if ( DisplayNameForPidl >= 0 )
          {
            v19 = v18;
            v18 = 0;
            pv = v19;
          }
        }
        else
        {
          DisplayNameForPidl = -2147024882;
        }
        if ( v18 )
          CoTaskMemFree(v18);
        v15 = (WCHAR *)lpString2;
        goto LABEL_23;
      }
      v15 = (WCHAR *)lpString2;
    }
    v26 = (WCHAR *)lpString1;
    lpString1 = 0;
    pv = v26;
LABEL_23:
    if ( v15 )
      CoTaskMemFree(v15);
    goto LABEL_25;
  }
  return (unsigned int)DisplayNameForPidl;
}

```

## disassembly

```asm
0x180067238  push    rbp
0x18006723a  push    rbx
0x18006723b  push    rsi
0x18006723c  push    rdi
0x18006723d  push    r12
0x18006723f  push    r13
0x180067241  push    r14
0x180067243  push    r15
0x180067245  lea     rbp, [rsp-7]
0x18006724a  sub     rsp, 0F8h
0x180067251  mov     rax, cs:__security_cookie
0x180067258  xor     rax, rsp
0x18006725b  mov     [rbp+3Fh+var_48], rax
0x18006725f  mov     [rbp+3Fh+var_90], r9
0x180067263  mov     r13, r8
0x180067266  mov     r14, rdx
0x180067269  mov     rsi, rcx
0x18006726c  mov     rax, [rbp+3Fh+arg_30]
0x180067270  mov     [rbp+3Fh+var_98], rax
0x180067274  xor     r15d, r15d
0x180067277  mov     [rbp+3Fh+ppv], r15
0x18006727b  mov     [rbp+3Fh+ppidlLast], r15
0x18006727f  lea     r9, [rbp+3Fh+ppidlLast]; ppidlLast
0x180067283  lea     r8, [rbp+3Fh+ppv]; ppv
0x180067287  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18006728e  mov     rcx, r14; pidl
0x180067291  call    cs:__imp_SHBindToParent
0x180067297  mov     edi, eax
0x180067299  test    eax, eax
0x18006729b  js      loc_18006768C
0x1800672a1  test    r13, r13
0x1800672a4  jnz     loc_1800676CD
0x1800672aa  mov     [rsp+130h+pv], r15
0x1800672af  mov     [rsp+130h+var_C8], r15
0x1800672b4  lea     rax, [rsp+130h+var_C8]
0x1800672b9  mov     [rsp+130h+ppvItem], rax; ppvItem
0x1800672be  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800672c5  mov     r8, [rbp+3Fh+ppidlLast]; pidl
0x1800672c9  mov     rdx, [rbp+3Fh+ppv]; psfParent
0x1800672cd  xor     ecx, ecx; pidlParent
0x1800672cf  call    cs:__imp_SHCreateItemWithParent
0x1800672d5  mov     rcx, [rbp+3Fh+ppv]
0x1800672d9  mov     rbx, [rbp+3Fh+ppidlLast]
0x1800672dd  mov     [rsp+130h+ppidl], r15
0x1800672e2  mov     rax, [rcx]
0x1800672e5  lea     r8, [rsp+130h+ppidl]
0x1800672ea  lea     rdx, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x1800672f1  mov     rax, [rax]
0x1800672f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800672f9  mov     r12d, 1
0x1800672ff  test    eax, eax
0x180067301  jns     loc_18006789A
0x180067307  mov     rcx, [rsp+130h+pv]; pv
0x18006730c  test    rcx, rcx
0x18006730f  jnz     loc_1800678F3
0x180067315  mov     [rsp+130h+pv], r15
0x18006731a  mov     rbx, [rsp+130h+var_C8]
0x18006731f  cmp     [rsi+154h], r15d
0x180067326  jnz     loc_1800678FD
0x18006732c  mov     [rsp+130h+ppidl], r15
0x180067331  test    rbx, rbx
0x180067334  jz      loc_180067991
0x18006733a  mov     [rsp+130h+lpString1], r15
0x18006733f  mov     rax, [rbx]
0x180067342  lea     r8, [rsp+130h+lpString1]
0x180067347  mov     edx, 80094001h
0x18006734c  mov     rcx, rbx
0x18006734f  mov     rax, [rax+28h]
0x180067353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067358  mov     edi, eax
0x18006735a  test    eax, eax
0x18006735c  js      loc_18006746B
0x180067362  mov     [rbp+3Fh+lpString2], r15
0x180067366  mov     [rsp+130h+var_C0], r15d
0x18006736b  mov     rax, [rbx]
0x18006736e  lea     r8, [rsp+130h+var_C0]
0x180067373  mov     edx, 40000000h
0x180067378  mov     rcx, rbx
0x18006737b  mov     rax, [rax+30h]
0x18006737f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067384  test    eax, eax
0x180067386  jnz     short loc_1800673BB
0x180067388  mov     rax, [rbx]
0x18006738b  mov     r15, [rax+28h]
0x18006738f  mov     rcx, [rbp+3Fh+lpString2]; pv
0x180067393  test    rcx, rcx
0x180067396  jnz     loc_1800679BA
0x18006739c  mov     [rbp+3Fh+lpString2], 0
0x1800673a4  lea     r8, [rbp+3Fh+lpString2]
0x1800673a8  mov     edx, 80018001h
0x1800673ad  mov     rcx, rbx
0x1800673b0  mov     rax, r15
0x1800673b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673b8  xor     r15d, r15d
0x1800673bb  mov     rcx, [rbp+3Fh+lpString2]
0x1800673bf  test    rcx, rcx
0x1800673c2  jz      loc_1800676AE
0x1800673c8  mov     dword ptr [rsp+130h+ppvItem], r12d; bIgnoreCase
0x1800673cd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800673d1  mov     r9d, ebx; cchCount2
0x1800673d4  mov     r8, rcx; lpString2
0x1800673d7  mov     edx, ebx; cchCount1
0x1800673d9  mov     rcx, [rsp+130h+lpString1]; lpString1
0x1800673de  call    cs:__imp_CompareStringOrdinal
0x1800673e4  cmp     eax, 2
0x1800673e7  jnz     loc_1800679C4
0x1800673ed  mov     rcx, [rsp+130h+lpString1]
0x1800673f2  mov     rax, rbx
0x1800673f5  inc     rax
0x1800673f8  cmp     [rcx+rax*2], r15w
0x1800673fd  jnz     short loc_1800673F5
0x1800673ff  lea     rdi, [rax+2]
0x180067403  mov     r8, rdi; unsigned __int64
0x180067406  xor     edx, edx; unsigned __int16 *
0x180067408  lea     rcx, [rbp+3Fh+var_A0]; this
0x18006740c  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180067411  mov     rbx, [rbp+3Fh+var_A0]
0x180067415  test    rbx, rbx
0x180067418  jz      loc_18006775A
0x18006741e  mov     rax, [rsp+130h+lpString1]
0x180067423  mov     [rsp+130h+ppvItem], rax
0x180067428  lea     r9, dword_180236F64
0x18006742f  lea     r8, aSS_1; "%s%s"
0x180067436  mov     rdx, rdi; unsigned __int64
0x180067439  mov     rcx, rbx; unsigned __int16 *
0x18006743c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067441  mov     edi, eax
0x180067443  test    eax, eax
0x180067445  js      short loc_180067452
0x180067447  mov     rax, rbx
0x18006744a  mov     rbx, r15
0x18006744d  mov     [rsp+130h+pv], rax
0x180067452  test    rbx, rbx
0x180067455  jnz     loc_18006774C
0x18006745b  mov     rcx, [rbp+3Fh+lpString2]; pv
0x18006745f  test    rcx, rcx
0x180067462  jz      short loc_18006746B
0x180067464  call    cs:__imp_CoTaskMemFree
0x18006746a  nop
0x18006746b  mov     rcx, [rsp+130h+lpString1]; pv
0x180067470  test    rcx, rcx
0x180067473  jnz     loc_1800676C2
0x180067479  mov     rcx, [rsp+130h+ppidl]
0x18006747e  mov     [rsp+130h+ppidl], r15
0x180067483  test    rcx, rcx
0x180067486  jz      short loc_180067494
0x180067488  mov     rax, [rcx]
0x18006748b  mov     rax, [rax+10h]
0x18006748f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067494  test    edi, edi
0x180067496  js      loc_180067650
0x18006749c  xorps   xmm0, xmm0
0x18006749f  movdqu  xmmword ptr [rbp+3Fh+lParam+4], xmm0
0x1800674a4  mov     [rbp+3Fh+var_74], r15d
0x1800674a8  mov     dword ptr [rbp+3Fh+lParam], 0FFFFFFFEh
0x1800674af  mov     rax, [rsp+130h+pv]
0x1800674b4  mov     [rbp+3Fh+var_70], rax
0x1800674b8  test    r14, r14
0x1800674bb  jz      loc_1800677B5
0x1800674c1  cmp     [r14], r15w
0x1800674c5  jz      loc_1800677B5
0x1800674cb  movsxd  rbx, [rbp+3Fh+arg_28]
0x1800674cf  lea     eax, [rbx+500h]
0x1800674d5  mov     dword ptr [rbp+3Fh+lParam+4], eax
0x1800674d8  mov     byte ptr [rbp-41h], 4
0x1800674dc  mov     al, 70h ; 'p'
0x1800674de  movzx   eax, al
0x1800674e1  mov     ecx, 78h ; 'x'
0x1800674e6  cmp     [rbp+3Fh+arg_20], r15d
0x1800674ea  cmovnz  eax, ecx
0x1800674ed  mov     [rbp-40h], al
0x1800674f0  mov     [rbp-39h], rbx
0x1800674f4  lea     r9, [rbp+3Fh+lParam]; lParam
0x1800674f8  mov     r8, rbx; wParam
0x1800674fb  mov     edx, 443h; Msg
0x180067500  mov     rcx, [rsi+110h]; hWnd
0x180067507  call    cs:__imp_SendMessageW
0x18006750d  xor     edx, edx
0x18006750f  test    rax, rax
0x180067512  jz      loc_1800679CD
0x180067518  lea     eax, [rbx+1]
0x18006751b  mov     rcx, [rbp+3Fh+var_98]
0x18006751f  mov     [rcx], eax
0x180067521  mov     [rsp+130h+lpString1], rdx
0x180067526  lea     rax, [rsp+130h+lpString1]
0x18006752b  mov     [rsp+130h+ppvItem], rax; ppv
0x180067530  lea     r9, _GUID_5c718a08_6ca1_4ae9_a9cc_7caf009f41b1; riid
0x180067537  xor     r8d, r8d; pUnkOuter
0x18006753a  lea     rdx, CLSID_ShellFolderSet; pclsid
0x180067541  xor     ecx, ecx; pszCLSID
0x180067543  call    cs:__imp_SHCoCreateInstance
0x180067549  mov     edi, eax
0x18006754b  test    eax, eax
0x18006754d  js      loc_1800679D2
0x180067553  mov     rax, rsi
0x180067556  lea     rcx, [rsi+10h]
0x18006755a  neg     rax
0x18006755d  sbb     rdx, rdx
0x180067560  and     rdx, rcx; punkSite
0x180067563  mov     rcx, [rsp+130h+lpString1]; punk
0x180067568  call    cs:__imp_IUnknown_SetSite
0x18006756e  xorps   xmm0, xmm0
0x180067571  movups  xmmword ptr [rbp+3Fh+var_68.fShowAllObjects], xmm0
0x180067575  movups  xmmword ptr [rbp+3Fh+var_68.iSortDirection], xmm0
0x180067579  xor     r8d, r8d; bSet
0x18006757c  mov     edx, r12d; dwMask
0x18006757f  lea     rcx, [rbp+3Fh+var_68]; lpss
0x180067583  call    cs:__imp_SHGetSetSettings
0x180067589  mov     edi, dword ptr [rbp+3Fh+var_68.fShowAllObjects]
0x18006758c  and     edi, r12d
0x18006758f  shl     edi, 7
0x180067592  or      edi, 20h
0x180067595  mov     [rsp+130h+ppidl], 0
0x18006759e  lea     r9, [rsp+130h+ppidl]; ppidl
0x1800675a3  xor     r8d, r8d; hToken
0x1800675a6  xor     edx, edx; dwFlags
0x1800675a8  lea     rcx, FOLDERID_ComputerFolder; rfid
0x1800675af  call    cs:__imp_SHGetKnownFolderIDList
0x1800675b5  xor     ecx, ecx
0x1800675b7  test    eax, eax
0x1800675b9  js      short loc_1800675F4
0x1800675bb  mov     rdx, [rsi+0E8h]; pidl2
0x1800675c2  test    rdx, rdx
0x1800675c5  jz      loc_18006781A
0x1800675cb  cmp     [rdx], cx
0x1800675ce  jz      loc_18006781A
0x1800675d4  mov     rcx, [rsp+130h+ppidl]; pidl1
0x1800675d9  call    cs:__imp_ILIsEqual
0x1800675df  xor     ecx, ecx
0x1800675e1  test    eax, eax
0x1800675e3  jnz     loc_18006781A
0x1800675e9  mov     rcx, [rsp+130h+ppidl]; pidl
0x1800675ee  call    cs:__imp_ILFree
0x1800675f4  mov     rcx, [rsp+130h+lpString1]
0x1800675f9  mov     r11, [rcx]
0x1800675fc  mov     rax, rsi
0x1800675ff  lea     r10, [rsi+30h]
0x180067603  neg     rax
0x180067606  sbb     r9, r9
0x180067609  and     r9, r10
0x18006760c  mov     [rsp+130h+var_F8], rbx
0x180067611  mov     rax, [rbp+3Fh+var_90]
0x180067615  mov     [rsp+130h+var_100], rax
0x18006761a  mov     [rsp+130h+var_108], r13
0x18006761f  mov     [rsp+130h+ppvItem], r14
0x180067624  mov     r8d, r12d
0x180067627  mov     edx, edi
0x180067629  mov     rax, [r11+18h]
0x18006762d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067632  mov     edi, eax
0x180067634  xor     r15d, r15d
0x180067637  test    eax, eax
0x180067639  jns     loc_180067764
0x18006763f  mov     rcx, [rsp+130h+lpString1]
0x180067644  mov     rax, [rcx]
0x180067647  mov     rax, [rax+10h]
0x18006764b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067650  mov     rcx, [rsp+130h+var_C8]
0x180067655  mov     [rsp+130h+var_C8], r15
0x18006765a  test    rcx, rcx
0x18006765d  jz      short loc_18006766C
0x18006765f  mov     rax, [rcx]
0x180067662  mov     rax, [rax+10h]
0x180067666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006766b  nop
0x18006766c  mov     rcx, [rsp+130h+pv]; pv
0x180067671  test    rcx, rcx
0x180067674  jz      short loc_18006767C
0x180067676  call    cs:__imp_CoTaskMemFree
0x18006767c  mov     rcx, [rbp+3Fh+ppv]
0x180067680  mov     rax, [rcx]
0x180067683  mov     rax, [rax+10h]
0x180067687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006768c  mov     eax, edi
0x18006768e  mov     rcx, [rbp+3Fh+var_48]
0x180067692  xor     rcx, rsp; StackCookie
0x180067695  call    __security_check_cookie
0x18006769a  add     rsp, 0F8h
0x1800676a1  pop     r15
0x1800676a3  pop     r14
0x1800676a5  pop     r13
0x1800676a7  pop     r12
0x1800676a9  pop     rdi
0x1800676aa  pop     rsi
0x1800676ab  pop     rbx
0x1800676ac  pop     rbp
0x1800676ad  retn
0x1800676ae  mov     rax, [rsp+130h+lpString1]
0x1800676b3  mov     [rsp+130h+lpString1], r15
0x1800676b8  mov     [rsp+130h+pv], rax
0x1800676bd  jmp     loc_18006745F
0x1800676c2  call    cs:__imp_CoTaskMemFree
0x1800676c8  jmp     loc_180067479
0x1800676cd  mov     [rsp+130h+ppidl], r15
0x1800676d2  mov     rcx, [rbp+3Fh+ppv]
0x1800676d6  mov     r8, [rcx]
0x1800676d9  mov     rax, [r8+28h]
0x1800676dd  lea     rdx, [rsp+130h+ppidl]
0x1800676e2  mov     [rsp+130h+ppvItem], rdx
0x1800676e7  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
  ... truncated ...
```
