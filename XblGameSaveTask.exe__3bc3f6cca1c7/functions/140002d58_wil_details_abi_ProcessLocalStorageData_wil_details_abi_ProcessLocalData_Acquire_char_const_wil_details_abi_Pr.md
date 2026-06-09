# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140002d58`
- end: `0x1400030f6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140003bd0`

## callees

- `0x140001480`
- `0x140001f36`
- `0x140002d58`
- `0x1400030fc`
- `0x140003320`
- `0x140003968`
- `0x140004448`
- `0x140004724`
- `0x1400050b0`
- `0x14000516c`
- `0x14000553c`
- `0x14000554c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002df1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002df1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002dd0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002dd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000300b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002f9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000300b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002d91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002d91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002fac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003021`

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
0x140002d58  mov     [rsp-8+arg_10], rbx
0x140002d5d  push    rbp
0x140002d5e  push    rsi
0x140002d5f  push    rdi
0x140002d60  push    r14
0x140002d62  push    r15
0x140002d64  lea     rbp, [rsp-160h]
0x140002d6c  sub     rsp, 260h
0x140002d73  mov     rax, cs:__security_cookie
0x140002d7a  xor     rax, rsp
0x140002d7d  mov     [rbp+180h+var_30], rax
0x140002d84  mov     r15, rdx
0x140002d87  mov     qword ptr [rdx], 0
0x140002d8e  mov     rbx, rcx
0x140002d91  call    cs:__imp_GetCurrentProcessId
0x140002d97  mov     r14d, 78h ; 'x'
0x140002d9d  mov     [rsp+280h+var_258], rbx
0x140002da2  mov     r9d, eax
0x140002da5  mov     [rsp+280h+var_260], r14d; int
0x140002daa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002db1  mov     edx, 104h; unsigned __int64
0x140002db6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002dbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002dc0  mov     r9d, 1F0001h; dwDesiredAccess
0x140002dc6  lea     rdx, [rsp+280h+Name]; lpName
0x140002dcb  xor     r8d, r8d; dwFlags
0x140002dce  xor     ecx, ecx; lpMutexAttributes
0x140002dd0  call    cs:__imp_CreateMutexExW
0x140002dd6  mov     rbx, rax
0x140002dd9  test    rax, rax
0x140002ddc  jnz     short loc_140002DE8
0x140002dde  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002de3  jmp     loc_14000302D
0x140002de8  xor     r8d, r8d; bAlertable
0x140002deb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002dee  mov     rcx, rbx; hHandle
0x140002df1  call    cs:__imp_WaitForSingleObjectEx
0x140002df7  cmp     eax, 102h
0x140002dfc  jz      short loc_140002E0E
0x140002dfe  test    eax, 0FFFFFF7Fh
0x140002e03  jnz     loc_140003065
0x140002e09  mov     rdi, rbx
0x140002e0c  jmp     short loc_140002E10
0x140002e0e  xor     edi, edi
0x140002e10  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140002e15  mov     [rsp+280h+hObject], 0
0x140002e1e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002e23  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140002e28  mov     esi, eax
0x140002e2a  test    eax, eax
0x140002e2c  jns     short loc_140002E98
0x140002e2e  mov     rcx, [rbp+188h]; this
0x140002e35  mov     r9d, eax; char *
0x140002e38  mov     edx, 66h ; 'f'; void *
0x140002e3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e42  mov     rcx, [rbp+188h]; this
0x140002e49  mov     r9d, esi; char *
0x140002e4c  mov     edx, 6Fh ; 'o'; void *
0x140002e51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e56  mov     rcx, [rbp+188h]; this
0x140002e5d  mov     r9d, esi; char *
0x140002e60  mov     edx, 12Eh; void *
0x140002e65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e6a  test    rdi, rdi
0x140002e6d  jz      short loc_140002E80
0x140002e6f  mov     rcx, rdi; hMutex
0x140002e72  call    cs:__imp_ReleaseMutex
0x140002e78  test    eax, eax
0x140002e7a  jz      loc_140003072
0x140002e80  mov     rcx, rbx; hObject
0x140002e83  call    cs:__imp_CloseHandle
0x140002e89  test    eax, eax
0x140002e8b  jz      loc_140003084
0x140002e91  mov     eax, esi
0x140002e93  jmp     loc_14000302D
0x140002e98  mov     rax, [rsp+280h+hObject]
0x140002e9d  lea     rcx, ds:0[rax*4]
0x140002ea5  test    rcx, rcx
0x140002ea8  jz      short loc_140002EB8
0x140002eaa  mov     [r15], rcx
0x140002ead  mov     eax, [rcx]
0x140002eaf  inc     eax
0x140002eb1  mov     [rcx], eax
0x140002eb3  jmp     loc_140003003
0x140002eb8  mov     rdx, r14; dwBytes
0x140002ebb  mov     qword ptr [r15], 0
0x140002ec2  mov     ecx, 8; dwFlags
0x140002ec7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002ecc  mov     rsi, rax
0x140002ecf  test    rax, rax
0x140002ed2  jnz     short loc_140002EF3
0x140002ed4  mov     rcx, [rbp+188h]; this
0x140002edb  mov     r14d, 8007000Eh
0x140002ee1  mov     r9d, r14d; char *
0x140002ee4  mov     edx, 14Bh; void *
0x140002ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002eee  jmp     loc_140002F7F
0x140002ef3  xorps   xmm0, xmm0
0x140002ef6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140002efc  test    sil, 3
0x140002f00  jnz     loc_140003096
0x140002f06  mov     r9, rsi
0x140002f09  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140002f0e  shr     r9, 2; unsigned __int64
0x140002f12  lea     rcx, [rsp+280h+hObject]; this
0x140002f17  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140002f1c  mov     r14d, eax
0x140002f1f  test    eax, eax
0x140002f21  jns     loc_140002FBF
0x140002f27  mov     rcx, [rbp+188h]; this
0x140002f2e  mov     r9d, eax; char *
0x140002f31  mov     edx, 14Eh; void *
0x140002f36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f3b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140002f40  test    rcx, rcx
0x140002f43  jz      short loc_140002F53
0x140002f45  call    cs:__imp_CloseHandle
0x140002f4b  test    eax, eax
0x140002f4d  jz      loc_14000309C
0x140002f53  mov     rcx, [rsp+280h+hObject]; hObject
0x140002f58  test    rcx, rcx
0x140002f5b  jz      short loc_140002F6B
0x140002f5d  call    cs:__imp_CloseHandle
0x140002f63  test    eax, eax
0x140002f65  jz      loc_1400030AE
0x140002f6b  call    cs:__imp_GetProcessHeap
0x140002f71  mov     r8, rsi; lpMem
0x140002f74  xor     edx, edx; dwFlags
0x140002f76  mov     rcx, rax; hHeap
0x140002f79  call    cs:__imp_HeapFree
0x140002f7f  mov     rcx, [rbp+188h]; this
0x140002f86  mov     r9d, r14d; char *
0x140002f89  mov     edx, 137h; void *
0x140002f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f93  test    rdi, rdi
0x140002f96  jz      short loc_140002FA9
0x140002f98  mov     rcx, rdi; hMutex
0x140002f9b  call    cs:__imp_ReleaseMutex
0x140002fa1  test    eax, eax
0x140002fa3  jz      loc_1400030C0
0x140002fa9  mov     rcx, rbx; hObject
0x140002fac  call    cs:__imp_CloseHandle
0x140002fb2  test    eax, eax
0x140002fb4  jz      loc_1400030D2
0x140002fba  mov     eax, r14d
0x140002fbd  jmp     short loc_14000302D
0x140002fbf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140002fc4  xor     edx, edx; Val
0x140002fc6  mov     dword ptr [rsi], 1
0x140002fcc  lea     rcx, [rsi+22h]; void *
0x140002fd0  mov     [rsi+8], rbx
0x140002fd4  movdqu  xmmword ptr [rsi+10h], xmm0
0x140002fd9  lea     r8d, [rdx+56h]; Size
0x140002fdd  call    memset_0
0x140002fe2  xor     edx, edx; Val
0x140002fe4  mov     word ptr [rsi+20h], 58h ; 'X'
0x140002fea  lea     rcx, [rsi+28h]; void *
0x140002fee  mov     dword ptr [rsi+24h], 1
0x140002ff5  lea     r8d, [rdx+50h]; Size
0x140002ff9  call    memset_0
0x140002ffe  xor     ebx, ebx
0x140003000  mov     [r15], rsi
0x140003003  test    rdi, rdi
0x140003006  jz      short loc_140003019
0x140003008  mov     rcx, rdi; hMutex
0x14000300b  call    cs:__imp_ReleaseMutex
0x140003011  test    eax, eax
0x140003013  jz      loc_1400030E4
0x140003019  test    rbx, rbx
0x14000301c  jz      short loc_14000302B
0x14000301e  mov     rcx, rbx; hObject
0x140003021  call    cs:__imp_CloseHandle
0x140003027  test    eax, eax
0x140003029  jz      short loc_140003053
0x14000302b  xor     eax, eax
0x14000302d  mov     rcx, [rbp+180h+var_30]
0x140003034  xor     rcx, rsp; StackCookie
0x140003037  call    __security_check_cookie
0x14000303c  mov     rbx, [rsp+280h+arg_10]
0x140003044  add     rsp, 260h
0x14000304b  pop     r15
0x14000304d  pop     r14
0x14000304f  pop     rdi
0x140003050  pop     rsi
0x140003051  pop     rbp
0x140003052  retn
0x140003053  mov     rcx, [rbp+188h]; this
0x14000305a  mov     edx, 0A0Bh; void *
0x14000305f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003065  mov     rcx, [rbp+188h]; this
0x14000306c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003072  mov     rcx, [rbp+188h]; this
0x140003079  mov     edx, 0A15h; void *
0x14000307e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003084  mov     rcx, [rbp+188h]; this
0x14000308b  mov     edx, 0A0Bh; void *
0x140003090  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003096  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000309c  mov     rcx, [rbp+188h]; this
0x1400030a3  mov     edx, 0A0Bh; void *
0x1400030a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030ae  mov     rcx, [rbp+188h]; this
0x1400030b5  mov     edx, 0A0Bh; void *
0x1400030ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030c0  mov     rcx, [rbp+188h]; this
0x1400030c7  mov     edx, 0A15h; void *
0x1400030cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030d2  mov     rcx, [rbp+188h]; this
0x1400030d9  mov     edx, 0A0Bh; void *
0x1400030de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030e4  mov     rcx, [rbp+188h]; this
0x1400030eb  mov     edx, 0A15h; void *
0x1400030f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
