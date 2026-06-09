# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006e28`
- end: `0x1800071f5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180008c9c`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180006e28`
- `0x1800076e8`
- `0x180007d5c`
- `0x1800088b0`
- `0x1800098e4`
- `0x18000b29c`
- `0x18000bed0`
- `0x18000c35c`
- `0x18000cce0`
- `0x18000ccf0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180006ea0`
- `KERNEL32!CreateMutexExW` at `0x180006ea0`
- `KERNEL32!GetCurrentProcessId` at `0x180006e61`
- `KERNEL32!GetCurrentProcessId` at `0x180006e61`
- `KERNEL32!GetProcessHeap` at `0x18000705e`
- `KERNEL32!GetProcessHeap` at `0x18000705e`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006ec1`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006ec1`
- `KERNEL32!ReleaseMutex` at `0x180006f57`
- `KERNEL32!ReleaseMutex` at `0x180007095`
- `KERNEL32!ReleaseMutex` at `0x180007105`
- `KERNEL32!ReleaseMutex` at `0x180006f57`
- `KERNEL32!ReleaseMutex` at `0x180007095`
- `KERNEL32!ReleaseMutex` at `0x180007105`
- `KERNEL32!HeapFree` at `0x18000706c`
- `KERNEL32!HeapFree` at `0x18000706c`
- `KERNEL32!CloseHandle` at `0x180006f68`
- `KERNEL32!CloseHandle` at `0x180007038`
- `KERNEL32!CloseHandle` at `0x180007050`
- `KERNEL32!CloseHandle` at `0x1800070a6`
- `KERNEL32!CloseHandle` at `0x18000711b`
- `KERNEL32!CloseHandle` at `0x180006f68`
- `KERNEL32!CloseHandle` at `0x180007038`
- `KERNEL32!CloseHandle` at `0x180007050`
- `KERNEL32!CloseHandle` at `0x1800070a6`
- `KERNEL32!CloseHandle` at `0x18000711b`

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
  bool v9; // dl
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
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v42);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v24 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v21 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    v26 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v23,
            v21 >> 2);
    v25 = v26;
    if ( v26 >= 0 )
    {
      v36 = *(_OWORD *)hObject;
      *(_DWORD *)v24 = 1;
      v24[1] = v6;
      *((_OWORD *)v24 + 1) = v36;
      memset_0((char *)v24 + 34, 0, 0x56u);
      *((_WORD *)v24 + 16) = 88;
      *((_DWORD *)v24 + 9) = 1;
      memset_0(v24 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v24;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v26, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
  }
  else
  {
    v25 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v25, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v32, v33);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
  return v25;
}

```

## disassembly

