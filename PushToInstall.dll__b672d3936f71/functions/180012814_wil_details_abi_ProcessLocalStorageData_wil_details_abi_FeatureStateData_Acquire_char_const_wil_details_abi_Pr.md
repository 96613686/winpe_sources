# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180012814`
- end: `0x180012c05`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180012c0c`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18000ed60`
- `0x18000f33c`
- `0x18000f650`
- `0x18000fca8`
- `0x180010788`
- `0x180010b84`
- `0x1800115fc`
- `0x1800116dc`
- `0x180011aec`
- `0x180011afc`
- `0x1800120dc`
- `0x180012814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800128ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800128ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012942`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012a55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012b14`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012942`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012a55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012b14`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001288b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001288b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180012ad7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180012ad7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012a2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012a1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001284d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001284d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012953`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012953`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012a66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b2a`

## string_xrefs

- `0x180012b63`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012b7c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012ba2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012bbb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012bda`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180012bf3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  const char *v16; // r9
  const char *v17; // r9
  _DWORD *v18; // rcx
  unsigned __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  bool v21; // r8
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v32[2]; // [rsp+30h] [rbp-D0h] BYREF
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
    v12 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  v32[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v32, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v29);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v30);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v17);
    return v15;
  }
  v18 = (_DWORD *)(4 * v32[0]);
  if ( 4 * v32[0] )
  {
    *a2 = v18;
    ++*v18;
    goto LABEL_24;
  }
  *a2 = 0;
  v19 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v22 = (_DWORD *)v19;
  if ( !v19 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v32 = 0;
  if ( (v19 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v32,
          Name,
          v21,
          v19 >> 2);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v31);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v32[0];
  *((_QWORD *)v22 + 3) = v32[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v32[0] = 0;
  v32[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v32);
  v6 = 0;
LABEL_24:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  return 0;
}

```

## disassembly

