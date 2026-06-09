# Appx::Packaging::Consumption::AppxEncryptedBundleReader::CreateAppxFilesWithManifestData(Appx::Packaging::EncryptedAppxHeader const &,Appx::Packaging::EncryptedAppxFootersReader *,uint,Appx::Packaging::AppxEncryptionSettings *)

- ea: `0x1800728bc`
- end: `0x180072eb1`
- name: `?CreateAppxFilesWithManifestData@AppxEncryptedBundleReader@Consumption@Packaging@Appx@@IEAAJAEBVEncryptedAppxHeader@34@PEAVEncryptedAppxFootersReader@34@IPEAVAppxEncryptionSettings@34@@Z`
- size: `1525`
- prototype: `__int64 __fastcall(Appx::Packaging::Consumption::AppxEncryptedBundleReader *__hidden this, const struct Appx::Packaging::EncryptedAppxHeader *, struct Appx::Packaging::EncryptedAppxFootersReader *, unsigned int, struct Appx::Packaging::AppxEncryptionSettings *)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006d578`
- `0x1800844ac`

## callees

- `0x180005eb8`
- `0x180006de4`
- `0x180008f4c`
- `0x1800133fc`
- `0x180019950`
- `0x180046fe4`
- `0x180071f50`
- `0x1800728bc`
- `0x180072eb8`
- `0x180072f14`
- `0x180072fec`
- `0x180073184`
- `0x180073388`
- `0x1800992d0`
- `0x1800cab20`
- `0x180106010`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180072e69`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180072e69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072e36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072d7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180072e36`

## string_xrefs

