# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003dd8`
- end: `0x1800041a0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004ca0`

## callees

- `0x180002200`
- `0x180002f7c`
- `0x180003dd8`
- `0x1800041a8`
- `0x1800043f0`
- `0x180004a38`
- `0x180005518`
- `0x180005984`
- `0x180006310`
- `0x1800063ec`
- `0x1800067cc`
- `0x1800067dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e50`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003e50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003e71`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004045`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003f07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004045`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800040b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000401c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000401c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000400e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000400e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003e11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fe8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003fe8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040cb`

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
0x180003dd8  mov     [rsp-8+arg_10], rbx
0x180003ddd  push    rbp
0x180003dde  push    rsi
0x180003ddf  push    rdi
0x180003de0  push    r14
0x180003de2  push    r15
0x180003de4  lea     rbp, [rsp-160h]
0x180003dec  sub     rsp, 260h
0x180003df3  mov     rax, cs:__security_cookie
0x180003dfa  xor     rax, rsp
0x180003dfd  mov     [rbp+180h+var_30], rax
0x180003e04  mov     r15, rdx
0x180003e07  mov     qword ptr [rdx], 0
0x180003e0e  mov     rbx, rcx
0x180003e11  call    cs:__imp_GetCurrentProcessId
0x180003e17  mov     r14d, 78h ; 'x'
0x180003e1d  mov     [rsp+280h+var_258], rbx
0x180003e22  mov     r9d, eax
0x180003e25  mov     [rsp+280h+var_260], r14d; int
0x180003e2a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003e31  mov     edx, 104h; unsigned __int64
0x180003e36  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003e3b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003e40  mov     r9d, 1F0001h; dwDesiredAccess
0x180003e46  lea     rdx, [rsp+280h+Name]; lpName
0x180003e4b  xor     r8d, r8d; dwFlags
0x180003e4e  xor     ecx, ecx; lpMutexAttributes
0x180003e50  call    cs:__imp_CreateMutexExW
0x180003e56  mov     rbx, rax
0x180003e59  test    rax, rax
0x180003e5c  jnz     short loc_180003E68
0x180003e5e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003e63  jmp     loc_1800040D7
0x180003e68  xor     r8d, r8d; bAlertable
0x180003e6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180003e6e  mov     rcx, rbx; hHandle
0x180003e71  call    cs:__imp_WaitForSingleObjectEx
0x180003e77  cmp     eax, 102h
0x180003e7c  jz      short loc_180003E8E
0x180003e7e  test    eax, 0FFFFFF7Fh
0x180003e83  jnz     loc_18000410F
0x180003e89  mov     rdi, rbx
0x180003e8c  jmp     short loc_180003E90
0x180003e8e  xor     edi, edi
0x180003e90  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003e95  mov     [rsp+280h+hObject], 0
0x180003e9e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003ea3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003ea8  mov     esi, eax
0x180003eaa  test    eax, eax
0x180003eac  jns     short loc_180003F2D
0x180003eae  mov     rcx, [rbp+188h]; this
0x180003eb5  lea     r8, aWil; "wil"
0x180003ebc  mov     r9d, eax; char *
0x180003ebf  mov     edx, 66h ; 'f'; void *
0x180003ec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ec9  mov     rcx, [rbp+188h]; this
0x180003ed0  lea     r8, aWil; "wil"
0x180003ed7  mov     r9d, esi; char *
0x180003eda  mov     edx, 6Fh ; 'o'; void *
0x180003edf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ee4  mov     rcx, [rbp+188h]; this
0x180003eeb  lea     r8, aWil; "wil"
0x180003ef2  mov     r9d, esi; char *
0x180003ef5  mov     edx, 12Eh; void *
0x180003efa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003eff  test    rdi, rdi
0x180003f02  jz      short loc_180003F15
0x180003f04  mov     rcx, rdi; hMutex
0x180003f07  call    cs:__imp_ReleaseMutex
0x180003f0d  test    eax, eax
0x180003f0f  jz      loc_18000411C
0x180003f15  mov     rcx, rbx; hObject
0x180003f18  call    cs:__imp_CloseHandle
0x180003f1e  test    eax, eax
0x180003f20  jz      loc_18000412E
0x180003f26  mov     eax, esi
0x180003f28  jmp     loc_1800040D7
0x180003f2d  mov     rax, [rsp+280h+hObject]
0x180003f32  lea     rcx, ds:0[rax*4]
0x180003f3a  test    rcx, rcx
0x180003f3d  jz      short loc_180003F4D
0x180003f3f  mov     [r15], rcx
0x180003f42  mov     eax, [rcx]
0x180003f44  inc     eax
0x180003f46  mov     [rcx], eax
0x180003f48  jmp     loc_1800040AD
0x180003f4d  mov     rdx, r14; dwBytes
0x180003f50  mov     qword ptr [r15], 0
0x180003f57  mov     ecx, 8; dwFlags
0x180003f5c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f61  mov     rsi, rax
0x180003f64  test    rax, rax
0x180003f67  jnz     short loc_180003F8F
0x180003f69  mov     rcx, [rbp+188h]; this
0x180003f70  lea     r8, aWil; "wil"
0x180003f77  mov     r14d, 8007000Eh
0x180003f7d  mov     edx, 14Bh; void *
0x180003f82  mov     r9d, r14d; char *
0x180003f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003f8a  jmp     loc_180004022
0x180003f8f  xorps   xmm0, xmm0
0x180003f92  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003f98  test    sil, 3
0x180003f9c  jnz     loc_180004140
0x180003fa2  mov     r9, rsi
0x180003fa5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003faa  shr     r9, 2; unsigned __int64
0x180003fae  lea     rcx, [rsp+280h+hObject]; this
0x180003fb3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003fb8  mov     r14d, eax
0x180003fbb  test    eax, eax
0x180003fbd  jns     loc_180004069
0x180003fc3  mov     rcx, [rbp+188h]; this
0x180003fca  lea     r8, aWil; "wil"
0x180003fd1  mov     r9d, eax; char *
0x180003fd4  mov     edx, 14Eh; void *
0x180003fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003fde  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003fe3  test    rcx, rcx
0x180003fe6  jz      short loc_180003FF6
0x180003fe8  call    cs:__imp_CloseHandle
0x180003fee  test    eax, eax
0x180003ff0  jz      loc_180004146
0x180003ff6  mov     rcx, [rsp+280h+hObject]; hObject
0x180003ffb  test    rcx, rcx
0x180003ffe  jz      short loc_18000400E
0x180004000  call    cs:__imp_CloseHandle
0x180004006  test    eax, eax
0x180004008  jz      loc_180004158
0x18000400e  call    cs:__imp_GetProcessHeap
0x180004014  mov     r8, rsi; lpMem
0x180004017  xor     edx, edx; dwFlags
0x180004019  mov     rcx, rax; hHeap
0x18000401c  call    cs:__imp_HeapFree
0x180004022  mov     rcx, [rbp+188h]; this
0x180004029  lea     r8, aWil; "wil"
0x180004030  mov     r9d, r14d; char *
0x180004033  mov     edx, 137h; void *
0x180004038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000403d  test    rdi, rdi
0x180004040  jz      short loc_180004053
0x180004042  mov     rcx, rdi; hMutex
0x180004045  call    cs:__imp_ReleaseMutex
0x18000404b  test    eax, eax
0x18000404d  jz      loc_18000416A
0x180004053  mov     rcx, rbx; hObject
0x180004056  call    cs:__imp_CloseHandle
0x18000405c  test    eax, eax
0x18000405e  jz      loc_18000417C
0x180004064  mov     eax, r14d
0x180004067  jmp     short loc_1800040D7
0x180004069  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x18000406e  xor     edx, edx; Val
0x180004070  mov     dword ptr [rsi], 1
0x180004076  lea     rcx, [rsi+22h]; void *
0x18000407a  mov     [rsi+8], rbx
0x18000407e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004083  lea     r8d, [rdx+56h]; Size
0x180004087  call    memset_0
0x18000408c  xor     edx, edx; Val
0x18000408e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004094  lea     rcx, [rsi+28h]; void *
0x180004098  mov     dword ptr [rsi+24h], 1
0x18000409f  lea     r8d, [rdx+50h]; Size
0x1800040a3  call    memset_0
0x1800040a8  xor     ebx, ebx
0x1800040aa  mov     [r15], rsi
0x1800040ad  test    rdi, rdi
0x1800040b0  jz      short loc_1800040C3
0x1800040b2  mov     rcx, rdi; hMutex
0x1800040b5  call    cs:__imp_ReleaseMutex
0x1800040bb  test    eax, eax
0x1800040bd  jz      loc_18000418E
0x1800040c3  test    rbx, rbx
0x1800040c6  jz      short loc_1800040D5
0x1800040c8  mov     rcx, rbx; hObject
0x1800040cb  call    cs:__imp_CloseHandle
0x1800040d1  test    eax, eax
0x1800040d3  jz      short loc_1800040FD
0x1800040d5  xor     eax, eax
0x1800040d7  mov     rcx, [rbp+180h+var_30]
0x1800040de  xor     rcx, rsp; StackCookie
0x1800040e1  call    __security_check_cookie
0x1800040e6  mov     rbx, [rsp+280h+arg_10]
0x1800040ee  add     rsp, 260h
0x1800040f5  pop     r15
0x1800040f7  pop     r14
0x1800040f9  pop     rdi
0x1800040fa  pop     rsi
0x1800040fb  pop     rbp
0x1800040fc  retn
0x1800040fd  mov     rcx, [rbp+188h]; this
0x180004104  mov     edx, 0A0Bh; void *
0x180004109  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000410f  mov     rcx, [rbp+188h]; this
0x180004116  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000411c  mov     rcx, [rbp+188h]; this
0x180004123  mov     edx, 0A15h; void *
0x180004128  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000412e  mov     rcx, [rbp+188h]; this
0x180004135  mov     edx, 0A0Bh; void *
0x18000413a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004140  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004146  mov     rcx, [rbp+188h]; this
0x18000414d  mov     edx, 0A0Bh; void *
0x180004152  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004158  mov     rcx, [rbp+188h]; this
0x18000415f  mov     edx, 0A0Bh; void *
0x180004164  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000416a  mov     rcx, [rbp+188h]; this
0x180004171  mov     edx, 0A15h; void *
0x180004176  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000417c  mov     rcx, [rbp+188h]; this
0x180004183  mov     edx, 0A0Bh; void *
0x180004188  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000418e  mov     rcx, [rbp+188h]; this
0x180004195  mov     edx, 0A15h; void *
0x18000419a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
