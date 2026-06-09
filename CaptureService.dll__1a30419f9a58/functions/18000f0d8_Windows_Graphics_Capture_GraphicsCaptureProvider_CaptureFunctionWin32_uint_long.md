# Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(uint,long)

- ea: `0x18000f0d8`
- end: `0x18000f32d`
- name: `?CaptureFunctionWin32@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAXIJ@Z`
- size: `597`
- prototype: `void __fastcall(int, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012444`
- `0x180016240`
- `0x1800162d0`

## callees

- `0x180002e60`
- `0x180003bc8`
- `0x18000bf34`
- `0x18000bfc0`
- `0x18000c8e4`
- `0x18000ddc4`
- `0x18000dec8`
- `0x18000f0d8`
- `0x180017da0`
- `0x18001892c`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f284`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000f284`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000f1d6`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18000f1d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f14f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f14f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f186`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f168`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f168`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f12e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f12e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f178`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f178`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f145`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f145`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000f249`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000f249`

## string_xrefs

- `0x18000f1a7`: `onecoreuap\windows\dwm\capture\svc\dll\CaptureTraceLogging.h`
- `0x18000f21f`: `onecoreuap\windows\dwm\capture\svc\dll\CaptureTraceLogging.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Graphics::Capture::GraphicsCaptureProvider::CaptureFunctionWin32(int a1, int a2)
{
  int v2; // esi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  void *v6; // rdi
  __int64 (__fastcall *v7)(void *, __int64, HANDLE *); // rbx
  int v8; // eax
  wchar_t *v9; // rax
  int v10; // esi
  WCHAR *v11; // rax
  WCHAR *v12; // rax
  WCHAR *v13; // rax
  void *ppInterface; // [rsp+20h] [rbp-258h] BYREF
  int v15; // [rsp+28h] [rbp-250h] BYREF
  HANDLE hProcess; // [rsp+30h] [rbp-248h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-240h] BYREF
  DWORD dwSize[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR ExeName[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v2 = a1;
  v15 = a2;
  memset_0(ExeName, 0, 0x208u);
  TokenHandle = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
    {
LABEL_6:
      LastError = 0;
      goto LABEL_33;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_33:
  try
  {
    if ( LastError < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\CaptureTraceLogging.h",
        (const char *)(unsigned int)LastError,
        (int)ppInterface);
    hProcess = 0;
    ppInterface = 0;
    if ( CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface) != -2147417833 )
    {
      v6 = ppInterface;
      v7 = *(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hProcess,
        0);
      v8 = v7(v6, 1052672, &hProcess);
      if ( v8 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\CaptureTraceLogging.h",
          (const char *)(unsigned int)v8,
          (int)ppInterface);
      dwSize[0] = 260;
      QueryFullProcessImageNameW(hProcess, 0, ExeName, dwSize);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&ppInterface);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  catch ( ... )
  {
    v2 = a1;
  }
  v9 = wcsrchr(ExeName, 0x5Cu);
  if ( v2 )
  {
    v10 = v2 - 1;
    if ( v10 )
    {
      if ( v10 == 1 )
      {
        if ( v9 )
          v11 = v9 + 1;
        else
          v11 = ExeName;
        ppInterface = v11;
        Windows::Graphics::Capture::GraphicsCaptureProvider::PickAsync<unsigned short *,long &>(&ppInterface, &v15);
      }
    }
    else
    {
      if ( v9 )
        v12 = v9 + 1;
      else
        v12 = ExeName;
      ppInterface = v12;
      Windows::Graphics::Capture::GraphicsCaptureProvider::CreateForMonitor<unsigned short *,long &>(&ppInterface, &v15);
    }
  }
  else
  {
    if ( v9 )
      v13 = v9 + 1;
    else
      v13 = ExeName;
    ppInterface = v13;
    Windows::Graphics::Capture::GraphicsCaptureProvider::CreateForWindow<unsigned short *,long &>(&ppInterface, &v15);
  }
}

```

## disassembly

