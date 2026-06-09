# WindowsPerformanceRecorder::CETWProperties::ConfigEventProviders(WindowsPerformanceRecorder::CControlManager *,WindowsPerformanceRecorder::CETWProperties::CEventSession *,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *,std::less<WindowsPerformanceRecorder::CBaseProfileElement const *>,std::allocator<WindowsPerformanceRecorder::CBaseProfileElement const *>> const &,WindowsPerformanceRecorder::CEventCollectorElement const *)

- ea: `0x18001f170`
- end: `0x18001fbae`
- name: `?ConfigEventProviders@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEAVCControlManager@2@PEAUCEventSession@12@AEBV?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@PEBVCEventCollectorElement@2@@Z`
- size: `2622`
- prototype: `__int64 __usercall@<rax>(WindowsPerformanceRecorder::CETWProperties *this@<rcx>, struct WindowsPerformanceRecorder::CControlManager *@<rdx>, WindowsPerformanceRecorder::CETWProperties::CEventSession *@<r8>, __int64)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800195b0`
- `0x18003d11c`

## callees

- `0x180009a84`
- `0x18000b34c`
- `0x18000bca0`
- `0x18000be30`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001f170`
- `0x18001fbc0`
- `0x1800209d0`
- `0x180021370`
- `0x180021634`
- `0x180025650`
- `0x18002d5c0`
- `0x180039de4`
- `0x180047130`
- `0x18004b688`
- `0x18004dfb0`
- `0x18004ece0`
- `0x18008c010`

## string_xrefs

- `0x18001f3c2`: `COMGUARD`
- `0x18001fb1b`: `COMGUARD`
- `0x18001fb7a`: `COMGUARD`
- `0x18001f3d7`: `ConfigEventProviders`
- `0x18001f63b`: `ConfigEventProviders`
- `0x18001f974`: `ConfigEventProviders`
- `0x18001fab3`: `ConfigEventProviders`
- `0x18001fb30`: `ConfigEventProviders`
- `0x18001fb8f`: `ConfigEventProviders`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall WindowsPerformanceRecorder::CETWProperties::ConfigEventProviders(
        WindowsPerformanceRecorder::CETWProperties *this,
        struct WindowsPerformanceRecorder::CControlManager *a2,
        WindowsPerformanceRecorder::CETWProperties::CEventSession *a3,
        _QWORD **a4,
        __int64 a5)
{
  struct WindowsPerformanceRecorder::CControlManager *v7; // r14
  int result; // eax
  __int64 *v10; // rbx
  __int64 v11; // r15
  int v12; // ecx
  int v13; // ecx
  char v14; // bp
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r8
  __int64 **v20; // rcx
  __int64 *j; // rcx
  struct WindowsPerformanceRecorder::CEventProviderElement *v22; // r15
  __int64 v23; // rbx
  __int64 v24; // rbp
  signed int UTCProviders; // esi
  __int64 *i; // rax
  bool v27; // al
  const unsigned __int16 *v28; // rax
  const struct _GUID *v29; // r8
  const char *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  unsigned __int64 k; // rbx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rcx
  const unsigned __int16 *v38; // r8
  _QWORD *v39; // rax
  __int64 v40; // r8
  __int64 v41; // rax
  const unsigned __int16 *v42; // rax
  struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *v43; // r9
  __int64 v44; // rdi
  __int64 v45; // r8
  __int64 v46; // rax
  const unsigned __int16 *v47; // rax
  __int64 v48; // r8
  __int64 v49; // rax
  const unsigned __int16 *SessionName; // rax
  struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *v51; // r9
  const unsigned __int16 *v52; // rax
  const struct _GUID *v53; // r8
  const char *v54; // rax
  unsigned __int64 v55; // rsi
  signed int PerfTrackProviders; // edi
  struct WindowsPerformanceRecorder::CControlManager *v57; // rdi
  const unsigned __int16 *v58; // rax
  __int64 v59; // r8
  const unsigned __int16 *v60; // rax
  const struct _GUID *v61; // r8
  const char *v62; // rax
  signed int UTCDisallowProviders; // ebx
  char *v64; // [rsp+28h] [rbp-4E0h]
  struct IControlErrorInfo *v65; // [rsp+38h] [rbp-4D0h]
  struct WindowsPerformanceRecorder::CEventProviderElement *v66; // [rsp+40h] [rbp-4C8h] BYREF
  struct WindowsPerformanceRecorder::CControlManager *v67; // [rsp+48h] [rbp-4C0h]
  char *v68; // [rsp+50h] [rbp-4B8h]
  __int64 v69; // [rsp+58h] [rbp-4B0h] BYREF
  _QWORD **v70; // [rsp+60h] [rbp-4A8h]
  __int64 v71; // [rsp+68h] [rbp-4A0h]
  _BYTE v72[8]; // [rsp+70h] [rbp-498h] BYREF
  _BYTE v73[8]; // [rsp+78h] [rbp-490h] BYREF
  _BYTE v74[272]; // [rsp+80h] [rbp-488h] BYREF
  _BYTE v75[272]; // [rsp+190h] [rbp-378h] BYREF
  _BYTE v76[272]; // [rsp+2A0h] [rbp-268h] BYREF
  _BYTE v77[272]; // [rsp+3B0h] [rbp-158h] BYREF

  v71 = -2;
  v70 = a4;
  v7 = a2;
  v67 = a2;
  v66 = 0;
  result = WindowsPerformanceRecorder::CWPRControl::GetInstance(&v66);
  if ( result < 0 )
    return result;
  v68 = (char *)v66 + 80;
  v66 = 0;
  v10 = (__int64 *)**a4;
  while ( !*((_BYTE *)v10 + 25) )
  {
    v11 = v10[4];
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) != 8 )
      goto LABEL_24;
    v12 = *(_DWORD *)(v11 + 24);
    if ( !v12 )
    {
      if ( *(_DWORD *)(v11 + 28) != *(_DWORD *)&GUID_NULL.Data2 || *(_DWORD *)(v11 + 32) != *(_DWORD *)GUID_NULL.Data4 )
        goto LABEL_8;
      if ( *(_DWORD *)(v11 + 36) == *(_DWORD *)&GUID_NULL.Data4[4] )
        goto LABEL_24;
    }
    if ( v12 != -1503067620 )
      goto LABEL_56;
    if ( *(_DWORD *)(v11 + 28) != *(_DWORD *)&ControlGuid_ClrRundown.Data2
      || *(_DWORD *)(v11 + 32) != *(_DWORD *)ControlGuid_ClrRundown.Data4 )
    {
      goto LABEL_8;
    }
    if ( *(_DWORD *)(v11 + 36) != *(_DWORD *)&ControlGuid_ClrRundown.Data4[4] )
    {
LABEL_56:
      if ( v12 != -516158173
        || *(_DWORD *)(v11 + 28) != *(_DWORD *)&ControlGuid_ClrRuntime.Data2
        || *(_DWORD *)(v11 + 32) != *(_DWORD *)ControlGuid_ClrRuntime.Data4
        || *(_DWORD *)(v11 + 36) != *(_DWORD *)&ControlGuid_ClrRuntime.Data4[4] )
      {
        goto LABEL_8;
      }
    }
    v27 = Performance::COSVersionInfo::IsWin7AndUp()
       && WindowsPerformanceRecorder::Impl::CDotNetVersion::IsV4Installed();
    *((_BYTE *)this + 304) = v27;
LABEL_8:
    if ( *(_BYTE *)(v11 + 45) )
    {
      std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CETWProperties::CEventProvider>>>,_GUID>(
        &v69,
        *((_QWORD *)a3 + 6),
        *((_QWORD *)a3 + 7),
        v11 + 24);
      if ( v69 == v48 )
      {
        v49 = WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(
                (WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v77,
                (const struct _GUID *)(v11 + 24));
        std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::push_back((char *)a3 + 48, v49);
        WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider((WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v77);
        *(_QWORD *)(*((_QWORD *)a3 + 7) - 264LL + 56) = v11;
      }
      SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
      result = WindowsPerformanceRecorder::CETWProperties::SetEventProviderProperties(
                 this,
                 v7,
                 SessionName,
                 (const struct WindowsPerformanceRecorder::CEventProviderElement *)v11,
                 v51);
      if ( result < 0 )
        return result;
    }
    else
    {
      v13 = *(_DWORD *)(v11 + 24);
      if ( v13 != -1941358955 )
      {
        if ( v13 == -479908279
          && *(_DWORD *)(v11 + 28) == *(_DWORD *)&ControlGuid_DotNetProvider.Data2
          && *(_DWORD *)(v11 + 32) == *(_DWORD *)ControlGuid_DotNetProvider.Data4 )
        {
          if ( *(_DWORD *)(v11 + 36) == *(_DWORD *)&ControlGuid_DotNetProvider.Data4[4] )
          {
            if ( !Performance::COSVersionInfo::IsWin7AndUp()
              || !WindowsPerformanceRecorder::Impl::CDotNetVersion::IsV4Installed() )
            {
              *((_BYTE *)this + 304) = 0;
              if ( v7 )
              {
                v60 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
                WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
                  v7,
                  -984080379,
                  v61,
                  &ControlGuid_DotNetProvider,
                  v60,
                  *((const unsigned __int16 **)this + 40),
                  0,
                  v65);
                v62 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
                WindowsPerformanceRecorder::TraceHR(
                  (WindowsPerformanceRecorder *)3,
                  (unsigned __int8)"ConfigEventProviders",
                  (const char *)0x56F,
                  0xC5582005,
                  "%ws: %ws",
                  v62,
                  *((_QWORD *)this + 40));
              }
              goto LABEL_24;
            }
            *((_BYTE *)this + 304) = 1;
            v39 = (_QWORD *)std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CETWProperties::CEventProvider>>>,_GUID>(
                              v72,
                              *((_QWORD *)a3 + 3),
                              *((_QWORD *)a3 + 4),
                              &ControlGuid_ClrRuntime);
            if ( *v39 == v40 )
            {
              v41 = WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(
                      (WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v74,
                      &ControlGuid_ClrRuntime);
              std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::push_back((char *)a3 + 24, v41);
              WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider((WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v74);
            }
            v42 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
            result = WindowsPerformanceRecorder::CETWProperties::SetEventProviderProperties(
                       this,
                       v7,
                       v42,
                       (const struct WindowsPerformanceRecorder::CEventProviderElement *)v11,
                       v43);
            if ( result < 0 )
              return result;
            v44 = *(_QWORD *)std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CETWProperties::CEventProvider>>>,_GUID>(
                               v73,
                               *((_QWORD *)a3 + 6),
                               *((_QWORD *)a3 + 7),
                               &ControlGuid_ClrRundown);
            if ( v44 == v45 )
            {
              v46 = WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(
                      (WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v75,
                      &ControlGuid_ClrRundown);
              std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::push_back((char *)a3 + 48, v46);
              WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider((WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v75);
              v44 = *((_QWORD *)a3 + 7) - 264LL;
            }
            v47 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
            result = WindowsPerformanceRecorder::CETWProperties::SetEventProviderProperties(
                       this,
                       v7,
                       v47,
                       (const struct WindowsPerformanceRecorder::CEventProviderElement *)v11,
                       (struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v44);
            if ( result < 0 )
              return result;
            *(_QWORD *)(v44 + 16) = 0;
            *(_BYTE *)(v44 + 248) = 0;
            goto LABEL_90;
          }
          v14 = 0;
        }
        else
        {
LABEL_11:
          v14 = 0;
          if ( v13 == 1698668509
            && *(_DWORD *)(v11 + 28) == 1074338319
            && *(_DWORD *)(v11 + 32) == -888303432
            && *(_DWORD *)(v11 + 36) == -1363564742 )
          {
            if ( !Performance::COSVersionInfo::IsWin7AndUp() )
            {
              if ( v7 )
              {
                v28 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
                WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
                  v7,
                  -984080381,
                  v29,
                  (const struct _GUID *)(v11 + 24),
                  v28,
                  *((const unsigned __int16 **)this + 40),
                  0,
                  v65);
                v30 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
                LODWORD(v65) = *(_DWORD *)(v11 + 24);
                WindowsPerformanceRecorder::TraceHR(
                  (WindowsPerformanceRecorder *)3,
                  (unsigned __int8)"ConfigEventProviders",
                  (const char *)0x57C,
                  0xC5582003,
                  "%ws: %ws, {0x%x...}",
                  v30,
                  *((_QWORD *)this + 40));
              }
              goto LABEL_24;
            }
            if ( !*((_BYTE *)a3 + 209) )
            {
              *((_BYTE *)a3 + 209) = 1;
              v66 = (struct WindowsPerformanceRecorder::CEventProviderElement *)v11;
            }
            v14 = 1;
          }
        }
LABEL_12:
        if ( *(_BYTE *)(v11 + 41) )
          *(_DWORD *)(*((_QWORD *)a3 + 1) + 64LL) &= ~0x1000000u;
        v15 = *((_QWORD *)a3 + 4);
        v16 = *((_QWORD *)a3 + 3);
        if ( v16 == v15 )
          goto LABEL_73;
        do
        {
          if ( *(_DWORD *)v16 == *(_DWORD *)(v11 + 24)
            && *(_DWORD *)(v16 + 4) == *(_DWORD *)(v11 + 28)
            && *(_DWORD *)(v16 + 8) == *(_DWORD *)(v11 + 32)
            && *(_DWORD *)(v16 + 12) == *(_DWORD *)(v11 + 36) )
          {
            break;
          }
          v16 += 264;
        }
        while ( v16 != v15 );
        if ( v16 == v15 )
        {
LABEL_73:
          v31 = WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(
                  (WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v76,
                  (const struct _GUID *)(v11 + 24));
          v32 = *((_QWORD *)a3 + 4);
          if ( v32 == *((_QWORD *)a3 + 5) )
          {
            std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventProvider>(
              (char *)a3 + 24,
              *((_QWORD *)a3 + 4),
              v31);
          }
          else
          {
            WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(v32, v31);
            *((_QWORD *)a3 + 4) += 264LL;
          }
          WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider((WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v76);
          v16 = *((_QWORD *)a3 + 4) - 264LL;
          *(_QWORD *)(v16 + 56) = v11;
        }
        if ( a5 && (*(_BYTE *)(a5 + 88) || *(_BYTE *)(a5 + 89)) )
          *(_OWORD *)(*((_QWORD *)a3 + 1) + 24LL) = *(_OWORD *)v16;
        v17 = *((_QWORD *)a3 + 1);
        if ( v17 && (v18 = *(unsigned int *)(v17 + 116), (_DWORD)v18) )
          v19 = (const unsigned __int16 *)(v17 + v18);
        else
          v19 = 0;
        v7 = v67;
        result = WindowsPerformanceRecorder::CETWProperties::SetEventProviderProperties(
                   this,
                   v67,
                   v19,
                   (const struct WindowsPerformanceRecorder::CEventProviderElement *)v11,
                   (struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *)v16);
        if ( result < 0 )
          return result;
        if ( !v14 && !*(_QWORD *)(v16 + 16) )
          *(_QWORD *)(v16 + 16) = -1;
        goto LABEL_24;
      }
      if ( *(_DWORD *)(v11 + 28) != 1087061492 || *(_DWORD *)(v11 + 32) != -593617487 )
        goto LABEL_11;
      if ( *(_DWORD *)(v11 + 36) != -1412246207 )
      {
        v14 = 0;
        goto LABEL_12;
      }
      if ( Performance::COSVersionInfo::IsWin7AndUp() )
      {
        if ( *((_BYTE *)a3 + 208) )
          goto LABEL_24;
        v55 = 0xF83E0F83E0F83E1LL * ((__int64)(*((_QWORD *)a3 + 4) - *((_QWORD *)a3 + 3)) >> 3);
        PerfTrackProviders = WindowsPerformanceRecorder::CEventProvidersCache::GetPerfTrackProviders(
                               v68,
                               (char *)a3 + 24);
        if ( PerfTrackProviders < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"ConfigEventProviders",
            (const char *)0x522,
            PerfTrackProviders,
            "COMGUARD",
            v64);
          return PerfTrackProviders;
        }
        v57 = v67;
        while ( v55 < 0xF83E0F83E0F83E1LL * ((__int64)(*((_QWORD *)a3 + 4) - *((_QWORD *)a3 + 3)) >> 3) )
        {
          v58 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
          result = WindowsPerformanceRecorder::CETWProperties::SetEventProviderProperties(
                     this,
                     v57,
                     v58,
                     (const struct WindowsPerformanceRecorder::CEventProviderElement *)v11,
                     (struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *)(v59 + 264 * v55));
          if ( result < 0 )
            return result;
          ++v55;
        }
        *((_BYTE *)a3 + 208) = 1;
        v7 = v57;
LABEL_90:
        if ( *(_BYTE *)(v11 + 41) )
          *(_DWORD *)(*((_QWORD *)a3 + 1) + 64LL) &= ~0x1000000u;
        goto LABEL_24;
      }
      if ( v7 )
      {
        v52 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
        WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
          v7,
          -984080381,
          v53,
          (const struct _GUID *)(v11 + 24),
          v52,
          *((const unsigned __int16 **)this + 40),
          0,
          v65);
        v54 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a3);
        LODWORD(v65) = *(_DWORD *)(v11 + 24);
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"ConfigEventProviders",
          (const char *)0x519,
          0xC5582003,
          "%ws: %ws, {0x%x...}",
          v54,
          *((_QWORD *)this + 40));
      }
    }
LABEL_24:
    v20 = (__int64 **)v10[2];
    if ( *((_BYTE *)v20 + 25) )
    {
      for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( v10 != (__int64 *)i[2] )
          break;
        v10 = i;
      }
      v10 = i;
    }
    else
    {
      v10 = (__int64 *)v10[2];
      for ( j = *v20; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v10 = j;
    }
  }
  if ( !*((_BYTE *)a3 + 209) )
    return 0;
  v22 = v66;
  if ( !v66 )
    return 0;
  v23 = *((_QWORD *)a3 + 4);
  v24 = *((_QWORD *)a3 + 3);
  UTCProviders = WindowsPerformanceRecorder::CEventProvidersCache::GetUTCProviders(v68, (char *)a3 + 24);
  if ( UTCProviders < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"ConfigEventProviders",
      (const char *)0x5C9,
      UTCProviders,
      "COMGUARD",
      v64);
    return UTCProviders;
  }
  for ( k = 0xF83E0F83E0F83E1LL * ((v23 - v24) >> 3); ; ++k )
  {
    v34 = *((_QWORD *)a3 + 3);
    v35 = *((_QWORD *)a3 + 4);
    if ( k >= 0xF83E0F83E0F83E1LL * ((v35 - v34) >> 3) )
      break;
    v36 = *((_QWORD *)a3 + 1);
    if ( v36 && (v37 = *(unsigned int *)(v36 + 116), (_DWORD)v37) )
      v38 = (const unsigned __int16 *)(v36 + v37);
    else
      v38 = 0;
    result = WindowsPerformanceRecorder::CETWProperties::SetEventProviderProperties(
               this,
               v7,
               v38,
               v22,
               (struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *)(v34 + 264 * k));
    if ( result < 0 )
      return result;
  }
  if ( v70[1] == (_QWORD *)1 && v35 == v34 )
    return -984087022;
  UTCDisallowProviders = WindowsPerformanceRecorder::CEventProvidersCache::GetUTCDisallowProviders(v35, (char *)a3 + 72);
  if ( UTCDisallowProviders >= 0 )
    return 0;
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)2,
    (unsigned __int8)"ConfigEventProviders",
    (const char *)0x5D6,
    UTCDisallowProviders,
    "COMGUARD",
    v64);
  return UTCDisallowProviders;
}

```

