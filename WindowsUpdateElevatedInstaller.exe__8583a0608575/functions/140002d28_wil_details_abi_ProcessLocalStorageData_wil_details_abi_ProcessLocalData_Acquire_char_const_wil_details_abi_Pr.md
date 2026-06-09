# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140002d28`
- end: `0x1400030f0`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140003c00`

## callees

- `0x140001480`
- `0x140001e7e`
- `0x140002d28`
- `0x1400030f8`
- `0x140003340`
- `0x140003998`
- `0x140004478`
- `0x1400048e4`
- `0x140005284`
- `0x14000535c`
- `0x14000572c`
- `0x14000573c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140002f6c`
- `KERNEL32!HeapFree` at `0x140002f6c`
- `KERNEL32!ReleaseMutex` at `0x140002e57`
- `KERNEL32!ReleaseMutex` at `0x140002f95`
- `KERNEL32!ReleaseMutex` at `0x140003005`
- `KERNEL32!ReleaseMutex` at `0x140002e57`
- `KERNEL32!ReleaseMutex` at `0x140002f95`
- `KERNEL32!ReleaseMutex` at `0x140003005`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002dc1`
- `KERNEL32!WaitForSingleObjectEx` at `0x140002dc1`
- `KERNEL32!CloseHandle` at `0x140002e68`
- `KERNEL32!CloseHandle` at `0x140002f38`
- `KERNEL32!CloseHandle` at `0x140002f50`
- `KERNEL32!CloseHandle` at `0x140002fa6`
- `KERNEL32!CloseHandle` at `0x14000301b`
- `KERNEL32!CloseHandle` at `0x140002e68`
- `KERNEL32!CloseHandle` at `0x140002f38`
- `KERNEL32!CloseHandle` at `0x140002f50`
- `KERNEL32!CloseHandle` at `0x140002fa6`
- `KERNEL32!CloseHandle` at `0x14000301b`
- `KERNEL32!CreateMutexExW` at `0x140002da0`
- `KERNEL32!CreateMutexExW` at `0x140002da0`
- `KERNEL32!GetCurrentProcessId` at `0x140002d61`
- `KERNEL32!GetCurrentProcessId` at `0x140002d61`
- `KERNEL32!GetProcessHeap` at `0x140002f5e`
- `KERNEL32!GetProcessHeap` at `0x140002f5e`

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
0x140002d28  mov     [rsp-8+arg_10], rbx
0x140002d2d  push    rbp
0x140002d2e  push    rsi
0x140002d2f  push    rdi
0x140002d30  push    r14
0x140002d32  push    r15
0x140002d34  lea     rbp, [rsp-160h]
0x140002d3c  sub     rsp, 260h
0x140002d43  mov     rax, cs:__security_cookie
0x140002d4a  xor     rax, rsp
0x140002d4d  mov     [rbp+180h+var_30], rax
0x140002d54  mov     r15, rdx
0x140002d57  mov     qword ptr [rdx], 0
0x140002d5e  mov     rbx, rcx
0x140002d61  call    cs:__imp_GetCurrentProcessId
0x140002d67  mov     r14d, 78h ; 'x'
0x140002d6d  mov     [rsp+280h+var_258], rbx
0x140002d72  mov     r9d, eax
0x140002d75  mov     [rsp+280h+var_260], r14d; int
0x140002d7a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002d81  mov     edx, 104h; unsigned __int64
0x140002d86  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002d8b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002d90  mov     r9d, 1F0001h; dwDesiredAccess
0x140002d96  lea     rdx, [rsp+280h+Name]; lpName
0x140002d9b  xor     r8d, r8d; dwFlags
0x140002d9e  xor     ecx, ecx; lpMutexAttributes
0x140002da0  call    cs:__imp_CreateMutexExW
0x140002da6  mov     rbx, rax
0x140002da9  test    rax, rax
0x140002dac  jnz     short loc_140002DB8
0x140002dae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140002db3  jmp     loc_140003027
0x140002db8  xor     r8d, r8d; bAlertable
0x140002dbb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140002dbe  mov     rcx, rbx; hHandle
0x140002dc1  call    cs:__imp_WaitForSingleObjectEx
0x140002dc7  cmp     eax, 102h
0x140002dcc  jz      short loc_140002DDE
0x140002dce  test    eax, 0FFFFFF7Fh
0x140002dd3  jnz     loc_14000305F
0x140002dd9  mov     rdi, rbx
0x140002ddc  jmp     short loc_140002DE0
0x140002dde  xor     edi, edi
0x140002de0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140002de5  mov     [rsp+280h+hObject], 0
0x140002dee  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140002df3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140002df8  mov     esi, eax
0x140002dfa  test    eax, eax
0x140002dfc  jns     short loc_140002E7D
0x140002dfe  mov     rcx, [rbp+188h]; this
0x140002e05  lea     r8, aWil; "wil"
0x140002e0c  mov     r9d, eax; char *
0x140002e0f  mov     edx, 66h ; 'f'; void *
0x140002e14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e19  mov     rcx, [rbp+188h]; this
0x140002e20  lea     r8, aWil; "wil"
0x140002e27  mov     r9d, esi; char *
0x140002e2a  mov     edx, 6Fh ; 'o'; void *
0x140002e2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e34  mov     rcx, [rbp+188h]; this
0x140002e3b  lea     r8, aWil; "wil"
0x140002e42  mov     r9d, esi; char *
0x140002e45  mov     edx, 12Eh; void *
0x140002e4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002e4f  test    rdi, rdi
0x140002e52  jz      short loc_140002E65
0x140002e54  mov     rcx, rdi; hMutex
0x140002e57  call    cs:__imp_ReleaseMutex
0x140002e5d  test    eax, eax
0x140002e5f  jz      loc_14000306C
0x140002e65  mov     rcx, rbx; hObject
0x140002e68  call    cs:__imp_CloseHandle
0x140002e6e  test    eax, eax
0x140002e70  jz      loc_14000307E
0x140002e76  mov     eax, esi
0x140002e78  jmp     loc_140003027
0x140002e7d  mov     rax, [rsp+280h+hObject]
0x140002e82  lea     rcx, ds:0[rax*4]
0x140002e8a  test    rcx, rcx
0x140002e8d  jz      short loc_140002E9D
0x140002e8f  mov     [r15], rcx
0x140002e92  mov     eax, [rcx]
0x140002e94  inc     eax
0x140002e96  mov     [rcx], eax
0x140002e98  jmp     loc_140002FFD
0x140002e9d  mov     rdx, r14; dwBytes
0x140002ea0  mov     qword ptr [r15], 0
0x140002ea7  mov     ecx, 8; dwFlags
0x140002eac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140002eb1  mov     rsi, rax
0x140002eb4  test    rax, rax
0x140002eb7  jnz     short loc_140002EDF
0x140002eb9  mov     rcx, [rbp+188h]; this
0x140002ec0  lea     r8, aWil; "wil"
0x140002ec7  mov     r14d, 8007000Eh
0x140002ecd  mov     edx, 14Bh; void *
0x140002ed2  mov     r9d, r14d; char *
0x140002ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002eda  jmp     loc_140002F72
0x140002edf  xorps   xmm0, xmm0
0x140002ee2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140002ee8  test    sil, 3
0x140002eec  jnz     loc_140003090
0x140002ef2  mov     r9, rsi
0x140002ef5  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140002efa  shr     r9, 2; unsigned __int64
0x140002efe  lea     rcx, [rsp+280h+hObject]; this
0x140002f03  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140002f08  mov     r14d, eax
0x140002f0b  test    eax, eax
0x140002f0d  jns     loc_140002FB9
0x140002f13  mov     rcx, [rbp+188h]; this
0x140002f1a  lea     r8, aWil; "wil"
0x140002f21  mov     r9d, eax; char *
0x140002f24  mov     edx, 14Eh; void *
0x140002f29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f2e  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140002f33  test    rcx, rcx
0x140002f36  jz      short loc_140002F46
0x140002f38  call    cs:__imp_CloseHandle
0x140002f3e  test    eax, eax
0x140002f40  jz      loc_140003096
0x140002f46  mov     rcx, [rsp+280h+hObject]; hObject
0x140002f4b  test    rcx, rcx
0x140002f4e  jz      short loc_140002F5E
0x140002f50  call    cs:__imp_CloseHandle
0x140002f56  test    eax, eax
0x140002f58  jz      loc_1400030A8
0x140002f5e  call    cs:__imp_GetProcessHeap
0x140002f64  mov     r8, rsi; lpMem
0x140002f67  xor     edx, edx; dwFlags
0x140002f69  mov     rcx, rax; hHeap
0x140002f6c  call    cs:__imp_HeapFree
0x140002f72  mov     rcx, [rbp+188h]; this
0x140002f79  lea     r8, aWil; "wil"
0x140002f80  mov     r9d, r14d; char *
0x140002f83  mov     edx, 137h; void *
0x140002f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002f8d  test    rdi, rdi
0x140002f90  jz      short loc_140002FA3
0x140002f92  mov     rcx, rdi; hMutex
0x140002f95  call    cs:__imp_ReleaseMutex
0x140002f9b  test    eax, eax
0x140002f9d  jz      loc_1400030BA
0x140002fa3  mov     rcx, rbx; hObject
0x140002fa6  call    cs:__imp_CloseHandle
0x140002fac  test    eax, eax
0x140002fae  jz      loc_1400030CC
0x140002fb4  mov     eax, r14d
0x140002fb7  jmp     short loc_140003027
0x140002fb9  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140002fbe  xor     edx, edx; Val
0x140002fc0  mov     dword ptr [rsi], 1
0x140002fc6  lea     rcx, [rsi+22h]; void *
0x140002fca  mov     [rsi+8], rbx
0x140002fce  movdqu  xmmword ptr [rsi+10h], xmm0
0x140002fd3  lea     r8d, [rdx+56h]; Size
0x140002fd7  call    memset_0
0x140002fdc  xor     edx, edx; Val
0x140002fde  mov     word ptr [rsi+20h], 58h ; 'X'
0x140002fe4  lea     rcx, [rsi+28h]; void *
0x140002fe8  mov     dword ptr [rsi+24h], 1
0x140002fef  lea     r8d, [rdx+50h]; Size
0x140002ff3  call    memset_0
0x140002ff8  xor     ebx, ebx
0x140002ffa  mov     [r15], rsi
0x140002ffd  test    rdi, rdi
0x140003000  jz      short loc_140003013
0x140003002  mov     rcx, rdi; hMutex
0x140003005  call    cs:__imp_ReleaseMutex
0x14000300b  test    eax, eax
0x14000300d  jz      loc_1400030DE
0x140003013  test    rbx, rbx
0x140003016  jz      short loc_140003025
0x140003018  mov     rcx, rbx; hObject
0x14000301b  call    cs:__imp_CloseHandle
0x140003021  test    eax, eax
0x140003023  jz      short loc_14000304D
0x140003025  xor     eax, eax
0x140003027  mov     rcx, [rbp+180h+var_30]
0x14000302e  xor     rcx, rsp; StackCookie
0x140003031  call    __security_check_cookie
0x140003036  mov     rbx, [rsp+280h+arg_10]
0x14000303e  add     rsp, 260h
0x140003045  pop     r15
0x140003047  pop     r14
0x140003049  pop     rdi
0x14000304a  pop     rsi
0x14000304b  pop     rbp
0x14000304c  retn
0x14000304d  mov     rcx, [rbp+188h]; this
0x140003054  mov     edx, 0A0Bh; void *
0x140003059  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000305f  mov     rcx, [rbp+188h]; this
0x140003066  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000306c  mov     rcx, [rbp+188h]; this
0x140003073  mov     edx, 0A15h; void *
0x140003078  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000307e  mov     rcx, [rbp+188h]; this
0x140003085  mov     edx, 0A0Bh; void *
0x14000308a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003090  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003096  mov     rcx, [rbp+188h]; this
0x14000309d  mov     edx, 0A0Bh; void *
0x1400030a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030a8  mov     rcx, [rbp+188h]; this
0x1400030af  mov     edx, 0A0Bh; void *
0x1400030b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030ba  mov     rcx, [rbp+188h]; this
0x1400030c1  mov     edx, 0A15h; void *
0x1400030c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030cc  mov     rcx, [rbp+188h]; this
0x1400030d3  mov     edx, 0A0Bh; void *
0x1400030d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400030de  mov     rcx, [rbp+188h]; this
0x1400030e5  mov     edx, 0A15h; void *
0x1400030ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
