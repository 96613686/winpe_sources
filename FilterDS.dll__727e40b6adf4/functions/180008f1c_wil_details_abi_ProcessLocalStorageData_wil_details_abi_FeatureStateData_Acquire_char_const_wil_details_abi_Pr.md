# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008f1c`
- end: `0x18000930d`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180009700`

## callees

- `0x180003ea0`
- `0x180004198`
- `0x1800049d8`
- `0x1800055ac`
- `0x180005ca4`
- `0x1800064d4`
- `0x1800066cc`
- `0x180006ba4`
- `0x180006bb4`
- `0x180008198`
- `0x180008f1c`
- `0x180021822`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f93`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008f93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008fb4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008fb4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800091ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800091ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000904a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009186`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009222`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000904a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009186`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000914f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000914f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000915d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000915d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008f55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000905b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009238`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000905b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009141`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009238`

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
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
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
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x180008f1c  mov     [rsp-8+arg_10], rbx
0x180008f21  push    rbp
0x180008f22  push    rsi
0x180008f23  push    rdi
0x180008f24  push    r14
0x180008f26  push    r15
0x180008f28  lea     rbp, [rsp-160h]
0x180008f30  sub     rsp, 260h
0x180008f37  mov     rax, cs:__security_cookie
0x180008f3e  xor     rax, rsp
0x180008f41  mov     [rbp+180h+var_30], rax
0x180008f48  mov     r15, rdx
0x180008f4b  mov     qword ptr [rdx], 0
0x180008f52  mov     rbx, rcx
0x180008f55  call    cs:__imp_GetCurrentProcessId
0x180008f5b  mov     r14d, 130h
0x180008f61  mov     [rsp+280h+var_258], rbx
0x180008f66  mov     r9d, eax
0x180008f69  mov     [rsp+280h+var_260], r14d; int
0x180008f6e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008f75  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008f7a  lea     edx, [r14-2Ch]; unsigned __int64
0x180008f7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008f83  mov     r9d, 1F0001h; dwDesiredAccess
0x180008f89  lea     rdx, [rsp+280h+Name]; lpName
0x180008f8e  xor     r8d, r8d; dwFlags
0x180008f91  xor     ecx, ecx; lpMutexAttributes
0x180008f93  call    cs:__imp_CreateMutexExW
0x180008f99  mov     rbx, rax
0x180008f9c  test    rax, rax
0x180008f9f  jnz     short loc_180008FAB
0x180008fa1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008fa6  jmp     loc_180009244
0x180008fab  xor     r8d, r8d; bAlertable
0x180008fae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008fb1  mov     rcx, rbx; hHandle
0x180008fb4  call    cs:__imp_WaitForSingleObjectEx
0x180008fba  cmp     eax, 102h
0x180008fbf  jz      short loc_180008FD1
0x180008fc1  test    eax, 0FFFFFF7Fh
0x180008fc6  jnz     loc_18000928E
0x180008fcc  mov     rdi, rbx
0x180008fcf  jmp     short loc_180008FD3
0x180008fd1  xor     edi, edi
0x180008fd3  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008fd8  mov     [rsp+280h+hObject], 0
0x180008fe1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008fe6  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008feb  mov     esi, eax
0x180008fed  test    eax, eax
0x180008fef  jns     short loc_180009070
0x180008ff1  mov     rcx, [rbp+188h]; this
0x180008ff8  lea     r8, aWil; "wil"
0x180008fff  mov     r9d, eax; char *
0x180009002  mov     edx, 66h ; 'f'; void *
0x180009007  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000900c  mov     rcx, [rbp+188h]; this
0x180009013  lea     r8, aWil; "wil"
0x18000901a  mov     r9d, esi; char *
0x18000901d  mov     edx, 6Fh ; 'o'; void *
0x180009022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009027  mov     rcx, [rbp+188h]; this
0x18000902e  lea     r8, aWil; "wil"
0x180009035  mov     r9d, esi; char *
0x180009038  mov     edx, 12Eh; void *
0x18000903d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009042  test    rdi, rdi
0x180009045  jz      short loc_180009058
0x180009047  mov     rcx, rdi; hMutex
0x18000904a  call    cs:__imp_ReleaseMutex
0x180009050  test    eax, eax
0x180009052  jz      loc_18000929B
0x180009058  mov     rcx, rbx; hObject
0x18000905b  call    cs:__imp_CloseHandle
0x180009061  test    eax, eax
0x180009063  jz      loc_1800092AD
0x180009069  mov     eax, esi
0x18000906b  jmp     loc_180009244
0x180009070  mov     rax, [rsp+280h+hObject]
0x180009075  lea     rcx, ds:0[rax*4]
0x18000907d  test    rcx, rcx
0x180009080  jz      short loc_180009090
0x180009082  mov     [r15], rcx
0x180009085  mov     eax, [rcx]
0x180009087  inc     eax
0x180009089  mov     [rcx], eax
0x18000908b  jmp     loc_18000921A
0x180009090  mov     rdx, r14; dwBytes
0x180009093  mov     qword ptr [r15], 0
0x18000909a  mov     ecx, 8; dwFlags
0x18000909f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800090a4  mov     r14, rax
0x1800090a7  test    rax, rax
0x1800090aa  jnz     short loc_1800090D1
0x1800090ac  mov     rcx, [rbp+188h]; this
0x1800090b3  lea     r8, aWil; "wil"
0x1800090ba  mov     esi, 8007000Eh
0x1800090bf  mov     edx, 14Bh; void *
0x1800090c4  mov     r9d, esi; char *
0x1800090c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090cc  jmp     loc_180009163
0x1800090d1  xorps   xmm0, xmm0
0x1800090d4  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800090da  test    r14b, 3
0x1800090de  jnz     loc_1800092BF
0x1800090e4  mov     r9, r14
0x1800090e7  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800090ec  shr     r9, 2; unsigned __int64
0x1800090f0  lea     rcx, [rsp+280h+hObject]; this
0x1800090f5  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800090fa  mov     esi, eax
0x1800090fc  test    eax, eax
0x1800090fe  jns     loc_1800091AA
0x180009104  mov     rcx, [rbp+188h]; this
0x18000910b  lea     r8, aWil; "wil"
0x180009112  mov     r9d, eax; char *
0x180009115  mov     edx, 14Eh; void *
0x18000911a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000911f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180009124  test    rcx, rcx
0x180009127  jz      short loc_180009137
0x180009129  call    cs:__imp_CloseHandle
0x18000912f  test    eax, eax
0x180009131  jz      loc_1800092C5
0x180009137  mov     rcx, [rsp+280h+hObject]; hObject
0x18000913c  test    rcx, rcx
0x18000913f  jz      short loc_18000914F
0x180009141  call    cs:__imp_CloseHandle
0x180009147  test    eax, eax
0x180009149  jz      loc_1800092D7
0x18000914f  call    cs:__imp_GetProcessHeap
0x180009155  mov     r8, r14; lpMem
0x180009158  xor     edx, edx; dwFlags
0x18000915a  mov     rcx, rax; hHeap
0x18000915d  call    cs:__imp_HeapFree
0x180009163  mov     rcx, [rbp+188h]; this
0x18000916a  lea     r8, aWil; "wil"
0x180009171  mov     r9d, esi; char *
0x180009174  mov     edx, 137h; void *
0x180009179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000917e  test    rdi, rdi
0x180009181  jz      short loc_180009194
0x180009183  mov     rcx, rdi; hMutex
0x180009186  call    cs:__imp_ReleaseMutex
0x18000918c  test    eax, eax
0x18000918e  jz      loc_1800092E9
0x180009194  mov     rcx, rbx; hObject
0x180009197  call    cs:__imp_CloseHandle
0x18000919d  test    eax, eax
0x18000919f  jz      loc_18000927C
0x1800091a5  jmp     loc_180009069
0x1800091aa  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800091af  lea     rcx, [r14+28h]; void *
0x1800091b3  mov     dword ptr [r14], 1
0x1800091ba  xor     edx, edx; Val
0x1800091bc  mov     [r14+8], rbx
0x1800091c0  mov     r8d, 108h; Size
0x1800091c6  movdqu  xmmword ptr [r14+10h], xmm0
0x1800091cc  call    memset_0
0x1800091d1  xor     eax, eax
0x1800091d3  lea     rcx, [r14+28h]; this
0x1800091d7  mov     [r14+20h], rax
0x1800091db  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800091e0  lea     rbx, [r14+0E8h]
0x1800091e7  xor     r8d, r8d; Flags
0x1800091ea  mov     rcx, rbx; lpCriticalSection
0x1800091ed  xor     edx, edx; dwSpinCount
0x1800091ef  call    cs:__imp_InitializeCriticalSectionEx
0x1800091f5  mov     qword ptr [rbx+28h], 0
0x1800091fd  mov     qword ptr [rbx+30h], 0
0x180009205  mov     qword ptr [rbx+38h], 0
0x18000920d  mov     qword ptr [rbx+40h], 0
0x180009215  xor     ebx, ebx
0x180009217  mov     [r15], r14
0x18000921a  test    rdi, rdi
0x18000921d  jz      short loc_180009230
0x18000921f  mov     rcx, rdi; hMutex
0x180009222  call    cs:__imp_ReleaseMutex
0x180009228  test    eax, eax
0x18000922a  jz      loc_1800092FB
0x180009230  test    rbx, rbx
0x180009233  jz      short loc_180009242
0x180009235  mov     rcx, rbx; hObject
0x180009238  call    cs:__imp_CloseHandle
0x18000923e  test    eax, eax
0x180009240  jz      short loc_18000926A
0x180009242  xor     eax, eax
0x180009244  mov     rcx, [rbp+180h+var_30]
0x18000924b  xor     rcx, rsp; StackCookie
0x18000924e  call    __security_check_cookie
0x180009253  mov     rbx, [rsp+280h+arg_10]
0x18000925b  add     rsp, 260h
0x180009262  pop     r15
0x180009264  pop     r14
0x180009266  pop     rdi
0x180009267  pop     rsi
0x180009268  pop     rbp
0x180009269  retn
0x18000926a  mov     rcx, [rbp+188h]; this
0x180009271  mov     edx, 0A0Bh; void *
0x180009276  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000927c  mov     rcx, [rbp+188h]; this
0x180009283  mov     edx, 0A0Bh; void *
0x180009288  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000928e  mov     rcx, [rbp+188h]; this
0x180009295  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000929b  mov     rcx, [rbp+188h]; this
0x1800092a2  mov     edx, 0A15h; void *
0x1800092a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092ad  mov     rcx, [rbp+188h]; this
0x1800092b4  mov     edx, 0A0Bh; void *
0x1800092b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092bf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800092c5  mov     rcx, [rbp+188h]; this
0x1800092cc  mov     edx, 0A0Bh; void *
0x1800092d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092d7  mov     rcx, [rbp+188h]; this
0x1800092de  mov     edx, 0A0Bh; void *
0x1800092e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092e9  mov     rcx, [rbp+188h]; this
0x1800092f0  mov     edx, 0A15h; void *
0x1800092f5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800092fb  mov     rcx, [rbp+188h]; this
0x180009302  mov     edx, 0A15h; void *
0x180009307  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