```asm
0x18000f0d8  mov     [rsp+arg_10], rbx
0x18000f0dd  mov     [rsp+arg_18], rsi
0x18000f0e2  mov     [rsp+arg_0], ecx
0x18000f0e6  push    rdi
0x18000f0e7  sub     rsp, 270h
0x18000f0ee  mov     rax, cs:__security_cookie
0x18000f0f5  xor     rax, rsp
0x18000f0f8  mov     [rsp+278h+var_18], rax
0x18000f100  mov     esi, ecx
0x18000f102  mov     [rsp+278h+var_250], edx
0x18000f106  xor     edx, edx; Val
0x18000f108  mov     r8d, 208h; Size
0x18000f10e  lea     rcx, [rsp+278h+ExeName]; void *
0x18000f113  call    memset_0
0x18000f118  nop
0x18000f119  mov     [rsp+278h+TokenHandle], 0
0x18000f122  xor     edx, edx
0x18000f124  lea     rcx, [rsp+278h+TokenHandle]
0x18000f129  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000f12e  call    cs:__imp_GetCurrentThread
0x18000f134  mov     rcx, rax; ThreadHandle
0x18000f137  lea     r9, [rsp+278h+TokenHandle]; TokenHandle
0x18000f13c  xor     r8d, r8d; OpenAsSelf
0x18000f13f  lea     ebx, [r8+0Ch]
0x18000f143  mov     edx, ebx; DesiredAccess
0x18000f145  call    cs:__imp_OpenThreadToken
0x18000f14b  test    eax, eax
0x18000f14d  jnz     short loc_18000F182
0x18000f14f  call    cs:__imp_GetLastError
0x18000f155  test    eax, eax
0x18000f157  jle     short loc_18000F161
0x18000f159  movzx   eax, ax
0x18000f15c  or      eax, 80070000h
0x18000f161  cmp     eax, 800703F0h
0x18000f166  jnz     short loc_18000F198
0x18000f168  call    cs:__imp_GetCurrentProcess
0x18000f16e  mov     rcx, rax; ProcessHandle
0x18000f171  lea     r8, [rsp+278h+TokenHandle]; TokenHandle
0x18000f176  mov     edx, ebx; DesiredAccess
0x18000f178  call    cs:__imp_OpenProcessToken
0x18000f17e  test    eax, eax
0x18000f180  jz      short loc_18000F186
0x18000f182  xor     eax, eax
0x18000f184  jmp     short loc_18000F198
0x18000f186  call    cs:__imp_GetLastError
0x18000f18c  test    eax, eax
0x18000f18e  jle     short loc_18000F198
0x18000f190  movzx   eax, ax
0x18000f193  or      eax, 80070000h
0x18000f198  mov     rcx, [rsp+278h]; this
0x18000f1a0  test    eax, eax
0x18000f1a2  jns     short loc_18000F1B8
0x18000f1a4  mov     r9d, eax; char *
0x18000f1a7  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000f1ae  mov     edx, 33h ; '3'; void *
0x18000f1b3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000f1b8  mov     [rsp+278h+hProcess], 0
0x18000f1c1  mov     [rsp+278h+ppInterface], 0; int
0x18000f1ca  lea     rdx, [rsp+278h+ppInterface]; ppInterface
0x18000f1cf  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18000f1d6  call    cs:__imp_CoGetCallContext
0x18000f1dc  cmp     eax, 80010117h
0x18000f1e1  jz      short loc_18000F250
0x18000f1e3  mov     rdi, [rsp+278h+ppInterface]
0x18000f1e8  mov     rax, [rdi]
0x18000f1eb  mov     rbx, [rax+18h]
0x18000f1ef  xor     edx, edx
0x18000f1f1  lea     rcx, [rsp+278h+hProcess]
0x18000f1f6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000f1fb  lea     r8, [rsp+278h+hProcess]
0x18000f200  mov     edx, 101000h
0x18000f205  mov     rcx, rdi
0x18000f208  mov     rax, rbx
0x18000f20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f210  mov     rcx, [rsp+278h]; this
0x18000f218  test    eax, eax
0x18000f21a  jns     short loc_18000F230
0x18000f21c  mov     r9d, eax; char *
0x18000f21f  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000f226  mov     edx, 3Ah ; ':'; void *
0x18000f22b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000f230  mov     [rsp+278h+dwSize], 104h
0x18000f238  lea     r9, [rsp+278h+dwSize]; lpdwSize
0x18000f23d  lea     r8, [rsp+278h+ExeName]; lpExeName
0x18000f242  xor     edx, edx; dwFlags
0x18000f244  mov     rcx, [rsp+278h+hProcess]; hProcess
0x18000f249  call    cs:__imp_QueryFullProcessImageNameW
0x18000f24f  nop
0x18000f250  lea     rcx, [rsp+278h+ppInterface]
0x18000f255  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18000f25a  nop
0x18000f25b  lea     rcx, [rsp+278h+hProcess]
0x18000f260  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000f265  nop
0x18000f266  lea     rcx, [rsp+278h+TokenHandle]
0x18000f26b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000f270  nop
0x18000f271  jmp     short loc_18000F27A
0x18000f273  mov     esi, [rsp+278h+arg_0]
0x18000f27a  mov     edx, 5Ch ; '\'; Ch
0x18000f27f  lea     rcx, [rsp+278h+ExeName]; Str
0x18000f284  call    cs:__imp_wcsrchr
0x18000f28a  test    esi, esi
0x18000f28c  jz      short loc_18000F2E4
0x18000f28e  sub     esi, 1
0x18000f291  jz      short loc_18000F2BE
0x18000f293  cmp     esi, 1
0x18000f296  jnz     short loc_18000F308
0x18000f298  test    rax, rax
0x18000f29b  jz      short loc_18000F2A3
0x18000f29d  add     rax, 2
0x18000f2a1  jmp     short loc_18000F2A8
0x18000f2a3  lea     rax, [rsp+278h+ExeName]
0x18000f2a8  mov     [rsp+278h+ppInterface], rax
0x18000f2ad  lea     rdx, [rsp+278h+var_250]
0x18000f2b2  lea     rcx, [rsp+278h+ppInterface]
0x18000f2b7  call    ??$PickAsync@PEAGAEAJ@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAX$$QEAPEAGAEAJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::PickAsync<ushort *,long &>(ushort * &&,long &)
0x18000f2bc  jmp     short loc_18000F308
0x18000f2be  test    rax, rax
0x18000f2c1  jz      short loc_18000F2C9
0x18000f2c3  add     rax, 2
0x18000f2c7  jmp     short loc_18000F2CE
0x18000f2c9  lea     rax, [rsp+278h+ExeName]
0x18000f2ce  mov     [rsp+278h+ppInterface], rax
0x18000f2d3  lea     rdx, [rsp+278h+var_250]
0x18000f2d8  lea     rcx, [rsp+278h+ppInterface]
0x18000f2dd  call    ??$CreateForMonitor@PEAGAEAJ@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAX$$QEAPEAGAEAJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::CreateForMonitor<ushort *,long &>(ushort * &&,long &)
0x18000f2e2  jmp     short loc_18000F308
0x18000f2e4  test    rax, rax
0x18000f2e7  jz      short loc_18000F2EF
0x18000f2e9  add     rax, 2
0x18000f2ed  jmp     short loc_18000F2F4
0x18000f2ef  lea     rax, [rsp+278h+ExeName]
0x18000f2f4  mov     [rsp+278h+ppInterface], rax
0x18000f2f9  lea     rdx, [rsp+278h+var_250]
0x18000f2fe  lea     rcx, [rsp+278h+ppInterface]
0x18000f303  call    ??$CreateForWindow@PEAGAEAJ@GraphicsCaptureProvider@Capture@Graphics@Windows@@SAX$$QEAPEAGAEAJ@Z; Windows::Graphics::Capture::GraphicsCaptureProvider::CreateForWindow<ushort *,long &>(ushort * &&,long &)
0x18000f308  mov     rcx, [rsp+278h+var_18]
0x18000f310  xor     rcx, rsp; StackCookie
0x18000f313  call    __security_check_cookie
0x18000f318  lea     r11, [rsp+278h+var_8]
0x18000f320  mov     rbx, [r11+20h]
0x18000f324  mov     rsi, [r11+28h]
0x18000f328  mov     rsp, r11
0x18000f32b  pop     rdi
0x18000f32c  retn
```
