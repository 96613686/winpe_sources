# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800068a8`
- end: `0x180006c80`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180008214`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x180006540`
- `0x1800068a8`
- `0x18000708c`
- `0x1800075e4`
- `0x180007f08`
- `0x180008c98`
- `0x18000a464`
- `0x18000af64`
- `0x18000b3ec`
- `0x18000bd88`
- `0x18000bd98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006aec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006b83`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800069d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006aec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006b83`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006941`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006941`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006920`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006920`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ab5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ab5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ac3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ac3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006afd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006afd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b99`

## string_xrefs

- `0x180006bd2`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180006beb`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180006c04`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180006c1d`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180006c3c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180006c55`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180006c6e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  const char *v15; // r9
  const char *v16; // r9
  _DWORD *v17; // rcx
  unsigned __int64 v18; // rax
  wil::details::in1diag3 *v19; // rcx
  bool v20; // r8
  _QWORD *v21; // rsi
  unsigned int v22; // r14d
  int v23; // eax
  HANDLE ProcessHeap; // rax
  const char *v25; // r9
  const char *v26; // r9
  unsigned __int64 v27; // rax
  const char *v28; // r9
  const char *v29; // r9
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v10);
    v11 = v6;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v33, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v30);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v31);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v16);
    return v14;
  }
  v17 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v13);
  v21 = (_QWORD *)v18;
  if ( v18 )
  {
    *(_OWORD *)v33 = 0;
    if ( (v18 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
    v23 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)v33,
            Name,
            v20,
            v18 >> 2);
    v22 = v23;
    if ( v23 >= 0 )
    {
      v21[2] = v33[0];
      v27 = v33[1];
      *(_DWORD *)v21 = 1;
      v21[1] = v6;
      v33[0] = 0;
      v21[3] = v27;
      v33[1] = 0;
      memset_0((char *)v21 + 34, 0, 0x56u);
      *((_WORD *)v21 + 16) = 88;
      *((_DWORD *)v21 + 9) = 1;
      memset_0(v21 + 5, 0, 0x50u);
      *a2 = v21;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
      v6 = 0;
LABEL_24:
      if ( v11 && !ReleaseMutex(v11) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA15,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v29);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v23, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  else
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v22, v32);
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v25);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v26);
  return v22;
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
0x180006906  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000690b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180006910  mov     r9d, 1F0001h; dwDesiredAccess
0x180006916  lea     rdx, [rsp+280h+Name]; lpName
0x18000691b  xor     r8d, r8d; dwFlags
0x18000691e  xor     ecx, ecx; lpMutexAttributes
0x180006920  call    cs:__imp_CreateMutexExW
0x180006926  mov     rbx, rax
0x180006929  test    rax, rax
0x18000692c  jnz     short loc_180006938
0x18000692e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006933  jmp     loc_180006BA5
0x180006938  xor     r8d, r8d; bAlertable
0x18000693b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000693e  mov     rcx, rbx; hHandle
0x180006941  call    cs:__imp_WaitForSingleObjectEx
0x180006947  cmp     eax, 102h
0x18000694c  jz      short loc_18000695E
0x18000694e  test    eax, 0FFFFFF7Fh
0x180006953  jnz     loc_180006BE4
0x180006959  mov     rdi, rbx
0x18000695c  jmp     short loc_180006960
0x18000695e  xor     edi, edi
0x180006960  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180006965  mov     [rsp+280h+var_250], 0
0x18000696e  lea     rcx, [rsp+280h+Name]; wchar_t *
0x180006973  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x180006978  mov     esi, eax
0x18000697a  test    eax, eax
0x18000697c  jns     short loc_1800069FD
0x18000697e  mov     rcx, [rbp+188h]; this
0x180006985  lea     r8, aWil; "wil"
0x18000698c  mov     r9d, eax; char *
0x18000698f  mov     edx, 66h ; 'f'; void *
0x180006994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006999  mov     rcx, [rbp+188h]; this
0x1800069a0  lea     r8, aWil; "wil"
0x1800069a7  mov     r9d, esi; char *
0x1800069aa  mov     edx, 6Fh ; 'o'; void *
0x1800069af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069b4  mov     rcx, [rbp+188h]; this
0x1800069bb  lea     r8, aWil; "wil"
0x1800069c2  mov     r9d, esi; char *
0x1800069c5  mov     edx, 12Eh; void *
0x1800069ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800069cf  test    rdi, rdi
0x1800069d2  jz      short loc_1800069E5
0x1800069d4  mov     rcx, rdi; hMutex
0x1800069d7  call    cs:__imp_ReleaseMutex
0x1800069dd  test    eax, eax
0x1800069df  jz      loc_180006BFD
0x1800069e5  mov     rcx, rbx; hObject
0x1800069e8  call    cs:__imp_CloseHandle
0x1800069ee  test    eax, eax
0x1800069f0  jz      loc_180006C16
0x1800069f6  mov     eax, esi
0x1800069f8  jmp     loc_180006BA5
0x1800069fd  mov     rax, [rsp+280h+var_250]
0x180006a02  lea     rcx, ds:0[rax*4]
0x180006a0a  test    rcx, rcx
0x180006a0d  jz      short loc_180006A1D
0x180006a0f  mov     [r15], rcx
0x180006a12  mov     eax, [rcx]
0x180006a14  inc     eax
0x180006a16  mov     [rcx], eax
0x180006a18  jmp     loc_180006B7B
0x180006a1d  mov     rdx, r14; dwBytes
0x180006a20  mov     qword ptr [r15], 0
0x180006a27  mov     ecx, 8; dwFlags
0x180006a2c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006a31  mov     rsi, rax
0x180006a34  test    rax, rax
0x180006a37  jnz     short loc_180006A5C
0x180006a39  mov     rcx, [rbp+188h]; this
0x180006a40  lea     r8, aWil; "wil"
0x180006a47  mov     r14d, 8007000Eh
0x180006a4d  mov     edx, 14Bh; void *
0x180006a52  mov     r9d, r14d; char *
0x180006a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a5a  jmp     short loc_180006AC9
0x180006a5c  xorps   xmm0, xmm0
0x180006a5f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180006a65  test    sil, 3
0x180006a69  jnz     loc_180006C2F
0x180006a6f  mov     r9, rsi
0x180006a72  lea     rdx, [rsp+280h+Name]; wchar_t *
0x180006a77  shr     r9, 2; unsigned __int64
0x180006a7b  lea     rcx, [rsp+280h+var_250]; this
0x180006a80  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180006a85  mov     r14d, eax
0x180006a88  test    eax, eax
0x180006a8a  jns     loc_180006B13
0x180006a90  mov     rcx, [rbp+188h]; this
0x180006a97  lea     r8, aWil; "wil"
0x180006a9e  mov     r9d, eax; char *
0x180006aa1  mov     edx, 14Eh; void *
0x180006aa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006aab  lea     rcx, [rsp+280h+var_250]; this
0x180006ab0  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006ab5  call    cs:__imp_GetProcessHeap
0x180006abb  mov     r8, rsi; lpMem
0x180006abe  xor     edx, edx; dwFlags
0x180006ac0  mov     rcx, rax; hHeap
0x180006ac3  call    cs:__imp_HeapFree
0x180006ac9  mov     rcx, [rbp+188h]; this
0x180006ad0  lea     r8, aWil; "wil"
0x180006ad7  mov     r9d, r14d; char *
0x180006ada  mov     edx, 137h; void *
0x180006adf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ae4  test    rdi, rdi
0x180006ae7  jz      short loc_180006AFA
0x180006ae9  mov     rcx, rdi; hMutex
0x180006aec  call    cs:__imp_ReleaseMutex
0x180006af2  test    eax, eax
0x180006af4  jz      loc_180006C35
0x180006afa  mov     rcx, rbx; hObject
0x180006afd  call    cs:__imp_CloseHandle
0x180006b03  test    eax, eax
0x180006b05  jz      loc_180006C4E
0x180006b0b  mov     eax, r14d
0x180006b0e  jmp     loc_180006BA5
0x180006b13  mov     rax, [rsp+280h+var_250]
0x180006b18  lea     rcx, [rsi+22h]; void *
0x180006b1c  xor     edx, edx; Val
0x180006b1e  mov     [rsi+10h], rax
0x180006b22  mov     rax, [rsp+280h+var_250+8]
0x180006b27  mov     dword ptr [rsi], 1
0x180006b2d  mov     [rsi+8], rbx
0x180006b31  lea     r8d, [rdx+56h]; Size
0x180006b35  mov     [rsp+280h+var_250], 0
0x180006b3e  mov     [rsi+18h], rax
0x180006b42  mov     [rsp+280h+var_250+8], 0
0x180006b4b  call    memset_0
0x180006b50  xor     edx, edx; Val
0x180006b52  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006b58  lea     rcx, [rsi+28h]; void *
0x180006b5c  mov     dword ptr [rsi+24h], 1
0x180006b63  lea     r8d, [rdx+50h]; Size
0x180006b67  call    memset_0
0x180006b6c  lea     rcx, [rsp+280h+var_250]; this
0x180006b71  mov     [r15], rsi
0x180006b74  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006b79  xor     ebx, ebx
0x180006b7b  test    rdi, rdi
0x180006b7e  jz      short loc_180006B91
0x180006b80  mov     rcx, rdi; hMutex
0x180006b83  call    cs:__imp_ReleaseMutex
0x180006b89  test    eax, eax
0x180006b8b  jz      loc_180006C67
0x180006b91  test    rbx, rbx
0x180006b94  jz      short loc_180006BA3
0x180006b96  mov     rcx, rbx; hObject
0x180006b99  call    cs:__imp_CloseHandle
0x180006b9f  test    eax, eax
0x180006ba1  jz      short loc_180006BCB
0x180006ba3  xor     eax, eax
0x180006ba5  mov     rcx, [rbp+180h+var_30]
0x180006bac  xor     rcx, rsp; StackCookie
0x180006baf  call    __security_check_cookie
0x180006bb4  mov     rbx, [rsp+280h+arg_10]
0x180006bbc  add     rsp, 260h
0x180006bc3  pop     r15
0x180006bc5  pop     r14
0x180006bc7  pop     rdi
0x180006bc8  pop     rsi
0x180006bc9  pop     rbp
0x180006bca  retn
0x180006bcb  mov     rcx, [rbp+188h]; this
0x180006bd2  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006bd9  mov     edx, 0A0Bh; void *
0x180006bde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006be4  mov     rcx, [rbp+188h]; this
0x180006beb  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006bf2  mov     edx, 0E01h; void *
0x180006bf7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006bfd  mov     rcx, [rbp+188h]; this
0x180006c04  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006c0b  mov     edx, 0A15h; void *
0x180006c10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006c16  mov     rcx, [rbp+188h]; this
0x180006c1d  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006c24  mov     edx, 0A0Bh; void *
0x180006c29  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006c2f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006c35  mov     rcx, [rbp+188h]; this
0x180006c3c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006c43  mov     edx, 0A15h; void *
0x180006c48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006c4e  mov     rcx, [rbp+188h]; this
0x180006c55  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006c5c  mov     edx, 0A0Bh; void *
0x180006c61  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006c67  mov     rcx, [rbp+188h]; this
0x180006c6e  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006c75  mov     edx, 0A15h; void *
0x180006c7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
