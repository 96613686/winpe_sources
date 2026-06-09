# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006108`
- end: `0x1800064a6`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18000aacc`

## callees

- `0x180006108`
- `0x180007134`
- `0x180007a1c`
- `0x180009d44`
- `0x18000c118`
- `0x18000df84`
- `0x1800105f8`
- `0x180010af4`
- `0x18001138c`
- `0x18001139c`
- `0x1800142d2`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180006141`
- `KERNEL32!GetCurrentProcessId` at `0x180006141`
- `KERNEL32!GetProcessHeap` at `0x18000631b`
- `KERNEL32!GetProcessHeap` at `0x18000631b`
- `KERNEL32!CreateMutexExW` at `0x180006180`
- `KERNEL32!CreateMutexExW` at `0x180006180`
- `KERNEL32!CloseHandle` at `0x180006233`
- `KERNEL32!CloseHandle` at `0x1800062f5`
- `KERNEL32!CloseHandle` at `0x18000630d`
- `KERNEL32!CloseHandle` at `0x18000635c`
- `KERNEL32!CloseHandle` at `0x1800063d1`
- `KERNEL32!CloseHandle` at `0x180006233`
- `KERNEL32!CloseHandle` at `0x1800062f5`
- `KERNEL32!CloseHandle` at `0x18000630d`
- `KERNEL32!CloseHandle` at `0x18000635c`
- `KERNEL32!CloseHandle` at `0x1800063d1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800061a1`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800061a1`
- `KERNEL32!ReleaseMutex` at `0x180006222`
- `KERNEL32!ReleaseMutex` at `0x18000634b`
- `KERNEL32!ReleaseMutex` at `0x1800063bb`
- `KERNEL32!ReleaseMutex` at `0x180006222`
- `KERNEL32!ReleaseMutex` at `0x18000634b`
- `KERNEL32!ReleaseMutex` at `0x1800063bb`
- `KERNEL32!HeapFree` at `0x180006329`
- `KERNEL32!HeapFree` at `0x180006329`

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
0x180006108  mov     [rsp-8+arg_10], rbx
0x18000610d  push    rbp
0x18000610e  push    rsi
0x18000610f  push    rdi
0x180006110  push    r14
0x180006112  push    r15
0x180006114  lea     rbp, [rsp-160h]
0x18000611c  sub     rsp, 260h
0x180006123  mov     rax, cs:__security_cookie
0x18000612a  xor     rax, rsp
0x18000612d  mov     [rbp+180h+var_30], rax
0x180006134  mov     r15, rdx
0x180006137  mov     qword ptr [rdx], 0
0x18000613e  mov     rbx, rcx
0x180006141  call    cs:__imp_GetCurrentProcessId
0x180006147  mov     r14d, 78h ; 'x'
0x18000614d  mov     [rsp+280h+var_258], rbx
0x180006152  mov     r9d, eax
0x180006155  mov     [rsp+280h+var_260], r14d; int
0x18000615a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180006161  mov     edx, 104h; unsigned __int64
0x180006166  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000616b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006170  mov     r9d, 1F0001h; dwDesiredAccess
0x180006176  lea     rdx, [rsp+280h+Name]; lpName
0x18000617b  xor     r8d, r8d; dwFlags
0x18000617e  xor     ecx, ecx; lpMutexAttributes
0x180006180  call    cs:__imp_CreateMutexExW
0x180006186  mov     rbx, rax
0x180006189  test    rax, rax
0x18000618c  jnz     short loc_180006198
0x18000618e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180006193  jmp     loc_1800063DD
0x180006198  xor     r8d, r8d; bAlertable
0x18000619b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000619e  mov     rcx, rbx; hHandle
0x1800061a1  call    cs:__imp_WaitForSingleObjectEx
0x1800061a7  cmp     eax, 102h
0x1800061ac  jz      short loc_1800061BE
0x1800061ae  test    eax, 0FFFFFF7Fh
0x1800061b3  jnz     loc_180006415
0x1800061b9  mov     rdi, rbx
0x1800061bc  jmp     short loc_1800061C0
0x1800061be  xor     edi, edi
0x1800061c0  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1800061c5  mov     [rsp+280h+hObject], 0
0x1800061ce  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800061d3  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800061d8  mov     esi, eax
0x1800061da  test    eax, eax
0x1800061dc  jns     short loc_180006248
0x1800061de  mov     rcx, [rbp+188h]; this
0x1800061e5  mov     r9d, eax; char *
0x1800061e8  mov     edx, 66h ; 'f'; void *
0x1800061ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061f2  mov     rcx, [rbp+188h]; this
0x1800061f9  mov     r9d, esi; char *
0x1800061fc  mov     edx, 6Fh ; 'o'; void *
0x180006201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006206  mov     rcx, [rbp+188h]; this
0x18000620d  mov     r9d, esi; char *
0x180006210  mov     edx, 12Eh; void *
0x180006215  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000621a  test    rdi, rdi
0x18000621d  jz      short loc_180006230
0x18000621f  mov     rcx, rdi; hMutex
0x180006222  call    cs:__imp_ReleaseMutex
0x180006228  test    eax, eax
0x18000622a  jz      loc_180006422
0x180006230  mov     rcx, rbx; hObject
0x180006233  call    cs:__imp_CloseHandle
0x180006239  test    eax, eax
0x18000623b  jz      loc_180006434
0x180006241  mov     eax, esi
0x180006243  jmp     loc_1800063DD
0x180006248  mov     rax, [rsp+280h+hObject]
0x18000624d  lea     rcx, ds:0[rax*4]
0x180006255  test    rcx, rcx
0x180006258  jz      short loc_180006268
0x18000625a  mov     [r15], rcx
0x18000625d  mov     eax, [rcx]
0x18000625f  inc     eax
0x180006261  mov     [rcx], eax
0x180006263  jmp     loc_1800063B3
0x180006268  mov     rdx, r14; dwBytes
0x18000626b  mov     qword ptr [r15], 0
0x180006272  mov     ecx, 8; dwFlags
0x180006277  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000627c  mov     rsi, rax
0x18000627f  test    rax, rax
0x180006282  jnz     short loc_1800062A3
0x180006284  mov     rcx, [rbp+188h]; this
0x18000628b  mov     r14d, 8007000Eh
0x180006291  mov     r9d, r14d; char *
0x180006294  mov     edx, 14Bh; void *
0x180006299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000629e  jmp     loc_18000632F
0x1800062a3  xorps   xmm0, xmm0
0x1800062a6  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1800062ac  test    sil, 3
0x1800062b0  jnz     loc_180006446
0x1800062b6  mov     r9, rsi
0x1800062b9  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1800062be  shr     r9, 2; unsigned __int64
0x1800062c2  lea     rcx, [rsp+280h+hObject]; this
0x1800062c7  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800062cc  mov     r14d, eax
0x1800062cf  test    eax, eax
0x1800062d1  jns     loc_18000636F
0x1800062d7  mov     rcx, [rbp+188h]; this
0x1800062de  mov     r9d, eax; char *
0x1800062e1  mov     edx, 14Eh; void *
0x1800062e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062eb  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800062f0  test    rcx, rcx
0x1800062f3  jz      short loc_180006303
0x1800062f5  call    cs:__imp_CloseHandle
0x1800062fb  test    eax, eax
0x1800062fd  jz      loc_18000644C
0x180006303  mov     rcx, [rsp+280h+hObject]; hObject
0x180006308  test    rcx, rcx
0x18000630b  jz      short loc_18000631B
0x18000630d  call    cs:__imp_CloseHandle
0x180006313  test    eax, eax
0x180006315  jz      loc_18000645E
0x18000631b  call    cs:__imp_GetProcessHeap
0x180006321  mov     r8, rsi; lpMem
0x180006324  xor     edx, edx; dwFlags
0x180006326  mov     rcx, rax; hHeap
0x180006329  call    cs:__imp_HeapFree
0x18000632f  mov     rcx, [rbp+188h]; this
0x180006336  mov     r9d, r14d; char *
0x180006339  mov     edx, 137h; void *
0x18000633e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006343  test    rdi, rdi
0x180006346  jz      short loc_180006359
0x180006348  mov     rcx, rdi; hMutex
0x18000634b  call    cs:__imp_ReleaseMutex
0x180006351  test    eax, eax
0x180006353  jz      loc_180006470
0x180006359  mov     rcx, rbx; hObject
0x18000635c  call    cs:__imp_CloseHandle
0x180006362  test    eax, eax
0x180006364  jz      loc_180006482
0x18000636a  mov     eax, r14d
0x18000636d  jmp     short loc_1800063DD
0x18000636f  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180006374  xor     edx, edx; Val
0x180006376  mov     dword ptr [rsi], 1
0x18000637c  lea     rcx, [rsi+22h]; void *
0x180006380  mov     [rsi+8], rbx
0x180006384  movdqu  xmmword ptr [rsi+10h], xmm0
0x180006389  lea     r8d, [rdx+56h]; Size
0x18000638d  call    memset_0
0x180006392  xor     edx, edx; Val
0x180006394  mov     word ptr [rsi+20h], 58h ; 'X'
0x18000639a  lea     rcx, [rsi+28h]; void *
0x18000639e  mov     dword ptr [rsi+24h], 1
0x1800063a5  lea     r8d, [rdx+50h]; Size
0x1800063a9  call    memset_0
0x1800063ae  xor     ebx, ebx
0x1800063b0  mov     [r15], rsi
0x1800063b3  test    rdi, rdi
0x1800063b6  jz      short loc_1800063C9
0x1800063b8  mov     rcx, rdi; hMutex
0x1800063bb  call    cs:__imp_ReleaseMutex
0x1800063c1  test    eax, eax
0x1800063c3  jz      loc_180006494
0x1800063c9  test    rbx, rbx
0x1800063cc  jz      short loc_1800063DB
0x1800063ce  mov     rcx, rbx; hObject
0x1800063d1  call    cs:__imp_CloseHandle
0x1800063d7  test    eax, eax
0x1800063d9  jz      short loc_180006403
0x1800063db  xor     eax, eax
0x1800063dd  mov     rcx, [rbp+180h+var_30]
0x1800063e4  xor     rcx, rsp; StackCookie
0x1800063e7  call    __security_check_cookie
0x1800063ec  mov     rbx, [rsp+280h+arg_10]
0x1800063f4  add     rsp, 260h
0x1800063fb  pop     r15
0x1800063fd  pop     r14
0x1800063ff  pop     rdi
0x180006400  pop     rsi
0x180006401  pop     rbp
0x180006402  retn
0x180006403  mov     rcx, [rbp+188h]; this
0x18000640a  mov     edx, 0A0Bh; void *
0x18000640f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006415  mov     rcx, [rbp+188h]; this
0x18000641c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180006422  mov     rcx, [rbp+188h]; this
0x180006429  mov     edx, 0A15h; void *
0x18000642e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006434  mov     rcx, [rbp+188h]; this
0x18000643b  mov     edx, 0A0Bh; void *
0x180006440  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006446  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000644c  mov     rcx, [rbp+188h]; this
0x180006453  mov     edx, 0A0Bh; void *
0x180006458  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000645e  mov     rcx, [rbp+188h]; this
0x180006465  mov     edx, 0A0Bh; void *
0x18000646a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006470  mov     rcx, [rbp+188h]; this
0x180006477  mov     edx, 0A15h; void *
0x18000647c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006482  mov     rcx, [rbp+188h]; this
0x180006489  mov     edx, 0A0Bh; void *
0x18000648e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006494  mov     rcx, [rbp+188h]; this
0x18000649b  mov     edx, 0A15h; void *
0x1800064a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
