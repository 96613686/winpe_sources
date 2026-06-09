# CspLoader::CspLoader(_WCM_MEDIA_TYPE,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800b7094`
- end: `0x1800b737e`
- name: `??0CspLoader@@QEAA@W4_WCM_MEDIA_TYPE@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006f8a0`

## callees

- `0x180038538`
- `0x18004e058`
- `0x180051f64`
- `0x180052104`
- `0x180084f50`
- `0x18008534c`
- `0x180085bc4`
- `0x1800b7094`
- `0x1800b7ce8`
- `0x1800b7d1c`
- `0x1800b842c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b71d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b71d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7285`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7228`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b7285`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800b71b3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800b71b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800b710c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800b710c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b7320`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800b7320`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b72d7`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800b72d7`

## string_xrefs

- `0x1800b71fa`: `onecoreuap\net\wcm\service\base\cspmanager\cspmanager.cpp`
- `0x1800b7257`: `onecoreuap\net\wcm\service\base\cspmanager\cspmanager.cpp`
- `0x1800b72b4`: `onecoreuap\net\wcm\service\base\cspmanager\cspmanager.cpp`
- `0x1800b72fb`: `onecoreuap\net\wcm\service\base\cspmanager\cspmanager.cpp`
- `0x1800b7342`: `onecoreuap\net\wcm\service\base\cspmanager\cspmanager.cpp`
- `0x1800b72f4`: `OpenCSManager`
- `0x1800b733b`: `OpenService`
- `0x1800b71f3`: `LoadLibraryEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CspLoader::CspLoader(__int64 a1, int a2, const WCHAR *a3, const WCHAR *a4, __int64 a5, __int64 a6)
{
  void *v10; // rbx
  __int64 v11; // rdx
  __int64 dwNumberOfProcessors; // r8
  HMODULE *v13; // rbx
  SC_HANDLE *v14; // rdi
  HMODULE Library; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  SC_HANDLE v18; // rax
  SC_HANDLE v19; // rax
  const char *v21; // [rsp+20h] [rbp-60h]
  const char *v22; // [rsp+28h] [rbp-58h]
  _SYSTEM_INFO SystemInfo; // [rsp+48h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v10 = operator new(0x118u);
  memset_0(v10, 0, 0x118u);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  dwNumberOfProcessors = 4;
  if ( SystemInfo.dwNumberOfProcessors > 4 )
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  *(_QWORD *)a1 = WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(v10, v11, dwNumberOfProcessors, 1);
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 128) = a2;
  v13 = (HMODULE *)(a1 + 136);
  *(_QWORD *)(a1 + 136) = 0;
  v14 = (SC_HANDLE *)(a1 + 144);
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 232), 0xFAu, 0);
  *(_DWORD *)(a1 + 272) = 0;
  if ( *((_QWORD *)a4 + 3) > 7u )
    a4 = *(const WCHAR **)a4;
  Library = LoadLibraryExW(a4, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    a1 + 136,
    Library);
  if ( !*v13 )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\cspmanager\\cspmanager.cpp",
      "LoadLibraryEx",
      v21);
  v16 = WcmCommon::String::ConvertToUtf8(&SystemInfo, a6);
  if ( *(_QWORD *)(v16 + 24) > 0xFu )
    v16 = *(_QWORD *)v16;
  *(_QWORD *)(a1 + 8) = GetProcAddress(*v13, (LPCSTR)v16);
  std::string::~string(&SystemInfo);
  if ( !*(_QWORD *)(a1 + 8) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\cspmanager\\cspmanager.cpp",
      (const char *)0x7F,
      (unsigned int)"GetProcAddress",
      v22);
  v17 = WcmCommon::String::ConvertToUtf8(&SystemInfo, a5);
  if ( *(_QWORD *)(v17 + 24) > 0xFu )
    v17 = *(_QWORD *)v17;
  *(_QWORD *)(a1 + 16) = GetProcAddress(*v13, (LPCSTR)v17);
  std::string::~string(&SystemInfo);
  if ( !*(_QWORD *)(a1 + 16) )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\cspmanager\\cspmanager.cpp",
      (const char *)0x7F,
      (unsigned int)"GetProcAddress",
      v22);
  if ( *((_QWORD *)a3 + 2) )
  {
    v18 = OpenSCManagerW(0, 0, 5u);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      a1 + 144,
      v18);
    if ( !*v14 )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\cspmanager\\cspmanager.cpp",
        "OpenCSManager",
        v21);
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    v19 = OpenServiceW(*v14, a3, 4u);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      a1 + 152,
      v19);
    if ( !*(_QWORD *)(a1 + 152) )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\cspmanager\\cspmanager.cpp",
        "OpenService",
        v21);
  }
  return a1;
}

```

## disassembly

