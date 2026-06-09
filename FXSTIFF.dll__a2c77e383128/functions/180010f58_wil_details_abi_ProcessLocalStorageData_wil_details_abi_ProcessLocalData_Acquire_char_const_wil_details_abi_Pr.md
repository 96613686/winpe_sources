# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180010f58`
- end: `0x18001131c`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `964`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180012700`

## callees

- `0x180006934`
- `0x180010f58`
- `0x180011708`
- `0x180011c34`
- `0x180012498`
- `0x18001315c`
- `0x180014664`
- `0x18001531c`
- `0x180015b5c`
- `0x180015b6c`
- `0x180017bce`
- `0x180017c00`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800111ad`
- `KERNEL32!HeapFree` at `0x1800111ad`
- `KERNEL32!GetProcessHeap` at `0x18001119f`
- `KERNEL32!GetProcessHeap` at `0x18001119f`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010ff8`
- `KERNEL32!WaitForSingleObjectEx` at `0x180010ff8`
- `KERNEL32!GetCurrentProcessId` at `0x180010f91`
- `KERNEL32!GetCurrentProcessId` at `0x180010f91`
- `KERNEL32!ReleaseMutex` at `0x18001107f`
- `KERNEL32!ReleaseMutex` at `0x1800111d0`
- `KERNEL32!ReleaseMutex` at `0x18001125b`
- `KERNEL32!ReleaseMutex` at `0x18001107f`
- `KERNEL32!ReleaseMutex` at `0x1800111d0`
- `KERNEL32!ReleaseMutex` at `0x18001125b`
- `KERNEL32!CreateMutexExW` at `0x180010fd1`
- `KERNEL32!CreateMutexExW` at `0x180010fd1`
- `KERNEL32!CloseHandle` at `0x180011097`
- `KERNEL32!CloseHandle` at `0x180011166`
- `KERNEL32!CloseHandle` at `0x180011185`
- `KERNEL32!CloseHandle` at `0x1800111ed`
- `KERNEL32!CloseHandle` at `0x180011278`
- `KERNEL32!CloseHandle` at `0x180011097`
- `KERNEL32!CloseHandle` at `0x180011166`
- `KERNEL32!CloseHandle` at `0x180011185`
- `KERNEL32!CloseHandle` at `0x1800111ed`
- `KERNEL32!CloseHandle` at `0x180011278`

## pseudocode

```c
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
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  unsigned int v25; // r8d
  _QWORD *v26; // rbx
  unsigned int v27; // r14d
  __int64 v28; // r8
  int v29; // eax
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  HANDLE ProcessHeap; // rax
  __int64 v34; // r8
  const char *v35; // r9
  __int64 v36; // r8
  const char *v37; // r9
  __int64 v38; // r8
  const char *v39; // r9
  __int64 v40; // r8
  const char *v41; // r9
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject[2]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v47; // [rsp+48h] [rbp-B8h]
  void *v48; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  v6 = Mutex;
  v47 = Mutex;
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
      v47 = 0;
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
0x180010f58  mov     [rsp-8+arg_10], rbx
0x180010f5d  push    rbp
0x180010f5e  push    rsi
0x180010f5f  push    rdi
0x180010f60  push    r14
0x180010f62  push    r15
0x180010f64  lea     rbp, [rsp-180h]
0x180010f6c  sub     rsp, 280h
0x180010f73  mov     rax, cs:__security_cookie
0x180010f7a  xor     rax, rsp
0x180010f7d  mov     [rbp+1A0h+var_30], rax
0x180010f84  mov     r15, rdx
0x180010f87  mov     rbx, rcx
0x180010f8a  mov     qword ptr [rdx], 0
0x180010f91  call    cs:__imp_GetCurrentProcessId
0x180010f97  mov     r9d, eax
0x180010f9a  mov     [rsp+2A0h+var_278], rbx
0x180010f9f  mov     r14d, 78h ; 'x'
0x180010fa5  mov     [rsp+2A0h+var_280], r14d; int
0x180010faa  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180010fb1  mov     edx, 104h; unsigned __int64
0x180010fb6  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180010fbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010fc0  nop
0x180010fc1  mov     r9d, 1F0001h; dwDesiredAccess
0x180010fc7  xor     r8d, r8d; dwFlags
0x180010fca  lea     rdx, [rsp+2A0h+Name]; lpName
0x180010fcf  xor     ecx, ecx; lpMutexAttributes
0x180010fd1  call    cs:__imp_CreateMutexExW
0x180010fd7  mov     rsi, rax
0x180010fda  mov     [rsp+2A0h+var_258], rax
0x180010fdf  test    rax, rax
0x180010fe2  jnz     short loc_180010FEF
0x180010fe4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180010fe9  nop
0x180010fea  jmp     loc_18001128B
0x180010fef  xor     r8d, r8d; bAlertable
0x180010ff2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010ff5  mov     rcx, rsi; hHandle
0x180010ff8  call    cs:__imp_WaitForSingleObjectEx
0x180010ffe  cmp     eax, 102h
0x180011003  jz      short loc_180011015
0x180011005  test    eax, 0FFFFFF7Fh
0x18001100a  jnz     loc_1800112BC
0x180011010  mov     rdi, rsi
0x180011013  jmp     short loc_180011017
0x180011015  xor     edi, edi
0x180011017  mov     [rsp+2A0h+var_250], rdi
0x18001101c  mov     [rsp+2A0h+var_270], 0
0x180011025  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x18001102a  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18001102f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180011034  mov     ebx, eax
0x180011036  test    eax, eax
0x180011038  jns     short loc_1800110B3
0x18001103a  mov     rcx, [rbp+1A8h]; this
0x180011041  mov     r9d, eax; char *
0x180011044  mov     edx, 66h ; 'f'; void *
0x180011049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001104e  mov     rcx, [rbp+1A8h]; this
0x180011055  mov     r9d, ebx; char *
0x180011058  mov     edx, 6Fh ; 'o'; void *
0x18001105d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011062  mov     rcx, [rbp+1A8h]; this
0x180011069  mov     r9d, ebx; char *
0x18001106c  mov     edx, 12Eh; void *
0x180011071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011076  nop
0x180011077  test    rdi, rdi
0x18001107a  jz      short loc_180011094
0x18001107c  mov     rcx, rdi; hMutex
0x18001107f  call    cs:__imp_ReleaseMutex
0x180011085  mov     rcx, [rbp+1A8h]; this
0x18001108c  test    eax, eax
0x18001108e  jz      loc_1800112C9
0x180011094  mov     rcx, rsi; hObject
0x180011097  call    cs:__imp_CloseHandle
0x18001109d  mov     rcx, [rbp+1A8h]; this
0x1800110a4  test    eax, eax
0x1800110a6  jz      loc_1800112D4
0x1800110ac  mov     eax, ebx
0x1800110ae  jmp     loc_18001128B
0x1800110b3  mov     rax, [rsp+2A0h+var_270]
0x1800110b8  lea     rcx, ds:0[rax*4]
0x1800110c0  test    rcx, rcx
0x1800110c3  jz      short loc_1800110D3
0x1800110c5  mov     [r15], rcx
0x1800110c8  mov     eax, [rcx]
0x1800110ca  inc     eax
0x1800110cc  mov     [rcx], eax
0x1800110ce  jmp     loc_180011253
0x1800110d3  mov     qword ptr [r15], 0
0x1800110da  mov     rdx, r14; dwBytes
0x1800110dd  mov     ecx, 8; dwFlags
0x1800110e2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800110e7  mov     rbx, rax
0x1800110ea  mov     [rsp+2A0h+var_270], rax
0x1800110ef  test    rax, rax
0x1800110f2  jnz     short loc_180011114
0x1800110f4  mov     rcx, [rbp+1A8h]; this
0x1800110fb  mov     r14d, 8007000Eh
0x180011101  mov     r9d, r14d; char *
0x180011104  mov     edx, 14Bh; void *
0x180011109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001110e  nop
0x18001110f  jmp     loc_1800111B3
0x180011114  xorps   xmm0, xmm0
0x180011117  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x18001111d  test    bl, 3
0x180011120  jnz     loc_1800112DF
0x180011126  mov     r9, rbx
0x180011129  shr     r9, 2; unsigned __int64
0x18001112d  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x180011132  lea     rcx, [rsp+2A0h+hObject]; this
0x180011137  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001113c  mov     r14d, eax
0x18001113f  test    eax, eax
0x180011141  jns     loc_18001120A
0x180011147  mov     rcx, [rbp+1A8h]; this
0x18001114e  mov     r9d, eax; char *
0x180011151  mov     edx, 14Eh; void *
0x180011156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001115b  nop
0x18001115c  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x180011161  test    rcx, rcx
0x180011164  jz      short loc_18001117B
0x180011166  call    cs:__imp_CloseHandle
0x18001116c  mov     rcx, [rbp+1A8h]; this
0x180011173  test    eax, eax
0x180011175  jz      loc_1800112E5
0x18001117b  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180011180  test    rcx, rcx
0x180011183  jz      short loc_18001119A
0x180011185  call    cs:__imp_CloseHandle
0x18001118b  mov     rcx, [rbp+1A8h]; this
0x180011192  test    eax, eax
0x180011194  jz      loc_1800112F0
0x18001119a  test    rbx, rbx
0x18001119d  jz      short loc_1800111B3
0x18001119f  call    cs:__imp_GetProcessHeap
0x1800111a5  mov     rcx, rax; hHeap
0x1800111a8  mov     r8, rbx; lpMem
0x1800111ab  xor     edx, edx; dwFlags
0x1800111ad  call    cs:__imp_HeapFree
0x1800111b3  mov     rcx, [rbp+1A8h]; this
0x1800111ba  mov     r9d, r14d; char *
0x1800111bd  mov     edx, 137h; void *
0x1800111c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111c7  nop
0x1800111c8  test    rdi, rdi
0x1800111cb  jz      short loc_1800111E5
0x1800111cd  mov     rcx, rdi; hMutex
0x1800111d0  call    cs:__imp_ReleaseMutex
0x1800111d6  mov     rcx, [rbp+1A8h]; this
0x1800111dd  test    eax, eax
0x1800111df  jz      loc_1800112FB
0x1800111e5  test    rsi, rsi
0x1800111e8  jz      short loc_180011202
0x1800111ea  mov     rcx, rsi; hObject
0x1800111ed  call    cs:__imp_CloseHandle
0x1800111f3  mov     rcx, [rbp+1A8h]; this
0x1800111fa  test    eax, eax
0x1800111fc  jz      loc_180011306
0x180011202  mov     eax, r14d
0x180011205  jmp     loc_18001128B
0x18001120a  mov     dword ptr [rbx], 1
0x180011210  mov     [rbx+8], rsi
0x180011214  xor     esi, esi
0x180011216  mov     [rsp+2A0h+var_258], rsi
0x18001121b  movups  xmm0, xmmword ptr [rsp+2A0h+hObject]
0x180011220  movdqu  xmmword ptr [rbx+10h], xmm0
0x180011225  lea     rcx, [rbx+22h]; void *
0x180011229  xor     edx, edx; Val
0x18001122b  lea     r8d, [rsi+56h]; Size
0x18001122f  call    memset_0
0x180011234  mov     word ptr [rbx+20h], 58h ; 'X'
0x18001123a  mov     dword ptr [rbx+24h], 1
0x180011241  lea     rcx, [rbx+28h]; void *
0x180011245  xor     edx, edx; Val
0x180011247  lea     r8d, [rsi+50h]; Size
0x18001124b  call    memset_0
0x180011250  mov     [r15], rbx
0x180011253  test    rdi, rdi
0x180011256  jz      short loc_180011270
0x180011258  mov     rcx, rdi; hMutex
0x18001125b  call    cs:__imp_ReleaseMutex
0x180011261  mov     rcx, [rbp+1A8h]; this
0x180011268  test    eax, eax
0x18001126a  jz      loc_180011311
0x180011270  test    rsi, rsi
0x180011273  jz      short loc_180011289
0x180011275  mov     rcx, rsi; hObject
0x180011278  call    cs:__imp_CloseHandle
0x18001127e  mov     rcx, [rbp+1A8h]; this
0x180011285  test    eax, eax
0x180011287  jz      short loc_1800112B1
0x180011289  xor     eax, eax
0x18001128b  mov     rcx, [rbp+1A0h+var_30]
0x180011292  xor     rcx, rsp; StackCookie
0x180011295  call    __security_check_cookie
0x18001129a  mov     rbx, [rsp+2A0h+arg_10]
0x1800112a2  add     rsp, 280h
0x1800112a9  pop     r15
0x1800112ab  pop     r14
0x1800112ad  pop     rdi
0x1800112ae  pop     rsi
0x1800112af  pop     rbp
0x1800112b0  retn
0x1800112b1  mov     edx, 0A0Bh; void *
0x1800112b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800112bc  mov     rcx, [rbp+1A8h]; this
0x1800112c3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800112c9  mov     edx, 0A15h; void *
0x1800112ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800112d4  mov     edx, 0A0Bh; void *
0x1800112d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800112df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800112e5  mov     edx, 0A0Bh; void *
0x1800112ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800112f0  mov     edx, 0A0Bh; void *
0x1800112f5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800112fb  mov     edx, 0A15h; void *
0x180011300  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011306  mov     edx, 0A0Bh; void *
0x18001130b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011311  mov     edx, 0A15h; void *
0x180011316  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
