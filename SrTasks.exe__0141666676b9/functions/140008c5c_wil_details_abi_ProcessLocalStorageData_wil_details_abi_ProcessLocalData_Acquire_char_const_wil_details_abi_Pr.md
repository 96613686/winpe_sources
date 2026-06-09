# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140008c5c`
- end: `0x140008ffa`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000a3bc`

## callees

- `0x140005cd0`
- `0x140005e24`
- `0x140008c5c`
- `0x1400093d0`
- `0x140009834`
- `0x14000a158`
- `0x14000bf30`
- `0x14000c5cc`
- `0x14000cdac`
- `0x14000cdbc`
- `0x14001094e`
- `0x140010980`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x140008d76`
- `KERNEL32!ReleaseMutex` at `0x140008e9f`
- `KERNEL32!ReleaseMutex` at `0x140008f0f`
- `KERNEL32!ReleaseMutex` at `0x140008d76`
- `KERNEL32!ReleaseMutex` at `0x140008e9f`
- `KERNEL32!ReleaseMutex` at `0x140008f0f`
- `KERNEL32!WaitForSingleObjectEx` at `0x140008cf5`
- `KERNEL32!WaitForSingleObjectEx` at `0x140008cf5`
- `KERNEL32!CreateMutexExW` at `0x140008cd4`
- `KERNEL32!CreateMutexExW` at `0x140008cd4`
- `KERNEL32!HeapFree` at `0x140008e7d`
- `KERNEL32!HeapFree` at `0x140008e7d`
- `KERNEL32!GetProcessHeap` at `0x140008e6f`
- `KERNEL32!GetProcessHeap` at `0x140008e6f`
- `KERNEL32!CloseHandle` at `0x140008d87`
- `KERNEL32!CloseHandle` at `0x140008e49`
- `KERNEL32!CloseHandle` at `0x140008e61`
- `KERNEL32!CloseHandle` at `0x140008eb0`
- `KERNEL32!CloseHandle` at `0x140008f25`
- `KERNEL32!CloseHandle` at `0x140008d87`
- `KERNEL32!CloseHandle` at `0x140008e49`
- `KERNEL32!CloseHandle` at `0x140008e61`
- `KERNEL32!CloseHandle` at `0x140008eb0`
- `KERNEL32!CloseHandle` at `0x140008f25`
- `KERNEL32!GetCurrentProcessId` at `0x140008c95`
- `KERNEL32!GetCurrentProcessId` at `0x140008c95`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
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
0x140008c5c  mov     [rsp-8+arg_10], rbx
0x140008c61  push    rbp
0x140008c62  push    rsi
0x140008c63  push    rdi
0x140008c64  push    r14
0x140008c66  push    r15
0x140008c68  lea     rbp, [rsp-160h]
0x140008c70  sub     rsp, 260h
0x140008c77  mov     rax, cs:__security_cookie
0x140008c7e  xor     rax, rsp
0x140008c81  mov     [rbp+180h+var_30], rax
0x140008c88  mov     r15, rdx
0x140008c8b  mov     qword ptr [rdx], 0
0x140008c92  mov     rbx, rcx
0x140008c95  call    cs:__imp_GetCurrentProcessId
0x140008c9b  mov     r14d, 78h ; 'x'
0x140008ca1  mov     [rsp+280h+var_258], rbx
0x140008ca6  mov     r9d, eax
0x140008ca9  mov     [rsp+280h+var_260], r14d; int
0x140008cae  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140008cb5  mov     edx, 104h; unsigned __int64
0x140008cba  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008cbf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008cc4  mov     r9d, 1F0001h; dwDesiredAccess
0x140008cca  lea     rdx, [rsp+280h+Name]; lpName
0x140008ccf  xor     r8d, r8d; dwFlags
0x140008cd2  xor     ecx, ecx; lpMutexAttributes
0x140008cd4  call    cs:__imp_CreateMutexExW
0x140008cda  mov     rbx, rax
0x140008cdd  test    rax, rax
0x140008ce0  jnz     short loc_140008CEC
0x140008ce2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140008ce7  jmp     loc_140008F31
0x140008cec  xor     r8d, r8d; bAlertable
0x140008cef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140008cf2  mov     rcx, rbx; hHandle
0x140008cf5  call    cs:__imp_WaitForSingleObjectEx
0x140008cfb  cmp     eax, 102h
0x140008d00  jz      short loc_140008D12
0x140008d02  test    eax, 0FFFFFF7Fh
0x140008d07  jnz     loc_140008F69
0x140008d0d  mov     rdi, rbx
0x140008d10  jmp     short loc_140008D14
0x140008d12  xor     edi, edi
0x140008d14  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140008d19  mov     [rsp+280h+hObject], 0
0x140008d22  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008d27  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140008d2c  mov     esi, eax
0x140008d2e  test    eax, eax
0x140008d30  jns     short loc_140008D9C
0x140008d32  mov     rcx, [rbp+188h]; this
0x140008d39  mov     r9d, eax; char *
0x140008d3c  mov     edx, 66h ; 'f'; void *
0x140008d41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008d46  mov     rcx, [rbp+188h]; this
0x140008d4d  mov     r9d, esi; char *
0x140008d50  mov     edx, 6Fh ; 'o'; void *
0x140008d55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008d5a  mov     rcx, [rbp+188h]; this
0x140008d61  mov     r9d, esi; char *
0x140008d64  mov     edx, 12Eh; void *
0x140008d69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008d6e  test    rdi, rdi
0x140008d71  jz      short loc_140008D84
0x140008d73  mov     rcx, rdi; hMutex
0x140008d76  call    cs:__imp_ReleaseMutex
0x140008d7c  test    eax, eax
0x140008d7e  jz      loc_140008F76
0x140008d84  mov     rcx, rbx; hObject
0x140008d87  call    cs:__imp_CloseHandle
0x140008d8d  test    eax, eax
0x140008d8f  jz      loc_140008F88
0x140008d95  mov     eax, esi
0x140008d97  jmp     loc_140008F31
0x140008d9c  mov     rax, [rsp+280h+hObject]
0x140008da1  lea     rcx, ds:0[rax*4]
0x140008da9  test    rcx, rcx
0x140008dac  jz      short loc_140008DBC
0x140008dae  mov     [r15], rcx
0x140008db1  mov     eax, [rcx]
0x140008db3  inc     eax
0x140008db5  mov     [rcx], eax
0x140008db7  jmp     loc_140008F07
0x140008dbc  mov     rdx, r14; dwBytes
0x140008dbf  mov     qword ptr [r15], 0
0x140008dc6  mov     ecx, 8; dwFlags
0x140008dcb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008dd0  mov     rsi, rax
0x140008dd3  test    rax, rax
0x140008dd6  jnz     short loc_140008DF7
0x140008dd8  mov     rcx, [rbp+188h]; this
0x140008ddf  mov     r14d, 8007000Eh
0x140008de5  mov     r9d, r14d; char *
0x140008de8  mov     edx, 14Bh; void *
0x140008ded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008df2  jmp     loc_140008E83
0x140008df7  xorps   xmm0, xmm0
0x140008dfa  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140008e00  test    sil, 3
0x140008e04  jnz     loc_140008F9A
0x140008e0a  mov     r9, rsi
0x140008e0d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140008e12  shr     r9, 2; unsigned __int64
0x140008e16  lea     rcx, [rsp+280h+hObject]; this
0x140008e1b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140008e20  mov     r14d, eax
0x140008e23  test    eax, eax
0x140008e25  jns     loc_140008EC3
0x140008e2b  mov     rcx, [rbp+188h]; this
0x140008e32  mov     r9d, eax; char *
0x140008e35  mov     edx, 14Eh; void *
0x140008e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008e3f  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140008e44  test    rcx, rcx
0x140008e47  jz      short loc_140008E57
0x140008e49  call    cs:__imp_CloseHandle
0x140008e4f  test    eax, eax
0x140008e51  jz      loc_140008FA0
0x140008e57  mov     rcx, [rsp+280h+hObject]; hObject
0x140008e5c  test    rcx, rcx
0x140008e5f  jz      short loc_140008E6F
0x140008e61  call    cs:__imp_CloseHandle
0x140008e67  test    eax, eax
0x140008e69  jz      loc_140008FB2
0x140008e6f  call    cs:__imp_GetProcessHeap
0x140008e75  mov     r8, rsi; lpMem
0x140008e78  xor     edx, edx; dwFlags
0x140008e7a  mov     rcx, rax; hHeap
0x140008e7d  call    cs:__imp_HeapFree
0x140008e83  mov     rcx, [rbp+188h]; this
0x140008e8a  mov     r9d, r14d; char *
0x140008e8d  mov     edx, 137h; void *
0x140008e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008e97  test    rdi, rdi
0x140008e9a  jz      short loc_140008EAD
0x140008e9c  mov     rcx, rdi; hMutex
0x140008e9f  call    cs:__imp_ReleaseMutex
0x140008ea5  test    eax, eax
0x140008ea7  jz      loc_140008FC4
0x140008ead  mov     rcx, rbx; hObject
0x140008eb0  call    cs:__imp_CloseHandle
0x140008eb6  test    eax, eax
0x140008eb8  jz      loc_140008FD6
0x140008ebe  mov     eax, r14d
0x140008ec1  jmp     short loc_140008F31
0x140008ec3  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140008ec8  xor     edx, edx; Val
0x140008eca  mov     dword ptr [rsi], 1
0x140008ed0  lea     rcx, [rsi+22h]; void *
0x140008ed4  mov     [rsi+8], rbx
0x140008ed8  movdqu  xmmword ptr [rsi+10h], xmm0
0x140008edd  lea     r8d, [rdx+56h]; Size
0x140008ee1  call    memset_0
0x140008ee6  xor     edx, edx; Val
0x140008ee8  mov     word ptr [rsi+20h], 58h ; 'X'
0x140008eee  lea     rcx, [rsi+28h]; void *
0x140008ef2  mov     dword ptr [rsi+24h], 1
0x140008ef9  lea     r8d, [rdx+50h]; Size
0x140008efd  call    memset_0
0x140008f02  xor     ebx, ebx
0x140008f04  mov     [r15], rsi
0x140008f07  test    rdi, rdi
0x140008f0a  jz      short loc_140008F1D
0x140008f0c  mov     rcx, rdi; hMutex
0x140008f0f  call    cs:__imp_ReleaseMutex
0x140008f15  test    eax, eax
0x140008f17  jz      loc_140008FE8
0x140008f1d  test    rbx, rbx
0x140008f20  jz      short loc_140008F2F
0x140008f22  mov     rcx, rbx; hObject
0x140008f25  call    cs:__imp_CloseHandle
0x140008f2b  test    eax, eax
0x140008f2d  jz      short loc_140008F57
0x140008f2f  xor     eax, eax
0x140008f31  mov     rcx, [rbp+180h+var_30]
0x140008f38  xor     rcx, rsp; StackCookie
0x140008f3b  call    __security_check_cookie
0x140008f40  mov     rbx, [rsp+280h+arg_10]
0x140008f48  add     rsp, 260h
0x140008f4f  pop     r15
0x140008f51  pop     r14
0x140008f53  pop     rdi
0x140008f54  pop     rsi
0x140008f55  pop     rbp
0x140008f56  retn
0x140008f57  mov     rcx, [rbp+188h]; this
0x140008f5e  mov     edx, 0A0Bh; void *
0x140008f63  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008f69  mov     rcx, [rbp+188h]; this
0x140008f70  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140008f76  mov     rcx, [rbp+188h]; this
0x140008f7d  mov     edx, 0A15h; void *
0x140008f82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008f88  mov     rcx, [rbp+188h]; this
0x140008f8f  mov     edx, 0A0Bh; void *
0x140008f94  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008f9a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008fa0  mov     rcx, [rbp+188h]; this
0x140008fa7  mov     edx, 0A0Bh; void *
0x140008fac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008fb2  mov     rcx, [rbp+188h]; this
0x140008fb9  mov     edx, 0A0Bh; void *
0x140008fbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008fc4  mov     rcx, [rbp+188h]; this
0x140008fcb  mov     edx, 0A15h; void *
0x140008fd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008fd6  mov     rcx, [rbp+188h]; this
0x140008fdd  mov     edx, 0A0Bh; void *
0x140008fe2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008fe8  mov     rcx, [rbp+188h]; this
0x140008fef  mov     edx, 0A15h; void *
0x140008ff4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
