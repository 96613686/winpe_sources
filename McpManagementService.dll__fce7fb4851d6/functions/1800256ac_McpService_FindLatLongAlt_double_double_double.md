# McpService::FindLatLongAlt(double &,double &,double &)

- ea: `0x1800256ac`
- end: `0x180025a7a`
- name: `?FindLatLongAlt@McpService@@AEAAJAEAN00@Z`
- size: `974`
- prototype: `__int64 __fastcall(McpService *__hidden this, double *, double *, double *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026f10`

## callees

- `0x180003a60`
- `0x180009fc0`
- `0x18000c4cc`
- `0x1800133a0`
- `0x1800194dc`
- `0x18001b0e8`
- `0x180022b04`
- `0x180024f40`
- `0x1800251d0`
- `0x1800256ac`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180025a56`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180025a56`

## string_xrefs

- `0x18002577a`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x1800257db`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x180025852`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x180025884`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x1800258db`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x180025945`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`
- `0x18002599f`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall McpService::FindLatLongAlt(McpService *this, double *a2, double *a3, double *a4)
{
  void **v9; // rax
  void *v10; // rdx
  int v11; // ebx
  const char *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rdi
  DWORD v17; // edx
  int v18; // r8d
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  const char *v25; // rax
  __int64 v26; // rdx
  int v27; // [rsp+20h] [rbp-69h]
  const char *v28; // [rsp+28h] [rbp-61h]
  _BYTE v29[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-51h] BYREF
  __int64 v31; // [rsp+40h] [rbp-49h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-41h] BYREF
  __int64 v33; // [rsp+50h] [rbp-39h] BYREF
  __int64 v34; // [rsp+58h] [rbp-31h] BYREF
  __int64 v35; // [rsp+60h] [rbp-29h] BYREF
  __int128 v36; // [rsp+68h] [rbp-21h] BYREF
  __int64 v37; // [rsp+78h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v39; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( CloudPrint::CloudPrintHelper::IsMockEnabled() )
    return 2147500033LL;
  v9 = (void **)*((_QWORD *)this + 5);
  if ( v9 )
    v10 = *v9;
  else
    v10 = 0;
  PrintCore::ImpersonateUserRAII::ImpersonateUserRAII((PrintCore::ImpersonateUserRAII *)v29, v10);
  v35 = 0;
  v39 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Geolocation.Geolocator",
    0x27u,
    0x26u);
  v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(
          v39,
          &v35);
  if ( v11 < 0 )
  {
    v12 = "Failed to IGeolocator instance";
    v13 = 477;
LABEL_10:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)(unsigned int)v11,
      (int)v12,
      v28);
    goto LABEL_33;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 56LL))(v35, 1);
  if ( v11 < 0 )
  {
    v12 = "Failed to set geolocation accuracy";
    v13 = 480;
    goto LABEL_10;
  }
  v30 = 0;
  v14 = v35;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v35 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v11 = v15(v14, &v30);
  if ( v11 >= 0 )
  {
    v31 = 0;
    v29[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    v16 = v30;
    v11 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(
            v30,
            v17,
            v18,
            v29);
    if ( v11 >= 0 )
      v11 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v16)[8])(
              v16,
              &v31);
    if ( v11 >= 0 )
    {
      if ( v29[0] )
      {
        v11 = -2147023436;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F0,
          (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
          (const char *)0x800705B4LL,
          v27);
      }
      else
      {
        v32 = 0;
        v19 = v31;
        v20 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v31 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        v11 = v20(v19, &v32);
        if ( v11 >= 0 )
        {
          v33 = 0;
          v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v32;
          v22 = **v32;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
          v11 = v22(v21, &GUID_feea0525_d22c_4d46_b527_0b96066fc7db, &v33);
          if ( v11 >= 0 )
          {
            v34 = 0;
            v23 = v33;
            v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
            v11 = v24(v23, &v34);
            if ( v11 >= 0 )
            {
              v36 = 0;
              v37 = 0;
              v11 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v34 + 48LL))(v34, &v36);
              if ( v11 >= 0 )
              {
                *(_QWORD *)a2 = v36;
                *a3 = *((double *)&v36 + 1);
                *(_QWORD *)a4 = v37;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                v11 = 0;
                goto LABEL_33;
              }
              v25 = "Failed to get BasicGeoposition";
              v26 = 509;
            }
            else
            {
              v25 = "Failed to get IGeopoint";
              v26 = 506;
            }
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)v26,
              (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
              (const char *)(unsigned int)v11,
              (int)v25,
              v28);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          }
          else
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x1F7,
              (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
              (const char *)(unsigned int)v11,
              (int)"Failed to get IGeocoordinateWithPoint",
              v28);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x1F4,
            (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
            (const char *)(unsigned int)v11,
            (int)"Failed to get IGeocoordinate",
            v28);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
        (const char *)(unsigned int)v11,
        (int)"Failed to wait for Geoposition operation",
        v28);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)(unsigned int)v11,
      (int)"Failed to get Geoposition Async",
      v28);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
