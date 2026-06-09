# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800068a8`
- end: `0x180006c46`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180008c94`

## callees

- `0x180002300`
- `0x180002de0`
- `0x1800068a8`
- `0x180007084`
- `0x1800079f4`
- `0x180008930`
- `0x180009ccc`
- `0x18000bfb4`
- `0x18000d290`
- `0x18000d71c`
- `0x18000e804`
- `0x18000e814`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006aeb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006b5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006aeb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006b5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006941`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006941`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006920`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006920`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ac9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ac9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006abb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006abb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006aad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b71`

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
0x1800068a8  mov     [rsp-8+arg_10], rbx
0x1800068ad  push    rbp
0x1800068ae  push    rsi
0x1800068af  push    rdi
0x1800068b0  push    r14
0x1800068b2  push    r15
0x1800068b4  lea     rbp, [rsp-160h]
0x1800068bc  sub     rsp, 260h
0x1800068c3  mov     rax, cs:__security_cookie
0x1800068ca  xor     rax, rsp
0x1800068cd  mov     [rbp+180h+var_30], rax
0x1800068d4  mov     r15, rdx
0x1800068d7  mov     qword ptr [rdx], 0
0x1800068de  mov     rbx, rcx
0x1800068e1  call    cs:__imp_GetCurrentProcessId
0x1800068e7  mov     r14d, 78h ; 'x'
0x1800068ed  mov     [rsp+280h+var_258], rbx
0x1800068f2  mov     r9d, eax
0x1800068f5  mov     [rsp+280h+var_260], r14d; int
0x1800068fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006901  mov     edx, 104h; unsigned __int64
0x180006906  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000690b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006910  mov     r9d, 1F0001h; dwDesiredAccess
0x180006916  lea     rdx, [rsp+280h+Name]; lpName
0x18000691b  xor     r8d, r8d; dwFlags
0x18000691e  xor     ecx, ecx; lpMutexAttributes
0x180006920  call    cs:__imp_CreateMutexExW
0x180006926  mov     rbx, rax
0x180006929  test    rax, rax
0x18000692c  jnz     short loc_180006938
0x18000692e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006933  jmp     loc_180006B7D
0x180006938  xor     r8d, r8d; bAlertable
0x18000693b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000693e  mov     rcx, rbx; hHandle
0x180006941  call    cs:__imp_WaitForSingleObjectEx
0x180006947  cmp     eax, 102h
0x18000694c  jz      short loc_18000695E
0x18000694e  test    eax, 0FFFFFF7Fh
0x180006953  jnz     loc_180006BB5
0x180006959  mov     rdi, rbx
0x18000695c  jmp     short loc_180006960
0x18000695e  xor     edi, edi
0x180006960  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006965  mov     [rsp+280h+hObject], 0
0x18000696e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006973  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006978  mov     esi, eax
0x18000697a  test    eax, eax
0x18000697c  jns     short loc_1800069E8
0x18000697e  mov     rcx, [rbp+188h]; this
0x180006985  mov     r9d, eax; char *
0x180006988  mov     edx, 66h ; 'f'; void *
0x18000698d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006992  mov     rcx, [rbp+188h]; this
0x180006999  mov     r9d, esi; char *
0x18000699c  mov     edx, 6Fh ; 'o'; void *
0x1800069a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069a6  mov     rcx, [rbp+188h]; this
0x1800069ad  mov     r9d, esi; char *
0x1800069b0  mov     edx, 12Eh; void *
0x1800069b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069ba  test    rdi, rdi
0x1800069bd  jz      short loc_1800069D0
0x1800069bf  mov     rcx, rdi; hMutex
0x1800069c2  call    cs:__imp_ReleaseMutex
0x1800069c8  test    eax, eax
0x1800069ca  jz      loc_180006BC2
0x1800069d0  mov     rcx, rbx; hObject
0x1800069d3  call    cs:__imp_CloseHandle
0x1800069d9  test    eax, eax
0x1800069db  jz      loc_180006BD4
0x1800069e1  mov     eax, esi
0x1800069e3  jmp     loc_180006B7D
0x1800069e8  mov     rax, [rsp+280h+hObject]
0x1800069ed  lea     rcx, ds:0[rax*4]
0x1800069f5  test    rcx, rcx
0x1800069f8  jz      short loc_180006A08
0x1800069fa  mov     [r15], rcx
0x1800069fd  mov     eax, [rcx]
0x1800069ff  inc     eax
0x180006a01  mov     [rcx], eax
0x180006a03  jmp     loc_180006B53
0x180006a08  mov     rdx, r14; dwBytes
0x180006a0b  mov     qword ptr [r15], 0
0x180006a12  mov     ecx, 8; dwFlags
0x180006a17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006a1c  mov     rsi, rax
0x180006a1f  test    rax, rax
0x180006a22  jnz     short loc_180006A43
0x180006a24  mov     rcx, [rbp+188h]; this
0x180006a2b  mov     r14d, 8007000Eh
0x180006a31  mov     r9d, r14d; char *
0x180006a34  mov     edx, 14Bh; void *
0x180006a39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a3e  jmp     loc_180006ACF
0x180006a43  xorps   xmm0, xmm0
0x180006a46  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006a4c  test    sil, 3
0x180006a50  jnz     loc_180006BE6
0x180006a56  mov     r9, rsi
0x180006a59  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006a5e  shr     r9, 2; unsigned __int64
0x180006a62  lea     rcx, [rsp+280h+hObject]; this
0x180006a67  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006a6c  mov     r14d, eax
0x180006a6f  test    eax, eax
0x180006a71  jns     loc_180006B0F
0x180006a77  mov     rcx, [rbp+188h]; this
0x180006a7e  mov     r9d, eax; char *
0x180006a81  mov     edx, 14Eh; void *
0x180006a86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a8b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006a90  test    rcx, rcx
0x180006a93  jz      short loc_180006AA3
0x180006a95  call    cs:__imp_CloseHandle
0x180006a9b  test    eax, eax
0x180006a9d  jz      loc_180006BEC
0x180006aa3  mov     rcx, [rsp+280h+hObject]; hObject
0x180006aa8  test    rcx, rcx
0x180006aab  jz      short loc_180006ABB
0x180006aad  call    cs:__imp_CloseHandle
0x180006ab3  test    eax, eax
0x180006ab5  jz      loc_180006BFE
0x180006abb  call    cs:__imp_GetProcessHeap
0x180006ac1  mov     r8, rsi; lpMem
0x180006ac4  xor     edx, edx; dwFlags
0x180006ac6  mov     rcx, rax; hHeap
0x180006ac9  call    cs:__imp_HeapFree
0x180006acf  mov     rcx, [rbp+188h]; this
0x180006ad6  mov     r9d, r14d; char *
0x180006ad9  mov     edx, 137h; void *
0x180006ade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ae3  test    rdi, rdi
0x180006ae6  jz      short loc_180006AF9
0x180006ae8  mov     rcx, rdi; hMutex
0x180006aeb  call    cs:__imp_ReleaseMutex
0x180006af1  test    eax, eax
0x180006af3  jz      loc_180006C10
0x180006af9  mov     rcx, rbx; hObject
0x180006afc  call    cs:__imp_CloseHandle
0x180006b02  test    eax, eax
0x180006b04  jz      loc_180006C22
0x180006b0a  mov     eax, r14d
0x180006b0d  jmp     short loc_180006B7D
0x180006b0f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006b14  xor     edx, edx; Val
0x180006b16  mov     dword ptr [rsi], 1
0x180006b1c  lea     rcx, [rsi+22h]; void *
0x180006b20  mov     [rsi+8], rbx
0x180006b24  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006b29  lea     r8d, [rdx+56h]; Size
0x180006b2d  call    memset_0
0x180006b32  xor     edx, edx; Val
0x180006b34  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006b3a  lea     rcx, [rsi+28h]; void *
0x180006b3e  mov     dword ptr [rsi+24h], 1
0x180006b45  lea     r8d, [rdx+50h]; Size
0x180006b49  call    memset_0
0x180006b4e  xor     ebx, ebx
0x180006b50  mov     [r15], rsi
0x180006b53  test    rdi, rdi
0x180006b56  jz      short loc_180006B69
0x180006b58  mov     rcx, rdi; hMutex
0x180006b5b  call    cs:__imp_ReleaseMutex
0x180006b61  test    eax, eax
0x180006b63  jz      loc_180006C34
0x180006b69  test    rbx, rbx
0x180006b6c  jz      short loc_180006B7B
0x180006b6e  mov     rcx, rbx; hObject
0x180006b71  call    cs:__imp_CloseHandle
0x180006b77  test    eax, eax
0x180006b79  jz      short loc_180006BA3
0x180006b7b  xor     eax, eax
0x180006b7d  mov     rcx, [rbp+180h+var_30]
0x180006b84  xor     rcx, rsp; StackCookie
0x180006b87  call    __security_check_cookie
0x180006b8c  mov     rbx, [rsp+280h+arg_10]
0x180006b94  add     rsp, 260h
0x180006b9b  pop     r15
0x180006b9d  pop     r14
0x180006b9f  pop     rdi
0x180006ba0  pop     rsi
0x180006ba1  pop     rbp
0x180006ba2  retn
0x180006ba3  mov     rcx, [rbp+188h]; this
0x180006baa  mov     edx, 0A0Bh; void *
0x180006baf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bb5  mov     rcx, [rbp+188h]; this
0x180006bbc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006bc2  mov     rcx, [rbp+188h]; this
0x180006bc9  mov     edx, 0A15h; void *
0x180006bce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bd4  mov     rcx, [rbp+188h]; this
0x180006bdb  mov     edx, 0A0Bh; void *
0x180006be0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006be6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006bec  mov     rcx, [rbp+188h]; this
0x180006bf3  mov     edx, 0A0Bh; void *
0x180006bf8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bfe  mov     rcx, [rbp+188h]; this
0x180006c05  mov     edx, 0A0Bh; void *
0x180006c0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006c10  mov     rcx, [rbp+188h]; this
0x180006c17  mov     edx, 0A15h; void *
0x180006c1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006c22  mov     rcx, [rbp+188h]; this
0x180006c29  mov     edx, 0A0Bh; void *
0x180006c2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006c34  mov     rcx, [rbp+188h]; this
0x180006c3b  mov     edx, 0A15h; void *
0x180006c40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
