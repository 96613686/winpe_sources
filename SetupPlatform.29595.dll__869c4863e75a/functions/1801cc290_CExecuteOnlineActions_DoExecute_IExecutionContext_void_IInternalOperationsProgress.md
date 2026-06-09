# CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)

- ea: `0x1801cc290`
- end: `0x1801cd18a`
- name: `?DoExecute@CExecuteOnlineActions@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z`
- size: `3834`
- prototype: `void __fastcall __noreturn(CExecuteOnlineActions *__hidden this, struct IExecutionContext *, void *, struct IInternalOperationsProgress *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x18001413d`
- `0x180057dec`
- `0x1801cc290`
- `0x1802d8bfc`
- `0x1802db0f8`
- `0x1802e2078`
- `0x180423cdc`
- `0x18045dd10`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1801cc523`
- `ADVAPI32!RegCloseKey` at `0x1801ccb7d`
- `ADVAPI32!RegCloseKey` at `0x1801cc523`
- `ADVAPI32!RegCloseKey` at `0x1801ccb7d`
- `ADVAPI32!RegSetValueExW` at `0x1801ccb70`
- `ADVAPI32!RegSetValueExW` at `0x1801ccb70`
- `ADVAPI32!RegCreateKeyExW` at `0x1801ccb42`
- `ADVAPI32!RegCreateKeyExW` at `0x1801ccb42`
- `ADVAPI32!RegOpenKeyExW` at `0x1801cc4fe`
- `ADVAPI32!RegOpenKeyExW` at `0x1801cc4fe`
- `ADVAPI32!RegDeleteValueW` at `0x1801cc516`
- `ADVAPI32!RegDeleteValueW` at `0x1801cc516`
- `KERNEL32!GetLastError` at `0x1801cc379`
- `KERNEL32!GetLastError` at `0x1801cc44a`
- `KERNEL32!GetLastError` at `0x1801cc569`
- `KERNEL32!GetLastError` at `0x1801cc5fd`
- `KERNEL32!GetLastError` at `0x1801cc68a`
- `KERNEL32!GetLastError` at `0x1801cc71f`
- `KERNEL32!GetLastError` at `0x1801cc804`
- `KERNEL32!GetLastError` at `0x1801cc87c`
- `KERNEL32!GetLastError` at `0x1801cc921`
- `KERNEL32!GetLastError` at `0x1801cca7e`
- `KERNEL32!GetLastError` at `0x1801ccbbd`
- `KERNEL32!GetLastError` at `0x1801ccc5e`
- `KERNEL32!GetLastError` at `0x1801ccced`
- `KERNEL32!GetLastError` at `0x1801ccd00`
- `KERNEL32!GetLastError` at `0x1801ccd1c`
- `KERNEL32!GetLastError` at `0x1801ccdab`
- `KERNEL32!GetLastError` at `0x1801cce3a`
- `KERNEL32!GetLastError` at `0x1801ccecb`
- `KERNEL32!GetLastError` at `0x1801ccf5a`
- `KERNEL32!GetLastError` at `0x1801cd068`
- `KERNEL32!GetLastError` at `0x1801cd07e`
- `KERNEL32!GetLastError` at `0x1801cd09e`
- `KERNEL32!GetLastError` at `0x1801cc379`
- `KERNEL32!GetLastError` at `0x1801cc44a`
- `KERNEL32!GetLastError` at `0x1801cc569`
- `KERNEL32!GetLastError` at `0x1801cc5fd`
- `KERNEL32!GetLastError` at `0x1801cc68a`
- `KERNEL32!GetLastError` at `0x1801cc71f`
- `KERNEL32!GetLastError` at `0x1801cc804`
- `KERNEL32!GetLastError` at `0x1801cc87c`
- `KERNEL32!GetLastError` at `0x1801cc921`
- `KERNEL32!GetLastError` at `0x1801cca7e`
- `KERNEL32!GetLastError` at `0x1801ccbbd`
- `KERNEL32!GetLastError` at `0x1801ccc5e`
- `KERNEL32!GetLastError` at `0x1801ccced`
- `KERNEL32!GetLastError` at `0x1801ccd00`
- `KERNEL32!GetLastError` at `0x1801ccd1c`
- `KERNEL32!GetLastError` at `0x1801ccdab`
- `KERNEL32!GetLastError` at `0x1801cce3a`
- `KERNEL32!GetLastError` at `0x1801ccecb`
- `KERNEL32!GetLastError` at `0x1801ccf5a`
- `KERNEL32!GetLastError` at `0x1801cd068`
- `KERNEL32!GetLastError` at `0x1801cd07e`
- `KERNEL32!GetLastError` at `0x1801cd09e`
- `KERNEL32!SetLastError` at `0x1801cc52b`
- `KERNEL32!SetLastError` at `0x1801ccb85`
- `KERNEL32!SetLastError` at `0x1801cc52b`
- `KERNEL32!SetLastError` at `0x1801ccb85`
- `ole32!CoInitializeSecurity` at `0x1801cc351`
- `ole32!CoInitializeSecurity` at `0x1801cc351`
- `ole32!CoCreateInstance` at `0x1801cc70d`
- `ole32!CoCreateInstance` at `0x1801cc70d`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801cc2f7`
- `unbcl!??0Exception@UnBCL@@QEAA@XZ` at `0x1801cc2f7`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801cc9c5`
- `unbcl!?Combine@Path@UnBCL@@SAPEAVString@2@PEBV32@0@Z` at `0x1801cc9c5`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801ccba0`
- `unbcl!??1Exception@UnBCL@@UEAA@XZ` at `0x1801ccba0`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1801cca5c`
- `unbcl!?Compare@String@UnBCL@@SAHPEBV12@0H@Z` at `0x1801cca5c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801cc431`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801cc66c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801cca4a`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801cc431`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801cc66c`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x1801cca4a`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801cc9e5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801cca6c`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801cc9e5`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1801cca6c`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801cc9a0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801cca39`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801cc9a0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1801cca39`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801cc9f3`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1801cc9f3`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801cc9fc`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1801cc9fc`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801cd139`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801cd148`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801cd139`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1801cd148`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801cc9d6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801cca23`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801cc9d6`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1801cca23`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc3f1`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc4a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc5c3`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc657`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc6e6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc776`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc86b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc8d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc97b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccad8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccc28`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cccbb`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccd79`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cce08`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cce99`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccf28`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccfb7`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cd035`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cd0fb`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc3f1`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc4a4`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc5c3`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc657`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc6e6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc776`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc86b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc8d6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cc97b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccad8`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccc28`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cccbb`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccd79`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cce08`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cce99`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccf28`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801ccfb7`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cd035`
- `WDSCORE!WdsSetupLogMessageW` at `0x1801cd0fb`
- `WDSCORE!CurrentIP` at `0x1801cc381`
- `WDSCORE!CurrentIP` at `0x1801cc452`
- `WDSCORE!CurrentIP` at `0x1801cc571`
- `WDSCORE!CurrentIP` at `0x1801cc605`
- `WDSCORE!CurrentIP` at `0x1801cc692`
- `WDSCORE!CurrentIP` at `0x1801cc727`
- `WDSCORE!CurrentIP` at `0x1801cc80c`
- `WDSCORE!CurrentIP` at `0x1801cc884`
- `WDSCORE!CurrentIP` at `0x1801cc929`
- `WDSCORE!CurrentIP` at `0x1801cca86`
- `WDSCORE!CurrentIP` at `0x1801ccbc6`
- `WDSCORE!CurrentIP` at `0x1801ccc66`
- `WDSCORE!CurrentIP` at `0x1801ccd24`
- `WDSCORE!CurrentIP` at `0x1801ccdb3`
- `WDSCORE!CurrentIP` at `0x1801cce42`
- `WDSCORE!CurrentIP` at `0x1801cced3`
- `WDSCORE!CurrentIP` at `0x1801ccf62`
- `WDSCORE!CurrentIP` at `0x1801cd0a6`
- `WDSCORE!CurrentIP` at `0x1801cc381`
- `WDSCORE!CurrentIP` at `0x1801cc452`
- `WDSCORE!CurrentIP` at `0x1801cc571`
- `WDSCORE!CurrentIP` at `0x1801cc605`
- `WDSCORE!CurrentIP` at `0x1801cc692`
- `WDSCORE!CurrentIP` at `0x1801cc727`
- `WDSCORE!CurrentIP` at `0x1801cc80c`
- `WDSCORE!CurrentIP` at `0x1801cc884`
- `WDSCORE!CurrentIP` at `0x1801cc929`
- `WDSCORE!CurrentIP` at `0x1801cca86`
- `WDSCORE!CurrentIP` at `0x1801ccbc6`
- `WDSCORE!CurrentIP` at `0x1801ccc66`
- `WDSCORE!CurrentIP` at `0x1801ccd24`
- `WDSCORE!CurrentIP` at `0x1801ccdb3`
- `WDSCORE!CurrentIP` at `0x1801cce42`
- `WDSCORE!CurrentIP` at `0x1801cced3`
- `WDSCORE!CurrentIP` at `0x1801ccf62`
- `WDSCORE!CurrentIP` at `0x1801cd0a6`

