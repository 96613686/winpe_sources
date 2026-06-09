# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140002d18`
- end: `0x1400030e0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140003c90`

## callees

- `0x140001530`
- `0x140001f50`
- `0x140002d18`
- `0x1400030e8`
- `0x1400033d4`
- `0x140003a28`
- `0x140004508`
- `0x140004764`
- `0x140005154`
- `0x14000521c`
- `0x1400055dc`
- `0x1400055ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002d90`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140002d90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002db1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140002db1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002e47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002ff5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002e47`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002f85`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140002ff5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002d51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002d51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000300b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002e58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000300b`

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
0x140002d18  mov     [rsp-8+arg_10], rbx
0x140002d1d  push    rbp
0x140002d1e  push    rsi
0x140002d1f  push    rdi
0x140002d20  push    r14
0x140002d22  push    r15
0x140002d24  lea     rbp, [rsp-160h]
0x140002d2c  sub     rsp, 260h
0x140002d33  mov     rax, cs:__security_cookie
0x140002d3a  xor     rax, rsp
0x140002d3d  mov     [rbp+180h+var_30], rax
0x140002d44  mov     r15, rdx
0x140002d47  mov     qword ptr [rdx], 0
0x140002d4e  mov     rbx, rcx
0x140002d51  call    cs:__imp_GetCurrentProcessId
0x140002d57  mov     r14d, 78h ; 'x'
0x140002d5d  mov     [rsp+280h+var_258], rbx
0x140002d62  mov     r9d, eax
0x140002d65  mov     [rsp+280h+var_260], r14d; int
0x140002d6a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002d71  mov     edx, 104h; unsigned __int64
0x140002d76  lea     rcx, [rsp+280h+Name]; Buffer
0x140002d7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002d80  mov     r9d, 1F0001h; dwDesiredAccess
0x140002d86  lea     rdx, [rsp+280h+Name]; lpName
0x140002d8b  xor     r8d, r8d; dwFlags
0x140002d8e  xor     ecx, ecx; lpMutexAttributes
0x140002d90  call    cs:__imp_CreateMutexExW
0x140002d96  mov     rbx, rax
0x140002d99  test    rax, rax
0x140002d9c  jnz     short loc_140002DA8
0x140002d9e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002da3  jmp     loc_140003017
0x140002da8  xor     r8d, r8d; bAlertable
0x140002dab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002dae  mov     rcx, rbx; hHandle
0x140002db1  call    cs:__imp_WaitForSingleObjectEx
0x140002db7  cmp     eax, 102h
0x140002dbc  jz      short loc_140002DCE
0x140002dbe  test    eax, 0FFFFFF7Fh
0x140002dc3  jnz     loc_14000304F
0x140002dc9  mov     rdi, rbx
0x140002dcc  jmp     short loc_140002DD0
0x140002dce  xor     edi, edi
0x140002dd0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140002dd5  mov     [rsp+280h+hObject], 0
0x140002dde  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002de3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140002de8  mov     esi, eax
0x140002dea  test    eax, eax
0x140002dec  jns     short loc_140002E6D
0x140002dee  mov     rcx, [rbp+188h]; this
0x140002df5  lea     r8, aWil; "wil"
0x140002dfc  mov     r9d, eax; char *
0x140002dff  mov     edx, 66h ; 'f'; void *
0x140002e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e09  mov     rcx, [rbp+188h]; this
0x140002e10  lea     r8, aWil; "wil"
0x140002e17  mov     r9d, esi; char *
0x140002e1a  mov     edx, 6Fh ; 'o'; void *
0x140002e1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e24  mov     rcx, [rbp+188h]; this
0x140002e2b  lea     r8, aWil; "wil"
0x140002e32  mov     r9d, esi; char *
0x140002e35  mov     edx, 12Eh; void *
0x140002e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e3f  test    rdi, rdi
0x140002e42  jz      short loc_140002E55
0x140002e44  mov     rcx, rdi; hMutex
0x140002e47  call    cs:__imp_ReleaseMutex
0x140002e4d  test    eax, eax
0x140002e4f  jz      loc_14000305C
0x140002e55  mov     rcx, rbx; hObject
0x140002e58  call    cs:__imp_CloseHandle
0x140002e5e  test    eax, eax
0x140002e60  jz      loc_14000306E
0x140002e66  mov     eax, esi
0x140002e68  jmp     loc_140003017
0x140002e6d  mov     rax, [rsp+280h+hObject]
0x140002e72  lea     rcx, ds:0[rax*4]
0x140002e7a  test    rcx, rcx
0x140002e7d  jz      short loc_140002E8D
0x140002e7f  mov     [r15], rcx
0x140002e82  mov     eax, [rcx]
0x140002e84  inc     eax
0x140002e86  mov     [rcx], eax
0x140002e88  jmp     loc_140002FED
0x140002e8d  mov     rdx, r14; dwBytes
0x140002e90  mov     qword ptr [r15], 0
0x140002e97  mov     ecx, 8; dwFlags
0x140002e9c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002ea1  mov     rsi, rax
0x140002ea4  test    rax, rax
0x140002ea7  jnz     short loc_140002ECF
0x140002ea9  mov     rcx, [rbp+188h]; this
0x140002eb0  lea     r8, aWil; "wil"
0x140002eb7  mov     r14d, 8007000Eh
0x140002ebd  mov     edx, 14Bh; void *
0x140002ec2  mov     r9d, r14d; char *
0x140002ec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002eca  jmp     loc_140002F62
0x140002ecf  xorps   xmm0, xmm0
0x140002ed2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140002ed8  test    sil, 3
0x140002edc  jnz     loc_140003080
0x140002ee2  mov     r9, rsi
0x140002ee5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140002eea  shr     r9, 2; unsigned __int64
0x140002eee  lea     rcx, [rsp+280h+hObject]; this
0x140002ef3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140002ef8  mov     r14d, eax
0x140002efb  test    eax, eax
0x140002efd  jns     loc_140002FA9
0x140002f03  mov     rcx, [rbp+188h]; this
0x140002f0a  lea     r8, aWil; "wil"
0x140002f11  mov     r9d, eax; char *
0x140002f14  mov     edx, 14Eh; void *
0x140002f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f1e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140002f23  test    rcx, rcx
0x140002f26  jz      short loc_140002F36
0x140002f28  call    cs:__imp_CloseHandle
0x140002f2e  test    eax, eax
0x140002f30  jz      loc_140003086
0x140002f36  mov     rcx, [rsp+280h+hObject]; hObject
0x140002f3b  test    rcx, rcx
0x140002f3e  jz      short loc_140002F4E
0x140002f40  call    cs:__imp_CloseHandle
0x140002f46  test    eax, eax
0x140002f48  jz      loc_140003098
0x140002f4e  call    cs:__imp_GetProcessHeap
0x140002f54  mov     r8, rsi; lpMem
0x140002f57  xor     edx, edx; dwFlags
0x140002f59  mov     rcx, rax; hHeap
0x140002f5c  call    cs:__imp_HeapFree
0x140002f62  mov     rcx, [rbp+188h]; this
0x140002f69  lea     r8, aWil; "wil"
0x140002f70  mov     r9d, r14d; char *
0x140002f73  mov     edx, 137h; void *
0x140002f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f7d  test    rdi, rdi
0x140002f80  jz      short loc_140002F93
0x140002f82  mov     rcx, rdi; hMutex
0x140002f85  call    cs:__imp_ReleaseMutex
0x140002f8b  test    eax, eax
0x140002f8d  jz      loc_1400030AA
0x140002f93  mov     rcx, rbx; hObject
0x140002f96  call    cs:__imp_CloseHandle
0x140002f9c  test    eax, eax
0x140002f9e  jz      loc_1400030BC
0x140002fa4  mov     eax, r14d
0x140002fa7  jmp     short loc_140003017
0x140002fa9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140002fae  xor     edx, edx; Val
0x140002fb0  mov     dword ptr [rsi], 1
0x140002fb6  lea     rcx, [rsi+22h]; void *
0x140002fba  mov     [rsi+8], rbx
0x140002fbe  movdqu  xmmword ptr [rsi+10h], xmm0
0x140002fc3  lea     r8d, [rdx+56h]; Size
0x140002fc7  call    memset_0
0x140002fcc  xor     edx, edx; Val
0x140002fce  mov     word ptr [rsi+20h], 58h ; 'X'
0x140002fd4  lea     rcx, [rsi+28h]; void *
0x140002fd8  mov     dword ptr [rsi+24h], 1
0x140002fdf  lea     r8d, [rdx+50h]; Size
0x140002fe3  call    memset_0
0x140002fe8  xor     ebx, ebx
0x140002fea  mov     [r15], rsi
0x140002fed  test    rdi, rdi
0x140002ff0  jz      short loc_140003003
0x140002ff2  mov     rcx, rdi; hMutex
0x140002ff5  call    cs:__imp_ReleaseMutex
0x140002ffb  test    eax, eax
0x140002ffd  jz      loc_1400030CE
0x140003003  test    rbx, rbx
0x140003006  jz      short loc_140003015
0x140003008  mov     rcx, rbx; hObject
0x14000300b  call    cs:__imp_CloseHandle
0x140003011  test    eax, eax
0x140003013  jz      short loc_14000303D
0x140003015  xor     eax, eax
0x140003017  mov     rcx, [rbp+180h+var_30]
0x14000301e  xor     rcx, rsp; StackCookie
0x140003021  call    __security_check_cookie
0x140003026  mov     rbx, [rsp+280h+arg_10]
0x14000302e  add     rsp, 260h
0x140003035  pop     r15
0x140003037  pop     r14
0x140003039  pop     rdi
0x14000303a  pop     rsi
0x14000303b  pop     rbp
0x14000303c  retn
0x14000303d  mov     rcx, [rbp+188h]; this
0x140003044  mov     edx, 0A0Bh; void *
0x140003049  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000304f  mov     rcx, [rbp+188h]; this
0x140003056  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000305c  mov     rcx, [rbp+188h]; this
0x140003063  mov     edx, 0A15h; void *
0x140003068  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000306e  mov     rcx, [rbp+188h]; this
0x140003075  mov     edx, 0A0Bh; void *
0x14000307a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003080  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003086  mov     rcx, [rbp+188h]; this
0x14000308d  mov     edx, 0A0Bh; void *
0x140003092  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003098  mov     rcx, [rbp+188h]; this
0x14000309f  mov     edx, 0A0Bh; void *
0x1400030a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030aa  mov     rcx, [rbp+188h]; this
0x1400030b1  mov     edx, 0A15h; void *
0x1400030b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030bc  mov     rcx, [rbp+188h]; this
0x1400030c3  mov     edx, 0A0Bh; void *
0x1400030c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030ce  mov     rcx, [rbp+188h]; this
0x1400030d5  mov     edx, 0A15h; void *
0x1400030da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
