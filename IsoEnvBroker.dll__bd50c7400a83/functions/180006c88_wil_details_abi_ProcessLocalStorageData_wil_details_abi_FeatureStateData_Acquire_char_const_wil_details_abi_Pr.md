# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180006c88`
- end: `0x180007085`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180007390`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x180005df8`
- `0x180006540`
- `0x180006c88`
- `0x18000708c`
- `0x1800075e4`
- `0x180007f08`
- `0x180008c98`
- `0x18000a464`
- `0x18000af64`
- `0x18000b3ec`
- `0x18000bd88`
- `0x18000bd98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006f4b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180006f4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006db6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ec9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f88`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006db6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ec9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f88`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006d20`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006d20`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006cff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006cff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006e92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ea0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006cc1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006cc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f9e`

## string_xrefs

- `0x180006fd7`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180006ff0`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180007009`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180007022`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000703b`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000705a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180007073`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    v11 = v6;
  }
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v29);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = (_DWORD *)v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v31 = 0;
  if ( (v18 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v22 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v31,
          Name,
          v20,
          v18 >> 2);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v30);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v25);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v31[0];
  *((_QWORD *)v21 + 3) = v31[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v31[0] = 0;
  v31[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x180006c88  mov     [rsp-8+arg_10], rbx
0x180006c8d  push    rbp
0x180006c8e  push    rsi
0x180006c8f  push    rdi
0x180006c90  push    r14
0x180006c92  push    r15
0x180006c94  lea     rbp, [rsp-160h]
0x180006c9c  sub     rsp, 260h
0x180006ca3  mov     rax, cs:__security_cookie
0x180006caa  xor     rax, rsp
0x180006cad  mov     [rbp+180h+var_30], rax
0x180006cb4  mov     r15, rdx
0x180006cb7  mov     qword ptr [rdx], 0
0x180006cbe  mov     rbx, rcx
0x180006cc1  call    cs:__imp_GetCurrentProcessId
0x180006cc7  mov     r14d, 130h
0x180006ccd  mov     [rsp+280h+var_258], rbx
0x180006cd2  mov     r9d, eax
0x180006cd5  mov     [rsp+280h+var_260], r14d; int
0x180006cda  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006ce1  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006ce6  lea     edx, [r14-2Ch]; unsigned __int64
0x180006cea  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006cef  mov     r9d, 1F0001h; dwDesiredAccess
0x180006cf5  lea     rdx, [rsp+280h+Name]; lpName
0x180006cfa  xor     r8d, r8d; dwFlags
0x180006cfd  xor     ecx, ecx; lpMutexAttributes
0x180006cff  call    cs:__imp_CreateMutexExW
0x180006d05  mov     rbx, rax
0x180006d08  test    rax, rax
0x180006d0b  jnz     short loc_180006D17
0x180006d0d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006d12  jmp     loc_180006FAA
0x180006d17  xor     r8d, r8d; bAlertable
0x180006d1a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006d1d  mov     rcx, rbx; hHandle
0x180006d20  call    cs:__imp_WaitForSingleObjectEx
0x180006d26  cmp     eax, 102h
0x180006d2b  jz      short loc_180006D3D
0x180006d2d  test    eax, 0FFFFFF7Fh
0x180006d32  jnz     loc_180007002
0x180006d38  mov     rdi, rbx
0x180006d3b  jmp     short loc_180006D3F
0x180006d3d  xor     edi, edi
0x180006d3f  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180006d44  mov     [rsp+280h+var_250], 0
0x180006d4d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006d52  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180006d57  mov     esi, eax
0x180006d59  test    eax, eax
0x180006d5b  jns     short loc_180006DDC
0x180006d5d  mov     rcx, [rbp+188h]; this
0x180006d64  lea     r8, aWil; "wil"
0x180006d6b  mov     r9d, eax; char *
0x180006d6e  mov     edx, 66h ; 'f'; void *
0x180006d73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d78  mov     rcx, [rbp+188h]; this
0x180006d7f  lea     r8, aWil; "wil"
0x180006d86  mov     r9d, esi; char *
0x180006d89  mov     edx, 6Fh ; 'o'; void *
0x180006d8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d93  mov     rcx, [rbp+188h]; this
0x180006d9a  lea     r8, aWil; "wil"
0x180006da1  mov     r9d, esi; char *
0x180006da4  mov     edx, 12Eh; void *
0x180006da9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006dae  test    rdi, rdi
0x180006db1  jz      short loc_180006DC4
0x180006db3  mov     rcx, rdi; hMutex
0x180006db6  call    cs:__imp_ReleaseMutex
0x180006dbc  test    eax, eax
0x180006dbe  jz      loc_18000701B
0x180006dc4  mov     rcx, rbx; hObject
0x180006dc7  call    cs:__imp_CloseHandle
0x180006dcd  test    eax, eax
0x180006dcf  jz      loc_180007034
0x180006dd5  mov     eax, esi
0x180006dd7  jmp     loc_180006FAA
0x180006ddc  mov     rax, [rsp+280h+var_250]
0x180006de1  lea     rcx, ds:0[rax*4]
0x180006de9  test    rcx, rcx
0x180006dec  jz      short loc_180006DFC
0x180006dee  mov     [r15], rcx
0x180006df1  mov     eax, [rcx]
0x180006df3  inc     eax
0x180006df5  mov     [rcx], eax
0x180006df7  jmp     loc_180006F80
0x180006dfc  mov     rdx, r14; dwBytes
0x180006dff  mov     qword ptr [r15], 0
0x180006e06  mov     ecx, 8; dwFlags
0x180006e0b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006e10  mov     r14, rax
0x180006e13  test    rax, rax
0x180006e16  jnz     short loc_180006E3A
0x180006e18  mov     rcx, [rbp+188h]; this
0x180006e1f  lea     r8, aWil; "wil"
0x180006e26  mov     esi, 8007000Eh
0x180006e2b  mov     edx, 14Bh; void *
0x180006e30  mov     r9d, esi; char *
0x180006e33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e38  jmp     short loc_180006EA6
0x180006e3a  xorps   xmm0, xmm0
0x180006e3d  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180006e43  test    r14b, 3
0x180006e47  jnz     loc_18000704D
0x180006e4d  mov     r9, r14
0x180006e50  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180006e55  shr     r9, 2; unsigned __int64
0x180006e59  lea     rcx, [rsp+280h+var_250]; this
0x180006e5e  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180006e63  mov     esi, eax
0x180006e65  test    eax, eax
0x180006e67  jns     loc_180006EED
0x180006e6d  mov     rcx, [rbp+188h]; this
0x180006e74  lea     r8, aWil; "wil"
0x180006e7b  mov     r9d, eax; char *
0x180006e7e  mov     edx, 14Eh; void *
0x180006e83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e88  lea     rcx, [rsp+280h+var_250]; this
0x180006e8d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006e92  call    cs:__imp_GetProcessHeap
0x180006e98  mov     r8, r14; lpMem
0x180006e9b  xor     edx, edx; dwFlags
0x180006e9d  mov     rcx, rax; hHeap
0x180006ea0  call    cs:__imp_HeapFree
0x180006ea6  mov     rcx, [rbp+188h]; this
0x180006ead  lea     r8, aWil; "wil"
0x180006eb4  mov     r9d, esi; char *
0x180006eb7  mov     edx, 137h; void *
0x180006ebc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ec1  test    rdi, rdi
0x180006ec4  jz      short loc_180006ED7
0x180006ec6  mov     rcx, rdi; hMutex
0x180006ec9  call    cs:__imp_ReleaseMutex
0x180006ecf  test    eax, eax
0x180006ed1  jz      loc_180007053
0x180006ed7  mov     rcx, rbx; hObject
0x180006eda  call    cs:__imp_CloseHandle
0x180006ee0  test    eax, eax
0x180006ee2  jz      loc_180006FE9
0x180006ee8  jmp     loc_180006DD5
0x180006eed  mov     rax, [rsp+280h+var_250]
0x180006ef2  lea     rcx, [r14+28h]; void *
0x180006ef6  mov     [r14+10h], rax
0x180006efa  xor     edx, edx; Val
0x180006efc  mov     rax, [rsp+280h+var_250+8]
0x180006f01  mov     r8d, 108h; Size
0x180006f07  mov     [r14+18h], rax
0x180006f0b  mov     dword ptr [r14], 1
0x180006f12  mov     [r14+8], rbx
0x180006f16  mov     [rsp+280h+var_250], 0
0x180006f1f  mov     [rsp+280h+var_250+8], 0
0x180006f28  call    memset_0
0x180006f2d  xor     eax, eax
0x180006f2f  lea     rcx, [r14+28h]; this
0x180006f33  mov     [r14+20h], rax
0x180006f37  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006f3c  lea     rbx, [r14+0E8h]
0x180006f43  xor     r8d, r8d; Flags
0x180006f46  mov     rcx, rbx; lpCriticalSection
0x180006f49  xor     edx, edx; dwSpinCount
0x180006f4b  call    cs:__imp_InitializeCriticalSectionEx
0x180006f51  mov     qword ptr [rbx+28h], 0
0x180006f59  lea     rcx, [rsp+280h+var_250]; this
0x180006f5e  mov     qword ptr [rbx+30h], 0
0x180006f66  mov     qword ptr [rbx+38h], 0
0x180006f6e  mov     qword ptr [rbx+40h], 0
0x180006f76  mov     [r15], r14
0x180006f79  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006f7e  xor     ebx, ebx
0x180006f80  test    rdi, rdi
0x180006f83  jz      short loc_180006F96
0x180006f85  mov     rcx, rdi; hMutex
0x180006f88  call    cs:__imp_ReleaseMutex
0x180006f8e  test    eax, eax
0x180006f90  jz      loc_18000706C
0x180006f96  test    rbx, rbx
0x180006f99  jz      short loc_180006FA8
0x180006f9b  mov     rcx, rbx; hObject
0x180006f9e  call    cs:__imp_CloseHandle
0x180006fa4  test    eax, eax
0x180006fa6  jz      short loc_180006FD0
0x180006fa8  xor     eax, eax
0x180006faa  mov     rcx, [rbp+180h+var_30]
0x180006fb1  xor     rcx, rsp; StackCookie
0x180006fb4  call    __security_check_cookie
0x180006fb9  mov     rbx, [rsp+280h+arg_10]
0x180006fc1  add     rsp, 260h
0x180006fc8  pop     r15
0x180006fca  pop     r14
0x180006fcc  pop     rdi
0x180006fcd  pop     rsi
0x180006fce  pop     rbp
0x180006fcf  retn
0x180006fd0  mov     rcx, [rbp+188h]; this
0x180006fd7  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006fde  mov     edx, 0A0Bh; void *
0x180006fe3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fe9  mov     rcx, [rbp+188h]; this
0x180006ff0  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006ff7  mov     edx, 0A0Bh; void *
0x180006ffc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007002  mov     rcx, [rbp+188h]; this
0x180007009  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007010  mov     edx, 0E01h; void *
0x180007015  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000701b  mov     rcx, [rbp+188h]; this
0x180007022  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007029  mov     edx, 0A15h; void *
0x18000702e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007034  mov     rcx, [rbp+188h]; this
0x18000703b  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007042  mov     edx, 0A0Bh; void *
0x180007047  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000704d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007053  mov     rcx, [rbp+188h]; this
0x18000705a  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007061  mov     edx, 0A15h; void *
0x180007066  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000706c  mov     rcx, [rbp+188h]; this
0x180007073  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000707a  mov     edx, 0A15h; void *
0x18000707f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
