# Appx::Packaging::Production::AppxPackageWriter::CloseInternal(IStream *,IStream *)

- ea: `0x18007fec0`
- end: `0x18008019b`
- name: `?CloseInternal@AppxPackageWriter@Production@Packaging@Appx@@AEAAJPEAUIStream@@0@Z`
- size: `731`
- prototype: `int(Appx::Packaging::Production::AppxPackageWriter *__hidden this, struct IStream *, struct IStream *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ef850`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180020ff0`
- `0x180071f50`
- `0x18007e568`
- `0x18007fdf4`
- `0x18007fec0`
- `0x1800801a4`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800800fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008010d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008012b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008013b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800800fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008010d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008012b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008013b`

## string_xrefs

- `0x18007ff44`: `AppxManifest.xml`
- `0x18007ffdd`: `AppxContentGroupMap.xml`
- `0x18007ff13`: `onecore\printscan\appxpackaging\production\src\appxpackagewriter.cpp`
- `0x18007ffaf`: `onecore\printscan\appxpackaging\production\src\appxpackagewriter.cpp`
- `0x18008005b`: `onecore\printscan\appxpackaging\production\src\appxpackagewriter.cpp`
- `0x18008009a`: `onecore\printscan\appxpackaging\production\src\appxpackagewriter.cpp`
- `0x1800800e5`: `onecore\printscan\appxpackaging\production\src\appxpackagewriter.cpp`
- `0x18008016c`: `onecore\printscan\appxpackaging\production\src\appxpackagewriter.cpp`
- `0x18007ff34`: `application/vnd.ms-appx.manifest+xml`
- `0x18007ffcd`: `application/vnd.ms-appx.streammap+xml`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Production::AppxPackageWriter::CloseInternal(
        Appx::Packaging::Production::AppxPackageWriter *this,
        struct IStream *a2,
        struct IStream *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  struct IAppxManifestReader *v12; // rdi
  HRESULT (__stdcall *GetPackageId)(IAppxManifestReader *, IAppxManifestPackageId **); // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-60h]
  struct IAppxManifestReader *v20; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+58h] [rbp-28h] BYREF
  struct IAppxContentGroupMapReader *v22; // [rsp+60h] [rbp-20h] BYREF
  LPVOID v23; // [rsp+68h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v26; // [rsp+B8h] [rbp+38h] BYREF

  v20 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v20);
  v6 = Appx::Packaging::Manifest::AppxManifestReaderImpl::Create(a2, &v20, 0, 0);
  if ( v6 < 0 )
  {
    v7 = 383;
LABEL_3:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxpackagewriter.cpp",
      (const char *)(unsigned int)v6,
      v19);
LABEL_4:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v20);
    return (unsigned int)v6;
  }
  v19 = 1;
  v6 = Appx::Packaging::Production::PackageWriterHelper::AddPart(
         *((_QWORD *)this + 5),
         L"AppxManifest.xml",
         0,
         L"application/vnd.ms-appx.manifest+xml");
  if ( v6 < 0 )
  {
    v7 = 393;
    goto LABEL_3;
  }
  if ( a3 )
  {
    v22 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v22);
    v8 = Appx::Packaging::ContentGroupMap::ContentGroupMapReaderImpl::Create(a3, &v22);
    v6 = v8;
    if ( v8 < 0 )
    {
      v9 = (unsigned int)v8;
      v10 = 402;
LABEL_10:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxpackagewriter.cpp",
        (const char *)v9,
        1);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v22);
      goto LABEL_4;
    }
    v11 = Appx::Packaging::Production::PackageWriterHelper::AddPart(
            *((_QWORD *)this + 5),
            L"AppxContentGroupMap.xml",
            0,
            L"application/vnd.ms-appx.streammap+xml");
    v6 = v11;
    if ( v11 < 0 )
    {
      v9 = (unsigned int)v11;
      v10 = 412;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v22);
  }
  if ( *((_DWORD *)this + 22) )
  {
    v12 = v20;
    v21 = 0;
    GetPackageId = v20->lpVtbl->GetPackageId;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v21);
    v14 = ((__int64 (__fastcall *)(struct IAppxManifestReader *, __int64 *))GetPackageId)(v12, &v21);
    v6 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxpackagewriter.cpp",
        (const char *)(unsigned int)v14,
        1);
