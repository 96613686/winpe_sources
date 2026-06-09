# ADPDatabase::GetDbPath(void)

- ea: `0x180032da4`
- end: `0x180032f70`
- name: `?GetDbPath@ADPDatabase@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `460`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031f64`
- `0x180033350`

## callees

- `0x180002250`
- `0x18000771c`
- `0x18000c13c`
- `0x1800328f4`
- `0x180032da4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f5a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032ec3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180032ec3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180032ed5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180032ed5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180032ee5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180032ee5`

## string_xrefs

- `0x180032f48`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\adpdatabase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ADPDatabase::GetDbPath(__int64 a1)
{
  const char *v2; // r9
  __int64 v3; // r8
  DWORD LastError; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  unsigned int v8; // [rsp+20h] [rbp-E0h]
  WCHAR Src[56]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Dst[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  wcscpy(Src, L"%LOCALAPPDATA%\\Microsoft\\Windows\\AggregatedDataPlatform");
  if ( !ExpandEnvironmentStringsW(Src, Dst, 0x104u) )
  {
    LastError = GetLastError();
    wil::details::in1diag3::FailFast_Win32(retaddr, v6, v7, (const char *)LastError, v8);
  }
  if ( !PathFileExistsW(Dst) && !CreateDirectoryW(Dst, 0) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\adpdatabase.cpp",
      v2);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v3 = -1;
  *(_QWORD *)(a1 + 24) = 0;
  do
    ++v3;
  while ( Dst[v3] );
  std::wstring::_Construct<1,wchar_t const *>(a1, Dst);
  return a1;
}

```

## disassembly

```asm
0x180032da4  push    rbp
0x180032da6  push    rbx
0x180032da7  push    rsi
0x180032da8  push    rdi
0x180032da9  push    r12
0x180032dab  push    r13
0x180032dad  push    r14
0x180032daf  push    r15
0x180032db1  lea     rbp, [rsp-1C8h]
0x180032db9  sub     rsp, 2C8h
0x180032dc0  mov     rax, cs:__security_cookie
0x180032dc7  xor     rax, rsp
0x180032dca  mov     [rbp+200h+var_50], rax
0x180032dd1  mov     rbx, rcx
0x180032dd4  mov     [rsp+300h+var_2D8], rcx
0x180032dd9  lea     rcx, [rsp+300h+Src]; lpSrc
0x180032dde  mov     dword ptr [rsp+300h+Src], 4C0025h
0x180032de6  mov     r8d, 104h; nSize
0x180032dec  mov     [rsp+300h+var_2CC], 43004Fh
0x180032df4  lea     rdx, [rbp+200h+Dst]; lpDst
0x180032df8  mov     [rsp+300h+var_2C8], 4C0041h
0x180032e00  xor     r13d, r13d
0x180032e03  mov     [rsp+300h+var_2C4], 500041h
0x180032e0b  mov     [rsp+300h+var_2C0], 440050h
0x180032e13  mov     [rsp+300h+var_2BC], 540041h
0x180032e1b  mov     [rsp+300h+var_2B8], 250041h
0x180032e23  mov     [rsp+300h+var_2B4], 4D005Ch
0x180032e2b  mov     [rsp+300h+var_2B0], 630069h
0x180032e33  mov     [rsp+300h+var_2AC], 6F0072h
0x180032e3b  mov     [rsp+300h+var_2A8], 6F0073h
0x180032e43  mov     [rsp+300h+var_2A4], 740066h
0x180032e4b  mov     [rsp+300h+var_2A0], 57005Ch
0x180032e53  mov     [rsp+300h+var_29C], 6E0069h
0x180032e5b  mov     [rsp+300h+var_298], 6F0064h
0x180032e63  mov     [rsp+300h+var_294], 730077h
0x180032e6b  mov     [rsp+300h+var_290], 41005Ch
0x180032e73  mov     [rsp+300h+var_28C], 670067h
0x180032e7b  mov     [rsp+300h+var_288], 650072h
0x180032e83  mov     [rsp+300h+var_284], 610067h
0x180032e8b  mov     [rbp+200h+var_280], 650074h
0x180032e92  mov     [rbp+200h+var_27C], 440064h
0x180032e99  mov     [rbp+200h+var_278], 740061h
0x180032ea0  mov     [rbp+200h+var_274], 500061h
0x180032ea7  mov     [rbp+200h+var_270], 61006Ch
0x180032eae  mov     [rbp+200h+var_26C], 660074h
0x180032eb5  mov     [rbp+200h+var_268], 72006Fh
0x180032ebc  mov     [rbp+200h+var_264], 6Dh ; 'm'
0x180032ec3  call    cs:__imp_ExpandEnvironmentStringsW
0x180032ec9  test    eax, eax
0x180032ecb  jz      loc_180032F5A
0x180032ed1  lea     rcx, [rbp+200h+Dst]; pszPath
0x180032ed5  call    cs:__imp_PathFileExistsW
0x180032edb  test    eax, eax
0x180032edd  jnz     short loc_180032EEF
0x180032edf  xor     edx, edx; lpSecurityAttributes
0x180032ee1  lea     rcx, [rbp+200h+Dst]; lpPathName
0x180032ee5  call    cs:__imp_CreateDirectoryW
0x180032eeb  test    eax, eax
0x180032eed  jz      short loc_180032F41
0x180032eef  xorps   xmm0, xmm0
0x180032ef2  lea     rax, [rbp+200h+Dst]
0x180032ef6  movups  xmmword ptr [rbx], xmm0
0x180032ef9  mov     [rbx+10h], r13
0x180032efd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032f01  mov     [rbx+18h], r13
0x180032f05  inc     r8
0x180032f08  cmp     [rax+r8*2], r13w
0x180032f0d  jnz     short loc_180032F05
0x180032f0f  lea     rdx, [rbp+200h+Dst]
0x180032f13  mov     rcx, rbx
0x180032f16  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180032f1b  mov     rax, rbx
0x180032f1e  mov     rcx, [rbp+200h+var_50]
0x180032f25  xor     rcx, rsp; StackCookie
0x180032f28  call    __security_check_cookie
0x180032f2d  add     rsp, 2C8h
0x180032f34  pop     r15
0x180032f36  pop     r14
0x180032f38  pop     r13
0x180032f3a  pop     r12
0x180032f3c  pop     rdi
0x180032f3d  pop     rsi
0x180032f3e  pop     rbx
0x180032f3f  pop     rbp
0x180032f40  retn
0x180032f41  mov     rcx, [rbp+208h]; this
0x180032f48  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180032f4f  mov     edx, 2Ch ; ','; void *
0x180032f54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180032f5a  call    cs:__imp_GetLastError
0x180032f60  mov     rcx, [rbp+208h]; this
0x180032f67  mov     r9d, eax; char *
0x180032f6a  call    ?FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::FailFast_Win32(void *,uint,char const *,ulong)
```
