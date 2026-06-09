# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800039f4`
- end: `0x180003dc6`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x18000410c`

## callees

- `0x180002d0c`
- `0x180003338`
- `0x1800039f4`
- `0x180003dcc`
- `0x18000436c`
- `0x1800055d0`
- `0x180006468`
- `0x180007a94`
- `0x1800084ac`
- `0x180008a0c`
- `0x180009500`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180003a2d`
- `KERNEL32!GetCurrentProcessId` at `0x180003a2d`
- `KERNEL32!CreateMutexExW` at `0x180003a71`
- `KERNEL32!CreateMutexExW` at `0x180003a71`
- `KERNEL32!GetProcessHeap` at `0x180003beb`
- `KERNEL32!GetProcessHeap` at `0x180003beb`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180003cb5`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180003cb5`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003a98`
- `KERNEL32!WaitForSingleObjectEx` at `0x180003a98`
- `KERNEL32!ReleaseMutex` at `0x180003b1f`
- `KERNEL32!ReleaseMutex` at `0x180003c27`
- `KERNEL32!ReleaseMutex` at `0x180003cf8`
- `KERNEL32!ReleaseMutex` at `0x180003b1f`
- `KERNEL32!ReleaseMutex` at `0x180003c27`
- `KERNEL32!ReleaseMutex` at `0x180003cf8`
- `KERNEL32!CloseHandle` at `0x180003b36`
- `KERNEL32!CloseHandle` at `0x180003c3e`
- `KERNEL32!CloseHandle` at `0x180003d14`
- `KERNEL32!CloseHandle` at `0x180003b36`
- `KERNEL32!CloseHandle` at `0x180003c3e`
- `KERNEL32!CloseHandle` at `0x180003d14`
- `KERNEL32!HeapFree` at `0x180003bff`
- `KERNEL32!HeapFree` at `0x180003bff`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  _DWORD *v23; // rax
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v41[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v41[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v41, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v38);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v39);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v41[0]);
  if ( 4 * v41[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
    goto LABEL_18;
  }
  *(_OWORD *)v41 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v41, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v41[0];
  *((_QWORD *)v25 + 3) = v41[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v41[0] = 0;
  v41[1] = 0;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v41);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return 0;
}

```

## disassembly

