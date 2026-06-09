# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005e38`
- end: `0x180006235`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x180006a64`

## callees

- `0x180002590`
- `0x180002f98`
- `0x180004c50`
- `0x1800054cc`
- `0x180005e38`
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

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005e71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005e71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006050`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006050`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006042`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005eaf`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005eaf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006079`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006138`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006079`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006138`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ed0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005ed0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800060fb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800060fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000608a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000614e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000608a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000614e`

## string_xrefs

- `0x180006187`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800061a0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800061b9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800061d2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800061eb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000620a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006223`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v21; // r14
  int v22; // eax
  HANDLE ProcessHeap; // rax
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v31[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v31[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, v31, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v28);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v29);
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
  v17 = (_DWORD *)(4 * v31[0]);
  if ( 4 * v31[0] )
  {
    *a2 = v17;
    ++*v17;
    goto LABEL_24;
  }
  *a2 = 0;
  v18 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v21 = (_DWORD *)v18;
  if ( !v18 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
    goto LABEL_19;
  }
  *(_OWORD *)v31 = 0;
  if ( (v18 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  v22 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)v31,
          Name,
          v20,
          v18 >> 2);
  v14 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v22, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
LABEL_19:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v30);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return v14;
  }
  *((_QWORD *)v21 + 2) = v31[0];
  *((_QWORD *)v21 + 3) = v31[1];
  *v21 = 1;
  *((_QWORD *)v21 + 1) = v6;
  v31[0] = 0;
  v31[1] = 0;
  memset_0(v21 + 10, 0, 0x108u);
  *((_QWORD *)v21 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v21 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v21 + 58), 0, 0);
  *((_QWORD *)v21 + 34) = 0;
  *((_QWORD *)v21 + 35) = 0;
  *((_QWORD *)v21 + 36) = 0;
  *((_QWORD *)v21 + 37) = 0;
  *a2 = v21;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v31);
  v6 = 0;
LABEL_24:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v26);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v27);
  return 0;
}

```

## disassembly

