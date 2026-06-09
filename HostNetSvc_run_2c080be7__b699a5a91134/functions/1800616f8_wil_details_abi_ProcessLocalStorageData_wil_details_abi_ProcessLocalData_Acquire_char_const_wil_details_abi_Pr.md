# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800616f8`
- end: `0x180061acc`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180062724`

## callees

- `0x18005f0c0`
- `0x18005ffc4`
- `0x1800616f8`
- `0x180061ad4`
- `0x180061dc4`
- `0x180062418`
- `0x180062c98`
- `0x180063094`
- `0x180063a98`
- `0x180063b7c`
- `0x180064008`
- `0x180064018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180061770`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180061770`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180061791`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180061791`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061827`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061965`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800619d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061827`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180061965`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800619d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006192e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006192e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006193c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006193c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061731`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061731`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061908`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800619eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061908`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800619eb`

## string_xrefs

- `0x180061a36`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _QWORD *v23; // rsi
  unsigned int v24; // r14d
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v15, v16);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    return v14;
  }
  v19 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v19;
    ++*v19;
    goto LABEL_28;
  }
  *a2 = 0;
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v23 = (_QWORD *)v20;
  if ( v20 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v20 & 3) != 0 )
      wil::details::in1diag3::FailFastImmediate_Unexpected(v21);
    v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v22,
            v20 >> 2);
    v24 = v25;
    if ( v25 >= 0 )
    {
      v35 = *(_OWORD *)hObject;
      *(_DWORD *)v23 = 1;
      v23[1] = v6;
      *((_OWORD *)v23 + 1) = v35;
      memset_0((char *)v23 + 34, 0, 0x56u);
      *((_WORD *)v23 + 16) = 88;
      *((_DWORD *)v23 + 9) = 1;
      memset_0(v23 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v23;
LABEL_28:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
  }
  else
  {
    v24 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v24, v42);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v24;
}

```

## disassembly

