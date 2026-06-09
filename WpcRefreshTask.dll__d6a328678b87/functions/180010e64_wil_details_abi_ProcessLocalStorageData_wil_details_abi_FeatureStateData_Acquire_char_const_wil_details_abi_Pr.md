# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180010e64`
- end: `0x180011255`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800112d8`

## callees

- `0x1800060a0`
- `0x180006ed4`
- `0x18000b734`
- `0x18000baf4`
- `0x18000c1c8`
- `0x18000cdc8`
- `0x18000d294`
- `0x18000dc84`
- `0x18000dea8`
- `0x18000e58c`
- `0x18000e59c`
- `0x180010210`
- `0x180010e64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010e9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010e9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011097`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011097`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011089`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010fa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011089`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800110df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011180`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010f92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800110ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001116a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180010f92`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800110ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001116a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011137`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180011137`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010efc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010efc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010edb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180010edb`

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
0x180010e64  mov     [rsp-8+arg_10], rbx
0x180010e69  push    rbp
0x180010e6a  push    rsi
0x180010e6b  push    rdi
0x180010e6c  push    r14
0x180010e6e  push    r15
0x180010e70  lea     rbp, [rsp-160h]
0x180010e78  sub     rsp, 260h
0x180010e7f  mov     rax, cs:__security_cookie
0x180010e86  xor     rax, rsp
0x180010e89  mov     [rbp+180h+var_30], rax
0x180010e90  mov     r15, rdx
0x180010e93  mov     qword ptr [rdx], 0
0x180010e9a  mov     rbx, rcx
0x180010e9d  call    cs:__imp_GetCurrentProcessId
0x180010ea3  mov     r14d, 130h
0x180010ea9  mov     [rsp+280h+var_258], rbx
0x180010eae  mov     r9d, eax
0x180010eb1  mov     [rsp+280h+var_260], r14d; int
0x180010eb6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010ebd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010ec2  lea     edx, [r14-2Ch]; unsigned __int64
0x180010ec6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010ecb  mov     r9d, 1F0001h; dwDesiredAccess
0x180010ed1  lea     rdx, [rsp+280h+Name]; lpName
0x180010ed6  xor     r8d, r8d; dwFlags
0x180010ed9  xor     ecx, ecx; lpMutexAttributes
0x180010edb  call    cs:__imp_CreateMutexExW
0x180010ee1  mov     rbx, rax
0x180010ee4  test    rax, rax
0x180010ee7  jnz     short loc_180010EF3
0x180010ee9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010eee  jmp     loc_18001118C
0x180010ef3  xor     r8d, r8d; bAlertable
0x180010ef6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010ef9  mov     rcx, rbx; hHandle
0x180010efc  call    cs:__imp_WaitForSingleObjectEx
0x180010f02  cmp     eax, 102h
0x180010f07  jz      short loc_180010F19
0x180010f09  test    eax, 0FFFFFF7Fh
0x180010f0e  jnz     loc_1800111D6
0x180010f14  mov     rdi, rbx
0x180010f17  jmp     short loc_180010F1B
0x180010f19  xor     edi, edi
0x180010f1b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180010f20  mov     [rsp+280h+hObject], 0
0x180010f29  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010f2e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180010f33  mov     esi, eax
0x180010f35  test    eax, eax
0x180010f37  jns     short loc_180010FB8
0x180010f39  mov     rcx, [rbp+188h]; this
0x180010f40  lea     r8, aWil; "wil"
0x180010f47  mov     r9d, eax; char *
0x180010f4a  mov     edx, 66h ; 'f'; void *
0x180010f4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f54  mov     rcx, [rbp+188h]; this
0x180010f5b  lea     r8, aWil; "wil"
0x180010f62  mov     r9d, esi; char *
0x180010f65  mov     edx, 6Fh ; 'o'; void *
0x180010f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f6f  mov     rcx, [rbp+188h]; this
0x180010f76  lea     r8, aWil; "wil"
0x180010f7d  mov     r9d, esi; char *
0x180010f80  mov     edx, 12Eh; void *
0x180010f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010f8a  test    rdi, rdi
0x180010f8d  jz      short loc_180010FA0
0x180010f8f  mov     rcx, rdi; hMutex
0x180010f92  call    cs:__imp_ReleaseMutex
0x180010f98  test    eax, eax
0x180010f9a  jz      loc_1800111E3
0x180010fa0  mov     rcx, rbx; hObject
0x180010fa3  call    cs:__imp_CloseHandle
0x180010fa9  test    eax, eax
0x180010fab  jz      loc_1800111F5
0x180010fb1  mov     eax, esi
0x180010fb3  jmp     loc_18001118C
0x180010fb8  mov     rax, [rsp+280h+hObject]
0x180010fbd  lea     rcx, ds:0[rax*4]
0x180010fc5  test    rcx, rcx
0x180010fc8  jz      short loc_180010FD8
0x180010fca  mov     [r15], rcx
0x180010fcd  mov     eax, [rcx]
0x180010fcf  inc     eax
0x180010fd1  mov     [rcx], eax
0x180010fd3  jmp     loc_180011162
0x180010fd8  mov     rdx, r14; dwBytes
0x180010fdb  mov     qword ptr [r15], 0
0x180010fe2  mov     ecx, 8; dwFlags
0x180010fe7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010fec  mov     r14, rax
0x180010fef  test    rax, rax
0x180010ff2  jnz     short loc_180011019
0x180010ff4  mov     rcx, [rbp+188h]; this
0x180010ffb  lea     r8, aWil; "wil"
0x180011002  mov     esi, 8007000Eh
0x180011007  mov     edx, 14Bh; void *
0x18001100c  mov     r9d, esi; char *
0x18001100f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011014  jmp     loc_1800110AB
0x180011019  xorps   xmm0, xmm0
0x18001101c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180011022  test    r14b, 3
0x180011026  jnz     loc_180011207
0x18001102c  mov     r9, r14
0x18001102f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180011034  shr     r9, 2; unsigned __int64
0x180011038  lea     rcx, [rsp+280h+hObject]; this
0x18001103d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180011042  mov     esi, eax
0x180011044  test    eax, eax
0x180011046  jns     loc_1800110F2
0x18001104c  mov     rcx, [rbp+188h]; this
0x180011053  lea     r8, aWil; "wil"
0x18001105a  mov     r9d, eax; char *
0x18001105d  mov     edx, 14Eh; void *
0x180011062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011067  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18001106c  test    rcx, rcx
0x18001106f  jz      short loc_18001107F
0x180011071  call    cs:__imp_CloseHandle
0x180011077  test    eax, eax
0x180011079  jz      loc_18001120D
0x18001107f  mov     rcx, [rsp+280h+hObject]; hObject
0x180011084  test    rcx, rcx
0x180011087  jz      short loc_180011097
0x180011089  call    cs:__imp_CloseHandle
0x18001108f  test    eax, eax
0x180011091  jz      loc_18001121F
0x180011097  call    cs:__imp_GetProcessHeap
0x18001109d  mov     r8, r14; lpMem
0x1800110a0  xor     edx, edx; dwFlags
0x1800110a2  mov     rcx, rax; hHeap
0x1800110a5  call    cs:__imp_HeapFree
0x1800110ab  mov     rcx, [rbp+188h]; this
0x1800110b2  lea     r8, aWil; "wil"
0x1800110b9  mov     r9d, esi; char *
0x1800110bc  mov     edx, 137h; void *
0x1800110c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800110c6  test    rdi, rdi
0x1800110c9  jz      short loc_1800110DC
0x1800110cb  mov     rcx, rdi; hMutex
0x1800110ce  call    cs:__imp_ReleaseMutex
0x1800110d4  test    eax, eax
0x1800110d6  jz      loc_180011231
0x1800110dc  mov     rcx, rbx; hObject
0x1800110df  call    cs:__imp_CloseHandle
0x1800110e5  test    eax, eax
0x1800110e7  jz      loc_1800111C4
0x1800110ed  jmp     loc_180010FB1
0x1800110f2  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800110f7  lea     rcx, [r14+28h]; void *
0x1800110fb  mov     dword ptr [r14], 1
0x180011102  xor     edx, edx; Val
0x180011104  mov     [r14+8], rbx
0x180011108  mov     r8d, 108h; Size
0x18001110e  movdqu  xmmword ptr [r14+10h], xmm0
0x180011114  call    memset_0
0x180011119  xor     eax, eax
0x18001111b  lea     rcx, [r14+28h]; this
0x18001111f  mov     [r14+20h], rax
0x180011123  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180011128  lea     rbx, [r14+0E8h]
0x18001112f  xor     r8d, r8d; Flags
0x180011132  mov     rcx, rbx; lpCriticalSection
0x180011135  xor     edx, edx; dwSpinCount
0x180011137  call    cs:__imp_InitializeCriticalSectionEx
0x18001113d  mov     qword ptr [rbx+28h], 0
0x180011145  mov     qword ptr [rbx+30h], 0
0x18001114d  mov     qword ptr [rbx+38h], 0
0x180011155  mov     qword ptr [rbx+40h], 0
0x18001115d  xor     ebx, ebx
0x18001115f  mov     [r15], r14
0x180011162  test    rdi, rdi
0x180011165  jz      short loc_180011178
0x180011167  mov     rcx, rdi; hMutex
0x18001116a  call    cs:__imp_ReleaseMutex
0x180011170  test    eax, eax
0x180011172  jz      loc_180011243
0x180011178  test    rbx, rbx
0x18001117b  jz      short loc_18001118A
0x18001117d  mov     rcx, rbx; hObject
0x180011180  call    cs:__imp_CloseHandle
0x180011186  test    eax, eax
0x180011188  jz      short loc_1800111B2
0x18001118a  xor     eax, eax
0x18001118c  mov     rcx, [rbp+180h+var_30]
0x180011193  xor     rcx, rsp; StackCookie
0x180011196  call    __security_check_cookie
0x18001119b  mov     rbx, [rsp+280h+arg_10]
0x1800111a3  add     rsp, 260h
0x1800111aa  pop     r15
0x1800111ac  pop     r14
0x1800111ae  pop     rdi
0x1800111af  pop     rsi
0x1800111b0  pop     rbp
0x1800111b1  retn
0x1800111b2  mov     rcx, [rbp+188h]; this
0x1800111b9  mov     edx, 0A0Bh; void *
0x1800111be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800111c4  mov     rcx, [rbp+188h]; this
0x1800111cb  mov     edx, 0A0Bh; void *
0x1800111d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800111d6  mov     rcx, [rbp+188h]; this
0x1800111dd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800111e3  mov     rcx, [rbp+188h]; this
0x1800111ea  mov     edx, 0A15h; void *
0x1800111ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800111f5  mov     rcx, [rbp+188h]; this
0x1800111fc  mov     edx, 0A0Bh; void *
0x180011201  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011207  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001120d  mov     rcx, [rbp+188h]; this
0x180011214  mov     edx, 0A0Bh; void *
0x180011219  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001121f  mov     rcx, [rbp+188h]; this
0x180011226  mov     edx, 0A0Bh; void *
0x18001122b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011231  mov     rcx, [rbp+188h]; this
0x180011238  mov     edx, 0A15h; void *
0x18001123d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011243  mov     rcx, [rbp+188h]; this
0x18001124a  mov     edx, 0A15h; void *
0x18001124f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
