# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000942c`
- end: `0x1400097f3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140009d14`

## callees

- `0x1400023f3`
- `0x14000849c`
- `0x14000942c`
- `0x14000992c`
- `0x140009f68`
- `0x14000a7c8`
- `0x14000bc90`
- `0x14000d2a4`
- `0x14000dc80`
- `0x14000e0ac`
- `0x14000ecd4`
- `0x14000ece4`
- `0x140011e10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140009465`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140009465`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000962e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000967d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000971e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140009616`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000962e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000967d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000971e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009545`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000966c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009708`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009545`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000966c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009708`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400094c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400094c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1400096d5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1400096d5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400094a3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400094a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000964a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000964a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000963c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000963c`

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
0x14000942c  mov     [rsp-8+arg_10], rbx
0x140009431  push    rbp
0x140009432  push    rsi
0x140009433  push    rdi
0x140009434  push    r14
0x140009436  push    r15
0x140009438  lea     rbp, [rsp-160h]
0x140009440  sub     rsp, 260h
0x140009447  mov     rax, cs:__security_cookie
0x14000944e  xor     rax, rsp
0x140009451  mov     [rbp+180h+var_30], rax
0x140009458  mov     r15, rdx
0x14000945b  mov     qword ptr [rdx], 0
0x140009462  mov     rbx, rcx
0x140009465  call    cs:__imp_GetCurrentProcessId
0x14000946b  mov     r14d, 130h
0x140009471  mov     [rsp+280h+var_258], rbx
0x140009476  mov     r9d, eax
0x140009479  mov     [rsp+280h+var_260], r14d; int
0x14000947e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009485  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000948a  lea     edx, [r14-2Ch]; unsigned __int64
0x14000948e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009493  mov     r9d, 1F0001h; dwDesiredAccess
0x140009499  lea     rdx, [rsp+280h+Name]; lpName
0x14000949e  xor     r8d, r8d; dwFlags
0x1400094a1  xor     ecx, ecx; lpMutexAttributes
0x1400094a3  call    cs:__imp_CreateMutexExW
0x1400094a9  mov     rbx, rax
0x1400094ac  test    rax, rax
0x1400094af  jnz     short loc_1400094BB
0x1400094b1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400094b6  jmp     loc_14000972A
0x1400094bb  xor     r8d, r8d; bAlertable
0x1400094be  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400094c1  mov     rcx, rbx; hHandle
0x1400094c4  call    cs:__imp_WaitForSingleObjectEx
0x1400094ca  cmp     eax, 102h
0x1400094cf  jz      short loc_1400094E1
0x1400094d1  test    eax, 0FFFFFF7Fh
0x1400094d6  jnz     loc_140009774
0x1400094dc  mov     rdi, rbx
0x1400094df  jmp     short loc_1400094E3
0x1400094e1  xor     edi, edi
0x1400094e3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400094e8  mov     [rsp+280h+hObject], 0
0x1400094f1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400094f6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400094fb  mov     esi, eax
0x1400094fd  test    eax, eax
0x1400094ff  jns     short loc_14000956B
0x140009501  mov     rcx, [rbp+188h]; this
0x140009508  mov     r9d, eax; char *
0x14000950b  mov     edx, 66h ; 'f'; void *
0x140009510  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009515  mov     rcx, [rbp+188h]; this
0x14000951c  mov     r9d, esi; char *
0x14000951f  mov     edx, 6Fh ; 'o'; void *
0x140009524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009529  mov     rcx, [rbp+188h]; this
0x140009530  mov     r9d, esi; char *
0x140009533  mov     edx, 12Eh; void *
0x140009538  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000953d  test    rdi, rdi
0x140009540  jz      short loc_140009553
0x140009542  mov     rcx, rdi; hMutex
0x140009545  call    cs:__imp_ReleaseMutex
0x14000954b  test    eax, eax
0x14000954d  jz      loc_140009781
0x140009553  mov     rcx, rbx; hObject
0x140009556  call    cs:__imp_CloseHandle
0x14000955c  test    eax, eax
0x14000955e  jz      loc_140009793
0x140009564  mov     eax, esi
0x140009566  jmp     loc_14000972A
0x14000956b  mov     rax, [rsp+280h+hObject]
0x140009570  lea     rcx, ds:0[rax*4]
0x140009578  test    rcx, rcx
0x14000957b  jz      short loc_14000958B
0x14000957d  mov     [r15], rcx
0x140009580  mov     eax, [rcx]
0x140009582  inc     eax
0x140009584  mov     [rcx], eax
0x140009586  jmp     loc_140009700
0x14000958b  mov     rdx, r14; dwBytes
0x14000958e  mov     qword ptr [r15], 0
0x140009595  mov     ecx, 8; dwFlags
0x14000959a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000959f  mov     r14, rax
0x1400095a2  test    rax, rax
0x1400095a5  jnz     short loc_1400095C5
0x1400095a7  mov     rcx, [rbp+188h]; this
0x1400095ae  mov     esi, 8007000Eh
0x1400095b3  mov     r9d, esi; char *
0x1400095b6  mov     edx, 14Bh; void *
0x1400095bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400095c0  jmp     loc_140009650
0x1400095c5  xorps   xmm0, xmm0
0x1400095c8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400095ce  test    r14b, 3
0x1400095d2  jnz     loc_1400097A5
0x1400095d8  mov     r9, r14
0x1400095db  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400095e0  shr     r9, 2; unsigned __int64
0x1400095e4  lea     rcx, [rsp+280h+hObject]; this
0x1400095e9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400095ee  mov     esi, eax
0x1400095f0  test    eax, eax
0x1400095f2  jns     loc_140009690
0x1400095f8  mov     rcx, [rbp+188h]; this
0x1400095ff  mov     r9d, eax; char *
0x140009602  mov     edx, 14Eh; void *
0x140009607  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000960c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140009611  test    rcx, rcx
0x140009614  jz      short loc_140009624
0x140009616  call    cs:__imp_CloseHandle
0x14000961c  test    eax, eax
0x14000961e  jz      loc_1400097AB
0x140009624  mov     rcx, [rsp+280h+hObject]; hObject
0x140009629  test    rcx, rcx
0x14000962c  jz      short loc_14000963C
0x14000962e  call    cs:__imp_CloseHandle
0x140009634  test    eax, eax
0x140009636  jz      loc_1400097BD
0x14000963c  call    cs:__imp_GetProcessHeap
0x140009642  mov     r8, r14; lpMem
0x140009645  xor     edx, edx; dwFlags
0x140009647  mov     rcx, rax; hHeap
0x14000964a  call    cs:__imp_HeapFree
0x140009650  mov     rcx, [rbp+188h]; this
0x140009657  mov     r9d, esi; char *
0x14000965a  mov     edx, 137h; void *
0x14000965f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009664  test    rdi, rdi
0x140009667  jz      short loc_14000967A
0x140009669  mov     rcx, rdi; hMutex
0x14000966c  call    cs:__imp_ReleaseMutex
0x140009672  test    eax, eax
0x140009674  jz      loc_1400097CF
0x14000967a  mov     rcx, rbx; hObject
0x14000967d  call    cs:__imp_CloseHandle
0x140009683  test    eax, eax
0x140009685  jz      loc_140009762
0x14000968b  jmp     loc_140009564
0x140009690  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140009695  lea     rcx, [r14+28h]; void *
0x140009699  mov     dword ptr [r14], 1
0x1400096a0  xor     edx, edx; Val
0x1400096a2  mov     [r14+8], rbx
0x1400096a6  mov     r8d, 108h; Size
0x1400096ac  movdqu  xmmword ptr [r14+10h], xmm0
0x1400096b2  call    memset_0
0x1400096b7  xor     eax, eax
0x1400096b9  lea     rcx, [r14+28h]; this
0x1400096bd  mov     [r14+20h], rax
0x1400096c1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400096c6  lea     rbx, [r14+0E8h]
0x1400096cd  xor     r8d, r8d; Flags
0x1400096d0  mov     rcx, rbx; lpCriticalSection
0x1400096d3  xor     edx, edx; dwSpinCount
0x1400096d5  call    cs:__imp_InitializeCriticalSectionEx
0x1400096db  mov     qword ptr [rbx+28h], 0
0x1400096e3  mov     qword ptr [rbx+30h], 0
0x1400096eb  mov     qword ptr [rbx+38h], 0
0x1400096f3  mov     qword ptr [rbx+40h], 0
0x1400096fb  xor     ebx, ebx
0x1400096fd  mov     [r15], r14
0x140009700  test    rdi, rdi
0x140009703  jz      short loc_140009716
0x140009705  mov     rcx, rdi; hMutex
0x140009708  call    cs:__imp_ReleaseMutex
0x14000970e  test    eax, eax
0x140009710  jz      loc_1400097E1
0x140009716  test    rbx, rbx
0x140009719  jz      short loc_140009728
0x14000971b  mov     rcx, rbx; hObject
0x14000971e  call    cs:__imp_CloseHandle
0x140009724  test    eax, eax
0x140009726  jz      short loc_140009750
0x140009728  xor     eax, eax
0x14000972a  mov     rcx, [rbp+180h+var_30]
0x140009731  xor     rcx, rsp; StackCookie
0x140009734  call    __security_check_cookie
0x140009739  mov     rbx, [rsp+280h+arg_10]
0x140009741  add     rsp, 260h
0x140009748  pop     r15
0x14000974a  pop     r14
0x14000974c  pop     rdi
0x14000974d  pop     rsi
0x14000974e  pop     rbp
0x14000974f  retn
0x140009750  mov     rcx, [rbp+188h]; this
0x140009757  mov     edx, 0A0Bh; void *
0x14000975c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009762  mov     rcx, [rbp+188h]; this
0x140009769  mov     edx, 0A0Bh; void *
0x14000976e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009774  mov     rcx, [rbp+188h]; this
0x14000977b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140009781  mov     rcx, [rbp+188h]; this
0x140009788  mov     edx, 0A15h; void *
0x14000978d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009793  mov     rcx, [rbp+188h]; this
0x14000979a  mov     edx, 0A0Bh; void *
0x14000979f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400097a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400097ab  mov     rcx, [rbp+188h]; this
0x1400097b2  mov     edx, 0A0Bh; void *
0x1400097b7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400097bd  mov     rcx, [rbp+188h]; this
0x1400097c4  mov     edx, 0A0Bh; void *
0x1400097c9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400097cf  mov     rcx, [rbp+188h]; this
0x1400097d6  mov     edx, 0A15h; void *
0x1400097db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400097e1  mov     rcx, [rbp+188h]; this
0x1400097e8  mov     edx, 0A15h; void *
0x1400097ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
