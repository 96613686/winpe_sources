# Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations(void)

- ea: `0x1800838ec`
- end: `0x1800841e8`
- name: `?GetPendingInstallations@PrinterExtensionRegistrarService@Driver@Print@@AEAA?AV?$list@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@V?$allocator@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@@2@@std@@XZ`
- size: `2300`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180085910`

## callees

- `0x180003400`
- `0x180003c20`
- `0x18000439e`
- `0x180004558`
- `0x180004564`
- `0x18000de1c`
- `0x18000e644`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180019618`
- `0x1800197b4`
- `0x180035600`
- `0x180036f2c`
- `0x180037d00`
- `0x1800412a4`
- `0x180081cc0`
- `0x180081f34`
- `0x180083460`
- `0x1800838ec`
- `0x1800ea158`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180083d49`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180083d49`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180083d58`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180083d6d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180083ddb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180083d58`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180083d6d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180083ddb`
- `ADVAPI32!RegCloseKey` at `0x1800840df`
- `ADVAPI32!RegCloseKey` at `0x1800840df`

## string_xrefs

- `0x180083ae5`: `Failed reading AppPath value. hr=0x%x`
- `0x180083eae`: `Failure reading pending installation action %ws; ignoring it. hr=0x%x`
- `0x180084082`: `Completed reading %u pending installs.`
- `0x180083937`: `Beginning reading pending installs.`
- `0x18008393e`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x180083aec`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x180083eb5`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x180084089`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x18008409e`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x180084097`: `Failed to reading any pending installs. The key may not exist or there may be no pending installs.`
- `0x180083992`: `OfflinePrinterExtensions`
- `0x180083a98`: `AppPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r14
  _QWORD *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r8
  char **v7; // rbx
  volatile signed __int32 *v8; // rsi
  __int64 v9; // r13
  char *v10; // rsi
  struct _GUID *v11; // r8
  Win32Adapters::Guid *v12; // rcx
  struct _GUID *v13; // r8
  Win32Adapters::Guid *v14; // rcx
  struct _GUID *v15; // r8
  Win32Adapters::Guid *v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r8
  __int128 *v19; // rcx
  int v20; // r12d
  __int64 v21; // rcx
  __int64 v22; // rcx
  char v23; // al
  _QWORD *v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // r13
  _QWORD *v27; // rax
  _QWORD *v28; // rcx
  _QWORD *v29; // rax
  volatile signed __int32 *v30; // rsi
  volatile signed __int32 *v31; // rsi
  volatile signed __int32 *v32; // rsi
  volatile signed __int32 *v33; // rsi
  volatile signed __int32 *v34; // rsi
  volatile signed __int32 *v35; // rsi
  unsigned int v37; // [rsp+20h] [rbp-278h]
  int v38; // [rsp+20h] [rbp-278h]
  int v39; // [rsp+28h] [rbp-270h]
  __int64 v41; // [rsp+38h] [rbp-260h]
  HKEY *v42; // [rsp+40h] [rbp-258h] BYREF
  volatile signed __int32 *v43; // [rsp+48h] [rbp-250h]
  __int64 v44; // [rsp+50h] [rbp-248h] BYREF
  volatile signed __int32 *v45; // [rsp+58h] [rbp-240h]
  _QWORD *v46; // [rsp+60h] [rbp-238h] BYREF
  __int64 v47; // [rsp+68h] [rbp-230h]
  __int64 v48; // [rsp+70h] [rbp-228h] BYREF
  volatile signed __int32 *v49; // [rsp+78h] [rbp-220h]
  __int128 v50; // [rsp+80h] [rbp-218h] BYREF
  __int64 v51; // [rsp+90h] [rbp-208h]
  __int64 v52; // [rsp+98h] [rbp-200h]
  __int64 v53; // [rsp+A0h] [rbp-1F8h]
  const hr_error *v54; // [rsp+A8h] [rbp-1F0h] BYREF
  const PrintCore::WindowsError *v55[2]; // [rsp+B0h] [rbp-1E8h] BYREF
  const hr_error *v56; // [rsp+C0h] [rbp-1D8h] BYREF
  const PrintCore::WindowsError *v57[3]; // [rsp+C8h] [rbp-1D0h] BYREF
  char v58[32]; // [rsp+E0h] [rbp-1B8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+100h] [rbp-198h] BYREF
  _BYTE v60[32]; // [rsp+120h] [rbp-178h] BYREF
  _BYTE v61[32]; // [rsp+140h] [rbp-158h] BYREF
  __int128 v62; // [rsp+160h] [rbp-138h] BYREF
  __int64 v63; // [rsp+170h] [rbp-128h]
  unsigned __int64 v64; // [rsp+178h] [rbp-120h]
  __int128 v65; // [rsp+180h] [rbp-118h] BYREF
  __int64 v66; // [rsp+190h] [rbp-108h]
  __int64 v67; // [rsp+198h] [rbp-100h]
  __int128 v68; // [rsp+1A0h] [rbp-F8h] BYREF
  __int64 v69; // [rsp+1B0h] [rbp-E8h]
  __int64 v70; // [rsp+1B8h] [rbp-E0h]
  void *Src[4]; // [rsp+1C0h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+1E0h] [rbp-B8h] BYREF
  char *v73; // [rsp+1E8h] [rbp-B0h] BYREF
  char *v74; // [rsp+208h] [rbp-90h] BYREF
  char *v75; // [rsp+228h] [rbp-70h] BYREF
  int v76; // [rsp+248h] [rbp-50h]

  v53 = -2;
  v2 = a2;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
    L"Beginning reading pending installs.");
  *v2 = 0;
  v2[1] = 0;
  v4 = operator new(0x20u);
  *v4 = v4;
  v4[1] = v4;
  *v2 = v4;
  v39 = 1;
  std::wstring::wstring((__int64)Src, a1);
  std::wstring::append(Src, L"\\", v5);
  std::wstring::append(Src, L"OfflinePrinterExtensions", v6);
  v7 = (char **)std::wstring::wstring((__int64)v58, (__int64)Src);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v50, &Filename, 0);
  Win32Adapters::Registry::CKeyEnumerator::CKeyEnumerator(&hKey, (char **)&v50, v7);
  if ( !hKey || !v76 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
      L"Failed to reading any pending installs. The key may not exist or there may be no pending installs.");
    goto LABEL_71;
  }
  while ( 1 )
  {
    Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey((__int64)&hKey, &v42);
    if ( !v42 )
      break;
    try
    {
      v65 = 0;
      v66 = 0;
      v67 = 7;
      LOWORD(v65) = 0;
      v62 = 0;
      v63 = 0;
      v64 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v62, L"AppPath", 7u);
      Win32Adapters::Registry::RegQueryValueW(v42, (const WCHAR *)&v62, 1, (__int64)&v65);
      std::wstring::~wstring((char **)&v62);
    }
    catch ( std::bad_alloc )
    {
      v38 = -2147024882;
      goto LABEL_5;
    }
    catch ( const hr_error *v54 )
    {
      v38 = *((_DWORD *)v54 + 6);
      goto LABEL_10;
    }
    catch ( const PrintCore::WindowsError *v55 )
    {
      v38 = *((_DWORD *)v55[0] + 6);
LABEL_10:
      if ( v38 >= 0 )
      {
        v2 = a2;
        goto LABEL_12;
      }
LABEL_5:
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
        L"Failed reading AppPath value. hr=0x%x",
        (unsigned int)v38);
      std::wstring::~wstring((char **)&v65);
      v8 = v43;
      if ( v43 )
      {
        if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
          if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        }
      }
      v2 = a2;
      continue;
    }
    catch ( std::exception )
    {
      v38 = -2147467259;
      goto LABEL_5;
    }
    catch ( ... )
    {
      v38 = -2147418113;
      goto LABEL_5;
    }
LABEL_12:
    Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey((__int64)v42, &v44);
    if ( v44 )
    {
      while ( 1 )
      {
        Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(v44, &v48);
        v9 = v48;
        if ( !v48 )
        {
          v31 = v49;
          if ( v49 )
          {
            if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
              if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
            }
          }
          v32 = v45;
          if ( v45 )
          {
            if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
              if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
            }
          }
          goto LABEL_12;
        }
        if ( *(_QWORD *)(v48 + 96) <= 7u )
          v41 = v48 + 72;
        else
          v41 = *(_QWORD *)(v48 + 72);
        try
        {
          v37 = 0;
          v10 = (char *)operator new(0xC0u);
          v55[1] = (const PrintCore::WindowsError *)v10;
          *((_DWORD *)v10 + 2) = 1;
          *((_DWORD *)v10 + 3) = 1;
          *(_QWORD *)v10 = &std::_Ref_count_obj2<Print::Driver::PrinterExtensionInstallAction>::`vftable';
          memset_0(v10 + 16, 0, 0xB0u);
          Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo((GUID *)v10 + 1);
          *((_OWORD *)v10 + 9) = 0;
          *((_QWORD *)v10 + 20) = 0;
          *((_QWORD *)v10 + 21) = 7;
          *((_WORD *)v10 + 72) = 0;
          v39 |= 2u;
          v57[1] = (const PrintCore::WindowsError *)(v10 + 16);
          v57[2] = (const PrintCore::WindowsError *)v10;
          v12 = (Win32Adapters::Guid *)(v42 + 5);
          if ( (unsigned __int64)v42[8] > 7 )
            v12 = *(Win32Adapters::Guid **)v12;
          Win32Adapters::Guid::GuidFromString(v12, (UUID *)v10 + 2, v11);
          v14 = (Win32Adapters::Guid *)(v44 + 40);
          if ( *(_QWORD *)(v44 + 64) > 7u )
            v14 = *(Win32Adapters::Guid **)v14;
          Win32Adapters::Guid::GuidFromString(v14, (UUID *)v10 + 3, v13);
          v16 = (Win32Adapters::Guid *)(v9 + 40);
          if ( *(_QWORD *)(v9 + 64) > 7u )
            v16 = *(Win32Adapters::Guid **)v16;
          Win32Adapters::Guid::GuidFromString(v16, (UUID *)v10 + 4, v15);
          std::wstring::operator=((__int64)(v10 + 80), &v65, v17);
          std::wstring::operator=((__int64)(v10 + 144), (_QWORD *)(v9 + 72), v18);
          v68 = 0;
          v69 = 0;
          v70 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v68, &Filename, 0);
          v62 = 0;
          v63 = 0;
          v64 = 7;
          LOWORD(v62) = 0;
          Win32Adapters::Registry::RegQueryValueW((HKEY *)v9, (const WCHAR *)&v68, 1, (__int64)&v62);
          if ( !v63 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, -2147024883);
            throw (hr_error *)pExceptionObject;
          }
          v19 = &v62;
          if ( v64 > 7 )
            v19 = (__int128 *)v62;
          v20 = _o__wtol(v19);
          if ( *(_DWORD *)_o__errno(v21) == 34 || *(_DWORD *)_o__errno(v22) == 22 )
          {
            hr_error::hr_error((hr_error *)v61, -2147024883);
            throw (hr_error *)v61;
          }
          std::wstring::~wstring((char **)&v62);
          std::wstring::~wstring((char **)&v68);
          if ( v20 )
          {
            if ( v20 != 1 )
            {
              if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  0xAu,
                  (const GUID *)WPP_ab1f4819a6c43c283527ec690d8b9fc7_Traceguids,
                  -2147024883);
              }
              hr_error::hr_error((hr_error *)v60, -2147024883);
              throw (hr_error *)v60;
            }
            v23 = 1;
          }
          else
          {
            v23 = 0;
          }
          v10[176] = v23;
          v24 = v10 + 180;
          if ( v10 != (char *)-180LL )
          {
            v25 = (_QWORD *)(v9 + 112);
            if ( v9 != -112 )
            {
              *v24 = *v25;
LABEL_37:
              if ( v2[1] == 0x7FFFFFFFFFFFFFFLL )
                std::_Xlength_error("list too long");
              v26 = *v2;
              v46 = v2;
              v47 = 0;
              v27 = operator new(0x20u);
              v28 = v27;
              v27[2] = 0;
              v27[3] = 0;
              if ( v10 )
                _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
              v27[2] = v10 + 16;
              v27[3] = v10;
              ++v2[1];
              v29 = *(_QWORD **)(v26 + 8);
              *v28 = v26;
              v28[1] = v29;
              v47 = 0;
              *(_QWORD *)(v26 + 8) = v28;
              *v29 = v28;
              std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>((__int64)&v46);
              if ( v10 )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)v10 + 2) )
                {
                  (**(void (__fastcall ***)(void *))v10)(v10);
                  if ( !_InterlockedDecrement((volatile signed __int32 *)v10 + 3) )
                    (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
                }
              }
              goto LABEL_96;
            }
            *v24 = v25;
          }
          *(_DWORD *)_o__errno(v24) = 22;
          invalid_parameter_noinfo();
          goto LABEL_37;
        }
        catch ( std::bad_alloc )
        {
          v37 = -2147024882;
          v2 = a2;
        }
        catch ( const hr_error *v56 )
        {
          v37 = *((_DWORD *)v56 + 6);
          v2 = a2;
        }
        catch ( const PrintCore::WindowsError *v57 )
        {
          v37 = *((_DWORD *)v57[0] + 6);
          v2 = a2;
        }
        catch ( std::exception )
        {
          v37 = -2147467259;
          v2 = a2;
        }
        catch ( ... )
        {
          v37 = -2147418113;
          v2 = a2;
        }
