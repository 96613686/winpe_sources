# Appx::Packaging::CatalogHelper::CachePETempFile(ushort const *,IStream *,bool,ulong,bool,_IMAGE_DATA_DIRECTORY const *)

- ea: `0x1800ff464`
- end: `0x1800ff6ca`
- name: `?CachePETempFile@CatalogHelper@Packaging@Appx@@AEAAJPEBGPEAUIStream@@_NK2PEBU_IMAGE_DATA_DIRECTORY@@@Z`
- size: `614`
- prototype: `int(Appx::Packaging::CatalogHelper *__hidden this, const unsigned __int16 *, struct IStream *, bool, unsigned int, bool, const struct _IMAGE_DATA_DIRECTORY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801006dc`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18001bb60`
- `0x18003d318`
- `0x1800743a8`
- `0x180074678`
- `0x180090f98`
- `0x1800992c4`
- `0x1800fb4b8`
- `0x1800ff464`
- `0x1801000a4`

## import_xrefs

- `OpcServices!__imp_CreateTempFileName` at `0x1800ff4bd`
- `OpcServices!__imp_CreateTempFileName` at `0x1800ff4bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff5fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff60e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff69e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff5fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff60e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff68c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ff69e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ff59a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ff59a`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::CatalogHelper::CachePETempFile(
        struct IOpcFactory **this,
        const unsigned __int16 *a2,
        struct IStream *a3,
        char a4,
        unsigned int a5,
        bool a6,
        const struct _IMAGE_DATA_DIRECTORY *a7)
{
  int StreamOnFile; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  char *v18; // rcx
  _QWORD *v19; // rbx
  int v20; // eax
  int v21; // edi
  int v23; // [rsp+20h] [rbp-38h]
  unsigned __int64 *v24; // [rsp+28h] [rbp-30h]
  LPVOID pv; // [rsp+30h] [rbp-28h] BYREF
  char *v26[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  LPCWSTR lpFileName; // [rsp+90h] [rbp+38h] BYREF

  v26[1] = (char *)-2LL;
  v26[0] = 0;
  a7 = 0;
  pv = 0;
  lpFileName = 0;
  StreamOnFile = CreateTempFileName(*this, L"AXS", L".tmp", &lpFileName);
  v12 = StreamOnFile;
  if ( StreamOnFile < 0 )
  {
    v13 = 436;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
      (const char *)(unsigned int)StreamOnFile,
      v23);
LABEL_23:
    CoTaskMemFree((LPVOID)lpFileName);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a7);
    v18 = 0;
    goto LABEL_24;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a7);
  StreamOnFile = Appx::Packaging::CatalogHelper::CreateStreamOnFile(
                   lpFileName,
                   OPC_STREAM_IO_WRITE,
                   0x80u,
                   this[9],
                   (struct IStream **)&a7);
  v12 = StreamOnFile;
  if ( StreamOnFile < 0 )
  {
    v13 = 442;
    goto LABEL_5;
  }
  StreamOnFile = Appx::Packaging::CopyStream(
                   a3,
                   0,
                   0xFFFFFFFFFFFFFFFFuLL,
                   (unsigned __int64)a7,
                   (struct IStream *)&pv,
                   v24);
  v12 = StreamOnFile;
  if ( StreamOnFile < 0 )
  {
    v13 = 445;
    goto LABEL_5;
  }
  v14 = Appx::Packaging::StringHelper::ConvertToUtf8(lpFileName, v26);
  v12 = v14;
  if ( v14 >= 0 )
  {
    if ( this[6] )
      Appx::Packaging::DeleteFileOnFree::Free((Appx::Packaging::DeleteFileOnFree *)(this + 6));
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a7);
    if ( a4 )
    {
      DeleteFileW(lpFileName);
      v12 = 0;
    }
    else
    {
      pv = 0;
      v15 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
              &pv,
              a2);
      v12 = v15;
      if ( v15 >= 0 )
      {
        v15 = Common::GenericMap<unsigned short const *,unsigned short const *>::Insert(this + 10, lpFileName, pv);
        v12 = v15;
        if ( v15 >= 0 )
        {
          lpFileName = 0;
          v19 = this + 2;
          v20 = Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::EnsureCapacity(
                  this + 2,
                  (char *)&this[4]->lpVtbl + 1);
          v21 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F4,
              (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
              (const char *)(unsigned int)v20,
              v23);
            CoTaskMemFree(0);
            v12 = v21;
          }
          else
          {
            *(char **)(*v19 + 8LL * v19[2]++) = v26[0];
            CoTaskMemFree(0);
            v12 = 0;
          }
          goto LABEL_23;
        }
        v16 = 496;
      }
      else
      {
        v16 = 495;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
        (const char *)(unsigned int)v15,
        v23);
      CoTaskMemFree(pv);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\crypto\\src\\cataloghelper.cpp",
      (const char *)(unsigned int)v14,
      v23);
  }
  CoTaskMemFree((LPVOID)lpFileName);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&a7);
  v18 = v26[0];
LABEL_24:
  operator delete(v18, v17);
  return v12;
}

```

