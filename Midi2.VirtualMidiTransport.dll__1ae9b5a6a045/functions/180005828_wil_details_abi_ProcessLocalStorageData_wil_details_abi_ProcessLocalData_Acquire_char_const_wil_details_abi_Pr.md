# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005828`
- end: `0x180005bf0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800076d0`

## callees

- `0x1800038f0`
- `0x1800046a0`
- `0x180005828`
- `0x180006790`
- `0x180006e7c`
- `0x180007468`
- `0x1800083fc`
- `0x180009784`
- `0x18000a1c4`
- `0x18000a27c`
- `0x18000a924`
- `0x18000a934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005957`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b05`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005957`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b05`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800058a0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800058a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800058c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800058c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005861`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005aa6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b1b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180005828  mov     [rsp-8+arg_10], rbx
0x18000582d  push    rbp
0x18000582e  push    rsi
0x18000582f  push    rdi
0x180005830  push    r14
0x180005832  push    r15
0x180005834  lea     rbp, [rsp-160h]
0x18000583c  sub     rsp, 260h
0x180005843  mov     rax, cs:__security_cookie
0x18000584a  xor     rax, rsp
0x18000584d  mov     [rbp+180h+var_30], rax
0x180005854  mov     r15, rdx
0x180005857  mov     qword ptr [rdx], 0
0x18000585e  mov     rbx, rcx
0x180005861  call    cs:__imp_GetCurrentProcessId
0x180005867  mov     r14d, 78h ; 'x'
0x18000586d  mov     [rsp+280h+var_258], rbx
0x180005872  mov     r9d, eax
0x180005875  mov     [rsp+280h+var_260], r14d; int
0x18000587a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005881  mov     edx, 104h; unsigned __int64
0x180005886  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000588b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005890  mov     r9d, 1F0001h; dwDesiredAccess
0x180005896  lea     rdx, [rsp+280h+Name]; lpName
0x18000589b  xor     r8d, r8d; dwFlags
0x18000589e  xor     ecx, ecx; lpMutexAttributes
0x1800058a0  call    cs:__imp_CreateMutexExW
0x1800058a6  mov     rbx, rax
0x1800058a9  test    rax, rax
0x1800058ac  jnz     short loc_1800058B8
0x1800058ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800058b3  jmp     loc_180005B27
0x1800058b8  xor     r8d, r8d; bAlertable
0x1800058bb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800058be  mov     rcx, rbx; hHandle
0x1800058c1  call    cs:__imp_WaitForSingleObjectEx
0x1800058c7  cmp     eax, 102h
0x1800058cc  jz      short loc_1800058DE
0x1800058ce  test    eax, 0FFFFFF7Fh
0x1800058d3  jnz     loc_180005B5F
0x1800058d9  mov     rdi, rbx
0x1800058dc  jmp     short loc_1800058E0
0x1800058de  xor     edi, edi
0x1800058e0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800058e5  mov     [rsp+280h+hObject], 0
0x1800058ee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800058f3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800058f8  mov     esi, eax
0x1800058fa  test    eax, eax
0x1800058fc  jns     short loc_18000597D
0x1800058fe  mov     rcx, [rbp+188h]; this
0x180005905  lea     r8, aWil; "wil"
0x18000590c  mov     r9d, eax; char *
0x18000590f  mov     edx, 66h ; 'f'; void *
0x180005914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005919  mov     rcx, [rbp+188h]; this
0x180005920  lea     r8, aWil; "wil"
0x180005927  mov     r9d, esi; char *
0x18000592a  mov     edx, 6Fh ; 'o'; void *
0x18000592f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005934  mov     rcx, [rbp+188h]; this
0x18000593b  lea     r8, aWil; "wil"
0x180005942  mov     r9d, esi; char *
0x180005945  mov     edx, 12Eh; void *
0x18000594a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000594f  test    rdi, rdi
0x180005952  jz      short loc_180005965
0x180005954  mov     rcx, rdi; hMutex
0x180005957  call    cs:__imp_ReleaseMutex
0x18000595d  test    eax, eax
0x18000595f  jz      loc_180005B6C
0x180005965  mov     rcx, rbx; hObject
0x180005968  call    cs:__imp_CloseHandle
0x18000596e  test    eax, eax
0x180005970  jz      loc_180005B7E
0x180005976  mov     eax, esi
0x180005978  jmp     loc_180005B27
0x18000597d  mov     rax, [rsp+280h+hObject]
0x180005982  lea     rcx, ds:0[rax*4]
0x18000598a  test    rcx, rcx
0x18000598d  jz      short loc_18000599D
0x18000598f  mov     [r15], rcx
0x180005992  mov     eax, [rcx]
0x180005994  inc     eax
0x180005996  mov     [rcx], eax
0x180005998  jmp     loc_180005AFD
0x18000599d  mov     rdx, r14; dwBytes
0x1800059a0  mov     qword ptr [r15], 0
0x1800059a7  mov     ecx, 8; dwFlags
0x1800059ac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800059b1  mov     rsi, rax
0x1800059b4  test    rax, rax
0x1800059b7  jnz     short loc_1800059DF
0x1800059b9  mov     rcx, [rbp+188h]; this
0x1800059c0  lea     r8, aWil; "wil"
0x1800059c7  mov     r14d, 8007000Eh
0x1800059cd  mov     edx, 14Bh; void *
0x1800059d2  mov     r9d, r14d; char *
0x1800059d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800059da  jmp     loc_180005A72
0x1800059df  xorps   xmm0, xmm0
0x1800059e2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800059e8  test    sil, 3
0x1800059ec  jnz     loc_180005B90
0x1800059f2  mov     r9, rsi
0x1800059f5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800059fa  shr     r9, 2; unsigned __int64
0x1800059fe  lea     rcx, [rsp+280h+hObject]; this
0x180005a03  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005a08  mov     r14d, eax
0x180005a0b  test    eax, eax
0x180005a0d  jns     loc_180005AB9
0x180005a13  mov     rcx, [rbp+188h]; this
0x180005a1a  lea     r8, aWil; "wil"
0x180005a21  mov     r9d, eax; char *
0x180005a24  mov     edx, 14Eh; void *
0x180005a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a2e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005a33  test    rcx, rcx
0x180005a36  jz      short loc_180005A46
0x180005a38  call    cs:__imp_CloseHandle
0x180005a3e  test    eax, eax
0x180005a40  jz      loc_180005B96
0x180005a46  mov     rcx, [rsp+280h+hObject]; hObject
0x180005a4b  test    rcx, rcx
0x180005a4e  jz      short loc_180005A5E
0x180005a50  call    cs:__imp_CloseHandle
0x180005a56  test    eax, eax
0x180005a58  jz      loc_180005BA8
0x180005a5e  call    cs:__imp_GetProcessHeap
0x180005a64  mov     r8, rsi; lpMem
0x180005a67  xor     edx, edx; dwFlags
0x180005a69  mov     rcx, rax; hHeap
0x180005a6c  call    cs:__imp_HeapFree
0x180005a72  mov     rcx, [rbp+188h]; this
0x180005a79  lea     r8, aWil; "wil"
0x180005a80  mov     r9d, r14d; char *
0x180005a83  mov     edx, 137h; void *
0x180005a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a8d  test    rdi, rdi
0x180005a90  jz      short loc_180005AA3
0x180005a92  mov     rcx, rdi; hMutex
0x180005a95  call    cs:__imp_ReleaseMutex
0x180005a9b  test    eax, eax
0x180005a9d  jz      loc_180005BBA
0x180005aa3  mov     rcx, rbx; hObject
0x180005aa6  call    cs:__imp_CloseHandle
0x180005aac  test    eax, eax
0x180005aae  jz      loc_180005BCC
0x180005ab4  mov     eax, r14d
0x180005ab7  jmp     short loc_180005B27
0x180005ab9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005abe  xor     edx, edx; Val
0x180005ac0  mov     dword ptr [rsi], 1
0x180005ac6  lea     rcx, [rsi+22h]; void *
0x180005aca  mov     [rsi+8], rbx
0x180005ace  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005ad3  lea     r8d, [rdx+56h]; Size
0x180005ad7  call    memset_0
0x180005adc  xor     edx, edx; Val
0x180005ade  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005ae4  lea     rcx, [rsi+28h]; void *
0x180005ae8  mov     dword ptr [rsi+24h], 1
0x180005aef  lea     r8d, [rdx+50h]; Size
0x180005af3  call    memset_0
0x180005af8  xor     ebx, ebx
0x180005afa  mov     [r15], rsi
0x180005afd  test    rdi, rdi
0x180005b00  jz      short loc_180005B13
0x180005b02  mov     rcx, rdi; hMutex
0x180005b05  call    cs:__imp_ReleaseMutex
0x180005b0b  test    eax, eax
0x180005b0d  jz      loc_180005BDE
0x180005b13  test    rbx, rbx
0x180005b16  jz      short loc_180005B25
0x180005b18  mov     rcx, rbx; hObject
0x180005b1b  call    cs:__imp_CloseHandle
0x180005b21  test    eax, eax
0x180005b23  jz      short loc_180005B4D
0x180005b25  xor     eax, eax
0x180005b27  mov     rcx, [rbp+180h+var_30]
0x180005b2e  xor     rcx, rsp; StackCookie
0x180005b31  call    __security_check_cookie
0x180005b36  mov     rbx, [rsp+280h+arg_10]
0x180005b3e  add     rsp, 260h
0x180005b45  pop     r15
0x180005b47  pop     r14
0x180005b49  pop     rdi
0x180005b4a  pop     rsi
0x180005b4b  pop     rbp
0x180005b4c  retn
0x180005b4d  mov     rcx, [rbp+188h]; this
0x180005b54  mov     edx, 0A0Bh; void *
0x180005b59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005b5f  mov     rcx, [rbp+188h]; this
0x180005b66  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005b6c  mov     rcx, [rbp+188h]; this
0x180005b73  mov     edx, 0A15h; void *
0x180005b78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005b7e  mov     rcx, [rbp+188h]; this
0x180005b85  mov     edx, 0A0Bh; void *
0x180005b8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005b90  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005b96  mov     rcx, [rbp+188h]; this
0x180005b9d  mov     edx, 0A0Bh; void *
0x180005ba2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ba8  mov     rcx, [rbp+188h]; this
0x180005baf  mov     edx, 0A0Bh; void *
0x180005bb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005bba  mov     rcx, [rbp+188h]; this
0x180005bc1  mov     edx, 0A15h; void *
0x180005bc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005bcc  mov     rcx, [rbp+188h]; this
0x180005bd3  mov     edx, 0A0Bh; void *
0x180005bd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005bde  mov     rcx, [rbp+188h]; this
0x180005be5  mov     edx, 0A15h; void *
0x180005bea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