## string_xrefs

- `0x1801cc394`: `%hs: Failed to initialize COM security. hr = 0x%08X`
- `0x1801ccbd2`: `CExecuteOnlineActions::DoExecute: Failed to initialize COM. Error: 0x%08X`
- `0x1801ccd30`: `CExecuteOnlineActions::DoExecute: Failed to delete Respecialize registry value. Error: 0x%08X`
- `0x1801cce50`: `Failed to create CBS session 10. hr = 0x%08X`
- `0x1801cd0b2`: `Failed to set shutdown suppression registry value. Error: 0x%08X`
- `0x1801cca8f`: `Ignoring reboot request per external configuration`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall __noreturn CExecuteOnlineActions::DoExecute(
        CExecuteOnlineActions *this,
        struct IExecutionContext *a2,
        void *a3,
        struct IInternalOperationsProgress *a4)
{
  struct IExecutionContext *v4; // rbx
  int v5; // esi
  HRESULT v6; // esi
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  struct UnBCL::String *P; // rax
  int v11; // r8d
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  signed int v20; // esi
  LSTATUS v21; // ebx
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  struct UnBCL::String *v28; // rax
  int v29; // r8d
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  int v36; // esi
  int v37; // esi
  DWORD v38; // edi
  __int64 v39; // rbx
  struct tagLOG_PARTIAL_MSG *v40; // rax
  DWORD v41; // edi
  __int64 v42; // rbx
  struct tagLOG_PARTIAL_MSG *v43; // rax
  int v44; // eax
  int v45; // ebx
  DWORD v46; // edi
  __int64 v47; // rbx
  struct tagLOG_PARTIAL_MSG *v48; // rax
  const struct UnBCL::String *v49; // rdi
  const struct UnBCL::String *v50; // rax
  struct UnBCL::String *v51; // rax
  UnBCL::String *v52; // rax
  const WCHAR *CString; // rax
  struct UnBCL::String *v54; // rax
  const struct UnBCL::String *v55; // rdi
  const struct UnBCL::String *v56; // rax
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  LSTATUS v60; // ebx
  DWORD LastError; // edi
  __int64 v62; // rbx
  struct tagLOG_PARTIAL_MSG *v63; // rax
  DWORD v64; // edi
  __int64 v65; // rbx
  struct tagLOG_PARTIAL_MSG *v66; // rax
  signed int v67; // eax
  bool v68; // sf
  signed int v69; // eax
  unsigned int v70; // esi
  DWORD v71; // edi
  __int64 v72; // rbx
  struct tagLOG_PARTIAL_MSG *v73; // rax
  DWORD v74; // edi
  __int64 v75; // rbx
  struct tagLOG_PARTIAL_MSG *v76; // rax
  DWORD v77; // edi
  __int64 v78; // rbx
  struct tagLOG_PARTIAL_MSG *v79; // rax
  DWORD v80; // edi
  __int64 v81; // rbx
  struct tagLOG_PARTIAL_MSG *v82; // rax
  DWORD v83; // edi
  __int64 v84; // rbx
  struct tagLOG_PARTIAL_MSG *v85; // rax
  struct tagLOG_PARTIAL_MSG *v86; // rax
  signed int v87; // eax
  bool v88; // sf
  signed int v89; // eax
  unsigned int v90; // esi
  DWORD v91; // edi
  __int64 v92; // rbx
  struct tagLOG_PARTIAL_MSG *v93; // rax
  __int64 *v94; // rbp
  __int64 v95; // rcx
  __int64 *v96; // rdx
  __int64 v97; // [rsp+0h] [rbp-198h] BYREF
  DWORD dwAuthnLevel[2]; // [rsp+20h] [rbp-178h]
  DWORD dwImpLevel[2]; // [rsp+28h] [rbp-170h]
  HRESULT v100; // [rsp+60h] [rbp-138h]
  HKEY hKey; // [rsp+68h] [rbp-130h] BYREF
  int v102; // [rsp+70h] [rbp-128h]
  HKEY phkResult; // [rsp+78h] [rbp-120h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-118h] BYREF
  int v105; // [rsp+88h] [rbp-110h] BYREF
  _QWORD v106[2]; // [rsp+90h] [rbp-108h] BYREF
  _QWORD *pExceptionObject; // [rsp+A0h] [rbp-F8h] BYREF
  _QWORD *v108; // [rsp+A8h] [rbp-F0h] BYREF
  _QWORD *v109; // [rsp+B0h] [rbp-E8h] BYREF
  _QWORD *v110; // [rsp+B8h] [rbp-E0h] BYREF
  _QWORD *v111; // [rsp+C0h] [rbp-D8h] BYREF
  _QWORD *v112; // [rsp+C8h] [rbp-D0h] BYREF
  _QWORD *v113; // [rsp+D0h] [rbp-C8h] BYREF
  _QWORD *v114; // [rsp+D8h] [rbp-C0h] BYREF
  _QWORD *v115; // [rsp+E0h] [rbp-B8h] BYREF
  _QWORD *v116; // [rsp+E8h] [rbp-B0h] BYREF
  _QWORD v117[7]; // [rsp+F0h] [rbp-A8h] BYREF
  _BYTE v118[16]; // [rsp+128h] [rbp-70h] BYREF
  _BYTE v119[24]; // [rsp+138h] [rbp-60h] BYREF
  __int64 v120; // [rsp+150h] [rbp-48h]
  struct IExecutionContext *dwDisposition; // [rsp+1A8h] [rbp+10h] BYREF
  void *v123; // [rsp+1B0h] [rbp+18h]

