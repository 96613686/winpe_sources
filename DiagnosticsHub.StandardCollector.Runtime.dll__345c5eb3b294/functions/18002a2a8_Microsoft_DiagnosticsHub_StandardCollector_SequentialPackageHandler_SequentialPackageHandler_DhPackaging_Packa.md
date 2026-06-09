# Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::SequentialPackageHandler(DhPackaging::PackageArchiveType)

- ea: `0x18002a2a8`
- end: `0x18002a607`
- name: `??0SequentialPackageHandler@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@W4PackageArchiveType@DhPackaging@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b290`

## callees

- `0x180009fa4`
- `0x18000a078`
- `0x18000a17c`
- `0x18002a2a8`
- `0x18002b2f0`
- `0x18002b5ac`
- `0x180040d8c`
- `0x180049b50`
- `0x180049bac`
- `0x180049c18`
- `0x18004a024`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x18002a3eb`
- `VCRUNTIME140!wcsrchr` at `0x18002a3eb`
- `KERNEL32!LoadLibraryExW` at `0x18002a47e`
- `KERNEL32!LoadLibraryExW` at `0x18002a47e`
- `KERNEL32!InitializeSRWLock` at `0x18002a332`
- `KERNEL32!InitializeSRWLock` at `0x18002a332`
- `KERNEL32!InitializeCriticalSection` at `0x18002a350`
- `KERNEL32!InitializeCriticalSection` at `0x18002a350`
- `KERNEL32!GetLastError` at `0x18002a490`
- `KERNEL32!GetLastError` at `0x18002a490`
- `KERNEL32!GetProcAddress` at `0x18002a4b0`
- `KERNEL32!GetProcAddress` at `0x18002a4b0`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002a432`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18002a432`

## string_xrefs

- `0x18002a4a6`: `CreatePackageFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::SequentialPackageHandler(
        __int64 a1,
        unsigned int a2)
{
  _QWORD *v4; // rsi
  int ModulePath; // eax
  wchar_t *v6; // rax
  const wchar_t *v7; // rbx
  size_t v8; // rax
  __int64 v9; // rax
  const WCHAR *v10; // rcx
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v13; // ebx
  FARPROC ProcAddress; // rax
  Microsoft::DiagnosticsHub::Hosting::PackagingFactoryLoader *v15; // rcx
  int PackageFactory; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int pExceptionObject; // [rsp+20h] [rbp-59h] BYREF
  __int64 v22; // [rsp+28h] [rbp-51h]
  _BYTE v23[32]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+50h] [rbp-29h] BYREF
  wchar_t *Str[2]; // [rsp+58h] [rbp-21h] BYREF
  wchar_t *String[2]; // [rsp+68h] [rbp-11h]
  wchar_t *v27; // [rsp+78h] [rbp-1h]
  _OWORD Src[2]; // [rsp+80h] [rbp+7h] BYREF

  v22 = a1;
  *(_DWORD *)(a1 + 16) = 1;
  *(_QWORD *)(a1 + 8) = &CModuleRefCount::`vftable';
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&CModuleRefCount::s_ulcModuleRef) >= 0x7FFFFFFF )
    __fastfail(0xEu);
  *(_QWORD *)a1 = &Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::`vftable'{for `DhPackaging::IDhPackage'};
  *(_QWORD *)(a1 + 8) = &Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::`vftable'{for `CModuleRefCount'};
  v4 = (_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  InitializeSRWLock((PSRWLOCK)(a1 + 40));
  *(_QWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  *(_BYTE *)(a1 + 96) = 0;
  if ( dword_180077A28 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180077A28);
    if ( dword_180077A28 == -1 )
    {
      *(_OWORD *)&hLibModule = 0;
      atexit(Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::SequentialPackageHandler_::_2_::_dynamic_atexit_destructor_for__PackagingLoader__);
      Init_thread_footer(&dword_180077A28);
    }
  }
  *(_OWORD *)Str = 0;
  *(_OWORD *)String = 0;
  v27 = 0;
  ModulePath = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x180000000LL);
  if ( ModulePath < 0
    || ((v6 = wcsrchr(Str[0], 0x5Cu)) != 0
      ? (const wchar_t *)(*v6 = 0, v7 = Str[0], String[1] = Str[0], v27 = v6 + 1, ModulePath = 0)
      : (ModulePath = -2147024735, v7 = String[1]),
        ModulePath < 0) )
  {
    pExceptionObject = ModulePath;
    throw (long *)&pExceptionObject;
  }
  memset(Src, 0, sizeof(Src));
  v8 = wcslen(v7);
  std::wstring::_Construct<1,unsigned short const *>(Src, v7, v8);
  v9 = std::operator+<unsigned short>(v23, Src);
  v10 = (const WCHAR *)v9;
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v10 = *(const WCHAR **)v9;
  if ( a1 == -24 || !v10 )
  {
    v13 = -2147024809;
  }
  else
  {
    Library = hLibModule;
    if ( (hLibModule || (Library = LoadLibraryExW(v10, 0, 8u), (hLibModule = Library) != 0))
      && (ProcAddress = GetProcAddress(Library, "CreatePackageFactory")) != 0 )
    {
      v13 = ((__int64 (__fastcall *)(__int64))ProcAddress)(a1 + 24);
    }
    else
    {
      LastError = GetLastError();
      v13 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v13 = LastError;
    }
  }
  std::wstring::~wstring(v23);
  if ( v13 )
  {
    PackageFactory = Microsoft::DiagnosticsHub::Hosting::PackagingFactoryLoader::CreatePackageFactory(
                       v15,
                       (struct DhPackaging::IDhPackageFactory **)(a1 + 24));
    if ( PackageFactory < 0 )
    {
      pExceptionObject = PackageFactory;
      throw (long *)&pExceptionObject;
    }
  }
  if ( a2 )
  {
    v24 = 0;
    v17 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v4)(
            *v4,
            &GUID_abd60f84_5579_434f_8a74_90f81bd2f635,
            &v24);
    if ( v17 < 0 )
    {
      pExceptionObject = v17;
      throw (long *)&pExceptionObject;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, a2);
    if ( v18 < 0 )
    {
      pExceptionObject = v18;
      throw (long *)&pExceptionObject;
    }
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v4 + 24LL))(*v4, a1 + 32);
  if ( v19 < 0 )
  {
    pExceptionObject = v19;
    throw (long *)&pExceptionObject;
  }
  _mm_lfence();
  std::wstring::~wstring(Src);
  std::vector<unsigned short>::~vector<unsigned short>(Str);
  return a1;
}

