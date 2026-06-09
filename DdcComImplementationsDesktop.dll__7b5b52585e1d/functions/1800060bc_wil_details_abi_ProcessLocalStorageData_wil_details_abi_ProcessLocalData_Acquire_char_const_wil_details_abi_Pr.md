# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800060bc`
- end: `0x18000645a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007820`

## callees

- `0x1800016b0`
- `0x180002134`
- `0x1800060bc`
- `0x180006830`
- `0x180006c94`
- `0x1800075b8`
- `0x1800081a8`
- `0x1800094d4`
- `0x180009fc8`
- `0x18000a31c`
- `0x18000aafc`
- `0x18000ab0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062cf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006134`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006134`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006155`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006155`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800062ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000636f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800061d6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800062ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000636f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800061e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800062c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006385`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x1800060bc  mov     [rsp-8+arg_10], rbx
0x1800060c1  push    rbp
0x1800060c2  push    rsi
0x1800060c3  push    rdi
0x1800060c4  push    r14
0x1800060c6  push    r15
0x1800060c8  lea     rbp, [rsp-160h]
0x1800060d0  sub     rsp, 260h
0x1800060d7  mov     rax, cs:__security_cookie
0x1800060de  xor     rax, rsp
0x1800060e1  mov     [rbp+180h+var_30], rax
0x1800060e8  mov     r15, rdx
0x1800060eb  mov     qword ptr [rdx], 0
0x1800060f2  mov     rbx, rcx
0x1800060f5  call    cs:__imp_GetCurrentProcessId
0x1800060fb  mov     r14d, 78h ; 'x'
0x180006101  mov     [rsp+280h+var_258], rbx
0x180006106  mov     r9d, eax
0x180006109  mov     [rsp+280h+var_260], r14d; int
0x18000610e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006115  mov     edx, 104h; unsigned __int64
0x18000611a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000611f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006124  mov     r9d, 1F0001h; dwDesiredAccess
0x18000612a  lea     rdx, [rsp+280h+Name]; lpName
0x18000612f  xor     r8d, r8d; dwFlags
0x180006132  xor     ecx, ecx; lpMutexAttributes
0x180006134  call    cs:__imp_CreateMutexExW
0x18000613a  mov     rbx, rax
0x18000613d  test    rax, rax
0x180006140  jnz     short loc_18000614C
0x180006142  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006147  jmp     loc_180006391
0x18000614c  xor     r8d, r8d; bAlertable
0x18000614f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006152  mov     rcx, rbx; hHandle
0x180006155  call    cs:__imp_WaitForSingleObjectEx
0x18000615b  cmp     eax, 102h
0x180006160  jz      short loc_180006172
0x180006162  test    eax, 0FFFFFF7Fh
0x180006167  jnz     loc_1800063C9
0x18000616d  mov     rdi, rbx
0x180006170  jmp     short loc_180006174
0x180006172  xor     edi, edi
0x180006174  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006179  mov     [rsp+280h+hObject], 0
0x180006182  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006187  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000618c  mov     esi, eax
0x18000618e  test    eax, eax
0x180006190  jns     short loc_1800061FC
0x180006192  mov     rcx, [rbp+188h]; this
0x180006199  mov     r9d, eax; char *
0x18000619c  mov     edx, 66h ; 'f'; void *
0x1800061a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061a6  mov     rcx, [rbp+188h]; this
0x1800061ad  mov     r9d, esi; char *
0x1800061b0  mov     edx, 6Fh ; 'o'; void *
0x1800061b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061ba  mov     rcx, [rbp+188h]; this
0x1800061c1  mov     r9d, esi; char *
0x1800061c4  mov     edx, 12Eh; void *
0x1800061c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061ce  test    rdi, rdi
0x1800061d1  jz      short loc_1800061E4
0x1800061d3  mov     rcx, rdi; hMutex
0x1800061d6  call    cs:__imp_ReleaseMutex
0x1800061dc  test    eax, eax
0x1800061de  jz      loc_1800063D6
0x1800061e4  mov     rcx, rbx; hObject
0x1800061e7  call    cs:__imp_CloseHandle
0x1800061ed  test    eax, eax
0x1800061ef  jz      loc_1800063E8
0x1800061f5  mov     eax, esi
0x1800061f7  jmp     loc_180006391
0x1800061fc  mov     rax, [rsp+280h+hObject]
0x180006201  lea     rcx, ds:0[rax*4]
0x180006209  test    rcx, rcx
0x18000620c  jz      short loc_18000621C
0x18000620e  mov     [r15], rcx
0x180006211  mov     eax, [rcx]
0x180006213  inc     eax
0x180006215  mov     [rcx], eax
0x180006217  jmp     loc_180006367
0x18000621c  mov     rdx, r14; dwBytes
0x18000621f  mov     qword ptr [r15], 0
0x180006226  mov     ecx, 8; dwFlags
0x18000622b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006230  mov     rsi, rax
0x180006233  test    rax, rax
0x180006236  jnz     short loc_180006257
0x180006238  mov     rcx, [rbp+188h]; this
0x18000623f  mov     r14d, 8007000Eh
0x180006245  mov     r9d, r14d; char *
0x180006248  mov     edx, 14Bh; void *
0x18000624d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006252  jmp     loc_1800062E3
0x180006257  xorps   xmm0, xmm0
0x18000625a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006260  test    sil, 3
0x180006264  jnz     loc_1800063FA
0x18000626a  mov     r9, rsi
0x18000626d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006272  shr     r9, 2; unsigned __int64
0x180006276  lea     rcx, [rsp+280h+hObject]; this
0x18000627b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006280  mov     r14d, eax
0x180006283  test    eax, eax
0x180006285  jns     loc_180006323
0x18000628b  mov     rcx, [rbp+188h]; this
0x180006292  mov     r9d, eax; char *
0x180006295  mov     edx, 14Eh; void *
0x18000629a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000629f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800062a4  test    rcx, rcx
0x1800062a7  jz      short loc_1800062B7
0x1800062a9  call    cs:__imp_CloseHandle
0x1800062af  test    eax, eax
0x1800062b1  jz      loc_180006400
0x1800062b7  mov     rcx, [rsp+280h+hObject]; hObject
0x1800062bc  test    rcx, rcx
0x1800062bf  jz      short loc_1800062CF
0x1800062c1  call    cs:__imp_CloseHandle
0x1800062c7  test    eax, eax
0x1800062c9  jz      loc_180006412
0x1800062cf  call    cs:__imp_GetProcessHeap
0x1800062d5  mov     r8, rsi; lpMem
0x1800062d8  xor     edx, edx; dwFlags
0x1800062da  mov     rcx, rax; hHeap
0x1800062dd  call    cs:__imp_HeapFree
0x1800062e3  mov     rcx, [rbp+188h]; this
0x1800062ea  mov     r9d, r14d; char *
0x1800062ed  mov     edx, 137h; void *
0x1800062f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062f7  test    rdi, rdi
0x1800062fa  jz      short loc_18000630D
0x1800062fc  mov     rcx, rdi; hMutex
0x1800062ff  call    cs:__imp_ReleaseMutex
0x180006305  test    eax, eax
0x180006307  jz      loc_180006424
0x18000630d  mov     rcx, rbx; hObject
0x180006310  call    cs:__imp_CloseHandle
0x180006316  test    eax, eax
0x180006318  jz      loc_180006436
0x18000631e  mov     eax, r14d
0x180006321  jmp     short loc_180006391
0x180006323  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006328  xor     edx, edx; Val
0x18000632a  mov     dword ptr [rsi], 1
0x180006330  lea     rcx, [rsi+22h]; void *
0x180006334  mov     [rsi+8], rbx
0x180006338  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000633d  lea     r8d, [rdx+56h]; Size
0x180006341  call    memset_0
0x180006346  xor     edx, edx; Val
0x180006348  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000634e  lea     rcx, [rsi+28h]; void *
0x180006352  mov     dword ptr [rsi+24h], 1
0x180006359  lea     r8d, [rdx+50h]; Size
0x18000635d  call    memset_0
0x180006362  xor     ebx, ebx
0x180006364  mov     [r15], rsi
0x180006367  test    rdi, rdi
0x18000636a  jz      short loc_18000637D
0x18000636c  mov     rcx, rdi; hMutex
0x18000636f  call    cs:__imp_ReleaseMutex
0x180006375  test    eax, eax
0x180006377  jz      loc_180006448
0x18000637d  test    rbx, rbx
0x180006380  jz      short loc_18000638F
0x180006382  mov     rcx, rbx; hObject
0x180006385  call    cs:__imp_CloseHandle
0x18000638b  test    eax, eax
0x18000638d  jz      short loc_1800063B7
0x18000638f  xor     eax, eax
0x180006391  mov     rcx, [rbp+180h+var_30]
0x180006398  xor     rcx, rsp; StackCookie
0x18000639b  call    __security_check_cookie
0x1800063a0  mov     rbx, [rsp+280h+arg_10]
0x1800063a8  add     rsp, 260h
0x1800063af  pop     r15
0x1800063b1  pop     r14
0x1800063b3  pop     rdi
0x1800063b4  pop     rsi
0x1800063b5  pop     rbp
0x1800063b6  retn
0x1800063b7  mov     rcx, [rbp+188h]; this
0x1800063be  mov     edx, 0A0Bh; void *
0x1800063c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063c9  mov     rcx, [rbp+188h]; this
0x1800063d0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800063d6  mov     rcx, [rbp+188h]; this
0x1800063dd  mov     edx, 0A15h; void *
0x1800063e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063e8  mov     rcx, [rbp+188h]; this
0x1800063ef  mov     edx, 0A0Bh; void *
0x1800063f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800063fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006400  mov     rcx, [rbp+188h]; this
0x180006407  mov     edx, 0A0Bh; void *
0x18000640c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006412  mov     rcx, [rbp+188h]; this
0x180006419  mov     edx, 0A0Bh; void *
0x18000641e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006424  mov     rcx, [rbp+188h]; this
0x18000642b  mov     edx, 0A15h; void *
0x180006430  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006436  mov     rcx, [rbp+188h]; this
0x18000643d  mov     edx, 0A0Bh; void *
0x180006442  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006448  mov     rcx, [rbp+188h]; this
0x18000644f  mov     edx, 0A15h; void *
0x180006454  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