```asm
0x1800b7094  mov     [rsp-38h+arg_8], rbx
0x1800b7099  push    rbp
0x1800b709a  push    rsi
0x1800b709b  push    rdi
0x1800b709c  push    r12
0x1800b709e  push    r13
0x1800b70a0  push    r14
0x1800b70a2  push    r15
0x1800b70a4  mov     rbp, rsp
0x1800b70a7  sub     rsp, 80h
0x1800b70ae  mov     rax, cs:__security_cookie
0x1800b70b5  xor     rax, rsp
0x1800b70b8  mov     [rbp+var_8], rax
0x1800b70bc  mov     r15, r9
0x1800b70bf  mov     r14, r8
0x1800b70c2  mov     edi, edx
0x1800b70c4  mov     rsi, rcx
0x1800b70c7  mov     [rbp+var_48], rcx
0x1800b70cb  mov     rax, [rbp+arg_20]
0x1800b70cf  mov     [rbp+var_50], rax
0x1800b70d3  mov     r13, [rbp+arg_28]
0x1800b70d7  mov     r12d, 118h
0x1800b70dd  mov     ecx, r12d; Size
0x1800b70e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b70e5  mov     rbx, rax
0x1800b70e8  mov     [rbp+var_40], rax
0x1800b70ec  mov     r8d, r12d; Size
0x1800b70ef  xor     edx, edx; Val
0x1800b70f1  mov     rcx, rax; void *
0x1800b70f4  call    memset_0
0x1800b70f9  xorps   xmm0, xmm0
0x1800b70fc  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1800b7100  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800b7104  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x1800b7108  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1800b710c  call    cs:__imp_GetSystemInfo
0x1800b7112  mov     r8d, 4
0x1800b7118  cmp     [rbp+SystemInfo.dwNumberOfProcessors], r8d
0x1800b711c  cmova   r8d, [rbp+SystemInfo.dwNumberOfProcessors]
0x1800b7121  mov     r9d, 1
0x1800b7127  mov     rcx, rbx
0x1800b712a  call    ??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z; WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)
0x1800b712f  nop
0x1800b7130  mov     [rsi], rax
0x1800b7133  xor     eax, eax
0x1800b7135  mov     [rsi+8], rax
0x1800b7139  mov     [rsi+10h], rax
0x1800b713d  mov     [rsi+18h], rax
0x1800b7141  mov     [rsi+20h], rax
0x1800b7145  mov     [rsi+28h], rax
0x1800b7149  mov     [rsi+30h], rax
0x1800b714d  mov     [rsi+38h], rax
0x1800b7151  mov     [rsi+40h], rax
0x1800b7155  mov     [rsi+48h], rax
0x1800b7159  mov     [rsi+50h], rax
0x1800b715d  mov     [rsi+58h], rax
0x1800b7161  mov     [rsi+60h], rax
0x1800b7165  mov     [rsi+68h], rax
0x1800b7169  mov     [rsi+70h], rax
0x1800b716d  mov     [rsi+78h], rax
0x1800b7171  mov     [rsi+80h], edi
0x1800b7177  lea     rbx, [rsi+88h]
0x1800b717e  mov     [rbx], rax
0x1800b7181  lea     rdi, [rsi+90h]
0x1800b7188  mov     [rdi], rax
0x1800b718b  lea     r12, [rsi+98h]
0x1800b7192  mov     [r12], rax
0x1800b7196  mov     [rsi+0A0h], rax
0x1800b719d  mov     [rsi+0E0h], rax
0x1800b71a4  lea     rcx, [rsi+0E8h]; lpCriticalSection
0x1800b71ab  xor     r8d, r8d; Flags
0x1800b71ae  mov     edx, 0FAh; dwSpinCount
0x1800b71b3  call    cs:__imp_InitializeCriticalSectionEx
0x1800b71b9  nop
0x1800b71ba  mov     dword ptr [rsi+110h], 0
0x1800b71c4  cmp     qword ptr [r15+18h], 7
0x1800b71c9  jbe     short loc_1800B71CE
0x1800b71cb  mov     r15, [r15]
0x1800b71ce  xor     r8d, r8d; dwFlags
0x1800b71d1  xor     edx, edx; hFile
0x1800b71d3  mov     rcx, r15; lpLibFileName
0x1800b71d6  call    cs:__imp_LoadLibraryExW
0x1800b71dc  mov     rdx, rax
0x1800b71df  mov     rcx, rbx
0x1800b71e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800b71e7  xor     r15d, r15d
0x1800b71ea  cmp     [rbx], r15
0x1800b71ed  jnz     short loc_1800B720C
0x1800b71ef  mov     rcx, [rbp+38h]; this
0x1800b71f3  lea     r9, aLoadlibraryex; "LoadLibraryEx"
0x1800b71fa  lea     r8, aOnecoreuapNetW_32; "onecoreuap\\net\\wcm\\service\\base\\cs"...
0x1800b7201  mov     edx, 0A2h; void *
0x1800b7206  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800b720c  mov     rdx, r13
0x1800b720f  lea     rcx, [rbp+SystemInfo]
0x1800b7213  call    ?ConvertToUtf8@String@WcmCommon@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; WcmCommon::String::ConvertToUtf8(std::wstring const &)
0x1800b7218  cmp     qword ptr [rax+18h], 0Fh
0x1800b721d  jbe     short loc_1800B7222
0x1800b721f  mov     rax, [rax]
0x1800b7222  mov     rdx, rax; lpProcName
0x1800b7225  mov     rcx, [rbx]; hModule
0x1800b7228  call    cs:__imp_GetProcAddress
0x1800b722e  mov     [rsi+8], rax
0x1800b7232  lea     rcx, [rbp+SystemInfo]
0x1800b7236  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800b723b  cmp     [rsi+8], r15
0x1800b723f  jnz     short loc_1800B7268
0x1800b7241  mov     rcx, [rbp+38h]; this
0x1800b7245  lea     rax, aGetprocaddress_0; "GetProcAddress"
0x1800b724c  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x1800b7251  mov     r9d, 7Fh; char *
0x1800b7257  lea     r8, aOnecoreuapNetW_32; "onecoreuap\\net\\wcm\\service\\base\\cs"...
0x1800b725e  lea     edx, [r9+2Ah]; void *
0x1800b7262  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800b7268  mov     rdx, [rbp+var_50]
0x1800b726c  lea     rcx, [rbp+SystemInfo]
0x1800b7270  call    ?ConvertToUtf8@String@WcmCommon@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; WcmCommon::String::ConvertToUtf8(std::wstring const &)
0x1800b7275  cmp     qword ptr [rax+18h], 0Fh
0x1800b727a  jbe     short loc_1800B727F
0x1800b727c  mov     rax, [rax]
0x1800b727f  mov     rdx, rax; lpProcName
0x1800b7282  mov     rcx, [rbx]; hModule
0x1800b7285  call    cs:__imp_GetProcAddress
0x1800b728b  mov     [rsi+10h], rax
0x1800b728f  lea     rcx, [rbp+SystemInfo]
0x1800b7293  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800b7298  cmp     [rsi+10h], r15
0x1800b729c  jnz     short loc_1800B72C5
0x1800b729e  mov     rcx, [rbp+38h]; this
0x1800b72a2  lea     rax, aGetprocaddress_0; "GetProcAddress"
0x1800b72a9  mov     qword ptr [rsp+80h+var_60], rax; unsigned int
0x1800b72ae  mov     r9d, 7Fh; char *
0x1800b72b4  lea     r8, aOnecoreuapNetW_32; "onecoreuap\\net\\wcm\\service\\base\\cs"...
0x1800b72bb  lea     edx, [r9+31h]; void *
0x1800b72bf  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800b72c5  cmp     [r14+10h], r15
0x1800b72c9  jbe     loc_1800B7354
0x1800b72cf  xor     edx, edx; lpDatabaseName
0x1800b72d1  xor     ecx, ecx; lpMachineName
0x1800b72d3  lea     r8d, [rdx+5]; dwDesiredAccess
0x1800b72d7  call    cs:__imp_OpenSCManagerW
0x1800b72dd  mov     rdx, rax
0x1800b72e0  mov     rcx, rdi
0x1800b72e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800b72e8  mov     rcx, [rdi]; hSCManager
0x1800b72eb  test    rcx, rcx
0x1800b72ee  jnz     short loc_1800B730D
0x1800b72f0  mov     rcx, [rbp+38h]; this
0x1800b72f4  lea     r9, aOpencsmanager; "OpenCSManager"
0x1800b72fb  lea     r8, aOnecoreuapNetW_32; "onecoreuap\\net\\wcm\\service\\base\\cs"...
0x1800b7302  mov     edx, 0BAh; void *
0x1800b7307  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800b730d  cmp     qword ptr [r14+18h], 7
0x1800b7312  jbe     short loc_1800B7317
0x1800b7314  mov     r14, [r14]
0x1800b7317  mov     r8d, 4; dwDesiredAccess
0x1800b731d  mov     rdx, r14; lpServiceName
0x1800b7320  call    cs:__imp_OpenServiceW
0x1800b7326  mov     rdx, rax
0x1800b7329  mov     rcx, r12
0x1800b732c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800b7331  cmp     [r12], r15
0x1800b7335  jnz     short loc_1800B7354
0x1800b7337  mov     rcx, [rbp+38h]; this
0x1800b733b  lea     r9, aOpenservice; "OpenService"
0x1800b7342  lea     r8, aOnecoreuapNetW_32; "onecoreuap\\net\\wcm\\service\\base\\cs"...
0x1800b7349  mov     edx, 0C1h; void *
0x1800b734e  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800b7354  mov     rax, rsi
0x1800b7357  mov     rcx, [rbp+var_8]
0x1800b735b  xor     rcx, rsp; StackCookie
0x1800b735e  call    __security_check_cookie
0x1800b7363  mov     rbx, [rsp+80h+arg_8]
0x1800b736b  add     rsp, 80h
0x1800b7372  pop     r15
0x1800b7374  pop     r14
0x1800b7376  pop     r13
0x1800b7378  pop     r12
0x1800b737a  pop     rdi
0x1800b737b  pop     rsi
0x1800b737c  pop     rbp
0x1800b737d  retn
```
