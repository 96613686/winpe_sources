# Unpack

- ea: `0x180091fc0`
- end: `0x1800922ad`
- name: `Unpack`
- size: `749`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18001bb60`
- `0x180046f00`
- `0x180071f50`
- `0x180091fc0`
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

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009212f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009217b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800921cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009225a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009226a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009212f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009217b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800921cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009225a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009226a`

## string_xrefs

- `0x180091ff1`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180092030`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180092073`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x18009211a`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180092166`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x1800921ba`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x180092214`: `onecore\printscan\appxpackaging\dll\lib\exports.cpp`
- `0x1800920be`: `Appx::Packaging::Consumption::AppxPackageReader::Create(packageStream.Get(), &packageReader)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Unpack(
        Appx::Packaging *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct IAppxPackageReader **a5)
{
  unsigned int v6; // r15d
  __int64 v9; // rdx
  int v10; // ebx
  int v11; // eax
  struct IStream **v12; // r9
  int PackageStream; // eax
  struct IAppxMessageHandler *v14; // rdx
  unsigned __int16 **v15; // r8
  int PackageFullNameFromPackage; // eax
  unsigned __int64 v17; // rdx
  int DestinationDirectory; // eax
  unsigned __int64 v19; // rdx
  struct IAppxPackageReader *v20; // rbx
  int v21; // eax
  int v22; // edi
  unsigned __int64 v23; // rdx
  struct IAppxPackageReader **v24; // rsi
  int v25; // eax
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  unsigned __int16 **v29; // [rsp+20h] [rbp-48h]
  struct IAppxMessageHandler *v30; // [rsp+20h] [rbp-48h]
  int v31; // [rsp+20h] [rbp-48h]
  struct IAppxPackageReader *v32; // [rsp+30h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-30h] BYREF
  struct IStream *v34; // [rsp+40h] [rbp-28h] BYREF
  struct IAppxPackageReader *v35[4]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  int v37; // [rsp+A0h] [rbp+38h] BYREF

  v35[1] = (struct IAppxPackageReader *)-2LL;
  v6 = (unsigned int)a3;
  if ( this )
  {
    if ( !a2 )
    {
      v9 = 29;
      goto LABEL_3;
    }
    v37 = -2147221008;
    v11 = Common::AutoCoInitialize::Initialize((Common::AutoCoInitialize *)&v37, (unsigned int)a2);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)v11,
        (int)v29);
LABEL_26:
      Common::AutoCoInitialize::~AutoCoInitialize((Common::AutoCoInitialize *)&v37);
      return (unsigned int)v10;
    }
    v34 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v34);
    PackageStream = Appx::Packaging::GetPackageStream(this, a4, (struct IAppxMessageHandler *)&v34, v12);
    v10 = PackageStream;
    if ( PackageStream < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)PackageStream,
        (int)v29);
LABEL_25:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v34);
      goto LABEL_26;
    }
    v32 = 0;
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v32);
    v10 = Appx::Packaging::Consumption::AppxPackageReader::Create(v34, 1, 0, &v32);
    if ( v10 < 0 )
    {
      Appx::Packaging::LogErrorInfo((Appx::Packaging *)a4, v14);
      Appx::Packaging::LogMessage(
        a4,
        2,
        1,
        L"Failure at %1!hs! - 0x%2!x!\n",
        "Appx::Packaging::Consumption::AppxPackageReader::Create(packageStream.Get(), &packageReader)",
        v10);
LABEL_12:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v32);
      goto LABEL_25;
    }
    v35[0] = 0;
    pv = 0;
    PackageFullNameFromPackage = Appx::Packaging::GetPackageFullNameFromPackage(
                                   (Appx::Packaging *)v32,
                                   (struct IAppxPackageReader *)&pv,
                                   v15);
    v10 = PackageFullNameFromPackage;
    if ( PackageFullNameFromPackage < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)PackageFullNameFromPackage,
        (int)v29);
      CoTaskMemFree(pv);
      operator delete(0, v17);
      goto LABEL_12;
    }
    DestinationDirectory = Appx::Packaging::GetDestinationDirectory(
                             (Appx::Packaging *)pv,
                             a2,
                             (const unsigned __int16 *)v6,
                             (int)v35,
                             v29);
    v10 = DestinationDirectory;
    if ( DestinationDirectory < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)DestinationDirectory,
        (int)v30);
      CoTaskMemFree(pv);
      operator delete(v35[0], v19);
      goto LABEL_12;
    }
    v20 = v35[0];
    v21 = Appx::Packaging::UnpackInternal((Appx::Packaging *)v32, v35[0], 0, (int)a4, v30);
    v22 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
        (const char *)(unsigned int)v21,
        v31);
      CoTaskMemFree(pv);
      operator delete(v20, v23);
LABEL_24:
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v32);
      v10 = v22;
      goto LABEL_25;
    }
    v24 = a5;
    if ( a5 )
    {
      v35[0] = 0;
      v25 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoCoTaskMemStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoCoTaskMemStringDeallocate(unsigned short *)>::CopyFromString(
              v35,
              v20);
      v22 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
          (const char *)(unsigned int)v25,
          v31);
        CoTaskMemFree(v35[0]);
        CoTaskMemFree(pv);
        operator delete(v20, v26);
        goto LABEL_24;
      }
      *v24 = v35[0];
      CoTaskMemFree(0);
    }
    CoTaskMemFree(pv);
    operator delete(v20, v27);
    goto LABEL_24;
  }
  v9 = 28;
LABEL_3:
  v10 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\exports.cpp",
    (const char *)0x80070057LL,
    (int)v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180091fc0  push    rbp
0x180091fc2  push    rbx
0x180091fc3  push    rsi
0x180091fc4  push    rdi
0x180091fc5  push    r14
0x180091fc7  push    r15
0x180091fc9  mov     rbp, rsp
0x180091fcc  sub     rsp, 68h
0x180091fd0  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x180091fd8  mov     rdi, r9
0x180091fdb  mov     r15d, r8d
0x180091fde  mov     rsi, rdx
0x180091fe1  mov     r14, rcx
0x180091fe4  test    rcx, rcx
0x180091fe7  jnz     short loc_180092009
0x180091fe9  lea     edx, [rcx+1Ch]; void *
0x180091fec  mov     ebx, 80070057h
0x180091ff1  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180091ff8  mov     r9d, ebx; char *
0x180091ffb  mov     rcx, [rbp+30h]; this
0x180091fff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180092004  jmp     loc_18009229D
0x180092009  test    rsi, rsi
0x18009200c  jnz     short loc_180092013
0x18009200e  lea     edx, [rsi+1Dh]; unsigned int
0x180092011  jmp     short loc_180091FEC
0x180092013  mov     [rbp+arg_0], 800401F0h
0x18009201a  lea     rcx, [rbp+arg_0]; this
0x18009201e  call    ?Initialize@AutoCoInitialize@Common@@QEAAJK@Z; Common::AutoCoInitialize::Initialize(ulong)
0x180092023  mov     ebx, eax
0x180092025  mov     rcx, [rbp+30h]; this
0x180092029  test    eax, eax
0x18009202b  jns     short loc_180092046
0x18009202d  mov     r9d, eax; char *
0x180092030  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180092037  mov     edx, 21h ; '!'; void *
0x18009203c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092041  jmp     loc_180092294
0x180092046  mov     [rbp+var_28], 0
0x18009204e  lea     rcx, [rbp+var_28]
0x180092052  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180092057  lea     r8, [rbp+var_28]; struct IAppxMessageHandler *
0x18009205b  mov     rdx, rdi; unsigned __int16 *
0x18009205e  mov     rcx, r14; this
0x180092061  call    ?GetPackageStream@Packaging@Appx@@YAJPEBGPEAUIAppxMessageHandler@@PEAPEAUIStream@@@Z; Appx::Packaging::GetPackageStream(ushort const *,IAppxMessageHandler *,IStream * *)
0x180092066  mov     ebx, eax
0x180092068  mov     rcx, [rbp+30h]; this
0x18009206c  test    eax, eax
0x18009206e  jns     short loc_180092089
0x180092070  mov     r9d, eax; char *
0x180092073  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x18009207a  mov     edx, 24h ; '$'; void *
0x18009207f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092084  jmp     loc_18009228B
0x180092089  mov     [rbp+var_38], 0
0x180092091  lea     rcx, [rbp+var_38]
0x180092095  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009209a  lea     r9, [rbp+var_38]; struct IAppxPackageReader **
0x18009209e  xor     r8d, r8d; unsigned __int16 *
0x1800920a1  mov     dl, 1; bool
0x1800920a3  mov     rcx, [rbp+var_28]; struct IStream *
0x1800920a7  call    ?Create@AppxPackageReader@Consumption@Packaging@Appx@@SAJPEAUIStream@@_NPEBGPEAPEAUIAppxPackageReader@@@Z; Appx::Packaging::Consumption::AppxPackageReader::Create(IStream *,bool,ushort const *,IAppxPackageReader * *)
0x1800920ac  mov     ebx, eax
0x1800920ae  test    eax, eax
0x1800920b0  jns     short loc_1800920F0
0x1800920b2  mov     rcx, rdi; this
0x1800920b5  call    ?LogErrorInfo@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@@Z; Appx::Packaging::LogErrorInfo(IAppxMessageHandler *)
0x1800920ba  mov     [rsp+68h+var_40], ebx
0x1800920be  lea     rax, aAppxPackagingC_1; "Appx::Packaging::Consumption::AppxPacka"...
0x1800920c5  mov     [rsp+68h+var_48], rax
0x1800920ca  lea     r9, aFailureAt1Hs0x; "Failure at %1!hs! - 0x%2!x!\n"
0x1800920d1  mov     edx, 2
0x1800920d6  lea     r8d, [rdx-1]
0x1800920da  mov     rcx, rdi
0x1800920dd  call    ?LogMessage@Packaging@Appx@@YAXPEAUIAppxMessageHandler@@W4APPX_MESSAGE_TYPE@@_NPEBGZZ; Appx::Packaging::LogMessage(IAppxMessageHandler *,APPX_MESSAGE_TYPE,bool,ushort const *,...)
0x1800920e2  lea     rcx, [rbp+var_38]
0x1800920e6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800920eb  jmp     loc_18009228B
0x1800920f0  mov     [rbp+var_20], 0
0x1800920f8  mov     [rbp+pv], 0
0x180092100  lea     rdx, [rbp+pv]; struct IAppxPackageReader *
0x180092104  mov     rcx, [rbp+var_38]; this
0x180092108  call    ?GetPackageFullNameFromPackage@Packaging@Appx@@YAJPEAUIAppxPackageReader@@PEAPEAG@Z; Appx::Packaging::GetPackageFullNameFromPackage(IAppxPackageReader *,ushort * *)
0x18009210d  mov     ebx, eax
0x18009210f  mov     rcx, [rbp+30h]; this
0x180092113  test    eax, eax
0x180092115  jns     short loc_180092146
0x180092117  mov     r9d, eax; char *
0x18009211a  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x180092121  mov     edx, 2Ch ; ','; void *
0x180092126  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009212b  mov     rcx, [rbp+pv]; pv
0x18009212f  call    cs:__imp_CoTaskMemFree
0x180092136  nop     dword ptr [rax+rax+00h]
0x18009213b  nop
0x18009213c  xor     ecx, ecx; void *
0x18009213e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180092143  nop
0x180092144  jmp     short loc_1800920E2
0x180092146  lea     r9, [rbp+var_20]; int
0x18009214a  mov     r8d, r15d; unsigned __int16 *
0x18009214d  mov     rdx, rsi; unsigned __int16 *
0x180092150  mov     rcx, [rbp+pv]; this
0x180092154  call    ?GetDestinationDirectory@Packaging@Appx@@YAJPEBG0HPEAPEAG@Z; Appx::Packaging::GetDestinationDirectory(ushort const *,ushort const *,int,ushort * *)
0x180092159  mov     ebx, eax
0x18009215b  mov     rcx, [rbp+30h]; this
0x18009215f  test    eax, eax
0x180092161  jns     short loc_180092197
0x180092163  mov     r9d, eax; char *
0x180092166  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x18009216d  mov     edx, 2Dh ; '-'; void *
0x180092172  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092177  mov     rcx, [rbp+pv]; pv
0x18009217b  call    cs:__imp_CoTaskMemFree
0x180092182  nop     dword ptr [rax+rax+00h]
0x180092187  nop
0x180092188  mov     rcx, [rbp+var_20]; void *
0x18009218c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180092191  nop
0x180092192  jmp     loc_1800920E2
0x180092197  mov     r9, rdi; int
0x18009219a  xor     r8d, r8d; unsigned __int16 *
0x18009219d  mov     rbx, [rbp+var_20]
0x1800921a1  mov     rdx, rbx; struct IAppxPackageReader *
0x1800921a4  mov     rcx, [rbp+var_38]; this
0x1800921a8  call    ?UnpackInternal@Packaging@Appx@@YAJPEAUIAppxPackageReader@@PEBGHPEAUIAppxMessageHandler@@@Z; Appx::Packaging::UnpackInternal(IAppxPackageReader *,ushort const *,int,IAppxMessageHandler *)
0x1800921ad  mov     edi, eax
0x1800921af  mov     rcx, [rbp+30h]; this
0x1800921b3  test    eax, eax
0x1800921b5  jns     short loc_1800921EA
0x1800921b7  mov     r9d, eax; char *
0x1800921ba  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x1800921c1  mov     edx, 2Fh ; '/'; void *
0x1800921c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800921cb  mov     rcx, [rbp+pv]; pv
0x1800921cf  call    cs:__imp_CoTaskMemFree
0x1800921d6  nop     dword ptr [rax+rax+00h]
0x1800921db  nop
0x1800921dc  mov     rcx, rbx; void *
0x1800921df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800921e4  nop
0x1800921e5  jmp     loc_180092280
0x1800921ea  mov     rsi, [rbp+arg_20]
0x1800921ee  test    rsi, rsi
0x1800921f1  jz      short loc_180092266
0x1800921f3  mov     [rbp+var_20], 0
0x1800921fb  mov     rdx, rbx
0x1800921fe  lea     rcx, [rbp+var_20]
0x180092202  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoCoTaskMemStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoCoTaskMemStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoCoTaskMemStringAllocateAndCopy(ushort const *,uint),&Common::AutoCoTaskMemStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x180092207  mov     edi, eax
0x180092209  mov     rcx, [rbp+30h]; this
0x18009220d  test    eax, eax
0x18009220f  jns     short loc_180092251
0x180092211  mov     r9d, eax; char *
0x180092214  lea     r8, aOnecorePrintsc_142; "onecore\\printscan\\appxpackaging\\dll"...
0x18009221b  mov     edx, 34h ; '4'; void *
0x180092220  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092225  mov     rcx, [rbp+var_20]; pv
0x180092229  call    cs:__imp_CoTaskMemFree
0x180092230  nop     dword ptr [rax+rax+00h]
0x180092235  mov     rcx, [rbp+pv]; pv
0x180092239  call    cs:__imp_CoTaskMemFree
0x180092240  nop     dword ptr [rax+rax+00h]
0x180092245  nop
0x180092246  mov     rcx, rbx; void *
0x180092249  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009224e  nop
0x18009224f  jmp     short loc_180092280
0x180092251  mov     rax, [rbp+var_20]
0x180092255  mov     [rsi], rax
0x180092258  xor     ecx, ecx; pv
0x18009225a  call    cs:__imp_CoTaskMemFree
0x180092261  nop     dword ptr [rax+rax+00h]
0x180092266  mov     rcx, [rbp+pv]; pv
0x18009226a  call    cs:__imp_CoTaskMemFree
0x180092271  nop     dword ptr [rax+rax+00h]
0x180092276  nop
0x180092277  mov     rcx, rbx; void *
0x18009227a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009227f  nop
0x180092280  lea     rcx, [rbp+var_38]
0x180092284  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180092289  mov     ebx, edi
0x18009228b  lea     rcx, [rbp+var_28]
0x18009228f  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180092294  lea     rcx, [rbp+arg_0]; this
0x180092298  call    ??1AutoCoInitialize@Common@@QEAA@XZ; Common::AutoCoInitialize::~AutoCoInitialize(void)
0x18009229d  mov     eax, ebx
0x18009229f  add     rsp, 68h
0x1800922a3  pop     r15
0x1800922a5  pop     r14
0x1800922a7  pop     rdi
0x1800922a8  pop     rsi
0x1800922a9  pop     rbx
0x1800922aa  pop     rbp
0x1800922ab  retn
```
