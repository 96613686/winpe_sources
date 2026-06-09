# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006128`
- end: `0x1800064f0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007c08`

## callees

- `0x1800021c0`
- `0x180002c04`
- `0x180006128`
- `0x1800065d4`
- `0x180006d04`
- `0x1800076b8`
- `0x18000877c`
- `0x180009544`
- `0x18000a368`
- `0x18000a44c`
- `0x18000a938`
- `0x18000a948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800061a0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800061a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006257`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006395`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006405`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006257`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006395`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006405`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800061c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800061c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000635e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000635e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000636c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000636c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006161`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006161`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006268`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000641b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006268`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800063a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000641b`

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
0x180006128  mov     [rsp-8+arg_10], rbx
0x18000612d  push    rbp
0x18000612e  push    rsi
0x18000612f  push    rdi
0x180006130  push    r14
0x180006132  push    r15
0x180006134  lea     rbp, [rsp-160h]
0x18000613c  sub     rsp, 260h
0x180006143  mov     rax, cs:__security_cookie
0x18000614a  xor     rax, rsp
0x18000614d  mov     [rbp+180h+var_30], rax
0x180006154  mov     r15, rdx
0x180006157  mov     qword ptr [rdx], 0
0x18000615e  mov     rbx, rcx
0x180006161  call    cs:__imp_GetCurrentProcessId
0x180006167  mov     r14d, 78h ; 'x'
0x18000616d  mov     [rsp+280h+var_258], rbx
0x180006172  mov     r9d, eax
0x180006175  mov     [rsp+280h+var_260], r14d; int
0x18000617a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006181  mov     edx, 104h; unsigned __int64
0x180006186  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000618b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006190  mov     r9d, 1F0001h; dwDesiredAccess
0x180006196  lea     rdx, [rsp+280h+Name]; lpName
0x18000619b  xor     r8d, r8d; dwFlags
0x18000619e  xor     ecx, ecx; lpMutexAttributes
0x1800061a0  call    cs:__imp_CreateMutexExW
0x1800061a6  mov     rbx, rax
0x1800061a9  test    rax, rax
0x1800061ac  jnz     short loc_1800061B8
0x1800061ae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800061b3  jmp     loc_180006427
0x1800061b8  xor     r8d, r8d; bAlertable
0x1800061bb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800061be  mov     rcx, rbx; hHandle
0x1800061c1  call    cs:__imp_WaitForSingleObjectEx
0x1800061c7  cmp     eax, 102h
0x1800061cc  jz      short loc_1800061DE
0x1800061ce  test    eax, 0FFFFFF7Fh
0x1800061d3  jnz     loc_18000645F
0x1800061d9  mov     rdi, rbx
0x1800061dc  jmp     short loc_1800061E0
0x1800061de  xor     edi, edi
0x1800061e0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800061e5  mov     [rsp+280h+hObject], 0
0x1800061ee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800061f3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800061f8  mov     esi, eax
0x1800061fa  test    eax, eax
0x1800061fc  jns     short loc_18000627D
0x1800061fe  mov     rcx, [rbp+188h]; this
0x180006205  lea     r8, aWil; "wil"
0x18000620c  mov     r9d, eax; char *
0x18000620f  mov     edx, 66h ; 'f'; void *
0x180006214  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006219  mov     rcx, [rbp+188h]; this
0x180006220  lea     r8, aWil; "wil"
0x180006227  mov     r9d, esi; char *
0x18000622a  mov     edx, 6Fh ; 'o'; void *
0x18000622f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006234  mov     rcx, [rbp+188h]; this
0x18000623b  lea     r8, aWil; "wil"
0x180006242  mov     r9d, esi; char *
0x180006245  mov     edx, 12Eh; void *
0x18000624a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000624f  test    rdi, rdi
0x180006252  jz      short loc_180006265
0x180006254  mov     rcx, rdi; hMutex
0x180006257  call    cs:__imp_ReleaseMutex
0x18000625d  test    eax, eax
0x18000625f  jz      loc_18000646C
0x180006265  mov     rcx, rbx; hObject
0x180006268  call    cs:__imp_CloseHandle
0x18000626e  test    eax, eax
0x180006270  jz      loc_18000647E
0x180006276  mov     eax, esi
0x180006278  jmp     loc_180006427
0x18000627d  mov     rax, [rsp+280h+hObject]
0x180006282  lea     rcx, ds:0[rax*4]
0x18000628a  test    rcx, rcx
0x18000628d  jz      short loc_18000629D
0x18000628f  mov     [r15], rcx
0x180006292  mov     eax, [rcx]
0x180006294  inc     eax
0x180006296  mov     [rcx], eax
0x180006298  jmp     loc_1800063FD
0x18000629d  mov     rdx, r14; dwBytes
0x1800062a0  mov     qword ptr [r15], 0
0x1800062a7  mov     ecx, 8; dwFlags
0x1800062ac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800062b1  mov     rsi, rax
0x1800062b4  test    rax, rax
0x1800062b7  jnz     short loc_1800062DF
0x1800062b9  mov     rcx, [rbp+188h]; this
0x1800062c0  lea     r8, aWil; "wil"
0x1800062c7  mov     r14d, 8007000Eh
0x1800062cd  mov     edx, 14Bh; void *
0x1800062d2  mov     r9d, r14d; char *
0x1800062d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062da  jmp     loc_180006372
0x1800062df  xorps   xmm0, xmm0
0x1800062e2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800062e8  test    sil, 3
0x1800062ec  jnz     loc_180006490
0x1800062f2  mov     r9, rsi
0x1800062f5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800062fa  shr     r9, 2; unsigned __int64
0x1800062fe  lea     rcx, [rsp+280h+hObject]; this
0x180006303  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006308  mov     r14d, eax
0x18000630b  test    eax, eax
0x18000630d  jns     loc_1800063B9
0x180006313  mov     rcx, [rbp+188h]; this
0x18000631a  lea     r8, aWil; "wil"
0x180006321  mov     r9d, eax; char *
0x180006324  mov     edx, 14Eh; void *
0x180006329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000632e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006333  test    rcx, rcx
0x180006336  jz      short loc_180006346
0x180006338  call    cs:__imp_CloseHandle
0x18000633e  test    eax, eax
0x180006340  jz      loc_180006496
0x180006346  mov     rcx, [rsp+280h+hObject]; hObject
0x18000634b  test    rcx, rcx
0x18000634e  jz      short loc_18000635E
0x180006350  call    cs:__imp_CloseHandle
0x180006356  test    eax, eax
0x180006358  jz      loc_1800064A8
0x18000635e  call    cs:__imp_GetProcessHeap
0x180006364  mov     r8, rsi; lpMem
0x180006367  xor     edx, edx; dwFlags
0x180006369  mov     rcx, rax; hHeap
0x18000636c  call    cs:__imp_HeapFree
0x180006372  mov     rcx, [rbp+188h]; this
0x180006379  lea     r8, aWil; "wil"
0x180006380  mov     r9d, r14d; char *
0x180006383  mov     edx, 137h; void *
0x180006388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000638d  test    rdi, rdi
0x180006390  jz      short loc_1800063A3
0x180006392  mov     rcx, rdi; hMutex
0x180006395  call    cs:__imp_ReleaseMutex
0x18000639b  test    eax, eax
0x18000639d  jz      loc_1800064BA
0x1800063a3  mov     rcx, rbx; hObject
0x1800063a6  call    cs:__imp_CloseHandle
0x1800063ac  test    eax, eax
0x1800063ae  jz      loc_1800064CC
0x1800063b4  mov     eax, r14d
0x1800063b7  jmp     short loc_180006427
0x1800063b9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800063be  xor     edx, edx; Val
0x1800063c0  mov     dword ptr [rsi], 1
0x1800063c6  lea     rcx, [rsi+22h]; void *
0x1800063ca  mov     [rsi+8], rbx
0x1800063ce  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800063d3  lea     r8d, [rdx+56h]; Size
0x1800063d7  call    memset_0
0x1800063dc  xor     edx, edx; Val
0x1800063de  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800063e4  lea     rcx, [rsi+28h]; void *
0x1800063e8  mov     dword ptr [rsi+24h], 1
0x1800063ef  lea     r8d, [rdx+50h]; Size
0x1800063f3  call    memset_0
0x1800063f8  xor     ebx, ebx
0x1800063fa  mov     [r15], rsi
0x1800063fd  test    rdi, rdi
0x180006400  jz      short loc_180006413
0x180006402  mov     rcx, rdi; hMutex
0x180006405  call    cs:__imp_ReleaseMutex
0x18000640b  test    eax, eax
0x18000640d  jz      loc_1800064DE
0x180006413  test    rbx, rbx
0x180006416  jz      short loc_180006425
0x180006418  mov     rcx, rbx; hObject
0x18000641b  call    cs:__imp_CloseHandle
0x180006421  test    eax, eax
0x180006423  jz      short loc_18000644D
0x180006425  xor     eax, eax
0x180006427  mov     rcx, [rbp+180h+var_30]
0x18000642e  xor     rcx, rsp; StackCookie
0x180006431  call    __security_check_cookie
0x180006436  mov     rbx, [rsp+280h+arg_10]
0x18000643e  add     rsp, 260h
0x180006445  pop     r15
0x180006447  pop     r14
0x180006449  pop     rdi
0x18000644a  pop     rsi
0x18000644b  pop     rbp
0x18000644c  retn
0x18000644d  mov     rcx, [rbp+188h]; this
0x180006454  mov     edx, 0A0Bh; void *
0x180006459  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000645f  mov     rcx, [rbp+188h]; this
0x180006466  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000646c  mov     rcx, [rbp+188h]; this
0x180006473  mov     edx, 0A15h; void *
0x180006478  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000647e  mov     rcx, [rbp+188h]; this
0x180006485  mov     edx, 0A0Bh; void *
0x18000648a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006490  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006496  mov     rcx, [rbp+188h]; this
0x18000649d  mov     edx, 0A0Bh; void *
0x1800064a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800064a8  mov     rcx, [rbp+188h]; this
0x1800064af  mov     edx, 0A0Bh; void *
0x1800064b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800064ba  mov     rcx, [rbp+188h]; this
0x1800064c1  mov     edx, 0A15h; void *
0x1800064c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800064cc  mov     rcx, [rbp+188h]; this
0x1800064d3  mov     edx, 0A0Bh; void *
0x1800064d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800064de  mov     rcx, [rbp+188h]; this
0x1800064e5  mov     edx, 0A15h; void *
0x1800064ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
