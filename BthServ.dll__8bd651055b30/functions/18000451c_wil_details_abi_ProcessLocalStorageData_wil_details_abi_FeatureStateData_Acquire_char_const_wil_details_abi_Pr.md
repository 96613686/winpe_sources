# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000451c`
- end: `0x180004912`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1014`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180004c04`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180003620`
- `0x18000451c`
- `0x180004918`
- `0x180004e60`
- `0x180005788`
- `0x180006478`
- `0x180007be4`
- `0x1800086d8`
- `0x180008b6c`
- `0x18000943c`
- `0x18000944c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800045b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800045b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004593`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004593`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800047ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800047ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000464a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004786`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004822`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000464a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004786`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004822`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000474f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000474f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000475d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000475d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004555`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004555`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000465b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004741`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000465b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004741`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004838`

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
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_28;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x18000451c  mov     [rsp-8+arg_10], rbx
0x180004521  push    rbp
0x180004522  push    rsi
0x180004523  push    rdi
0x180004524  push    r14
0x180004526  push    r15
0x180004528  lea     rbp, [rsp-160h]
0x180004530  sub     rsp, 260h
0x180004537  mov     rax, cs:__security_cookie
0x18000453e  xor     rax, rsp
0x180004541  mov     [rbp+180h+var_30], rax
0x180004548  mov     r15, rdx
0x18000454b  mov     qword ptr [rdx], 0
0x180004552  mov     rbx, rcx
0x180004555  call    cs:__imp_GetCurrentProcessId
0x18000455b  mov     r14d, 130h
0x180004561  mov     [rsp+280h+var_258], rbx
0x180004566  mov     r9d, eax
0x180004569  mov     [rsp+280h+var_260], r14d; int
0x18000456e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004575  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000457a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000457e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004583  mov     r9d, 1F0001h; dwDesiredAccess
0x180004589  lea     rdx, [rsp+280h+Name]; lpName
0x18000458e  xor     r8d, r8d; dwFlags
0x180004591  xor     ecx, ecx; lpMutexAttributes
0x180004593  call    cs:__imp_CreateMutexExW
0x180004599  mov     rbx, rax
0x18000459c  test    rax, rax
0x18000459f  jnz     short loc_1800045AB
0x1800045a1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800045a6  jmp     loc_180004844
0x1800045ab  xor     r8d, r8d; bAlertable
0x1800045ae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800045b1  mov     rcx, rbx; hHandle
0x1800045b4  call    cs:__imp_WaitForSingleObjectEx
0x1800045ba  cmp     eax, 102h
0x1800045bf  jz      short loc_1800045D1
0x1800045c1  test    eax, 0FFFFFF7Fh
0x1800045c6  jnz     loc_18000488E
0x1800045cc  mov     rdi, rbx
0x1800045cf  jmp     short loc_1800045D3
0x1800045d1  xor     edi, edi
0x1800045d3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800045d8  mov     [rsp+280h+hObject], 0
0x1800045e1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800045e6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800045eb  mov     esi, eax
0x1800045ed  test    eax, eax
0x1800045ef  jns     short loc_180004670
0x1800045f1  mov     rcx, [rbp+188h]; this
0x1800045f8  lea     r8, aWil; "wil"
0x1800045ff  mov     r9d, eax; char *
0x180004602  mov     edx, 66h ; 'f'; void *
0x180004607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000460c  mov     rcx, [rbp+188h]; this
0x180004613  lea     r8, aWil; "wil"
0x18000461a  mov     r9d, esi; char *
0x18000461d  mov     edx, 6Fh ; 'o'; void *
0x180004622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004627  mov     rcx, [rbp+188h]; this
0x18000462e  lea     r8, aWil; "wil"
0x180004635  mov     r9d, esi; char *
0x180004638  mov     edx, 12Eh; void *
0x18000463d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004642  test    rdi, rdi
0x180004645  jz      short loc_180004658
0x180004647  mov     rcx, rdi; hMutex
0x18000464a  call    cs:__imp_ReleaseMutex
0x180004650  test    eax, eax
0x180004652  jz      loc_1800048A0
0x180004658  mov     rcx, rbx; hObject
0x18000465b  call    cs:__imp_CloseHandle
0x180004661  test    eax, eax
0x180004663  jz      loc_1800048B2
0x180004669  mov     eax, esi
0x18000466b  jmp     loc_180004844
0x180004670  mov     rax, [rsp+280h+hObject]
0x180004675  lea     rcx, ds:0[rax*4]
0x18000467d  test    rcx, rcx
0x180004680  jz      short loc_180004690
0x180004682  mov     [r15], rcx
0x180004685  mov     eax, [rcx]
0x180004687  inc     eax
0x180004689  mov     [rcx], eax
0x18000468b  jmp     loc_18000481A
0x180004690  mov     rdx, r14; dwBytes
0x180004693  mov     qword ptr [r15], 0
0x18000469a  mov     ecx, 8; dwFlags
0x18000469f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800046a4  mov     r14, rax
0x1800046a7  test    rax, rax
0x1800046aa  jnz     short loc_1800046D1
0x1800046ac  mov     rcx, [rbp+188h]; this
0x1800046b3  lea     r8, aWil; "wil"
0x1800046ba  mov     esi, 8007000Eh
0x1800046bf  mov     edx, 14Bh; void *
0x1800046c4  mov     r9d, esi; char *
0x1800046c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046cc  jmp     loc_180004763
0x1800046d1  xorps   xmm0, xmm0
0x1800046d4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800046da  test    r14b, 3
0x1800046de  jnz     loc_1800048C4
0x1800046e4  mov     r9, r14
0x1800046e7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800046ec  shr     r9, 2; unsigned __int64
0x1800046f0  lea     rcx, [rsp+280h+hObject]; this
0x1800046f5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800046fa  mov     esi, eax
0x1800046fc  test    eax, eax
0x1800046fe  jns     loc_1800047AA
0x180004704  mov     rcx, [rbp+188h]; this
0x18000470b  lea     r8, aWil; "wil"
0x180004712  mov     r9d, eax; char *
0x180004715  mov     edx, 14Eh; void *
0x18000471a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000471f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004724  test    rcx, rcx
0x180004727  jz      short loc_180004737
0x180004729  call    cs:__imp_CloseHandle
0x18000472f  test    eax, eax
0x180004731  jz      loc_1800048CA
0x180004737  mov     rcx, [rsp+280h+hObject]; hObject
0x18000473c  test    rcx, rcx
0x18000473f  jz      short loc_18000474F
0x180004741  call    cs:__imp_CloseHandle
0x180004747  test    eax, eax
0x180004749  jz      loc_1800048DC
0x18000474f  call    cs:__imp_GetProcessHeap
0x180004755  mov     r8, r14; lpMem
0x180004758  xor     edx, edx; dwFlags
0x18000475a  mov     rcx, rax; hHeap
0x18000475d  call    cs:__imp_HeapFree
0x180004763  mov     rcx, [rbp+188h]; this
0x18000476a  lea     r8, aWil; "wil"
0x180004771  mov     r9d, esi; char *
0x180004774  mov     edx, 137h; void *
0x180004779  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000477e  test    rdi, rdi
0x180004781  jz      short loc_180004794
0x180004783  mov     rcx, rdi; hMutex
0x180004786  call    cs:__imp_ReleaseMutex
0x18000478c  test    eax, eax
0x18000478e  jz      loc_1800048EE
0x180004794  mov     rcx, rbx; hObject
0x180004797  call    cs:__imp_CloseHandle
0x18000479d  test    eax, eax
0x18000479f  jz      loc_18000487C
0x1800047a5  jmp     loc_180004669
0x1800047aa  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800047af  lea     rcx, [r14+28h]; void *
0x1800047b3  mov     dword ptr [r14], 1
0x1800047ba  xor     edx, edx; Val
0x1800047bc  mov     [r14+8], rbx
0x1800047c0  mov     r8d, 108h; Size
0x1800047c6  movdqu  xmmword ptr [r14+10h], xmm0
0x1800047cc  call    memset_0
0x1800047d1  xor     eax, eax
0x1800047d3  lea     rcx, [r14+28h]; this
0x1800047d7  mov     [r14+20h], rax
0x1800047db  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800047e0  lea     rbx, [r14+0E8h]
0x1800047e7  xor     r8d, r8d; Flags
0x1800047ea  mov     rcx, rbx; lpCriticalSection
0x1800047ed  xor     edx, edx; dwSpinCount
0x1800047ef  call    cs:__imp_InitializeCriticalSectionEx
0x1800047f5  mov     qword ptr [rbx+28h], 0
0x1800047fd  mov     qword ptr [rbx+30h], 0
0x180004805  mov     qword ptr [rbx+38h], 0
0x18000480d  mov     qword ptr [rbx+40h], 0
0x180004815  xor     ebx, ebx
0x180004817  mov     [r15], r14
0x18000481a  test    rdi, rdi
0x18000481d  jz      short loc_180004830
0x18000481f  mov     rcx, rdi; hMutex
0x180004822  call    cs:__imp_ReleaseMutex
0x180004828  test    eax, eax
0x18000482a  jz      loc_180004900
0x180004830  test    rbx, rbx
0x180004833  jz      short loc_180004842
0x180004835  mov     rcx, rbx; hObject
0x180004838  call    cs:__imp_CloseHandle
0x18000483e  test    eax, eax
0x180004840  jz      short loc_18000486A
0x180004842  xor     eax, eax
0x180004844  mov     rcx, [rbp+180h+var_30]
0x18000484b  xor     rcx, rsp; StackCookie
0x18000484e  call    __security_check_cookie
0x180004853  mov     rbx, [rsp+280h+arg_10]
0x18000485b  add     rsp, 260h
0x180004862  pop     r15
0x180004864  pop     r14
0x180004866  pop     rdi
0x180004867  pop     rsi
0x180004868  pop     rbp
0x180004869  retn
0x18000486a  mov     rcx, [rbp+188h]; this
0x180004871  mov     edx, 0A0Bh; void *
0x180004876  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000487c  mov     rcx, [rbp+188h]; this
0x180004883  mov     edx, 0A0Bh; void *
0x180004888  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000488e  mov     rcx, [rbp+188h]; this
0x180004895  mov     edx, 0E01h; void *
0x18000489a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800048a0  mov     rcx, [rbp+188h]; this
0x1800048a7  mov     edx, 0A15h; void *
0x1800048ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048b2  mov     rcx, [rbp+188h]; this
0x1800048b9  mov     edx, 0A0Bh; void *
0x1800048be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048c4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800048ca  mov     rcx, [rbp+188h]; this
0x1800048d1  mov     edx, 0A0Bh; void *
0x1800048d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048dc  mov     rcx, [rbp+188h]; this
0x1800048e3  mov     edx, 0A0Bh; void *
0x1800048e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048ee  mov     rcx, [rbp+188h]; this
0x1800048f5  mov     edx, 0A15h; void *
0x1800048fa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004900  mov     rcx, [rbp+188h]; this
0x180004907  mov     edx, 0A15h; void *
0x18000490c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
