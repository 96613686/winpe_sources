# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800064a8`
- end: `0x180006846`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180007e6c`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x1800064a8`
- `0x180006b30`
- `0x180007164`
- `0x180007a98`
- `0x180008b08`
- `0x180009434`
- `0x180009e24`
- `0x18000a040`
- `0x18000a8dc`
- `0x18000a8ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006520`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180006520`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006541`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180006541`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000675b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800065c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800066eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000675b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800064e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800064e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006771`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006695`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006771`

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
0x1800064a8  mov     [rsp-8+arg_10], rbx
0x1800064ad  push    rbp
0x1800064ae  push    rsi
0x1800064af  push    rdi
0x1800064b0  push    r14
0x1800064b2  push    r15
0x1800064b4  lea     rbp, [rsp-160h]
0x1800064bc  sub     rsp, 260h
0x1800064c3  mov     rax, cs:__security_cookie
0x1800064ca  xor     rax, rsp
0x1800064cd  mov     [rbp+180h+var_30], rax
0x1800064d4  mov     r15, rdx
0x1800064d7  mov     qword ptr [rdx], 0
0x1800064de  mov     rbx, rcx
0x1800064e1  call    cs:__imp_GetCurrentProcessId
0x1800064e7  mov     r14d, 78h ; 'x'
0x1800064ed  mov     [rsp+280h+var_258], rbx
0x1800064f2  mov     r9d, eax
0x1800064f5  mov     [rsp+280h+var_260], r14d; int
0x1800064fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006501  mov     edx, 104h; unsigned __int64
0x180006506  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000650b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006510  mov     r9d, 1F0001h; dwDesiredAccess
0x180006516  lea     rdx, [rsp+280h+Name]; lpName
0x18000651b  xor     r8d, r8d; dwFlags
0x18000651e  xor     ecx, ecx; lpMutexAttributes
0x180006520  call    cs:__imp_CreateMutexExW
0x180006526  mov     rbx, rax
0x180006529  test    rax, rax
0x18000652c  jnz     short loc_180006538
0x18000652e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006533  jmp     loc_18000677D
0x180006538  xor     r8d, r8d; bAlertable
0x18000653b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000653e  mov     rcx, rbx; hHandle
0x180006541  call    cs:__imp_WaitForSingleObjectEx
0x180006547  cmp     eax, 102h
0x18000654c  jz      short loc_18000655E
0x18000654e  test    eax, 0FFFFFF7Fh
0x180006553  jnz     loc_1800067B5
0x180006559  mov     rdi, rbx
0x18000655c  jmp     short loc_180006560
0x18000655e  xor     edi, edi
0x180006560  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180006565  mov     [rsp+280h+hObject], 0
0x18000656e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006573  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180006578  mov     esi, eax
0x18000657a  test    eax, eax
0x18000657c  jns     short loc_1800065E8
0x18000657e  mov     rcx, [rbp+188h]; this
0x180006585  mov     r9d, eax; char *
0x180006588  mov     edx, 66h ; 'f'; void *
0x18000658d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006592  mov     rcx, [rbp+188h]; this
0x180006599  mov     r9d, esi; char *
0x18000659c  mov     edx, 6Fh ; 'o'; void *
0x1800065a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065a6  mov     rcx, [rbp+188h]; this
0x1800065ad  mov     r9d, esi; char *
0x1800065b0  mov     edx, 12Eh; void *
0x1800065b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065ba  test    rdi, rdi
0x1800065bd  jz      short loc_1800065D0
0x1800065bf  mov     rcx, rdi; hMutex
0x1800065c2  call    cs:__imp_ReleaseMutex
0x1800065c8  test    eax, eax
0x1800065ca  jz      loc_1800067C2
0x1800065d0  mov     rcx, rbx; hObject
0x1800065d3  call    cs:__imp_CloseHandle
0x1800065d9  test    eax, eax
0x1800065db  jz      loc_1800067D4
0x1800065e1  mov     eax, esi
0x1800065e3  jmp     loc_18000677D
0x1800065e8  mov     rax, [rsp+280h+hObject]
0x1800065ed  lea     rcx, ds:0[rax*4]
0x1800065f5  test    rcx, rcx
0x1800065f8  jz      short loc_180006608
0x1800065fa  mov     [r15], rcx
0x1800065fd  mov     eax, [rcx]
0x1800065ff  inc     eax
0x180006601  mov     [rcx], eax
0x180006603  jmp     loc_180006753
0x180006608  mov     rdx, r14; dwBytes
0x18000660b  mov     qword ptr [r15], 0
0x180006612  mov     ecx, 8; dwFlags
0x180006617  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000661c  mov     rsi, rax
0x18000661f  test    rax, rax
0x180006622  jnz     short loc_180006643
0x180006624  mov     rcx, [rbp+188h]; this
0x18000662b  mov     r14d, 8007000Eh
0x180006631  mov     r9d, r14d; char *
0x180006634  mov     edx, 14Bh; void *
0x180006639  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000663e  jmp     loc_1800066CF
0x180006643  xorps   xmm0, xmm0
0x180006646  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x18000664c  test    sil, 3
0x180006650  jnz     loc_1800067E6
0x180006656  mov     r9, rsi
0x180006659  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x18000665e  shr     r9, 2; unsigned __int64
0x180006662  lea     rcx, [rsp+280h+hObject]; this
0x180006667  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000666c  mov     r14d, eax
0x18000666f  test    eax, eax
0x180006671  jns     loc_18000670F
0x180006677  mov     rcx, [rbp+188h]; this
0x18000667e  mov     r9d, eax; char *
0x180006681  mov     edx, 14Eh; void *
0x180006686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000668b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180006690  test    rcx, rcx
0x180006693  jz      short loc_1800066A3
0x180006695  call    cs:__imp_CloseHandle
0x18000669b  test    eax, eax
0x18000669d  jz      loc_1800067EC
0x1800066a3  mov     rcx, [rsp+280h+hObject]; hObject
0x1800066a8  test    rcx, rcx
0x1800066ab  jz      short loc_1800066BB
0x1800066ad  call    cs:__imp_CloseHandle
0x1800066b3  test    eax, eax
0x1800066b5  jz      loc_1800067FE
0x1800066bb  call    cs:__imp_GetProcessHeap
0x1800066c1  mov     r8, rsi; lpMem
0x1800066c4  xor     edx, edx; dwFlags
0x1800066c6  mov     rcx, rax; hHeap
0x1800066c9  call    cs:__imp_HeapFree
0x1800066cf  mov     rcx, [rbp+188h]; this
0x1800066d6  mov     r9d, r14d; char *
0x1800066d9  mov     edx, 137h; void *
0x1800066de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066e3  test    rdi, rdi
0x1800066e6  jz      short loc_1800066F9
0x1800066e8  mov     rcx, rdi; hMutex
0x1800066eb  call    cs:__imp_ReleaseMutex
0x1800066f1  test    eax, eax
0x1800066f3  jz      loc_180006810
0x1800066f9  mov     rcx, rbx; hObject
0x1800066fc  call    cs:__imp_CloseHandle
0x180006702  test    eax, eax
0x180006704  jz      loc_180006822
0x18000670a  mov     eax, r14d
0x18000670d  jmp     short loc_18000677D
0x18000670f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006714  xor     edx, edx; Val
0x180006716  mov     dword ptr [rsi], 1
0x18000671c  lea     rcx, [rsi+22h]; void *
0x180006720  mov     [rsi+8], rbx
0x180006724  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006729  lea     r8d, [rdx+56h]; Size
0x18000672d  call    memset_0
0x180006732  xor     edx, edx; Val
0x180006734  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000673a  lea     rcx, [rsi+28h]; void *
0x18000673e  mov     dword ptr [rsi+24h], 1
0x180006745  lea     r8d, [rdx+50h]; Size
0x180006749  call    memset_0
0x18000674e  xor     ebx, ebx
0x180006750  mov     [r15], rsi
0x180006753  test    rdi, rdi
0x180006756  jz      short loc_180006769
0x180006758  mov     rcx, rdi; hMutex
0x18000675b  call    cs:__imp_ReleaseMutex
0x180006761  test    eax, eax
0x180006763  jz      loc_180006834
0x180006769  test    rbx, rbx
0x18000676c  jz      short loc_18000677B
0x18000676e  mov     rcx, rbx; hObject
0x180006771  call    cs:__imp_CloseHandle
0x180006777  test    eax, eax
0x180006779  jz      short loc_1800067A3
0x18000677b  xor     eax, eax
0x18000677d  mov     rcx, [rbp+180h+var_30]
0x180006784  xor     rcx, rsp; StackCookie
0x180006787  call    __security_check_cookie
0x18000678c  mov     rbx, [rsp+280h+arg_10]
0x180006794  add     rsp, 260h
0x18000679b  pop     r15
0x18000679d  pop     r14
0x18000679f  pop     rdi
0x1800067a0  pop     rsi
0x1800067a1  pop     rbp
0x1800067a2  retn
0x1800067a3  mov     rcx, [rbp+188h]; this
0x1800067aa  mov     edx, 0A0Bh; void *
0x1800067af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067b5  mov     rcx, [rbp+188h]; this
0x1800067bc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800067c2  mov     rcx, [rbp+188h]; this
0x1800067c9  mov     edx, 0A15h; void *
0x1800067ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067d4  mov     rcx, [rbp+188h]; this
0x1800067db  mov     edx, 0A0Bh; void *
0x1800067e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067e6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800067ec  mov     rcx, [rbp+188h]; this
0x1800067f3  mov     edx, 0A0Bh; void *
0x1800067f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067fe  mov     rcx, [rbp+188h]; this
0x180006805  mov     edx, 0A0Bh; void *
0x18000680a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006810  mov     rcx, [rbp+188h]; this
0x180006817  mov     edx, 0A15h; void *
0x18000681c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006822  mov     rcx, [rbp+188h]; this
0x180006829  mov     edx, 0A0Bh; void *
0x18000682e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006834  mov     rcx, [rbp+188h]; this
0x18000683b  mov     edx, 0A15h; void *
0x180006840  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
