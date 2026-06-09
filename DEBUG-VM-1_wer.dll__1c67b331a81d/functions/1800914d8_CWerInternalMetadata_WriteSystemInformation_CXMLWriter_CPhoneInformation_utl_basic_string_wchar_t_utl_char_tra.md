# CWerInternalMetadata::WriteSystemInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800914d8`
- end: `0x180091d09`
- name: `?WriteSystemInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `2097`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008f958`

## callees

- `0x180004bb4`
- `0x180006cb0`
- `0x180009298`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000cc74`
- `0x18000dad0`
- `0x18000e7fc`
- `0x1800293ac`
- `0x180038668`
- `0x18004144c`
- `0x180041588`
- `0x180047cc4`
- `0x180050db0`
- `0x1800517cc`
- `0x1800914d8`
- `0x180094650`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180091ad5`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180091ad5`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180091b6a`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180091b6a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180091a0f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180091a0f`

## string_xrefs

- `0x180091c75`: `WriteSystemInformation found XmlWriter == NULL || !XmlWriter->IsInitialized() || PhoneInformation == NULL\n`
- `0x180091893`: `SystemProductName`
- `0x18009193e`: `InstallDate`
- `0x1800919a5`: `OSInstallDate`
- `0x180091a90`: `OSInstallTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWerInternalMetadata::WriteSystemInformation(_QWORD *a1, _DWORD *a2, __int64 a3)
{
  int MachineId; // ebx
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int DWORD; // eax
  int v13; // r9d
  int v14; // r9d
  int v15; // r9d
  unsigned int Bias; // r9d
  __int64 v17; // r8
  __int64 v18; // r9
  const wchar_t *v19; // rdx
  int v20; // r9d
  bool *v22; // [rsp+20h] [rbp-E0h]
  bool v23; // [rsp+28h] [rbp-D8h]
  bool v24[8]; // [rsp+28h] [rbp-D8h]
  bool v25; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  _OWORD v29[2]; // [rsp+70h] [rbp-90h] BYREF
  FILETIME FileTime; // [rsp+90h] [rbp-70h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v36; // [rsp+E0h] [rbp-20h]
  _QWORD v37[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v38[4]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v39[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v40[4]; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v41[4]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v42[4]; // [rsp+198h] [rbp+98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+1B8h] [rbp+B8h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+1D0h] [rbp+D0h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+210h] [rbp+110h] BYREF

  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v42);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v41);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v33);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v31);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v35);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v39);
  v25 = 0;
  FileTime = 0;
  SystemTime = 0;
  memset_0(&Buffer, 0, sizeof(Buffer));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v37);
  if ( !a1 || (unsigned __int64)(*a1 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL || !a2 )
  {
    MachineId = -2147024809;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4a9f1d31f1e33513501ec057b2633f65_Traceguids);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
      a3,
      L"WriteSystemInformation found XmlWriter == NULL || !XmlWriter->IsInitialized() || PhoneInformation == NULL\r\n");
    goto LABEL_56;
  }
  v26 = 0;
  v29[0] = 0;
  v27 = L"SystemInformation";
  v28 = 17;
  MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)v29, 0, (__int64)&v26);
  if ( MachineId < 0 )
    goto LABEL_56;
  MachineId = MachineId::GetMachineId((__int64)v42);
  if ( MachineId < 0 )
    goto LABEL_56;
  v29[0] = 0;
  v27 = (const wchar_t *)v42[0];
  v28 = (v42[1] - v42[0]) >> 1;
  *(_QWORD *)&v26 = L"MID";
  *((_QWORD *)&v26 + 1) = 3;
  LOBYTE(v7) = 1;
  MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v26, (unsigned int)&v27, v7, (__int64)v29);
  if ( MachineId < 0 )
    goto LABEL_56;
  if ( (int)UtilGetMarkerFileData(v41) >= 0 )
  {
    v29[0] = 0;
    *(_QWORD *)&v26 = v41[0];
    *((_QWORD *)&v26 + 1) = (__int64)(v41[1] - v41[0]) >> 1;
    v27 = L"MarkerFile";
    v28 = 10;
    LOBYTE(v8) = 1;
    MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v8, (__int64)v29);
    if ( MachineId < 0 )
      goto LABEL_56;
  }
  if ( (int)UtilGetManufacturerInformation((__int64)&v33, (__int64)&v31, (__int64)&v35) < 0 )
  {
    v34 = v33;
    *(_WORD *)v33 = 0;
    v32 = v31;
    *(_WORD *)v31 = 0;
    v36 = v35;
    *(_WORD *)v35 = 0;
  }
  v10 = v33;
  if ( *a2 )
  {
    if ( v33 == v34 )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
      if ( (int)CPhoneInformation::QueryPhoneInfo(a2, 0, v29) < 0
        || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               &v33,
                               *(_QWORD *)&v29[0],
                               (__int64)(*((_QWORD *)&v29[0] + 1) - *(_QWORD *)&v29[0]) >> 1) )
      {
        v34 = v33;
        *(_WORD *)v33 = 0;
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
      v10 = v33;
    }
    v11 = v31;
    if ( v31 != v32 )
      goto LABEL_23;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
    if ( (int)CPhoneInformation::QueryPhoneInfo(a2, 15, v29) < 0
      || !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v31,
                             *(_QWORD *)&v29[0],
                             (__int64)(*((_QWORD *)&v29[0] + 1) - *(_QWORD *)&v29[0]) >> 1) )
    {
      v32 = v31;
      *(_WORD *)v31 = 0;
    }
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
    v10 = v33;
  }
  v11 = v31;
