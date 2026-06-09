# _anonymous_namespace_::LoadKernelTraceControl

- ea: `0x180042e38`
- end: `0x180043040`
- name: `_anonymous_namespace_::LoadKernelTraceControl`
- size: `520`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800432f8`

## callees

- `0x180008914`
- `0x180009fa4`
- `0x18000a078`
- `0x18000a17c`
- `0x180035c60`
- `0x18003d864`
- `0x18003da40`
- `0x180040d8c`
- `0x180041e6c`
- `0x180042e38`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x180042edd`
- `VCRUNTIME140!wcsrchr` at `0x180042edd`
- `KERNEL32!LoadLibraryW` at `0x180042ff2`
- `KERNEL32!LoadLibraryW` at `0x180042ff2`
- `KERNEL32!LoadLibraryExW` at `0x180042e9b`
- `KERNEL32!LoadLibraryExW` at `0x180042e9b`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x180042f47`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x180042f47`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180042f94`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180042f94`

## string_xrefs

- `0x180042e94`: `KernelTraceControl.dll`
- `0x180042faa`: `KernelTraceControl.dll`
- `0x180042e79`: `Loading KernelTraceControl.dll from System32`
- `0x180042e80`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\KernelTraceControl.cpp`
- `0x180042fd8`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\KernelTraceControl.cpp`
- `0x180042fd1`: `Loading KernelTraceControl.dll from %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HMODULE anonymous_namespace_::LoadKernelTraceControl()
{
  struct DiagHubCommon::Logger *Logger; // rax
  struct DiagHubCommon::Logger *v1; // rax
  HMODULE Library; // rbx
  wchar_t *v3; // rax
  int v4; // eax
  const wchar_t *v5; // rdi
  __int64 v6; // rbx
  unsigned __int64 v7; // r8
  wchar_t *v9; // rbx
  size_t v10; // rax
  DiagHubCommon::LogStream *v11; // rcx
  LPCWSTR *v12; // r9
  const WCHAR *v13; // rcx
  wchar_t *S1[2]; // [rsp+28h] [rbp-19h] BYREF
  __int64 v15; // [rsp+38h] [rbp-9h]
  wchar_t *Str[2]; // [rsp+40h] [rbp-1h] BYREF
  wchar_t *S2[2]; // [rsp+50h] [rbp+Fh]
  wchar_t *v18; // [rsp+60h] [rbp+1Fh]
  LPCWSTR lpLibFileName[2]; // [rsp+68h] [rbp+27h] BYREF
  __int128 v20; // [rsp+78h] [rbp+37h]

  Logger = DiagHubCommon::Logger::GetLogger();
  if ( *((_QWORD *)Logger + 7) != *((_QWORD *)Logger + 8) )
  {
    v1 = DiagHubCommon::Logger::GetLogger();
    DiagHubCommon::LogStream::Write(
      (struct DiagHubCommon::Logger *)((char *)v1 + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\KernelTraceControl.cpp",
      L"Loading KernelTraceControl.dll from System32");
  }
  Library = LoadLibraryExW(L"KernelTraceControl.dll", 0, 0x800u);
  if ( !Library )
  {
    *(_OWORD *)Str = 0;
    *(_OWORD *)S2 = 0;
    v18 = 0;
    if ( (int)DiagHubCommon::ModulePath::GetModulePath(0) < 0 )
      goto LABEL_13;
    v3 = wcsrchr(Str[0], 0x5Cu);
    if ( v3 )
    {
      *v3 = 0;
      v5 = Str[0];
      S2[1] = Str[0];
      v18 = v3 + 1;
      v4 = 0;
    }
    else
    {
      v4 = -2147024735;
      v5 = S2[1];
    }
    if ( v4 )
      goto LABEL_13;
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    *(_OWORD *)S1 = 0;
    v15 = 0;
    std::vector<unsigned short>::resize(S1, v6 + 2);
    wmemcpy_s(S1[0], S1[1] - S1[0], v5, v6 + 1);
    if ( (unsigned int)Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(
                         (Microsoft::DiagnosticsHub::UnifiedPlatform *)S1[0],
                         (unsigned __int16 *)(S1[1] - S1[0]),
                         v7) )
    {
      std::vector<unsigned short>::~vector<unsigned short>(S1);
LABEL_13:
      std::vector<unsigned short>::~vector<unsigned short>(Str);
      return 0;
    }
    v9 = S1[0];
    *(_OWORD *)lpLibFileName = 0;
    v20 = 0;
    v10 = wcslen(S1[0]);
    std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, v9, v10);
    std::wstring::append(lpLibFileName, (void *)L"KernelTraceControl.dll");
    v11 = (struct DiagHubCommon::Logger *)((char *)DiagHubCommon::Logger::GetLogger() + 56);
    v12 = lpLibFileName;
    if ( *((_QWORD *)&v20 + 1) > 7u )
      v12 = (LPCWSTR *)lpLibFileName[0];
    DiagHubCommon::LogStream::Write(
      v11,
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\KernelTraceControl.cpp",
      L"Loading KernelTraceControl.dll from %s",
      v12);
    v13 = (const WCHAR *)lpLibFileName;
    if ( *((_QWORD *)&v20 + 1) > 7u )
      v13 = lpLibFileName[0];
    Library = LoadLibraryW(v13);
    std::wstring::~wstring(lpLibFileName);
    std::vector<unsigned short>::~vector<unsigned short>(S1);
    std::vector<unsigned short>::~vector<unsigned short>(Str);
  }
  return Library;
}

```

