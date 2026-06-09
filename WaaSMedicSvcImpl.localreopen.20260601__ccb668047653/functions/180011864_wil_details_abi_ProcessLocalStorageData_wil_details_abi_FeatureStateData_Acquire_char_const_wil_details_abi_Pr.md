# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011864`
- end: `0x180011c55`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180012658`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000a328`
- `0x18000a614`
- `0x18000ac68`
- `0x18000b7e8`
- `0x18000bbd4`
- `0x18000c638`
- `0x18000c71c`
- `0x18000cba8`
- `0x18000cbb8`
- `0x18000fb04`
- `0x180011864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800118fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800118fc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800118db`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800118db`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011992`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011ace`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011b6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011992`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011ace`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180011b6a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011b37`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011b37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011a97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001189d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001189d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011b80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011b80`

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
0x180011864  mov     [rsp-8+arg_10], rbx
0x180011869  push    rbp
0x18001186a  push    rsi
0x18001186b  push    rdi
0x18001186c  push    r14
0x18001186e  push    r15
0x180011870  lea     rbp, [rsp-160h]
0x180011878  sub     rsp, 260h
0x18001187f  mov     rax, cs:__security_cookie
0x180011886  xor     rax, rsp
0x180011889  mov     [rbp+180h+var_30], rax
0x180011890  mov     r15, rdx
0x180011893  mov     qword ptr [rdx], 0
0x18001189a  mov     rbx, rcx
0x18001189d  call    cs:__imp_GetCurrentProcessId
0x1800118a3  mov     r14d, 130h
0x1800118a9  mov     [rsp+280h+var_258], rbx
0x1800118ae  mov     r9d, eax
0x1800118b1  mov     [rsp+280h+var_260], r14d; int
0x1800118b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800118bd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800118c2  lea     edx, [r14-2Ch]; unsigned __int64
0x1800118c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800118cb  mov     r9d, 1F0001h; dwDesiredAccess
0x1800118d1  lea     rdx, [rsp+280h+Name]; lpName
0x1800118d6  xor     r8d, r8d; dwFlags
0x1800118d9  xor     ecx, ecx; lpMutexAttributes
0x1800118db  call    cs:__imp_CreateMutexExW
0x1800118e1  mov     rbx, rax
0x1800118e4  test    rax, rax
0x1800118e7  jnz     short loc_1800118F3
0x1800118e9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800118ee  jmp     loc_180011B8C
0x1800118f3  xor     r8d, r8d; bAlertable
0x1800118f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800118f9  mov     rcx, rbx; hHandle
0x1800118fc  call    cs:__imp_WaitForSingleObjectEx
0x180011902  cmp     eax, 102h
0x180011907  jz      short loc_180011919
0x180011909  test    eax, 0FFFFFF7Fh
0x18001190e  jnz     loc_180011BD6
0x180011914  mov     rdi, rbx
0x180011917  jmp     short loc_18001191B
0x180011919  xor     edi, edi
0x18001191b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180011920  mov     [rsp+280h+hObject], 0
0x180011929  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001192e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180011933  mov     esi, eax
0x180011935  test    eax, eax
0x180011937  jns     short loc_1800119B8
0x180011939  mov     rcx, [rbp+188h]; this
0x180011940  lea     r8, aWil; "wil"
0x180011947  mov     r9d, eax; char *
0x18001194a  mov     edx, 66h ; 'f'; void *
0x18001194f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011954  mov     rcx, [rbp+188h]; this
0x18001195b  lea     r8, aWil; "wil"
0x180011962  mov     r9d, esi; char *
0x180011965  mov     edx, 6Fh ; 'o'; void *
0x18001196a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001196f  mov     rcx, [rbp+188h]; this
0x180011976  lea     r8, aWil; "wil"
0x18001197d  mov     r9d, esi; char *
0x180011980  mov     edx, 12Eh; void *
0x180011985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001198a  test    rdi, rdi
0x18001198d  jz      short loc_1800119A0
0x18001198f  mov     rcx, rdi; hMutex
0x180011992  call    cs:__imp_ReleaseMutex
0x180011998  test    eax, eax
0x18001199a  jz      loc_180011BE3
0x1800119a0  mov     rcx, rbx; hObject
0x1800119a3  call    cs:__imp_CloseHandle
0x1800119a9  test    eax, eax
0x1800119ab  jz      loc_180011BF5
0x1800119b1  mov     eax, esi
0x1800119b3  jmp     loc_180011B8C
0x1800119b8  mov     rax, [rsp+280h+hObject]
0x1800119bd  lea     rcx, ds:0[rax*4]
0x1800119c5  test    rcx, rcx
0x1800119c8  jz      short loc_1800119D8
0x1800119ca  mov     [r15], rcx
0x1800119cd  mov     eax, [rcx]
0x1800119cf  inc     eax
0x1800119d1  mov     [rcx], eax
0x1800119d3  jmp     loc_180011B62
0x1800119d8  mov     rdx, r14; dwBytes
0x1800119db  mov     qword ptr [r15], 0
0x1800119e2  mov     ecx, 8; dwFlags
0x1800119e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800119ec  mov     r14, rax
0x1800119ef  test    rax, rax
0x1800119f2  jnz     short loc_180011A19
0x1800119f4  mov     rcx, [rbp+188h]; this
0x1800119fb  lea     r8, aWil; "wil"
0x180011a02  mov     esi, 8007000Eh
0x180011a07  mov     edx, 14Bh; void *
0x180011a0c  mov     r9d, esi; char *
0x180011a0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a14  jmp     loc_180011AAB
0x180011a19  xorps   xmm0, xmm0
0x180011a1c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180011a22  test    r14b, 3
0x180011a26  jnz     loc_180011C07
0x180011a2c  mov     r9, r14
0x180011a2f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180011a34  shr     r9, 2; unsigned __int64
0x180011a38  lea     rcx, [rsp+280h+hObject]; this
0x180011a3d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180011a42  mov     esi, eax
0x180011a44  test    eax, eax
0x180011a46  jns     loc_180011AF2
0x180011a4c  mov     rcx, [rbp+188h]; this
0x180011a53  lea     r8, aWil; "wil"
0x180011a5a  mov     r9d, eax; char *
0x180011a5d  mov     edx, 14Eh; void *
0x180011a62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a67  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180011a6c  test    rcx, rcx
0x180011a6f  jz      short loc_180011A7F
0x180011a71  call    cs:__imp_CloseHandle
0x180011a77  test    eax, eax
0x180011a79  jz      loc_180011C0D
0x180011a7f  mov     rcx, [rsp+280h+hObject]; hObject
0x180011a84  test    rcx, rcx
0x180011a87  jz      short loc_180011A97
0x180011a89  call    cs:__imp_CloseHandle
0x180011a8f  test    eax, eax
0x180011a91  jz      loc_180011C1F
0x180011a97  call    cs:__imp_GetProcessHeap
0x180011a9d  mov     r8, r14; lpMem
0x180011aa0  xor     edx, edx; dwFlags
0x180011aa2  mov     rcx, rax; hHeap
0x180011aa5  call    cs:__imp_HeapFree
0x180011aab  mov     rcx, [rbp+188h]; this
0x180011ab2  lea     r8, aWil; "wil"
0x180011ab9  mov     r9d, esi; char *
0x180011abc  mov     edx, 137h; void *
0x180011ac1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ac6  test    rdi, rdi
0x180011ac9  jz      short loc_180011ADC
0x180011acb  mov     rcx, rdi; hMutex
0x180011ace  call    cs:__imp_ReleaseMutex
0x180011ad4  test    eax, eax
0x180011ad6  jz      loc_180011C31
0x180011adc  mov     rcx, rbx; hObject
0x180011adf  call    cs:__imp_CloseHandle
0x180011ae5  test    eax, eax
0x180011ae7  jz      loc_180011BC4
0x180011aed  jmp     loc_1800119B1
0x180011af2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180011af7  lea     rcx, [r14+28h]; void *
0x180011afb  mov     dword ptr [r14], 1
0x180011b02  xor     edx, edx; Val
0x180011b04  mov     [r14+8], rbx
0x180011b08  mov     r8d, 108h; Size
0x180011b0e  movdqu  xmmword ptr [r14+10h], xmm0
0x180011b14  call    memset_0
0x180011b19  xor     eax, eax
0x180011b1b  lea     rcx, [r14+28h]; this
0x180011b1f  mov     [r14+20h], rax
0x180011b23  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180011b28  lea     rbx, [r14+0E8h]
0x180011b2f  xor     r8d, r8d; Flags
0x180011b32  mov     rcx, rbx; lpCriticalSection
0x180011b35  xor     edx, edx; dwSpinCount
0x180011b37  call    cs:__imp_InitializeCriticalSectionEx
0x180011b3d  mov     qword ptr [rbx+28h], 0
0x180011b45  mov     qword ptr [rbx+30h], 0
0x180011b4d  mov     qword ptr [rbx+38h], 0
0x180011b55  mov     qword ptr [rbx+40h], 0
0x180011b5d  xor     ebx, ebx
0x180011b5f  mov     [r15], r14
0x180011b62  test    rdi, rdi
0x180011b65  jz      short loc_180011B78
0x180011b67  mov     rcx, rdi; hMutex
0x180011b6a  call    cs:__imp_ReleaseMutex
0x180011b70  test    eax, eax
0x180011b72  jz      loc_180011C43
0x180011b78  test    rbx, rbx
0x180011b7b  jz      short loc_180011B8A
0x180011b7d  mov     rcx, rbx; hObject
0x180011b80  call    cs:__imp_CloseHandle
0x180011b86  test    eax, eax
0x180011b88  jz      short loc_180011BB2
0x180011b8a  xor     eax, eax
0x180011b8c  mov     rcx, [rbp+180h+var_30]
0x180011b93  xor     rcx, rsp; StackCookie
0x180011b96  call    __security_check_cookie
0x180011b9b  mov     rbx, [rsp+280h+arg_10]
0x180011ba3  add     rsp, 260h
0x180011baa  pop     r15
0x180011bac  pop     r14
0x180011bae  pop     rdi
0x180011baf  pop     rsi
0x180011bb0  pop     rbp
0x180011bb1  retn
0x180011bb2  mov     rcx, [rbp+188h]; this
0x180011bb9  mov     edx, 0A0Bh; void *
0x180011bbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011bc4  mov     rcx, [rbp+188h]; this
0x180011bcb  mov     edx, 0A0Bh; void *
0x180011bd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011bd6  mov     rcx, [rbp+188h]; this
0x180011bdd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180011be3  mov     rcx, [rbp+188h]; this
0x180011bea  mov     edx, 0A15h; void *
0x180011bef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011bf5  mov     rcx, [rbp+188h]; this
0x180011bfc  mov     edx, 0A0Bh; void *
0x180011c01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011c07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011c0d  mov     rcx, [rbp+188h]; this
0x180011c14  mov     edx, 0A0Bh; void *
0x180011c19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011c1f  mov     rcx, [rbp+188h]; this
0x180011c26  mov     edx, 0A0Bh; void *
0x180011c2b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011c31  mov     rcx, [rbp+188h]; this
0x180011c38  mov     edx, 0A15h; void *
0x180011c3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011c43  mov     rcx, [rbp+188h]; this
0x180011c4a  mov     edx, 0A15h; void *
0x180011c4f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