LABEL_23:
  if ( v10 != v34 )
  {
    v29[0] = 0;
    *(_QWORD *)&v26 = v10;
    *((_QWORD *)&v26 + 1) = (v34 - v10) >> 1;
    v27 = L"SystemManufacturer";
    v28 = 18;
    LOBYTE(v9) = 1;
    MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v9, (__int64)v29);
    if ( MachineId < 0 )
      goto LABEL_56;
    v11 = v31;
  }
  if ( v11 == v32
    || (v29[0] = 0,
        *(_QWORD *)&v26 = v11,
        *((_QWORD *)&v26 + 1) = (v32 - v11) >> 1,
        v27 = L"SystemProductName",
        v28 = 17,
        LOBYTE(v9) = 1,
        MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v9, (__int64)v29),
        MachineId >= 0) )
  {
    if ( v35 == v36
      || (v29[0] = 0,
          *(_QWORD *)&v26 = v35,
          *((_QWORD *)&v26 + 1) = (v36 - v35) >> 1,
          v27 = L"BIOSVersion",
          v28 = 11,
          LOBYTE(v9) = 1,
          MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v9, (__int64)v29),
          MachineId >= 0) )
    {
      DWORD = UtilRegGetDWORD(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
                L"InstallDate",
                0,
                &v25,
                v23);
      if ( !DWORD )
        goto LABEL_59;
      if ( v25 )
        goto LABEL_59;
      MachineId = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v40, L"%u", DWORD);
      if ( MachineId >= 0 )
      {
        v29[0] = 0;
        *(_QWORD *)&v26 = v40[0];
        *((_QWORD *)&v26 + 1) = (__int64)(v40[1] - v40[0]) >> 1;
        v27 = L"OSInstallDate";
        v28 = 13;
        LOBYTE(v13) = 1;
        MachineId = CXMLWriter::BeginElement((_DWORD)a1, (unsigned int)&v27, (unsigned int)&v26, v13, (__int64)v29);
        if ( MachineId >= 0 )
        {
LABEL_59:
          if ( (int)UtilGetInstallTime(&FileTime) < 0 || !FileTime.dwLowDateTime && !FileTime.dwHighDateTime )
            goto LABEL_60;
          if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
            goto LABEL_60;
          *(_DWORD *)v24 = SystemTime.wHour;
          LODWORD(v22) = SystemTime.wDay;
          if ( (int)tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      v39,
                      L"%04hu-%02hu-%02huT%02hu:%02hu:%02huZ",
                      SystemTime.wYear,
                      SystemTime.wMonth,
                      v22,
                      *(_QWORD *)v24,
                      SystemTime.wMinute,
                      SystemTime.wSecond) < 0
            || (v29[0] = 0,
                *(_QWORD *)&v26 = v39[0],
                *((_QWORD *)&v26 + 1) = (__int64)(v39[1] - v39[0]) >> 1,
                v27 = L"OSInstallTime",
                v28 = 13,
                LOBYTE(v14) = 1,
                MachineId = CXMLWriter::BeginElement(
                              (_DWORD)a1,
                              (unsigned int)&v27,
                              (unsigned int)&v26,
                              v14,
                              (__int64)v29),
                MachineId >= 0) )
          {
LABEL_60:
            if ( !GlobalMemoryStatusEx(&Buffer) )
              goto LABEL_43;
            MachineId = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                          v38,
                          L"%I64u",
                          Buffer.ullTotalPhys);
            if ( MachineId >= 0 )
            {
              v29[0] = 0;
              *(_QWORD *)&v26 = v38[0];
              *((_QWORD *)&v26 + 1) = (__int64)(v38[1] - v38[0]) >> 1;
              v27 = L"Ram";
              v28 = 3;
              LOBYTE(v15) = 1;
              MachineId = CXMLWriter::BeginElement(
                            (_DWORD)a1,
                            (unsigned int)&v27,
                            (unsigned int)&v26,
                            v15,
                            (__int64)v29);
              if ( MachineId >= 0 )
              {
LABEL_43:
                if ( GetTimeZoneInformation(&TimeZoneInformation) == -1 )
                  goto LABEL_50;
                Bias = -TimeZoneInformation.Bias;
                if ( TimeZoneInformation.Bias > 0 )
                  Bias = TimeZoneInformation.Bias;
                v17 = Bias / 0x3C;
                v18 = Bias % 0x3C;
                v19 = L"-%02u:%02u";
                if ( TimeZoneInformation.Bias >= 0 )
                  v19 = L"%02u:%02u";
                MachineId = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                              v37,
                              v19,
                              v17,
                              v18);
                if ( MachineId >= 0 )
                {
                  v29[0] = 0;
                  *(_QWORD *)&v26 = v37[0];
                  *((_QWORD *)&v26 + 1) = (__int64)(v37[1] - v37[0]) >> 1;
                  v27 = L"TimeZoneBias";
                  v28 = 12;
                  LOBYTE(v20) = 1;
                  MachineId = CXMLWriter::BeginElement(
                                (_DWORD)a1,
                                (unsigned int)&v27,
                                (unsigned int)&v26,
                                v20,
                                (__int64)v29);
                  if ( MachineId >= 0 )
                  {
LABEL_50:
                    *(_QWORD *)&v26 = L"SystemInformation";
                    *((_QWORD *)&v26 + 1) = 17;
                    MachineId = CXMLWriter::EndElement(a1, &v26);
                    if ( MachineId >= 0 )
                      MachineId = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_56:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v37);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v39);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v40);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v35);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v31);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v33);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v41);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v42);
  return (unsigned int)MachineId;
}