  v123 = a3;
  dwDisposition = a2;
  v120 = -2;
  v4 = a2;
  v105 = 0;
  v106[0] = (*(__int64 (__fastcall **)(struct IExecutionContext *, struct IExecutionContext *, void *, struct IInternalOperationsProgress *))(*(_QWORD *)a2 + 64LL))(
              a2,
              a2,
              a3,
              a4);
  v102 = 0;
  ppv = 0;
  LODWORD(hKey) = 0;
  UnBCL::Exception::Exception((UnBCL::Exception *)v117);
  v117[0] = &`CExecuteOnlineActions::DoExecute'::`3'::CXXXXXHandledException::`vftable';
  try
  {
    try
    {
      v5 = SPInitializeCOM(&v105);
      v100 = v5;
      if ( v5 < 0 )
      {
        LastError = GetLastError();
        v62 = CurrentIP();
        v63 = ConstructPartialMsgW(
                0x2000000u,
                "CExecuteOnlineActions::DoExecute: Failed to initialize COM. Error: 0x%08X",
                v5);
        WdsSetupLogMessageW(
          v63,
          819200,
          L"D",
          0,
          702,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v62,
          LastError,
          0,
          0);
        LODWORD(hKey) = 1;
        pExceptionObject = v117;
        throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&pExceptionObject;
      }
      v6 = CoInitializeSecurity(0, -1, 0, 0, 5u, 3u, 0, 0, 0);
      v100 = v6;
      if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147417831 )
      {
        v7 = GetLastError();
        v8 = CurrentIP();
        v9 = ConstructPartialMsgW(
               0x4000000u,
               "%hs: Failed to initialize COM security. hr = 0x%08X",
               "CExecuteOnlineActions::DoExecute",
               v6);
        WdsSetupLogMessageW(
          v9,
          819200,
          L"D",
          0,
          719,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v8,
          v7,
          0,
          0);
        v6 = 0;
        v100 = 0;
        v4 = dwDisposition;
      }
      P = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 208);
      if ( (unsigned int)SPGetStoredBOOL(v4, P, v11) )
      {
        v12 = GetLastError();
        v13 = CurrentIP();
        v14 = ConstructPartialMsgW(0x4000000u, "Executing Respecialize actions.");
        WdsSetupLogMessageW(
          v14,
          819200,
          L"D",
          0,
          726,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v13,
          v12,
          0,
          0);
        v19 = RunPlatformActions(v16, v15, v17, v18, dwAuthnLevel[0], dwImpLevel[0], v123);
        v20 = v19;
        if ( v19 > 0 )
          v20 = (unsigned __int16)v19 | 0x80070000;
        if ( v20 < 0 )
        {
          v100 = v20;
          v64 = GetLastError();
          v65 = CurrentIP();
          v66 = ConstructPartialMsgW(
                  0x2000000u,
                  "CExecuteOnlineActions::DoExecute: Failed while running Respecialize phase. Error: 0x%08X",
                  v20);
          WdsSetupLogMessageW(
            v66,
            819200,
            L"D",
            0,
            731,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v65,
            v64,
            0,
            0);
          LODWORD(hKey) = 1;
          v108 = v117;
          throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v108;
        }
        phkResult = 0;
        v21 = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\Sysprep",
                0,
                0x20006u,
                &phkResult);
        if ( !v21 )
        {
          v21 = RegDeleteValueW(phkResult, L"RespecializePending");
          RegCloseKey(phkResult);
        }
        SetLastError(v21);
        if ( v21 )
        {
          v67 = GetLastError();
          v68 = v67 < 0;
          if ( v67 > 0 )
            v68 = 1;
          if ( v68 )
          {
            v69 = GetLastError();
            v70 = v69;
            if ( v69 > 0 )
              v70 = (unsigned __int16)v69 | 0x80070000;
          }
          else
          {
            v70 = -2147467259;
          }
          v100 = v70;
          v71 = GetLastError();
          v72 = CurrentIP();
          v73 = ConstructPartialMsgW(
                  0x2000000u,
                  "CExecuteOnlineActions::DoExecute: Failed to delete Respecialize registry value. Error: 0x%08X",
                  v70);
          WdsSetupLogMessageW(
            v73,
            819200,
            L"D",
            0,
            738,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v72,
            v71,
            0,
            0);
          LODWORD(hKey) = 1;
          v109 = v117;
          throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v109;
        }
        LODWORD(phkResult) = 0;
        v6 = OrchestrateWillShutdownBeforeLogon(&phkResult);
        v100 = v6;
        if ( v6 < 0 )
        {
          v74 = GetLastError();
          v75 = CurrentIP();
          v76 = ConstructPartialMsgW(
                  0x2000000u,
                  "CExecuteOnlineActions::DoExecute: Failed to determine whether system will reboot. Error: 0x%08X",
                  v6);
          WdsSetupLogMessageW(
            v76,
            819200,
            L"D",
            0,
            746,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v75,
            v74,
            0,
            0);
          LODWORD(hKey) = 1;
          v110 = v117;
          throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v110;
        }
        v102 = (int)phkResult;
        if ( (_DWORD)phkResult )
        {
          v22 = GetLastError();
          v23 = CurrentIP();
          v24 = ConstructPartialMsgW(0x4000000u, "Respecialize requested immediate reboot");
          WdsSetupLogMessageW(
            v24,
            819200,
            L"D",
            0,
            752,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v23,
            v22,
            0,
            0);
          if ( v106[0] )
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v106[0] + 16LL))(
              v106[0],
              L"SP_SECONDBOOT_INFO",
              L"RespecializeReboot",
              L"True");
        }
      }
      else
      {
        v25 = GetLastError();
        v26 = CurrentIP();
        v27 = ConstructPartialMsgW(0x4000000u, "Respecialize does not need to run online");
        WdsSetupLogMessageW(
          v27,
          819200,
          L"D",
          0,
          767,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v26,
          v25,
          0,
          0);
      }
      v28 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P((char *)this + 224);
      if ( (unsigned int)SPGetStoredBOOL(dwDisposition, v28, v29) )
      {
        v30 = GetLastError();
        v31 = CurrentIP();
        v32 = ConstructPartialMsgW(0x4000000u, "Executing postponed CBS online actions");
        WdsSetupLogMessageW(
          v32,
          819200,
          L"D",
          0,
          772,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v31,
          v30,
          0,
          0);
        v100 = CoCreateInstance(&CLSID_CbsSession, 0, 0x15u, &GUID_f112757a_565b_4260_bd05_9fa34417349a, &ppv);
        if ( v100 < 0 )
        {
          v77 = GetLastError();
          v78 = CurrentIP();
          v79 = ConstructPartialMsgW(0x2000000u, "Failed to create CBS session 10. hr = 0x%08X", v100);
          WdsSetupLogMessageW(
            v79,
            819200,
            L"D",
            0,
            784,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v78,
            v77,
            0,
            0);
          LODWORD(hKey) = 1;
          v111 = v117;
          throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v111;
        }
        v33 = GetLastError();
        v34 = CurrentIP();
        v35 = ConstructPartialMsgW(0x4000000u, "Initializing the ICbsSession10 interface");
        WdsSetupLogMessageW(
          v35,
          819200,
          L"D",
          0,
          789,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v34,
          v33,
          0,
          0);
        v36 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                0,
                L"Setup Platform",
                0,
                0);
        v100 = v36;
        if ( v36 < 0 )
        {
          v80 = GetLastError();
          v81 = CurrentIP();
          v82 = ConstructPartialMsgW(0x2000000u, "Failed to initialize the CBS session. hr = 0x%08X", v36);
          WdsSetupLogMessageW(
            v82,
            819200,
            L"D",
            0,
            793,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v81,
            v80,
            0,
            0);
          LODWORD(hKey) = 1;
          v112 = v117;
          throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v112;
        }
        v37 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 184LL))(ppv, 2);
        v100 = v37;
        if ( v37 < 0 )
        {
          v83 = GetLastError();
          v84 = CurrentIP();
          v85 = ConstructPartialMsgW(0x2000000u, "Failed to set enhanced options. hr = 0x%08X", v37);
          WdsSetupLogMessageW(
            v85,
            819200,
            L"D",
            0,
            802,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v84,
            v83,
            0,
            0);
          LODWORD(hKey) = 1;
          v113 = v117;
          throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v113;
        }
        LODWORD(phkResult) = 0;
        v6 = (*(__int64 (__fastcall **)(LPVOID, HKEY *))(*(_QWORD *)ppv + 32LL))(ppv, &phkResult);
        v100 = v6;
        v38 = GetLastError();
        v39 = CurrentIP();
        if ( v6 < 0 )
        {
          v86 = ConstructPartialMsgW(0x2000000u, "Failed to call finalize. hr = 0x%08X", v6);
          WdsSetupLogMessageW(
            v86,
            819200,
            L"D",
            0,
            811,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v39,
            v38,
            0,
            0);
          LODWORD(hKey) = 1;
          v114 = v117;
          throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v114;
        }
        v40 = ConstructPartialMsgW(0x4000000u, "Finalize result: %d", (_DWORD)phkResult);
        WdsSetupLogMessageW(
          v40,
          819200,
          L"D",
          0,
          815,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v39,
          v38,
          0,
          0);
        if ( (_DWORD)phkResult == 1 )
        {
          v41 = GetLastError();
          v42 = CurrentIP();
          v43 = ConstructPartialMsgW(0x4000000u, "CBS online actions requested immediate reboot");
          WdsSetupLogMessageW(
            v43,
            819200,
            L"D",
            0,
            821,
            L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
            L"CExecuteOnlineActions::DoExecute",
            v42,
            v41,
            0,
            0);
          if ( v106[0] )
            (*(void (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, const wchar_t *))(*(_QWORD *)v106[0] + 16LL))(
              v106[0],
              L"SP_SECONDBOOT_INFO",
              L"PreOOBECbsOnlineReboot",
              L"True");
          v44 = 1;
        }
        else
        {
          v44 = 0;
        }
        v45 = v102;
        if ( v102 )
        {
LABEL_33:
          v49 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v119, L"SetupPlatform.ini");
          v50 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(struct IExecutionContext *))dwDisposition)(dwDisposition);
          v51 = UnBCL::Path::Combine(v50, v49);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v118, v51);
          UnBCL::String::~String((UnBCL::String *)v119);
          v52 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v118);
          CString = UnBCL::String::get_CString(v52);
          v54 = SPReadConfigValue(L"Parameters", L"SuppressOnlineReboot", CString);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v106, v54);
          v55 = (const struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v119, L"Yes");
          v56 = (const struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v106);
          LODWORD(v55) = UnBCL::String::Compare(v56, v55, 1);
          UnBCL::String::~String((UnBCL::String *)v119);
          if ( !(_DWORD)v55 )
          {
            v102 = 0;
            v57 = GetLastError();
            v58 = CurrentIP();
            v59 = ConstructPartialMsgW(0x4000000u, "Ignoring reboot request per external configuration");
            WdsSetupLogMessageW(
              v59,
              819200,
              L"D",
              0,
              851,
              L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
              L"CExecuteOnlineActions::DoExecute",
              v58,
              v57,
              0,
              0);
            LODWORD(phkResult) = 1;
            hKey = 0;
            LODWORD(dwDisposition) = 0;
            v60 = RegCreateKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"SYSTEM\\Setup",
                    0,
                    (LPWSTR)&Class,
                    0,
                    0x20006u,
                    0,
                    &hKey,
                    (LPDWORD)&dwDisposition);
            if ( !v60 )
            {
              v60 = RegSetValueExW(hKey, L"SetupShutdownSuppressed", 0, 4u, (const BYTE *)&phkResult, 4u);
              RegCloseKey(hKey);
            }
            SetLastError(v60);
            if ( v60 )
            {
              v87 = GetLastError();
              v88 = v87 < 0;
              if ( v87 > 0 )
                v88 = 1;
              if ( v88 )
              {
                v89 = GetLastError();
                v90 = v89;
                if ( v89 > 0 )
                  v90 = (unsigned __int16)v89 | 0x80070000;
              }
              else
              {
                v90 = -2147467259;
              }
              v100 = v90;
              v91 = GetLastError();
              v92 = CurrentIP();
              v93 = ConstructPartialMsgW(
                      0x2000000u,
                      "Failed to set shutdown suppression registry value. Error: 0x%08X",
                      v90);
              WdsSetupLogMessageW(
                v93,
                819200,
                L"D",
                0,
                856,
                L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
                L"CExecuteOnlineActions::DoExecute",
                v92,
                v91,
                0,
                0);
              LODWORD(hKey) = 1;
              v115 = v117;
              throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v115;
            }
            v45 = v102;
          }
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v106);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v118);
          if ( v45 )
            v6 = 3010;
          v100 = v6;
          goto LABEL_72;
        }
        v102 = v44;
      }
      else
      {
        v46 = GetLastError();
        v47 = CurrentIP();
        v48 = ConstructPartialMsgW(0x4000000u, "CBS online actions were not postponed, CBS does not need to run online");
        WdsSetupLogMessageW(
          v48,
          819200,
          L"D",
          0,
          836,
          L"base\\ntsetup\\setupplatform\\lib\\src\\sysprep.cpp",
          L"CExecuteOnlineActions::DoExecute",
          v47,
          v46,
          0,
          0);
        v44 = v102;
      }
      if ( !v44 )
        goto LABEL_72;
      v45 = v102;
      goto LABEL_33;
    }
    catch ( UEAAJPEAUIExecutionContext:: )
    {
      CExecuteOnlineActions::DoExecute_::_1_::catch_8();
      __eh34_caught_type(
        1,
        UEAAJPEAUIExecutionContext::`CExecuteOnlineActions::DoExecute'::`4'::CXXXXXTemp * `RTTI Type Descriptor');
    }
