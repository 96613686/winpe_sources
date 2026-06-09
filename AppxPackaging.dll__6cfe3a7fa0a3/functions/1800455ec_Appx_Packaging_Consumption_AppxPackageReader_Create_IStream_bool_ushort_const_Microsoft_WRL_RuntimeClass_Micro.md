# Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageReader> * *)

- ea: `0x1800455ec`
- end: `0x180045982`
- name: `?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAV?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@Z`
- size: `918`
- prototype: ``
- caller_count: `7`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046f00`
- `0x180076584`
- `0x1800b9ec0`
- `0x1800ba130`
- `0x1800be410`
- `0x1800c1aa0`
- `0x1800f00cc`

## callees

- `0x180005eb8`
- `0x180008114`
- `0x180008488`
- `0x1800133fc`
- `0x180022b50`
- `0x1800455ec`
- `0x180045988`
- `0x1800459f0`
- `0x18004656c`
- `0x180046ce8`
- `0x180046da4`
- `0x180046e28`
- `0x180071f50`
- `0x1800992a0`
- `0x180106010`

## import_xrefs

- `OpcServices!__imp_GetCloneableStream` at `0x180045650`
- `OpcServices!__imp_GetCloneableStream` at `0x180045650`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800458d3`

## string_xrefs

- `0x18004573b`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800457a1`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800457d3`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x180045802`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x180045825`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800458bb`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`
- `0x1800458f4`: `onecore\printscan\appxpackaging\consumption\src\appxpackagereader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::AppxPackageReader::Create(
        __int64 a1,
        char a2,
        Appx::Packaging *a3,
        Appx::Packaging::Consumption::AppxPackageReader **a4)
{
  int CloneableStream; // eax
  unsigned __int64 v9; // r8
  unsigned int v10; // ebx
  int PackagePartsMap; // eax
  Appx::Packaging::Consumption::AppxPackageReader *v12; // rdi
  int v13; // eax
  void *v14; // rbx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int v18; // esi
  Appx::Packaging *v20; // rcx
  void (*v21)(void); // rax
  Appx::Packaging *v22; // rcx
  Appx::Packaging *v23; // rcx
  int PackageFullName; // eax
  __int64 v25; // rcx
  __int64 v26; // rdx
  Appx::Packaging::Consumption::AppxPackageReader **v27; // [rsp+20h] [rbp-50h]
  int v28; // [rsp+20h] [rbp-50h]
  Appx::Packaging *v29; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-38h] BYREF
  Appx::Packaging::Consumption::AppxPackageReader *v31[2]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( !a1 )
  {
    v26 = 207;
LABEL_38:
    v10 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
      (const char *)0x80004003LL,
      (int)v27);
    return v10;
  }
  if ( !a4 )
  {
    v26 = 208;
    goto LABEL_38;
  }
  if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
  {
    v27 = v31;
    McGenEventWrite_EventWriteTransfer(a1, EVENT_PACKAGE_READER_CREATE_START, a3, 1);
  }
  v29 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
  CloneableStream = GetCloneableStream(a1, &v29);
  v10 = CloneableStream;
  if ( CloneableStream < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
      (const char *)(unsigned int)CloneableStream,
      (int)v27);
    v22 = v29;
    if ( !v29 )
      return v10;
    v29 = 0;
    v21 = *(void (**)(void))(*(_QWORD *)v22 + 16LL);
    goto LABEL_20;
  }
  pv[0] = 0;
  PackagePartsMap = Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(v29, (__int64 *)pv, v9);
  v10 = PackagePartsMap;
  if ( PackagePartsMap < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
      (const char *)(unsigned int)PackagePartsMap,
      (int)v27);
LABEL_25:
    Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(pv[0]);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
    return v10;
  }
  Microsoft::WRL::Details::Make<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageReader>,>((__int64 *)v31);
  v12 = v31[0];
  if ( v31[0] )
  {
    Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=((char *)v31[0] + 56, &v29);
    *((_BYTE *)v12 + 40) = a2;
    v13 = Appx::Packaging::Consumption::AppxPackageReader::Initialize(v12);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v14 = pv[0];
      v15 = Appx::Packaging::Consumption::AppxPackageReader::ProcessPackagePartsMap(
              (__int64)v12,
              (struct _RTL_AVL_TABLE *)pv[0],
              0,
              0,
              a3);
      v18 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE8,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
          (const char *)(unsigned int)v15,
          v28);
        if ( v12 )
          (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxPackageReader *))(*(_QWORD *)v12 + 16LL))(v12);
        Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v14);
        v23 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(Appx::Packaging *))(*(_QWORD *)v23 + 16LL))(v23);
        }
        return v18;
      }
      if ( a2 )
      {
        pv[0] = 0;
        PackageFullName = Appx::Packaging::Consumption::AppxPackageReader::GetPackageFullName(
                            v12,
                            (unsigned __int16 **)pv);
        v18 = PackageFullName;
        if ( PackageFullName < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xEE,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
            (const char *)(unsigned int)PackageFullName,
            v28);
          CoTaskMemFree(pv[0]);
LABEL_16:
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v31);
          Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(v14);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v29);
          return v18;
        }
        if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
          McTemplateU0z_EventWriteTransfer(v25, EVENT_PACKAGE_READER_CREATED, pv[0]);
        CoTaskMemFree(pv[0]);
      }
      else if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 2) != 0 )
      {
        McGenEventWrite_EventWriteTransfer(v16, EVENT_PACKAGE_READER_WITHOUT_VALIDATION_CREATED, v17, 1);
      }
      if ( (Microsoft_Windows_AppxPackagingOMEnableBits & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(v16, EVENT_PACKAGE_READER_CREATE_STOP, v17, 1);
      (*(void (__fastcall **)(Appx::Packaging::Consumption::AppxPackageReader *))(*(_QWORD *)v12 + 8LL))(v12);
      v18 = 0;
      *a4 = v12;
      goto LABEL_16;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
      (const char *)(unsigned int)v13,
      (int)v27);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(v31);
    goto LABEL_25;
  }
  v10 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE0,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxpackagereader.cpp",
    (const char *)0x8007000ELL,
    (int)v27);
  Common::AutoPtrDeallocate<Common::GenericMap<unsigned short *,Appx::Packaging::Consumption::AppxFileInfo *>>(pv[0]);
  v20 = v29;
  if ( v29 )
  {
    v29 = 0;
    v21 = *(void (**)(void))(*(_QWORD *)v20 + 16LL);
LABEL_20:
    v21();
  }
  return v10;
}

```

