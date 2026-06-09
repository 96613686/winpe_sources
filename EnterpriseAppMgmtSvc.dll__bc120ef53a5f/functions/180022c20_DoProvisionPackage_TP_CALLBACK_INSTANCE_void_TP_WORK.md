# DoProvisionPackage(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180022c20`
- end: `0x1800230b5`
- name: `?DoProvisionPackage@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1173`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180001444`
- `0x180001c24`
- `0x180005ff4`
- `0x18001d65c`
- `0x18001dc00`
- `0x18001e9fc`
- `0x18001f048`
- `0x180020bdc`
- `0x180021514`
- `0x180022c20`
- `0x18002be98`
- `0x18002c594`
- `0x180030780`
- `0x18003442c`
- `0x1800352d8`
- `0x1800356d0`
- `0x180036618`
- `0x18003ac38`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180022e18`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022ea6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022e18`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022ea6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002306f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002306f`

## string_xrefs

- `0x180022fb0`: `./Device/Vendor/MSFT/EnterpriseModernAppManagement/AppInstallation/%s/HostedInstall`
- `0x180022f0b`: `Reversed-Domain-Name:com.microsoft.mdm.%s.result`
- `0x180022f04`: `EnterpriseHostedAppInstall`
- `0x180022c9e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180022d62`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DoProvisionPackage(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  int v5; // eax
  int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  EnterpriseModernAppManagement **v9; // rdi
  int v10; // r15d
  int v11; // eax
  HKEY v12; // r8
  int v13; // r9d
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
  int v28; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+28h] [rbp-D8h]
  char *v31; // [rsp+50h] [rbp-B0h]
  MsixPackage::Provisioning::Library::MsixProvisioningManager *v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+80h] [rbp-80h] BYREF
  int v34[2]; // [rsp+88h] [rbp-78h] BYREF
  char *v35; // [rsp+90h] [rbp-70h]
  char v36[8]; // [rsp+A0h] [rbp-60h] BYREF
  char v37[104]; // [rsp+A8h] [rbp-58h] BYREF
  void *v38; // [rsp+110h] [rbp+10h]
  int *v39; // [rsp+148h] [rbp+48h]
  _BYTE v40[240]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v41[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v42[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+618h]

  if ( !Work )
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance);
  if ( !Context )
    MicrosoftTelemetryAssertTriggeredNoArgs(Instance);
  MsixPackage::Provisioning::Library::MsixProvisioningManager::MsixProvisioningManager((MsixPackage::Provisioning::Library::MsixProvisioningManager *)v40);
  v35 = Context;
  v5 = MsixPackage::Provisioning::Library::MsixProvisioningManager::Initialize((MsixPackage::Provisioning::Library::MsixProvisioningManager *)v40);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v9 = (EnterpriseModernAppManagement **)(Context + 32);
    LOBYTE(v32) = Context[192];
    LODWORD(v31) = *((_DWORD *)Context + 22);
    v10 = MsixPackage::Provisioning::Library::MsixProvisioningManager::AddAllUserAppxPackageForCSP(
            (MsixPackage::Provisioning::Library::MsixProvisioningManager *)v40,
            *((OLECHAR **)Context + 1),
            *((unsigned __int16 **)Context + 4),
            *((unsigned __int16 ***)Context + 7),
            *((_DWORD *)Context + 16),
            *((const unsigned __int16 ***)Context + 16),
            *((_DWORD *)Context + 34),
            *((_DWORD *)Context + 35),
            *((OLECHAR **)Context + 19),
            *((const unsigned __int16 ***)Context + 10),
            v31,
            *((unsigned __int16 ***)Context + 13),
            *((_DWORD *)Context + 28),
            v32,
            Context[193]);
    v11 = DeleteScratchDirectory(*((const unsigned __int16 **)Context + 19));
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x559,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v11,
        (int)v29);
    if ( v10 >= 0 )
    {
      if ( (unsigned int)dword_1800950A0 > 5
        && (qword_1800950B0 & 0x400000000000LL) != 0
        && (qword_1800950B8 & 0x400000000000LL) == qword_1800950B8 )
      {
        v33 = v10;
        *(_QWORD *)v34 = *v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          qword_1800950B8,
          (unsigned int)byte_180088615,
          (_DWORD)v12,
          v13,
          (__int64)v34,
          (__int64)&v33);
      }
      v25 = EnterpriseModernAppManagement::DeleteProductIDKey(*v9, (const unsigned __int16 *)0xFFFFFFFF80000002LL, v12);
      v6 = v25;
      v26 = retaddr;
      if ( v25 < 0 )
      {
        v27 = 1393;
LABEL_49:
        wil::details::in1diag3::_Log_Hr(
          v26,
          (void *)v27,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v25,
          (int)v29);
        goto LABEL_50;
      }
    }
    else
    {
      if ( (unsigned int)dword_1800950A0 > 5
        && (qword_1800950B0 & 0x400000000000LL) != 0
        && (qword_1800950B8 & 0x400000000000LL) == qword_1800950B8 )
      {
        v33 = v10;
        *(_QWORD *)v34 = *v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          qword_1800950B8,
          (unsigned int)word_1800885E2,
          (_DWORD)v12,
          v13,
          (__int64)v34,
          (__int64)&v33);
      }
      EnterpriseModernAppManagement::tagProductInfo::tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v36);
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
      v16 = v39;
      if ( v39 != v14 )
      {
        operator delete(v39);
        v16 = v14;
        v39 = v14;
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
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)v18,
          (int)v29);
        EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v36);
        goto LABEL_50;
      }
      v20 = Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoStringAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoStringDeallocate(unsigned short *)>::CopyFromString(
              v37,
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
      v24 = v38;
      if ( v38 != v23 )
      {
        operator delete(v38);
        v24 = v23;
        v38 = v23;
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
              (EnterpriseModernAppManagement *)v36,
              (const struct EnterpriseModernAppManagement::tagProductInfo *)0xFFFFFFFF80000002LL,
              v22);
      v6 = v20;
      v17 = retaddr;
      if ( v20 < 0 )
      {
        v19 = 1387;
        goto LABEL_25;
      }
      EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo((EnterpriseModernAppManagement::tagProductInfo *)v36);
    }
    v25 = StringCchPrintfW(
            v42,
            0x105u,
            L"Reversed-Domain-Name:com.microsoft.mdm.%s.result",
            L"EnterpriseHostedAppInstall");
    v6 = v25;
    v26 = retaddr;
    if ( v25 >= 0 )
    {
      v25 = StringCchPrintfW(
              v41,
              0x105u,
              L"./Device/Vendor/MSFT/EnterpriseModernAppManagement/AppInstallation/%s/HostedInstall",
              *v9);
      v6 = v25;
      v26 = retaddr;
      if ( v25 >= 0 )
      {
        LODWORD(v29) = v10;
        v25 = EnterpriseModernAppManagement::SendOmaDmAlert(
                *((EnterpriseModernAppManagement **)Context + 22),
                v42,
                v41,
                0,
                v29,
                v30);
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
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)(unsigned int)v5,
    v28);
  v9 = (EnterpriseModernAppManagement **)(Context + 32);
