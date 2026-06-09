# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000421c`
- end: `0x1400045e3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x14000492c`

## callees

- `0x1400016a0`
- `0x140002168`
- `0x1400031c4`
- `0x14000421c`
- `0x140004600`
- `0x140004b80`
- `0x140006560`
- `0x140007d2c`
- `0x1400098a4`
- `0x14000a800`
- `0x14000ac6c`
- `0x14000b51c`
- `0x14000b52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004293`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004293`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400042b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400042b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000445c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400044f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004335`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000445c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400044f8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1400044c5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1400044c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000443a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000443a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000442c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000442c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000441e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000446d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000450e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004406`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000441e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000446d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000450e`

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
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v9, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x14000421c  mov     [rsp-8+arg_10], rbx
0x140004221  push    rbp
0x140004222  push    rsi
0x140004223  push    rdi
0x140004224  push    r14
0x140004226  push    r15
0x140004228  lea     rbp, [rsp-160h]
0x140004230  sub     rsp, 260h
0x140004237  mov     rax, cs:__security_cookie
0x14000423e  xor     rax, rsp
0x140004241  mov     [rbp+180h+var_30], rax
0x140004248  mov     r15, rdx
0x14000424b  mov     qword ptr [rdx], 0
0x140004252  mov     rbx, rcx
0x140004255  call    cs:__imp_GetCurrentProcessId
0x14000425b  mov     r14d, 130h
0x140004261  mov     [rsp+280h+var_258], rbx
0x140004266  mov     r9d, eax
0x140004269  mov     [rsp+280h+var_260], r14d; int
0x14000426e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004275  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000427a  lea     edx, [r14-2Ch]; unsigned __int64
0x14000427e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004283  mov     r9d, 1F0001h; dwDesiredAccess
0x140004289  lea     rdx, [rsp+280h+Name]; lpName
0x14000428e  xor     r8d, r8d; dwFlags
0x140004291  xor     ecx, ecx; lpMutexAttributes
0x140004293  call    cs:__imp_CreateMutexExW
0x140004299  mov     rbx, rax
0x14000429c  test    rax, rax
0x14000429f  jnz     short loc_1400042AB
0x1400042a1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400042a6  jmp     loc_14000451A
0x1400042ab  xor     r8d, r8d; bAlertable
0x1400042ae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400042b1  mov     rcx, rbx; hHandle
0x1400042b4  call    cs:__imp_WaitForSingleObjectEx
0x1400042ba  cmp     eax, 102h
0x1400042bf  jz      short loc_1400042D1
0x1400042c1  test    eax, 0FFFFFF7Fh
0x1400042c6  jnz     loc_140004564
0x1400042cc  mov     rdi, rbx
0x1400042cf  jmp     short loc_1400042D3
0x1400042d1  xor     edi, edi
0x1400042d3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400042d8  mov     [rsp+280h+hObject], 0
0x1400042e1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400042e6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400042eb  mov     esi, eax
0x1400042ed  test    eax, eax
0x1400042ef  jns     short loc_14000435B
0x1400042f1  mov     rcx, [rbp+188h]; this
0x1400042f8  mov     r9d, eax; char *
0x1400042fb  mov     edx, 66h ; 'f'; void *
0x140004300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004305  mov     rcx, [rbp+188h]; this
0x14000430c  mov     r9d, esi; char *
0x14000430f  mov     edx, 6Fh ; 'o'; void *
0x140004314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004319  mov     rcx, [rbp+188h]; this
0x140004320  mov     r9d, esi; char *
0x140004323  mov     edx, 12Eh; void *
0x140004328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000432d  test    rdi, rdi
0x140004330  jz      short loc_140004343
0x140004332  mov     rcx, rdi; hMutex
0x140004335  call    cs:__imp_ReleaseMutex
0x14000433b  test    eax, eax
0x14000433d  jz      loc_140004571
0x140004343  mov     rcx, rbx; hObject
0x140004346  call    cs:__imp_CloseHandle
0x14000434c  test    eax, eax
0x14000434e  jz      loc_140004583
0x140004354  mov     eax, esi
0x140004356  jmp     loc_14000451A
0x14000435b  mov     rax, [rsp+280h+hObject]
0x140004360  lea     rcx, ds:0[rax*4]
0x140004368  test    rcx, rcx
0x14000436b  jz      short loc_14000437B
0x14000436d  mov     [r15], rcx
0x140004370  mov     eax, [rcx]
0x140004372  inc     eax
0x140004374  mov     [rcx], eax
0x140004376  jmp     loc_1400044F0
0x14000437b  mov     rdx, r14; dwBytes
0x14000437e  mov     qword ptr [r15], 0
0x140004385  mov     ecx, 8; dwFlags
0x14000438a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000438f  mov     r14, rax
0x140004392  test    rax, rax
0x140004395  jnz     short loc_1400043B5
0x140004397  mov     rcx, [rbp+188h]; this
0x14000439e  mov     esi, 8007000Eh
0x1400043a3  mov     r9d, esi; char *
0x1400043a6  mov     edx, 14Bh; void *
0x1400043ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400043b0  jmp     loc_140004440
0x1400043b5  xorps   xmm0, xmm0
0x1400043b8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400043be  test    r14b, 3
0x1400043c2  jnz     loc_140004595
0x1400043c8  mov     r9, r14
0x1400043cb  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400043d0  shr     r9, 2; unsigned __int64
0x1400043d4  lea     rcx, [rsp+280h+hObject]; this
0x1400043d9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400043de  mov     esi, eax
0x1400043e0  test    eax, eax
0x1400043e2  jns     loc_140004480
0x1400043e8  mov     rcx, [rbp+188h]; this
0x1400043ef  mov     r9d, eax; char *
0x1400043f2  mov     edx, 14Eh; void *
0x1400043f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400043fc  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140004401  test    rcx, rcx
0x140004404  jz      short loc_140004414
0x140004406  call    cs:__imp_CloseHandle
0x14000440c  test    eax, eax
0x14000440e  jz      loc_14000459B
0x140004414  mov     rcx, [rsp+280h+hObject]; hObject
0x140004419  test    rcx, rcx
0x14000441c  jz      short loc_14000442C
0x14000441e  call    cs:__imp_CloseHandle
0x140004424  test    eax, eax
0x140004426  jz      loc_1400045AD
0x14000442c  call    cs:__imp_GetProcessHeap
0x140004432  mov     r8, r14; lpMem
0x140004435  xor     edx, edx; dwFlags
0x140004437  mov     rcx, rax; hHeap
0x14000443a  call    cs:__imp_HeapFree
0x140004440  mov     rcx, [rbp+188h]; this
0x140004447  mov     r9d, esi; char *
0x14000444a  mov     edx, 137h; void *
0x14000444f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004454  test    rdi, rdi
0x140004457  jz      short loc_14000446A
0x140004459  mov     rcx, rdi; hMutex
0x14000445c  call    cs:__imp_ReleaseMutex
0x140004462  test    eax, eax
0x140004464  jz      loc_1400045BF
0x14000446a  mov     rcx, rbx; hObject
0x14000446d  call    cs:__imp_CloseHandle
0x140004473  test    eax, eax
0x140004475  jz      loc_140004552
0x14000447b  jmp     loc_140004354
0x140004480  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140004485  lea     rcx, [r14+28h]; void *
0x140004489  mov     dword ptr [r14], 1
0x140004490  xor     edx, edx; Val
0x140004492  mov     [r14+8], rbx
0x140004496  mov     r8d, 108h; Size
0x14000449c  movdqu  xmmword ptr [r14+10h], xmm0
0x1400044a2  call    memset_0
0x1400044a7  xor     eax, eax
0x1400044a9  lea     rcx, [r14+28h]; this
0x1400044ad  mov     [r14+20h], rax
0x1400044b1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400044b6  lea     rbx, [r14+0E8h]
0x1400044bd  xor     r8d, r8d; Flags
0x1400044c0  mov     rcx, rbx; lpCriticalSection
0x1400044c3  xor     edx, edx; dwSpinCount
0x1400044c5  call    cs:__imp_InitializeCriticalSectionEx
0x1400044cb  mov     qword ptr [rbx+28h], 0
0x1400044d3  mov     qword ptr [rbx+30h], 0
0x1400044db  mov     qword ptr [rbx+38h], 0
0x1400044e3  mov     qword ptr [rbx+40h], 0
0x1400044eb  xor     ebx, ebx
0x1400044ed  mov     [r15], r14
0x1400044f0  test    rdi, rdi
0x1400044f3  jz      short loc_140004506
0x1400044f5  mov     rcx, rdi; hMutex
0x1400044f8  call    cs:__imp_ReleaseMutex
0x1400044fe  test    eax, eax
0x140004500  jz      loc_1400045D1
0x140004506  test    rbx, rbx
0x140004509  jz      short loc_140004518
0x14000450b  mov     rcx, rbx; hObject
0x14000450e  call    cs:__imp_CloseHandle
0x140004514  test    eax, eax
0x140004516  jz      short loc_140004540
0x140004518  xor     eax, eax
0x14000451a  mov     rcx, [rbp+180h+var_30]
0x140004521  xor     rcx, rsp; StackCookie
0x140004524  call    __security_check_cookie
0x140004529  mov     rbx, [rsp+280h+arg_10]
0x140004531  add     rsp, 260h
0x140004538  pop     r15
0x14000453a  pop     r14
0x14000453c  pop     rdi
0x14000453d  pop     rsi
0x14000453e  pop     rbp
0x14000453f  retn
0x140004540  mov     rcx, [rbp+188h]; this
0x140004547  mov     edx, 0A0Bh; void *
0x14000454c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004552  mov     rcx, [rbp+188h]; this
0x140004559  mov     edx, 0A0Bh; void *
0x14000455e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004564  mov     rcx, [rbp+188h]; this
0x14000456b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004571  mov     rcx, [rbp+188h]; this
0x140004578  mov     edx, 0A15h; void *
0x14000457d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004583  mov     rcx, [rbp+188h]; this
0x14000458a  mov     edx, 0A0Bh; void *
0x14000458f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004595  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000459b  mov     rcx, [rbp+188h]; this
0x1400045a2  mov     edx, 0A0Bh; void *
0x1400045a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400045ad  mov     rcx, [rbp+188h]; this
0x1400045b4  mov     edx, 0A0Bh; void *
0x1400045b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400045bf  mov     rcx, [rbp+188h]; this
0x1400045c6  mov     edx, 0A15h; void *
0x1400045cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400045d1  mov     rcx, [rbp+188h]; this
0x1400045d8  mov     edx, 0A15h; void *
0x1400045dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
