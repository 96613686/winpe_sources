# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023ca4`
- end: `0x180024095`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180024394`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18002317c`
- `0x180023ca4`
- `0x18002409c`
- `0x180024524`
- `0x180024f0c`
- `0x180025b78`
- `0x180026e80`
- `0x180027598`
- `0x180027dac`
- `0x180027dbc`
- `0x180028418`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180023ed7`
- `KERNEL32!GetProcessHeap` at `0x180023ed7`
- `KERNEL32!GetCurrentProcessId` at `0x180023cdd`
- `KERNEL32!GetCurrentProcessId` at `0x180023cdd`
- `KERNEL32!CreateMutexExW` at `0x180023d1b`
- `KERNEL32!CreateMutexExW` at `0x180023d1b`
- `KERNEL32!WaitForSingleObjectEx` at `0x180023d3c`
- `KERNEL32!WaitForSingleObjectEx` at `0x180023d3c`
- `KERNEL32!ReleaseMutex` at `0x180023dd2`
- `KERNEL32!ReleaseMutex` at `0x180023f0e`
- `KERNEL32!ReleaseMutex` at `0x180023faa`
- `KERNEL32!ReleaseMutex` at `0x180023dd2`
- `KERNEL32!ReleaseMutex` at `0x180023f0e`
- `KERNEL32!ReleaseMutex` at `0x180023faa`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180023f77`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180023f77`
- `KERNEL32!HeapFree` at `0x180023ee5`
- `KERNEL32!HeapFree` at `0x180023ee5`
- `KERNEL32!CloseHandle` at `0x180023de3`
- `KERNEL32!CloseHandle` at `0x180023eb1`
- `KERNEL32!CloseHandle` at `0x180023ec9`
- `KERNEL32!CloseHandle` at `0x180023f1f`
- `KERNEL32!CloseHandle` at `0x180023fc0`
- `KERNEL32!CloseHandle` at `0x180023de3`
- `KERNEL32!CloseHandle` at `0x180023eb1`
- `KERNEL32!CloseHandle` at `0x180023ec9`
- `KERNEL32!CloseHandle` at `0x180023f1f`
- `KERNEL32!CloseHandle` at `0x180023fc0`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(pszDest, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, pszDest, 0, 0x1F0001u);
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
                    pszDest,
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
          pszDest,
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
0x180023ca4  mov     [rsp-8+arg_10], rbx
0x180023ca9  push    rbp
0x180023caa  push    rsi
0x180023cab  push    rdi
0x180023cac  push    r14
0x180023cae  push    r15
0x180023cb0  lea     rbp, [rsp-160h]
0x180023cb8  sub     rsp, 260h
0x180023cbf  mov     rax, cs:__security_cookie
0x180023cc6  xor     rax, rsp
0x180023cc9  mov     [rbp+180h+var_30], rax
0x180023cd0  mov     r15, rdx
0x180023cd3  mov     qword ptr [rdx], 0
0x180023cda  mov     rbx, rcx
0x180023cdd  call    cs:__imp_GetCurrentProcessId
0x180023ce3  mov     r14d, 130h
0x180023ce9  mov     [rsp+280h+var_258], rbx
0x180023cee  mov     r9d, eax
0x180023cf1  mov     [rsp+280h+var_260], r14d; int
0x180023cf6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023cfd  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180023d02  lea     edx, [r14-2Ch]; cchDest
0x180023d06  call    StringCchPrintfW
0x180023d0b  mov     r9d, 1F0001h; dwDesiredAccess
0x180023d11  lea     rdx, [rsp+280h+pszDest]; lpName
0x180023d16  xor     r8d, r8d; dwFlags
0x180023d19  xor     ecx, ecx; lpMutexAttributes
0x180023d1b  call    cs:__imp_CreateMutexExW
0x180023d21  mov     rbx, rax
0x180023d24  test    rax, rax
0x180023d27  jnz     short loc_180023D33
0x180023d29  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023d2e  jmp     loc_180023FCC
0x180023d33  xor     r8d, r8d; bAlertable
0x180023d36  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180023d39  mov     rcx, rbx; hHandle
0x180023d3c  call    cs:__imp_WaitForSingleObjectEx
0x180023d42  cmp     eax, 102h
0x180023d47  jz      short loc_180023D59
0x180023d49  test    eax, 0FFFFFF7Fh
0x180023d4e  jnz     loc_180024016
0x180023d54  mov     rdi, rbx
0x180023d57  jmp     short loc_180023D5B
0x180023d59  xor     edi, edi
0x180023d5b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180023d60  mov     [rsp+280h+hObject], 0
0x180023d69  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180023d6e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180023d73  mov     esi, eax
0x180023d75  test    eax, eax
0x180023d77  jns     short loc_180023DF8
0x180023d79  mov     rcx, [rbp+188h]; this
0x180023d80  lea     r8, aWil; "wil"
0x180023d87  mov     r9d, eax; char *
0x180023d8a  mov     edx, 66h ; 'f'; void *
0x180023d8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023d94  mov     rcx, [rbp+188h]; this
0x180023d9b  lea     r8, aWil; "wil"
0x180023da2  mov     r9d, esi; char *
0x180023da5  mov     edx, 6Fh ; 'o'; void *
0x180023daa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023daf  mov     rcx, [rbp+188h]; this
0x180023db6  lea     r8, aWil; "wil"
0x180023dbd  mov     r9d, esi; char *
0x180023dc0  mov     edx, 12Eh; void *
0x180023dc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023dca  test    rdi, rdi
0x180023dcd  jz      short loc_180023DE0
0x180023dcf  mov     rcx, rdi; hMutex
0x180023dd2  call    cs:__imp_ReleaseMutex
0x180023dd8  test    eax, eax
0x180023dda  jz      loc_180024023
0x180023de0  mov     rcx, rbx; hObject
0x180023de3  call    cs:__imp_CloseHandle
0x180023de9  test    eax, eax
0x180023deb  jz      loc_180024035
0x180023df1  mov     eax, esi
0x180023df3  jmp     loc_180023FCC
0x180023df8  mov     rax, [rsp+280h+hObject]
0x180023dfd  lea     rcx, ds:0[rax*4]
0x180023e05  test    rcx, rcx
0x180023e08  jz      short loc_180023E18
0x180023e0a  mov     [r15], rcx
0x180023e0d  mov     eax, [rcx]
0x180023e0f  inc     eax
0x180023e11  mov     [rcx], eax
0x180023e13  jmp     loc_180023FA2
0x180023e18  mov     rdx, r14; dwBytes
0x180023e1b  mov     qword ptr [r15], 0
0x180023e22  mov     ecx, 8; dwFlags
0x180023e27  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180023e2c  mov     r14, rax
0x180023e2f  test    rax, rax
0x180023e32  jnz     short loc_180023E59
0x180023e34  mov     rcx, [rbp+188h]; this
0x180023e3b  lea     r8, aWil; "wil"
0x180023e42  mov     esi, 8007000Eh
0x180023e47  mov     edx, 14Bh; void *
0x180023e4c  mov     r9d, esi; char *
0x180023e4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e54  jmp     loc_180023EEB
0x180023e59  xorps   xmm0, xmm0
0x180023e5c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180023e62  test    r14b, 3
0x180023e66  jnz     loc_180024047
0x180023e6c  mov     r9, r14
0x180023e6f  lea     rdx, [rsp+280h+pszDest]; unsigned __int16 *
0x180023e74  shr     r9, 2; unsigned __int64
0x180023e78  lea     rcx, [rsp+280h+hObject]; this
0x180023e7d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180023e82  mov     esi, eax
0x180023e84  test    eax, eax
0x180023e86  jns     loc_180023F32
0x180023e8c  mov     rcx, [rbp+188h]; this
0x180023e93  lea     r8, aWil; "wil"
0x180023e9a  mov     r9d, eax; char *
0x180023e9d  mov     edx, 14Eh; void *
0x180023ea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023ea7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180023eac  test    rcx, rcx
0x180023eaf  jz      short loc_180023EBF
0x180023eb1  call    cs:__imp_CloseHandle
0x180023eb7  test    eax, eax
0x180023eb9  jz      loc_18002404D
0x180023ebf  mov     rcx, [rsp+280h+hObject]; hObject
0x180023ec4  test    rcx, rcx
0x180023ec7  jz      short loc_180023ED7
0x180023ec9  call    cs:__imp_CloseHandle
0x180023ecf  test    eax, eax
0x180023ed1  jz      loc_18002405F
0x180023ed7  call    cs:__imp_GetProcessHeap
0x180023edd  mov     r8, r14; lpMem
0x180023ee0  xor     edx, edx; dwFlags
0x180023ee2  mov     rcx, rax; hHeap
0x180023ee5  call    cs:__imp_HeapFree
0x180023eeb  mov     rcx, [rbp+188h]; this
0x180023ef2  lea     r8, aWil; "wil"
0x180023ef9  mov     r9d, esi; char *
0x180023efc  mov     edx, 137h; void *
0x180023f01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f06  test    rdi, rdi
0x180023f09  jz      short loc_180023F1C
0x180023f0b  mov     rcx, rdi; hMutex
0x180023f0e  call    cs:__imp_ReleaseMutex
0x180023f14  test    eax, eax
0x180023f16  jz      loc_180024071
0x180023f1c  mov     rcx, rbx; hObject
0x180023f1f  call    cs:__imp_CloseHandle
0x180023f25  test    eax, eax
0x180023f27  jz      loc_180024004
0x180023f2d  jmp     loc_180023DF1
0x180023f32  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180023f37  lea     rcx, [r14+28h]; void *
0x180023f3b  mov     dword ptr [r14], 1
0x180023f42  xor     edx, edx; Val
0x180023f44  mov     [r14+8], rbx
0x180023f48  mov     r8d, 108h; Size
0x180023f4e  movdqu  xmmword ptr [r14+10h], xmm0
0x180023f54  call    memset_0
0x180023f59  xor     eax, eax
0x180023f5b  lea     rcx, [r14+28h]; this
0x180023f5f  mov     [r14+20h], rax
0x180023f63  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180023f68  lea     rbx, [r14+0E8h]
0x180023f6f  xor     r8d, r8d; Flags
0x180023f72  mov     rcx, rbx; lpCriticalSection
0x180023f75  xor     edx, edx; dwSpinCount
0x180023f77  call    cs:__imp_InitializeCriticalSectionEx
0x180023f7d  mov     qword ptr [rbx+28h], 0
0x180023f85  mov     qword ptr [rbx+30h], 0
0x180023f8d  mov     qword ptr [rbx+38h], 0
0x180023f95  mov     qword ptr [rbx+40h], 0
0x180023f9d  xor     ebx, ebx
0x180023f9f  mov     [r15], r14
0x180023fa2  test    rdi, rdi
0x180023fa5  jz      short loc_180023FB8
0x180023fa7  mov     rcx, rdi; hMutex
0x180023faa  call    cs:__imp_ReleaseMutex
0x180023fb0  test    eax, eax
0x180023fb2  jz      loc_180024083
0x180023fb8  test    rbx, rbx
0x180023fbb  jz      short loc_180023FCA
0x180023fbd  mov     rcx, rbx; hObject
0x180023fc0  call    cs:__imp_CloseHandle
0x180023fc6  test    eax, eax
0x180023fc8  jz      short loc_180023FF2
0x180023fca  xor     eax, eax
0x180023fcc  mov     rcx, [rbp+180h+var_30]
0x180023fd3  xor     rcx, rsp; StackCookie
0x180023fd6  call    __security_check_cookie
0x180023fdb  mov     rbx, [rsp+280h+arg_10]
0x180023fe3  add     rsp, 260h
0x180023fea  pop     r15
0x180023fec  pop     r14
0x180023fee  pop     rdi
0x180023fef  pop     rsi
0x180023ff0  pop     rbp
0x180023ff1  retn
0x180023ff2  mov     rcx, [rbp+188h]; this
0x180023ff9  mov     edx, 0A0Bh; void *
0x180023ffe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024004  mov     rcx, [rbp+188h]; this
0x18002400b  mov     edx, 0A0Bh; void *
0x180024010  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024016  mov     rcx, [rbp+188h]; this
0x18002401d  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180024023  mov     rcx, [rbp+188h]; this
0x18002402a  mov     edx, 0A15h; void *
0x18002402f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024035  mov     rcx, [rbp+188h]; this
0x18002403c  mov     edx, 0A0Bh; void *
0x180024041  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024047  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002404d  mov     rcx, [rbp+188h]; this
0x180024054  mov     edx, 0A0Bh; void *
0x180024059  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002405f  mov     rcx, [rbp+188h]; this
0x180024066  mov     edx, 0A0Bh; void *
0x18002406b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024071  mov     rcx, [rbp+188h]; this
0x180024078  mov     edx, 0A15h; void *
0x18002407d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180024083  mov     rcx, [rbp+188h]; this
0x18002408a  mov     edx, 0A15h; void *
0x18002408f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