```

## disassembly

```asm
0x18002a2a8  mov     [rsp-8+arg_10], rbx
0x18002a2ad  mov     [rsp-8+arg_18], rsi
0x18002a2b2  push    rbp
0x18002a2b3  push    rdi
0x18002a2b4  push    r12
0x18002a2b6  push    r14
0x18002a2b8  push    r15
0x18002a2ba  lea     rbp, [rsp-37h]
0x18002a2bf  sub     rsp, 0B0h
0x18002a2c6  mov     rax, cs:__security_cookie
0x18002a2cd  xor     rax, rsp
0x18002a2d0  mov     [rbp+57h+var_30], rax
0x18002a2d4  mov     r14d, edx
0x18002a2d7  mov     rdi, rcx
0x18002a2da  mov     [rbp+57h+var_A8], rcx
0x18002a2de  mov     ecx, 1
0x18002a2e3  mov     [rdi+10h], ecx
0x18002a2e6  lea     rax, ??_7CModuleRefCount@@6B@; const CModuleRefCount::`vftable'
0x18002a2ed  mov     [rdi+8], rax
0x18002a2f1  mov     eax, ecx
0x18002a2f3  lock xadd cs:?s_ulcModuleRef@CModuleRefCount@@0KA, eax; ulong CModuleRefCount::s_ulcModuleRef
0x18002a2fb  add     eax, ecx
0x18002a2fd  cmp     eax, 7FFFFFFFh
0x18002a302  jb      short loc_18002A30B
0x18002a304  mov     ecx, 0Eh
0x18002a309  int     29h; Win8: RtlFailFast(ecx)
0x18002a30b  lea     rax, ??_7SequentialPackageHandler@StandardCollector@DiagnosticsHub@Microsoft@@6BIDhPackage@DhPackaging@@@; const Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::`vftable'{for `DhPackaging::IDhPackage'}
0x18002a312  mov     [rdi], rax
0x18002a315  lea     rax, ??_7SequentialPackageHandler@StandardCollector@DiagnosticsHub@Microsoft@@6BCModuleRefCount@@@; const Microsoft::DiagnosticsHub::StandardCollector::SequentialPackageHandler::`vftable'{for `CModuleRefCount'}
0x18002a31c  mov     [rdi+8], rax
0x18002a320  lea     rsi, [rdi+18h]
0x18002a324  xor     r12d, r12d
0x18002a327  mov     [rsi], r12
0x18002a32a  mov     [rdi+20h], r12
0x18002a32e  lea     rcx, [rdi+28h]; SRWLock
0x18002a332  call    cs:__imp_InitializeSRWLock
0x18002a338  mov     [rdi+30h], r12
0x18002a33c  lea     rcx, [rdi+38h]; lpCriticalSection
0x18002a340  xorps   xmm0, xmm0
0x18002a343  xor     eax, eax
0x18002a345  movups  xmmword ptr [rcx], xmm0
0x18002a348  movups  xmmword ptr [rcx+10h], xmm0
0x18002a34c  mov     [rcx+20h], rax
0x18002a350  call    cs:__imp_InitializeCriticalSection
0x18002a356  nop
0x18002a357  mov     [rdi+60h], r12b
0x18002a35b  mov     ecx, cs:_tls_index
0x18002a361  mov     rax, gs:58h
0x18002a36a  mov     edx, 4
0x18002a36f  mov     rax, [rax+rcx*8]
0x18002a373  mov     ecx, [rdx+rax]
0x18002a376  cmp     cs:dword_180077A28, ecx
0x18002a37c  jle     short loc_18002A3B6
0x18002a37e  lea     rcx, dword_180077A28
0x18002a385  call    _Init_thread_header
0x18002a38a  cmp     cs:dword_180077A28, 0FFFFFFFFh
0x18002a391  jnz     short loc_18002A3B6
0x18002a393  xorps   xmm0, xmm0
0x18002a396  movdqu  cs:hLibModule, xmm0
0x18002a39e  lea     rcx, _Microsoft__DiagnosticsHub__StandardCollector__SequentialPackageHandler__SequentialPackageHandler____2____dynamic_atexit_destructor_for__PackagingLoader__; void (__cdecl *)()
0x18002a3a5  call    atexit
0x18002a3aa  lea     rcx, dword_180077A28
0x18002a3b1  call    _Init_thread_footer
0x18002a3b6  xorps   xmm0, xmm0
0x18002a3b9  movdqu  xmmword ptr [rbp+57h+Str], xmm0
0x18002a3be  xorps   xmm1, xmm1
0x18002a3c1  movdqu  xmmword ptr [rbp+57h+String], xmm1
0x18002a3c6  mov     [rbp+57h+var_58], r12
0x18002a3ca  lea     rdx, [rbp+57h+Str]
0x18002a3ce  lea     rcx, cs:180000000h; hModule
0x18002a3d5  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x18002a3da  test    eax, eax
0x18002a3dc  js      loc_18002A5B7
0x18002a3e2  mov     edx, 5Ch ; '\'; Ch
0x18002a3e7  mov     rcx, [rbp+57h+Str]; Str
0x18002a3eb  call    cs:__imp_wcsrchr
0x18002a3f1  test    rax, rax
0x18002a3f4  jnz     short loc_18002A401
0x18002a3f6  mov     eax, 800700A1h
0x18002a3fb  mov     rbx, [rbp+57h+String+8]
0x18002a3ff  jmp     short loc_18002A418
0x18002a401  mov     [rax], r12w
0x18002a405  mov     rbx, [rbp+57h+Str]
0x18002a409  mov     [rbp+57h+String+8], rbx
0x18002a40d  add     rax, 2
0x18002a411  mov     [rbp+57h+var_58], rax
0x18002a415  mov     eax, r12d
0x18002a418  test    eax, eax
0x18002a41a  js      loc_18002A5B7
0x18002a420  xorps   xmm0, xmm0
0x18002a423  movups  [rbp+57h+Src], xmm0
0x18002a427  xorps   xmm1, xmm1
0x18002a42a  movdqu  [rbp+57h+var_40], xmm1
0x18002a42f  mov     rcx, rbx; String
0x18002a432  call    cs:__imp_wcslen
0x18002a438  mov     r8, rax
0x18002a43b  mov     rdx, rbx
0x18002a43e  lea     rcx, [rbp+57h+Src]
0x18002a442  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a447  nop
0x18002a448  lea     rdx, [rbp+57h+Src]; Src
0x18002a44c  lea     rcx, [rbp+57h+var_A0]; void *
0x18002a450  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002a455  mov     rcx, rax
0x18002a458  cmp     qword ptr [rax+18h], 7
0x18002a45d  jbe     short loc_18002A462
0x18002a45f  mov     rcx, [rax]; lpLibFileName
0x18002a462  test    rsi, rsi
0x18002a465  jz      short loc_18002A4C8
0x18002a467  test    rcx, rcx
0x18002a46a  jz      short loc_18002A4C8
0x18002a46c  mov     rax, qword ptr cs:hLibModule
0x18002a473  test    rax, rax
0x18002a476  jnz     short loc_18002A4A6
0x18002a478  xor     edx, edx; hFile
0x18002a47a  lea     r8d, [rax+8]; dwFlags
0x18002a47e  call    cs:__imp_LoadLibraryExW
0x18002a484  mov     qword ptr cs:hLibModule, rax
0x18002a48b  test    rax, rax
0x18002a48e  jnz     short loc_18002A4A6
0x18002a490  call    cs:__imp_GetLastError
0x18002a496  movzx   ebx, ax
0x18002a499  or      ebx, 80070000h
0x18002a49f  test    eax, eax
0x18002a4a1  cmovle  ebx, eax
0x18002a4a4  jmp     short loc_18002A4CD
0x18002a4a6  lea     rdx, aCreatepackagef; "CreatePackageFactory"
0x18002a4ad  mov     rcx, rax; hModule
0x18002a4b0  call    cs:__imp_GetProcAddress
0x18002a4b6  test    rax, rax
0x18002a4b9  jz      short loc_18002A490
0x18002a4bb  mov     rcx, rsi
0x18002a4be  call    cs:__guard_dispatch_icall_fptr
0x18002a4c4  mov     ebx, eax
0x18002a4c6  jmp     short loc_18002A4CD
0x18002a4c8  mov     ebx, 80070057h
0x18002a4cd  lea     rcx, [rbp+57h+var_A0]
0x18002a4d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a4d6  test    ebx, ebx
0x18002a4d8  jz      short loc_18002A4EA
0x18002a4da  mov     rdx, rsi; struct DhPackaging::IDhPackageFactory **
0x18002a4dd  call    ?CreatePackageFactory@PackagingFactoryLoader@Hosting@DiagnosticsHub@Microsoft@@QEAAJPEAPEAUIDhPackageFactory@DhPackaging@@@Z; Microsoft::DiagnosticsHub::Hosting::PackagingFactoryLoader::CreatePackageFactory(DhPackaging::IDhPackageFactory * *)
0x18002a4e2  test    eax, eax
0x18002a4e4  js      loc_18002A5CB
0x18002a4ea  test    r14d, r14d
0x18002a4ed  jz      short loc_18002A549
0x18002a4ef  mov     [rbp+57h+var_80], r12
0x18002a4f3  mov     rcx, [rsi]
0x18002a4f6  mov     rax, [rcx]
0x18002a4f9  lea     r8, [rbp+57h+var_80]
0x18002a4fd  lea     rdx, _GUID_abd60f84_5579_434f_8a74_90f81bd2f635
0x18002a504  mov     rax, [rax]
0x18002a507  call    cs:__guard_dispatch_icall_fptr
0x18002a50d  nop
0x18002a50e  test    eax, eax
0x18002a510  js      loc_18002A5DF
0x18002a516  mov     rcx, [rbp+57h+var_80]
0x18002a51a  mov     rax, [rcx]
0x18002a51d  mov     edx, r14d
0x18002a520  mov     rax, [rax+18h]
0x18002a524  call    cs:__guard_dispatch_icall_fptr
0x18002a52a  test    eax, eax
0x18002a52c  js      loc_18002A5F3
0x18002a532  mov     rcx, [rbp+57h+var_80]
0x18002a536  test    rcx, rcx
0x18002a539  jz      short loc_18002A549
0x18002a53b  mov     rax, [rcx]
0x18002a53e  mov     rax, [rax+10h]
0x18002a542  call    cs:__guard_dispatch_icall_fptr
0x18002a548  nop
0x18002a549  mov     rcx, [rsi]
0x18002a54c  mov     rax, [rcx]
0x18002a54f  lea     rdx, [rdi+20h]
0x18002a553  mov     rax, [rax+18h]
0x18002a557  call    cs:__guard_dispatch_icall_fptr
0x18002a55d  test    eax, eax
0x18002a55f  js      short loc_18002A5A3
0x18002a561  lfence
0x18002a564  lea     rcx, [rbp+57h+Src]
0x18002a568  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a56d  nop
0x18002a56e  lea     rcx, [rbp+57h+Str]
0x18002a572  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18002a577  nop
0x18002a578  mov     rax, rdi
0x18002a57b  mov     rcx, [rbp+57h+var_30]
0x18002a57f  xor     rcx, rsp; StackCookie
0x18002a582  call    __security_check_cookie
0x18002a587  lea     r11, [rsp+0D0h+var_20]
0x18002a58f  mov     rbx, [r11+40h]
0x18002a593  mov     rsi, [r11+48h]
0x18002a597  mov     rsp, r11
0x18002a59a  pop     r15
0x18002a59c  pop     r14
0x18002a59e  pop     r12
0x18002a5a0  pop     rdi
0x18002a5a1  pop     rbp
0x18002a5a2  retn
0x18002a5a3  mov     [rbp+57h+pExceptionObject], eax
0x18002a5a6  lea     rdx, _TI1J; pThrowInfo
0x18002a5ad  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002a5b1  call    _CxxThrowException_0
0x18002a5b7  mov     [rbp+57h+pExceptionObject], eax
0x18002a5ba  lea     rdx, _TI1J; pThrowInfo
0x18002a5c1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002a5c5  call    _CxxThrowException_0
0x18002a5cb  mov     [rbp+57h+pExceptionObject], eax
0x18002a5ce  lea     rdx, _TI1J; pThrowInfo
0x18002a5d5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002a5d9  call    _CxxThrowException_0
0x18002a5df  mov     [rbp+57h+pExceptionObject], eax
0x18002a5e2  lea     rdx, _TI1J; pThrowInfo
0x18002a5e9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002a5ed  call    _CxxThrowException_0
0x18002a5f3  mov     [rbp+57h+pExceptionObject], eax
0x18002a5f6  lea     rdx, _TI1J; pThrowInfo
0x18002a5fd  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002a601  call    _CxxThrowException_0
```