```

## disassembly

```asm
0x1800914d8  mov     [rsp-8+arg_8], rbx
0x1800914dd  push    rbp
0x1800914de  push    rsi
0x1800914df  push    rdi
0x1800914e0  push    r12
0x1800914e2  push    r14
0x1800914e4  lea     rbp, [rsp-1D0h]
0x1800914ec  sub     rsp, 2D0h
0x1800914f3  mov     rax, cs:__security_cookie
0x1800914fa  xor     rax, rsp
0x1800914fd  mov     [rbp+1F0h+var_30], rax
0x180091504  mov     r14, r8
0x180091507  mov     rsi, rdx
0x18009150a  mov     rdi, rcx
0x18009150d  lea     rcx, [rbp+1F0h+var_158]; void *
0x180091514  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091519  nop
0x18009151a  lea     rcx, [rbp+1F0h+var_178]; void *
0x18009151e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091523  nop
0x180091524  lea     rcx, [rbp+1F0h+var_238]; void *
0x180091528  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009152d  nop
0x18009152e  lea     rcx, [rbp+1F0h+var_258]; void *
0x180091532  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091537  nop
0x180091538  lea     rcx, [rbp+1F0h+var_218]; void *
0x18009153c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091541  nop
0x180091542  lea     rcx, [rbp+1F0h+var_198]; void *
0x180091546  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009154b  nop
0x18009154c  lea     rcx, [rbp+1F0h+var_1B8]; void *
0x180091550  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091555  nop
0x180091556  mov     [rsp+2F0h+var_2B0], 0
0x18009155b  mov     qword ptr [rbp+1F0h+FileTime.dwLowDateTime], 0
0x180091563  xorps   xmm0, xmm0
0x180091566  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18009156d  xor     edx, edx; Val
0x18009156f  lea     r8d, [rdx+40h]; Size
0x180091573  lea     rcx, [rbp+1F0h+Buffer]; void *
0x18009157a  call    memset_0
0x18009157f  lea     rcx, [rbp+1F0h+var_1D8]; void *
0x180091583  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091588  nop
0x180091589  xor     edx, edx; Val
0x18009158b  mov     r8d, 0ACh; Size
0x180091591  lea     rcx, [rbp+1F0h+TimeZoneInformation]; void *
0x180091598  call    memset_0
0x18009159d  lea     rcx, [rbp+1F0h+var_1F8]; void *
0x1800915a1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800915a6  nop
0x1800915a7  test    rdi, rdi
0x1800915aa  jz      loc_180091C42
0x1800915b0  mov     rax, [rdi]
0x1800915b3  dec     rax
0x1800915b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800915ba  ja      loc_180091C42
0x1800915c0  test    rsi, rsi
0x1800915c3  jz      loc_180091C42
0x1800915c9  xorps   xmm0, xmm0
0x1800915cc  movdqa  [rsp+2F0h+var_2A0], xmm0
0x1800915d2  xorps   xmm1, xmm1
0x1800915d5  movdqa  [rsp+2F0h+var_280], xmm1
0x1800915db  lea     r12, aSysteminformat; "SystemInformation"
0x1800915e2  mov     [rsp+2F0h+var_290], r12
0x1800915e7  mov     r14d, 11h
0x1800915ed  mov     [rsp+2F0h+var_288], r14
0x1800915f2  lea     rax, [rsp+2F0h+var_2A0]
0x1800915f7  mov     [rsp+2F0h+var_2D0], rax
0x1800915fc  xor     r9d, r9d
0x1800915ff  lea     r8, [rsp+2F0h+var_280]
0x180091604  lea     rdx, [rsp+2F0h+var_290]
0x180091609  mov     rcx, rdi
0x18009160c  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180091611  mov     ebx, eax
0x180091613  test    eax, eax
0x180091615  js      loc_180091C85
0x18009161b  lea     rcx, [rbp+1F0h+var_158]; __int64
0x180091622  call    ?GetMachineId@MachineId@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; MachineId::GetMachineId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180091627  mov     ebx, eax
0x180091629  test    eax, eax
0x18009162b  js      loc_180091C85
0x180091631  xorps   xmm0, xmm0
0x180091634  movdqa  [rsp+2F0h+var_280], xmm0
0x18009163a  mov     rax, [rbp+1F0h+var_158]
0x180091641  mov     [rsp+2F0h+var_290], rax
0x180091646  mov     rcx, [rbp+1F0h+var_150]
0x18009164d  sub     rcx, rax
0x180091650  sar     rcx, 1
0x180091653  mov     [rsp+2F0h+var_288], rcx
0x180091658  lea     rax, aMid; "MID"
0x18009165f  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180091664  mov     qword ptr [rsp+2F0h+var_2A0+8], 3
0x18009166d  lea     rax, [rsp+2F0h+var_280]
0x180091672  mov     [rsp+2F0h+var_2D0], rax
0x180091677  mov     r9b, 1
0x18009167a  lea     r8, [rsp+2F0h+var_290]
0x18009167f  lea     rdx, [rsp+2F0h+var_2A0]
0x180091684  mov     rcx, rdi
0x180091687  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x18009168c  mov     ebx, eax
0x18009168e  test    eax, eax
0x180091690  js      loc_180091C85
0x180091696  lea     rcx, [rbp+1F0h+var_178]
0x18009169a  call    ?UtilGetMarkerFileData@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetMarkerFileData(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009169f  test    eax, eax
0x1800916a1  js      short loc_180091705
0x1800916a3  xorps   xmm0, xmm0
0x1800916a6  movdqa  [rsp+2F0h+var_280], xmm0
0x1800916ac  mov     rax, [rbp+1F0h+var_178]
0x1800916b0  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x1800916b5  mov     rcx, [rbp+1F0h+var_170]
0x1800916bc  sub     rcx, rax
0x1800916bf  sar     rcx, 1
0x1800916c2  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x1800916c7  lea     rax, aMarkerfile; "MarkerFile"
0x1800916ce  mov     [rsp+2F0h+var_290], rax
0x1800916d3  mov     [rsp+2F0h+var_288], 0Ah
0x1800916dc  lea     rax, [rsp+2F0h+var_280]
0x1800916e1  mov     [rsp+2F0h+var_2D0], rax
0x1800916e6  mov     r9b, 1
0x1800916e9  lea     r8, [rsp+2F0h+var_2A0]
0x1800916ee  lea     rdx, [rsp+2F0h+var_290]
0x1800916f3  mov     rcx, rdi
0x1800916f6  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800916fb  mov     ebx, eax
0x1800916fd  test    eax, eax
0x1800916ff  js      loc_180091C85
0x180091705  lea     r8, [rbp+1F0h+var_218]; __int64
0x180091709  lea     rdx, [rbp+1F0h+var_258]; __int64
0x18009170d  lea     rcx, [rbp+1F0h+var_238]; __int64
0x180091711  call    ?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z; UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180091716  test    eax, eax
0x180091718  jns     short loc_18009173D
0x18009171a  mov     rcx, [rbp+1F0h+var_238]
0x18009171e  mov     [rbp+1F0h+var_230], rcx
0x180091722  xor     eax, eax
0x180091724  mov     [rcx], ax
0x180091727  mov     rcx, [rbp+1F0h+var_258]
0x18009172b  mov     [rbp+1F0h+var_250], rcx
0x18009172f  mov     [rcx], ax
0x180091732  mov     rcx, [rbp+1F0h+var_218]
0x180091736  mov     [rbp+1F0h+var_210], rcx
0x18009173a  mov     [rcx], ax
0x18009173d  mov     rcx, [rbp+1F0h+var_238]
0x180091741  cmp     dword ptr [rsi], 0
0x180091744  jz      loc_180091809
0x18009174a  cmp     rcx, [rbp+1F0h+var_230]
0x18009174e  jnz     short loc_1800917A6
0x180091750  lea     rcx, [rsp+2F0h+var_280]; void *
0x180091755  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009175a  nop
0x18009175b  lea     r8, [rsp+2F0h+var_280]
0x180091760  xor     edx, edx
0x180091762  mov     rcx, rsi
0x180091765  call    ?QueryPhoneInfo@CPhoneInformation@@QEAAJW4_PHONE_INFORMATION_KEY@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPhoneInformation::QueryPhoneInfo(_PHONE_INFORMATION_KEY,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009176a  test    eax, eax
0x18009176c  js      short loc_18009178B
0x18009176e  mov     r8, qword ptr [rsp+2F0h+var_280+8]
0x180091773  mov     rdx, qword ptr [rsp+2F0h+var_280]
0x180091778  sub     r8, rdx
0x18009177b  sar     r8, 1
0x18009177e  lea     rcx, [rbp+1F0h+var_238]
0x180091782  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180091787  test    al, al
0x180091789  jnz     short loc_180091798
0x18009178b  mov     rcx, [rbp+1F0h+var_238]
0x18009178f  mov     [rbp+1F0h+var_230], rcx
0x180091793  xor     eax, eax
0x180091795  mov     [rcx], ax
0x180091798  lea     rcx, [rsp+2F0h+var_280]; void *
0x18009179d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800917a2  mov     rcx, [rbp+1F0h+var_238]
0x1800917a6  mov     rax, [rbp+1F0h+var_258]
0x1800917aa  cmp     rax, [rbp+1F0h+var_250]
0x1800917ae  jnz     short loc_18009180D
0x1800917b0  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800917b5  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800917ba  nop
0x1800917bb  lea     r8, [rsp+2F0h+var_280]
0x1800917c0  mov     edx, 0Fh
0x1800917c5  mov     rcx, rsi
0x1800917c8  call    ?QueryPhoneInfo@CPhoneInformation@@QEAAJW4_PHONE_INFORMATION_KEY@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPhoneInformation::QueryPhoneInfo(_PHONE_INFORMATION_KEY,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800917cd  test    eax, eax
0x1800917cf  js      short loc_1800917EE
0x1800917d1  mov     r8, qword ptr [rsp+2F0h+var_280+8]
0x1800917d6  mov     rdx, qword ptr [rsp+2F0h+var_280]
0x1800917db  sub     r8, rdx
0x1800917de  sar     r8, 1
0x1800917e1  lea     rcx, [rbp+1F0h+var_258]
0x1800917e5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800917ea  test    al, al
0x1800917ec  jnz     short loc_1800917FB
0x1800917ee  mov     rcx, [rbp+1F0h+var_258]
0x1800917f2  mov     [rbp+1F0h+var_250], rcx
0x1800917f6  xor     eax, eax
0x1800917f8  mov     [rcx], ax
0x1800917fb  lea     rcx, [rsp+2F0h+var_280]; void *
0x180091800  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180091805  mov     rcx, [rbp+1F0h+var_238]
0x180091809  mov     rax, [rbp+1F0h+var_258]
0x18009180d  mov     rdx, [rbp+1F0h+var_230]
0x180091811  cmp     rcx, rdx
0x180091814  jz      short loc_180091871
0x180091816  xorps   xmm0, xmm0
0x180091819  movdqa  [rsp+2F0h+var_280], xmm0
0x18009181f  mov     qword ptr [rsp+2F0h+var_2A0], rcx
0x180091824  sub     rdx, rcx
0x180091827  sar     rdx, 1
0x18009182a  mov     qword ptr [rsp+2F0h+var_2A0+8], rdx
0x18009182f  lea     rax, aSystemmanufact; "SystemManufacturer"
0x180091836  mov     [rsp+2F0h+var_290], rax
0x18009183b  mov     [rsp+2F0h+var_288], 12h
0x180091844  lea     rax, [rsp+2F0h+var_280]
0x180091849  mov     [rsp+2F0h+var_2D0], rax
0x18009184e  mov     r9b, 1
0x180091851  lea     r8, [rsp+2F0h+var_2A0]
0x180091856  lea     rdx, [rsp+2F0h+var_290]
0x18009185b  mov     rcx, rdi
0x18009185e  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180091863  mov     ebx, eax
0x180091865  test    eax, eax
0x180091867  js      loc_180091C85
0x18009186d  mov     rax, [rbp+1F0h+var_258]
0x180091871  mov     rcx, [rbp+1F0h+var_250]
0x180091875  cmp     rax, rcx
0x180091878  jz      short loc_1800918CD
0x18009187a  xorps   xmm0, xmm0
0x18009187d  movdqa  [rsp+2F0h+var_280], xmm0
0x180091883  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180091888  sub     rcx, rax
0x18009188b  sar     rcx, 1
0x18009188e  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x180091893  lea     rax, aSystemproductn; "SystemProductName"
0x18009189a  mov     [rsp+2F0h+var_290], rax
0x18009189f  mov     [rsp+2F0h+var_288], r14
0x1800918a4  lea     rax, [rsp+2F0h+var_280]
0x1800918a9  mov     [rsp+2F0h+var_2D0], rax
0x1800918ae  mov     r9b, 1
0x1800918b1  lea     r8, [rsp+2F0h+var_2A0]
0x1800918b6  lea     rdx, [rsp+2F0h+var_290]
0x1800918bb  mov     rcx, rdi
0x1800918be  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800918c3  mov     ebx, eax
0x1800918c5  test    eax, eax
0x1800918c7  js      loc_180091C85
0x1800918cd  mov     rcx, [rbp+1F0h+var_218]
0x1800918d1  mov     rax, [rbp+1F0h+var_210]
0x1800918d5  cmp     rcx, rax
0x1800918d8  jz      short loc_180091931
0x1800918da  xorps   xmm0, xmm0
0x1800918dd  movdqa  [rsp+2F0h+var_280], xmm0
0x1800918e3  mov     qword ptr [rsp+2F0h+var_2A0], rcx
0x1800918e8  sub     rax, rcx
0x1800918eb  sar     rax, 1
0x1800918ee  mov     qword ptr [rsp+2F0h+var_2A0+8], rax
0x1800918f3  lea     rax, aBiosversion; "BIOSVersion"
0x1800918fa  mov     [rsp+2F0h+var_290], rax
0x1800918ff  mov     [rsp+2F0h+var_288], 0Bh
0x180091908  lea     rax, [rsp+2F0h+var_280]
0x18009190d  mov     [rsp+2F0h+var_2D0], rax
0x180091912  mov     r9b, 1
0x180091915  lea     r8, [rsp+2F0h+var_2A0]
0x18009191a  lea     rdx, [rsp+2F0h+var_290]
0x18009191f  mov     rcx, rdi
0x180091922  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180091927  mov     ebx, eax
0x180091929  test    eax, eax
0x18009192b  js      loc_180091C85
0x180091931  lea     rax, [rsp+2F0h+var_2B0]
0x180091936  mov     [rsp+2F0h+var_2D0], rax; bool *
0x18009193b  xor     r9d, r9d; unsigned int
0x18009193e  lea     r8, aInstalldate; "InstallDate"
0x180091945  lea     rdx, aSoftwareMicros_33; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18009194c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180091953  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180091958  test    eax, eax
0x18009195a  jz      loc_1800919E3
0x180091960  cmp     [rsp+2F0h+var_2B0], 0
0x180091965  jnz     short loc_1800919E3
0x180091967  mov     r8d, eax
0x18009196a  lea     rdx, aU_0; "%u"
0x180091971  lea     rcx, [rbp+1F0h+var_198]
0x180091975  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18009197a  mov     ebx, eax
0x18009197c  test    eax, eax
0x18009197e  js      loc_180091C85
0x180091984  xorps   xmm0, xmm0
0x180091987  movdqa  [rsp+2F0h+var_280], xmm0
0x18009198d  mov     rax, [rbp+1F0h+var_198]
0x180091991  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180091996  mov     rcx, [rbp+1F0h+var_190]
0x18009199a  sub     rcx, rax
0x18009199d  sar     rcx, 1
0x1800919a0  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x1800919a5  lea     rax, aOsinstalldate; "OSInstallDate"
0x1800919ac  mov     [rsp+2F0h+var_290], rax
0x1800919b1  mov     [rsp+2F0h+var_288], 0Dh
  ... truncated ...
```