LABEL_33:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  SetThreadToken(0, 0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800256ac  push    rbp
0x1800256ae  push    rbx
0x1800256af  push    rsi
0x1800256b0  push    rdi
0x1800256b1  push    r14
0x1800256b3  push    r15
0x1800256b5  lea     rbp, [rsp-2Fh]
0x1800256ba  sub     rsp, 0B8h
0x1800256c1  mov     rax, cs:__security_cookie
0x1800256c8  xor     rax, rsp
0x1800256cb  mov     [rbp+57h+var_40], rax
0x1800256cf  mov     r15, r9
0x1800256d2  mov     r14, r8
0x1800256d5  mov     rsi, rdx
0x1800256d8  mov     rbx, rcx
0x1800256db  call    ?IsMockEnabled@CloudPrintHelper@CloudPrint@@SA_NXZ; CloudPrint::CloudPrintHelper::IsMockEnabled(void)
0x1800256e0  test    al, al
0x1800256e2  jz      short loc_1800256EE
0x1800256e4  mov     eax, 80004001h
0x1800256e9  jmp     loc_180025A5E
0x1800256ee  mov     rax, [rbx+28h]
0x1800256f2  test    rax, rax
0x1800256f5  jz      short loc_1800256FC
0x1800256f7  mov     rdx, [rax]
0x1800256fa  jmp     short loc_1800256FE
0x1800256fc  xor     edx, edx; void *
0x1800256fe  lea     rcx, [rbp+57h+var_B0]; this
0x180025702  call    ??0ImpersonateUserRAII@PrintCore@@QEAA@PEAX@Z; PrintCore::ImpersonateUserRAII::ImpersonateUserRAII(void *)
0x180025707  nop
0x180025708  mov     [rbp+57h+var_80], 0
0x180025710  mov     [rbp+57h+var_48], 0
0x180025718  mov     r9d, 26h ; '&'; unsigned int
0x18002571e  lea     r8d, [r9+1]; unsigned int
0x180025722  lea     rdx, ?RuntimeClass_Windows_Devices_Geolocation_Geolocator@@3QBGB; "Windows.Devices.Geolocation.Geolocator"
0x180025729  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002572d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180025732  lea     rdx, [rbp+57h+var_80]
0x180025736  mov     rcx, [rbp+57h+var_48]
0x18002573a  call    ??$ActivateInstance@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeolocator@Geolocation@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeolocator>>)
0x18002573f  mov     ebx, eax
0x180025741  test    eax, eax
0x180025743  jns     short loc_180025753
0x180025745  lea     rax, aFailedToIgeolo; "Failed to IGeolocator instance"
0x18002574c  mov     edx, 1DDh
0x180025751  jmp     short loc_18002577A
0x180025753  mov     rcx, [rbp+57h+var_80]
0x180025757  mov     rax, [rcx]
0x18002575a  mov     edx, 1
0x18002575f  mov     rax, [rax+38h]
0x180025763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025768  mov     ebx, eax
0x18002576a  test    eax, eax
0x18002576c  jns     short loc_180025797
0x18002576e  lea     rax, aFailedToSetGeo; "Failed to set geolocation accuracy"
0x180025775  mov     edx, 1E0h; void *
0x18002577a  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180025781  mov     r9d, ebx; char *
0x180025784  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180025789  mov     rcx, [rbp+5Fh]; this
0x18002578d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025792  jmp     loc_180025A48
0x180025797  mov     [rbp+57h+var_A8], 0
0x18002579f  mov     rdi, [rbp+57h+var_80]
0x1800257a3  mov     rax, [rdi]
0x1800257a6  mov     rbx, [rax+68h]
0x1800257aa  lea     rcx, [rbp+57h+var_A8]
0x1800257ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800257b3  lea     rdx, [rbp+57h+var_A8]
0x1800257b7  mov     rcx, rdi
0x1800257ba  mov     rax, rbx
0x1800257bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800257c2  mov     ebx, eax
0x1800257c4  test    eax, eax
0x1800257c6  jns     short loc_1800257FB
0x1800257c8  mov     rcx, [rbp+5Fh]; this
0x1800257cc  lea     rax, aFailedToGetGeo; "Failed to get Geoposition Async"
0x1800257d3  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800257d8  mov     r9d, ebx; char *
0x1800257db  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800257e2  mov     edx, 1E4h; void *
0x1800257e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800257ec  nop
0x1800257ed  lea     rcx, [rbp+57h+var_A8]
0x1800257f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800257f6  jmp     loc_180025A48
0x1800257fb  mov     [rbp+57h+var_A0], 0
0x180025803  mov     [rbp+57h+var_B0], 0
0x180025807  lea     rcx, [rbp+57h+var_A0]
0x18002580b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025810  mov     rdi, [rbp+57h+var_A8]
0x180025814  lea     r9, [rbp+57h+var_B0]
0x180025818  mov     rcx, rdi
0x18002581b  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *>(Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geoposition *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180025820  mov     ebx, eax
0x180025822  test    eax, eax
0x180025824  js      short loc_18002583B
0x180025826  mov     rax, [rdi]
0x180025829  lea     rdx, [rbp+57h+var_A0]
0x18002582d  mov     rcx, rdi
0x180025830  mov     rax, [rax+40h]
0x180025834  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025839  mov     ebx, eax
0x18002583b  test    ebx, ebx
0x18002583d  jns     short loc_180025872
0x18002583f  mov     rcx, [rbp+5Fh]; this
0x180025843  lea     rax, aFailedToWaitFo; "Failed to wait for Geoposition operatio"...
0x18002584a  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18002584f  mov     r9d, ebx; char *
0x180025852  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180025859  mov     edx, 1EBh; void *
0x18002585e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025863  nop
0x180025864  lea     rcx, [rbp+57h+var_A0]
0x180025868  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002586d  jmp     loc_1800257ED
0x180025872  cmp     [rbp+57h+var_B0], 0
0x180025876  jz      short loc_180025897
0x180025878  mov     rcx, [rbp+5Fh]; this
0x18002587c  mov     ebx, 800705B4h
0x180025881  mov     r9d, ebx; char *
0x180025884  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002588b  mov     edx, 1F0h; void *
0x180025890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025895  jmp     short loc_180025864
0x180025897  mov     [rbp+57h+var_98], 0
0x18002589f  mov     rdi, [rbp+57h+var_A0]
0x1800258a3  mov     rax, [rdi]
0x1800258a6  mov     rbx, [rax+30h]
0x1800258aa  lea     rcx, [rbp+57h+var_98]
0x1800258ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800258b3  lea     rdx, [rbp+57h+var_98]
0x1800258b7  mov     rcx, rdi
0x1800258ba  mov     rax, rbx
0x1800258bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c2  mov     ebx, eax
0x1800258c4  test    eax, eax
0x1800258c6  jns     short loc_1800258FB
0x1800258c8  mov     rcx, [rbp+5Fh]; this
0x1800258cc  lea     rax, aFailedToGetIge_1; "Failed to get IGeocoordinate"
0x1800258d3  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800258d8  mov     r9d, ebx; char *
0x1800258db  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800258e2  mov     edx, 1F4h; void *
0x1800258e7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800258ec  nop
0x1800258ed  lea     rcx, [rbp+57h+var_98]
0x1800258f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800258f6  jmp     loc_180025864
0x1800258fb  mov     [rbp+57h+var_90], 0
0x180025903  mov     rbx, [rbp+57h+var_98]
0x180025907  mov     rax, [rbx]
0x18002590a  mov     rdi, [rax]
0x18002590d  lea     rcx, [rbp+57h+var_90]
0x180025911  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025916  lea     r8, [rbp+57h+var_90]
0x18002591a  lea     rdx, _GUID_feea0525_d22c_4d46_b527_0b96066fc7db
0x180025921  mov     rcx, rbx
0x180025924  mov     rax, rdi
0x180025927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002592c  mov     ebx, eax
0x18002592e  test    eax, eax
0x180025930  jns     short loc_180025962
0x180025932  mov     rcx, [rbp+5Fh]; this
0x180025936  lea     rax, aFailedToGetIge_0; "Failed to get IGeocoordinateWithPoint"
0x18002593d  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180025942  mov     r9d, ebx; char *
0x180025945  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002594c  mov     edx, 1F7h; void *
0x180025951  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180025956  nop
0x180025957  lea     rcx, [rbp+57h+var_90]
0x18002595b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025960  jmp     short loc_1800258ED
0x180025962  mov     [rbp+57h+var_88], 0
0x18002596a  mov     rdi, [rbp+57h+var_90]
0x18002596e  mov     rax, [rdi]
0x180025971  mov     rbx, [rax+30h]
0x180025975  lea     rcx, [rbp+57h+var_88]
0x180025979  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002597e  lea     rdx, [rbp+57h+var_88]
0x180025982  mov     rcx, rdi
0x180025985  mov     rax, rbx
0x180025988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002598d  mov     ebx, eax
0x18002598f  test    eax, eax
0x180025991  jns     short loc_1800259C3
0x180025993  lea     rax, aFailedToGetIge; "Failed to get IGeopoint"
0x18002599a  mov     edx, 1FAh; void *
0x18002599f  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800259a6  mov     r9d, ebx; char *
0x1800259a9  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800259ae  mov     rcx, [rbp+5Fh]; this
0x1800259b2  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800259b7  nop
0x1800259b8  lea     rcx, [rbp+57h+var_88]
0x1800259bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800259c1  jmp     short loc_180025957
0x1800259c3  xorps   xmm0, xmm0
0x1800259c6  xor     eax, eax
0x1800259c8  movups  [rbp+57h+var_78], xmm0
0x1800259cc  mov     [rbp+57h+var_68], rax
0x1800259d0  mov     rcx, [rbp+57h+var_88]
0x1800259d4  mov     rax, [rcx]
0x1800259d7  lea     rdx, [rbp+57h+var_78]
0x1800259db  mov     rax, [rax+30h]
0x1800259df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259e4  mov     ebx, eax
0x1800259e6  test    eax, eax
0x1800259e8  jns     short loc_1800259F8
0x1800259ea  lea     rax, aFailedToGetBas; "Failed to get BasicGeoposition"
0x1800259f1  mov     edx, 1FDh
0x1800259f6  jmp     short loc_18002599F
0x1800259f8  movsd   xmm0, qword ptr [rbp+57h+var_78]
0x1800259fd  movsd   qword ptr [rsi], xmm0
0x180025a01  movsd   xmm1, qword ptr [rbp+57h+var_78+8]
0x180025a06  movsd   qword ptr [r14], xmm1
0x180025a0b  movsd   xmm0, [rbp+57h+var_68]
0x180025a10  movsd   qword ptr [r15], xmm0
0x180025a15  lea     rcx, [rbp+57h+var_88]
0x180025a19  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a1e  nop
0x180025a1f  lea     rcx, [rbp+57h+var_90]
0x180025a23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a28  nop
0x180025a29  lea     rcx, [rbp+57h+var_98]
0x180025a2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a32  nop
0x180025a33  lea     rcx, [rbp+57h+var_A0]
0x180025a37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a3c  nop
0x180025a3d  lea     rcx, [rbp+57h+var_A8]
0x180025a41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a46  xor     ebx, ebx
0x180025a48  lea     rcx, [rbp+57h+var_80]
0x180025a4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025a51  nop
0x180025a52  xor     edx, edx; Token
0x180025a54  xor     ecx, ecx; Thread
0x180025a56  call    cs:__imp_SetThreadToken
0x180025a5c  mov     eax, ebx
0x180025a5e  mov     rcx, [rbp+57h+var_40]
0x180025a62  xor     rcx, rsp; StackCookie
0x180025a65  call    __security_check_cookie
0x180025a6a  add     rsp, 0B8h
0x180025a71  pop     r15
0x180025a73  pop     r14
0x180025a75  pop     rdi
0x180025a76  pop     rsi
0x180025a77  pop     rbx
0x180025a78  pop     rbp
0x180025a79  retn
```
