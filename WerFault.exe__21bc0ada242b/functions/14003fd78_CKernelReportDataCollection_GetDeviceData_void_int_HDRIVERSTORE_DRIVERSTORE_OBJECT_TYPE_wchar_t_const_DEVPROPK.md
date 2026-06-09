# CKernelReportDataCollection::GetDeviceData(void *,int (*)(HDRIVERSTORE__ *,_DRIVERSTORE_OBJECT_TYPE,wchar_t const *,_DEVPROPKEY const *,ulong *,uchar *,ulong,ulong *,ulong))

- ea: `0x14003fd78`
- end: `0x140040ede`
- name: `?GetDeviceData@CKernelReportDataCollection@@AEAAJPEAXP6AHPEAUHDRIVERSTORE__@@W4_DRIVERSTORE_OBJECT_TYPE@@PEB_WPEBU_DEVPROPKEY@@PEAKPEAEK5K@Z@Z`
- size: `4454`
- prototype: `__int64 __fastcall(CKernelReportDataCollection *__hidden this, void *, int (__high *)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140042250`

## callees

- `0x140002470`
- `0x140002494`
- `0x140002728`
- `0x140002d24`
- `0x1400030a8`
- `0x140003f10`
- `0x14000b408`
- `0x14000b540`
- `0x14000e3c4`
- `0x140034d9c`
- `0x140038fd0`
- `0x14003fd78`
- `0x140042084`
- `0x140042bc4`
- `0x140042c60`
- `0x140043c14`
- `0x14005b770`
- `0x14005b7e8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140040647`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140040647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040dea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004076b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004078f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400407c3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400407eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040818`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040849`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040871`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040895`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004090f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040939`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040964`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040995`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400409bd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400409df`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a10`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a38`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a61`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a92`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040aba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040ae5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b16`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b3e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b69`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b9a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040bc2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c0e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c6e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c97`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040cc8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040cf0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040d1f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040d50`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040d78`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040da4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004076b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004078f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400407c3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400407eb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040818`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040849`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040871`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040895`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004090f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040939`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040964`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040995`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400409bd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400409df`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a10`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a38`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a61`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040a92`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040aba`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040ae5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b16`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b3e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b69`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040b9a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040bc2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c0e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c46`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c6e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040c97`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040cc8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040cf0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040d1f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040d50`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040d78`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140040da4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400405cc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400405cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140040744`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140040e99`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140040744`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140040e99`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400405ee`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1400405ee`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140040630`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x140040630`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400408b3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1400408b3`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x14003fe45`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_ListW` at `0x14003fe45`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14003fe84`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14003ff14`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140040e3a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14003fe84`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x14003ff14`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x140040e3a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14003ffe2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004002d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1400402dd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1400404c2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004050c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004054d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004059d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14003ffe2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004002d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1400402dd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x1400404c2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004050c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004054d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14004059d`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14003ff03`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x14003ff03`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x14003fde5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x14003fe68`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x14003fde5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_List_SizeW` at `0x14003fe68`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140040095`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140040343`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140040095`
- `ext-ms-win-setupapi-classinstallers-l1-1-2!SetupVerifyInfFileW` at `0x140040343`

## string_xrefs

- `0x1400403db`: `StringCchCopy failed`
- `0x140040440`: `GetSubmissionId (extension) failed`
- `0x1400406af`: `StringCchCopy failedTemp`
- `0x140040712`: `StringCchCopy failedTemp`
- `0x140040ab0`: `</SERVICE>\n`
- `0x140040a57`: `		<SERVICE>`
- `0x140040bb8`: `</EXTENSIONSUBMISSIONIDS>\n`
- `0x140040b5f`: `		<EXTENSIONSUBMISSIONIDS>`

## pseudocode

```c
__int64 __fastcall CKernelReportDataCollection::GetDeviceData(
        CKernelReportDataCollection *this,
        void *a2,
        int (__high *a3)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int))
{
  void *v3; // r15
  _WORD *v4; // rsi
  _WORD *v5; // rdi
  int v6; // ebx
  CONFIGRET Device_ID_List_SizeW; // eax
  _WORD **unique_for; // rax
  const struct std::nothrow_t *v9; // rdx
  unsigned int v10; // r8d
  _WORD *v11; // r13
  void *v12; // rcx
  CONFIGRET Device_ID_ListW; // eax
  signed int v14; // eax
  signed int v15; // ebx
  const char *v16; // rax
  __int64 v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  CONFIGRET v19; // eax
  signed int v20; // eax
  CONFIGRET DevNode_PropertyW; // eax
  unsigned __int64 v22; // rcx
  char v23; // al
  BOOL v24; // eax
  __int64 v25; // rcx
  BYTE *v26; // r8
  __int64 v27; // rdx
  _WORD *v28; // rax
  __int16 v29; // r9
  _WORD *v30; // rcx
  unsigned int v31; // edx
  DWORD v32; // r8d
  BYTE *v33; // rbx
  CKernelReportDataCollection *v34; // rcx
  int SubmissionId; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  _SP_INF_SIGNER_INFO_V2_W *p_InfSignerInfo; // r8
  _WORD *v39; // rax
  __int16 cbSize; // r9
  _WORD *v41; // rcx
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rax
  SC_HANDLE v46; // rax
  SC_HANDLE v47; // rsi
  struct _QUERY_SERVICE_CONFIGW *v48; // rax
  const wchar_t **v49; // rbx
  wchar_t *v50; // rax
  __int64 v51; // r8
  wchar_t *v52; // r9
  __int64 v53; // rcx
  __int16 *v54; // rax
  wchar_t v55; // dx
  wchar_t *v56; // rcx
  __int64 v57; // rax
  const wchar_t *v58; // rcx
  wchar_t v59; // dx
  wchar_t *v60; // rcx
  CKernelReportDataCollection *v61; // rcx
  unsigned int v62; // eax
  CKernelReportDataCollection *v63; // rcx
  unsigned int v64; // eax
  __int64 v65; // r8
  CKernelReportDataCollection *v66; // rcx
  unsigned int v67; // eax
  CKernelReportDataCollection *v68; // rcx
  unsigned int v69; // eax
  CKernelReportDataCollection *v70; // rcx
  CKernelReportDataCollection *v71; // rcx
  unsigned int v72; // eax
  CKernelReportDataCollection *v73; // rcx
  unsigned int v74; // eax
  CKernelReportDataCollection *v75; // rcx
  unsigned int v76; // eax
  CKernelReportDataCollection *v77; // rcx
  unsigned int v78; // eax
  CKernelReportDataCollection *v79; // rcx
  unsigned int v80; // eax
  CKernelReportDataCollection *v81; // rcx
  unsigned int v82; // eax
  __int64 v83; // rax
  signed int LastError; // eax
  __int64 v85; // rdx
  signed int v86; // eax
  wil::details *PropertyBufferSize; // [rsp+20h] [rbp-E0h]
  const char *PropertyBufferSizea; // [rsp+20h] [rbp-E0h]
  char *PropertyBufferSizeb; // [rsp+20h] [rbp-E0h]
  wil::details *PropertyBufferSizec; // [rsp+20h] [rbp-E0h]
  PULONG PropertyBufferSized; // [rsp+20h] [rbp-E0h]
  int ulFlags; // [rsp+28h] [rbp-D8h]
  const char *ulFlagsa; // [rsp+28h] [rbp-D8h]
  const char *ulFlagsb; // [rsp+28h] [rbp-D8h]
  ULONG ulFlagsc[2]; // [rsp+28h] [rbp-D8h]
  const char *v97; // [rsp+30h] [rbp-D0h]
  ULONG NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+54h] [rbp-ACh] BYREF
  ULONG pulLen; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbBytesNeeded; // [rsp+5Ch] [rbp-A4h] BYREF
  void *v102; // [rsp+60h] [rbp-A0h] BYREF
  int (__high *v103)(struct HDRIVERSTORE__ *, enum _DRIVERSTORE_OBJECT_TYPE, const wchar_t *, const struct _DEVPROPKEY *, unsigned int *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int); // [rsp+68h] [rbp-98h]
  SC_HANDLE hSCManager; // [rsp+70h] [rbp-90h]
  void *v105; // [rsp+78h] [rbp-88h]
  struct _GUID v106; // [rsp+80h] [rbp-80h] BYREF
  void *v107; // [rsp+90h] [rbp-70h]
  _WORD *v108; // [rsp+98h] [rbp-68h]
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  _SP_INF_SIGNER_INFO_V2_W InfSignerInfo; // [rsp+B0h] [rbp-50h] BYREF
  struct _SP_INF_SIGNER_INFO_V2_W Src; // [rsp+6D0h] [rbp+5D0h] BYREF
  BYTE v112[2]; // [rsp+CF0h] [rbp+BF0h] BYREF
  int v113; // [rsp+EF4h] [rbp+DF4h]
  BYTE PropertyBuffer[2]; // [rsp+F00h] [rbp+E00h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+1158h] [rbp+1058h]

  v103 = a3;
  v3 = a2;
  v107 = a2;
  v4 = 0;
  hSCManager = 0;
  v5 = 0;
  v105 = 0;
  v6 = 0;
  pulLen = 0;
  Device_ID_List_SizeW = CM_Get_Device_ID_List_SizeW(&pulLen, 0, 0x100u);
  if ( Device_ID_List_SizeW )
  {
LABEL_153:
    v86 = CM_MapCrToWin32Err(Device_ID_List_SizeW, 0xDu);
    v15 = v86;
    if ( v86 > 0 )
      v15 = (unsigned __int16)v86 | 0x80070000;
    v16 = "CM_Get_Device_ID_List_SizeW";
    v17 = 1865;
    goto LABEL_156;
  }
  while ( 1 )
  {
    unique_for = (_WORD **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v102, pulLen);
    v11 = *unique_for;
    *unique_for = 0;
    v12 = v5;
    v5 = v11;
    v105 = v11;
    v108 = v11;
    if ( v12 )
      operator delete(v12, v9);
    if ( v102 )
      operator delete(v102, v9);
    if ( !v11 )
    {
      v85 = 1873;
      goto LABEL_152;
    }
    Device_ID_ListW = CM_Get_Device_ID_ListW(0, v11, pulLen, 0x100u);
    if ( !Device_ID_ListW )
    {
      v4 = operator new(0x6428u, (const struct std::nothrow_t *)&std::nothrow);
      v102 = v4;
      v15 = 0;
      if ( v4 )
      {
        if ( !*v11 )
          goto LABEL_157;
        while ( 1 )
        {
          NumberOfBytesWritten = 0;
          PropertyType = 0;
          pulLen = 0;
          v19 = CM_Locate_DevNodeW(&pulLen, v11, 0);
          if ( v19 )
          {
            v20 = CM_MapCrToWin32Err(v19, 0x48Fu);
            if ( v20 > 0 )
              v20 = (unsigned __int16)v20 | 0x80070000;
            LODWORD(PropertyBufferSize) = v20;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x778,
              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
              "CKernelReportDataCollection::GetDeviceData",
              PropertyBufferSize,
              (int)"CM_Locate_DevNodeW",
              v97);
            goto LABEL_140;
          }
          *v4 = 0;
          v4[256] = 0;
          v4[512] = 0;
          v4[8704] = 0;
          *(_QWORD *)&v106.Data1 = v4 + 8960;
          v4[8960] = 0;
          v4[9220] = 0;
          v4[10244] = 0;
          v4[10372] = 0;
          v4[10500] = 0;
          v4[11524] = 0;
          v4[12548] = 0;
          *((_OWORD *)v4 + 1601) = 0;
          *((_QWORD *)v4 + 3204) = 0;
          NumberOfBytesWritten = 0x4000;
          if ( CM_Get_DevNode_PropertyW(
                 pulLen,
                 &DEVPKEY_Device_HardwareIds,
                 &PropertyType,
                 (PBYTE)v4 + 1024,
                 &NumberOfBytesWritten,
                 0)
            || PropertyType != 8210 )
          {
            v15 = 0;
          }
          else
          {
            NumberOfBytesWritten = 520;
            DevNode_PropertyW = CM_Get_DevNode_PropertyW(
                                  pulLen,
                                  &DEVPKEY_Device_DriverInfPath,
                                  &PropertyType,
                                  PropertyBuffer,
                                  &NumberOfBytesWritten,
                                  0);
            v22 = 0;
            if ( DevNode_PropertyW || PropertyType != 18 )
            {
              *(_WORD *)PropertyBuffer = 0;
            }
            else
            {
              v23 = IsSetupVerifyInfFileWPresent(0);
              v22 = 0;
              if ( v23 )
              {
                memset_0(&Src, 0, sizeof(Src));
                memcpy_0(&InfSignerInfo, &Src, sizeof(InfSignerInfo));
                InfSignerInfo.cbSize = 1568;
                v24 = SetupVerifyInfFileW((PCWSTR)PropertyBuffer, 0, &InfSignerInfo);
                v22 = 0;
                if ( v24 )
                {
                  v4[10244] = 0;
                  LODWORD(PropertyBufferSizea) = CKernelReportDataCollection::GetSubmissionId(
                                                   (CKernelReportDataCollection *)(v4 + 10244),
                                                   InfSignerInfo.CatalogFile,
                                                   v4 + 10244,
                                                   0x80u);
                  wil::details::in1diag4::Log_IfFailedMsg(
                    retaddr,
                    (void *)0x7B6,
                    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
                    "CKernelReportDataCollection::GetDeviceData",
                    PropertyBufferSizea,
                    (int)"GetSubmissionId failed",
                    v97);
                  v22 = 0;
                }
              }
            }
            if ( v103 )
            {
              pcbBytesNeeded = 0;
              if ( !((unsigned int (__fastcall *)(_QWORD, __int64, BYTE *, __int64 *, DEVPROPTYPE *, _WORD *, int, DWORD *, _DWORD))v103)(
                      0,
                      2,
                      PropertyBuffer,
                      DEVPKEY_DriverPackage_OriginalInfName,
                      &PropertyType,
                      v4 + 12548,
                      260,
                      &pcbBytesNeeded,
                      0)
                || PropertyType != 18 )
              {
                v25 = 2147483646;
                v26 = PropertyBuffer;
                v27 = 260;
                v28 = v4 + 12548;
                do
                {
                  if ( !v25 )
                    break;
                  v29 = *(_WORD *)v26;
                  if ( !*(_WORD *)v26 )
                    break;
                  v26 += 2;
                  *v28++ = v29;
                  --v25;
                  --v27;
                }
                while ( v27 );
                v30 = v28 - 1;
                if ( v27 )
                  v30 = v28;
                *v30 = 0;
              }
              if ( !((unsigned int (__fastcall *)(_QWORD, __int64, BYTE *, __int64 *, DEVPROPTYPE *, _WORD *, int, DWORD *, _DWORD))v103)(
                      0,
                      2,
                      PropertyBuffer,
                      DEVPKEY_DriverPackage_DriverDate,
                      &PropertyType,
                      v4 + 12816,
                      8,
                      &pcbBytesNeeded,
                      0)
                || PropertyType != 16 )
              {
                *((_QWORD *)v4 + 3204) = 0;
              }
              LODWORD(v97) = 128;
              if ( ((unsigned int (__fastcall *)(_QWORD, __int64, BYTE *, __int64 *, DEVPROPTYPE *, _WORD *))v103)(
                     0,
                     2,
                     PropertyBuffer,
                     DEVPKEY_DriverPackage_DriverFlightIds,
                     &PropertyType,
                     v4 + 10372) )
              {
                if ( PropertyType == 8210 )
                {
                  v31 = 0;
                  v32 = pcbBytesNeeded;
                  if ( (unsigned __int64)pcbBytesNeeded >> 1 != 2 )
                  {
                    do
                    {
                      if ( !v4[v31 + 10372] )
                      {
                        v4[v31 + 10372] = 59;
                        v32 = pcbBytesNeeded;
                      }
                      ++v31;
                      v22 = ((unsigned __int64)v32 >> 1) - 2;
                    }
                    while ( v31 < v22 );
                  }
                }
              }
            }
            if ( (unsigned __int8)IsSetupVerifyInfFileWPresent(v22) )
            {
              memset_0(v112, 0, 0x208u);
              NumberOfBytesWritten = 520;
              if ( !CM_Get_DevNode_PropertyW(
                      pulLen,
                      &DEVPKEY_Device_DriverExtendedInfs,
                      &PropertyType,
                      v112,
                      &NumberOfBytesWritten,
                      0)
                && PropertyType == 8210 )
              {
                v113 = 0;
                v33 = v112;
                if ( *(_WORD *)v112 )
                {
                  while ( 1 )
                  {
                    memset_0(&Src, 0, sizeof(Src));
                    if ( !SetupVerifyInfFileW((PCWSTR)v33, 0, &Src) )
                      goto LABEL_68;
                    memset_0(&InfSignerInfo, 0, 0x208u);
                    SubmissionId = CKernelReportDataCollection::GetSubmissionId(
                                     v34,
                                     Src.CatalogFile,
                                     (wchar_t *)&InfSignerInfo,
                                     0x104u);
                    if ( SubmissionId < 0 )
                    {
                      ulFlagsb = "GetSubmissionId (extension) failed";
                      v44 = 2123;
                    }
                    else
                    {
                      v36 = 1024;
                      if ( !v4[11524] )
                      {
                        v37 = 2147483646;
                        p_InfSignerInfo = &InfSignerInfo;
                        v39 = v4 + 11524;
                        do
                        {
                          if ( !v37 )
                            break;
                          cbSize = p_InfSignerInfo->cbSize;
                          if ( !LOWORD(p_InfSignerInfo->cbSize) )
                            break;
                          p_InfSignerInfo = (_SP_INF_SIGNER_INFO_V2_W *)((char *)p_InfSignerInfo + 2);
                          *v39++ = cbSize;
                          --v37;
                          --v36;
                        }
                        while ( v36 );
                        v41 = v39 - 1;
                        if ( v36 )
                          v41 = v39;
                        *v41 = 0;
                        v42 = v36 == 0 ? 0x8007007A : 0;
                        ulFlagsa = "StringCchCopy failed";
                        v43 = 2101;
                        goto LABEL_62;
                      }
                      SubmissionId = StringCchCatW(v4 + 11524, 0x400u, L";");
                      if ( SubmissionId >= 0 )
                      {
                        v42 = StringCchCatW(v4 + 11524, 0x400u, (const wchar_t *)&InfSignerInfo);
                        ulFlagsa = "StringCchCat failed";
                        v43 = 2115;
LABEL_62:
                        LODWORD(PropertyBufferSizeb) = v42;
                        wil::details::in1diag4::Log_IfFailedMsg(
                          retaddr,
                          (void *)v43,
                          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
                          "CKernelReportDataCollection::GetDeviceData",
                          PropertyBufferSizeb,
                          (int)ulFlagsa,
                          v97);
                        goto LABEL_68;
                      }
                      ulFlagsb = "StringCchCat failed";
                      v44 = 2118;
                    }
                    LODWORD(PropertyBufferSizeb) = SubmissionId;
                    wil::details::in1diag4::Log_HrMsg(
                      retaddr,
                      (void *)v44,
                      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
                      "CKernelReportDataCollection::GetDeviceData",
                      (wil::details *)PropertyBufferSizeb,
                      (int)ulFlagsb,
                      v97);
LABEL_68:
                    v45 = -1;
                    do
                      ++v45;
                    while ( *(_WORD *)&v33[2 * v45] );
                    v33 += 2 * v45 + 2;
                    if ( !*(_WORD *)v33 )
                    {
                      v3 = v107;
                      break;
                    }
                  }
                }
              }
            }
            NumberOfBytesWritten = 16;
            if ( CM_Get_DevNode_PropertyW(
                   pulLen,
                   &DEVPKEY_Device_ClassGuid,
                   &PropertyType,
                   (PBYTE)v4 + 25616,
                   &NumberOfBytesWritten,
                   0)
              || PropertyType != 13 )
            {
              *((_OWORD *)v4 + 1601) = 0;
            }
            NumberOfBytesWritten = 512;
            if ( CM_Get_DevNode_PropertyW(
                   pulLen,
                   &DEVPKEY_Device_DriverVersion,
                   &PropertyType,
                   (PBYTE)v4 + 512,
                   &NumberOfBytesWritten,
                   0)
              || PropertyType != 18 )
            {
              v4[256] = 0;
            }
            NumberOfBytesWritten = 512;
            v15 = 0;
            if ( !CM_Get_DevNode_PropertyW(
                    pulLen,
                    &DEVPKEY_Device_DriverDesc,
                    &PropertyType,
                    (PBYTE)v4,
                    &NumberOfBytesWritten,
                    0)
              && PropertyType == 18 )
            {
              v4[8960] = 0;
              NumberOfBytesWritten = 512;
              if ( CM_Get_DevNode_PropertyW(
                     pulLen,
                     &DEVPKEY_Device_Service,
                     &PropertyType,
                     (PBYTE)v4 + 17408,
                     &NumberOfBytesWritten,
                     0)
                || PropertyType != 18 )
              {
                v4[8704] = 0;
              }
              else
              {
                pcbBytesNeeded = 0;
                v46 = hSCManager;
                if ( hSCManager || (v46 = OpenSCManagerW(0, 0, 4u), (hSCManager = v46) != 0) )
                {
                  v47 = OpenServiceW(v46, v4 + 8704, 1u);
                  if ( v47 )
                  {
                    v48 = (struct _QUERY_SERVICE_CONFIGW *)operator new(
                                                             0x2000u,
                                                             (const struct std::nothrow_t *)&std::nothrow);
                    v49 = (const wchar_t **)v48;
                    if ( v48 )
                    {
                      if ( QueryServiceConfigW(v47, v48, 0x2000u, &pcbBytesNeeded) )
                      {
                        v50 = wcsrchr(v49[2], 0x5Cu);
                        v51 = 260;
                        v52 = *(wchar_t **)&v106.Data1;
                        if ( v50 )
                        {
                          v53 = 2147483646;
                          v54 = (__int16 *)(v50 + 1);
                          do
                          {
                            if ( !v53 )
                              break;
                            v55 = *v54;
                            if ( !*v54 )
                              break;
                            ++v54;
                            *v52++ = v55;
                            --v53;
                            --v51;
                          }
                          while ( v51 );
                          v56 = v52 - 1;
                          if ( v51 )
                            v56 = v52;
                          *v56 = 0;
                          if ( !v51 )
                          {
                            LODWORD(PropertyBufferSizec) = -2147024774;
                            wil::details::in1diag4::Log_HrMsg(
                              retaddr,
                              (void *)0x8C2,
                              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
                              "CKernelReportDataCollection::GetDeviceData",
                              PropertyBufferSizec,
                              (int)"StringCchCopy failedTemp",
                              v97);
                          }
                        }
                        else
                        {
                          v57 = 2147483646;
                          v58 = v49[2];
                          do
                          {
                            if ( !v57 )
                              break;
                            v59 = *v58;
                            if ( !*v58 )
                              break;
                            ++v58;
                            *v52++ = v59;
                            --v57;
                            --v51;
                          }
                          while ( v51 );
                          v60 = v52 - 1;
                          if ( v51 )
                            v60 = v52;
                          *v60 = 0;
                          if ( !v51 )
                          {
                            LODWORD(PropertyBufferSizec) = -2147024774;
                            wil::details::in1diag4::Log_HrMsg(
                              retaddr,
                              (void *)0x8CD,
                              (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
                              "CKernelReportDataCollection::GetDeviceData",
                              PropertyBufferSizec,
                              (int)"StringCchCopy failedTemp",
                              v97);
                          }
                        }
                      }
                      operator delete(v49);
                    }
                    CloseServiceHandle(v47);
                  }
                  v4 = v102;
                }
              }
              WriteFile(v3, L"\t<DEVICE>\r\n", 0x16u, &NumberOfBytesWritten, 0);
              WriteFile(v3, L"\t\t<DESCRIPTION>", 0x1Eu, &NumberOfBytesWritten, 0);
              v62 = CKernelReportDataCollection::XMLEncodeString(v61, v4, v4 + 9220, 0x400u);
              if ( !WriteFile(v3, v4 + 9220, 2 * v62, &NumberOfBytesWritten, 0) )
                goto LABEL_145;
              WriteFile(v3, L"</DESCRIPTION>\r\n", 0x20u, &NumberOfBytesWritten, 0);
              if ( v4[12548] )
              {
                WriteFile(v3, L"\t\t<INFNAME>", 0x16u, &NumberOfBytesWritten, 0);
                v64 = CKernelReportDataCollection::XMLEncodeString(v63, v4 + 12548, v4 + 9220, 0x400u);
                if ( !WriteFile(v3, v4 + 9220, 2 * v64, &NumberOfBytesWritten, 0) )
                  goto LABEL_145;
                WriteFile(v3, L"</INFNAME>\r\n", 0x18u, &NumberOfBytesWritten, 0);
                WriteFile(v3, L"\t\t<INFDATE>", 0x16u, &NumberOfBytesWritten, 0);
                LOWORD(InfSignerInfo.cbSize) = 0;
                SystemTime = 0;
                FileTimeToSystemTime((const FILETIME *)v4 + 3204, &SystemTime);
                ulFlagsc[0] = SystemTime.wYear;
                LODWORD(PropertyBufferSized) = SystemTime.wDay;
                if ( (int)StringCchPrintfW(
                            (wchar_t *)&InfSignerInfo,
                            0x104u,
                            L"%02d-%02d-%04d",
                            SystemTime.wMonth,
                            PropertyBufferSized,
                            *(_QWORD *)ulFlagsc) >= 0 )
                {
                  v65 = -1;
                  do
                    ++v65;
                  while ( *((_WORD *)&InfSignerInfo.cbSize + v65) );
                  if ( !WriteFile(v3, &InfSignerInfo, 2 * v65, &NumberOfBytesWritten, 0) )
                    goto LABEL_145;
                }
                WriteFile(v3, L"</INFDATE>\r\n", 0x18u, &NumberOfBytesWritten, 0);
              }
              if ( v4[256] )
              {
                WriteFile(v3, L"\t\t<INFVERSION>", 0x1Cu, &NumberOfBytesWritten, 0);
                v67 = CKernelReportDataCollection::XMLEncodeString(v66, v4 + 256, v4 + 9220, 0x400u);
                if ( !WriteFile(v3, v4 + 9220, 2 * v67, &NumberOfBytesWritten, 0) )
                  goto LABEL_145;
                WriteFile(v3, L"</INFVERSION>\r\n", 0x1Eu, &NumberOfBytesWritten, 0);
              }
              WriteFile(v3, L"\t\t<HARDWAREID>", 0x1Cu, &NumberOfBytesWritten, 0);
              v69 = CKernelReportDataCollection::XMLEncodeString(v68, v4 + 512, v4 + 9220, 0x400u);
              if ( !WriteFile(v3, v4 + 9220, 2 * v69, &NumberOfBytesWritten, 0) )
              {
LABEL_145:
                LastError = GetLastError();
                v15 = LastError;
                if ( LastError > 0 )
                  v15 = (unsigned __int16)LastError | 0x80070000;
                if ( v15 >= 0 )
                  v15 = -2147467259;
                goto LABEL_157;
              }
              WriteFile(v3, L"</HARDWAREID>\r\n", 0x1Eu, &NumberOfBytesWritten, 0);
              if ( v4[8704] )
              {
                WriteFile(v3, L"\t\t<SERVICE>", 0x16u, &NumberOfBytesWritten, 0);
                v72 = CKernelReportDataCollection::XMLEncodeString(v71, v4 + 8704, v4 + 9220, 0x400u);
                if ( !WriteFile(v3, v4 + 9220, 2 * v72, &NumberOfBytesWritten, 0) )
                  goto LABEL_145;
                WriteFile(v3, L"</SERVICE>\r\n", 0x18u, &NumberOfBytesWritten, 0);
              }
              if ( v4[10244] )
              {
                WriteFile(v3, L"\t\t<SUBMISSIONID>", 0x20u, &NumberOfBytesWritten, 0);
                v74 = CKernelReportDataCollection::XMLEncodeString(v73, v4 + 10244, v4 + 9220, 0x400u);
                if ( !WriteFile(v3, v4 + 9220, 2 * v74, &NumberOfBytesWritten, 0) )
                  goto LABEL_145;
                WriteFile(v3, L"</SUBMISSIONID>\r\n", 0x22u, &NumberOfBytesWritten, 0);
              }
              if ( v4[11524] )
              {
                WriteFile(v3, L"\t\t<EXTENSIONSUBMISSIONIDS>", 0x34u, &NumberOfBytesWritten, 0);
                v76 = CKernelReportDataCollection::XMLEncodeString(v75, v4 + 11524, v4 + 9220, 0x400u);
                if ( !WriteFile(v3, v4 + 9220, 2 * v76, &NumberOfBytesWritten, 0) )
                  goto LABEL_145;
                WriteFile(v3, L"</EXTENSIONSUBMISSIONIDS>\r\n", 0x36u, &NumberOfBytesWritten, 0);
              }
              v106 = (struct _GUID)*((_OWORD *)v4 + 1601);
              v15 = CKernelReportDataCollection::GuidToString(v70, (wchar_t *)v112, 0x104u, &v106);
              if ( v15 < 0 )
              {
                v16 = "GuidToString failed";
                v17 = 2421;
                goto LABEL_156;
              }
              WriteFile(v3, L"\t\t<CLASSGUID>", 0x1Au, &NumberOfBytesWritten, 0);
              v78 = CKernelReportDataCollection::XMLEncodeString(v77, (const wchar_t *)v112, v4 + 9220, 0x400u);
              if ( !WriteFile(v3, v4 + 9220, 2 * v78, &NumberOfBytesWritten, 0) )
                goto LABEL_145;
              WriteFile(v3, L"</CLASSGUID>\r\n", 0x1Cu, &NumberOfBytesWritten, 0);
              if ( v4[10372] )
              {
                WriteFile(v3, L"\t\t<FLIGHTID>", 0x18u, &NumberOfBytesWritten, 0);
                v80 = CKernelReportDataCollection::XMLEncodeString(v79, v4 + 10372, v4 + 9220, 0x400u);
                if ( !WriteFile(v3, v4 + 9220, 2 * v80, &NumberOfBytesWritten, 0) )
                  goto LABEL_145;
                WriteFile(v3, L"</FLIGHTID>\r\n", 0x1Au, &NumberOfBytesWritten, 0);
              }
              if ( v4[8960] )
              {
                WriteFile(v3, L"\t\t<DRIVER>", 0x14u, &NumberOfBytesWritten, 0);
                v82 = CKernelReportDataCollection::XMLEncodeString(v81, v4 + 8960, v4 + 9220, 0x400u);
                v15 = 0;
                if ( !WriteFile(v3, v4 + 9220, 2 * v82, &NumberOfBytesWritten, 0) )
                  goto LABEL_145;
                WriteFile(v3, L"</DRIVER>\r\n", 0x16u, &NumberOfBytesWritten, 0);
              }
              else
              {
                v15 = 0;
              }
              WriteFile(v3, L"\t</DEVICE>\r\n", 0x18u, &NumberOfBytesWritten, 0);
            }
          }
LABEL_140:
          v83 = -1;
          do
            ++v83;
          while ( v11[v83] );
          v11 += v83 + 1;
          if ( !*v11 )
            goto LABEL_157;
        }
      }
      v85 = 1895;
LABEL_152:
      LODWORD(PropertyBufferSize) = -2147024882;
      v15 = -2147024882;
      wil::details::in1diag4::Log_Hr(
        retaddr,
        (void *)v85,
        v10,
        "CKernelReportDataCollection::GetDeviceData",
        PropertyBufferSize,
        ulFlags);
      goto LABEL_157;
    }
    if ( v6 == 4 || Device_ID_ListW != 26 )
      break;
    pulLen = 0;
    Device_ID_List_SizeW = CM_Get_Device_ID_List_SizeW(&pulLen, 0, 0x100u);
    if ( Device_ID_List_SizeW )
      goto LABEL_153;
    ++v6;
  }
  v14 = CM_MapCrToWin32Err(Device_ID_ListW, 0xDu);
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
  v16 = "CM_Get_Device_ID_ListW";
  v17 = 1885;
