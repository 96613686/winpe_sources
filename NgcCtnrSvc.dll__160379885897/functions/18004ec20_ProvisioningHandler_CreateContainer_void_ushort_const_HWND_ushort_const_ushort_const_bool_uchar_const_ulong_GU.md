# ProvisioningHandler::CreateContainer(void *,ushort const *,HWND__ *,ushort const *,ushort const *,bool,uchar const *,ulong,_GUID *,uchar * *,ulong *,unsigned __int64 *)

- ea: `0x18004ec20`
- end: `0x18004fd0c`
- name: `?CreateContainer@ProvisioningHandler@@QEAAJPEAXPEBGPEAUHWND__@@11_NPEBEKPEAU_GUID@@PEAPEAEPEAKPEA_K@Z`
- size: `4332`
- prototype: `__int64 __fastcall(__int64 (**this)(void), void *, WCHAR *, HWND, const unsigned __int16 *, const unsigned __int16 *, bool, unsigned __int16 *, unsigned int, struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `50`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180051998`

## callees

- `0x1800010c4`
- `0x1800025f4`
- `0x180004960`
- `0x18000b180`
- `0x18000c688`
- `0x18000c6b0`
- `0x18000c7e0`
- `0x1800134a0`
- `0x180014384`
- `0x180016550`
- `0x180016f14`
- `0x180017820`
- `0x180017f68`
- `0x180018194`
- `0x18001825c`
- `0x180019b48`
- `0x18001ced8`
- `0x180029980`
- `0x18002c640`
- `0x18002d500`
- `0x18002d518`
- `0x18003cdfc`
- `0x18003d3bc`
- `0x18003d448`
- `0x18003d4a0`
- `0x180047558`
- `0x18004e594`
- `0x18004e9f8`
- `0x18004ea20`
- `0x18004ea7c`
- `0x18004eafc`
- `0x18004eb88`
- `0x18004ec20`
- `0x180050774`
- `0x180050958`
- `0x180050ad4`
- `0x180050b44`
- `0x180051190`
- `0x18005170c`
- `0x1800517f8`
- `0x18005289c`
- `0x180055034`
- `0x180055bb4`
- `0x180057524`
- `0x18005addc`
- `0x18005b5ec`
- `0x18005e424`
- `0x18005e4d0`
- `0x180079400`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fcb0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ef41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fb11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fcb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004efd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ef0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004efd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ecf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ecf6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004fcce`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004fcce`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f3df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004f3df`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ecdb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004ecdb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f800`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f89f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f800`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004f89f`
- `ntdll!RtlPublishWnfStateData` at `0x18004fbd8`
- `ntdll!RtlPublishWnfStateData` at `0x18004fbd8`
- `dsreg!DsrGetJoinInfo` at `0x18004f0f1`
- `dsreg!DsrGetJoinInfo` at `0x18004f0f1`

## string_xrefs

