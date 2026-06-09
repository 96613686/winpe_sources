# Appx::Packaging::Consumption::BundlePackageReader::Create(IStream *,bool,ushort const *,IAppxBundleReader * *)

- ea: `0x18008328c`
- end: `0x18008357f`
- name: `?Create@BundlePackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAUIAppxBundleReader@@@Z`
- size: `755`
- prototype: `static int(struct IStream *, bool, const unsigned __int16 *, struct IAppxBundleReader **)`
- caller_count: `6`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180082cb0`
- `0x180091730`
- `0x1800c4d70`
- `0x1800c4d80`
- `0x1800c5430`
- `0x1800f292c`

## callees

- `0x180005eb8`
- `0x180008114`
- `0x180008488`
- `0x180008f4c`
- `0x1800133fc`
- `0x180022b50`
- `0x180046da4`
- `0x180046e28`
- `0x180047244`
- `0x180047d20`
- `0x180071f50`
- `0x18008328c`
- `0x180084400`
- `0x1800992a0`
- `0x1800c9b04`
- `0x180106010`

## import_xrefs

- `OpcServices!__imp_GetCloneableStream` at `0x180083325`
- `OpcServices!__imp_GetCloneableStream` at `0x180083325`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800834fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800834fd`

## string_xrefs

- `0x1800832c5`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x18008333b`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x180083373`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x1800833a2`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x1800833ed`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`
- `0x180083471`: `onecore\printscan\appxpackaging\consumption\src\bundlepackagereader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::BundlePackageReader::Create(
        struct IStream *a1,
        char a2,
        Appx::Packaging *a3,
        struct IAppxBundleReader **a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int CloneableStream; // eax
  unsigned __int64 v11; // r8
  int PackagePartsMap; // eax
  _BYTE *v13; // rbx
  unsigned __int64 *v14; // r8
  int StreamSize; // edi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int BundleFullName; // eax
  __int64 v20; // rcx
  Appx::Packaging *v22; // [rsp+20h] [rbp-50h]
  Appx::Packaging *v23; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-38h] BYREF
  int v25[2]; // [rsp+48h] [rbp-28h] BYREF
  char v26; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( a1 )
  {
    if ( !a4 )
    {
      v8 = 68;
      goto LABEL_3;
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      v22 = (Appx::Packaging *)v25;
      McGenEventWrite_EventWriteTransfer(a1, EVENT_BUNDLE_READER_CREATE_START, a3, 1);
    }
    v23 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v23);
    CloneableStream = GetCloneableStream(a1, &v23);
    v9 = CloneableStream;
    if ( CloneableStream < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
        (const char *)(unsigned int)CloneableStream,
        (int)v22);
LABEL_29:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v23);
      return v9;
    }
    *(_QWORD *)v25 = 0;
    PackagePartsMap = Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(v23, (__int64 *)v25, v11);
    v9 = PackagePartsMap;
    if ( PackagePartsMap < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
        (const char *)(unsigned int)PackagePartsMap,
        (int)v22);
