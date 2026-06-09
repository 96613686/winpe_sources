# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800064ac`
- end: `0x180006873`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800077c8`

## callees

- `0x1800055ec`
- `0x1800064ac`
- `0x180007134`
- `0x180007a1c`
- `0x180009d44`
- `0x18000c118`
- `0x18000df84`
- `0x1800105f8`
- `0x180010af4`
- `0x18001138c`
- `0x18001139c`
- `0x1800142d2`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800064e5`
- `KERNEL32!GetCurrentProcessId` at `0x1800064e5`
- `KERNEL32!GetProcessHeap` at `0x1800066bc`
- `KERNEL32!GetProcessHeap` at `0x1800066bc`
- `KERNEL32!CreateMutexExW` at `0x180006523`
- `KERNEL32!CreateMutexExW` at `0x180006523`
- `KERNEL32!CloseHandle` at `0x1800065d6`
- `KERNEL32!CloseHandle` at `0x180006696`
- `KERNEL32!CloseHandle` at `0x1800066ae`
- `KERNEL32!CloseHandle` at `0x1800066fd`
- `KERNEL32!CloseHandle` at `0x18000679e`
- `KERNEL32!CloseHandle` at `0x1800065d6`
- `KERNEL32!CloseHandle` at `0x180006696`
- `KERNEL32!CloseHandle` at `0x1800066ae`
- `KERNEL32!CloseHandle` at `0x1800066fd`
- `KERNEL32!CloseHandle` at `0x18000679e`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006544`
- `KERNEL32!WaitForSingleObjectEx` at `0x180006544`
- `KERNEL32!ReleaseMutex` at `0x1800065c5`
- `KERNEL32!ReleaseMutex` at `0x1800066ec`
- `KERNEL32!ReleaseMutex` at `0x180006788`
- `KERNEL32!ReleaseMutex` at `0x1800065c5`
- `KERNEL32!ReleaseMutex` at `0x1800066ec`
- `KERNEL32!ReleaseMutex` at `0x180006788`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180006755`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180006755`
- `KERNEL32!HeapFree` at `0x1800066ca`
- `KERNEL32!HeapFree` at `0x1800066ca`

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
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_28;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
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
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x1800064ac  mov     [rsp-8+arg_10], rbx
0x1800064b1  push    rbp
0x1800064b2  push    rsi
0x1800064b3  push    rdi
0x1800064b4  push    r14
0x1800064b6  push    r15
0x1800064b8  lea     rbp, [rsp-160h]
0x1800064c0  sub     rsp, 260h
0x1800064c7  mov     rax, cs:__security_cookie
0x1800064ce  xor     rax, rsp
0x1800064d1  mov     [rbp+180h+var_30], rax
0x1800064d8  mov     r15, rdx
0x1800064db  mov     qword ptr [rdx], 0
0x1800064e2  mov     rbx, rcx
0x1800064e5  call    cs:__imp_GetCurrentProcessId
0x1800064eb  mov     r14d, 130h
0x1800064f1  mov     [rsp+280h+var_258], rbx
0x1800064f6  mov     r9d, eax
0x1800064f9  mov     [rsp+280h+var_260], r14d; int
0x1800064fe  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006505  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000650a  lea     edx, [r14-2Ch]; unsigned __int64
0x18000650e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006513  mov     r9d, 1F0001h; dwDesiredAccess
0x180006519  lea     rdx, [rsp+280h+Name]; lpName
0x18000651e  xor     r8d, r8d; dwFlags
0x180006521  xor     ecx, ecx; lpMutexAttributes
0x180006523  call    cs:__imp_CreateMutexExW
0x180006529  mov     rbx, rax
0x18000652c  test    rax, rax
0x18000652f  jnz     short loc_18000653B
0x180006531  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006536  jmp     loc_1800067AA
0x18000653b  xor     r8d, r8d; bAlertable
0x18000653e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006541  mov     rcx, rbx; hHandle
0x180006544  call    cs:__imp_WaitForSingleObjectEx
0x18000654a  cmp     eax, 102h
0x18000654f  jz      short loc_180006561
0x180006551  test    eax, 0FFFFFF7Fh
0x180006556  jnz     loc_1800067F4
0x18000655c  mov     rdi, rbx
0x18000655f  jmp     short loc_180006563
0x180006561  xor     edi, edi
0x180006563  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006568  mov     [rsp+280h+hObject], 0
0x180006571  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006576  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000657b  mov     esi, eax
0x18000657d  test    eax, eax
0x18000657f  jns     short loc_1800065EB
0x180006581  mov     rcx, [rbp+188h]; this
0x180006588  mov     r9d, eax; char *
0x18000658b  mov     edx, 66h ; 'f'; void *
0x180006590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006595  mov     rcx, [rbp+188h]; this
0x18000659c  mov     r9d, esi; char *
0x18000659f  mov     edx, 6Fh ; 'o'; void *
0x1800065a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065a9  mov     rcx, [rbp+188h]; this
0x1800065b0  mov     r9d, esi; char *
0x1800065b3  mov     edx, 12Eh; void *
0x1800065b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065bd  test    rdi, rdi
0x1800065c0  jz      short loc_1800065D3
0x1800065c2  mov     rcx, rdi; hMutex
0x1800065c5  call    cs:__imp_ReleaseMutex
0x1800065cb  test    eax, eax
0x1800065cd  jz      loc_180006801
0x1800065d3  mov     rcx, rbx; hObject
0x1800065d6  call    cs:__imp_CloseHandle
0x1800065dc  test    eax, eax
0x1800065de  jz      loc_180006813
0x1800065e4  mov     eax, esi
0x1800065e6  jmp     loc_1800067AA
0x1800065eb  mov     rax, [rsp+280h+hObject]
0x1800065f0  lea     rcx, ds:0[rax*4]
0x1800065f8  test    rcx, rcx
0x1800065fb  jz      short loc_18000660B
0x1800065fd  mov     [r15], rcx
0x180006600  mov     eax, [rcx]
0x180006602  inc     eax
0x180006604  mov     [rcx], eax
0x180006606  jmp     loc_180006780
0x18000660b  mov     rdx, r14; dwBytes
0x18000660e  mov     qword ptr [r15], 0
0x180006615  mov     ecx, 8; dwFlags
0x18000661a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000661f  mov     r14, rax
0x180006622  test    rax, rax
0x180006625  jnz     short loc_180006645
0x180006627  mov     rcx, [rbp+188h]; this
0x18000662e  mov     esi, 8007000Eh
0x180006633  mov     r9d, esi; char *
0x180006636  mov     edx, 14Bh; void *
0x18000663b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006640  jmp     loc_1800066D0
0x180006645  xorps   xmm0, xmm0
0x180006648  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000664e  test    r14b, 3
0x180006652  jnz     loc_180006825
0x180006658  mov     r9, r14
0x18000665b  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006660  shr     r9, 2; unsigned __int64
0x180006664  lea     rcx, [rsp+280h+hObject]; this
0x180006669  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000666e  mov     esi, eax
0x180006670  test    eax, eax
0x180006672  jns     loc_180006710
0x180006678  mov     rcx, [rbp+188h]; this
0x18000667f  mov     r9d, eax; char *
0x180006682  mov     edx, 14Eh; void *
0x180006687  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000668c  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006691  test    rcx, rcx
0x180006694  jz      short loc_1800066A4
0x180006696  call    cs:__imp_CloseHandle
0x18000669c  test    eax, eax
0x18000669e  jz      loc_18000682B
0x1800066a4  mov     rcx, [rsp+280h+hObject]; hObject
0x1800066a9  test    rcx, rcx
0x1800066ac  jz      short loc_1800066BC
0x1800066ae  call    cs:__imp_CloseHandle
0x1800066b4  test    eax, eax
0x1800066b6  jz      loc_18000683D
0x1800066bc  call    cs:__imp_GetProcessHeap
0x1800066c2  mov     r8, r14; lpMem
0x1800066c5  xor     edx, edx; dwFlags
0x1800066c7  mov     rcx, rax; hHeap
0x1800066ca  call    cs:__imp_HeapFree
0x1800066d0  mov     rcx, [rbp+188h]; this
0x1800066d7  mov     r9d, esi; char *
0x1800066da  mov     edx, 137h; void *
0x1800066df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066e4  test    rdi, rdi
0x1800066e7  jz      short loc_1800066FA
0x1800066e9  mov     rcx, rdi; hMutex
0x1800066ec  call    cs:__imp_ReleaseMutex
0x1800066f2  test    eax, eax
0x1800066f4  jz      loc_18000684F
0x1800066fa  mov     rcx, rbx; hObject
0x1800066fd  call    cs:__imp_CloseHandle
0x180006703  test    eax, eax
0x180006705  jz      loc_1800067E2
0x18000670b  jmp     loc_1800065E4
0x180006710  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006715  lea     rcx, [r14+28h]; void *
0x180006719  mov     dword ptr [r14], 1
0x180006720  xor     edx, edx; Val
0x180006722  mov     [r14+8], rbx
0x180006726  mov     r8d, 108h; Size
0x18000672c  movdqu  xmmword ptr [r14+10h], xmm0
0x180006732  call    memset_0
0x180006737  xor     eax, eax
0x180006739  lea     rcx, [r14+28h]; this
0x18000673d  mov     [r14+20h], rax
0x180006741  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006746  lea     rbx, [r14+0E8h]
0x18000674d  xor     r8d, r8d; Flags
0x180006750  mov     rcx, rbx; lpCriticalSection
0x180006753  xor     edx, edx; dwSpinCount
0x180006755  call    cs:__imp_InitializeCriticalSectionEx
0x18000675b  mov     qword ptr [rbx+28h], 0
0x180006763  mov     qword ptr [rbx+30h], 0
0x18000676b  mov     qword ptr [rbx+38h], 0
0x180006773  mov     qword ptr [rbx+40h], 0
0x18000677b  xor     ebx, ebx
0x18000677d  mov     [r15], r14
0x180006780  test    rdi, rdi
0x180006783  jz      short loc_180006796
0x180006785  mov     rcx, rdi; hMutex
0x180006788  call    cs:__imp_ReleaseMutex
0x18000678e  test    eax, eax
0x180006790  jz      loc_180006861
0x180006796  test    rbx, rbx
0x180006799  jz      short loc_1800067A8
0x18000679b  mov     rcx, rbx; hObject
0x18000679e  call    cs:__imp_CloseHandle
0x1800067a4  test    eax, eax
0x1800067a6  jz      short loc_1800067D0
0x1800067a8  xor     eax, eax
0x1800067aa  mov     rcx, [rbp+180h+var_30]
0x1800067b1  xor     rcx, rsp; StackCookie
0x1800067b4  call    __security_check_cookie
0x1800067b9  mov     rbx, [rsp+280h+arg_10]
0x1800067c1  add     rsp, 260h
0x1800067c8  pop     r15
0x1800067ca  pop     r14
0x1800067cc  pop     rdi
0x1800067cd  pop     rsi
0x1800067ce  pop     rbp
0x1800067cf  retn
0x1800067d0  mov     rcx, [rbp+188h]; this
0x1800067d7  mov     edx, 0A0Bh; void *
0x1800067dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067e2  mov     rcx, [rbp+188h]; this
0x1800067e9  mov     edx, 0A0Bh; void *
0x1800067ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067f4  mov     rcx, [rbp+188h]; this
0x1800067fb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006801  mov     rcx, [rbp+188h]; this
0x180006808  mov     edx, 0A15h; void *
0x18000680d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006813  mov     rcx, [rbp+188h]; this
0x18000681a  mov     edx, 0A0Bh; void *
0x18000681f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006825  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000682b  mov     rcx, [rbp+188h]; this
0x180006832  mov     edx, 0A0Bh; void *
0x180006837  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000683d  mov     rcx, [rbp+188h]; this
0x180006844  mov     edx, 0A0Bh; void *
0x180006849  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000684f  mov     rcx, [rbp+188h]; this
0x180006856  mov     edx, 0A15h; void *
0x18000685b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006861  mov     rcx, [rbp+188h]; this
0x180006868  mov     edx, 0A15h; void *
0x18000686d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
