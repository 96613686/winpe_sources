# Appx::Packaging::Consumption::EncryptedPackageReaderHelper::MatchBlockMapDataWithFooterData(Appx::Packaging::EncryptedAppxFootersReader *,Appx::Packaging::BlockMap::AppxBlockMapReader *,Appx::Packaging::AppxEncryptionSettings *,Appx::Packaging::FileNameHelper *,ushort const *,IStream *,Appx::Packaging::Consumption::AppxEncryptedFile * *,Appx::Packaging::Consumption::AppxEncryptedFile * *,Common::GenericMap<ushort const *,IAppxFile *> * *)

- ea: `0x180086460`
- end: `0x1800868e1`
- name: `?MatchBlockMapDataWithFooterData@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@SAJPEAVEncryptedAppxFootersReader@34@PEAVAppxBlockMapReader@BlockMap@34@PEAVAppxEncryptionSettings@34@PEAVFileNameHelper@34@PEBGPEAUIStream@@PEAPEAVAppxEncryptedFile@234@6PEAPEAV?$GenericMap@PEBGPEAUIAppxFile@@@Common@@@Z`
- size: `1153`
- prototype: `__int64 __fastcall(int, int, int, int, LPCWCH lpString1, struct IStream *, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18006d578`
- `0x18006e15c`
- `0x18006f3a8`
- `0x1800844ac`
- `0x18008612c`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180019950`
- `0x180022b50`
- `0x1800455c0`
- `0x18004ccd0`
- `0x18004cf28`
- `0x18004ec7c`
- `0x18005af80`
- `0x18006f358`
- `0x180071f50`
- `0x180072eb8`
- `0x180085958`
- `0x180085a8c`
- `0x180085b10`
- `0x180085c94`
- `0x180086460`
- `0x1800992c4`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180086568`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800865a3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180086568`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800865a3`

## string_xrefs