## disassembly

```asm
0x18001f170  push    rbp
0x18001f172  push    rsi
0x18001f173  push    rdi
0x18001f174  push    r12
0x18001f176  push    r13
0x18001f178  push    r14
0x18001f17a  push    r15
0x18001f17c  sub     rsp, 4D0h
0x18001f183  mov     [rsp+508h+var_4A0], 0FFFFFFFFFFFFFFFEh
0x18001f18c  mov     [rsp+508h+arg_18], rbx
0x18001f194  mov     rax, cs:__security_cookie
0x18001f19b  xor     rax, rsp
0x18001f19e  mov     [rsp+508h+var_48], rax
0x18001f1a6  mov     rbx, r9
0x18001f1a9  mov     [rsp+508h+var_4A8], rbx
0x18001f1ae  mov     r13, r8
0x18001f1b1  mov     r14, rdx
0x18001f1b4  mov     [rsp+508h+var_4C0], rdx
0x18001f1b9  mov     r12, rcx
0x18001f1bc  mov     [rsp+508h+var_4C8], 0
0x18001f1c5  lea     rcx, [rsp+508h+var_4C8]; struct WindowsPerformanceRecorder::CWPRControl **
0x18001f1ca  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x18001f1cf  test    eax, eax
0x18001f1d1  js      loc_18001F3EA
0x18001f1d7  mov     rax, [rsp+508h+var_4C8]
0x18001f1dc  add     rax, 50h ; 'P'
0x18001f1e0  mov     [rsp+508h+var_4B8], rax
0x18001f1e5  xor     r15d, r15d
0x18001f1e8  mov     [rsp+508h+var_4C8], r15
0x18001f1ed  mov     rbx, [rbx]
0x18001f1f0  mov     rbx, [rbx]
0x18001f1f3  lea     rdi, aWsWs0xX; "%ws: %ws, {0x%x...}"
0x18001f1fa  mov     rbp, 0F83E0F83E0F83E1h
0x18001f204  cmp     byte ptr [rbx+19h], 0
0x18001f208  jnz     loc_18001F386
0x18001f20e  mov     r15, [rbx+20h]
0x18001f212  mov     rax, [r15]
0x18001f215  mov     rcx, r15
0x18001f218  mov     rax, [rax+8]
0x18001f21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f221  cmp     eax, 8
0x18001f224  jnz     loc_18001F328
0x18001f22a  mov     ecx, [r15+18h]
0x18001f22e  test    ecx, ecx
0x18001f230  jz      loc_18001F46A
0x18001f236  cmp     ecx, 0A669021Ch
0x18001f23c  jz      loc_18001F49F
0x18001f242  cmp     ecx, 0E13C0D23h
0x18001f248  jz      loc_18001F4F0
0x18001f24e  cmp     byte ptr [r15+2Dh], 0
0x18001f253  jnz     loc_18001F862
0x18001f259  mov     ecx, [r15+18h]
0x18001f25d  cmp     ecx, 8C493695h
0x18001f263  jz      loc_18001F522
0x18001f269  cmp     ecx, 0E3652E49h
0x18001f26f  jz      loc_18001F55A
0x18001f275  xor     bpl, bpl
0x18001f278  cmp     ecx, 653F9FDDh
0x18001f27e  jz      loc_18001F592
0x18001f284  cmp     byte ptr [r15+29h], 0
0x18001f289  jnz     loc_18001F43A
0x18001f28f  mov     rcx, [r13+20h]
0x18001f293  mov     rdi, [r13+18h]
0x18001f297  cmp     rdi, rcx
0x18001f29a  jz      loc_18001F65B
0x18001f2a0  mov     edx, [r15+18h]
0x18001f2a4  cmp     [rdi], edx
0x18001f2a6  jz      loc_18001F35A
0x18001f2ac  add     rdi, 108h
0x18001f2b3  cmp     rdi, rcx
0x18001f2b6  jnz     short loc_18001F2A4
0x18001f2b8  cmp     rdi, rcx
0x18001f2bb  jz      loc_18001F65B
0x18001f2c1  mov     rax, [rsp+508h+arg_20]
0x18001f2c9  test    rax, rax
0x18001f2cc  jnz     loc_18001F44A
0x18001f2d2  mov     rax, [r13+8]
0x18001f2d6  test    rax, rax
0x18001f2d9  jz      loc_18001FAFB
0x18001f2df  mov     ecx, [rax+74h]
0x18001f2e2  test    ecx, ecx
0x18001f2e4  jz      loc_18001FAFB
0x18001f2ea  lea     r8, [rax+rcx]; unsigned __int16 *
0x18001f2ee  mov     [rsp+508h+Format], rdi; struct WindowsPerformanceRecorder::CETWProperties::CEventProvider *
0x18001f2f3  mov     r9, r15; struct WindowsPerformanceRecorder::CEventProviderElement *
0x18001f2f6  mov     r14, [rsp+508h+var_4C0]
0x18001f2fb  mov     rdx, r14; struct WindowsPerformanceRecorder::CControlManager *
0x18001f2fe  mov     rcx, r12; this
0x18001f301  call    ?SetEventProviderProperties@CETWProperties@WindowsPerformanceRecorder@@AEBAJPEAVCControlManager@2@PEBGPEBVCEventProviderElement@2@PEAUCEventProvider@12@@Z; WindowsPerformanceRecorder::CETWProperties::SetEventProviderProperties(WindowsPerformanceRecorder::CControlManager *,ushort const *,WindowsPerformanceRecorder::CEventProviderElement const *,WindowsPerformanceRecorder::CETWProperties::CEventProvider *)
0x18001f306  test    eax, eax
0x18001f308  js      loc_18001F3EA
0x18001f30e  test    bpl, bpl
0x18001f311  mov     rbp, 0F83E0F83E0F83E1h
0x18001f31b  jz      loc_18001FB03
0x18001f321  lea     rdi, aWsWs0xX; "%ws: %ws, {0x%x...}"
0x18001f328  mov     rcx, [rbx+10h]
0x18001f32c  cmp     byte ptr [rcx+19h], 0
0x18001f330  jnz     loc_18001F415
0x18001f336  mov     rbx, rcx
0x18001f339  mov     rcx, [rcx]
0x18001f33c  cmp     byte ptr [rcx+19h], 0
0x18001f340  jnz     loc_18001F204
0x18001f346  mov     rbx, rcx
0x18001f349  mov     rax, [rcx]
0x18001f34c  mov     rcx, rax
0x18001f34f  cmp     byte ptr [rax+19h], 0
0x18001f353  jz      short loc_18001F346
0x18001f355  jmp     loc_18001F204
0x18001f35a  mov     eax, [r15+1Ch]
0x18001f35e  cmp     [rdi+4], eax
0x18001f361  jnz     loc_18001F2AC
0x18001f367  mov     eax, [r15+20h]
0x18001f36b  cmp     [rdi+8], eax
0x18001f36e  jnz     loc_18001F2AC
0x18001f374  mov     eax, [r15+24h]
0x18001f378  cmp     [rdi+0Ch], eax
0x18001f37b  jz      loc_18001F2B8
0x18001f381  jmp     loc_18001F2AC
0x18001f386  cmp     byte ptr [r13+0D1h], 0
0x18001f38e  jz      loc_18001FBA7
0x18001f394  mov     r15, [rsp+508h+var_4C8]
0x18001f399  test    r15, r15
0x18001f39c  jz      loc_18001FBA7
0x18001f3a2  mov     rbx, [r13+20h]
0x18001f3a6  mov     rbp, [r13+18h]
0x18001f3aa  lea     rdx, [r13+18h]
0x18001f3ae  mov     rcx, [rsp+508h+var_4B8]
0x18001f3b3  call    ?GetUTCProviders@CEventProvidersCache@WindowsPerformanceRecorder@@QEAAJAEAV?$vector@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@@Z; WindowsPerformanceRecorder::CEventProvidersCache::GetUTCProviders(std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider> &)
0x18001f3b8  mov     esi, eax
0x18001f3ba  test    eax, eax
0x18001f3bc  jns     loc_18001F6AC
0x18001f3c2  lea     rax, aComguard; "COMGUARD"
0x18001f3c9  mov     [rsp+508h+Format], rax; Format
0x18001f3ce  mov     r9d, esi; unsigned int
0x18001f3d1  mov     r8d, 5C9h; char *
0x18001f3d7  lea     rdx, aConfigeventpro; "ConfigEventProviders"
0x18001f3de  mov     ecx, 2; this
0x18001f3e3  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001f3e8  mov     eax, esi
0x18001f3ea  mov     rcx, [rsp+508h+var_48]
0x18001f3f2  xor     rcx, rsp; StackCookie
0x18001f3f5  call    __security_check_cookie
0x18001f3fa  mov     rbx, [rsp+508h+arg_18]
0x18001f402  add     rsp, 4D0h
0x18001f409  pop     r15
0x18001f40b  pop     r14
0x18001f40d  pop     r13
0x18001f40f  pop     r12
0x18001f411  pop     rdi
0x18001f412  pop     rsi
0x18001f413  pop     rbp
0x18001f414  retn
0x18001f415  mov     rax, [rbx+8]
0x18001f419  cmp     byte ptr [rax+19h], 0
0x18001f41d  jnz     short loc_18001F432
0x18001f41f  cmp     rbx, [rax+10h]
0x18001f423  jnz     short loc_18001F432
0x18001f425  mov     rbx, rax
0x18001f428  mov     rax, [rax+8]
0x18001f42c  cmp     byte ptr [rax+19h], 0
0x18001f430  jz      short loc_18001F41F
0x18001f432  mov     rbx, rax
0x18001f435  jmp     loc_18001F204
0x18001f43a  mov     rax, [r13+8]
0x18001f43e  and     dword ptr [rax+40h], 0FEFFFFFFh
0x18001f445  jmp     loc_18001F28F
0x18001f44a  cmp     byte ptr [rax+58h], 0
0x18001f44e  jnz     short loc_18001F45A
0x18001f450  cmp     byte ptr [rax+59h], 0
0x18001f454  jz      loc_18001F2D2
0x18001f45a  movups  xmm0, xmmword ptr [rdi]
0x18001f45d  mov     rax, [r13+8]
0x18001f461  movups  xmmword ptr [rax+18h], xmm0
0x18001f465  jmp     loc_18001F2D2
0x18001f46a  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18001f470  cmp     [r15+1Ch], eax
0x18001f474  jnz     loc_18001F24E
0x18001f47a  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18001f480  cmp     [r15+20h], eax
0x18001f484  jnz     loc_18001F24E
0x18001f48a  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18001f490  cmp     [r15+24h], eax
0x18001f494  jnz     loc_18001F236
0x18001f49a  jmp     loc_18001F328
0x18001f49f  mov     eax, dword ptr cs:ControlGuid_ClrRundown.Data2
0x18001f4a5  cmp     [r15+1Ch], eax
0x18001f4a9  jnz     loc_18001F24E
0x18001f4af  mov     eax, dword ptr cs:ControlGuid_ClrRundown.Data4
0x18001f4b5  cmp     [r15+20h], eax
0x18001f4b9  jnz     loc_18001F24E
0x18001f4bf  mov     eax, dword ptr cs:ControlGuid_ClrRundown.Data4+4
0x18001f4c5  cmp     [r15+24h], eax
0x18001f4c9  jnz     loc_18001F242
0x18001f4cf  call    ?IsWin7AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin7AndUp(void)
0x18001f4d4  test    al, al
0x18001f4d6  jz      loc_18001F8E8
0x18001f4dc  call    ?IsV4Installed@CDotNetVersion@Impl@WindowsPerformanceRecorder@@SA_NXZ; WindowsPerformanceRecorder::Impl::CDotNetVersion::IsV4Installed(void)
0x18001f4e1  test    al, al
0x18001f4e3  jz      loc_18001F8E8
0x18001f4e9  mov     al, 1
0x18001f4eb  jmp     loc_18001F8EA
0x18001f4f0  mov     eax, dword ptr cs:ControlGuid_ClrRuntime.Data2
0x18001f4f6  cmp     [r15+1Ch], eax
0x18001f4fa  jnz     loc_18001F24E
0x18001f500  mov     eax, dword ptr cs:ControlGuid_ClrRuntime.Data4
0x18001f506  cmp     [r15+20h], eax
0x18001f50a  jnz     loc_18001F24E
0x18001f510  mov     eax, dword ptr cs:ControlGuid_ClrRuntime.Data4+4
0x18001f516  cmp     [r15+24h], eax
0x18001f51a  jnz     loc_18001F24E
0x18001f520  jmp     short loc_18001F4CF
0x18001f522  mov     eax, cs:dword_18009850C
0x18001f528  cmp     [r15+1Ch], eax
0x18001f52c  jnz     loc_18001F275
0x18001f532  mov     eax, cs:dword_180098510
0x18001f538  cmp     [r15+20h], eax
0x18001f53c  jnz     loc_18001F275
0x18001f542  mov     eax, cs:dword_180098514
0x18001f548  cmp     [r15+24h], eax
0x18001f54c  jz      loc_18001F8F7
0x18001f552  xor     bpl, bpl
0x18001f555  jmp     loc_18001F284
0x18001f55a  mov     eax, dword ptr cs:ControlGuid_DotNetProvider.Data2
0x18001f560  cmp     [r15+1Ch], eax
0x18001f564  jnz     loc_18001F275
0x18001f56a  mov     eax, dword ptr cs:ControlGuid_DotNetProvider.Data4
0x18001f570  cmp     [r15+20h], eax
0x18001f574  jnz     loc_18001F275
0x18001f57a  mov     eax, dword ptr cs:ControlGuid_DotNetProvider.Data4+4
0x18001f580  cmp     [r15+24h], eax
0x18001f584  jz      loc_18001FA22
0x18001f58a  xor     bpl, bpl
0x18001f58d  jmp     loc_18001F284
0x18001f592  mov     eax, cs:dword_18009852C
0x18001f598  cmp     [r15+1Ch], eax
0x18001f59c  jnz     loc_18001F284
0x18001f5a2  mov     eax, cs:dword_180098530
0x18001f5a8  cmp     [r15+20h], eax
0x18001f5ac  jnz     loc_18001F284
0x18001f5b2  mov     eax, cs:dword_180098534
0x18001f5b8  cmp     [r15+24h], eax
0x18001f5bc  jnz     loc_18001F284
0x18001f5c2  call    ?IsWin7AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin7AndUp(void)
0x18001f5c7  test    al, al
0x18001f5c9  jnz     loc_18001FAC9
0x18001f5cf  test    r14, r14
0x18001f5d2  jz      short loc_18001F64C
0x18001f5d4  mov     rcx, r13; this
0x18001f5d7  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18001f5dc  mov     [rsp+508h+var_4D8], 0; unsigned __int16 *
0x18001f5e5  mov     rcx, [r12+140h]
0x18001f5ed  mov     [rsp+508h+var_4E0], rcx; unsigned __int16 *
0x18001f5f2  mov     [rsp+508h+Format], rax; unsigned __int16 *
0x18001f5f7  lea     r9, [r15+18h]; struct _GUID *
0x18001f5fb  mov     edx, 0C5582003h; int
0x18001f600  mov     rcx, r14; this
0x18001f603  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x18001f608  mov     rcx, r13; this
0x18001f60b  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18001f610  mov     ecx, [r15+18h]
0x18001f614  mov     dword ptr [rsp+508h+var_4D0], ecx
0x18001f618  mov     rcx, [r12+140h]
0x18001f620  mov     [rsp+508h+var_4D8], rcx
0x18001f625  mov     [rsp+508h+var_4E0], rax; char *
0x18001f62a  mov     [rsp+508h+Format], rdi; Format
0x18001f62f  mov     r9d, 0C5582003h; unsigned int
0x18001f635  mov     r8d, 57Ch; char *
0x18001f63b  lea     rdx, aConfigeventpro; "ConfigEventProviders"
0x18001f642  mov     ecx, 3; this
0x18001f647  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001f64c  mov     rbp, 0F83E0F83E0F83E1h
0x18001f656  jmp     loc_18001F328
0x18001f65b  lea     rdx, [r15+18h]; struct _GUID *
0x18001f65f  lea     rcx, [rsp+508h+var_268]; this
0x18001f667  call    ??0CEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAA@AEBU_GUID@@@Z; WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(_GUID const &)
0x18001f66c  nop
0x18001f66d  mov     rcx, [r13+20h]
0x18001f671  cmp     rcx, [r13+28h]
0x18001f675  jz      loc_18001FAE7
0x18001f67b  mov     rdx, rax
0x18001f67e  call    ??0CEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAA@$$QEAU012@@Z; WindowsPerformanceRecorder::CETWProperties::CEventProvider::CEventProvider(WindowsPerformanceRecorder::CETWProperties::CEventProvider &&)
0x18001f683  add     qword ptr [r13+20h], 108h
0x18001f68b  lea     rcx, [rsp+508h+var_268]; this
0x18001f693  call    ??1CEventProvider@CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CEventProvider::~CEventProvider(void)
0x18001f698  mov     rdi, [r13+20h]
0x18001f69c  add     rdi, 0FFFFFFFFFFFFFEF8h
0x18001f6a3  mov     [rdi+38h], r15
0x18001f6a7  jmp     loc_18001F2C1
0x18001f6ac  sub     rbx, rbp
0x18001f6af  sar     rbx, 3
0x18001f6b3  mov     rsi, 0F83E0F83E0F83E1h
0x18001f6bd  imul    rbx, rsi
0x18001f6c1  mov     rdx, [r13+18h]
0x18001f6c5  mov     rcx, [r13+20h]
0x18001f6c9  mov     rax, rcx
0x18001f6cc  sub     rax, rdx
0x18001f6cf  sar     rax, 3
0x18001f6d3  imul    rax, rsi
0x18001f6d7  cmp     rbx, rax
0x18001f6da  jnb     loc_18001FB50
  ... truncated ...
```
