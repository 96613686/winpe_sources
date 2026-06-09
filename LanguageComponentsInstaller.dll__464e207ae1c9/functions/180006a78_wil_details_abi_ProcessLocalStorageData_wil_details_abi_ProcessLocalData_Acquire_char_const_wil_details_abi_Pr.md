# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006a78`
- end: `0x180006e45`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180008394`

## callees

- `0x180003520`
- `0x180004118`
- `0x180006a78`
- `0x18000708c`
- `0x1800074c4`
- `0x180008088`
- `0x180008d74`
- `0x1800092a4`
- `0x180009c94`
- `0x180009d88`
- `0x18000a364`
- `0x18000a374`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006af0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006af0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006b11`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ba7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ce5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d55`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ba7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006ce5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180006d55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006cae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006ab1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d6b`

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
  bool v9; // dl
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
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xE01, v10, v11);
    v12 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
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
0x180006a78  mov     [rsp-8+arg_10], rbx
0x180006a7d  push    rbp
0x180006a7e  push    rsi
0x180006a7f  push    rdi
0x180006a80  push    r14
0x180006a82  push    r15
0x180006a84  lea     rbp, [rsp-160h]
0x180006a8c  sub     rsp, 260h
0x180006a93  mov     rax, cs:__security_cookie
0x180006a9a  xor     rax, rsp
0x180006a9d  mov     [rbp+180h+var_30], rax
0x180006aa4  mov     r15, rdx
0x180006aa7  mov     qword ptr [rdx], 0
0x180006aae  mov     rbx, rcx
0x180006ab1  call    cs:__imp_GetCurrentProcessId
0x180006ab7  mov     r14d, 78h ; 'x'
0x180006abd  mov     [rsp+280h+var_258], rbx
0x180006ac2  mov     r9d, eax
0x180006ac5  mov     [rsp+280h+var_260], r14d; int
0x180006aca  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006ad1  mov     edx, 104h; unsigned __int64
0x180006ad6  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006adb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006ae0  mov     r9d, 1F0001h; dwDesiredAccess
0x180006ae6  lea     rdx, [rsp+280h+Name]; lpName
0x180006aeb  xor     r8d, r8d; dwFlags
0x180006aee  xor     ecx, ecx; lpMutexAttributes
0x180006af0  call    cs:__imp_CreateMutexExW
0x180006af6  mov     rbx, rax
0x180006af9  test    rax, rax
0x180006afc  jnz     short loc_180006B08
0x180006afe  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006b03  jmp     loc_180006D77
0x180006b08  xor     r8d, r8d; bAlertable
0x180006b0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006b0e  mov     rcx, rbx; hHandle
0x180006b11  call    cs:__imp_WaitForSingleObjectEx
0x180006b17  cmp     eax, 102h
0x180006b1c  jz      short loc_180006B2E
0x180006b1e  test    eax, 0FFFFFF7Fh
0x180006b23  jnz     loc_180006DAF
0x180006b29  mov     rdi, rbx
0x180006b2c  jmp     short loc_180006B30
0x180006b2e  xor     edi, edi
0x180006b30  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006b35  mov     [rsp+280h+hObject], 0
0x180006b3e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006b43  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006b48  mov     esi, eax
0x180006b4a  test    eax, eax
0x180006b4c  jns     short loc_180006BCD
0x180006b4e  mov     rcx, [rbp+188h]; this
0x180006b55  lea     r8, aWil; "wil"
0x180006b5c  mov     r9d, eax; char *
0x180006b5f  mov     edx, 66h ; 'f'; void *
0x180006b64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b69  mov     rcx, [rbp+188h]; this
0x180006b70  lea     r8, aWil; "wil"
0x180006b77  mov     r9d, esi; char *
0x180006b7a  mov     edx, 6Fh ; 'o'; void *
0x180006b7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b84  mov     rcx, [rbp+188h]; this
0x180006b8b  lea     r8, aWil; "wil"
0x180006b92  mov     r9d, esi; char *
0x180006b95  mov     edx, 12Eh; void *
0x180006b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b9f  test    rdi, rdi
0x180006ba2  jz      short loc_180006BB5
0x180006ba4  mov     rcx, rdi; hMutex
0x180006ba7  call    cs:__imp_ReleaseMutex
0x180006bad  test    eax, eax
0x180006baf  jz      loc_180006DC1
0x180006bb5  mov     rcx, rbx; hObject
0x180006bb8  call    cs:__imp_CloseHandle
0x180006bbe  test    eax, eax
0x180006bc0  jz      loc_180006DD3
0x180006bc6  mov     eax, esi
0x180006bc8  jmp     loc_180006D77
0x180006bcd  mov     rax, [rsp+280h+hObject]
0x180006bd2  lea     rcx, ds:0[rax*4]
0x180006bda  test    rcx, rcx
0x180006bdd  jz      short loc_180006BED
0x180006bdf  mov     [r15], rcx
0x180006be2  mov     eax, [rcx]
0x180006be4  inc     eax
0x180006be6  mov     [rcx], eax
0x180006be8  jmp     loc_180006D4D
0x180006bed  mov     rdx, r14; dwBytes
0x180006bf0  mov     qword ptr [r15], 0
0x180006bf7  mov     ecx, 8; dwFlags
0x180006bfc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006c01  mov     rsi, rax
0x180006c04  test    rax, rax
0x180006c07  jnz     short loc_180006C2F
0x180006c09  mov     rcx, [rbp+188h]; this
0x180006c10  lea     r8, aWil; "wil"
0x180006c17  mov     r14d, 8007000Eh
0x180006c1d  mov     edx, 14Bh; void *
0x180006c22  mov     r9d, r14d; char *
0x180006c25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c2a  jmp     loc_180006CC2
0x180006c2f  xorps   xmm0, xmm0
0x180006c32  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180006c38  test    sil, 3
0x180006c3c  jnz     loc_180006DE5
0x180006c42  mov     r9, rsi
0x180006c45  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180006c4a  shr     r9, 2; unsigned __int64
0x180006c4e  lea     rcx, [rsp+280h+hObject]; this
0x180006c53  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180006c58  mov     r14d, eax
0x180006c5b  test    eax, eax
0x180006c5d  jns     loc_180006D09
0x180006c63  mov     rcx, [rbp+188h]; this
0x180006c6a  lea     r8, aWil; "wil"
0x180006c71  mov     r9d, eax; char *
0x180006c74  mov     edx, 14Eh; void *
0x180006c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c7e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006c83  test    rcx, rcx
0x180006c86  jz      short loc_180006C96
0x180006c88  call    cs:__imp_CloseHandle
0x180006c8e  test    eax, eax
0x180006c90  jz      loc_180006DEB
0x180006c96  mov     rcx, [rsp+280h+hObject]; hObject
0x180006c9b  test    rcx, rcx
0x180006c9e  jz      short loc_180006CAE
0x180006ca0  call    cs:__imp_CloseHandle
0x180006ca6  test    eax, eax
0x180006ca8  jz      loc_180006DFD
0x180006cae  call    cs:__imp_GetProcessHeap
0x180006cb4  mov     r8, rsi; lpMem
0x180006cb7  xor     edx, edx; dwFlags
0x180006cb9  mov     rcx, rax; hHeap
0x180006cbc  call    cs:__imp_HeapFree
0x180006cc2  mov     rcx, [rbp+188h]; this
0x180006cc9  lea     r8, aWil; "wil"
0x180006cd0  mov     r9d, r14d; char *
0x180006cd3  mov     edx, 137h; void *
0x180006cd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cdd  test    rdi, rdi
0x180006ce0  jz      short loc_180006CF3
0x180006ce2  mov     rcx, rdi; hMutex
0x180006ce5  call    cs:__imp_ReleaseMutex
0x180006ceb  test    eax, eax
0x180006ced  jz      loc_180006E0F
0x180006cf3  mov     rcx, rbx; hObject
0x180006cf6  call    cs:__imp_CloseHandle
0x180006cfc  test    eax, eax
0x180006cfe  jz      loc_180006E21
0x180006d04  mov     eax, r14d
0x180006d07  jmp     short loc_180006D77
0x180006d09  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006d0e  xor     edx, edx; Val
0x180006d10  mov     dword ptr [rsi], 1
0x180006d16  lea     rcx, [rsi+22h]; void *
0x180006d1a  mov     [rsi+8], rbx
0x180006d1e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006d23  lea     r8d, [rdx+56h]; Size
0x180006d27  call    memset_0
0x180006d2c  xor     edx, edx; Val
0x180006d2e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180006d34  lea     rcx, [rsi+28h]; void *
0x180006d38  mov     dword ptr [rsi+24h], 1
0x180006d3f  lea     r8d, [rdx+50h]; Size
0x180006d43  call    memset_0
0x180006d48  xor     ebx, ebx
0x180006d4a  mov     [r15], rsi
0x180006d4d  test    rdi, rdi
0x180006d50  jz      short loc_180006D63
0x180006d52  mov     rcx, rdi; hMutex
0x180006d55  call    cs:__imp_ReleaseMutex
0x180006d5b  test    eax, eax
0x180006d5d  jz      loc_180006E33
0x180006d63  test    rbx, rbx
0x180006d66  jz      short loc_180006D75
0x180006d68  mov     rcx, rbx; hObject
0x180006d6b  call    cs:__imp_CloseHandle
0x180006d71  test    eax, eax
0x180006d73  jz      short loc_180006D9D
0x180006d75  xor     eax, eax
0x180006d77  mov     rcx, [rbp+180h+var_30]
0x180006d7e  xor     rcx, rsp; StackCookie
0x180006d81  call    __security_check_cookie
0x180006d86  mov     rbx, [rsp+280h+arg_10]
0x180006d8e  add     rsp, 260h
0x180006d95  pop     r15
0x180006d97  pop     r14
0x180006d99  pop     rdi
0x180006d9a  pop     rsi
0x180006d9b  pop     rbp
0x180006d9c  retn
0x180006d9d  mov     rcx, [rbp+188h]; this
0x180006da4  mov     edx, 0A0Bh; void *
0x180006da9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006daf  mov     rcx, [rbp+188h]; this
0x180006db6  mov     edx, 0E01h; void *
0x180006dbb  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006dc1  mov     rcx, [rbp+188h]; this
0x180006dc8  mov     edx, 0A15h; void *
0x180006dcd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006dd3  mov     rcx, [rbp+188h]; this
0x180006dda  mov     edx, 0A0Bh; void *
0x180006ddf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006de5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180006deb  mov     rcx, [rbp+188h]; this
0x180006df2  mov     edx, 0A0Bh; void *
0x180006df7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006dfd  mov     rcx, [rbp+188h]; this
0x180006e04  mov     edx, 0A0Bh; void *
0x180006e09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e0f  mov     rcx, [rbp+188h]; this
0x180006e16  mov     edx, 0A15h; void *
0x180006e1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e21  mov     rcx, [rbp+188h]; this
0x180006e28  mov     edx, 0A0Bh; void *
0x180006e2d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e33  mov     rcx, [rbp+188h]; this
0x180006e3a  mov     edx, 0A15h; void *
0x180006e3f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