LABEL_50:
  if ( (unsigned int)dword_1800950A0 > 5
    && (qword_1800950B0 & 0x400000000000LL) != 0
    && (qword_1800950B8 & 0x400000000000LL) == qword_1800950B8 )
  {
    v33 = v6;
    *(_QWORD *)v34 = *v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      qword_1800950B8,
      (unsigned int)&byte_180088377,
      v7,
      v8,
      (__int64)v34,
      (__int64)&v33);
  }
LABEL_54:
  CloseThreadpoolWork(Work);
  Common::AutoPtrDeallocate<ProvisionPackageParameters>(Context);
  MsixPackage::Provisioning::Library::MsixProvisioningManager::~MsixProvisioningManager((MsixPackage::Provisioning::Library::MsixProvisioningManager *)v40);
}

```

## disassembly

```asm
0x180022c20  push    rbp
0x180022c22  push    rbx
0x180022c23  push    rsi
0x180022c24  push    rdi
0x180022c25  push    r12
0x180022c27  push    r13
0x180022c29  push    r14
0x180022c2b  push    r15
0x180022c2d  lea     rbp, [rsp-5D8h]
0x180022c35  sub     rsp, 6D8h
0x180022c3c  mov     rax, cs:__security_cookie
0x180022c43  xor     rax, rsp
0x180022c46  mov     [rbp+610h+var_50], rax
0x180022c4d  mov     r12, r8
0x180022c50  mov     r14, rdx
0x180022c53  test    r8, r8
0x180022c56  jnz     short loc_180022C5D
0x180022c58  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022c5d  test    r14, r14
0x180022c60  jnz     short loc_180022C67
0x180022c62  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022c67  lea     rcx, [rbp+610h+var_560]; this
0x180022c6e  call    ??0MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningManager::MsixProvisioningManager(void)
0x180022c73  nop
0x180022c74  mov     [rbp+610h+var_680], r14
0x180022c78  lea     rcx, [rbp+610h+var_560]; this
0x180022c7f  call    ?Initialize@MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningManager::Initialize(void)
0x180022c84  mov     ebx, eax
0x180022c86  mov     rcx, [rbp+618h]; this
0x180022c8d  mov     r13, 400000000000h
0x180022c97  test    eax, eax
0x180022c99  jns     short loc_180022CB8
0x180022c9b  mov     r9d, eax; char *
0x180022c9e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180022ca5  mov     edx, 545h; void *
0x180022caa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022caf  lea     rdi, [r14+20h]
0x180022cb3  jmp     loc_18002301B
0x180022cb8  lea     rdi, [r14+20h]
0x180022cbc  mov     al, [r14+0C2h]
0x180022cc3  mov     [rsp+710h+var_698], al; bool
0x180022cc7  mov     al, [r14+0C1h]
0x180022cce  mov     [rsp+710h+var_6A0], al; bool
0x180022cd2  mov     al, [r14+0C0h]
0x180022cd9  mov     byte ptr [rsp+710h+var_6A8], al; MsixPackage::Provisioning::Library::MsixProvisioningManager *
0x180022cdd  mov     eax, [r14+70h]
0x180022ce1  mov     [rsp+710h+var_6B0], eax; unsigned int
0x180022ce5  mov     rax, [r14+68h]
0x180022ce9  mov     [rsp+710h+var_6B8], rax; unsigned __int16 **
0x180022cee  mov     eax, [r14+58h]
0x180022cf2  mov     dword ptr [rsp+710h+var_6C0], eax; char *
0x180022cf6  mov     rax, [r14+50h]
0x180022cfa  mov     [rsp+710h+var_6C8], rax; unsigned __int16 **
0x180022cff  mov     rax, [r14+98h]
0x180022d06  mov     [rsp+710h+var_6D0], rax; unsigned __int16 *
0x180022d0b  mov     eax, [r14+8Ch]
0x180022d12  mov     [rsp+710h+var_6D8], eax; int
0x180022d16  mov     eax, [r14+88h]
0x180022d1d  mov     [rsp+710h+var_6E0], eax; unsigned int
0x180022d21  mov     rax, [r14+80h]
0x180022d28  mov     [rsp+710h+var_6E8], rax; unsigned __int16 **
0x180022d2d  mov     eax, [r14+40h]
0x180022d31  mov     dword ptr [rsp+710h+var_6F0], eax; int
0x180022d35  mov     r9, [r14+38h]; unsigned __int16 **
0x180022d39  mov     r8, [rdi]; unsigned __int16 *
0x180022d3c  mov     rdx, [r14+8]; unsigned __int16 *
0x180022d40  lea     rcx, [rbp+610h+var_560]; this
0x180022d47  call    ?AddAllUserAppxPackageForCSP@MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAAJPEBG0PEAPEBGI1IH01I1I_N22@Z; MsixPackage::Provisioning::Library::MsixProvisioningManager::AddAllUserAppxPackageForCSP(ushort const *,ushort const *,ushort const * *,uint,ushort const * *,uint,int,ushort const *,ushort const * *,uint,ushort const * *,uint,bool,bool,bool)
0x180022d4c  mov     r15d, eax
0x180022d4f  mov     rcx, [r14+98h]; unsigned __int16 *
0x180022d56  call    ?DeleteScratchDirectory@@YAJPEBG@Z; DeleteScratchDirectory(ushort const *)
0x180022d5b  mov     rcx, [rbp+618h]; this
0x180022d62  lea     rsi, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180022d69  test    eax, eax
0x180022d6b  jns     short loc_180022D7D
0x180022d6d  mov     r9d, eax; char *
0x180022d70  mov     r8, rsi; unsigned int
0x180022d73  mov     edx, 559h; void *
0x180022d78  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022d7d  mov     eax, cs:dword_1800950A0
0x180022d83  test    r15d, r15d
0x180022d86  jns     loc_180022F3A
0x180022d8c  cmp     eax, 5
0x180022d8f  jbe     short loc_180022DD8
0x180022d91  mov     rcx, cs:qword_1800950B8
0x180022d98  mov     rax, cs:qword_1800950B0
0x180022d9f  test    r13, rax
0x180022da2  jz      short loc_180022DD8
0x180022da4  mov     rax, rcx
0x180022da7  and     rax, r13
0x180022daa  cmp     rax, rcx
0x180022dad  jnz     short loc_180022DD8
0x180022daf  mov     [rbp+610h+var_690], r15d
0x180022db3  mov     rax, [rdi]
0x180022db6  mov     qword ptr [rbp+610h+var_688], rax
0x180022dba  lea     rax, [rbp+610h+var_690]
0x180022dbe  mov     [rsp+710h+var_6E8], rax; int
0x180022dc3  lea     rax, [rbp+610h+var_688]
0x180022dc7  mov     [rsp+710h+var_6F0], rax; int
0x180022dcc  lea     rdx, word_1800885E2
0x180022dd3  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180022dd8  lea     rcx, [rbp+610h+var_670]; this
0x180022ddc  call    ??0tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::tagProductInfo(void)
0x180022de1  nop
0x180022de2  mov     ecx, 4; Size
0x180022de7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022dec  mov     rbx, rax
0x180022def  test    rax, rax
0x180022df2  jz      short loc_180022E0A
0x180022df4  mov     ecx, r15d
0x180022df7  mov     eax, 800700B7h
0x180022dfc  cmp     r15d, 0C1570118h
0x180022e03  cmovz   ecx, eax
0x180022e06  mov     [rbx], ecx
0x180022e08  jmp     short loc_180022E0C
0x180022e0a  xor     ebx, ebx
0x180022e0c  mov     rax, [rbp+610h+var_5C8]
0x180022e10  cmp     rax, rbx
0x180022e13  jz      short loc_180022E2B
0x180022e15  mov     rcx, rax
0x180022e18  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022e1f  nop     dword ptr [rax+rax+00h]
0x180022e24  mov     rax, rbx
0x180022e27  mov     [rbp+610h+var_5C8], rbx
0x180022e2b  test    rax, rax
0x180022e2e  jnz     short loc_180022E46
0x180022e30  mov     rcx, [rbp+618h]
0x180022e37  mov     ebx, 8007000Eh
0x180022e3c  mov     r9d, ebx
0x180022e3f  mov     edx, 565h
0x180022e44  jmp     short loc_180022E67
0x180022e46  mov     rdx, [rdi]
0x180022e49  lea     rcx, [rbp+610h+var_668]
0x180022e4d  call    ?CopyFromString@?$AutoStringWithAllocator@G$1?AutoStringAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoStringDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z; Common::AutoStringWithAllocator<ushort,&Common::AutoStringAllocateAndCopy(ushort const *,uint),&Common::AutoStringDeallocate(ushort *)>::CopyFromString(ushort const *)
0x180022e52  mov     ebx, eax
0x180022e54  mov     rcx, [rbp+618h]; this
0x180022e5b  test    eax, eax
0x180022e5d  jns     short loc_180022E7E
0x180022e5f  mov     edx, 566h; void *
0x180022e64  mov     r9d, eax; char *
0x180022e67  mov     r8, rsi; unsigned int
0x180022e6a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022e6f  nop
0x180022e70  lea     rcx, [rbp+610h+var_670]; this
0x180022e74  call    ??1tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo(void)
0x180022e79  jmp     loc_18002301B
0x180022e7e  mov     ecx, 4; Size
0x180022e83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022e88  mov     rbx, rax
0x180022e8b  test    rax, rax
0x180022e8e  jz      short loc_180022E98
0x180022e90  mov     dword ptr [rax], 2
0x180022e96  jmp     short loc_180022E9A
0x180022e98  xor     ebx, ebx
0x180022e9a  mov     rax, [rbp+610h+var_600]
0x180022e9e  cmp     rax, rbx
0x180022ea1  jz      short loc_180022EB9
0x180022ea3  mov     rcx, rax
0x180022ea6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022ead  nop     dword ptr [rax+rax+00h]
0x180022eb2  mov     rax, rbx
0x180022eb5  mov     [rbp+610h+var_600], rbx
0x180022eb9  test    rax, rax
0x180022ebc  jnz     short loc_180022ED4
0x180022ebe  mov     rcx, [rbp+618h]
0x180022ec5  mov     ebx, 8007000Eh
0x180022eca  mov     r9d, ebx
0x180022ecd  mov     edx, 569h
0x180022ed2  jmp     short loc_180022E67
0x180022ed4  mov     rdx, 0FFFFFFFF80000002h; struct EnterpriseModernAppManagement::tagProductInfo *
0x180022edb  lea     rcx, [rbp+610h+var_670]; this
0x180022edf  call    ?AddProductInfo@EnterpriseModernAppManagement@@YAJAEBUtagProductInfo@1@PEAUHKEY__@@@Z; EnterpriseModernAppManagement::AddProductInfo(EnterpriseModernAppManagement::tagProductInfo const &,HKEY__ *)
0x180022ee4  mov     ebx, eax
0x180022ee6  mov     rcx, [rbp+618h]
0x180022eed  test    eax, eax
0x180022eef  jns     short loc_180022EFB
0x180022ef1  mov     edx, 56Bh
0x180022ef6  jmp     loc_180022E64
0x180022efb  lea     rcx, [rbp+610h+var_670]; this
0x180022eff  call    ??1tagProductInfo@EnterpriseModernAppManagement@@QEAA@XZ; EnterpriseModernAppManagement::tagProductInfo::~tagProductInfo(void)
0x180022f04  lea     r9, ?c_HostedAppInstall@EnterpriseModernAppManagement@@3QBGB; "EnterpriseHostedAppInstall"
0x180022f0b  lea     r8, ?c_AlertTypeFormat@EnterpriseModernAppManagement@@3QBGB; "Reversed-Domain-Name:com.microsoft.mdm."...
0x180022f12  mov     edx, 105h; unsigned __int64
0x180022f17  lea     rcx, [rbp+610h+var_260]; unsigned __int16 *
0x180022f1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022f23  mov     ebx, eax
0x180022f25  mov     rcx, [rbp+618h]
0x180022f2c  test    eax, eax
0x180022f2e  jns     short loc_180022FAD
0x180022f30  mov     edx, 578h
0x180022f35  jmp     loc_180023010
0x180022f3a  cmp     eax, 5
0x180022f3d  jbe     short loc_180022F86
0x180022f3f  mov     rcx, cs:qword_1800950B8
0x180022f46  mov     rax, cs:qword_1800950B0
0x180022f4d  test    r13, rax
0x180022f50  jz      short loc_180022F86
0x180022f52  mov     rax, rcx
0x180022f55  and     rax, r13
0x180022f58  cmp     rax, rcx
0x180022f5b  jnz     short loc_180022F86
0x180022f5d  mov     [rbp+610h+var_690], r15d
0x180022f61  mov     rax, [rdi]
0x180022f64  mov     qword ptr [rbp+610h+var_688], rax
0x180022f68  lea     rax, [rbp+610h+var_690]
0x180022f6c  mov     [rsp+710h+var_6E8], rax
0x180022f71  lea     rax, [rbp+610h+var_688]
0x180022f75  mov     [rsp+710h+var_6F0], rax
0x180022f7a  lea     rdx, byte_180088615
0x180022f81  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180022f86  mov     rdx, 0FFFFFFFF80000002h; unsigned __int16 *
0x180022f8d  mov     rcx, [rdi]; this
0x180022f90  call    ?DeleteProductIDKey@EnterpriseModernAppManagement@@YAJPEBGPEAUHKEY__@@@Z; EnterpriseModernAppManagement::DeleteProductIDKey(ushort const *,HKEY__ *)
0x180022f95  mov     ebx, eax
0x180022f97  mov     rcx, [rbp+618h]
0x180022f9e  test    eax, eax
0x180022fa0  jns     loc_180022F04
0x180022fa6  mov     edx, 571h
0x180022fab  jmp     short loc_180023010
0x180022fad  mov     r9, [rdi]
0x180022fb0  lea     r8, ?c_HostedAppInstallAlertSourceDeviceFormat@EnterpriseModernAppManagement@@3QBGB; "./Device/Vendor/MSFT/EnterpriseModernAp"...
0x180022fb7  mov     edx, 105h; unsigned __int64
0x180022fbc  lea     rcx, [rbp+610h+var_470]; unsigned __int16 *
0x180022fc3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022fc8  mov     ebx, eax
0x180022fca  mov     rcx, [rbp+618h]
0x180022fd1  test    eax, eax
0x180022fd3  jns     short loc_180022FDC
0x180022fd5  mov     edx, 57Ch
0x180022fda  jmp     short loc_180023010
0x180022fdc  mov     dword ptr [rsp+710h+var_6F0], r15d; int
0x180022fe1  xor     r9d, r9d; unsigned __int16 *
0x180022fe4  lea     r8, [rbp+610h+var_470]; unsigned __int16 *
0x180022feb  lea     rdx, [rbp+610h+var_260]; unsigned __int16 *
0x180022ff2  mov     rcx, [r14+0B0h]; this
0x180022ff9  call    ?SendOmaDmAlert@EnterpriseModernAppManagement@@YAJPEBG000J@Z; EnterpriseModernAppManagement::SendOmaDmAlert(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x180022ffe  mov     ebx, eax
0x180023000  mov     rcx, [rbp+618h]; this
0x180023007  test    eax, eax
0x180023009  jns     short loc_18002306C
0x18002300b  mov     edx, 57Eh; void *
0x180023010  mov     r9d, eax; char *
0x180023013  mov     r8, rsi; unsigned int
0x180023016  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002301b  mov     eax, cs:dword_1800950A0
0x180023021  cmp     eax, 5
0x180023024  jbe     short loc_18002306C
0x180023026  mov     rcx, cs:qword_1800950B8
0x18002302d  mov     rax, cs:qword_1800950B0
0x180023034  test    r13, rax
0x180023037  jz      short loc_18002306C
0x180023039  mov     rax, rcx
0x18002303c  and     rax, r13
0x18002303f  cmp     rax, rcx
0x180023042  jnz     short loc_18002306C
0x180023044  mov     [rbp+610h+var_690], ebx
0x180023047  mov     rax, [rdi]
0x18002304a  mov     qword ptr [rbp+610h+var_688], rax
0x18002304e  lea     rax, [rbp+610h+var_690]
0x180023052  mov     [rsp+710h+var_6E8], rax
0x180023057  lea     rax, [rbp+610h+var_688]
0x18002305b  mov     [rsp+710h+var_6F0], rax
0x180023060  lea     rdx, byte_180088377
0x180023067  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002306c  mov     rcx, r12; pwk
0x18002306f  call    cs:__imp_CloseThreadpoolWork
0x180023076  nop     dword ptr [rax+rax+00h]
0x18002307b  nop
0x18002307c  mov     rcx, r14
0x18002307f  call    ??$AutoPtrDeallocate@VProvisionPackageParameters@@@Common@@YAXPEAVProvisionPackageParameters@@@Z; Common::AutoPtrDeallocate<ProvisionPackageParameters>(ProvisionPackageParameters *)
0x180023084  nop
0x180023085  lea     rcx, [rbp+610h+var_560]; this
0x18002308c  call    ??1MsixProvisioningManager@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningManager::~MsixProvisioningManager(void)
0x180023091  mov     rcx, [rbp+610h+var_50]
0x180023098  xor     rcx, rsp; StackCookie
0x18002309b  call    __security_check_cookie
0x1800230a0  add     rsp, 6D8h
0x1800230a7  pop     r15
0x1800230a9  pop     r14
0x1800230ab  pop     r13
0x1800230ad  pop     r12
0x1800230af  pop     rdi
0x1800230b0  pop     rsi
0x1800230b1  pop     rbx
0x1800230b2  pop     rbp
0x1800230b3  retn
```
