# CNscTree::_GetChildren(IShellFolder *,_ITEMID_CHILD const *,_TREEITEM *)

- ea: `0x1800287d0`
- end: `0x180028db4`
- name: `?_GetChildren@CNscTree@@AEAAHPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@PEAU_TREEITEM@@@Z`
- size: `1508`
- prototype: `__int64 __fastcall(CNscTree *__hidden this, IUnknown *punk, LPCITEMIDLIST pidl2, struct _TREEITEM *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180096e58`
- `0x1800a9110`

## callees

- `0x1800287d0`
- `0x180028dbc`
- `0x18002903c`
- `0x180029078`
- `0x1800290d0`
- `0x18002ae50`
- `0x180047410`
- `0x1800dc3a4`
- `0x18013f7d0`
- `0x18013fcac`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x1800288dc`
- `SHCORE!IUnknown_QueryService` at `0x1800288dc`
- `SHCORE!IUnknown_Set` at `0x180028c8e`
- `SHCORE!IUnknown_Set` at `0x180028d1d`
- `SHCORE!IUnknown_Set` at `0x180028c8e`
- `SHCORE!IUnknown_Set` at `0x180028d1d`
- `SHELL32!SHCreateItemWithParent` at `0x180028c78`
- `SHELL32!SHCreateItemWithParent` at `0x180028c78`
- `SHELL32!SHBindToFolderIDListParentEx` at `0x18002883c`
- `SHELL32!SHBindToFolderIDListParentEx` at `0x18002883c`
- `SHELL32!SHGetIDListFromObject` at `0x180028908`
- `SHELL32!SHGetIDListFromObject` at `0x180028908`
- `SHELL32!__imp_ILClone` at `0x180028a87`
- `SHELL32!__imp_ILClone` at `0x180028a87`
- `SHELL32!__imp_ILCombine` at `0x18002891d`
- `SHELL32!__imp_ILCombine` at `0x18002891d`
- `SHELL32!__imp_ILFree` at `0x18002892a`
- `SHELL32!__imp_ILFree` at `0x180028b59`
- `SHELL32!__imp_ILFree` at `0x18002892a`
- `SHELL32!__imp_ILFree` at `0x180028b59`
- `USER32!SendMessageW` at `0x1800289aa`
- `USER32!SendMessageW` at `0x180028b2a`
- `USER32!SendMessageW` at `0x1800289aa`
- `USER32!SendMessageW` at `0x180028b2a`

## pseudocode

```c
__int64 __fastcall CNscTree::_GetChildren(
        CNscTree *this,
        IShellFolder *punk,
        LPCITEMIDLIST pidl2,
        struct _TREEITEM *a4)
{
  int v8; // edi
  int v9; // eax
  const struct _ITEMIDLIST_ABSOLUTE *v10; // r13
  volatile signed __int32 *v11; // rsi
  __int64 v12; // r12
  HWND v13; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // rdi
  LPITEMIDLIST v16; // rax
  signed int v17; // r14d
  const struct _GUID *v18; // r8
  HWND v19; // rcx
  ITEMIDLIST *v21; // rax
  CNscLock *v22; // rdi
  CNscLock *v23; // rax
  volatile signed __int32 *v24; // rdi
  int v25; // esi
  __int64 v26; // rdi
  int (__fastcall ***v27)(_QWORD, GUID *, HWND *); // rbx
  int (__fastcall **v28)(_QWORD, GUID *, HWND *); // rax
  int (__fastcall **v29)(_QWORD, GUID *, HWND *); // rax
  int v30; // ebx
  void **ppv; // [rsp+20h] [rbp-89h]
  unsigned __int8 v32; // [rsp+30h] [rbp-79h]
  LPCITEMIDLIST ppidlLast; // [rsp+38h] [rbp-71h] BYREF
  HWND v34; // [rsp+40h] [rbp-69h] BYREF
  __int64 v35; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v36; // [rsp+50h] [rbp-59h]
  LPITEMIDLIST ppidl; // [rsp+58h] [rbp-51h] BYREF
  LPARAM lParam[2]; // [rsp+60h] [rbp-49h] BYREF
  __int128 v39; // [rsp+70h] [rbp-39h]
  __int128 v40; // [rsp+80h] [rbp-29h]
  __int64 v41; // [rsp+90h] [rbp-19h]
  IShellFolder *psfParent; // [rsp+98h] [rbp-11h]
  LPCITEMIDLIST pidl; // [rsp+A0h] [rbp-9h]
  _QWORD *v44; // [rsp+A8h] [rbp-1h]

