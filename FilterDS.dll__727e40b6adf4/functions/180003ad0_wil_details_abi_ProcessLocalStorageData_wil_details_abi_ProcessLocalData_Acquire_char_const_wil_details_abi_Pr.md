# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003ad0`
- end: `0x180003e98`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004c74`

## callees

- `0x180003ad0`
- `0x180003ea0`
- `0x180004198`
- `0x1800049d8`
- `0x1800055ac`
- `0x180005ca4`
- `0x1800064d4`
- `0x1800066cc`
- `0x180006ba4`
- `0x180006bb4`
- `0x180021822`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b48`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003b48`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003b69`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003bff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003dad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003b09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003c10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ce0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003dc3`

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
0x180003ad0  mov     [rsp-8+arg_10], rbx
0x180003ad5  push    rbp
0x180003ad6  push    rsi
0x180003ad7  push    rdi
0x180003ad8  push    r14
0x180003ada  push    r15
0x180003adc  lea     rbp, [rsp-160h]
0x180003ae4  sub     rsp, 260h
0x180003aeb  mov     rax, cs:__security_cookie
0x180003af2  xor     rax, rsp
0x180003af5  mov     [rbp+180h+var_30], rax
0x180003afc  mov     r15, rdx
0x180003aff  mov     qword ptr [rdx], 0
0x180003b06  mov     rbx, rcx
0x180003b09  call    cs:__imp_GetCurrentProcessId
0x180003b0f  mov     r14d, 78h ; 'x'
0x180003b15  mov     [rsp+280h+var_258], rbx
0x180003b1a  mov     r9d, eax
0x180003b1d  mov     [rsp+280h+var_260], r14d; int
0x180003b22  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003b29  mov     edx, 104h; unsigned __int64
0x180003b2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003b38  mov     r9d, 1F0001h; dwDesiredAccess
0x180003b3e  lea     rdx, [rsp+280h+Name]; lpName
0x180003b43  xor     r8d, r8d; dwFlags
0x180003b46  xor     ecx, ecx; lpMutexAttributes
0x180003b48  call    cs:__imp_CreateMutexExW
0x180003b4e  mov     rbx, rax
0x180003b51  test    rax, rax
0x180003b54  jnz     short loc_180003B60
0x180003b56  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003b5b  jmp     loc_180003DCF
0x180003b60  xor     r8d, r8d; bAlertable
0x180003b63  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003b66  mov     rcx, rbx; hHandle
0x180003b69  call    cs:__imp_WaitForSingleObjectEx
0x180003b6f  cmp     eax, 102h
0x180003b74  jz      short loc_180003B86
0x180003b76  test    eax, 0FFFFFF7Fh
0x180003b7b  jnz     loc_180003E07
0x180003b81  mov     rdi, rbx
0x180003b84  jmp     short loc_180003B88
0x180003b86  xor     edi, edi
0x180003b88  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003b8d  mov     [rsp+280h+hObject], 0
0x180003b96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003b9b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003ba0  mov     esi, eax
0x180003ba2  test    eax, eax
0x180003ba4  jns     short loc_180003C25
0x180003ba6  mov     rcx, [rbp+188h]; this
0x180003bad  lea     r8, aWil; "wil"
0x180003bb4  mov     r9d, eax; char *
0x180003bb7  mov     edx, 66h ; 'f'; void *
0x180003bbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bc1  mov     rcx, [rbp+188h]; this
0x180003bc8  lea     r8, aWil; "wil"
0x180003bcf  mov     r9d, esi; char *
0x180003bd2  mov     edx, 6Fh ; 'o'; void *
0x180003bd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bdc  mov     rcx, [rbp+188h]; this
0x180003be3  lea     r8, aWil; "wil"
0x180003bea  mov     r9d, esi; char *
0x180003bed  mov     edx, 12Eh; void *
0x180003bf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bf7  test    rdi, rdi
0x180003bfa  jz      short loc_180003C0D
0x180003bfc  mov     rcx, rdi; hMutex
0x180003bff  call    cs:__imp_ReleaseMutex
0x180003c05  test    eax, eax
0x180003c07  jz      loc_180003E14
0x180003c0d  mov     rcx, rbx; hObject
0x180003c10  call    cs:__imp_CloseHandle
0x180003c16  test    eax, eax
0x180003c18  jz      loc_180003E26
0x180003c1e  mov     eax, esi
0x180003c20  jmp     loc_180003DCF
0x180003c25  mov     rax, [rsp+280h+hObject]
0x180003c2a  lea     rcx, ds:0[rax*4]
0x180003c32  test    rcx, rcx
0x180003c35  jz      short loc_180003C45
0x180003c37  mov     [r15], rcx
0x180003c3a  mov     eax, [rcx]
0x180003c3c  inc     eax
0x180003c3e  mov     [rcx], eax
0x180003c40  jmp     loc_180003DA5
0x180003c45  mov     rdx, r14; dwBytes
0x180003c48  mov     qword ptr [r15], 0
0x180003c4f  mov     ecx, 8; dwFlags
0x180003c54  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003c59  mov     rsi, rax
0x180003c5c  test    rax, rax
0x180003c5f  jnz     short loc_180003C87
0x180003c61  mov     rcx, [rbp+188h]; this
0x180003c68  lea     r8, aWil; "wil"
0x180003c6f  mov     r14d, 8007000Eh
0x180003c75  mov     edx, 14Bh; void *
0x180003c7a  mov     r9d, r14d; char *
0x180003c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c82  jmp     loc_180003D1A
0x180003c87  xorps   xmm0, xmm0
0x180003c8a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003c90  test    sil, 3
0x180003c94  jnz     loc_180003E38
0x180003c9a  mov     r9, rsi
0x180003c9d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003ca2  shr     r9, 2; unsigned __int64
0x180003ca6  lea     rcx, [rsp+280h+hObject]; this
0x180003cab  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003cb0  mov     r14d, eax
0x180003cb3  test    eax, eax
0x180003cb5  jns     loc_180003D61
0x180003cbb  mov     rcx, [rbp+188h]; this
0x180003cc2  lea     r8, aWil; "wil"
0x180003cc9  mov     r9d, eax; char *
0x180003ccc  mov     edx, 14Eh; void *
0x180003cd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cd6  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003cdb  test    rcx, rcx
0x180003cde  jz      short loc_180003CEE
0x180003ce0  call    cs:__imp_CloseHandle
0x180003ce6  test    eax, eax
0x180003ce8  jz      loc_180003E3E
0x180003cee  mov     rcx, [rsp+280h+hObject]; hObject
0x180003cf3  test    rcx, rcx
0x180003cf6  jz      short loc_180003D06
0x180003cf8  call    cs:__imp_CloseHandle
0x180003cfe  test    eax, eax
0x180003d00  jz      loc_180003E50
0x180003d06  call    cs:__imp_GetProcessHeap
0x180003d0c  mov     r8, rsi; lpMem
0x180003d0f  xor     edx, edx; dwFlags
0x180003d11  mov     rcx, rax; hHeap
0x180003d14  call    cs:__imp_HeapFree
0x180003d1a  mov     rcx, [rbp+188h]; this
0x180003d21  lea     r8, aWil; "wil"
0x180003d28  mov     r9d, r14d; char *
0x180003d2b  mov     edx, 137h; void *
0x180003d30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d35  test    rdi, rdi
0x180003d38  jz      short loc_180003D4B
0x180003d3a  mov     rcx, rdi; hMutex
0x180003d3d  call    cs:__imp_ReleaseMutex
0x180003d43  test    eax, eax
0x180003d45  jz      loc_180003E62
0x180003d4b  mov     rcx, rbx; hObject
0x180003d4e  call    cs:__imp_CloseHandle
0x180003d54  test    eax, eax
0x180003d56  jz      loc_180003E74
0x180003d5c  mov     eax, r14d
0x180003d5f  jmp     short loc_180003DCF
0x180003d61  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003d66  xor     edx, edx; Val
0x180003d68  mov     dword ptr [rsi], 1
0x180003d6e  lea     rcx, [rsi+22h]; void *
0x180003d72  mov     [rsi+8], rbx
0x180003d76  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003d7b  lea     r8d, [rdx+56h]; Size
0x180003d7f  call    memset_0
0x180003d84  xor     edx, edx; Val
0x180003d86  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003d8c  lea     rcx, [rsi+28h]; void *
0x180003d90  mov     dword ptr [rsi+24h], 1
0x180003d97  lea     r8d, [rdx+50h]; Size
0x180003d9b  call    memset_0
0x180003da0  xor     ebx, ebx
0x180003da2  mov     [r15], rsi
0x180003da5  test    rdi, rdi
0x180003da8  jz      short loc_180003DBB
0x180003daa  mov     rcx, rdi; hMutex
0x180003dad  call    cs:__imp_ReleaseMutex
0x180003db3  test    eax, eax
0x180003db5  jz      loc_180003E86
0x180003dbb  test    rbx, rbx
0x180003dbe  jz      short loc_180003DCD
0x180003dc0  mov     rcx, rbx; hObject
0x180003dc3  call    cs:__imp_CloseHandle
0x180003dc9  test    eax, eax
0x180003dcb  jz      short loc_180003DF5
0x180003dcd  xor     eax, eax
0x180003dcf  mov     rcx, [rbp+180h+var_30]
0x180003dd6  xor     rcx, rsp; StackCookie
0x180003dd9  call    __security_check_cookie
0x180003dde  mov     rbx, [rsp+280h+arg_10]
0x180003de6  add     rsp, 260h
0x180003ded  pop     r15
0x180003def  pop     r14
0x180003df1  pop     rdi
0x180003df2  pop     rsi
0x180003df3  pop     rbp
0x180003df4  retn
0x180003df5  mov     rcx, [rbp+188h]; this
0x180003dfc  mov     edx, 0A0Bh; void *
0x180003e01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e07  mov     rcx, [rbp+188h]; this
0x180003e0e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003e14  mov     rcx, [rbp+188h]; this
0x180003e1b  mov     edx, 0A15h; void *
0x180003e20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e26  mov     rcx, [rbp+188h]; this
0x180003e2d  mov     edx, 0A0Bh; void *
0x180003e32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003e3e  mov     rcx, [rbp+188h]; this
0x180003e45  mov     edx, 0A0Bh; void *
0x180003e4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e50  mov     rcx, [rbp+188h]; this
0x180003e57  mov     edx, 0A0Bh; void *
0x180003e5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e62  mov     rcx, [rbp+188h]; this
0x180003e69  mov     edx, 0A15h; void *
0x180003e6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e74  mov     rcx, [rbp+188h]; this
0x180003e7b  mov     edx, 0A0Bh; void *
0x180003e80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003e86  mov     rcx, [rbp+188h]; this
0x180003e8d  mov     edx, 0A15h; void *
0x180003e92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