LABEL_96:
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
          L"Failure reading pending installation action %ws; ignoring it. hr=0x%x",
          v41,
          v37);
        v30 = v49;
        if ( v49 && _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
    }
    v33 = v45;
    if ( v45 )
    {
      if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    std::wstring::~wstring((char **)&v65);
    v34 = v43;
    if ( v43 )
    {
      if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
        if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
  }
  v35 = v43;
  if ( v43 )
  {
    if ( !_InterlockedDecrement(v43 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
      if ( !_InterlockedDecrement(v35 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
    }
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
    L"Completed reading %u pending installs.",
    v2[1]);
LABEL_71:
  std::wstring::~wstring(&v75);
  std::wstring::~wstring(&v74);
  std::wstring::~wstring(&v73);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  std::wstring::~wstring((char **)Src);
  return v2;
}

```

## disassembly

```asm
0x1800838ec  mov     rax, rsp
0x1800838ef  push    rdi
0x1800838f0  push    r12
0x1800838f2  push    r13
0x1800838f4  push    r14
0x1800838f6  push    r15
0x1800838f8  sub     rsp, 270h
0x1800838ff  mov     qword ptr [rax-1F8h], 0FFFFFFFFFFFFFFFEh
0x18008390a  mov     [rax+18h], rbx
0x18008390e  mov     [rax+20h], rsi
0x180083912  mov     rax, cs:__security_cookie
0x180083919  xor     rax, rsp
0x18008391c  mov     [rsp+298h+var_38], rax
0x180083924  mov     r14, rdx
0x180083927  mov     rbx, rcx
0x18008392a  mov     [rsp+298h+var_268], rdx
0x18008392f  mov     [rsp+298h+var_270], 1
0x180083937  lea     rdx, aBeginningReadi; "Beginning reading pending installs."
0x18008393e  lea     rcx, aPrintDriverPri; "Print::Driver::PrinterExtensionRegistra"...
0x180083945  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008394a  xor     edi, edi
0x18008394c  mov     [r14], rdi
0x18008394f  mov     [r14+8], rdi
0x180083953  lea     ecx, [rdi+20h]; Size
0x180083956  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008395b  mov     [rax], rax
0x18008395e  mov     [rax+8], rax
0x180083962  mov     [r14], rax
0x180083965  mov     [rsp+298h+var_270], 1
0x18008396d  mov     rdx, rbx
0x180083970  lea     rcx, [rsp+298h+Src]
0x180083978  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008397d  nop
0x18008397e  lea     rdx, SubBlock; "\\"
0x180083985  lea     rcx, [rsp+298h+Src]; Src
0x18008398d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180083992  lea     rdx, aOfflineprinter; "OfflinePrinterExtensions"
0x180083999  lea     rcx, [rsp+298h+Src]; Src
0x1800839a1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800839a6  lea     rax, [rsp+298h+var_1B8]
0x1800839ae  mov     [rsp+298h+var_260], rax
0x1800839b3  lea     rdx, [rsp+298h+Src]
0x1800839bb  lea     rcx, [rsp+298h+var_1B8]
0x1800839c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800839c8  mov     rbx, rax
0x1800839cb  xorps   xmm0, xmm0
0x1800839ce  movups  [rsp+298h+var_218], xmm0
0x1800839d6  mov     [rsp+298h+var_208], rdi
0x1800839de  mov     [rsp+298h+var_200], rdi
0x1800839e6  xor     r8d, r8d
0x1800839e9  lea     rdx, Filename
0x1800839f0  lea     rcx, [rsp+298h+var_218]
0x1800839f8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800839fd  nop
0x1800839fe  mov     r8, rbx
0x180083a01  lea     rdx, [rsp+298h+var_218]
0x180083a09  lea     rcx, [rsp+298h+hKey]; PHKEY
0x180083a11  call    ??0CKeyEnumerator@Registry@Win32Adapters@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Win32Adapters::Registry::CKeyEnumerator::CKeyEnumerator(std::wstring,std::wstring)
0x180083a16  nop
0x180083a17  cmp     [rsp+298h+hKey], rdi
0x180083a1f  jz      loc_180084097
0x180083a25  cmp     [rsp+298h+var_50], edi
0x180083a2c  jz      loc_180084097
0x180083a32  or      ebx, 0FFFFFFFFh
0x180083a35  lea     rdx, [rsp+298h+var_258]
0x180083a3a  lea     rcx, [rsp+298h+hKey]
0x180083a42  call    ?GetNextSubKey@CKeyEnumerator@Registry@Win32Adapters@@QEAA?AV?$shared_ptr@VCKeyEnumerator@Registry@Win32Adapters@@@std@@XZ; Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(void)
0x180083a47  nop
0x180083a48  cmp     [rsp+298h+var_258], rdi
0x180083a4d  jz      loc_180084041
0x180083a53  xorps   xmm0, xmm0
0x180083a56  movups  [rsp+298h+var_118], xmm0
0x180083a5e  mov     [rsp+298h+var_108], rdi
0x180083a66  mov     [rsp+298h+var_100], 7
0x180083a72  mov     word ptr [rsp+298h+var_118], di
0x180083a7a  movups  [rsp+298h+var_138], xmm0
0x180083a82  mov     [rsp+298h+var_128], rdi
0x180083a8a  mov     [rsp+298h+var_120], rdi
0x180083a92  mov     r8d, 7
0x180083a98  lea     rdx, aApppath; "AppPath"
0x180083a9f  lea     rcx, [rsp+298h+var_138]
0x180083aa7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180083aac  nop
0x180083aad  lea     r9, [rsp+298h+var_118]
0x180083ab5  mov     r8b, 1
0x180083ab8  lea     rdx, [rsp+298h+var_138]
0x180083ac0  mov     rcx, [rsp+298h+var_258]
0x180083ac5  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV45@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,std::wstring &)
0x180083aca  nop
0x180083acb  lea     rcx, [rsp+298h+var_138]
0x180083ad3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083ad8  nop
0x180083ad9  jmp     loc_180083B61
0x180083ade  xor     edi, edi
0x180083ae0  mov     r8d, [rsp+298h+var_278]
0x180083ae5  lea     rdx, aFailedReadingA; "Failed reading AppPath value. hr=0x%x"
0x180083aec  lea     rcx, aPrintDriverPri; "Print::Driver::PrinterExtensionRegistra"...
0x180083af3  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180083af8  nop
0x180083af9  lea     rcx, [rsp+298h+var_118]
0x180083b01  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083b06  nop
0x180083b07  mov     rsi, [rsp+298h+var_250]
0x180083b0c  or      ebx, 0FFFFFFFFh
0x180083b0f  test    rsi, rsi
0x180083b12  jz      short loc_180083B47
0x180083b14  mov     eax, ebx
0x180083b16  lock xadd [rsi+8], eax
0x180083b1b  add     eax, ebx
0x180083b1d  jnz     short loc_180083B47
0x180083b1f  mov     rax, [rsi]
0x180083b22  mov     rcx, rsi
0x180083b25  mov     rax, [rax]
0x180083b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b2d  mov     eax, ebx
0x180083b2f  lock xadd [rsi+0Ch], eax
0x180083b34  add     eax, ebx
0x180083b36  jnz     short loc_180083B47
0x180083b38  mov     rax, [rsi]
0x180083b3b  mov     rcx, rsi
0x180083b3e  mov     rax, [rax+8]
0x180083b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083b47  mov     r14, [rsp+298h+var_268]
0x180083b4c  jmp     loc_180083A35
0x180083b51  xor     edi, edi
0x180083b53  cmp     [rsp+298h+var_278], edi
0x180083b57  jl      short loc_180083AE0
0x180083b59  or      ebx, 0FFFFFFFFh
0x180083b5c  mov     r14, [rsp+298h+var_268]
0x180083b61  lea     rdx, [rsp+298h+var_248]
0x180083b66  mov     rcx, [rsp+298h+var_258]
0x180083b6b  call    ?GetNextSubKey@CKeyEnumerator@Registry@Win32Adapters@@QEAA?AV?$shared_ptr@VCKeyEnumerator@Registry@Win32Adapters@@@std@@XZ; Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(void)
0x180083b70  nop
0x180083b71  cmp     [rsp+298h+var_248], rdi
0x180083b76  jz      loc_180083FA2
0x180083b7c  lea     rdx, [rsp+298h+var_228]
0x180083b81  mov     rcx, [rsp+298h+var_248]
0x180083b86  call    ?GetNextSubKey@CKeyEnumerator@Registry@Win32Adapters@@QEAA?AV?$shared_ptr@VCKeyEnumerator@Registry@Win32Adapters@@@std@@XZ; Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(void)
0x180083b8b  nop
0x180083b8c  mov     r13, [rsp+298h+var_228]
0x180083b91  test    r13, r13
0x180083b94  jz      loc_180083F16
0x180083b9a  lea     r12, [r13+48h]
0x180083b9e  cmp     qword ptr [r12+18h], 7
0x180083ba4  jbe     short loc_180083BB1
0x180083ba6  mov     rax, [r12]
0x180083baa  mov     [rsp+298h+var_260], rax
0x180083baf  jmp     short loc_180083BB6
0x180083bb1  mov     [rsp+298h+var_260], r12
0x180083bb6  mov     [rsp+298h+var_278], edi
0x180083bba  mov     ecx, 0C0h; Size
0x180083bbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083bc4  mov     rsi, rax
0x180083bc7  mov     [rsp+298h+var_1E0], rax
0x180083bcf  mov     dword ptr [rax+8], 1
0x180083bd6  mov     dword ptr [rax+0Ch], 1
0x180083bdd  lea     rax, ??_7?$_Ref_count_obj2@VPrinterExtensionInstallAction@Driver@Print@@@std@@6B@; const std::_Ref_count_obj2<Print::Driver::PrinterExtensionInstallAction>::`vftable'
0x180083be4  mov     [rsi], rax
0x180083be7  lea     r15, [rsi+10h]
0x180083beb  xor     edx, edx; Val
0x180083bed  mov     r8d, 0B0h; Size
0x180083bf3  mov     rcx, r15; void *
0x180083bf6  call    memset_0
0x180083bfb  mov     rcx, r15; this
0x180083bfe  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x180083c03  xorps   xmm0, xmm0
0x180083c06  movups  xmmword ptr [r15+80h], xmm0
0x180083c0e  mov     [r15+90h], rdi
0x180083c15  mov     qword ptr [r15+98h], 7
0x180083c20  mov     [r15+80h], di
0x180083c28  or      [rsp+298h+var_270], 2
0x180083c2d  mov     [rsp+298h+var_1C8], r15
0x180083c35  mov     [rsp+298h+var_1C0], rsi
0x180083c3d  lea     rdx, [r15+10h]; unsigned __int16 *
0x180083c41  mov     rcx, [rsp+298h+var_258]
0x180083c46  add     rcx, 28h ; '('
0x180083c4a  cmp     qword ptr [rcx+18h], 7
0x180083c4f  jbe     short loc_180083C54
0x180083c51  mov     rcx, [rcx]; this
0x180083c54  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180083c59  lea     rdx, [r15+20h]; unsigned __int16 *
0x180083c5d  mov     rcx, [rsp+298h+var_248]
0x180083c62  add     rcx, 28h ; '('
0x180083c66  cmp     qword ptr [rcx+18h], 7
0x180083c6b  jbe     short loc_180083C70
0x180083c6d  mov     rcx, [rcx]; this
0x180083c70  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180083c75  lea     rdx, [r15+30h]; unsigned __int16 *
0x180083c79  lea     rcx, [r13+28h]
0x180083c7d  cmp     qword ptr [rcx+18h], 7
0x180083c82  jbe     short loc_180083C87
0x180083c84  mov     rcx, [rcx]; this
0x180083c87  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180083c8c  lea     rcx, [r15+40h]
0x180083c90  lea     rdx, [rsp+298h+var_118]
0x180083c98  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180083c9d  lea     rcx, [r15+80h]
0x180083ca4  mov     rdx, r12
0x180083ca7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180083cac  xorps   xmm0, xmm0
0x180083caf  movups  [rsp+298h+var_F8], xmm0
0x180083cb7  mov     [rsp+298h+var_E8], rdi
0x180083cbf  mov     [rsp+298h+var_E0], rdi
0x180083cc7  xor     r8d, r8d
0x180083cca  lea     rdx, Filename
0x180083cd1  lea     rcx, [rsp+298h+var_F8]
0x180083cd9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180083cde  nop
0x180083cdf  xorps   xmm0, xmm0
0x180083ce2  movups  [rsp+298h+var_138], xmm0
0x180083cea  mov     [rsp+298h+var_128], rdi
0x180083cf2  mov     [rsp+298h+var_120], 7
0x180083cfe  mov     word ptr [rsp+298h+var_138], di
0x180083d06  lea     r9, [rsp+298h+var_138]
0x180083d0e  mov     r8b, 1
0x180083d11  lea     rdx, [rsp+298h+var_F8]
0x180083d19  mov     rcx, r13
0x180083d1c  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV45@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,std::wstring &)
0x180083d21  cmp     [rsp+298h+var_128], rdi
0x180083d29  jz      loc_180084132
0x180083d2f  lea     rcx, [rsp+298h+var_138]
0x180083d37  cmp     [rsp+298h+var_120], 7
0x180083d40  cmova   rcx, qword ptr [rsp+298h+var_138]
0x180083d49  call    cs:__imp__o__wtol
0x180083d50  nop     dword ptr [rax+rax+00h]
0x180083d55  mov     r12d, eax
0x180083d58  call    cs:__imp__o__errno
0x180083d5f  nop     dword ptr [rax+rax+00h]
0x180083d64  cmp     dword ptr [rax], 22h ; '"'
0x180083d67  jz      loc_1800841C0
0x180083d6d  call    cs:__imp__o__errno
0x180083d74  nop     dword ptr [rax+rax+00h]
0x180083d79  cmp     dword ptr [rax], 16h
0x180083d7c  jz      loc_1800841C0
0x180083d82  lea     rcx, [rsp+298h+var_138]
0x180083d8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083d8f  nop
0x180083d90  lea     rcx, [rsp+298h+var_F8]
0x180083d98  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180083d9d  test    r12d, r12d
0x180083da0  jnz     short loc_180083DA7
0x180083da2  mov     al, dil
0x180083da5  jmp     short loc_180083DB4
0x180083da7  cmp     r12d, 1
0x180083dab  jnz     loc_180084165
0x180083db1  mov     al, r12b
0x180083db4  mov     [r15+0A0h], al
0x180083dbb  lea     rcx, [r15+0A4h]
0x180083dc2  test    rcx, rcx
0x180083dc5  jz      short loc_180083DDB
0x180083dc7  lea     rax, [r13+70h]
0x180083dcb  test    rax, rax
0x180083dce  jz      short loc_180083DD8
0x180083dd0  mov     rax, [rax]
0x180083dd3  mov     [rcx], rax
0x180083dd6  jmp     short loc_180083DF2
0x180083dd8  mov     [rcx], rax
0x180083ddb  call    cs:__imp__o__errno
0x180083de2  nop     dword ptr [rax+rax+00h]
0x180083de7  mov     dword ptr [rax], 16h
0x180083ded  call    _invalid_parameter_noinfo
0x180083df2  mov     rax, 7FFFFFFFFFFFFFFh
0x180083dfc  cmp     [r14+8], rax
0x180083e00  jz      loc_180084159
0x180083e06  mov     r13, [r14]
0x180083e09  mov     [rsp+298h+var_238], r14
0x180083e0e  mov     [rsp+298h+var_230], rdi
0x180083e13  mov     ecx, 20h ; ' '; Size
0x180083e18  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180083e1d  mov     rcx, rax
0x180083e20  mov     [rax+10h], rdi
0x180083e24  mov     [rax+18h], rdi
0x180083e28  test    rsi, rsi
0x180083e2b  jz      short loc_180083E31
0x180083e2d  lock inc dword ptr [rsi+8]
0x180083e31  mov     [rax+10h], r15
0x180083e35  mov     [rax+18h], rsi
0x180083e39  inc     qword ptr [r14+8]
0x180083e3d  mov     rax, [r13+8]
0x180083e41  mov     [rcx], r13
0x180083e44  mov     [rcx+8], rax
0x180083e48  mov     [rsp+298h+var_230], rdi
0x180083e4d  mov     [r13+8], rcx
0x180083e51  mov     [rax], rcx
0x180083e54  lea     rcx, [rsp+298h+var_238]
0x180083e59  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>(void)
0x180083e5e  nop
0x180083e5f  test    rsi, rsi
0x180083e62  jz      short loc_180083E98
0x180083e64  mov     eax, ebx
0x180083e66  lock xadd [rsi+8], eax
0x180083e6b  add     eax, ebx
0x180083e6d  jnz     short loc_180083E98
0x180083e6f  mov     rax, [rsi]
0x180083e72  mov     rcx, rsi
0x180083e75  mov     rax, [rax]
0x180083e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e7d  mov     eax, ebx
0x180083e7f  lock xadd [rsi+0Ch], eax
0x180083e84  add     eax, ebx
  ... truncated ...
```
