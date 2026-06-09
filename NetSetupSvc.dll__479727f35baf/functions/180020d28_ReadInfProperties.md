# ReadInfProperties

- ea: `0x180020d28`
- end: `0x18002134a`
- name: `ReadInfProperties`
- size: `1570`
- prototype: `__int64 __fastcall(struct NetSetupDevice *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, int *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x180021650`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180003568`
- `0x1800078d0`
- `0x180008854`
- `0x18000d384`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x180018490`
- `0x18001a874`
- `0x18001d584`
- `0x18001d89c`
- `0x180020c28`
- `0x180020d28`
- `0x180022370`
- `0x18002498c`
- `0x18002923c`
- `0x1800298c8`

## import_xrefs

- `ext-ms-win-setupapi-inf-l1-1-0!SetupOpenInfFileW` at `0x180020ebd`
- `ext-ms-win-setupapi-inf-l1-1-0!SetupOpenInfFileW` at `0x180020ebd`

## string_xrefs

- `0x1800211d5`: `*AccessType`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ReadInfProperties(
        struct NetSetupDevice *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        int *a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8,
        unsigned __int64 *a9,
        unsigned __int64 *a10,
        unsigned __int64 *a11,
        unsigned __int64 *a12,
        unsigned __int64 *a13)
{
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  const WCHAR *v20; // rax
  HINF v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdx
  const wchar_t *v26; // rax
  const wchar_t *v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned int DatabaseForBestMatchingIfType; // eax
  int v31; // eax
  __int64 v32; // r10
  char v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  const wchar_t *v36; // rax
  const wchar_t *v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rdx
  const wchar_t *v42; // rax
  const wchar_t *v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rax
  __int64 v47; // rdx
  const wchar_t *v48; // rax
  const wchar_t *v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rax
  __int64 v53; // r10
  __int64 v54; // rax
  __int64 v55; // rdx
  const wchar_t *v56; // rax
  const wchar_t *v57; // r8
  __int64 v58; // rdx
  __int64 v59; // r8
  int v60; // ecx
  __int64 v61; // rax
  __int64 v62; // rdx
  const wchar_t *v63; // rax
  const wchar_t *v64; // r8
  unsigned __int64 OptionalDwordFromInfFile; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rax
  __int64 v69; // rdx
  const wchar_t *v70; // rax
  const wchar_t *v71; // r8
  unsigned __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rax
  __int64 v76; // rdx
  const wchar_t *v77; // rax
  const wchar_t *v78; // r8
  unsigned __int64 v79; // rax
  __int64 v80; // rdx
  __int64 v81; // r8
  __int64 v82; // rax
  __int64 v83; // rdx
  const wchar_t *v84; // rax
  const wchar_t *v85; // r8
  unsigned __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // rax
  __int64 v90; // rdx
  const wchar_t *v91; // rax
  const wchar_t *v92; // r8
  unsigned __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // rax
  __int64 v97; // rdx
  const wchar_t *v98; // rax
  const wchar_t *v99; // r8
  unsigned __int64 v100; // rax
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // rax
  __int64 v104; // rdx
  const wchar_t *v105; // rax
  const wchar_t *v106; // r8
  unsigned __int64 v107; // rax
  unsigned int v109; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 *v110; // [rsp+38h] [rbp-C8h]
  unsigned __int64 *v111; // [rsp+40h] [rbp-C0h]
  unsigned __int64 *v112; // [rsp+48h] [rbp-B8h]
  unsigned __int64 *v113; // [rsp+50h] [rbp-B0h]
  unsigned __int64 *v114; // [rsp+58h] [rbp-A8h]
  unsigned __int64 *v115; // [rsp+60h] [rbp-A0h]
  unsigned __int64 *v116; // [rsp+68h] [rbp-98h]
  _BYTE v117[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+90h] [rbp-70h] BYREF
  HINF v119; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v120[32]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v121[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v122[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v123[32]; // [rsp+1C8h] [rbp+C8h] BYREF

  v110 = a7;
  v111 = a8;
  v112 = a9;
  v113 = a10;
  v114 = a11;
  v115 = a12;
  v116 = a13;
  if ( !(unsigned __int8)IsSetupFindFirstLineWPresent()
    || !(unsigned __int8)IsSetupFindFirstLineWPresent()
    || !(unsigned __int8)IsSetupFindFirstLineWPresent()
    || !(unsigned __int8)IsSetupFindFirstLineWPresent() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_ebd892180d513f9593fffe48317335f2_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024846);
    throw (HResultException *)pExceptionObject;
  }
  std::wstring::wstring(v120);
  std::wstring::wstring(v123);
  std::wstring::wstring(v122);
  std::wstring::wstring(v121);
  if ( !(unsigned __int8)NetSetupDevice::GetStringProperty(a1, &DEVPKEY_Device_DriverInfPath, v120)
    || !(unsigned __int8)NetSetupDevice::GetStringProperty(a1, &DEVPKEY_Device_DriverInfSection, v123) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_ebd892180d513f9593fffe48317335f2_Traceguids);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  NetSetupDevice::GetStringProperty(a1, &DEVPKEY_Device_DriverInfSectionExt, v122);
  v17 = std::operator+<wchar_t>(v117, v123, v122);
  std::wstring::operator=(v121, v17);
  std::wstring::_Tidy_deallocate(v117);
  v20 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v18, v19);
  v21 = SetupOpenInfFileW(v20, 0, 2u, 0);
  if ( (((unsigned __int64)v21 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    Win32Exception::ThrowLastError();
  v119 = v21;
  v24 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v22, v23);
  v26 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v25, v24);
  if ( !ReadDwordFromInfFile((struct InfFile *)&v119, v26, v27, L"*IfType", a2) )
  {
    DatabaseForBestMatchingIfType = QueryDatabaseForBestMatchingIfType(a1);
    v29 = DatabaseForBestMatchingIfType;
    *a2 = DatabaseForBestMatchingIfType;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v28, DatabaseForBestMatchingIfType);
      WPP_SF_Sd(*(_QWORD *)(v32 + 16), 41, (unsigned int)WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v31, v33);
    }
  }
  v34 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v28, v29);
  v36 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v35, v34);
  if ( !ReadDwordFromInfFile((struct InfFile *)&v119, v36, v37, L"*MediaType", a3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_ebd892180d513f9593fffe48317335f2_Traceguids);
    *a3 = 0;
  }
  v40 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v38, v39);
  v42 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v41, v40);
  if ( !ReadDwordFromInfFile((struct InfFile *)&v119, v42, v43, L"*PhysicalMediaType", a4) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_ebd892180d513f9593fffe48317335f2_Traceguids);
    *a4 = 0;
  }
  v46 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v44, v45);
  v48 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v47, v46);
  if ( !ReadDwordFromInfFile((struct InfFile *)&v119, v48, v49, L"Characteristics", a5) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v52 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v50, v51);
      WPP_SF_S(*(_QWORD *)(v53 + 16), 44, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v52);
    }
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  v109 = 0;
  v54 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v50, v51);
  v56 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v55, v54);
  if ( ReadDwordFromInfFile((struct InfFile *)&v119, v56, v57, L"EnableDhcp", &v109) )
    v60 = 2 - (v109 != 0);
  else
    v60 = 0;
  *a6 = v60;
  v61 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v58, v59);
  v63 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v62, v61);
  OptionalDwordFromInfFile = ReadOptionalDwordFromInfFile((struct InfFile *)&v119, v63, v64, L"BusType");
  *v110 = OptionalDwordFromInfFile;
  v68 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v66, v67);
  v70 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v69, v68);
  v72 = ReadOptionalDwordFromInfFile((struct InfFile *)&v119, v70, v71, L"Port1DeviceNumber");
  *v111 = v72;
  v75 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v73, v74);
  v77 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v76, v75);
  v79 = ReadOptionalDwordFromInfFile((struct InfFile *)&v119, v77, v78, L"Port1FunctionNumber");
  *v112 = v79;
  v82 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v80, v81);
  v84 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v83, v82);
  v86 = ReadOptionalDwordFromInfFile((struct InfFile *)&v119, v84, v85, L"*IfConnectorPresent");
  *v113 = v86;
  v89 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v87, v88);
  v91 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v90, v89);
  v93 = ReadOptionalDwordFromInfFile((struct InfFile *)&v119, v91, v92, L"*AccessType");
  *v114 = v93;
  v96 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v94, v95);
  v98 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v97, v96);
  v100 = ReadOptionalDwordFromInfFile((struct InfFile *)&v119, v98, v99, L"*ConnectionType");
  *v115 = v100;
  v103 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v121, v101, v102);
  v105 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v120, v104, v103);
  v107 = ReadOptionalDwordFromInfFile((struct InfFile *)&v119, v105, v106, L"*DirectionType");
  *v116 = v107;
  std::unique_ptr<void,SafeHandleCleanupIsCloseInf>::~unique_ptr<void,SafeHandleCleanupIsCloseInf>(&v119);
  std::wstring::_Tidy_deallocate(v121);
  std::wstring::_Tidy_deallocate(v122);
  std::wstring::_Tidy_deallocate(v123);
  return std::wstring::_Tidy_deallocate(v120);
}

