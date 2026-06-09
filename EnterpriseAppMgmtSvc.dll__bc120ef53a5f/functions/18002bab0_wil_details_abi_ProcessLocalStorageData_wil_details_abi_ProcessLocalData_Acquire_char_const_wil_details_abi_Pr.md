# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002bab0`
- end: `0x18002be90`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `992`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18002cf38`

## callees

- `0x180005ff4`
- `0x18000a448`
- `0x18000aa68`
- `0x18000aedc`
- `0x18000b5b8`
- `0x18000bc08`
- `0x18000d3dc`
- `0x18000daf4`
- `0x18000e7c8`
- `0x18002bab0`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bce9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002bce9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002bcfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002bae9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002bae9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bc16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002be01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002bbf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002bd2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002bdde`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002bbf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002bd2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002bdde`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002bb57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18002bb57`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002bb2f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18002bb2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v36; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+38h] [rbp-C8h]
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
  v36 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v36, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v33);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v34);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v36);
  if ( 4 * v36 )
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
  v36 = 0;
  v37 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)&v36, Name, v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v36);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v35);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v6;
  *((_QWORD *)v22 + 2) = v36;
  v36 = 0;
  *((_QWORD *)v22 + 3) = v37;
  v37 = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v36);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x18002bab0  mov     [rsp-8+arg_10], rbx
