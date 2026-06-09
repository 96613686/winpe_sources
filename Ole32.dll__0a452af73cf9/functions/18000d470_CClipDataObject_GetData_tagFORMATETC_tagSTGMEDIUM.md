# CClipDataObject::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x18000d470`
- end: `0x18000d94b`
- name: `?GetData@CClipDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `1243`
- prototype: `HRESULT __fastcall(CClipDataObject *this, tagFORMATETC *pformatetc, tagSTGMEDIUM *pmedium)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000aab0`
- `0x18000d300`
- `0x18000d38c`
- `0x18000d470`
- `0x18000d954`
- `0x18000e010`
- `0x18000e034`
- `0x18000e9b4`
- `0x18000ebc8`
- `0x18000ed28`
- `0x18000ef7c`
- `0x18000efd0`
- `0x18000f070`
- `0x180025ffc`
- `0x18002c3c0`
- `0x180031ff0`
- `0x1800405d4`
- `0x1800914dc`
- `0x1800916a0`
- `0x1800918fc`
- `0x180092e10`
- `0x1800a5550`
- `0x1800a55dc`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!Sleep` at `0x18000d76d`
- `KERNELBASE!Sleep` at `0x18000d76d`
- `USER32!OpenClipboard` at `0x18000d613`
- `USER32!OpenClipboard` at `0x18000d776`
- `USER32!OpenClipboard` at `0x18000d613`
- `USER32!OpenClipboard` at `0x18000d776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d8ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d8ae`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000d877`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18000d877`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x18000d8cf`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetClipboardAccessDeniedData` at `0x18000d8cf`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000d621`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x18000d621`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetData(CClipDataObject *this, tagFORMATETC *pformatetc, tagSTGMEDIUM *pmedium)
{
  FormatMatchFlag matched; // r12d
  IDataObject *m_pDataObject; // rcx
  HRESULT Ole2FromOle1; // ebx
  wil::ReportingKind v9; // r8
  unsigned __int64 v10; // r9
  CClipDataObject *v11; // rcx
  HWND PrivateClipboardWindow; // rax
  HWND v13; // rbx
  unsigned int cfFormat; // edx
  FreeResourcesFlags v15; // edx
  ClipboardDataObjectTask *ptr; // rcx
  HWND__ *v18; // rdx
  HBITMAP v19; // rax
  int v20; // ecx
  unsigned __int32 v21; // eax
  ClipboardDataObjectTask *v22; // rdx
  HRESULT TempFileName; // eax
  wchar_t *v24; // rax
  wchar_t *v25; // rcx
  HBITMAP v26; // rax
  void *handle; // [rsp+30h] [rbp-10h] BYREF
  Microsoft::WRL::ComPtr<ClipboardDataObjectTask> pTask; // [rsp+38h] [rbp-8h] BYREF
  OleClipboardLock clipLock; // [rsp+70h] [rbp+30h] BYREF
  tagTYMED tymedOriginal; // [rsp+88h] [rbp+48h] BYREF

  handle = 0;
  tymedOriginal = TYMED_NULL;
  if ( !CThreadCheck::VerifyThreadId(&this->CThreadCheck) )
    return 2147549454LL;
  if ( !pmedium )
    return 2147942487LL;
  *(_OWORD *)&pmedium->tymed = 0;
  pmedium->pUnkForRelease = 0;
  matched = 0;
  CClipDataObject::CacheDataPointer(this, &pTask);
  if ( !this->m_fIsClientAppContainer )
  {
    m_pDataObject = this->m_pDataObject;
    if ( m_pDataObject )
    {
      Ole2FromOle1 = ((__int64 (__fastcall *)(IDataObject *, tagFORMATETC *, tagSTGMEDIUM *))m_pDataObject->lpVtbl[1].QueryInterface)(
                       m_pDataObject,
                       pformatetc,
                       pmedium);
      if ( !Ole2FromOle1 )
      {
        if ( pTask.ptr_ && MediumContainsObject(pmedium) )
          ClipboardDataObjectTask::RunToTimeLimit(v22);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipboardCredentialMonitor>::ReportUsage(
          &`wil::Feature<__WilFeatureTraits_Feature_ClipboardCredentialMonitor>::GetImpl'::`2'::impl,
          1,
          v9,
          v10);
        CClipDataObject::OnPastingData(v11, pmedium, pformatetc);
        goto $errRtn_5;
      }
    }
  }
  if ( (unsigned __int16)(pformatetc->cfFormat - 768) <= 0xFFu
    || (matched = CClipDataObject::MatchFormatetc(this, pformatetc, 1, &tymedOriginal, 1), matched == FORMAT_BADMATCH) )
  {
    Ole2FromOle1 = -2147221404;
    goto $errRtn_5;
  }
  switch ( pformatetc->cfFormat )
  {
    case 2u:
      goto LABEL_40;
    case 3u:
      if ( (pformatetc->tymed & 0x20) == 0 )
        goto LABEL_86;
      pmedium->tymed = 32;
      goto LABEL_18;
    case 9u:
LABEL_40:
      if ( (pformatetc->tymed & 0x10) != 0 )
      {
        pmedium->tymed = 16;
        goto LABEL_18;
      }
      goto LABEL_86;
  }
  if ( pformatetc->cfFormat != 14 )
  {
    if ( tymedOriginal )
    {
      v21 = pformatetc->tymed & tymedOriginal;
      if ( (v21 & 8) != 0 )
        goto LABEL_52;
      if ( (v21 & 1) != 0 )
        goto LABEL_17;
      if ( (v21 & 4) != 0 )
      {
LABEL_60:
        pmedium->tymed = 4;
        goto LABEL_18;
      }
    }
    if ( (pformatetc->tymed & 8) == 0 )
    {
      if ( (pformatetc->tymed & 1) != 0 )
      {
LABEL_17:
        pmedium->tymed = 1;
        goto LABEL_18;
      }
      if ( (pformatetc->tymed & 4) != 0 )
        goto LABEL_60;
LABEL_86:
      Ole2FromOle1 = -2147221399;
      goto $errRtn_5;
    }
LABEL_52:
    pmedium->tymed = 8;
    goto LABEL_18;
  }
  if ( (pformatetc->tymed & 0x40) == 0 )
    goto LABEL_86;
  pmedium->tymed = 64;
LABEL_18:
  if ( !this->m_fIsEdpAccessDenied && CanRetrieveOle2FromOle1(pformatetc->cfFormat) )
  {
    clipLock.m_locked = 0;
    Ole2FromOle1 = OleClipboardLock::Lock(&clipLock, v18, 0);
    if ( Ole2FromOle1 )
    {
      OleClipboardLock::Release(&clipLock);
      goto $errRtn_5;
    }
    Ole2FromOle1 = CClipDataObject::GetOle2FromOle1(this, pformatetc->cfFormat, pmedium);
    OleClipboardLock::Release(&clipLock);
    if ( !Ole2FromOle1 )
    {
      v15 = JUST_RESET;
      goto LABEL_35;
    }
  }
  switch ( pmedium->tymed )
  {
    case 1u:
LABEL_24:
      if ( this->m_fIsEdpAccessDenied )
      {
        Ole2FromOle1 = EdpGetClipboardAccessDeniedData(pformatetc->cfFormat, &handle);
        if ( Ole2FromOle1 >= 0 )
        {
          v26 = (HBITMAP)OleDuplicateData(handle, pformatetc->cfFormat, 0);
          pmedium->hBitmap = v26;
          if ( !v26 )
            Ole2FromOle1 = -2147024882;
        }
      }
      else
      {
        clipLock.m_locked = 0;
        PrivateClipboardWindow = GetPrivateClipboardWindow(CLIP_CREATEIFNOTTHERE);
        v13 = PrivateClipboardWindow;
        if ( PrivateClipboardWindow )
        {
          if ( OpenClipboard(PrivateClipboardWindow) || (Sleep(0), OpenClipboard(v13)) )
          {
            if ( (unsigned int)EdpGetIsManaged() )
              EdpInlSetCurrentThreadPolicyEvaluation(1);
            cfFormat = pformatetc->cfFormat;
            clipLock.m_locked = 1;
            Ole2FromOle1 = CClipDataObject::OleGetClipboardData(this, cfFormat, &handle);
            if ( !Ole2FromOle1 )
            {
              v19 = (HBITMAP)OleDuplicateData(handle, pformatetc->cfFormat, 0);
              v20 = 0;
              pmedium->hBitmap = v19;
              if ( !v19 )
                v20 = -2147024882;
              Ole2FromOle1 = v20;
            }
            if ( OleClipboardLock::Release(&clipLock) < 0 && !Ole2FromOle1 )
              Ole2FromOle1 = -2147221036;
          }
          else
          {
            Ole2FromOle1 = -2147221040;
          }
        }
        else
        {
          Ole2FromOle1 = -2147467259;
        }
        OleClipboardLock::Release(&clipLock);
      }
      goto LABEL_32;
    case 2u:
      v24 = (wchar_t *)CoTaskMemAlloc(0x20Au);
      pmedium->hBitmap = (HBITMAP)v24;
      if ( !v24 )
      {
        Ole2FromOle1 = -2147024882;
        goto LABEL_33;
      }
      TempFileName = UtGetTempFileName(v25, v24);
      goto LABEL_76;
    case 4u:
      if ( !this->m_fIsClientAppContainer )
      {
        TempFileName = CreateStreamOnHGlobal(0, 1, &pmedium->pstm);
        goto LABEL_76;
      }
LABEL_72:
      Ole2FromOle1 = -2147221399;
      goto LABEL_33;
  }
  if ( pmedium->tymed != 8 )
  {
    if ( pmedium->tymed != 16 && pmedium->tymed != 32 && pmedium->tymed != 64 )
    {
      Ole2FromOle1 = -2147418113;
      goto LABEL_33;
    }
    goto LABEL_24;
  }
  if ( this->m_fIsClientAppContainer )
    goto LABEL_72;
  TempFileName = UtCreateStorageOnHGlobal((void *)(pmedium->tymed - 8), 1, &pmedium->pstg, 0);
LABEL_76:
  Ole2FromOle1 = TempFileName;
  if ( TempFileName )
    goto LABEL_33;
  Ole2FromOle1 = CClipDataObject::GetDataHereImpl(this, pformatetc, pmedium, 1);
LABEL_32:
  if ( Ole2FromOle1 )
LABEL_33:
    ReleaseStgMedium(pmedium);
  v15 = RESET_AND_FREE;
LABEL_35:
  CClipDataObject::FreeResources(this, v15);
$errRtn_5:
  OleClipboardTracing::CClipDataObject_GetDataEtw(
    Ole2FromOle1,
    pformatetc,
    pmedium,
    matched,
    this->m_pDataObject,
    pTask.ptr_);
  ptr = pTask.ptr_;
  if ( pTask.ptr_ )
  {
    pTask.ptr_ = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase>::Release((Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ITypeLibRegistrationReader,Microsoft::WRL::FtmBase> *)ptr);
  }
  return (unsigned int)Ole2FromOle1;
}

