# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009b4c`
- end: `0x180009f1f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000aaa4`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800098a4`
- `0x180009b4c`
- `0x180009f28`
- `0x18000a180`
- `0x18000a774`
- `0x18000b54c`
- `0x18000ba40`
- `0x18000c350`
- `0x18000c488`
- `0x18000c9f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009b85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009b85`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009bca`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009bca`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009bf1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180009bf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c91`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e51`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009c91`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009dae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009e51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009d7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009dc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009e6d`

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
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned __int64 v29; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v37[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v37[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v37, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v34);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v37[0]);
  if ( 4 * v37[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v37, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v36);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v37[0];
  v29 = v37[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  v37[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v37[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v37);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x180009b4c  mov     [rsp-8+arg_10], rbx
0x180009b51  push    rbp
0x180009b52  push    rsi
0x180009b53  push    rdi
0x180009b54  push    r14
0x180009b56  push    r15
0x180009b58  lea     rbp, [rsp-160h]
0x180009b60  sub     rsp, 260h
0x180009b67  mov     rax, cs:__security_cookie
0x180009b6e  xor     rax, rsp
0x180009b71  mov     [rbp+180h+var_30], rax
0x180009b78  mov     r15, rdx
0x180009b7b  mov     qword ptr [rdx], 0
0x180009b82  mov     rbx, rcx
0x180009b85  call    cs:__imp_GetCurrentProcessId
0x180009b8c  nop     dword ptr [rax+rax+00h]
0x180009b91  mov     r14d, 78h ; 'x'
0x180009b97  mov     [rsp+280h+var_258], rbx
0x180009b9c  mov     r9d, eax
0x180009b9f  mov     [rsp+280h+var_260], r14d; int
0x180009ba4  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009bab  mov     edx, 104h; unsigned __int64
0x180009bb0  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180009bb5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009bba  mov     r9d, 1F0001h; dwDesiredAccess
0x180009bc0  lea     rdx, [rsp+280h+Name]; lpName
0x180009bc5  xor     r8d, r8d; dwFlags
0x180009bc8  xor     ecx, ecx; lpMutexAttributes
0x180009bca  call    cs:__imp_CreateMutexExW
0x180009bd1  nop     dword ptr [rax+rax+00h]
0x180009bd6  mov     rbx, rax
0x180009bd9  test    rax, rax
0x180009bdc  jnz     short loc_180009BE8
0x180009bde  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009be3  jmp     loc_180009E7F
0x180009be8  xor     r8d, r8d; bAlertable
0x180009beb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180009bee  mov     rcx, rbx; hHandle
0x180009bf1  call    cs:__imp_WaitForSingleObjectEx
0x180009bf8  nop     dword ptr [rax+rax+00h]
0x180009bfd  cmp     eax, 102h
0x180009c02  jz      short loc_180009C14
0x180009c04  test    eax, 0FFFFFF7Fh
0x180009c09  jnz     loc_180009ECA
0x180009c0f  mov     rdi, rbx
0x180009c12  jmp     short loc_180009C16
0x180009c14  xor     edi, edi
0x180009c16  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180009c1b  mov     [rsp+280h+var_250], 0
0x180009c24  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180009c29  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180009c2e  mov     esi, eax
0x180009c30  test    eax, eax
0x180009c32  jns     loc_180009CC3
0x180009c38  mov     rcx, [rbp+188h]; this
0x180009c3f  lea     r8, aWil; "wil"
0x180009c46  mov     r9d, eax; char *
0x180009c49  mov     edx, 66h ; 'f'; void *
0x180009c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c53  mov     rcx, [rbp+188h]; this
0x180009c5a  lea     r8, aWil; "wil"
0x180009c61  mov     r9d, esi; char *
0x180009c64  mov     edx, 6Fh ; 'o'; void *
0x180009c69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c6e  mov     rcx, [rbp+188h]; this
0x180009c75  lea     r8, aWil; "wil"
0x180009c7c  mov     r9d, esi; char *
0x180009c7f  mov     edx, 12Eh; void *
0x180009c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c89  test    rdi, rdi
0x180009c8c  jz      short loc_180009CA5
0x180009c8e  mov     rcx, rdi; hMutex
0x180009c91  call    cs:__imp_ReleaseMutex
0x180009c98  nop     dword ptr [rax+rax+00h]
0x180009c9d  test    eax, eax
0x180009c9f  jz      loc_180009ED7
0x180009ca5  mov     rcx, rbx; hObject
0x180009ca8  call    cs:__imp_CloseHandle
0x180009caf  nop     dword ptr [rax+rax+00h]
0x180009cb4  test    eax, eax
0x180009cb6  jz      loc_180009EE9
0x180009cbc  mov     eax, esi
0x180009cbe  jmp     loc_180009E7F
0x180009cc3  mov     rax, [rsp+280h+var_250]
0x180009cc8  lea     rcx, ds:0[rax*4]
0x180009cd0  test    rcx, rcx
0x180009cd3  jz      short loc_180009CE3
0x180009cd5  mov     [r15], rcx
0x180009cd8  mov     eax, [rcx]
0x180009cda  inc     eax
0x180009cdc  mov     [rcx], eax
0x180009cde  jmp     loc_180009E49
0x180009ce3  mov     rdx, r14; dwBytes
0x180009ce6  mov     qword ptr [r15], 0
0x180009ced  mov     ecx, 8; dwFlags
0x180009cf2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009cf7  mov     r14, rax
0x180009cfa  test    rax, rax
0x180009cfd  jnz     short loc_180009D21
0x180009cff  mov     rcx, [rbp+188h]; this
0x180009d06  lea     r8, aWil; "wil"
0x180009d0d  mov     esi, 8007000Eh
0x180009d12  mov     edx, 14Bh; void *
0x180009d17  mov     r9d, esi; char *
0x180009d1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d1f  jmp     short loc_180009D8B
0x180009d21  xorps   xmm0, xmm0
0x180009d24  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180009d29  mov     r8, r14; void *
0x180009d2c  lea     rcx, [rsp+280h+var_250]; this
0x180009d31  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180009d37  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEB_WPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(wchar_t const *,void *)
0x180009d3c  mov     esi, eax
0x180009d3e  test    eax, eax
0x180009d40  jns     loc_180009DDE
0x180009d46  mov     rcx, [rbp+188h]; this
0x180009d4d  lea     r8, aWil; "wil"
0x180009d54  mov     r9d, eax; char *
0x180009d57  mov     edx, 14Eh; void *
0x180009d5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d61  lea     rcx, [rsp+280h+var_250]; this
0x180009d66  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009d6b  call    cs:__imp_GetProcessHeap
0x180009d72  nop     dword ptr [rax+rax+00h]
0x180009d77  mov     r8, r14; lpMem
0x180009d7a  xor     edx, edx; dwFlags
0x180009d7c  mov     rcx, rax; hHeap
0x180009d7f  call    cs:__imp_HeapFree
0x180009d86  nop     dword ptr [rax+rax+00h]
0x180009d8b  mov     rcx, [rbp+188h]; this
0x180009d92  lea     r8, aWil; "wil"
0x180009d99  mov     r9d, esi; char *
0x180009d9c  mov     edx, 137h; void *
0x180009da1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009da6  test    rdi, rdi
0x180009da9  jz      short loc_180009DC2
0x180009dab  mov     rcx, rdi; hMutex
0x180009dae  call    cs:__imp_ReleaseMutex
0x180009db5  nop     dword ptr [rax+rax+00h]
0x180009dba  test    eax, eax
0x180009dbc  jz      loc_180009EFB
0x180009dc2  mov     rcx, rbx; hObject
0x180009dc5  call    cs:__imp_CloseHandle
0x180009dcc  nop     dword ptr [rax+rax+00h]
0x180009dd1  test    eax, eax
0x180009dd3  jz      loc_180009EB8
0x180009dd9  jmp     loc_180009CBC
0x180009dde  mov     rax, [rsp+280h+var_250]
0x180009de3  lea     rcx, [r14+22h]; void *
0x180009de7  xor     edx, edx; Val
0x180009de9  mov     [r14+10h], rax
0x180009ded  mov     rax, [rsp+280h+var_250+8]
0x180009df2  mov     dword ptr [r14], 1
0x180009df9  mov     [r14+8], rbx
0x180009dfd  lea     r8d, [rdx+56h]; Size
0x180009e01  mov     [rsp+280h+var_250], 0
0x180009e0a  mov     [r14+18h], rax
0x180009e0e  mov     [rsp+280h+var_250+8], 0
0x180009e17  call    memset_0
0x180009e1c  xor     edx, edx; Val
0x180009e1e  mov     word ptr [r14+20h], 58h ; 'X'
0x180009e25  lea     rcx, [r14+28h]; void *
0x180009e29  mov     dword ptr [r14+24h], 1
0x180009e31  lea     r8d, [rdx+50h]; Size
0x180009e35  call    memset_0
0x180009e3a  lea     rcx, [rsp+280h+var_250]; this
0x180009e3f  mov     [r15], r14
0x180009e42  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009e47  xor     ebx, ebx
0x180009e49  test    rdi, rdi
0x180009e4c  jz      short loc_180009E65
0x180009e4e  mov     rcx, rdi; hMutex
0x180009e51  call    cs:__imp_ReleaseMutex
0x180009e58  nop     dword ptr [rax+rax+00h]
0x180009e5d  test    eax, eax
0x180009e5f  jz      loc_180009F0D
0x180009e65  test    rbx, rbx
0x180009e68  jz      short loc_180009E7D
0x180009e6a  mov     rcx, rbx; hObject
0x180009e6d  call    cs:__imp_CloseHandle
0x180009e74  nop     dword ptr [rax+rax+00h]
0x180009e79  test    eax, eax
0x180009e7b  jz      short loc_180009EA6
0x180009e7d  xor     eax, eax
0x180009e7f  mov     rcx, [rbp+180h+var_30]
0x180009e86  xor     rcx, rsp; StackCookie
0x180009e89  call    __security_check_cookie
0x180009e8e  mov     rbx, [rsp+280h+arg_10]
0x180009e96  add     rsp, 260h
0x180009e9d  pop     r15
0x180009e9f  pop     r14
0x180009ea1  pop     rdi
0x180009ea2  pop     rsi
0x180009ea3  pop     rbp
0x180009ea4  retn
0x180009ea6  mov     rcx, [rbp+188h]; this
0x180009ead  mov     edx, 0A0Bh; void *
0x180009eb2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009eb8  mov     rcx, [rbp+188h]; this
0x180009ebf  mov     edx, 0A0Bh; void *
0x180009ec4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009eca  mov     rcx, [rbp+188h]; this
0x180009ed1  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180009ed7  mov     rcx, [rbp+188h]; this
0x180009ede  mov     edx, 0A15h; void *
0x180009ee3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ee9  mov     rcx, [rbp+188h]; this
0x180009ef0  mov     edx, 0A0Bh; void *
0x180009ef5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009efb  mov     rcx, [rbp+188h]; this
0x180009f02  mov     edx, 0A15h; void *
0x180009f07  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009f0d  mov     rcx, [rbp+188h]; this
0x180009f14  mov     edx, 0A15h; void *
0x180009f19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