- `0x18007291a`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072964`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x1800729ef`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072a29`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072ce3`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072d0d`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072d2b`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072d59`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072df4`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`
- `0x180072e23`: `onecore\printscan\appxpackaging\consumption\src\appxencryptedbundlereader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::AppxEncryptedBundleReader::CreateAppxFilesWithManifestData(
        Appx::Packaging::Consumption::AppxEncryptedBundleReader *this,
        const struct Appx::Packaging::EncryptedAppxHeader *a2,
        struct Appx::Packaging::EncryptedAppxFootersReader *a3,
        unsigned int a4,
        struct Appx::Packaging::AppxEncryptionSettings *a5)
{
  __int64 v5; // rdi
  int v7; // r13d
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, struct IUri **); // rbx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // eax
  struct _RTL_AVL_TABLE *v18; // rdi
  __int64 v19; // r9
  __int64 v20; // rdx
  void *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  unsigned __int64 *v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rsi
  unsigned __int64 v27; // r15
  struct _RTL_AVL_TABLE *v28; // r12
  Appx::Packaging *v29; // rcx
  int StreamSize; // eax
  int v31; // eax
  unsigned __int64 v32; // r15
  unsigned int v33; // esi
  __int64 v34; // rsi
  void (__fastcall *v35)(__int64, struct IAppxBundleManifestPackageInfo **); // rbx
  int v36; // eax
  __int64 Element; // rax
  __int64 v38; // rcx
  int v39; // eax
  struct Appx::Packaging::Consumption::EncryptedBundlePayloadPackage *v40; // rbx
  int AppendedSize; // eax
  __int64 (__fastcall *v42)(struct Appx::Packaging::Consumption::EncryptedBundlePayloadPackage *, GUID *, __int64 *); // rsi
  int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r9
  __int64 v46; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  unsigned int v50; // ebx
  int v51; // [rsp+20h] [rbp-51h]
  struct IAppxBundleManifestPackageInfo *v52; // [rsp+40h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-29h] BYREF
  struct Appx::Packaging::Consumption::EncryptedBundlePayloadPackage *v54; // [rsp+50h] [rbp-21h] BYREF
  PRTL_AVL_TABLE Table; // [rsp+58h] [rbp-19h] BYREF
  __int64 v56; // [rsp+60h] [rbp-11h] BYREF
  __int64 v57; // [rsp+68h] [rbp-9h] BYREF
  struct IUri *v58; // [rsp+70h] [rbp-1h] BYREF
  __int64 v59; // [rsp+78h] [rbp+7h] BYREF
  unsigned __int64 v60[8]; // [rsp+80h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]
  int v62; // [rsp+D0h] [rbp+5Fh] BYREF
  unsigned int v63; // [rsp+E8h] [rbp+77h]

  v63 = a4;
  v5 = *((_QWORD *)this + 4);
  v7 = 0;
  v56 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 32LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
  v11 = v10(v5, &v56);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
      (const char *)(unsigned int)v11,
      v51);
    goto LABEL_59;
  }
  v13 = *((_QWORD *)this + 3);
  v58 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, struct IUri **))(*(_QWORD *)v13 + 40LL);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
  v15 = v14(v13, &v58);
  v12 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
      (const char *)(unsigned int)v15,
      v51);
    goto LABEL_58;
  }
  Table = 0;
  v17 = Appx::Packaging::Consumption::AppxEncryptedBundleReader::CreateFileOffsetToFooterMap(v16, a3, &Table);
  v18 = Table;
  v12 = v17;
  if ( v17 < 0 )
  {
    v19 = (unsigned int)v17;
    v20 = 300;
LABEL_16:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
      (const char *)v19,
      v51);
    goto LABEL_57;
  }
  v21 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v21 )
    v23 = Common::GenericMap<unsigned short const *,IAppxFile *>::GenericMap<unsigned short const *,IAppxFile *>(
            v21,
            v22,
            0);
  else
    v23 = 0;
  Common::AutoPtr<Common::GenericMap<unsigned short const *,IAppxFile *>,&void Common::AutoPtrDeallocate<Common::GenericMap<unsigned short const *,IAppxFile *>>(Common::GenericMap<unsigned short const *,IAppxFile *> *)>::operator=(
    (char *)this + 248,
    v23);
  if ( !*((_QWORD *)this + 31) )
  {
    v12 = -2147024882;
    v25 = 307;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
      (const char *)v12,
      v51);
    goto LABEL_57;
  }
  v26 = *((_QWORD *)a2 + 2);
  v27 = *((_QWORD *)a2 + 1);
  if ( v27 > ~v26 )
  {
    v20 = 311;
LABEL_15:
    v12 = -2147024362;
    v19 = 2147942934LL;
    goto LABEL_16;
  }
  v28 = (struct _RTL_AVL_TABLE *)*((_QWORD *)a2 + 4);
  Table = v28;
  if ( !v28 )
  {
    v29 = (Appx::Packaging *)*((_QWORD *)this + 30);
    if ( v29 )
    {
      StreamSize = Appx::Packaging::GetStreamSize(v29, (struct IStream *)&Table, v24);
      v12 = StreamSize;
      if ( StreamSize < 0 )
      {
        v19 = (unsigned int)StreamSize;
        v20 = 315;
        goto LABEL_16;
      }
      v28 = Table;
    }
  }
  v62 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v56 + 32LL))(v56, &v62);
  v12 = v31;
  if ( v31 < 0 )
  {
    v19 = (unsigned int)v31;
    v20 = 320;
    goto LABEL_16;
  }
  v32 = v26 + v27;
  v33 = 0;
  while ( 1 )
  {
    if ( v62 != 1 )
    {
      v50 = v63;
      if ( v63 > ~v7 )
      {
        v20 = 391;
        goto LABEL_15;
      }
      if ( v50 + v7 != RtlNumberGenericTableElementsAvl(v18) )
      {
        v12 = -2147024883;
        v25 = 392;
        goto LABEL_12;
      }
      if ( *((_QWORD *)this + 30) && (struct _RTL_AVL_TABLE *)v32 != v28 )
      {
        v12 = -2147024883;
        v25 = 401;
        goto LABEL_12;
      }
      goto LABEL_56;
    }
    v52 = 0;
    v34 = v56;
    v35 = *(void (__fastcall **)(__int64, struct IAppxBundleManifestPackageInfo **))(*(_QWORD *)v56 + 24LL);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
    v35(v34, &v52);
    v33 = 0;
    pv = 0;
    v36 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, LPVOID *))v52->lpVtbl->GetFileName)(
            v52,
            &pv);
    v12 = v36;
    if ( v36 < 0 )
    {
      v49 = 329;
      goto LABEL_70;
    }
    Table = 0;
    v36 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, PRTL_AVL_TABLE *))v52->lpVtbl->GetOffset)(
            v52,
            &Table);
    v12 = v36;
    if ( v36 < 0 )
    {
      v49 = 333;
      goto LABEL_70;
    }
    v59 = 0;
    v36 = ((__int64 (__fastcall *)(struct IAppxBundleManifestPackageInfo *, __int64 *))v52->lpVtbl->GetSize)(v52, &v59);
    v12 = v36;
    if ( v36 < 0 )
    {
      v49 = 336;
      goto LABEL_70;
    }
    if ( Table )
      break;
