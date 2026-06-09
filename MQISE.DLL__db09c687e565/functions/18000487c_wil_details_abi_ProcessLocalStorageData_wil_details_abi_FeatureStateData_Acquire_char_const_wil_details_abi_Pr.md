# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18000487c`
- end: `0x180004c73`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1015`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800059dc`

## callees

- `0x18000301c`
- `0x18000487c`
- `0x180005310`
- `0x180005c48`
- `0x1800067dc`
- `0x180007dfc`
- `0x1800095c4`
- `0x180009fbc`
- `0x18000a534`
- `0x18000b3b8`
- `0x18000b3c8`
- `0x18000f5c2`
- `0x18000f5f0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800048f9`
- `KERNEL32!CreateMutexExW` at `0x1800048f9`
- `KERNEL32!GetCurrentProcessId` at `0x1800048b5`
- `KERNEL32!GetCurrentProcessId` at `0x1800048b5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180004b90`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180004b90`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004920`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004920`
- `KERNEL32!ReleaseMutex` at `0x1800049a7`
- `KERNEL32!ReleaseMutex` at `0x180004af8`
- `KERNEL32!ReleaseMutex` at `0x180004bb2`
- `KERNEL32!ReleaseMutex` at `0x1800049a7`
- `KERNEL32!ReleaseMutex` at `0x180004af8`
- `KERNEL32!ReleaseMutex` at `0x180004bb2`
- `KERNEL32!CloseHandle` at `0x1800049bf`
- `KERNEL32!CloseHandle` at `0x180004a8d`
- `KERNEL32!CloseHandle` at `0x180004aac`
- `KERNEL32!CloseHandle` at `0x180004b19`
- `KERNEL32!CloseHandle` at `0x180004bcf`
- `KERNEL32!CloseHandle` at `0x1800049bf`
- `KERNEL32!CloseHandle` at `0x180004a8d`
- `KERNEL32!CloseHandle` at `0x180004aac`
- `KERNEL32!CloseHandle` at `0x180004b19`
- `KERNEL32!CloseHandle` at `0x180004bcf`
- `KERNEL32!GetProcessHeap` at `0x180004ac6`
- `KERNEL32!GetProcessHeap` at `0x180004ac6`
- `KERNEL32!HeapFree` at `0x180004ad4`
- `KERNEL32!HeapFree` at `0x180004ad4`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // r14
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // rsi
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject[2]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v46; // [rsp+48h] [rbp-B8h]
  void *v47; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  v46 = Mutex;
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
  v47 = v12;
  v44 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v44, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v44);
  if ( 4 * v44 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_30;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  v44 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_24:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v43);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v33, v34);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
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
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v30);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v31);
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
    goto LABEL_24;
  }
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  v6 = 0;
  v46 = 0;
  *((HANDLE *)v26 + 2) = hObject[0];
  hObject[0] = 0;
  *((HANDLE *)v26 + 3) = hObject[1];
  hObject[1] = 0;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  *a2 = v26;
LABEL_30:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
  return 0;
}

```

## disassembly

