# CMonitorConfig::ValidateAndFixMonitorConfig(void)

- ea: `0x180022990`
- end: `0x180022e15`
- name: `?ValidateAndFixMonitorConfig@CMonitorConfig@@AEAAXXZ`
- size: `1157`
- prototype: `void __fastcall(CMonitorConfig *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180021de8`
- `0x180021f78`

## callees

- `0x180001cec`
- `0x180006970`
- `0x18000d614`
- `0x180010e74`
- `0x180010f88`
- `0x1800115e4`
- `0x180022990`

## string_xrefs

- `0x1800229a9`: `onecoreuap\termsrv\rdp_bin\win\rdpidd\monitorconfig.cpp`
- `0x1800229a2`: `CMonitorConfig::ValidateAndFixMonitorConfig`

## pseudocode

```c
void __fastcall CMonitorConfig::ValidateAndFixMonitorConfig(CMonitorConfig *this, unsigned __int64 a2)
{
  _DWORD *v3; // rcx
  int v4; // r8d
  int v5; // r9d
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  int v9; // eax
  _DWORD *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  _DWORD *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  _DWORD *v16; // rdi
  _DWORD *v17; // rcx
  int v18; // r8d
  int v19; // r9d
  _DWORD *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  _DWORD *v23; // rdi
  _DWORD *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  _DWORD *v27; // rcx
  int v28; // r8d
  int v29; // r9d
  _DWORD *v30; // rdi
  _DWORD *v31; // rcx
  int v32; // r8d
  int v33; // r9d
  char *Buffer[4]; // [rsp+40h] [rbp-20h] BYREF
  int v35; // [rsp+90h] [rbp+30h] BYREF
  const char *v36; // [rsp+98h] [rbp+38h] BYREF
  const char *v37; // [rsp+A0h] [rbp+40h] BYREF
  const char *v38; // [rsp+A8h] [rbp+48h] BYREF

  if ( (*((_BYTE *)this + 28) & 2) != 0 )
  {
    if ( *((_DWORD *)this + 24) < 0xC8u )
    {
      v3 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v3 > 3u )
      {
        v36 = "Resolution.cx is less than minimum allowed(200). Resetting to 200";
        v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
        v35 = 458;
        v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v3,
          (unsigned int)byte_18004E4E5,
          v4,
          v5,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v37,
          (__int64)&v36);
      }
      *((_DWORD *)this + 24) = 200;
    }
    if ( *((_DWORD *)this + 25) < 0xC8u )
    {
      v6 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v6 > 3u )
      {
        v36 = "Resolution.cy is less than minimum allowed(200). Resetting to 200";
        v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
        v35 = 464;
        v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v6,
          (unsigned int)byte_18004E4AD,
          v7,
          v8,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v37,
          (__int64)&v36);
      }
      *((_DWORD *)this + 25) = 200;
    }
    v9 = *((_DWORD *)this + 27);
    if ( v9 && v9 != 90 && v9 != 180 && v9 != 270 )
    {
      v10 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v10 > 3u )
      {
        v36 = "Orientation does not have a valid value. Resetting to 0";
        v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
        v35 = 473;
        v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v10,
          (unsigned int)byte_18004E475,
          v11,
          v12,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v37,
          (__int64)&v36);
      }
      *((_DWORD *)this + 27) = 0;
    }
    if ( *(_DWORD *)this )
    {
      if ( RdpIddLoggingProvider::IsEnabled(3u, a2) )
      {
        std::vector<char>::vector<char>(Buffer);
        snprintf(Buffer[0], Buffer[1] - Buffer[0], "Overriding RefreshRate. Resetting to %dHz", *(_DWORD *)this);
        v13 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v13 > 3u )
        {
          v36 = Buffer[0];
          v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
          v35 = 479;
          v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)v13,
            (unsigned int)byte_18004E43D,
            v14,
            v15,
            (__int64)&v38,
            (__int64)&v35,
            (__int64)&v37,
            (__int64)&v36);
        }
        std::vector<char>::_Tidy(Buffer);
      }
      *((_DWORD *)this + 28) = *(_DWORD *)this;
      *((_DWORD *)this + 29) = 1;
    }
    else
    {
      v16 = (_DWORD *)((char *)this + 116);
      if ( !*((_DWORD *)this + 28) || !*v16 )
      {
        v17 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
        if ( *v17 > 3u )
        {
          v36 = "RefreshRate is out of range. Resetting to 32Hz";
          v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
          v35 = 486;
          v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)v17,
            (unsigned int)byte_18004E405,
            v18,
            v19,
            (__int64)&v38,
            (__int64)&v35,
            (__int64)&v37,
            (__int64)&v36);
        }
        *((_DWORD *)this + 28) = 32;
        *v16 = 1;
      }
    }
    if ( !*((_DWORD *)this + 30) )
    {
      v20 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v20 > 3u )
      {
        v36 = "VSyncFreqDivider is 0. Resetting to 1";
        v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
        v35 = 493;
        v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v20,
          (unsigned int)byte_18004E3CD,
          v21,
          v22,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v37,
          (__int64)&v36);
      }
      *((_DWORD *)this + 30) = 1;
    }
  }
  if ( (*((_BYTE *)this + 28) & 8) != 0 )
  {
    v23 = (_DWORD *)((char *)this + 156);
    if ( !*((_DWORD *)this + 38) || !*v23 )
    {
      v24 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v24 > 3u )
      {
        v36 = "PhysicalSize.cx or PhysicalSize.cy is 0. Resetting both to 0";
        v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
        v35 = 506;
        v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v24,
          (unsigned int)byte_18004E395,
          v25,
          v26,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v37,
          (__int64)&v36);
      }
      *((_DWORD *)this + 38) = 0;
      *v23 = 0;
    }
  }
  if ( (*((_BYTE *)this + 28) & 4) != 0 && (unsigned int)(*((_DWORD *)this + 34) - 100) > 0x190 )
  {
    v27 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v27 > 3u )
    {
      v36 = "DesktopScaleFactor is out of range(100-500). Resetting to 100";
      v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
      v35 = 520;
      v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v27,
        (unsigned int)byte_18004E35D,
        v28,
        v29,
        (__int64)&v38,
        (__int64)&v35,
        (__int64)&v37,
        (__int64)&v36);
    }
    *((_DWORD *)this + 34) = 100;
  }
  if ( *((char *)this + 28) < 0 )
  {
    v30 = (_DWORD *)((char *)this + 276);
    if ( !*((_DWORD *)this + 68) || !*v30 )
    {
      v31 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v31 > 3u )
      {
        v36 = "ContainerInfo.VSyncFreq is out of range. Resetting to 32Hz";
        v37 = "CMonitorConfig::ValidateAndFixMonitorConfig";
        v35 = 533;
        v38 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\monitorconfig.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v31,
          (unsigned int)byte_18004E325,
          v32,
          v33,
          (__int64)&v38,
          (__int64)&v35,
          (__int64)&v37,
          (__int64)&v36);
      }
      *((_DWORD *)this + 68) = 32;
      *v30 = 1;
    }
  }
}

```

