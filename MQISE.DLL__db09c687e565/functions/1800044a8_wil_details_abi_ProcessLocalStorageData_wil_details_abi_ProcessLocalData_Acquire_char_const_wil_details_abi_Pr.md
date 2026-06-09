# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800044a8`
- end: `0x180004875`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `973`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180006fac`

## callees

- `0x1800044a8`
- `0x180005310`
- `0x180005c48`
- `0x1800067dc`
- `0x180007dfc`
- `0x1800095c4`
- `0x180009fbc`
- `0x18000a534`
- `0x18000b3b8`
- `0x18000b3c8`
- `0x18000f5c2`
- `0x18000f5f0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180004529`
- `KERNEL32!CreateMutexExW` at `0x180004529`
- `KERNEL32!GetCurrentProcessId` at `0x1800044e1`
- `KERNEL32!GetCurrentProcessId` at `0x1800044e1`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004550`
- `KERNEL32!WaitForSingleObjectEx` at `0x180004550`
- `KERNEL32!ReleaseMutex` at `0x1800045d7`
- `KERNEL32!ReleaseMutex` at `0x180004729`
- `KERNEL32!ReleaseMutex` at `0x1800047b4`
- `KERNEL32!ReleaseMutex` at `0x1800045d7`
- `KERNEL32!ReleaseMutex` at `0x180004729`
- `KERNEL32!ReleaseMutex` at `0x1800047b4`
- `KERNEL32!CloseHandle` at `0x1800045ef`
- `KERNEL32!CloseHandle` at `0x1800046be`
- `KERNEL32!CloseHandle` at `0x1800046dd`
- `KERNEL32!CloseHandle` at `0x180004746`
- `KERNEL32!CloseHandle` at `0x1800047d1`
- `KERNEL32!CloseHandle` at `0x1800045ef`
- `KERNEL32!CloseHandle` at `0x1800046be`
- `KERNEL32!CloseHandle` at `0x1800046dd`
- `KERNEL32!CloseHandle` at `0x180004746`
- `KERNEL32!CloseHandle` at `0x1800047d1`
- `KERNEL32!GetProcessHeap` at `0x1800046f7`
- `KERNEL32!GetProcessHeap` at `0x1800046f7`
- `KERNEL32!HeapFree` at `0x180004705`
- `KERNEL32!HeapFree` at `0x180004705`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rsi
  DWORD v8; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // rdi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // ebx
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
  _QWORD *v26; // rbx
  unsigned int v27; // r14d
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  unsigned int v40; // r8d
  const char *v41; // r9
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v46; // [rsp+38h] [rbp-C8h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *v48; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  v46 = Mutex;
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
  v48 = v12;
  v45 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v45, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v42);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v43);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v45);
  if ( 4 * v45 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_30;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (_QWORD *)v23;
  v45 = v23;
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
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      v6 = 0;
      v46 = 0;
      *((_OWORD *)v26 + 1) = *(_OWORD *)hObject;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      *a2 = v26;
LABEL_30:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v38, v39);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v40, v41);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v32);
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v44);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
  return v27;
}

