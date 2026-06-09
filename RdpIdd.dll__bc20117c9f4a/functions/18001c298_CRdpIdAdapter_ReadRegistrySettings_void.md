# CRdpIdAdapter::ReadRegistrySettings(void)

- ea: `0x18001c298`
- end: `0x18001cbb6`
- name: `?ReadRegistrySettings@CRdpIdAdapter@@QEAAXXZ`
- size: `2334`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180013fdc`

## callees

- `0x180001cec`
- `0x180001f14`
- `0x18000203c`
- `0x1800022f4`
- `0x180002458`
- `0x180007b2c`
- `0x180008de0`
- `0x180009258`
- `0x18000ca18`
- `0x18000d614`
- `0x1800106b8`
- `0x180013294`
- `0x180013340`
- `0x18001c298`
- `0x180020d00`
- `0x18003f010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001c2cd`
- `ntdll!RtlInitUnicodeString` at `0x18001c38e`
- `ntdll!RtlInitUnicodeString` at `0x18001c3e7`
- `ntdll!RtlInitUnicodeString` at `0x18001c58a`
- `ntdll!RtlInitUnicodeString` at `0x18001c68c`
- `ntdll!RtlInitUnicodeString` at `0x18001c725`
- `ntdll!RtlInitUnicodeString` at `0x18001c8b9`
- `ntdll!RtlInitUnicodeString` at `0x18001caa1`
- `ntdll!RtlInitUnicodeString` at `0x18001c2cd`
- `ntdll!RtlInitUnicodeString` at `0x18001c38e`
- `ntdll!RtlInitUnicodeString` at `0x18001c3e7`
- `ntdll!RtlInitUnicodeString` at `0x18001c58a`
- `ntdll!RtlInitUnicodeString` at `0x18001c68c`
- `ntdll!RtlInitUnicodeString` at `0x18001c725`
- `ntdll!RtlInitUnicodeString` at `0x18001c8b9`
- `ntdll!RtlInitUnicodeString` at `0x18001caa1`

## string_xrefs

- `0x18001c359`: `Failed to open WinStations registry key`
- `0x18001c3c6`: `CRdpIdAdapter::ReadRegistrySettings`
- `0x18001c9bf`: `CRdpIdAdapter::ReadRegistrySettings`
- `0x18001ca30`: `CRdpIdAdapter::ReadRegistrySettings`
- `0x18001c88b`: `Failed to create DWM dump registry key path`
- `0x18001c8ae`: `DwmDumpFramesPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRdpIdAdapter::ReadRegistrySettings(CRdpIdAdapter *this)
{
  unsigned int v2; // eax
  unsigned int *v3; // rbx
  _DWORD *v4; // rcx
  int v5; // r8d
  int v6; // r9d
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  _DWORD *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rbx
  _DWORD *v14; // rcx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // eax
  __int64 v18; // r8
  unsigned __int64 v19; // rdx
  __int64 *v20; // r12
  char *v21; // rcx
  char *v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rbx
  const void *v25; // r9
  _DWORD *v26; // rcx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // r8
  char *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r8
  __int16 v33; // r9
  __int64 v34; // rdx
  _DWORD *v35; // rcx
  int v36; // r8d
  int v37; // r9d
  char *v38; // [rsp+28h] [rbp-D8h]
  char *v39; // [rsp+28h] [rbp-D8h]
  PWSTR Buffer; // [rsp+60h] [rbp-A0h] BYREF
  const char *v41; // [rsp+68h] [rbp-98h] BYREF
  const char *v42; // [rsp+70h] [rbp-90h] BYREF
  const char *v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  char v45[8]; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v46; // [rsp+90h] [rbp-70h] BYREF
  const char *v47; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v50; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v51; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING v52; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING v53; // [rsp+F0h] [rbp-10h] BYREF
  struct _UNICODE_STRING v54; // [rsp+100h] [rbp+0h] BYREF
  struct _UNICODE_STRING v55; // [rsp+110h] [rbp+10h] BYREF
  __int128 v56; // [rsp+120h] [rbp+20h] BYREF
  __int64 v57; // [rsp+130h] [rbp+30h]
  __int64 v58; // [rsp+138h] [rbp+38h]
  __int128 v59; // [rsp+140h] [rbp+40h]
  __int64 v60; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  unsigned int v62; // [rsp+1B0h] [rbp+B0h] BYREF
  int v63; // [rsp+1B8h] [rbp+B8h] BYREF
  const char *v64; // [rsp+1C0h] [rbp+C0h] BYREF
  const char *v65; // [rsp+1C8h] [rbp+C8h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations");
  *(_QWORD *)v45 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _UNICODE_STRING *, __int64, _QWORD, char *))(WdfFunctions_02025 + 1048))(
         WdfDriverGlobals,
         0,
         &DestinationString,
         0x80000000LL,
         0,
         v45);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0xD9,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)v2,
    (int)"Failed to open WinStations registry key",
    v38);
  v50 = 0;
  RtlInitUnicodeString(&v50, L"DisplayRefreshRate");
  v3 = (unsigned int *)((char *)this + 432);
  if ( (*(int (__fastcall **)(__int64, _QWORD, struct _UNICODE_STRING *, char *))(WdfFunctions_02025 + 1128))(
         WdfDriverGlobals,
         *(_QWORD *)v45,
         &v50,
         (char *)this + 432) >= 0 )
  {
    if ( *v3 - 5 > 0x1EF )
    {
      v7 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v7 > 3u )
      {
        v64 = "RefreshRateOverrideInHz is out of range (5Hz-500Hz). Resetting to 32Hz";
        v65 = "CRdpIdAdapter::ReadRegistrySettings";
        v62 = 266;
        Buffer = (PWSTR)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v7,
          (unsigned int)&dword_18004E204,
          v8,
          v9,
          (__int64)&Buffer,
          (__int64)&v62,
          (__int64)&v65,
          (__int64)&v64);
      }
      *v3 = 32;
    }
  }
  else
  {
    v46 = 0;
    RtlInitUnicodeString(&v46, L"DWMFRAMEINTERVAL");
    v62 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_02025 + 1128))(
           WdfDriverGlobals,
           *(_QWORD *)v45,
           &v46,
           &v62) < 0
      || !v62 )
    {
      v62 = 31;
    }
    v4 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v4 > 4u )
    {
      LODWORD(v64) = v62;
      v41 = (const char *)*((_QWORD *)this + 65);
      LODWORD(v65) = *((_DWORD *)this + 129);
      v42 = "DWM frame interval in Ms";
      v43 = "CRdpIdAdapter::ReadRegistrySettings";
      LODWORD(v47) = 254;
      Buffer = (PWSTR)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v4,
        (unsigned int)&dword_18004E23C,
        v5,
        v6,
        (__int64)&Buffer,
        (__int64)&v47,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v65,
        (__int64)&v41,
        (__int64)&v64);
    }
    *v3 = 0x3E8 / v62;
  }
  v51 = 0;
  RtlInitUnicodeString(&v51, L"SetGpuRealtimePriority");
  if ( (*(int (__fastcall **)(__int64, _QWORD, struct _UNICODE_STRING *, char *))(WdfFunctions_02025 + 1128))(
         WdfDriverGlobals,
         *(_QWORD *)v45,
         &v51,
         (char *)this + 536) >= 0 )
  {
    v10 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v10 > 4u )
    {
      v62 = *((_DWORD *)this + 134);
      Buffer = (PWSTR)*((_QWORD *)this + 65);
      LODWORD(v64) = *((_DWORD *)this + 129);
      v43 = "Realtime GPU priority is explicitly specified";
      v42 = "CRdpIdAdapter::ReadRegistrySettings";
      LODWORD(v65) = 288;
      v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)&word_18004E19E,
        v11,
        v12,
        (__int64)&v41,
        (__int64)&v65,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&v64,
        (__int64)&Buffer,
        (__int64)&v62);
    }
  }
  v44 = 0;
  v52 = 0;
  RtlInitUnicodeString(&v52, L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\RdpIdd");
  v13 = v44;
  if ( v44 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v62);
    (*(void (__fastcall **)(__int64, __int64))(WdfFunctions_02025 + 1064))(WdfDriverGlobals, v13);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v62);
  }
  v44 = 0;
  if ( (*(int (__fastcall **)(__int64, _QWORD, struct _UNICODE_STRING *, __int64, _QWORD, __int64 *))(WdfFunctions_02025 + 1048))(
         WdfDriverGlobals,
         0,
         &v52,
         0x80000000LL,
         0,
         &v44) >= 0 )
  {
    v53 = 0;
    RtlInitUnicodeString(&v53, L"HandleLostGpu");
    v63 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64, struct _UNICODE_STRING *, int *))(WdfFunctions_02025 + 1128))(
           WdfDriverGlobals,
           v44,
           &v53,
           &v63) >= 0 )
    {
      *((_BYTE *)this + 512) = v63 != 0;
      v14 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v14 > 4u )
      {
        LOBYTE(v62) = *((_BYTE *)this + 512);
        Buffer = (PWSTR)*((_QWORD *)this + 65);
        LODWORD(v64) = *((_DWORD *)this + 129);
        v43 = "HandleLostGpu is explicitly specified";
        v42 = "CRdpIdAdapter::ReadRegistrySettings";
        LODWORD(v65) = 330;
        v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
          (_DWORD)v14,
          (unsigned int)&dword_18004E13C,
          v15,
          v16,
          (__int64)&v41,
          (__int64)&v65,
          (__int64)&v42,
          (__int64)&v43,
          (__int64)&v64,
          (__int64)&Buffer,
          (__int64)&v62);
      }
    }
    v56 = 0;
    v57 = 0;
    v59 = 0;
    v60 = 0;
    LODWORD(v56) = 56;
    v58 = 0x100000001LL;
    *(_QWORD *)&v59 = *((_QWORD *)this + 57);
    v48 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *, __int64 *))(WdfFunctions_02025 + 1504))(
            WdfDriverGlobals,
            0,
            &v56,
            &v48);
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
      (const char *)v17,
      (int)"Failed to create DWM dump registry key path",
      v39);
    v54 = 0;
    RtlInitUnicodeString(&v54, L"DwmDumpFramesPath");
    if ( (*(int (__fastcall **)(__int64, __int64, struct _UNICODE_STRING *, __int64))(WdfFunctions_02025 + 1120))(
           WdfDriverGlobals,
           v44,
           &v54,
           v48) >= 0 )
    {
      v46 = 0;
      (*(void (__fastcall **)(__int64, __int64, struct _UNICODE_STRING *))(WdfFunctions_02025 + 1512))(
        WdfDriverGlobals,
        v48,
        &v46);
      v19 = -1;
      do
        ++v19;
      while ( v46.Buffer[v19] );
      v20 = (__int64 *)((char *)this + 488);
      v21 = (char *)this + 472;
      if ( v19 > *((_QWORD *)this + 62) )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v21,
          v19,
          v18,
          v46.Buffer);
      }
      else
      {
        v22 = (char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21, v19, v18);
        *v20 = v23;
        v24 = 2 * v23;
        memmove_0(v22, v25, 2 * v23);
        *(_WORD *)&v22[v24] = 0;
      }
      if ( v46.Length )
      {
        v26 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v26 > 4u )
        {
          Buffer = v46.Buffer;
          v43 = (const char *)*((_QWORD *)this + 65);
          LODWORD(v64) = *((_DWORD *)this + 129);
          v42 = "DWM dump frames mode enabled";
          v41 = "CRdpIdAdapter::ReadRegistrySettings";
          LODWORD(v65) = 368;
          v47 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v26,
            (unsigned int)byte_18004E0E5,
            v27,
            v28,
            (__int64)&v47,
            (__int64)&v65,
            (__int64)&v41,
            (__int64)&v42,
            (__int64)&v64,
            (__int64)&v43,
            (__int64)&Buffer);
        }
        *((_BYTE *)this + 504) = 1;
        if ( v46.Buffer[(unsigned __int64)v46.Length >> 1] != 92 )
        {
          v29 = *v20;
          v30 = (char *)this + 472;
          if ( *((_QWORD *)this + 62) == *v20 )
          {
            ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
              v30,
              1);
          }
          else
          {
            *v20 = v29 + 1;
            v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30, v29 + 1, v29);
            *(_WORD *)(v31 + 2 * v32) = v33;
            *(_WORD *)(v31 + 2 * v34) = 0;
          }
        }
        v55 = 0;
        RtlInitUnicodeString(&v55, L"DwmDumpFramesAutoStart");
        v62 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64, struct _UNICODE_STRING *, unsigned int *))(WdfFunctions_02025
                                                                                               + 1128))(
               WdfDriverGlobals,
               v44,
               &v55,
               &v62) >= 0
          && v62 == 1 )
        {
          v35 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
          if ( *v35 > 4u )
          {
            Buffer = (PWSTR)*((_QWORD *)this + 65);
            LODWORD(v64) = *((_DWORD *)this + 129);
            v43 = "DWM dump frames auto started";
            v42 = "CRdpIdAdapter::ReadRegistrySettings";
            LODWORD(v65) = 398;
            v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              (_DWORD)v35,
              (unsigned int)&dword_18004E094,
              v36,
              v37,
              (__int64)&v41,
              (__int64)&v65,
              (__int64)&v42,
              (__int64)&v43,
              (__int64)&v64,
              (__int64)&Buffer);
          }
          *((_BYTE *)this + 505) = 1;
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&void WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&void WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>(&v44);
  wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&void WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(WDFKEY__ *),&void WdfRegistryClose(WDFKEY__ *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>(v45);
}

