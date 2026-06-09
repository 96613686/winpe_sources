# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140008f9c`
- end: `0x140009364`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000a764`

## callees

- `0x1400023d0`
- `0x140002fcc`
- `0x140004664`
- `0x140006008`
- `0x140008f9c`
- `0x140009764`
- `0x140009bc8`
- `0x14000a628`
- `0x14000ac10`
- `0x14000c188`
- `0x14000c81c`
- `0x14000db34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400091e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400091e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008fd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140008fd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000921a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000928f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400090dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400091c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000921a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000928f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009035`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140009035`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400090cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009209`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009279`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400090cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009209`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140009279`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009014`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140009014`

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
  wil::details::in1diag4 *v22; // rcx
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
      wil::details::in1diag4::_FailFastImmediate_Unexpected(v22);
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
0x140008f9c  mov     [rsp-8+arg_10], rbx
0x140008fa1  push    rbp
0x140008fa2  push    rsi
0x140008fa3  push    rdi
0x140008fa4  push    r14
0x140008fa6  push    r15
0x140008fa8  lea     rbp, [rsp-160h]
0x140008fb0  sub     rsp, 260h
0x140008fb7  mov     rax, cs:__security_cookie
0x140008fbe  xor     rax, rsp
0x140008fc1  mov     [rbp+180h+var_30], rax
0x140008fc8  mov     r15, rdx
0x140008fcb  mov     qword ptr [rdx], 0
0x140008fd2  mov     rbx, rcx
0x140008fd5  call    cs:__imp_GetCurrentProcessId
0x140008fdb  mov     r14d, 78h ; 'x'
0x140008fe1  mov     [rsp+280h+var_258], rbx
0x140008fe6  mov     r9d, eax
0x140008fe9  mov     [rsp+280h+var_260], r14d; int
0x140008fee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140008ff5  mov     edx, 104h; unsigned __int64
0x140008ffa  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140008fff  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140009004  mov     r9d, 1F0001h; dwDesiredAccess
0x14000900a  lea     rdx, [rsp+280h+Name]; lpName
0x14000900f  xor     r8d, r8d; dwFlags
0x140009012  xor     ecx, ecx; lpMutexAttributes
0x140009014  call    cs:__imp_CreateMutexExW
0x14000901a  mov     rbx, rax
0x14000901d  test    rax, rax
0x140009020  jnz     short loc_14000902C
0x140009022  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009027  jmp     loc_14000929B
0x14000902c  xor     r8d, r8d; bAlertable
0x14000902f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140009032  mov     rcx, rbx; hHandle
0x140009035  call    cs:__imp_WaitForSingleObjectEx
0x14000903b  cmp     eax, 102h
0x140009040  jz      short loc_140009052
0x140009042  test    eax, 0FFFFFF7Fh
0x140009047  jnz     loc_1400092D3
0x14000904d  mov     rdi, rbx
0x140009050  jmp     short loc_140009054
0x140009052  xor     edi, edi
0x140009054  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140009059  mov     [rsp+280h+hObject], 0
0x140009062  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140009067  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x14000906c  mov     esi, eax
0x14000906e  test    eax, eax
0x140009070  jns     short loc_1400090F1
0x140009072  mov     rcx, [rbp+188h]; this
0x140009079  lea     r8, aWil; "wil"
0x140009080  mov     r9d, eax; char *
0x140009083  mov     edx, 66h ; 'f'; void *
0x140009088  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000908d  mov     rcx, [rbp+188h]; this
0x140009094  lea     r8, aWil; "wil"
0x14000909b  mov     r9d, esi; char *
0x14000909e  mov     edx, 6Fh ; 'o'; void *
0x1400090a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400090a8  mov     rcx, [rbp+188h]; this
0x1400090af  lea     r8, aWil; "wil"
0x1400090b6  mov     r9d, esi; char *
0x1400090b9  mov     edx, 12Eh; void *
0x1400090be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400090c3  test    rdi, rdi
0x1400090c6  jz      short loc_1400090D9
0x1400090c8  mov     rcx, rdi; hMutex
0x1400090cb  call    cs:__imp_ReleaseMutex
0x1400090d1  test    eax, eax
0x1400090d3  jz      loc_1400092E0
0x1400090d9  mov     rcx, rbx; hObject
0x1400090dc  call    cs:__imp_CloseHandle
0x1400090e2  test    eax, eax
0x1400090e4  jz      loc_1400092F2
0x1400090ea  mov     eax, esi
0x1400090ec  jmp     loc_14000929B
0x1400090f1  mov     rax, [rsp+280h+hObject]
0x1400090f6  lea     rcx, ds:0[rax*4]
0x1400090fe  test    rcx, rcx
0x140009101  jz      short loc_140009111
0x140009103  mov     [r15], rcx
0x140009106  mov     eax, [rcx]
0x140009108  inc     eax
0x14000910a  mov     [rcx], eax
0x14000910c  jmp     loc_140009271
0x140009111  mov     rdx, r14; dwBytes
0x140009114  mov     qword ptr [r15], 0
0x14000911b  mov     ecx, 8; dwFlags
0x140009120  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009125  mov     rsi, rax
0x140009128  test    rax, rax
0x14000912b  jnz     short loc_140009153
0x14000912d  mov     rcx, [rbp+188h]; this
0x140009134  lea     r8, aWil; "wil"
0x14000913b  mov     r14d, 8007000Eh
0x140009141  mov     edx, 14Bh; void *
0x140009146  mov     r9d, r14d; char *
0x140009149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000914e  jmp     loc_1400091E6
0x140009153  xorps   xmm0, xmm0
0x140009156  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x14000915c  test    sil, 3
0x140009160  jnz     loc_140009304
0x140009166  mov     r9, rsi
0x140009169  lea     rdx, [rsp+280h+Name]; wchar_t *
0x14000916e  shr     r9, 2; unsigned __int64
0x140009172  lea     rcx, [rsp+280h+hObject]; this
0x140009177  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x14000917c  mov     r14d, eax
0x14000917f  test    eax, eax
0x140009181  jns     loc_14000922D
0x140009187  mov     rcx, [rbp+188h]; this
0x14000918e  lea     r8, aWil; "wil"
0x140009195  mov     r9d, eax; char *
0x140009198  mov     edx, 14Eh; void *
0x14000919d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091a2  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400091a7  test    rcx, rcx
0x1400091aa  jz      short loc_1400091BA
0x1400091ac  call    cs:__imp_CloseHandle
0x1400091b2  test    eax, eax
0x1400091b4  jz      loc_14000930A
0x1400091ba  mov     rcx, [rsp+280h+hObject]; hObject
0x1400091bf  test    rcx, rcx
0x1400091c2  jz      short loc_1400091D2
0x1400091c4  call    cs:__imp_CloseHandle
0x1400091ca  test    eax, eax
0x1400091cc  jz      loc_14000931C
0x1400091d2  call    cs:__imp_GetProcessHeap
0x1400091d8  mov     r8, rsi; lpMem
0x1400091db  xor     edx, edx; dwFlags
0x1400091dd  mov     rcx, rax; hHeap
0x1400091e0  call    cs:__imp_HeapFree
0x1400091e6  mov     rcx, [rbp+188h]; this
0x1400091ed  lea     r8, aWil; "wil"
0x1400091f4  mov     r9d, r14d; char *
0x1400091f7  mov     edx, 137h; void *
0x1400091fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009201  test    rdi, rdi
0x140009204  jz      short loc_140009217
0x140009206  mov     rcx, rdi; hMutex
0x140009209  call    cs:__imp_ReleaseMutex
0x14000920f  test    eax, eax
0x140009211  jz      loc_14000932E
0x140009217  mov     rcx, rbx; hObject
0x14000921a  call    cs:__imp_CloseHandle
0x140009220  test    eax, eax
0x140009222  jz      loc_140009340
0x140009228  mov     eax, r14d
0x14000922b  jmp     short loc_14000929B
0x14000922d  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140009232  xor     edx, edx; Val
0x140009234  mov     dword ptr [rsi], 1
0x14000923a  lea     rcx, [rsi+22h]; void *
0x14000923e  mov     [rsi+8], rbx
0x140009242  movdqu  xmmword ptr [rsi+10h], xmm0
0x140009247  lea     r8d, [rdx+56h]; Size
0x14000924b  call    memset_0
0x140009250  xor     edx, edx; Val
0x140009252  mov     word ptr [rsi+20h], 58h ; 'X'
0x140009258  lea     rcx, [rsi+28h]; void *
0x14000925c  mov     dword ptr [rsi+24h], 1
0x140009263  lea     r8d, [rdx+50h]; Size
0x140009267  call    memset_0
0x14000926c  xor     ebx, ebx
0x14000926e  mov     [r15], rsi
0x140009271  test    rdi, rdi
0x140009274  jz      short loc_140009287
0x140009276  mov     rcx, rdi; hMutex
0x140009279  call    cs:__imp_ReleaseMutex
0x14000927f  test    eax, eax
0x140009281  jz      loc_140009352
0x140009287  test    rbx, rbx
0x14000928a  jz      short loc_140009299
0x14000928c  mov     rcx, rbx; hObject
0x14000928f  call    cs:__imp_CloseHandle
0x140009295  test    eax, eax
0x140009297  jz      short loc_1400092C1
0x140009299  xor     eax, eax
0x14000929b  mov     rcx, [rbp+180h+var_30]
0x1400092a2  xor     rcx, rsp; StackCookie
0x1400092a5  call    __security_check_cookie
0x1400092aa  mov     rbx, [rsp+280h+arg_10]
0x1400092b2  add     rsp, 260h
0x1400092b9  pop     r15
0x1400092bb  pop     r14
0x1400092bd  pop     rdi
0x1400092be  pop     rsi
0x1400092bf  pop     rbp
0x1400092c0  retn
0x1400092c1  mov     rcx, [rbp+188h]; this
0x1400092c8  mov     edx, 0A0Bh; void *
0x1400092cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400092d3  mov     rcx, [rbp+188h]; this
0x1400092da  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1400092e0  mov     rcx, [rbp+188h]; this
0x1400092e7  mov     edx, 0A15h; void *
0x1400092ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400092f2  mov     rcx, [rbp+188h]; this
0x1400092f9  mov     edx, 0A0Bh; void *
0x1400092fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009304  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
0x14000930a  mov     rcx, [rbp+188h]; this
0x140009311  mov     edx, 0A0Bh; void *
0x140009316  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000931c  mov     rcx, [rbp+188h]; this
0x140009323  mov     edx, 0A0Bh; void *
0x140009328  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000932e  mov     rcx, [rbp+188h]; this
0x140009335  mov     edx, 0A15h; void *
0x14000933a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009340  mov     rcx, [rbp+188h]; this
0x140009347  mov     edx, 0A0Bh; void *
0x14000934c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140009352  mov     rcx, [rbp+188h]; this
0x140009359  mov     edx, 0A15h; void *
0x14000935e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
