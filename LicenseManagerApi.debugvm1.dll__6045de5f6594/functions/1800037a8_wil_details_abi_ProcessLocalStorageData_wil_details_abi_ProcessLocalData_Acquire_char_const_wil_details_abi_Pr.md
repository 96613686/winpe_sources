# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800037a8`
- end: `0x180003b07`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `863`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800045f4`

## callees

- `0x180001960`
- `0x1800022ea`
- `0x1800037a8`
- `0x180003b10`
- `0x180003d40`
- `0x18000438c`
- `0x180004e58`
- `0x1800052a8`
- `0x180005c54`
- `0x180005d2c`
- `0x1800060bc`
- `0x1800060cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003a5b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003820`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003820`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003841`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003841`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800037e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800037e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003995`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003995`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a71`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  DWORD v9; // eax
  unsigned int v10; // edx
  wil::details::in1diag3 *v11; // rcx
  const char *v12; // r8
  bool *v13; // r9
  void *v14; // rdi
  int ValueInternal; // eax
  unsigned __int64 v16; // r8
  int v17; // r9d
  unsigned int v18; // esi
  int v19; // r9d
  int v20; // r9d
  unsigned int v21; // edx
  const char *v22; // r8
  unsigned int v23; // edx
  const char *v24; // r8
  _DWORD *v25; // rcx
  unsigned __int64 v26; // rax
  wil::details::in1diag3 *v27; // rcx
  __int64 v28; // r8
  int v29; // r9d
  _QWORD *v30; // rsi
  unsigned int v31; // r14d
  int v32; // r9d
  int v33; // eax
  int v34; // r9d
  unsigned int v35; // edx
  const char *v36; // r8
  unsigned int v37; // edx
  const char *v38; // r8
  HANDLE ProcessHeap; // rax
  unsigned int v40; // edx
  const char *v41; // r8
  unsigned int v42; // edx
  const char *v43; // r8
  __int128 v44; // xmm0
  unsigned int v45; // edx
  const char *v46; // r8
  unsigned int v47; // edx
  const char *v48; // r8
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v14 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(v11, v10, v12);
    v14 = v7;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, (unsigned __int64 *)hObject, v13);
  v18 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x66,
      (unsigned int)"wil",
      (wil::details *)(unsigned int)ValueInternal,
      v17);
    wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0x6F, (unsigned int)"wil", (wil::details *)v18, v19);
    wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0x12E, (unsigned int)"wil", (wil::details *)v18, v20);
    if ( v14 && !ReleaseMutex(v14) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA15, v21, v22);
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v23, v24);
    return v18;
  }
  v25 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v25;
    ++*v25;
    goto LABEL_28;
  }
  *a2 = 0;
  v26 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v16);
  v30 = (_QWORD *)v26;
  if ( v26 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v26 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v27);
    v33 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v28,
            v26 >> 2);
    v31 = v33;
    if ( v33 >= 0 )
    {
      v44 = *(_OWORD *)hObject;
      *(_DWORD *)v30 = 1;
      v30[1] = v7;
      *((_OWORD *)v30 + 1) = v44;
      memset_0((char *)v30 + 34, 0, 0x56u);
      *((_WORD *)v30 + 16) = 88;
      *((_DWORD *)v30 + 9) = 1;
      memset_0(v30 + 5, 0, 0x50u);
      v7 = 0;
      *a2 = v30;
LABEL_28:
      if ( v14 && !ReleaseMutex(v14) )
        wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA15, v45, v46);
      if ( v7 && !CloseHandle(v7) )
        wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v47, v48);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x14E,
      (unsigned int)"wil",
      (wil::details *)(unsigned int)v33,
      v34);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v35, v36);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v37, v38);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v30);
  }
  else
  {
    v31 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0x14B,
      (unsigned int)"wil",
      (wil::details *)0x8007000ELL,
      v29);
  }
  wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0x137, (unsigned int)"wil", (wil::details *)v31, v32);
  if ( v14 && !ReleaseMutex(v14) )
    wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA15, v40, v41);
  if ( !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v42, v43);
  return v31;
}

```

## disassembly

