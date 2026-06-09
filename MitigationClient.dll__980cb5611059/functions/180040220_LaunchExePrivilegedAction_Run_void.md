# LaunchExePrivilegedAction::Run(void)

- ea: `0x180040220`
- end: `0x1800406ad`
- name: `?Run@LaunchExePrivilegedAction@@UEAAXXZ`
- size: `1165`
- prototype: `void __fastcall(LaunchExePrivilegedAction *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x180013ebc`
- `0x180018858`
- `0x180019878`
- `0x180019ecc`
- `0x18001e164`
- `0x18002407c`
- `0x1800240b8`
- `0x18002db58`
- `0x180036010`
- `0x18003ba00`
- `0x18003bd40`
- `0x18003c970`
- `0x18003e60c`
- `0x18003f508`
- `0x18003f75c`
- `0x18003fd60`
- `0x180040220`
- `0x180042c8c`
- `0x180042edc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800402ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800402ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040284`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040284`

## string_xrefs

- `0x1800402a0`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x1800402c9`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x180040325`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x180040370`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x180040410`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x180040469`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x180040496`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x18004057f`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`
- `0x1800405c5`: `onecore\base\diagnosis\mitigation\client\libs\serviceactions\launchexeprivilegedaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LaunchExePrivilegedAction::Run(LaunchExePrivilegedAction *this)
{
  unsigned __int16 *v2; // r14
  struct MitigationContext *MitigationContext; // rsi
  const char *v4; // r9
  int IsFileMicrosoftSigned; // eax
  const unsigned __int16 *v6; // rbx
  int v7; // r8d
  int v8; // eax
  int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rdx
  char *v13; // rbx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  wil *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  unsigned int i; // ecx
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  unsigned int v31; // eax
  __int64 v32; // rax
  wil *v33; // rcx
  unsigned int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-2B8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-298h] BYREF
  struct _FILETIME v39; // [rsp+48h] [rbp-290h] BYREF
  _QWORD v40[3]; // [rsp+50h] [rbp-288h] BYREF
  HANDLE FileW; // [rsp+68h] [rbp-270h] BYREF
  _QWORD v42[3]; // [rsp+70h] [rbp-268h] BYREF
  _QWORD v43[3]; // [rsp+88h] [rbp-250h] BYREF
  const wil::ResultException *v44; // [rsp+A0h] [rbp-238h] BYREF
  const wil::ResultException *v45; // [rsp+A8h] [rbp-230h] BYREF
  _BYTE v46[424]; // [rsp+B0h] [rbp-228h] BYREF
  _BYTE v47[32]; // [rsp+258h] [rbp-80h] BYREF
  _BYTE v48[32]; // [rsp+278h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v2 = *(unsigned __int16 **)(*((_QWORD *)this + 20) + 40LL);
  MitigationContext = MitigationExecutionContext::GetMitigationContext(v2);
  FileW = CreateFileW(*((LPCWSTR *)this + 7), 0x120089u, 1u, 0, 3u, 4u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    try
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
        v4);
    }
    catch ( const wil::ResultException *v45 )
    {
      v36 = MitigationException::MitigationException(v46, 4, v45);
      wil::details::ReportFailure_CustomException<MitigationException>(
        retaddr,
        337,
        "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
        v36);
    }
    catch ( ... )
    {
      v34 = wil::ResultFromCaughtException(v33);
      v35 = MitigationException::MitigationException(v46, 4, v34);
      wil::details::ReportFailure_CustomException<MitigationException>(
        retaddr,
        342,
        "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
        v35);
    }
  }
  try
  {
    IsFileMicrosoftSigned = CabUtils::IsFileMicrosoftSigned(*((const unsigned __int16 **)this + 7));
    if ( IsFileMicrosoftSigned < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
        (const char *)(unsigned int)IsFileMicrosoftSigned,
        dwCreationDisposition);
    if ( (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace((char *)this + 136) )
    {
LABEL_14:
      memset(v43, 0, sizeof(v43));
      if ( (*((_BYTE *)this + 128) & 1) == 0
        || (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(*((_QWORD *)this + 20) + 16LL) )
      {
        v13 = (char *)this + 104;
        v12 = *((_QWORD *)this + 13);
      }
      else
      {
        v12 = *(_QWORD *)(*((_QWORD *)this + 20) + 16LL);
        v13 = (char *)this + 104;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v43, v12, -1);
      memset(v42, 0, sizeof(v42));
      v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v42,
              *((_QWORD *)this + 7),
              -1);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x16D,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
          (const char *)(unsigned int)v14,
          dwCreationDisposition);
      memset(v40, 0, sizeof(v40));
      if ( (unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::IsEmptyIgnoringWhitespace(v13) )
      {
        v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                v40,
                v42[0],
                -1);
        if ( v16 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
            (const char *)(unsigned int)v16,
            dwCreationDisposition);
      }
      else
      {
        v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                v40,
                L"%s %s",
                v42[0],
                v43[0]);
        if ( v15 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x172,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
            (const char *)(unsigned int)v15,
            dwCreationDisposition);
      }
      if ( *((_BYTE *)MitigationContext + 424) )
      {
        *((_DWORD *)MitigationContext + 87) = 0;
        *((_WORD *)MitigationContext + 172) = 257;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v42);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v43);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
      }
      else
      {
        if ( *((_BYTE *)MitigationContext + 112) )
        {
          std::wstring::wstring(v47, L" /restart", 9);
          v18 = std::_WChar_traits<unsigned short>::length(v40[0]);
          v21 = std::wstring::_Insert<unsigned short>(v47, v19, v20, v18);
          std::wstring::wstring(v48, v21);
          std::wstring::_Tidy_deallocate(v47);
          v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
          v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                  v40,
                  v22,
                  -1);
          if ( v23 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x184,
              (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
              (const char *)(unsigned int)v23,
              dwCreationDisposition);
          std::wstring::_Tidy_deallocate(v48);
        }
        v24 = Windows::Internal::Mitigation::LaunchExePrivilegedAction::LaunchMitigationProcessUnderJobManagement(v2);
        if ( v24 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x18C,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
            (const char *)(unsigned int)v24,
            dwCreationDisposition);
        if ( (unsigned int)(*((_DWORD *)MitigationContext + 87) + 2135164162) <= 1
          && *((_DWORD *)MitigationContext + 29) != 1 )
        {
          MitigationExecutionContext::DispatchEvent(21, 2159802916LL);
        }
        v25 = *((_QWORD *)this + 21);
        if ( v25 )
        {
          for ( i = 0; i < *((_DWORD *)this + 44); ++i )
          {
            v27 = 204LL * i;
            if ( *(_DWORD *)(v27 + v25) == *((_DWORD *)MitigationContext + 87) )
            {
              *((_BYTE *)MitigationContext + 345) = 1;
              v28 = std::_WChar_traits<unsigned short>::length(v27 + *((_QWORD *)this + 21) + 4LL);
              std::wstring::_Assign<unsigned short>((char *)MitigationContext + 352, v29, v28);
              break;
            }
          }
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v42);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v43);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
      }
      return;
    }
    v6 = (const unsigned __int16 *)*((_QWORD *)this + 17);
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v39 = 0;
    v8 = MitigationAPICommon::StringToFileTime(v6, &v39, v7);
    v9 = v8;
    if ( v8 >= 0 )
    {
      if ( MitigationAPICommon::TimeDiffInMs(SystemTimeAsFileTime, v39) )
      {
        v9 = 0;
LABEL_12:
        if ( v9 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x15D,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
            (const char *)(unsigned int)v9,
            dwCreationDisposition);
        goto LABEL_14;
      }
      v9 = -2135164385;
      v10 = 2159802911LL;
      v11 = 451;
    }
    else
    {
      v10 = (unsigned int)v8;
      v11 = 447;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
      (const char *)v10,
      dwCreationDisposition);
    goto LABEL_12;
  }
  catch ( const wil::ResultException *v44 )
  {
    v30 = MitigationException::MitigationException(v46, 8, v44);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      422,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
      v30);
  }
  catch ( ... )
  {
    v31 = wil::ResultFromCaughtException(v17);
    v32 = MitigationException::MitigationException(v46, 8, v31);
    wil::details::ReportFailure_CustomException<MitigationException>(
      retaddr,
      427,
      "onecore\\base\\diagnosis\\mitigation\\client\\libs\\serviceactions\\launchexeprivilegedaction.cpp",
      v32);
  }
}

