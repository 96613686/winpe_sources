# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180011324`
- end: `0x1800116ff`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `987`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1800119d4`

## callees

- `0x180006934`
- `0x180010474`
- `0x180011324`
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

- `KERNEL32!HeapFree` at `0x180011574`
- `KERNEL32!HeapFree` at `0x180011574`
- `KERNEL32!GetProcessHeap` at `0x180011566`
- `KERNEL32!GetProcessHeap` at `0x180011566`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18001161d`
- `KERNEL32!InitializeCriticalSectionEx` at `0x18001161d`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800113c0`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800113c0`
- `KERNEL32!GetCurrentProcessId` at `0x18001135d`
- `KERNEL32!GetCurrentProcessId` at `0x18001135d`
- `KERNEL32!ReleaseMutex` at `0x180011447`
- `KERNEL32!ReleaseMutex` at `0x180011597`
- `KERNEL32!ReleaseMutex` at `0x18001163e`
- `KERNEL32!ReleaseMutex` at `0x180011447`
- `KERNEL32!ReleaseMutex` at `0x180011597`
- `KERNEL32!ReleaseMutex` at `0x18001163e`
- `KERNEL32!CreateMutexExW` at `0x180011399`
- `KERNEL32!CreateMutexExW` at `0x180011399`
- `KERNEL32!CloseHandle` at `0x18001145f`
- `KERNEL32!CloseHandle` at `0x18001152d`
- `KERNEL32!CloseHandle` at `0x18001154c`
- `KERNEL32!CloseHandle` at `0x1800115b8`
- `KERNEL32!CloseHandle` at `0x18001165b`
- `KERNEL32!CloseHandle` at `0x18001145f`
- `KERNEL32!CloseHandle` at `0x18001152d`
- `KERNEL32!CloseHandle` at `0x18001154c`
- `KERNEL32!CloseHandle` at `0x1800115b8`
- `KERNEL32!CloseHandle` at `0x18001165b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // r14
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
  _DWORD *v26; // rsi
  __int64 v27; // r8
  int v28; // eax
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  HANDLE ProcessHeap; // rax
  __int64 v33; // r8
  const char *v34; // r9
  __int64 v35; // r8
  const char *v36; // r9
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
  const char *v40; // r9
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject[2]; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v46; // [rsp+48h] [rbp-B8h]
  void *v47; // [rsp+50h] [rbp-B0h]
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
  v47 = v12;
  v44 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, (bool)v9, &v44, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v41);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v18, v19);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v20, v21);
    return v15;
  }
  v22 = (_DWORD *)(4 * v44);
  if ( 4 * v44 )
  {
    *a2 = v22;
    ++*v22;
    goto LABEL_30;
  }
  *a2 = 0;
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  v44 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_24:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v43);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v33, v34);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v23 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
  v28 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v25,
          v23 >> 2);
  v15 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v29, (const char *)(unsigned int)v28, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v30);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v31);
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
    goto LABEL_24;
  }
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  v6 = 0;
  v46 = 0;
  *((_OWORD *)v26 + 1) = *(_OWORD *)hObject;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  *a2 = v26;
LABEL_30:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v37, v38);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
  return 0;
}

```

## disassembly

