# CAudioDevice::UpdateDeviceProperty(_tagpropertykey)

- ea: `0x180003de0`
- end: `0x18000461f`
- name: `?UpdateDeviceProperty@CAudioDevice@@QEAAJU_tagpropertykey@@@Z`
- size: `2111`
- prototype: `__int64 __fastcall(CAudioDevice *__hidden this, struct _tagpropertykey *__struct_ptr)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180003630`
- `0x180003de0`

## callees

- `0x180003de0`
- `0x180006b0c`
- `0x180010da8`
- `0x18001707c`
- `0x180025464`
- `0x180026478`
- `0x180026ff4`
- `0x180029024`
- `0x180033578`
- `0x18003e920`
- `0x18003f780`
- `0x180058dbc`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004198`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004198`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800043e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003e17`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003ed8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180003ed8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003f74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004189`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800042d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800043d5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180003f74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004189`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800042d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800043d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003fb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004236`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004358`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800043be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003fb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004099`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004236`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004291`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004358`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800043be`
- `api-ms-win-devices-swdevice-l1-1-0!SwDevicePropertySet` at `0x180004002`
- `api-ms-win-devices-swdevice-l1-1-0!SwDevicePropertySet` at `0x180004002`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x180003f14`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x180004064`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x180003f14`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x180004064`

## string_xrefs

