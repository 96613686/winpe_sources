# CWerInternalMetadata::WriteSystemInformation(CXMLWriter *,CPhoneInformation *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180091488`
- end: `0x180091cb9`
- name: `?WriteSystemInformation@CWerInternalMetadata@@CAJPEAVCXMLWriter@@PEAVCPhoneInformation@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `2097`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008f908`

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
- `0x180091488`
- `0x180094600`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180091a85`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180091a85`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180091b1a`
- `api-ms-win-core-timezone-l1-1-0!GetTimeZoneInformation` at `0x180091b1a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800919bf`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800919bf`

## string_xrefs

- `0x180091c25`: `WriteSystemInformation found XmlWriter == NULL || !XmlWriter->IsInitialized() || PhoneInformation == NULL\n`
- `0x180091843`: `SystemProductName`
- `0x1800918ee`: `InstallDate`
- `0x180091955`: `OSInstallDate`
- `0x180091a40`: `OSInstallTime`

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
0x180091488  mov     [rsp-8+arg_8], rbx
0x18009148d  push    rbp
0x18009148e  push    rsi
0x18009148f  push    rdi
0x180091490  push    r12
0x180091492  push    r14
0x180091494  lea     rbp, [rsp-1D0h]
0x18009149c  sub     rsp, 2D0h
0x1800914a3  mov     rax, cs:__security_cookie
0x1800914aa  xor     rax, rsp
0x1800914ad  mov     [rbp+1F0h+var_30], rax
0x1800914b4  mov     r14, r8
0x1800914b7  mov     rsi, rdx
0x1800914ba  mov     rdi, rcx
0x1800914bd  lea     rcx, [rbp+1F0h+var_158]; void *
0x1800914c4  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800914c9  nop
0x1800914ca  lea     rcx, [rbp+1F0h+var_178]; void *
0x1800914ce  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800914d3  nop
0x1800914d4  lea     rcx, [rbp+1F0h+var_238]; void *
0x1800914d8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800914dd  nop
0x1800914de  lea     rcx, [rbp+1F0h+var_258]; void *
0x1800914e2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800914e7  nop
0x1800914e8  lea     rcx, [rbp+1F0h+var_218]; void *
0x1800914ec  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800914f1  nop
0x1800914f2  lea     rcx, [rbp+1F0h+var_198]; void *
0x1800914f6  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800914fb  nop
0x1800914fc  lea     rcx, [rbp+1F0h+var_1B8]; void *
0x180091500  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091505  nop
0x180091506  mov     [rsp+2F0h+var_2B0], 0
0x18009150b  mov     qword ptr [rbp+1F0h+FileTime.dwLowDateTime], 0
0x180091513  xorps   xmm0, xmm0
0x180091516  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x18009151d  xor     edx, edx; Val
0x18009151f  lea     r8d, [rdx+40h]; Size
0x180091523  lea     rcx, [rbp+1F0h+Buffer]; void *
0x18009152a  call    memset_0
0x18009152f  lea     rcx, [rbp+1F0h+var_1D8]; void *
0x180091533  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091538  nop
0x180091539  xor     edx, edx; Val
0x18009153b  mov     r8d, 0ACh; Size
0x180091541  lea     rcx, [rbp+1F0h+TimeZoneInformation]; void *
0x180091548  call    memset_0
0x18009154d  lea     rcx, [rbp+1F0h+var_1F8]; void *
0x180091551  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180091556  nop
0x180091557  test    rdi, rdi
0x18009155a  jz      loc_180091BF2
0x180091560  mov     rax, [rdi]
0x180091563  dec     rax
0x180091566  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009156a  ja      loc_180091BF2
0x180091570  test    rsi, rsi
0x180091573  jz      loc_180091BF2
0x180091579  xorps   xmm0, xmm0
0x18009157c  movdqa  [rsp+2F0h+var_2A0], xmm0
0x180091582  xorps   xmm1, xmm1
0x180091585  movdqa  [rsp+2F0h+var_280], xmm1
0x18009158b  lea     r12, aSysteminformat; "SystemInformation"
0x180091592  mov     [rsp+2F0h+var_290], r12
0x180091597  mov     r14d, 11h
0x18009159d  mov     [rsp+2F0h+var_288], r14
0x1800915a2  lea     rax, [rsp+2F0h+var_2A0]
0x1800915a7  mov     [rsp+2F0h+var_2D0], rax
0x1800915ac  xor     r9d, r9d
0x1800915af  lea     r8, [rsp+2F0h+var_280]
0x1800915b4  lea     rdx, [rsp+2F0h+var_290]
0x1800915b9  mov     rcx, rdi
0x1800915bc  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800915c1  mov     ebx, eax
0x1800915c3  test    eax, eax
0x1800915c5  js      loc_180091C35
0x1800915cb  lea     rcx, [rbp+1F0h+var_158]; __int64
0x1800915d2  call    ?GetMachineId@MachineId@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; MachineId::GetMachineId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800915d7  mov     ebx, eax
0x1800915d9  test    eax, eax
0x1800915db  js      loc_180091C35
0x1800915e1  xorps   xmm0, xmm0
0x1800915e4  movdqa  [rsp+2F0h+var_280], xmm0
0x1800915ea  mov     rax, [rbp+1F0h+var_158]
0x1800915f1  mov     [rsp+2F0h+var_290], rax
0x1800915f6  mov     rcx, [rbp+1F0h+var_150]
0x1800915fd  sub     rcx, rax
0x180091600  sar     rcx, 1
0x180091603  mov     [rsp+2F0h+var_288], rcx
0x180091608  lea     rax, aMid; "MID"
0x18009160f  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180091614  mov     qword ptr [rsp+2F0h+var_2A0+8], 3
0x18009161d  lea     rax, [rsp+2F0h+var_280]
0x180091622  mov     [rsp+2F0h+var_2D0], rax
0x180091627  mov     r9b, 1
0x18009162a  lea     r8, [rsp+2F0h+var_290]
0x18009162f  lea     rdx, [rsp+2F0h+var_2A0]
0x180091634  mov     rcx, rdi
0x180091637  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x18009163c  mov     ebx, eax
0x18009163e  test    eax, eax
0x180091640  js      loc_180091C35
0x180091646  lea     rcx, [rbp+1F0h+var_178]
0x18009164a  call    ?UtilGetMarkerFileData@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetMarkerFileData(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009164f  test    eax, eax
0x180091651  js      short loc_1800916B5
0x180091653  xorps   xmm0, xmm0
0x180091656  movdqa  [rsp+2F0h+var_280], xmm0
0x18009165c  mov     rax, [rbp+1F0h+var_178]
0x180091660  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180091665  mov     rcx, [rbp+1F0h+var_170]
0x18009166c  sub     rcx, rax
0x18009166f  sar     rcx, 1
0x180091672  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x180091677  lea     rax, aMarkerfile; "MarkerFile"
0x18009167e  mov     [rsp+2F0h+var_290], rax
0x180091683  mov     [rsp+2F0h+var_288], 0Ah
0x18009168c  lea     rax, [rsp+2F0h+var_280]
0x180091691  mov     [rsp+2F0h+var_2D0], rax
0x180091696  mov     r9b, 1
0x180091699  lea     r8, [rsp+2F0h+var_2A0]
0x18009169e  lea     rdx, [rsp+2F0h+var_290]
0x1800916a3  mov     rcx, rdi
0x1800916a6  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800916ab  mov     ebx, eax
0x1800916ad  test    eax, eax
0x1800916af  js      loc_180091C35
0x1800916b5  lea     r8, [rbp+1F0h+var_218]; __int64
0x1800916b9  lea     rdx, [rbp+1F0h+var_258]; __int64
0x1800916bd  lea     rcx, [rbp+1F0h+var_238]; __int64
0x1800916c1  call    ?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z; UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800916c6  test    eax, eax
0x1800916c8  jns     short loc_1800916ED
0x1800916ca  mov     rcx, [rbp+1F0h+var_238]
0x1800916ce  mov     [rbp+1F0h+var_230], rcx
0x1800916d2  xor     eax, eax
0x1800916d4  mov     [rcx], ax
0x1800916d7  mov     rcx, [rbp+1F0h+var_258]
0x1800916db  mov     [rbp+1F0h+var_250], rcx
0x1800916df  mov     [rcx], ax
0x1800916e2  mov     rcx, [rbp+1F0h+var_218]
0x1800916e6  mov     [rbp+1F0h+var_210], rcx
0x1800916ea  mov     [rcx], ax
0x1800916ed  mov     rcx, [rbp+1F0h+var_238]
0x1800916f1  cmp     dword ptr [rsi], 0
0x1800916f4  jz      loc_1800917B9
0x1800916fa  cmp     rcx, [rbp+1F0h+var_230]
0x1800916fe  jnz     short loc_180091756
0x180091700  lea     rcx, [rsp+2F0h+var_280]; void *
0x180091705  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009170a  nop
0x18009170b  lea     r8, [rsp+2F0h+var_280]
0x180091710  xor     edx, edx
0x180091712  mov     rcx, rsi
0x180091715  call    ?QueryPhoneInfo@CPhoneInformation@@QEAAJW4_PHONE_INFORMATION_KEY@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPhoneInformation::QueryPhoneInfo(_PHONE_INFORMATION_KEY,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009171a  test    eax, eax
0x18009171c  js      short loc_18009173B
0x18009171e  mov     r8, qword ptr [rsp+2F0h+var_280+8]
0x180091723  mov     rdx, qword ptr [rsp+2F0h+var_280]
0x180091728  sub     r8, rdx
0x18009172b  sar     r8, 1
0x18009172e  lea     rcx, [rbp+1F0h+var_238]
0x180091732  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180091737  test    al, al
0x180091739  jnz     short loc_180091748
0x18009173b  mov     rcx, [rbp+1F0h+var_238]
0x18009173f  mov     [rbp+1F0h+var_230], rcx
0x180091743  xor     eax, eax
0x180091745  mov     [rcx], ax
0x180091748  lea     rcx, [rsp+2F0h+var_280]; void *
0x18009174d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180091752  mov     rcx, [rbp+1F0h+var_238]
0x180091756  mov     rax, [rbp+1F0h+var_258]
0x18009175a  cmp     rax, [rbp+1F0h+var_250]
0x18009175e  jnz     short loc_1800917BD
0x180091760  lea     rcx, [rsp+2F0h+var_280]; void *
0x180091765  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18009176a  nop
0x18009176b  lea     r8, [rsp+2F0h+var_280]
0x180091770  mov     edx, 0Fh
0x180091775  mov     rcx, rsi
0x180091778  call    ?QueryPhoneInfo@CPhoneInformation@@QEAAJW4_PHONE_INFORMATION_KEY@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CPhoneInformation::QueryPhoneInfo(_PHONE_INFORMATION_KEY,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18009177d  test    eax, eax
0x18009177f  js      short loc_18009179E
0x180091781  mov     r8, qword ptr [rsp+2F0h+var_280+8]
0x180091786  mov     rdx, qword ptr [rsp+2F0h+var_280]
0x18009178b  sub     r8, rdx
0x18009178e  sar     r8, 1
0x180091791  lea     rcx, [rbp+1F0h+var_258]
0x180091795  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18009179a  test    al, al
0x18009179c  jnz     short loc_1800917AB
0x18009179e  mov     rcx, [rbp+1F0h+var_258]
0x1800917a2  mov     [rbp+1F0h+var_250], rcx
0x1800917a6  xor     eax, eax
0x1800917a8  mov     [rcx], ax
0x1800917ab  lea     rcx, [rsp+2F0h+var_280]; void *
0x1800917b0  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800917b5  mov     rcx, [rbp+1F0h+var_238]
0x1800917b9  mov     rax, [rbp+1F0h+var_258]
0x1800917bd  mov     rdx, [rbp+1F0h+var_230]
0x1800917c1  cmp     rcx, rdx
0x1800917c4  jz      short loc_180091821
0x1800917c6  xorps   xmm0, xmm0
0x1800917c9  movdqa  [rsp+2F0h+var_280], xmm0
0x1800917cf  mov     qword ptr [rsp+2F0h+var_2A0], rcx
0x1800917d4  sub     rdx, rcx
0x1800917d7  sar     rdx, 1
0x1800917da  mov     qword ptr [rsp+2F0h+var_2A0+8], rdx
0x1800917df  lea     rax, aSystemmanufact; "SystemManufacturer"
0x1800917e6  mov     [rsp+2F0h+var_290], rax
0x1800917eb  mov     [rsp+2F0h+var_288], 12h
0x1800917f4  lea     rax, [rsp+2F0h+var_280]
0x1800917f9  mov     [rsp+2F0h+var_2D0], rax
0x1800917fe  mov     r9b, 1
0x180091801  lea     r8, [rsp+2F0h+var_2A0]
0x180091806  lea     rdx, [rsp+2F0h+var_290]
0x18009180b  mov     rcx, rdi
0x18009180e  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180091813  mov     ebx, eax
0x180091815  test    eax, eax
0x180091817  js      loc_180091C35
0x18009181d  mov     rax, [rbp+1F0h+var_258]
0x180091821  mov     rcx, [rbp+1F0h+var_250]
0x180091825  cmp     rax, rcx
0x180091828  jz      short loc_18009187D
0x18009182a  xorps   xmm0, xmm0
0x18009182d  movdqa  [rsp+2F0h+var_280], xmm0
0x180091833  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180091838  sub     rcx, rax
0x18009183b  sar     rcx, 1
0x18009183e  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x180091843  lea     rax, aSystemproductn; "SystemProductName"
0x18009184a  mov     [rsp+2F0h+var_290], rax
0x18009184f  mov     [rsp+2F0h+var_288], r14
0x180091854  lea     rax, [rsp+2F0h+var_280]
0x180091859  mov     [rsp+2F0h+var_2D0], rax
0x18009185e  mov     r9b, 1
0x180091861  lea     r8, [rsp+2F0h+var_2A0]
0x180091866  lea     rdx, [rsp+2F0h+var_290]
0x18009186b  mov     rcx, rdi
0x18009186e  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180091873  mov     ebx, eax
0x180091875  test    eax, eax
0x180091877  js      loc_180091C35
0x18009187d  mov     rcx, [rbp+1F0h+var_218]
0x180091881  mov     rax, [rbp+1F0h+var_210]
0x180091885  cmp     rcx, rax
0x180091888  jz      short loc_1800918E1
0x18009188a  xorps   xmm0, xmm0
0x18009188d  movdqa  [rsp+2F0h+var_280], xmm0
0x180091893  mov     qword ptr [rsp+2F0h+var_2A0], rcx
0x180091898  sub     rax, rcx
0x18009189b  sar     rax, 1
0x18009189e  mov     qword ptr [rsp+2F0h+var_2A0+8], rax
0x1800918a3  lea     rax, aBiosversion; "BIOSVersion"
0x1800918aa  mov     [rsp+2F0h+var_290], rax
0x1800918af  mov     [rsp+2F0h+var_288], 0Bh
0x1800918b8  lea     rax, [rsp+2F0h+var_280]
0x1800918bd  mov     [rsp+2F0h+var_2D0], rax
0x1800918c2  mov     r9b, 1
0x1800918c5  lea     r8, [rsp+2F0h+var_2A0]
0x1800918ca  lea     rdx, [rsp+2F0h+var_290]
0x1800918cf  mov     rcx, rdi
0x1800918d2  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x1800918d7  mov     ebx, eax
0x1800918d9  test    eax, eax
0x1800918db  js      loc_180091C35
0x1800918e1  lea     rax, [rsp+2F0h+var_2B0]
0x1800918e6  mov     [rsp+2F0h+var_2D0], rax; bool *
0x1800918eb  xor     r9d, r9d; unsigned int
0x1800918ee  lea     r8, aInstalldate; "InstallDate"
0x1800918f5  lea     rdx, aSoftwareMicros_33; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800918fc  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180091903  call    ?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z; UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)
0x180091908  test    eax, eax
0x18009190a  jz      loc_180091993
0x180091910  cmp     [rsp+2F0h+var_2B0], 0
0x180091915  jnz     short loc_180091993
0x180091917  mov     r8d, eax
0x18009191a  lea     rdx, aU_0; "%u"
0x180091921  lea     rcx, [rbp+1F0h+var_198]
0x180091925  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18009192a  mov     ebx, eax
0x18009192c  test    eax, eax
0x18009192e  js      loc_180091C35
0x180091934  xorps   xmm0, xmm0
0x180091937  movdqa  [rsp+2F0h+var_280], xmm0
0x18009193d  mov     rax, [rbp+1F0h+var_198]
0x180091941  mov     qword ptr [rsp+2F0h+var_2A0], rax
0x180091946  mov     rcx, [rbp+1F0h+var_190]
0x18009194a  sub     rcx, rax
0x18009194d  sar     rcx, 1
0x180091950  mov     qword ptr [rsp+2F0h+var_2A0+8], rcx
0x180091955  lea     rax, aOsinstalldate; "OSInstallDate"
0x18009195c  mov     [rsp+2F0h+var_290], rax
0x180091961  mov     [rsp+2F0h+var_288], 0Dh
  ... truncated ...
```
