# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011a14`
- end: `0x180011df2`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180012020`

## callees

- `0x180006b18`
- `0x180010c5c`
- `0x18001133c`
- `0x180011a14`
- `0x180011df8`
- `0x180012280`
- `0x180012b20`
- `0x18001393c`
- `0x180014f64`
- `0x180015dcc`
- `0x180016644`
- `0x18001899e`
- `0x1800189d0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180011c43`
- `KERNEL32!HeapFree` at `0x180011c43`
- `KERNEL32!GetProcessHeap` at `0x180011c2f`
- `KERNEL32!GetProcessHeap` at `0x180011c2f`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180011d0e`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180011d0e`
- `KERNEL32!WaitForSingleObjectEx` at `0x180011abc`
- `KERNEL32!WaitForSingleObjectEx` at `0x180011abc`
- `KERNEL32!GetCurrentProcessId` at `0x180011a4d`
- `KERNEL32!GetCurrentProcessId` at `0x180011a4d`
- `KERNEL32!ReleaseMutex` at `0x180011b4d`
- `KERNEL32!ReleaseMutex` at `0x180011c6c`
- `KERNEL32!ReleaseMutex` at `0x180011d40`
- `KERNEL32!ReleaseMutex` at `0x180011b4d`
- `KERNEL32!ReleaseMutex` at `0x180011c6c`
- `KERNEL32!ReleaseMutex` at `0x180011d40`
- `KERNEL32!CreateMutexExW` at `0x180011a8f`
- `KERNEL32!CreateMutexExW` at `0x180011a8f`
- `KERNEL32!CloseHandle` at `0x180011b6b`
- `KERNEL32!CloseHandle` at `0x180011c8f`
- `KERNEL32!CloseHandle` at `0x180011d63`
- `KERNEL32!CloseHandle` at `0x180011b6b`
- `KERNEL32!CloseHandle` at `0x180011c8f`
- `KERNEL32!CloseHandle` at `0x180011d63`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  void *v12; // rsi
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
  char *v23; // rax
  unsigned int v24; // r8d
  char *v25; // rbx
  unsigned int v26; // edi
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
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
  __int128 v43; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v44; // [rsp+48h] [rbp-B8h]
  void *v45; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  v44 = Mutex;
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v42);
  if ( 4 * v42 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_24;
  }
  *a2 = 0;
  v23 = (char *)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  v42 = (unsigned __int64)v23;
  if ( v23 )
  {
    v43 = 0;
    v28 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)&v43, Name, v23);
    v26 = v28;
    if ( v28 >= 0 )
    {
      *(_DWORD *)v25 = 1;
      *((_QWORD *)v25 + 1) = v6;
      v6 = 0;
      v44 = 0;
      *((_QWORD *)v25 + 2) = v43;
      *(_QWORD *)&v43 = 0;
      *((_QWORD *)v25 + 3) = *((_QWORD *)&v43 + 1);
      *((_QWORD *)&v43 + 1) = 0;
      memset_0(v25 + 40, 0, 0x108u);
      *((_QWORD *)v25 + 4) = 0;
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 40));
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 232), 0, 0);
      *((_QWORD *)v25 + 34) = 0;
      *((_QWORD *)v25 + 35) = 0;
      *((_QWORD *)v25 + 36) = 0;
      *((_QWORD *)v25 + 37) = 0;
      *a2 = v25;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v43);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)&v43);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v26, v41);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
  return v26;
}

```

## disassembly