LABEL_44:
    v36 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v56 + 40LL))(v56, &v62);
    v12 = v36;
    if ( v36 < 0 )
    {
      v49 = 385;
LABEL_70:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)v36,
        v51);
      goto LABEL_71;
    }
    CoTaskMemFree(pv);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
  }
  Element = Common::GenericMap<unsigned short *,IXMLDOMNode *>::FindElement(v18, &Table);
  if ( Element )
  {
    v38 = *(_QWORD *)(Element + 8);
    if ( v38 )
    {
      if ( *(_DWORD *)(v38 + 4) )
      {
        v48 = 345;
        goto LABEL_64;
      }
      if ( *(_QWORD *)(v38 + 24) != v59 )
      {
        v12 = -2146958844;
        v48 = 349;
        goto LABEL_65;
      }
      v54 = 0;
      if ( !*((_QWORD *)this + 30) )
      {
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
        v39 = Appx::Packaging::Consumption::EncryptedBundlePayloadPackage::CreateStreaming(v52, a5, &v54);
        v12 = v39;
        if ( v39 >= 0 )
        {
          v40 = v54;
          goto LABEL_41;
        }
        v44 = 357;
LABEL_47:
        v45 = (unsigned int)v39;
LABEL_48:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v44,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
          (const char *)v45,
          v51);
        goto LABEL_49;
      }
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
      v39 = Appx::Packaging::Consumption::EncryptedBundlePayloadPackage::CreateNonstreaming(
              v52,
              *((struct IStream **)this + 30),
              v58,
              (Appx::Packaging::Consumption::AppxEncryptedBundleReader *)((char *)this + 64),
              a5,
              v32,
              &v54);
      v12 = v39;
      if ( v39 < 0 )
      {
        v44 = 368;
        goto LABEL_47;
      }
      v40 = v54;
      v60[0] = 0;
      AppendedSize = Appx::Packaging::Consumption::EncryptedBundlePayloadPackage::GetAppendedSize(v54, v60);
      v33 = AppendedSize;
      if ( AppendedSize >= 0 )
      {
        if ( v32 > -1LL - v60[0] )
        {
          v12 = -2147024362;
          v44 = 372;
          v45 = 2147942934LL;
          goto LABEL_48;
        }
        v32 += v60[0];
        if ( v32 > (unsigned __int64)v28 )
        {
          v12 = -2147024883;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x175,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
            (const char *)0x8007000DLL,
            v51);
        }
        else
        {
LABEL_41:
          v57 = 0;
          v42 = **(__int64 (__fastcall ***)(struct Appx::Packaging::Consumption::EncryptedBundlePayloadPackage *, GUID *, __int64 *))v40;
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
          v43 = v42(v40, &GUID_91df827b_94fd_468f_827b_57f41b2f6f2e, &v57);
          v33 = 0;
          v12 = v43;
          if ( v43 < 0 )
          {
            v46 = 377;
          }
          else
          {
            v43 = Common::GenericMap<unsigned short *,unsigned short *>::Insert(*((_QWORD *)this + 31), pv, v57);
            v12 = v43;
            if ( v43 >= 0 )
            {
              v57 = 0;
              pv = 0;
              ++v7;
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
              Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
              goto LABEL_44;
            }
            v46 = 378;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v46,
            (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
            (const char *)(unsigned int)v43,
            v51);
          Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v57);
        }
LABEL_49:
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
        goto LABEL_71;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
        (const char *)(unsigned int)AppendedSize,
        v51);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v54);
      CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
