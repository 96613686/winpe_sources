# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006f1c`
- end: `0x1800072f4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `984`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180008cbc`

## callees

- `0x180003400`
- `0x180004558`
- `0x180006a64`
- `0x180006f1c`
- `0x180007808`
- `0x180007dcc`
- `0x1800088b4`
- `0x180009a5c`
- `0x18000b470`
- `0x18000bf2c`
- `0x18000c49c`
- `0x18000ce74`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180006f9a`
- `KERNEL32!CreateMutexExW` at `0x180006f9a`
- `KERNEL32!GetCurrentProcessId` at `0x180006f55`
- `KERNEL32!GetCurrentProcessId` at `0x180006f55`
- `KERNEL32!GetProcessHeap` at `0x18000713b`
- `KERNEL32!GetProcessHeap` at `0x18000713b`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006fc1`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006fc1`
- `KERNEL32!ReleaseMutex` at `0x180007061`
- `KERNEL32!ReleaseMutex` at `0x18000717e`
- `KERNEL32!ReleaseMutex` at `0x180007221`
- `KERNEL32!ReleaseMutex` at `0x180007061`
- `KERNEL32!ReleaseMutex` at `0x18000717e`
- `KERNEL32!ReleaseMutex` at `0x180007221`
- `KERNEL32!HeapFree` at `0x18000714f`
- `KERNEL32!HeapFree` at `0x18000714f`
- `KERNEL32!CloseHandle` at `0x180007078`
- `KERNEL32!CloseHandle` at `0x180007195`
- `KERNEL32!CloseHandle` at `0x18000723d`
- `KERNEL32!CloseHandle` at `0x180007078`
- `KERNEL32!CloseHandle` at `0x180007195`
- `KERNEL32!CloseHandle` at `0x18000723d`

## pseudocode

```c
signed int __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rbx
  DWORD v9; // eax
  __int64 v10; // rdx
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
  unsigned __int64 v29; // rax
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  unsigned __int64 v34[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, 3585, v11, v12);
    v13 = v7;
  }
  v34[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, v34, (bool *)v12);
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
  v20 = (_DWORD *)(4 * v34[0]);
  if ( 4 * v34[0] )
  {
    *a2 = v20;
    ++*v20;
    goto LABEL_23;
  }
  *a2 = 0;
  v21 = wil::details::ProcessHeapAlloc(8u, 0x78u);
  v22 = v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (__int64)"wil", (const char *)0x8007000ELL);
    goto LABEL_18;
  }
  *(_OWORD *)v34 = 0;
  v23 = wil::details_abi::SemaphoreValue::CreateFromPointer(
          (wil::details_abi::SemaphoreValue *)v34,
          Name,
          (unsigned __int64)v21);
  v15 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (__int64)"wil", (const char *)(unsigned int)v23);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
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
  *((_QWORD *)v22 + 2) = v34[0];
  v29 = v34[1];
  *v22 = 1;
  *((_QWORD *)v22 + 1) = v7;
  v34[0] = 0;
  *((_QWORD *)v22 + 3) = v29;
  v34[1] = 0;
  memset_0((char *)v22 + 34, 0, 0x56u);
  *((_WORD *)v22 + 16) = 88;
  v22[9] = 1;
  memset_0(v22 + 10, 0, 0x50u);
  *a2 = v22;
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)v34);
  v7 = 0;
LABEL_23:
  if ( v13 && !ReleaseMutex(v13) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v30, v31);
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  return 0;
}