```asm
0x180011a14  mov     [rsp-8+arg_10], rbx
0x180011a19  push    rbp
0x180011a1a  push    rsi
0x180011a1b  push    rdi
0x180011a1c  push    r14
0x180011a1e  push    r15
0x180011a20  lea     rbp, [rsp-180h]
0x180011a28  sub     rsp, 280h
0x180011a2f  mov     rax, cs:__security_cookie
0x180011a36  xor     rax, rsp
0x180011a39  mov     [rbp+1A0h+var_30], rax
0x180011a40  mov     r15, rdx
0x180011a43  mov     rbx, rcx
0x180011a46  mov     qword ptr [rdx], 0
0x180011a4d  call    cs:__imp_GetCurrentProcessId
0x180011a54  nop     dword ptr [rax+rax+00h]
0x180011a59  mov     r9d, eax
0x180011a5c  mov     [rsp+2A0h+var_278], rbx
0x180011a61  mov     edi, 130h
0x180011a66  mov     [rsp+2A0h+var_280], edi; int
0x180011a6a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011a71  lea     edx, [rdi-2Ch]; unsigned __int64
0x180011a74  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180011a79  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011a7e  nop
0x180011a7f  mov     r9d, 1F0001h; dwDesiredAccess
0x180011a85  xor     r8d, r8d; dwFlags
0x180011a88  lea     rdx, [rsp+2A0h+Name]; lpName
0x180011a8d  xor     ecx, ecx; lpMutexAttributes
0x180011a8f  call    cs:__imp_CreateMutexExW
0x180011a96  nop     dword ptr [rax+rax+00h]
0x180011a9b  mov     r14, rax
0x180011a9e  mov     [rsp+2A0h+var_258], rax
0x180011aa3  test    rax, rax
0x180011aa6  jnz     short loc_180011AB3
0x180011aa8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011aad  nop
0x180011aae  jmp     loc_180011D7C
0x180011ab3  xor     r8d, r8d; bAlertable
0x180011ab6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011ab9  mov     rcx, r14; hHandle
0x180011abc  call    cs:__imp_WaitForSingleObjectEx
0x180011ac3  nop     dword ptr [rax+rax+00h]
0x180011ac8  cmp     eax, 102h
0x180011acd  jz      short loc_180011ADF
0x180011acf  test    eax, 0FFFFFF7Fh
0x180011ad4  jnz     loc_180011DAE
0x180011ada  mov     rsi, r14
0x180011add  jmp     short loc_180011AE1
0x180011adf  xor     esi, esi
0x180011ae1  mov     [rsp+2A0h+var_250], rsi
0x180011ae6  mov     [rsp+2A0h+var_270], 0
0x180011aef  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x180011af4  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180011af9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180011afe  mov     ebx, eax
0x180011b00  test    eax, eax
0x180011b02  jns     loc_180011B8D
0x180011b08  mov     rcx, [rbp+1A8h]; this
0x180011b0f  mov     r9d, eax; char *
0x180011b12  mov     edx, 66h ; 'f'; void *
0x180011b17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b1c  mov     rcx, [rbp+1A8h]; this
0x180011b23  mov     r9d, ebx; char *
0x180011b26  mov     edx, 6Fh ; 'o'; void *
0x180011b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b30  mov     rcx, [rbp+1A8h]; this
0x180011b37  mov     r9d, ebx; char *
0x180011b3a  mov     edx, 12Eh; void *
0x180011b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011b44  nop
0x180011b45  test    rsi, rsi
0x180011b48  jz      short loc_180011B68
0x180011b4a  mov     rcx, rsi; hMutex
0x180011b4d  call    cs:__imp_ReleaseMutex
0x180011b54  nop     dword ptr [rax+rax+00h]
0x180011b59  mov     rcx, [rbp+1A8h]; this
0x180011b60  test    eax, eax
0x180011b62  jz      loc_180011DBB
0x180011b68  mov     rcx, r14; hObject
0x180011b6b  call    cs:__imp_CloseHandle
0x180011b72  nop     dword ptr [rax+rax+00h]
0x180011b77  mov     rcx, [rbp+1A8h]; this
0x180011b7e  test    eax, eax
0x180011b80  jz      loc_180011DC6
0x180011b86  mov     eax, ebx
0x180011b88  jmp     loc_180011D7C
0x180011b8d  mov     rax, [rsp+2A0h+var_270]
0x180011b92  lea     rcx, ds:0[rax*4]
0x180011b9a  test    rcx, rcx
0x180011b9d  jz      short loc_180011BAD
0x180011b9f  mov     [r15], rcx
0x180011ba2  mov     eax, [rcx]
0x180011ba4  inc     eax
0x180011ba6  mov     [rcx], eax
0x180011ba8  jmp     loc_180011D38
0x180011bad  mov     qword ptr [r15], 0
0x180011bb4  mov     rdx, rdi; dwBytes
0x180011bb7  mov     ecx, 8; dwFlags
0x180011bbc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011bc1  mov     rbx, rax
0x180011bc4  mov     [rsp+2A0h+var_270], rax
0x180011bc9  test    rax, rax
0x180011bcc  jnz     short loc_180011BEA
0x180011bce  mov     rcx, [rbp+1A8h]; this
0x180011bd5  mov     edi, 8007000Eh
0x180011bda  mov     r9d, edi; char *
0x180011bdd  mov     edx, 14Bh; void *
0x180011be2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011be7  nop
0x180011be8  jmp     short loc_180011C4F
0x180011bea  xorps   xmm0, xmm0
0x180011bed  movdqu  [rsp+2A0h+var_268], xmm0
0x180011bf3  mov     r8, rbx; void *
0x180011bf6  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180011bfb  lea     rcx, [rsp+2A0h+var_268]; this
0x180011c00  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180011c05  mov     edi, eax
0x180011c07  test    eax, eax
0x180011c09  jns     loc_180011CB1
0x180011c0f  mov     rcx, [rbp+1A8h]; this
0x180011c16  mov     r9d, eax; char *
0x180011c19  mov     edx, 14Eh; void *
0x180011c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c23  nop
0x180011c24  lea     rcx, [rsp+2A0h+var_268]; this
0x180011c29  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180011c2e  nop
0x180011c2f  call    cs:__imp_GetProcessHeap
0x180011c36  nop     dword ptr [rax+rax+00h]
0x180011c3b  mov     rcx, rax; hHeap
0x180011c3e  mov     r8, rbx; lpMem
0x180011c41  xor     edx, edx; dwFlags
0x180011c43  call    cs:__imp_HeapFree
0x180011c4a  nop     dword ptr [rax+rax+00h]
0x180011c4f  mov     rcx, [rbp+1A8h]; this
0x180011c56  mov     r9d, edi; char *
0x180011c59  mov     edx, 137h; void *
0x180011c5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c63  nop
0x180011c64  test    rsi, rsi
0x180011c67  jz      short loc_180011C87
0x180011c69  mov     rcx, rsi; hMutex
0x180011c6c  call    cs:__imp_ReleaseMutex
0x180011c73  nop     dword ptr [rax+rax+00h]
0x180011c78  mov     rcx, [rbp+1A8h]; this
0x180011c7f  test    eax, eax
0x180011c81  jz      loc_180011DD1
0x180011c87  test    r14, r14
0x180011c8a  jz      short loc_180011CAA
0x180011c8c  mov     rcx, r14; hObject
0x180011c8f  call    cs:__imp_CloseHandle
0x180011c96  nop     dword ptr [rax+rax+00h]
0x180011c9b  mov     rcx, [rbp+1A8h]; this
0x180011ca2  test    eax, eax
0x180011ca4  jz      loc_180011DDC
0x180011caa  mov     eax, edi
0x180011cac  jmp     loc_180011D7C
0x180011cb1  mov     dword ptr [rbx], 1
0x180011cb7  mov     [rbx+8], r14
0x180011cbb  xor     r14d, r14d
0x180011cbe  mov     [rsp+2A0h+var_258], r14
0x180011cc3  mov     rax, qword ptr [rsp+2A0h+var_268]
0x180011cc8  mov     [rbx+10h], rax
0x180011ccc  mov     qword ptr [rsp+2A0h+var_268], r14
0x180011cd1  mov     rax, qword ptr [rsp+2A0h+var_268+8]
0x180011cd6  mov     [rbx+18h], rax
0x180011cda  mov     qword ptr [rsp+2A0h+var_268+8], r14
0x180011cdf  lea     rcx, [rbx+28h]; void *
0x180011ce3  xor     edx, edx; Val
0x180011ce5  mov     r8d, 108h; Size
0x180011ceb  call    memset_0
0x180011cf0  xor     eax, eax
0x180011cf2  mov     [rbx+20h], rax
0x180011cf6  lea     rcx, [rbx+28h]; this
0x180011cfa  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180011cff  lea     rdi, [rbx+0E8h]
0x180011d06  xor     r8d, r8d; Flags
0x180011d09  xor     edx, edx; dwSpinCount
0x180011d0b  mov     rcx, rdi; lpCriticalSection
0x180011d0e  call    cs:__imp_InitializeCriticalSectionEx
0x180011d15  nop     dword ptr [rax+rax+00h]
0x180011d1a  mov     [rdi+28h], r14
0x180011d1e  mov     [rdi+30h], r14
0x180011d22  mov     [rdi+38h], r14
0x180011d26  mov     [rdi+40h], r14
0x180011d2a  mov     [r15], rbx
0x180011d2d  lea     rcx, [rsp+2A0h+var_268]; this
0x180011d32  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180011d37  nop
0x180011d38  test    rsi, rsi
0x180011d3b  jz      short loc_180011D5B
0x180011d3d  mov     rcx, rsi; hMutex
0x180011d40  call    cs:__imp_ReleaseMutex
0x180011d47  nop     dword ptr [rax+rax+00h]
0x180011d4c  mov     rcx, [rbp+1A8h]; this
0x180011d53  test    eax, eax
0x180011d55  jz      loc_180011DE7
0x180011d5b  test    r14, r14
0x180011d5e  jz      short loc_180011D7A
0x180011d60  mov     rcx, r14; hObject
0x180011d63  call    cs:__imp_CloseHandle
0x180011d6a  nop     dword ptr [rax+rax+00h]
0x180011d6f  mov     rcx, [rbp+1A8h]; this
0x180011d76  test    eax, eax
0x180011d78  jz      short loc_180011DA3
0x180011d7a  xor     eax, eax
0x180011d7c  mov     rcx, [rbp+1A0h+var_30]
0x180011d83  xor     rcx, rsp; StackCookie
0x180011d86  call    __security_check_cookie
0x180011d8b  mov     rbx, [rsp+2A0h+arg_10]
0x180011d93  add     rsp, 280h
0x180011d9a  pop     r15
0x180011d9c  pop     r14
0x180011d9e  pop     rdi
0x180011d9f  pop     rsi
0x180011da0  pop     rbp
0x180011da1  retn
0x180011da3  mov     edx, 0A0Bh; void *
0x180011da8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011dae  mov     rcx, [rbp+1A8h]; this
0x180011db5  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180011dbb  mov     edx, 0A15h; void *
0x180011dc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011dc6  mov     edx, 0A0Bh; void *
0x180011dcb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011dd1  mov     edx, 0A15h; void *
0x180011dd6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011ddc  mov     edx, 0A0Bh; void *
0x180011de1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011de7  mov     edx, 0A15h; void *
0x180011dec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