```

## disassembly

```asm
0x18001c298  push    rbp
0x18001c29a  push    rbx
0x18001c29b  push    rsi
0x18001c29c  push    rdi
0x18001c29d  push    r12
0x18001c29f  push    r13
0x18001c2a1  push    r14
0x18001c2a3  push    r15
0x18001c2a5  lea     rbp, [rsp-68h]
0x18001c2aa  sub     rsp, 168h
0x18001c2b1  mov     rsi, rcx
0x18001c2b4  xor     r13d, r13d
0x18001c2b7  mov     qword ptr [rbp+0A0h+var_118], r13
0x18001c2bb  xorps   xmm0, xmm0
0x18001c2be  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x18001c2c2  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18001c2c9  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x18001c2cd  call    cs:__imp_RtlInitUnicodeString
0x18001c2d4  nop     dword ptr [rax+rax+00h]
0x18001c2d9  mov     rbx, qword ptr [rbp+0A0h+var_118]
0x18001c2dd  test    rbx, rbx
0x18001c2e0  jz      short loc_18001C317
0x18001c2e2  lea     rcx, [rbp+0A0h+arg_0]; this
0x18001c2e9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c2ee  mov     rax, cs:WdfFunctions_02025
0x18001c2f5  mov     rdx, rbx
0x18001c2f8  mov     rcx, cs:WdfDriverGlobals
0x18001c2ff  mov     rax, [rax+428h]
0x18001c306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c30b  lea     rcx, [rbp+0A0h+arg_0]; this
0x18001c312  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c317  mov     qword ptr [rbp+0A0h+var_118], r13
0x18001c31b  mov     rax, cs:WdfFunctions_02025
0x18001c322  lea     rcx, [rbp+0A0h+var_118]
0x18001c326  mov     [rsp+1A0h+var_178], rcx; char *
0x18001c32b  mov     [rsp+1A0h+var_180], r13
0x18001c330  mov     r15d, 80000000h
0x18001c336  mov     r9d, r15d
0x18001c339  lea     r8, [rbp+0A0h+DestinationString]
0x18001c33d  xor     edx, edx
0x18001c33f  mov     rcx, cs:WdfDriverGlobals
0x18001c346  mov     rax, [rax+418h]
0x18001c34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c352  mov     rcx, [rbp+0A8h]; this
0x18001c359  lea     rdx, aFailedToOpenWi; "Failed to open WinStations registry key"
0x18001c360  mov     [rsp+1A0h+var_180], rdx; int
0x18001c365  mov     r9d, eax; char *
0x18001c368  lea     rdi, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001c36f  mov     r8, rdi; unsigned int
0x18001c372  mov     edx, 0D9h; void *
0x18001c377  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001c37c  xorps   xmm0, xmm0
0x18001c37f  movups  xmmword ptr [rbp+0A0h+var_E0.Length], xmm0
0x18001c383  lea     rdx, aDisplayrefresh; "DisplayRefreshRate"
0x18001c38a  lea     rcx, [rbp+0A0h+var_E0]; DestinationString
0x18001c38e  call    cs:__imp_RtlInitUnicodeString
0x18001c395  nop     dword ptr [rax+rax+00h]
0x18001c39a  lea     rbx, [rsi+1B0h]
0x18001c3a1  mov     rax, cs:WdfFunctions_02025
0x18001c3a8  mov     r9, rbx
0x18001c3ab  lea     r8, [rbp+0A0h+var_E0]
0x18001c3af  mov     rdx, qword ptr [rbp+0A0h+var_118]
0x18001c3b3  mov     rcx, cs:WdfDriverGlobals
0x18001c3ba  mov     rax, [rax+468h]
0x18001c3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3c6  lea     r14, aCrdpidadapterR_1; "CRdpIdAdapter::ReadRegistrySettings"
0x18001c3cd  test    eax, eax
0x18001c3cf  jns     loc_18001C4F8
0x18001c3d5  xorps   xmm0, xmm0
0x18001c3d8  movups  xmmword ptr [rbp+0A0h+var_110.Length], xmm0
0x18001c3dc  lea     rdx, aDwmframeinterv; "DWMFRAMEINTERVAL"
0x18001c3e3  lea     rcx, [rbp+0A0h+var_110]; DestinationString
0x18001c3e7  call    cs:__imp_RtlInitUnicodeString
0x18001c3ee  nop     dword ptr [rax+rax+00h]
0x18001c3f3  mov     [rbp+0A0h+arg_0], r13d
0x18001c3fa  mov     rax, cs:WdfFunctions_02025
0x18001c401  lea     r9, [rbp+0A0h+arg_0]
0x18001c408  lea     r8, [rbp+0A0h+var_110]
0x18001c40c  mov     rdx, qword ptr [rbp+0A0h+var_118]
0x18001c410  mov     rcx, cs:WdfDriverGlobals
0x18001c417  mov     rax, [rax+468h]
0x18001c41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c423  test    eax, eax
0x18001c425  js      short loc_18001C430
0x18001c427  cmp     [rbp+0A0h+arg_0], r13d
0x18001c42e  jnz     short loc_18001C43A
0x18001c430  mov     [rbp+0A0h+arg_0], 1Fh
0x18001c43a  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001c43f  mov     rcx, [rax+8]
0x18001c443  mov     eax, [rcx]
0x18001c445  cmp     eax, 4
0x18001c448  jbe     loc_18001C4E4
0x18001c44e  mov     eax, [rbp+0A0h+arg_0]
0x18001c454  mov     dword ptr [rbp+0A0h+arg_10], eax
0x18001c45a  mov     rax, [rsi+208h]
0x18001c461  mov     [rsp+1A0h+var_138], rax
0x18001c466  mov     eax, [rsi+204h]
0x18001c46c  mov     dword ptr [rbp+0A0h+arg_18], eax
0x18001c472  lea     rax, aDwmFrameInterv; "DWM frame interval in Ms"
0x18001c479  mov     [rsp+1A0h+var_130], rax
0x18001c47e  mov     [rsp+1A0h+var_128], r14
0x18001c483  mov     dword ptr [rbp+0A0h+var_100], 0FEh
0x18001c48a  mov     [rsp+1A0h+var_140], rdi
0x18001c48f  lea     rax, [rbp+0A0h+arg_10]
0x18001c496  mov     [rsp+1A0h+var_150], rax
0x18001c49b  lea     rax, [rsp+1A0h+var_138]
0x18001c4a0  mov     [rsp+1A0h+var_158], rax
0x18001c4a5  lea     rax, [rbp+0A0h+arg_18]
0x18001c4ac  mov     [rsp+1A0h+var_160], rax
0x18001c4b1  lea     rax, [rsp+1A0h+var_130]
0x18001c4b6  mov     [rsp+1A0h+var_168], rax
0x18001c4bb  lea     rax, [rsp+1A0h+var_128]
0x18001c4c0  mov     [rsp+1A0h+var_170], rax
0x18001c4c5  lea     rax, [rbp+0A0h+var_100]
0x18001c4c9  mov     [rsp+1A0h+var_178], rax
0x18001c4ce  lea     rax, [rsp+1A0h+var_140]
0x18001c4d3  mov     [rsp+1A0h+var_180], rax
0x18001c4d8  lea     rdx, dword_18004E23C
0x18001c4df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001c4e4  xor     edx, edx
0x18001c4e6  mov     eax, 3E8h
0x18001c4eb  div     [rbp+0A0h+arg_0]
0x18001c4f1  mov     [rbx], eax
0x18001c4f3  jmp     loc_18001C578
0x18001c4f8  mov     eax, [rbx]
0x18001c4fa  sub     eax, 5
0x18001c4fd  cmp     eax, 1EFh
0x18001c502  jbe     short loc_18001C578
0x18001c504  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001c509  mov     rcx, [rax+8]
0x18001c50d  mov     eax, [rcx]
0x18001c50f  cmp     eax, 3
0x18001c512  jbe     short loc_18001C572
0x18001c514  lea     rax, aRefreshrateove; "RefreshRateOverrideInHz is out of range"...
0x18001c51b  mov     [rbp+0A0h+arg_10], rax
0x18001c522  mov     [rbp+0A0h+arg_18], r14
0x18001c529  mov     [rbp+0A0h+arg_0], 10Ah
0x18001c533  mov     [rsp+1A0h+var_140], rdi
0x18001c538  lea     rax, [rbp+0A0h+arg_10]
0x18001c53f  mov     [rsp+1A0h+var_168], rax
0x18001c544  lea     rax, [rbp+0A0h+arg_18]
0x18001c54b  mov     [rsp+1A0h+var_170], rax
0x18001c550  lea     rax, [rbp+0A0h+arg_0]
0x18001c557  mov     [rsp+1A0h+var_178], rax
0x18001c55c  lea     rax, [rsp+1A0h+var_140]
0x18001c561  mov     [rsp+1A0h+var_180], rax
0x18001c566  lea     rdx, dword_18004E204
0x18001c56d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001c572  mov     dword ptr [rbx], 20h ; ' '
0x18001c578  xorps   xmm0, xmm0
0x18001c57b  movups  xmmword ptr [rbp+0A0h+var_D0.Length], xmm0
0x18001c57f  lea     rdx, aSetgpurealtime; "SetGpuRealtimePriority"
0x18001c586  lea     rcx, [rbp+0A0h+var_D0]; DestinationString
0x18001c58a  call    cs:__imp_RtlInitUnicodeString
0x18001c591  nop     dword ptr [rax+rax+00h]
0x18001c596  lea     rbx, [rsi+218h]
0x18001c59d  mov     rax, cs:WdfFunctions_02025
0x18001c5a4  mov     r9, rbx
0x18001c5a7  lea     r8, [rbp+0A0h+var_D0]
0x18001c5ab  mov     rdx, qword ptr [rbp+0A0h+var_118]
0x18001c5af  mov     rcx, cs:WdfDriverGlobals
0x18001c5b6  mov     rax, [rax+468h]
0x18001c5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5c2  test    eax, eax
0x18001c5c4  js      loc_18001C676
0x18001c5ca  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001c5cf  mov     rcx, [rax+8]
0x18001c5d3  mov     eax, [rcx]
0x18001c5d5  cmp     eax, 4
0x18001c5d8  jbe     loc_18001C676
0x18001c5de  mov     eax, [rbx]
0x18001c5e0  mov     [rbp+0A0h+arg_0], eax
0x18001c5e6  mov     rax, [rsi+208h]
0x18001c5ed  mov     [rsp+1A0h+var_140], rax
0x18001c5f2  mov     eax, [rsi+204h]
0x18001c5f8  mov     dword ptr [rbp+0A0h+arg_10], eax
0x18001c5fe  lea     rax, aRealtimeGpuPri; "Realtime GPU priority is explicitly spe"...
0x18001c605  mov     [rsp+1A0h+var_128], rax
0x18001c60a  mov     [rsp+1A0h+var_130], r14
0x18001c60f  mov     dword ptr [rbp+0A0h+arg_18], 120h
0x18001c619  mov     [rsp+1A0h+var_138], rdi
0x18001c61e  lea     rax, [rbp+0A0h+arg_0]
0x18001c625  mov     [rsp+1A0h+var_150], rax
0x18001c62a  lea     rax, [rsp+1A0h+var_140]
0x18001c62f  mov     [rsp+1A0h+var_158], rax
0x18001c634  lea     rax, [rbp+0A0h+arg_10]
0x18001c63b  mov     [rsp+1A0h+var_160], rax
0x18001c640  lea     rax, [rsp+1A0h+var_128]
0x18001c645  mov     [rsp+1A0h+var_168], rax
0x18001c64a  lea     rax, [rsp+1A0h+var_130]
0x18001c64f  mov     [rsp+1A0h+var_170], rax
0x18001c654  lea     rax, [rbp+0A0h+arg_18]
0x18001c65b  mov     [rsp+1A0h+var_178], rax
0x18001c660  lea     rax, [rsp+1A0h+var_138]
0x18001c665  mov     [rsp+1A0h+var_180], rax
0x18001c66a  lea     rdx, word_18004E19E
0x18001c671  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001c676  mov     [rbp+0A0h+var_120], r13
0x18001c67a  xorps   xmm0, xmm0
0x18001c67d  movups  xmmword ptr [rbp+0A0h+var_C0.Length], xmm0
0x18001c681  lea     rdx, SourceString; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x18001c688  lea     rcx, [rbp+0A0h+var_C0]; DestinationString
0x18001c68c  call    cs:__imp_RtlInitUnicodeString
0x18001c693  nop     dword ptr [rax+rax+00h]
0x18001c698  mov     rbx, [rbp+0A0h+var_120]
0x18001c69c  test    rbx, rbx
0x18001c69f  jz      short loc_18001C6D6
0x18001c6a1  lea     rcx, [rbp+0A0h+arg_0]; this
0x18001c6a8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001c6ad  mov     rax, cs:WdfFunctions_02025
0x18001c6b4  mov     rdx, rbx
0x18001c6b7  mov     rcx, cs:WdfDriverGlobals
0x18001c6be  mov     rax, [rax+428h]
0x18001c6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6ca  lea     rcx, [rbp+0A0h+arg_0]; this
0x18001c6d1  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001c6d6  mov     [rbp+0A0h+var_120], r13
0x18001c6da  mov     rax, cs:WdfFunctions_02025
0x18001c6e1  lea     rcx, [rbp+0A0h+var_120]
0x18001c6e5  mov     [rsp+1A0h+var_178], rcx
0x18001c6ea  mov     [rsp+1A0h+var_180], r13
0x18001c6ef  mov     r9d, r15d
0x18001c6f2  lea     r8, [rbp+0A0h+var_C0]
0x18001c6f6  xor     edx, edx
0x18001c6f8  mov     rcx, cs:WdfDriverGlobals
0x18001c6ff  mov     rax, [rax+418h]
0x18001c706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c70b  test    eax, eax
0x18001c70d  js      loc_18001CB8E
0x18001c713  xorps   xmm0, xmm0
0x18001c716  movups  xmmword ptr [rbp+0A0h+var_B0.Length], xmm0
0x18001c71a  lea     rdx, aHandlelostgpu; "HandleLostGpu"
0x18001c721  lea     rcx, [rbp+0A0h+var_B0]; DestinationString
0x18001c725  call    cs:__imp_RtlInitUnicodeString
0x18001c72c  nop     dword ptr [rax+rax+00h]
0x18001c731  mov     [rbp+0A0h+arg_8], r13d
0x18001c738  mov     rax, cs:WdfFunctions_02025
0x18001c73f  lea     r9, [rbp+0A0h+arg_8]
0x18001c746  lea     r8, [rbp+0A0h+var_B0]
0x18001c74a  mov     rdx, [rbp+0A0h+var_120]
0x18001c74e  mov     rcx, cs:WdfDriverGlobals
0x18001c755  mov     rax, [rax+468h]
0x18001c75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c761  test    eax, eax
0x18001c763  js      loc_18001C829
0x18001c769  cmp     [rbp+0A0h+arg_8], r13d
0x18001c770  setnz   al
0x18001c773  mov     [rsi+200h], al
0x18001c779  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001c77e  mov     rcx, [rax+8]
0x18001c782  mov     eax, [rcx]
0x18001c784  cmp     eax, 4
0x18001c787  jbe     loc_18001C829
0x18001c78d  mov     al, [rsi+200h]
0x18001c793  mov     byte ptr [rbp+0A0h+arg_0], al
0x18001c799  mov     rax, [rsi+208h]
0x18001c7a0  mov     [rsp+1A0h+var_140], rax
0x18001c7a5  mov     eax, [rsi+204h]
0x18001c7ab  mov     dword ptr [rbp+0A0h+arg_10], eax
0x18001c7b1  lea     rax, aHandlelostgpuI; "HandleLostGpu is explicitly specified"
0x18001c7b8  mov     [rsp+1A0h+var_128], rax
0x18001c7bd  mov     [rsp+1A0h+var_130], r14
0x18001c7c2  mov     dword ptr [rbp+0A0h+arg_18], 14Ah
0x18001c7cc  mov     [rsp+1A0h+var_138], rdi
0x18001c7d1  lea     rax, [rbp+0A0h+arg_0]
0x18001c7d8  mov     [rsp+1A0h+var_150], rax
0x18001c7dd  lea     rax, [rsp+1A0h+var_140]
0x18001c7e2  mov     [rsp+1A0h+var_158], rax
0x18001c7e7  lea     rax, [rbp+0A0h+arg_10]
0x18001c7ee  mov     [rsp+1A0h+var_160], rax
0x18001c7f3  lea     rax, [rsp+1A0h+var_128]
0x18001c7f8  mov     [rsp+1A0h+var_168], rax
0x18001c7fd  lea     rax, [rsp+1A0h+var_130]
0x18001c802  mov     [rsp+1A0h+var_170], rax
0x18001c807  lea     rax, [rbp+0A0h+arg_18]
0x18001c80e  mov     [rsp+1A0h+var_178], rax; char *
0x18001c813  lea     rax, [rsp+1A0h+var_138]
0x18001c818  mov     [rsp+1A0h+var_180], rax
0x18001c81d  lea     rdx, dword_18004E13C
0x18001c824  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &)
0x18001c829  xorps   xmm0, xmm0
0x18001c82c  xor     eax, eax
0x18001c82e  movups  [rbp+0A0h+var_80], xmm0
0x18001c832  movups  [rbp+0A0h+var_70], xmm0
0x18001c836  movups  [rbp+0A0h+var_60], xmm0
0x18001c83a  mov     [rbp+0A0h+var_50], rax
0x18001c83e  mov     dword ptr [rbp+0A0h+var_80], 38h ; '8'
0x18001c845  lea     r15d, [rax+1]
0x18001c849  mov     dword ptr [rbp+0A0h+var_70+8], r15d
0x18001c84d  mov     dword ptr [rbp+0A0h+var_70+0Ch], r15d
0x18001c851  mov     rax, [rsi+1C8h]
0x18001c858  mov     qword ptr [rbp+0A0h+var_60], rax
0x18001c85c  mov     [rbp+0A0h+var_F8], r13
0x18001c860  mov     rax, cs:WdfFunctions_02025
0x18001c867  lea     r9, [rbp+0A0h+var_F8]
0x18001c86b  lea     r8, [rbp+0A0h+var_80]
0x18001c86f  xor     edx, edx
0x18001c871  mov     rcx, cs:WdfDriverGlobals
0x18001c878  mov     rax, [rax+5E0h]
0x18001c87f  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
