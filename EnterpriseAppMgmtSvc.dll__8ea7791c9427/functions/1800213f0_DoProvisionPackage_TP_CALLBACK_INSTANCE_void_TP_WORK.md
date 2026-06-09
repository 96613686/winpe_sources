# DoProvisionPackage(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800213f0`
- end: `0x180021872`
- name: `?DoProvisionPackage@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1154`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000143c`
- `0x180001bf4`
- `0x180005de8`
- `0x18001c5b8`
- `0x18001cb50`
- `0x18001d704`
- `0x18001dbc8`
- `0x18001f604`
- `0x18001fe74`
- `0x1800213f0`
- `0x180029ca0`
- `0x18002a32c`
- `0x18002dec8`
- `0x1800315d4`
- `0x1800323f8`
- `0x180032788`
- `0x1800335d8`
- `0x18003780c`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800215e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021670`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800215e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021670`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180021833`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180021833`

## string_xrefs

- `0x180021774`: `./Device/Vendor/MSFT/EnterpriseModernAppManagement/AppInstallation/%s/HostedInstall`
- `0x1800216cf`: `Reversed-Domain-Name:com.microsoft.mdm.%s.result`
- `0x1800216c8`: `EnterpriseHostedAppInstall`
- `0x18002146e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180021532`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DoProvisionPackage(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  int v5; // eax
  int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  EnterpriseModernAppManagement **v9; // rdi
  int v10; // r15d
  int v11; // eax
  HKEY v12; // r8
  struct Common::RegistryKey *v13; // r9
  int *v14; // rbx
  int v15; // ecx
  int *v16; // rax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  _DWORD *v21; // rax
  HKEY v22; // r8
  void *v23; // rbx
  void *v24; // rax
  int v25; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // rdx
  unsigned __int16 *v28; // [rsp+20h] [rbp-E0h]
  int *v29; // [rsp+28h] [rbp-D8h]
  char *v30; // [rsp+50h] [rbp-B0h]
  MsixPackage::Provisioning::Library::MsixProvisioningManager *v31; // [rsp+68h] [rbp-98h]
  int v32; // [rsp+80h] [rbp-80h] BYREF
  int v33[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v34; // [rsp+90h] [rbp-70h]
  char v35[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *v36; // [rsp+A8h] [rbp-58h] BYREF
  void *v37; // [rsp+110h] [rbp+10h]
  int *v38; // [rsp+148h] [rbp+48h]
  void *v39[30]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v40[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v41[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+618h]

  if ( !Work )
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance, Context);
  if ( !Context )
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance, Context);
  MsixPackage::Provisioning::Library::MsixProvisioningManager::MsixProvisioningManager((MsixPackage::Provisioning::Library::MsixProvisioningManager *)v39);
  v34 = Context;
  v5 = MsixPackage::Provisioning::Library::MsixProvisioningManager::Initialize((MsixPackage::Provisioning::Library::MsixProvisioningManager *)v39);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v9 = (EnterpriseModernAppManagement **)(Context + 32);
    LOBYTE(v31) = Context[192];
    LODWORD(v30) = *((_DWORD *)Context + 22);
    v10 = MsixPackage::Provisioning::Library::MsixProvisioningManager::AddAllUserAppxPackageForCSP(
            (MsixPackage::Provisioning::Library::MsixProvisioningManager *)v39,
            *((OLECHAR **)Context + 1),
            *((unsigned __int16 **)Context + 4),
            *((unsigned __int16 ***)Context + 7),
            *((_DWORD *)Context + 16),
            *((const unsigned __int16 ***)Context + 16),
            *((_DWORD *)Context + 34),
            *((_DWORD *)Context + 35),
            *((OLECHAR **)Context + 19),
            *((const unsigned __int16 ***)Context + 10),
            v30,
            *((unsigned __int16 ***)Context + 13),
            *((_DWORD *)Context + 28),
            v31,
            Context[193]);
    v11 = DeleteScratchDirectory(*((const unsigned __int16 **)Context + 19));
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x559,
        (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v11);
    if ( v10 >= 0 )
    {
      if ( (unsigned int)dword_18008F0A0 > 5
        && (qword_18008F0B0 & 0x400000000000LL) != 0
        && (qword_18008F0B8 & 0x400000000000LL) == qword_18008F0B8 )
      {
        v32 = v10;
        *(_QWORD *)v33 = *v9;
        v29 = &v32;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          qword_18008F0B8,
          (__int64)byte_18008260D,
          (__int64)v12,
          (__int64)v13,
          v33);
      }
      v25 = EnterpriseModernAppManagement::DeleteProductIDKey(
              *v9,
              (const unsigned __int16 *)0xFFFFFFFF80000002LL,
              v12,
              v13);
      v6 = v25;
      v26 = retaddr;
      if ( v25 < 0 )
      {
        v27 = 1393;
LABEL_49:
        wil::details::in1diag3::_Log_Hr(
          v26,
          (void *)v27,
          (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v25);
        goto LABEL_50;
      }
    }
    else
    {
      if ( (unsigned int)dword_18008F0A0 > 5
        && (qword_18008F0B0 & 0x400000000000LL) != 0
        && (qword_18008F0B8 & 0x400000000000LL) == qword_18008F0B8 )
      {
        v32 = v10;
        *(_QWORD *)v33 = *v9;
        v29 = &v32;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          qword_18008F0B8,
          (__int64)word_1800825DA,
          (__int64)v12,
          (__int64)v13,
          v33);
      }
      EnterpriseModernAppManagement::tagProductInfo::tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v35);
      v14 = (int *)operator new(4u);
      if ( v14 )
      {
        v15 = v10;
        if ( v10 == -1051262696 )
          v15 = -2147024713;
        *v14 = v15;
      }
      else
      {
        v14 = 0;
      }
      v16 = v38;
      if ( v38 != v14 )
      {
        operator delete(v38);
        v16 = v14;
        v38 = v14;
      }
      if ( !v16 )
      {
        v17 = retaddr;
        v6 = -2147024882;
        v18 = 2147942414LL;
        v19 = 1381;
LABEL_26:
        wil::details::in1diag3::_Log_Hr(
          v17,
          (void *)v19,
          (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)v18);
        EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v35);
        goto LABEL_50;
      }
      v20 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoStringDeallocate(unsigned short *)>::CopyFromString(
              &v36,
              *v9);
      v6 = v20;
      v17 = retaddr;
      if ( v20 < 0 )
      {
        v19 = 1382;
LABEL_25:
        v18 = (unsigned int)v20;
        goto LABEL_26;
      }
      v21 = operator new(4u);
      v23 = v21;
      if ( v21 )
        *v21 = 2;
      else
        v23 = 0;
      v24 = v37;
      if ( v37 != v23 )
      {
        operator delete(v37);
        v24 = v23;
        v37 = v23;
      }
      if ( !v24 )
      {
        v17 = retaddr;
        v6 = -2147024882;
        v18 = 2147942414LL;
        v19 = 1385;
        goto LABEL_26;
      }
      v20 = EnterpriseModernAppManagement::AddProductInfo(
              (EnterpriseModernAppManagement *)v35,
              (const struct EnterpriseModernAppManagement::tagProductInfo *)0xFFFFFFFF80000002LL,
              v22);
      v6 = v20;
      v17 = retaddr;
      if ( v20 < 0 )
      {
        v19 = 1387;
        goto LABEL_25;
      }
      EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v35);
    }
    v25 = StringCchPrintfW(
            v41,
            0x105u,
            L"Reversed-Domain-Name:com.microsoft.mdm.%s.result",
            L"EnterpriseHostedAppInstall");
    v6 = v25;
    v26 = retaddr;
    if ( v25 >= 0 )
    {
      v25 = StringCchPrintfW(
              v40,
              0x105u,
              L"./Device/Vendor/MSFT/EnterpriseModernAppManagement/AppInstallation/%s/HostedInstall",
              *v9);
      v6 = v25;
      v26 = retaddr;
      if ( v25 >= 0 )
      {
        LODWORD(v28) = v10;
        v25 = EnterpriseModernAppManagement::SendOmaDmAlert(
                *((EnterpriseModernAppManagement **)Context + 22),
                v41,
                v40,
                0,
                v28,
                (int)v29);
        v6 = v25;
        v26 = retaddr;
        if ( v25 >= 0 )
          goto LABEL_54;
        v27 = 1406;
      }
      else
      {
        v27 = 1404;
      }
    }
    else
    {
      v27 = 1400;
    }
    goto LABEL_49;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x545,
    (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v5);
  v9 = (EnterpriseModernAppManagement **)(Context + 32);
LABEL_50:
  if ( (unsigned int)dword_18008F0A0 > 5
    && (qword_18008F0B0 & 0x400000000000LL) != 0
    && (qword_18008F0B8 & 0x400000000000LL) == qword_18008F0B8 )
  {
    v32 = v6;
    *(_QWORD *)v33 = *v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      qword_18008F0B8,
      (__int64)&byte_18008236F,
      v7,
      v8,
      v33);
  }
LABEL_54:
  CloseThreadpoolWork(Work);
  Common::AutoPtrDeallocate<ProvisionPackageParameters>((ProvisionPackageParameters *)Context);
  MsixPackage::Provisioning::Library::MsixProvisioningManager::~MsixProvisioningManager(v39);
}

```