```asm
0x18000487c  mov     [rsp-8+arg_10], rbx
0x180004881  push    rbp
0x180004882  push    rsi
0x180004883  push    rdi
0x180004884  push    r14
0x180004886  push    r15
0x180004888  lea     rbp, [rsp-180h]
0x180004890  sub     rsp, 280h
0x180004897  mov     rax, cs:__security_cookie
0x18000489e  xor     rax, rsp
0x1800048a1  mov     [rbp+1A0h+var_30], rax
0x1800048a8  mov     r15, rdx
0x1800048ab  mov     rbx, rcx
0x1800048ae  mov     qword ptr [rdx], 0
0x1800048b5  call    cs:__imp_GetCurrentProcessId
0x1800048bb  mov     r9d, eax
0x1800048be  mov     [rsp+2A0h+var_278], rbx
0x1800048c3  mov     esi, 130h
0x1800048c8  mov     [rsp+2A0h+var_280], esi; int
0x1800048cc  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800048d3  lea     edx, [rsi-2Ch]; unsigned __int64
0x1800048d6  lea     rcx, [rsp+2A0h+Name]; wchar_t *
0x1800048db  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800048e0  mov     [rsp+2A0h+var_258], 0
0x1800048e9  mov     r9d, 1F0001h; dwDesiredAccess
0x1800048ef  xor     r8d, r8d; dwFlags
0x1800048f2  lea     rdx, [rsp+2A0h+Name]; lpName
0x1800048f7  xor     ecx, ecx; lpMutexAttributes
0x1800048f9  call    cs:__imp_CreateMutexExW
0x1800048ff  mov     r14, rax
0x180004902  mov     [rsp+2A0h+var_258], rax
0x180004907  test    rax, rax
0x18000490a  jnz     short loc_180004917
0x18000490c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004911  nop
0x180004912  jmp     loc_180004BE2
0x180004917  xor     r8d, r8d; bAlertable
0x18000491a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000491d  mov     rcx, r14; hHandle
0x180004920  call    cs:__imp_WaitForSingleObjectEx
0x180004926  cmp     eax, 102h
0x18000492b  jz      short loc_18000493D
0x18000492d  test    eax, 0FFFFFF7Fh
0x180004932  jnz     loc_180004C13
0x180004938  mov     rdi, r14
0x18000493b  jmp     short loc_18000493F
0x18000493d  xor     edi, edi
0x18000493f  mov     [rsp+2A0h+var_250], rdi
0x180004944  mov     [rsp+2A0h+var_270], 0
0x18000494d  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x180004952  lea     rcx, [rsp+2A0h+Name]; wchar_t *
0x180004957  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000495c  mov     ebx, eax
0x18000495e  test    eax, eax
0x180004960  jns     short loc_1800049DB
0x180004962  mov     rcx, [rbp+1A8h]; this
0x180004969  mov     r9d, eax; char *
0x18000496c  mov     edx, 66h ; 'f'; void *
0x180004971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004976  mov     rcx, [rbp+1A8h]; this
0x18000497d  mov     r9d, ebx; char *
0x180004980  mov     edx, 6Fh ; 'o'; void *
0x180004985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000498a  mov     rcx, [rbp+1A8h]; this
0x180004991  mov     r9d, ebx; char *
0x180004994  mov     edx, 12Eh; void *
0x180004999  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000499e  nop
0x18000499f  test    rdi, rdi
0x1800049a2  jz      short loc_1800049BC
0x1800049a4  mov     rcx, rdi; hMutex
0x1800049a7  call    cs:__imp_ReleaseMutex
0x1800049ad  mov     rcx, [rbp+1A8h]; this
0x1800049b4  test    eax, eax
0x1800049b6  jz      loc_180004C20
0x1800049bc  mov     rcx, r14; hObject
0x1800049bf  call    cs:__imp_CloseHandle
0x1800049c5  mov     rcx, [rbp+1A8h]; this
0x1800049cc  test    eax, eax
0x1800049ce  jz      loc_180004C2B
0x1800049d4  mov     eax, ebx
0x1800049d6  jmp     loc_180004BE2
0x1800049db  mov     rax, [rsp+2A0h+var_270]
0x1800049e0  lea     rcx, ds:0[rax*4]
0x1800049e8  test    rcx, rcx
0x1800049eb  jz      short loc_1800049FB
0x1800049ed  mov     [r15], rcx
0x1800049f0  mov     eax, [rcx]
0x1800049f2  inc     eax
0x1800049f4  mov     [rcx], eax
0x1800049f6  jmp     loc_180004BAA
0x1800049fb  mov     qword ptr [r15], 0
0x180004a02  mov     rdx, rsi; dwBytes
0x180004a05  mov     ecx, 8; dwFlags
0x180004a0a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004a0f  mov     rsi, rax
0x180004a12  mov     [rsp+2A0h+var_270], rax
0x180004a17  test    rax, rax
0x180004a1a  jnz     short loc_180004A3B
0x180004a1c  mov     rcx, [rbp+1A8h]; this
0x180004a23  mov     ebx, 8007000Eh
0x180004a28  mov     r9d, ebx; char *
0x180004a2b  mov     edx, 14Bh; void *
0x180004a30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a35  nop
0x180004a36  jmp     loc_180004ADB
0x180004a3b  xorps   xmm0, xmm0
0x180004a3e  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x180004a44  test    sil, 3
0x180004a48  jnz     loc_180004C36
0x180004a4e  mov     r9, rsi
0x180004a51  shr     r9, 2; unsigned __int64
0x180004a55  lea     rdx, [rsp+2A0h+Name]; wchar_t *
0x180004a5a  lea     rcx, [rsp+2A0h+hObject]; this
0x180004a5f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180004a64  mov     ebx, eax
0x180004a66  test    eax, eax
0x180004a68  jns     loc_180004B33
0x180004a6e  mov     rcx, [rbp+1A8h]; this
0x180004a75  mov     r9d, eax; char *
0x180004a78  mov     edx, 14Eh; void *
0x180004a7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004a82  nop
0x180004a83  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x180004a88  test    rcx, rcx
0x180004a8b  jz      short loc_180004AA2
0x180004a8d  call    cs:__imp_CloseHandle
0x180004a93  mov     rcx, [rbp+1A8h]; this
0x180004a9a  test    eax, eax
0x180004a9c  jz      loc_180004C3C
0x180004aa2  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180004aa7  test    rcx, rcx
0x180004aaa  jz      short loc_180004AC1
0x180004aac  call    cs:__imp_CloseHandle
0x180004ab2  mov     rcx, [rbp+1A8h]; this
0x180004ab9  test    eax, eax
0x180004abb  jz      loc_180004C47
0x180004ac1  test    rsi, rsi
0x180004ac4  jz      short loc_180004ADB
0x180004ac6  call    cs:__imp_GetProcessHeap
0x180004acc  mov     rcx, rax; hHeap
0x180004acf  mov     r8, rsi; lpMem
0x180004ad2  xor     edx, edx; dwFlags
0x180004ad4  call    cs:__imp_HeapFree
0x180004ada  nop
0x180004adb  mov     rcx, [rbp+1A8h]; this
0x180004ae2  mov     r9d, ebx; char *
0x180004ae5  mov     edx, 137h; void *
0x180004aea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004aef  nop
0x180004af0  test    rdi, rdi
0x180004af3  jz      short loc_180004B0D
0x180004af5  mov     rcx, rdi; hMutex
0x180004af8  call    cs:__imp_ReleaseMutex
0x180004afe  mov     rcx, [rbp+1A8h]; this
0x180004b05  test    eax, eax
0x180004b07  jz      loc_180004C52
0x180004b0d  test    r14, r14
0x180004b10  jz      loc_1800049D4
0x180004b16  mov     rcx, r14; hObject
0x180004b19  call    cs:__imp_CloseHandle
0x180004b1f  mov     rcx, [rbp+1A8h]; this
0x180004b26  test    eax, eax
0x180004b28  jz      loc_180004C5D
0x180004b2e  jmp     loc_1800049D4
0x180004b33  mov     dword ptr [rsi], 1
0x180004b39  mov     [rsi+8], r14
0x180004b3d  xor     r14d, r14d
0x180004b40  mov     [rsp+2A0h+var_258], r14
0x180004b45  mov     rax, [rsp+2A0h+hObject]
0x180004b4a  mov     [rsi+10h], rax
0x180004b4e  mov     [rsp+2A0h+hObject], r14
0x180004b53  mov     rax, [rsp+2A0h+hObject+8]
0x180004b58  mov     [rsi+18h], rax
0x180004b5c  mov     [rsp+2A0h+hObject+8], r14
0x180004b61  lea     rcx, [rsi+28h]; void *
0x180004b65  xor     edx, edx; Val
0x180004b67  mov     r8d, 108h; Size
0x180004b6d  call    memset_0
0x180004b72  xor     eax, eax
0x180004b74  mov     [rsi+20h], rax
0x180004b78  lea     rcx, [rsi+28h]; this
0x180004b7c  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004b81  lea     rbx, [rsi+0E8h]
0x180004b88  xor     r8d, r8d; Flags
0x180004b8b  xor     edx, edx; dwSpinCount
0x180004b8d  mov     rcx, rbx; lpCriticalSection
0x180004b90  call    cs:__imp_InitializeCriticalSectionEx
0x180004b96  nop
0x180004b97  mov     [rbx+28h], r14
0x180004b9b  mov     [rbx+30h], r14
0x180004b9f  mov     [rbx+38h], r14
0x180004ba3  mov     [rbx+40h], r14
0x180004ba7  mov     [r15], rsi
0x180004baa  test    rdi, rdi
0x180004bad  jz      short loc_180004BC7
0x180004baf  mov     rcx, rdi; hMutex
0x180004bb2  call    cs:__imp_ReleaseMutex
0x180004bb8  mov     rcx, [rbp+1A8h]; this
0x180004bbf  test    eax, eax
0x180004bc1  jz      loc_180004C68
0x180004bc7  test    r14, r14
0x180004bca  jz      short loc_180004BE0
0x180004bcc  mov     rcx, r14; hObject
0x180004bcf  call    cs:__imp_CloseHandle
0x180004bd5  mov     rcx, [rbp+1A8h]; this
0x180004bdc  test    eax, eax
0x180004bde  jz      short loc_180004C08
0x180004be0  xor     eax, eax
0x180004be2  mov     rcx, [rbp+1A0h+var_30]
0x180004be9  xor     rcx, rsp; StackCookie
0x180004bec  call    __security_check_cookie
0x180004bf1  mov     rbx, [rsp+2A0h+arg_10]
0x180004bf9  add     rsp, 280h
0x180004c00  pop     r15
0x180004c02  pop     r14
0x180004c04  pop     rdi
0x180004c05  pop     rsi
0x180004c06  pop     rbp
0x180004c07  retn
0x180004c08  mov     edx, 0A0Bh; void *
0x180004c0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c13  mov     rcx, [rbp+1A8h]; this
0x180004c1a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004c20  mov     edx, 0A15h; void *
0x180004c25  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c2b  mov     edx, 0A0Bh; void *
0x180004c30  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004c3c  mov     edx, 0A0Bh; void *
0x180004c41  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c47  mov     edx, 0A0Bh; void *
0x180004c4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c52  mov     edx, 0A15h; void *
0x180004c57  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c5d  mov     edx, 0A0Bh; void *
0x180004c62  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004c68  mov     edx, 0A15h; void *
0x180004c6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
