# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800114d8`
- end: `0x1800118ed`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800118f4`

## callees

- `0x18000b2d8`
- `0x18000cfac`
- `0x18000d280`
- `0x18000dbd0`
- `0x18000edc0`
- `0x18000efec`
- `0x18000f36c`
- `0x18000f6e0`
- `0x18000f6f0`
- `0x180010cd8`
- `0x1800114d8`
- `0x18001972e`
- `0x180019760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800117fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800117fd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011558`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011558`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001161f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001177d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001181e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001161f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001177d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001181e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001157f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001157f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011511`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011511`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011745`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011745`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011753`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001170c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001172b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001179e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001183b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001170c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001172b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001179e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001183b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  void *v12; // rsi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
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
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v42; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v43; // [rsp+38h] [rbp-C8h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *v45; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  v43 = Mutex;
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
  v45 = v12;
  v42 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v42);
  if ( 4 * v42 )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_30;
  }
  *a2 = 0;
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  v42 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_24:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    if ( v24 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
    }
    goto LABEL_24;
  }
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  v6 = 0;
  v43 = 0;
  *((_OWORD *)v24 + 1) = *(_OWORD *)hObject;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  *a2 = v24;
LABEL_30:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x1800114d8  mov     [rsp-8+arg_10], rbx
0x1800114dd  push    rbp
0x1800114de  push    rsi
0x1800114df  push    rdi
0x1800114e0  push    r14
0x1800114e2  push    r15
0x1800114e4  lea     rbp, [rsp-180h]
0x1800114ec  sub     rsp, 280h
0x1800114f3  mov     rax, cs:__security_cookie
0x1800114fa  xor     rax, rsp
0x1800114fd  mov     [rbp+1A0h+var_30], rax
0x180011504  mov     r15, rdx
0x180011507  mov     rbx, rcx
0x18001150a  mov     qword ptr [rdx], 0
0x180011511  call    cs:__imp_GetCurrentProcessId
0x180011517  mov     r9d, eax
0x18001151a  mov     [rsp+2A0h+var_278], rbx
0x18001151f  mov     r14d, 130h
0x180011525  mov     [rsp+2A0h+var_280], r14d; int
0x18001152a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011531  lea     edx, [r14-2Ch]; unsigned __int64
0x180011535  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18001153a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001153f  mov     [rsp+2A0h+var_268], 0
0x180011548  mov     r9d, 1F0001h; dwDesiredAccess
0x18001154e  xor     r8d, r8d; dwFlags
0x180011551  lea     rdx, [rsp+2A0h+Name]; lpName
0x180011556  xor     ecx, ecx; lpMutexAttributes
0x180011558  call    cs:__imp_CreateMutexExW
0x18001155e  mov     rbx, rax
0x180011561  mov     [rsp+2A0h+var_268], rax
0x180011566  test    rax, rax
0x180011569  jnz     short loc_180011576
0x18001156b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011570  nop
0x180011571  jmp     loc_180011847
0x180011576  xor     r8d, r8d; bAlertable
0x180011579  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001157c  mov     rcx, rbx; hHandle
0x18001157f  call    cs:__imp_WaitForSingleObjectEx
0x180011585  cmp     eax, 102h
0x18001158a  jz      short loc_18001159C
0x18001158c  test    eax, 0FFFFFF7Fh
0x180011591  jnz     loc_180011891
0x180011597  mov     rsi, rbx
0x18001159a  jmp     short loc_18001159E
0x18001159c  xor     esi, esi
0x18001159e  mov     [rsp+2A0h+var_250], rsi
0x1800115a3  mov     [rsp+2A0h+var_270], 0
0x1800115ac  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x1800115b1  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800115b6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800115bb  mov     edi, eax
0x1800115bd  test    eax, eax
0x1800115bf  jns     loc_18001164C
0x1800115c5  mov     rcx, [rbp+1A8h]; this
0x1800115cc  mov     r9d, eax; char *
0x1800115cf  lea     r8, aWil; "wil"
0x1800115d6  mov     edx, 66h ; 'f'; void *
0x1800115db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115e0  mov     rcx, [rbp+1A8h]; this
0x1800115e7  mov     r9d, edi; char *
0x1800115ea  lea     r8, aWil; "wil"
0x1800115f1  mov     edx, 6Fh ; 'o'; void *
0x1800115f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115fb  mov     rcx, [rbp+1A8h]; this
0x180011602  mov     r9d, edi; char *
0x180011605  lea     r8, aWil; "wil"
0x18001160c  mov     edx, 12Eh; void *
0x180011611  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011616  nop
0x180011617  test    rsi, rsi
0x18001161a  jz      short loc_180011634
0x18001161c  mov     rcx, rsi; hMutex
0x18001161f  call    cs:__imp_ReleaseMutex
0x180011625  mov     rcx, [rbp+1A8h]; this
0x18001162c  test    eax, eax
0x18001162e  jz      loc_18001189E
0x180011634  mov     rcx, rbx; hObject
0x180011637  call    cs:__imp_CloseHandle
0x18001163d  test    eax, eax
0x18001163f  jz      loc_1800118A9
0x180011645  mov     eax, edi
0x180011647  jmp     loc_180011847
0x18001164c  mov     rax, [rsp+2A0h+var_270]
0x180011651  lea     rcx, ds:0[rax*4]
0x180011659  test    rcx, rcx
0x18001165c  jz      short loc_18001166C
0x18001165e  mov     [r15], rcx
0x180011661  mov     eax, [rcx]
0x180011663  inc     eax
0x180011665  mov     [rcx], eax
0x180011667  jmp     loc_180011816
0x18001166c  mov     qword ptr [r15], 0
0x180011673  mov     rdx, r14; dwBytes
0x180011676  mov     ecx, 8; dwFlags
0x18001167b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011680  mov     r14, rax
0x180011683  mov     [rsp+2A0h+var_270], rax
0x180011688  test    rax, rax
0x18001168b  jnz     short loc_1800116B3
0x18001168d  mov     rcx, [rbp+1A8h]; this
0x180011694  mov     edi, 8007000Eh
0x180011699  mov     r9d, edi; char *
0x18001169c  lea     r8, aWil; "wil"
0x1800116a3  mov     edx, 14Bh; void *
0x1800116a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800116ad  nop
0x1800116ae  jmp     loc_180011759
0x1800116b3  xorps   xmm0, xmm0
0x1800116b6  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x1800116bc  test    r14b, 3
0x1800116c0  jnz     loc_1800118BB
0x1800116c6  mov     r9, r14
0x1800116c9  shr     r9, 2; unsigned __int64
0x1800116cd  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800116d2  lea     rcx, [rsp+2A0h+hObject]; this
0x1800116d7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800116dc  mov     edi, eax
0x1800116de  test    eax, eax
0x1800116e0  jns     loc_1800117B1
0x1800116e6  mov     rcx, [rbp+1A8h]; this
0x1800116ed  mov     r9d, eax; char *
0x1800116f0  lea     r8, aWil; "wil"
0x1800116f7  mov     edx, 14Eh; void *
0x1800116fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011701  nop
0x180011702  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x180011707  test    rcx, rcx
0x18001170a  jz      short loc_180011721
0x18001170c  call    cs:__imp_CloseHandle
0x180011712  mov     rcx, [rbp+1A8h]; this
0x180011719  test    eax, eax
0x18001171b  jz      loc_1800118C1
0x180011721  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180011726  test    rcx, rcx
0x180011729  jz      short loc_180011740
0x18001172b  call    cs:__imp_CloseHandle
0x180011731  mov     rcx, [rbp+1A8h]; this
0x180011738  test    eax, eax
0x18001173a  jz      loc_1800118CC
0x180011740  test    r14, r14
0x180011743  jz      short loc_180011759
0x180011745  call    cs:__imp_GetProcessHeap
0x18001174b  mov     rcx, rax; hHeap
0x18001174e  mov     r8, r14; lpMem
0x180011751  xor     edx, edx; dwFlags
0x180011753  call    cs:__imp_HeapFree
0x180011759  mov     rcx, [rbp+1A8h]; this
0x180011760  mov     r9d, edi; char *
0x180011763  lea     r8, aWil; "wil"
0x18001176a  mov     edx, 137h; void *
0x18001176f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011774  nop
0x180011775  test    rsi, rsi
0x180011778  jz      short loc_180011792
0x18001177a  mov     rcx, rsi; hMutex
0x18001177d  call    cs:__imp_ReleaseMutex
0x180011783  mov     rcx, [rbp+1A8h]; this
0x18001178a  test    eax, eax
0x18001178c  jz      loc_1800118D7
0x180011792  test    rbx, rbx
0x180011795  jz      loc_180011645
0x18001179b  mov     rcx, rbx; hObject
0x18001179e  call    cs:__imp_CloseHandle
0x1800117a4  test    eax, eax
0x1800117a6  jz      loc_18001187F
0x1800117ac  jmp     loc_180011645
0x1800117b1  mov     dword ptr [r14], 1
0x1800117b8  mov     [r14+8], rbx
0x1800117bc  xor     ebx, ebx
0x1800117be  mov     [rsp+2A0h+var_268], rbx
0x1800117c3  movups  xmm0, xmmword ptr [rsp+2A0h+hObject]
0x1800117c8  movdqu  xmmword ptr [r14+10h], xmm0
0x1800117ce  lea     rcx, [r14+28h]; void *
0x1800117d2  xor     edx, edx; Val
0x1800117d4  mov     r8d, 108h; Size
0x1800117da  call    memset_0
0x1800117df  xor     eax, eax
0x1800117e1  mov     [r14+20h], rax
0x1800117e5  lea     rcx, [r14+28h]; this
0x1800117e9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800117ee  lea     rdi, [r14+0E8h]
0x1800117f5  xor     r8d, r8d; Flags
0x1800117f8  xor     edx, edx; dwSpinCount
0x1800117fa  mov     rcx, rdi; lpCriticalSection
0x1800117fd  call    cs:__imp_InitializeCriticalSectionEx
0x180011803  mov     [rdi+28h], rbx
0x180011807  mov     [rdi+30h], rbx
0x18001180b  mov     [rdi+38h], rbx
0x18001180f  mov     [rdi+40h], rbx
0x180011813  mov     [r15], r14
0x180011816  test    rsi, rsi
0x180011819  jz      short loc_180011833
0x18001181b  mov     rcx, rsi; hMutex
0x18001181e  call    cs:__imp_ReleaseMutex
0x180011824  mov     rcx, [rbp+1A8h]; this
0x18001182b  test    eax, eax
0x18001182d  jz      loc_1800118E2
0x180011833  test    rbx, rbx
0x180011836  jz      short loc_180011845
0x180011838  mov     rcx, rbx; hObject
0x18001183b  call    cs:__imp_CloseHandle
0x180011841  test    eax, eax
0x180011843  jz      short loc_18001186D
0x180011845  xor     eax, eax
0x180011847  mov     rcx, [rbp+1A0h+var_30]
0x18001184e  xor     rcx, rsp; StackCookie
0x180011851  call    __security_check_cookie
0x180011856  mov     rbx, [rsp+2A0h+arg_10]
0x18001185e  add     rsp, 280h
0x180011865  pop     r15
0x180011867  pop     r14
0x180011869  pop     rdi
0x18001186a  pop     rsi
0x18001186b  pop     rbp
0x18001186c  retn
0x18001186d  mov     rcx, [rbp+1A8h]; this
0x180011874  mov     edx, 0A0Bh; void *
0x180011879  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001187f  mov     rcx, [rbp+1A8h]; this
0x180011886  mov     edx, 0A0Bh; void *
0x18001188b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011891  mov     rcx, [rbp+1A8h]; this
0x180011898  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001189e  mov     edx, 0A15h; void *
0x1800118a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800118a9  mov     rcx, [rbp+1A8h]; this
0x1800118b0  mov     edx, 0A0Bh; void *
0x1800118b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800118bb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800118c1  mov     edx, 0A0Bh; void *
0x1800118c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800118cc  mov     edx, 0A0Bh; void *
0x1800118d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800118d7  mov     edx, 0A15h; void *
0x1800118dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800118e2  mov     edx, 0A15h; void *
0x1800118e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
