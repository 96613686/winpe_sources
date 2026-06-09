# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001c7b4`
- end: `0x18001cb5e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001ce60`

## callees

- `0x180001d40`
- `0x180002928`
- `0x180007930`
- `0x18000a074`
- `0x1800124b0`
- `0x180014214`
- `0x180014c4c`
- `0x1800165e8`
- `0x180016dd4`
- `0x1800175e8`
- `0x180017f00`
- `0x18001c7b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c9c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c9c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c9d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c9d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c8ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c9f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ca67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c8ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c9f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001ca67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c84d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001c84d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c82c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001c82c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c7ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c7ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c8df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ca08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ca7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c8df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c9b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ca08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ca7d`

## string_xrefs

- `0x18001cac8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  const char *v18; // r9
  unsigned int v19; // r8d
  const char *v20; // r9
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag3 *v23; // rcx
  unsigned int v24; // r8d
  _QWORD *v25; // rsi
  unsigned int v26; // r14d
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v45);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_28;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v25 = (_QWORD *)v22;
  if ( v22 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v22 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v24,
            v22 >> 2);
    v26 = v28;
    if ( v28 >= 0 )
    {
      v39 = *(_OWORD *)hObject;
      *(_DWORD *)v25 = 1;
      v25[1] = v6;
      *((_OWORD *)v25 + 1) = v39;
      memset_0((char *)v25 + 34, 0, 0x56u);
      *((_WORD *)v25 + 16) = 88;
      *((_DWORD *)v25 + 9) = 1;
      memset_0(v25 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v25;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v26, v46);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return v26;
}

```

## disassembly

