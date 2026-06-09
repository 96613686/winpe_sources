# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180019770`
- end: `0x180019b0e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001c47c`

## callees

- `0x180003850`
- `0x180019770`
- `0x18001a64c`
- `0x18001b230`
- `0x18001be4c`
- `0x18001f350`
- `0x180021f38`
- `0x180023518`
- `0x1800247e4`
- `0x1800247f4`
- `0x1800322d2`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001988a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800199b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019a23`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001988a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800199b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019a23`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019809`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019809`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800197e8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800197e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800197a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800197a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001989b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001995d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800199c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001989b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001995d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800199c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019a39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019983`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019991`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019991`

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
0x180019770  mov     [rsp-8+arg_10], rbx
0x180019775  push    rbp
0x180019776  push    rsi
0x180019777  push    rdi
0x180019778  push    r14
0x18001977a  push    r15
0x18001977c  lea     rbp, [rsp-160h]
0x180019784  sub     rsp, 260h
0x18001978b  mov     rax, cs:__security_cookie
0x180019792  xor     rax, rsp
0x180019795  mov     [rbp+180h+var_30], rax
0x18001979c  mov     r15, rdx
0x18001979f  mov     qword ptr [rdx], 0
0x1800197a6  mov     rbx, rcx
0x1800197a9  call    cs:__imp_GetCurrentProcessId
0x1800197af  mov     r14d, 78h ; 'x'
0x1800197b5  mov     [rsp+280h+var_258], rbx
0x1800197ba  mov     r9d, eax
0x1800197bd  mov     [rsp+280h+var_260], r14d; int
0x1800197c2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800197c9  mov     edx, 104h; unsigned __int64
0x1800197ce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800197d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800197d8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800197de  lea     rdx, [rsp+280h+Name]; lpName
0x1800197e3  xor     r8d, r8d; dwFlags
0x1800197e6  xor     ecx, ecx; lpMutexAttributes
0x1800197e8  call    cs:__imp_CreateMutexExW
0x1800197ee  mov     rbx, rax
0x1800197f1  test    rax, rax
0x1800197f4  jnz     short loc_180019800
0x1800197f6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800197fb  jmp     loc_180019A45
0x180019800  xor     r8d, r8d; bAlertable
0x180019803  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019806  mov     rcx, rbx; hHandle
0x180019809  call    cs:__imp_WaitForSingleObjectEx
0x18001980f  cmp     eax, 102h
0x180019814  jz      short loc_180019826
0x180019816  test    eax, 0FFFFFF7Fh
0x18001981b  jnz     loc_180019A7D
0x180019821  mov     rdi, rbx
0x180019824  jmp     short loc_180019828
0x180019826  xor     edi, edi
0x180019828  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18001982d  mov     [rsp+280h+hObject], 0
0x180019836  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001983b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180019840  mov     esi, eax
0x180019842  test    eax, eax
0x180019844  jns     short loc_1800198B0
0x180019846  mov     rcx, [rbp+188h]; this
0x18001984d  mov     r9d, eax; char *
0x180019850  mov     edx, 66h ; 'f'; void *
0x180019855  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001985a  mov     rcx, [rbp+188h]; this
0x180019861  mov     r9d, esi; char *
0x180019864  mov     edx, 6Fh ; 'o'; void *
0x180019869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001986e  mov     rcx, [rbp+188h]; this
0x180019875  mov     r9d, esi; char *
0x180019878  mov     edx, 12Eh; void *
0x18001987d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019882  test    rdi, rdi
0x180019885  jz      short loc_180019898
0x180019887  mov     rcx, rdi; hMutex
0x18001988a  call    cs:__imp_ReleaseMutex
0x180019890  test    eax, eax
0x180019892  jz      loc_180019A8A
0x180019898  mov     rcx, rbx; hObject
0x18001989b  call    cs:__imp_CloseHandle
0x1800198a1  test    eax, eax
0x1800198a3  jz      loc_180019A9C
0x1800198a9  mov     eax, esi
0x1800198ab  jmp     loc_180019A45
0x1800198b0  mov     rax, [rsp+280h+hObject]
0x1800198b5  lea     rcx, ds:0[rax*4]
0x1800198bd  test    rcx, rcx
0x1800198c0  jz      short loc_1800198D0
0x1800198c2  mov     [r15], rcx
0x1800198c5  mov     eax, [rcx]
0x1800198c7  inc     eax
0x1800198c9  mov     [rcx], eax
0x1800198cb  jmp     loc_180019A1B
0x1800198d0  mov     rdx, r14; dwBytes
0x1800198d3  mov     qword ptr [r15], 0
0x1800198da  mov     ecx, 8; dwFlags
0x1800198df  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800198e4  mov     rsi, rax
0x1800198e7  test    rax, rax
0x1800198ea  jnz     short loc_18001990B
0x1800198ec  mov     rcx, [rbp+188h]; this
0x1800198f3  mov     r14d, 8007000Eh
0x1800198f9  mov     r9d, r14d; char *
0x1800198fc  mov     edx, 14Bh; void *
0x180019901  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019906  jmp     loc_180019997
0x18001990b  xorps   xmm0, xmm0
0x18001990e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180019914  test    sil, 3
0x180019918  jnz     loc_180019AAE
0x18001991e  mov     r9, rsi
0x180019921  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180019926  shr     r9, 2; unsigned __int64
0x18001992a  lea     rcx, [rsp+280h+hObject]; this
0x18001992f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180019934  mov     r14d, eax
0x180019937  test    eax, eax
0x180019939  jns     loc_1800199D7
0x18001993f  mov     rcx, [rbp+188h]; this
0x180019946  mov     r9d, eax; char *
0x180019949  mov     edx, 14Eh; void *
0x18001994e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019953  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180019958  test    rcx, rcx
0x18001995b  jz      short loc_18001996B
0x18001995d  call    cs:__imp_CloseHandle
0x180019963  test    eax, eax
0x180019965  jz      loc_180019AB4
0x18001996b  mov     rcx, [rsp+280h+hObject]; hObject
0x180019970  test    rcx, rcx
0x180019973  jz      short loc_180019983
0x180019975  call    cs:__imp_CloseHandle
0x18001997b  test    eax, eax
0x18001997d  jz      loc_180019AC6
0x180019983  call    cs:__imp_GetProcessHeap
0x180019989  mov     r8, rsi; lpMem
0x18001998c  xor     edx, edx; dwFlags
0x18001998e  mov     rcx, rax; hHeap
0x180019991  call    cs:__imp_HeapFree
0x180019997  mov     rcx, [rbp+188h]; this
0x18001999e  mov     r9d, r14d; char *
0x1800199a1  mov     edx, 137h; void *
0x1800199a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199ab  test    rdi, rdi
0x1800199ae  jz      short loc_1800199C1
0x1800199b0  mov     rcx, rdi; hMutex
0x1800199b3  call    cs:__imp_ReleaseMutex
0x1800199b9  test    eax, eax
0x1800199bb  jz      loc_180019AD8
0x1800199c1  mov     rcx, rbx; hObject
0x1800199c4  call    cs:__imp_CloseHandle
0x1800199ca  test    eax, eax
0x1800199cc  jz      loc_180019AEA
0x1800199d2  mov     eax, r14d
0x1800199d5  jmp     short loc_180019A45
0x1800199d7  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800199dc  xor     edx, edx; Val
0x1800199de  mov     dword ptr [rsi], 1
0x1800199e4  lea     rcx, [rsi+22h]; void *
0x1800199e8  mov     [rsi+8], rbx
0x1800199ec  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800199f1  lea     r8d, [rdx+56h]; Size
0x1800199f5  call    memset_0
0x1800199fa  xor     edx, edx; Val
0x1800199fc  mov     word ptr [rsi+20h], 58h ; 'X'
0x180019a02  lea     rcx, [rsi+28h]; void *
0x180019a06  mov     dword ptr [rsi+24h], 1
0x180019a0d  lea     r8d, [rdx+50h]; Size
0x180019a11  call    memset_0
0x180019a16  xor     ebx, ebx
0x180019a18  mov     [r15], rsi
0x180019a1b  test    rdi, rdi
0x180019a1e  jz      short loc_180019A31
0x180019a20  mov     rcx, rdi; hMutex
0x180019a23  call    cs:__imp_ReleaseMutex
0x180019a29  test    eax, eax
0x180019a2b  jz      loc_180019AFC
0x180019a31  test    rbx, rbx
0x180019a34  jz      short loc_180019A43
0x180019a36  mov     rcx, rbx; hObject
0x180019a39  call    cs:__imp_CloseHandle
0x180019a3f  test    eax, eax
0x180019a41  jz      short loc_180019A6B
0x180019a43  xor     eax, eax
0x180019a45  mov     rcx, [rbp+180h+var_30]
0x180019a4c  xor     rcx, rsp; StackCookie
0x180019a4f  call    __security_check_cookie
0x180019a54  mov     rbx, [rsp+280h+arg_10]
0x180019a5c  add     rsp, 260h
0x180019a63  pop     r15
0x180019a65  pop     r14
0x180019a67  pop     rdi
0x180019a68  pop     rsi
0x180019a69  pop     rbp
0x180019a6a  retn
0x180019a6b  mov     rcx, [rbp+188h]; this
0x180019a72  mov     edx, 0A0Bh; void *
0x180019a77  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019a7d  mov     rcx, [rbp+188h]; this
0x180019a84  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180019a8a  mov     rcx, [rbp+188h]; this
0x180019a91  mov     edx, 0A15h; void *
0x180019a96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019a9c  mov     rcx, [rbp+188h]; this
0x180019aa3  mov     edx, 0A0Bh; void *
0x180019aa8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019aae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180019ab4  mov     rcx, [rbp+188h]; this
0x180019abb  mov     edx, 0A0Bh; void *
0x180019ac0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019ac6  mov     rcx, [rbp+188h]; this
0x180019acd  mov     edx, 0A0Bh; void *
0x180019ad2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019ad8  mov     rcx, [rbp+188h]; this
0x180019adf  mov     edx, 0A15h; void *
0x180019ae4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019aea  mov     rcx, [rbp+188h]; this
0x180019af1  mov     edx, 0A0Bh; void *
0x180019af6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019afc  mov     rcx, [rbp+188h]; this
0x180019b03  mov     edx, 0A15h; void *
0x180019b08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