LABEL_56:
      v12 = v33;
      goto LABEL_57;
    }
  }
  v48 = 342;
LABEL_64:
  v12 = -2147024883;
LABEL_65:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v48,
    (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\appxencryptedbundlereader.cpp",
    (const char *)v12,
    v51);
LABEL_71:
  CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v52);
LABEL_57:
  Common::AutoPtrDeallocate<Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *>>(v18);
LABEL_58:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v58);
LABEL_59:
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v56);
  return v12;
}

```

## disassembly

```asm
0x1800728bc  mov     [rsp-8+arg_8], rbx
0x1800728c1  mov     [rsp-8+arg_18], r9d
0x1800728c6  push    rbp
0x1800728c7  push    rsi
0x1800728c8  push    rdi
0x1800728c9  push    r12
0x1800728cb  push    r13
0x1800728cd  push    r14
0x1800728cf  push    r15
0x1800728d1  lea     rbp, [rsp-1Fh]
0x1800728d6  sub     rsp, 90h
0x1800728dd  mov     rdi, [rcx+20h]
0x1800728e1  mov     r14, rcx
0x1800728e4  xor     r13d, r13d
0x1800728e7  lea     rcx, [rbp+4Fh+var_60]
0x1800728eb  mov     [rbp+4Fh+var_60], r13
0x1800728ef  mov     rsi, r8
0x1800728f2  mov     r12, rdx
0x1800728f5  mov     rax, [rdi]
0x1800728f8  mov     rbx, [rax+20h]
0x1800728fc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072901  lea     rdx, [rbp+4Fh+var_60]
0x180072905  mov     rcx, rdi
0x180072908  mov     rax, rbx
0x18007290b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072910  mov     ebx, eax
0x180072912  test    eax, eax
0x180072914  jns     short loc_180072933
0x180072916  mov     rcx, [rbp+57h]; this
0x18007291a  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180072921  mov     r9d, eax; char *
0x180072924  mov     edx, 126h; void *
0x180072929  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007292e  jmp     loc_180072DA2
0x180072933  mov     rdi, [r14+18h]
0x180072937  lea     rcx, [rbp+4Fh+var_50]
0x18007293b  mov     [rbp+4Fh+var_50], r13
0x18007293f  mov     rax, [rdi]
0x180072942  mov     rbx, [rax+28h]
0x180072946  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18007294b  lea     rdx, [rbp+4Fh+var_50]
0x18007294f  mov     rcx, rdi
0x180072952  mov     rax, rbx
0x180072955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007295a  mov     ebx, eax
0x18007295c  test    eax, eax
0x18007295e  jns     short loc_18007297D
0x180072960  mov     rcx, [rbp+57h]; this
0x180072964  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x18007296b  mov     r9d, eax; char *
0x18007296e  mov     edx, 128h; void *
0x180072973  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180072978  jmp     loc_180072D99
0x18007297d  lea     r8, [rbp+4Fh+Table]
0x180072981  mov     [rbp+4Fh+Table], r13
0x180072985  mov     rdx, rsi
0x180072988  call    ?CreateFileOffsetToFooterMap@AppxEncryptedBundleReader@Consumption@Packaging@Appx@@IEAAJPEAVEncryptedAppxFootersReader@34@PEAPEAV?$GenericMap@PEA_KPEAVEncryptedAppxFooter@Packaging@Appx@@@Common@@@Z; Appx::Packaging::Consumption::AppxEncryptedBundleReader::CreateFileOffsetToFooterMap(Appx::Packaging::EncryptedAppxFootersReader *,Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *> * *)
0x18007298d  mov     rdi, [rbp+4Fh+Table]
0x180072991  mov     ebx, eax
0x180072993  test    eax, eax
0x180072995  jns     short loc_1800729A4
0x180072997  mov     r9d, eax
0x18007299a  mov     edx, 12Ch
0x18007299f  jmp     loc_180072A25
0x1800729a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800729ab  mov     ecx, 78h ; 'x'; unsigned __int64
0x1800729b0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800729b5  test    rax, rax
0x1800729b8  jz      short loc_1800729C7
0x1800729ba  xor     r8d, r8d
0x1800729bd  mov     rcx, rax
0x1800729c0  call    ??0?$GenericMap@PEBGPEAUIAppxFile@@@Common@@QEAA@P6A?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@ZP6AXPEBG@ZP6AXPEAUIAppxFile@@@Z@Z; Common::GenericMap<ushort const *,IAppxFile *>::GenericMap<ushort const *,IAppxFile *>(_RTL_GENERIC_COMPARE_RESULTS (*)(_RTL_AVL_TABLE *,void *,void *),void (*)(ushort const *),void (*)(IAppxFile *))
0x1800729c5  jmp     short loc_1800729CA
0x1800729c7  mov     rax, r13
0x1800729ca  lea     rbx, [r14+0F8h]
0x1800729d1  mov     rdx, rax
0x1800729d4  mov     rcx, rbx
0x1800729d7  call    ??4?$AutoPtr@V?$GenericMap@PEBGPEAUIAppxFile@@@Common@@$1??$AutoPtrDeallocate@V?$GenericMap@PEBGPEAUIAppxFile@@@Common@@@2@YAXPEAV12@@Z@Common@@QEAAPEAV?$GenericMap@PEBGPEAUIAppxFile@@@1@PEAV21@@Z; Common::AutoPtr<Common::GenericMap<ushort const *,IAppxFile *>,&Common::AutoPtrDeallocate<Common::GenericMap<ushort const *,IAppxFile *>>(Common::GenericMap<ushort const *,IAppxFile *> *)>::operator=(Common::GenericMap<ushort const *,IAppxFile *> *)
0x1800729dc  cmp     [rbx], r13
0x1800729df  jnz     short loc_180072A03
0x1800729e1  mov     ebx, 8007000Eh
0x1800729e6  mov     edx, 133h; void *
0x1800729eb  mov     rcx, [rbp+57h]; this
0x1800729ef  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x1800729f6  mov     r9d, ebx; char *
0x1800729f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800729fe  jmp     loc_180072D91
0x180072a03  mov     rsi, [r12+10h]
0x180072a08  mov     r15, [r12+8]
0x180072a0d  mov     rax, rsi
0x180072a10  not     rax
0x180072a13  cmp     r15, rax
0x180072a16  jbe     short loc_180072A3A
0x180072a18  mov     edx, 137h; void *
0x180072a1d  mov     ebx, 80070216h
0x180072a22  mov     r9d, ebx; char *
0x180072a25  mov     rcx, [rbp+57h]; this
0x180072a29  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180072a30  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180072a35  jmp     loc_180072D91
0x180072a3a  mov     r12, [r12+20h]
0x180072a3f  mov     [rbp+4Fh+Table], r12
0x180072a43  test    r12, r12
0x180072a46  jnz     short loc_180072A71
0x180072a48  mov     rcx, [r14+0F0h]; this
0x180072a4f  test    rcx, rcx
0x180072a52  jz      short loc_180072A71
0x180072a54  lea     rdx, [rbp+4Fh+Table]; struct IStream *
0x180072a58  call    ?GetStreamSize@Packaging@Appx@@YAJPEAUIStream@@PEA_K@Z; Appx::Packaging::GetStreamSize(IStream *,unsigned __int64 *)
0x180072a5d  mov     ebx, eax
0x180072a5f  test    eax, eax
0x180072a61  jns     short loc_180072A6D
0x180072a63  mov     r9d, eax
0x180072a66  mov     edx, 13Bh
0x180072a6b  jmp     short loc_180072A25
0x180072a6d  mov     r12, [rbp+4Fh+Table]
0x180072a71  mov     rcx, [rbp+4Fh+var_60]
0x180072a75  lea     rdx, [rbp+4Fh+arg_0]
0x180072a79  mov     [rbp+4Fh+arg_0], r13d
0x180072a7d  mov     rax, [rcx]
0x180072a80  mov     rax, [rax+20h]
0x180072a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072a89  mov     ebx, eax
0x180072a8b  test    eax, eax
0x180072a8d  jns     short loc_180072A99
0x180072a8f  mov     r9d, eax
0x180072a92  mov     edx, 140h
0x180072a97  jmp     short loc_180072A25
0x180072a99  add     r15, rsi
0x180072a9c  xor     esi, esi
0x180072a9e  cmp     [rbp+4Fh+arg_0], 1
0x180072aa2  jnz     loc_180072E50
0x180072aa8  mov     [rbp+4Fh+var_80], rsi
0x180072aac  lea     rcx, [rbp+4Fh+var_80]
0x180072ab0  mov     rsi, [rbp+4Fh+var_60]
0x180072ab4  mov     rax, [rsi]
0x180072ab7  mov     rbx, [rax+18h]
0x180072abb  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072ac0  lea     rdx, [rbp+4Fh+var_80]
0x180072ac4  mov     rcx, rsi
0x180072ac7  mov     rax, rbx
0x180072aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072acf  mov     rcx, [rbp+4Fh+var_80]
0x180072ad3  lea     rdx, [rbp+4Fh+pv]
0x180072ad7  xor     esi, esi
0x180072ad9  mov     [rbp+4Fh+pv], rsi
0x180072add  mov     rax, [rcx]
0x180072ae0  mov     rax, [rax+28h]
0x180072ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ae9  mov     ebx, eax
0x180072aeb  test    eax, eax
0x180072aed  js      loc_180072E1A
0x180072af3  mov     rcx, [rbp+4Fh+var_80]
0x180072af7  lea     rdx, [rbp+4Fh+Table]
0x180072afb  mov     [rbp+4Fh+Table], rsi
0x180072aff  mov     rax, [rcx]
0x180072b02  mov     rax, [rax+30h]
0x180072b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b0b  mov     ebx, eax
0x180072b0d  test    eax, eax
0x180072b0f  js      loc_180072E13
0x180072b15  mov     rcx, [rbp+4Fh+var_80]
0x180072b19  lea     rdx, [rbp+4Fh+var_48]
0x180072b1d  mov     [rbp+4Fh+var_48], rsi
0x180072b21  mov     rax, [rcx]
0x180072b24  mov     rax, [rax+38h]
0x180072b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b2d  mov     ebx, eax
0x180072b2f  test    eax, eax
0x180072b31  js      loc_180072E0C
0x180072b37  cmp     [rbp+4Fh+Table], rsi
0x180072b3b  jbe     loc_180072C9B
0x180072b41  lea     rdx, [rbp+4Fh+Table]
0x180072b45  mov     rcx, rdi
0x180072b48  call    ?FindElement@?$GenericMap@PEAGPEAUIXMLDOMNode@@@Common@@AEAAPEAV?$GenericMapElement@PEAGPEAUIXMLDOMNode@@@2@PEBG@Z; Common::GenericMap<ushort *,IXMLDOMNode *>::FindElement(ushort const *)
0x180072b4d  test    rax, rax
0x180072b50  jz      loc_180072DE6
0x180072b56  mov     rcx, [rax+8]
0x180072b5a  test    rcx, rcx
0x180072b5d  jz      loc_180072DE6
0x180072b63  cmp     [rcx+4], esi
0x180072b66  jnz     loc_180072DDF
0x180072b6c  mov     rax, [rbp+4Fh+var_48]
0x180072b70  cmp     [rcx+18h], rax
0x180072b74  jnz     loc_180072DD3
0x180072b7a  lea     rcx, [rbp+4Fh+var_70]
0x180072b7e  mov     [rbp+4Fh+var_70], rsi
0x180072b82  cmp     [r14+0F0h], rsi
0x180072b89  jnz     short loc_180072BB1
0x180072b8b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072b90  mov     rdx, [rbp+4Fh+arg_20]; struct Appx::Packaging::AppxEncryptionSettings *
0x180072b94  lea     r8, [rbp+4Fh+var_70]; struct Appx::Packaging::Consumption::EncryptedBundlePayloadPackage **
0x180072b98  mov     rcx, [rbp+4Fh+var_80]; struct IAppxBundleManifestPackageInfo *
0x180072b9c  call    ?CreateStreaming@EncryptedBundlePayloadPackage@Consumption@Packaging@Appx@@SAJPEAUIAppxBundleManifestPackageInfo@@PEAVAppxEncryptionSettings@34@PEAPEAV1234@@Z; Appx::Packaging::Consumption::EncryptedBundlePayloadPackage::CreateStreaming(IAppxBundleManifestPackageInfo *,Appx::Packaging::AppxEncryptionSettings *,Appx::Packaging::Consumption::EncryptedBundlePayloadPackage * *)
0x180072ba1  mov     ebx, eax
0x180072ba3  test    eax, eax
0x180072ba5  js      loc_180072CD7
0x180072bab  mov     rbx, [rbp+4Fh+var_70]
0x180072baf  jmp     short loc_180072C2F
0x180072bb1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072bb6  mov     r8, [rbp+4Fh+var_50]; struct IUri *
0x180072bba  lea     rax, [rbp+4Fh+var_70]
0x180072bbe  mov     rdx, [r14+0F0h]; struct IStream *
0x180072bc5  lea     r9, [r14+40h]; struct Appx::Packaging::ManifestComparisonHelper *
0x180072bc9  mov     rcx, [rbp+4Fh+var_80]; struct IAppxBundleManifestPackageInfo *
0x180072bcd  mov     [rsp+0C0h+var_90], rax; struct Appx::Packaging::Consumption::EncryptedBundlePayloadPackage **
0x180072bd2  mov     rax, [rbp+4Fh+arg_20]
0x180072bd6  mov     [rsp+0C0h+var_98], r15; unsigned __int64
0x180072bdb  mov     [rsp+0C0h+var_A0], rax; int
0x180072be0  call    ?CreateNonstreaming@EncryptedBundlePayloadPackage@Consumption@Packaging@Appx@@SAJPEAUIAppxBundleManifestPackageInfo@@PEAUIStream@@PEAUIUri@@PEAVManifestComparisonHelper@34@PEAVAppxEncryptionSettings@34@_KPEAPEAV1234@@Z; Appx::Packaging::Consumption::EncryptedBundlePayloadPackage::CreateNonstreaming(IAppxBundleManifestPackageInfo *,IStream *,IUri *,Appx::Packaging::ManifestComparisonHelper *,Appx::Packaging::AppxEncryptionSettings *,unsigned __int64,Appx::Packaging::Consumption::EncryptedBundlePayloadPackage * *)
0x180072be5  mov     ebx, eax
0x180072be7  test    eax, eax
0x180072be9  js      loc_180072DC9
0x180072bef  mov     rbx, [rbp+4Fh+var_70]
0x180072bf3  lea     rdx, [rbp+4Fh+var_40]; unsigned __int64 *
0x180072bf7  mov     rcx, rbx; this
0x180072bfa  mov     [rbp+4Fh+var_40], rsi
0x180072bfe  call    ?GetAppendedSize@EncryptedBundlePayloadPackage@Consumption@Packaging@Appx@@QEAAJPEA_K@Z; Appx::Packaging::Consumption::EncryptedBundlePayloadPackage::GetAppendedSize(unsigned __int64 *)
0x180072c03  mov     esi, eax
0x180072c05  test    eax, eax
0x180072c07  js      loc_180072D55
0x180072c0d  mov     rcx, [rbp+4Fh+var_40]
0x180072c11  or      rax, 0FFFFFFFFFFFFFFFFh
0x180072c15  sub     rax, rcx
0x180072c18  cmp     r15, rax
0x180072c1b  ja      loc_180072D46
0x180072c21  add     r15, rcx
0x180072c24  cmp     r15, r12
0x180072c27  ja      loc_180072D27
0x180072c2d  xor     esi, esi
0x180072c2f  mov     [rbp+4Fh+var_58], rsi
0x180072c33  lea     rcx, [rbp+4Fh+var_58]
0x180072c37  mov     rax, [rbx]
0x180072c3a  mov     rsi, [rax]
0x180072c3d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072c42  lea     r8, [rbp+4Fh+var_58]
0x180072c46  mov     rcx, rbx
0x180072c49  lea     rdx, _GUID_91df827b_94fd_468f_827b_57f41b2f6f2e
0x180072c50  mov     rax, rsi
0x180072c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c58  xor     esi, esi
0x180072c5a  mov     ebx, eax
0x180072c5c  test    eax, eax
0x180072c5e  js      loc_180072D04
0x180072c64  mov     r8, [rbp+4Fh+var_58]
0x180072c68  mov     rdx, [rbp+4Fh+pv]
0x180072c6c  mov     rcx, [r14+0F8h]
0x180072c73  call    ?Insert@?$GenericMap@PEAGPEAG@Common@@QEAAJPEAG0@Z; Common::GenericMap<ushort *,ushort *>::Insert(ushort *,ushort *)
0x180072c78  mov     ebx, eax
0x180072c7a  test    eax, eax
0x180072c7c  js      short loc_180072CFD
0x180072c7e  lea     rcx, [rbp+4Fh+var_58]
0x180072c82  mov     [rbp+4Fh+var_58], rsi
0x180072c86  mov     [rbp+4Fh+pv], rsi
0x180072c8a  inc     r13d
0x180072c8d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072c92  lea     rcx, [rbp+4Fh+var_70]
0x180072c96  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072c9b  mov     rcx, [rbp+4Fh+var_60]
0x180072c9f  lea     rdx, [rbp+4Fh+arg_0]
0x180072ca3  mov     rax, [rcx]
0x180072ca6  mov     rax, [rax+28h]
0x180072caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072caf  mov     ebx, eax
0x180072cb1  test    eax, eax
0x180072cb3  js      loc_180072E05
0x180072cb9  mov     rcx, [rbp+4Fh+pv]; pv
0x180072cbd  call    cs:__imp_CoTaskMemFree
0x180072cc4  nop     dword ptr [rax+rax+00h]
0x180072cc9  lea     rcx, [rbp+4Fh+var_80]
0x180072ccd  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072cd2  jmp     loc_180072A9E
0x180072cd7  mov     edx, 165h; void *
0x180072cdc  mov     r9d, eax; char *
0x180072cdf  mov     rcx, [rbp+57h]; this
0x180072ce3  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180072cea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180072cef  lea     rcx, [rbp+4Fh+var_70]
0x180072cf3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072cf8  jmp     loc_180072E32
0x180072cfd  mov     edx, 17Ah
0x180072d02  jmp     short loc_180072D09
0x180072d04  mov     edx, 179h; void *
0x180072d09  mov     rcx, [rbp+57h]; this
0x180072d0d  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180072d14  mov     r9d, eax; char *
0x180072d17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180072d1c  lea     rcx, [rbp+4Fh+var_58]
0x180072d20  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180072d25  jmp     short loc_180072CEF
0x180072d27  mov     rcx, [rbp+57h]; this
0x180072d2b  lea     r8, aOnecorePrintsc_87; "onecore\\printscan\\appxpackaging\\cons"...
0x180072d32  mov     ebx, 8007000Dh
0x180072d37  mov     edx, 175h; void *
0x180072d3c  mov     r9d, ebx; char *
0x180072d3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072d44  jmp     short loc_180072CEF
0x180072d46  mov     ebx, 80070216h
0x180072d4b  mov     edx, 174h
0x180072d50  mov     r9d, ebx
  ... truncated ...
```
