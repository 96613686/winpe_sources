# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180008c68`
- end: `0x180009030`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000a510`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180008c68`
- `0x180009430`
- `0x180009970`
- `0x18000a2a8`
- `0x18000b368`
- `0x18000cac4`
- `0x18000d62c`
- `0x18000dc68`
- `0x18000e53c`
- `0x18000e54c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008ce0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008ce0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008d97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ed5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008f45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008d97`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008ed5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008f45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008e9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008eac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008eac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ca1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ca1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ee6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f5b`

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
  bool v23; // r8
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
0x180008c68  mov     [rsp-8+arg_10], rbx
0x180008c6d  push    rbp
0x180008c6e  push    rsi
0x180008c6f  push    rdi
0x180008c70  push    r14
0x180008c72  push    r15
0x180008c74  lea     rbp, [rsp-160h]
0x180008c7c  sub     rsp, 260h
0x180008c83  mov     rax, cs:__security_cookie
0x180008c8a  xor     rax, rsp
0x180008c8d  mov     [rbp+180h+var_30], rax
0x180008c94  mov     r15, rdx
0x180008c97  mov     qword ptr [rdx], 0
0x180008c9e  mov     rbx, rcx
0x180008ca1  call    cs:__imp_GetCurrentProcessId
0x180008ca7  mov     r14d, 78h ; 'x'
0x180008cad  mov     [rsp+280h+var_258], rbx
0x180008cb2  mov     r9d, eax
0x180008cb5  mov     [rsp+280h+var_260], r14d; int
0x180008cba  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008cc1  mov     edx, 104h; unsigned __int64
0x180008cc6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008ccb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008cd0  mov     r9d, 1F0001h; dwDesiredAccess
0x180008cd6  lea     rdx, [rsp+280h+Name]; lpName
0x180008cdb  xor     r8d, r8d; dwFlags
0x180008cde  xor     ecx, ecx; lpMutexAttributes
0x180008ce0  call    cs:__imp_CreateMutexExW
0x180008ce6  mov     rbx, rax
0x180008ce9  test    rax, rax
0x180008cec  jnz     short loc_180008CF8
0x180008cee  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008cf3  jmp     loc_180008F67
0x180008cf8  xor     r8d, r8d; bAlertable
0x180008cfb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008cfe  mov     rcx, rbx; hHandle
0x180008d01  call    cs:__imp_WaitForSingleObjectEx
0x180008d07  cmp     eax, 102h
0x180008d0c  jz      short loc_180008D1E
0x180008d0e  test    eax, 0FFFFFF7Fh
0x180008d13  jnz     loc_180008F9F
0x180008d19  mov     rdi, rbx
0x180008d1c  jmp     short loc_180008D20
0x180008d1e  xor     edi, edi
0x180008d20  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008d25  mov     [rsp+280h+hObject], 0
0x180008d2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008d33  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008d38  mov     esi, eax
0x180008d3a  test    eax, eax
0x180008d3c  jns     short loc_180008DBD
0x180008d3e  mov     rcx, [rbp+188h]; this
0x180008d45  lea     r8, aWil; "wil"
0x180008d4c  mov     r9d, eax; char *
0x180008d4f  mov     edx, 66h ; 'f'; void *
0x180008d54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d59  mov     rcx, [rbp+188h]; this
0x180008d60  lea     r8, aWil; "wil"
0x180008d67  mov     r9d, esi; char *
0x180008d6a  mov     edx, 6Fh ; 'o'; void *
0x180008d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d74  mov     rcx, [rbp+188h]; this
0x180008d7b  lea     r8, aWil; "wil"
0x180008d82  mov     r9d, esi; char *
0x180008d85  mov     edx, 12Eh; void *
0x180008d8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d8f  test    rdi, rdi
0x180008d92  jz      short loc_180008DA5
0x180008d94  mov     rcx, rdi; hMutex
0x180008d97  call    cs:__imp_ReleaseMutex
0x180008d9d  test    eax, eax
0x180008d9f  jz      loc_180008FAC
0x180008da5  mov     rcx, rbx; hObject
0x180008da8  call    cs:__imp_CloseHandle
0x180008dae  test    eax, eax
0x180008db0  jz      loc_180008FBE
0x180008db6  mov     eax, esi
0x180008db8  jmp     loc_180008F67
0x180008dbd  mov     rax, [rsp+280h+hObject]
0x180008dc2  lea     rcx, ds:0[rax*4]
0x180008dca  test    rcx, rcx
0x180008dcd  jz      short loc_180008DDD
0x180008dcf  mov     [r15], rcx
0x180008dd2  mov     eax, [rcx]
0x180008dd4  inc     eax
0x180008dd6  mov     [rcx], eax
0x180008dd8  jmp     loc_180008F3D
0x180008ddd  mov     rdx, r14; dwBytes
0x180008de0  mov     qword ptr [r15], 0
0x180008de7  mov     ecx, 8; dwFlags
0x180008dec  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008df1  mov     rsi, rax
0x180008df4  test    rax, rax
0x180008df7  jnz     short loc_180008E1F
0x180008df9  mov     rcx, [rbp+188h]; this
0x180008e00  lea     r8, aWil; "wil"
0x180008e07  mov     r14d, 8007000Eh
0x180008e0d  mov     edx, 14Bh; void *
0x180008e12  mov     r9d, r14d; char *
0x180008e15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e1a  jmp     loc_180008EB2
0x180008e1f  xorps   xmm0, xmm0
0x180008e22  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008e28  test    sil, 3
0x180008e2c  jnz     loc_180008FD0
0x180008e32  mov     r9, rsi
0x180008e35  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008e3a  shr     r9, 2; unsigned __int64
0x180008e3e  lea     rcx, [rsp+280h+hObject]; this
0x180008e43  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008e48  mov     r14d, eax
0x180008e4b  test    eax, eax
0x180008e4d  jns     loc_180008EF9
0x180008e53  mov     rcx, [rbp+188h]; this
0x180008e5a  lea     r8, aWil; "wil"
0x180008e61  mov     r9d, eax; char *
0x180008e64  mov     edx, 14Eh; void *
0x180008e69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e6e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008e73  test    rcx, rcx
0x180008e76  jz      short loc_180008E86
0x180008e78  call    cs:__imp_CloseHandle
0x180008e7e  test    eax, eax
0x180008e80  jz      loc_180008FD6
0x180008e86  mov     rcx, [rsp+280h+hObject]; hObject
0x180008e8b  test    rcx, rcx
0x180008e8e  jz      short loc_180008E9E
0x180008e90  call    cs:__imp_CloseHandle
0x180008e96  test    eax, eax
0x180008e98  jz      loc_180008FE8
0x180008e9e  call    cs:__imp_GetProcessHeap
0x180008ea4  mov     r8, rsi; lpMem
0x180008ea7  xor     edx, edx; dwFlags
0x180008ea9  mov     rcx, rax; hHeap
0x180008eac  call    cs:__imp_HeapFree
0x180008eb2  mov     rcx, [rbp+188h]; this
0x180008eb9  lea     r8, aWil; "wil"
0x180008ec0  mov     r9d, r14d; char *
0x180008ec3  mov     edx, 137h; void *
0x180008ec8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ecd  test    rdi, rdi
0x180008ed0  jz      short loc_180008EE3
0x180008ed2  mov     rcx, rdi; hMutex
0x180008ed5  call    cs:__imp_ReleaseMutex
0x180008edb  test    eax, eax
0x180008edd  jz      loc_180008FFA
0x180008ee3  mov     rcx, rbx; hObject
0x180008ee6  call    cs:__imp_CloseHandle
0x180008eec  test    eax, eax
0x180008eee  jz      loc_18000900C
0x180008ef4  mov     eax, r14d
0x180008ef7  jmp     short loc_180008F67
0x180008ef9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008efe  xor     edx, edx; Val
0x180008f00  mov     dword ptr [rsi], 1
0x180008f06  lea     rcx, [rsi+22h]; void *
0x180008f0a  mov     [rsi+8], rbx
0x180008f0e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180008f13  lea     r8d, [rdx+56h]; Size
0x180008f17  call    memset_0
0x180008f1c  xor     edx, edx; Val
0x180008f1e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180008f24  lea     rcx, [rsi+28h]; void *
0x180008f28  mov     dword ptr [rsi+24h], 1
0x180008f2f  lea     r8d, [rdx+50h]; Size
0x180008f33  call    memset_0
0x180008f38  xor     ebx, ebx
0x180008f3a  mov     [r15], rsi
0x180008f3d  test    rdi, rdi
0x180008f40  jz      short loc_180008F53
0x180008f42  mov     rcx, rdi; hMutex
0x180008f45  call    cs:__imp_ReleaseMutex
0x180008f4b  test    eax, eax
0x180008f4d  jz      loc_18000901E
0x180008f53  test    rbx, rbx
0x180008f56  jz      short loc_180008F65
0x180008f58  mov     rcx, rbx; hObject
0x180008f5b  call    cs:__imp_CloseHandle
0x180008f61  test    eax, eax
0x180008f63  jz      short loc_180008F8D
0x180008f65  xor     eax, eax
0x180008f67  mov     rcx, [rbp+180h+var_30]
0x180008f6e  xor     rcx, rsp; StackCookie
0x180008f71  call    __security_check_cookie
0x180008f76  mov     rbx, [rsp+280h+arg_10]
0x180008f7e  add     rsp, 260h
0x180008f85  pop     r15
0x180008f87  pop     r14
0x180008f89  pop     rdi
0x180008f8a  pop     rsi
0x180008f8b  pop     rbp
0x180008f8c  retn
0x180008f8d  mov     rcx, [rbp+188h]; this
0x180008f94  mov     edx, 0A0Bh; void *
0x180008f99  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008f9f  mov     rcx, [rbp+188h]; this
0x180008fa6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180008fac  mov     rcx, [rbp+188h]; this
0x180008fb3  mov     edx, 0A15h; void *
0x180008fb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008fbe  mov     rcx, [rbp+188h]; this
0x180008fc5  mov     edx, 0A0Bh; void *
0x180008fca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008fd0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008fd6  mov     rcx, [rbp+188h]; this
0x180008fdd  mov     edx, 0A0Bh; void *
0x180008fe2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008fe8  mov     rcx, [rbp+188h]; this
0x180008fef  mov     edx, 0A0Bh; void *
0x180008ff4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ffa  mov     rcx, [rbp+188h]; this
0x180009001  mov     edx, 0A15h; void *
0x180009006  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000900c  mov     rcx, [rbp+188h]; this
0x180009013  mov     edx, 0A0Bh; void *
0x180009018  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000901e  mov     rcx, [rbp+188h]; this
0x180009025  mov     edx, 0A15h; void *
0x18000902a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
