# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14006c548`
- end: `0x14006c8ed`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `933`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14006dd14`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x14006c234`
- `0x14006c548`
- `0x14006ce4c`
- `0x14006d1f8`
- `0x14006da90`
- `0x14006ea30`
- `0x14006fdf4`
- `0x140070cac`
- `0x1400714b0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x14006c5c6`
- `KERNEL32!CreateMutexExW` at `0x14006c5c6`
- `KERNEL32!WaitForSingleObjectEx` at `0x14006c5ed`
- `KERNEL32!WaitForSingleObjectEx` at `0x14006c5ed`
- `KERNEL32!ReleaseMutex` at `0x14006c674`
- `KERNEL32!ReleaseMutex` at `0x14006c77c`
- `KERNEL32!ReleaseMutex` at `0x14006c81f`
- `KERNEL32!ReleaseMutex` at `0x14006c674`
- `KERNEL32!ReleaseMutex` at `0x14006c77c`
- `KERNEL32!ReleaseMutex` at `0x14006c81f`
- `KERNEL32!GetCurrentProcessId` at `0x14006c581`
- `KERNEL32!GetCurrentProcessId` at `0x14006c581`
- `KERNEL32!GetProcessHeap` at `0x14006c740`
- `KERNEL32!GetProcessHeap` at `0x14006c740`
- `KERNEL32!CloseHandle` at `0x14006c68b`
- `KERNEL32!CloseHandle` at `0x14006c793`
- `KERNEL32!CloseHandle` at `0x14006c83b`
- `KERNEL32!CloseHandle` at `0x14006c68b`
- `KERNEL32!CloseHandle` at `0x14006c793`
- `KERNEL32!CloseHandle` at `0x14006c83b`
- `KERNEL32!HeapFree` at `0x14006c754`
- `KERNEL32!HeapFree` at `0x14006c754`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
  unsigned __int64 v34; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v42[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v42[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, v42, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v39);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v40);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v42[0]);
  if ( 4 * v42[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_23;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v25 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 120);
    goto LABEL_18;
  }
  *(_OWORD *)v42 = 0;
  v27 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)v42, Name, v23);
  v15 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
LABEL_18:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v15, v41);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return v15;
  }
  *((_QWORD *)v25 + 2) = v42[0];
  v34 = v42[1];
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  v42[0] = 0;
  *((_QWORD *)v25 + 3) = v34;
  v42[1] = 0;
  memset_0((char *)v25 + 34, 0, 0x56u);
  *((_WORD *)v25 + 16) = 88;
  v25[9] = 1;
  memset_0(v25 + 10, 0, 0x50u);
  *a2 = v25;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v42);
  v6 = 0;
