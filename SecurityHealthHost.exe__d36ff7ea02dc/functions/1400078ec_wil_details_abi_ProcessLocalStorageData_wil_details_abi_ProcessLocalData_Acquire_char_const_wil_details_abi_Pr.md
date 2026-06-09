# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400078ec`
- end: `0x140007cb4`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140008dd4`

## callees

- `0x1400015f0`
- `0x1400022ec`
- `0x14000674c`
- `0x1400068ec`
- `0x1400078ec`
- `0x1400080b4`
- `0x140008534`
- `0x140008b6c`
- `0x140009228`
- `0x14000afc8`
- `0x14000b34c`
- `0x14000ba50`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140007a2c`
- `KERNEL32!CloseHandle` at `0x140007afc`
- `KERNEL32!CloseHandle` at `0x140007b14`
- `KERNEL32!CloseHandle` at `0x140007b6a`
- `KERNEL32!CloseHandle` at `0x140007bdf`
- `KERNEL32!CloseHandle` at `0x140007a2c`
- `KERNEL32!CloseHandle` at `0x140007afc`
- `KERNEL32!CloseHandle` at `0x140007b14`
- `KERNEL32!CloseHandle` at `0x140007b6a`
- `KERNEL32!CloseHandle` at `0x140007bdf`
- `KERNEL32!WaitForSingleObjectEx` at `0x140007985`
- `KERNEL32!WaitForSingleObjectEx` at `0x140007985`
- `KERNEL32!GetCurrentProcessId` at `0x140007925`
- `KERNEL32!GetCurrentProcessId` at `0x140007925`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007964`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007964`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007a1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007b59`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007bc9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007a1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007b59`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140007bc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007b22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007b22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007b30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007b30`

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
0x1400078ec  mov     [rsp-8+arg_10], rbx
0x1400078f1  push    rbp
0x1400078f2  push    rsi
0x1400078f3  push    rdi
0x1400078f4  push    r14
0x1400078f6  push    r15
0x1400078f8  lea     rbp, [rsp-160h]
0x140007900  sub     rsp, 260h
0x140007907  mov     rax, cs:__security_cookie
0x14000790e  xor     rax, rsp
0x140007911  mov     [rbp+180h+var_30], rax
0x140007918  mov     r15, rdx
0x14000791b  mov     qword ptr [rdx], 0
0x140007922  mov     rbx, rcx
0x140007925  call    cs:__imp_GetCurrentProcessId
0x14000792b  mov     r14d, 78h ; 'x'
0x140007931  mov     [rsp+280h+var_258], rbx
0x140007936  mov     r9d, eax
0x140007939  mov     [rsp+280h+var_260], r14d; int
0x14000793e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007945  mov     edx, 104h; unsigned __int64
0x14000794a  lea     rcx, [rsp+280h+Name]; Buffer
0x14000794f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007954  mov     r9d, 1F0001h; dwDesiredAccess
0x14000795a  lea     rdx, [rsp+280h+Name]; lpName
0x14000795f  xor     r8d, r8d; dwFlags
0x140007962  xor     ecx, ecx; lpMutexAttributes
0x140007964  call    cs:__imp_CreateMutexExW
0x14000796a  mov     rbx, rax
0x14000796d  test    rax, rax
0x140007970  jnz     short loc_14000797C
0x140007972  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007977  jmp     loc_140007BEB
0x14000797c  xor     r8d, r8d; bAlertable
0x14000797f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007982  mov     rcx, rbx; hHandle
0x140007985  call    cs:__imp_WaitForSingleObjectEx
0x14000798b  cmp     eax, 102h
0x140007990  jz      short loc_1400079A2
0x140007992  test    eax, 0FFFFFF7Fh
0x140007997  jnz     loc_140007C23
0x14000799d  mov     rdi, rbx
0x1400079a0  jmp     short loc_1400079A4
0x1400079a2  xor     edi, edi
0x1400079a4  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400079a9  mov     [rsp+280h+hObject], 0
0x1400079b2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400079b7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400079bc  mov     esi, eax
0x1400079be  test    eax, eax
0x1400079c0  jns     short loc_140007A41
0x1400079c2  mov     rcx, [rbp+188h]; this
0x1400079c9  lea     r8, aWil; "wil"
0x1400079d0  mov     r9d, eax; char *
0x1400079d3  mov     edx, 66h ; 'f'; void *
0x1400079d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400079dd  mov     rcx, [rbp+188h]; this
0x1400079e4  lea     r8, aWil; "wil"
0x1400079eb  mov     r9d, esi; char *
0x1400079ee  mov     edx, 6Fh ; 'o'; void *
0x1400079f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400079f8  mov     rcx, [rbp+188h]; this
0x1400079ff  lea     r8, aWil; "wil"
0x140007a06  mov     r9d, esi; char *
0x140007a09  mov     edx, 12Eh; void *
0x140007a0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007a13  test    rdi, rdi
0x140007a16  jz      short loc_140007A29
0x140007a18  mov     rcx, rdi; hMutex
0x140007a1b  call    cs:__imp_ReleaseMutex
0x140007a21  test    eax, eax
0x140007a23  jz      loc_140007C30
0x140007a29  mov     rcx, rbx; hObject
0x140007a2c  call    cs:__imp_CloseHandle
0x140007a32  test    eax, eax
0x140007a34  jz      loc_140007C42
0x140007a3a  mov     eax, esi
0x140007a3c  jmp     loc_140007BEB
0x140007a41  mov     rax, [rsp+280h+hObject]
0x140007a46  lea     rcx, ds:0[rax*4]
0x140007a4e  test    rcx, rcx
0x140007a51  jz      short loc_140007A61
0x140007a53  mov     [r15], rcx
0x140007a56  mov     eax, [rcx]
0x140007a58  inc     eax
0x140007a5a  mov     [rcx], eax
0x140007a5c  jmp     loc_140007BC1
0x140007a61  mov     rdx, r14; dwBytes
0x140007a64  mov     qword ptr [r15], 0
0x140007a6b  mov     ecx, 8; dwFlags
0x140007a70  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140007a75  mov     rsi, rax
0x140007a78  test    rax, rax
0x140007a7b  jnz     short loc_140007AA3
0x140007a7d  mov     rcx, [rbp+188h]; this
0x140007a84  lea     r8, aWil; "wil"
0x140007a8b  mov     r14d, 8007000Eh
0x140007a91  mov     edx, 14Bh; void *
0x140007a96  mov     r9d, r14d; char *
0x140007a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007a9e  jmp     loc_140007B36
0x140007aa3  xorps   xmm0, xmm0
0x140007aa6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140007aac  test    sil, 3
0x140007ab0  jnz     loc_140007C54
0x140007ab6  mov     r9, rsi
0x140007ab9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140007abe  shr     r9, 2; unsigned __int64
0x140007ac2  lea     rcx, [rsp+280h+hObject]; this
0x140007ac7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140007acc  mov     r14d, eax
0x140007acf  test    eax, eax
0x140007ad1  jns     loc_140007B7D
0x140007ad7  mov     rcx, [rbp+188h]; this
0x140007ade  lea     r8, aWil; "wil"
0x140007ae5  mov     r9d, eax; char *
0x140007ae8  mov     edx, 14Eh; void *
0x140007aed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007af2  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140007af7  test    rcx, rcx
0x140007afa  jz      short loc_140007B0A
0x140007afc  call    cs:__imp_CloseHandle
0x140007b02  test    eax, eax
0x140007b04  jz      loc_140007C5A
0x140007b0a  mov     rcx, [rsp+280h+hObject]; hObject
0x140007b0f  test    rcx, rcx
0x140007b12  jz      short loc_140007B22
0x140007b14  call    cs:__imp_CloseHandle
0x140007b1a  test    eax, eax
0x140007b1c  jz      loc_140007C6C
0x140007b22  call    cs:__imp_GetProcessHeap
0x140007b28  mov     r8, rsi; lpMem
0x140007b2b  xor     edx, edx; dwFlags
0x140007b2d  mov     rcx, rax; hHeap
0x140007b30  call    cs:__imp_HeapFree
0x140007b36  mov     rcx, [rbp+188h]; this
0x140007b3d  lea     r8, aWil; "wil"
0x140007b44  mov     r9d, r14d; char *
0x140007b47  mov     edx, 137h; void *
0x140007b4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007b51  test    rdi, rdi
0x140007b54  jz      short loc_140007B67
0x140007b56  mov     rcx, rdi; hMutex
0x140007b59  call    cs:__imp_ReleaseMutex
0x140007b5f  test    eax, eax
0x140007b61  jz      loc_140007C7E
0x140007b67  mov     rcx, rbx; hObject
0x140007b6a  call    cs:__imp_CloseHandle
0x140007b70  test    eax, eax
0x140007b72  jz      loc_140007C90
0x140007b78  mov     eax, r14d
0x140007b7b  jmp     short loc_140007BEB
0x140007b7d  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140007b82  xor     edx, edx; Val
0x140007b84  mov     dword ptr [rsi], 1
0x140007b8a  lea     rcx, [rsi+22h]; void *
0x140007b8e  mov     [rsi+8], rbx
0x140007b92  movdqu  xmmword ptr [rsi+10h], xmm0
0x140007b97  lea     r8d, [rdx+56h]; Size
0x140007b9b  call    memset_0
0x140007ba0  xor     edx, edx; Val
0x140007ba2  mov     word ptr [rsi+20h], 58h ; 'X'
0x140007ba8  lea     rcx, [rsi+28h]; void *
0x140007bac  mov     dword ptr [rsi+24h], 1
0x140007bb3  lea     r8d, [rdx+50h]; Size
0x140007bb7  call    memset_0
0x140007bbc  xor     ebx, ebx
0x140007bbe  mov     [r15], rsi
0x140007bc1  test    rdi, rdi
0x140007bc4  jz      short loc_140007BD7
0x140007bc6  mov     rcx, rdi; hMutex
0x140007bc9  call    cs:__imp_ReleaseMutex
0x140007bcf  test    eax, eax
0x140007bd1  jz      loc_140007CA2
0x140007bd7  test    rbx, rbx
0x140007bda  jz      short loc_140007BE9
0x140007bdc  mov     rcx, rbx; hObject
0x140007bdf  call    cs:__imp_CloseHandle
0x140007be5  test    eax, eax
0x140007be7  jz      short loc_140007C11
0x140007be9  xor     eax, eax
0x140007beb  mov     rcx, [rbp+180h+var_30]
0x140007bf2  xor     rcx, rsp; StackCookie
0x140007bf5  call    __security_check_cookie
0x140007bfa  mov     rbx, [rsp+280h+arg_10]
0x140007c02  add     rsp, 260h
0x140007c09  pop     r15
0x140007c0b  pop     r14
0x140007c0d  pop     rdi
0x140007c0e  pop     rsi
0x140007c0f  pop     rbp
0x140007c10  retn
0x140007c11  mov     rcx, [rbp+188h]; this
0x140007c18  mov     edx, 0A0Bh; void *
0x140007c1d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007c23  mov     rcx, [rbp+188h]; this
0x140007c2a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140007c30  mov     rcx, [rbp+188h]; this
0x140007c37  mov     edx, 0A15h; void *
0x140007c3c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007c42  mov     rcx, [rbp+188h]; this
0x140007c49  mov     edx, 0A0Bh; void *
0x140007c4e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007c54  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140007c5a  mov     rcx, [rbp+188h]; this
0x140007c61  mov     edx, 0A0Bh; void *
0x140007c66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007c6c  mov     rcx, [rbp+188h]; this
0x140007c73  mov     edx, 0A0Bh; void *
0x140007c78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007c7e  mov     rcx, [rbp+188h]; this
0x140007c85  mov     edx, 0A15h; void *
0x140007c8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007c90  mov     rcx, [rbp+188h]; this
0x140007c97  mov     edx, 0A0Bh; void *
0x140007c9c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007ca2  mov     rcx, [rbp+188h]; this
0x140007ca9  mov     edx, 0A15h; void *
0x140007cae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
