# Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations(void)

- ea: `0x18008091c`
- end: `0x1800811f9`
- name: `?GetPendingInstallations@PrinterExtensionRegistrarService@Driver@Print@@AEAA?AV?$list@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@V?$allocator@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@@2@@std@@XZ`
- size: `2269`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800827f0`

## callees

- `0x1800032e0`
- `0x180003b00`
- `0x18000425e`
- `0x180004418`
- `0x180004424`
- `0x18000da28`
- `0x18000e23c`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018a28`
- `0x180018bbc`
- `0x180034488`
- `0x180035cdc`
- `0x1800368e8`
- `0x18003fb04`
- `0x18007edc4`
- `0x18007f028`
- `0x1800804a8`
- `0x18008091c`
- `0x1800e5a00`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180080d79`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180080d79`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180080d82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180080d91`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180080df9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180080d82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180080d91`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180080df9`
- `ADVAPI32!RegCloseKey` at `0x1800810f7`
- `ADVAPI32!RegCloseKey` at `0x1800810f7`

## string_xrefs

- `0x180080b15`: `Failed reading AppPath value. hr=0x%x`
- `0x180080ec6`: `Failure reading pending installation action %ws; ignoring it. hr=0x%x`
- `0x18008109a`: `Completed reading %u pending installs.`
- `0x180080967`: `Beginning reading pending installs.`
- `0x18008096e`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x180080b1c`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x180080ecd`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x1800810a1`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x1800810b6`: `Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations`
- `0x1800810af`: `Failed to reading any pending installs. The key may not exist or there may be no pending installs.`
- `0x1800809c2`: `OfflinePrinterExtensions`
- `0x180080ac8`: `AppPath`

## pseudocode

```c
_QWORD *__fastcall Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r14
  _QWORD *v4; // rax
  __int64 v5; // r8
  volatile signed __int32 *v6; // rsi
  _QWORD *v7; // r13
  char *v8; // rsi
  struct _GUID *v9; // r8
  Win32Adapters::Guid *v10; // rcx
  struct _GUID *v11; // r8
  Win32Adapters::Guid *v12; // rcx
  struct _GUID *v13; // r8
  Win32Adapters::Guid *v14; // rcx
  __int64 v15; // r8
  __int128 *v16; // rcx
  int v17; // r12d
  char v18; // al
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // r13
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // rax
  volatile signed __int32 *v25; // rsi
  volatile signed __int32 *v26; // rsi
  volatile signed __int32 *v27; // rsi
  volatile signed __int32 *v28; // rsi
  volatile signed __int32 *v29; // rsi
  volatile signed __int32 *v30; // rsi
  unsigned int v32; // [rsp+20h] [rbp-278h]
  int v33; // [rsp+20h] [rbp-278h]
  int v34; // [rsp+28h] [rbp-270h]
  _QWORD *v36; // [rsp+38h] [rbp-260h]
  __int64 v37; // [rsp+40h] [rbp-258h] BYREF
  volatile signed __int32 *v38; // [rsp+48h] [rbp-250h]
  __int64 v39; // [rsp+50h] [rbp-248h] BYREF
  volatile signed __int32 *v40; // [rsp+58h] [rbp-240h]
  _QWORD *v41; // [rsp+60h] [rbp-238h] BYREF
  __int64 v42; // [rsp+68h] [rbp-230h]
  _QWORD *v43; // [rsp+70h] [rbp-228h] BYREF
  volatile signed __int32 *v44; // [rsp+78h] [rbp-220h]
  __int128 v45; // [rsp+80h] [rbp-218h] BYREF
  __int64 v46; // [rsp+90h] [rbp-208h]
  __int64 v47; // [rsp+98h] [rbp-200h]
  __int64 v48; // [rsp+A0h] [rbp-1F8h]
  const hr_error *v49; // [rsp+A8h] [rbp-1F0h] BYREF
  const PrintCore::WindowsError *v50[2]; // [rsp+B0h] [rbp-1E8h] BYREF
  const hr_error *v51; // [rsp+C0h] [rbp-1D8h] BYREF
  const PrintCore::WindowsError *v52[3]; // [rsp+C8h] [rbp-1D0h] BYREF
  char v53[32]; // [rsp+E0h] [rbp-1B8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+100h] [rbp-198h] BYREF
  _BYTE v55[32]; // [rsp+120h] [rbp-178h] BYREF
  _BYTE v56[32]; // [rsp+140h] [rbp-158h] BYREF
  __int128 v57; // [rsp+160h] [rbp-138h] BYREF
  __int64 v58; // [rsp+170h] [rbp-128h]
  unsigned __int64 v59; // [rsp+178h] [rbp-120h]
  __int128 v60; // [rsp+180h] [rbp-118h] BYREF
  __int64 v61; // [rsp+190h] [rbp-108h]
  __int64 v62; // [rsp+198h] [rbp-100h]
  __int128 v63; // [rsp+1A0h] [rbp-F8h] BYREF
  __int64 v64; // [rsp+1B0h] [rbp-E8h]
  __int64 v65; // [rsp+1B8h] [rbp-E0h]
  _BYTE Src[32]; // [rsp+1C0h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+1E0h] [rbp-B8h] BYREF
  char v68[32]; // [rsp+1E8h] [rbp-B0h] BYREF
  char v69[32]; // [rsp+208h] [rbp-90h] BYREF
  char v70[32]; // [rsp+228h] [rbp-70h] BYREF
  int v71; // [rsp+248h] [rbp-50h]

  v48 = -2;
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
  v34 = 1;
  std::wstring::wstring(Src, a1);
  std::wstring::append(Src, (void *)L"\\");
  std::wstring::append(Src, L"OfflinePrinterExtensions");
  std::wstring::wstring(v53, Src);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v45, &Filename);
  Win32Adapters::Registry::CKeyEnumerator::CKeyEnumerator(&hKey);
  if ( !hKey || !v71 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
      "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
      L"Failed to reading any pending installs. The key may not exist or there may be no pending installs.");
    goto LABEL_71;
  }
  while ( 1 )
  {
    Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(&hKey, &v37);
    if ( !v37 )
      break;
    try
    {
      v60 = 0;
      v61 = 0;
      v62 = 7;
      LOWORD(v60) = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v57, L"AppPath");
      LOBYTE(v5) = 1;
      Win32Adapters::Registry::RegQueryValueW(v37, &v57, v5, &v60);
      std::wstring::~wstring(&v57);
    }
    catch ( std::bad_alloc )
    {
      v33 = -2147024882;
      goto LABEL_5;
    }
    catch ( const hr_error *v49 )
    {
      v33 = *((_DWORD *)v49 + 6);
      goto LABEL_10;
    }
    catch ( const PrintCore::WindowsError *v50 )
    {
      v33 = *((_DWORD *)v50[0] + 6);
LABEL_10:
      if ( v33 >= 0 )
      {
        v2 = a2;
        goto LABEL_12;
      }
LABEL_5:
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
        "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
        L"Failed reading AppPath value. hr=0x%x",
        (unsigned int)v33);
      std::wstring::~wstring(&v60);
      v6 = v38;
      if ( v38 )
      {
        if ( !_InterlockedDecrement(v38 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( !_InterlockedDecrement(v6 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      v2 = a2;
      continue;
    }
    catch ( std::exception )
    {
      v33 = -2147467259;
      goto LABEL_5;
    }
    catch ( ... )
    {
      v33 = -2147418113;
      goto LABEL_5;
    }
LABEL_12:
    Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(v37, &v39);
    if ( v39 )
    {
      while ( 1 )
      {
        Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(v39, &v43);
        v7 = v43;
        if ( !v43 )
        {
          v26 = v44;
          if ( v44 )
          {
            if ( !_InterlockedDecrement(v44 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
              if ( !_InterlockedDecrement(v26 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
            }
          }
          v27 = v40;
          if ( v40 )
          {
            if ( !_InterlockedDecrement(v40 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
              if ( !_InterlockedDecrement(v27 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
            }
          }
          goto LABEL_12;
        }
        if ( v43[12] <= 7u )
          v36 = v43 + 9;
        else
          v36 = (_QWORD *)v43[9];
        try
        {
          v32 = 0;
          v8 = (char *)operator new(0xC0u);
          v50[1] = (const PrintCore::WindowsError *)v8;
          *((_DWORD *)v8 + 2) = 1;
          *((_DWORD *)v8 + 3) = 1;
          *(_QWORD *)v8 = &std::_Ref_count_obj2<Print::Driver::PrinterExtensionInstallAction>::`vftable';
          memset_0(v8 + 16, 0, 0xB0u);
          Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo((Print::Driver::PrinterExtensionAssociationInfo *)(v8 + 16));
          *((_OWORD *)v8 + 9) = 0;
          *((_QWORD *)v8 + 20) = 0;
          *((_QWORD *)v8 + 21) = 7;
          *((_WORD *)v8 + 72) = 0;
          v34 |= 2u;
          v52[1] = (const PrintCore::WindowsError *)(v8 + 16);
          v52[2] = (const PrintCore::WindowsError *)v8;
          v10 = (Win32Adapters::Guid *)(v37 + 40);
          if ( *(_QWORD *)(v37 + 64) > 7u )
            v10 = *(Win32Adapters::Guid **)v10;
          Win32Adapters::Guid::GuidFromString(v10, (const unsigned __int16 *)v8 + 16, v9);
          v12 = (Win32Adapters::Guid *)(v39 + 40);
          if ( *(_QWORD *)(v39 + 64) > 7u )
            v12 = *(Win32Adapters::Guid **)v12;
          Win32Adapters::Guid::GuidFromString(v12, (const unsigned __int16 *)v8 + 24, v11);
          v14 = (Win32Adapters::Guid *)(v7 + 5);
          if ( v7[8] > 7u )
            v14 = *(Win32Adapters::Guid **)v14;
          Win32Adapters::Guid::GuidFromString(v14, (const unsigned __int16 *)v8 + 32, v13);
          std::wstring::operator=(v8 + 80, &v60);
          std::wstring::operator=(v8 + 144, v7 + 9);
          v63 = 0;
          v64 = 0;
          v65 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v63, &Filename);
          v57 = 0;
          v58 = 0;
          v59 = 7;
          LOWORD(v57) = 0;
          LOBYTE(v15) = 1;
          Win32Adapters::Registry::RegQueryValueW(v7, &v63, v15, &v57);
          if ( !v58 )
          {
            hr_error::hr_error((hr_error *)pExceptionObject, -2147024883);
            throw (hr_error *)pExceptionObject;
          }
          v16 = &v57;
          if ( v59 > 7 )
            v16 = (__int128 *)v57;
          v17 = _o__wtol(v16);
          if ( *(_DWORD *)_o__errno() == 34 || *(_DWORD *)_o__errno() == 22 )
          {
            hr_error::hr_error((hr_error *)v56, -2147024883);
            throw (hr_error *)v56;
          }
          std::wstring::~wstring(&v57);
          std::wstring::~wstring(&v63);
          if ( v17 )
          {
            if ( v17 != 1 )
            {
              if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  10,
                  WPP_ab1f4819a6c43c283527ec690d8b9fc7_Traceguids,
                  2147942413LL);
              }
              hr_error::hr_error((hr_error *)v55, -2147024883);
              throw (hr_error *)v55;
            }
            v18 = 1;
          }
          else
          {
            v18 = 0;
          }
          v8[176] = v18;
          v19 = v8 + 180;
          if ( v8 != (char *)-180LL )
          {
            v20 = v7 + 14;
            if ( v7 != (_QWORD *)-112LL )
            {
              *v19 = *v20;
LABEL_37:
              if ( v2[1] == 0x7FFFFFFFFFFFFFFLL )
                std::_Xlength_error("list too long");
              v21 = *v2;
              v41 = v2;
              v42 = 0;
              v22 = operator new(0x20u);
              v23 = v22;
              v22[2] = 0;
              v22[3] = 0;
              if ( v8 )
                _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
              v22[2] = v8 + 16;
              v22[3] = v8;
              ++v2[1];
              v24 = *(_QWORD **)(v21 + 8);
              *v23 = v21;
              v23[1] = v24;
              v42 = 0;
              *(_QWORD *)(v21 + 8) = v23;
              *v24 = v23;
              std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>(&v41);
              if ( v8 )
              {
                if ( !_InterlockedDecrement((volatile signed __int32 *)v8 + 2) )
                {
                  (**(void (__fastcall ***)(void *))v8)(v8);
                  if ( !_InterlockedDecrement((volatile signed __int32 *)v8 + 3) )
                    (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
                }
              }
              goto LABEL_96;
            }
            *v19 = v20;
          }
          *(_DWORD *)_o__errno() = 22;
          invalid_parameter_noinfo();
          goto LABEL_37;
        }
        catch ( std::bad_alloc )
        {
          v32 = -2147024882;
          v2 = a2;
        }
        catch ( const hr_error *v51 )
        {
          v32 = *((_DWORD *)v51 + 6);
          v2 = a2;
        }
        catch ( const PrintCore::WindowsError *v52 )
        {
          v32 = *((_DWORD *)v52[0] + 6);
          v2 = a2;
        }
        catch ( std::exception )
        {
          v32 = -2147467259;
          v2 = a2;
        }
        catch ( ... )
        {
          v32 = -2147418113;
          v2 = a2;
        }
LABEL_96:
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
          L"Failure reading pending installation action %ws; ignoring it. hr=0x%x",
          v36,
          v32);
        v25 = v44;
        if ( v44 && !_InterlockedDecrement(v44 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( !_InterlockedDecrement(v25 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
    }
    v28 = v40;
    if ( v40 )
    {
      if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
    std::wstring::~wstring(&v60);
    v29 = v38;
    if ( v38 )
    {
      if ( !_InterlockedDecrement(v38 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( !_InterlockedDecrement(v29 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
  }
  v30 = v38;
  if ( v38 )
  {
    if ( !_InterlockedDecrement(v38 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( !_InterlockedDecrement(v30 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "Print::Driver::PrinterExtensionRegistrarService::GetPendingInstallations",
    L"Completed reading %u pending installs.",
    v2[1]);
LABEL_71:
  std::wstring::~wstring(v70);
  std::wstring::~wstring(v69);
  std::wstring::~wstring(v68);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  std::wstring::~wstring(Src);
  return v2;
}

```

## disassembly

```asm
0x18008091c  mov     rax, rsp
0x18008091f  push    rdi
0x180080920  push    r12
0x180080922  push    r13
0x180080924  push    r14
0x180080926  push    r15
0x180080928  sub     rsp, 270h
0x18008092f  mov     qword ptr [rax-1F8h], 0FFFFFFFFFFFFFFFEh
0x18008093a  mov     [rax+18h], rbx
0x18008093e  mov     [rax+20h], rsi
0x180080942  mov     rax, cs:__security_cookie
0x180080949  xor     rax, rsp
0x18008094c  mov     [rsp+298h+var_38], rax
0x180080954  mov     r14, rdx
0x180080957  mov     rbx, rcx
0x18008095a  mov     [rsp+298h+var_268], rdx
0x18008095f  mov     [rsp+298h+var_270], 1
0x180080967  lea     rdx, aBeginningReadi; "Beginning reading pending installs."
0x18008096e  lea     rcx, aPrintDriverPri; "Print::Driver::PrinterExtensionRegistra"...
0x180080975  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008097a  xor     edi, edi
0x18008097c  mov     [r14], rdi
0x18008097f  mov     [r14+8], rdi
0x180080983  lea     ecx, [rdi+20h]; Size
0x180080986  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008098b  mov     [rax], rax
0x18008098e  mov     [rax+8], rax
0x180080992  mov     [r14], rax
0x180080995  mov     [rsp+298h+var_270], 1
0x18008099d  mov     rdx, rbx
0x1800809a0  lea     rcx, [rsp+298h+Src]
0x1800809a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800809ad  nop
0x1800809ae  lea     rdx, SubBlock; "\\"
0x1800809b5  lea     rcx, [rsp+298h+Src]; Src
0x1800809bd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800809c2  lea     rdx, aOfflineprinter; "OfflinePrinterExtensions"
0x1800809c9  lea     rcx, [rsp+298h+Src]; Src
0x1800809d1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800809d6  lea     rax, [rsp+298h+var_1B8]
0x1800809de  mov     [rsp+298h+var_260], rax
0x1800809e3  lea     rdx, [rsp+298h+Src]
0x1800809eb  lea     rcx, [rsp+298h+var_1B8]
0x1800809f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800809f8  mov     rbx, rax
0x1800809fb  xorps   xmm0, xmm0
0x1800809fe  movups  [rsp+298h+var_218], xmm0
0x180080a06  mov     [rsp+298h+var_208], rdi
0x180080a0e  mov     [rsp+298h+var_200], rdi
0x180080a16  xor     r8d, r8d
0x180080a19  lea     rdx, Filename
0x180080a20  lea     rcx, [rsp+298h+var_218]
0x180080a28  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180080a2d  nop
0x180080a2e  mov     r8, rbx
0x180080a31  lea     rdx, [rsp+298h+var_218]
0x180080a39  lea     rcx, [rsp+298h+hKey]; PHKEY
0x180080a41  call    ??0CKeyEnumerator@Registry@Win32Adapters@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Win32Adapters::Registry::CKeyEnumerator::CKeyEnumerator(std::wstring,std::wstring)
0x180080a46  nop
0x180080a47  cmp     [rsp+298h+hKey], rdi
0x180080a4f  jz      loc_1800810AF
0x180080a55  cmp     [rsp+298h+var_50], edi
0x180080a5c  jz      loc_1800810AF
0x180080a62  or      ebx, 0FFFFFFFFh
0x180080a65  lea     rdx, [rsp+298h+var_258]
0x180080a6a  lea     rcx, [rsp+298h+hKey]
0x180080a72  call    ?GetNextSubKey@CKeyEnumerator@Registry@Win32Adapters@@QEAA?AV?$shared_ptr@VCKeyEnumerator@Registry@Win32Adapters@@@std@@XZ; Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(void)
0x180080a77  nop
0x180080a78  cmp     [rsp+298h+var_258], rdi
0x180080a7d  jz      loc_180081059
0x180080a83  xorps   xmm0, xmm0
0x180080a86  movups  [rsp+298h+var_118], xmm0
0x180080a8e  mov     [rsp+298h+var_108], rdi
0x180080a96  mov     [rsp+298h+var_100], 7
0x180080aa2  mov     word ptr [rsp+298h+var_118], di
0x180080aaa  movups  [rsp+298h+var_138], xmm0
0x180080ab2  mov     [rsp+298h+var_128], rdi
0x180080aba  mov     [rsp+298h+var_120], rdi
0x180080ac2  mov     r8d, 7
0x180080ac8  lea     rdx, aApppath; "AppPath"
0x180080acf  lea     rcx, [rsp+298h+var_138]
0x180080ad7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180080adc  nop
0x180080add  lea     r9, [rsp+298h+var_118]
0x180080ae5  mov     r8b, 1
0x180080ae8  lea     rdx, [rsp+298h+var_138]
0x180080af0  mov     rcx, [rsp+298h+var_258]
0x180080af5  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV45@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,std::wstring &)
0x180080afa  nop
0x180080afb  lea     rcx, [rsp+298h+var_138]
0x180080b03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080b08  nop
0x180080b09  jmp     loc_180080B91
0x180080b0e  xor     edi, edi
0x180080b10  mov     r8d, [rsp+298h+var_278]
0x180080b15  lea     rdx, aFailedReadingA; "Failed reading AppPath value. hr=0x%x"
0x180080b1c  lea     rcx, aPrintDriverPri; "Print::Driver::PrinterExtensionRegistra"...
0x180080b23  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180080b28  nop
0x180080b29  lea     rcx, [rsp+298h+var_118]
0x180080b31  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080b36  nop
0x180080b37  mov     rsi, [rsp+298h+var_250]
0x180080b3c  or      ebx, 0FFFFFFFFh
0x180080b3f  test    rsi, rsi
0x180080b42  jz      short loc_180080B77
0x180080b44  mov     eax, ebx
0x180080b46  lock xadd [rsi+8], eax
0x180080b4b  add     eax, ebx
0x180080b4d  jnz     short loc_180080B77
0x180080b4f  mov     rax, [rsi]
0x180080b52  mov     rcx, rsi
0x180080b55  mov     rax, [rax]
0x180080b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b5d  mov     eax, ebx
0x180080b5f  lock xadd [rsi+0Ch], eax
0x180080b64  add     eax, ebx
0x180080b66  jnz     short loc_180080B77
0x180080b68  mov     rax, [rsi]
0x180080b6b  mov     rcx, rsi
0x180080b6e  mov     rax, [rax+8]
0x180080b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080b77  mov     r14, [rsp+298h+var_268]
0x180080b7c  jmp     loc_180080A65
0x180080b81  xor     edi, edi
0x180080b83  cmp     [rsp+298h+var_278], edi
0x180080b87  jl      short loc_180080B10
0x180080b89  or      ebx, 0FFFFFFFFh
0x180080b8c  mov     r14, [rsp+298h+var_268]
0x180080b91  lea     rdx, [rsp+298h+var_248]
0x180080b96  mov     rcx, [rsp+298h+var_258]
0x180080b9b  call    ?GetNextSubKey@CKeyEnumerator@Registry@Win32Adapters@@QEAA?AV?$shared_ptr@VCKeyEnumerator@Registry@Win32Adapters@@@std@@XZ; Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(void)
0x180080ba0  nop
0x180080ba1  cmp     [rsp+298h+var_248], rdi
0x180080ba6  jz      loc_180080FBA
0x180080bac  lea     rdx, [rsp+298h+var_228]
0x180080bb1  mov     rcx, [rsp+298h+var_248]
0x180080bb6  call    ?GetNextSubKey@CKeyEnumerator@Registry@Win32Adapters@@QEAA?AV?$shared_ptr@VCKeyEnumerator@Registry@Win32Adapters@@@std@@XZ; Win32Adapters::Registry::CKeyEnumerator::GetNextSubKey(void)
0x180080bbb  nop
0x180080bbc  mov     r13, [rsp+298h+var_228]
0x180080bc1  test    r13, r13
0x180080bc4  jz      loc_180080F2E
0x180080bca  lea     r12, [r13+48h]
0x180080bce  cmp     qword ptr [r12+18h], 7
0x180080bd4  jbe     short loc_180080BE1
0x180080bd6  mov     rax, [r12]
0x180080bda  mov     [rsp+298h+var_260], rax
0x180080bdf  jmp     short loc_180080BE6
0x180080be1  mov     [rsp+298h+var_260], r12
0x180080be6  mov     [rsp+298h+var_278], edi
0x180080bea  mov     ecx, 0C0h; Size
0x180080bef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080bf4  mov     rsi, rax
0x180080bf7  mov     [rsp+298h+var_1E0], rax
0x180080bff  mov     dword ptr [rax+8], 1
0x180080c06  mov     dword ptr [rax+0Ch], 1
0x180080c0d  lea     rax, ??_7?$_Ref_count_obj2@VPrinterExtensionInstallAction@Driver@Print@@@std@@6B@; const std::_Ref_count_obj2<Print::Driver::PrinterExtensionInstallAction>::`vftable'
0x180080c14  mov     [rsi], rax
0x180080c17  lea     r15, [rsi+10h]
0x180080c1b  xor     edx, edx; Val
0x180080c1d  mov     r8d, 0B0h; Size
0x180080c23  mov     rcx, r15; void *
0x180080c26  call    memset_0
0x180080c2b  mov     rcx, r15; this
0x180080c2e  call    ??0PrinterExtensionAssociationInfo@Driver@Print@@QEAA@XZ; Print::Driver::PrinterExtensionAssociationInfo::PrinterExtensionAssociationInfo(void)
0x180080c33  xorps   xmm0, xmm0
0x180080c36  movups  xmmword ptr [r15+80h], xmm0
0x180080c3e  mov     [r15+90h], rdi
0x180080c45  mov     qword ptr [r15+98h], 7
0x180080c50  mov     [r15+80h], di
0x180080c58  or      [rsp+298h+var_270], 2
0x180080c5d  mov     [rsp+298h+var_1C8], r15
0x180080c65  mov     [rsp+298h+var_1C0], rsi
0x180080c6d  lea     rdx, [r15+10h]; unsigned __int16 *
0x180080c71  mov     rcx, [rsp+298h+var_258]
0x180080c76  add     rcx, 28h ; '('
0x180080c7a  cmp     qword ptr [rcx+18h], 7
0x180080c7f  jbe     short loc_180080C84
0x180080c81  mov     rcx, [rcx]; this
0x180080c84  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180080c89  lea     rdx, [r15+20h]; unsigned __int16 *
0x180080c8d  mov     rcx, [rsp+298h+var_248]
0x180080c92  add     rcx, 28h ; '('
0x180080c96  cmp     qword ptr [rcx+18h], 7
0x180080c9b  jbe     short loc_180080CA0
0x180080c9d  mov     rcx, [rcx]; this
0x180080ca0  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180080ca5  lea     rdx, [r15+30h]; unsigned __int16 *
0x180080ca9  lea     rcx, [r13+28h]
0x180080cad  cmp     qword ptr [rcx+18h], 7
0x180080cb2  jbe     short loc_180080CB7
0x180080cb4  mov     rcx, [rcx]; this
0x180080cb7  call    ?GuidFromString@Guid@Win32Adapters@@YAXPEBGPEAU_GUID@@@Z; Win32Adapters::Guid::GuidFromString(ushort const *,_GUID *)
0x180080cbc  lea     rcx, [r15+40h]
0x180080cc0  lea     rdx, [rsp+298h+var_118]
0x180080cc8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180080ccd  lea     rcx, [r15+80h]
0x180080cd4  mov     rdx, r12
0x180080cd7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180080cdc  xorps   xmm0, xmm0
0x180080cdf  movups  [rsp+298h+var_F8], xmm0
0x180080ce7  mov     [rsp+298h+var_E8], rdi
0x180080cef  mov     [rsp+298h+var_E0], rdi
0x180080cf7  xor     r8d, r8d
0x180080cfa  lea     rdx, Filename
0x180080d01  lea     rcx, [rsp+298h+var_F8]
0x180080d09  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180080d0e  nop
0x180080d0f  xorps   xmm0, xmm0
0x180080d12  movups  [rsp+298h+var_138], xmm0
0x180080d1a  mov     [rsp+298h+var_128], rdi
0x180080d22  mov     [rsp+298h+var_120], 7
0x180080d2e  mov     word ptr [rsp+298h+var_138], di
0x180080d36  lea     r9, [rsp+298h+var_138]
0x180080d3e  mov     r8b, 1
0x180080d41  lea     rdx, [rsp+298h+var_F8]
0x180080d49  mov     rcx, r13
0x180080d4c  call    ?RegQueryValueW@Registry@Win32Adapters@@YAXAEAVRegistryHandleRAII@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV45@@Z; Win32Adapters::Registry::RegQueryValueW(RegistryHandleRAII &,std::wstring const &,bool,std::wstring &)
0x180080d51  cmp     [rsp+298h+var_128], rdi
0x180080d59  jz      loc_180081143
0x180080d5f  lea     rcx, [rsp+298h+var_138]
0x180080d67  cmp     [rsp+298h+var_120], 7
0x180080d70  cmova   rcx, qword ptr [rsp+298h+var_138]
0x180080d79  call    cs:__imp__o__wtol
0x180080d7f  mov     r12d, eax
0x180080d82  call    cs:__imp__o__errno
0x180080d88  cmp     dword ptr [rax], 22h ; '"'
0x180080d8b  jz      loc_1800811D1
0x180080d91  call    cs:__imp__o__errno
0x180080d97  cmp     dword ptr [rax], 16h
0x180080d9a  jz      loc_1800811D1
0x180080da0  lea     rcx, [rsp+298h+var_138]
0x180080da8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080dad  nop
0x180080dae  lea     rcx, [rsp+298h+var_F8]
0x180080db6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080dbb  test    r12d, r12d
0x180080dbe  jnz     short loc_180080DC5
0x180080dc0  mov     al, dil
0x180080dc3  jmp     short loc_180080DD2
0x180080dc5  cmp     r12d, 1
0x180080dc9  jnz     loc_180081176
0x180080dcf  mov     al, r12b
0x180080dd2  mov     [r15+0A0h], al
0x180080dd9  lea     rcx, [r15+0A4h]
0x180080de0  test    rcx, rcx
0x180080de3  jz      short loc_180080DF9
0x180080de5  lea     rax, [r13+70h]
0x180080de9  test    rax, rax
0x180080dec  jz      short loc_180080DF6
0x180080dee  mov     rax, [rax]
0x180080df1  mov     [rcx], rax
0x180080df4  jmp     short loc_180080E0A
0x180080df6  mov     [rcx], rax
0x180080df9  call    cs:__imp__o__errno
0x180080dff  mov     dword ptr [rax], 16h
0x180080e05  call    _invalid_parameter_noinfo
0x180080e0a  mov     rax, 7FFFFFFFFFFFFFFh
0x180080e14  cmp     [r14+8], rax
0x180080e18  jz      loc_18008116A
0x180080e1e  mov     r13, [r14]
0x180080e21  mov     [rsp+298h+var_238], r14
0x180080e26  mov     [rsp+298h+var_230], rdi
0x180080e2b  mov     ecx, 20h ; ' '; Size
0x180080e30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180080e35  mov     rcx, rax
0x180080e38  mov     [rax+10h], rdi
0x180080e3c  mov     [rax+18h], rdi
0x180080e40  test    rsi, rsi
0x180080e43  jz      short loc_180080E49
0x180080e45  lock inc dword ptr [rsi+8]
0x180080e49  mov     [rax+10h], r15
0x180080e4d  mov     [rax+18h], rsi
0x180080e51  inc     qword ptr [r14+8]
0x180080e55  mov     rax, [r13+8]
0x180080e59  mov     [rcx], r13
0x180080e5c  mov     [rcx+8], rax
0x180080e60  mov     [rsp+298h+var_230], rdi
0x180080e65  mov     [r13+8], rcx
0x180080e69  mov     [rax], rcx
0x180080e6c  lea     rcx, [rsp+298h+var_238]
0x180080e71  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$shared_ptr@VPrinterExtensionInstallAction@Driver@Print@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::shared_ptr<Print::Driver::PrinterExtensionInstallAction>,void *>>>(void)
0x180080e76  nop
0x180080e77  test    rsi, rsi
0x180080e7a  jz      short loc_180080EB0
0x180080e7c  mov     eax, ebx
0x180080e7e  lock xadd [rsi+8], eax
0x180080e83  add     eax, ebx
0x180080e85  jnz     short loc_180080EB0
0x180080e87  mov     rax, [rsi]
0x180080e8a  mov     rcx, rsi
0x180080e8d  mov     rax, [rax]
0x180080e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080e95  mov     eax, ebx
0x180080e97  lock xadd [rsi+0Ch], eax
0x180080e9c  add     eax, ebx
0x180080e9e  jnz     short loc_180080EB0
0x180080ea0  mov     rax, [rsi]
0x180080ea3  mov     rcx, rsi
0x180080ea6  mov     rax, [rax+8]
  ... truncated ...
```