```asm
0x180012814  mov     [rsp-8+arg_10], rbx
0x180012819  push    rbp
0x18001281a  push    rsi
0x18001281b  push    rdi
0x18001281c  push    r14
0x18001281e  push    r15
0x180012820  lea     rbp, [rsp-160h]
0x180012828  sub     rsp, 260h
0x18001282f  mov     rax, cs:__security_cookie
0x180012836  xor     rax, rsp
0x180012839  mov     [rbp+180h+var_30], rax
0x180012840  mov     r15, rdx
0x180012843  mov     qword ptr [rdx], 0
0x18001284a  mov     rbx, rcx
0x18001284d  call    cs:__imp_GetCurrentProcessId
0x180012853  mov     r14d, 130h
0x180012859  mov     [rsp+280h+var_258], rbx
0x18001285e  mov     r9d, eax
0x180012861  mov     [rsp+280h+var_260], r14d; int
0x180012866  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001286d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180012872  lea     edx, [r14-2Ch]; unsigned __int64
0x180012876  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001287b  mov     r9d, 1F0001h; dwDesiredAccess
0x180012881  lea     rdx, [rsp+280h+Name]; lpName
0x180012886  xor     r8d, r8d; dwFlags
0x180012889  xor     ecx, ecx; lpMutexAttributes
0x18001288b  call    cs:__imp_CreateMutexExW
0x180012891  mov     rbx, rax
0x180012894  test    rax, rax
0x180012897  jnz     short loc_1800128A3
0x180012899  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001289e  jmp     loc_180012B36
0x1800128a3  xor     r8d, r8d; bAlertable
0x1800128a6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800128a9  mov     rcx, rbx; hHandle
0x1800128ac  call    cs:__imp_WaitForSingleObjectEx
0x1800128b2  cmp     eax, 102h
0x1800128b7  jz      short loc_1800128C9
0x1800128b9  test    eax, 0FFFFFF7Fh
0x1800128be  jnz     loc_180012B8E
0x1800128c4  mov     rdi, rbx
0x1800128c7  jmp     short loc_1800128CB
0x1800128c9  xor     edi, edi
0x1800128cb  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800128d0  mov     [rsp+280h+var_250], 0
0x1800128d9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800128de  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800128e3  mov     esi, eax
0x1800128e5  test    eax, eax
0x1800128e7  jns     short loc_180012968
0x1800128e9  mov     rcx, [rbp+188h]; this
0x1800128f0  lea     r8, aWil; "wil"
0x1800128f7  mov     r9d, eax; char *
0x1800128fa  mov     edx, 66h ; 'f'; void *
0x1800128ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012904  mov     rcx, [rbp+188h]; this
0x18001290b  lea     r8, aWil; "wil"
0x180012912  mov     r9d, esi; char *
0x180012915  mov     edx, 6Fh ; 'o'; void *
0x18001291a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001291f  mov     rcx, [rbp+188h]; this
0x180012926  lea     r8, aWil; "wil"
0x18001292d  mov     r9d, esi; char *
0x180012930  mov     edx, 12Eh; void *
0x180012935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001293a  test    rdi, rdi
0x18001293d  jz      short loc_180012950
0x18001293f  mov     rcx, rdi; hMutex
0x180012942  call    cs:__imp_ReleaseMutex
0x180012948  test    eax, eax
0x18001294a  jz      loc_180012B9B
0x180012950  mov     rcx, rbx; hObject
0x180012953  call    cs:__imp_CloseHandle
0x180012959  test    eax, eax
0x18001295b  jz      loc_180012BB4
0x180012961  mov     eax, esi
0x180012963  jmp     loc_180012B36
0x180012968  mov     rax, [rsp+280h+var_250]
0x18001296d  lea     rcx, ds:0[rax*4]
0x180012975  test    rcx, rcx
0x180012978  jz      short loc_180012988
0x18001297a  mov     [r15], rcx
0x18001297d  mov     eax, [rcx]
0x18001297f  inc     eax
0x180012981  mov     [rcx], eax
0x180012983  jmp     loc_180012B0C
0x180012988  mov     rdx, r14; dwBytes
0x18001298b  mov     qword ptr [r15], 0
0x180012992  mov     ecx, 8; dwFlags
0x180012997  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001299c  mov     r14, rax
0x18001299f  test    rax, rax
0x1800129a2  jnz     short loc_1800129C6
0x1800129a4  mov     rcx, [rbp+188h]; this
0x1800129ab  lea     r8, aWil; "wil"
0x1800129b2  mov     esi, 8007000Eh
0x1800129b7  mov     edx, 14Bh; void *
0x1800129bc  mov     r9d, esi; char *
0x1800129bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800129c4  jmp     short loc_180012A32
0x1800129c6  xorps   xmm0, xmm0
0x1800129c9  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800129cf  test    r14b, 3
0x1800129d3  jnz     loc_180012BCD
0x1800129d9  mov     r9, r14
0x1800129dc  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800129e1  shr     r9, 2; unsigned __int64
0x1800129e5  lea     rcx, [rsp+280h+var_250]; this
0x1800129ea  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800129ef  mov     esi, eax
0x1800129f1  test    eax, eax
0x1800129f3  jns     loc_180012A79
0x1800129f9  mov     rcx, [rbp+188h]; this
0x180012a00  lea     r8, aWil; "wil"
0x180012a07  mov     r9d, eax; char *
0x180012a0a  mov     edx, 14Eh; void *
0x180012a0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a14  lea     rcx, [rsp+280h+var_250]; this
0x180012a19  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180012a1e  call    cs:__imp_GetProcessHeap
0x180012a24  mov     r8, r14; lpMem
0x180012a27  xor     edx, edx; dwFlags
0x180012a29  mov     rcx, rax; hHeap
0x180012a2c  call    cs:__imp_HeapFree
0x180012a32  mov     rcx, [rbp+188h]; this
0x180012a39  lea     r8, aWil; "wil"
0x180012a40  mov     r9d, esi; char *
0x180012a43  mov     edx, 137h; void *
0x180012a48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a4d  test    rdi, rdi
0x180012a50  jz      short loc_180012A63
0x180012a52  mov     rcx, rdi; hMutex
0x180012a55  call    cs:__imp_ReleaseMutex
0x180012a5b  test    eax, eax
0x180012a5d  jz      loc_180012BD3
0x180012a63  mov     rcx, rbx; hObject
0x180012a66  call    cs:__imp_CloseHandle
0x180012a6c  test    eax, eax
0x180012a6e  jz      loc_180012B75
0x180012a74  jmp     loc_180012961
0x180012a79  mov     rax, [rsp+280h+var_250]
0x180012a7e  lea     rcx, [r14+28h]; void *
0x180012a82  mov     [r14+10h], rax
0x180012a86  xor     edx, edx; Val
0x180012a88  mov     rax, [rsp+280h+var_250+8]
0x180012a8d  mov     r8d, 108h; Size
0x180012a93  mov     [r14+18h], rax
0x180012a97  mov     dword ptr [r14], 1
0x180012a9e  mov     [r14+8], rbx
0x180012aa2  mov     [rsp+280h+var_250], 0
0x180012aab  mov     [rsp+280h+var_250+8], 0
0x180012ab4  call    memset_0
0x180012ab9  xor     eax, eax
0x180012abb  lea     rcx, [r14+28h]; this
0x180012abf  mov     [r14+20h], rax
0x180012ac3  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180012ac8  lea     rbx, [r14+0E8h]
0x180012acf  xor     r8d, r8d; Flags
0x180012ad2  mov     rcx, rbx; lpCriticalSection
0x180012ad5  xor     edx, edx; dwSpinCount
0x180012ad7  call    cs:__imp_InitializeCriticalSectionEx
0x180012add  mov     qword ptr [rbx+28h], 0
0x180012ae5  lea     rcx, [rsp+280h+var_250]; this
0x180012aea  mov     qword ptr [rbx+30h], 0
0x180012af2  mov     qword ptr [rbx+38h], 0
0x180012afa  mov     qword ptr [rbx+40h], 0
0x180012b02  mov     [r15], r14
0x180012b05  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180012b0a  xor     ebx, ebx
0x180012b0c  test    rdi, rdi
0x180012b0f  jz      short loc_180012B22
0x180012b11  mov     rcx, rdi; hMutex
0x180012b14  call    cs:__imp_ReleaseMutex
0x180012b1a  test    eax, eax
0x180012b1c  jz      loc_180012BEC
0x180012b22  test    rbx, rbx
0x180012b25  jz      short loc_180012B34
0x180012b27  mov     rcx, rbx; hObject
0x180012b2a  call    cs:__imp_CloseHandle
0x180012b30  test    eax, eax
0x180012b32  jz      short loc_180012B5C
0x180012b34  xor     eax, eax
0x180012b36  mov     rcx, [rbp+180h+var_30]
0x180012b3d  xor     rcx, rsp; StackCookie
0x180012b40  call    __security_check_cookie
0x180012b45  mov     rbx, [rsp+280h+arg_10]
0x180012b4d  add     rsp, 260h
0x180012b54  pop     r15
0x180012b56  pop     r14
0x180012b58  pop     rdi
0x180012b59  pop     rsi
0x180012b5a  pop     rbp
0x180012b5b  retn
0x180012b5c  mov     rcx, [rbp+188h]; this
0x180012b63  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012b6a  mov     edx, 0A0Bh; void *
0x180012b6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012b75  mov     rcx, [rbp+188h]; this
0x180012b7c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012b83  mov     edx, 0A0Bh; void *
0x180012b88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012b8e  mov     rcx, [rbp+188h]; this
0x180012b95  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180012b9b  mov     rcx, [rbp+188h]; this
0x180012ba2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012ba9  mov     edx, 0A15h; void *
0x180012bae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012bb4  mov     rcx, [rbp+188h]; this
0x180012bbb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012bc2  mov     edx, 0A0Bh; void *
0x180012bc7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012bcd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180012bd3  mov     rcx, [rbp+188h]; this
0x180012bda  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012be1  mov     edx, 0A15h; void *
0x180012be6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012bec  mov     rcx, [rbp+188h]; this
0x180012bf3  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180012bfa  mov     edx, 0A15h; void *
0x180012bff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
