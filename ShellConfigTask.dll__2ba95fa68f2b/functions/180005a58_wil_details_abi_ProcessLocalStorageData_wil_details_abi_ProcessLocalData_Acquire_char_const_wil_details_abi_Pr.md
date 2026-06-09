# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005a58`
- end: `0x180005e30`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180007ef4`

## callees

- `0x180002590`
- `0x180002f98`
- `0x1800054cc`
- `0x180005a58`
- `0x180006274`
- `0x180006cb8`
- `0x180007c58`
- `0x18000882c`
- `0x18000ab14`
- `0x18000b730`
- `0x18000bbbc`
- `0x18000c5c4`
- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005a91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005c73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005c65`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005ad0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005ad0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d33`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005b87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005c9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005d33`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005af1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005af1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005cad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005d49`

## string_xrefs

- `0x180005d82`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005d9b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005db4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005dcd`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005dec`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005e05`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005e1e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v15);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v28);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA0B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v25);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  return v22;
}

```

## disassembly

```asm
0x180005a58  mov     [rsp-8+arg_10], rbx
0x180005a5d  push    rbp
0x180005a5e  push    rsi
0x180005a5f  push    rdi
0x180005a60  push    r14
0x180005a62  push    r15
0x180005a64  lea     rbp, [rsp-160h]
0x180005a6c  sub     rsp, 260h
0x180005a73  mov     rax, cs:__security_cookie
0x180005a7a  xor     rax, rsp
0x180005a7d  mov     [rbp+180h+var_30], rax
0x180005a84  mov     r15, rdx
0x180005a87  mov     qword ptr [rdx], 0
0x180005a8e  mov     rbx, rcx
0x180005a91  call    cs:__imp_GetCurrentProcessId
0x180005a97  mov     r14d, 78h ; 'x'
0x180005a9d  mov     [rsp+280h+var_258], rbx
0x180005aa2  mov     r9d, eax
0x180005aa5  mov     [rsp+280h+var_260], r14d; int
0x180005aaa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005ab1  mov     edx, 104h; unsigned __int64
0x180005ab6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005abb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005ac0  mov     r9d, 1F0001h; dwDesiredAccess
0x180005ac6  lea     rdx, [rsp+280h+Name]; lpName
0x180005acb  xor     r8d, r8d; dwFlags
0x180005ace  xor     ecx, ecx; lpMutexAttributes
0x180005ad0  call    cs:__imp_CreateMutexExW
0x180005ad6  mov     rbx, rax
0x180005ad9  test    rax, rax
0x180005adc  jnz     short loc_180005AE8
0x180005ade  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005ae3  jmp     loc_180005D55
0x180005ae8  xor     r8d, r8d; bAlertable
0x180005aeb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005aee  mov     rcx, rbx; hHandle
0x180005af1  call    cs:__imp_WaitForSingleObjectEx
0x180005af7  cmp     eax, 102h
0x180005afc  jz      short loc_180005B0E
0x180005afe  test    eax, 0FFFFFF7Fh
0x180005b03  jnz     loc_180005D94
0x180005b09  mov     rdi, rbx
0x180005b0c  jmp     short loc_180005B10
0x180005b0e  xor     edi, edi
0x180005b10  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180005b15  mov     [rsp+280h+var_250], 0
0x180005b1e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005b23  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005b28  mov     esi, eax
0x180005b2a  test    eax, eax
0x180005b2c  jns     short loc_180005BAD
0x180005b2e  mov     rcx, [rbp+188h]; this
0x180005b35  lea     r8, aWil; "wil"
0x180005b3c  mov     r9d, eax; char *
0x180005b3f  mov     edx, 66h ; 'f'; void *
0x180005b44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b49  mov     rcx, [rbp+188h]; this
0x180005b50  lea     r8, aWil; "wil"
0x180005b57  mov     r9d, esi; char *
0x180005b5a  mov     edx, 6Fh ; 'o'; void *
0x180005b5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b64  mov     rcx, [rbp+188h]; this
0x180005b6b  lea     r8, aWil; "wil"
0x180005b72  mov     r9d, esi; char *
0x180005b75  mov     edx, 12Eh; void *
0x180005b7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b7f  test    rdi, rdi
0x180005b82  jz      short loc_180005B95
0x180005b84  mov     rcx, rdi; hMutex
0x180005b87  call    cs:__imp_ReleaseMutex
0x180005b8d  test    eax, eax
0x180005b8f  jz      loc_180005DAD
0x180005b95  mov     rcx, rbx; hObject
0x180005b98  call    cs:__imp_CloseHandle
0x180005b9e  test    eax, eax
0x180005ba0  jz      loc_180005DC6
0x180005ba6  mov     eax, esi
0x180005ba8  jmp     loc_180005D55
0x180005bad  mov     rax, [rsp+280h+var_250]
0x180005bb2  lea     rcx, ds:0[rax*4]
0x180005bba  test    rcx, rcx
0x180005bbd  jz      short loc_180005BCD
0x180005bbf  mov     [r15], rcx
0x180005bc2  mov     eax, [rcx]
0x180005bc4  inc     eax
0x180005bc6  mov     [rcx], eax
0x180005bc8  jmp     loc_180005D2B
0x180005bcd  mov     rdx, r14; dwBytes
0x180005bd0  mov     qword ptr [r15], 0
0x180005bd7  mov     ecx, 8; dwFlags
0x180005bdc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005be1  mov     rsi, rax
0x180005be4  test    rax, rax
0x180005be7  jnz     short loc_180005C0C
0x180005be9  mov     rcx, [rbp+188h]; this
0x180005bf0  lea     r8, aWil; "wil"
0x180005bf7  mov     r14d, 8007000Eh
0x180005bfd  mov     edx, 14Bh; void *
0x180005c02  mov     r9d, r14d; char *
0x180005c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c0a  jmp     short loc_180005C79
0x180005c0c  xorps   xmm0, xmm0
0x180005c0f  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180005c15  test    sil, 3
0x180005c19  jnz     loc_180005DDF
0x180005c1f  mov     r9, rsi
0x180005c22  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005c27  shr     r9, 2; unsigned __int64
0x180005c2b  lea     rcx, [rsp+280h+var_250]; this
0x180005c30  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005c35  mov     r14d, eax
0x180005c38  test    eax, eax
0x180005c3a  jns     loc_180005CC3
0x180005c40  mov     rcx, [rbp+188h]; this
0x180005c47  lea     r8, aWil; "wil"
0x180005c4e  mov     r9d, eax; char *
0x180005c51  mov     edx, 14Eh; void *
0x180005c56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c5b  lea     rcx, [rsp+280h+var_250]; this
0x180005c60  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005c65  call    cs:__imp_GetProcessHeap
0x180005c6b  mov     r8, rsi; lpMem
0x180005c6e  xor     edx, edx; dwFlags
0x180005c70  mov     rcx, rax; hHeap
0x180005c73  call    cs:__imp_HeapFree
0x180005c79  mov     rcx, [rbp+188h]; this
0x180005c80  lea     r8, aWil; "wil"
0x180005c87  mov     r9d, r14d; char *
0x180005c8a  mov     edx, 137h; void *
0x180005c8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c94  test    rdi, rdi
0x180005c97  jz      short loc_180005CAA
0x180005c99  mov     rcx, rdi; hMutex
0x180005c9c  call    cs:__imp_ReleaseMutex
0x180005ca2  test    eax, eax
0x180005ca4  jz      loc_180005DE5
0x180005caa  mov     rcx, rbx; hObject
0x180005cad  call    cs:__imp_CloseHandle
0x180005cb3  test    eax, eax
0x180005cb5  jz      loc_180005DFE
0x180005cbb  mov     eax, r14d
0x180005cbe  jmp     loc_180005D55
0x180005cc3  mov     rax, [rsp+280h+var_250]
0x180005cc8  lea     rcx, [rsi+22h]; void *
0x180005ccc  xor     edx, edx; Val
0x180005cce  mov     [rsi+10h], rax
0x180005cd2  mov     rax, [rsp+280h+var_250+8]
0x180005cd7  mov     dword ptr [rsi], 1
0x180005cdd  mov     [rsi+8], rbx
0x180005ce1  lea     r8d, [rdx+56h]; Size
0x180005ce5  mov     [rsp+280h+var_250], 0
0x180005cee  mov     [rsi+18h], rax
0x180005cf2  mov     [rsp+280h+var_250+8], 0
0x180005cfb  call    memset_0
0x180005d00  xor     edx, edx; Val
0x180005d02  mov     word ptr [rsi+20h], 58h ; 'X'
0x180005d08  lea     rcx, [rsi+28h]; void *
0x180005d0c  mov     dword ptr [rsi+24h], 1
0x180005d13  lea     r8d, [rdx+50h]; Size
0x180005d17  call    memset_0
0x180005d1c  lea     rcx, [rsp+280h+var_250]; this
0x180005d21  mov     [r15], rsi
0x180005d24  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180005d29  xor     ebx, ebx
0x180005d2b  test    rdi, rdi
0x180005d2e  jz      short loc_180005D41
0x180005d30  mov     rcx, rdi; hMutex
0x180005d33  call    cs:__imp_ReleaseMutex
0x180005d39  test    eax, eax
0x180005d3b  jz      loc_180005E17
0x180005d41  test    rbx, rbx
0x180005d44  jz      short loc_180005D53
0x180005d46  mov     rcx, rbx; hObject
0x180005d49  call    cs:__imp_CloseHandle
0x180005d4f  test    eax, eax
0x180005d51  jz      short loc_180005D7B
0x180005d53  xor     eax, eax
0x180005d55  mov     rcx, [rbp+180h+var_30]
0x180005d5c  xor     rcx, rsp; StackCookie
0x180005d5f  call    __security_check_cookie
0x180005d64  mov     rbx, [rsp+280h+arg_10]
0x180005d6c  add     rsp, 260h
0x180005d73  pop     r15
0x180005d75  pop     r14
0x180005d77  pop     rdi
0x180005d78  pop     rsi
0x180005d79  pop     rbp
0x180005d7a  retn
0x180005d7b  mov     rcx, [rbp+188h]; this
0x180005d82  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005d89  mov     edx, 0A0Bh; void *
0x180005d8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005d94  mov     rcx, [rbp+188h]; this
0x180005d9b  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005da2  mov     edx, 0E01h; void *
0x180005da7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005dad  mov     rcx, [rbp+188h]; this
0x180005db4  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005dbb  mov     edx, 0A15h; void *
0x180005dc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005dc6  mov     rcx, [rbp+188h]; this
0x180005dcd  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005dd4  mov     edx, 0A0Bh; void *
0x180005dd9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005ddf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005de5  mov     rcx, [rbp+188h]; this
0x180005dec  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005df3  mov     edx, 0A15h; void *
0x180005df8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005dfe  mov     rcx, [rbp+188h]; this
0x180005e05  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005e0c  mov     edx, 0A0Bh; void *
0x180005e11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005e17  mov     rcx, [rbp+188h]; this
0x180005e1e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005e25  mov     edx, 0A15h; void *
0x180005e2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