- `0x18004ee2f`: `onecore\ds\security\ngc\ctnrsvc\handlers\provisioning\provisioninghandler.cpp`
- `0x18004f4d0`: `onecore\ds\security\ngc\ctnrsvc\handlers\provisioning\provisioninghandler.cpp`
- `0x18004fbfa`: `onecore\ds\security\ngc\ctnrsvc\handlers\provisioning\provisioninghandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ProvisioningHandler::CreateContainer(
        __int64 (**this)(void),
        void *a2,
        WCHAR *a3,
        HWND a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        bool a7,
        unsigned __int16 *a8,
        unsigned int a9,
        struct _GUID *a10,
        unsigned __int8 **a11,
        unsigned int *a12,
        unsigned __int64 *a13)
{
  BOOL v16; // ebx
  enum _NGC_ENABLED_STATE *v17; // rdx
  DWORD LastError; // eax
  signed int BioProtector; // ebx
  __int64 v20; // rdx
  __int64 v21; // rcx
  char *v22; // rdx
  int v23; // eax
  enum PolicyManager::PolicyType *v24; // r9
  unsigned int v25; // edx
  bool v26; // zf
  void *v27; // r14
  HWND v28; // rdx
  __int64 (*v29)(void); // rbx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  char v33; // al
  bool IsZero; // al
  struct _GUID *v35; // r9
  int v36; // eax
  wil::details::in1diag3 *v37; // rcx
  __int64 v38; // rdx
  struct INgcCtnrContainer *v39; // rcx
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  char *v43; // rdx
  int *v44; // rdx
  ProvisioningHandler *v45; // rcx
  ProvisioningHandler *v46; // rcx
  signed int v47; // ebx
  char v48; // r12
  LSTATUS ValueW; // eax
  int v50; // r14d
  __int64 v51; // rcx
  LSTATUS v52; // r14d
  bool v53; // r9
  const unsigned __int16 *v54; // rdx
  unsigned __int16 *v55; // rax
  unsigned __int8 *v56; // rbx
  int v57; // eax
  wil::details::in1diag3 *v58; // rcx
  __int64 v59; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  LPVOID *ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  char v64[4]; // [rsp+60h] [rbp-A0h] BYREF
  HRESULT IsNgcEnabled; // [rsp+64h] [rbp-9Ch] BYREF
  int v66; // [rsp+68h] [rbp-98h] BYREF
  char v67; // [rsp+6Ch] [rbp-94h] BYREF
  struct INgcCtnrContainer *v68; // [rsp+70h] [rbp-90h] BYREF
  __int64 v69; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbData[2]; // [rsp+80h] [rbp-80h] BYREF
  int *v71; // [rsp+88h] [rbp-78h]
  char v72[4]; // [rsp+90h] [rbp-70h] BYREF
  int v73; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v74; // [rsp+98h] [rbp-68h] BYREF
  LSTATUS v75; // [rsp+9Ch] [rbp-64h] BYREF
  LSTATUS v76; // [rsp+A0h] [rbp-60h] BYREF
  int v77[4]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v78; // [rsp+B8h] [rbp-48h]
  __int16 v79[2]; // [rsp+C0h] [rbp-40h] BYREF
  HRESULT v80; // [rsp+C4h] [rbp-3Ch] BYREF
  DWORD v81; // [rsp+C8h] [rbp-38h] BYREF
  HRESULT pvData; // [rsp+CCh] [rbp-34h] BYREF
  void *v83; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v84; // [rsp+D8h] [rbp-28h] BYREF
  struct INgcCtnrContainer **v85; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v86; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v87; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v88; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v89; // [rsp+100h] [rbp+0h]
  unsigned __int64 *v90; // [rsp+108h] [rbp+8h] BYREF
  PSID Sid; // [rsp+110h] [rbp+10h] BYREF
  __int16 v92; // [rsp+118h] [rbp+18h]
  unsigned __int64 v93; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v94; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 v95[2]; // [rsp+130h] [rbp+30h] BYREF
  int v96; // [rsp+134h] [rbp+34h]
  __int64 v97; // [rsp+138h] [rbp+38h]
  char v98; // [rsp+140h] [rbp+40h]
  int v99; // [rsp+144h] [rbp+44h]
  int v100; // [rsp+148h] [rbp+48h]
  __int128 v101; // [rsp+14Ch] [rbp+4Ch]
  int v102; // [rsp+15Ch] [rbp+5Ch]
  __int64 v103; // [rsp+160h] [rbp+60h]
  int v104; // [rsp+168h] [rbp+68h]
  _QWORD v105[8]; // [rsp+170h] [rbp+70h] BYREF
  __int16 v106; // [rsp+1B0h] [rbp+B0h]
  unsigned __int8 **v107; // [rsp+1C0h] [rbp+C0h]
  unsigned int *v108; // [rsp+1C8h] [rbp+C8h]
  struct _GUID *v109; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 *v110; // [rsp+1D8h] [rbp+D8h]
  _QWORD v111[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v112; // [rsp+1F0h] [rbp+F0h]
  int v113; // [rsp+1F4h] [rbp+F4h]
  __int64 (**v114)(void); // [rsp+1F8h] [rbp+F8h]
  _BYTE Src[2160]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 *v116[2]; // [rsp+A70h] [rbp+970h] BYREF
  unsigned __int64 v117; // [rsp+A88h] [rbp+988h]
  int v118; // [rsp+A90h] [rbp+990h] BYREF
  char v119; // [rsp+A94h] [rbp+994h]
  char v120; // [rsp+A98h] [rbp+998h] BYREF
  struct _GUID v121; // [rsp+AA8h] [rbp+9A8h] BYREF
  struct _GUID v122; // [rsp+AC0h] [rbp+9C0h] BYREF
  _BYTE v123[32]; // [rsp+AD0h] [rbp+9D0h] BYREF
  int v124; // [rsp+AF0h] [rbp+9F0h] BYREF
  unsigned __int16 v125[1076]; // [rsp+AF4h] [rbp+9F4h] BYREF
  bool v126; // [rsp+135Ch] [rbp+125Ch]
  wil::details::in1diag3 *retaddr; // [rsp+13B8h] [rbp+12B8h]

  v83 = a2;
  v116[0] = a8;
  v109 = a10;
  v107 = a11;
  v108 = a12;
  v110 = a13;
  IsNgcEnabled = 0;
  v84 = 0;
  v90 = &v84;
  Sid = 0;
  LOBYTE(v92) = 1;
  v16 = ConvertStringSidToSidW(a3, &Sid);
  wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v90);
  if ( !v16 )
  {
    LastError = GetLastError();
    BioProtector = LastError;
    if ( (unsigned int)dword_1800BE0B8 > 3 )
    {
      v66 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)byte_1800AC315,
        0,
        0,
        (__int64)&v66);
    }
    if ( BioProtector > 0 )
      BioProtector = (unsigned __int16)BioProtector | 0x80070000;
    IsNgcEnabled = BioProtector;
    goto LABEL_157;
  }
  v66 = 2;
  IsNgcEnabled = NgcUtils::IsNgcEnabled((NgcUtils *)&v66, v17);
  if ( IsNgcEnabled < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
    {
LABEL_11:
      BioProtector = IsNgcEnabled;
      goto LABEL_157;
    }
    v22 = byte_1800AC36D;
LABEL_10:
    v66 = IsNgcEnabled;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BE0B8,
      (_DWORD)v22,
      0,
      0,
      (__int64)&v66);
    goto LABEL_11;
  }
  if ( !v66 )
  {
    BioProtector = -2146893808;
    if ( (unsigned int)dword_1800BE0B8 > 3 )
    {
      v66 = -2146893808;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)qword_1800AC348,
        0,
        0,
        (__int64)&v66);
    }
    if ( (Microsoft_Windows_HelloForBusinessEnableBits & 1) != 0 )
      McTemplateU0kq_EventWriteTransfer(v21, v20, v84);
    goto LABEL_157;
  }
  if ( (Microsoft_Windows_HelloForBusinessEnableBits & 1) != 0 )
    McTemplateU0kq_EventWriteTransfer(v21, v20, v84);
  v23 = this[12]();
  if ( v23 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\provisioning\\provisioninghandler.cpp",
      (const char *)(unsigned int)v23,
      ppv);
  LOBYTE(v95[0]) = 0;
  v96 = 1;
  v97 = 1;
  v98 = 0;
  v99 = 8;
  v100 = 127;
  v101 = 0;
  v102 = 2;
  v103 = 1;
  v104 = 0;
  v66 = 0;
  IsNgcEnabled = PolicyManager::GetManagedPolicy((PolicyManager *)a3, v95, (struct NgcPolicy *)&v66, v24);
  if ( IsNgcEnabled < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_11;
    v22 = byte_1800AC263;
    goto LABEL_10;
  }
  v64[0] = 0;
  IsNgcEnabled = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v64, v25);
  if ( IsNgcEnabled < 0 )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v66 = IsNgcEnabled;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)&unk_1800AC228,
        0,
        0,
        (__int64)&v66);
    }
    BioProtector = IsNgcEnabled;
    goto LABEL_28;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v87 = (unsigned __int64)this;
  BioProtector = ProvisioningHandler::PerformExistingContainerChecks((ProvisioningHandler *)this, a3);
  IsNgcEnabled = BioProtector;
  if ( BioProtector < 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
LABEL_28:
    v26 = v64[0] == 0;
    goto LABEL_155;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  *(_OWORD *)v77 = 0;
  v78 = 0;
  if ( v116[0] && a9 )
  {
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::assign<unsigned char const *,0>(
      v77,
      v116[0],
      (char *)v116[0] + a9);
    v27 = v83;
    goto LABEL_35;
  }
  LOBYTE(ppv) = a7;
  v28 = a4;
  v27 = v83;
  BioProtector = ProvisioningHandler::PromptForPinCredential(v83, v28, a5, a6, ppv, v95, v84, v77);
  IsNgcEnabled = BioProtector;
  if ( BioProtector >= 0 )
  {
LABEL_35:
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    v114 = this;
    BioProtector = ProvisioningHandler::PerformExistingContainerChecks((ProvisioningHandler *)this, a3);
    IsNgcEnabled = BioProtector;
    if ( BioProtector < 0 )
    {
LABEL_153:
      LeaveCriticalSection((LPCRITICAL_SECTION)this);
      goto LABEL_154;
    }
    v69 = 0;
    v29 = this[13];
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v69,
      0);
    IsNgcEnabled = ((__int64 (__fastcall *)(__int64 *))v29)(&v69);
    if ( IsNgcEnabled < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v66 = IsNgcEnabled;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)byte_1800AC2C9,
          0,
          0,
          (__int64)&v66);
      }
      BioProtector = IsNgcEnabled;
      goto LABEL_152;
    }
    v68 = 0;
    IsNgcEnabled = ((__int64 (__fastcall *)(struct INgcCtnrContainer **))this[14])(&v68);
    if ( IsNgcEnabled < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v116[0] = (unsigned __int16 *)&GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317;
        v66 = IsNgcEnabled;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v30,
          (unsigned int)byte_1800AC28B,
          v31,
          v32,
          (__int64)&v66,
          (__int64)v116);
      }
      BioProtector = IsNgcEnabled;
      goto LABEL_151;
    }
    v89 = 0;
    v88 = 0;
    v73 = 2;
    v67 = 0;
    v83 = 0;
    IsNgcEnabled = DsrGetJoinInfo(0, &v83);
    if ( IsNgcEnabled < 0 )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v66 = IsNgcEnabled;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)&byte_1800AC1C7,
          0,
          0,
          (__int64)&v66);
      }
      BioProtector = IsNgcEnabled;
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v83);
      goto LABEL_151;
    }
    if ( !v83 || (v33 = 1, *(_DWORD *)v83 != 1) )
      v33 = 0;
    v67 = v33;
    wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v83);
    if ( v67 || HIDWORD(v97) == 1 )
      v73 = 1;
    v80 = 0;
    v76 = 0;
    v74 = 0;
    v118 = 0;
    v119 = 0;
    _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::zInternalStart(&v118);
    if ( (unsigned int)dword_1800BE0B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0x800000000000LL) )
    {
      v81 = v74;
      v75 = v76;
      v72[0] = v67;
      v79[0] = WORD2(v97);
      LOWORD(v66) = v73;
      pvData = v80;
      pcbData[0] = IsNgcEnabled;
      if ( !v119 || (IsZero = _tlgGuidIsZero(&v121), v35 = &v121, IsZero) )
        LODWORD(v35) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)&byte_1800AC127,
        (unsigned int)&v120,
        (_DWORD)v35,
        (__int64)pcbData,
        (__int64)&pvData,
        (__int64)&v66,
        (__int64)v79,
        (__int64)v72,
        (__int64)&v75,
        (__int64)&v81);
    }
    v105[0] = &v118;
    v105[1] = &IsNgcEnabled;
    v105[2] = &v80;
    v105[3] = &v73;
    v105[4] = v95;
    v105[5] = &v67;
    v105[6] = &v76;
    v105[7] = &v74;
    v106 = 256;
    ppva = *(LPVOID **)v77;
    IsNgcEnabled = ProvisioningHandler::InternalCreateContainerAndDecryptionKeys(this, v68, a3, v69);
    v80 = IsNgcEnabled;
    if ( IsNgcEnabled >= 0 )
    {
      v36 = (*(__int64 (__fastcall **)(struct INgcCtnrContainer *, LSTATUS *, DWORD *))(*(_QWORD *)v68 + 72LL))(
              v68,
              &v76,
              &v74);
      v37 = retaddr;
      if ( v36 >= 0 )
        goto LABEL_77;
      v38 = 962;
      goto LABEL_76;
    }
    if ( HIDWORD(v97) )
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v43 = (char *)&unk_1800AC0E8;
        goto LABEL_148;
      }
    }
    else
    {
      if ( (unsigned int)dword_1800BE0B8 > 3 )
      {
        pcbData[0] = IsNgcEnabled;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)byte_1800AC1ED,
          0,
          0,
          (__int64)pcbData);
      }
      v39 = v68;
      v68 = 0;
      if ( v39 )
        (*(void (__fastcall **)(struct INgcCtnrContainer *))(*(_QWORD *)v39 + 16LL))(v39);
      IsNgcEnabled = CoCreateInstance(
                       &GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317,
                       0,
                       1u,
                       &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
                       (LPVOID *)&v68);
      if ( IsNgcEnabled < 0 )
      {
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          v116[0] = (unsigned __int16 *)&GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317;
          pcbData[0] = IsNgcEnabled;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
            v40,
            (unsigned int)&word_1800AC06E,
            v41,
            v42,
            (__int64)pcbData,
            (__int64)v116);
        }
        goto LABEL_149;
      }
      v73 = 0;
      ppva = *(LPVOID **)v77;
      IsNgcEnabled = ProvisioningHandler::InternalCreateContainerAndDecryptionKeys(this, v68, a3, v69);
      if ( IsNgcEnabled >= 0 )
      {
        v36 = (*(__int64 (__fastcall **)(struct INgcCtnrContainer *, LSTATUS *, DWORD *))(*(_QWORD *)v68 + 72LL))(
                v68,
                &v76,
                &v74);
        v37 = retaddr;
        if ( v36 >= 0 )
          goto LABEL_77;
        v38 = 1019;
LABEL_76:
        wil::details::in1diag3::_Log_Hr(
          v37,
          (void *)v38,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\provisioning\\provisioninghandler.cpp",
          (const char *)(unsigned int)v36,
          (int)ppva);
LABEL_77:
        v85 = &v68;
        v86 = 256;
        *(_QWORD *)pcbData = 0;
        IsNgcEnabled = StringCbLengthW(a3, 0x1FEu, (unsigned __int64 *)pcbData);
        if ( IsNgcEnabled < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 2 )
          {
LABEL_81:
            BioProtector = IsNgcEnabled;
LABEL_82:
            wil::details::ScopeExitFnGuard__lambda_a348a45b1eac92d5e91dd06f2d441454___::operator()(&v85);
LABEL_150:
            wil::details::ScopeExitFnGuard__lambda_f261a08160a797ca8623d2aca3f7e221___::operator()(v105);
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v118);
LABEL_151:
            wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v68);
LABEL_152:
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v69);
            goto LABEL_153;
          }
          v44 = &dword_1800AC0B4;
LABEL_80:
          pcbData[0] = IsNgcEnabled;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800BE0B8,
            (_DWORD)v44,
            0,
            0,
            (__int64)pcbData);
          goto LABEL_81;
        }
        LODWORD(ppva) = 0;
        IsNgcEnabled = (*(__int64 (__fastcall **)(struct INgcCtnrContainer *, __int64, WCHAR *, __int64, LPVOID *))(*(_QWORD *)v68 + 128LL))(
                         v68,
                         1,
                         a3,
                         *(_QWORD *)pcbData + 2LL,
                         ppva);
        if ( IsNgcEnabled < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 2 )
            goto LABEL_81;
          v44 = &dword_1800ABFC4;
          goto LABEL_80;
        }
        if ( v96 == 1 )
        {
          v87 = v84;
          v66 = 0;
          *(_QWORD *)pcbData = &v87;
          v71 = &v66;
          lambda_dcc46b57e3b17782259cf4b8e691dc4d_::operator()(pcbData);
          if ( (v66 & 0x1A) != 0 )
          {
            v87 = 0;
            BioProtector = (*(__int64 (__fastcall **)(struct INgcCtnrContainer *, __int64, unsigned __int64 *))(*(_QWORD *)v68 + 456LL))(
                             v68,
                             v88,
                             &v87);
            IsNgcEnabled = BioProtector;
            if ( BioProtector < 0 )
              goto LABEL_82;
            BioProtector = ProvisioningHandler::CreateBioProtector(v45, v68, v89, v87);
            IsNgcEnabled = BioProtector;
            if ( BioProtector < 0 )
              goto LABEL_82;
          }
        }
        v94 = 0;
        BioProtector = (*(__int64 (__fastcall **)(struct INgcCtnrContainer *, __int64, unsigned __int64 *))(*(_QWORD *)v68 + 456LL))(
                         v68,
                         v88,
                         &v94);
        IsNgcEnabled = BioProtector;
        if ( BioProtector < 0 )
          goto LABEL_82;
        ProvisioningHandler::CreateCompanionDeviceProtector(v46, v68, v89, v94);
        IsNgcEnabled = ((__int64 (__fastcall *)(struct INgcCtnrContainer *))this[16])(v68);
        if ( IsNgcEnabled < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 <= 2 )
            goto LABEL_81;
          v44 = (int *)byte_1800ABFF3;
          goto LABEL_80;
        }
        v90 = (unsigned __int64 *)this;
        Sid = &v68;
        v92 = 256;
        v122 = 0;
        IsNgcEnabled = (*(__int64 (__fastcall **)(struct INgcCtnrContainer *, struct _GUID *))(*(_QWORD *)v68 + 64LL))(
                         v68,
                         &v122);
        if ( IsNgcEnabled < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            pcbData[0] = IsNgcEnabled;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BE0B8,
              (unsigned int)&byte_1800ABF17,
              0,
              0,
              (__int64)pcbData);
          }
          BioProtector = IsNgcEnabled;
LABEL_98:
          wil::details::ScopeExitFnGuard__lambda_771cfa833085edf349575f3f4def4cf2___::operator()(&v90);
          goto LABEL_82;
        }
        v111[0] = 1;
        v111[1] = *(_QWORD *)v77;
        v112 = v77[2] - v77[0];
        v113 = 0;
        v93 = 0;
        if ( !v116[0] )
        {
          NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v116, v27);
          IsNgcEnabled = NgcTicketCreateForNewKey((const struct _NGC_RPC_GESTURE_INFO *)v111, &v122, &v93);
          if ( IsNgcEnabled < 0 )
          {
            if ( (unsigned int)dword_1800BE0B8 > 2 )
            {
              pcbData[0] = IsNgcEnabled;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1800BE0B8,
                (unsigned int)&unk_1800ABF88,
                0,
                0,
                (__int64)pcbData);
            }
            BioProtector = IsNgcEnabled;
            NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v116);
            goto LABEL_98;
          }
          NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v116);
        }
        v47 = 0;
        v48 = 0;
        pvData = 0;
        pcbData[0] = 4;
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"SOFTWARE\\Policies\\Microsoft\\PassportForWork",
                   L"AllowPrebootAuth",
                   0x10u,
                   0,
                   &pvData,
                   pcbData);
        v50 = ValueW;
        if ( (ValueW & 0xFFFFFFFD) != 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            v75 = ValueW;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BE0B8,
              (unsigned int)&unk_1800AD750,
              0,
              0,
              (__int64)&v75);
          }
          if ( v50 > 0 )
            v47 = (unsigned __int16)v50 | 0x80070000;
          else
            v47 = v50;
        }
        v66 = 0;
        v81 = 4;
        v52 = RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailUnlock",
                L"Enabled",
                0x10u,
                0,
                &v66,
                &v81);
        if ( v52 )
        {
          if ( v52 != 2 )
          {
            if ( (unsigned int)dword_1800BE0B8 > 2 )
            {
              v75 = v52;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1800BE0B8,
                (unsigned int)&word_1800AD726,
                0,
                0,
                (__int64)&v75);
            }
            if ( v52 > 0 )
              v47 = (unsigned __int16)v52 | 0x80070000;
            else
              v47 = v52;
          }
        }
        else if ( v66 )
        {
          v48 = 1;
        }
        IsNgcEnabled = v47;
        if ( v47 < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 3 )
          {
            pcbData[0] = IsNgcEnabled;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BE0B8,
              (unsigned int)&dword_1800ABF4C,
              0,
              0,
              (__int64)pcbData);
          }
          IsNgcEnabled = 0;
        }
        if ( v48 )
        {
          std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>(
            v123,
            *(_QWORD *)v77,
            *(_QWORD *)&v77[2]);
          std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v116);
          NgcUtils::ConvertMultiByteToWideChar(v123, v116);
          v54 = (const unsigned __int16 *)v116;
          if ( v117 > 7 )
            v54 = v116[0];
          IsNgcEnabled = NgcPreboot::ProvisionRecoveryKey((NgcPreboot *)a3, v54, 0, v53);
          if ( IsNgcEnabled < 0 )
          {
            if ( (unsigned int)dword_1800BE0B8 > 3 )
            {
              pcbData[0] = IsNgcEnabled;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1800BE0B8,
                (unsigned int)byte_1800ABEB9,
                0,
                0,
                (__int64)pcbData);
            }
            IsNgcEnabled = 0;
          }
          std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::_Tidy_deallocate(v116);
          std::basic_string<char,std::char_traits<char>,wil::secure_allocator<char>>::_Tidy_deallocate(v123);
        }
        *(struct _GUID *)v116 = v122;
        IsNgcEnabled = ProvisioningHandler::NotifyDplContainerChanges(v51, a3, v116, 4);
        if ( IsNgcEnabled < 0 )
        {
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            pcbData[0] = IsNgcEnabled;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BE0B8,
              (unsigned int)&unk_1800ABE88,
              0,
              0,
              (__int64)pcbData);
          }
          IsNgcEnabled = 0;
        }
        v55 = (unsigned __int16 *)MIDL_user_allocate(0x18u);
        v56 = (unsigned __int8 *)v55;
        v116[0] = (unsigned __int16 *)24;
        v116[1] = v55;
        if ( !v55 )
        {
          IsNgcEnabled = -2147024882;
          if ( (unsigned int)dword_1800BE0B8 > 2 )
          {
            pcbData[0] = IsNgcEnabled;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800BE0B8,
              (unsigned int)byte_1800ABEE5,
              0,
              0,
              (__int64)pcbData);
          }
          goto LABEL_139;
        }
        *(_OWORD *)v55 = 0;
        *((_QWORD *)v55 + 2) = 0;
        ((void (__fastcall *)(struct INgcCtnrContainer *, _QWORD, unsigned __int64, __int64))this[10])(v68, 0, v89, v88);
        v124 = 6;
        memset_0(Src, 0, 0x868u);
        memcpy_0(v125, Src, sizeof(v125));
        v126 = v74 != 0;
        v57 = StringCchCopyW(v125, 0x433u, a3);
        v58 = retaddr;
        if ( v57 >= 0 )
        {
          ppvb = 0;
          v57 = RtlPublishWnfStateData(WNF_NGC_CREDENTIAL_REFRESH_REQUIRED, 0, &v124, 2160) | 0x10000000;
          v58 = retaddr;
          if ( v57 >= 0 )
          {
LABEL_145:
            ProvisioningHandler::ResetTpmDictionaryAttackParametersIfApplicable((NgcPolicy *)a3);
            v116[1] = 0;
            *v107 = v56;
            *v108 = 24;
            *v109 = 0;
            *v110 = v93;
            HIBYTE(v92) = 0;
            HIBYTE(v86) = 0;
LABEL_139:
            BioProtector = IsNgcEnabled;
            std::unique_ptr<unsigned char,rpcmem_secure_delete<unsigned char>>::~unique_ptr<unsigned char,rpcmem_secure_delete<unsigned char>>(v116);
            wil::details::ScopeExitFnGuard__lambda_771cfa833085edf349575f3f4def4cf2___::operator()(&v90);
            wil::details::ScopeExitFnGuard__lambda_a348a45b1eac92d5e91dd06f2d441454___::operator()(&v85);
            wil::details::ScopeExitFnGuard__lambda_f261a08160a797ca8623d2aca3f7e221___::operator()(v105);
            _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider>,140737488355328,5>(&v118);
            wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v68);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v69);
            LeaveCriticalSection((LPCRITICAL_SECTION)this);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v77);
            v26 = v64[0] == 0;
            goto LABEL_155;
          }
          v59 = 1279;
        }
        else
        {
          v59 = 1274;
        }
        wil::details::in1diag3::_Log_Hr(
          v58,
          (void *)v59,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\handlers\\provisioning\\provisioninghandler.cpp",
          (const char *)(unsigned int)v57,
          ppvb);
        goto LABEL_145;
      }
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v43 = byte_1800AC039;
LABEL_148:
        pcbData[0] = IsNgcEnabled;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (_DWORD)v43,
          0,
          0,
          (__int64)pcbData);
      }
    }
LABEL_149:
    BioProtector = IsNgcEnabled;
    goto LABEL_150;
  }
LABEL_154:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v77);
  v26 = v64[0] == 0;
LABEL_155:
  if ( !v26 )
    CoUninitialize();
LABEL_157:
  wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
    &v84,
    0);
  return (unsigned int)BioProtector;
}

```

