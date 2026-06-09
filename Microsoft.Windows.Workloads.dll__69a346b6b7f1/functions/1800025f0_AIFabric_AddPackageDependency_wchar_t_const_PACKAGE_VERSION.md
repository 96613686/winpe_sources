# AIFabric::AddPackageDependency(wchar_t const *,PACKAGE_VERSION)

- ea: `0x1800025f0`
- end: `0x1800027bd`
- name: `?AddPackageDependency@AIFabric@@YAXPEB_WUPACKAGE_VERSION@@@Z`
- size: `461`
- prototype: `void __fastcall(AIFabric *__hidden this, const wchar_t *, struct PACKAGE_VERSION)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001dae0`

## callees

- `0x1800025f0`
- `0x1800027d0`
- `0x1800029f0`
- `0x180003db0`
- `0x180004810`
- `0x180004a00`
- `0x180004a20`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180002718`
- `KERNEL32!HeapFree` at `0x180002718`
- `KERNEL32!GetProcessHeap` at `0x18000270a`
- `KERNEL32!GetProcessHeap` at `0x18000270a`
- `KERNEL32!GetProcAddress` at `0x18000264c`
- `KERNEL32!GetProcAddress` at `0x18000266c`
- `KERNEL32!GetProcAddress` at `0x18000264c`
- `KERNEL32!GetProcAddress` at `0x18000266c`
- `KERNEL32!LoadLibraryExW` at `0x180002630`
- `KERNEL32!LoadLibraryExW` at `0x180002630`

## string_xrefs

- `0x180002629`: `api-ms-win-appmodel-runtime-l1-1-6.dll`
- `0x180002642`: `TryCreatePackageDependency`

## pseudocode

```c
void __fastcall AIFabric::AddPackageDependency(AIFabric *this, const wchar_t *a2, struct PACKAGE_VERSION a3)
{
  HMODULE Library; // rax
  winrt *v6; // rcx
  HMODULE v7; // rdi
  bool v8; // al
  int v9; // eax
  unsigned __int64 v10; // r8
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  __int128 *v13; // rcx
  int v14; // eax
  winrt::hresult *v15; // rax
  winrt::hresult *v16; // rax
  _BYTE v17[8]; // [rsp+50h] [rbp-48h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-40h] BYREF
  __int64 v19; // [rsp+60h] [rbp-38h] BYREF
  __int128 v20; // [rsp+68h] [rbp-30h] BYREF
  __int128 v21; // [rsp+78h] [rbp-20h]

  if ( !AIFabric::g_win11TryCreatePackageDependency )
  {
    Library = LoadLibraryExW(L"api-ms-win-appmodel-runtime-l1-1-6.dll", 0, 0);
    v7 = Library;
    if ( !Library
      || (AIFabric::g_win11TryCreatePackageDependency = (int (__high *)(void *, const wchar_t *, struct PACKAGE_VERSION, enum PackageDependencyProcessorArchitectures, enum PackageDependencyLifetimeKind, const wchar_t *, enum CreatePackageDependencyOptions, wchar_t **))GetProcAddress(Library, "TryCreatePackageDependency")) == 0
      || (AIFabric::g_win11AddPackageDependency = (int (__high *)(const wchar_t *, int, enum AddPackageDependencyOptions, struct PACKAGEDEPENDENCY_CONTEXT__ **, wchar_t **))GetProcAddress(v7, "AddPackageDependency")) == 0 )
    {
      winrt::throw_last_error(v6);
    }
  }
  v8 = IsRunningOnArm64();
  lpMem = 0;
  v9 = ((__int64 (__fastcall *)(_QWORD, AIFabric *, const wchar_t *, _QWORD, _DWORD, _QWORD, _DWORD, LPVOID *))AIFabric::g_win11TryCreatePackageDependency)(
         0,
         this,
         a2,
         16 * (unsigned int)v8,
         0,
         0,
         0,
         &lpMem);
  if ( v9 < 0 )
  {
    _mm_lfence();
    v16 = winrt::hresult::hresult((winrt::hresult *)v17, v9);
    winrt::throw_hresult(*(unsigned int *)v16);
  }
  v20 = 0;
  v21 = 0;
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)lpMem + v10) );
  std::wstring::_Construct<1,wchar_t const *>(&v20, lpMem, v10);
  v11 = lpMem;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v11);
  v19 = 0;
  v13 = &v20;
  if ( *((_QWORD *)&v21 + 1) > 7u )
    v13 = (__int128 *)v20;
  v14 = ((__int64 (__fastcall *)(__int128 *, _QWORD, __int64, __int64 *, _QWORD))AIFabric::g_win11AddPackageDependency)(
          v13,
          0,
          1,
          &v19,
          0);
  if ( v14 < 0 )
  {
    _mm_lfence();
    v15 = winrt::hresult::hresult((winrt::hresult *)v17, v14);
    winrt::throw_hresult(*(unsigned int *)v15);
  }
  std::wstring::_Tidy_deallocate((__int64)&v20);
}

