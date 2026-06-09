# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800042e8`
- end: `0x18000468b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `931`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005364`

## callees

- `0x180002650`
- `0x1800032a4`
- `0x1800042e8`
- `0x180004694`
- `0x1800048d4`
- `0x1800050c8`
- `0x180005c44`
- `0x180006224`
- `0x180006bb0`
- `0x180006dbc`
- `0x18000716c`
- `0x18000717c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004402`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000452b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000459b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004402`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000452b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000459b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004360`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004360`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004381`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004381`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800044fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004509`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004321`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004321`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000453c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000453c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800045b1`

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
  bool v9; // dl
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // esi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x1800042e8  mov     [rsp-8+arg_10], rbx
0x1800042ed  push    rbp
0x1800042ee  push    rsi
0x1800042ef  push    rdi
0x1800042f0  push    r14
0x1800042f2  push    r15
0x1800042f4  lea     rbp, [rsp-160h]
0x1800042fc  sub     rsp, 260h
0x180004303  mov     rax, cs:__security_cookie
0x18000430a  xor     rax, rsp
0x18000430d  mov     [rbp+180h+var_30], rax
0x180004314  mov     r15, rdx
0x180004317  mov     qword ptr [rdx], 0
0x18000431e  mov     rbx, rcx
0x180004321  call    cs:__imp_GetCurrentProcessId
0x180004327  mov     r14d, 78h ; 'x'
0x18000432d  mov     [rsp+280h+var_258], rbx
0x180004332  mov     r9d, eax
0x180004335  mov     [rsp+280h+var_260], r14d; int
0x18000433a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004341  mov     edx, 104h; unsigned __int64
0x180004346  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000434b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004350  mov     r9d, 1F0001h; dwDesiredAccess
0x180004356  lea     rdx, [rsp+280h+Name]; lpName
0x18000435b  xor     r8d, r8d; dwFlags
0x18000435e  xor     ecx, ecx; lpMutexAttributes
0x180004360  call    cs:__imp_CreateMutexExW
0x180004366  mov     rbx, rax
0x180004369  test    rax, rax
0x18000436c  jnz     short loc_180004378
0x18000436e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004373  jmp     loc_1800045BD
0x180004378  xor     r8d, r8d; bAlertable
0x18000437b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000437e  mov     rcx, rbx; hHandle
0x180004381  call    cs:__imp_WaitForSingleObjectEx
0x180004387  cmp     eax, 102h
0x18000438c  jz      short loc_18000439E
0x18000438e  test    eax, 0FFFFFF7Fh
0x180004393  jnz     loc_1800045F5
0x180004399  mov     rdi, rbx
0x18000439c  jmp     short loc_1800043A0
0x18000439e  xor     edi, edi
0x1800043a0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800043a5  mov     [rsp+280h+hObject], 0
0x1800043ae  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800043b3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800043b8  mov     esi, eax
0x1800043ba  test    eax, eax
0x1800043bc  jns     short loc_180004428
0x1800043be  mov     rcx, [rbp+188h]; this
0x1800043c5  mov     r9d, eax; char *
0x1800043c8  mov     edx, 66h ; 'f'; void *
0x1800043cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043d2  mov     rcx, [rbp+188h]; this
0x1800043d9  mov     r9d, esi; char *
0x1800043dc  mov     edx, 6Fh ; 'o'; void *
0x1800043e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043e6  mov     rcx, [rbp+188h]; this
0x1800043ed  mov     r9d, esi; char *
0x1800043f0  mov     edx, 12Eh; void *
0x1800043f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800043fa  test    rdi, rdi
0x1800043fd  jz      short loc_180004410
0x1800043ff  mov     rcx, rdi; hMutex
0x180004402  call    cs:__imp_ReleaseMutex
0x180004408  test    eax, eax
0x18000440a  jz      loc_180004607
0x180004410  mov     rcx, rbx; hObject
0x180004413  call    cs:__imp_CloseHandle
0x180004419  test    eax, eax
0x18000441b  jz      loc_180004619
0x180004421  mov     eax, esi
0x180004423  jmp     loc_1800045BD
0x180004428  mov     rax, [rsp+280h+hObject]
0x18000442d  lea     rcx, ds:0[rax*4]
0x180004435  test    rcx, rcx
0x180004438  jz      short loc_180004448
0x18000443a  mov     [r15], rcx
0x18000443d  mov     eax, [rcx]
0x18000443f  inc     eax
0x180004441  mov     [rcx], eax
0x180004443  jmp     loc_180004593
0x180004448  mov     rdx, r14; dwBytes
0x18000444b  mov     qword ptr [r15], 0
0x180004452  mov     ecx, 8; dwFlags
0x180004457  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000445c  mov     rsi, rax
0x18000445f  test    rax, rax
0x180004462  jnz     short loc_180004483
0x180004464  mov     rcx, [rbp+188h]; this
0x18000446b  mov     r14d, 8007000Eh
0x180004471  mov     r9d, r14d; char *
0x180004474  mov     edx, 14Bh; void *
0x180004479  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000447e  jmp     loc_18000450F
0x180004483  xorps   xmm0, xmm0
0x180004486  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000448c  test    sil, 3
0x180004490  jnz     loc_18000462B
0x180004496  mov     r9, rsi
0x180004499  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000449e  shr     r9, 2; unsigned __int64
0x1800044a2  lea     rcx, [rsp+280h+hObject]; this
0x1800044a7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800044ac  mov     r14d, eax
0x1800044af  test    eax, eax
0x1800044b1  jns     loc_18000454F
0x1800044b7  mov     rcx, [rbp+188h]; this
0x1800044be  mov     r9d, eax; char *
0x1800044c1  mov     edx, 14Eh; void *
0x1800044c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800044cb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800044d0  test    rcx, rcx
0x1800044d3  jz      short loc_1800044E3
0x1800044d5  call    cs:__imp_CloseHandle
0x1800044db  test    eax, eax
0x1800044dd  jz      loc_180004631
0x1800044e3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800044e8  test    rcx, rcx
0x1800044eb  jz      short loc_1800044FB
0x1800044ed  call    cs:__imp_CloseHandle
0x1800044f3  test    eax, eax
0x1800044f5  jz      loc_180004643
0x1800044fb  call    cs:__imp_GetProcessHeap
0x180004501  mov     r8, rsi; lpMem
0x180004504  xor     edx, edx; dwFlags
0x180004506  mov     rcx, rax; hHeap
0x180004509  call    cs:__imp_HeapFree
0x18000450f  mov     rcx, [rbp+188h]; this
0x180004516  mov     r9d, r14d; char *
0x180004519  mov     edx, 137h; void *
0x18000451e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004523  test    rdi, rdi
0x180004526  jz      short loc_180004539
0x180004528  mov     rcx, rdi; hMutex
0x18000452b  call    cs:__imp_ReleaseMutex
0x180004531  test    eax, eax
0x180004533  jz      loc_180004655
0x180004539  mov     rcx, rbx; hObject
0x18000453c  call    cs:__imp_CloseHandle
0x180004542  test    eax, eax
0x180004544  jz      loc_180004667
0x18000454a  mov     eax, r14d
0x18000454d  jmp     short loc_1800045BD
0x18000454f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004554  xor     edx, edx; Val
0x180004556  mov     dword ptr [rsi], 1
0x18000455c  lea     rcx, [rsi+22h]; void *
0x180004560  mov     [rsi+8], rbx
0x180004564  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004569  lea     r8d, [rdx+56h]; Size
0x18000456d  call    memset_0
0x180004572  xor     edx, edx; Val
0x180004574  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000457a  lea     rcx, [rsi+28h]; void *
0x18000457e  mov     dword ptr [rsi+24h], 1
0x180004585  lea     r8d, [rdx+50h]; Size
0x180004589  call    memset_0
0x18000458e  xor     ebx, ebx
0x180004590  mov     [r15], rsi
0x180004593  test    rdi, rdi
0x180004596  jz      short loc_1800045A9
0x180004598  mov     rcx, rdi; hMutex
0x18000459b  call    cs:__imp_ReleaseMutex
0x1800045a1  test    eax, eax
0x1800045a3  jz      loc_180004679
0x1800045a9  test    rbx, rbx
0x1800045ac  jz      short loc_1800045BB
0x1800045ae  mov     rcx, rbx; hObject
0x1800045b1  call    cs:__imp_CloseHandle
0x1800045b7  test    eax, eax
0x1800045b9  jz      short loc_1800045E3
0x1800045bb  xor     eax, eax
0x1800045bd  mov     rcx, [rbp+180h+var_30]
0x1800045c4  xor     rcx, rsp; StackCookie
0x1800045c7  call    __security_check_cookie
0x1800045cc  mov     rbx, [rsp+280h+arg_10]
0x1800045d4  add     rsp, 260h
0x1800045db  pop     r15
0x1800045dd  pop     r14
0x1800045df  pop     rdi
0x1800045e0  pop     rsi
0x1800045e1  pop     rbp
0x1800045e2  retn
0x1800045e3  mov     rcx, [rbp+188h]; this
0x1800045ea  mov     edx, 0A0Bh; void *
0x1800045ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800045f5  mov     rcx, [rbp+188h]; this
0x1800045fc  mov     edx, 0E01h; void *
0x180004601  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004607  mov     rcx, [rbp+188h]; this
0x18000460e  mov     edx, 0A15h; void *
0x180004613  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004619  mov     rcx, [rbp+188h]; this
0x180004620  mov     edx, 0A0Bh; void *
0x180004625  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000462b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004631  mov     rcx, [rbp+188h]; this
0x180004638  mov     edx, 0A0Bh; void *
0x18000463d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004643  mov     rcx, [rbp+188h]; this
0x18000464a  mov     edx, 0A0Bh; void *
0x18000464f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004655  mov     rcx, [rbp+188h]; this
0x18000465c  mov     edx, 0A15h; void *
0x180004661  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004667  mov     rcx, [rbp+188h]; this
0x18000466e  mov     edx, 0A0Bh; void *
0x180004673  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004679  mov     rcx, [rbp+188h]; this
0x180004680  mov     edx, 0A15h; void *
0x180004685  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