```

## disassembly

```asm
0x1800044a8  mov     [rsp-8+arg_10], rbx
0x1800044ad  push    rbp
0x1800044ae  push    rsi
0x1800044af  push    rdi
0x1800044b0  push    r14
0x1800044b2  push    r15
0x1800044b4  lea     rbp, [rsp-180h]
0x1800044bc  sub     rsp, 280h
0x1800044c3  mov     rax, cs:__security_cookie
0x1800044ca  xor     rax, rsp
0x1800044cd  mov     [rbp+1A0h+var_30], rax
0x1800044d4  mov     r15, rdx
0x1800044d7  mov     rbx, rcx
0x1800044da  mov     qword ptr [rdx], 0
0x1800044e1  call    cs:__imp_GetCurrentProcessId
0x1800044e7  mov     r9d, eax
0x1800044ea  mov     [rsp+2A0h+var_278], rbx
0x1800044ef  mov     r14d, 78h ; 'x'
0x1800044f5  mov     [rsp+2A0h+var_280], r14d; int
0x1800044fa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004501  mov     edx, 104h; unsigned __int64
0x180004506  lea     rcx, [rsp+2A0h+Name]; wchar_t *
0x18000450b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180004510  mov     [rsp+2A0h+var_268], 0
0x180004519  mov     r9d, 1F0001h; dwDesiredAccess
0x18000451f  xor     r8d, r8d; dwFlags
0x180004522  lea     rdx, [rsp+2A0h+Name]; lpName
0x180004527  xor     ecx, ecx; lpMutexAttributes
0x180004529  call    cs:__imp_CreateMutexExW
0x18000452f  mov     rsi, rax
0x180004532  mov     [rsp+2A0h+var_268], rax
0x180004537  test    rax, rax
0x18000453a  jnz     short loc_180004547
0x18000453c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004541  nop
0x180004542  jmp     loc_1800047E4
0x180004547  xor     r8d, r8d; bAlertable
0x18000454a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000454d  mov     rcx, rsi; hHandle
0x180004550  call    cs:__imp_WaitForSingleObjectEx
0x180004556  cmp     eax, 102h
0x18000455b  jz      short loc_18000456D
0x18000455d  test    eax, 0FFFFFF7Fh
0x180004562  jnz     loc_180004815
0x180004568  mov     rdi, rsi
0x18000456b  jmp     short loc_18000456F
0x18000456d  xor     edi, edi
0x18000456f  mov     [rsp+2A0h+var_250], rdi
0x180004574  mov     [rsp+2A0h+var_270], 0
0x18000457d  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x180004582  lea     rcx, [rsp+2A0h+Name]; wchar_t *
0x180004587  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x18000458c  mov     ebx, eax
0x18000458e  test    eax, eax
0x180004590  jns     short loc_18000460B
0x180004592  mov     rcx, [rbp+1A8h]; this
0x180004599  mov     r9d, eax; char *
0x18000459c  mov     edx, 66h ; 'f'; void *
0x1800045a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045a6  mov     rcx, [rbp+1A8h]; this
0x1800045ad  mov     r9d, ebx; char *
0x1800045b0  mov     edx, 6Fh ; 'o'; void *
0x1800045b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045ba  mov     rcx, [rbp+1A8h]; this
0x1800045c1  mov     r9d, ebx; char *
0x1800045c4  mov     edx, 12Eh; void *
0x1800045c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045ce  nop
0x1800045cf  test    rdi, rdi
0x1800045d2  jz      short loc_1800045EC
0x1800045d4  mov     rcx, rdi; hMutex
0x1800045d7  call    cs:__imp_ReleaseMutex
0x1800045dd  mov     rcx, [rbp+1A8h]; this
0x1800045e4  test    eax, eax
0x1800045e6  jz      loc_180004822
0x1800045ec  mov     rcx, rsi; hObject
0x1800045ef  call    cs:__imp_CloseHandle
0x1800045f5  mov     rcx, [rbp+1A8h]; this
0x1800045fc  test    eax, eax
0x1800045fe  jz      loc_18000482D
0x180004604  mov     eax, ebx
0x180004606  jmp     loc_1800047E4
0x18000460b  mov     rax, [rsp+2A0h+var_270]
0x180004610  lea     rcx, ds:0[rax*4]
0x180004618  test    rcx, rcx
0x18000461b  jz      short loc_18000462B
0x18000461d  mov     [r15], rcx
0x180004620  mov     eax, [rcx]
0x180004622  inc     eax
0x180004624  mov     [rcx], eax
0x180004626  jmp     loc_1800047AC
0x18000462b  mov     qword ptr [r15], 0
0x180004632  mov     rdx, r14; dwBytes
0x180004635  mov     ecx, 8; dwFlags
0x18000463a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000463f  mov     rbx, rax
0x180004642  mov     [rsp+2A0h+var_270], rax
0x180004647  test    rax, rax
0x18000464a  jnz     short loc_18000466C
0x18000464c  mov     rcx, [rbp+1A8h]; this
0x180004653  mov     r14d, 8007000Eh
0x180004659  mov     r9d, r14d; char *
0x18000465c  mov     edx, 14Bh; void *
0x180004661  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004666  nop
0x180004667  jmp     loc_18000470C
0x18000466c  xorps   xmm0, xmm0
0x18000466f  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x180004675  test    bl, 3
0x180004678  jnz     loc_180004838
0x18000467e  mov     r9, rbx
0x180004681  shr     r9, 2; unsigned __int64
0x180004685  lea     rdx, [rsp+2A0h+Name]; wchar_t *
0x18000468a  lea     rcx, [rsp+2A0h+hObject]; this
0x18000468f  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x180004694  mov     r14d, eax
0x180004697  test    eax, eax
0x180004699  jns     loc_180004763
0x18000469f  mov     rcx, [rbp+1A8h]; this
0x1800046a6  mov     r9d, eax; char *
0x1800046a9  mov     edx, 14Eh; void *
0x1800046ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800046b3  nop
0x1800046b4  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x1800046b9  test    rcx, rcx
0x1800046bc  jz      short loc_1800046D3
0x1800046be  call    cs:__imp_CloseHandle
0x1800046c4  mov     rcx, [rbp+1A8h]; this
0x1800046cb  test    eax, eax
0x1800046cd  jz      loc_18000483E
0x1800046d3  mov     rcx, [rsp+2A0h+hObject]; hObject
0x1800046d8  test    rcx, rcx
0x1800046db  jz      short loc_1800046F2
0x1800046dd  call    cs:__imp_CloseHandle
0x1800046e3  mov     rcx, [rbp+1A8h]; this
0x1800046ea  test    eax, eax
0x1800046ec  jz      loc_180004849
0x1800046f2  test    rbx, rbx
0x1800046f5  jz      short loc_18000470C
0x1800046f7  call    cs:__imp_GetProcessHeap
0x1800046fd  mov     rcx, rax; hHeap
0x180004700  mov     r8, rbx; lpMem
0x180004703  xor     edx, edx; dwFlags
0x180004705  call    cs:__imp_HeapFree
0x18000470b  nop
0x18000470c  mov     rcx, [rbp+1A8h]; this
0x180004713  mov     r9d, r14d; char *
0x180004716  mov     edx, 137h; void *
0x18000471b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004720  nop
0x180004721  test    rdi, rdi
0x180004724  jz      short loc_18000473E
0x180004726  mov     rcx, rdi; hMutex
0x180004729  call    cs:__imp_ReleaseMutex
0x18000472f  mov     rcx, [rbp+1A8h]; this
0x180004736  test    eax, eax
0x180004738  jz      loc_180004854
0x18000473e  test    rsi, rsi
0x180004741  jz      short loc_18000475B
0x180004743  mov     rcx, rsi; hObject
0x180004746  call    cs:__imp_CloseHandle
0x18000474c  mov     rcx, [rbp+1A8h]; this
0x180004753  test    eax, eax
0x180004755  jz      loc_18000485F
0x18000475b  mov     eax, r14d
0x18000475e  jmp     loc_1800047E4
0x180004763  mov     dword ptr [rbx], 1
0x180004769  mov     [rbx+8], rsi
0x18000476d  xor     esi, esi
0x18000476f  mov     [rsp+2A0h+var_268], rsi
0x180004774  movups  xmm0, xmmword ptr [rsp+2A0h+hObject]
0x180004779  movdqu  xmmword ptr [rbx+10h], xmm0
0x18000477e  lea     rcx, [rbx+22h]; void *
0x180004782  xor     edx, edx; Val
0x180004784  lea     r8d, [rsi+56h]; Size
0x180004788  call    memset_0
0x18000478d  mov     word ptr [rbx+20h], 58h ; 'X'
0x180004793  mov     dword ptr [rbx+24h], 1
0x18000479a  lea     rcx, [rbx+28h]; void *
0x18000479e  xor     edx, edx; Val
0x1800047a0  lea     r8d, [rsi+50h]; Size
0x1800047a4  call    memset_0
0x1800047a9  mov     [r15], rbx
0x1800047ac  test    rdi, rdi
0x1800047af  jz      short loc_1800047C9
0x1800047b1  mov     rcx, rdi; hMutex
0x1800047b4  call    cs:__imp_ReleaseMutex
0x1800047ba  mov     rcx, [rbp+1A8h]; this
0x1800047c1  test    eax, eax
0x1800047c3  jz      loc_18000486A
0x1800047c9  test    rsi, rsi
0x1800047cc  jz      short loc_1800047E2
0x1800047ce  mov     rcx, rsi; hObject
0x1800047d1  call    cs:__imp_CloseHandle
0x1800047d7  mov     rcx, [rbp+1A8h]; this
0x1800047de  test    eax, eax
0x1800047e0  jz      short loc_18000480A
0x1800047e2  xor     eax, eax
0x1800047e4  mov     rcx, [rbp+1A0h+var_30]
0x1800047eb  xor     rcx, rsp; StackCookie
0x1800047ee  call    __security_check_cookie
0x1800047f3  mov     rbx, [rsp+2A0h+arg_10]
0x1800047fb  add     rsp, 280h
0x180004802  pop     r15
0x180004804  pop     r14
0x180004806  pop     rdi
0x180004807  pop     rsi
0x180004808  pop     rbp
0x180004809  retn
0x18000480a  mov     edx, 0A0Bh; void *
0x18000480f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004815  mov     rcx, [rbp+1A8h]; this
0x18000481c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180004822  mov     edx, 0A15h; void *
0x180004827  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000482d  mov     edx, 0A0Bh; void *
0x180004832  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004838  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000483e  mov     edx, 0A0Bh; void *
0x180004843  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004849  mov     edx, 0A0Bh; void *
0x18000484e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004854  mov     edx, 0A15h; void *
0x180004859  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000485f  mov     edx, 0A0Bh; void *
0x180004864  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000486a  mov     edx, 0A15h; void *
0x18000486f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
