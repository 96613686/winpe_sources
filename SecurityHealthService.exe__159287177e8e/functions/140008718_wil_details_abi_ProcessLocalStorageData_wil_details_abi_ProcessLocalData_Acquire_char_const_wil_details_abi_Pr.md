# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140008718`
- end: `0x140008ae0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140009b8c`

## callees

- `0x1400015d0`
- `0x14000202c`
- `0x140006670`
- `0x140006bec`
- `0x140006e3c`
- `0x140008718`
- `0x140008ee0`
- `0x140009354`
- `0x140009924`
- `0x14000bbd8`
- `0x14000bf1c`
- `0x14000c620`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140008858`
- `KERNEL32!CloseHandle` at `0x140008928`
- `KERNEL32!CloseHandle` at `0x140008940`
- `KERNEL32!CloseHandle` at `0x140008996`
- `KERNEL32!CloseHandle` at `0x140008a0b`
- `KERNEL32!CloseHandle` at `0x140008858`
- `KERNEL32!CloseHandle` at `0x140008928`
- `KERNEL32!CloseHandle` at `0x140008940`
- `KERNEL32!CloseHandle` at `0x140008996`
- `KERNEL32!CloseHandle` at `0x140008a0b`
- `KERNEL32!GetCurrentProcessId` at `0x140008751`
- `KERNEL32!GetCurrentProcessId` at `0x140008751`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008847`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008985`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400089f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008847`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008985`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400089f5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008790`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008790`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400087b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400087b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000895c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000895c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000894e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000894e`

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
0x140008718  mov     [rsp-8+arg_10], rbx
0x14000871d  push    rbp
0x14000871e  push    rsi
0x14000871f  push    rdi
0x140008720  push    r14
0x140008722  push    r15
0x140008724  lea     rbp, [rsp-160h]
0x14000872c  sub     rsp, 260h
0x140008733  mov     rax, cs:__security_cookie
0x14000873a  xor     rax, rsp
0x14000873d  mov     [rbp+180h+var_30], rax
0x140008744  mov     r15, rdx
0x140008747  mov     qword ptr [rdx], 0
0x14000874e  mov     rbx, rcx
0x140008751  call    cs:__imp_GetCurrentProcessId
0x140008757  mov     r14d, 78h ; 'x'
0x14000875d  mov     [rsp+280h+var_258], rbx
0x140008762  mov     r9d, eax
0x140008765  mov     [rsp+280h+var_260], r14d; int
0x14000876a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140008771  mov     edx, 104h; unsigned __int64
0x140008776  lea     rcx, [rsp+280h+Name]; Buffer
0x14000877b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008780  mov     r9d, 1F0001h; dwDesiredAccess
0x140008786  lea     rdx, [rsp+280h+Name]; lpName
0x14000878b  xor     r8d, r8d; dwFlags
0x14000878e  xor     ecx, ecx; lpMutexAttributes
0x140008790  call    cs:__imp_CreateMutexExW
0x140008796  mov     rbx, rax
0x140008799  test    rax, rax
0x14000879c  jnz     short loc_1400087A8
0x14000879e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400087a3  jmp     loc_140008A17
0x1400087a8  xor     r8d, r8d; bAlertable
0x1400087ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400087ae  mov     rcx, rbx; hHandle
0x1400087b1  call    cs:__imp_WaitForSingleObjectEx
0x1400087b7  cmp     eax, 102h
0x1400087bc  jz      short loc_1400087CE
0x1400087be  test    eax, 0FFFFFF7Fh
0x1400087c3  jnz     loc_140008A4F
0x1400087c9  mov     rdi, rbx
0x1400087cc  jmp     short loc_1400087D0
0x1400087ce  xor     edi, edi
0x1400087d0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400087d5  mov     [rsp+280h+hObject], 0
0x1400087de  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400087e3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400087e8  mov     esi, eax
0x1400087ea  test    eax, eax
0x1400087ec  jns     short loc_14000886D
0x1400087ee  mov     rcx, [rbp+188h]; this
0x1400087f5  lea     r8, aWil; "wil"
0x1400087fc  mov     r9d, eax; char *
0x1400087ff  mov     edx, 66h ; 'f'; void *
0x140008804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008809  mov     rcx, [rbp+188h]; this
0x140008810  lea     r8, aWil; "wil"
0x140008817  mov     r9d, esi; char *
0x14000881a  mov     edx, 6Fh ; 'o'; void *
0x14000881f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008824  mov     rcx, [rbp+188h]; this
0x14000882b  lea     r8, aWil; "wil"
0x140008832  mov     r9d, esi; char *
0x140008835  mov     edx, 12Eh; void *
0x14000883a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000883f  test    rdi, rdi
0x140008842  jz      short loc_140008855
0x140008844  mov     rcx, rdi; hMutex
0x140008847  call    cs:__imp_ReleaseMutex
0x14000884d  test    eax, eax
0x14000884f  jz      loc_140008A5C
0x140008855  mov     rcx, rbx; hObject
0x140008858  call    cs:__imp_CloseHandle
0x14000885e  test    eax, eax
0x140008860  jz      loc_140008A6E
0x140008866  mov     eax, esi
0x140008868  jmp     loc_140008A17
0x14000886d  mov     rax, [rsp+280h+hObject]
0x140008872  lea     rcx, ds:0[rax*4]
0x14000887a  test    rcx, rcx
0x14000887d  jz      short loc_14000888D
0x14000887f  mov     [r15], rcx
0x140008882  mov     eax, [rcx]
0x140008884  inc     eax
0x140008886  mov     [rcx], eax
0x140008888  jmp     loc_1400089ED
0x14000888d  mov     rdx, r14; dwBytes
0x140008890  mov     qword ptr [r15], 0
0x140008897  mov     ecx, 8; dwFlags
0x14000889c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400088a1  mov     rsi, rax
0x1400088a4  test    rax, rax
0x1400088a7  jnz     short loc_1400088CF
0x1400088a9  mov     rcx, [rbp+188h]; this
0x1400088b0  lea     r8, aWil; "wil"
0x1400088b7  mov     r14d, 8007000Eh
0x1400088bd  mov     edx, 14Bh; void *
0x1400088c2  mov     r9d, r14d; char *
0x1400088c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400088ca  jmp     loc_140008962
0x1400088cf  xorps   xmm0, xmm0
0x1400088d2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400088d8  test    sil, 3
0x1400088dc  jnz     loc_140008A80
0x1400088e2  mov     r9, rsi
0x1400088e5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400088ea  shr     r9, 2; unsigned __int64
0x1400088ee  lea     rcx, [rsp+280h+hObject]; this
0x1400088f3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400088f8  mov     r14d, eax
0x1400088fb  test    eax, eax
0x1400088fd  jns     loc_1400089A9
0x140008903  mov     rcx, [rbp+188h]; this
0x14000890a  lea     r8, aWil; "wil"
0x140008911  mov     r9d, eax; char *
0x140008914  mov     edx, 14Eh; void *
0x140008919  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000891e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140008923  test    rcx, rcx
0x140008926  jz      short loc_140008936
0x140008928  call    cs:__imp_CloseHandle
0x14000892e  test    eax, eax
0x140008930  jz      loc_140008A86
0x140008936  mov     rcx, [rsp+280h+hObject]; hObject
0x14000893b  test    rcx, rcx
0x14000893e  jz      short loc_14000894E
0x140008940  call    cs:__imp_CloseHandle
0x140008946  test    eax, eax
0x140008948  jz      loc_140008A98
0x14000894e  call    cs:__imp_GetProcessHeap
0x140008954  mov     r8, rsi; lpMem
0x140008957  xor     edx, edx; dwFlags
0x140008959  mov     rcx, rax; hHeap
0x14000895c  call    cs:__imp_HeapFree
0x140008962  mov     rcx, [rbp+188h]; this
0x140008969  lea     r8, aWil; "wil"
0x140008970  mov     r9d, r14d; char *
0x140008973  mov     edx, 137h; void *
0x140008978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000897d  test    rdi, rdi
0x140008980  jz      short loc_140008993
0x140008982  mov     rcx, rdi; hMutex
0x140008985  call    cs:__imp_ReleaseMutex
0x14000898b  test    eax, eax
0x14000898d  jz      loc_140008AAA
0x140008993  mov     rcx, rbx; hObject
0x140008996  call    cs:__imp_CloseHandle
0x14000899c  test    eax, eax
0x14000899e  jz      loc_140008ABC
0x1400089a4  mov     eax, r14d
0x1400089a7  jmp     short loc_140008A17
0x1400089a9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400089ae  xor     edx, edx; Val
0x1400089b0  mov     dword ptr [rsi], 1
0x1400089b6  lea     rcx, [rsi+22h]; void *
0x1400089ba  mov     [rsi+8], rbx
0x1400089be  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400089c3  lea     r8d, [rdx+56h]; Size
0x1400089c7  call    memset_0
0x1400089cc  xor     edx, edx; Val
0x1400089ce  mov     word ptr [rsi+20h], 58h ; 'X'
0x1400089d4  lea     rcx, [rsi+28h]; void *
0x1400089d8  mov     dword ptr [rsi+24h], 1
0x1400089df  lea     r8d, [rdx+50h]; Size
0x1400089e3  call    memset_0
0x1400089e8  xor     ebx, ebx
0x1400089ea  mov     [r15], rsi
0x1400089ed  test    rdi, rdi
0x1400089f0  jz      short loc_140008A03
0x1400089f2  mov     rcx, rdi; hMutex
0x1400089f5  call    cs:__imp_ReleaseMutex
0x1400089fb  test    eax, eax
0x1400089fd  jz      loc_140008ACE
0x140008a03  test    rbx, rbx
0x140008a06  jz      short loc_140008A15
0x140008a08  mov     rcx, rbx; hObject
0x140008a0b  call    cs:__imp_CloseHandle
0x140008a11  test    eax, eax
0x140008a13  jz      short loc_140008A3D
0x140008a15  xor     eax, eax
0x140008a17  mov     rcx, [rbp+180h+var_30]
0x140008a1e  xor     rcx, rsp; StackCookie
0x140008a21  call    __security_check_cookie
0x140008a26  mov     rbx, [rsp+280h+arg_10]
0x140008a2e  add     rsp, 260h
0x140008a35  pop     r15
0x140008a37  pop     r14
0x140008a39  pop     rdi
0x140008a3a  pop     rsi
0x140008a3b  pop     rbp
0x140008a3c  retn
0x140008a3d  mov     rcx, [rbp+188h]; this
0x140008a44  mov     edx, 0A0Bh; void *
0x140008a49  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008a4f  mov     rcx, [rbp+188h]; this
0x140008a56  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140008a5c  mov     rcx, [rbp+188h]; this
0x140008a63  mov     edx, 0A15h; void *
0x140008a68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008a6e  mov     rcx, [rbp+188h]; this
0x140008a75  mov     edx, 0A0Bh; void *
0x140008a7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008a80  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008a86  mov     rcx, [rbp+188h]; this
0x140008a8d  mov     edx, 0A0Bh; void *
0x140008a92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008a98  mov     rcx, [rbp+188h]; this
0x140008a9f  mov     edx, 0A0Bh; void *
0x140008aa4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008aaa  mov     rcx, [rbp+188h]; this
0x140008ab1  mov     edx, 0A15h; void *
0x140008ab6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008abc  mov     rcx, [rbp+188h]; this
0x140008ac3  mov     edx, 0A0Bh; void *
0x140008ac8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008ace  mov     rcx, [rbp+188h]; this
0x140008ad5  mov     edx, 0A15h; void *
0x140008ada  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