```asm
0x18001c7b4  mov     [rsp-8+arg_10], rbx
0x18001c7b9  push    rbp
0x18001c7ba  push    rsi
0x18001c7bb  push    rdi
0x18001c7bc  push    r14
0x18001c7be  push    r15
0x18001c7c0  lea     rbp, [rsp-160h]
0x18001c7c8  sub     rsp, 260h
0x18001c7cf  mov     rax, cs:__security_cookie
0x18001c7d6  xor     rax, rsp
0x18001c7d9  mov     [rbp+180h+var_30], rax
0x18001c7e0  mov     r15, rdx
0x18001c7e3  mov     qword ptr [rdx], 0
0x18001c7ea  mov     rbx, rcx
0x18001c7ed  call    cs:__imp_GetCurrentProcessId
0x18001c7f3  mov     r14d, 78h ; 'x'
0x18001c7f9  mov     [rsp+280h+var_258], rbx
0x18001c7fe  mov     r9d, eax
0x18001c801  mov     [rsp+280h+var_260], r14d; int
0x18001c806  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001c80d  mov     edx, 104h; unsigned __int64
0x18001c812  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001c817  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c81c  mov     r9d, 1F0001h; dwDesiredAccess
0x18001c822  lea     rdx, [rsp+280h+Name]; lpName
0x18001c827  xor     r8d, r8d; dwFlags
0x18001c82a  xor     ecx, ecx; lpMutexAttributes
0x18001c82c  call    cs:__imp_CreateMutexExW
0x18001c832  mov     rbx, rax
0x18001c835  test    rax, rax
0x18001c838  jnz     short loc_18001C844
0x18001c83a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001c83f  jmp     loc_18001CA89
0x18001c844  xor     r8d, r8d; bAlertable
0x18001c847  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001c84a  mov     rcx, rbx; hHandle
0x18001c84d  call    cs:__imp_WaitForSingleObjectEx
0x18001c853  cmp     eax, 102h
0x18001c858  jz      short loc_18001C86A
0x18001c85a  test    eax, 0FFFFFF7Fh
0x18001c85f  jnz     loc_18001CAC1
0x18001c865  mov     rdi, rbx
0x18001c868  jmp     short loc_18001C86C
0x18001c86a  xor     edi, edi
0x18001c86c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18001c871  mov     [rsp+280h+hObject], 0
0x18001c87a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001c87f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001c884  mov     esi, eax
0x18001c886  test    eax, eax
0x18001c888  jns     short loc_18001C8F4
0x18001c88a  mov     rcx, [rbp+188h]; this
0x18001c891  mov     r9d, eax; char *
0x18001c894  mov     edx, 66h ; 'f'; void *
0x18001c899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c89e  mov     rcx, [rbp+188h]; this
0x18001c8a5  mov     r9d, esi; char *
0x18001c8a8  mov     edx, 6Fh ; 'o'; void *
0x18001c8ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8b2  mov     rcx, [rbp+188h]; this
0x18001c8b9  mov     r9d, esi; char *
0x18001c8bc  mov     edx, 12Eh; void *
0x18001c8c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c8c6  test    rdi, rdi
0x18001c8c9  jz      short loc_18001C8DC
0x18001c8cb  mov     rcx, rdi; hMutex
0x18001c8ce  call    cs:__imp_ReleaseMutex
0x18001c8d4  test    eax, eax
0x18001c8d6  jz      loc_18001CADA
0x18001c8dc  mov     rcx, rbx; hObject
0x18001c8df  call    cs:__imp_CloseHandle
0x18001c8e5  test    eax, eax
0x18001c8e7  jz      loc_18001CAEC
0x18001c8ed  mov     eax, esi
0x18001c8ef  jmp     loc_18001CA89
0x18001c8f4  mov     rax, [rsp+280h+hObject]
0x18001c8f9  lea     rcx, ds:0[rax*4]
0x18001c901  test    rcx, rcx
0x18001c904  jz      short loc_18001C914
0x18001c906  mov     [r15], rcx
0x18001c909  mov     eax, [rcx]
0x18001c90b  inc     eax
0x18001c90d  mov     [rcx], eax
0x18001c90f  jmp     loc_18001CA5F
0x18001c914  mov     rdx, r14; dwBytes
0x18001c917  mov     qword ptr [r15], 0
0x18001c91e  mov     ecx, 8; dwFlags
0x18001c923  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001c928  mov     rsi, rax
0x18001c92b  test    rax, rax
0x18001c92e  jnz     short loc_18001C94F
0x18001c930  mov     rcx, [rbp+188h]; this
0x18001c937  mov     r14d, 8007000Eh
0x18001c93d  mov     r9d, r14d; char *
0x18001c940  mov     edx, 14Bh; void *
0x18001c945  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c94a  jmp     loc_18001C9DB
0x18001c94f  xorps   xmm0, xmm0
0x18001c952  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18001c958  test    sil, 3
0x18001c95c  jnz     loc_18001CAFE
0x18001c962  mov     r9, rsi
0x18001c965  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18001c96a  shr     r9, 2; unsigned __int64
0x18001c96e  lea     rcx, [rsp+280h+hObject]; this
0x18001c973  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001c978  mov     r14d, eax
0x18001c97b  test    eax, eax
0x18001c97d  jns     loc_18001CA1B
0x18001c983  mov     rcx, [rbp+188h]; this
0x18001c98a  mov     r9d, eax; char *
0x18001c98d  mov     edx, 14Eh; void *
0x18001c992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c997  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18001c99c  test    rcx, rcx
0x18001c99f  jz      short loc_18001C9AF
0x18001c9a1  call    cs:__imp_CloseHandle
0x18001c9a7  test    eax, eax
0x18001c9a9  jz      loc_18001CB04
0x18001c9af  mov     rcx, [rsp+280h+hObject]; hObject
0x18001c9b4  test    rcx, rcx
0x18001c9b7  jz      short loc_18001C9C7
0x18001c9b9  call    cs:__imp_CloseHandle
0x18001c9bf  test    eax, eax
0x18001c9c1  jz      loc_18001CB16
0x18001c9c7  call    cs:__imp_GetProcessHeap
0x18001c9cd  mov     r8, rsi; lpMem
0x18001c9d0  xor     edx, edx; dwFlags
0x18001c9d2  mov     rcx, rax; hHeap
0x18001c9d5  call    cs:__imp_HeapFree
0x18001c9db  mov     rcx, [rbp+188h]; this
0x18001c9e2  mov     r9d, r14d; char *
0x18001c9e5  mov     edx, 137h; void *
0x18001c9ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c9ef  test    rdi, rdi
0x18001c9f2  jz      short loc_18001CA05
0x18001c9f4  mov     rcx, rdi; hMutex
0x18001c9f7  call    cs:__imp_ReleaseMutex
0x18001c9fd  test    eax, eax
0x18001c9ff  jz      loc_18001CB28
0x18001ca05  mov     rcx, rbx; hObject
0x18001ca08  call    cs:__imp_CloseHandle
0x18001ca0e  test    eax, eax
0x18001ca10  jz      loc_18001CB3A
0x18001ca16  mov     eax, r14d
0x18001ca19  jmp     short loc_18001CA89
0x18001ca1b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18001ca20  xor     edx, edx; Val
0x18001ca22  mov     dword ptr [rsi], 1
0x18001ca28  lea     rcx, [rsi+22h]; void *
0x18001ca2c  mov     [rsi+8], rbx
0x18001ca30  movdqu  xmmword ptr [rsi+10h], xmm0
0x18001ca35  lea     r8d, [rdx+56h]; Size
0x18001ca39  call    memset_0
0x18001ca3e  xor     edx, edx; Val
0x18001ca40  mov     word ptr [rsi+20h], 58h ; 'X'
0x18001ca46  lea     rcx, [rsi+28h]; void *
0x18001ca4a  mov     dword ptr [rsi+24h], 1
0x18001ca51  lea     r8d, [rdx+50h]; Size
0x18001ca55  call    memset_0
0x18001ca5a  xor     ebx, ebx
0x18001ca5c  mov     [r15], rsi
0x18001ca5f  test    rdi, rdi
0x18001ca62  jz      short loc_18001CA75
0x18001ca64  mov     rcx, rdi; hMutex
0x18001ca67  call    cs:__imp_ReleaseMutex
0x18001ca6d  test    eax, eax
0x18001ca6f  jz      loc_18001CB4C
0x18001ca75  test    rbx, rbx
0x18001ca78  jz      short loc_18001CA87
0x18001ca7a  mov     rcx, rbx; hObject
0x18001ca7d  call    cs:__imp_CloseHandle
0x18001ca83  test    eax, eax
0x18001ca85  jz      short loc_18001CAAF
0x18001ca87  xor     eax, eax
0x18001ca89  mov     rcx, [rbp+180h+var_30]
0x18001ca90  xor     rcx, rsp; StackCookie
0x18001ca93  call    __security_check_cookie
0x18001ca98  mov     rbx, [rsp+280h+arg_10]
0x18001caa0  add     rsp, 260h
0x18001caa7  pop     r15
0x18001caa9  pop     r14
0x18001caab  pop     rdi
0x18001caac  pop     rsi
0x18001caad  pop     rbp
0x18001caae  retn
0x18001caaf  mov     rcx, [rbp+188h]; this
0x18001cab6  mov     edx, 0A0Bh; void *
0x18001cabb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cac1  mov     rcx, [rbp+188h]; this
0x18001cac8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001cacf  mov     edx, 0E01h; void *
0x18001cad4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001cada  mov     rcx, [rbp+188h]; this
0x18001cae1  mov     edx, 0A15h; void *
0x18001cae6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001caec  mov     rcx, [rbp+188h]; this
0x18001caf3  mov     edx, 0A0Bh; void *
0x18001caf8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cafe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001cb04  mov     rcx, [rbp+188h]; this
0x18001cb0b  mov     edx, 0A0Bh; void *
0x18001cb10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cb16  mov     rcx, [rbp+188h]; this
0x18001cb1d  mov     edx, 0A0Bh; void *
0x18001cb22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cb28  mov     rcx, [rbp+188h]; this
0x18001cb2f  mov     edx, 0A15h; void *
0x18001cb34  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cb3a  mov     rcx, [rbp+188h]; this
0x18001cb41  mov     edx, 0A0Bh; void *
0x18001cb46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cb4c  mov     rcx, [rbp+188h]; this
0x18001cb53  mov     edx, 0A15h; void *
0x18001cb58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
