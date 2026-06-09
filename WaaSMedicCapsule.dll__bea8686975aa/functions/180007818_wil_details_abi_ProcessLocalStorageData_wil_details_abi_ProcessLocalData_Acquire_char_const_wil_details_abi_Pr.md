# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007818`
- end: `0x180007be0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000897c`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180007818`
- `0x180007be8`
- `0x180007f18`
- `0x180008578`
- `0x180009664`
- `0x180009a54`
- `0x18000a5d0`
- `0x18000a6ac`
- `0x18000ab38`
- `0x18000ab48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007947`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a85`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007af5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007947`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007a85`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007af5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800078b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800078b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007890`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007890`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007851`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007958`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007958`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b0b`

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
0x180007818  mov     [rsp-8+arg_10], rbx
0x18000781d  push    rbp
0x18000781e  push    rsi
0x18000781f  push    rdi
0x180007820  push    r14
0x180007822  push    r15
0x180007824  lea     rbp, [rsp-160h]
0x18000782c  sub     rsp, 260h
0x180007833  mov     rax, cs:__security_cookie
0x18000783a  xor     rax, rsp
0x18000783d  mov     [rbp+180h+var_30], rax
0x180007844  mov     r15, rdx
0x180007847  mov     qword ptr [rdx], 0
0x18000784e  mov     rbx, rcx
0x180007851  call    cs:__imp_GetCurrentProcessId
0x180007857  mov     r14d, 78h ; 'x'
0x18000785d  mov     [rsp+280h+var_258], rbx
0x180007862  mov     r9d, eax
0x180007865  mov     [rsp+280h+var_260], r14d; int
0x18000786a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007871  mov     edx, 104h; unsigned __int64
0x180007876  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000787b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007880  mov     r9d, 1F0001h; dwDesiredAccess
0x180007886  lea     rdx, [rsp+280h+Name]; lpName
0x18000788b  xor     r8d, r8d; dwFlags
0x18000788e  xor     ecx, ecx; lpMutexAttributes
0x180007890  call    cs:__imp_CreateMutexExW
0x180007896  mov     rbx, rax
0x180007899  test    rax, rax
0x18000789c  jnz     short loc_1800078A8
0x18000789e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800078a3  jmp     loc_180007B17
0x1800078a8  xor     r8d, r8d; bAlertable
0x1800078ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800078ae  mov     rcx, rbx; hHandle
0x1800078b1  call    cs:__imp_WaitForSingleObjectEx
0x1800078b7  cmp     eax, 102h
0x1800078bc  jz      short loc_1800078CE
0x1800078be  test    eax, 0FFFFFF7Fh
0x1800078c3  jnz     loc_180007B4F
0x1800078c9  mov     rdi, rbx
0x1800078cc  jmp     short loc_1800078D0
0x1800078ce  xor     edi, edi
0x1800078d0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800078d5  mov     [rsp+280h+hObject], 0
0x1800078de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800078e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800078e8  mov     esi, eax
0x1800078ea  test    eax, eax
0x1800078ec  jns     short loc_18000796D
0x1800078ee  mov     rcx, [rbp+188h]; this
0x1800078f5  lea     r8, aWil; "wil"
0x1800078fc  mov     r9d, eax; char *
0x1800078ff  mov     edx, 66h ; 'f'; void *
0x180007904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007909  mov     rcx, [rbp+188h]; this
0x180007910  lea     r8, aWil; "wil"
0x180007917  mov     r9d, esi; char *
0x18000791a  mov     edx, 6Fh ; 'o'; void *
0x18000791f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007924  mov     rcx, [rbp+188h]; this
0x18000792b  lea     r8, aWil; "wil"
0x180007932  mov     r9d, esi; char *
0x180007935  mov     edx, 12Eh; void *
0x18000793a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000793f  test    rdi, rdi
0x180007942  jz      short loc_180007955
0x180007944  mov     rcx, rdi; hMutex
0x180007947  call    cs:__imp_ReleaseMutex
0x18000794d  test    eax, eax
0x18000794f  jz      loc_180007B5C
0x180007955  mov     rcx, rbx; hObject
0x180007958  call    cs:__imp_CloseHandle
0x18000795e  test    eax, eax
0x180007960  jz      loc_180007B6E
0x180007966  mov     eax, esi
0x180007968  jmp     loc_180007B17
0x18000796d  mov     rax, [rsp+280h+hObject]
0x180007972  lea     rcx, ds:0[rax*4]
0x18000797a  test    rcx, rcx
0x18000797d  jz      short loc_18000798D
0x18000797f  mov     [r15], rcx
0x180007982  mov     eax, [rcx]
0x180007984  inc     eax
0x180007986  mov     [rcx], eax
0x180007988  jmp     loc_180007AED
0x18000798d  mov     rdx, r14; dwBytes
0x180007990  mov     qword ptr [r15], 0
0x180007997  mov     ecx, 8; dwFlags
0x18000799c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800079a1  mov     rsi, rax
0x1800079a4  test    rax, rax
0x1800079a7  jnz     short loc_1800079CF
0x1800079a9  mov     rcx, [rbp+188h]; this
0x1800079b0  lea     r8, aWil; "wil"
0x1800079b7  mov     r14d, 8007000Eh
0x1800079bd  mov     edx, 14Bh; void *
0x1800079c2  mov     r9d, r14d; char *
0x1800079c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079ca  jmp     loc_180007A62
0x1800079cf  xorps   xmm0, xmm0
0x1800079d2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800079d8  test    sil, 3
0x1800079dc  jnz     loc_180007B80
0x1800079e2  mov     r9, rsi
0x1800079e5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800079ea  shr     r9, 2; unsigned __int64
0x1800079ee  lea     rcx, [rsp+280h+hObject]; this
0x1800079f3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800079f8  mov     r14d, eax
0x1800079fb  test    eax, eax
0x1800079fd  jns     loc_180007AA9
0x180007a03  mov     rcx, [rbp+188h]; this
0x180007a0a  lea     r8, aWil; "wil"
0x180007a11  mov     r9d, eax; char *
0x180007a14  mov     edx, 14Eh; void *
0x180007a19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a1e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007a23  test    rcx, rcx
0x180007a26  jz      short loc_180007A36
0x180007a28  call    cs:__imp_CloseHandle
0x180007a2e  test    eax, eax
0x180007a30  jz      loc_180007B86
0x180007a36  mov     rcx, [rsp+280h+hObject]; hObject
0x180007a3b  test    rcx, rcx
0x180007a3e  jz      short loc_180007A4E
0x180007a40  call    cs:__imp_CloseHandle
0x180007a46  test    eax, eax
0x180007a48  jz      loc_180007B98
0x180007a4e  call    cs:__imp_GetProcessHeap
0x180007a54  mov     r8, rsi; lpMem
0x180007a57  xor     edx, edx; dwFlags
0x180007a59  mov     rcx, rax; hHeap
0x180007a5c  call    cs:__imp_HeapFree
0x180007a62  mov     rcx, [rbp+188h]; this
0x180007a69  lea     r8, aWil; "wil"
0x180007a70  mov     r9d, r14d; char *
0x180007a73  mov     edx, 137h; void *
0x180007a78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a7d  test    rdi, rdi
0x180007a80  jz      short loc_180007A93
0x180007a82  mov     rcx, rdi; hMutex
0x180007a85  call    cs:__imp_ReleaseMutex
0x180007a8b  test    eax, eax
0x180007a8d  jz      loc_180007BAA
0x180007a93  mov     rcx, rbx; hObject
0x180007a96  call    cs:__imp_CloseHandle
0x180007a9c  test    eax, eax
0x180007a9e  jz      loc_180007BBC
0x180007aa4  mov     eax, r14d
0x180007aa7  jmp     short loc_180007B17
0x180007aa9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180007aae  xor     edx, edx; Val
0x180007ab0  mov     dword ptr [rsi], 1
0x180007ab6  lea     rcx, [rsi+22h]; void *
0x180007aba  mov     [rsi+8], rbx
0x180007abe  movdqu  xmmword ptr [rsi+10h], xmm0
0x180007ac3  lea     r8d, [rdx+56h]; Size
0x180007ac7  call    memset_0
0x180007acc  xor     edx, edx; Val
0x180007ace  mov     word ptr [rsi+20h], 58h ; 'X'
0x180007ad4  lea     rcx, [rsi+28h]; void *
0x180007ad8  mov     dword ptr [rsi+24h], 1
0x180007adf  lea     r8d, [rdx+50h]; Size
0x180007ae3  call    memset_0
0x180007ae8  xor     ebx, ebx
0x180007aea  mov     [r15], rsi
0x180007aed  test    rdi, rdi
0x180007af0  jz      short loc_180007B03
0x180007af2  mov     rcx, rdi; hMutex
0x180007af5  call    cs:__imp_ReleaseMutex
0x180007afb  test    eax, eax
0x180007afd  jz      loc_180007BCE
0x180007b03  test    rbx, rbx
0x180007b06  jz      short loc_180007B15
0x180007b08  mov     rcx, rbx; hObject
0x180007b0b  call    cs:__imp_CloseHandle
0x180007b11  test    eax, eax
0x180007b13  jz      short loc_180007B3D
0x180007b15  xor     eax, eax
0x180007b17  mov     rcx, [rbp+180h+var_30]
0x180007b1e  xor     rcx, rsp; StackCookie
0x180007b21  call    __security_check_cookie
0x180007b26  mov     rbx, [rsp+280h+arg_10]
0x180007b2e  add     rsp, 260h
0x180007b35  pop     r15
0x180007b37  pop     r14
0x180007b39  pop     rdi
0x180007b3a  pop     rsi
0x180007b3b  pop     rbp
0x180007b3c  retn
0x180007b3d  mov     rcx, [rbp+188h]; this
0x180007b44  mov     edx, 0A0Bh; void *
0x180007b49  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b4f  mov     rcx, [rbp+188h]; this
0x180007b56  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007b5c  mov     rcx, [rbp+188h]; this
0x180007b63  mov     edx, 0A15h; void *
0x180007b68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b6e  mov     rcx, [rbp+188h]; this
0x180007b75  mov     edx, 0A0Bh; void *
0x180007b7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b80  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007b86  mov     rcx, [rbp+188h]; this
0x180007b8d  mov     edx, 0A0Bh; void *
0x180007b92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007b98  mov     rcx, [rbp+188h]; this
0x180007b9f  mov     edx, 0A0Bh; void *
0x180007ba4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007baa  mov     rcx, [rbp+188h]; this
0x180007bb1  mov     edx, 0A15h; void *
0x180007bb6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bbc  mov     rcx, [rbp+188h]; this
0x180007bc3  mov     edx, 0A0Bh; void *
0x180007bc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007bce  mov     rcx, [rbp+188h]; this
0x180007bd5  mov     edx, 0A15h; void *
0x180007bda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
