# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800045b8`
- end: `0x180004980`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800055e4`

## callees

- `0x180002bc0`
- `0x18000354c`
- `0x1800045b8`
- `0x180004988`
- `0x180004c74`
- `0x1800052d8`
- `0x180005e58`
- `0x180006244`
- `0x180006c34`
- `0x180006d0c`
- `0x180007198`
- `0x1800071a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004825`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004895`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800046e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004825`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004895`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004651`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004651`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004630`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004630`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800045f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800045f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004836`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800046f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800047e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004836`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800048ab`

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
0x1800045b8  mov     [rsp-8+arg_10], rbx
0x1800045bd  push    rbp
0x1800045be  push    rsi
0x1800045bf  push    rdi
0x1800045c0  push    r14
0x1800045c2  push    r15
0x1800045c4  lea     rbp, [rsp-160h]
0x1800045cc  sub     rsp, 260h
0x1800045d3  mov     rax, cs:__security_cookie
0x1800045da  xor     rax, rsp
0x1800045dd  mov     [rbp+180h+var_30], rax
0x1800045e4  mov     r15, rdx
0x1800045e7  mov     qword ptr [rdx], 0
0x1800045ee  mov     rbx, rcx
0x1800045f1  call    cs:__imp_GetCurrentProcessId
0x1800045f7  mov     r14d, 78h ; 'x'
0x1800045fd  mov     [rsp+280h+var_258], rbx
0x180004602  mov     r9d, eax
0x180004605  mov     [rsp+280h+var_260], r14d; int
0x18000460a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004611  mov     edx, 104h; unsigned __int64
0x180004616  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000461b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004620  mov     r9d, 1F0001h; dwDesiredAccess
0x180004626  lea     rdx, [rsp+280h+Name]; lpName
0x18000462b  xor     r8d, r8d; dwFlags
0x18000462e  xor     ecx, ecx; lpMutexAttributes
0x180004630  call    cs:__imp_CreateMutexExW
0x180004636  mov     rbx, rax
0x180004639  test    rax, rax
0x18000463c  jnz     short loc_180004648
0x18000463e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004643  jmp     loc_1800048B7
0x180004648  xor     r8d, r8d; bAlertable
0x18000464b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000464e  mov     rcx, rbx; hHandle
0x180004651  call    cs:__imp_WaitForSingleObjectEx
0x180004657  cmp     eax, 102h
0x18000465c  jz      short loc_18000466E
0x18000465e  test    eax, 0FFFFFF7Fh
0x180004663  jnz     loc_1800048EF
0x180004669  mov     rdi, rbx
0x18000466c  jmp     short loc_180004670
0x18000466e  xor     edi, edi
0x180004670  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004675  mov     [rsp+280h+hObject], 0
0x18000467e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004683  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004688  mov     esi, eax
0x18000468a  test    eax, eax
0x18000468c  jns     short loc_18000470D
0x18000468e  mov     rcx, [rbp+188h]; this
0x180004695  lea     r8, aWil; "wil"
0x18000469c  mov     r9d, eax; char *
0x18000469f  mov     edx, 66h ; 'f'; void *
0x1800046a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046a9  mov     rcx, [rbp+188h]; this
0x1800046b0  lea     r8, aWil; "wil"
0x1800046b7  mov     r9d, esi; char *
0x1800046ba  mov     edx, 6Fh ; 'o'; void *
0x1800046bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046c4  mov     rcx, [rbp+188h]; this
0x1800046cb  lea     r8, aWil; "wil"
0x1800046d2  mov     r9d, esi; char *
0x1800046d5  mov     edx, 12Eh; void *
0x1800046da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046df  test    rdi, rdi
0x1800046e2  jz      short loc_1800046F5
0x1800046e4  mov     rcx, rdi; hMutex
0x1800046e7  call    cs:__imp_ReleaseMutex
0x1800046ed  test    eax, eax
0x1800046ef  jz      loc_1800048FC
0x1800046f5  mov     rcx, rbx; hObject
0x1800046f8  call    cs:__imp_CloseHandle
0x1800046fe  test    eax, eax
0x180004700  jz      loc_18000490E
0x180004706  mov     eax, esi
0x180004708  jmp     loc_1800048B7
0x18000470d  mov     rax, [rsp+280h+hObject]
0x180004712  lea     rcx, ds:0[rax*4]
0x18000471a  test    rcx, rcx
0x18000471d  jz      short loc_18000472D
0x18000471f  mov     [r15], rcx
0x180004722  mov     eax, [rcx]
0x180004724  inc     eax
0x180004726  mov     [rcx], eax
0x180004728  jmp     loc_18000488D
0x18000472d  mov     rdx, r14; dwBytes
0x180004730  mov     qword ptr [r15], 0
0x180004737  mov     ecx, 8; dwFlags
0x18000473c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004741  mov     rsi, rax
0x180004744  test    rax, rax
0x180004747  jnz     short loc_18000476F
0x180004749  mov     rcx, [rbp+188h]; this
0x180004750  lea     r8, aWil; "wil"
0x180004757  mov     r14d, 8007000Eh
0x18000475d  mov     edx, 14Bh; void *
0x180004762  mov     r9d, r14d; char *
0x180004765  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000476a  jmp     loc_180004802
0x18000476f  xorps   xmm0, xmm0
0x180004772  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004778  test    sil, 3
0x18000477c  jnz     loc_180004920
0x180004782  mov     r9, rsi
0x180004785  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000478a  shr     r9, 2; unsigned __int64
0x18000478e  lea     rcx, [rsp+280h+hObject]; this
0x180004793  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004798  mov     r14d, eax
0x18000479b  test    eax, eax
0x18000479d  jns     loc_180004849
0x1800047a3  mov     rcx, [rbp+188h]; this
0x1800047aa  lea     r8, aWil; "wil"
0x1800047b1  mov     r9d, eax; char *
0x1800047b4  mov     edx, 14Eh; void *
0x1800047b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047be  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800047c3  test    rcx, rcx
0x1800047c6  jz      short loc_1800047D6
0x1800047c8  call    cs:__imp_CloseHandle
0x1800047ce  test    eax, eax
0x1800047d0  jz      loc_180004926
0x1800047d6  mov     rcx, [rsp+280h+hObject]; hObject
0x1800047db  test    rcx, rcx
0x1800047de  jz      short loc_1800047EE
0x1800047e0  call    cs:__imp_CloseHandle
0x1800047e6  test    eax, eax
0x1800047e8  jz      loc_180004938
0x1800047ee  call    cs:__imp_GetProcessHeap
0x1800047f4  mov     r8, rsi; lpMem
0x1800047f7  xor     edx, edx; dwFlags
0x1800047f9  mov     rcx, rax; hHeap
0x1800047fc  call    cs:__imp_HeapFree
0x180004802  mov     rcx, [rbp+188h]; this
0x180004809  lea     r8, aWil; "wil"
0x180004810  mov     r9d, r14d; char *
0x180004813  mov     edx, 137h; void *
0x180004818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000481d  test    rdi, rdi
0x180004820  jz      short loc_180004833
0x180004822  mov     rcx, rdi; hMutex
0x180004825  call    cs:__imp_ReleaseMutex
0x18000482b  test    eax, eax
0x18000482d  jz      loc_18000494A
0x180004833  mov     rcx, rbx; hObject
0x180004836  call    cs:__imp_CloseHandle
0x18000483c  test    eax, eax
0x18000483e  jz      loc_18000495C
0x180004844  mov     eax, r14d
0x180004847  jmp     short loc_1800048B7
0x180004849  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000484e  xor     edx, edx; Val
0x180004850  mov     dword ptr [rsi], 1
0x180004856  lea     rcx, [rsi+22h]; void *
0x18000485a  mov     [rsi+8], rbx
0x18000485e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004863  lea     r8d, [rdx+56h]; Size
0x180004867  call    memset_0
0x18000486c  xor     edx, edx; Val
0x18000486e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004874  lea     rcx, [rsi+28h]; void *
0x180004878  mov     dword ptr [rsi+24h], 1
0x18000487f  lea     r8d, [rdx+50h]; Size
0x180004883  call    memset_0
0x180004888  xor     ebx, ebx
0x18000488a  mov     [r15], rsi
0x18000488d  test    rdi, rdi
0x180004890  jz      short loc_1800048A3
0x180004892  mov     rcx, rdi; hMutex
0x180004895  call    cs:__imp_ReleaseMutex
0x18000489b  test    eax, eax
0x18000489d  jz      loc_18000496E
0x1800048a3  test    rbx, rbx
0x1800048a6  jz      short loc_1800048B5
0x1800048a8  mov     rcx, rbx; hObject
0x1800048ab  call    cs:__imp_CloseHandle
0x1800048b1  test    eax, eax
0x1800048b3  jz      short loc_1800048DD
0x1800048b5  xor     eax, eax
0x1800048b7  mov     rcx, [rbp+180h+var_30]
0x1800048be  xor     rcx, rsp; StackCookie
0x1800048c1  call    __security_check_cookie
0x1800048c6  mov     rbx, [rsp+280h+arg_10]
0x1800048ce  add     rsp, 260h
0x1800048d5  pop     r15
0x1800048d7  pop     r14
0x1800048d9  pop     rdi
0x1800048da  pop     rsi
0x1800048db  pop     rbp
0x1800048dc  retn
0x1800048dd  mov     rcx, [rbp+188h]; this
0x1800048e4  mov     edx, 0A0Bh; void *
0x1800048e9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800048ef  mov     rcx, [rbp+188h]; this
0x1800048f6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800048fc  mov     rcx, [rbp+188h]; this
0x180004903  mov     edx, 0A15h; void *
0x180004908  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000490e  mov     rcx, [rbp+188h]; this
0x180004915  mov     edx, 0A0Bh; void *
0x18000491a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004920  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004926  mov     rcx, [rbp+188h]; this
0x18000492d  mov     edx, 0A0Bh; void *
0x180004932  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004938  mov     rcx, [rbp+188h]; this
0x18000493f  mov     edx, 0A0Bh; void *
0x180004944  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000494a  mov     rcx, [rbp+188h]; this
0x180004951  mov     edx, 0A15h; void *
0x180004956  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000495c  mov     rcx, [rbp+188h]; this
0x180004963  mov     edx, 0A0Bh; void *
0x180004968  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000496e  mov     rcx, [rbp+188h]; this
0x180004975  mov     edx, 0A15h; void *
0x18000497a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