## disassembly

```asm
0x180042e38  mov     rax, rsp
0x180042e3b  mov     [rax+8], rbx
0x180042e3f  mov     [rax+10h], rsi
0x180042e43  mov     [rax+18h], rdi
0x180042e47  push    rbp
0x180042e48  lea     rbp, [rax-5Fh]
0x180042e4c  sub     rsp, 90h
0x180042e53  mov     rax, cs:__security_cookie
0x180042e5a  xor     rax, rsp
0x180042e5d  mov     [rbp+57h+var_10], rax
0x180042e61  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ; DiagHubCommon::Logger::GetLogger(void)
0x180042e66  mov     rcx, [rax+40h]
0x180042e6a  cmp     [rax+38h], rcx
0x180042e6e  jz      short loc_180042E8C
0x180042e70  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ; DiagHubCommon::Logger::GetLogger(void)
0x180042e75  lea     rcx, [rax+38h]; this
0x180042e79  lea     r8, aLoadingKernelt; "Loading KernelTraceControl.dll from Sys"...
0x180042e80  lea     rdx, aDAWork1SSource_14; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x180042e87  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180042e8c  xor     edx, edx; hFile
0x180042e8e  mov     r8d, 800h; dwFlags
0x180042e94  lea     rcx, aKerneltracecon; "KernelTraceControl.dll"
0x180042e9b  call    cs:__imp_LoadLibraryExW
0x180042ea1  mov     rbx, rax
0x180042ea4  xor     esi, esi
0x180042ea6  test    rax, rax
0x180042ea9  jnz     loc_180043018
0x180042eaf  xorps   xmm0, xmm0
0x180042eb2  movdqu  xmmword ptr [rbp+57h+Str], xmm0
0x180042eb7  xorps   xmm1, xmm1
0x180042eba  movdqu  xmmword ptr [rbp+57h+S2], xmm1
0x180042ebf  mov     [rbp+57h+var_38], rsi
0x180042ec3  lea     rdx, [rbp+57h+Str]
0x180042ec7  xor     ecx, ecx; hModule
0x180042ec9  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x180042ece  test    eax, eax
0x180042ed0  js      loc_180042F6E
0x180042ed6  lea     edx, [rbx+5Ch]; Ch
0x180042ed9  mov     rcx, [rbp+57h+Str]; Str
0x180042edd  call    cs:__imp_wcsrchr
0x180042ee3  test    rax, rax
0x180042ee6  jnz     short loc_180042EF3
0x180042ee8  mov     eax, 800700A1h
0x180042eed  mov     rdi, [rbp+57h+S2+8]
0x180042ef1  jmp     short loc_180042F08
0x180042ef3  mov     [rax], si
0x180042ef6  mov     rdi, [rbp+57h+Str]
0x180042efa  mov     [rbp+57h+S2+8], rdi
0x180042efe  add     rax, 2
0x180042f02  mov     [rbp+57h+var_38], rax
0x180042f06  mov     eax, esi
0x180042f08  test    eax, eax
0x180042f0a  jnz     short loc_180042F6E
0x180042f0c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180042f10  inc     rbx
0x180042f13  cmp     [rdi+rbx*2], si
0x180042f17  jnz     short loc_180042F10
0x180042f19  xorps   xmm1, xmm1
0x180042f1c  movdqu  xmmword ptr [rbp+57h+S1], xmm1
0x180042f21  mov     [rbp+57h+var_60], rsi
0x180042f25  lea     rdx, [rbx+2]
0x180042f29  lea     rcx, [rbp+57h+S1]
0x180042f2d  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180042f32  mov     rdx, [rbp+57h+S1+8]
0x180042f36  mov     rcx, [rbp+57h+S1]; S1
0x180042f3a  sub     rdx, rcx
0x180042f3d  sar     rdx, 1; N1
0x180042f40  lea     r9, [rbx+1]; N
0x180042f44  mov     r8, rdi; S2
0x180042f47  call    cs:__imp_wmemcpy_s
0x180042f4d  mov     rcx, [rbp+57h+S1]; this
0x180042f51  mov     rdx, [rbp+57h+S1+8]
0x180042f55  sub     rdx, rcx
0x180042f58  sar     rdx, 1; unsigned __int16 *
0x180042f5b  call    ?PathCchAddBackslash@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_K@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(ushort *,unsigned __int64)
0x180042f60  test    eax, eax
0x180042f62  jz      short loc_180042F7E
0x180042f64  lea     rcx, [rbp+57h+S1]
0x180042f68  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042f6d  nop
0x180042f6e  lea     rcx, [rbp+57h+Str]
0x180042f72  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180042f77  xor     eax, eax
0x180042f79  jmp     loc_18004301B
0x180042f7e  mov     rbx, [rbp+57h+S1]
0x180042f82  xorps   xmm0, xmm0
0x180042f85  movups  xmmword ptr [rbp+57h+lpLibFileName], xmm0
0x180042f89  xorps   xmm1, xmm1
0x180042f8c  movdqu  [rbp+57h+var_20], xmm1
0x180042f91  mov     rcx, rbx; String
0x180042f94  call    cs:__imp_wcslen
0x180042f9a  mov     r8, rax
0x180042f9d  mov     rdx, rbx
0x180042fa0  lea     rcx, [rbp+57h+lpLibFileName]
0x180042fa4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180042fa9  nop
0x180042faa  lea     rdx, aKerneltracecon; "KernelTraceControl.dll"
0x180042fb1  lea     rcx, [rbp+57h+lpLibFileName]; Src
0x180042fb5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180042fba  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ; DiagHubCommon::Logger::GetLogger(void)
0x180042fbf  lea     rcx, [rax+38h]; this
0x180042fc3  lea     r9, [rbp+57h+lpLibFileName]
0x180042fc7  cmp     qword ptr [rbp+57h+var_20+8], 7
0x180042fcc  cmova   r9, [rbp+57h+lpLibFileName]
0x180042fd1  lea     r8, aLoadingKernelt_0; "Loading KernelTraceControl.dll from %s"
0x180042fd8  lea     rdx, aDAWork1SSource_14; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x180042fdf  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180042fe4  lea     rcx, [rbp+57h+lpLibFileName]
0x180042fe8  cmp     qword ptr [rbp+57h+var_20+8], 7
0x180042fed  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x180042ff2  call    cs:__imp_LoadLibraryW
0x180042ff8  mov     rbx, rax
0x180042ffb  lea     rcx, [rbp+57h+lpLibFileName]
0x180042fff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043004  nop
0x180043005  lea     rcx, [rbp+57h+S1]
0x180043009  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004300e  nop
0x18004300f  lea     rcx, [rbp+57h+Str]
0x180043013  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180043018  mov     rax, rbx
0x18004301b  mov     rcx, [rbp+57h+var_10]
0x18004301f  xor     rcx, rsp; StackCookie
0x180043022  call    __security_check_cookie
0x180043027  lea     r11, [rsp+90h+var_s0]
0x18004302f  mov     rbx, [r11+10h]
0x180043033  mov     rsi, [r11+18h]
0x180043037  mov     rdi, [r11+20h]
0x18004303b  mov     rsp, r11
0x18004303e  pop     rbp
0x18004303f  retn
```
