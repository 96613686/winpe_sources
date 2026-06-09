# GetServicingStatusOneCore(FeatureClient const * const,StoreStyle,ServicingStatusFlags * const)

- ea: `0x1800196d8`
- end: `0x180019deb`
- name: `?GetServicingStatusOneCore@@YAXQEBUFeatureClient@@W4StoreStyle@@QEAW4ServicingStatusFlags@@@Z`
- size: `1811`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d6c0`

## callees

- `0x1800031d0`
- `0x180009750`
- `0x18000c468`
- `0x18000f614`
- `0x18000f874`
- `0x18000fe74`
- `0x180012418`
- `0x18001695c`
- `0x1800196d8`
- `0x18002bc54`
- `0x18002dd20`
- `0x18002ea4c`
- `0x1801bd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b7c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180019b6c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180019b6c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800198b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800198b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180019ae1`
- `OLEAUT32!__imp_SysFreeString` at `0x180019bfb`
- `OLEAUT32!__imp_SysFreeString` at `0x180019c3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cc3`
- `OLEAUT32!__imp_SysFreeString` at `0x180019ae1`
- `OLEAUT32!__imp_SysFreeString` at `0x180019bfb`
- `OLEAUT32!__imp_SysFreeString` at `0x180019c3e`
- `OLEAUT32!__imp_SysFreeString` at `0x180019cc3`

## string_xrefs

- `0x1800197af`: `UpdateAPI.dll`
- `0x180019766`: `Failed to get current running path`
- `0x1800197fe`: `GetUpdateResults`
- `0x1800198c6`: `Failed to start USO session to query update state`
- `0x18001991d`: `Failed to get USO update manager to query update state`
- `0x180019980`: `Failed to get list of applicable updates from USO to query update state`
- `0x1800199f5`: `Failed to get count of applicable updates from USO to query update state`
- `0x180019d2d`: `Failed to get update object from USO to query update state`
- `0x180019ca8`: `Failed to get update title from USO to query update state`
- `0x180019c23`: `Failed to get update state from USO`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall GetServicingStatusOneCore(const struct FeatureClient *a1, __int64 a2, int *a3)
{
  int RunningDllPath; // eax
  int v6; // edi
  __int64 v7; // rdx
  __int128 *v8; // rax
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  int v12; // edi
  HRESULT v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  unsigned int v19; // esi
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  OLECHAR *v28; // rcx
  int *ppv; // [rsp+28h] [rbp-99h]
  HMODULE hLibModule; // [rsp+48h] [rbp-79h] BYREF
  int v31[2]; // [rsp+50h] [rbp-71h] BYREF
  __int64 v32; // [rsp+58h] [rbp-69h]
  __int64 v33; // [rsp+60h] [rbp-61h]
  __int64 *v34; // [rsp+68h] [rbp-59h] BYREF
  __int64 *v35; // [rsp+70h] [rbp-51h] BYREF
  LPVOID v36; // [rsp+78h] [rbp-49h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-41h] BYREF
  int v38; // [rsp+88h] [rbp-39h] BYREF
  unsigned int v39; // [rsp+8Ch] [rbp-35h] BYREF
  _QWORD v40[2]; // [rsp+90h] [rbp-31h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-11h]
  unsigned __int64 v43; // [rsp+B8h] [rbp-9h]
  int v44; // [rsp+C0h] [rbp-1h] BYREF
  __int128 v45; // [rsp+C8h] [rbp+7h] BYREF
  __int64 v46; // [rsp+D8h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  v33 = -2;
  if ( a3 )
    *a3 = 0;
  ValidateClient(a1);
  hLibModule = 0;
  bstrString = 0;
  v41 = 0;
  v42 = 0;
  v43 = 7;
  LOWORD(v41) = 0;
  RunningDllPath = GetRunningDllPath(&v41);
  v6 = RunningDllPath;
  if ( RunningDllPath < 0 )
  {
    LODWORD(v40[0]) = RunningDllPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get current running path");
      *(_QWORD *)v31 = v40;
      ppv = v31;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
  }
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x351,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      (const char *)(unsigned int)v6,
      (int)ppv);
  *(_QWORD *)v31 = L"UpdateAPI.dll";
  v32 = 13;
  v8 = &v41;
  if ( v43 > 7 )
    v8 = (__int128 *)v41;
  v40[0] = v8;
  v40[1] = v42;
  v9 = CreatePath(&v45, v40, v31);
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v9 = *(_QWORD *)v9;
  v10 = LoadLibraryAndFunction(
          (const wchar_t *const)v9,
          "GetUpdateResults",
          &hLibModule,
          (__int64 (**)(void))&bstrString);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x358,
      (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
      (const char *)(unsigned int)v10,
      (int)ppv);
  std::wstring::~wstring(&v45);
  v44 = 0;
  v38 = 5;
  v11 = ((__int64 (__fastcall *)(int *, int *))bstrString)(&v38, &v44);
  if ( v11 >= 0 )
  {
    if ( v38 == 2 )
    {
      v12 = 17;
    }
    else
    {
      v12 = 8;
      if ( v38 != 7 )
        v12 = 1;
    }
    if ( (*((_BYTE *)a1 + 160) & 1) != 0 || (v12 & 1) == 0 )
    {
      if ( a3 )
        *a3 = v12;
    }
    else
    {
      v36 = 0;
      v13 = CoCreateInstance(
              &GUID_b91d5831_b1bd_4608_8198_d72e155020f7,
              0,
              4u,
              &GUID_c57692f8_8f5f_47cb_9381_34329b40285a,
              &v36);
      if ( v13 >= 0 )
      {
        v35 = 0;
        v14 = *(_QWORD *)v36;
        v35 = 0;
        v15 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, __int64 **))(v14 + 24))(
                v36,
                *(_QWORD *)a1,
                L"FodProvider",
                &v35);
        if ( v15 >= 0 )
        {
          v34 = 0;
          v16 = *v35;
          v34 = 0;
          v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v16 + 48))(v35, &v34);
          if ( v17 >= 0 )
          {
            v39 = 0;
            v18 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v34 + 32))(v34, &v39);
            if ( v18 >= 0 )
            {
              v19 = 0;
              if ( v39 )
              {
                while ( 1 )
                {
                  v40[0] = 0;
                  v20 = *v34;
                  v40[0] = 0;
                  v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *))(v20 + 24))(v34, v19, v40);
                  if ( v21 < 0 )
                    break;
                  bstrString = 0;
                  v22 = *(_QWORD *)v40[0];
                  bstrString = 0;
                  v23 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(v22 + 24))(v40[0], &bstrString);
                  if ( v23 < 0 )
                  {
                    LogAdapter::TraceAtLevelHr<long,>(
                      1,
                      (unsigned int)v23,
                      "Failed to get update title from USO to query update state");
                    if ( bstrString )
                      SysFreeString(bstrString);
                    if ( v40[0] )
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
                    if ( v34 )
                      (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
                    if ( v35 )
                      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
                    if ( v36 )
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
                    goto LABEL_67;
                  }
                  v45 = 0;
                  v46 = 0;
                  v24 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v40[0] + 120LL))(v40[0], &v45);
                  if ( v24 < 0 )
                  {
                    LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)v24, "Failed to get update state from USO");
                    if ( bstrString )
                      SysFreeString(bstrString);
                    if ( v40[0] )
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
                    if ( v34 )
                      (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
                    if ( v35 )
                      (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
                    if ( v36 )
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
                    goto LABEL_67;
                  }
                  if ( HIDWORD(v45) )
                  {
                    v28 = bstrString;
                    *(_QWORD *)v31 = bstrString;
                    if ( *(_QWORD *)&LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *,unsigned long>(
                        LogAdapter::g_Logger,
                        v25,
                        v26,
                        v27,
                        (__int64)&v45,
                        (__int64)v31,
                        (__int64)&v46);
                      v28 = bstrString;
                    }
                    v12 = 2;
                    if ( v28 )
                      SysFreeString(v28);
                    if ( v40[0] )
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
                    goto LABEL_59;
                  }
                  if ( bstrString )
                    SysFreeString(bstrString);
                  if ( v40[0] )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
                  if ( ++v19 >= v39 )
                    goto LABEL_59;
                }
                LogAdapter::TraceAtLevelHr<long,>(
                  1,
                  (unsigned int)v21,
                  "Failed to get update object from USO to query update state");
                if ( v40[0] )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v40[0] + 16LL))(v40[0]);
                if ( v34 )
                  (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
                if ( v35 )
                  (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
                if ( v36 )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
              }
              else
              {
LABEL_59:
                if ( a3 )
                  *a3 = v12;
                if ( v34 )
                  (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
                if ( v35 )
                  (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
                if ( v36 )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
              }
            }
            else
            {
              LogAdapter::TraceAtLevelHr<long,>(
                1,
                (unsigned int)v18,
                "Failed to get count of applicable updates from USO to query update state");
              if ( v34 )
                (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
              if ( v35 )
                (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
              if ( v36 )
                (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
            }
          }
          else
          {
            LogAdapter::TraceAtLevelHr<long,>(
              1,
              (unsigned int)v17,
              "Failed to get list of applicable updates from USO to query update state");
            if ( v34 )
              (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
            if ( v35 )
              (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
            if ( v36 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
          }
        }
        else
        {
          LogAdapter::TraceAtLevelHr<long,>(
            1,
            (unsigned int)v15,
            "Failed to get USO update manager to query update state");
          if ( v35 )
            (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
          if ( v36 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
        }
      }
      else
      {
        LogAdapter::TraceAtLevelHr<long,>(1, (unsigned int)v13, "Failed to start USO session to query update state");
        if ( v36 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
      }
    }
  }
  else
  {
    if ( v11 != -2147024726 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35F,
        (unsigned int)"onecore\\base\\servicing\\uapi\\lib\\query_onecore.cpp",
        (const char *)(unsigned int)v11,
        (int)ppv);
    if ( a3 )
      *a3 = 2;
  }
LABEL_67:
  std::wstring::~wstring(&v41);
  if ( hLibModule )
  {
    if ( !FreeLibrary(hLibModule) )
    {
      GetLastError();
      __fastfail(7u);
    }
  }
}

```