```asm
0x180005e38  mov     [rsp-8+arg_10], rbx
0x180005e3d  push    rbp
0x180005e3e  push    rsi
0x180005e3f  push    rdi
0x180005e40  push    r14
0x180005e42  push    r15
0x180005e44  lea     rbp, [rsp-160h]
0x180005e4c  sub     rsp, 260h
0x180005e53  mov     rax, cs:__security_cookie
0x180005e5a  xor     rax, rsp
0x180005e5d  mov     [rbp+180h+var_30], rax
0x180005e64  mov     r15, rdx
0x180005e67  mov     qword ptr [rdx], 0
0x180005e6e  mov     rbx, rcx
0x180005e71  call    cs:__imp_GetCurrentProcessId
0x180005e77  mov     r14d, 130h
0x180005e7d  mov     [rsp+280h+var_258], rbx
0x180005e82  mov     r9d, eax
0x180005e85  mov     [rsp+280h+var_260], r14d; int
0x180005e8a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005e91  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005e96  lea     edx, [r14-2Ch]; unsigned __int64
0x180005e9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005e9f  mov     r9d, 1F0001h; dwDesiredAccess
0x180005ea5  lea     rdx, [rsp+280h+Name]; lpName
0x180005eaa  xor     r8d, r8d; dwFlags
0x180005ead  xor     ecx, ecx; lpMutexAttributes
0x180005eaf  call    cs:__imp_CreateMutexExW
0x180005eb5  mov     rbx, rax
0x180005eb8  test    rax, rax
0x180005ebb  jnz     short loc_180005EC7
0x180005ebd  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005ec2  jmp     loc_18000615A
0x180005ec7  xor     r8d, r8d; bAlertable
0x180005eca  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005ecd  mov     rcx, rbx; hHandle
0x180005ed0  call    cs:__imp_WaitForSingleObjectEx
0x180005ed6  cmp     eax, 102h
0x180005edb  jz      short loc_180005EED
0x180005edd  test    eax, 0FFFFFF7Fh
0x180005ee2  jnz     loc_1800061B2
0x180005ee8  mov     rdi, rbx
0x180005eeb  jmp     short loc_180005EEF
0x180005eed  xor     edi, edi
0x180005eef  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180005ef4  mov     [rsp+280h+var_250], 0
0x180005efd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005f02  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005f07  mov     esi, eax
0x180005f09  test    eax, eax
0x180005f0b  jns     short loc_180005F8C
0x180005f0d  mov     rcx, [rbp+188h]; this
0x180005f14  lea     r8, aWil; "wil"
0x180005f1b  mov     r9d, eax; char *
0x180005f1e  mov     edx, 66h ; 'f'; void *
0x180005f23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f28  mov     rcx, [rbp+188h]; this
0x180005f2f  lea     r8, aWil; "wil"
0x180005f36  mov     r9d, esi; char *
0x180005f39  mov     edx, 6Fh ; 'o'; void *
0x180005f3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f43  mov     rcx, [rbp+188h]; this
0x180005f4a  lea     r8, aWil; "wil"
0x180005f51  mov     r9d, esi; char *
0x180005f54  mov     edx, 12Eh; void *
0x180005f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f5e  test    rdi, rdi
0x180005f61  jz      short loc_180005F74
0x180005f63  mov     rcx, rdi; hMutex
0x180005f66  call    cs:__imp_ReleaseMutex
0x180005f6c  test    eax, eax
0x180005f6e  jz      loc_1800061CB
0x180005f74  mov     rcx, rbx; hObject
0x180005f77  call    cs:__imp_CloseHandle
0x180005f7d  test    eax, eax
0x180005f7f  jz      loc_1800061E4
0x180005f85  mov     eax, esi
0x180005f87  jmp     loc_18000615A
0x180005f8c  mov     rax, [rsp+280h+var_250]
0x180005f91  lea     rcx, ds:0[rax*4]
0x180005f99  test    rcx, rcx
0x180005f9c  jz      short loc_180005FAC
0x180005f9e  mov     [r15], rcx
0x180005fa1  mov     eax, [rcx]
0x180005fa3  inc     eax
0x180005fa5  mov     [rcx], eax
0x180005fa7  jmp     loc_180006130
0x180005fac  mov     rdx, r14; dwBytes
0x180005faf  mov     qword ptr [r15], 0
0x180005fb6  mov     ecx, 8; dwFlags
0x180005fbb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005fc0  mov     r14, rax
0x180005fc3  test    rax, rax
0x180005fc6  jnz     short loc_180005FEA
0x180005fc8  mov     rcx, [rbp+188h]; this
0x180005fcf  lea     r8, aWil; "wil"
0x180005fd6  mov     esi, 8007000Eh
0x180005fdb  mov     edx, 14Bh; void *
0x180005fe0  mov     r9d, esi; char *
0x180005fe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fe8  jmp     short loc_180006056
0x180005fea  xorps   xmm0, xmm0
0x180005fed  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180005ff3  test    r14b, 3
0x180005ff7  jnz     loc_1800061FD
0x180005ffd  mov     r9, r14
0x180006000  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006005  shr     r9, 2; unsigned __int64
0x180006009  lea     rcx, [rsp+280h+var_250]; this
0x18000600e  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006013  mov     esi, eax
0x180006015  test    eax, eax
0x180006017  jns     loc_18000609D
0x18000601d  mov     rcx, [rbp+188h]; this
0x180006024  lea     r8, aWil; "wil"
0x18000602b  mov     r9d, eax; char *
0x18000602e  mov     edx, 14Eh; void *
0x180006033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006038  lea     rcx, [rsp+280h+var_250]; this
0x18000603d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180006042  call    cs:__imp_GetProcessHeap
0x180006048  mov     r8, r14; lpMem
0x18000604b  xor     edx, edx; dwFlags
0x18000604d  mov     rcx, rax; hHeap
0x180006050  call    cs:__imp_HeapFree
0x180006056  mov     rcx, [rbp+188h]; this
0x18000605d  lea     r8, aWil; "wil"
0x180006064  mov     r9d, esi; char *
0x180006067  mov     edx, 137h; void *
0x18000606c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006071  test    rdi, rdi
0x180006074  jz      short loc_180006087
0x180006076  mov     rcx, rdi; hMutex
0x180006079  call    cs:__imp_ReleaseMutex
0x18000607f  test    eax, eax
0x180006081  jz      loc_180006203
0x180006087  mov     rcx, rbx; hObject
0x18000608a  call    cs:__imp_CloseHandle
0x180006090  test    eax, eax
0x180006092  jz      loc_180006199
0x180006098  jmp     loc_180005F85
0x18000609d  mov     rax, [rsp+280h+var_250]
0x1800060a2  lea     rcx, [r14+28h]; void *
0x1800060a6  mov     [r14+10h], rax
0x1800060aa  xor     edx, edx; Val
0x1800060ac  mov     rax, [rsp+280h+var_250+8]
0x1800060b1  mov     r8d, 108h; Size
0x1800060b7  mov     [r14+18h], rax
0x1800060bb  mov     dword ptr [r14], 1
0x1800060c2  mov     [r14+8], rbx
0x1800060c6  mov     [rsp+280h+var_250], 0
0x1800060cf  mov     [rsp+280h+var_250+8], 0
0x1800060d8  call    memset_0
0x1800060dd  xor     eax, eax
0x1800060df  lea     rcx, [r14+28h]; this
0x1800060e3  mov     [r14+20h], rax
0x1800060e7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800060ec  lea     rbx, [r14+0E8h]
0x1800060f3  xor     r8d, r8d; Flags
0x1800060f6  mov     rcx, rbx; lpCriticalSection
0x1800060f9  xor     edx, edx; dwSpinCount
0x1800060fb  call    cs:__imp_InitializeCriticalSectionEx
0x180006101  mov     qword ptr [rbx+28h], 0
0x180006109  lea     rcx, [rsp+280h+var_250]; this
0x18000610e  mov     qword ptr [rbx+30h], 0
0x180006116  mov     qword ptr [rbx+38h], 0
0x18000611e  mov     qword ptr [rbx+40h], 0
0x180006126  mov     [r15], r14
0x180006129  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000612e  xor     ebx, ebx
0x180006130  test    rdi, rdi
0x180006133  jz      short loc_180006146
0x180006135  mov     rcx, rdi; hMutex
0x180006138  call    cs:__imp_ReleaseMutex
0x18000613e  test    eax, eax
0x180006140  jz      loc_18000621C
0x180006146  test    rbx, rbx
0x180006149  jz      short loc_180006158
0x18000614b  mov     rcx, rbx; hObject
0x18000614e  call    cs:__imp_CloseHandle
0x180006154  test    eax, eax
0x180006156  jz      short loc_180006180
0x180006158  xor     eax, eax
0x18000615a  mov     rcx, [rbp+180h+var_30]
0x180006161  xor     rcx, rsp; StackCookie
0x180006164  call    __security_check_cookie
0x180006169  mov     rbx, [rsp+280h+arg_10]
0x180006171  add     rsp, 260h
0x180006178  pop     r15
0x18000617a  pop     r14
0x18000617c  pop     rdi
0x18000617d  pop     rsi
0x18000617e  pop     rbp
0x18000617f  retn
0x180006180  mov     rcx, [rbp+188h]; this
0x180006187  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000618e  mov     edx, 0A0Bh; void *
0x180006193  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006199  mov     rcx, [rbp+188h]; this
0x1800061a0  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800061a7  mov     edx, 0A0Bh; void *
0x1800061ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061b2  mov     rcx, [rbp+188h]; this
0x1800061b9  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800061c0  mov     edx, 0E01h; void *
0x1800061c5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800061cb  mov     rcx, [rbp+188h]; this
0x1800061d2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800061d9  mov     edx, 0A15h; void *
0x1800061de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061e4  mov     rcx, [rbp+188h]; this
0x1800061eb  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800061f2  mov     edx, 0A0Bh; void *
0x1800061f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800061fd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006203  mov     rcx, [rbp+188h]; this
0x18000620a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006211  mov     edx, 0A15h; void *
0x180006216  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000621c  mov     rcx, [rbp+188h]; this
0x180006223  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000622a  mov     edx, 0A15h; void *
0x18000622f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
