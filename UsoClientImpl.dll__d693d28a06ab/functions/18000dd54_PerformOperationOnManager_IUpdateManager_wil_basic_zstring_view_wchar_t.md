# PerformOperationOnManager(IUpdateManager *,wil::basic_zstring_view<wchar_t>)

- ea: `0x18000dd54`
- end: `0x18000e64e`
- name: `?PerformOperationOnManager@@YAJPEAUIUpdateManager@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `2298`
- prototype: `__int64 __fastcall(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **), __int128 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180007804`
- `0x18000cde8`
- `0x18000d2a8`
- `0x18000d948`
- `0x18000dd54`
- `0x18001b0e0`
- `0x180033f14`
- `0x180036b10`
- `0x18003a204`
- `0x180056500`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e12d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e149`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e156`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e12d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e149`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e156`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e11c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e11c`

## string_xrefs

- `0x18000dec6`: `StartModelUpdates`
- `0x18000df54`: `StartModelUpdates`
- `0x18000e345`: `StartOobeAppsScanAfterUpdate`
- `0x18000e54a`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e560`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e576`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e58c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e5a2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e5b8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e5ce`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e5e4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e5fa`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e610`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e626`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18000e63c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
__int64 __fastcall PerformOperationOnManager(
        __int64 (__fastcall ***a1)(__int64, GUID *, const wchar_t **),
        __int128 *a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  __int64 traits_2_unsigned_short; // rax
  const char *v8; // r9
  __int64 v9; // r11
  __int64 v10; // rax
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // r11
  __int64 v14; // rax
  __int64 v15; // rax
  const char *v16; // r9
  __int64 v17; // r11
  __int64 v18; // rax
  __int64 v19; // rax
  const char *v20; // r9
  __int64 v21; // r11
  __int64 v22; // rax
  __int64 v23; // rax
  const char *v24; // r9
  __int64 v25; // r11
  __int64 v26; // rax
  __int64 v27; // rax
  const char *v28; // r9
  __int64 v29; // r11
  __int64 v30; // rax
  __int64 v31; // rax
  const char *v32; // r9
  __int64 v33; // r11
  __int64 v34; // rax
  const WCHAR *v35; // rcx
  __int64 v36; // rax
  const char *v37; // r9
  __int64 v38; // r11
  __int64 v39; // rax
  __int64 v40; // rax
  const char *v41; // r9
  __int64 v42; // r11
  __int64 v43; // rax
  __int64 v44; // rax
  const char *v45; // r9
  __int64 v46; // r11
  __int64 v47; // rax
  __int64 (__fastcall **v48)(__int64, GUID *, const wchar_t **); // rax
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rax
  const char *v52; // r9
  __int64 v53; // r11
  __int64 v54; // rax
  __int64 (__fastcall **v55)(__int64, GUID *, const wchar_t **); // rax
  int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // rax
  const char *v59; // r9
  __int64 v60; // r11
  __int64 v61; // rax
  __int64 (__fastcall **v62)(__int64, GUID *, const wchar_t **); // rax
  int v63; // eax
  __int64 v64; // rdx
  int v65; // [rsp+20h] [rbp-40h]
  __int128 v66; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *v67; // [rsp+40h] [rbp-20h] BYREF
  __int64 v68; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( !a1 )
  {
    v4 = 204;
LABEL_3:
    v5 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)v5,
      v65);
    return (unsigned int)v5;
  }
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"StartScan",
                              &dword_18006813C,
                              0);
  if ( traits_2_unsigned_short == v9 || (v10 = (traits_2_unsigned_short - (__int64)L"StartScan") >> 1, v10 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v8);
  v67 = L"StartScan";
  v68 = v10;
  v66 = *a2;
  if ( !(unsigned __int8)Strings::iequals(&v66, &v67) )
  {
    v11 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"StartBypassOobeScan",
            L"StartBypassScan",
            0);
    if ( v11 == v13 || (v14 = (v11 - (__int64)L"StartBypassOobeScan") >> 1, v14 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v12);
    v67 = L"StartBypassOobeScan";
    v68 = v14;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v65 = 1;
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **), _QWORD, _QWORD, __int64))(*a1)[9])(
             a1,
             0,
             0,
             1);
      if ( v5 < 0 )
      {
        v4 = 220;
        goto LABEL_4;
      }
      return 0;
    }
    v15 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"StartBypassScan",
            L"StartModelUpdates",
            0);
    if ( v15 == v17 || (v18 = (v15 - (__int64)L"StartBypassScan") >> 1, v18 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v16);
    v67 = L"StartBypassScan";
    v68 = v18;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v65 = 0;
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **), _QWORD, _QWORD, __int64))(*a1)[9])(
             a1,
             0,
             0,
             1);
      if ( v5 < 0 )
      {
        v4 = 228;
        goto LABEL_4;
      }
      return 0;
    }
    v19 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"StartModelUpdates",
            &dword_1800681AC,
            0);
    if ( v19 == v21 || (v22 = (v19 - (__int64)L"StartModelUpdates") >> 1, v22 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v20);
    v67 = L"StartModelUpdates";
    v68 = v22;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
      return 0;
    v23 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"StartWork",
            &dword_1800681C4,
            0);
    if ( v23 == v25 || (v26 = (v23 - (__int64)L"StartWork") >> 1, v26 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v24);
    v67 = L"StartWork";
    v68 = v26;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **)))(*a1)[22])(a1);
      if ( v5 < 0 )
      {
        v4 = 236;
        goto LABEL_4;
      }
      return 0;
    }
    v27 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"StartMaintenanceWork",
            word_1800681F2,
            0);
    if ( v27 == v29 || (v30 = (v27 - (__int64)L"StartMaintenanceWork") >> 1, v30 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v28);
    v67 = L"StartMaintenanceWork";
    v68 = v30;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **)))(*a1)[23])(a1);
      if ( v5 < 0 )
      {
        v4 = 240;
        goto LABEL_4;
      }
      return 0;
    }
    v31 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"GetAutoRescan",
            &dword_180068214,
            0);
    if ( v31 == v33 || (v34 = (v31 - (__int64)L"GetAutoRescan") >> 1, v34 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v32);
    v67 = L"GetAutoRescan";
    v68 = v34;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      LODWORD(v67) = 0;
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **), const wchar_t **))(*a1)[24])(
             a1,
             &v67);
      if ( v5 < 0 )
      {
        v4 = 246;
        goto LABEL_4;
      }
      if ( IsDebuggerPresent() )
      {
        OutputDebugStringW(L"AutoRescan Mode: ");
        v35 = L"Disabled";
        if ( (_DWORD)v67 )
          v35 = L"Enabled";
        OutputDebugStringW(v35);
        OutputDebugStringW(L"\n\r");
      }
      return 0;
    }
    v36 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"SetAutoRescan",
            &dword_18006828C,
            0);
    if ( v36 == v38 || (v39 = (v36 - (__int64)L"SetAutoRescan") >> 1, v39 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v37);
    v67 = L"SetAutoRescan";
    v68 = v39;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **), __int64))(*a1)[25])(
             a1,
             1);
      if ( v5 < 0 )
      {
        v4 = 256;
        goto LABEL_4;
      }
      return 0;
    }
    v40 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"ClearAutoRescan",
            L"StartOobeScan",
            0);
    if ( v40 == v42 || (v43 = (v40 - (__int64)L"ClearAutoRescan") >> 1, v43 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v41);
    v67 = L"ClearAutoRescan";
    v68 = v43;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **), _QWORD))(*a1)[25])(
             a1,
             0);
      if ( v5 < 0 )
      {
        v4 = 260;
        goto LABEL_4;
      }
      return 0;
    }
    v44 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"StartOobeScan",
            &dword_1800682CC,
            0);
    if ( v44 == v46 || (v47 = (v44 - (__int64)L"StartOobeScan") >> 1, v47 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v45);
    v67 = L"StartOobeScan";
    v68 = v47;
    v66 = *a2;
    if ( (unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v48 = *a1;
      v67 = 0;
      v49 = (*v48)((__int64)a1, &GUID_bf6ff983_c70b_49c5_8ac8_e4d895205f89, &v67);
      v5 = v49;
      if ( v49 < 0 )
      {
        v50 = 265;
        goto LABEL_61;
      }
      v49 = (*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 280LL))(v67);
      v5 = v49;
      if ( v49 < 0 )
      {
        v50 = 266;
LABEL_61:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v50,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
          (const char *)(unsigned int)v49,
          v65);
        if ( v67 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 16LL))(v67);
        return (unsigned int)v5;
      }
