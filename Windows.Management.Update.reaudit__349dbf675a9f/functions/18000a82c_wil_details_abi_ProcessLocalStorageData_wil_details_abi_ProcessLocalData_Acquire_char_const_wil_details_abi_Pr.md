# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000a82c`
- end: `0x18000abe9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `957`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c450`

## callees

- `0x180002880`
- `0x1800035cc`
- `0x18000a35c`
- `0x18000a82c`
- `0x18000afc8`
- `0x18000b408`
- `0x18000c1b8`
- `0x18000d154`
- `0x18000eb04`
- `0x18000f648`
- `0x18000fb7c`
- `0x180010474`
- `0x18001080c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000a8ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a8e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a8e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a967`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aa76`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ab1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a967`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000aa76`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000ab1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a862`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a862`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a97e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a97e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aa92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ab37`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rdi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rsi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  HANDLE v23; // rdi
  _QWORD *v24; // rax
  unsigned int v25; // r8d
  _QWORD *v26; // rbx
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int64 v36; // rax
  __int64 v37; // rax
  unsigned int v38; // r8d
  const char *v39; // r9
  unsigned int v40; // r8d
  const char *v41; // r9
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v46; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  v6 = hHandle;
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
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
  v47 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v47, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v15, v42);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v15, v43);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v47);
  if ( 4 * v47 )
  {
    *a2 = v22;
    v23 = hHandle;
    *(_DWORD *)*a2 = *v22 + 1;
    goto LABEL_24;
  }
  *a2 = 0;
  v24 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = v24;
  if ( v24 )
  {
    v46 = 0;
    v29 = wil::details_abi::SemaphoreValue::CreateFromPointer(
            (wil::details_abi::SemaphoreValue *)&v46,
            (char *)Name,
            (unsigned __int64)v24);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v36 = v46;
      v26[1] = v6;
      v23 = 0;
      v26[2] = v36;
      v37 = *((_QWORD *)&v46 + 1);
      v46 = 0u;
      *(_DWORD *)v26 = 1;
      hHandle = 0;
      v26[3] = v37;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      *a2 = v26;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v46);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v38, v39);
      if ( v23 && !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v40, v41);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v30, (const char *)(unsigned int)v29, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v46);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v28, (const char *)v27, v44);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E7, v32, v33);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
  return v27;
}