## disassembly

```asm
0x1800455ec  mov     [rsp-28h+arg_8], rbx
0x1800455f1  push    rbp
0x1800455f2  push    rsi
0x1800455f3  push    rdi
0x1800455f4  push    r14
0x1800455f6  push    r15
0x1800455f8  mov     rbp, rsp
0x1800455fb  sub     rsp, 70h
0x1800455ff  mov     rax, cs:__security_cookie
0x180045606  xor     rax, rsp
0x180045609  mov     [rbp+var_8], rax
0x18004560d  mov     r15, r9
0x180045610  mov     rsi, r8
0x180045613  mov     r14b, dl
0x180045616  mov     rbx, rcx
0x180045619  test    rcx, rcx
0x18004561c  jz      loc_1800458E4
0x180045622  test    r9, r9
0x180045625  jz      loc_1800458EB
0x18004562b  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x180045632  jnz     loc_18004590D
0x180045638  lea     rcx, [rbp+var_40]
0x18004563c  mov     [rbp+var_40], 0
0x180045644  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180045649  lea     rdx, [rbp+var_40]
0x18004564d  mov     rcx, rbx
0x180045650  call    cs:__imp_GetCloneableStream
0x180045657  nop     dword ptr [rax+rax+00h]
0x18004565c  mov     ebx, eax
0x18004565e  test    eax, eax
0x180045660  js      loc_18004579D
0x180045666  mov     rcx, [rbp+var_40]
0x18004566a  lea     rdx, [rbp+pv]
0x18004566e  mov     [rbp+pv], 0
0x180045676  call    ?GetPackagePartsMap@PackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEAPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Z; Appx::Packaging::Consumption::PackageReaderHelper::GetPackagePartsMap(IStream *,Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> * *)
0x18004567b  mov     ebx, eax
0x18004567d  test    eax, eax
0x18004567f  js      loc_1800457CF
0x180045685  lea     rcx, [rbp+var_28]
0x180045689  call    ??$Make@V?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@VAppxPackageReader@Consumption@Packaging@Appx@@@WRL@Microsoft@@@12@XZ; Microsoft::WRL::Details::Make<Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Appx::Packaging::Consumption::AppxPackageReader>,>(void)
0x18004568e  mov     rdi, [rbp+var_28]
0x180045692  test    rdi, rdi
0x180045695  jz      loc_180045737
0x18004569b  lea     rcx, [rdi+38h]
0x18004569f  lea     rdx, [rbp+var_40]
0x1800456a3  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x1800456a8  mov     rcx, rdi; this
0x1800456ab  mov     [rdi+28h], r14b
0x1800456af  call    ?Initialize@AppxPackageReader@Consumption@Packaging@Appx@@IEAAJXZ; Appx::Packaging::Consumption::AppxPackageReader::Initialize(void)
0x1800456b4  mov     ebx, eax
0x1800456b6  test    eax, eax
0x1800456b8  js      loc_1800457FE
0x1800456be  mov     rbx, [rbp+pv]
0x1800456c2  xor     r9d, r9d; int
0x1800456c5  mov     rdx, rbx; int
0x1800456c8  mov     [rsp+70h+var_50], rsi; int
0x1800456cd  xor     r8d, r8d; int
0x1800456d0  mov     rcx, rdi; int
0x1800456d3  call    ?ProcessPackagePartsMap@AppxPackageReader@Consumption@Packaging@Appx@@IEAAJPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@_NPEAUSignatureValidationInfo@234@PEBG@Z; Appx::Packaging::Consumption::AppxPackageReader::ProcessPackagePartsMap(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *,bool,Appx::Packaging::Consumption::SignatureValidationInfo *,ushort const *)
0x1800456d8  mov     esi, eax
0x1800456da  test    eax, eax
0x1800456dc  js      loc_180045821
0x1800456e2  test    r14b, r14b
0x1800456e5  jnz     loc_18004587B
0x1800456eb  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 2
0x1800456f2  jnz     loc_180045942
0x1800456f8  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 10h
0x1800456ff  jnz     loc_180045962
0x180045705  mov     rax, [rdi]
0x180045708  mov     rcx, rdi
0x18004570b  mov     rax, [rax+8]
0x18004570f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045714  xor     esi, esi
0x180045716  mov     [r15], rdi
0x180045719  lea     rcx, [rbp+var_28]
0x18004571d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180045722  mov     rcx, rbx
0x180045725  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x18004572a  lea     rcx, [rbp+var_40]
0x18004572e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180045733  mov     eax, esi
0x180045735  jmp     short loc_18004577C
0x180045737  mov     rcx, [rbp+28h]; this
0x18004573b  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x180045742  mov     ebx, 8007000Eh
0x180045747  mov     edx, 0E0h; void *
0x18004574c  mov     r9d, ebx; char *
0x18004574f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045754  mov     rcx, [rbp+pv]
0x180045758  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x18004575d  mov     rcx, [rbp+var_40]
0x180045761  test    rcx, rcx
0x180045764  jz      short loc_18004577A
0x180045766  mov     [rbp+var_40], 0
0x18004576e  mov     rdx, [rcx]
0x180045771  mov     rax, [rdx+10h]
0x180045775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004577a  mov     eax, ebx
0x18004577c  mov     rcx, [rbp+var_8]
0x180045780  xor     rcx, rsp; StackCookie
0x180045783  call    __security_check_cookie
0x180045788  mov     rbx, [rsp+70h+arg_8]
0x180045790  add     rsp, 70h
0x180045794  pop     r15
0x180045796  pop     r14
0x180045798  pop     rdi
0x180045799  pop     rsi
0x18004579a  pop     rbp
0x18004579b  retn
0x18004579d  mov     rcx, [rbp+28h]; this
0x1800457a1  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800457a8  mov     r9d, ebx; char *
0x1800457ab  mov     edx, 0D9h; void *
0x1800457b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800457b5  mov     rcx, [rbp+var_40]
0x1800457b9  test    rcx, rcx
0x1800457bc  jz      short loc_18004577A
0x1800457be  mov     [rbp+var_40], 0
0x1800457c6  mov     rax, [rcx]
0x1800457c9  mov     rax, [rax+10h]
0x1800457cd  jmp     short loc_180045775
0x1800457cf  mov     rcx, [rbp+28h]; this
0x1800457d3  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800457da  mov     r9d, ebx; char *
0x1800457dd  mov     edx, 0DCh; void *
0x1800457e2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800457e7  mov     rcx, [rbp+pv]
0x1800457eb  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x1800457f0  lea     rcx, [rbp+var_40]
0x1800457f4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800457f9  jmp     loc_18004577A
0x1800457fe  mov     rcx, [rbp+28h]; this
0x180045802  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x180045809  mov     r9d, ebx; char *
0x18004580c  mov     edx, 0E3h; void *
0x180045811  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045816  lea     rcx, [rbp+var_28]
0x18004581a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18004581f  jmp     short loc_1800457E7
0x180045821  mov     rcx, [rbp+28h]; this
0x180045825  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x18004582c  mov     r9d, esi; char *
0x18004582f  mov     edx, 0E8h; void *
0x180045834  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045839  test    rdi, rdi
0x18004583c  jz      short loc_18004584D
0x18004583e  mov     rdx, [rdi]
0x180045841  mov     rcx, rdi
0x180045844  mov     rax, [rdx+10h]
0x180045848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004584d  mov     rcx, rbx
0x180045850  call    ??$AutoPtrDeallocate@V?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEAGPEAUAppxFileInfo@Consumption@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *>>(Common::GenericMap<ushort *,Appx::Packaging::Consumption::AppxFileInfo *> *)
0x180045855  mov     rcx, [rbp+var_40]
0x180045859  test    rcx, rcx
0x18004585c  jz      loc_180045733
0x180045862  mov     [rbp+var_40], 0
0x18004586a  mov     rax, [rcx]
0x18004586d  mov     rax, [rax+10h]
0x180045871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045876  jmp     loc_180045733
0x18004587b  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18004587f  mov     [rbp+pv], 0
0x180045887  mov     rcx, rdi; this
0x18004588a  call    ?GetPackageFullName@AppxPackageReader@Consumption@Packaging@Appx@@IEAAJPEAPEAG@Z; Appx::Packaging::Consumption::AppxPackageReader::GetPackageFullName(ushort * *)
0x18004588f  mov     esi, eax
0x180045891  test    eax, eax
0x180045893  js      short loc_1800458B7
0x180045895  test    byte ptr cs:Microsoft_Windows_AppxPackagingOMEnableBits, 2
0x18004589c  jnz     loc_18004592D
0x1800458a2  mov     rcx, [rbp+pv]; pv
0x1800458a6  call    cs:__imp_CoTaskMemFree
0x1800458ad  nop     dword ptr [rax+rax+00h]
0x1800458b2  jmp     loc_1800456F8
0x1800458b7  mov     rcx, [rbp+28h]; this
0x1800458bb  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800458c2  mov     r9d, eax; char *
0x1800458c5  mov     edx, 0EEh; void *
0x1800458ca  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800458cf  mov     rcx, [rbp+pv]; pv
0x1800458d3  call    cs:__imp_CoTaskMemFree
0x1800458da  nop     dword ptr [rax+rax+00h]
0x1800458df  jmp     loc_180045719
0x1800458e4  mov     edx, 0CFh
0x1800458e9  jmp     short loc_1800458F0
0x1800458eb  mov     edx, 0D0h; void *
0x1800458f0  mov     rcx, [rbp+28h]; this
0x1800458f4  lea     r8, aOnecorePrintsc_44; "onecore\\printscan\\appxpackaging\\cons"...
0x1800458fb  mov     ebx, 80004003h
0x180045900  mov     r9d, ebx; char *
0x180045903  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045908  jmp     loc_18004577A
0x18004590d  lea     rax, [rbp+var_28]
0x180045911  mov     r9d, 1
0x180045917  lea     rdx, EVENT_PACKAGE_READER_CREATE_START
0x18004591e  mov     [rsp+70h+var_50], rax
0x180045923  call    McGenEventWrite_EventWriteTransfer
0x180045928  jmp     loc_180045638
0x18004592d  mov     r8, [rbp+pv]
0x180045931  lea     rdx, EVENT_PACKAGE_READER_CREATED
0x180045938  call    McTemplateU0z_EventWriteTransfer
0x18004593d  jmp     loc_1800458A2
0x180045942  lea     rax, [rbp+pv]
0x180045946  mov     r9d, 1
0x18004594c  lea     rdx, EVENT_PACKAGE_READER_WITHOUT_VALIDATION_CREATED
0x180045953  mov     [rsp+70h+var_50], rax
0x180045958  call    McGenEventWrite_EventWriteTransfer
0x18004595d  jmp     loc_1800456F8
0x180045962  lea     rax, [rbp+var_18]
0x180045966  mov     r9d, 1
0x18004596c  lea     rdx, EVENT_PACKAGE_READER_CREATE_STOP
0x180045973  mov     [rsp+70h+var_50], rax
0x180045978  call    McGenEventWrite_EventWriteTransfer
0x18004597d  jmp     loc_180045705
```