```

## disassembly

```asm
0x18000d470  mov     [rsp-28h+arg_8], rbx
0x18000d475  mov     [rsp-28h+arg_10], rsi
0x18000d47a  push    rbp
0x18000d47b  push    rdi
0x18000d47c  push    r12
0x18000d47e  push    r14
0x18000d480  push    r15
0x18000d482  mov     rbp, rsp
0x18000d485  sub     rsp, 40h
0x18000d489  mov     rsi, this
0x18000d48c  mov     [rbp+handle], 0
0x18000d494  add     this, 10h; this
0x18000d498  mov     [rbp+tymedOriginal], 0
0x18000d49f  mov     rdi, pmedium
0x18000d4a2  mov     r14, pformatetc
0x18000d4a5  call    ?VerifyThreadId@CThreadCheck@@QEAAHXZ; CThreadCheck::VerifyThreadId(void)
0x18000d4aa  test    eax, eax
0x18000d4ac  jz      loc_18000D78E
0x18000d4b2  test    rdi, rdi
0x18000d4b5  jz      loc_18000D798
0x18000d4bb  xorps   xmm0, xmm0
0x18000d4be  lea     pformatetc, [rbp+pTask]; result
0x18000d4c2  xor     eax, eax
0x18000d4c4  mov     this, rsi; this
0x18000d4c7  movups  xmmword ptr [rdi], xmm0
0x18000d4ca  mov     [rdi+10h], rax
0x18000d4ce  xor     r12d, r12d
0x18000d4d1  call    ?CacheDataPointer@CClipDataObject@@QEAA?AV?$ComPtr@VClipboardDataObjectTask@@@WRL@Microsoft@@XZ; CClipDataObject::CacheDataPointer(void)
0x18000d4d6  cmp     [rsi+44h], r12b
0x18000d4da  jnz     short loc_18000D52B
0x18000d4dc  mov     this, [rsi+38h]
0x18000d4e0  test    this, this
0x18000d4e3  jz      short loc_18000D52B
0x18000d4e5  mov     rax, [this]
0x18000d4e8  mov     pmedium, rdi
0x18000d4eb  mov     pformatetc, r14
0x18000d4ee  mov     rax, [rax+18h]
0x18000d4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4f7  mov     ebx, eax
0x18000d4f9  test    eax, eax
0x18000d4fb  jnz     short loc_18000D52B
0x18000d4fd  mov     pformatetc, [rbp+pTask.ptr_]
0x18000d501  test    pformatetc, pformatetc
0x18000d504  jnz     loc_18000D7A2
0x18000d50a  mov     edx, 1; __annotation("WILSTG:|41016858|Feature_ClipboardCredentialMonitor|AlwaysEnabled")
0x18000d50f  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ClipboardCredentialMonitor@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ClipboardCredentialMonitor@@@details@3@XZ@4V453@A; this
0x18000d516  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ClipboardCredentialMonitor@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipboardCredentialMonitor>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000d51b  mov     pmedium, r14; pformatetc
0x18000d51e  mov     pformatetc, rdi; pmedium
0x18000d521  call    ?OnPastingData@CClipDataObject@@AEAAXPEBUtagSTGMEDIUM@@QEAUtagFORMATETC@@@Z; CClipDataObject::OnPastingData(tagSTGMEDIUM const *,tagFORMATETC * const)
0x18000d526  jmp     $errRtn_5
0x18000d52b  movzx   eax, word ptr [r14]
0x18000d52f  mov     ecx, 300h
0x18000d534  sub     ax, cx
0x18000d537  mov     ecx, 0FFh
0x18000d53c  cmp     ax, cx
0x18000d53f  jbe     loc_18000D6C8
0x18000d545  mov     r15d, 1
0x18000d54b  lea     r9, [rbp+tymedOriginal]; ptymed
0x18000d54f  mov     r8d, r15d; fNativeOnly
0x18000d552  mov     [rsp+40h+fAllowSynthesized], r15d; fAllowSynthesized
0x18000d557  mov     pformatetc, r14; pformatetc
0x18000d55a  mov     this, rsi; this
0x18000d55d  call    ?MatchFormatetc@CClipDataObject@@AEAA?AW4FormatMatchFlag@@PEAUtagFORMATETC@@HPEAW4tagTYMED@@H@Z; CClipDataObject::MatchFormatetc(tagFORMATETC *,int,tagTYMED *,int)
0x18000d562  mov     r12d, eax
0x18000d565  cmp     eax, 2
0x18000d568  jz      loc_18000D6C8
0x18000d56e  movzx   ecx, word ptr [r14]
0x18000d572  sub     ecx, 2
0x18000d575  jz      loc_18000D6CF
0x18000d57b  sub     ecx, r15d
0x18000d57e  jz      loc_18000D7EB
0x18000d584  sub     ecx, 6
0x18000d587  jz      loc_18000D6CF
0x18000d58d  cmp     ecx, 5
0x18000d590  jz      loc_18000D7D5
0x18000d596  mov     eax, [rbp+tymedOriginal]
0x18000d599  test    eax, eax
0x18000d59b  jnz     loc_18000D746
0x18000d5a1  test    byte ptr [r14+18h], 8
0x18000d5a6  jnz     loc_18000D760
0x18000d5ac  test    [r14+18h], r15b
0x18000d5b0  jz      loc_18000D7BF
0x18000d5b6  mov     [rdi], r15d
0x18000d5b9  cmp     byte ptr [rsi+45h], 0
0x18000d5bd  jz      loc_18000D6E5
0x18000d5c3  mov     ecx, [rdi]
0x18000d5c5  sub     ecx, r15d
0x18000d5c8  jz      short loc_18000D5EE
0x18000d5ca  sub     ecx, r15d
0x18000d5cd  jz      loc_18000D8A9
0x18000d5d3  sub     ecx, 2
0x18000d5d6  jz      loc_18000D868
0x18000d5dc  sub     ecx, 4; fDeleteOnRelease
0x18000d5df  jz      loc_18000D847
0x18000d5e5  sub     ecx, 8
0x18000d5e8  jnz     loc_18000D82B
0x18000d5ee  cmp     byte ptr [rsi+45h], 0
0x18000d5f2  jnz     loc_18000D8C7
0x18000d5f8  mov     ecx, r15d; fFlags
0x18000d5fb  mov     [rbp+clipLock.m_locked], 0
0x18000d5ff  call    ?GetPrivateClipboardWindow@@YAPEAUHWND__@@W4tagCLIPWINDOWFLAGS@@@Z; GetPrivateClipboardWindow(tagCLIPWINDOWFLAGS)
0x18000d604  mov     rbx, rax
0x18000d607  test    rax, rax
0x18000d60a  jz      loc_18000D906
0x18000d610  mov     this, rax; hWndNewOwner
0x18000d613  call    cs:__imp_OpenClipboard
0x18000d619  test    eax, eax
0x18000d61b  jz      loc_18000D76B
0x18000d621  call    cs:__imp_EdpGetIsManaged
0x18000d627  test    eax, eax
0x18000d629  jnz     loc_18000D910
0x18000d62f  movzx   edx, word ptr [r14]; cf
0x18000d633  lea     pmedium, [rbp+handle]; phglobal
0x18000d637  mov     this, rsi; this
0x18000d63a  mov     [rbp+clipLock.m_locked], r15b
0x18000d63e  call    ?OleGetClipboardData@CClipDataObject@@AEAAJIPEAPEAX@Z; CClipDataObject::OleGetClipboardData(uint,void * *)
0x18000d643  mov     ebx, eax
0x18000d645  test    eax, eax
0x18000d647  jz      loc_18000D71E
0x18000d64d  lea     this, [rbp+clipLock]; this
0x18000d651  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000d656  test    eax, eax
0x18000d658  js      loc_18000D91D
0x18000d65e  lea     this, [rbp+clipLock]; this
0x18000d662  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000d667  test    ebx, ebx
0x18000d669  jz      short loc_18000D673
0x18000d66b  mov     this, rdi; LPSTGMEDIUM
0x18000d66e  call    ReleaseStgMedium
0x18000d673  mov     edx, r15d; fFlags
0x18000d676  mov     this, rsi; this
0x18000d679  call    ?FreeResources@CClipDataObject@@AEAAXW4FreeResourcesFlags@@@Z; CClipDataObject::FreeResources(FreeResourcesFlags)
0x18000d67e  mov     rax, [rbp+pTask.ptr_]
0x18000d682  mov     r9d, r12d; formatMatchFlag
0x18000d685  mov     [rsp+40h+var_18], rax; pTask
0x18000d68a  mov     pmedium, rdi; pmedium
0x18000d68d  mov     rax, [rsi+38h]
0x18000d691  mov     pformatetc, r14; pformatetc
0x18000d694  mov     ecx, ebx; hr
0x18000d696  mov     qword ptr [rsp+40h+fAllowSynthesized], rax; pDataObject
0x18000d69b  call    ?CClipDataObject_GetDataEtw@OleClipboardTracing@@SAXJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@W4FormatMatchFlag@@PEAUIDataObject@@PEAVClipboardDataObjectTask@@@Z; OleClipboardTracing::CClipDataObject_GetDataEtw(long,tagFORMATETC *,tagSTGMEDIUM *,FormatMatchFlag,IDataObject *,ClipboardDataObjectTask *)
0x18000d6a0  mov     this, [rbp+pTask.ptr_]; this
0x18000d6a4  test    this, this
0x18000d6a7  jnz     loc_18000D939
0x18000d6ad  mov     eax, ebx
0x18000d6af  lea     r11, [rsp+40h+var_s0]
0x18000d6b4  mov     rbx, [r11+38h]
0x18000d6b8  mov     rsi, [r11+40h]
0x18000d6bc  mov     rsp, r11
0x18000d6bf  pop     r15
0x18000d6c1  pop     r14
0x18000d6c3  pop     r12
0x18000d6c5  pop     rdi
0x18000d6c6  pop     rbp
0x18000d6c7  retn
0x18000d6c8  mov     ebx, 80040064h
0x18000d6cd  jmp     short $errRtn_5
0x18000d6cf  test    byte ptr [r14+18h], 10h
0x18000d6d4  jz      loc_18000D92F
0x18000d6da  mov     dword ptr [rdi], 10h
0x18000d6e0  jmp     loc_18000D5B9
0x18000d6e5  movzx   ecx, word ptr [r14]; cf
0x18000d6e9  call    ?CanRetrieveOle2FromOle1@@YAHI@Z; CanRetrieveOle2FromOle1(uint)
0x18000d6ee  test    eax, eax
0x18000d6f0  jz      loc_18000D5C3
0x18000d6f6  xor     r8d, r8d; hClipWnd
0x18000d6f9  mov     [rbp+clipLock.m_locked], 0
0x18000d6fd  lea     this, [rbp+clipLock]; this
0x18000d701  call    ?Lock@OleClipboardLock@@QEAAJPEAUHWND__@@PEAPEAU2@@Z; OleClipboardLock::Lock(HWND__ *,HWND__ * *)
0x18000d706  mov     ebx, eax
0x18000d708  test    eax, eax
0x18000d70a  jz      loc_18000D801
0x18000d710  lea     this, [rbp+clipLock]; this
0x18000d714  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000d719  jmp     $errRtn_5
0x18000d71e  movzx   edx, word ptr [r14]; cfFormat
0x18000d722  xor     r8d, r8d; uiFlags
0x18000d725  mov     this, [rbp+handle]; hSrc
0x18000d729  call    OleDuplicateData
0x18000d72e  mov     ecx, ebx
0x18000d730  mov     [rdi+8], rax
0x18000d734  mov     ebx, 8007000Eh
0x18000d739  test    rax, rax
0x18000d73c  cmovz   ecx, ebx
0x18000d73f  mov     ebx, ecx
0x18000d741  jmp     loc_18000D64D
0x18000d746  and     eax, [r14+18h]
0x18000d74a  test    al, 8
0x18000d74c  jnz     short loc_18000D760
0x18000d74e  test    r15b, al
0x18000d751  jnz     loc_18000D5B6
0x18000d757  test    al, 4
0x18000d759  jnz     short loc_18000D7CA
0x18000d75b  jmp     loc_18000D5A1
0x18000d760  mov     dword ptr [rdi], 8
0x18000d766  jmp     loc_18000D5B9
0x18000d76b  xor     ecx, ecx; dwMilliseconds
0x18000d76d  call    cs:__imp_Sleep
0x18000d773  mov     this, rbx; hWndNewOwner
0x18000d776  call    cs:__imp_OpenClipboard
0x18000d77c  test    eax, eax
0x18000d77e  jnz     loc_18000D621
0x18000d784  mov     ebx, 800401D0h
0x18000d789  jmp     loc_18000D65E
0x18000d78e  mov     eax, 8001010Eh
0x18000d793  jmp     loc_18000D6AF
0x18000d798  mov     eax, 80070057h
0x18000d79d  jmp     loc_18000D6AF
0x18000d7a2  mov     this, rdi; pmedium
0x18000d7a5  call    ?MediumContainsObject@@YAHPEAUtagSTGMEDIUM@@@Z; MediumContainsObject(tagSTGMEDIUM *)
0x18000d7aa  test    eax, eax
0x18000d7ac  jz      loc_18000D50A
0x18000d7b2  mov     this, pformatetc; this
0x18000d7b5  call    ?RunToTimeLimit@ClipboardDataObjectTask@@UEAAJXZ; ClipboardDataObjectTask::RunToTimeLimit(void)
0x18000d7ba  jmp     loc_18000D50A
0x18000d7bf  test    byte ptr [r14+18h], 4
0x18000d7c4  jz      loc_18000D92F
0x18000d7ca  mov     dword ptr [rdi], 4
0x18000d7d0  jmp     loc_18000D5B9
0x18000d7d5  test    byte ptr [r14+18h], 40h
0x18000d7da  jz      loc_18000D92F
0x18000d7e0  mov     dword ptr [rdi], 40h ; '@'
0x18000d7e6  jmp     loc_18000D5B9
0x18000d7eb  test    byte ptr [r14+18h], 20h
0x18000d7f0  jz      loc_18000D92F
0x18000d7f6  mov     dword ptr [rdi], 20h ; ' '
0x18000d7fc  jmp     loc_18000D5B9
0x18000d801  movzx   edx, word ptr [r14]; cf
0x18000d805  mov     pmedium, rdi; pmedium
0x18000d808  mov     this, rsi; this
0x18000d80b  call    ?GetOle2FromOle1@CClipDataObject@@AEAAJIPEAUtagSTGMEDIUM@@@Z; CClipDataObject::GetOle2FromOle1(uint,tagSTGMEDIUM *)
0x18000d810  lea     this, [rbp+clipLock]; this
0x18000d814  mov     ebx, eax
0x18000d816  call    ?Release@OleClipboardLock@@QEAAJXZ; OleClipboardLock::Release(void)
0x18000d81b  test    ebx, ebx
0x18000d81d  jnz     loc_18000D5C3
0x18000d823  lea     edx, [rbx+2]
0x18000d826  jmp     loc_18000D676
0x18000d82b  sub     ecx, 10h
0x18000d82e  jz      loc_18000D5EE
0x18000d834  cmp     ecx, 20h ; ' '
0x18000d837  jz      loc_18000D5EE
0x18000d83d  mov     ebx, 8000FFFFh
0x18000d842  jmp     loc_18000D66B
0x18000d847  cmp     byte ptr [rsi+44h], 0
0x18000d84b  jnz     short loc_18000D85E
0x18000d84d  lea     pmedium, [rdi+8]; ppILockBytes
0x18000d851  xor     r9d, r9d; hGlobal
0x18000d854  mov     edx, r15d; ppStg
0x18000d857  call    ?UtCreateStorageOnHGlobal@@YAJPEAXHPEAPEAUIStorage@@PEAPEAUILockBytes@@@Z; UtCreateStorageOnHGlobal(void *,int,IStorage * *,ILockBytes * *)
0x18000d85c  jmp     short loc_18000D887
0x18000d85e  mov     ebx, 80040069h
0x18000d863  jmp     loc_18000D66B
0x18000d868  cmp     byte ptr [rsi+44h], 0
0x18000d86c  jnz     short loc_18000D85E
0x18000d86e  lea     pmedium, [rdi+8]; ppstm
0x18000d872  mov     edx, r15d; fDeleteOnRelease
0x18000d875  xor     ecx, ecx; hGlobal
0x18000d877  call    cs:__imp_CreateStreamOnHGlobal
0x18000d87d  jmp     short loc_18000D887
0x18000d87f  mov     pformatetc, rax; pszPrefix
0x18000d882  call    ?UtGetTempFileName@@YAJPEAG0@Z; UtGetTempFileName(ushort *,ushort *)
0x18000d887  mov     ebx, eax
0x18000d889  test    eax, eax
0x18000d88b  jnz     loc_18000D66B
0x18000d891  mov     r9b, r15b; fTryWrappedObject
0x18000d894  mov     pmedium, rdi; pmedium
0x18000d897  mov     pformatetc, r14; pformatetc
0x18000d89a  mov     this, rsi; this
0x18000d89d  call    ?GetDataHereImpl@CClipDataObject@@IEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@_N@Z; CClipDataObject::GetDataHereImpl(tagFORMATETC *,tagSTGMEDIUM *,bool)
0x18000d8a2  mov     ebx, eax
0x18000d8a4  jmp     loc_18000D667
0x18000d8a9  mov     ecx, 20Ah; cb
0x18000d8ae  call    cs:__imp_CoTaskMemAlloc
0x18000d8b4  mov     [rdi+8], rax
0x18000d8b8  test    rax, rax
0x18000d8bb  jnz     short loc_18000D87F
0x18000d8bd  mov     ebx, 8007000Eh
0x18000d8c2  jmp     loc_18000D66B
0x18000d8c7  movzx   ecx, word ptr [r14]
0x18000d8cb  lea     pformatetc, [rbp+handle]
0x18000d8cf  call    cs:__imp_EdpGetClipboardAccessDeniedData
0x18000d8d5  mov     ebx, eax
0x18000d8d7  test    eax, eax
0x18000d8d9  js      loc_18000D667
0x18000d8df  movzx   edx, word ptr [r14]; cfFormat
0x18000d8e3  xor     r8d, r8d; uiFlags
0x18000d8e6  mov     this, [rbp+handle]; hSrc
0x18000d8ea  call    OleDuplicateData
0x18000d8ef  mov     [rdi+8], rax
0x18000d8f3  test    rax, rax
0x18000d8f6  jnz     loc_18000D667
0x18000d8fc  mov     ebx, 8007000Eh
0x18000d901  jmp     loc_18000D667
0x18000d906  mov     ebx, 80004005h
0x18000d90b  jmp     loc_18000D65E
0x18000d910  mov     ecx, r15d; EvaluationDisabled
0x18000d913  call    ?EdpInlSetCurrentThreadPolicyEvaluation@@YAJH@Z; EdpInlSetCurrentThreadPolicyEvaluation(int)
0x18000d918  jmp     loc_18000D62F
  ... truncated ...
```
