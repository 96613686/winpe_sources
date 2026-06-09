# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003648`
- end: `0x180003a10`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004960`

## callees

- `0x180003648`
- `0x180003a54`
- `0x1800040cc`
- `0x180004658`
- `0x1800056bc`
- `0x180005e6c`
- `0x180006ed0`
- `0x180006f5c`
- `0x1800078e4`
- `0x1800078f4`
- `0x180007c62`
- `0x180007c90`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003870`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000393b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003788`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003870`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000393b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003681`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003681`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003777`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003925`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003777`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003925`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800036c0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800036c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800036e1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800036e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000387e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000387e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000388c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000388c`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
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
0x180003648  mov     [rsp-8+arg_10], rbx
0x18000364d  push    rbp
0x18000364e  push    rsi
0x18000364f  push    rdi
0x180003650  push    r14
0x180003652  push    r15
0x180003654  lea     rbp, [rsp-160h]
0x18000365c  sub     rsp, 260h
0x180003663  mov     rax, cs:__security_cookie
0x18000366a  xor     rax, rsp
0x18000366d  mov     [rbp+180h+var_30], rax
0x180003674  mov     r15, rdx
0x180003677  mov     qword ptr [rdx], 0
0x18000367e  mov     rbx, rcx
0x180003681  call    cs:__imp_GetCurrentProcessId
0x180003687  mov     r14d, 78h ; 'x'
0x18000368d  mov     [rsp+280h+var_258], rbx
0x180003692  mov     r9d, eax
0x180003695  mov     [rsp+280h+var_260], r14d; int
0x18000369a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800036a1  mov     edx, 104h; unsigned __int64
0x1800036a6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800036ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800036b0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800036b6  lea     rdx, [rsp+280h+Name]; lpName
0x1800036bb  xor     r8d, r8d; dwFlags
0x1800036be  xor     ecx, ecx; lpMutexAttributes
0x1800036c0  call    cs:__imp_CreateMutexExW
0x1800036c6  mov     rbx, rax
0x1800036c9  test    rax, rax
0x1800036cc  jnz     short loc_1800036D8
0x1800036ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800036d3  jmp     loc_180003947
0x1800036d8  xor     r8d, r8d; bAlertable
0x1800036db  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800036de  mov     rcx, rbx; hHandle
0x1800036e1  call    cs:__imp_WaitForSingleObjectEx
0x1800036e7  cmp     eax, 102h
0x1800036ec  jz      short loc_1800036FE
0x1800036ee  test    eax, 0FFFFFF7Fh
0x1800036f3  jnz     loc_18000397F
0x1800036f9  mov     rdi, rbx
0x1800036fc  jmp     short loc_180003700
0x1800036fe  xor     edi, edi
0x180003700  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003705  mov     [rsp+280h+hObject], 0
0x18000370e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003713  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003718  mov     esi, eax
0x18000371a  test    eax, eax
0x18000371c  jns     short loc_18000379D
0x18000371e  mov     rcx, [rbp+188h]; this
0x180003725  lea     r8, aWil; "wil"
0x18000372c  mov     r9d, eax; char *
0x18000372f  mov     edx, 66h ; 'f'; void *
0x180003734  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003739  mov     rcx, [rbp+188h]; this
0x180003740  lea     r8, aWil; "wil"
0x180003747  mov     r9d, esi; char *
0x18000374a  mov     edx, 6Fh ; 'o'; void *
0x18000374f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003754  mov     rcx, [rbp+188h]; this
0x18000375b  lea     r8, aWil; "wil"
0x180003762  mov     r9d, esi; char *
0x180003765  mov     edx, 12Eh; void *
0x18000376a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000376f  test    rdi, rdi
0x180003772  jz      short loc_180003785
0x180003774  mov     rcx, rdi; hMutex
0x180003777  call    cs:__imp_ReleaseMutex
0x18000377d  test    eax, eax
0x18000377f  jz      loc_18000398C
0x180003785  mov     rcx, rbx; hObject
0x180003788  call    cs:__imp_CloseHandle
0x18000378e  test    eax, eax
0x180003790  jz      loc_18000399E
0x180003796  mov     eax, esi
0x180003798  jmp     loc_180003947
0x18000379d  mov     rax, [rsp+280h+hObject]
0x1800037a2  lea     rcx, ds:0[rax*4]
0x1800037aa  test    rcx, rcx
0x1800037ad  jz      short loc_1800037BD
0x1800037af  mov     [r15], rcx
0x1800037b2  mov     eax, [rcx]
0x1800037b4  inc     eax
0x1800037b6  mov     [rcx], eax
0x1800037b8  jmp     loc_18000391D
0x1800037bd  mov     rdx, r14; dwBytes
0x1800037c0  mov     qword ptr [r15], 0
0x1800037c7  mov     ecx, 8; dwFlags
0x1800037cc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800037d1  mov     rsi, rax
0x1800037d4  test    rax, rax
0x1800037d7  jnz     short loc_1800037FF
0x1800037d9  mov     rcx, [rbp+188h]; this
0x1800037e0  lea     r8, aWil; "wil"
0x1800037e7  mov     r14d, 8007000Eh
0x1800037ed  mov     edx, 14Bh; void *
0x1800037f2  mov     r9d, r14d; char *
0x1800037f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037fa  jmp     loc_180003892
0x1800037ff  xorps   xmm0, xmm0
0x180003802  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003808  test    sil, 3
0x18000380c  jnz     loc_1800039B0
0x180003812  mov     r9, rsi
0x180003815  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000381a  shr     r9, 2; unsigned __int64
0x18000381e  lea     rcx, [rsp+280h+hObject]; this
0x180003823  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003828  mov     r14d, eax
0x18000382b  test    eax, eax
0x18000382d  jns     loc_1800038D9
0x180003833  mov     rcx, [rbp+188h]; this
0x18000383a  lea     r8, aWil; "wil"
0x180003841  mov     r9d, eax; char *
0x180003844  mov     edx, 14Eh; void *
0x180003849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000384e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003853  test    rcx, rcx
0x180003856  jz      short loc_180003866
0x180003858  call    cs:__imp_CloseHandle
0x18000385e  test    eax, eax
0x180003860  jz      loc_1800039B6
0x180003866  mov     rcx, [rsp+280h+hObject]; hObject
0x18000386b  test    rcx, rcx
0x18000386e  jz      short loc_18000387E
0x180003870  call    cs:__imp_CloseHandle
0x180003876  test    eax, eax
0x180003878  jz      loc_1800039C8
0x18000387e  call    cs:__imp_GetProcessHeap
0x180003884  mov     r8, rsi; lpMem
0x180003887  xor     edx, edx; dwFlags
0x180003889  mov     rcx, rax; hHeap
0x18000388c  call    cs:__imp_HeapFree
0x180003892  mov     rcx, [rbp+188h]; this
0x180003899  lea     r8, aWil; "wil"
0x1800038a0  mov     r9d, r14d; char *
0x1800038a3  mov     edx, 137h; void *
0x1800038a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038ad  test    rdi, rdi
0x1800038b0  jz      short loc_1800038C3
0x1800038b2  mov     rcx, rdi; hMutex
0x1800038b5  call    cs:__imp_ReleaseMutex
0x1800038bb  test    eax, eax
0x1800038bd  jz      loc_1800039DA
0x1800038c3  mov     rcx, rbx; hObject
0x1800038c6  call    cs:__imp_CloseHandle
0x1800038cc  test    eax, eax
0x1800038ce  jz      loc_1800039EC
0x1800038d4  mov     eax, r14d
0x1800038d7  jmp     short loc_180003947
0x1800038d9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800038de  xor     edx, edx; Val
0x1800038e0  mov     dword ptr [rsi], 1
0x1800038e6  lea     rcx, [rsi+22h]; void *
0x1800038ea  mov     [rsi+8], rbx
0x1800038ee  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800038f3  lea     r8d, [rdx+56h]; Size
0x1800038f7  call    memset_0
0x1800038fc  xor     edx, edx; Val
0x1800038fe  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003904  lea     rcx, [rsi+28h]; void *
0x180003908  mov     dword ptr [rsi+24h], 1
0x18000390f  lea     r8d, [rdx+50h]; Size
0x180003913  call    memset_0
0x180003918  xor     ebx, ebx
0x18000391a  mov     [r15], rsi
0x18000391d  test    rdi, rdi
0x180003920  jz      short loc_180003933
0x180003922  mov     rcx, rdi; hMutex
0x180003925  call    cs:__imp_ReleaseMutex
0x18000392b  test    eax, eax
0x18000392d  jz      loc_1800039FE
0x180003933  test    rbx, rbx
0x180003936  jz      short loc_180003945
0x180003938  mov     rcx, rbx; hObject
0x18000393b  call    cs:__imp_CloseHandle
0x180003941  test    eax, eax
0x180003943  jz      short loc_18000396D
0x180003945  xor     eax, eax
0x180003947  mov     rcx, [rbp+180h+var_30]
0x18000394e  xor     rcx, rsp; StackCookie
0x180003951  call    __security_check_cookie
0x180003956  mov     rbx, [rsp+280h+arg_10]
0x18000395e  add     rsp, 260h
0x180003965  pop     r15
0x180003967  pop     r14
0x180003969  pop     rdi
0x18000396a  pop     rsi
0x18000396b  pop     rbp
0x18000396c  retn
0x18000396d  mov     rcx, [rbp+188h]; this
0x180003974  mov     edx, 0A0Bh; void *
0x180003979  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000397f  mov     rcx, [rbp+188h]; this
0x180003986  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000398c  mov     rcx, [rbp+188h]; this
0x180003993  mov     edx, 0A15h; void *
0x180003998  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000399e  mov     rcx, [rbp+188h]; this
0x1800039a5  mov     edx, 0A0Bh; void *
0x1800039aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800039b6  mov     rcx, [rbp+188h]; this
0x1800039bd  mov     edx, 0A0Bh; void *
0x1800039c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039c8  mov     rcx, [rbp+188h]; this
0x1800039cf  mov     edx, 0A0Bh; void *
0x1800039d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039da  mov     rcx, [rbp+188h]; this
0x1800039e1  mov     edx, 0A15h; void *
0x1800039e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039ec  mov     rcx, [rbp+188h]; this
0x1800039f3  mov     edx, 0A0Bh; void *
0x1800039f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039fe  mov     rcx, [rbp+188h]; this
0x180003a05  mov     edx, 0A15h; void *
0x180003a0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
