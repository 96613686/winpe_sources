# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003a38`
- end: `0x140003e00`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140004900`

## callees

- `0x140002120`
- `0x140002c58`
- `0x140003a38`
- `0x140003e08`
- `0x140004050`
- `0x140004698`
- `0x140005178`
- `0x140005454`
- `0x140005de0`
- `0x140005ebc`
- `0x14000629c`
- `0x1400062ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003ca5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003d15`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003b67`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003ca5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140003d15`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003ab0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140003ab0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003ad1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003cb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003cb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003d2b`

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
0x140003a38  mov     [rsp-8+arg_10], rbx
0x140003a3d  push    rbp
0x140003a3e  push    rsi
0x140003a3f  push    rdi
0x140003a40  push    r14
0x140003a42  push    r15
0x140003a44  lea     rbp, [rsp-160h]
0x140003a4c  sub     rsp, 260h
0x140003a53  mov     rax, cs:__security_cookie
0x140003a5a  xor     rax, rsp
0x140003a5d  mov     [rbp+180h+var_30], rax
0x140003a64  mov     r15, rdx
0x140003a67  mov     qword ptr [rdx], 0
0x140003a6e  mov     rbx, rcx
0x140003a71  call    cs:__imp_GetCurrentProcessId
0x140003a77  mov     r14d, 78h ; 'x'
0x140003a7d  mov     [rsp+280h+var_258], rbx
0x140003a82  mov     r9d, eax
0x140003a85  mov     [rsp+280h+var_260], r14d; int
0x140003a8a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140003a91  mov     edx, 104h; unsigned __int64
0x140003a96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003a9b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003aa0  mov     r9d, 1F0001h; dwDesiredAccess
0x140003aa6  lea     rdx, [rsp+280h+Name]; lpName
0x140003aab  xor     r8d, r8d; dwFlags
0x140003aae  xor     ecx, ecx; lpMutexAttributes
0x140003ab0  call    cs:__imp_CreateMutexExW
0x140003ab6  mov     rbx, rax
0x140003ab9  test    rax, rax
0x140003abc  jnz     short loc_140003AC8
0x140003abe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140003ac3  jmp     loc_140003D37
0x140003ac8  xor     r8d, r8d; bAlertable
0x140003acb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003ace  mov     rcx, rbx; hHandle
0x140003ad1  call    cs:__imp_WaitForSingleObjectEx
0x140003ad7  cmp     eax, 102h
0x140003adc  jz      short loc_140003AEE
0x140003ade  test    eax, 0FFFFFF7Fh
0x140003ae3  jnz     loc_140003D6F
0x140003ae9  mov     rdi, rbx
0x140003aec  jmp     short loc_140003AF0
0x140003aee  xor     edi, edi
0x140003af0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003af5  mov     [rsp+280h+hObject], 0
0x140003afe  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003b03  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003b08  mov     esi, eax
0x140003b0a  test    eax, eax
0x140003b0c  jns     short loc_140003B8D
0x140003b0e  mov     rcx, [rbp+188h]; this
0x140003b15  lea     r8, aWil; "wil"
0x140003b1c  mov     r9d, eax; char *
0x140003b1f  mov     edx, 66h ; 'f'; void *
0x140003b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b29  mov     rcx, [rbp+188h]; this
0x140003b30  lea     r8, aWil; "wil"
0x140003b37  mov     r9d, esi; char *
0x140003b3a  mov     edx, 6Fh ; 'o'; void *
0x140003b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b44  mov     rcx, [rbp+188h]; this
0x140003b4b  lea     r8, aWil; "wil"
0x140003b52  mov     r9d, esi; char *
0x140003b55  mov     edx, 12Eh; void *
0x140003b5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b5f  test    rdi, rdi
0x140003b62  jz      short loc_140003B75
0x140003b64  mov     rcx, rdi; hMutex
0x140003b67  call    cs:__imp_ReleaseMutex
0x140003b6d  test    eax, eax
0x140003b6f  jz      loc_140003D7C
0x140003b75  mov     rcx, rbx; hObject
0x140003b78  call    cs:__imp_CloseHandle
0x140003b7e  test    eax, eax
0x140003b80  jz      loc_140003D8E
0x140003b86  mov     eax, esi
0x140003b88  jmp     loc_140003D37
0x140003b8d  mov     rax, [rsp+280h+hObject]
0x140003b92  lea     rcx, ds:0[rax*4]
0x140003b9a  test    rcx, rcx
0x140003b9d  jz      short loc_140003BAD
0x140003b9f  mov     [r15], rcx
0x140003ba2  mov     eax, [rcx]
0x140003ba4  inc     eax
0x140003ba6  mov     [rcx], eax
0x140003ba8  jmp     loc_140003D0D
0x140003bad  mov     rdx, r14; dwBytes
0x140003bb0  mov     qword ptr [r15], 0
0x140003bb7  mov     ecx, 8; dwFlags
0x140003bbc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003bc1  mov     rsi, rax
0x140003bc4  test    rax, rax
0x140003bc7  jnz     short loc_140003BEF
0x140003bc9  mov     rcx, [rbp+188h]; this
0x140003bd0  lea     r8, aWil; "wil"
0x140003bd7  mov     r14d, 8007000Eh
0x140003bdd  mov     edx, 14Bh; void *
0x140003be2  mov     r9d, r14d; char *
0x140003be5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003bea  jmp     loc_140003C82
0x140003bef  xorps   xmm0, xmm0
0x140003bf2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003bf8  test    sil, 3
0x140003bfc  jnz     loc_140003DA0
0x140003c02  mov     r9, rsi
0x140003c05  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003c0a  shr     r9, 2; unsigned __int64
0x140003c0e  lea     rcx, [rsp+280h+hObject]; this
0x140003c13  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003c18  mov     r14d, eax
0x140003c1b  test    eax, eax
0x140003c1d  jns     loc_140003CC9
0x140003c23  mov     rcx, [rbp+188h]; this
0x140003c2a  lea     r8, aWil; "wil"
0x140003c31  mov     r9d, eax; char *
0x140003c34  mov     edx, 14Eh; void *
0x140003c39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003c3e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003c43  test    rcx, rcx
0x140003c46  jz      short loc_140003C56
0x140003c48  call    cs:__imp_CloseHandle
0x140003c4e  test    eax, eax
0x140003c50  jz      loc_140003DA6
0x140003c56  mov     rcx, [rsp+280h+hObject]; hObject
0x140003c5b  test    rcx, rcx
0x140003c5e  jz      short loc_140003C6E
0x140003c60  call    cs:__imp_CloseHandle
0x140003c66  test    eax, eax
0x140003c68  jz      loc_140003DB8
0x140003c6e  call    cs:__imp_GetProcessHeap
0x140003c74  mov     r8, rsi; lpMem
0x140003c77  xor     edx, edx; dwFlags
0x140003c79  mov     rcx, rax; hHeap
0x140003c7c  call    cs:__imp_HeapFree
0x140003c82  mov     rcx, [rbp+188h]; this
0x140003c89  lea     r8, aWil; "wil"
0x140003c90  mov     r9d, r14d; char *
0x140003c93  mov     edx, 137h; void *
0x140003c98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003c9d  test    rdi, rdi
0x140003ca0  jz      short loc_140003CB3
0x140003ca2  mov     rcx, rdi; hMutex
0x140003ca5  call    cs:__imp_ReleaseMutex
0x140003cab  test    eax, eax
0x140003cad  jz      loc_140003DCA
0x140003cb3  mov     rcx, rbx; hObject
0x140003cb6  call    cs:__imp_CloseHandle
0x140003cbc  test    eax, eax
0x140003cbe  jz      loc_140003DDC
0x140003cc4  mov     eax, r14d
0x140003cc7  jmp     short loc_140003D37
0x140003cc9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003cce  xor     edx, edx; Val
0x140003cd0  mov     dword ptr [rsi], 1
0x140003cd6  lea     rcx, [rsi+22h]; void *
0x140003cda  mov     [rsi+8], rbx
0x140003cde  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003ce3  lea     r8d, [rdx+56h]; Size
0x140003ce7  call    memset_0
0x140003cec  xor     edx, edx; Val
0x140003cee  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003cf4  lea     rcx, [rsi+28h]; void *
0x140003cf8  mov     dword ptr [rsi+24h], 1
0x140003cff  lea     r8d, [rdx+50h]; Size
0x140003d03  call    memset_0
0x140003d08  xor     ebx, ebx
0x140003d0a  mov     [r15], rsi
0x140003d0d  test    rdi, rdi
0x140003d10  jz      short loc_140003D23
0x140003d12  mov     rcx, rdi; hMutex
0x140003d15  call    cs:__imp_ReleaseMutex
0x140003d1b  test    eax, eax
0x140003d1d  jz      loc_140003DEE
0x140003d23  test    rbx, rbx
0x140003d26  jz      short loc_140003D35
0x140003d28  mov     rcx, rbx; hObject
0x140003d2b  call    cs:__imp_CloseHandle
0x140003d31  test    eax, eax
0x140003d33  jz      short loc_140003D5D
0x140003d35  xor     eax, eax
0x140003d37  mov     rcx, [rbp+180h+var_30]
0x140003d3e  xor     rcx, rsp; StackCookie
0x140003d41  call    __security_check_cookie
0x140003d46  mov     rbx, [rsp+280h+arg_10]
0x140003d4e  add     rsp, 260h
0x140003d55  pop     r15
0x140003d57  pop     r14
0x140003d59  pop     rdi
0x140003d5a  pop     rsi
0x140003d5b  pop     rbp
0x140003d5c  retn
0x140003d5d  mov     rcx, [rbp+188h]; this
0x140003d64  mov     edx, 0A0Bh; void *
0x140003d69  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d6f  mov     rcx, [rbp+188h]; this
0x140003d76  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003d7c  mov     rcx, [rbp+188h]; this
0x140003d83  mov     edx, 0A15h; void *
0x140003d88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d8e  mov     rcx, [rbp+188h]; this
0x140003d95  mov     edx, 0A0Bh; void *
0x140003d9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003da0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003da6  mov     rcx, [rbp+188h]; this
0x140003dad  mov     edx, 0A0Bh; void *
0x140003db2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003db8  mov     rcx, [rbp+188h]; this
0x140003dbf  mov     edx, 0A0Bh; void *
0x140003dc4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003dca  mov     rcx, [rbp+188h]; this
0x140003dd1  mov     edx, 0A15h; void *
0x140003dd6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003ddc  mov     rcx, [rbp+188h]; this
0x140003de3  mov     edx, 0A0Bh; void *
0x140003de8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003dee  mov     rcx, [rbp+188h]; this
0x140003df5  mov     edx, 0A15h; void *
0x140003dfa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
