# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140008ae8`
- end: `0x140008ed9`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400091c4`

## callees

- `0x1400015d0`
- `0x14000202c`
- `0x140006670`
- `0x140006bec`
- `0x140006e3c`
- `0x140007dac`
- `0x140008ae8`
- `0x140008ee0`
- `0x140009354`
- `0x140009924`
- `0x14000bbd8`
- `0x14000bf1c`
- `0x14000c620`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140008c27`
- `KERNEL32!CloseHandle` at `0x140008cf5`
- `KERNEL32!CloseHandle` at `0x140008d0d`
- `KERNEL32!CloseHandle` at `0x140008d63`
- `KERNEL32!CloseHandle` at `0x140008e04`
- `KERNEL32!CloseHandle` at `0x140008c27`
- `KERNEL32!CloseHandle` at `0x140008cf5`
- `KERNEL32!CloseHandle` at `0x140008d0d`
- `KERNEL32!CloseHandle` at `0x140008d63`
- `KERNEL32!CloseHandle` at `0x140008e04`
- `KERNEL32!GetCurrentProcessId` at `0x140008b21`
- `KERNEL32!GetCurrentProcessId` at `0x140008b21`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008c16`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008d52`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008dee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008c16`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008d52`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140008dee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140008dbb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140008dbb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008b5f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140008b5f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008b80`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140008b80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008d1b`

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
0x140008ae8  mov     [rsp-8+arg_10], rbx
0x140008aed  push    rbp
0x140008aee  push    rsi
0x140008aef  push    rdi
0x140008af0  push    r14
0x140008af2  push    r15
0x140008af4  lea     rbp, [rsp-160h]
0x140008afc  sub     rsp, 260h
0x140008b03  mov     rax, cs:__security_cookie
0x140008b0a  xor     rax, rsp
0x140008b0d  mov     [rbp+180h+var_30], rax
0x140008b14  mov     r15, rdx
0x140008b17  mov     qword ptr [rdx], 0
0x140008b1e  mov     rbx, rcx
0x140008b21  call    cs:__imp_GetCurrentProcessId
0x140008b27  mov     r14d, 130h
0x140008b2d  mov     [rsp+280h+var_258], rbx
0x140008b32  mov     r9d, eax
0x140008b35  mov     [rsp+280h+var_260], r14d; int
0x140008b3a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140008b41  lea     rcx, [rsp+280h+Name]; Buffer
0x140008b46  lea     edx, [r14-2Ch]; unsigned __int64
0x140008b4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008b4f  mov     r9d, 1F0001h; dwDesiredAccess
0x140008b55  lea     rdx, [rsp+280h+Name]; lpName
0x140008b5a  xor     r8d, r8d; dwFlags
0x140008b5d  xor     ecx, ecx; lpMutexAttributes
0x140008b5f  call    cs:__imp_CreateMutexExW
0x140008b65  mov     rbx, rax
0x140008b68  test    rax, rax
0x140008b6b  jnz     short loc_140008B77
0x140008b6d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140008b72  jmp     loc_140008E10
0x140008b77  xor     r8d, r8d; bAlertable
0x140008b7a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140008b7d  mov     rcx, rbx; hHandle
0x140008b80  call    cs:__imp_WaitForSingleObjectEx
0x140008b86  cmp     eax, 102h
0x140008b8b  jz      short loc_140008B9D
0x140008b8d  test    eax, 0FFFFFF7Fh
0x140008b92  jnz     loc_140008E5A
0x140008b98  mov     rdi, rbx
0x140008b9b  jmp     short loc_140008B9F
0x140008b9d  xor     edi, edi
0x140008b9f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140008ba4  mov     [rsp+280h+hObject], 0
0x140008bad  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008bb2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140008bb7  mov     esi, eax
0x140008bb9  test    eax, eax
0x140008bbb  jns     short loc_140008C3C
0x140008bbd  mov     rcx, [rbp+188h]; this
0x140008bc4  lea     r8, aWil; "wil"
0x140008bcb  mov     r9d, eax; char *
0x140008bce  mov     edx, 66h ; 'f'; void *
0x140008bd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008bd8  mov     rcx, [rbp+188h]; this
0x140008bdf  lea     r8, aWil; "wil"
0x140008be6  mov     r9d, esi; char *
0x140008be9  mov     edx, 6Fh ; 'o'; void *
0x140008bee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008bf3  mov     rcx, [rbp+188h]; this
0x140008bfa  lea     r8, aWil; "wil"
0x140008c01  mov     r9d, esi; char *
0x140008c04  mov     edx, 12Eh; void *
0x140008c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008c0e  test    rdi, rdi
0x140008c11  jz      short loc_140008C24
0x140008c13  mov     rcx, rdi; hMutex
0x140008c16  call    cs:__imp_ReleaseMutex
0x140008c1c  test    eax, eax
0x140008c1e  jz      loc_140008E67
0x140008c24  mov     rcx, rbx; hObject
0x140008c27  call    cs:__imp_CloseHandle
0x140008c2d  test    eax, eax
0x140008c2f  jz      loc_140008E79
0x140008c35  mov     eax, esi
0x140008c37  jmp     loc_140008E10
0x140008c3c  mov     rax, [rsp+280h+hObject]
0x140008c41  lea     rcx, ds:0[rax*4]
0x140008c49  test    rcx, rcx
0x140008c4c  jz      short loc_140008C5C
0x140008c4e  mov     [r15], rcx
0x140008c51  mov     eax, [rcx]
0x140008c53  inc     eax
0x140008c55  mov     [rcx], eax
0x140008c57  jmp     loc_140008DE6
0x140008c5c  mov     rdx, r14; dwBytes
0x140008c5f  mov     qword ptr [r15], 0
0x140008c66  mov     ecx, 8; dwFlags
0x140008c6b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008c70  mov     r14, rax
0x140008c73  test    rax, rax
0x140008c76  jnz     short loc_140008C9D
0x140008c78  mov     rcx, [rbp+188h]; this
0x140008c7f  lea     r8, aWil; "wil"
0x140008c86  mov     esi, 8007000Eh
0x140008c8b  mov     edx, 14Bh; void *
0x140008c90  mov     r9d, esi; char *
0x140008c93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008c98  jmp     loc_140008D2F
0x140008c9d  xorps   xmm0, xmm0
0x140008ca0  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140008ca6  test    r14b, 3
0x140008caa  jnz     loc_140008E8B
0x140008cb0  mov     r9, r14
0x140008cb3  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140008cb8  shr     r9, 2; unsigned __int64
0x140008cbc  lea     rcx, [rsp+280h+hObject]; this
0x140008cc1  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140008cc6  mov     esi, eax
0x140008cc8  test    eax, eax
0x140008cca  jns     loc_140008D76
0x140008cd0  mov     rcx, [rbp+188h]; this
0x140008cd7  lea     r8, aWil; "wil"
0x140008cde  mov     r9d, eax; char *
0x140008ce1  mov     edx, 14Eh; void *
0x140008ce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008ceb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140008cf0  test    rcx, rcx
0x140008cf3  jz      short loc_140008D03
0x140008cf5  call    cs:__imp_CloseHandle
0x140008cfb  test    eax, eax
0x140008cfd  jz      loc_140008E91
0x140008d03  mov     rcx, [rsp+280h+hObject]; hObject
0x140008d08  test    rcx, rcx
0x140008d0b  jz      short loc_140008D1B
0x140008d0d  call    cs:__imp_CloseHandle
0x140008d13  test    eax, eax
0x140008d15  jz      loc_140008EA3
0x140008d1b  call    cs:__imp_GetProcessHeap
0x140008d21  mov     r8, r14; lpMem
0x140008d24  xor     edx, edx; dwFlags
0x140008d26  mov     rcx, rax; hHeap
0x140008d29  call    cs:__imp_HeapFree
0x140008d2f  mov     rcx, [rbp+188h]; this
0x140008d36  lea     r8, aWil; "wil"
0x140008d3d  mov     r9d, esi; char *
0x140008d40  mov     edx, 137h; void *
0x140008d45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008d4a  test    rdi, rdi
0x140008d4d  jz      short loc_140008D60
0x140008d4f  mov     rcx, rdi; hMutex
0x140008d52  call    cs:__imp_ReleaseMutex
0x140008d58  test    eax, eax
0x140008d5a  jz      loc_140008EB5
0x140008d60  mov     rcx, rbx; hObject
0x140008d63  call    cs:__imp_CloseHandle
0x140008d69  test    eax, eax
0x140008d6b  jz      loc_140008E48
0x140008d71  jmp     loc_140008C35
0x140008d76  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140008d7b  lea     rcx, [r14+28h]; void *
0x140008d7f  mov     dword ptr [r14], 1
0x140008d86  xor     edx, edx; Val
0x140008d88  mov     [r14+8], rbx
0x140008d8c  mov     r8d, 108h; Size
0x140008d92  movdqu  xmmword ptr [r14+10h], xmm0
0x140008d98  call    memset_0
0x140008d9d  xor     eax, eax
0x140008d9f  lea     rcx, [r14+28h]; this
0x140008da3  mov     [r14+20h], rax
0x140008da7  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140008dac  lea     rbx, [r14+0E8h]
0x140008db3  xor     r8d, r8d; Flags
0x140008db6  mov     rcx, rbx; lpCriticalSection
0x140008db9  xor     edx, edx; dwSpinCount
0x140008dbb  call    cs:__imp_InitializeCriticalSectionEx
0x140008dc1  mov     qword ptr [rbx+28h], 0
0x140008dc9  mov     qword ptr [rbx+30h], 0
0x140008dd1  mov     qword ptr [rbx+38h], 0
0x140008dd9  mov     qword ptr [rbx+40h], 0
0x140008de1  xor     ebx, ebx
0x140008de3  mov     [r15], r14
0x140008de6  test    rdi, rdi
0x140008de9  jz      short loc_140008DFC
0x140008deb  mov     rcx, rdi; hMutex
0x140008dee  call    cs:__imp_ReleaseMutex
0x140008df4  test    eax, eax
0x140008df6  jz      loc_140008EC7
0x140008dfc  test    rbx, rbx
0x140008dff  jz      short loc_140008E0E
0x140008e01  mov     rcx, rbx; hObject
0x140008e04  call    cs:__imp_CloseHandle
0x140008e0a  test    eax, eax
0x140008e0c  jz      short loc_140008E36
0x140008e0e  xor     eax, eax
0x140008e10  mov     rcx, [rbp+180h+var_30]
0x140008e17  xor     rcx, rsp; StackCookie
0x140008e1a  call    __security_check_cookie
0x140008e1f  mov     rbx, [rsp+280h+arg_10]
0x140008e27  add     rsp, 260h
0x140008e2e  pop     r15
0x140008e30  pop     r14
0x140008e32  pop     rdi
0x140008e33  pop     rsi
0x140008e34  pop     rbp
0x140008e35  retn
0x140008e36  mov     rcx, [rbp+188h]; this
0x140008e3d  mov     edx, 0A0Bh; void *
0x140008e42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008e48  mov     rcx, [rbp+188h]; this
0x140008e4f  mov     edx, 0A0Bh; void *
0x140008e54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008e5a  mov     rcx, [rbp+188h]; this
0x140008e61  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140008e67  mov     rcx, [rbp+188h]; this
0x140008e6e  mov     edx, 0A15h; void *
0x140008e73  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008e79  mov     rcx, [rbp+188h]; this
0x140008e80  mov     edx, 0A0Bh; void *
0x140008e85  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008e8b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008e91  mov     rcx, [rbp+188h]; this
0x140008e98  mov     edx, 0A0Bh; void *
0x140008e9d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008ea3  mov     rcx, [rbp+188h]; this
0x140008eaa  mov     edx, 0A0Bh; void *
0x140008eaf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008eb5  mov     rcx, [rbp+188h]; this
0x140008ebc  mov     edx, 0A15h; void *
0x140008ec1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008ec7  mov     rcx, [rbp+188h]; this
0x140008ece  mov     edx, 0A15h; void *
0x140008ed3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
