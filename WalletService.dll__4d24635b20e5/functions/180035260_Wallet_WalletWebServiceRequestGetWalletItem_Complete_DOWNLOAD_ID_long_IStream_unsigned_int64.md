# Wallet::WalletWebServiceRequestGetWalletItem::Complete(_DOWNLOAD_ID *,long,IStream *,unsigned __int64)

- ea: `0x180035260`
- end: `0x180035486`
- name: `?Complete@WalletWebServiceRequestGetWalletItem@Wallet@@EEAAJPEAU_DOWNLOAD_ID@@JPEAUIStream@@_K@Z`
- size: `550`
- prototype: `__int64 __fastcall(Wallet::WalletWebServiceRequestGetWalletItem *this, struct _DOWNLOAD_ID *, unsigned int, struct IStream *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x18000d8d8`
- `0x180013f78`
- `0x180014328`
- `0x18001aa30`
- `0x180035260`
- `0x180035a10`
- `0x180035c80`
- `0x180036e00`
- `0x18003772c`
- `0x180037ce0`
- `0x180039058`
- `0x180039230`
- `0x180039594`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800353a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800353a2`

## string_xrefs

- `0x1800352d6`: `Update-%s.mswallet`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Wallet::WalletWebServiceRequestGetWalletItem::Complete(
        Wallet::WalletWebServiceRequestGetWalletItem *this,
        struct _DOWNLOAD_ID *a2,
        unsigned int a3,
        struct IStream *a4)
{
  unsigned int v5; // r15d
  int v8; // r8d
  int TemporaryFilename; // eax
  const unsigned __int16 *v10; // r8
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64); // rbx
  __int64 v13; // rax
  struct IWalletItem *v14; // rdx
  Wallet::Utils *v15; // rbx
  unsigned __int64 WalletItemId; // rdi
  struct IWalletItem *v17; // rdx
  __int64 v18; // r14
  unsigned int v19; // edi
  void (__fastcall *v20)(__int64, _BYTE *, __int64, __int64); // rsi
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  struct IWalletItem *v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdi
  void (__fastcall *v28)(__int64, _QWORD, unsigned __int64); // rbx
  unsigned __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v33; // [rsp+30h] [rbp-40h] BYREF
  __int64 v34; // [rsp+38h] [rbp-38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v36[8]; // [rsp+48h] [rbp-28h] BYREF
  struct IStream *v37[4]; // [rsp+50h] [rbp-20h] BYREF
  Wallet::Utils *v38; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v39; // [rsp+C0h] [rbp+50h]

  v5 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v37);
  v34 = 0;
  v38 = 0;
  v33 = 0;
  SystemTimeAsFileTime = 0;
  if ( v8 == -2141577194 || v8 == 5902339 )
  {
    v39 = 200;
    a3 = 5902339;
  }
  else
  {
    v39 = v8 & 0xFFF;
    if ( v8 < 0 )
    {
      v5 = v8;
      goto LABEL_18;
    }
    TemporaryFilename = Wallet::Utils::GenerateTemporaryFilename(L"Update-%s.mswallet");
    if ( TemporaryFilename < 0 )
      goto LABEL_6;
    TemporaryFilename = Wallet::SaveStreamToFile(a4, (const WCHAR *)v37[0], v10);
    if ( TemporaryFilename < 0 )
      goto LABEL_6;
    TemporaryFilename = Wallet::Utils::CreateReadDeleteDssTokenForService(v37[0], &v34);
    if ( TemporaryFilename < 0 )
      goto LABEL_6;
    TemporaryFilename = Wallet::Utils::GetWalletPackageProcessor(&v33, v34);
    if ( TemporaryFilename < 0 )
      goto LABEL_6;
    v11 = v33;
    v12 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 32LL);
    v13 = ce::pointerTo<IWalletNotification>(&v38);
    TemporaryFilename = v12(v11, v13);
    if ( TemporaryFilename < 0 )
      goto LABEL_6;
    if ( (unsigned int)Wallet::Utils::IsItemInDatabase(&v38) )
    {
      v15 = (Wallet::Utils *)*((_QWORD *)this + 4);
      WalletItemId = Wallet::Utils::GetWalletItemId(v38, v14);
      if ( WalletItemId != Wallet::Utils::GetWalletItemId(v15, v17) )
      {
        a3 = -2143682478;
        goto LABEL_18;
      }
      TemporaryFilename = (*(__int64 (__fastcall **)(Wallet::Utils *))(*(_QWORD *)v38 + 144LL))(v38);
      if ( TemporaryFilename < 0 )
LABEL_6:
        v5 = TemporaryFilename;
    }
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Wallet::Utils::SetTFileTimeProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
    *((_QWORD *)this + 4),
    305,
    &SystemTimeAsFileTime);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
LABEL_18:
  DownloadManagerRelease(*((_QWORD *)this + 3));
  v18 = *((_QWORD *)this + 5);
  v19 = *((_DWORD *)this + 14);
  v20 = *(void (__fastcall **)(__int64, _BYTE *, __int64, __int64))(*(_QWORD *)v18 + 24LL);
  ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(v36, (char *)this - 8);
  v21 = v19;
  if ( !v19 )
    v21 = v39;
  v22 = 0;
  if ( !v19 )
    v22 = a3;
  v20(v18, v36, v22, v21);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(v36, v23, v24);
  v27 = *((_QWORD *)this + 6);
  if ( v27 )
  {
    v28 = *(void (__fastcall **)(__int64, _QWORD, unsigned __int64))(*(_QWORD *)v27 + 24LL);
    v29 = Wallet::Utils::GetWalletItemId(*((Wallet::Utils **)this + 4), v25);
    v28(v27, a3, v29);
  }
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v33, v25, v26);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v38, v30, v31);
  tlx::unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>::~unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&v34);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v37);
  return v5;
}

```