```

## disassembly

```asm
0x18000a82c  mov     [rsp-8+arg_10], rbx
0x18000a831  push    rbp
0x18000a832  push    rsi
0x18000a833  push    rdi
0x18000a834  push    r14
0x18000a836  push    r15
0x18000a838  lea     rbp, [rsp-170h]
0x18000a840  sub     rsp, 270h
0x18000a847  mov     rax, cs:__security_cookie
0x18000a84e  xor     rax, rsp
0x18000a851  mov     [rbp+190h+var_30], rax
0x18000a858  and     qword ptr [rdx], 0
0x18000a85c  mov     r15, rdx
0x18000a85f  mov     rbx, rcx
0x18000a862  call    cs:__imp_GetCurrentProcessId
0x18000a869  nop     dword ptr [rax+rax+00h]
0x18000a86e  mov     r14d, 78h ; 'x'
0x18000a874  mov     [rsp+290h+var_268], rbx
0x18000a879  mov     r9d, eax
0x18000a87c  mov     [rsp+290h+var_270], r14d; int
0x18000a881  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000a888  mov     edx, 104h; unsigned __int64
0x18000a88d  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a892  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a897  and     [rsp+290h+hHandle], 0
0x18000a89d  lea     rdx, [rsp+290h+Name]; lpName
0x18000a8a2  mov     r9d, 1F0001h; dwDesiredAccess
0x18000a8a8  xor     r8d, r8d; dwFlags
0x18000a8ab  xor     ecx, ecx; lpMutexAttributes
0x18000a8ad  call    cs:__imp_CreateMutexExW
0x18000a8b4  nop     dword ptr [rax+rax+00h]
0x18000a8b9  mov     rdx, rax
0x18000a8bc  lea     rcx, [rsp+290h+hHandle]
0x18000a8c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000a8c6  mov     rdi, [rsp+290h+hHandle]
0x18000a8cb  test    rdi, rdi
0x18000a8ce  jnz     short loc_18000A8DA
0x18000a8d0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a8d5  jmp     loc_18000AB49
0x18000a8da  xor     r8d, r8d; bAlertable
0x18000a8dd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a8e0  mov     rcx, rdi; hHandle
0x18000a8e3  call    cs:__imp_WaitForSingleObjectEx
0x18000a8ea  nop     dword ptr [rax+rax+00h]
0x18000a8ef  cmp     eax, 102h
0x18000a8f4  jz      short loc_18000A906
0x18000a8f6  test    eax, 0FFFFFF7Fh
0x18000a8fb  jnz     loc_18000AB82
0x18000a901  mov     rsi, rdi
0x18000a904  jmp     short loc_18000A908
0x18000a906  xor     esi, esi
0x18000a908  and     [rsp+290h+var_248], 0
0x18000a90e  lea     r8, [rsp+290h+var_248]; unsigned __int64 *
0x18000a913  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000a918  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000a91d  mov     ebx, eax
0x18000a91f  test    eax, eax
0x18000a921  jns     short loc_18000A999
0x18000a923  mov     rcx, [rbp+198h]; this
0x18000a92a  mov     r9d, eax; char *
0x18000a92d  mov     edx, 64h ; 'd'; void *
0x18000a932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a937  mov     rcx, [rbp+198h]; this
0x18000a93e  mov     r9d, ebx; char *
0x18000a941  mov     edx, 6Dh ; 'm'; void *
0x18000a946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a94b  mov     rcx, [rbp+198h]; this
0x18000a952  mov     r9d, ebx; char *
0x18000a955  mov     edx, 12Bh; void *
0x18000a95a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a95f  test    rsi, rsi
0x18000a962  jz      short loc_18000A97B
0x18000a964  mov     rcx, rsi; hMutex
0x18000a967  call    cs:__imp_ReleaseMutex
0x18000a96e  nop     dword ptr [rax+rax+00h]
0x18000a973  test    eax, eax
0x18000a975  jz      loc_18000AB8F
0x18000a97b  mov     rcx, rdi; hObject
0x18000a97e  call    cs:__imp_CloseHandle
0x18000a985  nop     dword ptr [rax+rax+00h]
0x18000a98a  test    eax, eax
0x18000a98c  jz      loc_18000ABA1
0x18000a992  mov     eax, ebx
0x18000a994  jmp     loc_18000AB49
0x18000a999  mov     rax, [rsp+290h+var_248]
0x18000a99e  lea     rcx, ds:0[rax*4]
0x18000a9a6  test    rcx, rcx
0x18000a9a9  jz      short loc_18000A9C1
0x18000a9ab  mov     [r15], rcx
0x18000a9ae  mov     ecx, [rcx]
0x18000a9b0  mov     rax, [r15]
0x18000a9b3  inc     ecx
0x18000a9b5  mov     rdi, [rsp+290h+hHandle]
0x18000a9ba  mov     [rax], ecx
0x18000a9bc  jmp     loc_18000AB13
0x18000a9c1  and     qword ptr [r15], 0
0x18000a9c5  mov     rdx, r14; dwBytes
0x18000a9c8  mov     ecx, 8; dwFlags
0x18000a9cd  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a9d2  mov     rbx, rax
0x18000a9d5  test    rax, rax
0x18000a9d8  jnz     short loc_18000A9F6
0x18000a9da  mov     rcx, [rbp+198h]; this
0x18000a9e1  mov     r14d, 8007000Eh
0x18000a9e7  mov     r9d, r14d; char *
0x18000a9ea  mov     edx, 148h; void *
0x18000a9ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a9f4  jmp     short loc_18000AA5A
0x18000a9f6  xorps   xmm0, xmm0
0x18000a9f9  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000a9fe  mov     r8, rbx; void *
0x18000aa01  lea     rcx, [rsp+290h+var_258]; this
0x18000aa06  movdqu  [rsp+290h+var_258], xmm0
0x18000aa0c  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000aa11  mov     r14d, eax
0x18000aa14  test    eax, eax
0x18000aa16  jns     loc_18000AAAE
0x18000aa1c  mov     rcx, [rbp+198h]; this
0x18000aa23  mov     r9d, eax; char *
0x18000aa26  mov     edx, 14Bh; void *
0x18000aa2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa30  lea     rcx, [rsp+290h+var_258]; this
0x18000aa35  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000aa3a  call    cs:__imp_GetProcessHeap
0x18000aa41  nop     dword ptr [rax+rax+00h]
0x18000aa46  mov     r8, rbx; lpMem
0x18000aa49  xor     edx, edx; dwFlags
0x18000aa4b  mov     rcx, rax; hHeap
0x18000aa4e  call    cs:__imp_HeapFree
0x18000aa55  nop     dword ptr [rax+rax+00h]
0x18000aa5a  mov     rcx, [rbp+198h]; this
0x18000aa61  mov     r9d, r14d; char *
0x18000aa64  mov     edx, 134h; void *
0x18000aa69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa6e  test    rsi, rsi
0x18000aa71  jz      short loc_18000AA8A
0x18000aa73  mov     rcx, rsi; hMutex
0x18000aa76  call    cs:__imp_ReleaseMutex
0x18000aa7d  nop     dword ptr [rax+rax+00h]
0x18000aa82  test    eax, eax
0x18000aa84  jz      loc_18000ABB3
0x18000aa8a  test    rdi, rdi
0x18000aa8d  jz      short loc_18000AAA6
0x18000aa8f  mov     rcx, rdi; hObject
0x18000aa92  call    cs:__imp_CloseHandle
0x18000aa99  nop     dword ptr [rax+rax+00h]
0x18000aa9e  test    eax, eax
0x18000aaa0  jz      loc_18000ABC5
0x18000aaa6  mov     eax, r14d
0x18000aaa9  jmp     loc_18000AB49
0x18000aaae  mov     rax, qword ptr [rsp+290h+var_258]
0x18000aab3  lea     rcx, [rbx+22h]; void *
0x18000aab7  mov     [rbx+8], rdi
0x18000aabb  xor     edx, edx; Val
0x18000aabd  xor     edi, edi
0x18000aabf  mov     [rbx+10h], rax
0x18000aac3  mov     rax, qword ptr [rsp+290h+var_258+8]
0x18000aac8  and     qword ptr [rsp+290h+var_258], rdi
0x18000aacd  and     qword ptr [rsp+290h+var_258+8], rdi
0x18000aad2  lea     r8d, [rdi+56h]; Size
0x18000aad6  mov     dword ptr [rbx], 1
0x18000aadc  mov     [rsp+290h+hHandle], rdi
0x18000aae1  mov     [rbx+18h], rax
0x18000aae5  call    memset_0
0x18000aaea  mov     word ptr [rbx+20h], 58h ; 'X'
0x18000aaf0  lea     rcx, [rbx+28h]; void *
0x18000aaf4  xor     edx, edx; Val
0x18000aaf6  mov     dword ptr [rbx+24h], 1
0x18000aafd  lea     r8d, [rdi+50h]; Size
0x18000ab01  call    memset_0
0x18000ab06  lea     rcx, [rsp+290h+var_258]; this
0x18000ab0b  mov     [r15], rbx
0x18000ab0e  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ab13  test    rsi, rsi
0x18000ab16  jz      short loc_18000AB2F
0x18000ab18  mov     rcx, rsi; hMutex
0x18000ab1b  call    cs:__imp_ReleaseMutex
0x18000ab22  nop     dword ptr [rax+rax+00h]
0x18000ab27  test    eax, eax
0x18000ab29  jz      loc_18000ABD7
0x18000ab2f  test    rdi, rdi
0x18000ab32  jz      short loc_18000AB47
0x18000ab34  mov     rcx, rdi; hObject
0x18000ab37  call    cs:__imp_CloseHandle
0x18000ab3e  nop     dword ptr [rax+rax+00h]
0x18000ab43  test    eax, eax
0x18000ab45  jz      short loc_18000AB70
0x18000ab47  xor     eax, eax
0x18000ab49  mov     rcx, [rbp+190h+var_30]
0x18000ab50  xor     rcx, rsp; StackCookie
0x18000ab53  call    __security_check_cookie
0x18000ab58  mov     rbx, [rsp+290h+arg_10]
0x18000ab60  add     rsp, 270h
0x18000ab67  pop     r15
0x18000ab69  pop     r14
0x18000ab6b  pop     rdi
0x18000ab6c  pop     rsi
0x18000ab6d  pop     rbp
0x18000ab6e  retn
0x18000ab70  mov     rcx, [rbp+198h]; this
0x18000ab77  mov     edx, 9DDh; void *
0x18000ab7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ab82  mov     rcx, [rbp+198h]; this
0x18000ab89  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000ab8f  mov     rcx, [rbp+198h]; this
0x18000ab96  mov     edx, 9E7h; void *
0x18000ab9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000aba1  mov     rcx, [rbp+198h]; this
0x18000aba8  mov     edx, 9DDh; void *
0x18000abad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000abb3  mov     rcx, [rbp+198h]; this
0x18000abba  mov     edx, 9E7h; void *
0x18000abbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000abc5  mov     rcx, [rbp+198h]; this
0x18000abcc  mov     edx, 9DDh; void *
0x18000abd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000abd7  mov     rcx, [rbp+198h]; this
0x18000abde  mov     edx, 9E7h; void *
0x18000abe3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
