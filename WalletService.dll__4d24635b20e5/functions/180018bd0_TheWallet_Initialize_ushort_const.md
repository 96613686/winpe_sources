# TheWallet::Initialize(ushort const *)

- ea: `0x180018bd0`
- end: `0x180018f59`
- name: `?Initialize@TheWallet@@MEAAJPEBG@Z`
- size: `905`
- prototype: `__int64 __fastcall(TheWallet *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x180002214`
- `0x180003b40`
- `0x1800082c0`
- `0x18000d8d8`
- `0x180013f78`
- `0x180013fe4`
- `0x1800151c0`
- `0x180018128`
- `0x180018bd0`
- `0x18001d114`
- `0x18001d2a0`
- `0x1800211b4`
- `0x180033350`
- `0x1800336ac`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018f17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018c6d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180018c6d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180018c98`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180018c98`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x180018ca4`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x180018ca4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180018cb3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180018cb3`

## pseudocode

```c
__int64 __fastcall TheWallet::Initialize(TheWallet *this, const unsigned __int16 *a2)
{
  __int64 v3; // r8
  void *v4; // r15
  int WalletAppDataPath; // ebx
  HANDLE FileW; // rax
  Wallet::WalletItemManager *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  struct IWalletItemManager **v10; // r14
  struct IUnknown **v11; // rax
  struct IUnknown **v12; // rbx
  __int64 v13; // rcx
  struct IUnknown *v14; // rdx
  struct IUnknown **v15; // rax
  struct IUnknown **v16; // rbx
  __int64 v17; // rcx
  struct IUnknown *v18; // rdx
  Wallet::WalletWebServiceManager *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rsi
  int v22; // eax
  LPCWSTR lpFileName[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v25[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szFilePath[264]; // [rsp+80h] [rbp-80h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v25);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  v4 = 0;
  if ( v3 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v25,
                             v3) )
      goto LABEL_34;
    lpFileName[1] = lpFileName[0];
    *lpFileName[0] = 0;
  }
  else
  {
    WalletAppDataPath = Wallet::ServerUtils::GetWalletAppDataPath((__int64)v25);
    if ( WalletAppDataPath < 0 )
      goto LABEL_35;
    WalletAppDataPath = Wallet::ServerUtils::GetWalletAppDataParentPath((__int64)lpFileName);
    if ( WalletAppDataPath < 0 )
      goto LABEL_35;
    FileW = CreateFileW(lpFileName[0], 0, 1u, 0, 3u, 0x2000000u, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1LL
      || (GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 0),
          PathCchStripPrefix(szFilePath, 0x104u),
          lstrcmpW(lpFileName[0], szFilePath)) )
    {
      WalletAppDataPath = -2147467259;
      goto LABEL_35;
    }
  }
  v7 = (Wallet::WalletItemManager *)operator new(0xD0u);
  if ( !v7 )
    goto LABEL_34;
  v8 = Wallet::WalletItemManager::WalletItemManager(v7);
  v9 = v8;
  if ( !v8 )
    goto LABEL_34;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v10 = (struct IWalletItemManager **)((char *)this + 16);
  ATL::CComPtrBase<Wallet::IWalletWebServiceRequest>::Attach((char *)this + 16, v9);
  WalletAppDataPath = (*(__int64 (__fastcall **)(struct IWalletItemManager *, _QWORD))(*(_QWORD *)*v10 + 24LL))(
                        *v10,
                        v25[0]);
  if ( WalletAppDataPath < 0 )
    goto LABEL_35;
  v11 = (struct IUnknown **)operator new(0x28u);
  v12 = v11;
  if ( !v11 )
  {
LABEL_34:
    WalletAppDataPath = -2147024882;
    goto LABEL_35;
  }
  *v11 = (struct IUnknown *)&Wallet::WalletNotificationManager::`vftable'{for `IWalletNotificationManager'};
  v11[1] = (struct IUnknown *)&Wallet::WalletNotificationManager::`vftable'{for `IWalletItemListener'};
  v11[2] = (struct IUnknown *)&Wallet::WalletNotificationManager::`vftable'{for `IFastRundown'};
  v11[3] = 0;
  *((_DWORD *)v11 + 8) = 0;
  IncrementServerReferenceCount();
  ((void (__fastcall *)(struct IUnknown **))(*v12)[1].lpVtbl)(v12);
  v13 = *((_QWORD *)this + 5);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  *((_QWORD *)this + 5) = v12;
  v14 = (struct IUnknown *)*v10;
  if ( !*v10 )
    goto LABEL_17;
  if ( v12[3] != v14 )
    ATL::AtlComPtrAssign(v12 + 3, v14);
  WalletAppDataPath = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64))v12[3]->lpVtbl[4].Release)(
                        v12[3],
                        (unsigned __int64)(v12 + 1) & -(__int64)(v12 != 0));
  if ( WalletAppDataPath >= 0 )
  {
    v15 = (struct IUnknown **)operator new(0x28u);
    v16 = v15;
    if ( !v15 )
      goto LABEL_34;
    *v15 = (struct IUnknown *)&Wallet::WalletTransactionManager::`vftable'{for `IWalletTransactionManager'};
    v15[1] = (struct IUnknown *)&Wallet::WalletTransactionManager::`vftable'{for `IWalletItemListener'};
    v15[2] = (struct IUnknown *)&Wallet::WalletTransactionManager::`vftable'{for `IFastRundown'};
    v15[3] = 0;
    v15[4] = 0;
    IncrementServerReferenceCount();
    ((void (__fastcall *)(struct IUnknown **))(*v16)[1].lpVtbl)(v16);
    v17 = *((_QWORD *)this + 6);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 6) = v16;
    v18 = (struct IUnknown *)*v10;
    if ( !*v10 )
    {
LABEL_17:
      WalletAppDataPath = -2147467261;
      goto LABEL_35;
    }
    if ( v16[3] != v18 )
      ATL::AtlComPtrAssign(v16 + 3, v18);
    WalletAppDataPath = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64))v16[3]->lpVtbl[4].Release)(
                          v16[3],
                          (unsigned __int64)(v16 + 1) & -(__int64)(v16 != 0));
    if ( WalletAppDataPath >= 0 )
    {
      WalletAppDataPath = Wallet::WalletLocationManager::CreateInstance(*v10, (char *)this + 56);
      if ( WalletAppDataPath >= 0 )
      {
        v19 = (Wallet::WalletWebServiceManager *)operator new(0x80u);
        if ( v19 )
        {
          v20 = Wallet::WalletWebServiceManager::WalletWebServiceManager(v19);
          v21 = v20;
          if ( v20 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
            ATL::CComPtrBase<Wallet::IWalletWebServiceRequest>::Attach((char *)this + 32, v21);
            v22 = Wallet::WalletWebServiceManager::Initialize(*((Wallet::WalletWebServiceManager **)this + 4), *v10);
            WalletAppDataPath = 0;
            if ( v22 < 0 )
              WalletAppDataPath = v22;
            goto LABEL_35;
          }
        }
        goto LABEL_34;
      }
    }
  }
