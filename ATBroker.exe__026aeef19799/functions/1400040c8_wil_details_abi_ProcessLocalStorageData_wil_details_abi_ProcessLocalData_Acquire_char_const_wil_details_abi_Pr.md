# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400040c8`
- end: `0x140004490`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1400063f4`

## callees

- `0x1400040c8`
- `0x140004974`
- `0x140004eb8`
- `0x140006190`
- `0x1400075c8`
- `0x140009384`
- `0x140009aa8`
- `0x140009e9c`
- `0x14000a764`
- `0x14000a774`
- `0x140015ac2`
- `0x140015b00`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000430c`
- `KERNEL32!HeapFree` at `0x14000430c`
- `KERNEL32!ReleaseMutex` at `0x1400041f7`
- `KERNEL32!ReleaseMutex` at `0x140004335`
- `KERNEL32!ReleaseMutex` at `0x1400043a5`
- `KERNEL32!ReleaseMutex` at `0x1400041f7`
- `KERNEL32!ReleaseMutex` at `0x140004335`
- `KERNEL32!ReleaseMutex` at `0x1400043a5`
- `KERNEL32!WaitForSingleObjectEx` at `0x140004161`
- `KERNEL32!WaitForSingleObjectEx` at `0x140004161`
- `KERNEL32!CloseHandle` at `0x140004208`
- `KERNEL32!CloseHandle` at `0x1400042d8`
- `KERNEL32!CloseHandle` at `0x1400042f0`
- `KERNEL32!CloseHandle` at `0x140004346`
- `KERNEL32!CloseHandle` at `0x1400043bb`
- `KERNEL32!CloseHandle` at `0x140004208`
- `KERNEL32!CloseHandle` at `0x1400042d8`
- `KERNEL32!CloseHandle` at `0x1400042f0`
- `KERNEL32!CloseHandle` at `0x140004346`
- `KERNEL32!CloseHandle` at `0x1400043bb`
- `KERNEL32!CreateMutexExW` at `0x140004140`
- `KERNEL32!CreateMutexExW` at `0x140004140`
- `KERNEL32!GetCurrentProcessId` at `0x140004101`
- `KERNEL32!GetCurrentProcessId` at `0x140004101`
- `KERNEL32!GetProcessHeap` at `0x1400042fe`
- `KERNEL32!GetProcessHeap` at `0x1400042fe`

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
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x1400040c8  mov     [rsp-8+arg_10], rbx
0x1400040cd  push    rbp
0x1400040ce  push    rsi
0x1400040cf  push    rdi
0x1400040d0  push    r14
0x1400040d2  push    r15
0x1400040d4  lea     rbp, [rsp-160h]
0x1400040dc  sub     rsp, 260h
0x1400040e3  mov     rax, cs:__security_cookie
0x1400040ea  xor     rax, rsp
0x1400040ed  mov     [rbp+180h+var_30], rax
0x1400040f4  mov     r15, rdx
0x1400040f7  mov     qword ptr [rdx], 0
0x1400040fe  mov     rbx, rcx
0x140004101  call    cs:__imp_GetCurrentProcessId
0x140004107  mov     r14d, 78h ; 'x'
0x14000410d  mov     [rsp+280h+var_258], rbx
0x140004112  mov     r9d, eax
0x140004115  mov     [rsp+280h+var_260], r14d; int
0x14000411a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140004121  mov     edx, 104h; unsigned __int64
0x140004126  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000412b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004130  mov     r9d, 1F0001h; dwDesiredAccess
0x140004136  lea     rdx, [rsp+280h+Name]; lpName
0x14000413b  xor     r8d, r8d; dwFlags
0x14000413e  xor     ecx, ecx; lpMutexAttributes
0x140004140  call    cs:__imp_CreateMutexExW
0x140004146  mov     rbx, rax
0x140004149  test    rax, rax
0x14000414c  jnz     short loc_140004158
0x14000414e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004153  jmp     loc_1400043C7
0x140004158  xor     r8d, r8d; bAlertable
0x14000415b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000415e  mov     rcx, rbx; hHandle
0x140004161  call    cs:__imp_WaitForSingleObjectEx
0x140004167  cmp     eax, 102h
0x14000416c  jz      short loc_14000417E
0x14000416e  test    eax, 0FFFFFF7Fh
0x140004173  jnz     loc_1400043FF
0x140004179  mov     rdi, rbx
0x14000417c  jmp     short loc_140004180
0x14000417e  xor     edi, edi
0x140004180  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140004185  mov     [rsp+280h+hObject], 0
0x14000418e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004193  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004198  mov     esi, eax
0x14000419a  test    eax, eax
0x14000419c  jns     short loc_14000421D
0x14000419e  mov     rcx, [rbp+188h]; this
0x1400041a5  lea     r8, aWil; "wil"
0x1400041ac  mov     r9d, eax; char *
0x1400041af  mov     edx, 66h ; 'f'; void *
0x1400041b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400041b9  mov     rcx, [rbp+188h]; this
0x1400041c0  lea     r8, aWil; "wil"
0x1400041c7  mov     r9d, esi; char *
0x1400041ca  mov     edx, 6Fh ; 'o'; void *
0x1400041cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400041d4  mov     rcx, [rbp+188h]; this
0x1400041db  lea     r8, aWil; "wil"
0x1400041e2  mov     r9d, esi; char *
0x1400041e5  mov     edx, 12Eh; void *
0x1400041ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400041ef  test    rdi, rdi
0x1400041f2  jz      short loc_140004205
0x1400041f4  mov     rcx, rdi; hMutex
0x1400041f7  call    cs:__imp_ReleaseMutex
0x1400041fd  test    eax, eax
0x1400041ff  jz      loc_14000440C
0x140004205  mov     rcx, rbx; hObject
0x140004208  call    cs:__imp_CloseHandle
0x14000420e  test    eax, eax
0x140004210  jz      loc_14000441E
0x140004216  mov     eax, esi
0x140004218  jmp     loc_1400043C7
0x14000421d  mov     rax, [rsp+280h+hObject]
0x140004222  lea     rcx, ds:0[rax*4]
0x14000422a  test    rcx, rcx
0x14000422d  jz      short loc_14000423D
0x14000422f  mov     [r15], rcx
0x140004232  mov     eax, [rcx]
0x140004234  inc     eax
0x140004236  mov     [rcx], eax
0x140004238  jmp     loc_14000439D
0x14000423d  mov     rdx, r14; dwBytes
0x140004240  mov     qword ptr [r15], 0
0x140004247  mov     ecx, 8; dwFlags
0x14000424c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004251  mov     rsi, rax
0x140004254  test    rax, rax
0x140004257  jnz     short loc_14000427F
0x140004259  mov     rcx, [rbp+188h]; this
0x140004260  lea     r8, aWil; "wil"
0x140004267  mov     r14d, 8007000Eh
0x14000426d  mov     edx, 14Bh; void *
0x140004272  mov     r9d, r14d; char *
0x140004275  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000427a  jmp     loc_140004312
0x14000427f  xorps   xmm0, xmm0
0x140004282  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140004288  test    sil, 3
0x14000428c  jnz     loc_140004430
0x140004292  mov     r9, rsi
0x140004295  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x14000429a  shr     r9, 2; unsigned __int64
0x14000429e  lea     rcx, [rsp+280h+hObject]; this
0x1400042a3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400042a8  mov     r14d, eax
0x1400042ab  test    eax, eax
0x1400042ad  jns     loc_140004359
0x1400042b3  mov     rcx, [rbp+188h]; this
0x1400042ba  lea     r8, aWil; "wil"
0x1400042c1  mov     r9d, eax; char *
0x1400042c4  mov     edx, 14Eh; void *
0x1400042c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400042ce  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400042d3  test    rcx, rcx
0x1400042d6  jz      short loc_1400042E6
0x1400042d8  call    cs:__imp_CloseHandle
0x1400042de  test    eax, eax
0x1400042e0  jz      loc_140004436
0x1400042e6  mov     rcx, [rsp+280h+hObject]; hObject
0x1400042eb  test    rcx, rcx
0x1400042ee  jz      short loc_1400042FE
0x1400042f0  call    cs:__imp_CloseHandle
0x1400042f6  test    eax, eax
0x1400042f8  jz      loc_140004448
0x1400042fe  call    cs:__imp_GetProcessHeap
0x140004304  mov     r8, rsi; lpMem
0x140004307  xor     edx, edx; dwFlags
0x140004309  mov     rcx, rax; hHeap
0x14000430c  call    cs:__imp_HeapFree
0x140004312  mov     rcx, [rbp+188h]; this
0x140004319  lea     r8, aWil; "wil"
0x140004320  mov     r9d, r14d; char *
0x140004323  mov     edx, 137h; void *
0x140004328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000432d  test    rdi, rdi
0x140004330  jz      short loc_140004343
0x140004332  mov     rcx, rdi; hMutex
0x140004335  call    cs:__imp_ReleaseMutex
0x14000433b  test    eax, eax
0x14000433d  jz      loc_14000445A
0x140004343  mov     rcx, rbx; hObject
0x140004346  call    cs:__imp_CloseHandle
0x14000434c  test    eax, eax
0x14000434e  jz      loc_14000446C
0x140004354  mov     eax, r14d
0x140004357  jmp     short loc_1400043C7
0x140004359  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000435e  xor     edx, edx; Val
0x140004360  mov     dword ptr [rsi], 1
0x140004366  lea     rcx, [rsi+22h]; void *
0x14000436a  mov     [rsi+8], rbx
0x14000436e  movdqu  xmmword ptr [rsi+10h], xmm0
0x140004373  lea     r8d, [rdx+56h]; Size
0x140004377  call    memset_0
0x14000437c  xor     edx, edx; Val
0x14000437e  mov     word ptr [rsi+20h], 58h ; 'X'
0x140004384  lea     rcx, [rsi+28h]; void *
0x140004388  mov     dword ptr [rsi+24h], 1
0x14000438f  lea     r8d, [rdx+50h]; Size
0x140004393  call    memset_0
0x140004398  xor     ebx, ebx
0x14000439a  mov     [r15], rsi
0x14000439d  test    rdi, rdi
0x1400043a0  jz      short loc_1400043B3
0x1400043a2  mov     rcx, rdi; hMutex
0x1400043a5  call    cs:__imp_ReleaseMutex
0x1400043ab  test    eax, eax
0x1400043ad  jz      loc_14000447E
0x1400043b3  test    rbx, rbx
0x1400043b6  jz      short loc_1400043C5
0x1400043b8  mov     rcx, rbx; hObject
0x1400043bb  call    cs:__imp_CloseHandle
0x1400043c1  test    eax, eax
0x1400043c3  jz      short loc_1400043ED
0x1400043c5  xor     eax, eax
0x1400043c7  mov     rcx, [rbp+180h+var_30]
0x1400043ce  xor     rcx, rsp; StackCookie
0x1400043d1  call    __security_check_cookie
0x1400043d6  mov     rbx, [rsp+280h+arg_10]
0x1400043de  add     rsp, 260h
0x1400043e5  pop     r15
0x1400043e7  pop     r14
0x1400043e9  pop     rdi
0x1400043ea  pop     rsi
0x1400043eb  pop     rbp
0x1400043ec  retn
0x1400043ed  mov     rcx, [rbp+188h]; this
0x1400043f4  mov     edx, 0A0Bh; void *
0x1400043f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400043ff  mov     rcx, [rbp+188h]; this
0x140004406  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000440c  mov     rcx, [rbp+188h]; this
0x140004413  mov     edx, 0A15h; void *
0x140004418  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000441e  mov     rcx, [rbp+188h]; this
0x140004425  mov     edx, 0A0Bh; void *
0x14000442a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004430  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004436  mov     rcx, [rbp+188h]; this
0x14000443d  mov     edx, 0A0Bh; void *
0x140004442  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004448  mov     rcx, [rbp+188h]; this
0x14000444f  mov     edx, 0A0Bh; void *
0x140004454  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000445a  mov     rcx, [rbp+188h]; this
0x140004461  mov     edx, 0A15h; void *
0x140004466  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000446c  mov     rcx, [rbp+188h]; this
0x140004473  mov     edx, 0A0Bh; void *
0x140004478  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000447e  mov     rcx, [rbp+188h]; this
0x140004485  mov     edx, 0A15h; void *
0x14000448a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
