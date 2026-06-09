# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009608`
- end: `0x1800099e0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000a654`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x1800093a0`
- `0x180009608`
- `0x1800099e8`
- `0x180009cf0`
- `0x18000a348`
- `0x18000abc8`
- `0x18000b064`
- `0x18000ba68`
- `0x18000bb4c`
- `0x18000c008`
- `0x18000c018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800096a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800096a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009737`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000984c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800098e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009737`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000984c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800098e3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009680`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180009680`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009815`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009823`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009823`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009641`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000985d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000985d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800098f9`

## string_xrefs

- `0x180009932`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000994b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009964`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000997d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000999c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800099b5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800099ce`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::details::in1diag3::FailFast_Unexpected(
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
0x180009608  mov     [rsp-8+arg_10], rbx
0x18000960d  push    rbp
0x18000960e  push    rsi
0x18000960f  push    rdi
0x180009610  push    r14
0x180009612  push    r15
0x180009614  lea     rbp, [rsp-160h]
0x18000961c  sub     rsp, 260h
0x180009623  mov     rax, cs:__security_cookie
0x18000962a  xor     rax, rsp
0x18000962d  mov     [rbp+180h+var_30], rax
0x180009634  mov     r15, rdx
0x180009637  mov     qword ptr [rdx], 0
0x18000963e  mov     rbx, rcx
0x180009641  call    cs:__imp_GetCurrentProcessId
0x180009647  mov     r14d, 78h ; 'x'
0x18000964d  mov     [rsp+280h+var_258], rbx
0x180009652  mov     r9d, eax
0x180009655  mov     [rsp+280h+var_260], r14d; int
0x18000965a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180009661  mov     edx, 104h; unsigned __int64
0x180009666  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000966b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180009670  mov     r9d, 1F0001h; dwDesiredAccess
0x180009676  lea     rdx, [rsp+280h+Name]; lpName
0x18000967b  xor     r8d, r8d; dwFlags
0x18000967e  xor     ecx, ecx; lpMutexAttributes
0x180009680  call    cs:__imp_CreateMutexExW
0x180009686  mov     rbx, rax
0x180009689  test    rax, rax
0x18000968c  jnz     short loc_180009698
0x18000968e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009693  jmp     loc_180009905
0x180009698  xor     r8d, r8d; bAlertable
0x18000969b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000969e  mov     rcx, rbx; hHandle
0x1800096a1  call    cs:__imp_WaitForSingleObjectEx
0x1800096a7  cmp     eax, 102h
0x1800096ac  jz      short loc_1800096BE
0x1800096ae  test    eax, 0FFFFFF7Fh
0x1800096b3  jnz     loc_180009944
0x1800096b9  mov     rdi, rbx
0x1800096bc  jmp     short loc_1800096C0
0x1800096be  xor     edi, edi
0x1800096c0  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x1800096c5  mov     [rsp+280h+var_250], 0
0x1800096ce  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1800096d3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x1800096d8  mov     esi, eax
0x1800096da  test    eax, eax
0x1800096dc  jns     short loc_18000975D
0x1800096de  mov     rcx, [rbp+188h]; this
0x1800096e5  lea     r8, aWil; "wil"
0x1800096ec  mov     r9d, eax; char *
0x1800096ef  mov     edx, 66h ; 'f'; void *
0x1800096f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096f9  mov     rcx, [rbp+188h]; this
0x180009700  lea     r8, aWil; "wil"
0x180009707  mov     r9d, esi; char *
0x18000970a  mov     edx, 6Fh ; 'o'; void *
0x18000970f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009714  mov     rcx, [rbp+188h]; this
0x18000971b  lea     r8, aWil; "wil"
0x180009722  mov     r9d, esi; char *
0x180009725  mov     edx, 12Eh; void *
0x18000972a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000972f  test    rdi, rdi
0x180009732  jz      short loc_180009745
0x180009734  mov     rcx, rdi; hMutex
0x180009737  call    cs:__imp_ReleaseMutex
0x18000973d  test    eax, eax
0x18000973f  jz      loc_18000995D
0x180009745  mov     rcx, rbx; hObject
0x180009748  call    cs:__imp_CloseHandle
0x18000974e  test    eax, eax
0x180009750  jz      loc_180009976
0x180009756  mov     eax, esi
0x180009758  jmp     loc_180009905
0x18000975d  mov     rax, [rsp+280h+var_250]
0x180009762  lea     rcx, ds:0[rax*4]
0x18000976a  test    rcx, rcx
0x18000976d  jz      short loc_18000977D
0x18000976f  mov     [r15], rcx
0x180009772  mov     eax, [rcx]
0x180009774  inc     eax
0x180009776  mov     [rcx], eax
0x180009778  jmp     loc_1800098DB
0x18000977d  mov     rdx, r14; dwBytes
0x180009780  mov     qword ptr [r15], 0
0x180009787  mov     ecx, 8; dwFlags
0x18000978c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009791  mov     rsi, rax
0x180009794  test    rax, rax
0x180009797  jnz     short loc_1800097BC
0x180009799  mov     rcx, [rbp+188h]; this
0x1800097a0  lea     r8, aWil; "wil"
0x1800097a7  mov     r14d, 8007000Eh
0x1800097ad  mov     edx, 14Bh; void *
0x1800097b2  mov     r9d, r14d; char *
0x1800097b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097ba  jmp     short loc_180009829
0x1800097bc  xorps   xmm0, xmm0
0x1800097bf  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x1800097c5  test    sil, 3
0x1800097c9  jnz     loc_18000998F
0x1800097cf  mov     r9, rsi
0x1800097d2  lea     rdx, [rsp+280h+Name]; wchar_t *
0x1800097d7  shr     r9, 2; unsigned __int64
0x1800097db  lea     rcx, [rsp+280h+var_250]; this
0x1800097e0  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x1800097e5  mov     r14d, eax
0x1800097e8  test    eax, eax
0x1800097ea  jns     loc_180009873
0x1800097f0  mov     rcx, [rbp+188h]; this
0x1800097f7  lea     r8, aWil; "wil"
0x1800097fe  mov     r9d, eax; char *
0x180009801  mov     edx, 14Eh; void *
0x180009806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000980b  lea     rcx, [rsp+280h+var_250]; this
0x180009810  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180009815  call    cs:__imp_GetProcessHeap
0x18000981b  mov     r8, rsi; lpMem
0x18000981e  xor     edx, edx; dwFlags
0x180009820  mov     rcx, rax; hHeap
0x180009823  call    cs:__imp_HeapFree
0x180009829  mov     rcx, [rbp+188h]; this
0x180009830  lea     r8, aWil; "wil"
0x180009837  mov     r9d, r14d; char *
0x18000983a  mov     edx, 137h; void *
0x18000983f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009844  test    rdi, rdi
0x180009847  jz      short loc_18000985A
0x180009849  mov     rcx, rdi; hMutex
0x18000984c  call    cs:__imp_ReleaseMutex
0x180009852  test    eax, eax
0x180009854  jz      loc_180009995
0x18000985a  mov     rcx, rbx; hObject
0x18000985d  call    cs:__imp_CloseHandle
0x180009863  test    eax, eax
0x180009865  jz      loc_1800099AE
0x18000986b  mov     eax, r14d
0x18000986e  jmp     loc_180009905
0x180009873  mov     rax, [rsp+280h+var_250]
0x180009878  lea     rcx, [rsi+22h]; void *
0x18000987c  xor     edx, edx; Val
0x18000987e  mov     [rsi+10h], rax
0x180009882  mov     rax, [rsp+280h+var_250+8]
0x180009887  mov     dword ptr [rsi], 1
0x18000988d  mov     [rsi+8], rbx
0x180009891  lea     r8d, [rdx+56h]; Size
0x180009895  mov     [rsp+280h+var_250], 0
0x18000989e  mov     [rsi+18h], rax
0x1800098a2  mov     [rsp+280h+var_250+8], 0
0x1800098ab  call    memset_0
0x1800098b0  xor     edx, edx; Val
0x1800098b2  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800098b8  lea     rcx, [rsi+28h]; void *
0x1800098bc  mov     dword ptr [rsi+24h], 1
0x1800098c3  lea     r8d, [rdx+50h]; Size
0x1800098c7  call    memset_0
0x1800098cc  lea     rcx, [rsp+280h+var_250]; this
0x1800098d1  mov     [r15], rsi
0x1800098d4  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800098d9  xor     ebx, ebx
0x1800098db  test    rdi, rdi
0x1800098de  jz      short loc_1800098F1
0x1800098e0  mov     rcx, rdi; hMutex
0x1800098e3  call    cs:__imp_ReleaseMutex
0x1800098e9  test    eax, eax
0x1800098eb  jz      loc_1800099C7
0x1800098f1  test    rbx, rbx
0x1800098f4  jz      short loc_180009903
0x1800098f6  mov     rcx, rbx; hObject
0x1800098f9  call    cs:__imp_CloseHandle
0x1800098ff  test    eax, eax
0x180009901  jz      short loc_18000992B
0x180009903  xor     eax, eax
0x180009905  mov     rcx, [rbp+180h+var_30]
0x18000990c  xor     rcx, rsp; StackCookie
0x18000990f  call    __security_check_cookie
0x180009914  mov     rbx, [rsp+280h+arg_10]
0x18000991c  add     rsp, 260h
0x180009923  pop     r15
0x180009925  pop     r14
0x180009927  pop     rdi
0x180009928  pop     rsi
0x180009929  pop     rbp
0x18000992a  retn
0x18000992b  mov     rcx, [rbp+188h]; this
0x180009932  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009939  mov     edx, 0A0Bh; void *
0x18000993e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009944  mov     rcx, [rbp+188h]; this
0x18000994b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009952  mov     edx, 0E01h; void *
0x180009957  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000995d  mov     rcx, [rbp+188h]; this
0x180009964  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000996b  mov     edx, 0A15h; void *
0x180009970  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009976  mov     rcx, [rbp+188h]; this
0x18000997d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009984  mov     edx, 0A0Bh; void *
0x180009989  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000998f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009995  mov     rcx, [rbp+188h]; this
0x18000999c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800099a3  mov     edx, 0A15h; void *
0x1800099a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800099ae  mov     rcx, [rbp+188h]; this
0x1800099b5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800099bc  mov     edx, 0A0Bh; void *
0x1800099c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800099c7  mov     rcx, [rbp+188h]; this
0x1800099ce  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800099d5  mov     edx, 0A15h; void *
0x1800099da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