0x18002bab5  push    rbp
0x18002bab6  push    rsi
0x18002bab7  push    rdi
0x18002bab8  push    r14
0x18002baba  push    r15
0x18002babc  lea     rbp, [rsp-160h]
0x18002bac4  sub     rsp, 260h
0x18002bacb  mov     rax, cs:__security_cookie
0x18002bad2  xor     rax, rsp
0x18002bad5  mov     [rbp+180h+var_30], rax
0x18002badc  mov     r15, rdx
0x18002badf  mov     rbx, rcx
0x18002bae2  mov     qword ptr [rdx], 0
0x18002bae9  call    cs:__imp_GetCurrentProcessId
0x18002baf0  nop     dword ptr [rax+rax+00h]
0x18002baf5  mov     r9d, eax
0x18002baf8  mov     [rsp+280h+var_258], rbx
0x18002bafd  mov     r14d, 78h ; 'x'
0x18002bb03  mov     [rsp+280h+var_260], r14d; int
0x18002bb08  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002bb0f  mov     edx, 104h; unsigned __int64
0x18002bb14  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002bb19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002bb1e  nop
0x18002bb1f  mov     r9d, 1F0001h; dwDesiredAccess
0x18002bb25  xor     r8d, r8d; dwFlags
0x18002bb28  lea     rdx, [rsp+280h+Name]; lpName
0x18002bb2d  xor     ecx, ecx; lpMutexAttributes
0x18002bb2f  call    cs:__imp_CreateMutexExW
0x18002bb36  nop     dword ptr [rax+rax+00h]
0x18002bb3b  mov     rbx, rax
0x18002bb3e  test    rax, rax
0x18002bb41  jnz     short loc_18002BB4E
0x18002bb43  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18002bb48  nop
0x18002bb49  jmp     loc_18002BE1A
0x18002bb4e  xor     r8d, r8d; bAlertable
0x18002bb51  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002bb54  mov     rcx, rbx; hHandle
0x18002bb57  call    cs:__imp_WaitForSingleObjectEx
0x18002bb5e  nop     dword ptr [rax+rax+00h]
0x18002bb63  cmp     eax, 102h
0x18002bb68  jz      short loc_18002BB7A
0x18002bb6a  test    eax, 0FFFFFF7Fh
0x18002bb6f  jnz     loc_18002BE4C
0x18002bb75  mov     rdi, rbx
0x18002bb78  jmp     short loc_18002BB7C
0x18002bb7a  xor     edi, edi
0x18002bb7c  mov     [rsp+280h+var_250], 0
0x18002bb85  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x18002bb8a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002bb8f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18002bb94  mov     esi, eax
0x18002bb96  test    eax, eax
0x18002bb98  jns     loc_18002BC38
0x18002bb9e  mov     rcx, [rbp+188h]; this
0x18002bba5  mov     r9d, eax; char *
0x18002bba8  lea     r8, aWil; "wil"
0x18002bbaf  mov     edx, 66h ; 'f'; void *
0x18002bbb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bbb9  mov     rcx, [rbp+188h]; this
0x18002bbc0  mov     r9d, esi; char *
0x18002bbc3  lea     r8, aWil; "wil"
0x18002bbca  mov     edx, 6Fh ; 'o'; void *
0x18002bbcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bbd4  mov     rcx, [rbp+188h]; this
0x18002bbdb  mov     r9d, esi; char *
0x18002bbde  lea     r8, aWil; "wil"
0x18002bbe5  mov     edx, 12Eh; void *
0x18002bbea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bbef  nop
0x18002bbf0  test    rdi, rdi
0x18002bbf3  jz      short loc_18002BC13
0x18002bbf5  mov     rcx, rdi; hMutex
0x18002bbf8  call    cs:__imp_ReleaseMutex
0x18002bbff  nop     dword ptr [rax+rax+00h]
0x18002bc04  mov     rcx, [rbp+188h]; this
0x18002bc0b  test    eax, eax
0x18002bc0d  jz      loc_18002BE59
0x18002bc13  mov     rcx, rbx; hObject
0x18002bc16  call    cs:__imp_CloseHandle
0x18002bc1d  nop     dword ptr [rax+rax+00h]
0x18002bc22  mov     rcx, [rbp+188h]; this
0x18002bc29  test    eax, eax
0x18002bc2b  jz      loc_18002BE64
0x18002bc31  mov     eax, esi
0x18002bc33  jmp     loc_18002BE1A
0x18002bc38  mov     rax, [rsp+280h+var_250]
0x18002bc3d  lea     rcx, ds:0[rax*4]
0x18002bc45  test    rcx, rcx
0x18002bc48  jz      short loc_18002BC58
0x18002bc4a  mov     [r15], rcx
0x18002bc4d  mov     eax, [rcx]
0x18002bc4f  inc     eax
0x18002bc51  mov     [rcx], eax
0x18002bc53  jmp     loc_18002BDD6
0x18002bc58  mov     qword ptr [r15], 0
0x18002bc5f  mov     rdx, r14; dwBytes
0x18002bc62  mov     ecx, 8; dwFlags
0x18002bc67  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002bc6c  mov     r14, rax
0x18002bc6f  test    rax, rax
0x18002bc72  jnz     short loc_18002BC96
0x18002bc74  mov     rcx, [rbp+188h]; this
0x18002bc7b  mov     esi, 8007000Eh
0x18002bc80  mov     r9d, esi; char *
0x18002bc83  lea     r8, aWil; "wil"
0x18002bc8a  mov     edx, 14Bh; void *
0x18002bc8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc94  jmp     short loc_18002BD09
0x18002bc96  mov     [rsp+280h+var_250], 0
0x18002bc9f  mov     [rsp+280h+var_248], 0
0x18002bca8  mov     r8, r14; void *
0x18002bcab  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18002bcb0  lea     rcx, [rsp+280h+var_250]; this
0x18002bcb5  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18002bcba  mov     esi, eax
0x18002bcbc  test    eax, eax
0x18002bcbe  jns     loc_18002BD6B
0x18002bcc4  mov     rcx, [rbp+188h]; this
0x18002bccb  mov     r9d, eax; char *
0x18002bcce  lea     r8, aWil; "wil"
0x18002bcd5  mov     edx, 14Eh; void *
0x18002bcda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bcdf  lea     rcx, [rsp+280h+var_250]; this
0x18002bce4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18002bce9  call    cs:__imp_GetProcessHeap
0x18002bcf0  nop     dword ptr [rax+rax+00h]
0x18002bcf5  mov     rcx, rax; hHeap
0x18002bcf8  mov     r8, r14; lpMem
0x18002bcfb  xor     edx, edx; dwFlags
0x18002bcfd  call    cs:__imp_HeapFree
0x18002bd04  nop     dword ptr [rax+rax+00h]
0x18002bd09  mov     rcx, [rbp+188h]; this
0x18002bd10  mov     r9d, esi; char *
0x18002bd13  lea     r8, aWil; "wil"
0x18002bd1a  mov     edx, 137h; void *
0x18002bd1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd24  nop
0x18002bd25  test    rdi, rdi
0x18002bd28  jz      short loc_18002BD48
0x18002bd2a  mov     rcx, rdi; hMutex
0x18002bd2d  call    cs:__imp_ReleaseMutex
0x18002bd34  nop     dword ptr [rax+rax+00h]
0x18002bd39  mov     rcx, [rbp+188h]; this
0x18002bd40  test    eax, eax
0x18002bd42  jz      loc_18002BE6F
0x18002bd48  mov     rcx, rbx; hObject
0x18002bd4b  call    cs:__imp_CloseHandle
0x18002bd52  nop     dword ptr [rax+rax+00h]
0x18002bd57  mov     rcx, [rbp+188h]; this
0x18002bd5e  test    eax, eax
0x18002bd60  jz      loc_18002BE7A
0x18002bd66  jmp     loc_18002BC31
0x18002bd6b  mov     dword ptr [r14], 1
0x18002bd72  mov     [r14+8], rbx
0x18002bd76  mov     rax, [rsp+280h+var_250]
0x18002bd7b  mov     [r14+10h], rax
0x18002bd7f  mov     [rsp+280h+var_250], 0
0x18002bd88  mov     rax, [rsp+280h+var_248]
0x18002bd8d  mov     [r14+18h], rax
0x18002bd91  mov     [rsp+280h+var_248], 0
0x18002bd9a  lea     rcx, [r14+22h]; void *
0x18002bd9e  xor     edx, edx; Val
0x18002bda0  lea     r8d, [rdx+56h]; Size
0x18002bda4  call    memset_0
0x18002bda9  mov     word ptr [r14+20h], 58h ; 'X'
0x18002bdb0  mov     dword ptr [r14+24h], 1
0x18002bdb8  lea     rcx, [r14+28h]; void *
0x18002bdbc  xor     edx, edx; Val
0x18002bdbe  lea     r8d, [rdx+50h]; Size
0x18002bdc2  call    memset_0
0x18002bdc7  mov     [r15], r14
0x18002bdca  lea     rcx, [rsp+280h+var_250]; this
0x18002bdcf  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18002bdd4  xor     ebx, ebx
0x18002bdd6  test    rdi, rdi
0x18002bdd9  jz      short loc_18002BDF9
0x18002bddb  mov     rcx, rdi; hMutex
0x18002bdde  call    cs:__imp_ReleaseMutex
0x18002bde5  nop     dword ptr [rax+rax+00h]
0x18002bdea  mov     rcx, [rbp+188h]; this
0x18002bdf1  test    eax, eax
0x18002bdf3  jz      loc_18002BE85
0x18002bdf9  test    rbx, rbx
0x18002bdfc  jz      short loc_18002BE18
0x18002bdfe  mov     rcx, rbx; hObject
0x18002be01  call    cs:__imp_CloseHandle
0x18002be08  nop     dword ptr [rax+rax+00h]
0x18002be0d  mov     rcx, [rbp+188h]; this
0x18002be14  test    eax, eax
0x18002be16  jz      short loc_18002BE41
0x18002be18  xor     eax, eax
0x18002be1a  mov     rcx, [rbp+180h+var_30]
0x18002be21  xor     rcx, rsp; StackCookie
0x18002be24  call    __security_check_cookie
0x18002be29  mov     rbx, [rsp+280h+arg_10]
0x18002be31  add     rsp, 260h
0x18002be38  pop     r15
0x18002be3a  pop     r14
0x18002be3c  pop     rdi
0x18002be3d  pop     rsi
0x18002be3e  pop     rbp
0x18002be3f  retn
0x18002be41  mov     edx, 0A0Bh; void *
0x18002be46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002be4c  mov     rcx, [rbp+188h]; this
0x18002be53  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002be59  mov     edx, 0A15h; void *
0x18002be5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002be64  mov     edx, 0A0Bh; void *
0x18002be69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002be6f  mov     edx, 0A15h; void *
0x18002be74  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002be7a  mov     edx, 0A0Bh; void *
0x18002be7f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002be85  mov     edx, 0A15h; void *
0x18002be8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
