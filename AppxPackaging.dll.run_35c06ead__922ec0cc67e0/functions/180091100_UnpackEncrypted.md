# UnpackEncrypted

- ea: `0x180091100`
- end: `0x180091409`
- name: `UnpackEncrypted`
- size: `777`
- prototype: `__int64 __fastcall(int, int, int, int, struct APPX_KEY_INFO *, Appx::Packaging *, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18001bb60`
- `0x180071f50`
- `0x18008fe34`
- `0x180091100`
- `0x1800922b4`
- `0x18009239c`
- `0x1800924c8`
- `0x18009257c`
- `0x1800925b8`
- `0x1800925e8`
- `0x1800992c4`
- `0x1800c3ddc`
- `0x1800c3e84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009127f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800912cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009131f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800913aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800913ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009127f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800912cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009131f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091379`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091389`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800913aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800913ba`

## string_xrefs

- `0x18009113b`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x18009117a`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x1800911c1`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x18009126a`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x1800912b6`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x18009130a`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180091364`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x18009120e`: `Appx::Packaging::Consumption::AppxEncryptedPackageReader::Create(packageStream.Get(), keyInfo, &packageReader)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnpackEncrypted(
        Appx::Packaging *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        struct APPX_KEY_INFO *a5,
        Appx::Packaging *a6,
        struct IAppxPackageReader **a7)
{
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // eax
  Appx::Packaging *v14; // rdi
  struct IStream **v15; // r9
  int PackageStream; // eax
  struct IAppxMessageHandler *v17; // rdx
  unsigned __int16 **v18; // r8
  int PackageFullNameFromPackage; // eax
  unsigned __int64 v20; // rdx
  int DestinationDirectory; // eax
  unsigned __int64 v22; // rdx
  struct IAppxPackageReader *v23; // rbx
  int v24; // eax
  int v25; // edi
  unsigned __int64 v26; // rdx
  struct IAppxPackageReader **v27; // rsi
  int v28; // eax
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  unsigned __int16 **v32; // [rsp+20h] [rbp-40h]
  struct IAppxMessageHandler *v33; // [rsp+20h] [rbp-40h]
  int v34; // [rsp+20h] [rbp-40h]
  struct IAppxPackageReader *v35; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  struct IStream *v37; // [rsp+40h] [rbp-20h] BYREF
  struct IAppxPackageReader *v38[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v40; // [rsp+90h] [rbp+30h] BYREF

  v38[1] = (struct IAppxPackageReader *)-2LL;
  if ( a1 )
  {
    if ( !a2 )
    {
      v11 = 110;
      goto LABEL_3;
    }
    v40 = -2147221008;
    v13 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v40, (unsigned int)a2);
    v12 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)v13,
        (int)v32);
LABEL_26:
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v40);
      return (unsigned int)v12;
    }
    v37 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
    v14 = a6;
    PackageStream = Appx::Packaging::GetPackageStream(
                      a1,
                      (const unsigned __int16 *)a6,
                      (struct IAppxMessageHandler *)&v37,
                      v15);
    v12 = PackageStream;
    if ( PackageStream < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)PackageStream,
        (int)v32);
LABEL_25:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
      goto LABEL_26;
    }
    v35 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
    v12 = Appx::Packaging::Consumption::AppxEncryptedPackageReader::Create(v37, a5, 0, &v35);
    if ( v12 < 0 )
    {
      Appx::Packaging::LogErrorInfo(v14, v17);
      Appx::Packaging::LogMessage(
        v14,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "Appx::Packaging::Consumption::AppxEncryptedPackageReader::Create(packageStream.Get(), keyInfo, &packageReader)",
        v12);
LABEL_12:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
      goto LABEL_25;
    }
    v38[0] = 0;
    pv = 0;
    PackageFullNameFromPackage = Appx::Packaging::GetPackageFullNameFromPackage(
                                   (Appx::Packaging *)v35,
                                   (struct IAppxPackageReader *)&pv,
                                   v18);
    v12 = PackageFullNameFromPackage;
    if ( PackageFullNameFromPackage < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)PackageFullNameFromPackage,
        (int)v32);
      CoTaskMemFree(pv);
      operator delete(0, v20);
      goto LABEL_12;
    }
    DestinationDirectory = Appx::Packaging::GetDestinationDirectory(
                             (Appx::Packaging *)pv,
                             a2,
                             (const unsigned __int16 *)a3,
                             (int)v38,
                             v32);
    v12 = DestinationDirectory;
    if ( DestinationDirectory < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)DestinationDirectory,
        (int)v33);
      CoTaskMemFree(pv);
      operator delete(v38[0], v22);
      goto LABEL_12;
    }
    v23 = v38[0];
    v24 = Appx::Packaging::UnpackInternal((Appx::Packaging *)v35, v38[0], (const unsigned __int16 *)a4, (int)v14, v33);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)v24,
        v34);
      CoTaskMemFree(pv);
      operator delete(v23, v26);
