# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180028a60`
- end: `0x180028e28`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18002adb4`

## callees

- `0x1800268ef`
- `0x180028a60`
- `0x180029264`
- `0x180029bd4`
- `0x18002aaa8`
- `0x18002bdbc`
- `0x18002dcd4`
- `0x18002edf0`
- `0x18002f1fc`
- `0x18002febc`
- `0x18002fecc`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028cde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028cde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028a99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180028a99`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028b8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028ccd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028d3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028b8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028ccd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028d3d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028ad8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180028ad8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180028af9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180028af9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028ca4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028ca4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028c96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028c96`

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
0x180028a60  mov     [rsp-8+arg_10], rbx
0x180028a65  push    rbp
0x180028a66  push    rsi
0x180028a67  push    rdi
0x180028a68  push    r14
0x180028a6a  push    r15
0x180028a6c  lea     rbp, [rsp-160h]
0x180028a74  sub     rsp, 260h
0x180028a7b  mov     rax, cs:__security_cookie
0x180028a82  xor     rax, rsp
0x180028a85  mov     [rbp+180h+var_30], rax
0x180028a8c  mov     r15, rdx
0x180028a8f  mov     qword ptr [rdx], 0
0x180028a96  mov     rbx, rcx
0x180028a99  call    cs:__imp_GetCurrentProcessId
0x180028a9f  mov     r14d, 78h ; 'x'
0x180028aa5  mov     [rsp+280h+var_258], rbx
0x180028aaa  mov     r9d, eax
0x180028aad  mov     [rsp+280h+var_260], r14d; int
0x180028ab2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180028ab9  mov     edx, 104h; unsigned __int64
0x180028abe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180028ac3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028ac8  mov     r9d, 1F0001h; dwDesiredAccess
0x180028ace  lea     rdx, [rsp+280h+Name]; lpName
0x180028ad3  xor     r8d, r8d; dwFlags
0x180028ad6  xor     ecx, ecx; lpMutexAttributes
0x180028ad8  call    cs:__imp_CreateMutexExW
0x180028ade  mov     rbx, rax
0x180028ae1  test    rax, rax
0x180028ae4  jnz     short loc_180028AF0
0x180028ae6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180028aeb  jmp     loc_180028D5F
0x180028af0  xor     r8d, r8d; bAlertable
0x180028af3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180028af6  mov     rcx, rbx; hHandle
0x180028af9  call    cs:__imp_WaitForSingleObjectEx
0x180028aff  cmp     eax, 102h
0x180028b04  jz      short loc_180028B16
0x180028b06  test    eax, 0FFFFFF7Fh
0x180028b0b  jnz     loc_180028D97
0x180028b11  mov     rdi, rbx
0x180028b14  jmp     short loc_180028B18
0x180028b16  xor     edi, edi
0x180028b18  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180028b1d  mov     [rsp+280h+hObject], 0
0x180028b26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180028b2b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180028b30  mov     esi, eax
0x180028b32  test    eax, eax
0x180028b34  jns     short loc_180028BB5
0x180028b36  mov     rcx, [rbp+188h]; this
0x180028b3d  lea     r8, aWil; "wil"
0x180028b44  mov     r9d, eax; char *
0x180028b47  mov     edx, 66h ; 'f'; void *
0x180028b4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b51  mov     rcx, [rbp+188h]; this
0x180028b58  lea     r8, aWil; "wil"
0x180028b5f  mov     r9d, esi; char *
0x180028b62  mov     edx, 6Fh ; 'o'; void *
0x180028b67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b6c  mov     rcx, [rbp+188h]; this
0x180028b73  lea     r8, aWil; "wil"
0x180028b7a  mov     r9d, esi; char *
0x180028b7d  mov     edx, 12Eh; void *
0x180028b82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b87  test    rdi, rdi
0x180028b8a  jz      short loc_180028B9D
0x180028b8c  mov     rcx, rdi; hMutex
0x180028b8f  call    cs:__imp_ReleaseMutex
0x180028b95  test    eax, eax
0x180028b97  jz      loc_180028DA4
0x180028b9d  mov     rcx, rbx; hObject
0x180028ba0  call    cs:__imp_CloseHandle
0x180028ba6  test    eax, eax
0x180028ba8  jz      loc_180028DB6
0x180028bae  mov     eax, esi
0x180028bb0  jmp     loc_180028D5F
0x180028bb5  mov     rax, [rsp+280h+hObject]
0x180028bba  lea     rcx, ds:0[rax*4]
0x180028bc2  test    rcx, rcx
0x180028bc5  jz      short loc_180028BD5
0x180028bc7  mov     [r15], rcx
0x180028bca  mov     eax, [rcx]
0x180028bcc  inc     eax
0x180028bce  mov     [rcx], eax
0x180028bd0  jmp     loc_180028D35
0x180028bd5  mov     rdx, r14; dwBytes
0x180028bd8  mov     qword ptr [r15], 0
0x180028bdf  mov     ecx, 8; dwFlags
0x180028be4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180028be9  mov     rsi, rax
0x180028bec  test    rax, rax
0x180028bef  jnz     short loc_180028C17
0x180028bf1  mov     rcx, [rbp+188h]; this
0x180028bf8  lea     r8, aWil; "wil"
0x180028bff  mov     r14d, 8007000Eh
0x180028c05  mov     edx, 14Bh; void *
0x180028c0a  mov     r9d, r14d; char *
0x180028c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c12  jmp     loc_180028CAA
0x180028c17  xorps   xmm0, xmm0
0x180028c1a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180028c20  test    sil, 3
0x180028c24  jnz     loc_180028DC8
0x180028c2a  mov     r9, rsi
0x180028c2d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180028c32  shr     r9, 2; unsigned __int64
0x180028c36  lea     rcx, [rsp+280h+hObject]; this
0x180028c3b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180028c40  mov     r14d, eax
0x180028c43  test    eax, eax
0x180028c45  jns     loc_180028CF1
0x180028c4b  mov     rcx, [rbp+188h]; this
0x180028c52  lea     r8, aWil; "wil"
0x180028c59  mov     r9d, eax; char *
0x180028c5c  mov     edx, 14Eh; void *
0x180028c61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028c66  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180028c6b  test    rcx, rcx
0x180028c6e  jz      short loc_180028C7E
0x180028c70  call    cs:__imp_CloseHandle
0x180028c76  test    eax, eax
0x180028c78  jz      loc_180028DCE
0x180028c7e  mov     rcx, [rsp+280h+hObject]; hObject
0x180028c83  test    rcx, rcx
0x180028c86  jz      short loc_180028C96
0x180028c88  call    cs:__imp_CloseHandle
0x180028c8e  test    eax, eax
0x180028c90  jz      loc_180028DE0
0x180028c96  call    cs:__imp_GetProcessHeap
0x180028c9c  mov     r8, rsi; lpMem
0x180028c9f  xor     edx, edx; dwFlags
0x180028ca1  mov     rcx, rax; hHeap
0x180028ca4  call    cs:__imp_HeapFree
0x180028caa  mov     rcx, [rbp+188h]; this
0x180028cb1  lea     r8, aWil; "wil"
0x180028cb8  mov     r9d, r14d; char *
0x180028cbb  mov     edx, 137h; void *
0x180028cc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028cc5  test    rdi, rdi
0x180028cc8  jz      short loc_180028CDB
0x180028cca  mov     rcx, rdi; hMutex
0x180028ccd  call    cs:__imp_ReleaseMutex
0x180028cd3  test    eax, eax
0x180028cd5  jz      loc_180028DF2
0x180028cdb  mov     rcx, rbx; hObject
0x180028cde  call    cs:__imp_CloseHandle
0x180028ce4  test    eax, eax
0x180028ce6  jz      loc_180028E04
0x180028cec  mov     eax, r14d
0x180028cef  jmp     short loc_180028D5F
0x180028cf1  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180028cf6  xor     edx, edx; Val
0x180028cf8  mov     dword ptr [rsi], 1
0x180028cfe  lea     rcx, [rsi+22h]; void *
0x180028d02  mov     [rsi+8], rbx
0x180028d06  movdqu  xmmword ptr [rsi+10h], xmm0
0x180028d0b  lea     r8d, [rdx+56h]; Size
0x180028d0f  call    memset_0
0x180028d14  xor     edx, edx; Val
0x180028d16  mov     word ptr [rsi+20h], 58h ; 'X'
0x180028d1c  lea     rcx, [rsi+28h]; void *
0x180028d20  mov     dword ptr [rsi+24h], 1
0x180028d27  lea     r8d, [rdx+50h]; Size
0x180028d2b  call    memset_0
0x180028d30  xor     ebx, ebx
0x180028d32  mov     [r15], rsi
0x180028d35  test    rdi, rdi
0x180028d38  jz      short loc_180028D4B
0x180028d3a  mov     rcx, rdi; hMutex
0x180028d3d  call    cs:__imp_ReleaseMutex
0x180028d43  test    eax, eax
0x180028d45  jz      loc_180028E16
0x180028d4b  test    rbx, rbx
0x180028d4e  jz      short loc_180028D5D
0x180028d50  mov     rcx, rbx; hObject
0x180028d53  call    cs:__imp_CloseHandle
0x180028d59  test    eax, eax
0x180028d5b  jz      short loc_180028D85
0x180028d5d  xor     eax, eax
0x180028d5f  mov     rcx, [rbp+180h+var_30]
0x180028d66  xor     rcx, rsp; StackCookie
0x180028d69  call    __security_check_cookie
0x180028d6e  mov     rbx, [rsp+280h+arg_10]
0x180028d76  add     rsp, 260h
0x180028d7d  pop     r15
0x180028d7f  pop     r14
0x180028d81  pop     rdi
0x180028d82  pop     rsi
0x180028d83  pop     rbp
0x180028d84  retn
0x180028d85  mov     rcx, [rbp+188h]; this
0x180028d8c  mov     edx, 0A0Bh; void *
0x180028d91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028d97  mov     rcx, [rbp+188h]; this
0x180028d9e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180028da4  mov     rcx, [rbp+188h]; this
0x180028dab  mov     edx, 0A15h; void *
0x180028db0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028db6  mov     rcx, [rbp+188h]; this
0x180028dbd  mov     edx, 0A0Bh; void *
0x180028dc2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028dc8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180028dce  mov     rcx, [rbp+188h]; this
0x180028dd5  mov     edx, 0A0Bh; void *
0x180028dda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028de0  mov     rcx, [rbp+188h]; this
0x180028de7  mov     edx, 0A0Bh; void *
0x180028dec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028df2  mov     rcx, [rbp+188h]; this
0x180028df9  mov     edx, 0A15h; void *
0x180028dfe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028e04  mov     rcx, [rbp+188h]; this
0x180028e0b  mov     edx, 0A0Bh; void *
0x180028e10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180028e16  mov     rcx, [rbp+188h]; this
0x180028e1d  mov     edx, 0A15h; void *
0x180028e22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
