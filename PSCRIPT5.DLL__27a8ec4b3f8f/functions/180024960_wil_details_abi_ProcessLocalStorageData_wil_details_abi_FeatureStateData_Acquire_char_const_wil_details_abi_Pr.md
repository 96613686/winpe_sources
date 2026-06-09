# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180024960`
- end: `0x180024d60`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180024f9c`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180023ef4`
- `0x1800242d8`
- `0x180024960`
- `0x180024d68`
- `0x180025118`
- `0x180025b68`
- `0x180026880`
- `0x180027c74`
- `0x1800284d4`
- `0x180028d00`
- `0x180029488`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180024b7e`
- `KERNEL32!GetProcessHeap` at `0x180024b7e`
- `KERNEL32!GetCurrentProcessId` at `0x180024999`
- `KERNEL32!GetCurrentProcessId` at `0x180024999`
- `KERNEL32!CreateMutexExW` at `0x1800249dd`
- `KERNEL32!CreateMutexExW` at `0x1800249dd`
- `KERNEL32!WaitForSingleObjectEx` at `0x180024a04`
- `KERNEL32!WaitForSingleObjectEx` at `0x180024a04`
- `KERNEL32!ReleaseMutex` at `0x180024aa4`
- `KERNEL32!ReleaseMutex` at `0x180024bc1`
- `KERNEL32!ReleaseMutex` at `0x180024c92`
- `KERNEL32!ReleaseMutex` at `0x180024aa4`
- `KERNEL32!ReleaseMutex` at `0x180024bc1`
- `KERNEL32!ReleaseMutex` at `0x180024c92`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180024c4f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180024c4f`
- `KERNEL32!HeapFree` at `0x180024b92`
- `KERNEL32!HeapFree` at `0x180024b92`
- `KERNEL32!CloseHandle` at `0x180024abb`
- `KERNEL32!CloseHandle` at `0x180024bd8`
- `KERNEL32!CloseHandle` at `0x180024cae`
- `KERNEL32!CloseHandle` at `0x180024abb`
- `KERNEL32!CloseHandle` at `0x180024bd8`
- `KERNEL32!CloseHandle` at `0x180024cae`

## pseudocode

```c
signed int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  DWORD v9; // eax
  void *v10; // rdx
  __int64 v11; // r8
  char *v12; // r9
  void *v13; // rdi
  int ValueInternal; // eax
  unsigned int v15; // esi
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  _DWORD *v21; // rax
  _DWORD *v22; // r14
  int v23; // eax
  HANDLE ProcessHeap; // rax
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  unsigned __int64 v33[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 304, a1);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
  v7 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v6);
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v13 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v10, v11, v12);
    v13 = v7;
  }
  v33[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(pszDest, (__int64)v10, v33, (bool *)v12);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, (__int64)"wil", (const char *)(unsigned int)ValueInternal);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (__int64)"wil", (const char *)v15);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (__int64)"wil", (const char *)v15);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v16, v17);
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    return v15;
  }
  v20 = (_DWORD *)(4 * v33[0]);
  if ( 4 * v33[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x130u);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (__int64)"wil", (const char *)0x8007000ELL);
    goto LABEL_18;
  }
  *(_OWORD *)v33 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer(
          (wil::details_abi::SemaphoreValue *)v33,
          pszDest,
          (unsigned __int64)v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (__int64)"wil", (const char *)(unsigned int)v23);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v22);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (__int64)"wil", (const char *)v15);
    if ( v13 && !ReleaseMutex(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v25, v26);
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return v15;
  }
  *((_QWORD *)v22 + 2) = v33[0];
  *((_QWORD *)v22 + 3) = v33[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v7;
  v33[0] = 0;
  v33[1] = 0;
  memset_0(v22 + 10, 0, 0x108u);
  *((_QWORD *)v22 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v22 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v22 + 58), 0, 0);
  *((_QWORD *)v22 + 34) = 0;
  *((_QWORD *)v22 + 35) = 0;
  *((_QWORD *)v22 + 36) = 0;
  *((_QWORD *)v22 + 37) = 0;
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v33);
  v7 = 0;
LABEL_23:
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v29, v30);
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
  return 0;
}

```

## disassembly