LABEL_28:
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(*(_QWORD *)v25);
      goto LABEL_29;
    }
    Microsoft::WRL::Details::Make<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::BundlePackageReader>,>(pv);
    v13 = pv[0];
    if ( !pv[0] )
    {
      v9 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
        (const char *)0x8007000ELL,
        (int)v22);
      goto LABEL_28;
    }
    Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=((char *)pv[0] + 112, &v23);
    v13[104] = a2;
    StreamSize = Appx::Packaging::GetStreamSize(v23, (struct IStream *)(v13 + 40), v14);
    if ( StreamSize < 0 )
    {
      v16 = 88;
      goto LABEL_16;
    }
    StreamSize = Appx::Packaging::Consumption::BundlePackageReader::Initialize((Appx::Packaging::Consumption::BundlePackageReader *)v13);
    if ( StreamSize < 0 )
    {
      v16 = 90;
      goto LABEL_16;
    }
    StreamSize = Appx::Packaging::Consumption::BundlePackageReader::ProcessPackagePartsMap(
                   (__int64)v13,
                   *(__int64 *)v25,
                   0,
                   0,
                   a3);
    if ( StreamSize < 0 )
    {
      v16 = 95;
      goto LABEL_16;
    }
    if ( a2 )
    {
      pv[0] = 0;
      BundleFullName = Appx::Packaging::Consumption::BundlePackageReader::GetBundleFullName(
                         (Appx::Packaging::Consumption::BundlePackageReader *)v13,
                         (unsigned __int16 **)pv);
      StreamSize = BundleFullName;
      if ( BundleFullName < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x65,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
          (const char *)(unsigned int)BundleFullName,
          (int)v22);
        CoTaskMemFree(pv[0]);
        goto LABEL_25;
      }
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
        McTemplateU0z_EventWriteTransfer(v20, EVENT_BUNDLE_READER_CREATED, pv[0]);
      CoTaskMemFree(pv[0]);
    }
    else if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
    {
      v22 = (Appx::Packaging *)pv;
      McGenEventWrite_EventWriteTransfer(v17, EVENT_BUNDLE_READER_WITHOUT_VALIDATION_CREATED, v18, 1);
    }
    if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
    {
      v22 = (Appx::Packaging *)&v26;
      McGenEventWrite_EventWriteTransfer(v17, EVENT_BUNDLE_READER_CREATE_STOP, v18, 1);
    }
    StreamSize = (**(__int64 (__fastcall ***)(_BYTE *, GUID *, struct IAppxBundleReader **))v13)(
                   v13,
                   &GUID_dd75b8c0_ba76_43b0_ae0f_68656a1dc5c8,
                   a4);
    if ( StreamSize < 0 )
    {
      v16 = 110;
LABEL_16:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
        (const char *)(unsigned int)StreamSize,
        (int)v22);
      if ( v13 )
        goto LABEL_26;
      goto LABEL_27;
    }
LABEL_25:
    if ( v13 )
LABEL_26:
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_27:
    v9 = StreamSize;
    goto LABEL_28;
  }
  v8 = 67;
LABEL_3:
  v9 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\bundlepackagereader.cpp",
    (const char *)0x80004003LL,
    (int)v22);
  return v9;
}

