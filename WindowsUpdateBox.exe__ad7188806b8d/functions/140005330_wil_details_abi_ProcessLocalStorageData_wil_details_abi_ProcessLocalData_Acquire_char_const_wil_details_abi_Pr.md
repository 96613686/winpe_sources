# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140005330`
- end: `0x1400056ec`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `956`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14001057c`

## callees

- `0x140002116`
- `0x140004918`
- `0x140005330`
- `0x140009c54`
- `0x14000d15c`
- `0x14000f8a4`
- `0x14001b1b8`
- `0x14001d240`
- `0x14001f7a0`
- `0x14001ffc0`
- `0x140020ff8`
- `0x1400213a8`
- `0x140080d70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000548b`
- `KERNEL32!CloseHandle` at `0x14000559a`
- `KERNEL32!CloseHandle` at `0x14000563a`
- `KERNEL32!CloseHandle` at `0x14000548b`
- `KERNEL32!CloseHandle` at `0x14000559a`
- `KERNEL32!CloseHandle` at `0x14000563a`
- `KERNEL32!CreateMutexExW` at `0x1400053b7`
- `KERNEL32!CreateMutexExW` at `0x1400053b7`
- `KERNEL32!GetCurrentProcessId` at `0x140005369`
- `KERNEL32!GetCurrentProcessId` at `0x140005369`
- `KERNEL32!HeapFree` at `0x140005556`
- `KERNEL32!HeapFree` at `0x140005556`
- `KERNEL32!GetProcessHeap` at `0x140005542`
- `KERNEL32!GetProcessHeap` at `0x140005542`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400053ed`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400053ed`
- `KERNEL32!ReleaseMutex` at `0x140005474`
- `KERNEL32!ReleaseMutex` at `0x14000557e`
- `KERNEL32!ReleaseMutex` at `0x14000561e`
- `KERNEL32!ReleaseMutex` at `0x140005474`
- `KERNEL32!ReleaseMutex` at `0x14000557e`
- `KERNEL32!ReleaseMutex` at `0x14000561e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rsi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  _QWORD *v23; // rax
  unsigned int v24; // r8d
  _QWORD *v25; // rdi
  unsigned int v26; // r14d
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE v35; // rax
  HANDLE v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle[0] = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    hHandle,
    Mutex);
  v6 = hHandle[0];
  if ( !hHandle[0] )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(hHandle[0], 0xFFFFFFFF, 0);
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
  hHandle[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    (bool)v9,
                    (unsigned __int64 *)hHandle,
                    (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x64, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6D, v16, (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12B, v17, (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9EC, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hHandle[0]);
  if ( 4 * (__int64)hHandle[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_24;
  }
  *a2 = 0;
  v23 = wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v25 = v23;
  if ( v23 )
  {
    *(_OWORD *)hHandle = 0;
    v28 = wil::details_abi::SemaphoreValue::CreateFromPointer((wil::details_abi::SemaphoreValue *)hHandle, Name, v23);
    v26 = v28;
    if ( v28 >= 0 )
    {
      v35 = hHandle[0];
      v25[1] = v6;
      v6 = 0;
      v25[2] = v35;
      v36 = hHandle[1];
      *(_DWORD *)v25 = 1;
      hHandle[0] = 0;
      v25[3] = v36;
      hHandle[1] = 0;
      memset_0((char *)v25 + 34, 0, 0x56u);
      *((_WORD *)v25 + 16) = 88;
      *((_DWORD *)v25 + 9) = 1;
      memset_0(v25 + 5, 0, 0x50u);
      *a2 = v25;
      wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
LABEL_24:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9EC, v37, v38);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v39, v40);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v29, (const char *)(unsigned int)v28, 120);
    wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)hHandle);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
  }
  else
  {
    v26 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x148, v24, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x134, v27, (const char *)v26, v43);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9EC, v31, v32);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9E2, v33, v34);
  return v26;
}

