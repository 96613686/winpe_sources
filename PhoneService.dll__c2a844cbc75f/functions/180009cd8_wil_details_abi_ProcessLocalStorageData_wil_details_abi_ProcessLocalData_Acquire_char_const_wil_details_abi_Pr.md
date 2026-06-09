# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009cd8`
- end: `0x18000a0a0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000ac4c`

## callees

- `0x180009cd8`
- `0x18000a0a8`
- `0x18000a394`
- `0x18000a9e8`
- `0x18000b514`
- `0x18000b760`
- `0x18000bbb4`
- `0x18000bc5c`
- `0x18000c02c`
- `0x18000c03c`
- `0x18008d95a`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009d71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009d71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009f45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009fb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009f45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009fb5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009d50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009d50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009d11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ee8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009fcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ee8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009f56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009fcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f1c`

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
0x180009cd8  mov     [rsp-8+arg_10], rbx
0x180009cdd  push    rbp
0x180009cde  push    rsi
0x180009cdf  push    rdi
0x180009ce0  push    r14
0x180009ce2  push    r15
0x180009ce4  lea     rbp, [rsp-160h]
0x180009cec  sub     rsp, 260h
0x180009cf3  mov     rax, cs:__security_cookie
0x180009cfa  xor     rax, rsp
0x180009cfd  mov     [rbp+180h+var_30], rax
0x180009d04  mov     r15, rdx
0x180009d07  mov     qword ptr [rdx], 0
0x180009d0e  mov     rbx, rcx
0x180009d11  call    cs:__imp_GetCurrentProcessId
0x180009d17  mov     r14d, 78h ; 'x'
0x180009d1d  mov     [rsp+280h+var_258], rbx
0x180009d22  mov     r9d, eax
0x180009d25  mov     [rsp+280h+var_260], r14d; int
0x180009d2a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009d31  mov     edx, 104h; unsigned __int64
0x180009d36  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009d3b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009d40  mov     r9d, 1F0001h; dwDesiredAccess
0x180009d46  lea     rdx, [rsp+280h+Name]; lpName
0x180009d4b  xor     r8d, r8d; dwFlags
0x180009d4e  xor     ecx, ecx; lpMutexAttributes
0x180009d50  call    cs:__imp_CreateMutexExW
0x180009d56  mov     rbx, rax
0x180009d59  test    rax, rax
0x180009d5c  jnz     short loc_180009D68
0x180009d5e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009d63  jmp     loc_180009FD7
0x180009d68  xor     r8d, r8d; bAlertable
0x180009d6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009d6e  mov     rcx, rbx; hHandle
0x180009d71  call    cs:__imp_WaitForSingleObjectEx
0x180009d77  cmp     eax, 102h
0x180009d7c  jz      short loc_180009D8E
0x180009d7e  test    eax, 0FFFFFF7Fh
0x180009d83  jnz     loc_18000A00F
0x180009d89  mov     rdi, rbx
0x180009d8c  jmp     short loc_180009D90
0x180009d8e  xor     edi, edi
0x180009d90  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180009d95  mov     [rsp+280h+hObject], 0
0x180009d9e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009da3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180009da8  mov     esi, eax
0x180009daa  test    eax, eax
0x180009dac  jns     short loc_180009E2D
0x180009dae  mov     rcx, [rbp+188h]; this
0x180009db5  lea     r8, aWil; "wil"
0x180009dbc  mov     r9d, eax; char *
0x180009dbf  mov     edx, 66h ; 'f'; void *
0x180009dc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dc9  mov     rcx, [rbp+188h]; this
0x180009dd0  lea     r8, aWil; "wil"
0x180009dd7  mov     r9d, esi; char *
0x180009dda  mov     edx, 6Fh ; 'o'; void *
0x180009ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009de4  mov     rcx, [rbp+188h]; this
0x180009deb  lea     r8, aWil; "wil"
0x180009df2  mov     r9d, esi; char *
0x180009df5  mov     edx, 12Eh; void *
0x180009dfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dff  test    rdi, rdi
0x180009e02  jz      short loc_180009E15
0x180009e04  mov     rcx, rdi; hMutex
0x180009e07  call    cs:__imp_ReleaseMutex
0x180009e0d  test    eax, eax
0x180009e0f  jz      loc_18000A01C
0x180009e15  mov     rcx, rbx; hObject
0x180009e18  call    cs:__imp_CloseHandle
0x180009e1e  test    eax, eax
0x180009e20  jz      loc_18000A02E
0x180009e26  mov     eax, esi
0x180009e28  jmp     loc_180009FD7
0x180009e2d  mov     rax, [rsp+280h+hObject]
0x180009e32  lea     rcx, ds:0[rax*4]
0x180009e3a  test    rcx, rcx
0x180009e3d  jz      short loc_180009E4D
0x180009e3f  mov     [r15], rcx
0x180009e42  mov     eax, [rcx]
0x180009e44  inc     eax
0x180009e46  mov     [rcx], eax
0x180009e48  jmp     loc_180009FAD
0x180009e4d  mov     rdx, r14; dwBytes
0x180009e50  mov     qword ptr [r15], 0
0x180009e57  mov     ecx, 8; dwFlags
0x180009e5c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009e61  mov     rsi, rax
0x180009e64  test    rax, rax
0x180009e67  jnz     short loc_180009E8F
0x180009e69  mov     rcx, [rbp+188h]; this
0x180009e70  lea     r8, aWil; "wil"
0x180009e77  mov     r14d, 8007000Eh
0x180009e7d  mov     edx, 14Bh; void *
0x180009e82  mov     r9d, r14d; char *
0x180009e85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e8a  jmp     loc_180009F22
0x180009e8f  xorps   xmm0, xmm0
0x180009e92  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180009e98  test    sil, 3
0x180009e9c  jnz     loc_18000A040
0x180009ea2  mov     r9, rsi
0x180009ea5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180009eaa  shr     r9, 2; unsigned __int64
0x180009eae  lea     rcx, [rsp+280h+hObject]; this
0x180009eb3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180009eb8  mov     r14d, eax
0x180009ebb  test    eax, eax
0x180009ebd  jns     loc_180009F69
0x180009ec3  mov     rcx, [rbp+188h]; this
0x180009eca  lea     r8, aWil; "wil"
0x180009ed1  mov     r9d, eax; char *
0x180009ed4  mov     edx, 14Eh; void *
0x180009ed9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ede  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009ee3  test    rcx, rcx
0x180009ee6  jz      short loc_180009EF6
0x180009ee8  call    cs:__imp_CloseHandle
0x180009eee  test    eax, eax
0x180009ef0  jz      loc_18000A046
0x180009ef6  mov     rcx, [rsp+280h+hObject]; hObject
0x180009efb  test    rcx, rcx
0x180009efe  jz      short loc_180009F0E
0x180009f00  call    cs:__imp_CloseHandle
0x180009f06  test    eax, eax
0x180009f08  jz      loc_18000A058
0x180009f0e  call    cs:__imp_GetProcessHeap
0x180009f14  mov     r8, rsi; lpMem
0x180009f17  xor     edx, edx; dwFlags
0x180009f19  mov     rcx, rax; hHeap
0x180009f1c  call    cs:__imp_HeapFree
0x180009f22  mov     rcx, [rbp+188h]; this
0x180009f29  lea     r8, aWil; "wil"
0x180009f30  mov     r9d, r14d; char *
0x180009f33  mov     edx, 137h; void *
0x180009f38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f3d  test    rdi, rdi
0x180009f40  jz      short loc_180009F53
0x180009f42  mov     rcx, rdi; hMutex
0x180009f45  call    cs:__imp_ReleaseMutex
0x180009f4b  test    eax, eax
0x180009f4d  jz      loc_18000A06A
0x180009f53  mov     rcx, rbx; hObject
0x180009f56  call    cs:__imp_CloseHandle
0x180009f5c  test    eax, eax
0x180009f5e  jz      loc_18000A07C
0x180009f64  mov     eax, r14d
0x180009f67  jmp     short loc_180009FD7
0x180009f69  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180009f6e  xor     edx, edx; Val
0x180009f70  mov     dword ptr [rsi], 1
0x180009f76  lea     rcx, [rsi+22h]; void *
0x180009f7a  mov     [rsi+8], rbx
0x180009f7e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180009f83  lea     r8d, [rdx+56h]; Size
0x180009f87  call    memset_0
0x180009f8c  xor     edx, edx; Val
0x180009f8e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180009f94  lea     rcx, [rsi+28h]; void *
0x180009f98  mov     dword ptr [rsi+24h], 1
0x180009f9f  lea     r8d, [rdx+50h]; Size
0x180009fa3  call    memset_0
0x180009fa8  xor     ebx, ebx
0x180009faa  mov     [r15], rsi
0x180009fad  test    rdi, rdi
0x180009fb0  jz      short loc_180009FC3
0x180009fb2  mov     rcx, rdi; hMutex
0x180009fb5  call    cs:__imp_ReleaseMutex
0x180009fbb  test    eax, eax
0x180009fbd  jz      loc_18000A08E
0x180009fc3  test    rbx, rbx
0x180009fc6  jz      short loc_180009FD5
0x180009fc8  mov     rcx, rbx; hObject
0x180009fcb  call    cs:__imp_CloseHandle
0x180009fd1  test    eax, eax
0x180009fd3  jz      short loc_180009FFD
0x180009fd5  xor     eax, eax
0x180009fd7  mov     rcx, [rbp+180h+var_30]
0x180009fde  xor     rcx, rsp; StackCookie
0x180009fe1  call    __security_check_cookie
0x180009fe6  mov     rbx, [rsp+280h+arg_10]
0x180009fee  add     rsp, 260h
0x180009ff5  pop     r15
0x180009ff7  pop     r14
0x180009ff9  pop     rdi
0x180009ffa  pop     rsi
0x180009ffb  pop     rbp
0x180009ffc  retn
0x180009ffd  mov     rcx, [rbp+188h]; this
0x18000a004  mov     edx, 0A0Bh; void *
0x18000a009  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a00f  mov     rcx, [rbp+188h]; this
0x18000a016  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000a01c  mov     rcx, [rbp+188h]; this
0x18000a023  mov     edx, 0A15h; void *
0x18000a028  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a02e  mov     rcx, [rbp+188h]; this
0x18000a035  mov     edx, 0A0Bh; void *
0x18000a03a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a040  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a046  mov     rcx, [rbp+188h]; this
0x18000a04d  mov     edx, 0A0Bh; void *
0x18000a052  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a058  mov     rcx, [rbp+188h]; this
0x18000a05f  mov     edx, 0A0Bh; void *
0x18000a064  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a06a  mov     rcx, [rbp+188h]; this
0x18000a071  mov     edx, 0A15h; void *
0x18000a076  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a07c  mov     rcx, [rbp+188h]; this
0x18000a083  mov     edx, 0A0Bh; void *
0x18000a088  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a08e  mov     rcx, [rbp+188h]; this
0x18000a095  mov     edx, 0A15h; void *
0x18000a09a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
