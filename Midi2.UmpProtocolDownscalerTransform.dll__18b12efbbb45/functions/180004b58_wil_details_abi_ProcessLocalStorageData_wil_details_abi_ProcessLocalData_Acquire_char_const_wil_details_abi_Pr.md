# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004b58`
- end: `0x180004f20`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006a00`

## callees

- `0x180002e70`
- `0x180003a20`
- `0x180004b58`
- `0x180005ac0`
- `0x1800061ac`
- `0x180006798`
- `0x18000772c`
- `0x180008924`
- `0x180009364`
- `0x18000941c`
- `0x180009ac4`
- `0x180009ad4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004bf1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180004bf1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004dc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004c87`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004dc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004e35`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004bd0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004bd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004b91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004d80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004dd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004e4b`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x180004b58  mov     [rsp-8+arg_10], rbx
0x180004b5d  push    rbp
0x180004b5e  push    rsi
0x180004b5f  push    rdi
0x180004b60  push    r14
0x180004b62  push    r15
0x180004b64  lea     rbp, [rsp-160h]
0x180004b6c  sub     rsp, 260h
0x180004b73  mov     rax, cs:__security_cookie
0x180004b7a  xor     rax, rsp
0x180004b7d  mov     [rbp+180h+var_30], rax
0x180004b84  mov     r15, rdx
0x180004b87  mov     qword ptr [rdx], 0
0x180004b8e  mov     rbx, rcx
0x180004b91  call    cs:__imp_GetCurrentProcessId
0x180004b97  mov     r14d, 78h ; 'x'
0x180004b9d  mov     [rsp+280h+var_258], rbx
0x180004ba2  mov     r9d, eax
0x180004ba5  mov     [rsp+280h+var_260], r14d; int
0x180004baa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004bb1  mov     edx, 104h; unsigned __int64
0x180004bb6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004bbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004bc0  mov     r9d, 1F0001h; dwDesiredAccess
0x180004bc6  lea     rdx, [rsp+280h+Name]; lpName
0x180004bcb  xor     r8d, r8d; dwFlags
0x180004bce  xor     ecx, ecx; lpMutexAttributes
0x180004bd0  call    cs:__imp_CreateMutexExW
0x180004bd6  mov     rbx, rax
0x180004bd9  test    rax, rax
0x180004bdc  jnz     short loc_180004BE8
0x180004bde  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004be3  jmp     loc_180004E57
0x180004be8  xor     r8d, r8d; bAlertable
0x180004beb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004bee  mov     rcx, rbx; hHandle
0x180004bf1  call    cs:__imp_WaitForSingleObjectEx
0x180004bf7  cmp     eax, 102h
0x180004bfc  jz      short loc_180004C0E
0x180004bfe  test    eax, 0FFFFFF7Fh
0x180004c03  jnz     loc_180004E8F
0x180004c09  mov     rdi, rbx
0x180004c0c  jmp     short loc_180004C10
0x180004c0e  xor     edi, edi
0x180004c10  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180004c15  mov     [rsp+280h+hObject], 0
0x180004c1e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180004c23  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180004c28  mov     esi, eax
0x180004c2a  test    eax, eax
0x180004c2c  jns     short loc_180004CAD
0x180004c2e  mov     rcx, [rbp+188h]; this
0x180004c35  lea     r8, aWil; "wil"
0x180004c3c  mov     r9d, eax; char *
0x180004c3f  mov     edx, 66h ; 'f'; void *
0x180004c44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c49  mov     rcx, [rbp+188h]; this
0x180004c50  lea     r8, aWil; "wil"
0x180004c57  mov     r9d, esi; char *
0x180004c5a  mov     edx, 6Fh ; 'o'; void *
0x180004c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c64  mov     rcx, [rbp+188h]; this
0x180004c6b  lea     r8, aWil; "wil"
0x180004c72  mov     r9d, esi; char *
0x180004c75  mov     edx, 12Eh; void *
0x180004c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004c7f  test    rdi, rdi
0x180004c82  jz      short loc_180004C95
0x180004c84  mov     rcx, rdi; hMutex
0x180004c87  call    cs:__imp_ReleaseMutex
0x180004c8d  test    eax, eax
0x180004c8f  jz      loc_180004E9C
0x180004c95  mov     rcx, rbx; hObject
0x180004c98  call    cs:__imp_CloseHandle
0x180004c9e  test    eax, eax
0x180004ca0  jz      loc_180004EAE
0x180004ca6  mov     eax, esi
0x180004ca8  jmp     loc_180004E57
0x180004cad  mov     rax, [rsp+280h+hObject]
0x180004cb2  lea     rcx, ds:0[rax*4]
0x180004cba  test    rcx, rcx
0x180004cbd  jz      short loc_180004CCD
0x180004cbf  mov     [r15], rcx
0x180004cc2  mov     eax, [rcx]
0x180004cc4  inc     eax
0x180004cc6  mov     [rcx], eax
0x180004cc8  jmp     loc_180004E2D
0x180004ccd  mov     rdx, r14; dwBytes
0x180004cd0  mov     qword ptr [r15], 0
0x180004cd7  mov     ecx, 8; dwFlags
0x180004cdc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004ce1  mov     rsi, rax
0x180004ce4  test    rax, rax
0x180004ce7  jnz     short loc_180004D0F
0x180004ce9  mov     rcx, [rbp+188h]; this
0x180004cf0  lea     r8, aWil; "wil"
0x180004cf7  mov     r14d, 8007000Eh
0x180004cfd  mov     edx, 14Bh; void *
0x180004d02  mov     r9d, r14d; char *
0x180004d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d0a  jmp     loc_180004DA2
0x180004d0f  xorps   xmm0, xmm0
0x180004d12  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180004d18  test    sil, 3
0x180004d1c  jnz     loc_180004EC0
0x180004d22  mov     r9, rsi
0x180004d25  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180004d2a  shr     r9, 2; unsigned __int64
0x180004d2e  lea     rcx, [rsp+280h+hObject]; this
0x180004d33  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180004d38  mov     r14d, eax
0x180004d3b  test    eax, eax
0x180004d3d  jns     loc_180004DE9
0x180004d43  mov     rcx, [rbp+188h]; this
0x180004d4a  lea     r8, aWil; "wil"
0x180004d51  mov     r9d, eax; char *
0x180004d54  mov     edx, 14Eh; void *
0x180004d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004d5e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180004d63  test    rcx, rcx
0x180004d66  jz      short loc_180004D76
0x180004d68  call    cs:__imp_CloseHandle
0x180004d6e  test    eax, eax
0x180004d70  jz      loc_180004EC6
0x180004d76  mov     rcx, [rsp+280h+hObject]; hObject
0x180004d7b  test    rcx, rcx
0x180004d7e  jz      short loc_180004D8E
0x180004d80  call    cs:__imp_CloseHandle
0x180004d86  test    eax, eax
0x180004d88  jz      loc_180004ED8
0x180004d8e  call    cs:__imp_GetProcessHeap
0x180004d94  mov     r8, rsi; lpMem
0x180004d97  xor     edx, edx; dwFlags
0x180004d99  mov     rcx, rax; hHeap
0x180004d9c  call    cs:__imp_HeapFree
0x180004da2  mov     rcx, [rbp+188h]; this
0x180004da9  lea     r8, aWil; "wil"
0x180004db0  mov     r9d, r14d; char *
0x180004db3  mov     edx, 137h; void *
0x180004db8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dbd  test    rdi, rdi
0x180004dc0  jz      short loc_180004DD3
0x180004dc2  mov     rcx, rdi; hMutex
0x180004dc5  call    cs:__imp_ReleaseMutex
0x180004dcb  test    eax, eax
0x180004dcd  jz      loc_180004EEA
0x180004dd3  mov     rcx, rbx; hObject
0x180004dd6  call    cs:__imp_CloseHandle
0x180004ddc  test    eax, eax
0x180004dde  jz      loc_180004EFC
0x180004de4  mov     eax, r14d
0x180004de7  jmp     short loc_180004E57
0x180004de9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180004dee  xor     edx, edx; Val
0x180004df0  mov     dword ptr [rsi], 1
0x180004df6  lea     rcx, [rsi+22h]; void *
0x180004dfa  mov     [rsi+8], rbx
0x180004dfe  movdqu  xmmword ptr [rsi+10h], xmm0
0x180004e03  lea     r8d, [rdx+56h]; Size
0x180004e07  call    memset_0
0x180004e0c  xor     edx, edx; Val
0x180004e0e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180004e14  lea     rcx, [rsi+28h]; void *
0x180004e18  mov     dword ptr [rsi+24h], 1
0x180004e1f  lea     r8d, [rdx+50h]; Size
0x180004e23  call    memset_0
0x180004e28  xor     ebx, ebx
0x180004e2a  mov     [r15], rsi
0x180004e2d  test    rdi, rdi
0x180004e30  jz      short loc_180004E43
0x180004e32  mov     rcx, rdi; hMutex
0x180004e35  call    cs:__imp_ReleaseMutex
0x180004e3b  test    eax, eax
0x180004e3d  jz      loc_180004F0E
0x180004e43  test    rbx, rbx
0x180004e46  jz      short loc_180004E55
0x180004e48  mov     rcx, rbx; hObject
0x180004e4b  call    cs:__imp_CloseHandle
0x180004e51  test    eax, eax
0x180004e53  jz      short loc_180004E7D
0x180004e55  xor     eax, eax
0x180004e57  mov     rcx, [rbp+180h+var_30]
0x180004e5e  xor     rcx, rsp; StackCookie
0x180004e61  call    __security_check_cookie
0x180004e66  mov     rbx, [rsp+280h+arg_10]
0x180004e6e  add     rsp, 260h
0x180004e75  pop     r15
0x180004e77  pop     r14
0x180004e79  pop     rdi
0x180004e7a  pop     rsi
0x180004e7b  pop     rbp
0x180004e7c  retn
0x180004e7d  mov     rcx, [rbp+188h]; this
0x180004e84  mov     edx, 0A0Bh; void *
0x180004e89  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004e8f  mov     rcx, [rbp+188h]; this
0x180004e96  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004e9c  mov     rcx, [rbp+188h]; this
0x180004ea3  mov     edx, 0A15h; void *
0x180004ea8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004eae  mov     rcx, [rbp+188h]; this
0x180004eb5  mov     edx, 0A0Bh; void *
0x180004eba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ec0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004ec6  mov     rcx, [rbp+188h]; this
0x180004ecd  mov     edx, 0A0Bh; void *
0x180004ed2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004ed8  mov     rcx, [rbp+188h]; this
0x180004edf  mov     edx, 0A0Bh; void *
0x180004ee4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004eea  mov     rcx, [rbp+188h]; this
0x180004ef1  mov     edx, 0A15h; void *
0x180004ef6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004efc  mov     rcx, [rbp+188h]; this
0x180004f03  mov     edx, 0A0Bh; void *
0x180004f08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004f0e  mov     rcx, [rbp+188h]; this
0x180004f15  mov     edx, 0A15h; void *
0x180004f1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