```asm
0x180006e28  mov     [rsp-8+arg_10], rbx
0x180006e2d  push    rbp
0x180006e2e  push    rsi
0x180006e2f  push    rdi
0x180006e30  push    r14
0x180006e32  push    r15
0x180006e34  lea     rbp, [rsp-160h]
0x180006e3c  sub     rsp, 260h
0x180006e43  mov     rax, cs:__security_cookie
0x180006e4a  xor     rax, rsp
0x180006e4d  mov     [rbp+180h+var_30], rax
0x180006e54  mov     r15, rdx
0x180006e57  mov     qword ptr [rdx], 0
0x180006e5e  mov     rbx, rcx
0x180006e61  call    cs:__imp_GetCurrentProcessId
0x180006e67  mov     r14d, 78h ; 'x'
0x180006e6d  mov     [rsp+280h+var_258], rbx
0x180006e72  mov     r9d, eax
0x180006e75  mov     [rsp+280h+var_260], r14d; int
0x180006e7a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006e81  mov     edx, 104h; unsigned __int64
0x180006e86  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006e8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006e90  mov     r9d, 1F0001h; dwDesiredAccess
0x180006e96  lea     rdx, [rsp+280h+Name]; lpName
0x180006e9b  xor     r8d, r8d; dwFlags
0x180006e9e  xor     ecx, ecx; lpMutexAttributes
0x180006ea0  call    cs:__imp_CreateMutexExW
0x180006ea6  mov     rbx, rax
0x180006ea9  test    rax, rax
0x180006eac  jnz     short loc_180006EB8
0x180006eae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006eb3  jmp     loc_180007127
0x180006eb8  xor     r8d, r8d; bAlertable
0x180006ebb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006ebe  mov     rcx, rbx; hHandle
0x180006ec1  call    cs:__imp_WaitForSingleObjectEx
0x180006ec7  cmp     eax, 102h
0x180006ecc  jz      short loc_180006EDE
0x180006ece  test    eax, 0FFFFFF7Fh
0x180006ed3  jnz     loc_18000715F
0x180006ed9  mov     rdi, rbx
0x180006edc  jmp     short loc_180006EE0
0x180006ede  xor     edi, edi
0x180006ee0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006ee5  mov     [rsp+280h+hObject], 0
0x180006eee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006ef3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006ef8  mov     esi, eax
0x180006efa  test    eax, eax
0x180006efc  jns     short loc_180006F7D
0x180006efe  mov     rcx, [rbp+188h]; this
0x180006f05  lea     r8, aWil; "wil"
0x180006f0c  mov     r9d, eax; char *
0x180006f0f  mov     edx, 66h ; 'f'; void *
0x180006f14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f19  mov     rcx, [rbp+188h]; this
0x180006f20  lea     r8, aWil; "wil"
0x180006f27  mov     r9d, esi; char *
0x180006f2a  mov     edx, 6Fh ; 'o'; void *
0x180006f2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f34  mov     rcx, [rbp+188h]; this
0x180006f3b  lea     r8, aWil; "wil"
0x180006f42  mov     r9d, esi; char *
0x180006f45  mov     edx, 12Eh; void *
0x180006f4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f4f  test    rdi, rdi
0x180006f52  jz      short loc_180006F65
0x180006f54  mov     rcx, rdi; hMutex
0x180006f57  call    cs:__imp_ReleaseMutex
0x180006f5d  test    eax, eax
0x180006f5f  jz      loc_180007171
0x180006f65  mov     rcx, rbx; hObject
0x180006f68  call    cs:__imp_CloseHandle
0x180006f6e  test    eax, eax
0x180006f70  jz      loc_180007183
0x180006f76  mov     eax, esi
0x180006f78  jmp     loc_180007127
0x180006f7d  mov     rax, [rsp+280h+hObject]
0x180006f82  lea     rcx, ds:0[rax*4]
0x180006f8a  test    rcx, rcx
0x180006f8d  jz      short loc_180006F9D
0x180006f8f  mov     [r15], rcx
0x180006f92  mov     eax, [rcx]
0x180006f94  inc     eax
0x180006f96  mov     [rcx], eax
0x180006f98  jmp     loc_1800070FD
0x180006f9d  mov     rdx, r14; dwBytes
0x180006fa0  mov     qword ptr [r15], 0
0x180006fa7  mov     ecx, 8; dwFlags
0x180006fac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006fb1  mov     rsi, rax
0x180006fb4  test    rax, rax
0x180006fb7  jnz     short loc_180006FDF
0x180006fb9  mov     rcx, [rbp+188h]; this
0x180006fc0  lea     r8, aWil; "wil"
0x180006fc7  mov     r14d, 8007000Eh
0x180006fcd  mov     edx, 14Bh; void *
0x180006fd2  mov     r9d, r14d; char *
0x180006fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fda  jmp     loc_180007072
0x180006fdf  xorps   xmm0, xmm0
0x180006fe2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006fe8  test    sil, 3
0x180006fec  jnz     loc_180007195
0x180006ff2  mov     r9, rsi
0x180006ff5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006ffa  shr     r9, 2; unsigned __int64
0x180006ffe  lea     rcx, [rsp+280h+hObject]; this
0x180007003  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180007008  mov     r14d, eax
0x18000700b  test    eax, eax
0x18000700d  jns     loc_1800070B9
0x180007013  mov     rcx, [rbp+188h]; this
0x18000701a  lea     r8, aWil; "wil"
0x180007021  mov     r9d, eax; char *
0x180007024  mov     edx, 14Eh; void *
0x180007029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000702e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180007033  test    rcx, rcx
0x180007036  jz      short loc_180007046
0x180007038  call    cs:__imp_CloseHandle
0x18000703e  test    eax, eax
0x180007040  jz      loc_18000719B
0x180007046  mov     rcx, [rsp+280h+hObject]; hObject
0x18000704b  test    rcx, rcx
0x18000704e  jz      short loc_18000705E
0x180007050  call    cs:__imp_CloseHandle
0x180007056  test    eax, eax
0x180007058  jz      loc_1800071AD
0x18000705e  call    cs:__imp_GetProcessHeap
0x180007064  mov     r8, rsi; lpMem
0x180007067  xor     edx, edx; dwFlags
0x180007069  mov     rcx, rax; hHeap
0x18000706c  call    cs:__imp_HeapFree
0x180007072  mov     rcx, [rbp+188h]; this
0x180007079  lea     r8, aWil; "wil"
0x180007080  mov     r9d, r14d; char *
0x180007083  mov     edx, 137h; void *
0x180007088  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000708d  test    rdi, rdi
0x180007090  jz      short loc_1800070A3
0x180007092  mov     rcx, rdi; hMutex
0x180007095  call    cs:__imp_ReleaseMutex
0x18000709b  test    eax, eax
0x18000709d  jz      loc_1800071BF
0x1800070a3  mov     rcx, rbx; hObject
0x1800070a6  call    cs:__imp_CloseHandle
0x1800070ac  test    eax, eax
0x1800070ae  jz      loc_1800071D1
0x1800070b4  mov     eax, r14d
0x1800070b7  jmp     short loc_180007127
0x1800070b9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800070be  xor     edx, edx; Val
0x1800070c0  mov     dword ptr [rsi], 1
0x1800070c6  lea     rcx, [rsi+22h]; void *
0x1800070ca  mov     [rsi+8], rbx
0x1800070ce  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800070d3  lea     r8d, [rdx+56h]; Size
0x1800070d7  call    memset_0
0x1800070dc  xor     edx, edx; Val
0x1800070de  mov     word ptr [rsi+20h], 58h ; 'X'
0x1800070e4  lea     rcx, [rsi+28h]; void *
0x1800070e8  mov     dword ptr [rsi+24h], 1
0x1800070ef  lea     r8d, [rdx+50h]; Size
0x1800070f3  call    memset_0
0x1800070f8  xor     ebx, ebx
0x1800070fa  mov     [r15], rsi
0x1800070fd  test    rdi, rdi
0x180007100  jz      short loc_180007113
0x180007102  mov     rcx, rdi; hMutex
0x180007105  call    cs:__imp_ReleaseMutex
0x18000710b  test    eax, eax
0x18000710d  jz      loc_1800071E3
0x180007113  test    rbx, rbx
0x180007116  jz      short loc_180007125
0x180007118  mov     rcx, rbx; hObject
0x18000711b  call    cs:__imp_CloseHandle
0x180007121  test    eax, eax
0x180007123  jz      short loc_18000714D
0x180007125  xor     eax, eax
0x180007127  mov     rcx, [rbp+180h+var_30]
0x18000712e  xor     rcx, rsp; StackCookie
0x180007131  call    __security_check_cookie
0x180007136  mov     rbx, [rsp+280h+arg_10]
0x18000713e  add     rsp, 260h
0x180007145  pop     r15
0x180007147  pop     r14
0x180007149  pop     rdi
0x18000714a  pop     rsi
0x18000714b  pop     rbp
0x18000714c  retn
0x18000714d  mov     rcx, [rbp+188h]; this
0x180007154  mov     edx, 0A0Bh; void *
0x180007159  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000715f  mov     rcx, [rbp+188h]; this
0x180007166  mov     edx, 0E01h; void *
0x18000716b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007171  mov     rcx, [rbp+188h]; this
0x180007178  mov     edx, 0A15h; void *
0x18000717d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007183  mov     rcx, [rbp+188h]; this
0x18000718a  mov     edx, 0A0Bh; void *
0x18000718f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007195  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000719b  mov     rcx, [rbp+188h]; this
0x1800071a2  mov     edx, 0A0Bh; void *
0x1800071a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071ad  mov     rcx, [rbp+188h]; this
0x1800071b4  mov     edx, 0A0Bh; void *
0x1800071b9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071bf  mov     rcx, [rbp+188h]; this
0x1800071c6  mov     edx, 0A15h; void *
0x1800071cb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071d1  mov     rcx, [rbp+188h]; this
0x1800071d8  mov     edx, 0A0Bh; void *
0x1800071dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800071e3  mov     rcx, [rbp+188h]; this
0x1800071ea  mov     edx, 0A15h; void *
0x1800071ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