```asm
0x180011324  mov     [rsp-8+arg_10], rbx
0x180011329  push    rbp
0x18001132a  push    rsi
0x18001132b  push    rdi
0x18001132c  push    r14
0x18001132e  push    r15
0x180011330  lea     rbp, [rsp-180h]
0x180011338  sub     rsp, 280h
0x18001133f  mov     rax, cs:__security_cookie
0x180011346  xor     rax, rsp
0x180011349  mov     [rbp+1A0h+var_30], rax
0x180011350  mov     r15, rdx
0x180011353  mov     rbx, rcx
0x180011356  mov     qword ptr [rdx], 0
0x18001135d  call    cs:__imp_GetCurrentProcessId
0x180011363  mov     r9d, eax
0x180011366  mov     [rsp+2A0h+var_278], rbx
0x18001136b  mov     esi, 130h
0x180011370  mov     [rsp+2A0h+var_280], esi; int
0x180011374  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001137b  lea     edx, [rsi-2Ch]; unsigned __int64
0x18001137e  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x180011383  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011388  nop
0x180011389  mov     r9d, 1F0001h; dwDesiredAccess
0x18001138f  xor     r8d, r8d; dwFlags
0x180011392  lea     rdx, [rsp+2A0h+Name]; lpName
0x180011397  xor     ecx, ecx; lpMutexAttributes
0x180011399  call    cs:__imp_CreateMutexExW
0x18001139f  mov     r14, rax
0x1800113a2  mov     [rsp+2A0h+var_258], rax
0x1800113a7  test    rax, rax
0x1800113aa  jnz     short loc_1800113B7
0x1800113ac  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800113b1  nop
0x1800113b2  jmp     loc_18001166E
0x1800113b7  xor     r8d, r8d; bAlertable
0x1800113ba  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800113bd  mov     rcx, r14; hHandle
0x1800113c0  call    cs:__imp_WaitForSingleObjectEx
0x1800113c6  cmp     eax, 102h
0x1800113cb  jz      short loc_1800113DD
0x1800113cd  test    eax, 0FFFFFF7Fh
0x1800113d2  jnz     loc_18001169F
0x1800113d8  mov     rdi, r14
0x1800113db  jmp     short loc_1800113DF
0x1800113dd  xor     edi, edi
0x1800113df  mov     [rsp+2A0h+var_250], rdi
0x1800113e4  mov     [rsp+2A0h+var_270], 0
0x1800113ed  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x1800113f2  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800113f7  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800113fc  mov     ebx, eax
0x1800113fe  test    eax, eax
0x180011400  jns     short loc_18001147B
0x180011402  mov     rcx, [rbp+1A8h]; this
0x180011409  mov     r9d, eax; char *
0x18001140c  mov     edx, 66h ; 'f'; void *
0x180011411  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011416  mov     rcx, [rbp+1A8h]; this
0x18001141d  mov     r9d, ebx; char *
0x180011420  mov     edx, 6Fh ; 'o'; void *
0x180011425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001142a  mov     rcx, [rbp+1A8h]; this
0x180011431  mov     r9d, ebx; char *
0x180011434  mov     edx, 12Eh; void *
0x180011439  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001143e  nop
0x18001143f  test    rdi, rdi
0x180011442  jz      short loc_18001145C
0x180011444  mov     rcx, rdi; hMutex
0x180011447  call    cs:__imp_ReleaseMutex
0x18001144d  mov     rcx, [rbp+1A8h]; this
0x180011454  test    eax, eax
0x180011456  jz      loc_1800116AC
0x18001145c  mov     rcx, r14; hObject
0x18001145f  call    cs:__imp_CloseHandle
0x180011465  mov     rcx, [rbp+1A8h]; this
0x18001146c  test    eax, eax
0x18001146e  jz      loc_1800116B7
0x180011474  mov     eax, ebx
0x180011476  jmp     loc_18001166E
0x18001147b  mov     rax, [rsp+2A0h+var_270]
0x180011480  lea     rcx, ds:0[rax*4]
0x180011488  test    rcx, rcx
0x18001148b  jz      short loc_18001149B
0x18001148d  mov     [r15], rcx
0x180011490  mov     eax, [rcx]
0x180011492  inc     eax
0x180011494  mov     [rcx], eax
0x180011496  jmp     loc_180011636
0x18001149b  mov     qword ptr [r15], 0
0x1800114a2  mov     rdx, rsi; dwBytes
0x1800114a5  mov     ecx, 8; dwFlags
0x1800114aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800114af  mov     rsi, rax
0x1800114b2  mov     [rsp+2A0h+var_270], rax
0x1800114b7  test    rax, rax
0x1800114ba  jnz     short loc_1800114DB
0x1800114bc  mov     rcx, [rbp+1A8h]; this
0x1800114c3  mov     ebx, 8007000Eh
0x1800114c8  mov     r9d, ebx; char *
0x1800114cb  mov     edx, 14Bh; void *
0x1800114d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800114d5  nop
0x1800114d6  jmp     loc_18001157A
0x1800114db  xorps   xmm0, xmm0
0x1800114de  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x1800114e4  test    sil, 3
0x1800114e8  jnz     loc_1800116C2
0x1800114ee  mov     r9, rsi
0x1800114f1  shr     r9, 2; unsigned __int64
0x1800114f5  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x1800114fa  lea     rcx, [rsp+2A0h+hObject]; this
0x1800114ff  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180011504  mov     ebx, eax
0x180011506  test    eax, eax
0x180011508  jns     loc_1800115D2
0x18001150e  mov     rcx, [rbp+1A8h]; this
0x180011515  mov     r9d, eax; char *
0x180011518  mov     edx, 14Eh; void *
0x18001151d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011522  nop
0x180011523  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x180011528  test    rcx, rcx
0x18001152b  jz      short loc_180011542
0x18001152d  call    cs:__imp_CloseHandle
0x180011533  mov     rcx, [rbp+1A8h]; this
0x18001153a  test    eax, eax
0x18001153c  jz      loc_1800116C8
0x180011542  mov     rcx, [rsp+2A0h+hObject]; hObject
0x180011547  test    rcx, rcx
0x18001154a  jz      short loc_180011561
0x18001154c  call    cs:__imp_CloseHandle
0x180011552  mov     rcx, [rbp+1A8h]; this
0x180011559  test    eax, eax
0x18001155b  jz      loc_1800116D3
0x180011561  test    rsi, rsi
0x180011564  jz      short loc_18001157A
0x180011566  call    cs:__imp_GetProcessHeap
0x18001156c  mov     rcx, rax; hHeap
0x18001156f  mov     r8, rsi; lpMem
0x180011572  xor     edx, edx; dwFlags
0x180011574  call    cs:__imp_HeapFree
0x18001157a  mov     rcx, [rbp+1A8h]; this
0x180011581  mov     r9d, ebx; char *
0x180011584  mov     edx, 137h; void *
0x180011589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001158e  nop
0x18001158f  test    rdi, rdi
0x180011592  jz      short loc_1800115AC
0x180011594  mov     rcx, rdi; hMutex
0x180011597  call    cs:__imp_ReleaseMutex
0x18001159d  mov     rcx, [rbp+1A8h]; this
0x1800115a4  test    eax, eax
0x1800115a6  jz      loc_1800116DE
0x1800115ac  test    r14, r14
0x1800115af  jz      loc_180011474
0x1800115b5  mov     rcx, r14; hObject
0x1800115b8  call    cs:__imp_CloseHandle
0x1800115be  mov     rcx, [rbp+1A8h]; this
0x1800115c5  test    eax, eax
0x1800115c7  jz      loc_1800116E9
0x1800115cd  jmp     loc_180011474
0x1800115d2  mov     dword ptr [rsi], 1
0x1800115d8  mov     [rsi+8], r14
0x1800115dc  xor     r14d, r14d
0x1800115df  mov     [rsp+2A0h+var_258], r14
0x1800115e4  movups  xmm0, xmmword ptr [rsp+2A0h+hObject]
0x1800115e9  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800115ee  lea     rcx, [rsi+28h]; void *
0x1800115f2  xor     edx, edx; Val
0x1800115f4  mov     r8d, 108h; Size
0x1800115fa  call    memset_0
0x1800115ff  xor     eax, eax
0x180011601  mov     [rsi+20h], rax
0x180011605  lea     rcx, [rsi+28h]; this
0x180011609  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001160e  lea     rbx, [rsi+0E8h]
0x180011615  xor     r8d, r8d; Flags
0x180011618  xor     edx, edx; dwSpinCount
0x18001161a  mov     rcx, rbx; lpCriticalSection
0x18001161d  call    cs:__imp_InitializeCriticalSectionEx
0x180011623  mov     [rbx+28h], r14
0x180011627  mov     [rbx+30h], r14
0x18001162b  mov     [rbx+38h], r14
0x18001162f  mov     [rbx+40h], r14
0x180011633  mov     [r15], rsi
0x180011636  test    rdi, rdi
0x180011639  jz      short loc_180011653
0x18001163b  mov     rcx, rdi; hMutex
0x18001163e  call    cs:__imp_ReleaseMutex
0x180011644  mov     rcx, [rbp+1A8h]; this
0x18001164b  test    eax, eax
0x18001164d  jz      loc_1800116F4
0x180011653  test    r14, r14
0x180011656  jz      short loc_18001166C
0x180011658  mov     rcx, r14; hObject
0x18001165b  call    cs:__imp_CloseHandle
0x180011661  mov     rcx, [rbp+1A8h]; this
0x180011668  test    eax, eax
0x18001166a  jz      short loc_180011694
0x18001166c  xor     eax, eax
0x18001166e  mov     rcx, [rbp+1A0h+var_30]
0x180011675  xor     rcx, rsp; StackCookie
0x180011678  call    __security_check_cookie
0x18001167d  mov     rbx, [rsp+2A0h+arg_10]
0x180011685  add     rsp, 280h
0x18001168c  pop     r15
0x18001168e  pop     r14
0x180011690  pop     rdi
0x180011691  pop     rsi
0x180011692  pop     rbp
0x180011693  retn
0x180011694  mov     edx, 0A0Bh; void *
0x180011699  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001169f  mov     rcx, [rbp+1A8h]; this
0x1800116a6  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800116ac  mov     edx, 0A15h; void *
0x1800116b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800116b7  mov     edx, 0A0Bh; void *
0x1800116bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800116c2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800116c8  mov     edx, 0A0Bh; void *
0x1800116cd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800116d3  mov     edx, 0A0Bh; void *
0x1800116d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800116de  mov     edx, 0A15h; void *
0x1800116e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800116e9  mov     edx, 0A0Bh; void *
0x1800116ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800116f4  mov     edx, 0A15h; void *
0x1800116f9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