LABEL_22:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v21);
      goto LABEL_4;
    }
    v23 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v21 + 40LL))(v21, &v23);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxpackagewriter.cpp",
        (const char *)(unsigned int)v15,
        1);
LABEL_21:
      CoTaskMemFree(v23);
      goto LABEL_22;
    }
    v16 = *((_QWORD *)this + 6);
    v26 = 0;
    pv[0] = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, LPVOID, LPVOID *, int *))(*(_QWORD *)v16 + 48LL))(v16, v23, pv, &v26);
    v6 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A9,
        (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxpackagewriter.cpp",
        (const char *)(unsigned int)v17,
        1);
      CoTaskMemFree(pv[0]);
      goto LABEL_21;
    }
    CoTaskMemFree(pv[0]);
    CoTaskMemFree(v23);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v21);
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v20);
  result = Appx::Packaging::Production::PackageWriterHelper::Close(*((Appx::Packaging::Production::PackageWriterHelper **)this
                                                                   + 5));
  v6 = result;
  if ( (int)result >= 0 )
    return result;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1AD,
    (unsigned int)"onecore\\printscan\\appxpackaging\\production\\src\\appxpackagewriter.cpp",
    (const char *)(unsigned int)result,
    1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007fec0  mov     [rsp-18h+arg_0], rbx