```asm
0x1800039f4  mov     [rsp-8+arg_10], rbx
0x1800039f9  push    rbp
0x1800039fa  push    rsi
0x1800039fb  push    rdi
0x1800039fc  push    r14
0x1800039fe  push    r15
0x180003a00  lea     rbp, [rsp-160h]
0x180003a08  sub     rsp, 260h
0x180003a0f  mov     rax, cs:__security_cookie
0x180003a16  xor     rax, rsp
0x180003a19  mov     [rbp+180h+var_30], rax
0x180003a20  mov     r15, rdx
0x180003a23  mov     qword ptr [rdx], 0
0x180003a2a  mov     rbx, rcx
0x180003a2d  call    cs:__imp_GetCurrentProcessId
0x180003a34  nop     dword ptr [rax+rax+00h]
0x180003a39  mov     r14d, 130h
0x180003a3f  mov     [rsp+280h+var_258], rbx
0x180003a44  mov     r9d, eax
0x180003a47  mov     [rsp+280h+var_260], r14d; int
0x180003a4c  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003a53  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003a58  lea     edx, [r14-2Ch]; unsigned __int64
0x180003a5c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003a61  mov     r9d, 1F0001h; dwDesiredAccess
0x180003a67  lea     rdx, [rsp+280h+Name]; lpName
0x180003a6c  xor     r8d, r8d; dwFlags
0x180003a6f  xor     ecx, ecx; lpMutexAttributes
0x180003a71  call    cs:__imp_CreateMutexExW
0x180003a78  nop     dword ptr [rax+rax+00h]
0x180003a7d  mov     rbx, rax
0x180003a80  test    rax, rax
0x180003a83  jnz     short loc_180003A8F
0x180003a85  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003a8a  jmp     loc_180003D26
0x180003a8f  xor     r8d, r8d; bAlertable
0x180003a92  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003a95  mov     rcx, rbx; hHandle
0x180003a98  call    cs:__imp_WaitForSingleObjectEx
0x180003a9f  nop     dword ptr [rax+rax+00h]
0x180003aa4  cmp     eax, 102h
0x180003aa9  jz      short loc_180003ABB
0x180003aab  test    eax, 0FFFFFF7Fh
0x180003ab0  jnz     loc_180003D71
0x180003ab6  mov     rdi, rbx
0x180003ab9  jmp     short loc_180003ABD
0x180003abb  xor     edi, edi
0x180003abd  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180003ac2  mov     [rsp+280h+var_250], 0
0x180003acb  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ad0  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003ad5  mov     esi, eax
0x180003ad7  test    eax, eax
0x180003ad9  jns     short loc_180003B51
0x180003adb  mov     rcx, [rbp+188h]; this
0x180003ae2  mov     r9d, eax; char *
0x180003ae5  mov     edx, 66h ; 'f'; void *
0x180003aea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003aef  mov     rcx, [rbp+188h]; this
0x180003af6  mov     r9d, esi; char *
0x180003af9  mov     edx, 6Fh ; 'o'; void *
0x180003afe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b03  mov     rcx, [rbp+188h]; this
0x180003b0a  mov     r9d, esi; char *
0x180003b0d  mov     edx, 12Eh; void *
0x180003b12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b17  test    rdi, rdi
0x180003b1a  jz      short loc_180003B33
0x180003b1c  mov     rcx, rdi; hMutex
0x180003b1f  call    cs:__imp_ReleaseMutex
0x180003b26  nop     dword ptr [rax+rax+00h]
0x180003b2b  test    eax, eax
0x180003b2d  jz      loc_180003D7E
0x180003b33  mov     rcx, rbx; hObject
0x180003b36  call    cs:__imp_CloseHandle
0x180003b3d  nop     dword ptr [rax+rax+00h]
0x180003b42  test    eax, eax
0x180003b44  jz      loc_180003D90
0x180003b4a  mov     eax, esi
0x180003b4c  jmp     loc_180003D26
0x180003b51  mov     rax, [rsp+280h+var_250]
0x180003b56  lea     rcx, ds:0[rax*4]
0x180003b5e  test    rcx, rcx
0x180003b61  jz      short loc_180003B71
0x180003b63  mov     [r15], rcx
0x180003b66  mov     eax, [rcx]
0x180003b68  inc     eax
0x180003b6a  mov     [rcx], eax
0x180003b6c  jmp     loc_180003CF0
0x180003b71  mov     rdx, r14; dwBytes
0x180003b74  mov     qword ptr [r15], 0
0x180003b7b  mov     ecx, 8; dwFlags
0x180003b80  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003b85  mov     r14, rax
0x180003b88  test    rax, rax
0x180003b8b  jnz     short loc_180003BA8
0x180003b8d  mov     rcx, [rbp+188h]; this
0x180003b94  mov     esi, 8007000Eh
0x180003b99  mov     r9d, esi; char *
0x180003b9c  mov     edx, 14Bh; void *
0x180003ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ba6  jmp     short loc_180003C0B
0x180003ba8  xorps   xmm0, xmm0
0x180003bab  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003bb0  mov     r8, r14; void *
0x180003bb3  lea     rcx, [rsp+280h+var_250]; this
0x180003bb8  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180003bbe  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x180003bc3  mov     esi, eax
0x180003bc5  test    eax, eax
0x180003bc7  jns     loc_180003C57
0x180003bcd  mov     rcx, [rbp+188h]; this
0x180003bd4  mov     r9d, eax; char *
0x180003bd7  mov     edx, 14Eh; void *
0x180003bdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003be1  lea     rcx, [rsp+280h+var_250]; this
0x180003be6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003beb  call    cs:__imp_GetProcessHeap
0x180003bf2  nop     dword ptr [rax+rax+00h]
0x180003bf7  mov     r8, r14; lpMem
0x180003bfa  xor     edx, edx; dwFlags
0x180003bfc  mov     rcx, rax; hHeap
0x180003bff  call    cs:__imp_HeapFree
0x180003c06  nop     dword ptr [rax+rax+00h]
0x180003c0b  mov     rcx, [rbp+188h]; this
0x180003c12  mov     r9d, esi; char *
0x180003c15  mov     edx, 137h; void *
0x180003c1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c1f  test    rdi, rdi
0x180003c22  jz      short loc_180003C3B
0x180003c24  mov     rcx, rdi; hMutex
0x180003c27  call    cs:__imp_ReleaseMutex
0x180003c2e  nop     dword ptr [rax+rax+00h]
0x180003c33  test    eax, eax
0x180003c35  jz      loc_180003DA2
0x180003c3b  mov     rcx, rbx; hObject
0x180003c3e  call    cs:__imp_CloseHandle
0x180003c45  nop     dword ptr [rax+rax+00h]
0x180003c4a  test    eax, eax
0x180003c4c  jz      loc_180003D5F
0x180003c52  jmp     loc_180003B4A
0x180003c57  mov     rax, [rsp+280h+var_250]
0x180003c5c  lea     rcx, [r14+28h]; void *
0x180003c60  mov     [r14+10h], rax
0x180003c64  xor     edx, edx; Val
0x180003c66  mov     rax, [rsp+280h+var_250+8]
0x180003c6b  mov     r8d, 108h; Size
0x180003c71  mov     [r14+18h], rax
0x180003c75  mov     dword ptr [r14], 1
0x180003c7c  mov     [r14+8], rbx
0x180003c80  mov     [rsp+280h+var_250], 0
0x180003c89  mov     [rsp+280h+var_250+8], 0
0x180003c92  call    memset_0
0x180003c97  xor     eax, eax
0x180003c99  lea     rcx, [r14+28h]; this
0x180003c9d  mov     [r14+20h], rax
0x180003ca1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003ca6  lea     rbx, [r14+0E8h]
0x180003cad  xor     r8d, r8d; Flags
0x180003cb0  mov     rcx, rbx; lpCriticalSection
0x180003cb3  xor     edx, edx; dwSpinCount
0x180003cb5  call    cs:__imp_InitializeCriticalSectionEx
0x180003cbc  nop     dword ptr [rax+rax+00h]
0x180003cc1  mov     qword ptr [rbx+28h], 0
0x180003cc9  lea     rcx, [rsp+280h+var_250]; this
0x180003cce  mov     qword ptr [rbx+30h], 0
0x180003cd6  mov     qword ptr [rbx+38h], 0
0x180003cde  mov     qword ptr [rbx+40h], 0
0x180003ce6  mov     [r15], r14
0x180003ce9  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180003cee  xor     ebx, ebx
0x180003cf0  test    rdi, rdi
0x180003cf3  jz      short loc_180003D0C
0x180003cf5  mov     rcx, rdi; hMutex
0x180003cf8  call    cs:__imp_ReleaseMutex
0x180003cff  nop     dword ptr [rax+rax+00h]
0x180003d04  test    eax, eax
0x180003d06  jz      loc_180003DB4
0x180003d0c  test    rbx, rbx
0x180003d0f  jz      short loc_180003D24
0x180003d11  mov     rcx, rbx; hObject
0x180003d14  call    cs:__imp_CloseHandle
0x180003d1b  nop     dword ptr [rax+rax+00h]
0x180003d20  test    eax, eax
0x180003d22  jz      short loc_180003D4D
0x180003d24  xor     eax, eax
0x180003d26  mov     rcx, [rbp+180h+var_30]
0x180003d2d  xor     rcx, rsp; StackCookie
0x180003d30  call    __security_check_cookie
0x180003d35  mov     rbx, [rsp+280h+arg_10]
0x180003d3d  add     rsp, 260h
0x180003d44  pop     r15
0x180003d46  pop     r14
0x180003d48  pop     rdi
0x180003d49  pop     rsi
0x180003d4a  pop     rbp
0x180003d4b  retn
0x180003d4d  mov     rcx, [rbp+188h]; this
0x180003d54  mov     edx, 0A0Bh; void *
0x180003d59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d5f  mov     rcx, [rbp+188h]; this
0x180003d66  mov     edx, 0A0Bh; void *
0x180003d6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d71  mov     rcx, [rbp+188h]; this
0x180003d78  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003d7e  mov     rcx, [rbp+188h]; this
0x180003d85  mov     edx, 0A15h; void *
0x180003d8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003d90  mov     rcx, [rbp+188h]; this
0x180003d97  mov     edx, 0A0Bh; void *
0x180003d9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003da2  mov     rcx, [rbp+188h]; this
0x180003da9  mov     edx, 0A15h; void *
0x180003dae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003db4  mov     rcx, [rbp+188h]; this
0x180003dbb  mov     edx, 0A15h; void *
0x180003dc0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