```asm
0x1800037a8  mov     [rsp-8+arg_10], rbx
0x1800037ad  push    rbp
0x1800037ae  push    rsi
0x1800037af  push    rdi
0x1800037b0  push    r14
0x1800037b2  push    r15
0x1800037b4  lea     rbp, [rsp-160h]
0x1800037bc  sub     rsp, 260h
0x1800037c3  mov     rax, cs:__security_cookie
0x1800037ca  xor     rax, rsp
0x1800037cd  mov     [rbp+180h+var_30], rax
0x1800037d4  mov     r15, rdx
0x1800037d7  mov     qword ptr [rdx], 0
0x1800037de  mov     rbx, rcx
0x1800037e1  call    cs:__imp_GetCurrentProcessId
0x1800037e7  mov     r14d, 78h ; 'x'
0x1800037ed  mov     [rsp+280h+var_258], rbx
0x1800037f2  mov     r9d, eax
0x1800037f5  mov     [rsp+280h+var_260], r14d
0x1800037fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003801  mov     edx, 104h; unsigned __int64
0x180003806  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000380b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003810  mov     r9d, 1F0001h; dwDesiredAccess
0x180003816  lea     rdx, [rsp+280h+Name]; lpName
0x18000381b  xor     r8d, r8d; dwFlags
0x18000381e  xor     ecx, ecx; lpMutexAttributes
0x180003820  call    cs:__imp_CreateMutexExW
0x180003826  mov     rbx, rax
0x180003829  test    rax, rax
0x18000382c  jnz     short loc_180003838
0x18000382e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003833  jmp     loc_180003A7D
0x180003838  xor     r8d, r8d; bAlertable
0x18000383b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000383e  mov     rcx, rbx; hHandle
0x180003841  call    cs:__imp_WaitForSingleObjectEx
0x180003847  cmp     eax, 102h
0x18000384c  jz      short loc_18000385E
0x18000384e  test    eax, 0FFFFFF7Fh
0x180003853  jnz     loc_180003AAE
0x180003859  mov     rdi, rbx
0x18000385c  jmp     short loc_180003860
0x18000385e  xor     edi, edi
0x180003860  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003865  mov     [rsp+280h+hObject], 0
0x18000386e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003873  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003878  mov     esi, eax
0x18000387a  test    eax, eax
0x18000387c  jns     short loc_1800038E8
0x18000387e  mov     r8d, eax; wil::details *
0x180003881  lea     rdx, aWil; "wil"
0x180003888  mov     ecx, 66h ; 'f'; this
0x18000388d  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180003892  mov     r8d, esi; wil::details *
0x180003895  lea     rdx, aWil; "wil"
0x18000389c  mov     ecx, 6Fh ; 'o'; this
0x1800038a1  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x1800038a6  mov     r8d, esi; wil::details *
0x1800038a9  lea     rdx, aWil; "wil"
0x1800038b0  mov     ecx, 12Eh; this
0x1800038b5  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x1800038ba  test    rdi, rdi
0x1800038bd  jz      short loc_1800038D0
0x1800038bf  mov     rcx, rdi; hMutex
0x1800038c2  call    cs:__imp_ReleaseMutex
0x1800038c8  test    eax, eax
0x1800038ca  jz      loc_180003AB4
0x1800038d0  mov     rcx, rbx; hObject
0x1800038d3  call    cs:__imp_CloseHandle
0x1800038d9  test    eax, eax
0x1800038db  jz      loc_180003ABF
0x1800038e1  mov     eax, esi
0x1800038e3  jmp     loc_180003A7D
0x1800038e8  mov     rax, [rsp+280h+hObject]
0x1800038ed  lea     rcx, ds:0[rax*4]
0x1800038f5  test    rcx, rcx
0x1800038f8  jz      short loc_180003908
0x1800038fa  mov     [r15], rcx
0x1800038fd  mov     eax, [rcx]
0x1800038ff  inc     eax
0x180003901  mov     [rcx], eax
0x180003903  jmp     loc_180003A53
0x180003908  mov     rdx, r14; dwBytes
0x18000390b  mov     qword ptr [r15], 0
0x180003912  mov     ecx, 8; dwFlags
0x180003917  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000391c  mov     rsi, rax
0x18000391f  test    rax, rax
0x180003922  jnz     short loc_180003943
0x180003924  mov     r14d, 8007000Eh
0x18000392a  lea     rdx, aWil; "wil"
0x180003931  mov     r8d, r14d; wil::details *
0x180003934  mov     ecx, 14Bh; this
0x180003939  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000393e  jmp     loc_1800039CF
0x180003943  xorps   xmm0, xmm0
0x180003946  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000394c  test    sil, 3
0x180003950  jnz     loc_180003ACA
0x180003956  mov     r9, rsi
0x180003959  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000395e  shr     r9, 2; unsigned __int64
0x180003962  lea     rcx, [rsp+280h+hObject]; this
0x180003967  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000396c  mov     r14d, eax
0x18000396f  test    eax, eax
0x180003971  jns     loc_180003A0F
0x180003977  mov     r8d, eax; wil::details *
0x18000397a  lea     rdx, aWil; "wil"
0x180003981  mov     ecx, 14Eh; this
0x180003986  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x18000398b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003990  test    rcx, rcx
0x180003993  jz      short loc_1800039A3
0x180003995  call    cs:__imp_CloseHandle
0x18000399b  test    eax, eax
0x18000399d  jz      loc_180003AD0
0x1800039a3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800039a8  test    rcx, rcx
0x1800039ab  jz      short loc_1800039BB
0x1800039ad  call    cs:__imp_CloseHandle
0x1800039b3  test    eax, eax
0x1800039b5  jz      loc_180003ADB
0x1800039bb  call    cs:__imp_GetProcessHeap
0x1800039c1  mov     r8, rsi; lpMem
0x1800039c4  xor     edx, edx; dwFlags
0x1800039c6  mov     rcx, rax; hHeap
0x1800039c9  call    cs:__imp_HeapFree
0x1800039cf  mov     r8d, r14d; wil::details *
0x1800039d2  lea     rdx, aWil; "wil"
0x1800039d9  mov     ecx, 137h; this
0x1800039de  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x1800039e3  test    rdi, rdi
0x1800039e6  jz      short loc_1800039F9
0x1800039e8  mov     rcx, rdi; hMutex
0x1800039eb  call    cs:__imp_ReleaseMutex
0x1800039f1  test    eax, eax
0x1800039f3  jz      loc_180003AE6
0x1800039f9  mov     rcx, rbx; hObject
0x1800039fc  call    cs:__imp_CloseHandle
0x180003a02  test    eax, eax
0x180003a04  jz      loc_180003AF1
0x180003a0a  mov     eax, r14d
0x180003a0d  jmp     short loc_180003A7D
0x180003a0f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003a14  xor     edx, edx; Val
0x180003a16  mov     dword ptr [rsi], 1
0x180003a1c  lea     rcx, [rsi+22h]; void *
0x180003a20  mov     [rsi+8], rbx
0x180003a24  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003a29  lea     r8d, [rdx+56h]; Size
0x180003a2d  call    memset_0
0x180003a32  xor     edx, edx; Val
0x180003a34  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003a3a  lea     rcx, [rsi+28h]; void *
0x180003a3e  mov     dword ptr [rsi+24h], 1
0x180003a45  lea     r8d, [rdx+50h]; Size
0x180003a49  call    memset_0
0x180003a4e  xor     ebx, ebx
0x180003a50  mov     [r15], rsi
0x180003a53  test    rdi, rdi
0x180003a56  jz      short loc_180003A69
0x180003a58  mov     rcx, rdi; hMutex
0x180003a5b  call    cs:__imp_ReleaseMutex
0x180003a61  test    eax, eax
0x180003a63  jz      loc_180003AFC
0x180003a69  test    rbx, rbx
0x180003a6c  jz      short loc_180003A7B
0x180003a6e  mov     rcx, rbx; hObject
0x180003a71  call    cs:__imp_CloseHandle
0x180003a77  test    eax, eax
0x180003a79  jz      short loc_180003AA3
0x180003a7b  xor     eax, eax
0x180003a7d  mov     rcx, [rbp+180h+var_30]
0x180003a84  xor     rcx, rsp; StackCookie
0x180003a87  call    __security_check_cookie
0x180003a8c  mov     rbx, [rsp+280h+arg_10]
0x180003a94  add     rsp, 260h
0x180003a9b  pop     r15
0x180003a9d  pop     r14
0x180003a9f  pop     rdi
0x180003aa0  pop     rsi
0x180003aa1  pop     rbp
0x180003aa2  retn
0x180003aa3  mov     ecx, 0A0Bh; this
0x180003aa8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003aae  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(uint,char const *)
0x180003ab4  mov     ecx, 0A15h; this
0x180003ab9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003abf  mov     ecx, 0A0Bh; this
0x180003ac4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003aca  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003ad0  mov     ecx, 0A0Bh; this
0x180003ad5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003adb  mov     ecx, 0A0Bh; this
0x180003ae0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003ae6  mov     ecx, 0A15h; this
0x180003aeb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003af1  mov     ecx, 0A0Bh; this
0x180003af6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180003afc  mov     ecx, 0A15h; this
0x180003b01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
```