0x18007fec5  mov     [rsp-18h+arg_8], rsi
0x18007feca  push    rbp
0x18007fecb  push    rdi
0x18007fecc  push    r14
0x18007fece  mov     rbp, rsp
0x18007fed1  sub     rsp, 80h
0x18007fed8  mov     rsi, rcx
0x18007fedb  mov     [rbp+var_30], 0
0x18007fee3  lea     rcx, [rbp+var_30]
0x18007fee7  mov     rdi, r8
0x18007feea  mov     r14, rdx
0x18007feed  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007fef2  xor     r9d, r9d; unsigned __int16 **
0x18007fef5  lea     rdx, [rbp+var_30]; struct IAppxManifestReader **
0x18007fef9  xor     r8d, r8d; bool
0x18007fefc  mov     rcx, r14; struct IStream *
0x18007feff  call    ?Create@AppxManifestReaderImpl@Manifest@Packaging@Appx@@SAJPEAUIStream@@PEAPEAUIAppxManifestReader@@_NPEAPEAG@Z; Appx::Packaging::Manifest::AppxManifestReaderImpl::Create(IStream *,IAppxManifestReader * *,bool,ushort * *)
0x18007ff04  mov     ebx, eax
0x18007ff06  test    eax, eax
0x18007ff08  jns     short loc_18007FF30
0x18007ff0a  mov     edx, 17Fh; void *
0x18007ff0f  mov     rcx, [rbp+18h]; this
0x18007ff13  lea     r8, aOnecorePrintsc_61; "onecore\\printscan\\appxpackaging\\prod"...
0x18007ff1a  mov     r9d, ebx; char *
0x18007ff1d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007ff22  lea     rcx, [rbp+var_30]
0x18007ff26  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ff2b  jmp     loc_180080180
0x18007ff30  mov     rcx, [rsi+28h]
0x18007ff34  lea     r9, ?ContentType@Manifest@Packaging@Appx@@3QBGB; "application/vnd.ms-appx.manifest+xml"
0x18007ff3b  mov     [rsp+80h+var_40], 0
0x18007ff44  lea     rdx, ?FileName@Manifest@Packaging@Appx@@3QBGB; "AppxManifest.xml"
0x18007ff4b  mov     [rsp+80h+var_48], 0
0x18007ff50  xor     r8d, r8d
0x18007ff53  mov     [rsp+80h+var_50], 1
0x18007ff58  mov     [rsp+80h+var_58], r14
0x18007ff5d  mov     [rsp+80h+var_60], 1; int
0x18007ff65  call    ?AddPart@PackageWriterHelper@Production@Packaging@Appx@@QEAAJQEBGW4FileType@FileNameHelper@34@0W4APPX_COMPRESSION_OPTION@@PEAUIStream@@_N4_K@Z; Appx::Packaging::Production::PackageWriterHelper::AddPart(ushort const * const,Appx::Packaging::FileNameHelper::FileType,ushort const * const,APPX_COMPRESSION_OPTION,IStream *,bool,bool,unsigned __int64)
0x18007ff6a  mov     ebx, eax
0x18007ff6c  test    eax, eax
0x18007ff6e  jns     short loc_18007FF77
0x18007ff70  mov     edx, 189h
0x18007ff75  jmp     short loc_18007FF0F
0x18007ff77  test    rdi, rdi
0x18007ff7a  jz      loc_18008001C
0x18007ff80  lea     rcx, [rbp+var_20]
0x18007ff84  mov     [rbp+var_20], 0
0x18007ff8c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ff91  lea     rdx, [rbp+var_20]; struct IAppxContentGroupMapReader **
0x18007ff95  mov     rcx, rdi; struct IStream *
0x18007ff98  call    ?Create@ContentGroupMapReaderImpl@ContentGroupMap@Packaging@Appx@@SAJPEAUIStream@@PEAPEAUIAppxContentGroupMapReader@@@Z; Appx::Packaging::ContentGroupMap::ContentGroupMapReaderImpl::Create(IStream *,IAppxContentGroupMapReader * *)
0x18007ff9d  mov     ebx, eax
0x18007ff9f  test    eax, eax
0x18007ffa1  jns     short loc_18007FFC9
0x18007ffa3  mov     r9d, eax; char *
0x18007ffa6  mov     edx, 192h; void *
0x18007ffab  mov     rcx, [rbp+18h]; this
0x18007ffaf  lea     r8, aOnecorePrintsc_61; "onecore\\printscan\\appxpackaging\\prod"...
0x18007ffb6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007ffbb  lea     rcx, [rbp+var_20]
0x18007ffbf  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007ffc4  jmp     loc_18007FF22
0x18007ffc9  mov     rcx, [rsi+28h]
0x18007ffcd  lea     r9, ?ContentType@ContentGroupMap@Packaging@Appx@@3QBGB; "application/vnd.ms-appx.streammap+xml"
0x18007ffd4  mov     [rsp+80h+var_40], 0
0x18007ffdd  lea     rdx, ?FileName@ContentGroupMap@Packaging@Appx@@3QBGB; "AppxContentGroupMap.xml"
0x18007ffe4  mov     [rsp+80h+var_48], 0
0x18007ffe9  xor     r8d, r8d
0x18007ffec  mov     [rsp+80h+var_50], 1
0x18007fff1  mov     [rsp+80h+var_58], rdi
0x18007fff6  mov     [rsp+80h+var_60], 1; int
0x18007fffe  call    ?AddPart@PackageWriterHelper@Production@Packaging@Appx@@QEAAJQEBGW4FileType@FileNameHelper@34@0W4APPX_COMPRESSION_OPTION@@PEAUIStream@@_N4_K@Z; Appx::Packaging::Production::PackageWriterHelper::AddPart(ushort const * const,Appx::Packaging::FileNameHelper::FileType,ushort const * const,APPX_COMPRESSION_OPTION,IStream *,bool,bool,unsigned __int64)
0x180080003  mov     ebx, eax
0x180080005  test    eax, eax
0x180080007  jns     short loc_180080013
0x180080009  mov     r9d, eax
0x18008000c  mov     edx, 19Ch
0x180080011  jmp     short loc_18007FFAB
0x180080013  lea     rcx, [rbp+var_20]
0x180080017  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008001c  cmp     dword ptr [rsi+58h], 0
0x180080020  jbe     loc_180080150
0x180080026  mov     rdi, [rbp+var_30]
0x18008002a  lea     rcx, [rbp+var_28]
0x18008002e  mov     [rbp+var_28], 0
0x180080036  mov     rax, [rdi]
0x180080039  mov     rbx, [rax+18h]
0x18008003d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080042  lea     rdx, [rbp+var_28]
0x180080046  mov     rcx, rdi
0x180080049  mov     rax, rbx
0x18008004c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080051  mov     ebx, eax
0x180080053  test    eax, eax
0x180080055  jns     short loc_180080074
0x180080057  mov     rcx, [rbp+18h]; this
0x18008005b  lea     r8, aOnecorePrintsc_61; "onecore\\printscan\\appxpackaging\\prod"...
0x180080062  mov     r9d, eax; char *
0x180080065  mov     edx, 1A2h; void *
0x18008006a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008006f  jmp     loc_180080119
0x180080074  mov     rcx, [rbp+var_28]
0x180080078  lea     rdx, [rbp+var_18]
0x18008007c  mov     [rbp+var_18], 0
0x180080084  mov     rax, [rcx]
0x180080087  mov     rax, [rax+28h]
0x18008008b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080090  mov     ebx, eax
0x180080092  test    eax, eax
0x180080094  jns     short loc_1800800B0
0x180080096  mov     rcx, [rbp+18h]; this
0x18008009a  lea     r8, aOnecorePrintsc_61; "onecore\\printscan\\appxpackaging\\prod"...
0x1800800a1  mov     r9d, eax; char *
0x1800800a4  mov     edx, 1A4h; void *
0x1800800a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800800ae  jmp     short loc_180080109
0x1800800b0  mov     rcx, [rsi+30h]
0x1800800b4  lea     r9, [rbp+arg_18]
0x1800800b8  mov     rdx, [rbp+var_18]
0x1800800bc  lea     r8, [rbp+pv]
0x1800800c0  mov     [rbp+arg_18], 0
0x1800800c7  mov     [rbp+pv], 0
0x1800800cf  mov     rax, [rcx]
0x1800800d2  mov     rax, [rax+30h]
0x1800800d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800800db  mov     ebx, eax
0x1800800dd  test    eax, eax
0x1800800df  jns     short loc_180080127
0x1800800e1  mov     rcx, [rbp+18h]; this
0x1800800e5  lea     r8, aOnecorePrintsc_61; "onecore\\printscan\\appxpackaging\\prod"...
0x1800800ec  mov     r9d, eax; char *
0x1800800ef  mov     edx, 1A9h; void *
0x1800800f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800800f9  mov     rcx, [rbp+pv]; pv
0x1800800fd  call    cs:__imp_CoTaskMemFree
0x180080104  nop     dword ptr [rax+rax+00h]
0x180080109  mov     rcx, [rbp+var_18]; pv
0x18008010d  call    cs:__imp_CoTaskMemFree
0x180080114  nop     dword ptr [rax+rax+00h]
0x180080119  lea     rcx, [rbp+var_28]
0x18008011d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080122  jmp     loc_18007FF22
0x180080127  mov     rcx, [rbp+pv]; pv
0x18008012b  call    cs:__imp_CoTaskMemFree
0x180080132  nop     dword ptr [rax+rax+00h]
0x180080137  mov     rcx, [rbp+var_18]; pv
0x18008013b  call    cs:__imp_CoTaskMemFree
0x180080142  nop     dword ptr [rax+rax+00h]
0x180080147  lea     rcx, [rbp+var_28]
0x18008014b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080150  lea     rcx, [rbp+var_30]
0x180080154  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180080159  mov     rcx, [rsi+28h]; this
0x18008015d  call    ?Close@PackageWriterHelper@Production@Packaging@Appx@@QEAAJXZ; Appx::Packaging::Production::PackageWriterHelper::Close(void)
0x180080162  mov     ebx, eax
0x180080164  test    eax, eax
0x180080166  jns     short loc_180080182
0x180080168  mov     rcx, [rbp+18h]; this
0x18008016c  lea     r8, aOnecorePrintsc_61; "onecore\\printscan\\appxpackaging\\prod"...
0x180080173  mov     r9d, eax; char *
0x180080176  mov     edx, 1ADh; void *
0x18008017b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180080180  mov     eax, ebx
0x180080182  lea     r11, [rsp+80h+var_s0]
0x18008018a  mov     rbx, [r11+20h]
0x18008018e  mov     rsi, [r11+28h]
0x180080192  mov     rsp, r11
0x180080195  pop     r14
0x180080197  pop     rdi
0x180080198  pop     rbp
0x180080199  retn
```
