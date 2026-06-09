# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800048d8`
- end: `0x180004ca0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180005c54`

## callees

- `0x180002240`
- `0x180002db8`
- `0x1800048d8`
- `0x180004e7c`
- `0x180005194`
- `0x1800058a4`
- `0x1800065d8`
- `0x180006a14`
- `0x180007404`
- `0x1800075ac`
- `0x180007a48`
- `0x180007a58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004971`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004971`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004950`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004950`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004bb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004a07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004b45`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004bb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ae8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004ae8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcb`

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
0x1800048d8  mov     [rsp-8+arg_10], rbx
0x1800048dd  push    rbp
0x1800048de  push    rsi
0x1800048df  push    rdi
0x1800048e0  push    r14
0x1800048e2  push    r15
0x1800048e4  lea     rbp, [rsp-160h]
0x1800048ec  sub     rsp, 260h
0x1800048f3  mov     rax, cs:__security_cookie
0x1800048fa  xor     rax, rsp
0x1800048fd  mov     [rbp+180h+var_30], rax
0x180004904  mov     r15, rdx
0x180004907  mov     qword ptr [rdx], 0
0x18000490e  mov     rbx, rcx
0x180004911  call    cs:__imp_GetCurrentProcessId
0x180004917  mov     r14d, 78h ; 'x'
0x18000491d  mov     [rsp+280h+var_258], rbx
0x180004922  mov     r9d, eax
0x180004925  mov     [rsp+280h+var_260], r14d; int
0x18000492a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004931  mov     edx, 104h; unsigned __int64
0x180004936  lea     rcx, [rsp+280h+Name]; Buffer
0x18000493b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004940  mov     r9d, 1F0001h; dwDesiredAccess
0x180004946  lea     rdx, [rsp+280h+Name]; lpName
0x18000494b  xor     r8d, r8d; dwFlags
0x18000494e  xor     ecx, ecx; lpMutexAttributes
0x180004950  call    cs:__imp_CreateMutexExW
0x180004956  mov     rbx, rax
0x180004959  test    rax, rax
0x18000495c  jnz     short loc_180004968
0x18000495e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004963  jmp     loc_180004BD7
0x180004968  xor     r8d, r8d; bAlertable
0x18000496b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000496e  mov     rcx, rbx; hHandle
0x180004971  call    cs:__imp_WaitForSingleObjectEx
0x180004977  cmp     eax, 102h
0x18000497c  jz      short loc_18000498E
0x18000497e  test    eax, 0FFFFFF7Fh
0x180004983  jnz     loc_180004C0F
0x180004989  mov     rdi, rbx
0x18000498c  jmp     short loc_180004990
0x18000498e  xor     edi, edi
0x180004990  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004995  mov     [rsp+280h+hObject], 0
0x18000499e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800049a3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800049a8  mov     esi, eax
0x1800049aa  test    eax, eax
0x1800049ac  jns     short loc_180004A2D
0x1800049ae  mov     rcx, [rbp+188h]; this
0x1800049b5  lea     r8, aWil; "wil"
0x1800049bc  mov     r9d, eax; char *
0x1800049bf  mov     edx, 66h ; 'f'; void *
0x1800049c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049c9  mov     rcx, [rbp+188h]; this
0x1800049d0  lea     r8, aWil; "wil"
0x1800049d7  mov     r9d, esi; char *
0x1800049da  mov     edx, 6Fh ; 'o'; void *
0x1800049df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049e4  mov     rcx, [rbp+188h]; this
0x1800049eb  lea     r8, aWil; "wil"
0x1800049f2  mov     r9d, esi; char *
0x1800049f5  mov     edx, 12Eh; void *
0x1800049fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800049ff  test    rdi, rdi
0x180004a02  jz      short loc_180004A15
0x180004a04  mov     rcx, rdi; hMutex
0x180004a07  call    cs:__imp_ReleaseMutex
0x180004a0d  test    eax, eax
0x180004a0f  jz      loc_180004C1C
0x180004a15  mov     rcx, rbx; hObject
0x180004a18  call    cs:__imp_CloseHandle
0x180004a1e  test    eax, eax
0x180004a20  jz      loc_180004C2E
0x180004a26  mov     eax, esi
0x180004a28  jmp     loc_180004BD7
0x180004a2d  mov     rax, [rsp+280h+hObject]
0x180004a32  lea     rcx, ds:0[rax*4]
0x180004a3a  test    rcx, rcx
0x180004a3d  jz      short loc_180004A4D
0x180004a3f  mov     [r15], rcx
0x180004a42  mov     eax, [rcx]
0x180004a44  inc     eax
0x180004a46  mov     [rcx], eax
0x180004a48  jmp     loc_180004BAD
0x180004a4d  mov     rdx, r14; dwBytes
0x180004a50  mov     qword ptr [r15], 0
0x180004a57  mov     ecx, 8; dwFlags
0x180004a5c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004a61  mov     rsi, rax
0x180004a64  test    rax, rax
0x180004a67  jnz     short loc_180004A8F
0x180004a69  mov     rcx, [rbp+188h]; this
0x180004a70  lea     r8, aWil; "wil"
0x180004a77  mov     r14d, 8007000Eh
0x180004a7d  mov     edx, 14Bh; void *
0x180004a82  mov     r9d, r14d; char *
0x180004a85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a8a  jmp     loc_180004B22
0x180004a8f  xorps   xmm0, xmm0
0x180004a92  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004a98  test    sil, 3
0x180004a9c  jnz     loc_180004C40
0x180004aa2  mov     r9, rsi
0x180004aa5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004aaa  shr     r9, 2; unsigned __int64
0x180004aae  lea     rcx, [rsp+280h+hObject]; this
0x180004ab3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004ab8  mov     r14d, eax
0x180004abb  test    eax, eax
0x180004abd  jns     loc_180004B69
0x180004ac3  mov     rcx, [rbp+188h]; this
0x180004aca  lea     r8, aWil; "wil"
0x180004ad1  mov     r9d, eax; char *
0x180004ad4  mov     edx, 14Eh; void *
0x180004ad9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004ade  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004ae3  test    rcx, rcx
0x180004ae6  jz      short loc_180004AF6
0x180004ae8  call    cs:__imp_CloseHandle
0x180004aee  test    eax, eax
0x180004af0  jz      loc_180004C46
0x180004af6  mov     rcx, [rsp+280h+hObject]; hObject
0x180004afb  test    rcx, rcx
0x180004afe  jz      short loc_180004B0E
0x180004b00  call    cs:__imp_CloseHandle
0x180004b06  test    eax, eax
0x180004b08  jz      loc_180004C58
0x180004b0e  call    cs:__imp_GetProcessHeap
0x180004b14  mov     r8, rsi; lpMem
0x180004b17  xor     edx, edx; dwFlags
0x180004b19  mov     rcx, rax; hHeap
0x180004b1c  call    cs:__imp_HeapFree
0x180004b22  mov     rcx, [rbp+188h]; this
0x180004b29  lea     r8, aWil; "wil"
0x180004b30  mov     r9d, r14d; char *
0x180004b33  mov     edx, 137h; void *
0x180004b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004b3d  test    rdi, rdi
0x180004b40  jz      short loc_180004B53
0x180004b42  mov     rcx, rdi; hMutex
0x180004b45  call    cs:__imp_ReleaseMutex
0x180004b4b  test    eax, eax
0x180004b4d  jz      loc_180004C6A
0x180004b53  mov     rcx, rbx; hObject
0x180004b56  call    cs:__imp_CloseHandle
0x180004b5c  test    eax, eax
0x180004b5e  jz      loc_180004C7C
0x180004b64  mov     eax, r14d
0x180004b67  jmp     short loc_180004BD7
0x180004b69  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004b6e  xor     edx, edx; Val
0x180004b70  mov     dword ptr [rsi], 1
0x180004b76  lea     rcx, [rsi+22h]; void *
0x180004b7a  mov     [rsi+8], rbx
0x180004b7e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004b83  lea     r8d, [rdx+56h]; Size
0x180004b87  call    memset_0
0x180004b8c  xor     edx, edx; Val
0x180004b8e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004b94  lea     rcx, [rsi+28h]; void *
0x180004b98  mov     dword ptr [rsi+24h], 1
0x180004b9f  lea     r8d, [rdx+50h]; Size
0x180004ba3  call    memset_0
0x180004ba8  xor     ebx, ebx
0x180004baa  mov     [r15], rsi
0x180004bad  test    rdi, rdi
0x180004bb0  jz      short loc_180004BC3
0x180004bb2  mov     rcx, rdi; hMutex
0x180004bb5  call    cs:__imp_ReleaseMutex
0x180004bbb  test    eax, eax
0x180004bbd  jz      loc_180004C8E
0x180004bc3  test    rbx, rbx
0x180004bc6  jz      short loc_180004BD5
0x180004bc8  mov     rcx, rbx; hObject
0x180004bcb  call    cs:__imp_CloseHandle
0x180004bd1  test    eax, eax
0x180004bd3  jz      short loc_180004BFD
0x180004bd5  xor     eax, eax
0x180004bd7  mov     rcx, [rbp+180h+var_30]
0x180004bde  xor     rcx, rsp; StackCookie
0x180004be1  call    __security_check_cookie
0x180004be6  mov     rbx, [rsp+280h+arg_10]
0x180004bee  add     rsp, 260h
0x180004bf5  pop     r15
0x180004bf7  pop     r14
0x180004bf9  pop     rdi
0x180004bfa  pop     rsi
0x180004bfb  pop     rbp
0x180004bfc  retn
0x180004bfd  mov     rcx, [rbp+188h]; this
0x180004c04  mov     edx, 0A0Bh; void *
0x180004c09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c0f  mov     rcx, [rbp+188h]; this
0x180004c16  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004c1c  mov     rcx, [rbp+188h]; this
0x180004c23  mov     edx, 0A15h; void *
0x180004c28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c2e  mov     rcx, [rbp+188h]; this
0x180004c35  mov     edx, 0A0Bh; void *
0x180004c3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c40  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004c46  mov     rcx, [rbp+188h]; this
0x180004c4d  mov     edx, 0A0Bh; void *
0x180004c52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c58  mov     rcx, [rbp+188h]; this
0x180004c5f  mov     edx, 0A0Bh; void *
0x180004c64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c6a  mov     rcx, [rbp+188h]; this
0x180004c71  mov     edx, 0A15h; void *
0x180004c76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c7c  mov     rcx, [rbp+188h]; this
0x180004c83  mov     edx, 0A0Bh; void *
0x180004c88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c8e  mov     rcx, [rbp+188h]; this
0x180004c95  mov     edx, 0A15h; void *
0x180004c9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