## disassembly

```asm
0x180035260  mov     [rsp-38h+arg_8], rbx
0x180035265  push    rbp
0x180035266  push    rsi
0x180035267  push    rdi
0x180035268  push    r12
0x18003526a  push    r13
0x18003526c  push    r14
0x18003526e  push    r15
0x180035270  mov     rbp, rsp
0x180035273  sub     rsp, 70h
0x180035277  mov     r13, rcx
0x18003527a  xor     esi, esi
0x18003527c  lea     rcx, [rbp+var_20]
0x180035280  mov     r15d, esi
0x180035283  mov     rdi, r9
0x180035286  mov     r12d, r8d
0x180035289  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18003528e  mov     [rbp+var_38], rsi
0x180035292  mov     eax, 5A1003h
0x180035297  mov     [rbp+arg_0], rsi
0x18003529b  mov     [rbp+var_40], rsi
0x18003529f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800352a3  cmp     r8d, 805A2016h
0x1800352aa  jz      loc_180035394
0x1800352b0  cmp     r8d, eax
0x1800352b3  jz      loc_180035394
0x1800352b9  mov     ebx, r8d
0x1800352bc  and     ebx, 0FFFh
0x1800352c2  mov     [rbp+arg_10], ebx
0x1800352c5  test    r8d, r8d
0x1800352c8  jns     short loc_1800352D2
0x1800352ca  mov     r15d, r8d
0x1800352cd  jmp     loc_1800353CD
0x1800352d2  lea     rdx, [rbp+var_20]
0x1800352d6  lea     rcx, aUpdateSMswalle; "Update-%s.mswallet"
0x1800352dd  call    ?GenerateTemporaryFilename@Utils@Wallet@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GenerateTemporaryFilename(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800352e2  test    eax, eax
0x1800352e4  jns     short loc_1800352EE
0x1800352e6  mov     r15d, eax
0x1800352e9  jmp     loc_18003539E
0x1800352ee  mov     rdx, [rbp+var_20]; struct IStream *
0x1800352f2  mov     rcx, rdi; this
0x1800352f5  call    ?SaveStreamToFile@Wallet@@YAJPEAUIStream@@PEBG@Z; Wallet::SaveStreamToFile(IStream *,ushort const *)
0x1800352fa  test    eax, eax
0x1800352fc  js      short loc_1800352E6
0x1800352fe  mov     rcx, [rbp+var_20]
0x180035302  lea     rdx, [rbp+var_38]
0x180035306  call    ?CreateReadDeleteDssTokenForService@Utils@Wallet@@YAJPEBGAEAV?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@@Z; Wallet::Utils::CreateReadDeleteDssTokenForService(ushort const *,tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>> &)
0x18003530b  test    eax, eax
0x18003530d  js      short loc_1800352E6
0x18003530f  mov     rdx, [rbp+var_38]
0x180035313  lea     rcx, [rbp+var_40]
0x180035317  call    ?GetWalletPackageProcessor@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletPackageProcessor@@@ATL@@PEBG@Z; Wallet::Utils::GetWalletPackageProcessor(ATL::CComPtr<IWalletPackageProcessor> &,ushort const *)
0x18003531c  test    eax, eax
0x18003531e  js      short loc_1800352E6
0x180035320  mov     rdi, [rbp+var_40]
0x180035324  lea     rcx, [rbp+arg_0]
0x180035328  mov     rax, [rdi]
0x18003532b  mov     rbx, [rax+20h]
0x18003532f  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180035334  mov     rdx, rax
0x180035337  mov     rcx, rdi
0x18003533a  mov     rax, rbx
0x18003533d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035342  test    eax, eax
0x180035344  js      short loc_1800352E6
0x180035346  lea     rcx, [rbp+arg_0]
0x18003534a  call    ?IsItemInDatabase@Utils@Wallet@@YAHAEBV?$CComPtr@UIWalletItem@@@ATL@@@Z; Wallet::Utils::IsItemInDatabase(ATL::CComPtr<IWalletItem> const &)
0x18003534f  test    eax, eax
0x180035351  jz      short loc_18003539E
0x180035353  mov     rcx, [rbp+arg_0]; this
0x180035357  mov     rbx, [r13+20h]
0x18003535b  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x180035360  mov     rcx, rbx; this
0x180035363  mov     rdi, rax
0x180035366  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x18003536b  cmp     rdi, rax
0x18003536e  jz      short loc_180035378
0x180035370  mov     r12d, 803A0052h
0x180035376  jmp     short loc_1800353CD
0x180035378  mov     rcx, [rbp+arg_0]
0x18003537c  mov     rax, [rcx]
0x18003537f  mov     rax, [rax+90h]
0x180035386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003538b  test    eax, eax
0x18003538d  jns     short loc_18003539E
0x18003538f  jmp     loc_1800352E6
0x180035394  mov     [rbp+arg_10], 0C8h
0x18003539b  mov     r12d, eax
0x18003539e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800353a2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800353a8  mov     rcx, [r13+20h]
0x1800353ac  lea     r8, [rbp+SystemTimeAsFileTime]
0x1800353b0  mov     edx, 131h
0x1800353b5  call    ??$SetTFileTimeProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEBU_FILETIME@@@Z; Wallet::Utils::SetTFileTimeProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,_FILETIME const &)
0x1800353ba  mov     rcx, [r13+20h]
0x1800353be  mov     rax, [rcx]
0x1800353c1  mov     rax, [rax+90h]
0x1800353c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353cd  mov     rcx, [r13+18h]
0x1800353d1  call    DownloadManagerRelease
0x1800353d6  mov     r14, [r13+28h]
0x1800353da  lea     rdx, [r13-8]
0x1800353de  mov     edi, [r13+38h]
0x1800353e2  lea     rcx, [rbp+var_28]
0x1800353e6  mov     rax, [r14]
0x1800353e9  mov     rsi, [rax+18h]
0x1800353ed  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x1800353f2  test    edi, edi
0x1800353f4  lea     rdx, [rbp+var_28]
0x1800353f8  mov     r9d, edi
0x1800353fb  mov     rcx, r14
0x1800353fe  cmovz   r9d, [rbp+arg_10]
0x180035403  mov     rax, rsi
0x180035406  xor     r8d, r8d
0x180035409  test    edi, edi
0x18003540b  cmovz   r8d, r12d
0x18003540f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035414  lea     rcx, [rbp+var_28]
0x180035418  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18003541d  mov     rdi, [r13+30h]
0x180035421  test    rdi, rdi
0x180035424  jz      short loc_180035447
0x180035426  mov     rax, [rdi]
0x180035429  mov     rcx, [r13+20h]; this
0x18003542d  mov     rbx, [rax+18h]
0x180035431  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x180035436  mov     r8, rax
0x180035439  mov     edx, r12d
0x18003543c  mov     rax, rbx
0x18003543f  mov     rcx, rdi
0x180035442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035447  lea     rcx, [rbp+var_40]
0x18003544b  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180035450  lea     rcx, [rbp+arg_0]
0x180035454  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180035459  lea     rcx, [rbp+var_38]
0x18003545d  call    ??1?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>::~unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(void)
0x180035462  lea     rcx, [rbp+var_20]
0x180035466  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18003546b  mov     rbx, [rsp+70h+arg_8]
0x180035473  mov     eax, r15d
0x180035476  add     rsp, 70h
0x18003547a  pop     r15
0x18003547c  pop     r14
0x18003547e  pop     r13
0x180035480  pop     r12
0x180035482  pop     rdi
0x180035483  pop     rsi
0x180035484  pop     rbp
0x180035485  retn
```