LABEL_23:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x14006c548  mov     [rsp-8+arg_10], rbx
0x14006c54d  push    rbp
0x14006c54e  push    rsi
0x14006c54f  push    rdi
0x14006c550  push    r14
0x14006c552  push    r15
0x14006c554  lea     rbp, [rsp-160h]
0x14006c55c  sub     rsp, 260h
0x14006c563  mov     rax, cs:__security_cookie
0x14006c56a  xor     rax, rsp
0x14006c56d  mov     [rbp+180h+var_30], rax
0x14006c574  mov     r15, rdx
0x14006c577  mov     qword ptr [rdx], 0
0x14006c57e  mov     rbx, rcx
0x14006c581  call    cs:__imp_GetCurrentProcessId
0x14006c588  nop     dword ptr [rax+rax+00h]
0x14006c58d  mov     r14d, 78h ; 'x'
0x14006c593  mov     [rsp+280h+var_258], rbx
0x14006c598  mov     r9d, eax
0x14006c59b  mov     [rsp+280h+var_260], r14d; int
0x14006c5a0  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14006c5a7  mov     edx, 104h; unsigned __int64
0x14006c5ac  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14006c5b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14006c5b6  mov     r9d, 1F0001h; dwDesiredAccess
0x14006c5bc  lea     rdx, [rsp+280h+Name]; lpName
0x14006c5c1  xor     r8d, r8d; dwFlags
0x14006c5c4  xor     ecx, ecx; lpMutexAttributes
0x14006c5c6  call    cs:__imp_CreateMutexExW
0x14006c5cd  nop     dword ptr [rax+rax+00h]
0x14006c5d2  mov     rbx, rax
0x14006c5d5  test    rax, rax
0x14006c5d8  jnz     short loc_14006C5E4
0x14006c5da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14006c5df  jmp     loc_14006C84D
0x14006c5e4  xor     r8d, r8d; bAlertable
0x14006c5e7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14006c5ea  mov     rcx, rbx; hHandle
0x14006c5ed  call    cs:__imp_WaitForSingleObjectEx
0x14006c5f4  nop     dword ptr [rax+rax+00h]
0x14006c5f9  cmp     eax, 102h
0x14006c5fe  jz      short loc_14006C610
0x14006c600  test    eax, 0FFFFFF7Fh
0x14006c605  jnz     loc_14006C898
0x14006c60b  mov     rdi, rbx
0x14006c60e  jmp     short loc_14006C612
0x14006c610  xor     edi, edi
0x14006c612  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x14006c617  mov     [rsp+280h+var_250], 0
0x14006c620  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14006c625  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14006c62a  mov     esi, eax
0x14006c62c  test    eax, eax
0x14006c62e  jns     short loc_14006C6A6
0x14006c630  mov     rcx, [rbp+188h]; this
0x14006c637  mov     r9d, eax; char *
0x14006c63a  mov     edx, 66h ; 'f'; void *
0x14006c63f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c644  mov     rcx, [rbp+188h]; this
0x14006c64b  mov     r9d, esi; char *
0x14006c64e  mov     edx, 6Fh ; 'o'; void *
0x14006c653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c658  mov     rcx, [rbp+188h]; this
0x14006c65f  mov     r9d, esi; char *
0x14006c662  mov     edx, 12Eh; void *
0x14006c667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c66c  test    rdi, rdi
0x14006c66f  jz      short loc_14006C688
0x14006c671  mov     rcx, rdi; hMutex
0x14006c674  call    cs:__imp_ReleaseMutex
0x14006c67b  nop     dword ptr [rax+rax+00h]
0x14006c680  test    eax, eax
0x14006c682  jz      loc_14006C8A5
0x14006c688  mov     rcx, rbx; hObject
0x14006c68b  call    cs:__imp_CloseHandle
0x14006c692  nop     dword ptr [rax+rax+00h]
0x14006c697  test    eax, eax
0x14006c699  jz      loc_14006C8B7
0x14006c69f  mov     eax, esi
0x14006c6a1  jmp     loc_14006C84D
0x14006c6a6  mov     rax, [rsp+280h+var_250]
0x14006c6ab  lea     rcx, ds:0[rax*4]
0x14006c6b3  test    rcx, rcx
0x14006c6b6  jz      short loc_14006C6C6
0x14006c6b8  mov     [r15], rcx
0x14006c6bb  mov     eax, [rcx]
0x14006c6bd  inc     eax
0x14006c6bf  mov     [rcx], eax
0x14006c6c1  jmp     loc_14006C817
0x14006c6c6  mov     rdx, r14; dwBytes
0x14006c6c9  mov     qword ptr [r15], 0
0x14006c6d0  mov     ecx, 8; dwFlags
0x14006c6d5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14006c6da  mov     r14, rax
0x14006c6dd  test    rax, rax
0x14006c6e0  jnz     short loc_14006C6FD
0x14006c6e2  mov     rcx, [rbp+188h]; this
0x14006c6e9  mov     esi, 8007000Eh
0x14006c6ee  mov     r9d, esi; char *
0x14006c6f1  mov     edx, 14Bh; void *
0x14006c6f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c6fb  jmp     short loc_14006C760
0x14006c6fd  xorps   xmm0, xmm0
0x14006c700  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14006c705  mov     r8, r14; void *
0x14006c708  lea     rcx, [rsp+280h+var_250]; this
0x14006c70d  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x14006c713  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x14006c718  mov     esi, eax
0x14006c71a  test    eax, eax
0x14006c71c  jns     loc_14006C7AC
0x14006c722  mov     rcx, [rbp+188h]; this
0x14006c729  mov     r9d, eax; char *
0x14006c72c  mov     edx, 14Eh; void *
0x14006c731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c736  lea     rcx, [rsp+280h+var_250]; this
0x14006c73b  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14006c740  call    cs:__imp_GetProcessHeap
0x14006c747  nop     dword ptr [rax+rax+00h]
0x14006c74c  mov     r8, r14; lpMem
0x14006c74f  xor     edx, edx; dwFlags
0x14006c751  mov     rcx, rax; hHeap
0x14006c754  call    cs:__imp_HeapFree
0x14006c75b  nop     dword ptr [rax+rax+00h]
0x14006c760  mov     rcx, [rbp+188h]; this
0x14006c767  mov     r9d, esi; char *
0x14006c76a  mov     edx, 137h; void *
0x14006c76f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c774  test    rdi, rdi
0x14006c777  jz      short loc_14006C790
0x14006c779  mov     rcx, rdi; hMutex
0x14006c77c  call    cs:__imp_ReleaseMutex
0x14006c783  nop     dword ptr [rax+rax+00h]
0x14006c788  test    eax, eax
0x14006c78a  jz      loc_14006C8C9
0x14006c790  mov     rcx, rbx; hObject
0x14006c793  call    cs:__imp_CloseHandle
0x14006c79a  nop     dword ptr [rax+rax+00h]
0x14006c79f  test    eax, eax
0x14006c7a1  jz      loc_14006C886
0x14006c7a7  jmp     loc_14006C69F
0x14006c7ac  mov     rax, [rsp+280h+var_250]
0x14006c7b1  lea     rcx, [r14+22h]; void *
0x14006c7b5  xor     edx, edx; Val
0x14006c7b7  mov     [r14+10h], rax
0x14006c7bb  mov     rax, [rsp+280h+var_250+8]
0x14006c7c0  mov     dword ptr [r14], 1
0x14006c7c7  mov     [r14+8], rbx
0x14006c7cb  lea     r8d, [rdx+56h]; Size
0x14006c7cf  mov     [rsp+280h+var_250], 0
0x14006c7d8  mov     [r14+18h], rax
0x14006c7dc  mov     [rsp+280h+var_250+8], 0
0x14006c7e5  call    memset_0
0x14006c7ea  xor     edx, edx; Val
0x14006c7ec  mov     word ptr [r14+20h], 58h ; 'X'
0x14006c7f3  lea     rcx, [r14+28h]; void *
0x14006c7f7  mov     dword ptr [r14+24h], 1
0x14006c7ff  lea     r8d, [rdx+50h]; Size
0x14006c803  call    memset_0
0x14006c808  lea     rcx, [rsp+280h+var_250]; this
0x14006c80d  mov     [r15], r14
0x14006c810  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x14006c815  xor     ebx, ebx
0x14006c817  test    rdi, rdi
0x14006c81a  jz      short loc_14006C833
0x14006c81c  mov     rcx, rdi; hMutex
0x14006c81f  call    cs:__imp_ReleaseMutex
0x14006c826  nop     dword ptr [rax+rax+00h]
0x14006c82b  test    eax, eax
0x14006c82d  jz      loc_14006C8DB
0x14006c833  test    rbx, rbx
0x14006c836  jz      short loc_14006C84B
0x14006c838  mov     rcx, rbx; hObject
0x14006c83b  call    cs:__imp_CloseHandle
0x14006c842  nop     dword ptr [rax+rax+00h]
0x14006c847  test    eax, eax
0x14006c849  jz      short loc_14006C874
0x14006c84b  xor     eax, eax
0x14006c84d  mov     rcx, [rbp+180h+var_30]
0x14006c854  xor     rcx, rsp; StackCookie
0x14006c857  call    __security_check_cookie
0x14006c85c  mov     rbx, [rsp+280h+arg_10]
0x14006c864  add     rsp, 260h
0x14006c86b  pop     r15
0x14006c86d  pop     r14
0x14006c86f  pop     rdi
0x14006c870  pop     rsi
0x14006c871  pop     rbp
0x14006c872  retn
0x14006c874  mov     rcx, [rbp+188h]; this
0x14006c87b  mov     edx, 0A0Bh; void *
0x14006c880  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006c886  mov     rcx, [rbp+188h]; this
0x14006c88d  mov     edx, 0A0Bh; void *
0x14006c892  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006c898  mov     rcx, [rbp+188h]; this
0x14006c89f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14006c8a5  mov     rcx, [rbp+188h]; this
0x14006c8ac  mov     edx, 0A15h; void *
0x14006c8b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006c8b7  mov     rcx, [rbp+188h]; this
0x14006c8be  mov     edx, 0A0Bh; void *
0x14006c8c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006c8c9  mov     rcx, [rbp+188h]; this
0x14006c8d0  mov     edx, 0A15h; void *
0x14006c8d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14006c8db  mov     rcx, [rbp+188h]; this
0x14006c8e2  mov     edx, 0A15h; void *
0x14006c8e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