```

## disassembly

```asm
0x180020d28  push    rbp
0x180020d2a  push    rbx
0x180020d2b  push    rsi
0x180020d2c  push    rdi
0x180020d2d  push    r12
0x180020d2f  push    r13
0x180020d31  push    r14
0x180020d33  push    r15
0x180020d35  lea     rbp, [rsp-0F8h]
0x180020d3d  sub     rsp, 1F8h
0x180020d44  mov     rax, cs:__security_cookie
0x180020d4b  xor     rax, rsp
0x180020d4e  mov     [rbp+130h+var_48], rax
0x180020d55  mov     r15, r9
0x180020d58  mov     r14, r8
0x180020d5b  mov     rsi, rdx
0x180020d5e  mov     rdi, rcx
0x180020d61  mov     r12, [rbp+130h+arg_20]
0x180020d68  mov     r13, [rbp+130h+arg_28]
0x180020d6f  mov     rax, [rbp+130h+arg_30]
0x180020d76  mov     [rsp+230h+var_1F8], rax
0x180020d7b  mov     rax, [rbp+130h+arg_38]
0x180020d82  mov     [rsp+230h+var_1F0], rax
0x180020d87  mov     rax, [rbp+130h+arg_40]
0x180020d8e  mov     [rsp+230h+var_1E8], rax
0x180020d93  mov     rax, [rbp+130h+arg_48]
0x180020d9a  mov     [rsp+230h+var_1E0], rax
0x180020d9f  mov     rax, [rbp+130h+arg_50]
0x180020da6  mov     [rsp+230h+var_1D8], rax
0x180020dab  mov     rax, [rbp+130h+arg_58]
0x180020db2  mov     [rsp+230h+var_1D0], rax
0x180020db7  mov     rax, [rbp+130h+arg_60]
0x180020dbe  mov     [rsp+230h+var_1C8], rax
0x180020dc3  call    IsSetupFindFirstLineWPresent
0x180020dc8  test    al, al
0x180020dca  jz      loc_1800212FD
0x180020dd0  call    IsSetupFindFirstLineWPresent
0x180020dd5  test    al, al
0x180020dd7  jz      loc_1800212FD
0x180020ddd  call    IsSetupFindFirstLineWPresent
0x180020de2  test    al, al
0x180020de4  jz      loc_1800212FD
0x180020dea  call    IsSetupFindFirstLineWPresent
0x180020def  test    al, al
0x180020df1  jz      loc_1800212FD
0x180020df7  lea     rcx, [rbp+130h+var_C8]
0x180020dfb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020e00  nop
0x180020e01  lea     rcx, [rbp+130h+var_68]
0x180020e08  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020e0d  nop
0x180020e0e  lea     rcx, [rbp+130h+var_88]
0x180020e15  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020e1a  nop
0x180020e1b  lea     rcx, [rbp+130h+var_A8]
0x180020e22  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020e27  nop
0x180020e28  lea     r8, [rbp+130h+var_C8]
0x180020e2c  lea     rdx, DEVPKEY_Device_DriverInfPath
0x180020e33  mov     rcx, rdi
0x180020e36  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x180020e3b  test    al, al
0x180020e3d  jz      loc_1800212B0
0x180020e43  lea     r8, [rbp+130h+var_68]
0x180020e4a  lea     rdx, DEVPKEY_Device_DriverInfSection
0x180020e51  mov     rcx, rdi
0x180020e54  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x180020e59  test    al, al
0x180020e5b  jz      loc_1800212B0
0x180020e61  lea     r8, [rbp+130h+var_88]
0x180020e68  lea     rdx, DEVPKEY_Device_DriverInfSectionExt
0x180020e6f  mov     rcx, rdi
0x180020e72  call    ?GetStringProperty@NetSetupDevice@@QEAA_NAEBU_DEVPROPKEY@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetupDevice::GetStringProperty(_DEVPROPKEY const &,std::wstring &)
0x180020e77  lea     r8, [rbp+130h+var_88]
0x180020e7e  lea     rdx, [rbp+130h+var_68]
0x180020e85  lea     rcx, [rsp+230h+var_1C0]
0x180020e8a  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@0@Z; std::operator+<wchar_t>(std::wstring const &,std::wstring const &)
0x180020e8f  mov     rdx, rax
0x180020e92  lea     rcx, [rbp+130h+var_A8]
0x180020e99  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020e9e  lea     rcx, [rsp+230h+var_1C0]
0x180020ea3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020ea8  lea     rcx, [rbp+130h+var_C8]
0x180020eac  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020eb1  mov     rcx, rax; FileName
0x180020eb4  xor     r9d, r9d; ErrorLine
0x180020eb7  xor     edx, edx; InfClass
0x180020eb9  lea     r8d, [r9+2]; InfStyle
0x180020ebd  call    cs:__imp_SetupOpenInfFileW
0x180020ec3  lea     rcx, [rax+1]
0x180020ec7  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180020ece  jnz     short loc_180020ED6
0x180020ed0  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x180020ed6  mov     [rbp+130h+var_D0], rax
0x180020eda  lea     rcx, [rbp+130h+var_A8]
0x180020ee1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020ee6  mov     r8, rax
0x180020ee9  lea     rcx, [rbp+130h+var_C8]
0x180020eed  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020ef2  mov     rdx, rax; wchar_t *
0x180020ef5  mov     [rsp+230h+var_210], rsi; unsigned int *
0x180020efa  lea     r9, aIftype; "*IfType"
0x180020f01  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180020f05  call    ?ReadDwordFromInfFile@@YA_NAEAVInfFile@@PEB_W11AEAK@Z; ReadDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *,ulong &)
0x180020f0a  lea     rbx, WPP_GLOBAL_Control
0x180020f11  test    al, al
0x180020f13  jnz     short loc_180020F5B
0x180020f15  mov     rcx, rdi; struct NetSetupDevice *
0x180020f18  call    ?QueryDatabaseForBestMatchingIfType@@YAKAEAVNetSetupDevice@@@Z; QueryDatabaseForBestMatchingIfType(NetSetupDevice &)
0x180020f1d  mov     r8d, eax
0x180020f20  mov     [rsi], eax
0x180020f22  mov     r10, cs:WPP_GLOBAL_Control
0x180020f29  cmp     r10, rbx
0x180020f2c  jz      short loc_180020F5B
0x180020f2e  cmp     byte ptr [r10+19h], 3
0x180020f33  jb      short loc_180020F5B
0x180020f35  lea     rcx, [rbp+130h+var_C8]
0x180020f39  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020f3e  mov     r9, rax
0x180020f41  mov     edx, 29h ; ')'
0x180020f46  mov     dword ptr [rsp+230h+var_210], r8d
0x180020f4b  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180020f52  mov     rcx, [r10+10h]
0x180020f56  call    WPP_SF_Sd
0x180020f5b  lea     rcx, [rbp+130h+var_A8]
0x180020f62  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020f67  mov     r8, rax
0x180020f6a  lea     rcx, [rbp+130h+var_C8]
0x180020f6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020f73  mov     rdx, rax; wchar_t *
0x180020f76  mov     [rsp+230h+var_210], r14; unsigned int *
0x180020f7b  lea     r9, aMediatype; "*MediaType"
0x180020f82  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180020f86  call    ?ReadDwordFromInfFile@@YA_NAEAVInfFile@@PEB_W11AEAK@Z; ReadDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *,ulong &)
0x180020f8b  xor     edi, edi
0x180020f8d  test    al, al
0x180020f8f  jnz     short loc_180020FB9
0x180020f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f98  cmp     rcx, rbx
0x180020f9b  jz      short loc_180020FB6
0x180020f9d  cmp     byte ptr [rcx+19h], 3
0x180020fa1  jb      short loc_180020FB6
0x180020fa3  lea     edx, [rdi+2Ah]
0x180020fa6  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180020fad  mov     rcx, [rcx+10h]
0x180020fb1  call    WPP_SF_
0x180020fb6  mov     [r14], edi
0x180020fb9  lea     rcx, [rbp+130h+var_A8]
0x180020fc0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020fc5  mov     r8, rax
0x180020fc8  lea     rcx, [rbp+130h+var_C8]
0x180020fcc  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020fd1  mov     rdx, rax; wchar_t *
0x180020fd4  mov     [rsp+230h+var_210], r15; unsigned int *
0x180020fd9  lea     r9, aPhysicalmediat; "*PhysicalMediaType"
0x180020fe0  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180020fe4  call    ?ReadDwordFromInfFile@@YA_NAEAVInfFile@@PEB_W11AEAK@Z; ReadDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *,ulong &)
0x180020fe9  test    al, al
0x180020feb  jnz     short loc_180021017
0x180020fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ff4  cmp     rcx, rbx
0x180020ff7  jz      short loc_180021014
0x180020ff9  cmp     byte ptr [rcx+19h], 3
0x180020ffd  jb      short loc_180021014
0x180020fff  mov     edx, 2Bh ; '+'
0x180021004  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18002100b  mov     rcx, [rcx+10h]
0x18002100f  call    WPP_SF_
0x180021014  mov     [r15], edi
0x180021017  lea     rcx, [rbp+130h+var_A8]
0x18002101e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021023  mov     r8, rax
0x180021026  lea     rcx, [rbp+130h+var_C8]
0x18002102a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002102f  mov     rdx, rax; wchar_t *
0x180021032  mov     [rsp+230h+var_210], r12; unsigned int *
0x180021037  lea     r9, aCharacteristic; "Characteristics"
0x18002103e  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180021042  call    ?ReadDwordFromInfFile@@YA_NAEAVInfFile@@PEB_W11AEAK@Z; ReadDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *,ulong &)
0x180021047  test    al, al
0x180021049  jnz     short loc_18002109E
0x18002104b  mov     r10, cs:WPP_GLOBAL_Control
0x180021052  cmp     r10, rbx
0x180021055  jz      short loc_18002107F
0x180021057  cmp     byte ptr [r10+19h], 2
0x18002105c  jb      short loc_18002107F
0x18002105e  lea     rcx, [rbp+130h+var_C8]
0x180021062  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021067  mov     r9, rax
0x18002106a  mov     edx, 2Ch ; ','
0x18002106f  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180021076  mov     rcx, [r10+10h]
0x18002107a  call    WPP_SF_S
0x18002107f  mov     edx, 80070057h; int
0x180021084  lea     rcx, [rbp+130h+pExceptionObject]; this
0x180021088  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002108d  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180021094  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x180021098  call    _CxxThrowException_0
0x18002109e  mov     [rsp+230h+var_200], edi
0x1800210a2  lea     rcx, [rbp+130h+var_A8]
0x1800210a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800210ae  mov     r8, rax
0x1800210b1  lea     rcx, [rbp+130h+var_C8]
0x1800210b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800210ba  mov     rdx, rax; wchar_t *
0x1800210bd  lea     rax, [rsp+230h+var_200]
0x1800210c2  mov     [rsp+230h+var_210], rax; unsigned int *
0x1800210c7  lea     r9, aEnabledhcp; "EnableDhcp"
0x1800210ce  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x1800210d2  call    ?ReadDwordFromInfFile@@YA_NAEAVInfFile@@PEB_W11AEAK@Z; ReadDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *,ulong &)
0x1800210d7  test    al, al
0x1800210d9  jz      short loc_1800210E8
0x1800210db  mov     eax, [rsp+230h+var_200]
0x1800210df  neg     eax
0x1800210e1  sbb     ecx, ecx
0x1800210e3  add     ecx, 2
0x1800210e6  jmp     short loc_1800210EA
0x1800210e8  mov     ecx, edi
0x1800210ea  mov     [r13+0], ecx
0x1800210ee  lea     rcx, [rbp+130h+var_A8]
0x1800210f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800210fa  mov     r8, rax
0x1800210fd  lea     rcx, [rbp+130h+var_C8]
0x180021101  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021106  mov     rdx, rax; wchar_t *
0x180021109  lea     r9, aBustype; "BusType"
0x180021110  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180021114  call    ?ReadOptionalDwordFromInfFile@@YA_KAEAVInfFile@@PEB_W11@Z; ReadOptionalDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *)
0x180021119  mov     rcx, [rsp+230h+var_1F8]
0x18002111e  mov     [rcx], rax
0x180021121  lea     rcx, [rbp+130h+var_A8]
0x180021128  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002112d  mov     r8, rax
0x180021130  lea     rcx, [rbp+130h+var_C8]
0x180021134  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021139  mov     rdx, rax; wchar_t *
0x18002113c  lea     r9, aPort1devicenum; "Port1DeviceNumber"
0x180021143  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180021147  call    ?ReadOptionalDwordFromInfFile@@YA_KAEAVInfFile@@PEB_W11@Z; ReadOptionalDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *)
0x18002114c  mov     rcx, [rsp+230h+var_1F0]
0x180021151  mov     [rcx], rax
0x180021154  lea     rcx, [rbp+130h+var_A8]
0x18002115b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021160  mov     r8, rax
0x180021163  lea     rcx, [rbp+130h+var_C8]
0x180021167  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002116c  mov     rdx, rax; wchar_t *
0x18002116f  lea     r9, aPort1functionn; "Port1FunctionNumber"
0x180021176  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x18002117a  call    ?ReadOptionalDwordFromInfFile@@YA_KAEAVInfFile@@PEB_W11@Z; ReadOptionalDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *)
0x18002117f  mov     rcx, [rsp+230h+var_1E8]
0x180021184  mov     [rcx], rax
0x180021187  lea     rcx, [rbp+130h+var_A8]
0x18002118e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021193  mov     r8, rax
0x180021196  lea     rcx, [rbp+130h+var_C8]
0x18002119a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002119f  mov     rdx, rax; wchar_t *
0x1800211a2  lea     r9, aIfconnectorpre; "*IfConnectorPresent"
0x1800211a9  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x1800211ad  call    ?ReadOptionalDwordFromInfFile@@YA_KAEAVInfFile@@PEB_W11@Z; ReadOptionalDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800211b2  mov     rcx, [rsp+230h+var_1E0]
0x1800211b7  mov     [rcx], rax
0x1800211ba  lea     rcx, [rbp+130h+var_A8]
0x1800211c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800211c6  mov     r8, rax
0x1800211c9  lea     rcx, [rbp+130h+var_C8]
0x1800211cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800211d2  mov     rdx, rax; wchar_t *
0x1800211d5  lea     r9, aAccesstype; "*AccessType"
0x1800211dc  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x1800211e0  call    ?ReadOptionalDwordFromInfFile@@YA_KAEAVInfFile@@PEB_W11@Z; ReadOptionalDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800211e5  mov     rcx, [rsp+230h+var_1D8]
0x1800211ea  mov     [rcx], rax
0x1800211ed  lea     rcx, [rbp+130h+var_A8]
0x1800211f4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800211f9  mov     r8, rax
0x1800211fc  lea     rcx, [rbp+130h+var_C8]
0x180021200  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021205  mov     rdx, rax; wchar_t *
0x180021208  lea     r9, aConnectiontype; "*ConnectionType"
0x18002120f  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180021213  call    ?ReadOptionalDwordFromInfFile@@YA_KAEAVInfFile@@PEB_W11@Z; ReadOptionalDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *)
0x180021218  mov     rcx, [rsp+230h+var_1D0]
0x18002121d  mov     [rcx], rax
0x180021220  lea     rcx, [rbp+130h+var_A8]
0x180021227  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002122c  mov     r8, rax
0x18002122f  lea     rcx, [rbp+130h+var_C8]
0x180021233  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021238  mov     rdx, rax; wchar_t *
0x18002123b  lea     r9, aDirectiontype; "*DirectionType"
0x180021242  lea     rcx, [rbp+130h+var_D0]; struct InfFile *
0x180021246  call    ?ReadOptionalDwordFromInfFile@@YA_KAEAVInfFile@@PEB_W11@Z; ReadOptionalDwordFromInfFile(InfFile &,wchar_t const *,wchar_t const *,wchar_t const *)
0x18002124b  mov     rcx, [rsp+230h+var_1C8]
0x180021250  mov     [rcx], rax
0x180021253  lea     rcx, [rbp+130h+var_D0]
0x180021257  call    ??1?$unique_ptr@XUSafeHandleCleanupIsCloseInf@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupIsCloseInf>::~unique_ptr<void,SafeHandleCleanupIsCloseInf>(void)
0x18002125c  nop
  ... truncated ...
```