```

## disassembly

```asm
0x18008328c  mov     [rsp-28h+arg_8], rbx
0x180083291  push    rbp
0x180083292  push    rsi
0x180083293  push    rdi
0x180083294  push    r14
0x180083296  push    r15
0x180083298  mov     rbp, rsp
0x18008329b  sub     rsp, 70h
0x18008329f  mov     rax, cs:__security_cookie
0x1800832a6  xor     rax, rsp
0x1800832a9  mov     [rbp+var_8], rax
0x1800832ad  mov     r14, r9
0x1800832b0  mov     r15, r8
0x1800832b3  mov     sil, dl
0x1800832b6  mov     rbx, rcx
0x1800832b9  test    rcx, rcx
0x1800832bc  jnz     short loc_1800832DE
0x1800832be  lea     edx, [rcx+43h]; void *
0x1800832c1  mov     rcx, [rbp+28h]; this
0x1800832c5  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x1800832cc  mov     ebx, 80004003h
0x1800832d1  mov     r9d, ebx; char *
0x1800832d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800832d9  jmp     loc_1800834BD
0x1800832de  test    r14, r14
0x1800832e1  jnz     short loc_1800832E9
0x1800832e3  lea     edx, [r14+44h]
0x1800832e7  jmp     short loc_1800832C1
0x1800832e9  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x1800832f0  jz      short loc_18008330D
0x1800832f2  lea     rax, [rbp+var_28]
0x1800832f6  mov     r9d, 1
0x1800832fc  lea     rdx, EVENT_BUNDLE_READER_CREATE_START
0x180083303  mov     [rsp+70h+var_50], rax; int
0x180083308  call    McGenEventWrite_EventWriteTransfer
0x18008330d  lea     rcx, [rbp+var_40]
0x180083311  mov     [rbp+var_40], 0
0x180083319  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008331e  lea     rdx, [rbp+var_40]
0x180083322  mov     rcx, rbx
0x180083325  call    cs:__imp_GetCloneableStream
0x18008332c  nop     dword ptr [rax+rax+00h]
0x180083331  mov     ebx, eax
0x180083333  test    eax, eax
0x180083335  jns     short loc_180083354
0x180083337  mov     rcx, [rbp+28h]; this
0x18008333b  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x180083342  mov     r9d, eax; char *
0x180083345  mov     edx, 4Eh ; 'N'; void *
0x18008334a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008334f  jmp     loc_1800834B4
0x180083354  mov     rcx, [rbp+var_40]
0x180083358  lea     rdx, [rbp+var_28]
0x18008335c  mov     qword ptr [rbp+var_28], 0
0x180083364  call    ?GetPackagePartsMap@PackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEAPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(IStream *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> * *)
0x180083369  mov     ebx, eax
0x18008336b  test    eax, eax
0x18008336d  jns     short loc_18008338C
0x18008336f  mov     rcx, [rbp+28h]; this
0x180083373  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x18008337a  mov     r9d, eax; char *
0x18008337d  mov     edx, 51h ; 'Q'; void *
0x180083382  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083387  jmp     loc_1800834AB
0x18008338c  lea     rcx, [rbp+pv]
0x180083390  call    ??$Make@V?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VBundlePackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VBundlePackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@12@XZ; Microsoft::WRL::Details::Make<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::BundlePackageReader>,>(void)
0x180083395  mov     rbx, [rbp+pv]
0x180083399  test    rbx, rbx
0x18008339c  jnz     short loc_1800833C0
0x18008339e  mov     rcx, [rbp+28h]; this
0x1800833a2  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x1800833a9  mov     ebx, 8007000Eh
0x1800833ae  mov     edx, 55h ; 'U'; void *
0x1800833b3  mov     r9d, ebx; char *
0x1800833b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800833bb  jmp     loc_1800834AB
0x1800833c0  lea     rcx, [rbx+70h]
0x1800833c4  lea     rdx, [rbp+var_40]
0x1800833c8  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x1800833cd  mov     [rbx+68h], sil
0x1800833d1  lea     rdx, [rbx+28h]; struct IStream *
0x1800833d5  mov     rcx, [rbp+var_40]; this
0x1800833d9  call    ?GetStreamSize@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamSize(IStream *,unsigned __int64 *)
0x1800833de  mov     edi, eax
0x1800833e0  test    eax, eax
0x1800833e2  jns     short loc_180083411
0x1800833e4  mov     edx, 58h ; 'X'; void *
0x1800833e9  mov     rcx, [rbp+28h]; this
0x1800833ed  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x1800833f4  mov     r9d, edi; char *
0x1800833f7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800833fc  test    rbx, rbx
0x1800833ff  jz      loc_1800834A9
0x180083405  mov     rcx, [rbx]
0x180083408  mov     rax, [rcx+10h]
0x18008340c  jmp     loc_1800834A1
0x180083411  mov     rcx, rbx; this
0x180083414  call    ?Initialize@BundlePackageReader@Consumption@Packaging@Appx@@IEAAJXZ; Appx::Packaging::Consumption::BundlePackageReader::Initialize(void)
0x180083419  mov     edi, eax
0x18008341b  test    eax, eax
0x18008341d  jns     short loc_180083426
0x18008341f  mov     edx, 5Ah ; 'Z'
0x180083424  jmp     short loc_1800833E9
0x180083426  mov     rdx, qword ptr [rbp+var_28]; int
0x18008342a  xor     r9d, r9d; int
0x18008342d  xor     r8d, r8d; int
0x180083430  mov     [rsp+70h+var_50], r15; int
0x180083435  mov     rcx, rbx; int
0x180083438  call    ?ProcessPackagePartsMap@BundlePackageReader@Consumption@Packaging@Appx@@IEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@_NPEAUSignatureValidationInfo@234@PEBG@Z; Appx::Packaging::Consumption::BundlePackageReader::ProcessPackagePartsMap(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,bool,Appx::Packaging::Consumption::SignatureValidationInfo *,ushort const *)
0x18008343d  mov     edi, eax
0x18008343f  test    eax, eax
0x180083441  jns     short loc_18008344A
0x180083443  mov     edx, 5Fh ; '_'
0x180083448  jmp     short loc_1800833E9
0x18008344a  test    sil, sil
0x18008344d  jz      loc_18008350B
0x180083453  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180083457  mov     [rbp+pv], 0
0x18008345f  mov     rcx, rbx; this
0x180083462  call    ?GetBundleFullName@BundlePackageReader@Consumption@Packaging@Appx@@IEAAJPEAPEAG@Z; Appx::Packaging::Consumption::BundlePackageReader::GetBundleFullName(ushort * *)
0x180083467  mov     edi, eax
0x180083469  test    eax, eax
0x18008346b  jns     short loc_1800834E0
0x18008346d  mov     rcx, [rbp+28h]; this
0x180083471  lea     r8, aOnecorePrintsc_125; "onecore\\printscan\\appxpackaging\\cons"...
0x180083478  mov     r9d, eax; char *
0x18008347b  mov     edx, 65h ; 'e'; void *
0x180083480  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083485  mov     rcx, [rbp+pv]; pv
0x180083489  call    cs:__imp_CoTaskMemFree
0x180083490  nop     dword ptr [rax+rax+00h]
0x180083495  test    rbx, rbx
0x180083498  jz      short loc_1800834A9
0x18008349a  mov     rax, [rbx]
0x18008349d  mov     rax, [rax+10h]
0x1800834a1  mov     rcx, rbx
0x1800834a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800834a9  mov     ebx, edi
0x1800834ab  mov     rcx, qword ptr [rbp+var_28]
0x1800834af  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x1800834b4  lea     rcx, [rbp+var_40]
0x1800834b8  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800834bd  mov     eax, ebx
0x1800834bf  mov     rcx, [rbp+var_8]
0x1800834c3  xor     rcx, rsp; StackCookie
0x1800834c6  call    __security_check_cookie
0x1800834cb  mov     rbx, [rsp+70h+arg_8]
0x1800834d3  add     rsp, 70h
0x1800834d7  pop     r15
0x1800834d9  pop     r14
0x1800834db  pop     rdi
0x1800834dc  pop     rsi
0x1800834dd  pop     rbp
0x1800834de  retn
0x1800834e0  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 2
0x1800834e7  jz      short loc_1800834F9
0x1800834e9  mov     r8, [rbp+pv]
0x1800834ed  lea     rdx, EVENT_BUNDLE_READER_CREATED
0x1800834f4  call    McTemplateU0z_EventWriteTransfer
0x1800834f9  mov     rcx, [rbp+pv]; pv
0x1800834fd  call    cs:__imp_CoTaskMemFree
0x180083504  nop     dword ptr [rax+rax+00h]
0x180083509  jmp     short loc_18008352F
0x18008350b  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 2
0x180083512  jz      short loc_18008352F
0x180083514  lea     rax, [rbp+pv]
0x180083518  mov     r9d, 1
0x18008351e  lea     rdx, EVENT_BUNDLE_READER_WITHOUT_VALIDATION_CREATED
0x180083525  mov     [rsp+70h+var_50], rax
0x18008352a  call    McGenEventWrite_EventWriteTransfer
0x18008352f  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x180083536  jz      short loc_180083553
0x180083538  lea     rax, [rbp+var_18]
0x18008353c  mov     r9d, 1
0x180083542  lea     rdx, EVENT_BUNDLE_READER_CREATE_STOP
0x180083549  mov     [rsp+70h+var_50], rax
0x18008354e  call    McGenEventWrite_EventWriteTransfer
0x180083553  mov     rax, [rbx]
0x180083556  lea     rdx, _GUID_dd75b8c0_ba76_43b0_ae0f_68656a1dc5c8
0x18008355d  mov     r8, r14
0x180083560  mov     rcx, rbx
0x180083563  mov     rax, [rax]
0x180083566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008356b  mov     edi, eax
0x18008356d  test    eax, eax
0x18008356f  jns     loc_180083495
0x180083575  mov     edx, 6Eh ; 'n'
0x18008357a  jmp     loc_1800833E9
```
