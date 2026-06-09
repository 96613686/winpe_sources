# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400049d0`
- end: `0x140004d98`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400058fc`

## callees

- `0x14000195f`
- `0x1400049d0`
- `0x140004da0`
- `0x140004fe0`
- `0x140005698`
- `0x140006054`
- `0x140006314`
- `0x140006674`
- `0x140006700`
- `0x140006abc`
- `0x140006acc`
- `0x140006b90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140004b10`
- `KERNEL32!CloseHandle` at `0x140004be0`
- `KERNEL32!CloseHandle` at `0x140004bf8`
- `KERNEL32!CloseHandle` at `0x140004c4e`
- `KERNEL32!CloseHandle` at `0x140004cc3`
- `KERNEL32!CloseHandle` at `0x140004b10`
- `KERNEL32!CloseHandle` at `0x140004be0`
- `KERNEL32!CloseHandle` at `0x140004bf8`
- `KERNEL32!CloseHandle` at `0x140004c4e`
- `KERNEL32!CloseHandle` at `0x140004cc3`
- `KERNEL32!GetCurrentProcessId` at `0x140004a09`
- `KERNEL32!GetCurrentProcessId` at `0x140004a09`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004a69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140004a69`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004a48`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140004a48`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004aff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004c3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004cad`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004aff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004c3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004cad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004c14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004c14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004c06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004c06`

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
0x1400049d0  mov     [rsp-8+arg_10], rbx
0x1400049d5  push    rbp
0x1400049d6  push    rsi
0x1400049d7  push    rdi
0x1400049d8  push    r14
0x1400049da  push    r15
0x1400049dc  lea     rbp, [rsp-160h]
0x1400049e4  sub     rsp, 260h
0x1400049eb  mov     rax, cs:__security_cookie
0x1400049f2  xor     rax, rsp
0x1400049f5  mov     [rbp+180h+var_30], rax
0x1400049fc  mov     r15, rdx
0x1400049ff  mov     qword ptr [rdx], 0
0x140004a06  mov     rbx, rcx
0x140004a09  call    cs:__imp_GetCurrentProcessId
0x140004a0f  mov     r14d, 78h ; 'x'
0x140004a15  mov     [rsp+280h+var_258], rbx
0x140004a1a  mov     r9d, eax
0x140004a1d  mov     [rsp+280h+var_260], r14d; int
0x140004a22  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004a29  mov     edx, 104h; unsigned __int64
0x140004a2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004a33  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004a38  mov     r9d, 1F0001h; dwDesiredAccess
0x140004a3e  lea     rdx, [rsp+280h+Name]; lpName
0x140004a43  xor     r8d, r8d; dwFlags
0x140004a46  xor     ecx, ecx; lpMutexAttributes
0x140004a48  call    cs:__imp_CreateMutexExW
0x140004a4e  mov     rbx, rax
0x140004a51  test    rax, rax
0x140004a54  jnz     short loc_140004A60
0x140004a56  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004a5b  jmp     loc_140004CCF
0x140004a60  xor     r8d, r8d; bAlertable
0x140004a63  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004a66  mov     rcx, rbx; hHandle
0x140004a69  call    cs:__imp_WaitForSingleObjectEx
0x140004a6f  cmp     eax, 102h
0x140004a74  jz      short loc_140004A86
0x140004a76  test    eax, 0FFFFFF7Fh
0x140004a7b  jnz     loc_140004D07
0x140004a81  mov     rdi, rbx
0x140004a84  jmp     short loc_140004A88
0x140004a86  xor     edi, edi
0x140004a88  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140004a8d  mov     [rsp+280h+hObject], 0
0x140004a96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004a9b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004aa0  mov     esi, eax
0x140004aa2  test    eax, eax
0x140004aa4  jns     short loc_140004B25
0x140004aa6  mov     rcx, [rbp+188h]; this
0x140004aad  lea     r8, aWil; "wil"
0x140004ab4  mov     r9d, eax; char *
0x140004ab7  mov     edx, 66h ; 'f'; void *
0x140004abc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004ac1  mov     rcx, [rbp+188h]; this
0x140004ac8  lea     r8, aWil; "wil"
0x140004acf  mov     r9d, esi; char *
0x140004ad2  mov     edx, 6Fh ; 'o'; void *
0x140004ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004adc  mov     rcx, [rbp+188h]; this
0x140004ae3  lea     r8, aWil; "wil"
0x140004aea  mov     r9d, esi; char *
0x140004aed  mov     edx, 12Eh; void *
0x140004af2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004af7  test    rdi, rdi
0x140004afa  jz      short loc_140004B0D
0x140004afc  mov     rcx, rdi; hMutex
0x140004aff  call    cs:__imp_ReleaseMutex
0x140004b05  test    eax, eax
0x140004b07  jz      loc_140004D14
0x140004b0d  mov     rcx, rbx; hObject
0x140004b10  call    cs:__imp_CloseHandle
0x140004b16  test    eax, eax
0x140004b18  jz      loc_140004D26
0x140004b1e  mov     eax, esi
0x140004b20  jmp     loc_140004CCF
0x140004b25  mov     rax, [rsp+280h+hObject]
0x140004b2a  lea     rcx, ds:0[rax*4]
0x140004b32  test    rcx, rcx
0x140004b35  jz      short loc_140004B45
0x140004b37  mov     [r15], rcx
0x140004b3a  mov     eax, [rcx]
0x140004b3c  inc     eax
0x140004b3e  mov     [rcx], eax
0x140004b40  jmp     loc_140004CA5
0x140004b45  mov     rdx, r14; dwBytes
0x140004b48  mov     qword ptr [r15], 0
0x140004b4f  mov     ecx, 8; dwFlags
0x140004b54  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004b59  mov     rsi, rax
0x140004b5c  test    rax, rax
0x140004b5f  jnz     short loc_140004B87
0x140004b61  mov     rcx, [rbp+188h]; this
0x140004b68  lea     r8, aWil; "wil"
0x140004b6f  mov     r14d, 8007000Eh
0x140004b75  mov     edx, 14Bh; void *
0x140004b7a  mov     r9d, r14d; char *
0x140004b7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004b82  jmp     loc_140004C1A
0x140004b87  xorps   xmm0, xmm0
0x140004b8a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140004b90  test    sil, 3
0x140004b94  jnz     loc_140004D38
0x140004b9a  mov     r9, rsi
0x140004b9d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004ba2  shr     r9, 2; unsigned __int64
0x140004ba6  lea     rcx, [rsp+280h+hObject]; this
0x140004bab  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140004bb0  mov     r14d, eax
0x140004bb3  test    eax, eax
0x140004bb5  jns     loc_140004C61
0x140004bbb  mov     rcx, [rbp+188h]; this
0x140004bc2  lea     r8, aWil; "wil"
0x140004bc9  mov     r9d, eax; char *
0x140004bcc  mov     edx, 14Eh; void *
0x140004bd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004bd6  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140004bdb  test    rcx, rcx
0x140004bde  jz      short loc_140004BEE
0x140004be0  call    cs:__imp_CloseHandle
0x140004be6  test    eax, eax
0x140004be8  jz      loc_140004D3E
0x140004bee  mov     rcx, [rsp+280h+hObject]; hObject
0x140004bf3  test    rcx, rcx
0x140004bf6  jz      short loc_140004C06
0x140004bf8  call    cs:__imp_CloseHandle
0x140004bfe  test    eax, eax
0x140004c00  jz      loc_140004D50
0x140004c06  call    cs:__imp_GetProcessHeap
0x140004c0c  mov     r8, rsi; lpMem
0x140004c0f  xor     edx, edx; dwFlags
0x140004c11  mov     rcx, rax; hHeap
0x140004c14  call    cs:__imp_HeapFree
0x140004c1a  mov     rcx, [rbp+188h]; this
0x140004c21  lea     r8, aWil; "wil"
0x140004c28  mov     r9d, r14d; char *
0x140004c2b  mov     edx, 137h; void *
0x140004c30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004c35  test    rdi, rdi
0x140004c38  jz      short loc_140004C4B
0x140004c3a  mov     rcx, rdi; hMutex
0x140004c3d  call    cs:__imp_ReleaseMutex
0x140004c43  test    eax, eax
0x140004c45  jz      loc_140004D62
0x140004c4b  mov     rcx, rbx; hObject
0x140004c4e  call    cs:__imp_CloseHandle
0x140004c54  test    eax, eax
0x140004c56  jz      loc_140004D74
0x140004c5c  mov     eax, r14d
0x140004c5f  jmp     short loc_140004CCF
0x140004c61  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140004c66  xor     edx, edx; Val
0x140004c68  mov     dword ptr [rsi], 1
0x140004c6e  lea     rcx, [rsi+22h]; void *
0x140004c72  mov     [rsi+8], rbx
0x140004c76  movdqu  xmmword ptr [rsi+10h], xmm0
0x140004c7b  lea     r8d, [rdx+56h]; Size
0x140004c7f  call    memset_0
0x140004c84  xor     edx, edx; Val
0x140004c86  mov     word ptr [rsi+20h], 58h ; 'X'
0x140004c8c  lea     rcx, [rsi+28h]; void *
0x140004c90  mov     dword ptr [rsi+24h], 1
0x140004c97  lea     r8d, [rdx+50h]; Size
0x140004c9b  call    memset_0
0x140004ca0  xor     ebx, ebx
0x140004ca2  mov     [r15], rsi
0x140004ca5  test    rdi, rdi
0x140004ca8  jz      short loc_140004CBB
0x140004caa  mov     rcx, rdi; hMutex
0x140004cad  call    cs:__imp_ReleaseMutex
0x140004cb3  test    eax, eax
0x140004cb5  jz      loc_140004D86
0x140004cbb  test    rbx, rbx
0x140004cbe  jz      short loc_140004CCD
0x140004cc0  mov     rcx, rbx; hObject
0x140004cc3  call    cs:__imp_CloseHandle
0x140004cc9  test    eax, eax
0x140004ccb  jz      short loc_140004CF5
0x140004ccd  xor     eax, eax
0x140004ccf  mov     rcx, [rbp+180h+var_30]
0x140004cd6  xor     rcx, rsp; StackCookie
0x140004cd9  call    __security_check_cookie
0x140004cde  mov     rbx, [rsp+280h+arg_10]
0x140004ce6  add     rsp, 260h
0x140004ced  pop     r15
0x140004cef  pop     r14
0x140004cf1  pop     rdi
0x140004cf2  pop     rsi
0x140004cf3  pop     rbp
0x140004cf4  retn
0x140004cf5  mov     rcx, [rbp+188h]; this
0x140004cfc  mov     edx, 0A0Bh; void *
0x140004d01  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d07  mov     rcx, [rbp+188h]; this
0x140004d0e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004d14  mov     rcx, [rbp+188h]; this
0x140004d1b  mov     edx, 0A15h; void *
0x140004d20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d26  mov     rcx, [rbp+188h]; this
0x140004d2d  mov     edx, 0A0Bh; void *
0x140004d32  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004d3e  mov     rcx, [rbp+188h]; this
0x140004d45  mov     edx, 0A0Bh; void *
0x140004d4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d50  mov     rcx, [rbp+188h]; this
0x140004d57  mov     edx, 0A0Bh; void *
0x140004d5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d62  mov     rcx, [rbp+188h]; this
0x140004d69  mov     edx, 0A15h; void *
0x140004d6e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d74  mov     rcx, [rbp+188h]; this
0x140004d7b  mov     edx, 0A0Bh; void *
0x140004d80  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004d86  mov     rcx, [rbp+188h]; this
0x140004d8d  mov     edx, 0A15h; void *
0x140004d92  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