```asm
0x180024960  mov     [rsp-8+arg_10], rbx
0x180024965  push    rbp
0x180024966  push    rsi
0x180024967  push    rdi
0x180024968  push    r14
0x18002496a  push    r15
0x18002496c  lea     rbp, [rsp-160h]
0x180024974  sub     rsp, 260h
0x18002497b  mov     rax, cs:__security_cookie
0x180024982  xor     rax, rsp
0x180024985  mov     [rbp+180h+var_30], rax
0x18002498c  mov     r15, rdx
0x18002498f  mov     qword ptr [rdx], 0
0x180024996  mov     rbx, rcx
0x180024999  call    cs:__imp_GetCurrentProcessId
0x1800249a0  nop     dword ptr [rax+rax+00h]
0x1800249a5  mov     r14d, 130h
0x1800249ab  mov     [rsp+280h+var_258], rbx
0x1800249b0  mov     r9d, eax
0x1800249b3  mov     [rsp+280h+var_260], r14d; int
0x1800249b8  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800249bf  lea     rcx, [rsp+280h+pszDest]; pszDest
0x1800249c4  lea     edx, [r14-2Ch]; cchDest
0x1800249c8  call    StringCchPrintfW
0x1800249cd  mov     r9d, 1F0001h; dwDesiredAccess
0x1800249d3  lea     rdx, [rsp+280h+pszDest]; lpName
0x1800249d8  xor     r8d, r8d; dwFlags
0x1800249db  xor     ecx, ecx; lpMutexAttributes
0x1800249dd  call    cs:__imp_CreateMutexExW
0x1800249e4  nop     dword ptr [rax+rax+00h]
0x1800249e9  mov     rbx, rax
0x1800249ec  test    rax, rax
0x1800249ef  jnz     short loc_1800249FB
0x1800249f1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800249f6  jmp     loc_180024CC0
0x1800249fb  xor     r8d, r8d; bAlertable
0x1800249fe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180024a01  mov     rcx, rbx; hHandle
0x180024a04  call    cs:__imp_WaitForSingleObjectEx
0x180024a0b  nop     dword ptr [rax+rax+00h]
0x180024a10  cmp     eax, 102h
0x180024a15  jz      short loc_180024A27
0x180024a17  test    eax, 0FFFFFF7Fh
0x180024a1c  jnz     loc_180024D0B
0x180024a22  mov     rdi, rbx
0x180024a25  jmp     short loc_180024A29
0x180024a27  xor     edi, edi
0x180024a29  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180024a2e  mov     [rsp+280h+var_250], 0
0x180024a37  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180024a3c  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180024a41  mov     esi, eax
0x180024a43  test    eax, eax
0x180024a45  jns     loc_180024AD6
0x180024a4b  mov     rcx, [rbp+188h]; this
0x180024a52  lea     r8, aWil; "wil"
0x180024a59  mov     r9d, eax; char *
0x180024a5c  mov     edx, 66h ; 'f'; void *
0x180024a61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a66  mov     rcx, [rbp+188h]; this
0x180024a6d  lea     r8, aWil; "wil"
0x180024a74  mov     r9d, esi; char *
0x180024a77  mov     edx, 6Fh ; 'o'; void *
0x180024a7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a81  mov     rcx, [rbp+188h]; this
0x180024a88  lea     r8, aWil; "wil"
0x180024a8f  mov     r9d, esi; char *
0x180024a92  mov     edx, 12Eh; void *
0x180024a97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a9c  test    rdi, rdi
0x180024a9f  jz      short loc_180024AB8
0x180024aa1  mov     rcx, rdi; hMutex
0x180024aa4  call    cs:__imp_ReleaseMutex
0x180024aab  nop     dword ptr [rax+rax+00h]
0x180024ab0  test    eax, eax
0x180024ab2  jz      loc_180024D18
0x180024ab8  mov     rcx, rbx; hObject
0x180024abb  call    cs:__imp_CloseHandle
0x180024ac2  nop     dword ptr [rax+rax+00h]
0x180024ac7  test    eax, eax
0x180024ac9  jz      loc_180024D2A
0x180024acf  mov     eax, esi
0x180024ad1  jmp     loc_180024CC0
0x180024ad6  mov     rax, [rsp+280h+var_250]
0x180024adb  lea     rcx, ds:0[rax*4]
0x180024ae3  test    rcx, rcx
0x180024ae6  jz      short loc_180024AF6
0x180024ae8  mov     [r15], rcx
0x180024aeb  mov     eax, [rcx]
0x180024aed  inc     eax
0x180024aef  mov     [rcx], eax
0x180024af1  jmp     loc_180024C8A
0x180024af6  mov     rdx, r14; dwBytes
0x180024af9  mov     qword ptr [r15], 0
0x180024b00  mov     ecx, 8; dwFlags
0x180024b05  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180024b0a  mov     r14, rax
0x180024b0d  test    rax, rax
0x180024b10  jnz     short loc_180024B34
0x180024b12  mov     rcx, [rbp+188h]; this
0x180024b19  lea     r8, aWil; "wil"
0x180024b20  mov     esi, 8007000Eh
0x180024b25  mov     edx, 14Bh; void *
0x180024b2a  mov     r9d, esi; char *
0x180024b2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b32  jmp     short loc_180024B9E
0x180024b34  xorps   xmm0, xmm0
0x180024b37  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180024b3c  mov     r8, r14; void *
0x180024b3f  lea     rcx, [rsp+280h+var_250]; this
0x180024b44  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180024b4a  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180024b4f  mov     esi, eax
0x180024b51  test    eax, eax
0x180024b53  jns     loc_180024BF1
0x180024b59  mov     rcx, [rbp+188h]; this
0x180024b60  lea     r8, aWil; "wil"
0x180024b67  mov     r9d, eax; char *
0x180024b6a  mov     edx, 14Eh; void *
0x180024b6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b74  lea     rcx, [rsp+280h+var_250]; this
0x180024b79  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180024b7e  call    cs:__imp_GetProcessHeap
0x180024b85  nop     dword ptr [rax+rax+00h]
0x180024b8a  mov     r8, r14; lpMem
0x180024b8d  xor     edx, edx; dwFlags
0x180024b8f  mov     rcx, rax; hHeap
0x180024b92  call    cs:__imp_HeapFree
0x180024b99  nop     dword ptr [rax+rax+00h]
0x180024b9e  mov     rcx, [rbp+188h]; this
0x180024ba5  lea     r8, aWil; "wil"
0x180024bac  mov     r9d, esi; char *
0x180024baf  mov     edx, 137h; void *
0x180024bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bb9  test    rdi, rdi
0x180024bbc  jz      short loc_180024BD5
0x180024bbe  mov     rcx, rdi; hMutex
0x180024bc1  call    cs:__imp_ReleaseMutex
0x180024bc8  nop     dword ptr [rax+rax+00h]
0x180024bcd  test    eax, eax
0x180024bcf  jz      loc_180024D3C
0x180024bd5  mov     rcx, rbx; hObject
0x180024bd8  call    cs:__imp_CloseHandle
0x180024bdf  nop     dword ptr [rax+rax+00h]
0x180024be4  test    eax, eax
0x180024be6  jz      loc_180024CF9
0x180024bec  jmp     loc_180024ACF
0x180024bf1  mov     rax, [rsp+280h+var_250]
0x180024bf6  lea     rcx, [r14+28h]; void *
0x180024bfa  mov     [r14+10h], rax
0x180024bfe  xor     edx, edx; Val
0x180024c00  mov     rax, [rsp+280h+var_250+8]
0x180024c05  mov     r8d, 108h; Size
0x180024c0b  mov     [r14+18h], rax
0x180024c0f  mov     dword ptr [r14], 1
0x180024c16  mov     [r14+8], rbx
0x180024c1a  mov     [rsp+280h+var_250], 0
0x180024c23  mov     [rsp+280h+var_250+8], 0
0x180024c2c  call    memset_0
0x180024c31  xor     eax, eax
0x180024c33  lea     rcx, [r14+28h]; this
0x180024c37  mov     [r14+20h], rax
0x180024c3b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180024c40  lea     rbx, [r14+0E8h]
0x180024c47  xor     r8d, r8d; Flags
0x180024c4a  mov     rcx, rbx; lpCriticalSection
0x180024c4d  xor     edx, edx; dwSpinCount
0x180024c4f  call    cs:__imp_InitializeCriticalSectionEx
0x180024c56  nop     dword ptr [rax+rax+00h]
0x180024c5b  mov     qword ptr [rbx+28h], 0
0x180024c63  lea     rcx, [rsp+280h+var_250]; this
0x180024c68  mov     qword ptr [rbx+30h], 0
0x180024c70  mov     qword ptr [rbx+38h], 0
0x180024c78  mov     qword ptr [rbx+40h], 0
0x180024c80  mov     [r15], r14
0x180024c83  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180024c88  xor     ebx, ebx
0x180024c8a  test    rdi, rdi
0x180024c8d  jz      short loc_180024CA6
0x180024c8f  mov     rcx, rdi; hMutex
0x180024c92  call    cs:__imp_ReleaseMutex
0x180024c99  nop     dword ptr [rax+rax+00h]
0x180024c9e  test    eax, eax
0x180024ca0  jz      loc_180024D4E
0x180024ca6  test    rbx, rbx
0x180024ca9  jz      short loc_180024CBE
0x180024cab  mov     rcx, rbx; hObject
0x180024cae  call    cs:__imp_CloseHandle
0x180024cb5  nop     dword ptr [rax+rax+00h]
0x180024cba  test    eax, eax
0x180024cbc  jz      short loc_180024CE7
0x180024cbe  xor     eax, eax
0x180024cc0  mov     rcx, [rbp+180h+var_30]
0x180024cc7  xor     rcx, rsp; StackCookie
0x180024cca  call    __security_check_cookie
0x180024ccf  mov     rbx, [rsp+280h+arg_10]
0x180024cd7  add     rsp, 260h
0x180024cde  pop     r15
0x180024ce0  pop     r14
0x180024ce2  pop     rdi
0x180024ce3  pop     rsi
0x180024ce4  pop     rbp
0x180024ce5  retn
0x180024ce7  mov     rcx, [rbp+188h]; this
0x180024cee  mov     edx, 0A0Bh; void *
0x180024cf3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024cf9  mov     rcx, [rbp+188h]; this
0x180024d00  mov     edx, 0A0Bh; void *
0x180024d05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024d0b  mov     rcx, [rbp+188h]; this
0x180024d12  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180024d18  mov     rcx, [rbp+188h]; this
0x180024d1f  mov     edx, 0A15h; void *
0x180024d24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024d2a  mov     rcx, [rbp+188h]; this
0x180024d31  mov     edx, 0A0Bh; void *
0x180024d36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024d3c  mov     rcx, [rbp+188h]; this
0x180024d43  mov     edx, 0A15h; void *
0x180024d48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024d4e  mov     rcx, [rbp+188h]; this
0x180024d55  mov     edx, 0A15h; void *
0x180024d5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
