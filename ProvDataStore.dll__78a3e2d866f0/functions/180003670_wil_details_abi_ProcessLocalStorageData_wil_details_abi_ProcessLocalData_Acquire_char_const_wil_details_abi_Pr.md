# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003670`
- end: `0x180003a38`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800047a4`

## callees

- `0x180003670`
- `0x180003a9c`
- `0x180003dc4`
- `0x180004508`
- `0x180005088`
- `0x180005644`
- `0x180005e98`
- `0x18000608c`
- `0x180006550`
- `0x180006560`
- `0x180010f4e`
- `0x180010f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000379f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000394d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000379f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800038dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000394d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800036e8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800036e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003709`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003709`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800036a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003963`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003963`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
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
0x180003670  mov     [rsp-8+arg_10], rbx
0x180003675  push    rbp
0x180003676  push    rsi
0x180003677  push    rdi
0x180003678  push    r14
0x18000367a  push    r15
0x18000367c  lea     rbp, [rsp-160h]
0x180003684  sub     rsp, 260h
0x18000368b  mov     rax, cs:__security_cookie
0x180003692  xor     rax, rsp
0x180003695  mov     [rbp+180h+var_30], rax
0x18000369c  mov     r15, rdx
0x18000369f  mov     qword ptr [rdx], 0
0x1800036a6  mov     rbx, rcx
0x1800036a9  call    cs:__imp_GetCurrentProcessId
0x1800036af  mov     r14d, 78h ; 'x'
0x1800036b5  mov     [rsp+280h+var_258], rbx
0x1800036ba  mov     r9d, eax
0x1800036bd  mov     [rsp+280h+var_260], r14d; int
0x1800036c2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800036c9  mov     edx, 104h; unsigned __int64
0x1800036ce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800036d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800036d8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800036de  lea     rdx, [rsp+280h+Name]; lpName
0x1800036e3  xor     r8d, r8d; dwFlags
0x1800036e6  xor     ecx, ecx; lpMutexAttributes
0x1800036e8  call    cs:__imp_CreateMutexExW
0x1800036ee  mov     rbx, rax
0x1800036f1  test    rax, rax
0x1800036f4  jnz     short loc_180003700
0x1800036f6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800036fb  jmp     loc_18000396F
0x180003700  xor     r8d, r8d; bAlertable
0x180003703  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003706  mov     rcx, rbx; hHandle
0x180003709  call    cs:__imp_WaitForSingleObjectEx
0x18000370f  cmp     eax, 102h
0x180003714  jz      short loc_180003726
0x180003716  test    eax, 0FFFFFF7Fh
0x18000371b  jnz     loc_1800039A7
0x180003721  mov     rdi, rbx
0x180003724  jmp     short loc_180003728
0x180003726  xor     edi, edi
0x180003728  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000372d  mov     [rsp+280h+hObject], 0
0x180003736  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000373b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003740  mov     esi, eax
0x180003742  test    eax, eax
0x180003744  jns     short loc_1800037C5
0x180003746  mov     rcx, [rbp+188h]; this
0x18000374d  lea     r8, aWil; "wil"
0x180003754  mov     r9d, eax; char *
0x180003757  mov     edx, 66h ; 'f'; void *
0x18000375c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003761  mov     rcx, [rbp+188h]; this
0x180003768  lea     r8, aWil; "wil"
0x18000376f  mov     r9d, esi; char *
0x180003772  mov     edx, 6Fh ; 'o'; void *
0x180003777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000377c  mov     rcx, [rbp+188h]; this
0x180003783  lea     r8, aWil; "wil"
0x18000378a  mov     r9d, esi; char *
0x18000378d  mov     edx, 12Eh; void *
0x180003792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003797  test    rdi, rdi
0x18000379a  jz      short loc_1800037AD
0x18000379c  mov     rcx, rdi; hMutex
0x18000379f  call    cs:__imp_ReleaseMutex
0x1800037a5  test    eax, eax
0x1800037a7  jz      loc_1800039B4
0x1800037ad  mov     rcx, rbx; hObject
0x1800037b0  call    cs:__imp_CloseHandle
0x1800037b6  test    eax, eax
0x1800037b8  jz      loc_1800039C6
0x1800037be  mov     eax, esi
0x1800037c0  jmp     loc_18000396F
0x1800037c5  mov     rax, [rsp+280h+hObject]
0x1800037ca  lea     rcx, ds:0[rax*4]
0x1800037d2  test    rcx, rcx
0x1800037d5  jz      short loc_1800037E5
0x1800037d7  mov     [r15], rcx
0x1800037da  mov     eax, [rcx]
0x1800037dc  inc     eax
0x1800037de  mov     [rcx], eax
0x1800037e0  jmp     loc_180003945
0x1800037e5  mov     rdx, r14; dwBytes
0x1800037e8  mov     qword ptr [r15], 0
0x1800037ef  mov     ecx, 8; dwFlags
0x1800037f4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800037f9  mov     rsi, rax
0x1800037fc  test    rax, rax
0x1800037ff  jnz     short loc_180003827
0x180003801  mov     rcx, [rbp+188h]; this
0x180003808  lea     r8, aWil; "wil"
0x18000380f  mov     r14d, 8007000Eh
0x180003815  mov     edx, 14Bh; void *
0x18000381a  mov     r9d, r14d; char *
0x18000381d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003822  jmp     loc_1800038BA
0x180003827  xorps   xmm0, xmm0
0x18000382a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003830  test    sil, 3
0x180003834  jnz     loc_1800039D8
0x18000383a  mov     r9, rsi
0x18000383d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003842  shr     r9, 2; unsigned __int64
0x180003846  lea     rcx, [rsp+280h+hObject]; this
0x18000384b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003850  mov     r14d, eax
0x180003853  test    eax, eax
0x180003855  jns     loc_180003901
0x18000385b  mov     rcx, [rbp+188h]; this
0x180003862  lea     r8, aWil; "wil"
0x180003869  mov     r9d, eax; char *
0x18000386c  mov     edx, 14Eh; void *
0x180003871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003876  mov     rcx, [rsp+280h+hObject+8]; hObject
0x18000387b  test    rcx, rcx
0x18000387e  jz      short loc_18000388E
0x180003880  call    cs:__imp_CloseHandle
0x180003886  test    eax, eax
0x180003888  jz      loc_1800039DE
0x18000388e  mov     rcx, [rsp+280h+hObject]; hObject
0x180003893  test    rcx, rcx
0x180003896  jz      short loc_1800038A6
0x180003898  call    cs:__imp_CloseHandle
0x18000389e  test    eax, eax
0x1800038a0  jz      loc_1800039F0
0x1800038a6  call    cs:__imp_GetProcessHeap
0x1800038ac  mov     r8, rsi; lpMem
0x1800038af  xor     edx, edx; dwFlags
0x1800038b1  mov     rcx, rax; hHeap
0x1800038b4  call    cs:__imp_HeapFree
0x1800038ba  mov     rcx, [rbp+188h]; this
0x1800038c1  lea     r8, aWil; "wil"
0x1800038c8  mov     r9d, r14d; char *
0x1800038cb  mov     edx, 137h; void *
0x1800038d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038d5  test    rdi, rdi
0x1800038d8  jz      short loc_1800038EB
0x1800038da  mov     rcx, rdi; hMutex
0x1800038dd  call    cs:__imp_ReleaseMutex
0x1800038e3  test    eax, eax
0x1800038e5  jz      loc_180003A02
0x1800038eb  mov     rcx, rbx; hObject
0x1800038ee  call    cs:__imp_CloseHandle
0x1800038f4  test    eax, eax
0x1800038f6  jz      loc_180003A14
0x1800038fc  mov     eax, r14d
0x1800038ff  jmp     short loc_18000396F
0x180003901  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003906  xor     edx, edx; Val
0x180003908  mov     dword ptr [rsi], 1
0x18000390e  lea     rcx, [rsi+22h]; void *
0x180003912  mov     [rsi+8], rbx
0x180003916  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000391b  lea     r8d, [rdx+56h]; Size
0x18000391f  call    memset_0
0x180003924  xor     edx, edx; Val
0x180003926  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000392c  lea     rcx, [rsi+28h]; void *
0x180003930  mov     dword ptr [rsi+24h], 1
0x180003937  lea     r8d, [rdx+50h]; Size
0x18000393b  call    memset_0
0x180003940  xor     ebx, ebx
0x180003942  mov     [r15], rsi
0x180003945  test    rdi, rdi
0x180003948  jz      short loc_18000395B
0x18000394a  mov     rcx, rdi; hMutex
0x18000394d  call    cs:__imp_ReleaseMutex
0x180003953  test    eax, eax
0x180003955  jz      loc_180003A26
0x18000395b  test    rbx, rbx
0x18000395e  jz      short loc_18000396D
0x180003960  mov     rcx, rbx; hObject
0x180003963  call    cs:__imp_CloseHandle
0x180003969  test    eax, eax
0x18000396b  jz      short loc_180003995
0x18000396d  xor     eax, eax
0x18000396f  mov     rcx, [rbp+180h+var_30]
0x180003976  xor     rcx, rsp; StackCookie
0x180003979  call    __security_check_cookie
0x18000397e  mov     rbx, [rsp+280h+arg_10]
0x180003986  add     rsp, 260h
0x18000398d  pop     r15
0x18000398f  pop     r14
0x180003991  pop     rdi
0x180003992  pop     rsi
0x180003993  pop     rbp
0x180003994  retn
0x180003995  mov     rcx, [rbp+188h]; this
0x18000399c  mov     edx, 0A0Bh; void *
0x1800039a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039a7  mov     rcx, [rbp+188h]; this
0x1800039ae  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800039b4  mov     rcx, [rbp+188h]; this
0x1800039bb  mov     edx, 0A15h; void *
0x1800039c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039c6  mov     rcx, [rbp+188h]; this
0x1800039cd  mov     edx, 0A0Bh; void *
0x1800039d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039d8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800039de  mov     rcx, [rbp+188h]; this
0x1800039e5  mov     edx, 0A0Bh; void *
0x1800039ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800039f0  mov     rcx, [rbp+188h]; this
0x1800039f7  mov     edx, 0A0Bh; void *
0x1800039fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a02  mov     rcx, [rbp+188h]; this
0x180003a09  mov     edx, 0A15h; void *
0x180003a0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a14  mov     rcx, [rbp+188h]; this
0x180003a1b  mov     edx, 0A0Bh; void *
0x180003a20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a26  mov     rcx, [rbp+188h]; this
0x180003a2d  mov     edx, 0A15h; void *
0x180003a32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
