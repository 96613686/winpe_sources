# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003f90`
- end: `0x18000432e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004e00`

## callees

- `0x180003f90`
- `0x180004334`
- `0x180004604`
- `0x180004b98`
- `0x180005678`
- `0x1800058d4`
- `0x180006104`
- `0x1800061bc`
- `0x18000669c`
- `0x1800066ac`
- `0x18000b612`
- `0x18000b640`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003fc9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004029`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004029`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004243`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800041d3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004243`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004008`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800041a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800041b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000417d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004259`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000417d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004195`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800041e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004259`

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
0x180003f90  mov     [rsp-8+arg_10], rbx
0x180003f95  push    rbp
0x180003f96  push    rsi
0x180003f97  push    rdi
0x180003f98  push    r14
0x180003f9a  push    r15
0x180003f9c  lea     rbp, [rsp-160h]
0x180003fa4  sub     rsp, 260h
0x180003fab  mov     rax, cs:__security_cookie
0x180003fb2  xor     rax, rsp
0x180003fb5  mov     [rbp+180h+var_30], rax
0x180003fbc  mov     r15, rdx
0x180003fbf  mov     qword ptr [rdx], 0
0x180003fc6  mov     rbx, rcx
0x180003fc9  call    cs:__imp_GetCurrentProcessId
0x180003fcf  mov     r14d, 78h ; 'x'
0x180003fd5  mov     [rsp+280h+var_258], rbx
0x180003fda  mov     r9d, eax
0x180003fdd  mov     [rsp+280h+var_260], r14d; int
0x180003fe2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003fe9  mov     edx, 104h; unsigned __int64
0x180003fee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ff3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003ff8  mov     r9d, 1F0001h; dwDesiredAccess
0x180003ffe  lea     rdx, [rsp+280h+Name]; lpName
0x180004003  xor     r8d, r8d; dwFlags
0x180004006  xor     ecx, ecx; lpMutexAttributes
0x180004008  call    cs:__imp_CreateMutexExW
0x18000400e  mov     rbx, rax
0x180004011  test    rax, rax
0x180004014  jnz     short loc_180004020
0x180004016  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000401b  jmp     loc_180004265
0x180004020  xor     r8d, r8d; bAlertable
0x180004023  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004026  mov     rcx, rbx; hHandle
0x180004029  call    cs:__imp_WaitForSingleObjectEx
0x18000402f  cmp     eax, 102h
0x180004034  jz      short loc_180004046
0x180004036  test    eax, 0FFFFFF7Fh
0x18000403b  jnz     loc_18000429D
0x180004041  mov     rdi, rbx
0x180004044  jmp     short loc_180004048
0x180004046  xor     edi, edi
0x180004048  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18000404d  mov     [rsp+280h+hObject], 0
0x180004056  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000405b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004060  mov     esi, eax
0x180004062  test    eax, eax
0x180004064  jns     short loc_1800040D0
0x180004066  mov     rcx, [rbp+188h]; this
0x18000406d  mov     r9d, eax; char *
0x180004070  mov     edx, 66h ; 'f'; void *
0x180004075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000407a  mov     rcx, [rbp+188h]; this
0x180004081  mov     r9d, esi; char *
0x180004084  mov     edx, 6Fh ; 'o'; void *
0x180004089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000408e  mov     rcx, [rbp+188h]; this
0x180004095  mov     r9d, esi; char *
0x180004098  mov     edx, 12Eh; void *
0x18000409d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800040a2  test    rdi, rdi
0x1800040a5  jz      short loc_1800040B8
0x1800040a7  mov     rcx, rdi; hMutex
0x1800040aa  call    cs:__imp_ReleaseMutex
0x1800040b0  test    eax, eax
0x1800040b2  jz      loc_1800042AA
0x1800040b8  mov     rcx, rbx; hObject
0x1800040bb  call    cs:__imp_CloseHandle
0x1800040c1  test    eax, eax
0x1800040c3  jz      loc_1800042BC
0x1800040c9  mov     eax, esi
0x1800040cb  jmp     loc_180004265
0x1800040d0  mov     rax, [rsp+280h+hObject]
0x1800040d5  lea     rcx, ds:0[rax*4]
0x1800040dd  test    rcx, rcx
0x1800040e0  jz      short loc_1800040F0
0x1800040e2  mov     [r15], rcx
0x1800040e5  mov     eax, [rcx]
0x1800040e7  inc     eax
0x1800040e9  mov     [rcx], eax
0x1800040eb  jmp     loc_18000423B
0x1800040f0  mov     rdx, r14; dwBytes
0x1800040f3  mov     qword ptr [r15], 0
0x1800040fa  mov     ecx, 8; dwFlags
0x1800040ff  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004104  mov     rsi, rax
0x180004107  test    rax, rax
0x18000410a  jnz     short loc_18000412B
0x18000410c  mov     rcx, [rbp+188h]; this
0x180004113  mov     r14d, 8007000Eh
0x180004119  mov     r9d, r14d; char *
0x18000411c  mov     edx, 14Bh; void *
0x180004121  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004126  jmp     loc_1800041B7
0x18000412b  xorps   xmm0, xmm0
0x18000412e  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004134  test    sil, 3
0x180004138  jnz     loc_1800042CE
0x18000413e  mov     r9, rsi
0x180004141  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004146  shr     r9, 2; unsigned __int64
0x18000414a  lea     rcx, [rsp+280h+hObject]; this
0x18000414f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004154  mov     r14d, eax
0x180004157  test    eax, eax
0x180004159  jns     loc_1800041F7
0x18000415f  mov     rcx, [rbp+188h]; this
0x180004166  mov     r9d, eax; char *
0x180004169  mov     edx, 14Eh; void *
0x18000416e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004173  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004178  test    rcx, rcx
0x18000417b  jz      short loc_18000418B
0x18000417d  call    cs:__imp_CloseHandle
0x180004183  test    eax, eax
0x180004185  jz      loc_1800042D4
0x18000418b  mov     rcx, [rsp+280h+hObject]; hObject
0x180004190  test    rcx, rcx
0x180004193  jz      short loc_1800041A3
0x180004195  call    cs:__imp_CloseHandle
0x18000419b  test    eax, eax
0x18000419d  jz      loc_1800042E6
0x1800041a3  call    cs:__imp_GetProcessHeap
0x1800041a9  mov     r8, rsi; lpMem
0x1800041ac  xor     edx, edx; dwFlags
0x1800041ae  mov     rcx, rax; hHeap
0x1800041b1  call    cs:__imp_HeapFree
0x1800041b7  mov     rcx, [rbp+188h]; this
0x1800041be  mov     r9d, r14d; char *
0x1800041c1  mov     edx, 137h; void *
0x1800041c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800041cb  test    rdi, rdi
0x1800041ce  jz      short loc_1800041E1
0x1800041d0  mov     rcx, rdi; hMutex
0x1800041d3  call    cs:__imp_ReleaseMutex
0x1800041d9  test    eax, eax
0x1800041db  jz      loc_1800042F8
0x1800041e1  mov     rcx, rbx; hObject
0x1800041e4  call    cs:__imp_CloseHandle
0x1800041ea  test    eax, eax
0x1800041ec  jz      loc_18000430A
0x1800041f2  mov     eax, r14d
0x1800041f5  jmp     short loc_180004265
0x1800041f7  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1800041fc  xor     edx, edx; Val
0x1800041fe  mov     dword ptr [rsi], 1
0x180004204  lea     rcx, [rsi+22h]; void *
0x180004208  mov     [rsi+8], rbx
0x18000420c  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004211  lea     r8d, [rdx+56h]; Size
0x180004215  call    memset_0
0x18000421a  xor     edx, edx; Val
0x18000421c  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004222  lea     rcx, [rsi+28h]; void *
0x180004226  mov     dword ptr [rsi+24h], 1
0x18000422d  lea     r8d, [rdx+50h]; Size
0x180004231  call    memset_0
0x180004236  xor     ebx, ebx
0x180004238  mov     [r15], rsi
0x18000423b  test    rdi, rdi
0x18000423e  jz      short loc_180004251
0x180004240  mov     rcx, rdi; hMutex
0x180004243  call    cs:__imp_ReleaseMutex
0x180004249  test    eax, eax
0x18000424b  jz      loc_18000431C
0x180004251  test    rbx, rbx
0x180004254  jz      short loc_180004263
0x180004256  mov     rcx, rbx; hObject
0x180004259  call    cs:__imp_CloseHandle
0x18000425f  test    eax, eax
0x180004261  jz      short loc_18000428B
0x180004263  xor     eax, eax
0x180004265  mov     rcx, [rbp+180h+var_30]
0x18000426c  xor     rcx, rsp; StackCookie
0x18000426f  call    __security_check_cookie
0x180004274  mov     rbx, [rsp+280h+arg_10]
0x18000427c  add     rsp, 260h
0x180004283  pop     r15
0x180004285  pop     r14
0x180004287  pop     rdi
0x180004288  pop     rsi
0x180004289  pop     rbp
0x18000428a  retn
0x18000428b  mov     rcx, [rbp+188h]; this
0x180004292  mov     edx, 0A0Bh; void *
0x180004297  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000429d  mov     rcx, [rbp+188h]; this
0x1800042a4  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800042aa  mov     rcx, [rbp+188h]; this
0x1800042b1  mov     edx, 0A15h; void *
0x1800042b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042bc  mov     rcx, [rbp+188h]; this
0x1800042c3  mov     edx, 0A0Bh; void *
0x1800042c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042ce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800042d4  mov     rcx, [rbp+188h]; this
0x1800042db  mov     edx, 0A0Bh; void *
0x1800042e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042e6  mov     rcx, [rbp+188h]; this
0x1800042ed  mov     edx, 0A0Bh; void *
0x1800042f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800042f8  mov     rcx, [rbp+188h]; this
0x1800042ff  mov     edx, 0A15h; void *
0x180004304  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000430a  mov     rcx, [rbp+188h]; this
0x180004311  mov     edx, 0A0Bh; void *
0x180004316  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000431c  mov     rcx, [rbp+188h]; this
0x180004323  mov     edx, 0A15h; void *
0x180004328  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