- `0x18000407f`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000414d`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000421a`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004263`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004320`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000436a`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x1800043a2`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x1800043fb`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004511`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x18000457d`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x1800045da`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`
- `0x180004608`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CAudioDevice::UpdateDeviceProperty(CAudioDevice *this, struct _tagpropertykey *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  void *v5; // rbx
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  int v9; // r15d
  int v10; // eax
  DWORD pid; // eax
  HRESULT v12; // eax
  DWORD v13; // eax
  __int64 v15; // rdx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 *v19; // rdx
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // eax
  __int64 v23; // r12
  __int64 v24; // r9
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  char *v31; // [rsp+28h] [rbp-D8h]
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  int v37[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _tagpropertykey rclsid; // [rsp+80h] [rbp-80h] BYREF
  struct _RTL_CRITICAL_SECTION *v39; // [rsp+A0h] [rbp-60h]
  _DEVPROPERTY v40; // [rsp+B0h] [rbp-50h] BYREF
  struct _DEVPROPERTY v41; // [rsp+E0h] [rbp-20h] BYREF
  struct _DEVPROPERTY v42; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v39 = v4;
  *(_OWORD *)pvar = 0;
  v35 = 0;
  v32 = 0;
  lpsz = 0;
  v5 = 0;
  pv = 0;
  v37[0] = 2;
  if ( *((_DWORD *)this + 22) != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
    }
LABEL_56:
    PropVariantClear(pvar);
    if ( !v4 )
      return 0;
    goto LABEL_19;
  }
  v6 = (__int64 *)*((_QWORD *)this + 5);
  v7 = *v6;
  v32 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v7 + 32))(v6, 0, &v32);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v8,
      v28);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    goto LABEL_40;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v32 + 40LL))(
          v32,
          a2,
          pvar);
  v9 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F9,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
      (const char *)(unsigned int)v10,
      v28);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    goto LABEL_40;
  }
  pid = a2->pid;
  if ( pid != 12 )
  {
    if ( pid == 2 && !memcmp_0(a2, &PKEY_Device_DeviceDesc, 0x10u) )
    {
      v18 = memcmp_0(a2, &PKEY_Device_DeviceDesc, 0x10u);
      v15 = 0;
      if ( !v18 )
      {
        wil::unique_struct<tagPROPVARIANT,long (*)(tagPROPVARIANT *),&long PropVariantClear(tagPROPVARIANT *),void (*)(tagPROPVARIANT *),&void PropVariantInit(tagPROPVARIANT *)>::reset(
          pvar,
          0);
        (*(void (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v32 + 40LL))(
          v32,
          &PKEY_Device_FriendlyName,
          pvar);
        if ( LOWORD(pvar[0]) != 31 )
        {
LABEL_35:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
          goto LABEL_56;
        }
        v23 = -1;
        v24 = -1;
        do
          ++v24;
        while ( *((_WORD *)pvar[1] + v24) );
        v25 = InitializeDevProperty(&v40, &DEVPKEY_Device_DeviceDesc, 0x12u, 2 * v24 + 2, pvar[1], 0);
        v9 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA20,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
            (const char *)(unsigned int)v25,
            v29);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
          goto LABEL_40;
        }
        do
          ++v23;
        while ( *((_WORD *)pvar[1] + v23) );
        v26 = InitializeDevProperty(&v41, &DEVPKEY_Device_FriendlyName, 0x12u, 2 * v23 + 2, pvar[1], 0);
        v9 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA28,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
            (const char *)(unsigned int)v26,
            v30);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
          goto LABEL_40;
        }
        v27 = InitializeDevProperty(&v42, &DEVPKEY_Device_FriendlyNameAttributes, 7u, 4u, v37, 0);
        v9 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA30,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
            (const char *)(unsigned int)v27,
            v28);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
          goto LABEL_40;
        }
        v15 = 3;
      }
LABEL_24:
      v16 = SwDevicePropertySet(*((_QWORD *)this + 3), v15, &v40);
      if ( v16 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA36,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
          (const char *)(unsigned int)v16,
          v28);
      if ( a2->pid == 2 && !memcmp_0(a2, &PKEY_Device_DeviceDesc, 0x10u) )
      {
        v40.CompKey.Key = (DEVPROPKEY)PKEY_DeviceInterface_FriendlyName;
        v17 = SwDeviceInterfacePropertySet(*((_QWORD *)this + 3), *((_QWORD *)this + 2), 1, &v40);
        v9 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA43,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
            (const char *)(unsigned int)v17,
            v28);
          if ( !v5 )
          {
LABEL_31:
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
LABEL_40:
            PropVariantClear(pvar);
            if ( v4 )
              LeaveCriticalSection(v4);
            return (unsigned int)v9;
          }
LABEL_30:
          CoTaskMemFree(v5);
          goto LABEL_31;
        }
      }
LABEL_11:
      v13 = a2->pid;
      if ( v13 == 6 )
      {
        v19 = PKEY_Endpoint_Device_NAME;
      }
      else
      {
        if ( v13 != 2 )
        {
          if ( v13 != 26 || memcmp_0(a2, PKEY_Endpoint_DeviceInterface_FriendlyName, 0x10u) )
          {
LABEL_14:
            if ( v5 )
              CoTaskMemFree(v5);
            if ( v32 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
            PropVariantClear(pvar);
            if ( !v4 )
              return 0;
LABEL_19:
            LeaveCriticalSection(v4);
            return 0;
          }
LABEL_45:
          rclsid = PKEY_Device_DeviceDesc;
          CAudioDevice::UpdateDeviceProperty(this, &rclsid);
          goto LABEL_14;
        }
        v19 = PKEY_Endpoint_Devnode;
      }
      if ( memcmp_0(a2, v19, 0x10u) )
        goto LABEL_14;
      goto LABEL_45;
    }
LABEL_6:
    v40.CompKey.Key.fmtid = a2->fmtid;
    v40.CompKey.Key.pid = a2->pid;
    lpsz = 0;
    v12 = StringFromCLSID(&a2->fmtid, &lpsz);
    v9 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4C,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v12,
        v28);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      goto LABEL_40;
    }
    v9 = PROPVARIANT2DEVPROP(pvar, &v40);
    if ( v9 < 0 )
    {
      LODWORD(v31) = LOWORD(pvar[0]);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA50,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v9,
        (int)"Unsupported type 0x%04x for property %ls, %d",
        v31,
        lpsz,
        a2->pid);
      if ( lpsz )
        CoTaskMemFree(lpsz);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      goto LABEL_40;
    }
    v9 = SwDeviceInterfacePropertySet(*((_QWORD *)this + 3), *((_QWORD *)this + 2), 1, &v40);
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA55,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v9,
        (int)"Failed to set property for device interface %ls",
        *((const char **)this + 2));
      if ( lpsz )
        CoTaskMemFree(lpsz);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      goto LABEL_40;
    }
    if ( lpsz )
      CoTaskMemFree(lpsz);
    goto LABEL_11;
  }
  if ( memcmp_0(a2, &PKEY_DeviceClass_IconPath, 0x10u) )
    goto LABEL_6;
  if ( memcmp_0(a2, &PKEY_DeviceClass_IconPath, 0x10u) )
  {
    v15 = 0;
    goto LABEL_24;
  }
  if ( LOWORD(pvar[0]) != 31 )
    goto LABEL_35;
  pv = 0;
  v20 = StringToStringList((unsigned __int16 *)pvar[1], &pv, (unsigned __int64 *)&lpsz);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v5 = pv;
    v22 = InitializeDevProperty(&v40, &DEVPKEY_DrvPkg_Icon, 0x2012u, (unsigned int)lpsz, pv, 0);
    v9 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0D,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
        (const char *)(unsigned int)v22,
        v28);
      if ( !v5 )
        goto LABEL_31;
      goto LABEL_30;
    }
    v15 = 1;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA06,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audiodevice.cpp",
    (const char *)(unsigned int)v20,
    v28);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  PropVariantClear(pvar);
  if ( v4 )
    LeaveCriticalSection(v4);
  return v21;
}

```