LABEL_35:
  CloseHandle(v4);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
  return (unsigned int)WalletAppDataPath;
}

```

## disassembly

```asm
0x180018bd0  mov     [rsp-8+arg_10], rbx
0x180018bd5  push    rbp
0x180018bd6  push    rsi
0x180018bd7  push    rdi
0x180018bd8  push    r14
0x180018bda  push    r15
0x180018bdc  lea     rbp, [rsp-1A0h]
0x180018be4  sub     rsp, 2A0h
0x180018beb  mov     rax, cs:__security_cookie
0x180018bf2  xor     rax, rsp
0x180018bf5  mov     [rbp+1C0h+var_30], rax
0x180018bfc  mov     rdi, rcx
0x180018bff  mov     r8, rdx
0x180018c02  lea     rcx, [rsp+2C0h+var_260]
0x180018c07  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180018c0c  lea     rcx, [rsp+2C0h+lpFileName]
0x180018c11  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180018c16  xor     r15d, r15d
0x180018c19  lea     rcx, [rsp+2C0h+var_260]
0x180018c1e  test    r8, r8
0x180018c21  jnz     loc_180018CBF
0x180018c27  call    ?GetWalletAppDataPath@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::ServerUtils::GetWalletAppDataPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180018c2c  mov     ebx, eax
0x180018c2e  test    eax, eax
0x180018c30  js      loc_180018F14
0x180018c36  lea     rcx, [rsp+2C0h+lpFileName]
0x180018c3b  call    ?GetWalletAppDataParentPath@ServerUtils@Wallet@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::ServerUtils::GetWalletAppDataParentPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180018c40  mov     ebx, eax
0x180018c42  test    eax, eax
0x180018c44  js      loc_180018F14
0x180018c4a  mov     rcx, [rsp+2C0h+lpFileName]; lpFileName
0x180018c4f  lea     r8d, [r15+1]; dwShareMode
0x180018c53  mov     [rsp+2C0h+hTemplateFile], r15; hTemplateFile
0x180018c58  xor     r9d, r9d; lpSecurityAttributes
0x180018c5b  mov     [rsp+2C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180018c63  xor     edx, edx; dwDesiredAccess
0x180018c65  mov     [rsp+2C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180018c6d  call    cs:__imp_CreateFileW
0x180018c73  mov     r15, rax
0x180018c76  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018c7a  jnz     short loc_180018C86
0x180018c7c  mov     ebx, 80004005h
0x180018c81  jmp     loc_180018F14
0x180018c86  mov     ebx, 104h
0x180018c8b  lea     rdx, [rbp+1C0h+szFilePath]; lpszFilePath
0x180018c8f  mov     r8d, ebx; cchFilePath
0x180018c92  xor     r9d, r9d; dwFlags
0x180018c95  mov     rcx, rax; hFile
0x180018c98  call    cs:__imp_GetFinalPathNameByHandleW
0x180018c9e  mov     edx, ebx; cchPath
0x180018ca0  lea     rcx, [rbp+1C0h+szFilePath]; pszPath
0x180018ca4  call    cs:__imp_PathCchStripPrefix
0x180018caa  mov     rcx, [rsp+2C0h+lpFileName]; lpString1
0x180018caf  lea     rdx, [rbp+1C0h+szFilePath]; lpString2
0x180018cb3  call    cs:__imp_lstrcmpW
0x180018cb9  test    eax, eax
0x180018cbb  jz      short loc_180018CDE
0x180018cbd  jmp     short loc_180018C7C
0x180018cbf  mov     rdx, r8
0x180018cc2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180018cc7  test    al, al
0x180018cc9  jz      loc_180018F0F
0x180018ccf  mov     rcx, [rsp+2C0h+lpFileName]
0x180018cd4  xor     eax, eax
0x180018cd6  mov     [rsp+2C0h+var_278], rcx
0x180018cdb  mov     [rcx], ax
0x180018cde  mov     ecx, 0D0h; Size
0x180018ce3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ce8  test    rax, rax
0x180018ceb  jz      loc_180018F0F
0x180018cf1  mov     rcx, rax; this
0x180018cf4  call    ??0WalletItemManager@Wallet@@QEAA@XZ; Wallet::WalletItemManager::WalletItemManager(void)
0x180018cf9  mov     rbx, rax
0x180018cfc  test    rax, rax
0x180018cff  jz      loc_180018F0F
0x180018d05  mov     rcx, [rax]
0x180018d08  mov     rax, [rcx+8]
0x180018d0c  mov     rcx, rbx
0x180018d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d14  lea     r14, [rdi+10h]
0x180018d18  mov     rdx, rbx
0x180018d1b  mov     rcx, r14
0x180018d1e  call    ?Attach@?$CComPtrBase@UIWalletWebServiceRequest@Wallet@@@ATL@@QEAAXPEAUIWalletWebServiceRequest@Wallet@@@Z; ATL::CComPtrBase<Wallet::IWalletWebServiceRequest>::Attach(Wallet::IWalletWebServiceRequest *)
0x180018d23  mov     rcx, [r14]
0x180018d26  mov     rdx, [rsp+2C0h+var_260]
0x180018d2b  mov     rax, [rcx]
0x180018d2e  mov     rax, [rax+18h]
0x180018d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d37  mov     ebx, eax
0x180018d39  test    eax, eax
0x180018d3b  js      loc_180018F14
0x180018d41  mov     ecx, 28h ; '('; Size
0x180018d46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018d4b  mov     rbx, rax
0x180018d4e  test    rax, rax
0x180018d51  jz      loc_180018F0F
0x180018d57  lea     rax, ??_7WalletNotificationManager@Wallet@@6BIWalletNotificationManager@@@; const Wallet::WalletNotificationManager::`vftable'{for `IWalletNotificationManager'}
0x180018d5e  mov     [rbx], rax
0x180018d61  lea     rax, ??_7WalletNotificationManager@Wallet@@6BIWalletItemListener@@@; const Wallet::WalletNotificationManager::`vftable'{for `IWalletItemListener'}
0x180018d68  mov     [rbx+8], rax
0x180018d6c  lea     rax, ??_7WalletNotificationManager@Wallet@@6BIFastRundown@@@; const Wallet::WalletNotificationManager::`vftable'{for `IFastRundown'}
0x180018d73  mov     [rbx+10h], rax
0x180018d77  mov     qword ptr [rbx+18h], 0
0x180018d7f  mov     dword ptr [rbx+20h], 0
0x180018d86  call    ?IncrementServerReferenceCount@@YAJXZ; IncrementServerReferenceCount(void)
0x180018d8b  mov     rcx, [rbx]
0x180018d8e  mov     rax, [rcx+8]
0x180018d92  mov     rcx, rbx
0x180018d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d9a  mov     rcx, [rdi+28h]
0x180018d9e  test    rcx, rcx
0x180018da1  jz      short loc_180018DAF
0x180018da3  mov     rax, [rcx]
0x180018da6  mov     rax, [rax+10h]
0x180018daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018daf  mov     [rdi+28h], rbx
0x180018db3  mov     rdx, [r14]; struct IUnknown *
0x180018db6  test    rdx, rdx
0x180018db9  jnz     short loc_180018DC5
0x180018dbb  mov     ebx, 80004003h
0x180018dc0  jmp     loc_180018F14
0x180018dc5  lea     rsi, [rbx+18h]
0x180018dc9  cmp     [rsi], rdx
0x180018dcc  jz      short loc_180018DD6
0x180018dce  mov     rcx, rsi; struct IUnknown **
0x180018dd1  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180018dd6  mov     rcx, [rsi]
0x180018dd9  lea     rax, [rbx+8]
0x180018ddd  neg     rbx
0x180018de0  sbb     rdx, rdx
0x180018de3  mov     r8, [rcx]
0x180018de6  and     rdx, rax
0x180018de9  mov     rax, [r8+70h]
0x180018ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018df2  mov     ebx, eax
0x180018df4  test    eax, eax
0x180018df6  js      loc_180018F14
0x180018dfc  mov     ecx, 28h ; '('; Size
0x180018e01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018e06  mov     rbx, rax
0x180018e09  test    rax, rax
0x180018e0c  jz      loc_180018F0F
0x180018e12  lea     rax, ??_7WalletTransactionManager@Wallet@@6BIWalletTransactionManager@@@; const Wallet::WalletTransactionManager::`vftable'{for `IWalletTransactionManager'}
0x180018e19  mov     [rbx], rax
0x180018e1c  lea     rax, ??_7WalletTransactionManager@Wallet@@6BIWalletItemListener@@@; const Wallet::WalletTransactionManager::`vftable'{for `IWalletItemListener'}
0x180018e23  mov     [rbx+8], rax
0x180018e27  lea     rax, ??_7WalletTransactionManager@Wallet@@6BIFastRundown@@@; const Wallet::WalletTransactionManager::`vftable'{for `IFastRundown'}
0x180018e2e  mov     [rbx+10h], rax
0x180018e32  mov     qword ptr [rbx+18h], 0
0x180018e3a  mov     qword ptr [rbx+20h], 0
0x180018e42  call    ?IncrementServerReferenceCount@@YAJXZ; IncrementServerReferenceCount(void)
0x180018e47  mov     rcx, [rbx]
0x180018e4a  mov     rax, [rcx+8]
0x180018e4e  mov     rcx, rbx
0x180018e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e56  mov     rcx, [rdi+30h]
0x180018e5a  test    rcx, rcx
0x180018e5d  jz      short loc_180018E6B
0x180018e5f  mov     rax, [rcx]
0x180018e62  mov     rax, [rax+10h]
0x180018e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e6b  mov     [rdi+30h], rbx
0x180018e6f  mov     rdx, [r14]; struct IUnknown *
0x180018e72  test    rdx, rdx
0x180018e75  jz      loc_180018DBB
0x180018e7b  lea     rsi, [rbx+18h]
0x180018e7f  cmp     [rsi], rdx
0x180018e82  jz      short loc_180018E8C
0x180018e84  mov     rcx, rsi; struct IUnknown **
0x180018e87  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180018e8c  mov     rcx, [rsi]
0x180018e8f  lea     rax, [rbx+8]
0x180018e93  neg     rbx
0x180018e96  sbb     rdx, rdx
0x180018e99  mov     r8, [rcx]
0x180018e9c  and     rdx, rax
0x180018e9f  mov     rax, [r8+70h]
0x180018ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ea8  mov     ebx, eax
0x180018eaa  test    eax, eax
0x180018eac  js      short loc_180018F14
0x180018eae  mov     rcx, [r14]
0x180018eb1  lea     rdx, [rdi+38h]
0x180018eb5  call    ?CreateInstance@WalletLocationManager@Wallet@@SAJPEAUIWalletItemManager@@AEAV?$CComPtr@VWalletLocationManager@Wallet@@@ATL@@@Z; Wallet::WalletLocationManager::CreateInstance(IWalletItemManager *,ATL::CComPtr<Wallet::WalletLocationManager> &)
0x180018eba  mov     ebx, eax
0x180018ebc  test    eax, eax
0x180018ebe  js      short loc_180018F14
0x180018ec0  mov     ecx, 80h; Size
0x180018ec5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018eca  test    rax, rax
0x180018ecd  jz      short loc_180018F0F
0x180018ecf  mov     rcx, rax; this
0x180018ed2  call    ??0WalletWebServiceManager@Wallet@@QEAA@XZ; Wallet::WalletWebServiceManager::WalletWebServiceManager(void)
0x180018ed7  mov     rsi, rax
0x180018eda  test    rax, rax
0x180018edd  jz      short loc_180018F0F
0x180018edf  mov     rcx, [rax]
0x180018ee2  mov     rax, [rcx+8]
0x180018ee6  mov     rcx, rsi
0x180018ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eee  mov     rdx, rsi
0x180018ef1  lea     rcx, [rdi+20h]
0x180018ef5  call    ?Attach@?$CComPtrBase@UIWalletWebServiceRequest@Wallet@@@ATL@@QEAAXPEAUIWalletWebServiceRequest@Wallet@@@Z; ATL::CComPtrBase<Wallet::IWalletWebServiceRequest>::Attach(Wallet::IWalletWebServiceRequest *)
0x180018efa  mov     rdx, [r14]; struct IWalletItemManager *
0x180018efd  mov     rcx, [rdi+20h]; this
0x180018f01  call    ?Initialize@WalletWebServiceManager@Wallet@@QEAAJPEAUIWalletItemManager@@@Z; Wallet::WalletWebServiceManager::Initialize(IWalletItemManager *)
0x180018f06  xor     ebx, ebx
0x180018f08  test    eax, eax
0x180018f0a  cmovs   ebx, eax
0x180018f0d  jmp     short loc_180018F14
0x180018f0f  mov     ebx, 8007000Eh
0x180018f14  mov     rcx, r15; hObject
0x180018f17  call    cs:__imp_CloseHandle
0x180018f1d  lea     rcx, [rsp+2C0h+lpFileName]
0x180018f22  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180018f27  lea     rcx, [rsp+2C0h+var_260]
0x180018f2c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180018f31  mov     eax, ebx
0x180018f33  mov     rcx, [rbp+1C0h+var_30]
0x180018f3a  xor     rcx, rsp; StackCookie
0x180018f3d  call    __security_check_cookie
0x180018f42  mov     rbx, [rsp+2C0h+arg_10]
0x180018f4a  add     rsp, 2A0h
0x180018f51  pop     r15
0x180018f53  pop     r14
0x180018f55  pop     rdi
0x180018f56  pop     rsi
0x180018f57  pop     rbp
0x180018f58  retn
```
