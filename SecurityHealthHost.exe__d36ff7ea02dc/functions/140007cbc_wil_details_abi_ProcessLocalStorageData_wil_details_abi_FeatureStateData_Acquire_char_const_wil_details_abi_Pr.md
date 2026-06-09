# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140007cbc`
- end: `0x1400080ad`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400083a4`

## callees

- `0x1400015f0`
- `0x1400022ec`
- `0x14000674c`
- `0x1400068ec`
- `0x140007004`
- `0x140007cbc`
- `0x1400080b4`
- `0x140008534`
- `0x140008b6c`
- `0x140009228`
- `0x14000afc8`
- `0x14000b34c`
- `0x14000ba50`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140007dfb`
- `KERNEL32!CloseHandle` at `0x140007ec9`
- `KERNEL32!CloseHandle` at `0x140007ee1`
- `KERNEL32!CloseHandle` at `0x140007f37`
- `KERNEL32!CloseHandle` at `0x140007fd8`
- `KERNEL32!CloseHandle` at `0x140007dfb`
- `KERNEL32!CloseHandle` at `0x140007ec9`
- `KERNEL32!CloseHandle` at `0x140007ee1`
- `KERNEL32!CloseHandle` at `0x140007f37`
- `KERNEL32!CloseHandle` at `0x140007fd8`
- `KERNEL32!WaitForSingleObjectEx` at `0x140007d54`
- `KERNEL32!WaitForSingleObjectEx` at `0x140007d54`
- `KERNEL32!GetCurrentProcessId` at `0x140007cf5`
- `KERNEL32!GetCurrentProcessId` at `0x140007cf5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140007f8f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140007f8f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007d33`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007d33`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007dea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007f26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007fc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007dea`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007f26`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007fc2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007eef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007eef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007efd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007efd`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  __int128 v35; // xmm0
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
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
0x140007cbc  mov     [rsp-8+arg_10], rbx
0x140007cc1  push    rbp
0x140007cc2  push    rsi
0x140007cc3  push    rdi
0x140007cc4  push    r14
0x140007cc6  push    r15
0x140007cc8  lea     rbp, [rsp-160h]
0x140007cd0  sub     rsp, 260h
0x140007cd7  mov     rax, cs:__security_cookie
0x140007cde  xor     rax, rsp
0x140007ce1  mov     [rbp+180h+var_30], rax
0x140007ce8  mov     r15, rdx
0x140007ceb  mov     qword ptr [rdx], 0
0x140007cf2  mov     rbx, rcx
0x140007cf5  call    cs:__imp_GetCurrentProcessId
0x140007cfb  mov     r14d, 130h
0x140007d01  mov     [rsp+280h+var_258], rbx
0x140007d06  mov     r9d, eax
0x140007d09  mov     [rsp+280h+var_260], r14d; int
0x140007d0e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007d15  lea     rcx, [rsp+280h+Name]; Buffer
0x140007d1a  lea     edx, [r14-2Ch]; unsigned __int64
0x140007d1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007d23  mov     r9d, 1F0001h; dwDesiredAccess
0x140007d29  lea     rdx, [rsp+280h+Name]; lpName
0x140007d2e  xor     r8d, r8d; dwFlags
0x140007d31  xor     ecx, ecx; lpMutexAttributes
0x140007d33  call    cs:__imp_CreateMutexExW
0x140007d39  mov     rbx, rax
0x140007d3c  test    rax, rax
0x140007d3f  jnz     short loc_140007D4B
0x140007d41  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007d46  jmp     loc_140007FE4
0x140007d4b  xor     r8d, r8d; bAlertable
0x140007d4e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007d51  mov     rcx, rbx; hHandle
0x140007d54  call    cs:__imp_WaitForSingleObjectEx
0x140007d5a  cmp     eax, 102h
0x140007d5f  jz      short loc_140007D71
0x140007d61  test    eax, 0FFFFFF7Fh
0x140007d66  jnz     loc_14000802E
0x140007d6c  mov     rdi, rbx
0x140007d6f  jmp     short loc_140007D73
0x140007d71  xor     edi, edi
0x140007d73  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140007d78  mov     [rsp+280h+hObject], 0
0x140007d81  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140007d86  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140007d8b  mov     esi, eax
0x140007d8d  test    eax, eax
0x140007d8f  jns     short loc_140007E10
0x140007d91  mov     rcx, [rbp+188h]; this
0x140007d98  lea     r8, aWil; "wil"
0x140007d9f  mov     r9d, eax; char *
0x140007da2  mov     edx, 66h ; 'f'; void *
0x140007da7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007dac  mov     rcx, [rbp+188h]; this
0x140007db3  lea     r8, aWil; "wil"
0x140007dba  mov     r9d, esi; char *
0x140007dbd  mov     edx, 6Fh ; 'o'; void *
0x140007dc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007dc7  mov     rcx, [rbp+188h]; this
0x140007dce  lea     r8, aWil; "wil"
0x140007dd5  mov     r9d, esi; char *
0x140007dd8  mov     edx, 12Eh; void *
0x140007ddd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007de2  test    rdi, rdi
0x140007de5  jz      short loc_140007DF8
0x140007de7  mov     rcx, rdi; hMutex
0x140007dea  call    cs:__imp_ReleaseMutex
0x140007df0  test    eax, eax
0x140007df2  jz      loc_14000803B
0x140007df8  mov     rcx, rbx; hObject
0x140007dfb  call    cs:__imp_CloseHandle
0x140007e01  test    eax, eax
0x140007e03  jz      loc_14000804D
0x140007e09  mov     eax, esi
0x140007e0b  jmp     loc_140007FE4
0x140007e10  mov     rax, [rsp+280h+hObject]
0x140007e15  lea     rcx, ds:0[rax*4]
0x140007e1d  test    rcx, rcx
0x140007e20  jz      short loc_140007E30
0x140007e22  mov     [r15], rcx
0x140007e25  mov     eax, [rcx]
0x140007e27  inc     eax
0x140007e29  mov     [rcx], eax
0x140007e2b  jmp     loc_140007FBA
0x140007e30  mov     rdx, r14; dwBytes
0x140007e33  mov     qword ptr [r15], 0
0x140007e3a  mov     ecx, 8; dwFlags
0x140007e3f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140007e44  mov     r14, rax
0x140007e47  test    rax, rax
0x140007e4a  jnz     short loc_140007E71
0x140007e4c  mov     rcx, [rbp+188h]; this
0x140007e53  lea     r8, aWil; "wil"
0x140007e5a  mov     esi, 8007000Eh
0x140007e5f  mov     edx, 14Bh; void *
0x140007e64  mov     r9d, esi; char *
0x140007e67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007e6c  jmp     loc_140007F03
0x140007e71  xorps   xmm0, xmm0
0x140007e74  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140007e7a  test    r14b, 3
0x140007e7e  jnz     loc_14000805F
0x140007e84  mov     r9, r14
0x140007e87  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140007e8c  shr     r9, 2; unsigned __int64
0x140007e90  lea     rcx, [rsp+280h+hObject]; this
0x140007e95  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140007e9a  mov     esi, eax
0x140007e9c  test    eax, eax
0x140007e9e  jns     loc_140007F4A
0x140007ea4  mov     rcx, [rbp+188h]; this
0x140007eab  lea     r8, aWil; "wil"
0x140007eb2  mov     r9d, eax; char *
0x140007eb5  mov     edx, 14Eh; void *
0x140007eba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007ebf  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140007ec4  test    rcx, rcx
0x140007ec7  jz      short loc_140007ED7
0x140007ec9  call    cs:__imp_CloseHandle
0x140007ecf  test    eax, eax
0x140007ed1  jz      loc_140008065
0x140007ed7  mov     rcx, [rsp+280h+hObject]; hObject
0x140007edc  test    rcx, rcx
0x140007edf  jz      short loc_140007EEF
0x140007ee1  call    cs:__imp_CloseHandle
0x140007ee7  test    eax, eax
0x140007ee9  jz      loc_140008077
0x140007eef  call    cs:__imp_GetProcessHeap
0x140007ef5  mov     r8, r14; lpMem
0x140007ef8  xor     edx, edx; dwFlags
0x140007efa  mov     rcx, rax; hHeap
0x140007efd  call    cs:__imp_HeapFree
0x140007f03  mov     rcx, [rbp+188h]; this
0x140007f0a  lea     r8, aWil; "wil"
0x140007f11  mov     r9d, esi; char *
0x140007f14  mov     edx, 137h; void *
0x140007f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007f1e  test    rdi, rdi
0x140007f21  jz      short loc_140007F34
0x140007f23  mov     rcx, rdi; hMutex
0x140007f26  call    cs:__imp_ReleaseMutex
0x140007f2c  test    eax, eax
0x140007f2e  jz      loc_140008089
0x140007f34  mov     rcx, rbx; hObject
0x140007f37  call    cs:__imp_CloseHandle
0x140007f3d  test    eax, eax
0x140007f3f  jz      loc_14000801C
0x140007f45  jmp     loc_140007E09
0x140007f4a  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140007f4f  lea     rcx, [r14+28h]; void *
0x140007f53  mov     dword ptr [r14], 1
0x140007f5a  xor     edx, edx; Val
0x140007f5c  mov     [r14+8], rbx
0x140007f60  mov     r8d, 108h; Size
0x140007f66  movdqu  xmmword ptr [r14+10h], xmm0
0x140007f6c  call    memset_0
0x140007f71  xor     eax, eax
0x140007f73  lea     rcx, [r14+28h]; this
0x140007f77  mov     [r14+20h], rax
0x140007f7b  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140007f80  lea     rbx, [r14+0E8h]
0x140007f87  xor     r8d, r8d; Flags
0x140007f8a  mov     rcx, rbx; lpCriticalSection
0x140007f8d  xor     edx, edx; dwSpinCount
0x140007f8f  call    cs:__imp_InitializeCriticalSectionEx
0x140007f95  mov     qword ptr [rbx+28h], 0
0x140007f9d  mov     qword ptr [rbx+30h], 0
0x140007fa5  mov     qword ptr [rbx+38h], 0
0x140007fad  mov     qword ptr [rbx+40h], 0
0x140007fb5  xor     ebx, ebx
0x140007fb7  mov     [r15], r14
0x140007fba  test    rdi, rdi
0x140007fbd  jz      short loc_140007FD0
0x140007fbf  mov     rcx, rdi; hMutex
0x140007fc2  call    cs:__imp_ReleaseMutex
0x140007fc8  test    eax, eax
0x140007fca  jz      loc_14000809B
0x140007fd0  test    rbx, rbx
0x140007fd3  jz      short loc_140007FE2
0x140007fd5  mov     rcx, rbx; hObject
0x140007fd8  call    cs:__imp_CloseHandle
0x140007fde  test    eax, eax
0x140007fe0  jz      short loc_14000800A
0x140007fe2  xor     eax, eax
0x140007fe4  mov     rcx, [rbp+180h+var_30]
0x140007feb  xor     rcx, rsp; StackCookie
0x140007fee  call    __security_check_cookie
0x140007ff3  mov     rbx, [rsp+280h+arg_10]
0x140007ffb  add     rsp, 260h
0x140008002  pop     r15
0x140008004  pop     r14
0x140008006  pop     rdi
0x140008007  pop     rsi
0x140008008  pop     rbp
0x140008009  retn
0x14000800a  mov     rcx, [rbp+188h]; this
0x140008011  mov     edx, 0A0Bh; void *
0x140008016  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000801c  mov     rcx, [rbp+188h]; this
0x140008023  mov     edx, 0A0Bh; void *
0x140008028  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000802e  mov     rcx, [rbp+188h]; this
0x140008035  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000803b  mov     rcx, [rbp+188h]; this
0x140008042  mov     edx, 0A15h; void *
0x140008047  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000804d  mov     rcx, [rbp+188h]; this
0x140008054  mov     edx, 0A0Bh; void *
0x140008059  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000805f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008065  mov     rcx, [rbp+188h]; this
0x14000806c  mov     edx, 0A0Bh; void *
0x140008071  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008077  mov     rcx, [rbp+188h]; this
0x14000807e  mov     edx, 0A0Bh; void *
0x140008083  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008089  mov     rcx, [rbp+188h]; this
0x140008090  mov     edx, 0A15h; void *
0x140008095  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000809b  mov     rcx, [rbp+188h]; this
0x1400080a2  mov     edx, 0A15h; void *
0x1400080a7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
