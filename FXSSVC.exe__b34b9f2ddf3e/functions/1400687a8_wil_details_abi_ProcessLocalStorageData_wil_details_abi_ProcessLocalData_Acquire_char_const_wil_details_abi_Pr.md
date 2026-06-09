# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400687a8`
- end: `0x140068b46`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140069fd0`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x1400687a8`
- `0x140069088`
- `0x140069504`
- `0x140069d68`
- `0x14006ac38`
- `0x14006bf04`
- `0x14006cb6c`
- `0x14006d33c`
- `0x14006d34c`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140068820`
- `KERNEL32!CreateMutexExW` at `0x140068820`
- `KERNEL32!WaitForSingleObjectEx` at `0x140068841`
- `KERNEL32!WaitForSingleObjectEx` at `0x140068841`
- `KERNEL32!ReleaseMutex` at `0x1400688c2`
- `KERNEL32!ReleaseMutex` at `0x1400689eb`
- `KERNEL32!ReleaseMutex` at `0x140068a5b`
- `KERNEL32!ReleaseMutex` at `0x1400688c2`
- `KERNEL32!ReleaseMutex` at `0x1400689eb`
- `KERNEL32!ReleaseMutex` at `0x140068a5b`
- `KERNEL32!GetCurrentProcessId` at `0x1400687e1`
- `KERNEL32!GetCurrentProcessId` at `0x1400687e1`
- `KERNEL32!GetProcessHeap` at `0x1400689bb`
- `KERNEL32!GetProcessHeap` at `0x1400689bb`
- `KERNEL32!CloseHandle` at `0x1400688d3`
- `KERNEL32!CloseHandle` at `0x140068995`
- `KERNEL32!CloseHandle` at `0x1400689ad`
- `KERNEL32!CloseHandle` at `0x1400689fc`
- `KERNEL32!CloseHandle` at `0x140068a71`
- `KERNEL32!CloseHandle` at `0x1400688d3`
- `KERNEL32!CloseHandle` at `0x140068995`
- `KERNEL32!CloseHandle` at `0x1400689ad`
- `KERNEL32!CloseHandle` at `0x1400689fc`
- `KERNEL32!CloseHandle` at `0x140068a71`
- `KERNEL32!HeapFree` at `0x1400689c9`
- `KERNEL32!HeapFree` at `0x1400689c9`

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
  unsigned int v25; // r8d
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
0x1400687a8  mov     [rsp-8+arg_10], rbx
0x1400687ad  push    rbp
0x1400687ae  push    rsi
0x1400687af  push    rdi
0x1400687b0  push    r14
0x1400687b2  push    r15
0x1400687b4  lea     rbp, [rsp-160h]
0x1400687bc  sub     rsp, 260h
0x1400687c3  mov     rax, cs:__security_cookie
0x1400687ca  xor     rax, rsp
0x1400687cd  mov     [rbp+180h+var_30], rax
0x1400687d4  mov     r15, rdx
0x1400687d7  mov     qword ptr [rdx], 0
0x1400687de  mov     rbx, rcx
0x1400687e1  call    cs:__imp_GetCurrentProcessId
0x1400687e7  mov     r14d, 78h ; 'x'
0x1400687ed  mov     [rsp+280h+var_258], rbx
0x1400687f2  mov     r9d, eax
0x1400687f5  mov     [rsp+280h+var_260], r14d; int
0x1400687fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140068801  mov     edx, 104h; unsigned __int64
0x140068806  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14006880b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140068810  mov     r9d, 1F0001h; dwDesiredAccess
0x140068816  lea     rdx, [rsp+280h+Name]; lpName
0x14006881b  xor     r8d, r8d; dwFlags
0x14006881e  xor     ecx, ecx; lpMutexAttributes
0x140068820  call    cs:__imp_CreateMutexExW
0x140068826  mov     rbx, rax
0x140068829  test    rax, rax
0x14006882c  jnz     short loc_140068838
0x14006882e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140068833  jmp     loc_140068A7D
0x140068838  xor     r8d, r8d; bAlertable
0x14006883b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14006883e  mov     rcx, rbx; hHandle
0x140068841  call    cs:__imp_WaitForSingleObjectEx
0x140068847  cmp     eax, 102h
0x14006884c  jz      short loc_14006885E
0x14006884e  test    eax, 0FFFFFF7Fh
0x140068853  jnz     loc_140068AB5
0x140068859  mov     rdi, rbx
0x14006885c  jmp     short loc_140068860
0x14006885e  xor     edi, edi
0x140068860  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140068865  mov     [rsp+280h+hObject], 0
0x14006886e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140068873  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140068878  mov     esi, eax
0x14006887a  test    eax, eax
0x14006887c  jns     short loc_1400688E8
0x14006887e  mov     rcx, [rbp+188h]; this
0x140068885  mov     r9d, eax; char *
0x140068888  mov     edx, 66h ; 'f'; void *
0x14006888d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140068892  mov     rcx, [rbp+188h]; this
0x140068899  mov     r9d, esi; char *
0x14006889c  mov     edx, 6Fh ; 'o'; void *
0x1400688a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400688a6  mov     rcx, [rbp+188h]; this
0x1400688ad  mov     r9d, esi; char *
0x1400688b0  mov     edx, 12Eh; void *
0x1400688b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400688ba  test    rdi, rdi
0x1400688bd  jz      short loc_1400688D0
0x1400688bf  mov     rcx, rdi; hMutex
0x1400688c2  call    cs:__imp_ReleaseMutex
0x1400688c8  test    eax, eax
0x1400688ca  jz      loc_140068AC2
0x1400688d0  mov     rcx, rbx; hObject
0x1400688d3  call    cs:__imp_CloseHandle
0x1400688d9  test    eax, eax
0x1400688db  jz      loc_140068AD4
0x1400688e1  mov     eax, esi
0x1400688e3  jmp     loc_140068A7D
0x1400688e8  mov     rax, [rsp+280h+hObject]
0x1400688ed  lea     rcx, ds:0[rax*4]
0x1400688f5  test    rcx, rcx
0x1400688f8  jz      short loc_140068908
0x1400688fa  mov     [r15], rcx
0x1400688fd  mov     eax, [rcx]
0x1400688ff  inc     eax
0x140068901  mov     [rcx], eax
0x140068903  jmp     loc_140068A53
0x140068908  mov     rdx, r14; dwBytes
0x14006890b  mov     qword ptr [r15], 0
0x140068912  mov     ecx, 8; dwFlags
0x140068917  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14006891c  mov     rsi, rax
0x14006891f  test    rax, rax
0x140068922  jnz     short loc_140068943
0x140068924  mov     rcx, [rbp+188h]; this
0x14006892b  mov     r14d, 8007000Eh
0x140068931  mov     r9d, r14d; char *
0x140068934  mov     edx, 14Bh; void *
0x140068939  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006893e  jmp     loc_1400689CF
0x140068943  xorps   xmm0, xmm0
0x140068946  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14006894c  test    sil, 3
0x140068950  jnz     loc_140068AE6
0x140068956  mov     r9, rsi
0x140068959  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14006895e  shr     r9, 2; unsigned __int64
0x140068962  lea     rcx, [rsp+280h+hObject]; this
0x140068967  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x14006896c  mov     r14d, eax
0x14006896f  test    eax, eax
0x140068971  jns     loc_140068A0F
0x140068977  mov     rcx, [rbp+188h]; this
0x14006897e  mov     r9d, eax; char *
0x140068981  mov     edx, 14Eh; void *
0x140068986  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006898b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140068990  test    rcx, rcx
0x140068993  jz      short loc_1400689A3
0x140068995  call    cs:__imp_CloseHandle
0x14006899b  test    eax, eax
0x14006899d  jz      loc_140068AEC
0x1400689a3  mov     rcx, [rsp+280h+hObject]; hObject
0x1400689a8  test    rcx, rcx
0x1400689ab  jz      short loc_1400689BB
0x1400689ad  call    cs:__imp_CloseHandle
0x1400689b3  test    eax, eax
0x1400689b5  jz      loc_140068AFE
0x1400689bb  call    cs:__imp_GetProcessHeap
0x1400689c1  mov     r8, rsi; lpMem
0x1400689c4  xor     edx, edx; dwFlags
0x1400689c6  mov     rcx, rax; hHeap
0x1400689c9  call    cs:__imp_HeapFree
0x1400689cf  mov     rcx, [rbp+188h]; this
0x1400689d6  mov     r9d, r14d; char *
0x1400689d9  mov     edx, 137h; void *
0x1400689de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400689e3  test    rdi, rdi
0x1400689e6  jz      short loc_1400689F9
0x1400689e8  mov     rcx, rdi; hMutex
0x1400689eb  call    cs:__imp_ReleaseMutex
0x1400689f1  test    eax, eax
0x1400689f3  jz      loc_140068B10
0x1400689f9  mov     rcx, rbx; hObject
0x1400689fc  call    cs:__imp_CloseHandle
0x140068a02  test    eax, eax
0x140068a04  jz      loc_140068B22
0x140068a0a  mov     eax, r14d
0x140068a0d  jmp     short loc_140068A7D
0x140068a0f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140068a14  xor     edx, edx; Val
0x140068a16  mov     dword ptr [rsi], 1
0x140068a1c  lea     rcx, [rsi+22h]; void *
0x140068a20  mov     [rsi+8], rbx
0x140068a24  movdqu  xmmword ptr [rsi+10h], xmm0
0x140068a29  lea     r8d, [rdx+56h]; Size
0x140068a2d  call    memset_0
0x140068a32  xor     edx, edx; Val
0x140068a34  mov     word ptr [rsi+20h], 58h ; 'X'
0x140068a3a  lea     rcx, [rsi+28h]; void *
0x140068a3e  mov     dword ptr [rsi+24h], 1
0x140068a45  lea     r8d, [rdx+50h]; Size
0x140068a49  call    memset_0
0x140068a4e  xor     ebx, ebx
0x140068a50  mov     [r15], rsi
0x140068a53  test    rdi, rdi
0x140068a56  jz      short loc_140068A69
0x140068a58  mov     rcx, rdi; hMutex
0x140068a5b  call    cs:__imp_ReleaseMutex
0x140068a61  test    eax, eax
0x140068a63  jz      loc_140068B34
0x140068a69  test    rbx, rbx
0x140068a6c  jz      short loc_140068A7B
0x140068a6e  mov     rcx, rbx; hObject
0x140068a71  call    cs:__imp_CloseHandle
0x140068a77  test    eax, eax
0x140068a79  jz      short loc_140068AA3
0x140068a7b  xor     eax, eax
0x140068a7d  mov     rcx, [rbp+180h+var_30]
0x140068a84  xor     rcx, rsp; StackCookie
0x140068a87  call    __security_check_cookie
0x140068a8c  mov     rbx, [rsp+280h+arg_10]
0x140068a94  add     rsp, 260h
0x140068a9b  pop     r15
0x140068a9d  pop     r14
0x140068a9f  pop     rdi
0x140068aa0  pop     rsi
0x140068aa1  pop     rbp
0x140068aa2  retn
0x140068aa3  mov     rcx, [rbp+188h]; this
0x140068aaa  mov     edx, 0A0Bh; void *
0x140068aaf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068ab5  mov     rcx, [rbp+188h]; this
0x140068abc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140068ac2  mov     rcx, [rbp+188h]; this
0x140068ac9  mov     edx, 0A15h; void *
0x140068ace  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068ad4  mov     rcx, [rbp+188h]; this
0x140068adb  mov     edx, 0A0Bh; void *
0x140068ae0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068ae6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140068aec  mov     rcx, [rbp+188h]; this
0x140068af3  mov     edx, 0A0Bh; void *
0x140068af8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068afe  mov     rcx, [rbp+188h]; this
0x140068b05  mov     edx, 0A0Bh; void *
0x140068b0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068b10  mov     rcx, [rbp+188h]; this
0x140068b17  mov     edx, 0A15h; void *
0x140068b1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068b22  mov     rcx, [rbp+188h]; this
0x140068b29  mov     edx, 0A0Bh; void *
0x140068b2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140068b34  mov     rcx, [rbp+188h]; this
0x140068b3b  mov     edx, 0A15h; void *
0x140068b40  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