```

## disassembly

```asm
0x180040220  push    rbx
0x180040222  push    rsi
0x180040223  push    rdi
0x180040224  push    r13
0x180040226  push    r14
0x180040228  push    r15
0x18004022a  sub     rsp, 2A8h
0x180040231  mov     rax, cs:__security_cookie
0x180040238  xor     rax, rsp
0x18004023b  mov     [rsp+2D8h+var_40], rax
0x180040243  mov     rdi, rcx
0x180040246  xor     r15d, r15d
0x180040249  mov     rax, [rcx+0A0h]
0x180040250  mov     r14, [rax+28h]
0x180040254  mov     rcx, r14; unsigned __int16 *
0x180040257  call    ?GetMitigationContext@MitigationExecutionContext@@SAAEAVMitigationContext@@PEBG@Z; MitigationExecutionContext::GetMitigationContext(ushort const *)
0x18004025c  mov     rsi, rax
0x18004025f  mov     [rsp+2D8h+hTemplateFile], r15; hTemplateFile
0x180040264  mov     [rsp+2D8h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x18004026c  mov     [rsp+2D8h+dwCreationDisposition], 3; int
0x180040274  xor     r9d, r9d; lpSecurityAttributes
0x180040277  mov     edx, 120089h; dwDesiredAccess
0x18004027c  lea     r8d, [r15+1]; dwShareMode
0x180040280  mov     rcx, [rdi+38h]; lpFileName
0x180040284  call    cs:__imp_CreateFileW
0x18004028a  mov     [rsp+2D8h+var_270], rax
0x18004028f  mov     rcx, [rsp+2D8h]; this
0x180040297  or      r13, 0FFFFFFFFFFFFFFFFh
0x18004029b  cmp     rax, r13
0x18004029e  jnz     short loc_1800402B1
0x1800402a0  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800402a7  mov     edx, 14Ah; void *
0x1800402ac  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800402b1  mov     rcx, [rdi+38h]; unsigned __int16 *
0x1800402b5  call    ?IsFileMicrosoftSigned@CabUtils@@SAJPEBG@Z; CabUtils::IsFileMicrosoftSigned(ushort const *)
0x1800402ba  mov     rcx, [rsp+2D8h]; this
0x1800402c2  test    eax, eax
0x1800402c4  jns     short loc_1800402DB
0x1800402c6  mov     r9d, eax; char *
0x1800402c9  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800402d0  mov     edx, 14Dh; void *
0x1800402d5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800402db  lea     rbx, [rdi+88h]
0x1800402e2  mov     rcx, rbx
0x1800402e5  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x1800402ea  test    al, al
0x1800402ec  jnz     loc_180040381
0x1800402f2  mov     rbx, [rbx]
0x1800402f5  mov     qword ptr [rsp+2D8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800402fa  lea     rcx, [rsp+2D8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800402ff  call    cs:__imp_GetSystemTimeAsFileTime
0x180040305  mov     qword ptr [rsp+2D8h+var_290.dwLowDateTime], r15
0x18004030a  lea     rdx, [rsp+2D8h+var_290]; struct _FILETIME *
0x18004030f  mov     rcx, rbx; unsigned __int16 *
0x180040312  call    ?StringToFileTime@MitigationAPICommon@@SAJPEBGPEAU_FILETIME@@H@Z; MitigationAPICommon::StringToFileTime(ushort const *,_FILETIME *,int)
0x180040317  mov     ebx, eax
0x180040319  test    eax, eax
0x18004031b  jns     short loc_18004033B
0x18004031d  mov     r9d, eax; char *
0x180040320  mov     edx, 1BFh; void *
0x180040325  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18004032c  mov     rcx, [rsp+2D8h]; this
0x180040334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040339  jmp     short loc_180040361
0x18004033b  mov     rdx, qword ptr [rsp+2D8h+var_290.dwLowDateTime]; struct _FILETIME
0x180040340  mov     rcx, qword ptr [rsp+2D8h+SystemTimeAsFileTime.dwLowDateTime]; struct _FILETIME
0x180040345  call    ?TimeDiffInMs@MitigationAPICommon@@SA_KU_FILETIME@@0@Z; MitigationAPICommon::TimeDiffInMs(_FILETIME,_FILETIME)
0x18004034a  test    rax, rax
0x18004034d  jnz     short loc_18004035E
0x18004034f  mov     ebx, 80BBFA1Fh
0x180040354  mov     r9d, ebx
0x180040357  mov     edx, 1C3h
0x18004035c  jmp     short loc_180040325
0x18004035e  mov     ebx, r15d
0x180040361  mov     rcx, [rsp+2D8h]; this
0x180040369  test    ebx, ebx
0x18004036b  jns     short loc_180040381
0x18004036d  mov     r9d, ebx; char *
0x180040370  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180040377  mov     edx, 15Dh; void *
0x18004037c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180040381  mov     [rsp+2D8h+var_250], r15
0x180040389  mov     [rsp+2D8h+var_248], r15
0x180040391  mov     [rsp+2D8h+var_240], r15
0x180040399  test    byte ptr [rdi+80h], 1
0x1800403a0  jz      short loc_1800403C7
0x1800403a2  mov     rcx, [rdi+0A0h]
0x1800403a9  add     rcx, 10h
0x1800403ad  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x1800403b2  test    al, al
0x1800403b4  jnz     short loc_1800403C7
0x1800403b6  mov     rax, [rdi+0A0h]
0x1800403bd  mov     rdx, [rax+10h]
0x1800403c1  lea     rbx, [rdi+68h]
0x1800403c5  jmp     short loc_1800403CE
0x1800403c7  lea     rbx, [rdi+68h]
0x1800403cb  mov     rdx, [rbx]
0x1800403ce  mov     r8, r13
0x1800403d1  lea     rcx, [rsp+2D8h+var_250]
0x1800403d9  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800403de  mov     [rsp+2D8h+var_268], r15
0x1800403e3  mov     [rsp+2D8h+var_260], r15
0x1800403e8  mov     [rsp+2D8h+var_258], r15
0x1800403f0  mov     r8, r13
0x1800403f3  mov     rdx, [rdi+38h]
0x1800403f7  lea     rcx, [rsp+2D8h+var_268]
0x1800403fc  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180040401  mov     rcx, [rsp+2D8h]; this
0x180040409  test    eax, eax
0x18004040b  jns     short loc_180040421
0x18004040d  mov     r9d, eax; char *
0x180040410  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180040417  mov     edx, 16Dh; void *
0x18004041c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180040421  mov     [rsp+2D8h+var_288], r15
0x180040426  mov     [rsp+2D8h+var_280], r15
0x18004042b  mov     [rsp+2D8h+var_278], r15
0x180040430  mov     rcx, rbx
0x180040433  call    ?IsEmptyIgnoringWhitespace@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBA_NXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::IsEmptyIgnoringWhitespace(void)
0x180040438  lea     rcx, [rsp+2D8h+var_288]
0x18004043d  test    al, al
0x18004043f  jnz     short loc_18004047A
0x180040441  mov     r9, [rsp+2D8h+var_250]
0x180040449  mov     r8, [rsp+2D8h+var_268]
0x18004044e  lea     rdx, aSS_1; "%s %s"
0x180040455  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004045a  mov     rcx, [rsp+2D8h]; this
0x180040462  test    eax, eax
0x180040464  jns     short loc_1800404A7
0x180040466  mov     r9d, eax; char *
0x180040469  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180040470  mov     edx, 172h; void *
0x180040475  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004047a  mov     r8, r13
0x18004047d  mov     rdx, [rsp+2D8h+var_268]
0x180040482  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180040487  mov     rcx, [rsp+2D8h]; this
0x18004048f  test    eax, eax
0x180040491  jns     short loc_1800404A7
0x180040493  mov     r9d, eax; char *
0x180040496  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18004049d  mov     edx, 176h; void *
0x1800404a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800404a7  cmp     [rsi+1A8h], r15b
0x1800404ae  jz      short loc_1800404F3
0x1800404b0  mov     [rsi+15Ch], r15d
0x1800404b7  mov     word ptr [rsi+158h], 101h
0x1800404c0  lea     rcx, [rsp+2D8h+var_288]
0x1800404c5  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800404ca  nop
0x1800404cb  lea     rcx, [rsp+2D8h+var_268]
0x1800404d0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800404d5  nop
0x1800404d6  lea     rcx, [rsp+2D8h+var_250]
0x1800404de  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800404e3  nop
0x1800404e4  lea     rcx, [rsp+2D8h+var_270]
0x1800404e9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800404ee  jmp     loc_180040683
0x1800404f3  cmp     [rsi+70h], r15b
0x1800404f7  jz      loc_18004059E
0x1800404fd  mov     r8d, 9
0x180040503  lea     rdx, aRestart; " /restart"
0x18004050a  lea     rcx, [rsp+2D8h+var_80]
0x180040512  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x180040517  nop
0x180040518  mov     rcx, [rsp+2D8h+var_288]
0x18004051d  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180040522  mov     r9, rax
0x180040525  mov     r8, rcx
0x180040528  lea     rcx, [rsp+2D8h+var_80]
0x180040530  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x180040535  mov     rdx, rax
0x180040538  lea     rcx, [rsp+2D8h+var_60]
0x180040540  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180040545  nop
0x180040546  lea     rcx, [rsp+2D8h+var_80]
0x18004054e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040553  lea     rcx, [rsp+2D8h+var_60]
0x18004055b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180040560  mov     rdx, rax
0x180040563  mov     r8, r13
0x180040566  lea     rcx, [rsp+2D8h+var_288]
0x18004056b  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180040570  mov     rcx, [rsp+2D8h]; this
0x180040578  test    eax, eax
0x18004057a  jns     short loc_180040591
0x18004057c  mov     r9d, eax; char *
0x18004057f  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180040586  mov     edx, 184h; void *
0x18004058b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180040591  lea     rcx, [rsp+2D8h+var_60]
0x180040599  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004059e  lea     rdx, [rdi+50h]
0x1800405a2  mov     r9d, [rdi+84h]
0x1800405a9  lea     r8, [rsp+2D8h+var_288]
0x1800405ae  mov     rcx, r14; unsigned __int16 *
0x1800405b1  call    ?LaunchMitigationProcessUnderJobManagement@LaunchExePrivilegedAction@Mitigation@Internal@Windows@@YAJPEBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@1K@Z; Windows::Internal::Mitigation::LaunchExePrivilegedAction::LaunchMitigationProcessUnderJobManagement(ushort const *,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &,ulong)
0x1800405b6  mov     rcx, [rsp+2D8h]; this
0x1800405be  test    eax, eax
0x1800405c0  jns     short loc_1800405D6
0x1800405c2  mov     r9d, eax; char *
0x1800405c5  lea     r8, aOnecoreBaseDia_11; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800405cc  mov     edx, 18Ch; void *
0x1800405d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800405d6  mov     eax, [rsi+15Ch]
0x1800405dc  add     eax, 7F440502h
0x1800405e1  cmp     eax, 1
0x1800405e4  ja      short loc_1800405FB
0x1800405e6  cmp     dword ptr [rsi+74h], 1
0x1800405ea  jz      short loc_1800405FB
0x1800405ec  mov     edx, 80BBFA24h
0x1800405f1  mov     ecx, 15h
0x1800405f6  call    ?DispatchEvent@MitigationExecutionContext@@SAXW4MitigationError@@J@Z; MitigationExecutionContext::DispatchEvent(MitigationError,long)
0x1800405fb  mov     rdx, [rdi+0A8h]
0x180040602  test    rdx, rdx
0x180040605  jz      short loc_180040655
0x180040607  mov     r9d, [rsi+15Ch]
0x18004060e  mov     ecx, r15d
0x180040611  cmp     ecx, [rdi+0B0h]
0x180040617  jnb     short loc_180040655
0x180040619  mov     eax, ecx
0x18004061b  imul    r8, rax, 0CCh
0x180040622  cmp     [r8+rdx], r9d
0x180040626  jnz     short loc_1800406A4
0x180040628  mov     byte ptr [rsi+159h], 1
0x18004062f  mov     rdx, [rdi+0A8h]
0x180040636  add     rdx, 4
0x18004063a  add     rdx, r8
0x18004063d  mov     rcx, rdx
0x180040640  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180040645  lea     rcx, [rsi+160h]
0x18004064c  mov     r8, rax
0x18004064f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180040654  nop
0x180040655  lea     rcx, [rsp+2D8h+var_288]
0x18004065a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004065f  nop
0x180040660  lea     rcx, [rsp+2D8h+var_268]
0x180040665  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004066a  nop
0x18004066b  lea     rcx, [rsp+2D8h+var_250]
0x180040673  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180040678  nop
0x180040679  lea     rcx, [rsp+2D8h+var_270]
0x18004067e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040683  mov     rcx, [rsp+2D8h+var_40]
0x18004068b  xor     rcx, rsp; StackCookie
0x18004068e  call    __security_check_cookie
0x180040693  add     rsp, 2A8h
0x18004069a  pop     r15
0x18004069c  pop     r14
0x18004069e  pop     r13
0x1800406a0  pop     rdi
0x1800406a1  pop     rsi
0x1800406a2  pop     rbx
0x1800406a3  retn
0x1800406a4  inc     ecx
0x1800406a6  jmp     loc_180040611
```
