# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003c14`
- end: `0x180003fb2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004aa0`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180003c14`
- `0x180003fb8`
- `0x1800041e0`
- `0x180004838`
- `0x180005308`
- `0x180005774`
- `0x180006100`
- `0x1800061bc`
- `0x18000656c`
- `0x18000657c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e57`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ec7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003d2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003e57`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ec7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003cad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003cad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c8c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003c8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003edd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003edd`

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
0x180003c14  mov     [rsp-8+arg_10], rbx
0x180003c19  push    rbp
0x180003c1a  push    rsi
0x180003c1b  push    rdi
0x180003c1c  push    r14
0x180003c1e  push    r15
0x180003c20  lea     rbp, [rsp-160h]
0x180003c28  sub     rsp, 260h
0x180003c2f  mov     rax, cs:__security_cookie
0x180003c36  xor     rax, rsp
0x180003c39  mov     [rbp+180h+var_30], rax
0x180003c40  mov     r15, rdx
0x180003c43  mov     qword ptr [rdx], 0
0x180003c4a  mov     rbx, rcx
0x180003c4d  call    cs:__imp_GetCurrentProcessId
0x180003c53  mov     r14d, 78h ; 'x'
0x180003c59  mov     [rsp+280h+var_258], rbx
0x180003c5e  mov     r9d, eax
0x180003c61  mov     [rsp+280h+var_260], r14d; int
0x180003c66  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003c6d  mov     edx, 104h; unsigned __int64
0x180003c72  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003c77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003c7c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003c82  lea     rdx, [rsp+280h+Name]; lpName
0x180003c87  xor     r8d, r8d; dwFlags
0x180003c8a  xor     ecx, ecx; lpMutexAttributes
0x180003c8c  call    cs:__imp_CreateMutexExW
0x180003c92  mov     rbx, rax
0x180003c95  test    rax, rax
0x180003c98  jnz     short loc_180003CA4
0x180003c9a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003c9f  jmp     loc_180003EE9
0x180003ca4  xor     r8d, r8d; bAlertable
0x180003ca7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003caa  mov     rcx, rbx; hHandle
0x180003cad  call    cs:__imp_WaitForSingleObjectEx
0x180003cb3  cmp     eax, 102h
0x180003cb8  jz      short loc_180003CCA
0x180003cba  test    eax, 0FFFFFF7Fh
0x180003cbf  jnz     loc_180003F21
0x180003cc5  mov     rdi, rbx
0x180003cc8  jmp     short loc_180003CCC
0x180003cca  xor     edi, edi
0x180003ccc  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003cd1  mov     [rsp+280h+hObject], 0
0x180003cda  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003cdf  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003ce4  mov     esi, eax
0x180003ce6  test    eax, eax
0x180003ce8  jns     short loc_180003D54
0x180003cea  mov     rcx, [rbp+188h]; this
0x180003cf1  mov     r9d, eax; char *
0x180003cf4  mov     edx, 66h ; 'f'; void *
0x180003cf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003cfe  mov     rcx, [rbp+188h]; this
0x180003d05  mov     r9d, esi; char *
0x180003d08  mov     edx, 6Fh ; 'o'; void *
0x180003d0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d12  mov     rcx, [rbp+188h]; this
0x180003d19  mov     r9d, esi; char *
0x180003d1c  mov     edx, 12Eh; void *
0x180003d21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003d26  test    rdi, rdi
0x180003d29  jz      short loc_180003D3C
0x180003d2b  mov     rcx, rdi; hMutex
0x180003d2e  call    cs:__imp_ReleaseMutex
0x180003d34  test    eax, eax
0x180003d36  jz      loc_180003F2E
0x180003d3c  mov     rcx, rbx; hObject
0x180003d3f  call    cs:__imp_CloseHandle
0x180003d45  test    eax, eax
0x180003d47  jz      loc_180003F40
0x180003d4d  mov     eax, esi
0x180003d4f  jmp     loc_180003EE9
0x180003d54  mov     rax, [rsp+280h+hObject]
0x180003d59  lea     rcx, ds:0[rax*4]
0x180003d61  test    rcx, rcx
0x180003d64  jz      short loc_180003D74
0x180003d66  mov     [r15], rcx
0x180003d69  mov     eax, [rcx]
0x180003d6b  inc     eax
0x180003d6d  mov     [rcx], eax
0x180003d6f  jmp     loc_180003EBF
0x180003d74  mov     rdx, r14; dwBytes
0x180003d77  mov     qword ptr [r15], 0
0x180003d7e  mov     ecx, 8; dwFlags
0x180003d83  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003d88  mov     rsi, rax
0x180003d8b  test    rax, rax
0x180003d8e  jnz     short loc_180003DAF
0x180003d90  mov     rcx, [rbp+188h]; this
0x180003d97  mov     r14d, 8007000Eh
0x180003d9d  mov     r9d, r14d; char *
0x180003da0  mov     edx, 14Bh; void *
0x180003da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003daa  jmp     loc_180003E3B
0x180003daf  xorps   xmm0, xmm0
0x180003db2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003db8  test    sil, 3
0x180003dbc  jnz     loc_180003F52
0x180003dc2  mov     r9, rsi
0x180003dc5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003dca  shr     r9, 2; unsigned __int64
0x180003dce  lea     rcx, [rsp+280h+hObject]; this
0x180003dd3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003dd8  mov     r14d, eax
0x180003ddb  test    eax, eax
0x180003ddd  jns     loc_180003E7B
0x180003de3  mov     rcx, [rbp+188h]; this
0x180003dea  mov     r9d, eax; char *
0x180003ded  mov     edx, 14Eh; void *
0x180003df2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003df7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003dfc  test    rcx, rcx
0x180003dff  jz      short loc_180003E0F
0x180003e01  call    cs:__imp_CloseHandle
0x180003e07  test    eax, eax
0x180003e09  jz      loc_180003F58
0x180003e0f  mov     rcx, [rsp+280h+hObject]; hObject
0x180003e14  test    rcx, rcx
0x180003e17  jz      short loc_180003E27
0x180003e19  call    cs:__imp_CloseHandle
0x180003e1f  test    eax, eax
0x180003e21  jz      loc_180003F6A
0x180003e27  call    cs:__imp_GetProcessHeap
0x180003e2d  mov     r8, rsi; lpMem
0x180003e30  xor     edx, edx; dwFlags
0x180003e32  mov     rcx, rax; hHeap
0x180003e35  call    cs:__imp_HeapFree
0x180003e3b  mov     rcx, [rbp+188h]; this
0x180003e42  mov     r9d, r14d; char *
0x180003e45  mov     edx, 137h; void *
0x180003e4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003e4f  test    rdi, rdi
0x180003e52  jz      short loc_180003E65
0x180003e54  mov     rcx, rdi; hMutex
0x180003e57  call    cs:__imp_ReleaseMutex
0x180003e5d  test    eax, eax
0x180003e5f  jz      loc_180003F7C
0x180003e65  mov     rcx, rbx; hObject
0x180003e68  call    cs:__imp_CloseHandle
0x180003e6e  test    eax, eax
0x180003e70  jz      loc_180003F8E
0x180003e76  mov     eax, r14d
0x180003e79  jmp     short loc_180003EE9
0x180003e7b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003e80  xor     edx, edx; Val
0x180003e82  mov     dword ptr [rsi], 1
0x180003e88  lea     rcx, [rsi+22h]; void *
0x180003e8c  mov     [rsi+8], rbx
0x180003e90  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003e95  lea     r8d, [rdx+56h]; Size
0x180003e99  call    memset_0
0x180003e9e  xor     edx, edx; Val
0x180003ea0  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003ea6  lea     rcx, [rsi+28h]; void *
0x180003eaa  mov     dword ptr [rsi+24h], 1
0x180003eb1  lea     r8d, [rdx+50h]; Size
0x180003eb5  call    memset_0
0x180003eba  xor     ebx, ebx
0x180003ebc  mov     [r15], rsi
0x180003ebf  test    rdi, rdi
0x180003ec2  jz      short loc_180003ED5
0x180003ec4  mov     rcx, rdi; hMutex
0x180003ec7  call    cs:__imp_ReleaseMutex
0x180003ecd  test    eax, eax
0x180003ecf  jz      loc_180003FA0
0x180003ed5  test    rbx, rbx
0x180003ed8  jz      short loc_180003EE7
0x180003eda  mov     rcx, rbx; hObject
0x180003edd  call    cs:__imp_CloseHandle
0x180003ee3  test    eax, eax
0x180003ee5  jz      short loc_180003F0F
0x180003ee7  xor     eax, eax
0x180003ee9  mov     rcx, [rbp+180h+var_30]
0x180003ef0  xor     rcx, rsp; StackCookie
0x180003ef3  call    __security_check_cookie
0x180003ef8  mov     rbx, [rsp+280h+arg_10]
0x180003f00  add     rsp, 260h
0x180003f07  pop     r15
0x180003f09  pop     r14
0x180003f0b  pop     rdi
0x180003f0c  pop     rsi
0x180003f0d  pop     rbp
0x180003f0e  retn
0x180003f0f  mov     rcx, [rbp+188h]; this
0x180003f16  mov     edx, 0A0Bh; void *
0x180003f1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f21  mov     rcx, [rbp+188h]; this
0x180003f28  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003f2e  mov     rcx, [rbp+188h]; this
0x180003f35  mov     edx, 0A15h; void *
0x180003f3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f40  mov     rcx, [rbp+188h]; this
0x180003f47  mov     edx, 0A0Bh; void *
0x180003f4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f52  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003f58  mov     rcx, [rbp+188h]; this
0x180003f5f  mov     edx, 0A0Bh; void *
0x180003f64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f6a  mov     rcx, [rbp+188h]; this
0x180003f71  mov     edx, 0A0Bh; void *
0x180003f76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f7c  mov     rcx, [rbp+188h]; this
0x180003f83  mov     edx, 0A15h; void *
0x180003f88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003f8e  mov     rcx, [rbp+188h]; this
0x180003f95  mov     edx, 0A0Bh; void *
0x180003f9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003fa0  mov     rcx, [rbp+188h]; this
0x180003fa7  mov     edx, 0A15h; void *
0x180003fac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