## disassembly

```asm
0x1800213f0  push    rbp
0x1800213f2  push    rbx
0x1800213f3  push    rsi
0x1800213f4  push    rdi
0x1800213f5  push    r12
0x1800213f7  push    r13
0x1800213f9  push    r14
0x1800213fb  push    r15
0x1800213fd  lea     rbp, [rsp-5D8h]
0x180021405  sub     rsp, 6D8h
0x18002140c  mov     rax, cs:__security_cookie
0x180021413  xor     rax, rsp
0x180021416  mov     [rbp+610h+var_50], rax
0x18002141d  mov     r12, r8
0x180021420  mov     r14, rdx
0x180021423  test    r8, r8
0x180021426  jnz     short loc_18002142D
0x180021428  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002142d  test    r14, r14
0x180021430  jnz     short loc_180021437
0x180021432  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180021437  lea     rcx, [rbp+610h+var_560]; this
0x18002143e  call    ??0MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningManager::MsixProvisioningManager(void)
0x180021443  nop
0x180021444  mov     [rbp+610h+var_680], r14
0x180021448  lea     rcx, [rbp+610h+var_560]; this
0x18002144f  call    ?Initialize@MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningManager::Initialize(void)
0x180021454  mov     ebx, eax
0x180021456  mov     rcx, [rbp+618h]; this
0x18002145d  mov     r13, 400000000000h
0x180021467  test    eax, eax
0x180021469  jns     short loc_180021488
0x18002146b  mov     r9d, eax; char *
0x18002146e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180021475  mov     edx, 545h; void *
0x18002147a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002147f  lea     rdi, [r14+20h]
0x180021483  jmp     loc_1800217DF
0x180021488  lea     rdi, [r14+20h]
0x18002148c  mov     al, [r14+0C2h]
0x180021493  mov     [rsp+710h+var_698], al; bool
0x180021497  mov     al, [r14+0C1h]
0x18002149e  mov     [rsp+710h+var_6A0], al; bool
0x1800214a2  mov     al, [r14+0C0h]
0x1800214a9  mov     byte ptr [rsp+710h+var_6A8], al; MsixPackage::Provisioning::Library::MsixProvisioningManager *
0x1800214ad  mov     eax, [r14+70h]
0x1800214b1  mov     [rsp+710h+var_6B0], eax; unsigned int
0x1800214b5  mov     rax, [r14+68h]
0x1800214b9  mov     [rsp+710h+var_6B8], rax; unsigned __int16 **
0x1800214be  mov     eax, [r14+58h]
0x1800214c2  mov     dword ptr [rsp+710h+var_6C0], eax; char *
0x1800214c6  mov     rax, [r14+50h]
0x1800214ca  mov     [rsp+710h+var_6C8], rax; unsigned __int16 **
0x1800214cf  mov     rax, [r14+98h]
0x1800214d6  mov     [rsp+710h+var_6D0], rax; unsigned __int16 *
0x1800214db  mov     eax, [r14+8Ch]
0x1800214e2  mov     [rsp+710h+var_6D8], eax; int
0x1800214e6  mov     eax, [r14+88h]
0x1800214ed  mov     [rsp+710h+var_6E0], eax; unsigned int
0x1800214f1  mov     rax, [r14+80h]
0x1800214f8  mov     [rsp+710h+var_6E8], rax; unsigned __int16 **
0x1800214fd  mov     eax, [r14+40h]
0x180021501  mov     dword ptr [rsp+710h+var_6F0], eax; int
0x180021505  mov     r9, [r14+38h]; unsigned __int16 **
0x180021509  mov     r8, [rdi]; unsigned __int16 *
0x18002150c  mov     rdx, [r14+8]; unsigned __int16 *
0x180021510  lea     rcx, [rbp+610h+var_560]; this
0x180021517  call    ?AddAllUserAppxPackageForCSP@MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAAJPEBG0PEAPEBGI1IH01I1I_N22@Z; MsixPackage::Provisioning::Library::MsixProvisioningManager::AddAllUserAppxPackageForCSP(ushort const *,ushort const *,ushort const * *,uint,ushort const * *,uint,int,ushort const *,ushort const * *,uint,ushort const * *,uint,bool,bool,bool)
0x18002151c  mov     r15d, eax
0x18002151f  mov     rcx, [r14+98h]; unsigned __int16 *
0x180021526  call    ?DeleteScratchDirectory@@YAJPEBG@Z; DeleteScratchDirectory(ushort const *)
0x18002152b  mov     rcx, [rbp+618h]; this
0x180021532  lea     rsi, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180021539  test    eax, eax
0x18002153b  jns     short loc_18002154D
0x18002153d  mov     r9d, eax; char *
0x180021540  mov     r8, rsi; unsigned int
0x180021543  mov     edx, 559h; void *
0x180021548  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002154d  mov     eax, cs:dword_18008F0A0
0x180021553  test    r15d, r15d
0x180021556  jns     loc_1800216FE
0x18002155c  cmp     eax, 5
0x18002155f  jbe     short loc_1800215A8
0x180021561  mov     rcx, cs:qword_18008F0B8
0x180021568  mov     rax, cs:qword_18008F0B0
0x18002156f  test    r13, rax
0x180021572  jz      short loc_1800215A8
0x180021574  mov     rax, rcx
0x180021577  and     rax, r13
0x18002157a  cmp     rax, rcx
0x18002157d  jnz     short loc_1800215A8
0x18002157f  mov     [rbp+610h+var_690], r15d
0x180021583  mov     rax, [rdi]
0x180021586  mov     qword ptr [rbp+610h+var_688], rax
0x18002158a  lea     rax, [rbp+610h+var_690]
0x18002158e  mov     [rsp+710h+var_6E8], rax; int
0x180021593  lea     rax, [rbp+610h+var_688]
0x180021597  mov     [rsp+710h+var_6F0], rax; int
0x18002159c  lea     rdx, word_1800825DA
0x1800215a3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800215a8  lea     rcx, [rbp+610h+var_670]; this
0x1800215ac  call    ??0tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::tagProductInfo(void)
0x1800215b1  nop
0x1800215b2  mov     ecx, 4; Size
0x1800215b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800215bc  mov     rbx, rax
0x1800215bf  test    rax, rax
0x1800215c2  jz      short loc_1800215DA
0x1800215c4  mov     ecx, r15d
0x1800215c7  mov     eax, 800700B7h
0x1800215cc  cmp     r15d, 0C1570118h
0x1800215d3  cmovz   ecx, eax
0x1800215d6  mov     [rbx], ecx
0x1800215d8  jmp     short loc_1800215DC
0x1800215da  xor     ebx, ebx
0x1800215dc  mov     rax, [rbp+610h+var_5C8]
0x1800215e0  cmp     rax, rbx
0x1800215e3  jz      short loc_1800215F5
0x1800215e5  mov     rcx, rax
0x1800215e8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800215ee  mov     rax, rbx
0x1800215f1  mov     [rbp+610h+var_5C8], rbx
0x1800215f5  test    rax, rax
0x1800215f8  jnz     short loc_180021610
0x1800215fa  mov     rcx, [rbp+618h]
0x180021601  mov     ebx, 8007000Eh
0x180021606  mov     r9d, ebx
0x180021609  mov     edx, 565h
0x18002160e  jmp     short loc_180021631
0x180021610  mov     rdx, [rdi]
0x180021613  lea     rcx, [rbp+610h+var_668]
0x180021617  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoStringAllocateAndCopy(ushort const *,uint),&Common::AutoStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x18002161c  mov     ebx, eax
0x18002161e  mov     rcx, [rbp+618h]; this
0x180021625  test    eax, eax
0x180021627  jns     short loc_180021648
0x180021629  mov     edx, 566h; void *
0x18002162e  mov     r9d, eax; char *
0x180021631  mov     r8, rsi; unsigned int
0x180021634  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021639  nop
0x18002163a  lea     rcx, [rbp+610h+var_670]; this
0x18002163e  call    ??1tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo(void)
0x180021643  jmp     loc_1800217DF
0x180021648  mov     ecx, 4; Size
0x18002164d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021652  mov     rbx, rax
0x180021655  test    rax, rax
0x180021658  jz      short loc_180021662
0x18002165a  mov     dword ptr [rax], 2
0x180021660  jmp     short loc_180021664
0x180021662  xor     ebx, ebx
0x180021664  mov     rax, [rbp+610h+var_600]
0x180021668  cmp     rax, rbx
0x18002166b  jz      short loc_18002167D
0x18002166d  mov     rcx, rax
0x180021670  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021676  mov     rax, rbx
0x180021679  mov     [rbp+610h+var_600], rbx
0x18002167d  test    rax, rax
0x180021680  jnz     short loc_180021698
0x180021682  mov     rcx, [rbp+618h]
0x180021689  mov     ebx, 8007000Eh
0x18002168e  mov     r9d, ebx
0x180021691  mov     edx, 569h
0x180021696  jmp     short loc_180021631
0x180021698  mov     rdx, 0FFFFFFFF80000002h; struct EnterpriseModernAppManagement::tagProductInfo *
0x18002169f  lea     rcx, [rbp+610h+var_670]; this
0x1800216a3  call    ?AddProductInfo@EnterpriseModernAppManagement@@YAJAEBUtagProductInfo@1@PEAUHKEY__@@@Z; EnterpriseModernAppManagement::AddProductInfo(EnterpriseModernAppManagement::tagProductInfo const &,HKEY__ *)
0x1800216a8  mov     ebx, eax
0x1800216aa  mov     rcx, [rbp+618h]
0x1800216b1  test    eax, eax
0x1800216b3  jns     short loc_1800216BF
0x1800216b5  mov     edx, 56Bh
0x1800216ba  jmp     loc_18002162E
0x1800216bf  lea     rcx, [rbp+610h+var_670]; this
0x1800216c3  call    ??1tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo(void)
0x1800216c8  lea     r9, ?c_HostedAppInstall@EnterpriseModernAppManagement@@3QBGB; "EnterpriseHostedAppInstall"
0x1800216cf  lea     r8, ?c_AlertTypeFormat@EnterpriseModernAppManagement@@3QBGB; "Reversed-Domain-Name:com.microsoft.mdm."...
0x1800216d6  mov     edx, 105h; unsigned __int64
0x1800216db  lea     rcx, [rbp+610h+var_260]; unsigned __int16 *
0x1800216e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800216e7  mov     ebx, eax
0x1800216e9  mov     rcx, [rbp+618h]
0x1800216f0  test    eax, eax
0x1800216f2  jns     short loc_180021771
0x1800216f4  mov     edx, 578h
0x1800216f9  jmp     loc_1800217D4
0x1800216fe  cmp     eax, 5
0x180021701  jbe     short loc_18002174A
0x180021703  mov     rcx, cs:qword_18008F0B8
0x18002170a  mov     rax, cs:qword_18008F0B0
0x180021711  test    r13, rax
0x180021714  jz      short loc_18002174A
0x180021716  mov     rax, rcx
0x180021719  and     rax, r13
0x18002171c  cmp     rax, rcx
0x18002171f  jnz     short loc_18002174A
0x180021721  mov     [rbp+610h+var_690], r15d
0x180021725  mov     rax, [rdi]
0x180021728  mov     qword ptr [rbp+610h+var_688], rax
0x18002172c  lea     rax, [rbp+610h+var_690]
0x180021730  mov     [rsp+710h+var_6E8], rax
0x180021735  lea     rax, [rbp+610h+var_688]
0x180021739  mov     [rsp+710h+var_6F0], rax
0x18002173e  lea     rdx, byte_18008260D
0x180021745  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002174a  mov     rdx, 0FFFFFFFF80000002h; unsigned __int16 *
0x180021751  mov     rcx, [rdi]; this
0x180021754  call    ?DeleteProductIDKey@EnterpriseModernAppManagement@@YAJPEBGPEAUHKEY__@@@Z; EnterpriseModernAppManagement::DeleteProductIDKey(ushort const *,HKEY__ *)
0x180021759  mov     ebx, eax
0x18002175b  mov     rcx, [rbp+618h]
0x180021762  test    eax, eax
0x180021764  jns     loc_1800216C8
0x18002176a  mov     edx, 571h
0x18002176f  jmp     short loc_1800217D4
0x180021771  mov     r9, [rdi]
0x180021774  lea     r8, ?c_HostedAppInstallAlertSourceDeviceFormat@EnterpriseModernAppManagement@@3QBGB; "./Device/Vendor/MSFT/EnterpriseModernAp"...
0x18002177b  mov     edx, 105h; unsigned __int64
0x180021780  lea     rcx, [rbp+610h+var_470]; unsigned __int16 *
0x180021787  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002178c  mov     ebx, eax
0x18002178e  mov     rcx, [rbp+618h]
0x180021795  test    eax, eax
0x180021797  jns     short loc_1800217A0
0x180021799  mov     edx, 57Ch
0x18002179e  jmp     short loc_1800217D4
0x1800217a0  mov     dword ptr [rsp+710h+var_6F0], r15d; int
0x1800217a5  xor     r9d, r9d; unsigned __int16 *
0x1800217a8  lea     r8, [rbp+610h+var_470]; unsigned __int16 *
0x1800217af  lea     rdx, [rbp+610h+var_260]; unsigned __int16 *
0x1800217b6  mov     rcx, [r14+0B0h]; this
0x1800217bd  call    ?SendOmaDmAlert@EnterpriseModernAppManagement@@YAJPEBG000J@Z; EnterpriseModernAppManagement::SendOmaDmAlert(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x1800217c2  mov     ebx, eax
0x1800217c4  mov     rcx, [rbp+618h]; this
0x1800217cb  test    eax, eax
0x1800217cd  jns     short loc_180021830
0x1800217cf  mov     edx, 57Eh; void *
0x1800217d4  mov     r9d, eax; char *
0x1800217d7  mov     r8, rsi; unsigned int
0x1800217da  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800217df  mov     eax, cs:dword_18008F0A0
0x1800217e5  cmp     eax, 5
0x1800217e8  jbe     short loc_180021830
0x1800217ea  mov     rcx, cs:qword_18008F0B8
0x1800217f1  mov     rax, cs:qword_18008F0B0
0x1800217f8  test    r13, rax
0x1800217fb  jz      short loc_180021830
0x1800217fd  mov     rax, rcx
0x180021800  and     rax, r13
0x180021803  cmp     rax, rcx
0x180021806  jnz     short loc_180021830
0x180021808  mov     [rbp+610h+var_690], ebx
0x18002180b  mov     rax, [rdi]
0x18002180e  mov     qword ptr [rbp+610h+var_688], rax
0x180021812  lea     rax, [rbp+610h+var_690]
0x180021816  mov     [rsp+710h+var_6E8], rax
0x18002181b  lea     rax, [rbp+610h+var_688]
0x18002181f  mov     [rsp+710h+var_6F0], rax
0x180021824  lea     rdx, byte_18008236F
0x18002182b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180021830  mov     rcx, r12; pwk
0x180021833  call    cs:__imp_CloseThreadpoolWork
0x180021839  nop
0x18002183a  mov     rcx, r14
0x18002183d  call    ??$AutoPtrDeallocate@VProvisionPackageParameters@@@Common@@YAXPEAVProvisionPackageParameters@@@Z; Common::AutoPtrDeallocate<ProvisionPackageParameters>(ProvisionPackageParameters *)
0x180021842  nop
0x180021843  lea     rcx, [rbp+610h+var_560]; this
0x18002184a  call    ??1MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningManager::~MsixProvisioningManager(void)
0x18002184f  mov     rcx, [rbp+610h+var_50]
0x180021856  xor     rcx, rsp; StackCookie
0x180021859  call    __security_check_cookie
0x18002185e  add     rsp, 6D8h
0x180021865  pop     r15
0x180021867  pop     r14
0x180021869  pop     r13
0x18002186b  pop     r12
0x18002186d  pop     rdi
0x18002186e  pop     rsi
0x18002186f  pop     rbx
0x180021870  pop     rbp
0x180021871  retn
```
