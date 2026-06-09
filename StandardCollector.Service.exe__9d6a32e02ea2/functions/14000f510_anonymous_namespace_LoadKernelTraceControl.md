# _anonymous_namespace_::LoadKernelTraceControl

- ea: `0x14000f510`
- end: `0x14000f725`
- name: `_anonymous_namespace_::LoadKernelTraceControl`
- size: `533`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14000f938`

## callees

- `0x140003010`
- `0x140003088`
- `0x1400043a0`
- `0x1400097d0`
- `0x14000a278`
- `0x14000a42c`
- `0x14000b73c`
- `0x14000b8fc`
- `0x14000f510`
- `0x1400108a8`
- `0x1400137e0`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x14000f5ba`
- `VCRUNTIME140!wcsrchr` at `0x14000f5ba`
- `KERNEL32!LoadLibraryW` at `0x14000f6d3`
- `KERNEL32!LoadLibraryW` at `0x14000f6d3`
- `KERNEL32!LoadLibraryExW` at `0x14000f577`
- `KERNEL32!LoadLibraryExW` at `0x14000f577`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x14000f62a`
- `api-ms-win-crt-string-l1-1-0!wmemcpy_s` at `0x14000f62a`

## string_xrefs

- `0x14000f570`: `KernelTraceControl.dll`
- `0x14000f68b`: `KernelTraceControl.dll`
- `0x14000f555`: `Loading KernelTraceControl.dll from System32`
- `0x14000f55c`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\KernelTraceControl.cpp`
- `0x14000f6b9`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\KernelTraceControl.cpp`
- `0x14000f6b2`: `Loading KernelTraceControl.dll from %s`

## pseudocode

```c
HMODULE anonymous_namespace_::LoadKernelTraceControl()
{
  struct DiagHubCommon::Logger *Logger; // rax
  struct DiagHubCommon::Logger *v1; // rax
  HMODULE Library; // rbx
  wchar_t *v3; // rax
  int v4; // eax
  const wchar_t *v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // rbx
  unsigned __int64 v8; // r8
  DiagHubCommon::LogStream *v10; // rcx
  LPCWSTR *v11; // r9
  const WCHAR *v12; // rcx
  wchar_t *S1[2]; // [rsp+28h] [rbp-19h] BYREF
  __int64 v14; // [rsp+38h] [rbp-9h]
  wchar_t *Str[2]; // [rsp+40h] [rbp-1h] BYREF
  wchar_t *S2[2]; // [rsp+50h] [rbp+Fh]
  wchar_t *v17; // [rsp+60h] [rbp+1Fh]
  LPCWSTR lpLibFileName[2]; // [rsp+68h] [rbp+27h] BYREF
  __int128 v19; // [rsp+78h] [rbp+37h]

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
    v17 = 0;
    if ( (int)DiagHubCommon::ModulePath::GetModulePath(0) < 0 )
      goto LABEL_13;
    v3 = wcsrchr(Str[0], 0x5Cu);
    if ( v3 )
    {
      *v3 = 0;
      v5 = Str[0];
      S2[1] = Str[0];
      v17 = v3 + 1;
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
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    *(_OWORD *)S1 = 0;
    v14 = 0;
    std::vector<unsigned short>::resize(S1, v7 + 2);
    wmemcpy_s(S1[0], S1[1] - S1[0], v5, v7 + 1);
    if ( (unsigned int)Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(
                         (Microsoft::DiagnosticsHub::UnifiedPlatform *)S1[0],
                         (unsigned __int16 *)(S1[1] - S1[0]),
                         v8) )
    {
      std::vector<unsigned short>::~vector<unsigned short>(S1);
LABEL_13:
      std::vector<unsigned short>::~vector<unsigned short>(Str);
      return 0;
    }
    *(_OWORD *)lpLibFileName = 0;
    v19 = 0;
    do
      ++v6;
    while ( S1[0][v6] );
    std::wstring::_Construct<1,unsigned short const *>(lpLibFileName, S1[0], v6);
    std::wstring::append(lpLibFileName, (void *)L"KernelTraceControl.dll");
    v10 = (struct DiagHubCommon::Logger *)((char *)DiagHubCommon::Logger::GetLogger() + 56);
    v11 = lpLibFileName;
    if ( *((_QWORD *)&v19 + 1) > 7u )
      v11 = (LPCWSTR *)lpLibFileName[0];
    DiagHubCommon::LogStream::Write(
      v10,
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\KernelTraceControl.cpp",
      L"Loading KernelTraceControl.dll from %s",
      v11);
    v12 = (const WCHAR *)lpLibFileName;
    if ( *((_QWORD *)&v19 + 1) > 7u )
      v12 = lpLibFileName[0];
    Library = LoadLibraryW(v12);
    std::wstring::~wstring(lpLibFileName);
    std::vector<unsigned short>::~vector<unsigned short>(S1);
    std::vector<unsigned short>::~vector<unsigned short>(Str);
  }
  return Library;
}