LABEL_78:
      if ( v67 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 16LL))(v67);
      return 0;
    }
    v51 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
            L"StartOobeAppsScanAfterUpdate",
            word_18006830A,
            0);
    if ( v51 == v53 || (v54 = (v51 - (__int64)L"StartOobeAppsScanAfterUpdate") >> 1, v54 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v52);
    v67 = L"StartOobeAppsScanAfterUpdate";
    v68 = v54;
    v66 = *a2;
    if ( !(unsigned __int8)Strings::iequals(&v66, &v67) )
    {
      v58 = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
              L"StartOobeAppsScan",
              &dword_180068334,
              0);
      if ( v58 == v60 || (v61 = (v58 - (__int64)L"StartOobeAppsScan") >> 1, v61 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v59);
      v67 = L"StartOobeAppsScan";
      v68 = v61;
      v66 = *a2;
      if ( !(unsigned __int8)Strings::iequals(&v66, &v67) )
      {
        v4 = 298;
        goto LABEL_3;
      }
      v62 = *a1;
      v67 = 0;
      v63 = (*v62)((__int64)a1, &GUID_bf6ff983_c70b_49c5_8ac8_e4d895205f89, &v67);
      v5 = v63;
      if ( v63 >= 0 )
      {
        v63 = (*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 288LL))(v67);
        v5 = v63;
        if ( v63 >= 0 )
        {
          if ( v67 )
            (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 16LL))(v67);
          return 0;
        }
        v64 = 294;
      }
      else
      {
        v64 = 292;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v64,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
        (const char *)(unsigned int)v63,
        v65);
      if ( v67 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 16LL))(v67);
      return (unsigned int)v5;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_StopRetrying23H2ExpeditedApps_48960063>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_StopRetrying23H2ExpeditedApps_48960063>::GetImpl'::`2'::impl)
      && HasOsBuildNumberIncreased() )
    {
      Delete23H2ExpeditedUpdates();
    }
    DeleteExpeditedUpdates();
    v55 = *a1;
    v67 = 0;
    v56 = (*v55)((__int64)a1, &GUID_bf6ff983_c70b_49c5_8ac8_e4d895205f89, &v67);
    v5 = v56;
    if ( v56 >= 0 )
    {
      v56 = (*(__int64 (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 288LL))(v67);
      v5 = v56;
      if ( v56 >= 0 )
        goto LABEL_78;
      v57 = 287;
    }
    else
    {
      v57 = 285;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v57,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)v56,
      v65);
    if ( v67 )
      (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v67 + 16LL))(v67);
    return (unsigned int)v5;
  }
  v65 = 0;
  v5 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, const wchar_t **), _QWORD, _QWORD, _QWORD))(*a1)[9])(
         a1,
         0,
         0,
         0);
  if ( v5 < 0 )
  {
    v4 = 212;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dd54  mov     [rsp-18h+arg_10], rbx
0x18000dd59  push    rbp
0x18000dd5a  push    rdi
0x18000dd5b  push    r15
0x18000dd5d  mov     rbp, rsp
0x18000dd60  sub     rsp, 60h
0x18000dd64  mov     rax, cs:__security_cookie
0x18000dd6b  xor     rax, rsp
0x18000dd6e  mov     [rbp+var_10], rax
0x18000dd72  mov     rdi, rdx
0x18000dd75  mov     rbx, rcx
0x18000dd78  test    rcx, rcx
0x18000dd7b  jnz     short loc_18000DDB9
0x18000dd7d  mov     edx, 0CCh; void *
0x18000dd82  mov     ebx, 80070057h
0x18000dd87  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000dd8e  mov     r9d, ebx; char *
0x18000dd91  mov     rcx, [rbp+18h]; this
0x18000dd95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd9a  mov     eax, ebx
0x18000dd9c  mov     rcx, [rbp+var_10]
0x18000dda0  xor     rcx, rsp; StackCookie
0x18000dda3  call    __security_check_cookie
0x18000dda8  mov     rbx, [rsp+60h+arg_10]
0x18000ddb0  add     rsp, 60h
0x18000ddb4  pop     r15
0x18000ddb6  pop     rdi
0x18000ddb7  pop     rbp
0x18000ddb8  retn
0x18000ddb9  xor     r8d, r8d
0x18000ddbc  lea     r11, dword_18006813C
0x18000ddc3  mov     rdx, r11
0x18000ddc6  lea     r15, aStartscan; "StartScan"
0x18000ddcd  mov     rcx, r15
0x18000ddd0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000ddd5  cmp     rax, r11
0x18000ddd8  jz      loc_18000E55C
0x18000ddde  sub     rax, r15
0x18000dde1  sar     rax, 1
0x18000dde4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dde8  jz      loc_18000E55C
0x18000ddee  mov     [rbp+var_20], r15
0x18000ddf2  mov     [rbp+var_18], rax
0x18000ddf6  movaps  xmm0, xmmword ptr [rdi]
0x18000ddf9  movdqa  [rbp+var_30], xmm0
0x18000ddfe  lea     rdx, [rbp+var_20]
0x18000de02  lea     rcx, [rbp+var_30]
0x18000de06  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000de0b  xor     r8d, r8d
0x18000de0e  test    al, al
0x18000de10  jz      short loc_18000DE3F
0x18000de12  mov     rax, [rbx]
0x18000de15  mov     [rsp+60h+var_40], r8d
0x18000de1a  xor     r9d, r9d
0x18000de1d  xor     edx, edx
0x18000de1f  mov     rcx, rbx
0x18000de22  mov     rax, [rax+48h]
0x18000de26  call    _guard_dispatch_icall
0x18000de2b  mov     ebx, eax
0x18000de2d  test    eax, eax
0x18000de2f  jns     loc_18000E15C
0x18000de35  mov     edx, 0D4h
0x18000de3a  jmp     loc_18000DD87
0x18000de3f  lea     r11, aStartbypasssca; "StartBypassScan"
0x18000de46  mov     rdx, r11
0x18000de49  lea     r15, aStartbypassoob; "StartBypassOobeScan"
0x18000de50  mov     rcx, r15
0x18000de53  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000de58  cmp     rax, r11
0x18000de5b  jz      loc_18000E546
0x18000de61  sub     rax, r15
0x18000de64  sar     rax, 1
0x18000de67  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000de6b  jz      loc_18000E546
0x18000de71  mov     [rbp+var_20], r15
0x18000de75  mov     [rbp+var_18], rax
0x18000de79  movaps  xmm0, xmmword ptr [rdi]
0x18000de7c  movdqa  [rbp+var_30], xmm0
0x18000de81  lea     rdx, [rbp+var_20]
0x18000de85  lea     rcx, [rbp+var_30]
0x18000de89  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000de8e  xor     r8d, r8d
0x18000de91  test    al, al
0x18000de93  jz      short loc_18000DEC6
0x18000de95  mov     rax, [rbx]
0x18000de98  mov     [rsp+60h+var_40], 1
0x18000dea0  lea     r9d, [r8+1]
0x18000dea4  xor     edx, edx
0x18000dea6  mov     rcx, rbx
0x18000dea9  mov     rax, [rax+48h]
0x18000dead  call    _guard_dispatch_icall
0x18000deb2  mov     ebx, eax
0x18000deb4  test    eax, eax
0x18000deb6  jns     loc_18000E15C
0x18000debc  mov     edx, 0DCh
0x18000dec1  jmp     loc_18000DD87
0x18000dec6  lea     r11, aStartmodelupda; "StartModelUpdates"
0x18000decd  mov     rdx, r11
0x18000ded0  lea     r15, aStartbypasssca; "StartBypassScan"
0x18000ded7  mov     rcx, r15
0x18000deda  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000dedf  cmp     rax, r11
0x18000dee2  jz      loc_18000E638
0x18000dee8  sub     rax, r15
0x18000deeb  sar     rax, 1
0x18000deee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000def2  jz      loc_18000E638
0x18000def8  mov     [rbp+var_20], r15
0x18000defc  mov     [rbp+var_18], rax
0x18000df00  movaps  xmm0, xmmword ptr [rdi]
0x18000df03  movdqa  [rbp+var_30], xmm0
0x18000df08  lea     rdx, [rbp+var_20]
0x18000df0c  lea     rcx, [rbp+var_30]
0x18000df10  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000df15  xor     r8d, r8d
0x18000df18  test    al, al
0x18000df1a  jz      short loc_18000DF4A
0x18000df1c  mov     rax, [rbx]
0x18000df1f  mov     [rsp+60h+var_40], r8d
0x18000df24  lea     r9d, [r8+1]
0x18000df28  xor     edx, edx
0x18000df2a  mov     rcx, rbx
0x18000df2d  mov     rax, [rax+48h]
0x18000df31  call    _guard_dispatch_icall
0x18000df36  mov     ebx, eax
0x18000df38  test    eax, eax
0x18000df3a  jns     loc_18000E15C
0x18000df40  mov     edx, 0E4h
0x18000df45  jmp     loc_18000DD87
0x18000df4a  lea     r11, dword_1800681AC
0x18000df51  mov     rdx, r11
0x18000df54  lea     r15, aStartmodelupda; "StartModelUpdates"
0x18000df5b  mov     rcx, r15
0x18000df5e  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000df63  cmp     rax, r11
0x18000df66  jz      loc_18000E622
0x18000df6c  sub     rax, r15
0x18000df6f  sar     rax, 1
0x18000df72  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000df76  jz      loc_18000E622
0x18000df7c  mov     [rbp+var_20], r15
0x18000df80  mov     [rbp+var_18], rax
0x18000df84  movaps  xmm0, xmmword ptr [rdi]
0x18000df87  movdqa  [rbp+var_30], xmm0
0x18000df8c  lea     rdx, [rbp+var_20]
0x18000df90  lea     rcx, [rbp+var_30]
0x18000df94  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000df99  test    al, al
0x18000df9b  jnz     loc_18000E15C
0x18000dfa1  xor     r8d, r8d
0x18000dfa4  lea     r11, dword_1800681C4
0x18000dfab  mov     rdx, r11
0x18000dfae  lea     r15, aStartwork; "StartWork"
0x18000dfb5  mov     rcx, r15
0x18000dfb8  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000dfbd  cmp     rax, r11
0x18000dfc0  jz      loc_18000E60C
0x18000dfc6  sub     rax, r15
0x18000dfc9  sar     rax, 1
0x18000dfcc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dfd0  jz      loc_18000E60C
0x18000dfd6  mov     [rbp+var_20], r15
0x18000dfda  mov     [rbp+var_18], rax
0x18000dfde  movaps  xmm0, xmmword ptr [rdi]
0x18000dfe1  movdqa  [rbp+var_30], xmm0
0x18000dfe6  lea     rdx, [rbp+var_20]
0x18000dfea  lea     rcx, [rbp+var_30]
0x18000dfee  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000dff3  test    al, al
0x18000dff5  jz      short loc_18000E01D
0x18000dff7  mov     rax, [rbx]
0x18000dffa  mov     rcx, rbx
0x18000dffd  mov     rax, [rax+0B0h]
0x18000e004  call    _guard_dispatch_icall
0x18000e009  mov     ebx, eax
0x18000e00b  test    eax, eax
0x18000e00d  jns     loc_18000E15C
0x18000e013  mov     edx, 0ECh
0x18000e018  jmp     loc_18000DD87
0x18000e01d  xor     r8d, r8d
0x18000e020  lea     r11, word_1800681F2
0x18000e027  mov     rdx, r11
0x18000e02a  lea     r15, aStartmaintenan; "StartMaintenanceWork"
0x18000e031  mov     rcx, r15
0x18000e034  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e039  cmp     rax, r11
0x18000e03c  jz      loc_18000E5F6
0x18000e042  sub     rax, r15
0x18000e045  sar     rax, 1
0x18000e048  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e04c  jz      loc_18000E5F6
0x18000e052  mov     [rbp+var_20], r15
0x18000e056  mov     [rbp+var_18], rax
0x18000e05a  movaps  xmm0, xmmword ptr [rdi]
0x18000e05d  movdqa  [rbp+var_30], xmm0
0x18000e062  lea     rdx, [rbp+var_20]
0x18000e066  lea     rcx, [rbp+var_30]
0x18000e06a  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e06f  test    al, al
0x18000e071  jz      short loc_18000E099
0x18000e073  mov     rax, [rbx]
0x18000e076  mov     rcx, rbx
0x18000e079  mov     rax, [rax+0B8h]
0x18000e080  call    _guard_dispatch_icall
0x18000e085  mov     ebx, eax
0x18000e087  test    eax, eax
0x18000e089  jns     loc_18000E15C
0x18000e08f  mov     edx, 0F0h
0x18000e094  jmp     loc_18000DD87
0x18000e099  xor     r8d, r8d
0x18000e09c  lea     r11, dword_180068214
0x18000e0a3  mov     rdx, r11
0x18000e0a6  lea     r15, aGetautorescan; "GetAutoRescan"
0x18000e0ad  mov     rcx, r15
0x18000e0b0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e0b5  cmp     rax, r11
0x18000e0b8  jz      loc_18000E5E0
0x18000e0be  sub     rax, r15
0x18000e0c1  sar     rax, 1
0x18000e0c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e0c8  jz      loc_18000E5E0
0x18000e0ce  mov     [rbp+var_20], r15
0x18000e0d2  mov     [rbp+var_18], rax
0x18000e0d6  movaps  xmm0, xmmword ptr [rdi]
0x18000e0d9  movdqa  [rbp+var_30], xmm0
0x18000e0de  lea     rdx, [rbp+var_20]
0x18000e0e2  lea     rcx, [rbp+var_30]
0x18000e0e6  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e0eb  test    al, al
0x18000e0ed  jz      short loc_18000E163
0x18000e0ef  mov     dword ptr [rbp+var_20], 0
0x18000e0f6  mov     rax, [rbx]
0x18000e0f9  lea     rdx, [rbp+var_20]
0x18000e0fd  mov     rcx, rbx
0x18000e100  mov     rax, [rax+0C0h]
0x18000e107  call    _guard_dispatch_icall
0x18000e10c  mov     ebx, eax
0x18000e10e  test    eax, eax
0x18000e110  jns     short loc_18000E11C
0x18000e112  mov     edx, 0F6h
0x18000e117  jmp     loc_18000DD87
0x18000e11c  call    cs:__imp_IsDebuggerPresent
0x18000e122  test    eax, eax
0x18000e124  jz      short loc_18000E15C
0x18000e126  lea     rcx, OutputString; "AutoRescan Mode: "
0x18000e12d  call    cs:__imp_OutputDebugStringW
0x18000e133  lea     rax, aEnabled; "Enabled"
0x18000e13a  lea     rcx, aDisabled; "Disabled"
0x18000e141  cmp     dword ptr [rbp+var_20], 0
0x18000e145  cmovnz  rcx, rax; lpOutputString
0x18000e149  call    cs:__imp_OutputDebugStringW
0x18000e14f  lea     rcx, asc_180068264; "\n\r"
0x18000e156  call    cs:__imp_OutputDebugStringW
0x18000e15c  xor     eax, eax
0x18000e15e  jmp     loc_18000DD9C
0x18000e163  xor     r8d, r8d
0x18000e166  lea     r11, dword_18006828C
0x18000e16d  mov     rdx, r11
0x18000e170  lea     r15, aSetautorescan; "SetAutoRescan"
0x18000e177  mov     rcx, r15
0x18000e17a  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e17f  cmp     rax, r11
0x18000e182  jz      loc_18000E5CA
0x18000e188  sub     rax, r15
0x18000e18b  sar     rax, 1
0x18000e18e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e192  jz      loc_18000E5CA
0x18000e198  mov     [rbp+var_20], r15
0x18000e19c  mov     [rbp+var_18], rax
0x18000e1a0  movaps  xmm0, xmmword ptr [rdi]
0x18000e1a3  movdqa  [rbp+var_30], xmm0
0x18000e1a8  lea     rdx, [rbp+var_20]
0x18000e1ac  lea     rcx, [rbp+var_30]
0x18000e1b0  call    ?iequals@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::iequals(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18000e1b5  test    al, al
0x18000e1b7  jz      short loc_18000E1E0
0x18000e1b9  mov     rax, [rbx]
0x18000e1bc  mov     edx, 1
0x18000e1c1  mov     rcx, rbx
0x18000e1c4  mov     rax, [rax+0C8h]
0x18000e1cb  call    _guard_dispatch_icall
0x18000e1d0  mov     ebx, eax
0x18000e1d2  test    eax, eax
0x18000e1d4  jns     short loc_18000E15C
0x18000e1d6  mov     edx, 100h
0x18000e1db  jmp     loc_18000DD87
0x18000e1e0  xor     r8d, r8d
0x18000e1e3  lea     r11, aStartoobescan; "StartOobeScan"
0x18000e1ea  mov     rdx, r11
0x18000e1ed  lea     r15, aClearautoresca; "ClearAutoRescan"
0x18000e1f4  mov     rcx, r15
0x18000e1f7  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000e1fc  cmp     rax, r11
0x18000e1ff  jz      loc_18000E5B4
0x18000e205  sub     rax, r15
0x18000e208  sar     rax, 1
0x18000e20b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e20f  jz      loc_18000E5B4
0x18000e215  mov     [rbp+var_20], r15
0x18000e219  mov     [rbp+var_18], rax
  ... truncated ...
```