## disassembly

```asm
0x180022990  push    rbp
0x180022992  push    rbx
0x180022993  push    rdi
0x180022994  push    r12
0x180022996  push    r15
0x180022998  mov     rbp, rsp
0x18002299b  sub     rsp, 60h
0x18002299f  mov     rbx, rcx
0x1800229a2  lea     r15, aCmonitorconfig; "CMonitorConfig::ValidateAndFixMonitorCo"...
0x1800229a9  lea     r12, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x1800229b0  test    byte ptr [rcx+1Ch], 2
0x1800229b4  jz      loc_180022C84
0x1800229ba  mov     edi, 0C8h
0x1800229bf  cmp     [rcx+60h], edi
0x1800229c2  jnb     short loc_180022A21
0x1800229c4  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x1800229c9  mov     rcx, [rax+8]
0x1800229cd  mov     eax, [rcx]
0x1800229cf  cmp     eax, 3
0x1800229d2  jbe     short loc_180022A1E
0x1800229d4  lea     rax, aResolutionCxIs; "Resolution.cx is less than minimum allo"...
0x1800229db  mov     [rbp+arg_8], rax
0x1800229df  mov     [rbp+arg_10], r15
0x1800229e3  mov     [rbp+arg_0], 1CAh
0x1800229ea  mov     [rbp+arg_18], r12
0x1800229ee  lea     rax, [rbp+arg_8]
0x1800229f2  mov     [rsp+60h+var_28], rax
0x1800229f7  lea     rax, [rbp+arg_10]
0x1800229fb  mov     [rsp+60h+var_30], rax
0x180022a00  lea     rax, [rbp+arg_0]
0x180022a04  mov     [rsp+60h+var_38], rax
0x180022a09  lea     rax, [rbp+arg_18]
0x180022a0d  mov     [rsp+60h+var_40], rax
0x180022a12  lea     rdx, byte_18004E4E5
0x180022a19  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022a1e  mov     [rbx+60h], edi
0x180022a21  cmp     [rbx+64h], edi
0x180022a24  jnb     short loc_180022A83
0x180022a26  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022a2b  mov     rcx, [rax+8]
0x180022a2f  mov     eax, [rcx]
0x180022a31  cmp     eax, 3
0x180022a34  jbe     short loc_180022A80
0x180022a36  lea     rax, aResolutionCyIs; "Resolution.cy is less than minimum allo"...
0x180022a3d  mov     [rbp+arg_8], rax
0x180022a41  mov     [rbp+arg_10], r15
0x180022a45  mov     [rbp+arg_0], 1D0h
0x180022a4c  mov     [rbp+arg_18], r12
0x180022a50  lea     rax, [rbp+arg_8]
0x180022a54  mov     [rsp+60h+var_28], rax
0x180022a59  lea     rax, [rbp+arg_10]
0x180022a5d  mov     [rsp+60h+var_30], rax
0x180022a62  lea     rax, [rbp+arg_0]
0x180022a66  mov     [rsp+60h+var_38], rax
0x180022a6b  lea     rax, [rbp+arg_18]
0x180022a6f  mov     [rsp+60h+var_40], rax
0x180022a74  lea     rdx, byte_18004E4AD
0x180022a7b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022a80  mov     [rbx+64h], edi
0x180022a83  mov     eax, [rbx+6Ch]
0x180022a86  test    eax, eax
0x180022a88  jz      short loc_180022AFE
0x180022a8a  cmp     eax, 5Ah ; 'Z'
0x180022a8d  jz      short loc_180022AFE
0x180022a8f  cmp     eax, 0B4h
0x180022a94  jz      short loc_180022AFE
0x180022a96  cmp     eax, 10Eh
0x180022a9b  jz      short loc_180022AFE
0x180022a9d  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022aa2  mov     rcx, [rax+8]
0x180022aa6  mov     eax, [rcx]
0x180022aa8  cmp     eax, 3
0x180022aab  jbe     short loc_180022AF7
0x180022aad  lea     rax, aOrientationDoe; "Orientation does not have a valid value"...
0x180022ab4  mov     [rbp+arg_8], rax
0x180022ab8  mov     [rbp+arg_10], r15
0x180022abc  mov     [rbp+arg_0], 1D9h
0x180022ac3  mov     [rbp+arg_18], r12
0x180022ac7  lea     rax, [rbp+arg_8]
0x180022acb  mov     [rsp+60h+var_28], rax
0x180022ad0  lea     rax, [rbp+arg_10]
0x180022ad4  mov     [rsp+60h+var_30], rax
0x180022ad9  lea     rax, [rbp+arg_0]
0x180022add  mov     [rsp+60h+var_38], rax
0x180022ae2  lea     rax, [rbp+arg_18]
0x180022ae6  mov     [rsp+60h+var_40], rax
0x180022aeb  lea     rdx, byte_18004E475
0x180022af2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022af7  mov     dword ptr [rbx+6Ch], 0
0x180022afe  cmp     dword ptr [rbx], 0
0x180022b01  jz      loc_180022BA7
0x180022b07  mov     cl, 3; unsigned __int8
0x180022b09  call    ?IsEnabled@RdpIddLoggingProvider@@SA_NE_K@Z; RdpIddLoggingProvider::IsEnabled(uchar,unsigned __int64)
0x180022b0e  test    al, al
0x180022b10  jz      loc_180022B99
0x180022b16  lea     rcx, [rbp+Buffer]
0x180022b1a  call    ??0?$vector@DV?$allocator@D@std@@@std@@QEAA@_KAEBV?$allocator@D@1@@Z; std::vector<char>::vector<char>(unsigned __int64,std::allocator<char> const &)
0x180022b1f  mov     rdx, [rbp+var_18]
0x180022b23  mov     rcx, [rbp+Buffer]; Buffer
0x180022b27  sub     rdx, rcx; BufferCount
0x180022b2a  mov     r9d, [rbx]
0x180022b2d  lea     r8, aOverridingRefr; "Overriding RefreshRate. Resetting to %d"...
0x180022b34  call    snprintf
0x180022b39  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022b3e  mov     rcx, [rax+8]
0x180022b42  mov     eax, [rcx]
0x180022b44  cmp     eax, 3
0x180022b47  jbe     short loc_180022B90
0x180022b49  mov     rax, [rbp+Buffer]
0x180022b4d  mov     [rbp+arg_8], rax
0x180022b51  mov     [rbp+arg_10], r15
0x180022b55  mov     [rbp+arg_0], 1DFh
0x180022b5c  mov     [rbp+arg_18], r12
0x180022b60  lea     rax, [rbp+arg_8]
0x180022b64  mov     [rsp+60h+var_28], rax
0x180022b69  lea     rax, [rbp+arg_10]
0x180022b6d  mov     [rsp+60h+var_30], rax
0x180022b72  lea     rax, [rbp+arg_0]
0x180022b76  mov     [rsp+60h+var_38], rax
0x180022b7b  lea     rax, [rbp+arg_18]
0x180022b7f  mov     [rsp+60h+var_40], rax
0x180022b84  lea     rdx, byte_18004E43D
0x180022b8b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022b90  lea     rcx, [rbp+Buffer]
0x180022b94  call    ?_Tidy@?$vector@DV?$allocator@D@std@@@std@@AEAAXXZ; std::vector<char>::_Tidy(void)
0x180022b99  mov     eax, [rbx]
0x180022b9b  mov     [rbx+70h], eax
0x180022b9e  mov     dword ptr [rbx+74h], 1
0x180022ba5  jmp     short loc_180022C1D
0x180022ba7  lea     rdi, [rbx+74h]
0x180022bab  cmp     dword ptr [rbx+70h], 0
0x180022baf  jz      short loc_180022BB6
0x180022bb1  cmp     dword ptr [rdi], 0
0x180022bb4  jnz     short loc_180022C1D
0x180022bb6  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022bbb  mov     rcx, [rax+8]
0x180022bbf  mov     eax, [rcx]
0x180022bc1  cmp     eax, 3
0x180022bc4  jbe     short loc_180022C10
0x180022bc6  lea     rax, aRefreshrateIsO; "RefreshRate is out of range. Resetting "...
0x180022bcd  mov     [rbp+arg_8], rax
0x180022bd1  mov     [rbp+arg_10], r15
0x180022bd5  mov     [rbp+arg_0], 1E6h
0x180022bdc  mov     [rbp+arg_18], r12
0x180022be0  lea     rax, [rbp+arg_8]
0x180022be4  mov     [rsp+60h+var_28], rax
0x180022be9  lea     rax, [rbp+arg_10]
0x180022bed  mov     [rsp+60h+var_30], rax
0x180022bf2  lea     rax, [rbp+arg_0]
0x180022bf6  mov     [rsp+60h+var_38], rax
0x180022bfb  lea     rax, [rbp+arg_18]
0x180022bff  mov     [rsp+60h+var_40], rax
0x180022c04  lea     rdx, byte_18004E405
0x180022c0b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022c10  mov     dword ptr [rbx+70h], 20h ; ' '
0x180022c17  mov     dword ptr [rdi], 1
0x180022c1d  cmp     dword ptr [rbx+78h], 0
0x180022c21  jnz     short loc_180022C84
0x180022c23  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022c28  mov     rcx, [rax+8]
0x180022c2c  mov     eax, [rcx]
0x180022c2e  cmp     eax, 3
0x180022c31  jbe     short loc_180022C7D
0x180022c33  lea     rax, aVsyncfreqdivid; "VSyncFreqDivider is 0. Resetting to 1"
0x180022c3a  mov     [rbp+arg_8], rax
0x180022c3e  mov     [rbp+arg_10], r15
0x180022c42  mov     [rbp+arg_0], 1EDh
0x180022c49  mov     [rbp+arg_18], r12
0x180022c4d  lea     rax, [rbp+arg_8]
0x180022c51  mov     [rsp+60h+var_28], rax
0x180022c56  lea     rax, [rbp+arg_10]
0x180022c5a  mov     [rsp+60h+var_30], rax
0x180022c5f  lea     rax, [rbp+arg_0]
0x180022c63  mov     [rsp+60h+var_38], rax
0x180022c68  lea     rax, [rbp+arg_18]
0x180022c6c  mov     [rsp+60h+var_40], rax
0x180022c71  lea     rdx, byte_18004E3CD
0x180022c78  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022c7d  mov     dword ptr [rbx+78h], 1
0x180022c84  test    byte ptr [rbx+1Ch], 8
0x180022c88  jz      short loc_180022D09
0x180022c8a  lea     rdi, [rbx+9Ch]
0x180022c91  cmp     dword ptr [rbx+98h], 0
0x180022c98  jz      short loc_180022C9F
0x180022c9a  cmp     dword ptr [rdi], 0
0x180022c9d  jnz     short loc_180022D09
0x180022c9f  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022ca4  mov     rcx, [rax+8]
0x180022ca8  mov     eax, [rcx]
0x180022caa  cmp     eax, 3
0x180022cad  jbe     short loc_180022CF9
0x180022caf  lea     rax, aPhysicalsizeCx; "PhysicalSize.cx or PhysicalSize.cy is 0"...
0x180022cb6  mov     [rbp+arg_8], rax
0x180022cba  mov     [rbp+arg_10], r15
0x180022cbe  mov     [rbp+arg_0], 1FAh
0x180022cc5  mov     [rbp+arg_18], r12
0x180022cc9  lea     rax, [rbp+arg_8]
0x180022ccd  mov     [rsp+60h+var_28], rax
0x180022cd2  lea     rax, [rbp+arg_10]
0x180022cd6  mov     [rsp+60h+var_30], rax
0x180022cdb  lea     rax, [rbp+arg_0]
0x180022cdf  mov     [rsp+60h+var_38], rax
0x180022ce4  lea     rax, [rbp+arg_18]
0x180022ce8  mov     [rsp+60h+var_40], rax
0x180022ced  lea     rdx, byte_18004E395
0x180022cf4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022cf9  mov     dword ptr [rbx+98h], 0
0x180022d03  mov     dword ptr [rdi], 0
0x180022d09  test    byte ptr [rbx+1Ch], 4
0x180022d0d  jz      short loc_180022D83
0x180022d0f  mov     eax, [rbx+88h]
0x180022d15  sub     eax, 64h ; 'd'
0x180022d18  cmp     eax, 190h
0x180022d1d  jbe     short loc_180022D83
0x180022d1f  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022d24  mov     rcx, [rax+8]
0x180022d28  mov     eax, [rcx]
0x180022d2a  cmp     eax, 3
0x180022d2d  jbe     short loc_180022D79
0x180022d2f  lea     rax, aDesktopscalefa; "DesktopScaleFactor is out of range(100-"...
0x180022d36  mov     [rbp+arg_8], rax
0x180022d3a  mov     [rbp+arg_10], r15
0x180022d3e  mov     [rbp+arg_0], 208h
0x180022d45  mov     [rbp+arg_18], r12
0x180022d49  lea     rax, [rbp+arg_8]
0x180022d4d  mov     [rsp+60h+var_28], rax
0x180022d52  lea     rax, [rbp+arg_10]
0x180022d56  mov     [rsp+60h+var_30], rax
0x180022d5b  lea     rax, [rbp+arg_0]
0x180022d5f  mov     [rsp+60h+var_38], rax
0x180022d64  lea     rax, [rbp+arg_18]
0x180022d68  mov     [rsp+60h+var_40], rax
0x180022d6d  lea     rdx, byte_18004E35D
0x180022d74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022d79  mov     dword ptr [rbx+88h], 64h ; 'd'
0x180022d83  test    byte ptr [rbx+1Ch], 80h
0x180022d87  jz      short loc_180022E08
0x180022d89  lea     rdi, [rbx+114h]
0x180022d90  cmp     dword ptr [rbx+110h], 0
0x180022d97  jz      short loc_180022D9E
0x180022d99  cmp     dword ptr [rdi], 0
0x180022d9c  jnz     short loc_180022E08
0x180022d9e  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180022da3  mov     rcx, [rax+8]
0x180022da7  mov     eax, [rcx]
0x180022da9  cmp     eax, 3
0x180022dac  jbe     short loc_180022DF8
0x180022dae  lea     rax, aContainerinfoV; "ContainerInfo.VSyncFreq is out of range"...
0x180022db5  mov     [rbp+arg_8], rax
0x180022db9  mov     [rbp+arg_10], r15
0x180022dbd  mov     [rbp+arg_0], 215h
0x180022dc4  mov     [rbp+arg_18], r12
0x180022dc8  lea     rax, [rbp+arg_8]
0x180022dcc  mov     [rsp+60h+var_28], rax
0x180022dd1  lea     rax, [rbp+arg_10]
0x180022dd5  mov     [rsp+60h+var_30], rax
0x180022dda  lea     rax, [rbp+arg_0]
0x180022dde  mov     [rsp+60h+var_38], rax
0x180022de3  lea     rax, [rbp+arg_18]
0x180022de7  mov     [rsp+60h+var_40], rax
0x180022dec  lea     rdx, byte_18004E325
0x180022df3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180022df8  mov     dword ptr [rbx+110h], 20h ; ' '
0x180022e02  mov     dword ptr [rdi], 1
0x180022e08  add     rsp, 60h
0x180022e0c  pop     r15
0x180022e0e  pop     r12
0x180022e10  pop     rdi
0x180022e11  pop     rbx
0x180022e12  pop     rbp
0x180022e13  retn
```