## disassembly

```asm
0x180003de0  mov     [rsp-8+arg_10], rbx
0x180003de5  push    rbp
0x180003de6  push    rsi
0x180003de7  push    rdi
0x180003de8  push    r12
0x180003dea  push    r13
0x180003dec  push    r14
0x180003dee  push    r15
0x180003df0  lea     rbp, [rsp-50h]
0x180003df5  sub     rsp, 150h
0x180003dfc  mov     rax, cs:__security_cookie
0x180003e03  xor     rax, rsp
0x180003e06  mov     [rbp+80h+var_40], rax
0x180003e0a  mov     rdi, rdx
0x180003e0d  mov     r14, rcx
0x180003e10  lea     rsi, [rcx+30h]
0x180003e14  mov     rcx, rsi; lpCriticalSection
0x180003e17  call    cs:__imp_EnterCriticalSection
0x180003e1d  mov     [rbp+80h+var_E0], rsi
0x180003e21  xorps   xmm0, xmm0
0x180003e24  xor     eax, eax
0x180003e26  movups  xmmword ptr [rsp+180h+pvar], xmm0
0x180003e2b  mov     [rsp+180h+var_120], rax
0x180003e30  xor     r13d, r13d
0x180003e33  mov     ecx, r13d
0x180003e36  mov     [rsp+180h+var_140], rcx
0x180003e3b  mov     [rsp+180h+lpsz], r13
0x180003e40  mov     ebx, r13d
0x180003e43  mov     [rsp+180h+pv], rbx
0x180003e48  mov     [rsp+180h+var_110], 2
0x180003e50  mov     r9d, [r14+58h]
0x180003e54  cmp     r9d, 1
0x180003e58  jnz     loc_18000429C
0x180003e5e  mov     rcx, [r14+28h]
0x180003e62  mov     rax, [rcx]
0x180003e65  mov     [rsp+180h+var_140], r13
0x180003e6a  lea     r8, [rsp+180h+var_140]
0x180003e6f  xor     edx, edx
0x180003e71  mov     rax, [rax+20h]
0x180003e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e7a  mov     r15d, eax
0x180003e7d  test    eax, eax
0x180003e7f  js      loc_180004360
0x180003e85  mov     rcx, [rsp+180h+var_140]
0x180003e8a  mov     rax, [rcx]
0x180003e8d  lea     r8, [rsp+180h+pvar]
0x180003e92  mov     rdx, rdi
0x180003e95  mov     rax, [rax+28h]
0x180003e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e9e  mov     r15d, eax
0x180003ea1  test    eax, eax
0x180003ea3  js      loc_180004259
0x180003ea9  mov     eax, [rdi+10h]
0x180003eac  cmp     eax, 0Ch
0x180003eaf  jz      loc_180003FBD
0x180003eb5  cmp     eax, 2
0x180003eb8  jz      loc_1800040AF
0x180003ebe  movups  xmm0, xmmword ptr [rdi]
0x180003ec1  movaps  xmmword ptr [rbp+80h+var_D0.CompKey.Key.fmtid.Data1], xmm0
0x180003ec5  mov     eax, [rdi+10h]
0x180003ec8  mov     [rbp+80h+var_D0.CompKey.Key.pid], eax
0x180003ecb  mov     [rsp+180h+lpsz], r13
0x180003ed0  lea     rdx, [rsp+180h+lpsz]; lplpsz
0x180003ed5  mov     rcx, rdi; rclsid
0x180003ed8  call    cs:__imp_StringFromCLSID
0x180003ede  mov     r15d, eax
0x180003ee1  test    eax, eax
0x180003ee3  js      loc_180004316
0x180003ee9  lea     rdx, [rbp+80h+var_D0]; struct _DEVPROPERTY *
0x180003eed  lea     rcx, [rsp+180h+pvar]; pvar
0x180003ef2  call    ?PROPVARIANT2DEVPROP@@YAJAEAUtagPROPVARIANT@@PEAU_DEVPROPERTY@@@Z; PROPVARIANT2DEVPROP(tagPROPVARIANT &,_DEVPROPERTY *)
0x180003ef7  mov     r15d, eax
0x180003efa  test    eax, eax
0x180003efc  js      loc_1800041E8
0x180003f02  lea     r9, [rbp+80h+var_D0]
0x180003f06  mov     r8d, 1
0x180003f0c  mov     rdx, [r14+10h]
0x180003f10  mov     rcx, [r14+18h]
0x180003f14  call    cs:__imp_SwDeviceInterfacePropertySet
0x180003f1a  mov     r15d, eax
0x180003f1d  test    eax, eax
0x180003f1f  js      loc_18000412E
0x180003f25  mov     rcx, [rsp+180h+lpsz]; pv
0x180003f2a  test    rcx, rcx
0x180003f2d  jz      short loc_180003F35
0x180003f2f  call    cs:__imp_CoTaskMemFree
0x180003f35  mov     eax, [rdi+10h]
0x180003f38  cmp     eax, 6
0x180003f3b  jz      loc_1800041A6
0x180003f41  cmp     eax, 2
0x180003f44  jz      loc_1800042E8
0x180003f4a  cmp     eax, 1Ah
0x180003f4d  jz      loc_1800042F4
0x180003f53  test    rbx, rbx
0x180003f56  jnz     short loc_180003FB2
0x180003f58  mov     rcx, [rsp+180h+var_140]
0x180003f5d  test    rcx, rcx
0x180003f60  jz      short loc_180003F6F
0x180003f62  mov     rax, [rcx]
0x180003f65  mov     rax, [rax+10h]
0x180003f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f6e  nop
0x180003f6f  lea     rcx, [rsp+180h+pvar]; pvar
0x180003f74  call    cs:__imp_PropVariantClear
0x180003f7a  nop
0x180003f7b  test    rsi, rsi
0x180003f7e  jz      short loc_180003F89
0x180003f80  mov     rcx, rsi; lpCriticalSection
0x180003f83  call    cs:__imp_LeaveCriticalSection
0x180003f89  xor     eax, eax
0x180003f8b  mov     rcx, [rbp+80h+var_40]
0x180003f8f  xor     rcx, rsp; StackCookie
0x180003f92  call    __security_check_cookie
0x180003f97  mov     rbx, [rsp+180h+arg_10]
0x180003f9f  add     rsp, 150h
0x180003fa6  pop     r15
0x180003fa8  pop     r14
0x180003faa  pop     r13
0x180003fac  pop     r12
0x180003fae  pop     rdi
0x180003faf  pop     rsi
0x180003fb0  pop     rbp
0x180003fb1  retn
0x180003fb2  mov     rcx, rbx; pv
0x180003fb5  call    cs:__imp_CoTaskMemFree
0x180003fbb  jmp     short loc_180003F58
0x180003fbd  mov     r8d, 10h; Size
0x180003fc3  lea     rdx, PKEY_DeviceClass_IconPath; Buf2
0x180003fca  mov     rcx, rdi; Buf1
0x180003fcd  call    memcmp_0
0x180003fd2  test    eax, eax
0x180003fd4  jnz     loc_180003EBE
0x180003fda  mov     r8d, 10h; Size
0x180003fe0  lea     rdx, PKEY_DeviceClass_IconPath; Buf2
0x180003fe7  mov     rcx, rdi; Buf1
0x180003fea  call    memcmp_0
0x180003fef  test    eax, eax
0x180003ff1  jz      loc_180004444
0x180003ff7  mov     edx, r13d
0x180003ffa  lea     r8, [rbp+80h+var_D0]
0x180003ffe  mov     rcx, [r14+18h]
0x180004002  call    cs:__imp_SwDevicePropertySet
0x180004008  mov     rcx, [rbp+88h]; this
0x18000400f  test    eax, eax
0x180004011  js      loc_180004605
0x180004017  cmp     dword ptr [rdi+10h], 2
0x18000401b  jnz     loc_180003F35
0x180004021  mov     r8d, 10h; Size
0x180004027  lea     rdx, PKEY_Device_DeviceDesc; Buf2
0x18000402e  mov     rcx, rdi; Buf1
0x180004031  call    memcmp_0
0x180004036  test    eax, eax
0x180004038  jnz     loc_180003F35
0x18000403e  movups  xmm0, xmmword ptr cs:PKEY_DeviceInterface_FriendlyName.fmtid.Data1
0x180004045  movaps  xmmword ptr [rbp+80h+var_D0.CompKey.Key.fmtid.Data1], xmm0
0x180004049  mov     eax, cs:PKEY_DeviceInterface_FriendlyName.pid
0x18000404f  mov     [rbp+80h+var_D0.CompKey.Key.pid], eax
0x180004052  lea     r9, [rbp+80h+var_D0]
0x180004056  mov     r8d, 1
0x18000405c  mov     rdx, [r14+10h]
0x180004060  mov     rcx, [r14+18h]
0x180004064  call    cs:__imp_SwDeviceInterfacePropertySet
0x18000406a  mov     r15d, eax
0x18000406d  test    eax, eax
0x18000406f  jns     loc_180003F35
0x180004075  mov     rcx, [rbp+88h]; this
0x18000407c  mov     r9d, eax; char *
0x18000407f  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004086  mov     edx, 0A43h; void *
0x18000408b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004090  nop
0x180004091  test    rbx, rbx
0x180004094  jz      short loc_1800040A0
0x180004096  mov     rcx, rbx; pv
0x180004099  call    cs:__imp_CoTaskMemFree
0x18000409f  nop
0x1800040a0  lea     rcx, [rsp+180h+var_140]
0x1800040a5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800040aa  jmp     loc_180004184
0x1800040af  mov     r8d, 10h; Size
0x1800040b5  lea     rdx, PKEY_Device_DeviceDesc; Buf2
0x1800040bc  mov     rcx, rdi; Buf1
0x1800040bf  call    memcmp_0
0x1800040c4  test    eax, eax
0x1800040c6  jnz     loc_180003EBE
0x1800040cc  mov     r8d, 10h; Size
0x1800040d2  lea     rdx, PKEY_Device_DeviceDesc; Buf2
0x1800040d9  mov     rcx, rdi; Buf1
0x1800040dc  call    memcmp_0
0x1800040e1  mov     edx, r13d
0x1800040e4  test    eax, eax
0x1800040e6  jnz     loc_180003FFA
0x1800040ec  lea     rcx, [rsp+180h+pvar]
0x1800040f1  call    ?reset@?$unique_struct@UtagPROPVARIANT@@P6AJPEAU1@@Z$1?PropVariantClear@@YAJ0@ZP6AX0@Z$1?PropVariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagPROPVARIANT,long (*)(tagPROPVARIANT *),&PropVariantClear(tagPROPVARIANT *),void (*)(tagPROPVARIANT *),&PropVariantInit(tagPROPVARIANT *)>::reset(void)
0x1800040f6  mov     rcx, [rsp+180h+var_140]
0x1800040fb  mov     rax, [rcx]
0x1800040fe  lea     r8, [rsp+180h+pvar]
0x180004103  lea     rdx, PKEY_Device_FriendlyName
0x18000410a  mov     rax, [rax+28h]
0x18000410e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004113  cmp     word ptr [rsp+180h+pvar], 1Fh
0x180004119  jz      loc_1800044BD
0x18000411f  lea     rcx, [rsp+180h+var_140]
0x180004124  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180004129  jmp     loc_1800042CE
0x18000412e  mov     rcx, [rbp+88h]; this
0x180004135  mov     rdx, [r14+10h]
0x180004139  mov     [rsp+180h+var_158], rdx; char *
0x18000413e  lea     rax, aFailedToSetPro; "Failed to set property for device inter"...
0x180004145  mov     [rsp+180h+var_160], rax; int
0x18000414a  mov     r9d, r15d; char *
0x18000414d  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004154  mov     edx, 0A55h; void *
0x180004159  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000415e  nop
0x18000415f  mov     rcx, [rsp+180h+lpsz]; pv
0x180004164  test    rcx, rcx
0x180004167  jnz     loc_180004291
0x18000416d  mov     rcx, [rsp+180h+var_140]
0x180004172  test    rcx, rcx
0x180004175  jz      short loc_180004184
0x180004177  mov     rax, [rcx]
0x18000417a  mov     rax, [rax+10h]
0x18000417e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004183  nop
0x180004184  lea     rcx, [rsp+180h+pvar]; pvar
0x180004189  call    cs:__imp_PropVariantClear
0x18000418f  nop
0x180004190  test    rsi, rsi
0x180004193  jz      short loc_18000419E
0x180004195  mov     rcx, rsi; lpCriticalSection
0x180004198  call    cs:__imp_LeaveCriticalSection
0x18000419e  mov     eax, r15d
0x1800041a1  jmp     loc_180003F8B
0x1800041a6  lea     rdx, PKEY_Endpoint_Device_NAME; Buf2
0x1800041ad  mov     r8d, 10h; Size
0x1800041b3  mov     rcx, rdi; Buf1
0x1800041b6  call    memcmp_0
0x1800041bb  test    eax, eax
0x1800041bd  jnz     loc_180003F53
0x1800041c3  movups  xmm0, xmmword ptr cs:PKEY_Device_DeviceDesc.fmtid.Data1
0x1800041ca  movaps  xmmword ptr [rbp+80h+rclsid.Data1], xmm0
0x1800041ce  mov     eax, cs:PKEY_Device_DeviceDesc.pid
0x1800041d4  mov     [rbp+80h+var_F0], eax
0x1800041d7  lea     rdx, [rbp+80h+rclsid]; struct _tagpropertykey
0x1800041db  mov     rcx, r14; this
0x1800041de  call    ?UpdateDeviceProperty@CAudioDevice@@QEAAJU_tagpropertykey@@@Z; CAudioDevice::UpdateDeviceProperty(_tagpropertykey)
0x1800041e3  jmp     loc_180003F53
0x1800041e8  movzx   r8d, word ptr [rsp+180h+pvar]
0x1800041ee  mov     rcx, [rbp+88h]; this
0x1800041f5  mov     edx, [rdi+10h]
0x1800041f8  mov     [rsp+180h+var_148], edx
0x1800041fc  mov     rdx, [rsp+180h+lpsz]
0x180004201  mov     [rsp+180h+var_150], rdx
0x180004206  mov     dword ptr [rsp+180h+var_158], r8d; char *
0x18000420b  lea     rax, aUnsupportedTyp; "Unsupported type 0x%04x for property %l"...
0x180004212  mov     [rsp+180h+var_160], rax; int
0x180004217  mov     r9d, r15d; char *
0x18000421a  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x180004221  mov     edx, 0A50h; void *
0x180004226  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000422b  nop
0x18000422c  mov     rcx, [rsp+180h+lpsz]; pv
0x180004231  test    rcx, rcx
0x180004234  jz      short loc_18000423D
0x180004236  call    cs:__imp_CoTaskMemFree
0x18000423c  nop
0x18000423d  mov     rcx, [rsp+180h+var_140]
0x180004242  test    rcx, rcx
0x180004245  jz      short loc_180004254
0x180004247  mov     rax, [rcx]
0x18000424a  mov     rax, [rax+10h]
0x18000424e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004253  nop
0x180004254  jmp     loc_180004184
0x180004259  mov     rcx, [rbp+88h]; this
0x180004260  mov     r9d, r15d; char *
0x180004263  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audioendpoin"...
0x18000426a  mov     edx, 9F9h; void *
0x18000426f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004274  nop
0x180004275  mov     rcx, [rsp+180h+var_140]
0x18000427a  test    rcx, rcx
0x18000427d  jz      short loc_18000428C
0x18000427f  mov     rax, [rcx]
0x180004282  mov     rax, [rax+10h]
0x180004286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000428b  nop
0x18000428c  jmp     loc_180004184
0x180004291  call    cs:__imp_CoTaskMemFree
0x180004297  jmp     loc_18000416D
0x18000429c  lea     rdx, WPP_GLOBAL_Control
0x1800042a3  mov     rax, cs:WPP_GLOBAL_Control
0x1800042aa  cmp     rax, rdx
0x1800042ad  jz      short loc_1800042BC
0x1800042af  test    dword ptr [rax+1Ch], 80000h
0x1800042b6  jnz     loc_18000441B
0x1800042bc  test    rcx, rcx
0x1800042bf  jz      short loc_1800042CE
0x1800042c1  mov     rax, [rcx]
  ... truncated ...
```