## disassembly

```asm
0x18004ec20  push    rbp
0x18004ec22  push    rbx
0x18004ec23  push    rsi
0x18004ec24  push    rdi
0x18004ec25  push    r12
0x18004ec27  push    r13
0x18004ec29  push    r14
0x18004ec2b  push    r15
0x18004ec2d  lea     rbp, [rsp-1278h]
0x18004ec35  mov     eax, 1378h
0x18004ec3a  call    _alloca_probe
0x18004ec3f  sub     rsp, rax
0x18004ec42  mov     rax, cs:__security_cookie
0x18004ec49  xor     rax, rsp
0x18004ec4c  mov     [rbp+12B0h+var_50], rax
0x18004ec53  mov     r14, r9
0x18004ec56  mov     r13, r8
0x18004ec59  mov     [rbp+12B0h+var_12E0], rdx
0x18004ec5d  mov     rsi, rcx
0x18004ec60  mov     r15, [rbp+12B0h+arg_20]
0x18004ec67  mov     r12, [rbp+12B0h+arg_28]
0x18004ec6e  mov     rax, [rbp+12B0h+arg_38]
0x18004ec75  mov     [rbp+12B0h+var_940], rax
0x18004ec7c  mov     edi, [rbp+12B0h+arg_40]
0x18004ec82  mov     rax, [rbp+12B0h+arg_48]
0x18004ec89  mov     [rbp+12B0h+var_11E0], rax
0x18004ec90  mov     rax, [rbp+12B0h+arg_50]
0x18004ec97  mov     [rbp+12B0h+var_11F0], rax
0x18004ec9e  mov     rax, [rbp+12B0h+arg_58]
0x18004eca5  mov     [rbp+12B0h+var_11E8], rax
0x18004ecac  mov     rax, [rbp+12B0h+arg_60]
0x18004ecb3  mov     [rbp+12B0h+var_11D8], rax
0x18004ecba  xor     ecx, ecx
0x18004ecbc  mov     [rsp+13B0h+var_134C], ecx
0x18004ecc0  mov     [rbp+12B0h+var_12D8], rcx
0x18004ecc4  lea     rax, [rbp+12B0h+var_12D8]
0x18004ecc8  mov     [rbp+12B0h+var_12A8], rax
0x18004eccc  mov     [rbp+12B0h+Sid], rcx
0x18004ecd0  mov     byte ptr [rbp+12B0h+var_1298], 1
0x18004ecd4  lea     rdx, [rbp+12B0h+Sid]; Sid
0x18004ecd8  mov     rcx, r8; StringSid
0x18004ecdb  call    cs:__imp_ConvertStringSidToSidW
0x18004ece2  nop     dword ptr [rax+rax+00h]
0x18004ece7  mov     ebx, eax
0x18004ece9  lea     rcx, [rbp+12B0h+var_12A8]
0x18004eced  call    ??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18004ecf2  test    ebx, ebx
0x18004ecf4  jnz     short loc_18004ED4C
0x18004ecf6  call    cs:__imp_GetLastError
0x18004ecfd  nop     dword ptr [rax+rax+00h]
0x18004ed02  mov     ebx, eax
0x18004ed04  mov     ecx, cs:dword_1800BE0B8
0x18004ed0a  cmp     ecx, 3
0x18004ed0d  jbe     short loc_18004ED36
0x18004ed0f  mov     [rsp+13B0h+var_1348], eax
0x18004ed13  lea     rax, [rsp+13B0h+var_1348]
0x18004ed18  mov     [rsp+13B0h+ppv], rax
0x18004ed1d  xor     r9d, r9d
0x18004ed20  xor     r8d, r8d
0x18004ed23  lea     rdx, byte_1800AC315
0x18004ed2a  lea     rcx, dword_1800BE0B8
0x18004ed31  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004ed36  test    ebx, ebx
0x18004ed38  jle     short loc_18004ED43
0x18004ed3a  movzx   ebx, bx
0x18004ed3d  or      ebx, 80070000h
0x18004ed43  mov     [rsp+13B0h+var_134C], ebx
0x18004ed47  jmp     loc_18004FCDB
0x18004ed4c  mov     [rsp+13B0h+var_1348], 2
0x18004ed54  lea     rcx, [rsp+13B0h+var_1348]; this
0x18004ed59  call    ?IsNgcEnabled@NgcUtils@@YAJPEAW4_NGC_ENABLED_STATE@@@Z; NgcUtils::IsNgcEnabled(_NGC_ENABLED_STATE *)
0x18004ed5e  mov     [rsp+13B0h+var_134C], eax
0x18004ed62  xor     ebx, ebx
0x18004ed64  test    eax, eax
0x18004ed66  jns     short loc_18004EDA7
0x18004ed68  mov     eax, cs:dword_1800BE0B8
0x18004ed6e  cmp     eax, 2
0x18004ed71  jbe     short loc_18004ED9E
0x18004ed73  lea     rdx, byte_1800AC36D
0x18004ed7a  mov     eax, [rsp+13B0h+var_134C]
0x18004ed7e  mov     [rsp+13B0h+var_1348], eax
0x18004ed82  xor     r9d, r9d
0x18004ed85  lea     rax, [rsp+13B0h+var_1348]
0x18004ed8a  xor     r8d, r8d
0x18004ed8d  mov     [rsp+13B0h+ppv], rax
0x18004ed92  lea     rcx, dword_1800BE0B8
0x18004ed99  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004ed9e  mov     ebx, [rsp+13B0h+var_134C]
0x18004eda2  jmp     loc_18004FCDB
0x18004eda7  mov     r9d, [rsp+13B0h+var_1348]
0x18004edac  test    r9d, r9d
0x18004edaf  jnz     short loc_18004EE06
0x18004edb1  mov     eax, cs:dword_1800BE0B8
0x18004edb7  mov     ebx, 80090010h
0x18004edbc  cmp     eax, 3
0x18004edbf  jbe     short loc_18004EDE8
0x18004edc1  mov     [rsp+13B0h+var_1348], ebx
0x18004edc5  lea     rax, [rsp+13B0h+var_1348]
0x18004edca  mov     [rsp+13B0h+ppv], rax
0x18004edcf  xor     r9d, r9d
0x18004edd2  xor     r8d, r8d
0x18004edd5  lea     rdx, qword_1800AC348
0x18004eddc  lea     rcx, dword_1800BE0B8
0x18004ede3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004ede8  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 1
0x18004edef  jz      loc_18004FCDB
0x18004edf5  xor     r9d, r9d
0x18004edf8  mov     r8, [rbp+12B0h+var_12D8]
0x18004edfc  call    McTemplateU0kq_EventWriteTransfer
0x18004ee01  jmp     loc_18004FCDB
0x18004ee06  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 1
0x18004ee0d  jz      short loc_18004EE18
0x18004ee0f  mov     r8, [rbp+12B0h+var_12D8]
0x18004ee13  call    McTemplateU0kq_EventWriteTransfer
0x18004ee18  mov     rax, [rsi+60h]
0x18004ee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee21  mov     rcx, [rbp+12B8h]; this
0x18004ee28  test    eax, eax
0x18004ee2a  jns     short loc_18004EE40
0x18004ee2c  mov     r9d, eax; char *
0x18004ee2f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\ctnrsvc\\ha"...
0x18004ee36  mov     edx, 311h; void *
0x18004ee3b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ee40  mov     byte ptr [rbp+12B0h+var_1280], bl
0x18004ee43  mov     eax, 1
0x18004ee48  mov     [rbp+12B0h+var_127C], eax
0x18004ee4b  mov     [rbp+12B0h+var_1278], rax
0x18004ee4f  mov     [rbp+12B0h+var_1270], bl
0x18004ee52  mov     [rbp+12B0h+var_126C], 8
0x18004ee59  mov     [rbp+12B0h+var_1268], 7Fh
0x18004ee60  xorps   xmm0, xmm0
0x18004ee63  movdqu  [rbp+12B0h+var_1264], xmm0
0x18004ee68  mov     [rbp+12B0h+var_1254], 2
0x18004ee6f  mov     [rbp+12B0h+var_1250], rax
0x18004ee73  mov     [rbp+12B0h+var_1248], ebx
0x18004ee76  mov     [rsp+13B0h+var_1348], ebx
0x18004ee7a  lea     r8, [rsp+13B0h+var_1348]; struct NgcPolicy *
0x18004ee7f  lea     rdx, [rbp+12B0h+var_1280]; unsigned __int16 *
0x18004ee83  mov     rcx, r13; this
0x18004ee86  call    ?GetManagedPolicy@PolicyManager@@YAJPEBGPEAVNgcPolicy@2@PEAW4PolicyType@1@@Z; PolicyManager::GetManagedPolicy(ushort const *,NgcPolicy::NgcPolicy *,PolicyManager::PolicyType *)
0x18004ee8b  mov     [rsp+13B0h+var_134C], eax
0x18004ee8f  test    eax, eax
0x18004ee91  jns     short loc_18004EEAE
0x18004ee93  mov     eax, cs:dword_1800BE0B8
0x18004ee99  cmp     eax, 2
0x18004ee9c  jbe     loc_18004ED9E
0x18004eea2  lea     rdx, byte_1800AC263
0x18004eea9  jmp     loc_18004ED7A
0x18004eeae  mov     [rsp+13B0h+var_1350], bl
0x18004eeb2  lea     rcx, [rsp+13B0h+var_1350]; this
0x18004eeb7  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x18004eebc  mov     [rsp+13B0h+var_134C], eax
0x18004eec0  test    eax, eax
0x18004eec2  jns     short loc_18004EF08
0x18004eec4  mov     eax, cs:dword_1800BE0B8
0x18004eeca  cmp     eax, 2
0x18004eecd  jbe     short loc_18004EEFA
0x18004eecf  mov     eax, [rsp+13B0h+var_134C]
0x18004eed3  mov     [rsp+13B0h+var_1348], eax
0x18004eed7  lea     rax, [rsp+13B0h+var_1348]
0x18004eedc  mov     [rsp+13B0h+ppv], rax
0x18004eee1  xor     r9d, r9d
0x18004eee4  xor     r8d, r8d
0x18004eee7  lea     rdx, unk_1800AC228
0x18004eeee  lea     rcx, dword_1800BE0B8
0x18004eef5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004eefa  mov     ebx, [rsp+13B0h+var_134C]
0x18004eefe  cmp     [rsp+13B0h+var_1350], 0
0x18004ef03  jmp     loc_18004FCCC
0x18004ef08  mov     rcx, rsi; lpCriticalSection
0x18004ef0b  call    cs:__imp_EnterCriticalSection
0x18004ef12  nop     dword ptr [rax+rax+00h]
0x18004ef17  mov     [rbp+12B0h+var_12C0], rsi
0x18004ef1b  mov     rdx, r13; unsigned __int16 *
0x18004ef1e  mov     rcx, rsi; this
0x18004ef21  call    ?PerformExistingContainerChecks@ProvisioningHandler@@AEAAJPEBG@Z; ProvisioningHandler::PerformExistingContainerChecks(ushort const *)
0x18004ef26  mov     ebx, eax
0x18004ef28  mov     [rsp+13B0h+var_134C], eax
0x18004ef2c  mov     rcx, rsi; lpCriticalSection
0x18004ef2f  test    eax, eax
0x18004ef31  jns     short loc_18004EF41
0x18004ef33  call    cs:__imp_LeaveCriticalSection
0x18004ef3a  nop     dword ptr [rax+rax+00h]
0x18004ef3f  jmp     short loc_18004EEFE
0x18004ef41  call    cs:__imp_LeaveCriticalSection
0x18004ef48  nop     dword ptr [rax+rax+00h]
0x18004ef4d  xorps   xmm0, xmm0
0x18004ef50  movdqu  xmmword ptr [rbp+12B0h+var_1308], xmm0
0x18004ef55  mov     [rbp+12B0h+var_12F8], 0
0x18004ef5d  mov     rax, [rbp+12B0h+var_940]
0x18004ef64  test    rax, rax
0x18004ef67  jz      short loc_18004EF86
0x18004ef69  test    edi, edi
0x18004ef6b  jz      short loc_18004EF86
0x18004ef6d  lea     r8, [rax+rdi]
0x18004ef71  mov     rdx, rax
0x18004ef74  lea     rcx, [rbp+12B0h+var_1308]
0x18004ef78  call    ??$assign@PEBE$0A@@?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAXPEBE0@Z; std::vector<uchar,wil::secure_allocator<uchar>>::assign<uchar const *,0>(uchar const *,uchar const *)
0x18004ef7d  mov     r14, [rbp+12B0h+var_12E0]
0x18004ef81  xor     r15d, r15d
0x18004ef84  jmp     short loc_18004EFD1
0x18004ef86  lea     rax, [rbp+12B0h+var_1308]
0x18004ef8a  mov     [rsp+13B0h+var_1378], rax
0x18004ef8f  mov     rax, [rbp+12B0h+var_12D8]
0x18004ef93  mov     [rsp+13B0h+pcbData], rax
0x18004ef98  lea     rax, [rbp+12B0h+var_1280]
0x18004ef9c  mov     [rsp+13B0h+pvData], rax
0x18004efa1  mov     al, [rbp+12B0h+arg_30]
0x18004efa7  mov     byte ptr [rsp+13B0h+ppv], al
0x18004efab  mov     r9, r12
0x18004efae  mov     r8, r15
0x18004efb1  mov     rdx, r14
0x18004efb4  mov     r14, [rbp+12B0h+var_12E0]
0x18004efb8  mov     rcx, r14
0x18004efbb  call    ?PromptForPinCredential@ProvisioningHandler@@SAJPEAXPEAUHWND__@@PEBG2_NAEBVNgcPolicy@3@0PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; ProvisioningHandler::PromptForPinCredential(void *,HWND__ *,ushort const *,ushort const *,bool,NgcPolicy::NgcPolicy const &,void *,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18004efc0  mov     ebx, eax
0x18004efc2  mov     [rsp+13B0h+var_134C], eax
0x18004efc6  xor     r15d, r15d
0x18004efc9  test    eax, eax
0x18004efcb  js      loc_18004FCBD
0x18004efd1  mov     rcx, rsi; lpCriticalSection
0x18004efd4  call    cs:__imp_EnterCriticalSection
0x18004efdb  nop     dword ptr [rax+rax+00h]
0x18004efe0  mov     [rbp+12B0h+var_11B8], rsi
0x18004efe7  mov     rdx, r13; unsigned __int16 *
0x18004efea  mov     rcx, rsi; this
0x18004efed  call    ?PerformExistingContainerChecks@ProvisioningHandler@@AEAAJPEBG@Z; ProvisioningHandler::PerformExistingContainerChecks(ushort const *)
0x18004eff2  mov     ebx, eax
0x18004eff4  mov     [rsp+13B0h+var_134C], eax
0x18004eff8  test    eax, eax
0x18004effa  js      loc_18004FCAD
0x18004f000  mov     [rsp+13B0h+var_1338], r15
0x18004f005  mov     rbx, [rsi+68h]
0x18004f009  xor     edx, edx
0x18004f00b  lea     rcx, [rsp+13B0h+var_1338]
0x18004f010  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004f015  lea     rcx, [rsp+13B0h+var_1338]
0x18004f01a  mov     rax, rbx
0x18004f01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f022  mov     [rsp+13B0h+var_134C], eax
0x18004f026  test    eax, eax
0x18004f028  jns     short loc_18004F069
0x18004f02a  mov     eax, cs:dword_1800BE0B8
0x18004f030  cmp     eax, 2
0x18004f033  jbe     short loc_18004F060
0x18004f035  mov     eax, [rsp+13B0h+var_134C]
0x18004f039  mov     [rsp+13B0h+var_1348], eax
0x18004f03d  lea     rax, [rsp+13B0h+var_1348]
0x18004f042  mov     [rsp+13B0h+ppv], rax
0x18004f047  xor     r9d, r9d
0x18004f04a  xor     r8d, r8d
0x18004f04d  lea     rdx, byte_1800AC2C9
0x18004f054  lea     rcx, dword_1800BE0B8
0x18004f05b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004f060  mov     ebx, [rsp+13B0h+var_134C]
0x18004f064  jmp     loc_18004FCA2
0x18004f069  mov     [rsp+13B0h+var_1340], r15
0x18004f06e  lea     rcx, [rsp+13B0h+var_1340]
0x18004f073  mov     rax, [rsi+70h]
0x18004f077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f07c  mov     [rsp+13B0h+var_134C], eax
0x18004f080  test    eax, eax
0x18004f082  jns     short loc_18004F0D0
0x18004f084  mov     eax, cs:dword_1800BE0B8
0x18004f08a  cmp     eax, 2
0x18004f08d  jbe     short loc_18004F0C7
0x18004f08f  lea     rbx, _GUID_1bd3ac02_7468_49c8_80cf_a138ecb84317
0x18004f096  mov     [rbp+12B0h+var_940], rbx
0x18004f09d  mov     eax, [rsp+13B0h+var_134C]
0x18004f0a1  mov     [rsp+13B0h+var_1348], eax
0x18004f0a5  lea     rax, [rbp+12B0h+var_940]
0x18004f0ac  mov     [rsp+13B0h+pvData], rax
0x18004f0b1  lea     rax, [rsp+13B0h+var_1348]
0x18004f0b6  mov     [rsp+13B0h+ppv], rax
0x18004f0bb  lea     rdx, byte_1800AC28B
0x18004f0c2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004f0c7  mov     ebx, [rsp+13B0h+var_134C]
0x18004f0cb  jmp     loc_18004FC97
0x18004f0d0  mov     [rbp+12B0h+var_12B0], r15
0x18004f0d4  mov     [rbp+12B0h+var_12B8], r15
0x18004f0d8  mov     r12d, 2
0x18004f0de  mov     [rbp+12B0h+var_131C], r12d
0x18004f0e2  mov     [rsp+13B0h+var_1344], r15b
0x18004f0e7  mov     [rbp+12B0h+var_12E0], r15
0x18004f0eb  lea     rdx, [rbp+12B0h+var_12E0]
0x18004f0ef  xor     ecx, ecx
0x18004f0f1  call    cs:__imp_DsrGetJoinInfo
0x18004f0f8  nop     dword ptr [rax+rax+00h]
0x18004f0fd  mov     [rsp+13B0h+var_134C], eax
0x18004f101  test    eax, eax
0x18004f103  jns     short loc_18004F14D
0x18004f105  mov     eax, cs:dword_1800BE0B8
0x18004f10b  cmp     eax, r12d
0x18004f10e  jbe     short loc_18004F13B
0x18004f110  mov     eax, [rsp+13B0h+var_134C]
0x18004f114  mov     [rsp+13B0h+var_1348], eax
0x18004f118  lea     rax, [rsp+13B0h+var_1348]
0x18004f11d  mov     [rsp+13B0h+ppv], rax
0x18004f122  xor     r9d, r9d
0x18004f125  xor     r8d, r8d
  ... truncated ...
```