  pidl = pidl2;
  psfParent = punk;
  v36 = 0;
  ppidlLast = 0;
  v34 = 0;
  if ( SHBindToFolderIDListParentEx(
         punk,
         pidl2,
         0,
         &GUID_000214e6_0000_0000_c000_000000000046,
         (void **)&v34,
         &ppidlLast) >= 0 )
  {
    LODWORD(v35) = 1614807040;
    v8 = 0;
    if ( (*(int (__fastcall **)(HWND, __int64, LPCITEMIDLIST *, __int64 *))(*(_QWORD *)v34 + 72LL))(
           v34,
           1,
           &ppidlLast,
           &v35) >= 0 )
      v8 = v35 & 0x60400000;
    (*(void (__fastcall **)(HWND))(*(_QWORD *)v34 + 16LL))(v34);
    if ( (v8 & 0x20000000) != 0 )
    {
      v9 = *((_DWORD *)this + 113);
      if ( (v9 & 0x10000000) != 0 || v8 != 1614807040 )
      {
        v36 = 1;
        if ( (v9 & 0x80000) == 0
          && (*((_QWORD *)this + 86)
           || IUnknown_QueryService(
                *((IUnknown **)this + 22),
                &IID_IShellTaskScheduler,
                &GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec,
                (void **)this + 86) >= 0
           || (int)CreateDefaultTaskScheduler(&GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec, (void **)this + 86) >= 0) )
        {
          ppidl = 0;
          if ( SHGetIDListFromObject((IUnknown *)punk, &ppidl) >= 0 )
          {
            v10 = (const struct _ITEMIDLIST_ABSOLUTE *)ILCombine(ppidl, pidl2);
            ILFree(ppidl);
            if ( v10 )
            {
              if ( !*((_QWORD *)this + 87) )
              {
                *((_QWORD *)this + 87) = 0;
                v21 = (ITEMIDLIST *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
                ppidlLast = v21;
                v22 = (CNscLock *)v21;
                if ( !v21 )
                  goto LABEL_29;
                memset_0(v21, 0, 0x78u);
                v23 = CNscLock::CNscLock(v22);
                v24 = (volatile signed __int32 *)v23;
                if ( !v23 )
                  goto LABEL_29;
                v25 = CNscLock::Init(v23, this);
                if ( v25 >= 0 )
                {
                  *((_QWORD *)this + 87) = v24;
                  _InterlockedIncrement(v24 + 26);
                }
                CTaskLock::Release((CTaskLock *)v24);
                if ( v25 < 0 )
                  goto LABEL_29;
              }
              v11 = (volatile signed __int32 *)*((_QWORD *)this + 87);
              _InterlockedIncrement(v11 + 26);
              v12 = 0;
              LODWORD(v35) = CNscTree::_GetEnumFlags(this, a4, 0, v10, (HWND *)ppv);
              if ( a4 )
              {
                if ( a4 != (struct _TREEITEM *)-65536LL )
                {
                  v13 = (HWND)*((_QWORD *)this + 50);
                  lParam[0] = 20;
                  lParam[1] = (LPARAM)a4;
                  v39 = 0;
                  v41 = 0;
                  v40 = 0;
                  if ( (unsigned int)SendMessageW(v13, 0x113Eu, 0, (LPARAM)lParam) )
                    v12 = v41;
                }
              }
              LODWORD(v34) = *((_DWORD *)this + 114);
              v32 = *((_BYTE *)this + 768);
              ppidlLast = (LPCITEMIDLIST)*((_QWORD *)this + 86);
              v14 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
              v44 = v14;
              v15 = v14;
              if ( !v14 )
                goto LABEL_28;
              v14[5] = 1;
              *((_DWORD *)v14 + 12) = 0;
              v14[7] = 0;
              *((_DWORD *)v14 + 16) = 0;
              *v14 = &CNscPlusTask::`vftable'{for `IRunnableTask'};
              v14[1] = &CNscSortTask::`vftable'{for `IServiceProvider'};
              v14[2] = &CNscSortTask::`vftable'{for `IQueryContinue'};
              v14[3] = &CComCatCacheTask::`vftable'{for `IObjectWithCancelEvent'};
              v14[4] = &CFrameTask::`vftable'{for `ITestRunnableTask'};
              *((_DWORD *)v14 + 26) = v32;
              *((_DWORD *)v14 + 27) = v35;
              *((_DWORD *)v14 + 28) = (_DWORD)v34;
              v14[11] = a4;
              v14[12] = 0;
              _InterlockedIncrement(&g_cRefThisDll);
              v14[10] = 0;
              v14[9] = v11;
              _InterlockedIncrement(v11 + 26);
              if ( v12 )
              {
                v14[12] = v12;
                _InterlockedIncrement((volatile signed __int32 *)(v12 + 56));
              }
              v16 = ILClone((LPCITEMIDLIST)v10);
              v15[10] = v16;
              v17 = v16 == 0 ? 0x8007000E : 0;
              if ( v16 )
                v17 = (*(__int64 (__fastcall **)(LPCITEMIDLIST, _QWORD *, __int64 *, __int64, int))(*(_QWORD *)&ppidlLast->mkid.cb
                                                                                                  + 24LL))(
                        ppidlLast,
                        v15,
                        TASKID_PlusExtraction,
                        -1,
                        268435457);
              (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
              if ( v17 < 0 )
              {
LABEL_28:
                if ( _InterlockedExchangeAdd(v11 + 26, 0xFFFFFFFF) == 1 && v11 )
                  (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v11 + 16LL))(v11, 1);
LABEL_29:
                ILFree((LPITEMIDLIST)v10);
                return v36;
              }
              if ( a4 )
              {
                if ( a4 != (struct _TREEITEM *)-65536LL )
                {
                  v19 = (HWND)*((_QWORD *)this + 50);
                  lParam[0] = 20;
                  lParam[1] = (LPARAM)a4;
                  v39 = 0;
                  v41 = 0;
                  v40 = 0;
                  if ( (unsigned int)SendMessageW(v19, 0x113Eu, 0, (LPARAM)lParam) )
                  {
                    v26 = v41;
                    if ( v41 )
                    {
                      if ( !*(_QWORD *)(v41 + 40) )
                      {
                        if ( psfParent )
                        {
                          v18 = (const struct _GUID *)pidl;
                          if ( pidl )
                          {
                            ppidlLast = 0;
                            if ( SHCreateItemWithParent(
                                   0,
                                   psfParent,
                                   pidl,
                                   &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                   (void **)&ppidlLast) < 0 )
                              goto LABEL_26;
                            IUnknown_Set((IUnknown **)(v26 + 40), (IUnknown *)ppidlLast);
                            v27 = *(int (__fastcall ****)(_QWORD, GUID *, HWND *))(v26 + 40);
                            if ( v27 )
                            {
                              v28 = *v27;
                              v34 = 0;
                              if ( (*v28)(v27, &GUID_771e5917_5788_4a36_a276_b0ddbf8e4abf, &v34) >= 0
                                || (v29 = *v27,
                                    v35 = 0,
                                    (*v29)(v27, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (HWND *)&v35) >= 0)
                                && (v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *, HWND *))(*(_QWORD *)v35 + 24LL))(
                                            v35,
                                            0,
                                            &BHID_SFObject,
                                            &GUID_771e5917_5788_4a36_a276_b0ddbf8e4abf,
                                            &v34),
                                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35),
                                    v30 >= 0) )
                              {
                                (*(void (__fastcall **)(HWND))(*(_QWORD *)v34 + 24LL))(v34);
                                (*(void (__fastcall **)(HWND))(*(_QWORD *)v34 + 16LL))(v34);
                              }
                            }
                            goto LABEL_47;
                          }
                        }
                        ppidlLast = 0;
                        if ( (int)CNscTree::_GetTreeItemFolder(this, a4, v18, (void **)&ppidlLast) >= 0 )
                        {
                          IUnknown_Set((IUnknown **)(v26 + 40), *((IUnknown **)this + 66));
LABEL_47:
                          (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&ppidlLast->mkid.cb + 16LL))(ppidlLast);
                        }
                      }
                    }
                  }
                }
              }
LABEL_26:
              if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
                McGenEventWrite_EventWriteTransfer(
                  &Microsoft_Windows_Shell_Core_Provider_Context,
                  ShellTraceId_NamespaceControl_Plus_Calculation_Start,
                  v18,
                  1);
              goto LABEL_28;
            }
          }
        }
      }
    }
  }
  return v36;
}

