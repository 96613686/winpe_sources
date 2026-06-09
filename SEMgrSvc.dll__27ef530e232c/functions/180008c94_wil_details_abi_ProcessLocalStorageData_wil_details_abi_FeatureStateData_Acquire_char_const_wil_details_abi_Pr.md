# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180008c94`
- end: `0x180009091`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800093e0`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x180007c2c`
- `0x180008c94`
- `0x180009098`
- `0x180009634`
- `0x18000a0f8`
- `0x18000aff8`
- `0x18000c964`
- `0x18000d4ec`
- `0x18000dacc`
- `0x18000e4b8`
- `0x18000e4c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008f67`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180008f67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008dc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008efe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008f9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008dc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008efe`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008f9a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008d0b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008d0b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180008d2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ec7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008ec7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ed5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ed5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ccd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008ccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008dd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008dd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008eb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008f0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fb0`

## string_xrefs

- `0x18000900d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  _DWORD *v19; // rcx
  unsigned __int64 v20; // rax
  wil::details::in1diag3 *v21; // rcx
  bool v22; // r8
  _DWORD *v23; // r14
  int v24; // eax
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  __int128 v34; // xmm0
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v40);
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
  v20 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v23 = (_DWORD *)v20;
  if ( !v20 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v14, v41);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v20 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v21);
  v24 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v22,
          v20 >> 2);
  v14 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v24, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v23);
    goto LABEL_23;
  }
  v34 = *(_OWORD *)hObject;
  *v23 = 1;
  *((_QWORD *)v23 + 1) = v6;
  *((_OWORD *)v23 + 1) = v34;
  memset_0(v23 + 10, 0, 0x108u);
  *((_QWORD *)v23 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v23 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v23 + 58), 0, 0);
  *((_QWORD *)v23 + 34) = 0;
  *((_QWORD *)v23 + 35) = 0;
  *((_QWORD *)v23 + 36) = 0;
  *((_QWORD *)v23 + 37) = 0;
  v6 = 0;
  *a2 = v23;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x180008c94  mov     [rsp-8+arg_10], rbx
0x180008c99  push    rbp
0x180008c9a  push    rsi
0x180008c9b  push    rdi
0x180008c9c  push    r14
0x180008c9e  push    r15
0x180008ca0  lea     rbp, [rsp-160h]
0x180008ca8  sub     rsp, 260h
0x180008caf  mov     rax, cs:__security_cookie
0x180008cb6  xor     rax, rsp
0x180008cb9  mov     [rbp+180h+var_30], rax
0x180008cc0  mov     r15, rdx
0x180008cc3  mov     qword ptr [rdx], 0
0x180008cca  mov     rbx, rcx
0x180008ccd  call    cs:__imp_GetCurrentProcessId
0x180008cd3  mov     r14d, 130h
0x180008cd9  mov     [rsp+280h+var_258], rbx
0x180008cde  mov     r9d, eax
0x180008ce1  mov     [rsp+280h+var_260], r14d; int
0x180008ce6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180008ced  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008cf2  lea     edx, [r14-2Ch]; unsigned __int64
0x180008cf6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008cfb  mov     r9d, 1F0001h; dwDesiredAccess
0x180008d01  lea     rdx, [rsp+280h+Name]; lpName
0x180008d06  xor     r8d, r8d; dwFlags
0x180008d09  xor     ecx, ecx; lpMutexAttributes
0x180008d0b  call    cs:__imp_CreateMutexExW
0x180008d11  mov     rbx, rax
0x180008d14  test    rax, rax
0x180008d17  jnz     short loc_180008D23
0x180008d19  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008d1e  jmp     loc_180008FBC
0x180008d23  xor     r8d, r8d; bAlertable
0x180008d26  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008d29  mov     rcx, rbx; hHandle
0x180008d2c  call    cs:__imp_WaitForSingleObjectEx
0x180008d32  cmp     eax, 102h
0x180008d37  jz      short loc_180008D49
0x180008d39  test    eax, 0FFFFFF7Fh
0x180008d3e  jnz     loc_180009006
0x180008d44  mov     rdi, rbx
0x180008d47  jmp     short loc_180008D4B
0x180008d49  xor     edi, edi
0x180008d4b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180008d50  mov     [rsp+280h+hObject], 0
0x180008d59  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008d5e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180008d63  mov     esi, eax
0x180008d65  test    eax, eax
0x180008d67  jns     short loc_180008DE8
0x180008d69  mov     rcx, [rbp+188h]; this
0x180008d70  lea     r8, aWil; "wil"
0x180008d77  mov     r9d, eax; char *
0x180008d7a  mov     edx, 66h ; 'f'; void *
0x180008d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d84  mov     rcx, [rbp+188h]; this
0x180008d8b  lea     r8, aWil; "wil"
0x180008d92  mov     r9d, esi; char *
0x180008d95  mov     edx, 6Fh ; 'o'; void *
0x180008d9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d9f  mov     rcx, [rbp+188h]; this
0x180008da6  lea     r8, aWil; "wil"
0x180008dad  mov     r9d, esi; char *
0x180008db0  mov     edx, 12Eh; void *
0x180008db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dba  test    rdi, rdi
0x180008dbd  jz      short loc_180008DD0
0x180008dbf  mov     rcx, rdi; hMutex
0x180008dc2  call    cs:__imp_ReleaseMutex
0x180008dc8  test    eax, eax
0x180008dca  jz      loc_18000901F
0x180008dd0  mov     rcx, rbx; hObject
0x180008dd3  call    cs:__imp_CloseHandle
0x180008dd9  test    eax, eax
0x180008ddb  jz      loc_180009031
0x180008de1  mov     eax, esi
0x180008de3  jmp     loc_180008FBC
0x180008de8  mov     rax, [rsp+280h+hObject]
0x180008ded  lea     rcx, ds:0[rax*4]
0x180008df5  test    rcx, rcx
0x180008df8  jz      short loc_180008E08
0x180008dfa  mov     [r15], rcx
0x180008dfd  mov     eax, [rcx]
0x180008dff  inc     eax
0x180008e01  mov     [rcx], eax
0x180008e03  jmp     loc_180008F92
0x180008e08  mov     rdx, r14; dwBytes
0x180008e0b  mov     qword ptr [r15], 0
0x180008e12  mov     ecx, 8; dwFlags
0x180008e17  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008e1c  mov     r14, rax
0x180008e1f  test    rax, rax
0x180008e22  jnz     short loc_180008E49
0x180008e24  mov     rcx, [rbp+188h]; this
0x180008e2b  lea     r8, aWil; "wil"
0x180008e32  mov     esi, 8007000Eh
0x180008e37  mov     edx, 14Bh; void *
0x180008e3c  mov     r9d, esi; char *
0x180008e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e44  jmp     loc_180008EDB
0x180008e49  xorps   xmm0, xmm0
0x180008e4c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180008e52  test    r14b, 3
0x180008e56  jnz     loc_180009043
0x180008e5c  mov     r9, r14
0x180008e5f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180008e64  shr     r9, 2; unsigned __int64
0x180008e68  lea     rcx, [rsp+280h+hObject]; this
0x180008e6d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180008e72  mov     esi, eax
0x180008e74  test    eax, eax
0x180008e76  jns     loc_180008F22
0x180008e7c  mov     rcx, [rbp+188h]; this
0x180008e83  lea     r8, aWil; "wil"
0x180008e8a  mov     r9d, eax; char *
0x180008e8d  mov     edx, 14Eh; void *
0x180008e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e97  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180008e9c  test    rcx, rcx
0x180008e9f  jz      short loc_180008EAF
0x180008ea1  call    cs:__imp_CloseHandle
0x180008ea7  test    eax, eax
0x180008ea9  jz      loc_180009049
0x180008eaf  mov     rcx, [rsp+280h+hObject]; hObject
0x180008eb4  test    rcx, rcx
0x180008eb7  jz      short loc_180008EC7
0x180008eb9  call    cs:__imp_CloseHandle
0x180008ebf  test    eax, eax
0x180008ec1  jz      loc_18000905B
0x180008ec7  call    cs:__imp_GetProcessHeap
0x180008ecd  mov     r8, r14; lpMem
0x180008ed0  xor     edx, edx; dwFlags
0x180008ed2  mov     rcx, rax; hHeap
0x180008ed5  call    cs:__imp_HeapFree
0x180008edb  mov     rcx, [rbp+188h]; this
0x180008ee2  lea     r8, aWil; "wil"
0x180008ee9  mov     r9d, esi; char *
0x180008eec  mov     edx, 137h; void *
0x180008ef1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ef6  test    rdi, rdi
0x180008ef9  jz      short loc_180008F0C
0x180008efb  mov     rcx, rdi; hMutex
0x180008efe  call    cs:__imp_ReleaseMutex
0x180008f04  test    eax, eax
0x180008f06  jz      loc_18000906D
0x180008f0c  mov     rcx, rbx; hObject
0x180008f0f  call    cs:__imp_CloseHandle
0x180008f15  test    eax, eax
0x180008f17  jz      loc_180008FF4
0x180008f1d  jmp     loc_180008DE1
0x180008f22  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180008f27  lea     rcx, [r14+28h]; void *
0x180008f2b  mov     dword ptr [r14], 1
0x180008f32  xor     edx, edx; Val
0x180008f34  mov     [r14+8], rbx
0x180008f38  mov     r8d, 108h; Size
0x180008f3e  movdqu  xmmword ptr [r14+10h], xmm0
0x180008f44  call    memset_0
0x180008f49  xor     eax, eax
0x180008f4b  lea     rcx, [r14+28h]; this
0x180008f4f  mov     [r14+20h], rax
0x180008f53  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008f58  lea     rbx, [r14+0E8h]
0x180008f5f  xor     r8d, r8d; Flags
0x180008f62  mov     rcx, rbx; lpCriticalSection
0x180008f65  xor     edx, edx; dwSpinCount
0x180008f67  call    cs:__imp_InitializeCriticalSectionEx
0x180008f6d  mov     qword ptr [rbx+28h], 0
0x180008f75  mov     qword ptr [rbx+30h], 0
0x180008f7d  mov     qword ptr [rbx+38h], 0
0x180008f85  mov     qword ptr [rbx+40h], 0
0x180008f8d  xor     ebx, ebx
0x180008f8f  mov     [r15], r14
0x180008f92  test    rdi, rdi
0x180008f95  jz      short loc_180008FA8
0x180008f97  mov     rcx, rdi; hMutex
0x180008f9a  call    cs:__imp_ReleaseMutex
0x180008fa0  test    eax, eax
0x180008fa2  jz      loc_18000907F
0x180008fa8  test    rbx, rbx
0x180008fab  jz      short loc_180008FBA
0x180008fad  mov     rcx, rbx; hObject
0x180008fb0  call    cs:__imp_CloseHandle
0x180008fb6  test    eax, eax
0x180008fb8  jz      short loc_180008FE2
0x180008fba  xor     eax, eax
0x180008fbc  mov     rcx, [rbp+180h+var_30]
0x180008fc3  xor     rcx, rsp; StackCookie
0x180008fc6  call    __security_check_cookie
0x180008fcb  mov     rbx, [rsp+280h+arg_10]
0x180008fd3  add     rsp, 260h
0x180008fda  pop     r15
0x180008fdc  pop     r14
0x180008fde  pop     rdi
0x180008fdf  pop     rsi
0x180008fe0  pop     rbp
0x180008fe1  retn
0x180008fe2  mov     rcx, [rbp+188h]; this
0x180008fe9  mov     edx, 0A0Bh; void *
0x180008fee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ff4  mov     rcx, [rbp+188h]; this
0x180008ffb  mov     edx, 0A0Bh; void *
0x180009000  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009006  mov     rcx, [rbp+188h]; this
0x18000900d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009014  mov     edx, 0E01h; void *
0x180009019  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000901f  mov     rcx, [rbp+188h]; this
0x180009026  mov     edx, 0A15h; void *
0x18000902b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009031  mov     rcx, [rbp+188h]; this
0x180009038  mov     edx, 0A0Bh; void *
0x18000903d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009043  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180009049  mov     rcx, [rbp+188h]; this
0x180009050  mov     edx, 0A0Bh; void *
0x180009055  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000905b  mov     rcx, [rbp+188h]; this
0x180009062  mov     edx, 0A0Bh; void *
0x180009067  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000906d  mov     rcx, [rbp+188h]; this
0x180009074  mov     edx, 0A15h; void *
0x180009079  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000907f  mov     rcx, [rbp+188h]; this
0x180009086  mov     edx, 0A15h; void *
0x18000908b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
