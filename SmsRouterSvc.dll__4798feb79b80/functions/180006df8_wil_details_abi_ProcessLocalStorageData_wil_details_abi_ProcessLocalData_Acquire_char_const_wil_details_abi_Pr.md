# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006df8`
- end: `0x1800071c0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007d80`

## callees

- `0x180003a60`
- `0x180004998`
- `0x180006df8`
- `0x1800071c8`
- `0x1800074b4`
- `0x180007b18`
- `0x1800085f8`
- `0x1800089e4`
- `0x1800093d4`
- `0x18000948c`
- `0x18000986c`
- `0x18000987c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006e70`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006e70`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006e91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006e91`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007065`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800070d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006f27`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007065`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800070d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000702e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000702e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000703c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000703c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006e31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006e31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007008`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007076`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007008`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007076`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070eb`

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
0x180006df8  mov     [rsp-8+arg_10], rbx
0x180006dfd  push    rbp
0x180006dfe  push    rsi
0x180006dff  push    rdi
0x180006e00  push    r14
0x180006e02  push    r15
0x180006e04  lea     rbp, [rsp-160h]
0x180006e0c  sub     rsp, 260h
0x180006e13  mov     rax, cs:__security_cookie
0x180006e1a  xor     rax, rsp
0x180006e1d  mov     [rbp+180h+var_30], rax
0x180006e24  mov     r15, rdx
0x180006e27  mov     qword ptr [rdx], 0
0x180006e2e  mov     rbx, rcx
0x180006e31  call    cs:__imp_GetCurrentProcessId
0x180006e37  mov     r14d, 78h ; 'x'
0x180006e3d  mov     [rsp+280h+var_258], rbx
0x180006e42  mov     r9d, eax
0x180006e45  mov     [rsp+280h+var_260], r14d; int
0x180006e4a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006e51  mov     edx, 104h; unsigned __int64
0x180006e56  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006e5b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006e60  mov     r9d, 1F0001h; dwDesiredAccess
0x180006e66  lea     rdx, [rsp+280h+Name]; lpName
0x180006e6b  xor     r8d, r8d; dwFlags
0x180006e6e  xor     ecx, ecx; lpMutexAttributes
0x180006e70  call    cs:__imp_CreateMutexExW
0x180006e76  mov     rbx, rax
0x180006e79  test    rax, rax
0x180006e7c  jnz     short loc_180006E88
0x180006e7e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006e83  jmp     loc_1800070F7
0x180006e88  xor     r8d, r8d; bAlertable
0x180006e8b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006e8e  mov     rcx, rbx; hHandle
0x180006e91  call    cs:__imp_WaitForSingleObjectEx
0x180006e97  cmp     eax, 102h
0x180006e9c  jz      short loc_180006EAE
0x180006e9e  test    eax, 0FFFFFF7Fh
0x180006ea3  jnz     loc_18000712F
0x180006ea9  mov     rdi, rbx
0x180006eac  jmp     short loc_180006EB0
0x180006eae  xor     edi, edi
0x180006eb0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006eb5  mov     [rsp+280h+hObject], 0
0x180006ebe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006ec3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006ec8  mov     esi, eax
0x180006eca  test    eax, eax
0x180006ecc  jns     short loc_180006F4D
0x180006ece  mov     rcx, [rbp+188h]; this
0x180006ed5  lea     r8, aWil; "wil"
0x180006edc  mov     r9d, eax; char *
0x180006edf  mov     edx, 66h ; 'f'; void *
0x180006ee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ee9  mov     rcx, [rbp+188h]; this
0x180006ef0  lea     r8, aWil; "wil"
0x180006ef7  mov     r9d, esi; char *
0x180006efa  mov     edx, 6Fh ; 'o'; void *
0x180006eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f04  mov     rcx, [rbp+188h]; this
0x180006f0b  lea     r8, aWil; "wil"
0x180006f12  mov     r9d, esi; char *
0x180006f15  mov     edx, 12Eh; void *
0x180006f1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f1f  test    rdi, rdi
0x180006f22  jz      short loc_180006F35
0x180006f24  mov     rcx, rdi; hMutex
0x180006f27  call    cs:__imp_ReleaseMutex
0x180006f2d  test    eax, eax
0x180006f2f  jz      loc_18000713C
0x180006f35  mov     rcx, rbx; hObject
0x180006f38  call    cs:__imp_CloseHandle
0x180006f3e  test    eax, eax
0x180006f40  jz      loc_18000714E
0x180006f46  mov     eax, esi
0x180006f48  jmp     loc_1800070F7
0x180006f4d  mov     rax, [rsp+280h+hObject]
0x180006f52  lea     rcx, ds:0[rax*4]
0x180006f5a  test    rcx, rcx
0x180006f5d  jz      short loc_180006F6D
0x180006f5f  mov     [r15], rcx
0x180006f62  mov     eax, [rcx]
0x180006f64  inc     eax
0x180006f66  mov     [rcx], eax
0x180006f68  jmp     loc_1800070CD
0x180006f6d  mov     rdx, r14; dwBytes
0x180006f70  mov     qword ptr [r15], 0
0x180006f77  mov     ecx, 8; dwFlags
0x180006f7c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006f81  mov     rsi, rax
0x180006f84  test    rax, rax
0x180006f87  jnz     short loc_180006FAF
0x180006f89  mov     rcx, [rbp+188h]; this
0x180006f90  lea     r8, aWil; "wil"
0x180006f97  mov     r14d, 8007000Eh
0x180006f9d  mov     edx, 14Bh; void *
0x180006fa2  mov     r9d, r14d; char *
0x180006fa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006faa  jmp     loc_180007042
0x180006faf  xorps   xmm0, xmm0
0x180006fb2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006fb8  test    sil, 3
0x180006fbc  jnz     loc_180007160
0x180006fc2  mov     r9, rsi
0x180006fc5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006fca  shr     r9, 2; unsigned __int64
0x180006fce  lea     rcx, [rsp+280h+hObject]; this
0x180006fd3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006fd8  mov     r14d, eax
0x180006fdb  test    eax, eax
0x180006fdd  jns     loc_180007089
0x180006fe3  mov     rcx, [rbp+188h]; this
0x180006fea  lea     r8, aWil; "wil"
0x180006ff1  mov     r9d, eax; char *
0x180006ff4  mov     edx, 14Eh; void *
0x180006ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ffe  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007003  test    rcx, rcx
0x180007006  jz      short loc_180007016
0x180007008  call    cs:__imp_CloseHandle
0x18000700e  test    eax, eax
0x180007010  jz      loc_180007166
0x180007016  mov     rcx, [rsp+280h+hObject]; hObject
0x18000701b  test    rcx, rcx
0x18000701e  jz      short loc_18000702E
0x180007020  call    cs:__imp_CloseHandle
0x180007026  test    eax, eax
0x180007028  jz      loc_180007178
0x18000702e  call    cs:__imp_GetProcessHeap
0x180007034  mov     r8, rsi; lpMem
0x180007037  xor     edx, edx; dwFlags
0x180007039  mov     rcx, rax; hHeap
0x18000703c  call    cs:__imp_HeapFree
0x180007042  mov     rcx, [rbp+188h]; this
0x180007049  lea     r8, aWil; "wil"
0x180007050  mov     r9d, r14d; char *
0x180007053  mov     edx, 137h; void *
0x180007058  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000705d  test    rdi, rdi
0x180007060  jz      short loc_180007073
0x180007062  mov     rcx, rdi; hMutex
0x180007065  call    cs:__imp_ReleaseMutex
0x18000706b  test    eax, eax
0x18000706d  jz      loc_18000718A
0x180007073  mov     rcx, rbx; hObject
0x180007076  call    cs:__imp_CloseHandle
0x18000707c  test    eax, eax
0x18000707e  jz      loc_18000719C
0x180007084  mov     eax, r14d
0x180007087  jmp     short loc_1800070F7
0x180007089  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000708e  xor     edx, edx; Val
0x180007090  mov     dword ptr [rsi], 1
0x180007096  lea     rcx, [rsi+22h]; void *
0x18000709a  mov     [rsi+8], rbx
0x18000709e  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800070a3  lea     r8d, [rdx+56h]; Size
0x1800070a7  call    memset_0
0x1800070ac  xor     edx, edx; Val
0x1800070ae  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800070b4  lea     rcx, [rsi+28h]; void *
0x1800070b8  mov     dword ptr [rsi+24h], 1
0x1800070bf  lea     r8d, [rdx+50h]; Size
0x1800070c3  call    memset_0
0x1800070c8  xor     ebx, ebx
0x1800070ca  mov     [r15], rsi
0x1800070cd  test    rdi, rdi
0x1800070d0  jz      short loc_1800070E3
0x1800070d2  mov     rcx, rdi; hMutex
0x1800070d5  call    cs:__imp_ReleaseMutex
0x1800070db  test    eax, eax
0x1800070dd  jz      loc_1800071AE
0x1800070e3  test    rbx, rbx
0x1800070e6  jz      short loc_1800070F5
0x1800070e8  mov     rcx, rbx; hObject
0x1800070eb  call    cs:__imp_CloseHandle
0x1800070f1  test    eax, eax
0x1800070f3  jz      short loc_18000711D
0x1800070f5  xor     eax, eax
0x1800070f7  mov     rcx, [rbp+180h+var_30]
0x1800070fe  xor     rcx, rsp; StackCookie
0x180007101  call    __security_check_cookie
0x180007106  mov     rbx, [rsp+280h+arg_10]
0x18000710e  add     rsp, 260h
0x180007115  pop     r15
0x180007117  pop     r14
0x180007119  pop     rdi
0x18000711a  pop     rsi
0x18000711b  pop     rbp
0x18000711c  retn
0x18000711d  mov     rcx, [rbp+188h]; this
0x180007124  mov     edx, 0A0Bh; void *
0x180007129  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000712f  mov     rcx, [rbp+188h]; this
0x180007136  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000713c  mov     rcx, [rbp+188h]; this
0x180007143  mov     edx, 0A15h; void *
0x180007148  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000714e  mov     rcx, [rbp+188h]; this
0x180007155  mov     edx, 0A0Bh; void *
0x18000715a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007160  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007166  mov     rcx, [rbp+188h]; this
0x18000716d  mov     edx, 0A0Bh; void *
0x180007172  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007178  mov     rcx, [rbp+188h]; this
0x18000717f  mov     edx, 0A0Bh; void *
0x180007184  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000718a  mov     rcx, [rbp+188h]; this
0x180007191  mov     edx, 0A15h; void *
0x180007196  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000719c  mov     rcx, [rbp+188h]; this
0x1800071a3  mov     edx, 0A0Bh; void *
0x1800071a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071ae  mov     rcx, [rbp+188h]; this
0x1800071b5  mov     edx, 0A15h; void *
0x1800071ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