- `0x18008658e`: `AppxContentGroupMap.xml`
- `0x1800865c5`: `application/vnd.ms-appx.manifest+xml`
- `0x1800865d2`: `application/vnd.ms-appx.streammap+xml`
- `0x1800864c3`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagereaderhelper.cpp`
- `0x180086751`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagereaderhelper.cpp`
- `0x180086787`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagereaderhelper.cpp`
- `0x1800867aa`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagereaderhelper.cpp`
- `0x1800867d7`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagereaderhelper.cpp`
- `0x18008683d`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagereaderhelper.cpp`
- `0x180086892`: `onecore\printscan\appxpackaging\consumption\src\encryptedpackagereaderhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Consumption::EncryptedPackageReaderHelper::MatchBlockMapDataWithFooterData(
        Appx::Packaging::EncryptedAppxFootersReader *a1,
        struct Appx::Packaging::BlockMap::AppxBlockMapReader *a2,
        struct Appx::Packaging::AppxEncryptionSettings *a3,
        void *a4,
        LPCWCH lpString1,
        struct IStream *a6,
        _QWORD *a7,
        _QWORD *a8,
        _QWORD *a9)
{
  _QWORD *v9; // r12
  int v11; // eax
  unsigned int v12; // ebx
  void *v14; // rbx
  __int64 v15; // r13
  __int64 v16; // r14
  int FilesInternal; // eax
  _QWORD *v18; // rsi
  unsigned int v19; // edi
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  Appx::Packaging::BlockMap::AppxBlockMapFile *v22; // r15
  const WCHAR *v23; // rax
  bool v24; // di
  bool v25; // al
  unsigned __int16 *v26; // r15
  int v27; // eax
  int v28; // eax
  struct Appx::Packaging::EncryptedAppxFooter *v29; // rdi
  int v30; // eax
  unsigned int v31; // r15d
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  int v36; // eax
  void *v37; // rax
  int bIgnoreCase; // [rsp+28h] [rbp-61h]
  struct Appx::Packaging::EncryptedAppxFooter *v39; // [rsp+48h] [rbp-41h] BYREF
  __int64 v40; // [rsp+50h] [rbp-39h] BYREF
  __int64 v41; // [rsp+58h] [rbp-31h] BYREF
  __int64 v42; // [rsp+60h] [rbp-29h] BYREF
  unsigned __int16 *v43; // [rsp+68h] [rbp-21h]
  Appx::Packaging::BlockMap::AppxBlockMapFile *v44; // [rsp+70h] [rbp-19h]
  LPCWCH lpString2; // [rsp+78h] [rbp-11h]
  unsigned __int64 v46[9]; // [rsp+80h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+47h]
  void *v51; // [rsp+F0h] [rbp+67h] BYREF

  v51 = a4;
  v9 = a9;
  *a7 = 0;
  if ( v9 )
  {
    *v9 = 0;
    v51 = 0;
    v11 = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreatePayloadFilesMap(a1, a2, &v51);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagereaderhelper.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *>>(0);
      Common::AutoPtrDeallocate<Common::GenericMap<unsigned short const *,IAppxFile *>>(v51);
      return v12;
    }
    v14 = v51;
  }
  else
  {
    v14 = 0;
  }
  v42 = 0;
  v41 = 0;
  v15 = 0;
  v51 = 0;
  v16 = 0;
  FilesInternal = Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal(a2, &v51);
  v18 = v51;
  v19 = FilesInternal;
  if ( FilesInternal < 0 )
  {
    v20 = (unsigned int)FilesInternal;
    v21 = 344;
LABEL_48:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagereaderhelper.cpp",
      (const char *)v20,
      bIgnoreCase);
    goto LABEL_58;
  }
  while ( *((_BYTE *)v18 + 24) )
  {
    v22 = *(Appx::Packaging::BlockMap::AppxBlockMapFile **)(v18[2] + 8LL);
    v44 = v22;
    v23 = (const WCHAR *)*((_QWORD *)v22 + 7);
    lpString2 = v23;
    v24 = !v15 && CompareStringOrdinal(lpString1, -1, v23, -1, 1) == 2;
    LOBYTE(v51) = v24;
    v25 = !v16 && CompareStringOrdinal(L"AppxContentGroupMap.xml", -1, lpString2, -1, 1) == 2;
    LOBYTE(a9) = v25;
    if ( v24 )
    {
      v26 = L"application/vnd.ms-appx.manifest+xml";
LABEL_21:
      v43 = v26;
      v22 = v44;
      goto LABEL_23;
    }
    if ( v25 )
    {
      v26 = L"application/vnd.ms-appx.streammap+xml";
      goto LABEL_21;
    }
    v43 = 0;
    if ( !v9 )
    {
      v19 = -2146958843;
      v35 = 389;
LABEL_57:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v35,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagereaderhelper.cpp",
        (const char *)v19,
        bIgnoreCase);
      goto LABEL_58;
    }
LABEL_23:
    v46[0] = 0;
    v27 = (*(__int64 (__fastcall **)(Appx::Packaging::BlockMap::AppxBlockMapFile *, unsigned __int64 *))(*(_QWORD *)v22 + 72LL))(
            v22,
            v46);
    v19 = v27;
    if ( v27 < 0 )
    {
      v20 = (unsigned int)v27;
      v21 = 394;
      goto LABEL_48;
    }
    v39 = 0;
    v28 = Appx::Packaging::EncryptedAppxFootersReader::DetachFooterByFileId(a1, v46[0], &v39);
    if ( v28 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagereaderhelper.cpp",
        (const char *)(unsigned int)v28,
        bIgnoreCase);
      operator delete(v39, 0x38u);
      v19 = -2147024883;
      goto LABEL_58;
    }
    v29 = v39;
    v30 = Appx::Packaging::BlockMap::AppxBlockMapFile::MergeEncryptedFileData(v22, v39);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagereaderhelper.cpp",
        (const char *)(unsigned int)v30,
        bIgnoreCase);
      goto LABEL_41;
    }
    v39 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
    v32 = Appx::Packaging::Consumption::AppxEncryptedFile::Create(v29, a3, a2, v44, lpString2, v43, a6, &v39);
    v31 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x19B,
        (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagereaderhelper.cpp",
        (const char *)(unsigned int)v32,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
LABEL_41:
      operator delete(v29, 0x38u);
      v19 = v31;
      goto LABEL_58;
    }
    if ( (_BYTE)v51 )
    {
      Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(&v42, &v39);
      v15 = v42;
    }
    else if ( (_BYTE)a9 )
    {
      Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(&v41, &v39);
      v16 = v41;
    }
    else if ( v14 )
    {
      v40 = 0;
      v33 = Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(&v39, &v40);
      v19 = v33;
      if ( v33 < 0 )
      {
        v34 = 427;
        goto LABEL_38;
      }
      v33 = Common::GenericMap<unsigned short *,unsigned short *>::Insert(v14, lpString2, v40);
      v19 = v33;
      if ( v33 < 0 )
      {
        v34 = 428;
LABEL_38:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\printscan\\appxpackaging\\consumption\\src\\encryptedpackagereaderhelper.cpp",
          (const char *)(unsigned int)v33,
          bIgnoreCase);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
        operator delete(0, 0x38u);
        goto LABEL_58;
      }
      v40 = 0;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v40);
    }
    Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::MoveNext(v18);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v39);
    operator delete(0, 0x38u);
  }
  if ( !v15 )
  {
    v19 = -2146958845;
    v35 = 436;
    goto LABEL_57;
  }
  v36 = Appx::Packaging::Consumption::EncryptedPackageReaderHelper::VerifyBlockMapIgnoredFiles(a1, a2);
  v19 = v36;
  if ( v36 < 0 )
  {
    v20 = (unsigned int)v36;
    v21 = 439;
    goto LABEL_48;
  }
  if ( v9 )
  {
    v37 = v14;
    v14 = 0;
    *v9 = v37;
  }
  v42 = 0;
  *a7 = v15;
  if ( a8 )
  {
    if ( v16 )
      v41 = 0;
    else
      v16 = 0;
    *a8 = v16;
  }
LABEL_58:
  Common::AutoPtrDeallocate<Appx::Packaging::GenericMapEnumerator<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>(v18);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
  Common::AutoPtrDeallocate<Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *>>(0);
  Common::AutoPtrDeallocate<Common::GenericMap<unsigned short const *,IAppxFile *>>(v14);
  return v19;
}

```