```

## disassembly

```asm
0x140005330  mov     [rsp-8+arg_10], rbx
0x140005335  push    rbp
0x140005336  push    rsi
0x140005337  push    rdi
0x140005338  push    r14
0x14000533a  push    r15
0x14000533c  lea     rbp, [rsp-160h]
0x140005344  sub     rsp, 260h
0x14000534b  mov     rax, cs:__security_cookie
0x140005352  xor     rax, rsp
0x140005355  mov     [rbp+180h+var_30], rax
0x14000535c  mov     r15, rdx
0x14000535f  mov     qword ptr [rdx], 0
0x140005366  mov     rbx, rcx
0x140005369  call    cs:__imp_GetCurrentProcessId
0x140005370  nop     dword ptr [rax+rax+00h]
0x140005375  mov     r14d, 78h ; 'x'
0x14000537b  mov     [rsp+280h+var_258], rbx
0x140005380  mov     r9d, eax
0x140005383  mov     [rsp+280h+var_260], r14d; int
0x140005388  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000538f  mov     edx, 104h; unsigned __int64
0x140005394  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005399  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000539e  mov     r9d, 1F0001h; dwDesiredAccess
0x1400053a4  mov     [rsp+280h+hHandle], 0
0x1400053ad  xor     r8d, r8d; dwFlags
0x1400053b0  lea     rdx, [rsp+280h+Name]; lpName
0x1400053b5  xor     ecx, ecx; lpMutexAttributes
0x1400053b7  call    cs:__imp_CreateMutexExW
0x1400053be  nop     dword ptr [rax+rax+00h]
0x1400053c3  mov     rdx, rax
0x1400053c6  lea     rcx, [rsp+280h+hHandle]
0x1400053cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400053d0  mov     rbx, [rsp+280h+hHandle]
0x1400053d5  test    rbx, rbx
0x1400053d8  jnz     short loc_1400053E4
0x1400053da  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400053df  jmp     loc_14000564C
0x1400053e4  xor     r8d, r8d; bAlertable
0x1400053e7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400053ea  mov     rcx, rbx; hHandle
0x1400053ed  call    cs:__imp_WaitForSingleObjectEx
0x1400053f4  nop     dword ptr [rax+rax+00h]
0x1400053f9  cmp     eax, 102h
0x1400053fe  jz      short loc_140005410
0x140005400  test    eax, 0FFFFFF7Fh
0x140005405  jnz     loc_140005685
0x14000540b  mov     rsi, rbx
0x14000540e  jmp     short loc_140005412
0x140005410  xor     esi, esi
0x140005412  lea     r8, [rsp+280h+hHandle]; unsigned __int64 *
0x140005417  mov     [rsp+280h+hHandle], 0
0x140005420  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005425  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000542a  mov     edi, eax
0x14000542c  test    eax, eax
0x14000542e  jns     short loc_1400054A6
0x140005430  mov     rcx, [rbp+188h]; this
0x140005437  mov     r9d, eax; char *
0x14000543a  mov     edx, 64h ; 'd'; void *
0x14000543f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005444  mov     rcx, [rbp+188h]; this
0x14000544b  mov     r9d, edi; char *
0x14000544e  mov     edx, 6Dh ; 'm'; void *
0x140005453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005458  mov     rcx, [rbp+188h]; this
0x14000545f  mov     r9d, edi; char *
0x140005462  mov     edx, 12Bh; void *
0x140005467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000546c  test    rsi, rsi
0x14000546f  jz      short loc_140005488
0x140005471  mov     rcx, rsi; hMutex
0x140005474  call    cs:__imp_ReleaseMutex
0x14000547b  nop     dword ptr [rax+rax+00h]
0x140005480  test    eax, eax
0x140005482  jz      loc_140005692
0x140005488  mov     rcx, rbx; hObject
0x14000548b  call    cs:__imp_CloseHandle
0x140005492  nop     dword ptr [rax+rax+00h]
0x140005497  test    eax, eax
0x140005499  jz      loc_1400056A4
0x14000549f  mov     eax, edi
0x1400054a1  jmp     loc_14000564C
0x1400054a6  mov     rax, [rsp+280h+hHandle]
0x1400054ab  lea     rcx, ds:0[rax*4]
0x1400054b3  test    rcx, rcx
0x1400054b6  jz      short loc_1400054C6
0x1400054b8  mov     [r15], rcx
0x1400054bb  mov     eax, [rcx]
0x1400054bd  inc     eax
0x1400054bf  mov     [rcx], eax
0x1400054c1  jmp     loc_140005616
0x1400054c6  mov     rdx, r14; dwBytes
0x1400054c9  mov     qword ptr [r15], 0
0x1400054d0  mov     ecx, 8; dwFlags
0x1400054d5  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400054da  mov     rdi, rax
0x1400054dd  test    rax, rax
0x1400054e0  jnz     short loc_1400054FE
0x1400054e2  mov     rcx, [rbp+188h]; this
0x1400054e9  mov     r14d, 8007000Eh
0x1400054ef  mov     r9d, r14d; char *
0x1400054f2  mov     edx, 148h; void *
0x1400054f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400054fc  jmp     short loc_140005562
0x1400054fe  xorps   xmm0, xmm0
0x140005501  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140005506  mov     r8, rdi; void *
0x140005509  lea     rcx, [rsp+280h+hHandle]; this
0x14000550e  movdqu  xmmword ptr [rsp+280h+hHandle], xmm0
0x140005514  call    ?CreateFromPointer@SemaphoreValue@details_abi@wil@@QEAAJPEBGPEAX@Z; wil::details_abi::SemaphoreValue::CreateFromPointer(ushort const *,void *)
0x140005519  mov     r14d, eax
0x14000551c  test    eax, eax
0x14000551e  jns     loc_1400055B6
0x140005524  mov     rcx, [rbp+188h]; this
0x14000552b  mov     r9d, eax; char *
0x14000552e  mov     edx, 14Bh; void *
0x140005533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005538  lea     rcx, [rsp+280h+hHandle]; this
0x14000553d  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140005542  call    cs:__imp_GetProcessHeap
0x140005549  nop     dword ptr [rax+rax+00h]
0x14000554e  mov     r8, rdi; lpMem
0x140005551  xor     edx, edx; dwFlags
0x140005553  mov     rcx, rax; hHeap
0x140005556  call    cs:__imp_HeapFree
0x14000555d  nop     dword ptr [rax+rax+00h]
0x140005562  mov     rcx, [rbp+188h]; this
0x140005569  mov     r9d, r14d; char *
0x14000556c  mov     edx, 134h; void *
0x140005571  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005576  test    rsi, rsi
0x140005579  jz      short loc_140005592
0x14000557b  mov     rcx, rsi; hMutex
0x14000557e  call    cs:__imp_ReleaseMutex
0x140005585  nop     dword ptr [rax+rax+00h]
0x14000558a  test    eax, eax
0x14000558c  jz      loc_1400056B6
0x140005592  test    rbx, rbx
0x140005595  jz      short loc_1400055AE
0x140005597  mov     rcx, rbx; hObject
0x14000559a  call    cs:__imp_CloseHandle
0x1400055a1  nop     dword ptr [rax+rax+00h]
0x1400055a6  test    eax, eax
0x1400055a8  jz      loc_1400056C8
0x1400055ae  mov     eax, r14d
0x1400055b1  jmp     loc_14000564C
0x1400055b6  mov     rax, [rsp+280h+hHandle]
0x1400055bb  lea     rcx, [rdi+22h]; void *
0x1400055bf  mov     [rdi+8], rbx
0x1400055c3  xor     edx, edx; Val
0x1400055c5  xor     ebx, ebx
0x1400055c7  mov     [rdi+10h], rax
0x1400055cb  mov     rax, [rsp+280h+hHandle+8]
0x1400055d0  mov     dword ptr [rdi], 1
0x1400055d6  mov     [rsp+280h+hHandle], rbx
0x1400055db  lea     r8d, [rbx+56h]; Size
0x1400055df  mov     [rdi+18h], rax
0x1400055e3  mov     [rsp+280h+hHandle+8], rbx
0x1400055e8  call    memset_0
0x1400055ed  mov     word ptr [rdi+20h], 58h ; 'X'
0x1400055f3  lea     rcx, [rdi+28h]; void *
0x1400055f7  xor     edx, edx; Val
0x1400055f9  mov     dword ptr [rdi+24h], 1
0x140005600  lea     r8d, [rbx+50h]; Size
0x140005604  call    memset_0
0x140005609  lea     rcx, [rsp+280h+hHandle]; this
0x14000560e  mov     [r15], rdi
0x140005611  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x140005616  test    rsi, rsi
0x140005619  jz      short loc_140005632
0x14000561b  mov     rcx, rsi; hMutex
0x14000561e  call    cs:__imp_ReleaseMutex
0x140005625  nop     dword ptr [rax+rax+00h]
0x14000562a  test    eax, eax
0x14000562c  jz      loc_1400056DA
0x140005632  test    rbx, rbx
0x140005635  jz      short loc_14000564A
0x140005637  mov     rcx, rbx; hObject
0x14000563a  call    cs:__imp_CloseHandle
0x140005641  nop     dword ptr [rax+rax+00h]
0x140005646  test    eax, eax
0x140005648  jz      short loc_140005673
0x14000564a  xor     eax, eax
0x14000564c  mov     rcx, [rbp+180h+var_30]
0x140005653  xor     rcx, rsp; StackCookie
0x140005656  call    __security_check_cookie
0x14000565b  mov     rbx, [rsp+280h+arg_10]
0x140005663  add     rsp, 260h
0x14000566a  pop     r15
0x14000566c  pop     r14
0x14000566e  pop     rdi
0x14000566f  pop     rsi
0x140005670  pop     rbp
0x140005671  retn
0x140005673  mov     rcx, [rbp+188h]; this
0x14000567a  mov     edx, 9E2h; void *
0x14000567f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005685  mov     rcx, [rbp+188h]; this
0x14000568c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140005692  mov     rcx, [rbp+188h]; this
0x140005699  mov     edx, 9ECh; void *
0x14000569e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400056a4  mov     rcx, [rbp+188h]; this
0x1400056ab  mov     edx, 9E2h; void *
0x1400056b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400056b6  mov     rcx, [rbp+188h]; this
0x1400056bd  mov     edx, 9ECh; void *
0x1400056c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400056c8  mov     rcx, [rbp+188h]; this
0x1400056cf  mov     edx, 9E2h; void *
0x1400056d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400056da  mov     rcx, [rbp+188h]; this
0x1400056e1  mov     edx, 9ECh; void *
0x1400056e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
