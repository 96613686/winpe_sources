# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180005d10`
- end: `0x1800060d7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800063b4`

## callees

- `0x18000525c`
- `0x180005d10`
- `0x1800060e0`
- `0x180006544`
- `0x180006e68`
- `0x180007a58`
- `0x180008cf0`
- `0x1800091c0`
- `0x1800094c8`
- `0x180009c9c`
- `0x180009cac`
- `0x18000a19e`
- `0x18000a1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005e29`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f50`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005e29`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005f50`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005fec`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d87`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005d87`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005da8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180005da8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005fb9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180005fb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005d49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006002`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005efa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006002`

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
  unsigned int v17; // r8d
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int128 v39; // xmm0
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // r8
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x180005d10  mov     [rsp-8+arg_10], rbx
0x180005d15  push    rbp
0x180005d16  push    rsi
0x180005d17  push    rdi
0x180005d18  push    r14
0x180005d1a  push    r15
0x180005d1c  lea     rbp, [rsp-160h]
0x180005d24  sub     rsp, 260h
0x180005d2b  mov     rax, cs:__security_cookie
0x180005d32  xor     rax, rsp
0x180005d35  mov     [rbp+180h+var_30], rax
0x180005d3c  mov     r15, rdx
0x180005d3f  mov     qword ptr [rdx], 0
0x180005d46  mov     rbx, rcx
0x180005d49  call    cs:__imp_GetCurrentProcessId
0x180005d4f  mov     r14d, 130h
0x180005d55  mov     [rsp+280h+var_258], rbx
0x180005d5a  mov     r9d, eax
0x180005d5d  mov     [rsp+280h+var_260], r14d; int
0x180005d62  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180005d69  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005d6e  lea     edx, [r14-2Ch]; unsigned __int64
0x180005d72  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005d77  mov     r9d, 1F0001h; dwDesiredAccess
0x180005d7d  lea     rdx, [rsp+280h+Name]; lpName
0x180005d82  xor     r8d, r8d; dwFlags
0x180005d85  xor     ecx, ecx; lpMutexAttributes
0x180005d87  call    cs:__imp_CreateMutexExW
0x180005d8d  mov     rbx, rax
0x180005d90  test    rax, rax
0x180005d93  jnz     short loc_180005D9F
0x180005d95  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005d9a  jmp     loc_18000600E
0x180005d9f  xor     r8d, r8d; bAlertable
0x180005da2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005da5  mov     rcx, rbx; hHandle
0x180005da8  call    cs:__imp_WaitForSingleObjectEx
0x180005dae  cmp     eax, 102h
0x180005db3  jz      short loc_180005DC5
0x180005db5  test    eax, 0FFFFFF7Fh
0x180005dba  jnz     loc_180006058
0x180005dc0  mov     rdi, rbx
0x180005dc3  jmp     short loc_180005DC7
0x180005dc5  xor     edi, edi
0x180005dc7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180005dcc  mov     [rsp+280h+hObject], 0
0x180005dd5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180005dda  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180005ddf  mov     esi, eax
0x180005de1  test    eax, eax
0x180005de3  jns     short loc_180005E4F
0x180005de5  mov     rcx, [rbp+188h]; this
0x180005dec  mov     r9d, eax; char *
0x180005def  mov     edx, 66h ; 'f'; void *
0x180005df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005df9  mov     rcx, [rbp+188h]; this
0x180005e00  mov     r9d, esi; char *
0x180005e03  mov     edx, 6Fh ; 'o'; void *
0x180005e08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e0d  mov     rcx, [rbp+188h]; this
0x180005e14  mov     r9d, esi; char *
0x180005e17  mov     edx, 12Eh; void *
0x180005e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005e21  test    rdi, rdi
0x180005e24  jz      short loc_180005E37
0x180005e26  mov     rcx, rdi; hMutex
0x180005e29  call    cs:__imp_ReleaseMutex
0x180005e2f  test    eax, eax
0x180005e31  jz      loc_180006065
0x180005e37  mov     rcx, rbx; hObject
0x180005e3a  call    cs:__imp_CloseHandle
0x180005e40  test    eax, eax
0x180005e42  jz      loc_180006077
0x180005e48  mov     eax, esi
0x180005e4a  jmp     loc_18000600E
0x180005e4f  mov     rax, [rsp+280h+hObject]
0x180005e54  lea     rcx, ds:0[rax*4]
0x180005e5c  test    rcx, rcx
0x180005e5f  jz      short loc_180005E6F
0x180005e61  mov     [r15], rcx
0x180005e64  mov     eax, [rcx]
0x180005e66  inc     eax
0x180005e68  mov     [rcx], eax
0x180005e6a  jmp     loc_180005FE4
0x180005e6f  mov     rdx, r14; dwBytes
0x180005e72  mov     qword ptr [r15], 0
0x180005e79  mov     ecx, 8; dwFlags
0x180005e7e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005e83  mov     r14, rax
0x180005e86  test    rax, rax
0x180005e89  jnz     short loc_180005EA9
0x180005e8b  mov     rcx, [rbp+188h]; this
0x180005e92  mov     esi, 8007000Eh
0x180005e97  mov     r9d, esi; char *
0x180005e9a  mov     edx, 14Bh; void *
0x180005e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ea4  jmp     loc_180005F34
0x180005ea9  xorps   xmm0, xmm0
0x180005eac  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180005eb2  test    r14b, 3
0x180005eb6  jnz     loc_180006089
0x180005ebc  mov     r9, r14
0x180005ebf  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180005ec4  shr     r9, 2; unsigned __int64
0x180005ec8  lea     rcx, [rsp+280h+hObject]; this
0x180005ecd  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180005ed2  mov     esi, eax
0x180005ed4  test    eax, eax
0x180005ed6  jns     loc_180005F74
0x180005edc  mov     rcx, [rbp+188h]; this
0x180005ee3  mov     r9d, eax; char *
0x180005ee6  mov     edx, 14Eh; void *
0x180005eeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005ef0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180005ef5  test    rcx, rcx
0x180005ef8  jz      short loc_180005F08
0x180005efa  call    cs:__imp_CloseHandle
0x180005f00  test    eax, eax
0x180005f02  jz      loc_18000608F
0x180005f08  mov     rcx, [rsp+280h+hObject]; hObject
0x180005f0d  test    rcx, rcx
0x180005f10  jz      short loc_180005F20
0x180005f12  call    cs:__imp_CloseHandle
0x180005f18  test    eax, eax
0x180005f1a  jz      loc_1800060A1
0x180005f20  call    cs:__imp_GetProcessHeap
0x180005f26  mov     r8, r14; lpMem
0x180005f29  xor     edx, edx; dwFlags
0x180005f2b  mov     rcx, rax; hHeap
0x180005f2e  call    cs:__imp_HeapFree
0x180005f34  mov     rcx, [rbp+188h]; this
0x180005f3b  mov     r9d, esi; char *
0x180005f3e  mov     edx, 137h; void *
0x180005f43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f48  test    rdi, rdi
0x180005f4b  jz      short loc_180005F5E
0x180005f4d  mov     rcx, rdi; hMutex
0x180005f50  call    cs:__imp_ReleaseMutex
0x180005f56  test    eax, eax
0x180005f58  jz      loc_1800060B3
0x180005f5e  mov     rcx, rbx; hObject
0x180005f61  call    cs:__imp_CloseHandle
0x180005f67  test    eax, eax
0x180005f69  jz      loc_180006046
0x180005f6f  jmp     loc_180005E48
0x180005f74  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180005f79  lea     rcx, [r14+28h]; void *
0x180005f7d  mov     dword ptr [r14], 1
0x180005f84  xor     edx, edx; Val
0x180005f86  mov     [r14+8], rbx
0x180005f8a  mov     r8d, 108h; Size
0x180005f90  movdqu  xmmword ptr [r14+10h], xmm0
0x180005f96  call    memset_0
0x180005f9b  xor     eax, eax
0x180005f9d  lea     rcx, [r14+28h]; this
0x180005fa1  mov     [r14+20h], rax
0x180005fa5  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005faa  lea     rbx, [r14+0E8h]
0x180005fb1  xor     r8d, r8d; Flags
0x180005fb4  mov     rcx, rbx; lpCriticalSection
0x180005fb7  xor     edx, edx; dwSpinCount
0x180005fb9  call    cs:__imp_InitializeCriticalSectionEx
0x180005fbf  mov     qword ptr [rbx+28h], 0
0x180005fc7  mov     qword ptr [rbx+30h], 0
0x180005fcf  mov     qword ptr [rbx+38h], 0
0x180005fd7  mov     qword ptr [rbx+40h], 0
0x180005fdf  xor     ebx, ebx
0x180005fe1  mov     [r15], r14
0x180005fe4  test    rdi, rdi
0x180005fe7  jz      short loc_180005FFA
0x180005fe9  mov     rcx, rdi; hMutex
0x180005fec  call    cs:__imp_ReleaseMutex
0x180005ff2  test    eax, eax
0x180005ff4  jz      loc_1800060C5
0x180005ffa  test    rbx, rbx
0x180005ffd  jz      short loc_18000600C
0x180005fff  mov     rcx, rbx; hObject
0x180006002  call    cs:__imp_CloseHandle
0x180006008  test    eax, eax
0x18000600a  jz      short loc_180006034
0x18000600c  xor     eax, eax
0x18000600e  mov     rcx, [rbp+180h+var_30]
0x180006015  xor     rcx, rsp; StackCookie
0x180006018  call    __security_check_cookie
0x18000601d  mov     rbx, [rsp+280h+arg_10]
0x180006025  add     rsp, 260h
0x18000602c  pop     r15
0x18000602e  pop     r14
0x180006030  pop     rdi
0x180006031  pop     rsi
0x180006032  pop     rbp
0x180006033  retn
0x180006034  mov     rcx, [rbp+188h]; this
0x18000603b  mov     edx, 0A0Bh; void *
0x180006040  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006046  mov     rcx, [rbp+188h]; this
0x18000604d  mov     edx, 0A0Bh; void *
0x180006052  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006058  mov     rcx, [rbp+188h]; this
0x18000605f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006065  mov     rcx, [rbp+188h]; this
0x18000606c  mov     edx, 0A15h; void *
0x180006071  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006077  mov     rcx, [rbp+188h]; this
0x18000607e  mov     edx, 0A0Bh; void *
0x180006083  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006089  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000608f  mov     rcx, [rbp+188h]; this
0x180006096  mov     edx, 0A0Bh; void *
0x18000609b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800060a1  mov     rcx, [rbp+188h]; this
0x1800060a8  mov     edx, 0A0Bh; void *
0x1800060ad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800060b3  mov     rcx, [rbp+188h]; this
0x1800060ba  mov     edx, 0A15h; void *
0x1800060bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800060c5  mov     rcx, [rbp+188h]; this
0x1800060cc  mov     edx, 0A15h; void *
0x1800060d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