```

## disassembly

```asm
0x1800287d0  push    rbp
0x1800287d2  push    rbx
0x1800287d3  push    rsi
0x1800287d4  push    rdi
0x1800287d5  push    r12
0x1800287d7  push    r13
0x1800287d9  push    r14
0x1800287db  push    r15
0x1800287dd  lea     rbp, [rsp-1Fh]
0x1800287e2  sub     rsp, 0C8h
0x1800287e9  mov     rax, cs:__security_cookie
0x1800287f0  xor     rax, rsp
0x1800287f3  mov     [rbp+57h+var_48], rax
0x1800287f7  mov     r12, r8
0x1800287fa  mov     [rbp+57h+pidl], r8
0x1800287fe  mov     rsi, rdx
0x180028801  mov     [rbp+57h+psfParent], rdx
0x180028805  xor     r13d, r13d
0x180028808  lea     rax, [rbp+57h+var_C8]
0x18002880c  mov     [rsp+100h+ppidlLast], rax; ppidlLast
0x180028811  mov     r15, r9
0x180028814  lea     rax, [rbp+57h+var_C0]
0x180028818  mov     [rbp+57h+var_B0], r13d
0x18002881c  mov     rbx, rcx
0x18002881f  mov     [rsp+100h+ppv], rax; HWND *
0x180028824  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18002882b  mov     [rbp+57h+var_C8], r13
0x18002882f  xor     r8d, r8d; ppbc
0x180028832  mov     [rbp+57h+var_C0], r13
0x180028836  mov     rdx, r12; pidl
0x180028839  mov     rcx, rsi; psfRoot
0x18002883c  call    cs:__imp_SHBindToFolderIDListParentEx
0x180028842  test    eax, eax
0x180028844  js      loc_180028B5F
0x18002884a  mov     rcx, [rbp+57h+var_C0]
0x18002884e  lea     r14d, [r13+1]
0x180028852  mov     dword ptr [rbp+57h+var_B8], 60400000h
0x180028859  lea     r9, [rbp+57h+var_B8]
0x18002885d  lea     r8, [rbp+57h+var_C8]
0x180028861  mov     edx, r14d
0x180028864  mov     edi, r13d
0x180028867  mov     rax, [rcx]
0x18002886a  mov     rax, [rax+48h]
0x18002886e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028873  test    eax, eax
0x180028875  js      short loc_180028880
0x180028877  mov     edi, dword ptr [rbp+57h+var_B8]
0x18002887a  and     edi, 60400000h
0x180028880  mov     rcx, [rbp+57h+var_C0]
0x180028884  mov     rax, [rcx]
0x180028887  mov     rax, [rax+10h]
0x18002888b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028890  bt      edi, 1Dh
0x180028894  jnb     loc_180028B5F
0x18002889a  mov     eax, [rbx+1C4h]
0x1800288a0  bt      eax, 1Ch
0x1800288a4  jnb     loc_180028BF9
0x1800288aa  mov     [rbp+57h+var_B0], r14d
0x1800288ae  bt      eax, 13h
0x1800288b2  jb      loc_180028B5F
0x1800288b8  lea     r14, [rbx+2B0h]
0x1800288bf  cmp     [r14], r13
0x1800288c2  jnz     short loc_1800288FD
0x1800288c4  mov     rcx, [rbx+0B0h]; punk
0x1800288cb  lea     r8, _GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec; riid
0x1800288d2  mov     r9, r14; ppvOut
0x1800288d5  lea     rdx, IID_IShellTaskScheduler; guidService
0x1800288dc  call    cs:__imp_IUnknown_QueryService
0x1800288e2  test    eax, eax
0x1800288e4  jns     short loc_1800288FD
0x1800288e6  mov     rdx, r14; void **
0x1800288e9  lea     rcx, _GUID_6ccb7be0_6807_11d0_b810_00c04fd706ec; struct _GUID *
0x1800288f0  call    ?CreateDefaultTaskScheduler@@YAJAEBU_GUID@@PEAPEAX@Z; CreateDefaultTaskScheduler(_GUID const &,void * *)
0x1800288f5  test    eax, eax
0x1800288f7  js      loc_180028B5F
0x1800288fd  lea     rdx, [rbp+57h+ppidl]; ppidl
0x180028901  mov     [rbp+57h+ppidl], r13
0x180028905  mov     rcx, rsi; punk
0x180028908  call    cs:__imp_SHGetIDListFromObject
0x18002890e  test    eax, eax
0x180028910  js      loc_180028B5F
0x180028916  mov     rcx, [rbp+57h+ppidl]; pidl1
0x18002891a  mov     rdx, r12; pidl2
0x18002891d  call    cs:__imp_ILCombine
0x180028923  mov     rcx, [rbp+57h+ppidl]; pidl
0x180028927  mov     r13, rax
0x18002892a  call    cs:__imp_ILFree
0x180028930  test    r13, r13
0x180028933  jz      loc_180028B5F
0x180028939  cmp     qword ptr [rbx+2B8h], 0
0x180028941  jz      loc_180028B82
0x180028947  mov     rsi, [rbx+2B8h]
0x18002894e  lock inc dword ptr [rsi+68h]
0x180028952  mov     r9, r13; struct _ITEMIDLIST_ABSOLUTE *
0x180028955  xor     r8d, r8d; struct IShellFolder *
0x180028958  mov     rdx, r15; struct _TREEITEM *
0x18002895b  mov     rcx, rbx; this
0x18002895e  call    ?_GetEnumFlags@CNscTree@@AEAAKPEAU_TREEITEM@@PEAUIShellFolder@@PEBU_ITEMIDLIST_ABSOLUTE@@PEAPEAUHWND__@@@Z; CNscTree::_GetEnumFlags(_TREEITEM *,IShellFolder *,_ITEMIDLIST_ABSOLUTE const *,HWND__ * *)
0x180028963  xor     r12d, r12d
0x180028966  mov     dword ptr [rbp+57h+var_B8], eax
0x180028969  test    r15, r15
0x18002896c  jz      short loc_1800289B7
0x18002896e  cmp     r15, 0FFFFFFFFFFFF0000h
0x180028975  jz      short loc_1800289B7
0x180028977  mov     rcx, [rbx+190h]; hWnd
0x18002897e  lea     r9, [rbp+57h+lParam]; lParam
0x180028982  xorps   xmm0, xmm0
0x180028985  xor     eax, eax
0x180028987  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18002898b  xor     r8d, r8d; wParam
0x18002898e  mov     dword ptr [rbp+57h+lParam], 14h
0x180028995  mov     edx, 113Eh; Msg
0x18002899a  mov     [rbp+57h+lParam+8], r15
0x18002899e  movups  [rbp+57h+var_90], xmm0
0x1800289a2  mov     [rbp+57h+var_70], rax
0x1800289a6  movups  [rbp+57h+var_80], xmm0
0x1800289aa  call    cs:__imp_SendMessageW
0x1800289b0  test    eax, eax
0x1800289b2  cmovnz  r12, [rbp+57h+var_70]
0x1800289b7  mov     eax, [rbx+1C8h]
0x1800289bd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800289c4  mov     dword ptr [rbp+57h+var_C0], eax
0x1800289c7  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800289cc  mov     al, [rbx+300h]
0x1800289d2  mov     [rbp+57h+var_D0], al
0x1800289d5  mov     rax, [r14]
0x1800289d8  mov     [rbp+57h+var_C8], rax
0x1800289dc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800289e1  xor     r14d, r14d
0x1800289e4  mov     [rbp+57h+var_58], rax
0x1800289e8  mov     rdi, rax
0x1800289eb  test    rax, rax
0x1800289ee  jz      loc_180028B45
0x1800289f4  mov     qword ptr [rax+28h], 1
0x1800289fc  mov     [rax+30h], r14d
0x180028a00  mov     [rax+38h], r14
0x180028a04  mov     [rax+40h], r14d
0x180028a08  lea     rax, ??_7CNscPlusTask@@6BIRunnableTask@@@; const CNscPlusTask::`vftable'{for `IRunnableTask'}
0x180028a0f  mov     [rdi], rax
0x180028a12  lea     rax, ??_7CNscSortTask@@6BIServiceProvider@@@; const CNscSortTask::`vftable'{for `IServiceProvider'}
0x180028a19  mov     [rdi+8], rax
0x180028a1d  lea     rax, ??_7CNscSortTask@@6BIQueryContinue@@@; const CNscSortTask::`vftable'{for `IQueryContinue'}
0x180028a24  mov     [rdi+10h], rax
0x180028a28  lea     rax, ??_7CComCatCacheTask@@6BIObjectWithCancelEvent@@@; const CComCatCacheTask::`vftable'{for `IObjectWithCancelEvent'}
0x180028a2f  mov     [rdi+18h], rax
0x180028a33  lea     rax, ??_7CFrameTask@@6BITestRunnableTask@@@; const CFrameTask::`vftable'{for `ITestRunnableTask'}
0x180028a3a  mov     [rdi+20h], rax
0x180028a3e  movzx   eax, [rbp+57h+var_D0]
0x180028a42  mov     [rdi+68h], eax
0x180028a45  mov     eax, dword ptr [rbp+57h+var_B8]
0x180028a48  mov     [rdi+6Ch], eax
0x180028a4b  mov     eax, dword ptr [rbp+57h+var_C0]
0x180028a4e  mov     [rdi+70h], eax
0x180028a51  mov     [rdi+58h], r15
0x180028a55  mov     [rdi+60h], r14
0x180028a59  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180028a60  mov     [rdi+50h], r14
0x180028a64  mov     [rdi+48h], rsi
0x180028a68  lock inc dword ptr [rsi+68h]
0x180028a6c  test    r12, r12
0x180028a6f  jz      short loc_180028A7B
0x180028a71  mov     [rdi+60h], r12
0x180028a75  lock inc dword ptr [r12+38h]
0x180028a7b  test    rdi, rdi
0x180028a7e  jz      loc_180028B45
0x180028a84  mov     rcx, r13; pidl
0x180028a87  call    cs:__imp_ILClone
0x180028a8d  mov     rcx, rax
0x180028a90  mov     [rdi+50h], rax
0x180028a94  neg     rcx
0x180028a97  sbb     r14d, r14d
0x180028a9a  not     r14d
0x180028a9d  and     r14d, 8007000Eh
0x180028aa4  test    rax, rax
0x180028aa7  jz      short loc_180028AD2
0x180028aa9  mov     rcx, [rbp+57h+var_C8]
0x180028aad  lea     r8, TASKID_PlusExtraction
0x180028ab4  or      r9, 0FFFFFFFFFFFFFFFFh
0x180028ab8  mov     dword ptr [rsp+100h+ppv], 10000001h
0x180028ac0  mov     rdx, rdi
0x180028ac3  mov     rax, [rcx]
0x180028ac6  mov     rax, [rax+18h]
0x180028aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028acf  mov     r14d, eax
0x180028ad2  mov     rax, [rdi]
0x180028ad5  mov     rcx, rdi
0x180028ad8  mov     rax, [rax+10h]
0x180028adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ae1  test    r14d, r14d
0x180028ae4  js      short loc_180028B45
0x180028ae6  xor     r14d, r14d
0x180028ae9  test    r15, r15
0x180028aec  jz      short loc_180028B38
0x180028aee  cmp     r15, 0FFFFFFFFFFFF0000h
0x180028af5  jz      short loc_180028B38
0x180028af7  mov     rcx, [rbx+190h]; hWnd
0x180028afe  lea     r9, [rbp+57h+lParam]; lParam
0x180028b02  xorps   xmm0, xmm0
0x180028b05  xor     eax, eax
0x180028b07  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x180028b0b  xor     r8d, r8d; wParam
0x180028b0e  mov     dword ptr [rbp+57h+lParam], 14h
0x180028b15  mov     edx, 113Eh; Msg
0x180028b1a  mov     [rbp+57h+lParam+8], r15
0x180028b1e  movups  [rbp+57h+var_90], xmm0
0x180028b22  mov     [rbp+57h+var_70], rax
0x180028b26  movups  [rbp+57h+var_80], xmm0
0x180028b2a  call    cs:__imp_SendMessageW
0x180028b30  test    eax, eax
0x180028b32  jnz     loc_180028C31
0x180028b38  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180028b3f  jnz     loc_180028C0A
0x180028b45  or      eax, 0FFFFFFFFh
0x180028b48  lock xadd [rsi+68h], eax
0x180028b4d  cmp     eax, 1
0x180028b50  jz      loc_180028D25
0x180028b56  mov     rcx, r13; pidl
0x180028b59  call    cs:__imp_ILFree
0x180028b5f  mov     eax, [rbp+57h+var_B0]
0x180028b62  mov     rcx, [rbp+57h+var_48]
0x180028b66  xor     rcx, rsp; StackCookie
0x180028b69  call    __security_check_cookie
0x180028b6e  add     rsp, 0C8h
0x180028b75  pop     r15
0x180028b77  pop     r14
0x180028b79  pop     r13
0x180028b7b  pop     r12
0x180028b7d  pop     rdi
0x180028b7e  pop     rsi
0x180028b7f  pop     rbx
0x180028b80  pop     rbp
0x180028b81  retn
0x180028b82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180028b89  mov     qword ptr [rbx+2B8h], 0
0x180028b94  mov     ecx, 78h ; 'x'; unsigned __int64
0x180028b99  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180028b9e  mov     [rbp+57h+var_C8], rax
0x180028ba2  mov     rdi, rax
0x180028ba5  test    rax, rax
0x180028ba8  jz      short loc_180028B56
0x180028baa  xor     edx, edx; Val
0x180028bac  mov     rcx, rax; void *
0x180028baf  lea     r8d, [rdx+78h]; Size
0x180028bb3  call    memset_0
0x180028bb8  mov     rcx, rdi; this
0x180028bbb  call    ??0CNscLock@@QEAA@XZ; CNscLock::CNscLock(void)
0x180028bc0  mov     rdi, rax
0x180028bc3  test    rax, rax
0x180028bc6  jz      short loc_180028B56
0x180028bc8  mov     rdx, rbx; struct CNscTree *
0x180028bcb  mov     rcx, rax; this
0x180028bce  call    ?Init@CNscLock@@QEAAJPEAVCNscTree@@@Z; CNscLock::Init(CNscTree *)
0x180028bd3  mov     esi, eax
0x180028bd5  test    eax, eax
0x180028bd7  js      short loc_180028BE4
0x180028bd9  mov     [rbx+2B8h], rdi
0x180028be0  lock inc dword ptr [rdi+68h]
0x180028be4  mov     rcx, rdi; this
0x180028be7  call    ?Release@CTaskLock@@QEAAJXZ; CTaskLock::Release(void)
0x180028bec  test    esi, esi
0x180028bee  jns     loc_180028947
0x180028bf4  jmp     loc_180028B56
0x180028bf9  cmp     edi, 60400000h
0x180028bff  jnz     loc_1800288AA
0x180028c05  jmp     loc_180028B5F
0x180028c0a  lea     rax, [rbp+57h+var_58]
0x180028c0e  mov     r9d, 1
0x180028c14  lea     rdx, ShellTraceId_NamespaceControl_Plus_Calculation_Start
0x180028c1b  mov     [rsp+100h+ppv], rax
0x180028c20  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180028c27  call    McGenEventWrite_EventWriteTransfer
0x180028c2c  jmp     loc_180028B45
0x180028c31  mov     rdi, [rbp+57h+var_70]
0x180028c35  test    rdi, rdi
0x180028c38  jz      loc_180028B38
0x180028c3e  cmp     [rdi+28h], r14
0x180028c42  jnz     loc_180028B38
0x180028c48  mov     rdx, [rbp+57h+psfParent]; psfParent
0x180028c4c  test    rdx, rdx
0x180028c4f  jz      loc_180028CF7
0x180028c55  mov     r8, [rbp+57h+pidl]; pidl
0x180028c59  test    r8, r8
0x180028c5c  jz      loc_180028CF7
0x180028c62  lea     rax, [rbp+57h+var_C8]
0x180028c66  mov     [rbp+57h+var_C8], r14
0x180028c6a  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180028c71  mov     [rsp+100h+ppv], rax; ppvItem
0x180028c76  xor     ecx, ecx; pidlParent
0x180028c78  call    cs:__imp_SHCreateItemWithParent
0x180028c7e  test    eax, eax
0x180028c80  js      loc_180028B38
0x180028c86  mov     rdx, [rbp+57h+var_C8]; punk
0x180028c8a  lea     rcx, [rdi+28h]; ppunk
0x180028c8e  call    cs:__imp_IUnknown_Set
0x180028c94  mov     rbx, [rdi+28h]
0x180028c98  test    rbx, rbx
0x180028c9b  jz      short loc_180028CE2
0x180028c9d  mov     rax, [rbx]
0x180028ca0  lea     r8, [rbp+57h+var_C0]
0x180028ca4  lea     rdx, _GUID_771e5917_5788_4a36_a276_b0ddbf8e4abf
  ... truncated ...
```