## disassembly

```asm
0x1800ff464  push    rbp
0x1800ff466  push    rbx
0x1800ff467  push    rsi
0x1800ff468  push    rdi
0x1800ff469  push    r14
0x1800ff46b  push    r15
0x1800ff46d  mov     rbp, rsp
0x1800ff470  sub     rsp, 58h
0x1800ff474  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x1800ff47c  mov     sil, r9b
0x1800ff47f  mov     r15, r8
0x1800ff482  mov     r14, rdx
0x1800ff485  mov     rdi, rcx
0x1800ff488  mov     [rbp+var_20], 0
0x1800ff490  mov     [rbp+arg_30], 0
0x1800ff498  mov     [rbp+pv], 0
0x1800ff4a0  mov     [rbp+lpFileName], 0
0x1800ff4a8  lea     r9, [rbp+lpFileName]
0x1800ff4ac  lea     r8, aTmp; ".tmp"
0x1800ff4b3  lea     rdx, ?TempFilePrefix@Signature@Packaging@Appx@@3QBGB; "AXS"
0x1800ff4ba  mov     rcx, [rcx]
0x1800ff4bd  call    cs:__imp_CreateTempFileName
0x1800ff4c4  nop     dword ptr [rax+rax+00h]
0x1800ff4c9  mov     ebx, eax
0x1800ff4cb  test    eax, eax
0x1800ff4cd  jns     short loc_1800FF4D6
0x1800ff4cf  mov     edx, 1B4h
0x1800ff4d4  jmp     short loc_1800FF509
0x1800ff4d6  lea     rcx, [rbp+arg_30]
0x1800ff4da  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ff4df  lea     rax, [rbp+arg_30]
0x1800ff4e3  mov     [rsp+58h+var_38], rax; int
0x1800ff4e8  mov     r9, [rdi+48h]; struct IOpcFactory *
0x1800ff4ec  mov     edx, 2; enum __MIDL___MIDL_itf_msopc_0000_0002_0003
0x1800ff4f1  lea     r8d, [rdx+7Eh]; unsigned int
0x1800ff4f5  mov     rcx, [rbp+lpFileName]; unsigned __int16 *
0x1800ff4f9  call    ?CreateStreamOnFile@CatalogHelper@Packaging@Appx@@CAJPEBGW4__MIDL___MIDL_itf_msopc_0000_0002_0003@@KPEAUIOpcFactory@@PEAPEAUIStream@@@Z; Appx::Packaging::CatalogHelper::CreateStreamOnFile(ushort const *,__MIDL___MIDL_itf_msopc_0000_0002_0003,ulong,IOpcFactory *,IStream * *)
0x1800ff4fe  mov     ebx, eax
0x1800ff500  test    eax, eax
0x1800ff502  jns     short loc_1800FF521
0x1800ff504  mov     edx, 1BAh; void *
0x1800ff509  mov     rcx, [rbp+30h]; this
0x1800ff50d  mov     r9d, eax; char *
0x1800ff510  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ff517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff51c  jmp     loc_1800FF69A
0x1800ff521  lea     rax, [rbp+pv]
0x1800ff525  mov     [rsp+58h+var_38], rax; int
0x1800ff52a  mov     r9, [rbp+arg_30]; unsigned __int64
0x1800ff52e  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1800ff532  xor     edx, edx; struct IStream *
0x1800ff534  mov     rcx, r15; this
0x1800ff537  call    ?CopyStream@Packaging@Appx@@YAJPEAUIStream@@_K10PEA_K@Z; Appx::Packaging::CopyStream(IStream *,unsigned __int64,unsigned __int64,IStream *,unsigned __int64 *)
0x1800ff53c  mov     ebx, eax
0x1800ff53e  test    eax, eax
0x1800ff540  jns     short loc_1800FF549
0x1800ff542  mov     edx, 1BDh
0x1800ff547  jmp     short loc_1800FF509
0x1800ff549  lea     rdx, [rbp+var_20]; char **
0x1800ff54d  mov     rcx, [rbp+lpFileName]; lpWideCharStr
0x1800ff551  call    ?ConvertToUtf8@StringHelper@Packaging@Appx@@SAJPEBGPEAPEAD@Z; Appx::Packaging::StringHelper::ConvertToUtf8(ushort const *,char * *)
0x1800ff556  mov     ebx, eax
0x1800ff558  test    eax, eax
0x1800ff55a  jns     short loc_1800FF579
0x1800ff55c  mov     rcx, [rbp+30h]; this
0x1800ff560  mov     r9d, eax; char *
0x1800ff563  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ff56a  mov     edx, 1C2h; void *
0x1800ff56f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff574  jmp     loc_1800FF60A
0x1800ff579  lea     rcx, [rdi+30h]; this
0x1800ff57d  cmp     qword ptr [rcx], 0
0x1800ff581  jz      short loc_1800FF588
0x1800ff583  call    ?Free@DeleteFileOnFree@Packaging@Appx@@QEAAXXZ; Appx::Packaging::DeleteFileOnFree::Free(void)
0x1800ff588  lea     rcx, [rbp+arg_30]
0x1800ff58c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ff591  test    sil, sil
0x1800ff594  jz      short loc_1800FF5AA
0x1800ff596  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800ff59a  call    cs:__imp_DeleteFileW
0x1800ff5a1  nop     dword ptr [rax+rax+00h]
0x1800ff5a6  xor     ebx, ebx
0x1800ff5a8  jmp     short loc_1800FF60A
0x1800ff5aa  mov     [rbp+pv], 0
0x1800ff5b2  mov     rdx, r14
0x1800ff5b5  lea     rcx, [rbp+pv]
0x1800ff5b9  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x1800ff5be  mov     ebx, eax
0x1800ff5c0  test    eax, eax
0x1800ff5c2  jns     short loc_1800FF5CB
0x1800ff5c4  mov     edx, 1EFh
0x1800ff5c9  jmp     short loc_1800FF5E7
0x1800ff5cb  lea     rcx, [rdi+50h]
0x1800ff5cf  mov     r8, [rbp+pv]
0x1800ff5d3  mov     rdx, [rbp+lpFileName]
0x1800ff5d7  call    ?Insert@?$GenericMap@PEBGPEBG@Common@@QEAAJPEBG0@Z; Common::GenericMap<ushort const *,ushort const *>::Insert(ushort const *,ushort const *)
0x1800ff5dc  mov     ebx, eax
0x1800ff5de  test    eax, eax
0x1800ff5e0  jns     short loc_1800FF62C
0x1800ff5e2  mov     edx, 1F0h; void *
0x1800ff5e7  mov     r9d, eax; char *
0x1800ff5ea  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ff5f1  mov     rcx, [rbp+30h]; this
0x1800ff5f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff5fa  mov     rcx, [rbp+pv]; pv
0x1800ff5fe  call    cs:__imp_CoTaskMemFree
0x1800ff605  nop     dword ptr [rax+rax+00h]
0x1800ff60a  mov     rcx, [rbp+lpFileName]; pv
0x1800ff60e  call    cs:__imp_CoTaskMemFree
0x1800ff615  nop     dword ptr [rax+rax+00h]
0x1800ff61a  lea     rcx, [rbp+arg_30]
0x1800ff61e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ff623  mov     rcx, [rbp+var_20]
0x1800ff627  jmp     loc_1800FF6B5
0x1800ff62c  mov     [rbp+lpFileName], 0
0x1800ff634  lea     rbx, [rdi+10h]
0x1800ff638  mov     rdx, [rbx+10h]
0x1800ff63c  inc     rdx
0x1800ff63f  mov     rcx, rbx
0x1800ff642  call    ?EnsureCapacity@?$Array@UManifestQualifiedResourceFields@Packaging@Appx@@V?$ContainerOperations@UManifestQualifiedResourceFields@Packaging@Appx@@U123@@Common@@VNoKey@5@V?$ContainerOperations@VNoKey@Common@@UManifestQualifiedResourceFields@Packaging@Appx@@@5@V?$ArrayOperations@UManifestQualifiedResourceFields@Packaging@Appx@@VNoKey@Common@@@5@@Common@@QEAAJ_K@Z; Common::Array<Appx::Packaging::ManifestQualifiedResourceFields,Common::ContainerOperations<Appx::Packaging::ManifestQualifiedResourceFields,Appx::Packaging::ManifestQualifiedResourceFields>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Appx::Packaging::ManifestQualifiedResourceFields>,Common::ArrayOperations<Appx::Packaging::ManifestQualifiedResourceFields,Common::NoKey>>::EnsureCapacity(unsigned __int64)
0x1800ff647  mov     edi, eax
0x1800ff649  test    eax, eax
0x1800ff64b  js      short loc_1800FF672
0x1800ff64d  mov     rdx, [rbp+var_20]
0x1800ff651  mov     rcx, [rbx+10h]
0x1800ff655  mov     rax, [rbx]
0x1800ff658  mov     [rax+rcx*8], rdx
0x1800ff65c  inc     qword ptr [rbx+10h]
0x1800ff660  xor     ecx, ecx; pv
0x1800ff662  call    cs:__imp_CoTaskMemFree
0x1800ff669  nop     dword ptr [rax+rax+00h]
0x1800ff66e  xor     ebx, ebx
0x1800ff670  jmp     short loc_1800FF69A
0x1800ff672  mov     rcx, [rbp+30h]; this
0x1800ff676  mov     r9d, edi; char *
0x1800ff679  lea     r8, aOnecorePrintsc_171; "onecore\\printscan\\appxpackaging\\lib"...
0x1800ff680  mov     edx, 1F4h; void *
0x1800ff685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff68a  xor     ecx, ecx; pv
0x1800ff68c  call    cs:__imp_CoTaskMemFree
0x1800ff693  nop     dword ptr [rax+rax+00h]
0x1800ff698  mov     ebx, edi
0x1800ff69a  mov     rcx, [rbp+lpFileName]; pv
0x1800ff69e  call    cs:__imp_CoTaskMemFree
0x1800ff6a5  nop     dword ptr [rax+rax+00h]
0x1800ff6aa  lea     rcx, [rbp+arg_30]
0x1800ff6ae  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800ff6b3  xor     ecx, ecx; void *
0x1800ff6b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800ff6ba  mov     eax, ebx
0x1800ff6bc  add     rsp, 58h
0x1800ff6c0  pop     r15
0x1800ff6c2  pop     r14
0x1800ff6c4  pop     rdi
0x1800ff6c5  pop     rsi
0x1800ff6c6  pop     rbx
0x1800ff6c7  pop     rbp
0x1800ff6c8  retn
```
