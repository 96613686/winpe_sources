# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800113dc`
- end: `0x18001177a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001226c`

## callees

- `0x180006c30`
- `0x1800113dc`
- `0x180011780`
- `0x1800119c0`
- `0x180012008`
- `0x180012b30`
- `0x180012de4`
- `0x180013094`
- `0x18001344c`
- `0x18001345c`
- `0x18001358e`
- `0x1800135c0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180011415`
- `KERNEL32!GetCurrentProcessId` at `0x180011415`
- `KERNEL32!GetProcessHeap` at `0x1800115ef`
- `KERNEL32!GetProcessHeap` at `0x1800115ef`
- `KERNEL32!HeapFree` at `0x1800115fd`
- `KERNEL32!HeapFree` at `0x1800115fd`
- `KERNEL32!CloseHandle` at `0x180011507`
- `KERNEL32!CloseHandle` at `0x1800115c9`
- `KERNEL32!CloseHandle` at `0x1800115e1`
- `KERNEL32!CloseHandle` at `0x180011630`
- `KERNEL32!CloseHandle` at `0x1800116a5`
- `KERNEL32!CloseHandle` at `0x180011507`
- `KERNEL32!CloseHandle` at `0x1800115c9`
- `KERNEL32!CloseHandle` at `0x1800115e1`
- `KERNEL32!CloseHandle` at `0x180011630`
- `KERNEL32!CloseHandle` at `0x1800116a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180011475`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180011475`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800114f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001161f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001168f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800114f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001161f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001168f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011454`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180011454`

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
0x1800113dc  mov     [rsp-8+arg_10], rbx
0x1800113e1  push    rbp
0x1800113e2  push    rsi
0x1800113e3  push    rdi
0x1800113e4  push    r14
0x1800113e6  push    r15
0x1800113e8  lea     rbp, [rsp-160h]
0x1800113f0  sub     rsp, 260h
0x1800113f7  mov     rax, cs:__security_cookie
0x1800113fe  xor     rax, rsp
0x180011401  mov     [rbp+180h+var_30], rax
0x180011408  mov     r15, rdx
0x18001140b  mov     qword ptr [rdx], 0
0x180011412  mov     rbx, rcx
0x180011415  call    cs:__imp_GetCurrentProcessId
0x18001141b  mov     r14d, 78h ; 'x'
0x180011421  mov     [rsp+280h+var_258], rbx
0x180011426  mov     r9d, eax
0x180011429  mov     [rsp+280h+var_260], r14d; int
0x18001142e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180011435  mov     edx, 104h; unsigned __int64
0x18001143a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001143f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011444  mov     r9d, 1F0001h; dwDesiredAccess
0x18001144a  lea     rdx, [rsp+280h+Name]; lpName
0x18001144f  xor     r8d, r8d; dwFlags
0x180011452  xor     ecx, ecx; lpMutexAttributes
0x180011454  call    cs:__imp_CreateMutexExW
0x18001145a  mov     rbx, rax
0x18001145d  test    rax, rax
0x180011460  jnz     short loc_18001146C
0x180011462  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180011467  jmp     loc_1800116B1
0x18001146c  xor     r8d, r8d; bAlertable
0x18001146f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011472  mov     rcx, rbx; hHandle
0x180011475  call    cs:__imp_WaitForSingleObjectEx
0x18001147b  cmp     eax, 102h
0x180011480  jz      short loc_180011492
0x180011482  test    eax, 0FFFFFF7Fh
0x180011487  jnz     loc_1800116E9
0x18001148d  mov     rdi, rbx
0x180011490  jmp     short loc_180011494
0x180011492  xor     edi, edi
0x180011494  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180011499  mov     [rsp+280h+hObject], 0
0x1800114a2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800114a7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800114ac  mov     esi, eax
0x1800114ae  test    eax, eax
0x1800114b0  jns     short loc_18001151C
0x1800114b2  mov     rcx, [rbp+188h]; this
0x1800114b9  mov     r9d, eax; char *
0x1800114bc  mov     edx, 66h ; 'f'; void *
0x1800114c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114c6  mov     rcx, [rbp+188h]; this
0x1800114cd  mov     r9d, esi; char *
0x1800114d0  mov     edx, 6Fh ; 'o'; void *
0x1800114d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114da  mov     rcx, [rbp+188h]; this
0x1800114e1  mov     r9d, esi; char *
0x1800114e4  mov     edx, 12Eh; void *
0x1800114e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114ee  test    rdi, rdi
0x1800114f1  jz      short loc_180011504
0x1800114f3  mov     rcx, rdi; hMutex
0x1800114f6  call    cs:__imp_ReleaseMutex
0x1800114fc  test    eax, eax
0x1800114fe  jz      loc_1800116F6
0x180011504  mov     rcx, rbx; hObject
0x180011507  call    cs:__imp_CloseHandle
0x18001150d  test    eax, eax
0x18001150f  jz      loc_180011708
0x180011515  mov     eax, esi
0x180011517  jmp     loc_1800116B1
0x18001151c  mov     rax, [rsp+280h+hObject]
0x180011521  lea     rcx, ds:0[rax*4]
0x180011529  test    rcx, rcx
0x18001152c  jz      short loc_18001153C
0x18001152e  mov     [r15], rcx
0x180011531  mov     eax, [rcx]
0x180011533  inc     eax
0x180011535  mov     [rcx], eax
0x180011537  jmp     loc_180011687
0x18001153c  mov     rdx, r14; dwBytes
0x18001153f  mov     qword ptr [r15], 0
0x180011546  mov     ecx, 8; dwFlags
0x18001154b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011550  mov     rsi, rax
0x180011553  test    rax, rax
0x180011556  jnz     short loc_180011577
0x180011558  mov     rcx, [rbp+188h]; this
0x18001155f  mov     r14d, 8007000Eh
0x180011565  mov     r9d, r14d; char *
0x180011568  mov     edx, 14Bh; void *
0x18001156d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011572  jmp     loc_180011603
0x180011577  xorps   xmm0, xmm0
0x18001157a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180011580  test    sil, 3
0x180011584  jnz     loc_18001171A
0x18001158a  mov     r9, rsi
0x18001158d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180011592  shr     r9, 2; unsigned __int64
0x180011596  lea     rcx, [rsp+280h+hObject]; this
0x18001159b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800115a0  mov     r14d, eax
0x1800115a3  test    eax, eax
0x1800115a5  jns     loc_180011643
0x1800115ab  mov     rcx, [rbp+188h]; this
0x1800115b2  mov     r9d, eax; char *
0x1800115b5  mov     edx, 14Eh; void *
0x1800115ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115bf  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800115c4  test    rcx, rcx
0x1800115c7  jz      short loc_1800115D7
0x1800115c9  call    cs:__imp_CloseHandle
0x1800115cf  test    eax, eax
0x1800115d1  jz      loc_180011720
0x1800115d7  mov     rcx, [rsp+280h+hObject]; hObject
0x1800115dc  test    rcx, rcx
0x1800115df  jz      short loc_1800115EF
0x1800115e1  call    cs:__imp_CloseHandle
0x1800115e7  test    eax, eax
0x1800115e9  jz      loc_180011732
0x1800115ef  call    cs:__imp_GetProcessHeap
0x1800115f5  mov     r8, rsi; lpMem
0x1800115f8  xor     edx, edx; dwFlags
0x1800115fa  mov     rcx, rax; hHeap
0x1800115fd  call    cs:__imp_HeapFree
0x180011603  mov     rcx, [rbp+188h]; this
0x18001160a  mov     r9d, r14d; char *
0x18001160d  mov     edx, 137h; void *
0x180011612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011617  test    rdi, rdi
0x18001161a  jz      short loc_18001162D
0x18001161c  mov     rcx, rdi; hMutex
0x18001161f  call    cs:__imp_ReleaseMutex
0x180011625  test    eax, eax
0x180011627  jz      loc_180011744
0x18001162d  mov     rcx, rbx; hObject
0x180011630  call    cs:__imp_CloseHandle
0x180011636  test    eax, eax
0x180011638  jz      loc_180011756
0x18001163e  mov     eax, r14d
0x180011641  jmp     short loc_1800116B1
0x180011643  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180011648  xor     edx, edx; Val
0x18001164a  mov     dword ptr [rsi], 1
0x180011650  lea     rcx, [rsi+22h]; void *
0x180011654  mov     [rsi+8], rbx
0x180011658  movdqu  xmmword ptr [rsi+10h], xmm0
0x18001165d  lea     r8d, [rdx+56h]; Size
0x180011661  call    memset_0
0x180011666  xor     edx, edx; Val
0x180011668  mov     word ptr [rsi+20h], 58h ; 'X'
0x18001166e  lea     rcx, [rsi+28h]; void *
0x180011672  mov     dword ptr [rsi+24h], 1
0x180011679  lea     r8d, [rdx+50h]; Size
0x18001167d  call    memset_0
0x180011682  xor     ebx, ebx
0x180011684  mov     [r15], rsi
0x180011687  test    rdi, rdi
0x18001168a  jz      short loc_18001169D
0x18001168c  mov     rcx, rdi; hMutex
0x18001168f  call    cs:__imp_ReleaseMutex
0x180011695  test    eax, eax
0x180011697  jz      loc_180011768
0x18001169d  test    rbx, rbx
0x1800116a0  jz      short loc_1800116AF
0x1800116a2  mov     rcx, rbx; hObject
0x1800116a5  call    cs:__imp_CloseHandle
0x1800116ab  test    eax, eax
0x1800116ad  jz      short loc_1800116D7
0x1800116af  xor     eax, eax
0x1800116b1  mov     rcx, [rbp+180h+var_30]
0x1800116b8  xor     rcx, rsp; StackCookie
0x1800116bb  call    __security_check_cookie
0x1800116c0  mov     rbx, [rsp+280h+arg_10]
0x1800116c8  add     rsp, 260h
0x1800116cf  pop     r15
0x1800116d1  pop     r14
0x1800116d3  pop     rdi
0x1800116d4  pop     rsi
0x1800116d5  pop     rbp
0x1800116d6  retn
0x1800116d7  mov     rcx, [rbp+188h]; this
0x1800116de  mov     edx, 0A0Bh; void *
0x1800116e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800116e9  mov     rcx, [rbp+188h]; this
0x1800116f0  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800116f6  mov     rcx, [rbp+188h]; this
0x1800116fd  mov     edx, 0A15h; void *
0x180011702  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011708  mov     rcx, [rbp+188h]; this
0x18001170f  mov     edx, 0A0Bh; void *
0x180011714  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001171a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011720  mov     rcx, [rbp+188h]; this
0x180011727  mov     edx, 0A0Bh; void *
0x18001172c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011732  mov     rcx, [rbp+188h]; this
0x180011739  mov     edx, 0A0Bh; void *
0x18001173e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011744  mov     rcx, [rbp+188h]; this
0x18001174b  mov     edx, 0A15h; void *
0x180011750  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011756  mov     rcx, [rbp+188h]; this
0x18001175d  mov     edx, 0A0Bh; void *
0x180011762  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011768  mov     rcx, [rbp+188h]; this
0x18001176f  mov     edx, 0A15h; void *
0x180011774  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
