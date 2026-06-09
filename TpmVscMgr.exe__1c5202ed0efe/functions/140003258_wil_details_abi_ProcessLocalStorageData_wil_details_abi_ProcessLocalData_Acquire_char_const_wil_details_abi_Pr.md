# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003258`
- end: `0x1400035f6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400040e0`

## callees

- `0x1400016a0`
- `0x140002456`
- `0x140003258`
- `0x1400035fc`
- `0x140003820`
- `0x140003e78`
- `0x140004948`
- `0x140004db4`
- `0x140005740`
- `0x1400057fc`
- `0x140005bac`
- `0x140005bbc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003479`
- `KERNEL32!HeapFree` at `0x140003479`
- `KERNEL32!ReleaseMutex` at `0x140003372`
- `KERNEL32!ReleaseMutex` at `0x14000349b`
- `KERNEL32!ReleaseMutex` at `0x14000350b`
- `KERNEL32!ReleaseMutex` at `0x140003372`
- `KERNEL32!ReleaseMutex` at `0x14000349b`
- `KERNEL32!ReleaseMutex` at `0x14000350b`
- `KERNEL32!CloseHandle` at `0x140003383`
- `KERNEL32!CloseHandle` at `0x140003445`
- `KERNEL32!CloseHandle` at `0x14000345d`
- `KERNEL32!CloseHandle` at `0x1400034ac`
- `KERNEL32!CloseHandle` at `0x140003521`
- `KERNEL32!CloseHandle` at `0x140003383`
- `KERNEL32!CloseHandle` at `0x140003445`
- `KERNEL32!CloseHandle` at `0x14000345d`
- `KERNEL32!CloseHandle` at `0x1400034ac`
- `KERNEL32!CloseHandle` at `0x140003521`
- `KERNEL32!CreateMutexExW` at `0x1400032d0`
- `KERNEL32!CreateMutexExW` at `0x1400032d0`
- `KERNEL32!GetCurrentProcessId` at `0x140003291`
- `KERNEL32!GetCurrentProcessId` at `0x140003291`
- `KERNEL32!GetProcessHeap` at `0x14000346b`
- `KERNEL32!GetProcessHeap` at `0x14000346b`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400032f1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400032f1`

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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int128 v40; // xmm0
  __int64 v41; // r8
  const char *v42; // r9
  __int64 v43; // r8
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  if ( v23 )
  {
    *(_OWORD *)hObject = 0;
    if ( (v23 & 3) != 0 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    v29 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
            (wil::details_abi::SemaphoreValue *)hObject,
            Name,
            v25,
            v23 >> 2);
    v27 = v29;
    if ( v29 >= 0 )
    {
      v40 = *(_OWORD *)hObject;
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x140003258  mov     [rsp-8+arg_10], rbx
0x14000325d  push    rbp
0x14000325e  push    rsi
0x14000325f  push    rdi
0x140003260  push    r14
0x140003262  push    r15
0x140003264  lea     rbp, [rsp-160h]
0x14000326c  sub     rsp, 260h
0x140003273  mov     rax, cs:__security_cookie
0x14000327a  xor     rax, rsp
0x14000327d  mov     [rbp+180h+var_30], rax
0x140003284  mov     r15, rdx
0x140003287  mov     qword ptr [rdx], 0
0x14000328e  mov     rbx, rcx
0x140003291  call    cs:__imp_GetCurrentProcessId
0x140003297  mov     r14d, 78h ; 'x'
0x14000329d  mov     [rsp+280h+var_258], rbx
0x1400032a2  mov     r9d, eax
0x1400032a5  mov     [rsp+280h+var_260], r14d; int
0x1400032aa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400032b1  mov     edx, 104h; unsigned __int64
0x1400032b6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400032bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400032c0  mov     r9d, 1F0001h; dwDesiredAccess
0x1400032c6  lea     rdx, [rsp+280h+Name]; lpName
0x1400032cb  xor     r8d, r8d; dwFlags
0x1400032ce  xor     ecx, ecx; lpMutexAttributes
0x1400032d0  call    cs:__imp_CreateMutexExW
0x1400032d6  mov     rbx, rax
0x1400032d9  test    rax, rax
0x1400032dc  jnz     short loc_1400032E8
0x1400032de  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400032e3  jmp     loc_14000352D
0x1400032e8  xor     r8d, r8d; bAlertable
0x1400032eb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400032ee  mov     rcx, rbx; hHandle
0x1400032f1  call    cs:__imp_WaitForSingleObjectEx
0x1400032f7  cmp     eax, 102h
0x1400032fc  jz      short loc_14000330E
0x1400032fe  test    eax, 0FFFFFF7Fh
0x140003303  jnz     loc_140003565
0x140003309  mov     rdi, rbx
0x14000330c  jmp     short loc_140003310
0x14000330e  xor     edi, edi
0x140003310  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003315  mov     [rsp+280h+hObject], 0
0x14000331e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003323  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003328  mov     esi, eax
0x14000332a  test    eax, eax
0x14000332c  jns     short loc_140003398
0x14000332e  mov     rcx, [rbp+188h]; this
0x140003335  mov     r9d, eax; char *
0x140003338  mov     edx, 66h ; 'f'; void *
0x14000333d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003342  mov     rcx, [rbp+188h]; this
0x140003349  mov     r9d, esi; char *
0x14000334c  mov     edx, 6Fh ; 'o'; void *
0x140003351  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003356  mov     rcx, [rbp+188h]; this
0x14000335d  mov     r9d, esi; char *
0x140003360  mov     edx, 12Eh; void *
0x140003365  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000336a  test    rdi, rdi
0x14000336d  jz      short loc_140003380
0x14000336f  mov     rcx, rdi; hMutex
0x140003372  call    cs:__imp_ReleaseMutex
0x140003378  test    eax, eax
0x14000337a  jz      loc_140003572
0x140003380  mov     rcx, rbx; hObject
0x140003383  call    cs:__imp_CloseHandle
0x140003389  test    eax, eax
0x14000338b  jz      loc_140003584
0x140003391  mov     eax, esi
0x140003393  jmp     loc_14000352D
0x140003398  mov     rax, [rsp+280h+hObject]
0x14000339d  lea     rcx, ds:0[rax*4]
0x1400033a5  test    rcx, rcx
0x1400033a8  jz      short loc_1400033B8
0x1400033aa  mov     [r15], rcx
0x1400033ad  mov     eax, [rcx]
0x1400033af  inc     eax
0x1400033b1  mov     [rcx], eax
0x1400033b3  jmp     loc_140003503
0x1400033b8  mov     rdx, r14; dwBytes
0x1400033bb  mov     qword ptr [r15], 0
0x1400033c2  mov     ecx, 8; dwFlags
0x1400033c7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400033cc  mov     rsi, rax
0x1400033cf  test    rax, rax
0x1400033d2  jnz     short loc_1400033F3
0x1400033d4  mov     rcx, [rbp+188h]; this
0x1400033db  mov     r14d, 8007000Eh
0x1400033e1  mov     r9d, r14d; char *
0x1400033e4  mov     edx, 14Bh; void *
0x1400033e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400033ee  jmp     loc_14000347F
0x1400033f3  xorps   xmm0, xmm0
0x1400033f6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400033fc  test    sil, 3
0x140003400  jnz     loc_140003596
0x140003406  mov     r9, rsi
0x140003409  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000340e  shr     r9, 2; unsigned __int64
0x140003412  lea     rcx, [rsp+280h+hObject]; this
0x140003417  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14000341c  mov     r14d, eax
0x14000341f  test    eax, eax
0x140003421  jns     loc_1400034BF
0x140003427  mov     rcx, [rbp+188h]; this
0x14000342e  mov     r9d, eax; char *
0x140003431  mov     edx, 14Eh; void *
0x140003436  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000343b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003440  test    rcx, rcx
0x140003443  jz      short loc_140003453
0x140003445  call    cs:__imp_CloseHandle
0x14000344b  test    eax, eax
0x14000344d  jz      loc_14000359C
0x140003453  mov     rcx, [rsp+280h+hObject]; hObject
0x140003458  test    rcx, rcx
0x14000345b  jz      short loc_14000346B
0x14000345d  call    cs:__imp_CloseHandle
0x140003463  test    eax, eax
0x140003465  jz      loc_1400035AE
0x14000346b  call    cs:__imp_GetProcessHeap
0x140003471  mov     r8, rsi; lpMem
0x140003474  xor     edx, edx; dwFlags
0x140003476  mov     rcx, rax; hHeap
0x140003479  call    cs:__imp_HeapFree
0x14000347f  mov     rcx, [rbp+188h]; this
0x140003486  mov     r9d, r14d; char *
0x140003489  mov     edx, 137h; void *
0x14000348e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003493  test    rdi, rdi
0x140003496  jz      short loc_1400034A9
0x140003498  mov     rcx, rdi; hMutex
0x14000349b  call    cs:__imp_ReleaseMutex
0x1400034a1  test    eax, eax
0x1400034a3  jz      loc_1400035C0
0x1400034a9  mov     rcx, rbx; hObject
0x1400034ac  call    cs:__imp_CloseHandle
0x1400034b2  test    eax, eax
0x1400034b4  jz      loc_1400035D2
0x1400034ba  mov     eax, r14d
0x1400034bd  jmp     short loc_14000352D
0x1400034bf  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400034c4  xor     edx, edx; Val
0x1400034c6  mov     dword ptr [rsi], 1
0x1400034cc  lea     rcx, [rsi+22h]; void *
0x1400034d0  mov     [rsi+8], rbx
0x1400034d4  movdqu  xmmword ptr [rsi+10h], xmm0
0x1400034d9  lea     r8d, [rdx+56h]; Size
0x1400034dd  call    memset_0
0x1400034e2  xor     edx, edx; Val
0x1400034e4  mov     word ptr [rsi+20h], 58h ; 'X'
0x1400034ea  lea     rcx, [rsi+28h]; void *
0x1400034ee  mov     dword ptr [rsi+24h], 1
0x1400034f5  lea     r8d, [rdx+50h]; Size
0x1400034f9  call    memset_0
0x1400034fe  xor     ebx, ebx
0x140003500  mov     [r15], rsi
0x140003503  test    rdi, rdi
0x140003506  jz      short loc_140003519
0x140003508  mov     rcx, rdi; hMutex
0x14000350b  call    cs:__imp_ReleaseMutex
0x140003511  test    eax, eax
0x140003513  jz      loc_1400035E4
0x140003519  test    rbx, rbx
0x14000351c  jz      short loc_14000352B
0x14000351e  mov     rcx, rbx; hObject
0x140003521  call    cs:__imp_CloseHandle
0x140003527  test    eax, eax
0x140003529  jz      short loc_140003553
0x14000352b  xor     eax, eax
0x14000352d  mov     rcx, [rbp+180h+var_30]
0x140003534  xor     rcx, rsp; StackCookie
0x140003537  call    __security_check_cookie
0x14000353c  mov     rbx, [rsp+280h+arg_10]
0x140003544  add     rsp, 260h
0x14000354b  pop     r15
0x14000354d  pop     r14
0x14000354f  pop     rdi
0x140003550  pop     rsi
0x140003551  pop     rbp
0x140003552  retn
0x140003553  mov     rcx, [rbp+188h]; this
0x14000355a  mov     edx, 0A0Bh; void *
0x14000355f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003565  mov     rcx, [rbp+188h]; this
0x14000356c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003572  mov     rcx, [rbp+188h]; this
0x140003579  mov     edx, 0A15h; void *
0x14000357e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003584  mov     rcx, [rbp+188h]; this
0x14000358b  mov     edx, 0A0Bh; void *
0x140003590  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003596  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000359c  mov     rcx, [rbp+188h]; this
0x1400035a3  mov     edx, 0A0Bh; void *
0x1400035a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400035ae  mov     rcx, [rbp+188h]; this
0x1400035b5  mov     edx, 0A0Bh; void *
0x1400035ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400035c0  mov     rcx, [rbp+188h]; this
0x1400035c7  mov     edx, 0A15h; void *
0x1400035cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400035d2  mov     rcx, [rbp+188h]; this
0x1400035d9  mov     edx, 0A0Bh; void *
0x1400035de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400035e4  mov     rcx, [rbp+188h]; this
0x1400035eb  mov     edx, 0A15h; void *
0x1400035f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
