# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000596c`
- end: `0x180005d0a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800070cc`

## callees

- `0x18000596c`
- `0x1800060e0`
- `0x180006544`
- `0x180006e68`
- `0x180007a58`
- `0x180008cf0`
- `0x1800091c0`
- `0x1800094c8`
- `0x180009c9c`
- `0x180009cac`
- `0x18000a19e`
- `0x18000a1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a86`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005baf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005a86`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005baf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c1f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059e4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800059e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005a05`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005a05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800059a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800059a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c35`

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
0x18000596c  mov     [rsp-8+arg_10], rbx
0x180005971  push    rbp
0x180005972  push    rsi
0x180005973  push    rdi
0x180005974  push    r14
0x180005976  push    r15
0x180005978  lea     rbp, [rsp-160h]
0x180005980  sub     rsp, 260h
0x180005987  mov     rax, cs:__security_cookie
0x18000598e  xor     rax, rsp
0x180005991  mov     [rbp+180h+var_30], rax
0x180005998  mov     r15, rdx
0x18000599b  mov     qword ptr [rdx], 0
0x1800059a2  mov     rbx, rcx
0x1800059a5  call    cs:__imp_GetCurrentProcessId
0x1800059ab  mov     r14d, 78h ; 'x'
0x1800059b1  mov     [rsp+280h+var_258], rbx
0x1800059b6  mov     r9d, eax
0x1800059b9  mov     [rsp+280h+var_260], r14d; int
0x1800059be  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800059c5  mov     edx, 104h; unsigned __int64
0x1800059ca  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800059cf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800059d4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800059da  lea     rdx, [rsp+280h+Name]; lpName
0x1800059df  xor     r8d, r8d; dwFlags
0x1800059e2  xor     ecx, ecx; lpMutexAttributes
0x1800059e4  call    cs:__imp_CreateMutexExW
0x1800059ea  mov     rbx, rax
0x1800059ed  test    rax, rax
0x1800059f0  jnz     short loc_1800059FC
0x1800059f2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800059f7  jmp     loc_180005C41
0x1800059fc  xor     r8d, r8d; bAlertable
0x1800059ff  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005a02  mov     rcx, rbx; hHandle
0x180005a05  call    cs:__imp_WaitForSingleObjectEx
0x180005a0b  cmp     eax, 102h
0x180005a10  jz      short loc_180005A22
0x180005a12  test    eax, 0FFFFFF7Fh
0x180005a17  jnz     loc_180005C79
0x180005a1d  mov     rdi, rbx
0x180005a20  jmp     short loc_180005A24
0x180005a22  xor     edi, edi
0x180005a24  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005a29  mov     [rsp+280h+hObject], 0
0x180005a32  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005a37  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005a3c  mov     esi, eax
0x180005a3e  test    eax, eax
0x180005a40  jns     short loc_180005AAC
0x180005a42  mov     rcx, [rbp+188h]; this
0x180005a49  mov     r9d, eax; char *
0x180005a4c  mov     edx, 66h ; 'f'; void *
0x180005a51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a56  mov     rcx, [rbp+188h]; this
0x180005a5d  mov     r9d, esi; char *
0x180005a60  mov     edx, 6Fh ; 'o'; void *
0x180005a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a6a  mov     rcx, [rbp+188h]; this
0x180005a71  mov     r9d, esi; char *
0x180005a74  mov     edx, 12Eh; void *
0x180005a79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005a7e  test    rdi, rdi
0x180005a81  jz      short loc_180005A94
0x180005a83  mov     rcx, rdi; hMutex
0x180005a86  call    cs:__imp_ReleaseMutex
0x180005a8c  test    eax, eax
0x180005a8e  jz      loc_180005C86
0x180005a94  mov     rcx, rbx; hObject
0x180005a97  call    cs:__imp_CloseHandle
0x180005a9d  test    eax, eax
0x180005a9f  jz      loc_180005C98
0x180005aa5  mov     eax, esi
0x180005aa7  jmp     loc_180005C41
0x180005aac  mov     rax, [rsp+280h+hObject]
0x180005ab1  lea     rcx, ds:0[rax*4]
0x180005ab9  test    rcx, rcx
0x180005abc  jz      short loc_180005ACC
0x180005abe  mov     [r15], rcx
0x180005ac1  mov     eax, [rcx]
0x180005ac3  inc     eax
0x180005ac5  mov     [rcx], eax
0x180005ac7  jmp     loc_180005C17
0x180005acc  mov     rdx, r14; dwBytes
0x180005acf  mov     qword ptr [r15], 0
0x180005ad6  mov     ecx, 8; dwFlags
0x180005adb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005ae0  mov     rsi, rax
0x180005ae3  test    rax, rax
0x180005ae6  jnz     short loc_180005B07
0x180005ae8  mov     rcx, [rbp+188h]; this
0x180005aef  mov     r14d, 8007000Eh
0x180005af5  mov     r9d, r14d; char *
0x180005af8  mov     edx, 14Bh; void *
0x180005afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b02  jmp     loc_180005B93
0x180005b07  xorps   xmm0, xmm0
0x180005b0a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005b10  test    sil, 3
0x180005b14  jnz     loc_180005CAA
0x180005b1a  mov     r9, rsi
0x180005b1d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005b22  shr     r9, 2; unsigned __int64
0x180005b26  lea     rcx, [rsp+280h+hObject]; this
0x180005b2b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005b30  mov     r14d, eax
0x180005b33  test    eax, eax
0x180005b35  jns     loc_180005BD3
0x180005b3b  mov     rcx, [rbp+188h]; this
0x180005b42  mov     r9d, eax; char *
0x180005b45  mov     edx, 14Eh; void *
0x180005b4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b4f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005b54  test    rcx, rcx
0x180005b57  jz      short loc_180005B67
0x180005b59  call    cs:__imp_CloseHandle
0x180005b5f  test    eax, eax
0x180005b61  jz      loc_180005CB0
0x180005b67  mov     rcx, [rsp+280h+hObject]; hObject
0x180005b6c  test    rcx, rcx
0x180005b6f  jz      short loc_180005B7F
0x180005b71  call    cs:__imp_CloseHandle
0x180005b77  test    eax, eax
0x180005b79  jz      loc_180005CC2
0x180005b7f  call    cs:__imp_GetProcessHeap
0x180005b85  mov     r8, rsi; lpMem
0x180005b88  xor     edx, edx; dwFlags
0x180005b8a  mov     rcx, rax; hHeap
0x180005b8d  call    cs:__imp_HeapFree
0x180005b93  mov     rcx, [rbp+188h]; this
0x180005b9a  mov     r9d, r14d; char *
0x180005b9d  mov     edx, 137h; void *
0x180005ba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ba7  test    rdi, rdi
0x180005baa  jz      short loc_180005BBD
0x180005bac  mov     rcx, rdi; hMutex
0x180005baf  call    cs:__imp_ReleaseMutex
0x180005bb5  test    eax, eax
0x180005bb7  jz      loc_180005CD4
0x180005bbd  mov     rcx, rbx; hObject
0x180005bc0  call    cs:__imp_CloseHandle
0x180005bc6  test    eax, eax
0x180005bc8  jz      loc_180005CE6
0x180005bce  mov     eax, r14d
0x180005bd1  jmp     short loc_180005C41
0x180005bd3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005bd8  xor     edx, edx; Val
0x180005bda  mov     dword ptr [rsi], 1
0x180005be0  lea     rcx, [rsi+22h]; void *
0x180005be4  mov     [rsi+8], rbx
0x180005be8  movdqu  xmmword ptr [rsi+10h], xmm0
0x180005bed  lea     r8d, [rdx+56h]; Size
0x180005bf1  call    memset_0
0x180005bf6  xor     edx, edx; Val
0x180005bf8  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005bfe  lea     rcx, [rsi+28h]; void *
0x180005c02  mov     dword ptr [rsi+24h], 1
0x180005c09  lea     r8d, [rdx+50h]; Size
0x180005c0d  call    memset_0
0x180005c12  xor     ebx, ebx
0x180005c14  mov     [r15], rsi
0x180005c17  test    rdi, rdi
0x180005c1a  jz      short loc_180005C2D
0x180005c1c  mov     rcx, rdi; hMutex
0x180005c1f  call    cs:__imp_ReleaseMutex
0x180005c25  test    eax, eax
0x180005c27  jz      loc_180005CF8
0x180005c2d  test    rbx, rbx
0x180005c30  jz      short loc_180005C3F
0x180005c32  mov     rcx, rbx; hObject
0x180005c35  call    cs:__imp_CloseHandle
0x180005c3b  test    eax, eax
0x180005c3d  jz      short loc_180005C67
0x180005c3f  xor     eax, eax
0x180005c41  mov     rcx, [rbp+180h+var_30]
0x180005c48  xor     rcx, rsp; StackCookie
0x180005c4b  call    __security_check_cookie
0x180005c50  mov     rbx, [rsp+280h+arg_10]
0x180005c58  add     rsp, 260h
0x180005c5f  pop     r15
0x180005c61  pop     r14
0x180005c63  pop     rdi
0x180005c64  pop     rsi
0x180005c65  pop     rbp
0x180005c66  retn
0x180005c67  mov     rcx, [rbp+188h]; this
0x180005c6e  mov     edx, 0A0Bh; void *
0x180005c73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c79  mov     rcx, [rbp+188h]; this
0x180005c80  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180005c86  mov     rcx, [rbp+188h]; this
0x180005c8d  mov     edx, 0A15h; void *
0x180005c92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005c98  mov     rcx, [rbp+188h]; this
0x180005c9f  mov     edx, 0A0Bh; void *
0x180005ca4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005caa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005cb0  mov     rcx, [rbp+188h]; this
0x180005cb7  mov     edx, 0A0Bh; void *
0x180005cbc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005cc2  mov     rcx, [rbp+188h]; this
0x180005cc9  mov     edx, 0A0Bh; void *
0x180005cce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005cd4  mov     rcx, [rbp+188h]; this
0x180005cdb  mov     edx, 0A15h; void *
0x180005ce0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ce6  mov     rcx, [rbp+188h]; this
0x180005ced  mov     edx, 0A0Bh; void *
0x180005cf2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005cf8  mov     rcx, [rbp+188h]; this
0x180005cff  mov     edx, 0A15h; void *
0x180005d04  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
