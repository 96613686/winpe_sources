# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800036f4`
- end: `0x180003a92`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004e4c`

## callees

- `0x1800018e0`
- `0x1800024d4`
- `0x1800036f4`
- `0x180003e68`
- `0x1800042c4`
- `0x180004be8`
- `0x1800057d8`
- `0x180006ae0`
- `0x180007020`
- `0x180007348`
- `0x180007b2c`
- `0x180007b3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000378d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000378d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000376c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000376c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000380e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003937`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000380e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003937`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003907`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003907`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003915`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003915`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000372d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000372d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000381f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000381f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800038f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800039bd`

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
0x1800036f4  mov     [rsp-8+arg_10], rbx
0x1800036f9  push    rbp
0x1800036fa  push    rsi
0x1800036fb  push    rdi
0x1800036fc  push    r14
0x1800036fe  push    r15
0x180003700  lea     rbp, [rsp-160h]
0x180003708  sub     rsp, 260h
0x18000370f  mov     rax, cs:__security_cookie
0x180003716  xor     rax, rsp
0x180003719  mov     [rbp+180h+var_30], rax
0x180003720  mov     r15, rdx
0x180003723  mov     qword ptr [rdx], 0
0x18000372a  mov     rbx, rcx
0x18000372d  call    cs:__imp_GetCurrentProcessId
0x180003733  mov     r14d, 78h ; 'x'
0x180003739  mov     [rsp+280h+var_258], rbx
0x18000373e  mov     r9d, eax
0x180003741  mov     [rsp+280h+var_260], r14d; int
0x180003746  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000374d  mov     edx, 104h; unsigned __int64
0x180003752  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003757  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000375c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003762  lea     rdx, [rsp+280h+Name]; lpName
0x180003767  xor     r8d, r8d; dwFlags
0x18000376a  xor     ecx, ecx; lpMutexAttributes
0x18000376c  call    cs:__imp_CreateMutexExW
0x180003772  mov     rbx, rax
0x180003775  test    rax, rax
0x180003778  jnz     short loc_180003784
0x18000377a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000377f  jmp     loc_1800039C9
0x180003784  xor     r8d, r8d; bAlertable
0x180003787  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000378a  mov     rcx, rbx; hHandle
0x18000378d  call    cs:__imp_WaitForSingleObjectEx
0x180003793  cmp     eax, 102h
0x180003798  jz      short loc_1800037AA
0x18000379a  test    eax, 0FFFFFF7Fh
0x18000379f  jnz     loc_180003A01
0x1800037a5  mov     rdi, rbx
0x1800037a8  jmp     short loc_1800037AC
0x1800037aa  xor     edi, edi
0x1800037ac  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800037b1  mov     [rsp+280h+hObject], 0
0x1800037ba  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800037bf  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800037c4  mov     esi, eax
0x1800037c6  test    eax, eax
0x1800037c8  jns     short loc_180003834
0x1800037ca  mov     rcx, [rbp+188h]; this
0x1800037d1  mov     r9d, eax; char *
0x1800037d4  mov     edx, 66h ; 'f'; void *
0x1800037d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037de  mov     rcx, [rbp+188h]; this
0x1800037e5  mov     r9d, esi; char *
0x1800037e8  mov     edx, 6Fh ; 'o'; void *
0x1800037ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037f2  mov     rcx, [rbp+188h]; this
0x1800037f9  mov     r9d, esi; char *
0x1800037fc  mov     edx, 12Eh; void *
0x180003801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003806  test    rdi, rdi
0x180003809  jz      short loc_18000381C
0x18000380b  mov     rcx, rdi; hMutex
0x18000380e  call    cs:__imp_ReleaseMutex
0x180003814  test    eax, eax
0x180003816  jz      loc_180003A0E
0x18000381c  mov     rcx, rbx; hObject
0x18000381f  call    cs:__imp_CloseHandle
0x180003825  test    eax, eax
0x180003827  jz      loc_180003A20
0x18000382d  mov     eax, esi
0x18000382f  jmp     loc_1800039C9
0x180003834  mov     rax, [rsp+280h+hObject]
0x180003839  lea     rcx, ds:0[rax*4]
0x180003841  test    rcx, rcx
0x180003844  jz      short loc_180003854
0x180003846  mov     [r15], rcx
0x180003849  mov     eax, [rcx]
0x18000384b  inc     eax
0x18000384d  mov     [rcx], eax
0x18000384f  jmp     loc_18000399F
0x180003854  mov     rdx, r14; dwBytes
0x180003857  mov     qword ptr [r15], 0
0x18000385e  mov     ecx, 8; dwFlags
0x180003863  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003868  mov     rsi, rax
0x18000386b  test    rax, rax
0x18000386e  jnz     short loc_18000388F
0x180003870  mov     rcx, [rbp+188h]; this
0x180003877  mov     r14d, 8007000Eh
0x18000387d  mov     r9d, r14d; char *
0x180003880  mov     edx, 14Bh; void *
0x180003885  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000388a  jmp     loc_18000391B
0x18000388f  xorps   xmm0, xmm0
0x180003892  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003898  test    sil, 3
0x18000389c  jnz     loc_180003A32
0x1800038a2  mov     r9, rsi
0x1800038a5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800038aa  shr     r9, 2; unsigned __int64
0x1800038ae  lea     rcx, [rsp+280h+hObject]; this
0x1800038b3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800038b8  mov     r14d, eax
0x1800038bb  test    eax, eax
0x1800038bd  jns     loc_18000395B
0x1800038c3  mov     rcx, [rbp+188h]; this
0x1800038ca  mov     r9d, eax; char *
0x1800038cd  mov     edx, 14Eh; void *
0x1800038d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038d7  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800038dc  test    rcx, rcx
0x1800038df  jz      short loc_1800038EF
0x1800038e1  call    cs:__imp_CloseHandle
0x1800038e7  test    eax, eax
0x1800038e9  jz      loc_180003A38
0x1800038ef  mov     rcx, [rsp+280h+hObject]; hObject
0x1800038f4  test    rcx, rcx
0x1800038f7  jz      short loc_180003907
0x1800038f9  call    cs:__imp_CloseHandle
0x1800038ff  test    eax, eax
0x180003901  jz      loc_180003A4A
0x180003907  call    cs:__imp_GetProcessHeap
0x18000390d  mov     r8, rsi; lpMem
0x180003910  xor     edx, edx; dwFlags
0x180003912  mov     rcx, rax; hHeap
0x180003915  call    cs:__imp_HeapFree
0x18000391b  mov     rcx, [rbp+188h]; this
0x180003922  mov     r9d, r14d; char *
0x180003925  mov     edx, 137h; void *
0x18000392a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000392f  test    rdi, rdi
0x180003932  jz      short loc_180003945
0x180003934  mov     rcx, rdi; hMutex
0x180003937  call    cs:__imp_ReleaseMutex
0x18000393d  test    eax, eax
0x18000393f  jz      loc_180003A5C
0x180003945  mov     rcx, rbx; hObject
0x180003948  call    cs:__imp_CloseHandle
0x18000394e  test    eax, eax
0x180003950  jz      loc_180003A6E
0x180003956  mov     eax, r14d
0x180003959  jmp     short loc_1800039C9
0x18000395b  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003960  xor     edx, edx; Val
0x180003962  mov     dword ptr [rsi], 1
0x180003968  lea     rcx, [rsi+22h]; void *
0x18000396c  mov     [rsi+8], rbx
0x180003970  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003975  lea     r8d, [rdx+56h]; Size
0x180003979  call    memset_0
0x18000397e  xor     edx, edx; Val
0x180003980  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003986  lea     rcx, [rsi+28h]; void *
0x18000398a  mov     dword ptr [rsi+24h], 1
0x180003991  lea     r8d, [rdx+50h]; Size
0x180003995  call    memset_0
0x18000399a  xor     ebx, ebx
0x18000399c  mov     [r15], rsi
0x18000399f  test    rdi, rdi
0x1800039a2  jz      short loc_1800039B5
0x1800039a4  mov     rcx, rdi; hMutex
0x1800039a7  call    cs:__imp_ReleaseMutex
0x1800039ad  test    eax, eax
0x1800039af  jz      loc_180003A80
0x1800039b5  test    rbx, rbx
0x1800039b8  jz      short loc_1800039C7
0x1800039ba  mov     rcx, rbx; hObject
0x1800039bd  call    cs:__imp_CloseHandle
0x1800039c3  test    eax, eax
0x1800039c5  jz      short loc_1800039EF
0x1800039c7  xor     eax, eax
0x1800039c9  mov     rcx, [rbp+180h+var_30]
0x1800039d0  xor     rcx, rsp; StackCookie
0x1800039d3  call    __security_check_cookie
0x1800039d8  mov     rbx, [rsp+280h+arg_10]
0x1800039e0  add     rsp, 260h
0x1800039e7  pop     r15
0x1800039e9  pop     r14
0x1800039eb  pop     rdi
0x1800039ec  pop     rsi
0x1800039ed  pop     rbp
0x1800039ee  retn
0x1800039ef  mov     rcx, [rbp+188h]; this
0x1800039f6  mov     edx, 0A0Bh; void *
0x1800039fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a01  mov     rcx, [rbp+188h]; this
0x180003a08  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003a0e  mov     rcx, [rbp+188h]; this
0x180003a15  mov     edx, 0A15h; void *
0x180003a1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a20  mov     rcx, [rbp+188h]; this
0x180003a27  mov     edx, 0A0Bh; void *
0x180003a2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a32  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003a38  mov     rcx, [rbp+188h]; this
0x180003a3f  mov     edx, 0A0Bh; void *
0x180003a44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a4a  mov     rcx, [rbp+188h]; this
0x180003a51  mov     edx, 0A0Bh; void *
0x180003a56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a5c  mov     rcx, [rbp+188h]; this
0x180003a63  mov     edx, 0A15h; void *
0x180003a68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a6e  mov     rcx, [rbp+188h]; this
0x180003a75  mov     edx, 0A0Bh; void *
0x180003a7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003a80  mov     rcx, [rbp+188h]; this
0x180003a87  mov     edx, 0A15h; void *
0x180003a8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