```

## disassembly

```asm
0x1800025f0  mov     [rsp+arg_10], rbx
0x1800025f5  mov     [rsp+arg_18], rsi
0x1800025fa  push    rdi
0x1800025fb  sub     rsp, 90h
0x180002602  mov     rax, cs:__security_cookie
0x180002609  xor     rax, rsp
0x18000260c  mov     [rsp+98h+var_10], rax
0x180002614  mov     rbx, rdx
0x180002617  mov     rsi, rcx
0x18000261a  cmp     cs:?g_win11TryCreatePackageDependency@AIFabric@@3P6AJPEAXPEB_WUPACKAGE_VERSION@@W4PackageDependencyProcessorArchitectures@@W4PackageDependencyLifetimeKind@@1W4CreatePackageDependencyOptions@@PEAPEA_W@ZEA, 0; long (*AIFabric::g_win11TryCreatePackageDependency)(void *,wchar_t const *,PACKAGE_VERSION,PackageDependencyProcessorArchitectures,PackageDependencyLifetimeKind,wchar_t const *,CreatePackageDependencyOptions,wchar_t * *)
0x180002622  jnz     short loc_180002682
0x180002624  xor     r8d, r8d; dwFlags
0x180002627  xor     edx, edx; hFile
0x180002629  lea     rcx, LibFileName; "api-ms-win-appmodel-runtime-l1-1-6.dll"
0x180002630  call    cs:__imp_LoadLibraryExW
0x180002636  mov     rdi, rax
0x180002639  test    rax, rax
0x18000263c  jz      loc_1800027A0
0x180002642  lea     rdx, ProcName; "TryCreatePackageDependency"
0x180002649  mov     rcx, rax; hModule
0x18000264c  call    cs:__imp_GetProcAddress
0x180002652  mov     cs:?g_win11TryCreatePackageDependency@AIFabric@@3P6AJPEAXPEB_WUPACKAGE_VERSION@@W4PackageDependencyProcessorArchitectures@@W4PackageDependencyLifetimeKind@@1W4CreatePackageDependencyOptions@@PEAPEA_W@ZEA, rax; long (*AIFabric::g_win11TryCreatePackageDependency)(void *,wchar_t const *,PACKAGE_VERSION,PackageDependencyProcessorArchitectures,PackageDependencyLifetimeKind,wchar_t const *,CreatePackageDependencyOptions,wchar_t * *)
0x180002659  test    rax, rax
0x18000265c  jz      loc_1800027A0
0x180002662  lea     rdx, aAddpackagedepe; "AddPackageDependency"
0x180002669  mov     rcx, rdi; hModule
0x18000266c  call    cs:__imp_GetProcAddress
0x180002672  mov     cs:?g_win11AddPackageDependency@AIFabric@@3P6AJPEB_WHW4AddPackageDependencyOptions@@PEAPEAUPACKAGEDEPENDENCY_CONTEXT__@@PEAPEA_W@ZEA, rax; long (*AIFabric::g_win11AddPackageDependency)(wchar_t const *,int,AddPackageDependencyOptions,PACKAGEDEPENDENCY_CONTEXT__ * *,wchar_t * *)
0x180002679  test    rax, rax
0x18000267c  jz      loc_1800027A0
0x180002682  call    ?IsRunningOnArm64@@YA_NXZ; IsRunningOnArm64(void)
0x180002687  movzx   r9d, al
0x18000268b  shl     r9d, 4
0x18000268f  xor     edi, edi
0x180002691  mov     [rsp+98h+lpMem], rdi
0x180002696  lea     rax, [rsp+98h+lpMem]
0x18000269b  mov     [rsp+98h+var_60], rax
0x1800026a0  mov     [rsp+98h+var_68], edi
0x1800026a4  mov     [rsp+98h+var_70], rdi
0x1800026a9  mov     dword ptr [rsp+98h+var_78], edi
0x1800026ad  mov     r8, rbx
0x1800026b0  mov     rdx, rsi
0x1800026b3  xor     ecx, ecx
0x1800026b5  mov     rax, cs:?g_win11TryCreatePackageDependency@AIFabric@@3P6AJPEAXPEB_WUPACKAGE_VERSION@@W4PackageDependencyProcessorArchitectures@@W4PackageDependencyLifetimeKind@@1W4CreatePackageDependencyOptions@@PEAPEA_W@ZEA; long (*AIFabric::g_win11TryCreatePackageDependency)(void *,wchar_t const *,PACKAGE_VERSION,PackageDependencyProcessorArchitectures,PackageDependencyLifetimeKind,wchar_t const *,CreatePackageDependencyOptions,wchar_t * *)
0x1800026bc  call    cs:__guard_dispatch_icall_fptr
0x1800026c2  test    eax, eax
0x1800026c4  js      loc_1800027A6
0x1800026ca  xorps   xmm0, xmm0
0x1800026cd  movups  [rsp+98h+var_30], xmm0
0x1800026d2  xorps   xmm1, xmm1
0x1800026d5  movdqu  [rsp+98h+var_20], xmm1
0x1800026db  mov     rdx, [rsp+98h+lpMem]
0x1800026e0  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800026e7  nop     word ptr [rax+rax+00000000h]
0x1800026f0  inc     r8
0x1800026f3  cmp     [rdx+r8*2], di
0x1800026f8  jnz     short loc_1800026F0
0x1800026fa  lea     rcx, [rsp+98h+var_30]
0x1800026ff  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180002704  nop
0x180002705  mov     rbx, [rsp+98h+lpMem]
0x18000270a  call    cs:__imp_GetProcessHeap
0x180002710  mov     r8, rbx; lpMem
0x180002713  xor     edx, edx; dwFlags
0x180002715  mov     rcx, rax; hHeap
0x180002718  call    cs:__imp_HeapFree
0x18000271e  mov     [rsp+98h+var_38], rdi
0x180002723  lea     rcx, [rsp+98h+var_30]
0x180002728  cmp     qword ptr [rsp+98h+var_20+8], 7
0x180002731  cmova   rcx, qword ptr [rsp+98h+var_30]
0x180002737  mov     [rsp+98h+var_78], rdi
0x18000273c  lea     r9, [rsp+98h+var_38]
0x180002741  xor     edx, edx
0x180002743  mov     r8d, 1
0x180002749  mov     rax, cs:?g_win11AddPackageDependency@AIFabric@@3P6AJPEB_WHW4AddPackageDependencyOptions@@PEAPEAUPACKAGEDEPENDENCY_CONTEXT__@@PEAPEA_W@ZEA; long (*AIFabric::g_win11AddPackageDependency)(wchar_t const *,int,AddPackageDependencyOptions,PACKAGEDEPENDENCY_CONTEXT__ * *,wchar_t * *)
0x180002750  call    cs:__guard_dispatch_icall_fptr
0x180002756  test    eax, eax
0x180002758  js      short loc_180002789
0x18000275a  lea     rcx, [rsp+98h+var_30]
0x18000275f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002764  mov     rcx, [rsp+98h+var_10]
0x18000276c  xor     rcx, rsp; StackCookie
0x18000276f  call    __security_check_cookie
0x180002774  lea     r11, [rsp+98h+var_8]
0x18000277c  mov     rbx, [r11+20h]
0x180002780  mov     rsi, [r11+28h]
0x180002784  mov     rsp, r11
0x180002787  pop     rdi
0x180002788  retn
0x180002789  lfence
0x18000278c  mov     edx, eax; int
0x18000278e  lea     rcx, [rsp+98h+var_48]; this
0x180002793  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180002798  mov     ecx, [rax]
0x18000279a  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x1800027a0  call    ?throw_last_error@winrt@@YAXXZ; winrt::throw_last_error(void)
0x1800027a6  lfence
0x1800027a9  mov     edx, eax; int
0x1800027ab  lea     rcx, [rsp+98h+var_48]; this
0x1800027b0  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800027b5  mov     ecx, [rax]
0x1800027b7  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