LABEL_24:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
      v12 = v25;
      goto LABEL_25;
    }
    v27 = a7;
    if ( a7 )
    {
      v38[0] = 0;
      v28 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
              v38,
              v23);
      v25 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
          (const char *)(unsigned int)v28,
          v34);
        CoTaskMemFree(v38[0]);
        CoTaskMemFree(pv);
        operator delete(v23, v29);
        goto LABEL_24;
      }
      *v27 = v38[0];
      CoTaskMemFree(0);
    }
    CoTaskMemFree(pv);
    operator delete(v23, v30);
    goto LABEL_24;
  }
  v11 = 109;
LABEL_3:
  v12 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
    (const char *)0x80070057LL,
    (int)v32);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180091100  mov     rax, rsp
0x180091103  push    rbp
0x180091104  push    rdi
0x180091105  push    r12
0x180091107  push    r14
0x180091109  push    r15
0x18009110b  mov     rbp, rsp
0x18009110e  sub     rsp, 60h
0x180091112  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18009111a  mov     [rax+10h], rbx
0x18009111e  mov     [rax+18h], rsi
0x180091122  mov     r12d, r9d
0x180091125  mov     r15d, r8d
0x180091128  mov     rsi, rdx
0x18009112b  mov     r14, rcx
0x18009112e  test    rcx, rcx
0x180091131  jnz     short loc_180091153
0x180091133  lea     edx, [rcx+6Dh]; void *
0x180091136  mov     ebx, 80070057h
0x18009113b  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091142  mov     r9d, ebx; char *
0x180091145  mov     rcx, [rbp+28h]; this
0x180091149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009114e  jmp     loc_1800913ED
0x180091153  test    rsi, rsi
0x180091156  jnz     short loc_18009115D
0x180091158  lea     edx, [rsi+6Eh]; unsigned int
0x18009115b  jmp     short loc_180091136
0x18009115d  mov     [rbp+arg_0], 800401F0h
0x180091164  lea     rcx, [rbp+arg_0]; this
0x180091168  call    ?Initialize@AutoCoInitialize@Common@@QEAAJK@Z; Common::AutoCoInitialize::Initialize(ulong)
0x18009116d  mov     ebx, eax
0x18009116f  mov     rcx, [rbp+28h]; this
0x180091173  test    eax, eax
0x180091175  jns     short loc_180091190
0x180091177  mov     r9d, eax; char *
0x18009117a  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091181  mov     edx, 72h ; 'r'; void *
0x180091186  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009118b  jmp     loc_1800913E4
0x180091190  mov     [rbp+var_20], 0
0x180091198  lea     rcx, [rbp+var_20]
0x18009119c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800911a1  lea     r8, [rbp+var_20]; struct IAppxMessageHandler *
0x1800911a5  mov     rdi, [rbp+arg_28]
0x1800911a9  mov     rdx, rdi; unsigned __int16 *
0x1800911ac  mov     rcx, r14; this
0x1800911af  call    ?GetPackageStream@Packaging@Appx@@YAJPEBGPEAUIAppxMessageHandler@@PEAPEAUIStream@@@Z; Appx::Packaging::GetPackageStream(ushort const *,IAppxMessageHandler *,IStream * *)
0x1800911b4  mov     ebx, eax
0x1800911b6  mov     rcx, [rbp+28h]; this
0x1800911ba  test    eax, eax
0x1800911bc  jns     short loc_1800911D7
0x1800911be  mov     r9d, eax; char *
0x1800911c1  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x1800911c8  mov     edx, 75h ; 'u'; void *
0x1800911cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800911d2  jmp     loc_1800913DB
0x1800911d7  mov     [rbp+var_30], 0
0x1800911df  lea     rcx, [rbp+var_30]
0x1800911e3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800911e8  lea     r9, [rbp+var_30]; struct IAppxPackageReader **
0x1800911ec  xor     r8d, r8d; unsigned __int16 *
0x1800911ef  mov     rdx, [rbp+arg_20]; struct APPX_KEY_INFO *
0x1800911f3  mov     rcx, [rbp+var_20]; struct IStream *
0x1800911f7  call    ?Create@AppxEncryptedPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEBUAPPX_KEY_INFO@@PEBGPEAPEAUIAppxPackageReader@@@Z; Appx::Packaging::Consumption::AppxEncryptedPackageReader::Create(IStream *,APPX_KEY_INFO const *,ushort const *,IAppxPackageReader * *)
0x1800911fc  mov     ebx, eax
0x1800911fe  test    eax, eax
0x180091200  jns     short loc_180091240
0x180091202  mov     rcx, rdi; this
0x180091205  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x18009120a  mov     [rsp+60h+var_38], ebx
0x18009120e  lea     rax, aAppxPackagingC_0; "Appx::Packaging::Consumption::AppxEncry"...
0x180091215  mov     [rsp+60h+var_40], rax
0x18009121a  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x180091221  mov     edx, 2
0x180091226  lea     r8d, [rdx-1]
0x18009122a  mov     rcx, rdi
0x18009122d  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x180091232  lea     rcx, [rbp+var_30]
0x180091236  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009123b  jmp     loc_1800913DB
0x180091240  mov     [rbp+var_18], 0
0x180091248  mov     [rbp+pv], 0
0x180091250  lea     rdx, [rbp+pv]; struct IAppxPackageReader *
0x180091254  mov     rcx, [rbp+var_30]; this
0x180091258  call    ?GetPackageFullNameFromPackage@Packaging@Appx@@YAJPEAUIAppxPackageReader@@PEAPEAG@Z; Appx::Packaging::GetPackageFullNameFromPackage(IAppxPackageReader *,ushort * *)
0x18009125d  mov     ebx, eax
0x18009125f  mov     rcx, [rbp+28h]; this
0x180091263  test    eax, eax
0x180091265  jns     short loc_180091296
0x180091267  mov     r9d, eax; char *
0x18009126a  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091271  mov     edx, 7Dh ; '}'; void *
0x180091276  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009127b  mov     rcx, [rbp+pv]; pv
0x18009127f  call    cs:__imp_CoTaskMemFree
0x180091286  nop     dword ptr [rax+rax+00h]
0x18009128b  nop
0x18009128c  xor     ecx, ecx; void *
0x18009128e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180091293  nop
0x180091294  jmp     short loc_180091232
0x180091296  lea     r9, [rbp+var_18]; int
0x18009129a  mov     r8d, r15d; unsigned __int16 *
0x18009129d  mov     rdx, rsi; unsigned __int16 *
0x1800912a0  mov     rcx, [rbp+pv]; this
0x1800912a4  call    ?GetDestinationDirectory@Packaging@Appx@@YAJPEBG0HPEAPEAG@Z; Appx::Packaging::GetDestinationDirectory(ushort const *,ushort const *,int,ushort * *)
0x1800912a9  mov     ebx, eax
0x1800912ab  mov     rcx, [rbp+28h]; this
0x1800912af  test    eax, eax
0x1800912b1  jns     short loc_1800912E7
0x1800912b3  mov     r9d, eax; char *
0x1800912b6  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x1800912bd  mov     edx, 7Eh ; '~'; void *
0x1800912c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800912c7  mov     rcx, [rbp+pv]; pv
0x1800912cb  call    cs:__imp_CoTaskMemFree
0x1800912d2  nop     dword ptr [rax+rax+00h]
0x1800912d7  nop
0x1800912d8  mov     rcx, [rbp+var_18]; void *
0x1800912dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800912e1  nop
0x1800912e2  jmp     loc_180091232
0x1800912e7  mov     r9, rdi; int
0x1800912ea  mov     r8d, r12d; unsigned __int16 *
0x1800912ed  mov     rbx, [rbp+var_18]
0x1800912f1  mov     rdx, rbx; struct IAppxPackageReader *
0x1800912f4  mov     rcx, [rbp+var_30]; this
0x1800912f8  call    ?UnpackInternal@Packaging@Appx@@YAJPEAUIAppxPackageReader@@PEBGHPEAUIAppxMessageHandler@@@Z; Appx::Packaging::UnpackInternal(IAppxPackageReader *,ushort const *,int,IAppxMessageHandler *)
0x1800912fd  mov     edi, eax
0x1800912ff  mov     rcx, [rbp+28h]; this
0x180091303  test    eax, eax
0x180091305  jns     short loc_18009133A
0x180091307  mov     r9d, eax; char *
0x18009130a  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091311  mov     edx, 80h; void *
0x180091316  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009131b  mov     rcx, [rbp+pv]; pv
0x18009131f  call    cs:__imp_CoTaskMemFree
0x180091326  nop     dword ptr [rax+rax+00h]
0x18009132b  nop
0x18009132c  mov     rcx, rbx; void *
0x18009132f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180091334  nop
0x180091335  jmp     loc_1800913D0
0x18009133a  mov     rsi, [rbp+arg_30]
0x18009133e  test    rsi, rsi
0x180091341  jz      short loc_1800913B6
0x180091343  mov     [rbp+var_18], 0
0x18009134b  mov     rdx, rbx
0x18009134e  lea     rcx, [rbp+var_18]
0x180091352  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x180091357  mov     edi, eax
0x180091359  mov     rcx, [rbp+28h]; this
0x18009135d  test    eax, eax
0x18009135f  jns     short loc_1800913A1
0x180091361  mov     r9d, eax; char *
0x180091364  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x18009136b  mov     edx, 85h; void *
0x180091370  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091375  mov     rcx, [rbp+var_18]; pv
0x180091379  call    cs:__imp_CoTaskMemFree
0x180091380  nop     dword ptr [rax+rax+00h]
0x180091385  mov     rcx, [rbp+pv]; pv
0x180091389  call    cs:__imp_CoTaskMemFree
0x180091390  nop     dword ptr [rax+rax+00h]
0x180091395  nop
0x180091396  mov     rcx, rbx; void *
0x180091399  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009139e  nop
0x18009139f  jmp     short loc_1800913D0
0x1800913a1  mov     rax, [rbp+var_18]
0x1800913a5  mov     [rsi], rax
0x1800913a8  xor     ecx, ecx; pv
0x1800913aa  call    cs:__imp_CoTaskMemFree
0x1800913b1  nop     dword ptr [rax+rax+00h]
0x1800913b6  mov     rcx, [rbp+pv]; pv
0x1800913ba  call    cs:__imp_CoTaskMemFree
0x1800913c1  nop     dword ptr [rax+rax+00h]
0x1800913c6  nop
0x1800913c7  mov     rcx, rbx; void *
0x1800913ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800913cf  nop
0x1800913d0  lea     rcx, [rbp+var_30]
0x1800913d4  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800913d9  mov     ebx, edi
0x1800913db  lea     rcx, [rbp+var_20]
0x1800913df  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800913e4  lea     rcx, [rbp+arg_0]; this
0x1800913e8  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x1800913ed  mov     eax, ebx
0x1800913ef  lea     r11, [rsp+60h+var_s0]
0x1800913f4  mov     rbx, [r11+38h]
0x1800913f8  mov     rsi, [r11+40h]
0x1800913fc  mov     rsp, r11
0x1800913ff  pop     r15
0x180091401  pop     r14
0x180091403  pop     r12
0x180091405  pop     rdi
0x180091406  pop     rbp
0x180091407  retn
```
