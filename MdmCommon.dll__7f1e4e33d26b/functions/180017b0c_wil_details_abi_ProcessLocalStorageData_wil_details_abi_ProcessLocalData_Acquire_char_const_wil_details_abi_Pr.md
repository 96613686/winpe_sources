# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180017b0c`
- end: `0x180017eaa`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800186a4`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x18000611c`
- `0x18000ab78`
- `0x180017b0c`
- `0x180017eb0`
- `0x1800180e0`
- `0x18001843c`
- `0x1800189d8`
- `0x180018dd4`
- `0x18001978c`
- `0x180019a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017b45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180017b45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017cf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017cf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017d60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017dd5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180017ba5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180017ba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017c26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017d4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017dbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017c26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017d4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180017dbf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017b84`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180017b84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017d1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d2d`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
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
0x180017b0c  mov     [rsp-8+arg_10], rbx
0x180017b11  push    rbp
0x180017b12  push    rsi
0x180017b13  push    rdi
0x180017b14  push    r14
0x180017b16  push    r15
0x180017b18  lea     rbp, [rsp-160h]
0x180017b20  sub     rsp, 260h
0x180017b27  mov     rax, cs:__security_cookie
0x180017b2e  xor     rax, rsp
0x180017b31  mov     [rbp+180h+var_30], rax
0x180017b38  mov     r15, rdx
0x180017b3b  mov     qword ptr [rdx], 0
0x180017b42  mov     rbx, rcx
0x180017b45  call    cs:__imp_GetCurrentProcessId
0x180017b4b  mov     r14d, 78h ; 'x'
0x180017b51  mov     [rsp+280h+var_258], rbx
0x180017b56  mov     r9d, eax
0x180017b59  mov     [rsp+280h+var_260], r14d; int
0x180017b5e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180017b65  mov     edx, 104h; unsigned __int64
0x180017b6a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180017b6f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017b74  mov     r9d, 1F0001h; dwDesiredAccess
0x180017b7a  lea     rdx, [rsp+280h+Name]; lpName
0x180017b7f  xor     r8d, r8d; dwFlags
0x180017b82  xor     ecx, ecx; lpMutexAttributes
0x180017b84  call    cs:__imp_CreateMutexExW
0x180017b8a  mov     rbx, rax
0x180017b8d  test    rax, rax
0x180017b90  jnz     short loc_180017B9C
0x180017b92  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180017b97  jmp     loc_180017DE1
0x180017b9c  xor     r8d, r8d; bAlertable
0x180017b9f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017ba2  mov     rcx, rbx; hHandle
0x180017ba5  call    cs:__imp_WaitForSingleObjectEx
0x180017bab  cmp     eax, 102h
0x180017bb0  jz      short loc_180017BC2
0x180017bb2  test    eax, 0FFFFFF7Fh
0x180017bb7  jnz     loc_180017E19
0x180017bbd  mov     rdi, rbx
0x180017bc0  jmp     short loc_180017BC4
0x180017bc2  xor     edi, edi
0x180017bc4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180017bc9  mov     [rsp+280h+hObject], 0
0x180017bd2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180017bd7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180017bdc  mov     esi, eax
0x180017bde  test    eax, eax
0x180017be0  jns     short loc_180017C4C
0x180017be2  mov     rcx, [rbp+188h]; this
0x180017be9  mov     r9d, eax; char *
0x180017bec  mov     edx, 66h ; 'f'; void *
0x180017bf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017bf6  mov     rcx, [rbp+188h]; this
0x180017bfd  mov     r9d, esi; char *
0x180017c00  mov     edx, 6Fh ; 'o'; void *
0x180017c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c0a  mov     rcx, [rbp+188h]; this
0x180017c11  mov     r9d, esi; char *
0x180017c14  mov     edx, 12Eh; void *
0x180017c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c1e  test    rdi, rdi
0x180017c21  jz      short loc_180017C34
0x180017c23  mov     rcx, rdi; hMutex
0x180017c26  call    cs:__imp_ReleaseMutex
0x180017c2c  test    eax, eax
0x180017c2e  jz      loc_180017E26
0x180017c34  mov     rcx, rbx; hObject
0x180017c37  call    cs:__imp_CloseHandle
0x180017c3d  test    eax, eax
0x180017c3f  jz      loc_180017E38
0x180017c45  mov     eax, esi
0x180017c47  jmp     loc_180017DE1
0x180017c4c  mov     rax, [rsp+280h+hObject]
0x180017c51  lea     rcx, ds:0[rax*4]
0x180017c59  test    rcx, rcx
0x180017c5c  jz      short loc_180017C6C
0x180017c5e  mov     [r15], rcx
0x180017c61  mov     eax, [rcx]
0x180017c63  inc     eax
0x180017c65  mov     [rcx], eax
0x180017c67  jmp     loc_180017DB7
0x180017c6c  mov     rdx, r14; dwBytes
0x180017c6f  mov     qword ptr [r15], 0
0x180017c76  mov     ecx, 8; dwFlags
0x180017c7b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180017c80  mov     rsi, rax
0x180017c83  test    rax, rax
0x180017c86  jnz     short loc_180017CA7
0x180017c88  mov     rcx, [rbp+188h]; this
0x180017c8f  mov     r14d, 8007000Eh
0x180017c95  mov     r9d, r14d; char *
0x180017c98  mov     edx, 14Bh; void *
0x180017c9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ca2  jmp     loc_180017D33
0x180017ca7  xorps   xmm0, xmm0
0x180017caa  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180017cb0  test    sil, 3
0x180017cb4  jnz     loc_180017E4A
0x180017cba  mov     r9, rsi
0x180017cbd  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180017cc2  shr     r9, 2; unsigned __int64
0x180017cc6  lea     rcx, [rsp+280h+hObject]; this
0x180017ccb  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180017cd0  mov     r14d, eax
0x180017cd3  test    eax, eax
0x180017cd5  jns     loc_180017D73
0x180017cdb  mov     rcx, [rbp+188h]; this
0x180017ce2  mov     r9d, eax; char *
0x180017ce5  mov     edx, 14Eh; void *
0x180017cea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017cef  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180017cf4  test    rcx, rcx
0x180017cf7  jz      short loc_180017D07
0x180017cf9  call    cs:__imp_CloseHandle
0x180017cff  test    eax, eax
0x180017d01  jz      loc_180017E50
0x180017d07  mov     rcx, [rsp+280h+hObject]; hObject
0x180017d0c  test    rcx, rcx
0x180017d0f  jz      short loc_180017D1F
0x180017d11  call    cs:__imp_CloseHandle
0x180017d17  test    eax, eax
0x180017d19  jz      loc_180017E62
0x180017d1f  call    cs:__imp_GetProcessHeap
0x180017d25  mov     r8, rsi; lpMem
0x180017d28  xor     edx, edx; dwFlags
0x180017d2a  mov     rcx, rax; hHeap
0x180017d2d  call    cs:__imp_HeapFree
0x180017d33  mov     rcx, [rbp+188h]; this
0x180017d3a  mov     r9d, r14d; char *
0x180017d3d  mov     edx, 137h; void *
0x180017d42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d47  test    rdi, rdi
0x180017d4a  jz      short loc_180017D5D
0x180017d4c  mov     rcx, rdi; hMutex
0x180017d4f  call    cs:__imp_ReleaseMutex
0x180017d55  test    eax, eax
0x180017d57  jz      loc_180017E74
0x180017d5d  mov     rcx, rbx; hObject
0x180017d60  call    cs:__imp_CloseHandle
0x180017d66  test    eax, eax
0x180017d68  jz      loc_180017E86
0x180017d6e  mov     eax, r14d
0x180017d71  jmp     short loc_180017DE1
0x180017d73  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180017d78  xor     edx, edx; Val
0x180017d7a  mov     dword ptr [rsi], 1
0x180017d80  lea     rcx, [rsi+22h]; void *
0x180017d84  mov     [rsi+8], rbx
0x180017d88  movdqu  xmmword ptr [rsi+10h], xmm0
0x180017d8d  lea     r8d, [rdx+56h]; Size
0x180017d91  call    memset_0
0x180017d96  xor     edx, edx; Val
0x180017d98  mov     word ptr [rsi+20h], 58h ; 'X'
0x180017d9e  lea     rcx, [rsi+28h]; void *
0x180017da2  mov     dword ptr [rsi+24h], 1
0x180017da9  lea     r8d, [rdx+50h]; Size
0x180017dad  call    memset_0
0x180017db2  xor     ebx, ebx
0x180017db4  mov     [r15], rsi
0x180017db7  test    rdi, rdi
0x180017dba  jz      short loc_180017DCD
0x180017dbc  mov     rcx, rdi; hMutex
0x180017dbf  call    cs:__imp_ReleaseMutex
0x180017dc5  test    eax, eax
0x180017dc7  jz      loc_180017E98
0x180017dcd  test    rbx, rbx
0x180017dd0  jz      short loc_180017DDF
0x180017dd2  mov     rcx, rbx; hObject
0x180017dd5  call    cs:__imp_CloseHandle
0x180017ddb  test    eax, eax
0x180017ddd  jz      short loc_180017E07
0x180017ddf  xor     eax, eax
0x180017de1  mov     rcx, [rbp+180h+var_30]
0x180017de8  xor     rcx, rsp; StackCookie
0x180017deb  call    __security_check_cookie
0x180017df0  mov     rbx, [rsp+280h+arg_10]
0x180017df8  add     rsp, 260h
0x180017dff  pop     r15
0x180017e01  pop     r14
0x180017e03  pop     rdi
0x180017e04  pop     rsi
0x180017e05  pop     rbp
0x180017e06  retn
0x180017e07  mov     rcx, [rbp+188h]; this
0x180017e0e  mov     edx, 0A0Bh; void *
0x180017e13  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017e19  mov     rcx, [rbp+188h]; this
0x180017e20  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180017e26  mov     rcx, [rbp+188h]; this
0x180017e2d  mov     edx, 0A15h; void *
0x180017e32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017e38  mov     rcx, [rbp+188h]; this
0x180017e3f  mov     edx, 0A0Bh; void *
0x180017e44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017e4a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180017e50  mov     rcx, [rbp+188h]; this
0x180017e57  mov     edx, 0A0Bh; void *
0x180017e5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017e62  mov     rcx, [rbp+188h]; this
0x180017e69  mov     edx, 0A0Bh; void *
0x180017e6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017e74  mov     rcx, [rbp+188h]; this
0x180017e7b  mov     edx, 0A15h; void *
0x180017e80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017e86  mov     rcx, [rbp+188h]; this
0x180017e8d  mov     edx, 0A0Bh; void *
0x180017e92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180017e98  mov     rcx, [rbp+188h]; this
0x180017e9f  mov     edx, 0A15h; void *
0x180017ea4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
