# UnbundleEncrypted

- ea: `0x180091410`
- end: `0x180091726`
- name: `UnbundleEncrypted`
- size: `790`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, Appx::Packaging *, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18001bb60`
- `0x180071f50`
- `0x1800844ac`
- `0x180091410`
- `0x180091a24`
- `0x18009239c`
- `0x1800924c8`
- `0x18009257c`
- `0x1800925b8`
- `0x180092b7c`
- `0x1800992c4`
- `0x1800c3ddc`
- `0x1800c3e84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009159c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800915e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009163c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800916a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800916c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800916d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009159c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800915e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009163c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800916a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800916c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800916d7`

## string_xrefs

- `0x18009144d`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x18009148e`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x1800914d5`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180091587`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x1800915d3`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180091627`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180091681`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x18009152d`: `Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create(packageStream.Get(), keyInfo, &bundleReader)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UnbundleEncrypted(
        Appx::Packaging *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        Appx::Packaging *a6,
        struct IAppxBundleReader **a7)
{
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // eax
  Appx::Packaging *v14; // rdi
  struct IStream **v15; // r9
  int PackageStream; // eax
  struct IAppxMessageHandler *v17; // rdx
  unsigned __int16 **v18; // r8
  int PackageFullNameFromBundle; // eax
  unsigned __int64 v20; // rdx
  int DestinationDirectory; // eax
  unsigned __int64 v22; // rdx
  struct IAppxBundleReader *v23; // rbx
  int v24; // eax
  int v25; // edi
  unsigned __int64 v26; // rdx
  struct IAppxBundleReader **v27; // rsi
  int v28; // eax
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  unsigned __int16 **v32; // [rsp+20h] [rbp-40h]
  unsigned __int16 **v33; // [rsp+20h] [rbp-40h]
  int v34; // [rsp+20h] [rbp-40h]
  Appx::Packaging *v35; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  __int64 v37; // [rsp+40h] [rbp-20h] BYREF
  struct IAppxBundleReader *v38[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v40; // [rsp+90h] [rbp+30h] BYREF

  v38[1] = (struct IAppxBundleReader *)-2LL;
  if ( a1 )
  {
    if ( !a2 )
    {
      v11 = 151;
      goto LABEL_3;
    }
    v40 = -2147221008;
    v13 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v40, (unsigned int)a2);
    v12 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9B,
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
        (void *)0x9E,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)PackageStream,
        (int)v32);
LABEL_25:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v37);
      goto LABEL_26;
    }
    v35 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
    LODWORD(v32) = 1;
    v12 = Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create(v37, a5, 0, &v35);
    if ( v12 < 0 )
    {
      Appx::Packaging::LogErrorInfo(v14, v17);
      Appx::Packaging::LogMessage(
        v14,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create(packageStream.Get(), keyInfo, &bundleReader)",
        v12);
LABEL_12:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v35);
      goto LABEL_25;
    }
    v38[0] = 0;
    pv = 0;
    PackageFullNameFromBundle = Appx::Packaging::GetPackageFullNameFromBundle(v35, (struct IAppxBundleReader *)&pv, v18);
    v12 = PackageFullNameFromBundle;
    if ( PackageFullNameFromBundle < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)PackageFullNameFromBundle,
        1);
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
        (void *)0xA7,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)DestinationDirectory,
        (int)v33);
      CoTaskMemFree(pv);
      operator delete(v38[0], v22);
      goto LABEL_12;
    }
    v23 = v38[0];
    v24 = Appx::Packaging::UnbundleInternal(
            v35,
            v38[0],
            (const unsigned __int16 *)a4,
            (int)v14,
            (struct IAppxMessageHandler *)v33);
    v25 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA9,
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
          (void *)0xAE,
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
  v11 = 150;
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
0x180091410  mov     rax, rsp
0x180091413  push    rbp
0x180091414  push    rdi
0x180091415  push    r12
0x180091417  push    r14
0x180091419  push    r15
0x18009141b  mov     rbp, rsp
0x18009141e  sub     rsp, 60h
0x180091422  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18009142a  mov     [rax+10h], rbx
0x18009142e  mov     [rax+18h], rsi
0x180091432  mov     r12d, r9d
0x180091435  mov     r15d, r8d
0x180091438  mov     rsi, rdx
0x18009143b  mov     r14, rcx
0x18009143e  test    rcx, rcx
0x180091441  jnz     short loc_180091465
0x180091443  mov     edx, 96h; void *
0x180091448  mov     ebx, 80070057h
0x18009144d  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091454  mov     r9d, ebx; char *
0x180091457  mov     rcx, [rbp+28h]; this
0x18009145b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180091460  jmp     loc_18009170A
0x180091465  test    rsi, rsi
0x180091468  jnz     short loc_180091471
0x18009146a  mov     edx, 97h; unsigned int
0x18009146f  jmp     short loc_180091448
0x180091471  mov     [rbp+arg_0], 800401F0h
0x180091478  lea     rcx, [rbp+arg_0]; this
0x18009147c  call    ?Initialize@AutoCoInitialize@Common@@QEAAJK@Z; Common::AutoCoInitialize::Initialize(ulong)
0x180091481  mov     ebx, eax
0x180091483  mov     rcx, [rbp+28h]; this
0x180091487  test    eax, eax
0x180091489  jns     short loc_1800914A4
0x18009148b  mov     r9d, eax; char *
0x18009148e  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091495  mov     edx, 9Bh; void *
0x18009149a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009149f  jmp     loc_180091701
0x1800914a4  mov     [rbp+var_20], 0
0x1800914ac  lea     rcx, [rbp+var_20]
0x1800914b0  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800914b5  lea     r8, [rbp+var_20]; struct IAppxMessageHandler *
0x1800914b9  mov     rdi, [rbp+arg_28]
0x1800914bd  mov     rdx, rdi; unsigned __int16 *
0x1800914c0  mov     rcx, r14; this
0x1800914c3  call    ?GetPackageStream@Packaging@Appx@@YAJPEBGPEAUIAppxMessageHandler@@PEAPEAUIStream@@@Z; Appx::Packaging::GetPackageStream(ushort const *,IAppxMessageHandler *,IStream * *)
0x1800914c8  mov     ebx, eax
0x1800914ca  mov     rcx, [rbp+28h]; this
0x1800914ce  test    eax, eax
0x1800914d0  jns     short loc_1800914EB
0x1800914d2  mov     r9d, eax; char *
0x1800914d5  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x1800914dc  mov     edx, 9Eh; void *
0x1800914e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800914e6  jmp     loc_1800916F8
0x1800914eb  mov     [rbp+var_30], 0
0x1800914f3  lea     rcx, [rbp+var_30]
0x1800914f7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800914fc  mov     r14d, 1
0x180091502  mov     dword ptr [rsp+60h+var_40], r14d; int
0x180091507  lea     r9, [rbp+var_30]
0x18009150b  xor     r8d, r8d
0x18009150e  mov     rdx, [rbp+arg_20]
0x180091512  mov     rcx, [rbp+var_20]
0x180091516  call    ?Create@AppxEncryptedBundleReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@PEBUAPPX_KEY_INFO@@PEBGPEAPEAUIAppxBundleReader@@W4EncryptionKeyType@Encryption@34@@Z; Appx::Packaging::Consumption::AppxEncryptedBundleReader::Create(IStream *,APPX_KEY_INFO const *,ushort const *,IAppxBundleReader * *,Appx::Packaging::Encryption::EncryptionKeyType)
0x18009151b  mov     ebx, eax
0x18009151d  test    eax, eax
0x18009151f  jns     short loc_18009155D
0x180091521  mov     rcx, rdi; this
0x180091524  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x180091529  mov     [rsp+60h+var_38], ebx
0x18009152d  lea     rax, aAppxPackagingC_4; "Appx::Packaging::Consumption::AppxEncry"...
0x180091534  mov     [rsp+60h+var_40], rax
0x180091539  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x180091540  mov     r8d, r14d
0x180091543  lea     edx, [r14+1]
0x180091547  mov     rcx, rdi
0x18009154a  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x18009154f  lea     rcx, [rbp+var_30]
0x180091553  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180091558  jmp     loc_1800916F8
0x18009155d  mov     [rbp+var_18], 0
0x180091565  mov     [rbp+pv], 0
0x18009156d  lea     rdx, [rbp+pv]; struct IAppxBundleReader *
0x180091571  mov     rcx, [rbp+var_30]; this
0x180091575  call    ?GetPackageFullNameFromBundle@Packaging@Appx@@YAJPEAUIAppxBundleReader@@PEAPEAG@Z; Appx::Packaging::GetPackageFullNameFromBundle(IAppxBundleReader *,ushort * *)
0x18009157a  mov     ebx, eax
0x18009157c  mov     rcx, [rbp+28h]; this
0x180091580  test    eax, eax
0x180091582  jns     short loc_1800915B3
0x180091584  mov     r9d, eax; char *
0x180091587  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x18009158e  mov     edx, 0A6h; void *
0x180091593  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091598  mov     rcx, [rbp+pv]; pv
0x18009159c  call    cs:__imp_CoTaskMemFree
0x1800915a3  nop     dword ptr [rax+rax+00h]
0x1800915a8  nop
0x1800915a9  xor     ecx, ecx; void *
0x1800915ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800915b0  nop
0x1800915b1  jmp     short loc_18009154F
0x1800915b3  lea     r9, [rbp+var_18]; int
0x1800915b7  mov     r8d, r15d; unsigned __int16 *
0x1800915ba  mov     rdx, rsi; unsigned __int16 *
0x1800915bd  mov     rcx, [rbp+pv]; this
0x1800915c1  call    ?GetDestinationDirectory@Packaging@Appx@@YAJPEBG0HPEAPEAG@Z; Appx::Packaging::GetDestinationDirectory(ushort const *,ushort const *,int,ushort * *)
0x1800915c6  mov     ebx, eax
0x1800915c8  mov     rcx, [rbp+28h]; this
0x1800915cc  test    eax, eax
0x1800915ce  jns     short loc_180091604
0x1800915d0  mov     r9d, eax; char *
0x1800915d3  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x1800915da  mov     edx, 0A7h; void *
0x1800915df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800915e4  mov     rcx, [rbp+pv]; pv
0x1800915e8  call    cs:__imp_CoTaskMemFree
0x1800915ef  nop     dword ptr [rax+rax+00h]
0x1800915f4  nop
0x1800915f5  mov     rcx, [rbp+var_18]; void *
0x1800915f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800915fe  nop
0x1800915ff  jmp     loc_18009154F
0x180091604  mov     r9, rdi; int
0x180091607  mov     r8d, r12d; unsigned __int16 *
0x18009160a  mov     rbx, [rbp+var_18]
0x18009160e  mov     rdx, rbx; struct IAppxBundleReader *
0x180091611  mov     rcx, [rbp+var_30]; this
0x180091615  call    ?UnbundleInternal@Packaging@Appx@@YAJPEAUIAppxBundleReader@@PEBGHPEAUIAppxMessageHandler@@@Z; Appx::Packaging::UnbundleInternal(IAppxBundleReader *,ushort const *,int,IAppxMessageHandler *)
0x18009161a  mov     edi, eax
0x18009161c  mov     rcx, [rbp+28h]; this
0x180091620  test    eax, eax
0x180091622  jns     short loc_180091657
0x180091624  mov     r9d, eax; char *
0x180091627  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x18009162e  mov     edx, 0A9h; void *
0x180091633  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091638  mov     rcx, [rbp+pv]; pv
0x18009163c  call    cs:__imp_CoTaskMemFree
0x180091643  nop     dword ptr [rax+rax+00h]
0x180091648  nop
0x180091649  mov     rcx, rbx; void *
0x18009164c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180091651  nop
0x180091652  jmp     loc_1800916ED
0x180091657  mov     rsi, [rbp+arg_30]
0x18009165b  test    rsi, rsi
0x18009165e  jz      short loc_1800916D3
0x180091660  mov     [rbp+var_18], 0
0x180091668  mov     rdx, rbx
0x18009166b  lea     rcx, [rbp+var_18]
0x18009166f  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x180091674  mov     edi, eax
0x180091676  mov     rcx, [rbp+28h]; this
0x18009167a  test    eax, eax
0x18009167c  jns     short loc_1800916BE
0x18009167e  mov     r9d, eax; char *
0x180091681  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091688  mov     edx, 0AEh; void *
0x18009168d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180091692  mov     rcx, [rbp+var_18]; pv
0x180091696  call    cs:__imp_CoTaskMemFree
0x18009169d  nop     dword ptr [rax+rax+00h]
0x1800916a2  mov     rcx, [rbp+pv]; pv
0x1800916a6  call    cs:__imp_CoTaskMemFree
0x1800916ad  nop     dword ptr [rax+rax+00h]
0x1800916b2  nop
0x1800916b3  mov     rcx, rbx; void *
0x1800916b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800916bb  nop
0x1800916bc  jmp     short loc_1800916ED
0x1800916be  mov     rax, [rbp+var_18]
0x1800916c2  mov     [rsi], rax
0x1800916c5  xor     ecx, ecx; pv
0x1800916c7  call    cs:__imp_CoTaskMemFree
0x1800916ce  nop     dword ptr [rax+rax+00h]
0x1800916d3  mov     rcx, [rbp+pv]; pv
0x1800916d7  call    cs:__imp_CoTaskMemFree
0x1800916de  nop     dword ptr [rax+rax+00h]
0x1800916e3  nop
0x1800916e4  mov     rcx, rbx; void *
0x1800916e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800916ec  nop
0x1800916ed  lea     rcx, [rbp+var_30]
0x1800916f1  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800916f6  mov     ebx, edi
0x1800916f8  lea     rcx, [rbp+var_20]
0x1800916fc  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180091701  lea     rcx, [rbp+arg_0]; this
0x180091705  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x18009170a  mov     eax, ebx
0x18009170c  lea     r11, [rsp+60h+var_s0]
0x180091711  mov     rbx, [r11+38h]
0x180091715  mov     rsi, [r11+40h]
0x180091719  mov     rsp, r11
0x18009171c  pop     r15
0x18009171e  pop     r14
0x180091720  pop     r12
0x180091722  pop     rdi
0x180091723  pop     rbp
0x180091724  retn
```