## disassembly

```asm
0x1800196d8  mov     rax, rsp
0x1800196db  push    rbp
0x1800196dc  push    rdi
0x1800196dd  push    r12
0x1800196df  push    r13
0x1800196e1  push    r15
0x1800196e3  lea     rbp, [rax-5Fh]
0x1800196e7  sub     rsp, 0F0h
0x1800196ee  mov     [rbp+57h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800196f6  mov     [rax+10h], rbx
0x1800196fa  mov     [rax+20h], rsi
0x1800196fe  mov     rax, cs:__security_cookie
0x180019705  xor     rax, rsp
0x180019708  mov     [rbp+57h+var_30], rax
0x18001970c  mov     rbx, r8
0x18001970f  mov     rsi, rcx
0x180019712  xor     r15d, r15d
0x180019715  test    r8, r8
0x180019718  jz      short loc_18001971D
0x18001971a  mov     [r8], r15d
0x18001971d  call    ?ValidateClient@@YAXQEBUFeatureClient@@@Z; ValidateClient(FeatureClient const * const)
0x180019722  mov     [rbp+57h+hLibModule], r15
0x180019726  mov     [rbp+57h+bstrString], r15
0x18001972a  xorps   xmm0, xmm0
0x18001972d  movups  [rbp+57h+var_78], xmm0
0x180019731  mov     [rbp+57h+var_68], r15
0x180019735  mov     r13d, 7
0x18001973b  mov     [rbp+57h+var_60], r13
0x18001973f  mov     word ptr [rbp+57h+var_78], r15w
0x180019744  lea     rcx, [rbp+57h+var_78]
0x180019748  call    ?GetRunningDllPath@@YAJPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetRunningDllPath(std::wstring *)
0x18001974d  mov     edi, eax
0x18001974f  lea     r12d, [r13-6]
0x180019753  test    eax, eax
0x180019755  jns     short loc_1800197A3
0x180019757  mov     dword ptr [rbp+57h+var_88], eax
0x18001975a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180019761  test    rcx, rcx
0x180019764  jz      short loc_1800197A3
0x180019766  lea     r9, aFailedToGetCur_1; "Failed to get current running path"
0x18001976d  xor     edx, edx
0x18001976f  lea     r8d, [r13-4]
0x180019773  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180019778  lea     rax, [rbp+57h+var_88]
0x18001977c  mov     qword ptr [rbp+57h+var_C8], rax
0x180019780  lea     rax, [rbp+57h+var_C8]
0x180019784  mov     [rsp+110h+ppv], rax; int
0x180019789  lea     r9, asc_1801CAFB4; ": {}"
0x180019790  lea     r8d, [r13-4]
0x180019794  mov     dl, r12b
0x180019797  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001979e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800197a3  mov     rcx, [rbp+5Fh]; this
0x1800197a7  test    edi, edi
0x1800197a9  js      loc_180019DC1
0x1800197af  lea     rax, aUpdateapiDll_0; "UpdateAPI.dll"
0x1800197b6  mov     qword ptr [rbp+57h+var_C8], rax
0x1800197ba  mov     [rbp+57h+var_C0], 0Dh
0x1800197c2  lea     rax, [rbp+57h+var_78]
0x1800197c6  cmp     [rbp+57h+var_60], r13
0x1800197ca  cmova   rax, qword ptr [rbp+57h+var_78]
0x1800197cf  mov     [rbp+57h+var_88], rax
0x1800197d3  mov     rax, [rbp+57h+var_68]
0x1800197d7  mov     [rbp+57h+var_80], rax
0x1800197db  lea     r8, [rbp+57h+var_C8]
0x1800197df  lea     rdx, [rbp+57h+var_88]
0x1800197e3  lea     rcx, [rbp+57h+var_50]
0x1800197e7  call    ?CreatePath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@2@0@Z; CreatePath(std::wstring_view const &,std::wstring_view const &)
0x1800197ec  nop
0x1800197ed  cmp     [rax+18h], r13
0x1800197f1  jbe     short loc_1800197F6
0x1800197f3  mov     rax, [rax]
0x1800197f6  lea     r9, [rbp+57h+bstrString]; __int64 (**)(void)
0x1800197fa  lea     r8, [rbp+57h+hLibModule]; HINSTANCE *
0x1800197fe  lea     rdx, aGetupdateresul; "GetUpdateResults"
0x180019805  mov     rcx, rax; wchar_t *
0x180019808  call    ?LoadLibraryAndFunction@@YAJQEB_WQEBDPEAPEAUHINSTANCE__@@PEAP6A_JXZ@Z; LoadLibraryAndFunction(wchar_t const * const,char const * const,HINSTANCE__ * *,__int64 (**)(void))
0x18001980d  mov     rcx, [rbp+5Fh]; this
0x180019811  test    eax, eax
0x180019813  js      loc_180019DD6
0x180019819  lea     rcx, [rbp+57h+var_50]; void *
0x18001981d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019822  mov     [rbp+57h+var_58], r15d
0x180019826  mov     [rbp+57h+var_90], 5
0x18001982d  lea     rdx, [rbp+57h+var_58]
0x180019831  lea     rcx, [rbp+57h+var_90]
0x180019835  mov     rax, [rbp+57h+bstrString]
0x180019839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001983e  test    eax, eax
0x180019840  jns     short loc_180019865
0x180019842  mov     rcx, [rbp+5Fh]; this
0x180019846  cmp     eax, 800700AAh
0x18001984b  jnz     loc_180019DAC
0x180019851  test    rbx, rbx
0x180019854  jz      loc_180019B59
0x18001985a  mov     dword ptr [rbx], 2
0x180019860  jmp     loc_180019B59
0x180019865  cmp     [rbp+57h+var_90], 2
0x180019869  jz      short loc_18001987A
0x18001986b  mov     edi, 8
0x180019870  cmp     [rbp+57h+var_90], r13d
0x180019874  cmovnz  edi, r12d
0x180019878  jmp     short loc_18001987F
0x18001987a  mov     edi, 11h
0x18001987f  test    [rsi+0A0h], r12b
0x180019886  jnz     loc_180019D9C
0x18001988c  test    r12b, dil
0x18001988f  jz      loc_180019D9C
0x180019895  mov     [rbp+57h+var_A0], r15
0x180019899  lea     rax, [rbp+57h+var_A0]
0x18001989d  mov     [rsp+110h+ppv], rax; ppv
0x1800198a2  lea     r9, _GUID_c57692f8_8f5f_47cb_9381_34329b40285a; riid
0x1800198a9  xor     edx, edx; pUnkOuter
0x1800198ab  lea     r8d, [rdx+4]; dwClsContext
0x1800198af  lea     rcx, _GUID_b91d5831_b1bd_4608_8198_d72e155020f7; rclsid
0x1800198b6  call    cs:__imp_CoCreateInstance
0x1800198bd  nop     dword ptr [rax+rax+00h]
0x1800198c2  test    eax, eax
0x1800198c4  jns     short loc_1800198F3
0x1800198c6  lea     r8, aFailedToStartU; "Failed to start USO session to query up"...
0x1800198cd  mov     edx, eax
0x1800198cf  mov     ecx, r12d
0x1800198d2  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800198d7  nop
0x1800198d8  mov     rcx, [rbp+57h+var_A0]
0x1800198dc  test    rcx, rcx
0x1800198df  jz      short loc_1800198EE
0x1800198e1  mov     rax, [rcx]
0x1800198e4  mov     rax, [rax+10h]
0x1800198e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800198ed  nop
0x1800198ee  jmp     loc_180019B59
0x1800198f3  mov     [rbp+57h+var_A8], r15
0x1800198f7  mov     rcx, [rbp+57h+var_A0]
0x1800198fb  mov     rax, [rcx]
0x1800198fe  mov     [rbp+57h+var_A8], r15
0x180019902  lea     r9, [rbp+57h+var_A8]
0x180019906  lea     r8, aFodprovider; "FodProvider"
0x18001990d  mov     rdx, [rsi]
0x180019910  mov     rax, [rax+18h]
0x180019914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019919  test    eax, eax
0x18001991b  jns     short loc_180019960
0x18001991d  lea     r8, aFailedToGetUso; "Failed to get USO update manager to que"...
0x180019924  mov     edx, eax
0x180019926  mov     ecx, r12d
0x180019929  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x18001992e  nop
0x18001992f  mov     rcx, [rbp+57h+var_A8]
0x180019933  test    rcx, rcx
0x180019936  jz      short loc_180019945
0x180019938  mov     rax, [rcx]
0x18001993b  mov     rax, [rax+10h]
0x18001993f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019944  nop
0x180019945  mov     rcx, [rbp+57h+var_A0]
0x180019949  test    rcx, rcx
0x18001994c  jz      short loc_18001995B
0x18001994e  mov     rax, [rcx]
0x180019951  mov     rax, [rax+10h]
0x180019955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001995a  nop
0x18001995b  jmp     loc_180019B59
0x180019960  mov     [rbp+57h+var_B0], r15
0x180019964  mov     rcx, [rbp+57h+var_A8]
0x180019968  mov     rax, [rcx]
0x18001996b  mov     [rbp+57h+var_B0], r15
0x18001996f  lea     rdx, [rbp+57h+var_B0]
0x180019973  mov     rax, [rax+30h]
0x180019977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001997c  test    eax, eax
0x18001997e  jns     short loc_1800199D9
0x180019980  lea     r8, aFailedToGetLis; "Failed to get list of applicable update"...
0x180019987  mov     edx, eax
0x180019989  mov     ecx, r12d
0x18001998c  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180019991  nop
0x180019992  mov     rcx, [rbp+57h+var_B0]
0x180019996  test    rcx, rcx
0x180019999  jz      short loc_1800199A8
0x18001999b  mov     rax, [rcx]
0x18001999e  mov     rax, [rax+10h]
0x1800199a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199a7  nop
0x1800199a8  mov     rcx, [rbp+57h+var_A8]
0x1800199ac  test    rcx, rcx
0x1800199af  jz      short loc_1800199BE
0x1800199b1  mov     rax, [rcx]
0x1800199b4  mov     rax, [rax+10h]
0x1800199b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199bd  nop
0x1800199be  mov     rcx, [rbp+57h+var_A0]
0x1800199c2  test    rcx, rcx
0x1800199c5  jz      short loc_1800199D4
0x1800199c7  mov     rax, [rcx]
0x1800199ca  mov     rax, [rax+10h]
0x1800199ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199d3  nop
0x1800199d4  jmp     loc_180019B59
0x1800199d9  mov     [rbp+57h+var_8C], r15d
0x1800199dd  mov     rcx, [rbp+57h+var_B0]
0x1800199e1  mov     rax, [rcx]
0x1800199e4  lea     rdx, [rbp+57h+var_8C]
0x1800199e8  mov     rax, [rax+20h]
0x1800199ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199f1  test    eax, eax
0x1800199f3  jns     short loc_180019A4E
0x1800199f5  lea     r8, aFailedToGetCou; "Failed to get count of applicable updat"...
0x1800199fc  mov     edx, eax
0x1800199fe  mov     ecx, r12d
0x180019a01  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180019a06  nop
0x180019a07  mov     rcx, [rbp+57h+var_B0]
0x180019a0b  test    rcx, rcx
0x180019a0e  jz      short loc_180019A1D
0x180019a10  mov     rax, [rcx]
0x180019a13  mov     rax, [rax+10h]
0x180019a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a1c  nop
0x180019a1d  mov     rcx, [rbp+57h+var_A8]
0x180019a21  test    rcx, rcx
0x180019a24  jz      short loc_180019A33
0x180019a26  mov     rax, [rcx]
0x180019a29  mov     rax, [rax+10h]
0x180019a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a32  nop
0x180019a33  mov     rcx, [rbp+57h+var_A0]
0x180019a37  test    rcx, rcx
0x180019a3a  jz      short loc_180019A49
0x180019a3c  mov     rax, [rcx]
0x180019a3f  mov     rax, [rax+10h]
0x180019a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a48  nop
0x180019a49  jmp     loc_180019B59
0x180019a4e  mov     esi, r15d
0x180019a51  cmp     [rbp+57h+var_8C], r15d
0x180019a55  jbe     loc_180019B10
0x180019a5b  mov     [rbp+57h+var_88], r15
0x180019a5f  mov     rcx, [rbp+57h+var_B0]
0x180019a63  mov     rax, [rcx]
0x180019a66  mov     [rbp+57h+var_88], r15
0x180019a6a  lea     r8, [rbp+57h+var_88]
0x180019a6e  mov     edx, esi
0x180019a70  mov     rax, [rax+18h]
0x180019a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a79  test    eax, eax
0x180019a7b  js      loc_180019D2D
0x180019a81  mov     [rbp+57h+bstrString], r15
0x180019a85  mov     rcx, [rbp+57h+var_88]
0x180019a89  mov     rax, [rcx]
0x180019a8c  mov     [rbp+57h+bstrString], r15
0x180019a90  lea     rdx, [rbp+57h+bstrString]
0x180019a94  mov     rax, [rax+18h]
0x180019a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a9d  test    eax, eax
0x180019a9f  js      loc_180019CA8
0x180019aa5  xorps   xmm0, xmm0
0x180019aa8  xor     eax, eax
0x180019aaa  movups  [rbp+57h+var_50], xmm0
0x180019aae  mov     [rbp+57h+var_40], rax
0x180019ab2  mov     rcx, [rbp+57h+var_88]
0x180019ab6  mov     rax, [rcx]
0x180019ab9  lea     rdx, [rbp+57h+var_50]
0x180019abd  mov     rax, [rax+78h]
0x180019ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ac6  test    eax, eax
0x180019ac8  js      loc_180019C23
0x180019ace  cmp     dword ptr [rbp+57h+var_50+0Ch], r15d
0x180019ad2  jnz     loc_180019BB6
0x180019ad8  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180019adc  test    rcx, rcx
0x180019adf  jz      short loc_180019AEE
0x180019ae1  call    cs:__imp_SysFreeString
0x180019ae8  nop     dword ptr [rax+rax+00h]
0x180019aed  nop
0x180019aee  mov     rcx, [rbp+57h+var_88]
0x180019af2  test    rcx, rcx
0x180019af5  jz      short loc_180019B04
0x180019af7  mov     rax, [rcx]
0x180019afa  mov     rax, [rax+10h]
0x180019afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b03  nop
0x180019b04  add     esi, r12d
0x180019b07  cmp     esi, [rbp+57h+var_8C]
0x180019b0a  jb      loc_180019A5B
0x180019b10  test    rbx, rbx
0x180019b13  jz      short loc_180019B17
0x180019b15  mov     [rbx], edi
0x180019b17  mov     rcx, [rbp+57h+var_B0]
0x180019b1b  test    rcx, rcx
0x180019b1e  jz      short loc_180019B2D
0x180019b20  mov     rax, [rcx]
0x180019b23  mov     rax, [rax+10h]
0x180019b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b2c  nop
0x180019b2d  mov     rcx, [rbp+57h+var_A8]
0x180019b31  test    rcx, rcx
0x180019b34  jz      short loc_180019B43
0x180019b36  mov     rax, [rcx]
0x180019b39  mov     rax, [rax+10h]
  ... truncated ...
```