LABEL_72:
    LODWORD(hKey) = 1;
    v116 = v117;
    throw (`CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException **)&v116;
  }
  catch ( UnBCL::Exception * )
  {
    v96 = &v97;
    v94 = v96;
    v95 = v96[16];
    if ( v95 )
    {
      (*(void (**)(void))(*(_QWORD *)v95 + 16LL))();
      v94[16] = 0;
    }
    if ( *((_DWORD *)v94 + 34) )
      CoUninitialize();
    if ( !*((_DWORD *)v94 + 26) )
      throw;
    UnBCL::Exception::~Exception((UnBCL::Exception *)v117);
  }
}

```

## disassembly

```asm
0x1801cc290  mov     rax, rsp
0x1801cc293  mov     [rax+18h], r8
0x1801cc297  mov     [rax+10h], rdx
0x1801cc29b  mov     [rax+8], rcx
0x1801cc29f  push    rbx
0x1801cc2a0  push    rsi
0x1801cc2a1  push    rdi
0x1801cc2a2  push    r12
0x1801cc2a4  push    r13
0x1801cc2a6  push    r14
0x1801cc2a8  push    r15
0x1801cc2aa  sub     rsp, 160h
0x1801cc2b1  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1801cc2b9  mov     rbx, rdx
0x1801cc2bc  xor     r14d, r14d
0x1801cc2bf  mov     [rax-110h], r14d
0x1801cc2c6  mov     rax, [rdx]
0x1801cc2c9  mov     rcx, rdx
0x1801cc2cc  mov     rax, [rax+40h]
0x1801cc2d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc2d5  mov     [rsp+198h+var_108], rax
0x1801cc2dd  mov     [rsp+198h+var_128], r14d
0x1801cc2e2  mov     [rsp+198h+ppv], r14
0x1801cc2ea  mov     dword ptr [rsp+198h+hKey], r14d
0x1801cc2ef  lea     rcx, [rsp+198h+var_A8]
0x1801cc2f7  call    cs:__imp_??0Exception@UnBCL@@QEAA@XZ; UnBCL::Exception::Exception(void)
0x1801cc2fd  lea     rax, ??_7CXXXXXHandledException@?2??DoExecute@CExecuteOnlineActions@@UEAAJPEAUIExecutionContext@@PEAXPEAUIInternalOperationsProgress@@@Z@6B@; const `CExecuteOnlineActions::DoExecute(IExecutionContext *,void *,IInternalOperationsProgress *)'::`3'::CXXXXXHandledException::`vftable'
0x1801cc304  mov     [rsp+198h+var_A8], rax
0x1801cc30c  lea     rcx, [rsp+198h+var_110]; int *
0x1801cc314  call    ?SPInitializeCOM@@YAJAEAH@Z; SPInitializeCOM(int &)
0x1801cc319  mov     esi, eax
0x1801cc31b  mov     [rsp+198h+var_138], eax
0x1801cc31f  test    eax, eax
0x1801cc321  js      loc_1801CCBBD
0x1801cc327  mov     [rsp+198h+pReserved3], r14; pReserved3
0x1801cc32c  mov     [rsp+198h+dwCapabilities], r14d; dwCapabilities
0x1801cc331  mov     [rsp+198h+pAuthList], r14; pAuthList
0x1801cc336  mov     [rsp+198h+dwImpLevel], 3; dwImpLevel
0x1801cc33e  mov     [rsp+198h+dwAuthnLevel], 5; dwAuthnLevel
0x1801cc346  xor     r9d, r9d; pReserved1
0x1801cc349  xor     r8d, r8d; asAuthSvc
0x1801cc34c  or      edx, 0FFFFFFFFh; cAuthSvc
0x1801cc34f  xor     ecx, ecx; pSecDesc
0x1801cc351  call    cs:__imp_CoInitializeSecurity
0x1801cc357  mov     esi, eax
0x1801cc359  mov     [rsp+198h+var_138], eax
0x1801cc35d  mov     eax, 80000000h
0x1801cc362  lea     ecx, [rsi+rax]
0x1801cc365  test    eax, ecx
0x1801cc367  jnz     loc_1801CC407
0x1801cc36d  cmp     esi, 80010119h
0x1801cc373  jz      loc_1801CC407
0x1801cc379  call    cs:__imp_GetLastError
0x1801cc37f  mov     edi, eax
0x1801cc381  call    cs:__imp_CurrentIP
0x1801cc387  mov     rbx, rax
0x1801cc38a  mov     r9d, esi
0x1801cc38d  lea     r8, aCexecuteonline_0; "CExecuteOnlineActions::DoExecute"
0x1801cc394  lea     rdx, aHsFailedToInit_7; "%hs: Failed to initialize COM security."...
0x1801cc39b  mov     ecx, 4000000h; unsigned int
0x1801cc3a0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801cc3a5  mov     [rsp+198h+var_148], r14d
0x1801cc3aa  mov     [rsp+198h+var_150], r14
0x1801cc3af  mov     dword ptr [rsp+198h+pReserved3], edi
0x1801cc3b3  mov     qword ptr [rsp+198h+dwCapabilities], rbx
0x1801cc3b8  lea     r12, aCexecuteonline_2; "CExecuteOnlineActions::DoExecute"
0x1801cc3bf  mov     [rsp+198h+pAuthList], r12
0x1801cc3c4  lea     r13, aBaseNtsetupSet_5; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801cc3cb  mov     qword ptr [rsp+198h+dwImpLevel], r13
0x1801cc3d0  mov     [rsp+198h+dwAuthnLevel], 2CFh
0x1801cc3d8  xor     r9d, r9d
0x1801cc3db  lea     r14, aD_0; "D"
0x1801cc3e2  mov     r8, r14
0x1801cc3e5  mov     r15d, 0C8000h
0x1801cc3eb  mov     edx, r15d
0x1801cc3ee  mov     rcx, rax
0x1801cc3f1  call    cs:__imp_WdsSetupLogMessageW
0x1801cc3f7  xor     esi, esi
0x1801cc3f9  mov     [rsp+198h+var_138], esi
0x1801cc3fd  mov     rbx, [rsp+198h+dwDisposition]
0x1801cc405  jmp     short loc_1801CC422
0x1801cc407  lea     r12, aCexecuteonline_2; "CExecuteOnlineActions::DoExecute"
0x1801cc40e  lea     r13, aBaseNtsetupSet_5; "base\\ntsetup\\setupplatform\\lib\\src"...
0x1801cc415  lea     r14, aD_0; "D"
0x1801cc41c  mov     r15d, 0C8000h
0x1801cc422  mov     rcx, [rsp+198h+arg_0]
0x1801cc42a  add     rcx, 0D0h
0x1801cc431  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801cc437  mov     rdx, rax; struct UnBCL::String *
0x1801cc43a  mov     rcx, rbx; struct IExecutionContext *
0x1801cc43d  call    ?SPGetStoredBOOL@@YAHPEAUIExecutionContext@@PEAVString@UnBCL@@H@Z; SPGetStoredBOOL(IExecutionContext *,UnBCL::String *,int)
0x1801cc442  test    eax, eax
0x1801cc444  jz      loc_1801CC5FD
0x1801cc44a  call    cs:__imp_GetLastError
0x1801cc450  mov     edi, eax
0x1801cc452  call    cs:__imp_CurrentIP
0x1801cc458  mov     rbx, rax
0x1801cc45b  lea     rdx, aExecutingRespe; "Executing Respecialize actions."
0x1801cc462  mov     ecx, 4000000h; unsigned int
0x1801cc467  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801cc46c  mov     [rsp+198h+var_148], 0
0x1801cc474  mov     [rsp+198h+var_150], 0
0x1801cc47d  mov     dword ptr [rsp+198h+pReserved3], edi
0x1801cc481  mov     qword ptr [rsp+198h+dwCapabilities], rbx
0x1801cc486  mov     [rsp+198h+pAuthList], r12
0x1801cc48b  mov     qword ptr [rsp+198h+dwImpLevel], r13
0x1801cc490  mov     [rsp+198h+dwAuthnLevel], 2D6h
0x1801cc498  xor     r9d, r9d
0x1801cc49b  mov     r8, r14
0x1801cc49e  mov     edx, r15d
0x1801cc4a1  mov     rcx, rax
0x1801cc4a4  call    cs:__imp_WdsSetupLogMessageW
0x1801cc4aa  mov     rax, [rsp+198h+arg_10]
0x1801cc4b2  mov     [rsp+198h+pAuthList], rax
0x1801cc4b7  call    RunPlatformActions
0x1801cc4bc  mov     esi, eax
0x1801cc4be  mov     edi, 80070000h
0x1801cc4c3  test    eax, eax
0x1801cc4c5  jle     short loc_1801CC4CC
0x1801cc4c7  movzx   esi, ax
0x1801cc4ca  or      esi, edi
0x1801cc4cc  test    esi, esi
0x1801cc4ce  js      loc_1801CCC5A
0x1801cc4d4  mov     [rsp+198h+phkResult], 0
0x1801cc4dd  lea     rax, [rsp+198h+phkResult]
0x1801cc4e2  mov     qword ptr [rsp+198h+dwAuthnLevel], rax; phkResult
0x1801cc4e7  mov     r9d, 20006h; samDesired
0x1801cc4ed  xor     r8d, r8d; ulOptions
0x1801cc4f0  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801cc4f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801cc4fe  call    cs:__imp_RegOpenKeyExW
0x1801cc504  mov     ebx, eax
0x1801cc506  test    eax, eax
0x1801cc508  jnz     short loc_1801CC529
0x1801cc50a  lea     rdx, aRespecializepe; "RespecializePending"
0x1801cc511  mov     rcx, [rsp+198h+phkResult]; hKey
0x1801cc516  call    cs:__imp_RegDeleteValueW
0x1801cc51c  mov     ebx, eax
0x1801cc51e  mov     rcx, [rsp+198h+phkResult]; hKey
0x1801cc523  call    cs:__imp_RegCloseKey
0x1801cc529  mov     ecx, ebx; dwErrCode
0x1801cc52b  call    cs:__imp_SetLastError
0x1801cc531  test    ebx, ebx
0x1801cc533  jnz     loc_1801CCCED
0x1801cc539  mov     dword ptr [rsp+198h+phkResult], 0
0x1801cc541  lea     rcx, [rsp+198h+phkResult]
0x1801cc546  call    OrchestrateWillShutdownBeforeLogon
0x1801cc54b  mov     esi, eax
0x1801cc54d  mov     [rsp+198h+var_138], eax
0x1801cc551  test    eax, eax
0x1801cc553  js      loc_1801CCDAB
0x1801cc559  mov     eax, dword ptr [rsp+198h+phkResult]
0x1801cc55d  mov     [rsp+198h+var_128], eax
0x1801cc561  test    eax, eax
0x1801cc563  jz      loc_1801CC65D
0x1801cc569  call    cs:__imp_GetLastError
0x1801cc56f  mov     edi, eax
0x1801cc571  call    cs:__imp_CurrentIP
0x1801cc577  mov     rbx, rax
0x1801cc57a  lea     rdx, aRespecializeRe; "Respecialize requested immediate reboot"
0x1801cc581  mov     ecx, 4000000h; unsigned int
0x1801cc586  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801cc58b  mov     [rsp+198h+var_148], 0
0x1801cc593  mov     [rsp+198h+var_150], 0
0x1801cc59c  mov     dword ptr [rsp+198h+pReserved3], edi
0x1801cc5a0  mov     qword ptr [rsp+198h+dwCapabilities], rbx
0x1801cc5a5  mov     [rsp+198h+pAuthList], r12
0x1801cc5aa  mov     qword ptr [rsp+198h+dwImpLevel], r13
0x1801cc5af  mov     [rsp+198h+dwAuthnLevel], 2F0h
0x1801cc5b7  xor     r9d, r9d
0x1801cc5ba  mov     r8, r14
0x1801cc5bd  mov     edx, r15d
0x1801cc5c0  mov     rcx, rax
0x1801cc5c3  call    cs:__imp_WdsSetupLogMessageW
0x1801cc5c9  mov     rcx, [rsp+198h+var_108]
0x1801cc5d1  test    rcx, rcx
0x1801cc5d4  jz      loc_1801CC65D
0x1801cc5da  mov     rax, [rcx]
0x1801cc5dd  lea     r9, aTrue_0; "True"
0x1801cc5e4  lea     r8, aRespecializere; "RespecializeReboot"
0x1801cc5eb  lea     rdx, aSpSecondbootIn; "SP_SECONDBOOT_INFO"
0x1801cc5f2  mov     rax, [rax+10h]
0x1801cc5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc5fb  jmp     short loc_1801CC65D
0x1801cc5fd  call    cs:__imp_GetLastError
0x1801cc603  mov     edi, eax
0x1801cc605  call    cs:__imp_CurrentIP
0x1801cc60b  mov     rbx, rax
0x1801cc60e  lea     rdx, aRespecializeDo; "Respecialize does not need to run onlin"...
0x1801cc615  mov     ecx, 4000000h; unsigned int
0x1801cc61a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801cc61f  mov     [rsp+198h+var_148], 0
0x1801cc627  mov     [rsp+198h+var_150], 0
0x1801cc630  mov     dword ptr [rsp+198h+pReserved3], edi
0x1801cc634  mov     qword ptr [rsp+198h+dwCapabilities], rbx
0x1801cc639  mov     [rsp+198h+pAuthList], r12
0x1801cc63e  mov     qword ptr [rsp+198h+dwImpLevel], r13
0x1801cc643  mov     [rsp+198h+dwAuthnLevel], 2FFh
0x1801cc64b  xor     r9d, r9d
0x1801cc64e  mov     r8, r14
0x1801cc651  mov     edx, r15d
0x1801cc654  mov     rcx, rax
0x1801cc657  call    cs:__imp_WdsSetupLogMessageW
0x1801cc65d  mov     rcx, [rsp+198h+arg_0]
0x1801cc665  add     rcx, 0E0h
0x1801cc66c  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x1801cc672  mov     rdx, rax; struct UnBCL::String *
0x1801cc675  mov     rcx, [rsp+198h+dwDisposition]; struct IExecutionContext *
0x1801cc67d  call    ?SPGetStoredBOOL@@YAHPEAUIExecutionContext@@PEAVString@UnBCL@@H@Z; SPGetStoredBOOL(IExecutionContext *,UnBCL::String *,int)
0x1801cc682  test    eax, eax
0x1801cc684  jz      loc_1801CC921
0x1801cc68a  call    cs:__imp_GetLastError
0x1801cc690  mov     edi, eax
0x1801cc692  call    cs:__imp_CurrentIP
0x1801cc698  mov     rbx, rax
0x1801cc69b  lea     rdx, aExecutingPostp; "Executing postponed CBS online actions"
0x1801cc6a2  mov     esi, 4000000h
0x1801cc6a7  mov     ecx, esi; unsigned int
0x1801cc6a9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801cc6ae  mov     [rsp+198h+var_148], 0
0x1801cc6b6  mov     [rsp+198h+var_150], 0
0x1801cc6bf  mov     dword ptr [rsp+198h+pReserved3], edi
0x1801cc6c3  mov     qword ptr [rsp+198h+dwCapabilities], rbx
0x1801cc6c8  mov     [rsp+198h+pAuthList], r12
0x1801cc6cd  mov     qword ptr [rsp+198h+dwImpLevel], r13
0x1801cc6d2  mov     [rsp+198h+dwAuthnLevel], 304h
0x1801cc6da  xor     r9d, r9d
0x1801cc6dd  mov     r8, r14
0x1801cc6e0  mov     edx, r15d
0x1801cc6e3  mov     rcx, rax
0x1801cc6e6  call    cs:__imp_WdsSetupLogMessageW
0x1801cc6ec  lea     rax, [rsp+198h+ppv]
0x1801cc6f4  mov     qword ptr [rsp+198h+dwAuthnLevel], rax; ppv
0x1801cc6f9  lea     r9, _GUID_f112757a_565b_4260_bd05_9fa34417349a; riid
0x1801cc700  xor     edx, edx; pUnkOuter
0x1801cc702  lea     r8d, [rdx+15h]; dwClsContext
0x1801cc706  lea     rcx, CLSID_CbsSession; rclsid
0x1801cc70d  call    cs:__imp_CoCreateInstance
0x1801cc713  mov     [rsp+198h+var_138], eax
0x1801cc717  test    eax, eax
0x1801cc719  js      loc_1801CCE3A
0x1801cc71f  call    cs:__imp_GetLastError
0x1801cc725  mov     edi, eax
0x1801cc727  call    cs:__imp_CurrentIP
0x1801cc72d  mov     rbx, rax
0x1801cc730  lea     rdx, aInitializingTh; "Initializing the ICbsSession10 interfac"...
0x1801cc737  mov     ecx, esi; unsigned int
0x1801cc739  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801cc73e  mov     [rsp+198h+var_148], 0
0x1801cc746  mov     [rsp+198h+var_150], 0
0x1801cc74f  mov     dword ptr [rsp+198h+pReserved3], edi
0x1801cc753  mov     qword ptr [rsp+198h+dwCapabilities], rbx
0x1801cc758  mov     [rsp+198h+pAuthList], r12
0x1801cc75d  mov     qword ptr [rsp+198h+dwImpLevel], r13
0x1801cc762  mov     [rsp+198h+dwAuthnLevel], 315h
0x1801cc76a  xor     r9d, r9d
0x1801cc76d  mov     r8, r14
0x1801cc770  mov     edx, r15d
0x1801cc773  mov     rcx, rax
0x1801cc776  call    cs:__imp_WdsSetupLogMessageW
0x1801cc77c  mov     rcx, [rsp+198h+ppv]
0x1801cc784  mov     rax, [rcx]
0x1801cc787  mov     qword ptr [rsp+198h+dwAuthnLevel], 0
0x1801cc790  xor     r9d, r9d
0x1801cc793  lea     r8, aSetupPlatform; "Setup Platform"
0x1801cc79a  xor     edx, edx
0x1801cc79c  mov     rax, [rax+18h]
0x1801cc7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc7a5  mov     esi, eax
0x1801cc7a7  mov     [rsp+198h+var_138], eax
0x1801cc7ab  test    eax, eax
0x1801cc7ad  js      loc_1801CCECB
0x1801cc7b3  mov     rcx, [rsp+198h+ppv]
0x1801cc7bb  mov     rax, [rcx]
0x1801cc7be  mov     edx, 2
0x1801cc7c3  mov     rax, [rax+0B8h]
0x1801cc7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc7cf  mov     esi, eax
0x1801cc7d1  mov     [rsp+198h+var_138], eax
0x1801cc7d5  test    eax, eax
0x1801cc7d7  js      loc_1801CCF5A
0x1801cc7dd  mov     dword ptr [rsp+198h+phkResult], 0
0x1801cc7e5  mov     rcx, [rsp+198h+ppv]
0x1801cc7ed  mov     rax, [rcx]
0x1801cc7f0  lea     rdx, [rsp+198h+phkResult]
0x1801cc7f5  mov     rax, [rax+20h]
0x1801cc7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cc7fe  mov     esi, eax
0x1801cc800  mov     [rsp+198h+var_138], eax
0x1801cc804  call    cs:__imp_GetLastError
0x1801cc80a  mov     edi, eax
0x1801cc80c  call    cs:__imp_CurrentIP
0x1801cc812  mov     rbx, rax
0x1801cc815  test    esi, esi
0x1801cc817  js      loc_1801CCFE9
0x1801cc81d  mov     r8d, dword ptr [rsp+198h+phkResult]
0x1801cc822  lea     rdx, aFinalizeResult; "Finalize result: %d"
0x1801cc829  mov     ecx, 4000000h; unsigned int
0x1801cc82e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801cc833  mov     [rsp+198h+var_148], 0
  ... truncated ...
```