```

## disassembly

```asm
0x14000f510  mov     rax, rsp
0x14000f513  mov     [rax+8], rbx
0x14000f517  mov     [rax+10h], rsi
0x14000f51b  mov     [rax+18h], rdi
0x14000f51f  mov     [rax+20h], r14
0x14000f523  push    rbp
0x14000f524  lea     rbp, [rax-5Fh]
0x14000f528  sub     rsp, 90h
0x14000f52f  mov     rax, cs:__security_cookie
0x14000f536  xor     rax, rsp
0x14000f539  mov     [rbp+57h+var_10], rax
0x14000f53d  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ; DiagHubCommon::Logger::GetLogger(void)
0x14000f542  mov     rcx, [rax+40h]
0x14000f546  cmp     [rax+38h], rcx
0x14000f54a  jz      short loc_14000F568
0x14000f54c  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ; DiagHubCommon::Logger::GetLogger(void)
0x14000f551  lea     rcx, [rax+38h]; this
0x14000f555  lea     r8, aLoadingKernelt; "Loading KernelTraceControl.dll from Sys"...
0x14000f55c  lea     rdx, aDAWork1SSource_2; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x14000f563  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x14000f568  xor     edx, edx; hFile
0x14000f56a  mov     r8d, 800h; dwFlags
0x14000f570  lea     rcx, aKerneltracecon; "KernelTraceControl.dll"
0x14000f577  call    cs:__imp_LoadLibraryExW
0x14000f57d  mov     rbx, rax
0x14000f580  xor     r14d, r14d
0x14000f583  test    rax, rax
0x14000f586  jnz     loc_14000F6F9
0x14000f58c  xorps   xmm0, xmm0
0x14000f58f  movdqu  xmmword ptr [rbp+57h+Str], xmm0
0x14000f594  xorps   xmm1, xmm1
0x14000f597  movdqu  xmmword ptr [rbp+57h+S2], xmm1
0x14000f59c  mov     [rbp+57h+var_38], r14
0x14000f5a0  lea     rdx, [rbp+57h+Str]
0x14000f5a4  xor     ecx, ecx; hModule
0x14000f5a6  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x14000f5ab  test    eax, eax
0x14000f5ad  js      loc_14000F651
0x14000f5b3  lea     edx, [rbx+5Ch]; Ch
0x14000f5b6  mov     rcx, [rbp+57h+Str]; Str
0x14000f5ba  call    cs:__imp_wcsrchr
0x14000f5c0  test    rax, rax
0x14000f5c3  jnz     short loc_14000F5D0
0x14000f5c5  mov     eax, 800700A1h
0x14000f5ca  mov     rsi, [rbp+57h+S2+8]
0x14000f5ce  jmp     short loc_14000F5E7
0x14000f5d0  mov     [rax], r14w
0x14000f5d4  mov     rsi, [rbp+57h+Str]
0x14000f5d8  mov     [rbp+57h+S2+8], rsi
0x14000f5dc  add     rax, 2
0x14000f5e0  mov     [rbp+57h+var_38], rax
0x14000f5e4  mov     eax, r14d
0x14000f5e7  test    eax, eax
0x14000f5e9  jnz     short loc_14000F651
0x14000f5eb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000f5ef  mov     rbx, rdi
0x14000f5f2  inc     rbx
0x14000f5f5  cmp     [rsi+rbx*2], r14w
0x14000f5fa  jnz     short loc_14000F5F2
0x14000f5fc  xorps   xmm1, xmm1
0x14000f5ff  movdqu  xmmword ptr [rbp+57h+S1], xmm1
0x14000f604  mov     [rbp+57h+var_60], r14
0x14000f608  lea     rdx, [rbx+2]
0x14000f60c  lea     rcx, [rbp+57h+S1]
0x14000f610  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x14000f615  mov     rdx, [rbp+57h+S1+8]
0x14000f619  mov     rcx, [rbp+57h+S1]; S1
0x14000f61d  sub     rdx, rcx
0x14000f620  sar     rdx, 1; N1
0x14000f623  lea     r9, [rbx+1]; N
0x14000f627  mov     r8, rsi; S2
0x14000f62a  call    cs:__imp_wmemcpy_s
0x14000f630  mov     rcx, [rbp+57h+S1]; this
0x14000f634  mov     rdx, [rbp+57h+S1+8]
0x14000f638  sub     rdx, rcx
0x14000f63b  sar     rdx, 1; unsigned __int16 *
0x14000f63e  call    ?PathCchAddBackslash@UnifiedPlatform@DiagnosticsHub@Microsoft@@YAJPEAG_K@Z; Microsoft::DiagnosticsHub::UnifiedPlatform::PathCchAddBackslash(ushort *,unsigned __int64)
0x14000f643  test    eax, eax
0x14000f645  jz      short loc_14000F661
0x14000f647  lea     rcx, [rbp+57h+S1]
0x14000f64b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000f650  nop
0x14000f651  lea     rcx, [rbp+57h+Str]
0x14000f655  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000f65a  xor     eax, eax
0x14000f65c  jmp     loc_14000F6FC
0x14000f661  xorps   xmm0, xmm0
0x14000f664  movups  xmmword ptr [rbp+57h+lpLibFileName], xmm0
0x14000f668  xorps   xmm1, xmm1
0x14000f66b  movdqu  [rbp+57h+var_20], xmm1
0x14000f670  mov     rdx, [rbp+57h+S1]
0x14000f674  inc     rdi
0x14000f677  cmp     [rdx+rdi*2], r14w
0x14000f67c  jnz     short loc_14000F674
0x14000f67e  mov     r8, rdi
0x14000f681  lea     rcx, [rbp+57h+lpLibFileName]
0x14000f685  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000f68a  nop
0x14000f68b  lea     rdx, aKerneltracecon; "KernelTraceControl.dll"
0x14000f692  lea     rcx, [rbp+57h+lpLibFileName]; Src
0x14000f696  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x14000f69b  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ; DiagHubCommon::Logger::GetLogger(void)
0x14000f6a0  lea     rcx, [rax+38h]; this
0x14000f6a4  lea     r9, [rbp+57h+lpLibFileName]
0x14000f6a8  cmp     qword ptr [rbp+57h+var_20+8], 7
0x14000f6ad  cmova   r9, [rbp+57h+lpLibFileName]
0x14000f6b2  lea     r8, aLoadingKernelt_0; "Loading KernelTraceControl.dll from %s"
0x14000f6b9  lea     rdx, aDAWork1SSource_2; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x14000f6c0  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x14000f6c5  lea     rcx, [rbp+57h+lpLibFileName]
0x14000f6c9  cmp     qword ptr [rbp+57h+var_20+8], 7
0x14000f6ce  cmova   rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x14000f6d3  call    cs:__imp_LoadLibraryW
0x14000f6d9  mov     rbx, rax
0x14000f6dc  lea     rcx, [rbp+57h+lpLibFileName]
0x14000f6e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f6e5  nop
0x14000f6e6  lea     rcx, [rbp+57h+S1]
0x14000f6ea  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000f6ef  nop
0x14000f6f0  lea     rcx, [rbp+57h+Str]
0x14000f6f4  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000f6f9  mov     rax, rbx
0x14000f6fc  mov     rcx, [rbp+57h+var_10]
0x14000f700  xor     rcx, rsp; StackCookie
0x14000f703  call    __security_check_cookie
0x14000f708  lea     r11, [rsp+90h+var_s0]
0x14000f710  mov     rbx, [r11+10h]
0x14000f714  mov     rsi, [r11+18h]
0x14000f718  mov     rdi, [r11+20h]
0x14000f71c  mov     r14, [r11+28h]
0x14000f720  mov     rsp, r11
0x14000f723  pop     rbp
0x14000f724  retn
```