LABEL_156:
  LODWORD(PropertyBufferSize) = v15;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v17,
    (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
    "CKernelReportDataCollection::GetDeviceData",
    PropertyBufferSize,
    (int)v16,
    v97);
LABEL_157:
  if ( v105 )
    operator delete(v105, v18);
  if ( hSCManager )
    CloseServiceHandle(hSCManager);
  if ( v4 )
    operator delete(v4, (const struct std::nothrow_t *)0x6428);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14003fd78  mov     [rsp-8+arg_0], rbx
0x14003fd7d  push    rbp
0x14003fd7e  push    rsi
0x14003fd7f  push    rdi
0x14003fd80  push    r12
0x14003fd82  push    r13
0x14003fd84  push    r14
0x14003fd86  push    r15
0x14003fd88  lea     rbp, [rsp-1020h]
0x14003fd90  mov     eax, 1120h
0x14003fd95  call    _alloca_probe
0x14003fd9a  sub     rsp, rax
0x14003fd9d  mov     rax, cs:__security_cookie
0x14003fda4  xor     rax, rsp
0x14003fda7  mov     [rbp+1050h+var_40], rax
0x14003fdae  mov     [rsp+1150h+var_10E8], r8
0x14003fdb3  mov     r15, rdx
0x14003fdb6  mov     [rbp+1050h+var_10C0], rdx
0x14003fdba  xor     r14d, r14d
0x14003fdbd  mov     esi, r14d
0x14003fdc0  mov     [rsp+1150h+hSCManager], r14
0x14003fdc5  mov     edi, r14d
0x14003fdc8  mov     [rsp+1150h+var_10D8], r14
0x14003fdcd  mov     ebx, r14d
0x14003fdd0  mov     [rsp+1150h+pulLen], r14d
0x14003fdd5  mov     r12d, 100h
0x14003fddb  mov     r8d, r12d; ulFlags
0x14003fdde  xor     edx, edx; pszFilter
0x14003fde0  lea     rcx, [rsp+1150h+pulLen]; pulLen
0x14003fde5  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x14003fdeb  test    eax, eax
0x14003fded  jnz     loc_140040E33
0x14003fdf3  mov     edx, [rsp+1150h+pulLen]
0x14003fdf7  lea     rcx, [rsp+1150h+var_10F0]
0x14003fdfc  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x14003fe01  mov     r13, [rax]
0x14003fe04  mov     [rax], r14
0x14003fe07  mov     rcx, rdi; void *
0x14003fe0a  mov     rdi, r13
0x14003fe0d  mov     [rsp+1150h+var_10D8], r13
0x14003fe12  mov     [rbp+1050h+var_10B8], r13
0x14003fe16  test    rcx, rcx
0x14003fe19  jz      short loc_14003FE20
0x14003fe1b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003fe20  mov     rcx, [rsp+1150h+var_10F0]; void *
0x14003fe25  test    rcx, rcx
0x14003fe28  jz      short loc_14003FE2F
0x14003fe2a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003fe2f  test    r13, r13
0x14003fe32  jz      loc_140040E0E
0x14003fe38  mov     r9d, r12d; ulFlags
0x14003fe3b  mov     r8d, [rsp+1150h+pulLen]; BufferLen
0x14003fe40  mov     rdx, r13; Buffer
0x14003fe43  xor     ecx, ecx; pszFilter
0x14003fe45  call    cs:__imp_CM_Get_Device_ID_ListW
0x14003fe4b  test    eax, eax
0x14003fe4d  jz      short loc_14003FEAA
0x14003fe4f  cmp     ebx, 4
0x14003fe52  jz      short loc_14003FE7D
0x14003fe54  cmp     eax, 1Ah
0x14003fe57  jnz     short loc_14003FE7D
0x14003fe59  mov     [rsp+1150h+pulLen], r14d
0x14003fe5e  mov     r8d, r12d; ulFlags
0x14003fe61  xor     edx, edx; pszFilter
0x14003fe63  lea     rcx, [rsp+1150h+pulLen]; pulLen
0x14003fe68  call    cs:__imp_CM_Get_Device_ID_List_SizeW
0x14003fe6e  test    eax, eax
0x14003fe70  jnz     loc_140040E33
0x14003fe76  inc     ebx
0x14003fe78  jmp     loc_14003FDF3
0x14003fe7d  mov     edx, 0Dh; DefaultErr
0x14003fe82  mov     ecx, eax; CmReturnCode
0x14003fe84  call    cs:__imp_CM_MapCrToWin32Err
0x14003fe8a  mov     ebx, eax
0x14003fe8c  test    eax, eax
0x14003fe8e  jle     short loc_14003FE99
0x14003fe90  movzx   ebx, ax
0x14003fe93  or      ebx, 80070000h
0x14003fe99  lea     rax, aCmGetDeviceIdL_0; "CM_Get_Device_ID_ListW"
0x14003fea0  mov     edx, 75Dh
0x14003fea5  jmp     loc_140040E5B
0x14003feaa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003feb1  mov     ecx, 6428h; unsigned __int64
0x14003feb6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14003febb  mov     rsi, rax
0x14003febe  mov     [rsp+1150h+var_10F0], rax
0x14003fec3  xor     ebx, ebx
0x14003fec5  test    rax, rax
0x14003fec8  jz      loc_140040E07
0x14003fece  cmp     [r13+0], bx
0x14003fed3  jz      loc_140040E7F
0x14003fed9  mov     edi, 80070000h
0x14003fede  lea     r14, aCkernelreportd; "CKernelReportDataCollection::GetDeviceD"...
0x14003fee5  lea     r12, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x14003feec  mov     [rsp+1150h+NumberOfBytesWritten], ebx
0x14003fef0  mov     [rsp+1150h+PropertyType], ebx
0x14003fef4  mov     [rsp+1150h+pulLen], ebx
0x14003fef8  xor     r8d, r8d; ulFlags
0x14003fefb  mov     rdx, r13; pDeviceID
0x14003fefe  lea     rcx, [rsp+1150h+pulLen]; pdnDevInst
0x14003ff03  call    cs:__imp_CM_Locate_DevNodeW
0x14003ff09  test    eax, eax
0x14003ff0b  jz      short loc_14003FF4F
0x14003ff0d  mov     edx, 48Fh; DefaultErr
0x14003ff12  mov     ecx, eax; CmReturnCode
0x14003ff14  call    cs:__imp_CM_MapCrToWin32Err
0x14003ff1a  test    eax, eax
0x14003ff1c  jle     short loc_14003FF23
0x14003ff1e  movzx   eax, ax
0x14003ff21  or      eax, edi
0x14003ff23  mov     rcx, [rbp+1058h]; this
0x14003ff2a  lea     rdx, aCmLocateDevnod; "CM_Locate_DevNodeW"
0x14003ff31  mov     qword ptr [rsp+1150h+ulFlags], rdx; int
0x14003ff36  mov     dword ptr [rsp+1150h+PropertyBufferSize], eax; wil::details *
0x14003ff3a  mov     r9, r14; char *
0x14003ff3d  mov     r8, r12; unsigned int
0x14003ff40  mov     edx, 778h; void *
0x14003ff45  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ff4a  jmp     loc_140040DAE
0x14003ff4f  mov     [rsi], bx
0x14003ff52  mov     [rsi+200h], bx
0x14003ff59  lea     rdx, [rsi+400h]
0x14003ff60  mov     [rdx], bx
0x14003ff63  mov     [rsi+4400h], bx
0x14003ff6a  lea     rcx, [rsi+4600h]
0x14003ff71  mov     qword ptr [rbp+1050h+var_10D0.Data1], rcx
0x14003ff75  mov     [rcx], bx
0x14003ff78  xor     ecx, ecx
0x14003ff7a  mov     [rsi+4808h], cx
0x14003ff81  mov     [rsi+5008h], cx
0x14003ff88  mov     [rsi+5108h], cx
0x14003ff8f  mov     [rsi+5208h], cx
0x14003ff96  mov     [rsi+5A08h], cx
0x14003ff9d  lea     rbx, [rsi+6208h]
0x14003ffa4  mov     [rbx], cx
0x14003ffa7  xorps   xmm0, xmm0
0x14003ffaa  movdqu  xmmword ptr [rsi+6410h], xmm0
0x14003ffb2  mov     [rsi+6420h], rcx
0x14003ffb9  mov     [rsp+1150h+NumberOfBytesWritten], 4000h
0x14003ffc1  mov     [rsp+1150h+ulFlags], ecx; ulFlags
0x14003ffc5  lea     rax, [rsp+1150h+NumberOfBytesWritten]
0x14003ffca  mov     [rsp+1150h+PropertyBufferSize], rax; PropertyBufferSize
0x14003ffcf  mov     r9, rdx; PropertyBuffer
0x14003ffd2  lea     r8, [rsp+1150h+PropertyType]; PropertyType
0x14003ffd7  lea     rdx, DEVPKEY_Device_HardwareIds; PropertyKey
0x14003ffde  mov     ecx, [rsp+1150h+pulLen]; dnDevInst
0x14003ffe2  call    cs:__imp_CM_Get_DevNode_PropertyW
0x14003ffe8  xor     ecx, ecx
0x14003ffea  test    eax, eax
0x14003ffec  jnz     loc_140040DAC
0x14003fff2  cmp     [rsp+1150h+PropertyType], 2012h
0x14003fffa  jnz     loc_140040DAC
0x140040000  mov     [rsp+1150h+NumberOfBytesWritten], 208h
0x140040008  mov     [rsp+1150h+ulFlags], ecx; ulFlags
0x14004000c  lea     rax, [rsp+1150h+NumberOfBytesWritten]
0x140040011  mov     [rsp+1150h+PropertyBufferSize], rax; PropertyBufferSize
0x140040016  lea     r9, [rbp+1050h+PropertyBuffer]; PropertyBuffer
0x14004001d  lea     r8, [rsp+1150h+PropertyType]; PropertyType
0x140040022  lea     rdx, DEVPKEY_Device_DriverInfPath; PropertyKey
0x140040029  mov     ecx, [rsp+1150h+pulLen]; dnDevInst
0x14004002d  call    cs:__imp_CM_Get_DevNode_PropertyW
0x140040033  xor     ecx, ecx
0x140040035  test    eax, eax
0x140040037  jnz     loc_1400400EA
0x14004003d  cmp     [rsp+1150h+PropertyType], 12h
0x140040042  jnz     loc_1400400EA
0x140040048  call    IsSetupVerifyInfFileWPresent
0x14004004d  xor     ecx, ecx
0x14004004f  test    al, al
0x140040051  jz      loc_1400400F1
0x140040057  xor     edx, edx; Val
0x140040059  mov     r8d, 620h; Size
0x14004005f  lea     rcx, [rbp+1050h+Src]; void *
0x140040066  call    memset_0
0x14004006b  lea     rcx, [rbp+1050h+InfSignerInfo]; void *
0x14004006f  lea     rdx, [rbp+1050h+Src]; Src
0x140040076  mov     r8d, 620h; Size
0x14004007c  call    memcpy_0
0x140040081  mov     [rbp+1050h+InfSignerInfo.cbSize], 620h
0x140040088  lea     r8, [rbp+1050h+InfSignerInfo]; InfSignerInfo
0x14004008c  xor     edx, edx; AltPlatformInfo
0x14004008e  lea     rcx, [rbp+1050h+PropertyBuffer]; InfName
0x140040095  call    cs:__imp_SetupVerifyInfFileW
0x14004009b  xor     ecx, ecx
0x14004009d  test    eax, eax
0x14004009f  jz      short loc_1400400F1
0x1400400a1  mov     eax, ecx
0x1400400a3  lea     rcx, [rsi+5008h]; this
0x1400400aa  mov     [rcx], ax
0x1400400ad  mov     r9d, 80h; unsigned int
0x1400400b3  mov     r8, rcx; wchar_t *
0x1400400b6  lea     rdx, [rbp+1050h+InfSignerInfo.CatalogFile]; wchar_t *
0x1400400ba  call    ?GetSubmissionId@CKernelReportDataCollection@@AEAAJPEA_W0K@Z; CKernelReportDataCollection::GetSubmissionId(wchar_t *,wchar_t *,ulong)
0x1400400bf  mov     rcx, [rbp+1058h]; this
0x1400400c6  lea     rdx, aGetsubmissioni; "GetSubmissionId failed"
0x1400400cd  mov     qword ptr [rsp+1150h+ulFlags], rdx; int
0x1400400d2  mov     dword ptr [rsp+1150h+PropertyBufferSize], eax; char *
0x1400400d6  mov     r9, r14; char *
0x1400400d9  mov     r8, r12; unsigned int
0x1400400dc  mov     edx, 7B6h; void *
0x1400400e1  call    ?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400400e6  xor     ecx, ecx
0x1400400e8  jmp     short loc_1400400F1
0x1400400ea  mov     word ptr [rbp+1050h+PropertyBuffer], cx
0x1400400f1  mov     rax, [rsp+1150h+var_10E8]
0x1400400f6  test    rax, rax
0x1400400f9  jz      loc_14004028D
0x1400400ff  mov     [rsp+1150h+pcbBytesNeeded], ecx
0x140040103  mov     [rsp+1150h+var_1110], ecx
0x140040107  lea     rcx, [rsp+1150h+pcbBytesNeeded]
0x14004010c  mov     [rsp+1150h+var_1118], rcx
0x140040111  mov     dword ptr [rsp+1150h+var_1120], 104h
0x140040119  mov     qword ptr [rsp+1150h+ulFlags], rbx
0x14004011e  lea     rcx, [rsp+1150h+PropertyType]
0x140040123  mov     [rsp+1150h+PropertyBufferSize], rcx
0x140040128  lea     r9, DEVPKEY_DriverPackage_OriginalInfName
0x14004012f  lea     r8, [rbp+1050h+PropertyBuffer]
0x140040136  mov     edx, 2
0x14004013b  xor     ecx, ecx
0x14004013d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040142  xor     r10d, r10d
0x140040145  test    eax, eax
0x140040147  jz      short loc_140040150
0x140040149  cmp     [rsp+1150h+PropertyType], 12h
0x14004014e  jz      short loc_140040197
0x140040150  mov     ecx, 7FFFFFFEh
0x140040155  lea     r8, [rbp+1050h+PropertyBuffer]
0x14004015c  mov     edx, 104h
0x140040161  mov     rax, rbx
0x140040164  test    rcx, rcx
0x140040167  jz      short loc_140040188
0x140040169  movzx   r9d, word ptr [r8]
0x14004016d  test    r9w, r9w
0x140040171  jz      short loc_140040188
0x140040173  add     r8, 2
0x140040177  mov     [rax], r9w
0x14004017b  add     rax, 2
0x14004017f  dec     rcx
0x140040182  sub     rdx, 1
0x140040186  jnz     short loc_140040164
0x140040188  lea     rcx, [rax-2]
0x14004018c  test    rdx, rdx
0x14004018f  cmovnz  rcx, rax
0x140040193  mov     [rcx], r10w
0x140040197  mov     [rsp+1150h+var_1110], r10d
0x14004019c  lea     rax, [rsp+1150h+pcbBytesNeeded]
0x1400401a1  mov     [rsp+1150h+var_1118], rax
0x1400401a6  mov     dword ptr [rsp+1150h+var_1120], 8
0x1400401ae  lea     rbx, [rsi+6420h]
0x1400401b5  mov     qword ptr [rsp+1150h+ulFlags], rbx
0x1400401ba  lea     rax, [rsp+1150h+PropertyType]
0x1400401bf  mov     [rsp+1150h+PropertyBufferSize], rax
0x1400401c4  lea     r9, DEVPKEY_DriverPackage_DriverDate
0x1400401cb  lea     r8, [rbp+1050h+PropertyBuffer]
0x1400401d2  mov     edx, 2
0x1400401d7  xor     ecx, ecx
0x1400401d9  mov     rax, [rsp+1150h+var_10E8]
0x1400401de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400401e3  xor     ecx, ecx
0x1400401e5  test    eax, eax
0x1400401e7  jz      short loc_1400401F0
0x1400401e9  cmp     [rsp+1150h+PropertyType], 10h
0x1400401ee  jz      short loc_1400401F3
0x1400401f0  mov     [rbx], rcx
0x1400401f3  xor     ebx, ebx
0x1400401f5  mov     [rsp+1150h+var_1110], ebx
0x1400401f9  lea     rax, [rsp+1150h+pcbBytesNeeded]
0x1400401fe  mov     [rsp+1150h+var_1118], rax
0x140040203  mov     dword ptr [rsp+1150h+var_1120], 80h
0x14004020b  lea     rax, [rsi+5108h]
0x140040212  mov     qword ptr [rsp+1150h+ulFlags], rax
0x140040217  lea     rax, [rsp+1150h+PropertyType]
0x14004021c  mov     [rsp+1150h+PropertyBufferSize], rax
0x140040221  lea     r9, DEVPKEY_DriverPackage_DriverFlightIds
0x140040228  lea     r8, [rbp+1050h+PropertyBuffer]
0x14004022f  lea     edx, [rbx+2]
0x140040232  mov     rax, [rsp+1150h+var_10E8]
0x140040237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004023c  test    eax, eax
0x14004023e  jz      short loc_14004028F
0x140040240  cmp     [rsp+1150h+PropertyType], 2012h
0x140040248  jnz     short loc_14004028F
0x14004024a  mov     edx, ebx
0x14004024c  mov     r8d, [rsp+1150h+pcbBytesNeeded]
0x140040251  mov     eax, r8d
0x140040254  shr     rax, 1
0x140040257  cmp     rax, 2
0x14004025b  jz      short loc_14004028F
0x14004025d  mov     eax, edx
0x14004025f  cmp     [rsi+rax*2+5108h], bx
0x140040267  jnz     short loc_140040278
0x140040269  mov     word ptr [rsi+rax*2+5108h], 3Bh ; ';'
0x140040273  mov     r8d, [rsp+1150h+pcbBytesNeeded]
0x140040278  inc     edx
0x14004027a  mov     ecx, r8d
0x14004027d  shr     rcx, 1
0x140040280  sub     rcx, 2
0x140040284  mov     eax, edx
0x140040286  cmp     rax, rcx
0x140040289  jb      short loc_14004025D
  ... truncated ...
```