```asm
0x1800616f8  mov     [rsp-8+arg_10], rbx
0x1800616fd  push    rbp
0x1800616fe  push    rsi
0x1800616ff  push    rdi
0x180061700  push    r14
0x180061702  push    r15
0x180061704  lea     rbp, [rsp-160h]
0x18006170c  sub     rsp, 260h
0x180061713  mov     rax, cs:__security_cookie
0x18006171a  xor     rax, rsp
0x18006171d  mov     [rbp+180h+var_30], rax
0x180061724  mov     r15, rdx
0x180061727  mov     qword ptr [rdx], 0
0x18006172e  mov     rbx, rcx
0x180061731  call    cs:__imp_GetCurrentProcessId
0x180061737  mov     r14d, 78h ; 'x'
0x18006173d  mov     [rsp+280h+var_258], rbx
0x180061742  mov     r9d, eax
0x180061745  mov     [rsp+280h+var_260], r14d; int
0x18006174a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180061751  mov     edx, 104h; unsigned __int64
0x180061756  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18006175b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180061760  mov     r9d, 1F0001h; dwDesiredAccess
0x180061766  lea     rdx, [rsp+280h+Name]; lpName
0x18006176b  xor     r8d, r8d; dwFlags
0x18006176e  xor     ecx, ecx; lpMutexAttributes
0x180061770  call    cs:__imp_CreateMutexExW
0x180061776  mov     rbx, rax
0x180061779  test    rax, rax
0x18006177c  jnz     short loc_180061788
0x18006177e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180061783  jmp     loc_1800619F7
0x180061788  xor     r8d, r8d; bAlertable
0x18006178b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18006178e  mov     rcx, rbx; hHandle
0x180061791  call    cs:__imp_WaitForSingleObjectEx
0x180061797  cmp     eax, 102h
0x18006179c  jz      short loc_1800617AE
0x18006179e  test    eax, 0FFFFFF7Fh
0x1800617a3  jnz     loc_180061A2F
0x1800617a9  mov     rdi, rbx
0x1800617ac  jmp     short loc_1800617B0
0x1800617ae  xor     edi, edi
0x1800617b0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800617b5  mov     [rsp+280h+hObject], 0
0x1800617be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800617c3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800617c8  mov     esi, eax
0x1800617ca  test    eax, eax
0x1800617cc  jns     short loc_18006184D
0x1800617ce  mov     rcx, [rbp+188h]; this
0x1800617d5  lea     r8, aWil; "wil"
0x1800617dc  mov     r9d, eax; char *
0x1800617df  mov     edx, 66h ; 'f'; void *
0x1800617e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800617e9  mov     rcx, [rbp+188h]; this
0x1800617f0  lea     r8, aWil; "wil"
0x1800617f7  mov     r9d, esi; char *
0x1800617fa  mov     edx, 6Fh ; 'o'; void *
0x1800617ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061804  mov     rcx, [rbp+188h]; this
0x18006180b  lea     r8, aWil; "wil"
0x180061812  mov     r9d, esi; char *
0x180061815  mov     edx, 12Eh; void *
0x18006181a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006181f  test    rdi, rdi
0x180061822  jz      short loc_180061835
0x180061824  mov     rcx, rdi; hMutex
0x180061827  call    cs:__imp_ReleaseMutex
0x18006182d  test    eax, eax
0x18006182f  jz      loc_180061A48
0x180061835  mov     rcx, rbx; hObject
0x180061838  call    cs:__imp_CloseHandle
0x18006183e  test    eax, eax
0x180061840  jz      loc_180061A5A
0x180061846  mov     eax, esi
0x180061848  jmp     loc_1800619F7
0x18006184d  mov     rax, [rsp+280h+hObject]
0x180061852  lea     rcx, ds:0[rax*4]
0x18006185a  test    rcx, rcx
0x18006185d  jz      short loc_18006186D
0x18006185f  mov     [r15], rcx
0x180061862  mov     eax, [rcx]
0x180061864  inc     eax
0x180061866  mov     [rcx], eax
0x180061868  jmp     loc_1800619CD
0x18006186d  mov     rdx, r14; dwBytes
0x180061870  mov     qword ptr [r15], 0
0x180061877  mov     ecx, 8; dwFlags
0x18006187c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180061881  mov     rsi, rax
0x180061884  test    rax, rax
0x180061887  jnz     short loc_1800618AF
0x180061889  mov     rcx, [rbp+188h]; this
0x180061890  lea     r8, aWil; "wil"
0x180061897  mov     r14d, 8007000Eh
0x18006189d  mov     edx, 14Bh; void *
0x1800618a2  mov     r9d, r14d; char *
0x1800618a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800618aa  jmp     loc_180061942
0x1800618af  xorps   xmm0, xmm0
0x1800618b2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800618b8  test    sil, 3
0x1800618bc  jnz     loc_180061A6C
0x1800618c2  mov     r9, rsi
0x1800618c5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800618ca  shr     r9, 2; unsigned __int64
0x1800618ce  lea     rcx, [rsp+280h+hObject]; this
0x1800618d3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800618d8  mov     r14d, eax
0x1800618db  test    eax, eax
0x1800618dd  jns     loc_180061989
0x1800618e3  mov     rcx, [rbp+188h]; this
0x1800618ea  lea     r8, aWil; "wil"
0x1800618f1  mov     r9d, eax; char *
0x1800618f4  mov     edx, 14Eh; void *
0x1800618f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800618fe  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180061903  test    rcx, rcx
0x180061906  jz      short loc_180061916
0x180061908  call    cs:__imp_CloseHandle
0x18006190e  test    eax, eax
0x180061910  jz      loc_180061A72
0x180061916  mov     rcx, [rsp+280h+hObject]; hObject
0x18006191b  test    rcx, rcx
0x18006191e  jz      short loc_18006192E
0x180061920  call    cs:__imp_CloseHandle
0x180061926  test    eax, eax
0x180061928  jz      loc_180061A84
0x18006192e  call    cs:__imp_GetProcessHeap
0x180061934  mov     r8, rsi; lpMem
0x180061937  xor     edx, edx; dwFlags
0x180061939  mov     rcx, rax; hHeap
0x18006193c  call    cs:__imp_HeapFree
0x180061942  mov     rcx, [rbp+188h]; this
0x180061949  lea     r8, aWil; "wil"
0x180061950  mov     r9d, r14d; char *
0x180061953  mov     edx, 137h; void *
0x180061958  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006195d  test    rdi, rdi
0x180061960  jz      short loc_180061973
0x180061962  mov     rcx, rdi; hMutex
0x180061965  call    cs:__imp_ReleaseMutex
0x18006196b  test    eax, eax
0x18006196d  jz      loc_180061A96
0x180061973  mov     rcx, rbx; hObject
0x180061976  call    cs:__imp_CloseHandle
0x18006197c  test    eax, eax
0x18006197e  jz      loc_180061AA8
0x180061984  mov     eax, r14d
0x180061987  jmp     short loc_1800619F7
0x180061989  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18006198e  xor     edx, edx; Val
0x180061990  mov     dword ptr [rsi], 1
0x180061996  lea     rcx, [rsi+22h]; void *
0x18006199a  mov     [rsi+8], rbx
0x18006199e  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800619a3  lea     r8d, [rdx+56h]; Size
0x1800619a7  call    memset_0
0x1800619ac  xor     edx, edx; Val
0x1800619ae  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800619b4  lea     rcx, [rsi+28h]; void *
0x1800619b8  mov     dword ptr [rsi+24h], 1
0x1800619bf  lea     r8d, [rdx+50h]; Size
0x1800619c3  call    memset_0
0x1800619c8  xor     ebx, ebx
0x1800619ca  mov     [r15], rsi
0x1800619cd  test    rdi, rdi
0x1800619d0  jz      short loc_1800619E3
0x1800619d2  mov     rcx, rdi; hMutex
0x1800619d5  call    cs:__imp_ReleaseMutex
0x1800619db  test    eax, eax
0x1800619dd  jz      loc_180061ABA
0x1800619e3  test    rbx, rbx
0x1800619e6  jz      short loc_1800619F5
0x1800619e8  mov     rcx, rbx; hObject
0x1800619eb  call    cs:__imp_CloseHandle
0x1800619f1  test    eax, eax
0x1800619f3  jz      short loc_180061A1D
0x1800619f5  xor     eax, eax
0x1800619f7  mov     rcx, [rbp+180h+var_30]
0x1800619fe  xor     rcx, rsp; StackCookie
0x180061a01  call    __security_check_cookie
0x180061a06  mov     rbx, [rsp+280h+arg_10]
0x180061a0e  add     rsp, 260h
0x180061a15  pop     r15
0x180061a17  pop     r14
0x180061a19  pop     rdi
0x180061a1a  pop     rsi
0x180061a1b  pop     rbp
0x180061a1c  retn
0x180061a1d  mov     rcx, [rbp+188h]; this
0x180061a24  mov     edx, 0A0Bh; void *
0x180061a29  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061a2f  mov     rcx, [rbp+188h]; this
0x180061a36  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180061a3d  mov     edx, 0E01h; void *
0x180061a42  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180061a48  mov     rcx, [rbp+188h]; this
0x180061a4f  mov     edx, 0A15h; void *
0x180061a54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061a5a  mov     rcx, [rbp+188h]; this
0x180061a61  mov     edx, 0A0Bh; void *
0x180061a66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061a6c  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x180061a72  mov     rcx, [rbp+188h]; this
0x180061a79  mov     edx, 0A0Bh; void *
0x180061a7e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061a84  mov     rcx, [rbp+188h]; this
0x180061a8b  mov     edx, 0A0Bh; void *
0x180061a90  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061a96  mov     rcx, [rbp+188h]; this
0x180061a9d  mov     edx, 0A15h; void *
0x180061aa2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061aa8  mov     rcx, [rbp+188h]; this
0x180061aaf  mov     edx, 0A0Bh; void *
0x180061ab4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180061aba  mov     rcx, [rbp+188h]; this
0x180061ac1  mov     edx, 0A15h; void *
0x180061ac6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