```

## disassembly

```asm
0x180006f1c  mov     [rsp-8+arg_10], rbx
0x180006f21  push    rbp
0x180006f22  push    rsi
0x180006f23  push    rdi
0x180006f24  push    r14
0x180006f26  push    r15
0x180006f28  lea     rbp, [rsp-160h]
0x180006f30  sub     rsp, 260h
0x180006f37  mov     rax, cs:__security_cookie
0x180006f3e  xor     rax, rsp
0x180006f41  mov     [rbp+180h+var_30], rax
0x180006f48  mov     r15, rdx
0x180006f4b  mov     qword ptr [rdx], 0
0x180006f52  mov     rbx, rcx
0x180006f55  call    cs:__imp_GetCurrentProcessId
0x180006f5c  nop     dword ptr [rax+rax+00h]
0x180006f61  mov     r14d, 78h ; 'x'
0x180006f67  mov     [rsp+280h+var_258], rbx
0x180006f6c  mov     r9d, eax
0x180006f6f  mov     [rsp+280h+var_260], r14d; int
0x180006f74  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006f7b  mov     edx, 104h; unsigned __int64
0x180006f80  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006f85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006f8a  mov     r9d, 1F0001h; dwDesiredAccess
0x180006f90  lea     rdx, [rsp+280h+Name]; lpName
0x180006f95  xor     r8d, r8d; dwFlags
0x180006f98  xor     ecx, ecx; lpMutexAttributes
0x180006f9a  call    cs:__imp_CreateMutexExW
0x180006fa1  nop     dword ptr [rax+rax+00h]
0x180006fa6  mov     rbx, rax
0x180006fa9  test    rax, rax
0x180006fac  jnz     short loc_180006FB8
0x180006fae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006fb3  jmp     loc_18000724F
0x180006fb8  xor     r8d, r8d; bAlertable
0x180006fbb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006fbe  mov     rcx, rbx; hHandle
0x180006fc1  call    cs:__imp_WaitForSingleObjectEx
0x180006fc8  nop     dword ptr [rax+rax+00h]
0x180006fcd  cmp     eax, 102h
0x180006fd2  jz      short loc_180006FE4
0x180006fd4  test    eax, 0FFFFFF7Fh
0x180006fd9  jnz     loc_18000729A
0x180006fdf  mov     rdi, rbx
0x180006fe2  jmp     short loc_180006FE6
0x180006fe4  xor     edi, edi
0x180006fe6  lea     r8, [rsp+280h+var_250]; unsigned __int64 *
0x180006feb  mov     [rsp+280h+var_250], 0
0x180006ff4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006ff9  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006ffe  mov     esi, eax
0x180007000  test    eax, eax
0x180007002  jns     loc_180007093
0x180007008  mov     rcx, [rbp+188h]; this
0x18000700f  lea     r8, aWil; "wil"
0x180007016  mov     r9d, eax; char *
0x180007019  mov     edx, 66h ; 'f'; void *
0x18000701e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007023  mov     rcx, [rbp+188h]; this
0x18000702a  lea     r8, aWil; "wil"
0x180007031  mov     r9d, esi; char *
0x180007034  mov     edx, 6Fh ; 'o'; void *
0x180007039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000703e  mov     rcx, [rbp+188h]; this
0x180007045  lea     r8, aWil; "wil"
0x18000704c  mov     r9d, esi; char *
0x18000704f  mov     edx, 12Eh; void *
0x180007054  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007059  test    rdi, rdi
0x18000705c  jz      short loc_180007075
0x18000705e  mov     rcx, rdi; hMutex
0x180007061  call    cs:__imp_ReleaseMutex
0x180007068  nop     dword ptr [rax+rax+00h]
0x18000706d  test    eax, eax
0x18000706f  jz      loc_1800072AC
0x180007075  mov     rcx, rbx; hObject
0x180007078  call    cs:__imp_CloseHandle
0x18000707f  nop     dword ptr [rax+rax+00h]
0x180007084  test    eax, eax
0x180007086  jz      loc_1800072BE
0x18000708c  mov     eax, esi
0x18000708e  jmp     loc_18000724F
0x180007093  mov     rax, [rsp+280h+var_250]
0x180007098  lea     rcx, ds:0[rax*4]
0x1800070a0  test    rcx, rcx
0x1800070a3  jz      short loc_1800070B3
0x1800070a5  mov     [r15], rcx
0x1800070a8  mov     eax, [rcx]
0x1800070aa  inc     eax
0x1800070ac  mov     [rcx], eax
0x1800070ae  jmp     loc_180007219
0x1800070b3  mov     rdx, r14; dwBytes
0x1800070b6  mov     qword ptr [r15], 0
0x1800070bd  mov     ecx, 8; dwFlags
0x1800070c2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800070c7  mov     r14, rax
0x1800070ca  test    rax, rax
0x1800070cd  jnz     short loc_1800070F1
0x1800070cf  mov     rcx, [rbp+188h]; this
0x1800070d6  lea     r8, aWil; "wil"
0x1800070dd  mov     esi, 8007000Eh
0x1800070e2  mov     edx, 14Bh; void *
0x1800070e7  mov     r9d, esi; char *
0x1800070ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070ef  jmp     short loc_18000715B
0x1800070f1  xorps   xmm0, xmm0
0x1800070f4  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800070f9  mov     r8, r14; void *
0x1800070fc  lea     rcx, [rsp+280h+var_250]; this
0x180007101  movdqu  xmmword ptr [rsp+280h+var_250], xmm0
0x180007107  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x18000710c  mov     esi, eax
0x18000710e  test    eax, eax
0x180007110  jns     loc_1800071AE
0x180007116  mov     rcx, [rbp+188h]; this
0x18000711d  lea     r8, aWil; "wil"
0x180007124  mov     r9d, eax; char *
0x180007127  mov     edx, 14Eh; void *
0x18000712c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007131  lea     rcx, [rsp+280h+var_250]; this
0x180007136  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000713b  call    cs:__imp_GetProcessHeap
0x180007142  nop     dword ptr [rax+rax+00h]
0x180007147  mov     r8, r14; lpMem
0x18000714a  xor     edx, edx; dwFlags
0x18000714c  mov     rcx, rax; hHeap
0x18000714f  call    cs:__imp_HeapFree
0x180007156  nop     dword ptr [rax+rax+00h]
0x18000715b  mov     rcx, [rbp+188h]; this
0x180007162  lea     r8, aWil; "wil"
0x180007169  mov     r9d, esi; char *
0x18000716c  mov     edx, 137h; void *
0x180007171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007176  test    rdi, rdi
0x180007179  jz      short loc_180007192
0x18000717b  mov     rcx, rdi; hMutex
0x18000717e  call    cs:__imp_ReleaseMutex
0x180007185  nop     dword ptr [rax+rax+00h]
0x18000718a  test    eax, eax
0x18000718c  jz      loc_1800072D0
0x180007192  mov     rcx, rbx; hObject
0x180007195  call    cs:__imp_CloseHandle
0x18000719c  nop     dword ptr [rax+rax+00h]
0x1800071a1  test    eax, eax
0x1800071a3  jz      loc_180007288
0x1800071a9  jmp     loc_18000708C
0x1800071ae  mov     rax, [rsp+280h+var_250]
0x1800071b3  lea     rcx, [r14+22h]; void *
0x1800071b7  xor     edx, edx; Val
0x1800071b9  mov     [r14+10h], rax
0x1800071bd  mov     rax, [rsp+280h+var_250+8]
0x1800071c2  mov     dword ptr [r14], 1
0x1800071c9  mov     [r14+8], rbx
0x1800071cd  lea     r8d, [rdx+56h]; Size
0x1800071d1  mov     [rsp+280h+var_250], 0
0x1800071da  mov     [r14+18h], rax
0x1800071de  mov     [rsp+280h+var_250+8], 0
0x1800071e7  call    memset_0
0x1800071ec  xor     edx, edx; Val
0x1800071ee  mov     word ptr [r14+20h], 58h ; 'X'
0x1800071f5  lea     rcx, [r14+28h]; void *
0x1800071f9  mov     dword ptr [r14+24h], 1
0x180007201  lea     r8d, [rdx+50h]; Size
0x180007205  call    memset_0
0x18000720a  lea     rcx, [rsp+280h+var_250]; this
0x18000720f  mov     [r15], r14
0x180007212  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180007217  xor     ebx, ebx
0x180007219  test    rdi, rdi
0x18000721c  jz      short loc_180007235
0x18000721e  mov     rcx, rdi; hMutex
0x180007221  call    cs:__imp_ReleaseMutex
0x180007228  nop     dword ptr [rax+rax+00h]
0x18000722d  test    eax, eax
0x18000722f  jz      loc_1800072E2
0x180007235  test    rbx, rbx
0x180007238  jz      short loc_18000724D
0x18000723a  mov     rcx, rbx; hObject
0x18000723d  call    cs:__imp_CloseHandle
0x180007244  nop     dword ptr [rax+rax+00h]
0x180007249  test    eax, eax
0x18000724b  jz      short loc_180007276
0x18000724d  xor     eax, eax
0x18000724f  mov     rcx, [rbp+180h+var_30]
0x180007256  xor     rcx, rsp; StackCookie
0x180007259  call    __security_check_cookie
0x18000725e  mov     rbx, [rsp+280h+arg_10]
0x180007266  add     rsp, 260h
0x18000726d  pop     r15
0x18000726f  pop     r14
0x180007271  pop     rdi
0x180007272  pop     rsi
0x180007273  pop     rbp
0x180007274  retn
0x180007276  mov     rcx, [rbp+188h]; this
0x18000727d  mov     edx, 0A0Bh; void *
0x180007282  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007288  mov     rcx, [rbp+188h]; this
0x18000728f  mov     edx, 0A0Bh; void *
0x180007294  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000729a  mov     rcx, [rbp+188h]; this
0x1800072a1  mov     edx, 0E01h; void *
0x1800072a6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800072ac  mov     rcx, [rbp+188h]; this
0x1800072b3  mov     edx, 0A15h; void *
0x1800072b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800072be  mov     rcx, [rbp+188h]; this
0x1800072c5  mov     edx, 0A0Bh; void *
0x1800072ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800072d0  mov     rcx, [rbp+188h]; this
0x1800072d7  mov     edx, 0A15h; void *
0x1800072dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800072e2  mov     rcx, [rbp+188h]; this
0x1800072e9  mov     edx, 0A15h; void *
0x1800072ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
