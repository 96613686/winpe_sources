# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180007610`
- end: `0x1800079ae`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180010660`

## callees

- `0x180007610`
- `0x18000a3bc`
- `0x18000d398`
- `0x18000ea90`
- `0x180012424`
- `0x18001b214`
- `0x18001c5bc`
- `0x18001cab0`
- `0x18001dd64`
- `0x18001dd74`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007688`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180007688`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000772a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007853`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800078c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000772a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180007853`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800078c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800076a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800076a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007823`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007823`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007831`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007649`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000773b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000773b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800078d9`

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
0x180007610  mov     [rsp-8+arg_10], rbx
0x180007615  push    rbp
0x180007616  push    rsi
0x180007617  push    rdi
0x180007618  push    r14
0x18000761a  push    r15
0x18000761c  lea     rbp, [rsp-160h]
0x180007624  sub     rsp, 260h
0x18000762b  mov     rax, cs:__security_cookie
0x180007632  xor     rax, rsp
0x180007635  mov     [rbp+180h+var_30], rax
0x18000763c  mov     r15, rdx
0x18000763f  mov     qword ptr [rdx], 0
0x180007646  mov     rbx, rcx
0x180007649  call    cs:__imp_GetCurrentProcessId
0x18000764f  mov     r14d, 78h ; 'x'
0x180007655  mov     [rsp+280h+var_258], rbx
0x18000765a  mov     r9d, eax
0x18000765d  mov     [rsp+280h+var_260], r14d; int
0x180007662  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180007669  mov     edx, 104h; unsigned __int64
0x18000766e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007673  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007678  mov     r9d, 1F0001h; dwDesiredAccess
0x18000767e  lea     rdx, [rsp+280h+Name]; lpName
0x180007683  xor     r8d, r8d; dwFlags
0x180007686  xor     ecx, ecx; lpMutexAttributes
0x180007688  call    cs:__imp_CreateMutexExW
0x18000768e  mov     rbx, rax
0x180007691  test    rax, rax
0x180007694  jnz     short loc_1800076A0
0x180007696  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000769b  jmp     loc_1800078E5
0x1800076a0  xor     r8d, r8d; bAlertable
0x1800076a3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800076a6  mov     rcx, rbx; hHandle
0x1800076a9  call    cs:__imp_WaitForSingleObjectEx
0x1800076af  cmp     eax, 102h
0x1800076b4  jz      short loc_1800076C6
0x1800076b6  test    eax, 0FFFFFF7Fh
0x1800076bb  jnz     loc_18000791D
0x1800076c1  mov     rdi, rbx
0x1800076c4  jmp     short loc_1800076C8
0x1800076c6  xor     edi, edi
0x1800076c8  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800076cd  mov     [rsp+280h+hObject], 0
0x1800076d6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800076db  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800076e0  mov     esi, eax
0x1800076e2  test    eax, eax
0x1800076e4  jns     short loc_180007750
0x1800076e6  mov     rcx, [rbp+188h]; this
0x1800076ed  mov     r9d, eax; char *
0x1800076f0  mov     edx, 66h ; 'f'; void *
0x1800076f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076fa  mov     rcx, [rbp+188h]; this
0x180007701  mov     r9d, esi; char *
0x180007704  mov     edx, 6Fh ; 'o'; void *
0x180007709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000770e  mov     rcx, [rbp+188h]; this
0x180007715  mov     r9d, esi; char *
0x180007718  mov     edx, 12Eh; void *
0x18000771d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007722  test    rdi, rdi
0x180007725  jz      short loc_180007738
0x180007727  mov     rcx, rdi; hMutex
0x18000772a  call    cs:__imp_ReleaseMutex
0x180007730  test    eax, eax
0x180007732  jz      loc_18000792A
0x180007738  mov     rcx, rbx; hObject
0x18000773b  call    cs:__imp_CloseHandle
0x180007741  test    eax, eax
0x180007743  jz      loc_18000793C
0x180007749  mov     eax, esi
0x18000774b  jmp     loc_1800078E5
0x180007750  mov     rax, [rsp+280h+hObject]
0x180007755  lea     rcx, ds:0[rax*4]
0x18000775d  test    rcx, rcx
0x180007760  jz      short loc_180007770
0x180007762  mov     [r15], rcx
0x180007765  mov     eax, [rcx]
0x180007767  inc     eax
0x180007769  mov     [rcx], eax
0x18000776b  jmp     loc_1800078BB
0x180007770  mov     rdx, r14; dwBytes
0x180007773  mov     qword ptr [r15], 0
0x18000777a  mov     ecx, 8; dwFlags
0x18000777f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007784  mov     rsi, rax
0x180007787  test    rax, rax
0x18000778a  jnz     short loc_1800077AB
0x18000778c  mov     rcx, [rbp+188h]; this
0x180007793  mov     r14d, 8007000Eh
0x180007799  mov     r9d, r14d; char *
0x18000779c  mov     edx, 14Bh; void *
0x1800077a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077a6  jmp     loc_180007837
0x1800077ab  xorps   xmm0, xmm0
0x1800077ae  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800077b4  test    sil, 3
0x1800077b8  jnz     loc_18000794E
0x1800077be  mov     r9, rsi
0x1800077c1  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800077c6  shr     r9, 2; unsigned __int64
0x1800077ca  lea     rcx, [rsp+280h+hObject]; this
0x1800077cf  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800077d4  mov     r14d, eax
0x1800077d7  test    eax, eax
0x1800077d9  jns     loc_180007877
0x1800077df  mov     rcx, [rbp+188h]; this
0x1800077e6  mov     r9d, eax; char *
0x1800077e9  mov     edx, 14Eh; void *
0x1800077ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077f3  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800077f8  test    rcx, rcx
0x1800077fb  jz      short loc_18000780B
0x1800077fd  call    cs:__imp_CloseHandle
0x180007803  test    eax, eax
0x180007805  jz      loc_180007954
0x18000780b  mov     rcx, [rsp+280h+hObject]; hObject
0x180007810  test    rcx, rcx
0x180007813  jz      short loc_180007823
0x180007815  call    cs:__imp_CloseHandle
0x18000781b  test    eax, eax
0x18000781d  jz      loc_180007966
0x180007823  call    cs:__imp_GetProcessHeap
0x180007829  mov     r8, rsi; lpMem
0x18000782c  xor     edx, edx; dwFlags
0x18000782e  mov     rcx, rax; hHeap
0x180007831  call    cs:__imp_HeapFree
0x180007837  mov     rcx, [rbp+188h]; this
0x18000783e  mov     r9d, r14d; char *
0x180007841  mov     edx, 137h; void *
0x180007846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000784b  test    rdi, rdi
0x18000784e  jz      short loc_180007861
0x180007850  mov     rcx, rdi; hMutex
0x180007853  call    cs:__imp_ReleaseMutex
0x180007859  test    eax, eax
0x18000785b  jz      loc_180007978
0x180007861  mov     rcx, rbx; hObject
0x180007864  call    cs:__imp_CloseHandle
0x18000786a  test    eax, eax
0x18000786c  jz      loc_18000798A
0x180007872  mov     eax, r14d
0x180007875  jmp     short loc_1800078E5
0x180007877  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000787c  xor     edx, edx; Val
0x18000787e  mov     dword ptr [rsi], 1
0x180007884  lea     rcx, [rsi+22h]; void *
0x180007888  mov     [rsi+8], rbx
0x18000788c  movdqu  xmmword ptr [rsi+10h], xmm0
0x180007891  lea     r8d, [rdx+56h]; Size
0x180007895  call    memset_0
0x18000789a  xor     edx, edx; Val
0x18000789c  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800078a2  lea     rcx, [rsi+28h]; void *
0x1800078a6  mov     dword ptr [rsi+24h], 1
0x1800078ad  lea     r8d, [rdx+50h]; Size
0x1800078b1  call    memset_0
0x1800078b6  xor     ebx, ebx
0x1800078b8  mov     [r15], rsi
0x1800078bb  test    rdi, rdi
0x1800078be  jz      short loc_1800078D1
0x1800078c0  mov     rcx, rdi; hMutex
0x1800078c3  call    cs:__imp_ReleaseMutex
0x1800078c9  test    eax, eax
0x1800078cb  jz      loc_18000799C
0x1800078d1  test    rbx, rbx
0x1800078d4  jz      short loc_1800078E3
0x1800078d6  mov     rcx, rbx; hObject
0x1800078d9  call    cs:__imp_CloseHandle
0x1800078df  test    eax, eax
0x1800078e1  jz      short loc_18000790B
0x1800078e3  xor     eax, eax
0x1800078e5  mov     rcx, [rbp+180h+var_30]
0x1800078ec  xor     rcx, rsp; StackCookie
0x1800078ef  call    __security_check_cookie
0x1800078f4  mov     rbx, [rsp+280h+arg_10]
0x1800078fc  add     rsp, 260h
0x180007903  pop     r15
0x180007905  pop     r14
0x180007907  pop     rdi
0x180007908  pop     rsi
0x180007909  pop     rbp
0x18000790a  retn
0x18000790b  mov     rcx, [rbp+188h]; this
0x180007912  mov     edx, 0A0Bh; void *
0x180007917  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000791d  mov     rcx, [rbp+188h]; this
0x180007924  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000792a  mov     rcx, [rbp+188h]; this
0x180007931  mov     edx, 0A15h; void *
0x180007936  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000793c  mov     rcx, [rbp+188h]; this
0x180007943  mov     edx, 0A0Bh; void *
0x180007948  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000794e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007954  mov     rcx, [rbp+188h]; this
0x18000795b  mov     edx, 0A0Bh; void *
0x180007960  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007966  mov     rcx, [rbp+188h]; this
0x18000796d  mov     edx, 0A0Bh; void *
0x180007972  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007978  mov     rcx, [rbp+188h]; this
0x18000797f  mov     edx, 0A15h; void *
0x180007984  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000798a  mov     rcx, [rbp+188h]; this
0x180007991  mov     edx, 0A0Bh; void *
0x180007996  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000799c  mov     rcx, [rbp+188h]; this
0x1800079a3  mov     edx, 0A15h; void *
0x1800079a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