## disassembly

```asm
0x180086460  mov     rax, rsp
0x180086463  mov     [rax+20h], r9
0x180086467  mov     [rax+18h], r8
0x18008646b  mov     [rax+10h], rdx
0x18008646f  mov     [rax+8], rcx
0x180086473  push    rbp
0x180086474  push    rbx
0x180086475  push    rsi
0x180086476  push    rdi
0x180086477  push    r12
0x180086479  push    r13
0x18008647b  push    r14
0x18008647d  push    r15
0x18008647f  lea     rbp, [rax-47h]
0x180086483  sub     rsp, 88h
0x18008648a  mov     r12, [rbp+3Fh+arg_40]
0x180086491  xor     edi, edi
0x180086493  mov     rax, rcx
0x180086496  mov     rcx, [rbp+3Fh+arg_30]
0x18008649a  mov     r15, rdx
0x18008649d  mov     [rcx], rdi
0x1800864a0  test    r12, r12
0x1800864a3  jz      short loc_1800864F4
0x1800864a5  lea     r8, [rbp+3Fh+arg_18]
0x1800864a9  mov     [r12], rdi
0x1800864ad  mov     rcx, rax
0x1800864b0  mov     [rbp+3Fh+arg_18], rdi
0x1800864b4  call    ?CreatePayloadFilesMap@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@CAJPEAVEncryptedAppxFootersReader@34@PEAVAppxBlockMapReader@BlockMap@34@PEAPEAV?$GenericMap@PEBGPEAUIAppxFile@@@Common@@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::CreatePayloadFilesMap(Appx::Packaging::EncryptedAppxFootersReader *,Appx::Packaging::BlockMap::AppxBlockMapReader *,Common::GenericMap<ushort const *,IAppxFile *> * *)
0x1800864b9  mov     ebx, eax
0x1800864bb  test    eax, eax
0x1800864bd  jns     short loc_1800864EE
0x1800864bf  mov     rcx, [rbp+47h]; this
0x1800864c3  lea     r8, aOnecorePrintsc_67; "onecore\\printscan\\appxpackaging\\cons"...
0x1800864ca  mov     r9d, eax; char *
0x1800864cd  mov     edx, 152h; void *
0x1800864d2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800864d7  xor     ecx, ecx; void *
0x1800864d9  call    ??$AutoPtrDeallocate@V?$GenericMap@PEA_KPEAVEncryptedAppxFooter@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEA_KPEAVEncryptedAppxFooter@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *>>(Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *> *)
0x1800864de  mov     rcx, [rbp+3Fh+arg_18]; void *
0x1800864e2  call    ??$AutoPtrDeallocate@V?$GenericMap@PEBGPEAUIAppxFile@@@Common@@@Common@@YAXPEAV?$GenericMap@PEBGPEAUIAppxFile@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort const *,IAppxFile *>>(Common::GenericMap<ushort const *,IAppxFile *> *)
0x1800864e7  mov     eax, ebx
0x1800864e9  jmp     loc_1800868CC
0x1800864ee  mov     rbx, [rbp+3Fh+arg_18]
0x1800864f2  jmp     short loc_1800864F7
0x1800864f4  mov     rbx, rdi
0x1800864f7  lea     rdx, [rbp+3Fh+arg_18]
0x1800864fb  mov     [rbp+3Fh+var_68], rdi
0x1800864ff  mov     rcx, r15
0x180086502  mov     [rbp+3Fh+var_70], rdi
0x180086506  mov     r13, rdi
0x180086509  mov     [rbp+3Fh+arg_18], rdi
0x18008650d  mov     r14, rdi
0x180086510  call    ?GetFilesInternal@AppxBlockMapReader@BlockMap@Packaging@Appx@@QEAAJPEAPEAV?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@34@@Z; Appx::Packaging::BlockMap::AppxBlockMapReader::GetFilesInternal(Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *> * *)
0x180086515  mov     rsi, [rbp+3Fh+arg_18]
0x180086519  xor     r15d, r15d
0x18008651c  mov     edi, eax
0x18008651e  test    eax, eax
0x180086520  jns     short loc_18008652F
0x180086522  mov     r9d, eax
0x180086525  mov     edx, 158h
0x18008652a  jmp     loc_180086839
0x18008652f  cmp     [rsi+18h], r15b
0x180086533  jz      loc_180086819
0x180086539  mov     rax, [rsi+10h]
0x18008653d  mov     r15, [rax+8]
0x180086541  mov     [rbp+3Fh+var_58], r15
0x180086545  mov     rax, [r15+38h]
0x180086549  mov     [rbp+3Fh+lpString2], rax
0x18008654d  test    r13, r13
0x180086550  jnz     short loc_18008657E
0x180086552  mov     rcx, [rbp+3Fh+lpString1]; lpString1
0x180086556  or      r9d, 0FFFFFFFFh; cchCount2
0x18008655a  or      edx, r9d; cchCount1
0x18008655d  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x180086565  mov     r8, rax; lpString2
0x180086568  call    cs:__imp_CompareStringOrdinal
0x18008656f  nop     dword ptr [rax+rax+00h]
0x180086574  cmp     eax, 2
0x180086577  jnz     short loc_18008657E
0x180086579  mov     dil, 1
0x18008657c  jmp     short loc_180086581
0x18008657e  xor     dil, dil
0x180086581  mov     byte ptr [rbp+3Fh+arg_18], dil
0x180086585  test    r14, r14
0x180086588  jnz     short loc_1800865B8
0x18008658a  mov     r8, [rbp+3Fh+lpString2]; lpString2
0x18008658e  lea     rcx, ?FileName@ContentGroupMap@Packaging@Appx@@3QBGB; "AppxContentGroupMap.xml"
0x180086595  or      edx, 0FFFFFFFFh; cchCount1
0x180086598  mov     [rsp+0C0h+bIgnoreCase], 1; bIgnoreCase
0x1800865a0  mov     r9d, edx; cchCount2
0x1800865a3  call    cs:__imp_CompareStringOrdinal
0x1800865aa  nop     dword ptr [rax+rax+00h]
0x1800865af  cmp     eax, 2
0x1800865b2  jnz     short loc_1800865B8
0x1800865b4  mov     al, 1
0x1800865b6  jmp     short loc_1800865BA
0x1800865b8  xor     al, al
0x1800865ba  mov     byte ptr [rbp+3Fh+arg_40], al
0x1800865c0  test    dil, dil
0x1800865c3  jz      short loc_1800865CE
0x1800865c5  lea     r15, ?ContentType@Manifest@Packaging@Appx@@3QBGB; "application/vnd.ms-appx.manifest+xml"
0x1800865cc  jmp     short loc_1800865D9
0x1800865ce  test    al, al
0x1800865d0  jz      short loc_1800865E3
0x1800865d2  lea     r15, ?ContentType@ContentGroupMap@Packaging@Appx@@3QBGB; "application/vnd.ms-appx.streammap+xml"
0x1800865d9  mov     [rbp+3Fh+var_60], r15
0x1800865dd  mov     r15, [rbp+3Fh+var_58]
0x1800865e1  jmp     short loc_1800865F4
0x1800865e3  mov     [rbp+3Fh+var_60], 0
0x1800865eb  test    r12, r12
0x1800865ee  jz      loc_18008680D
0x1800865f4  mov     [rbp+3Fh+var_48], 0
0x1800865fc  lea     rdx, [rbp+3Fh+var_48]
0x180086600  mov     rax, [r15]
0x180086603  mov     rcx, r15
0x180086606  mov     rax, [rax+48h]
0x18008660a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008660f  mov     edi, eax
0x180086611  test    eax, eax
0x180086613  js      loc_180086803
0x180086619  mov     rdx, [rbp+3Fh+var_48]; unsigned __int64
0x18008661d  lea     r8, [rbp+3Fh+var_80]; struct Appx::Packaging::EncryptedAppxFooter **
0x180086621  mov     rcx, [rbp+3Fh+arg_0]; this
0x180086625  mov     [rbp+3Fh+var_80], 0
0x18008662d  call    ?DetachFooterByFileId@EncryptedAppxFootersReader@Packaging@Appx@@QEAAJ_KPEAPEAVEncryptedAppxFooter@23@@Z; Appx::Packaging::EncryptedAppxFootersReader::DetachFooterByFileId(unsigned __int64,Appx::Packaging::EncryptedAppxFooter * *)
0x180086632  test    eax, eax
0x180086634  js      loc_1800867D3
0x18008663a  mov     rdi, [rbp+3Fh+var_80]
0x18008663e  mov     rcx, r15; this
0x180086641  mov     rdx, rdi; struct Appx::Packaging::EncryptedAppxFooter *
0x180086644  call    ?MergeEncryptedFileData@AppxBlockMapFile@BlockMap@Packaging@Appx@@QEAAJPEBVEncryptedAppxFooter@34@@Z; Appx::Packaging::BlockMap::AppxBlockMapFile::MergeEncryptedFileData(Appx::Packaging::EncryptedAppxFooter const *)
0x180086649  mov     r15d, eax
0x18008664c  test    eax, eax
0x18008664e  js      loc_1800867A6
0x180086654  lea     rcx, [rbp+3Fh+var_80]
0x180086658  mov     [rbp+3Fh+var_80], 0
0x180086660  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180086665  mov     r9, [rbp+3Fh+var_58]; struct Appx::Packaging::BlockMap::AppxBlockMapFile *
0x180086669  lea     rax, [rbp+3Fh+var_80]
0x18008666d  mov     r8, [rbp+3Fh+arg_8]; struct Appx::Packaging::BlockMap::AppxBlockMapReader *
0x180086671  mov     rcx, rdi; struct Appx::Packaging::EncryptedAppxFooter *
0x180086674  mov     rdx, [rbp+3Fh+arg_10]; struct Appx::Packaging::AppxEncryptionSettings *
0x180086678  mov     [rsp+38h], rax; struct Appx::Packaging::Consumption::AppxEncryptedFile **
0x18008667d  mov     rax, [rbp+3Fh+arg_28]
0x180086681  mov     [rsp+0C0h+var_90], rax; struct IStream *
0x180086686  mov     rax, [rbp+3Fh+var_60]
0x18008668a  mov     [rsp+0C0h+var_98], rax; unsigned __int16 *
0x18008668f  mov     rax, [rbp+3Fh+lpString2]
0x180086693  mov     qword ptr [rsp+0C0h+bIgnoreCase], rax; int
0x180086698  call    ?Create@AppxEncryptedFile@Consumption@Packaging@Appx@@SAJPEAVEncryptedAppxFooter@34@PEAVAppxEncryptionSettings@34@PEAVAppxBlockMapReader@BlockMap@34@PEAVAppxBlockMapFile@834@PEBG4PEAUIStream@@PEAPEAV1234@@Z; Appx::Packaging::Consumption::AppxEncryptedFile::Create(Appx::Packaging::EncryptedAppxFooter *,Appx::Packaging::AppxEncryptionSettings *,Appx::Packaging::BlockMap::AppxBlockMapReader *,Appx::Packaging::BlockMap::AppxBlockMapFile *,ushort const *,ushort const *,IStream *,Appx::Packaging::Consumption::AppxEncryptedFile * *)
0x18008669d  mov     r15d, eax
0x1800866a0  test    eax, eax
0x1800866a2  js      loc_180086783
0x1800866a8  xor     r15d, r15d
0x1800866ab  cmp     byte ptr [rbp+3Fh+arg_18], r15b
0x1800866af  jz      short loc_1800866C4
0x1800866b1  lea     rdx, [rbp+3Fh+var_80]
0x1800866b5  lea     rcx, [rbp+3Fh+var_68]
0x1800866b9  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x1800866be  mov     r13, [rbp+3Fh+var_68]
0x1800866c2  jmp     short loc_18008671F
0x1800866c4  cmp     byte ptr [rbp+3Fh+arg_40], r15b
0x1800866cb  jz      short loc_1800866E0
0x1800866cd  lea     rdx, [rbp+3Fh+var_80]
0x1800866d1  lea     rcx, [rbp+3Fh+var_70]
0x1800866d5  call    ??4?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::operator=(Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile> const &)
0x1800866da  mov     r14, [rbp+3Fh+var_70]
0x1800866de  jmp     short loc_18008671F
0x1800866e0  test    rbx, rbx
0x1800866e3  jz      short loc_18008671F
0x1800866e5  lea     rdx, [rbp+3Fh+var_78]
0x1800866e9  mov     [rbp+3Fh+var_78], r15
0x1800866ed  lea     rcx, [rbp+3Fh+var_80]
0x1800866f1  call    ??$As@UIAppxFile@@@?$ComPtr@VAppxEncryptedFile@Consumption@Packaging@Appx@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppxFile@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Appx::Packaging::Consumption::AppxEncryptedFile>::As<IAppxFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppxFile>>)
0x1800866f6  mov     edi, eax
0x1800866f8  test    eax, eax
0x1800866fa  js      short loc_180086748
0x1800866fc  mov     r8, [rbp+3Fh+var_78]
0x180086700  mov     rcx, rbx
0x180086703  mov     rdx, [rbp+3Fh+lpString2]
0x180086707  call    ?Insert@?$GenericMap@PEAGPEAG@Common@@QEAAJPEAG0@Z; Common::GenericMap<ushort *,ushort *>::Insert(ushort *,ushort *)
0x18008670c  mov     edi, eax
0x18008670e  test    eax, eax
0x180086710  js      short loc_180086741
0x180086712  lea     rcx, [rbp+3Fh+var_78]
0x180086716  mov     [rbp+3Fh+var_78], r15
0x18008671a  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18008671f  mov     rcx, rsi
0x180086722  call    ?MoveNext@?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@QEAA_NXZ; Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>::MoveNext(void)
0x180086727  lea     rcx, [rbp+3Fh+var_80]
0x18008672b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180086730  mov     edx, 38h ; '8'; unsigned __int64
0x180086735  xor     ecx, ecx; void *
0x180086737  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008673c  jmp     loc_18008652F
0x180086741  mov     edx, 1ACh
0x180086746  jmp     short loc_18008674D
0x180086748  mov     edx, 1ABh; void *
0x18008674d  mov     rcx, [rbp+47h]; this
0x180086751  lea     r8, aOnecorePrintsc_67; "onecore\\printscan\\appxpackaging\\cons"...
0x180086758  mov     r9d, eax; char *
0x18008675b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086760  lea     rcx, [rbp+3Fh+var_78]
0x180086764  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180086769  lea     rcx, [rbp+3Fh+var_80]
0x18008676d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180086772  mov     edx, 38h ; '8'; unsigned __int64
0x180086777  xor     ecx, ecx; void *
0x180086779  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008677e  jmp     loc_1800868A1
0x180086783  mov     rcx, [rbp+47h]; this
0x180086787  lea     r8, aOnecorePrintsc_67; "onecore\\printscan\\appxpackaging\\cons"...
0x18008678e  mov     r9d, r15d; char *
0x180086791  mov     edx, 19Bh; void *
0x180086796  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008679b  lea     rcx, [rbp+3Fh+var_80]
0x18008679f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800867a4  jmp     short loc_1800867BE
0x1800867a6  mov     rcx, [rbp+47h]; this
0x1800867aa  lea     r8, aOnecorePrintsc_67; "onecore\\printscan\\appxpackaging\\cons"...
0x1800867b1  mov     r9d, r15d; char *
0x1800867b4  mov     edx, 18Fh; void *
0x1800867b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800867be  mov     edx, 38h ; '8'; unsigned __int64
0x1800867c3  mov     rcx, rdi; void *
0x1800867c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800867cb  mov     edi, r15d
0x1800867ce  jmp     loc_1800868A1
0x1800867d3  mov     rcx, [rbp+47h]; this
0x1800867d7  lea     r8, aOnecorePrintsc_67; "onecore\\printscan\\appxpackaging\\cons"...
0x1800867de  mov     r9d, eax; char *
0x1800867e1  mov     edx, 18Ch; void *
0x1800867e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800867eb  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800867ef  mov     edx, 38h ; '8'; unsigned __int64
0x1800867f4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800867f9  mov     edi, 8007000Dh
0x1800867fe  jmp     loc_1800868A1
0x180086803  mov     r9d, eax
0x180086806  mov     edx, 18Ah
0x18008680b  jmp     short loc_180086839
0x18008680d  mov     edi, 80080205h
0x180086812  mov     edx, 185h
0x180086817  jmp     short loc_18008688E
0x180086819  test    r13, r13
0x18008681c  jz      short loc_180086884
0x18008681e  mov     rdx, [rbp+3Fh+arg_8]; struct Appx::Packaging::BlockMap::AppxBlockMapReader *
0x180086822  mov     rcx, [rbp+3Fh+arg_0]; this
0x180086826  call    ?VerifyBlockMapIgnoredFiles@EncryptedPackageReaderHelper@Consumption@Packaging@Appx@@CAJPEAVEncryptedAppxFootersReader@34@PEAVAppxBlockMapReader@BlockMap@34@@Z; Appx::Packaging::Consumption::EncryptedPackageReaderHelper::VerifyBlockMapIgnoredFiles(Appx::Packaging::EncryptedAppxFootersReader *,Appx::Packaging::BlockMap::AppxBlockMapReader *)
0x18008682b  mov     edi, eax
0x18008682d  test    eax, eax
0x18008682f  jns     short loc_18008684B
0x180086831  mov     r9d, eax; char *
0x180086834  mov     edx, 1B7h; void *
0x180086839  mov     rcx, [rbp+47h]; this
0x18008683d  lea     r8, aOnecorePrintsc_67; "onecore\\printscan\\appxpackaging\\cons"...
0x180086844  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180086849  jmp     short loc_1800868A1
0x18008684b  test    r12, r12
0x18008684e  jz      short loc_18008685A
0x180086850  mov     rax, rbx
0x180086853  mov     rbx, r15
0x180086856  mov     [r12], rax
0x18008685a  mov     rax, [rbp+3Fh+arg_30]
0x18008685e  mov     [rbp+3Fh+var_68], r15
0x180086862  mov     [rax], r13
0x180086865  mov     rax, [rbp+3Fh+arg_38]
0x18008686c  test    rax, rax
0x18008686f  jz      short loc_1800868A1
0x180086871  test    r14, r14
0x180086874  jz      short loc_18008687C
0x180086876  mov     [rbp+3Fh+var_70], r15
0x18008687a  jmp     short loc_18008687F
0x18008687c  mov     r14, r15
0x18008687f  mov     [rax], r14
0x180086882  jmp     short loc_1800868A1
0x180086884  mov     edi, 80080203h
0x180086889  mov     edx, 1B4h; void *
0x18008688e  mov     rcx, [rbp+47h]; this
0x180086892  lea     r8, aOnecorePrintsc_67; "onecore\\printscan\\appxpackaging\\cons"...
0x180086899  mov     r9d, edi; char *
0x18008689c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800868a1  mov     rcx, rsi
0x1800868a4  call    ??$AutoPtrDeallocate@V?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@@Common@@YAXPEAV?$GenericMapEnumerator@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Packaging@Appx@@@Z; Common::AutoPtrDeallocate<Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>(Appx::Packaging::GenericMapEnumerator<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *> *)
0x1800868a9  lea     rcx, [rbp+3Fh+var_70]
0x1800868ad  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800868b2  lea     rcx, [rbp+3Fh+var_68]
0x1800868b6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800868bb  xor     ecx, ecx; void *
0x1800868bd  call    ??$AutoPtrDeallocate@V?$GenericMap@PEA_KPEAVEncryptedAppxFooter@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEA_KPEAVEncryptedAppxFooter@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *>>(Common::GenericMap<unsigned __int64 *,Appx::Packaging::EncryptedAppxFooter *> *)
0x1800868c2  mov     rcx, rbx; void *
0x1800868c5  call    ??$AutoPtrDeallocate@V?$GenericMap@PEBGPEAUIAppxFile@@@Common@@@Common@@YAXPEAV?$GenericMap@PEBGPEAUIAppxFile@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort const *,IAppxFile *>>(Common::GenericMap<ushort const *,IAppxFile *> *)
0x1800868ca  mov     eax, edi
0x1800868cc  add     rsp, 88h
0x1800868d3  pop     r15
0x1800868d5  pop     r14
0x1800868d7  pop     r13
0x1800868d9  pop     r12
0x1800868db  pop     rdi
0x1800868dc  pop     rsi
  ... truncated ...
```
