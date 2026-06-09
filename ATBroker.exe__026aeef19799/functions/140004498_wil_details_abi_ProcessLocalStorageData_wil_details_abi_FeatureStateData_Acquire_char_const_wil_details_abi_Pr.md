# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140004498`
- end: `0x140004889`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140004c64`

## callees

- `0x140003660`
- `0x140004498`
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

- `KERNEL32!HeapFree` at `0x1400046d9`
- `KERNEL32!HeapFree` at `0x1400046d9`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14000476b`
- `KERNEL32!InitializeCriticalSectionEx` at `0x14000476b`
- `KERNEL32!ReleaseMutex` at `0x1400045c6`
- `KERNEL32!ReleaseMutex` at `0x140004702`
- `KERNEL32!ReleaseMutex` at `0x14000479e`
- `KERNEL32!ReleaseMutex` at `0x1400045c6`
- `KERNEL32!ReleaseMutex` at `0x140004702`
- `KERNEL32!ReleaseMutex` at `0x14000479e`
- `KERNEL32!WaitForSingleObjectEx` at `0x140004530`
- `KERNEL32!WaitForSingleObjectEx` at `0x140004530`
- `KERNEL32!CloseHandle` at `0x1400045d7`
- `KERNEL32!CloseHandle` at `0x1400046a5`
- `KERNEL32!CloseHandle` at `0x1400046bd`
- `KERNEL32!CloseHandle` at `0x140004713`
- `KERNEL32!CloseHandle` at `0x1400047b4`
- `KERNEL32!CloseHandle` at `0x1400045d7`
- `KERNEL32!CloseHandle` at `0x1400046a5`
- `KERNEL32!CloseHandle` at `0x1400046bd`
- `KERNEL32!CloseHandle` at `0x140004713`
- `KERNEL32!CloseHandle` at `0x1400047b4`
- `KERNEL32!CreateMutexExW` at `0x14000450f`
- `KERNEL32!CreateMutexExW` at `0x14000450f`
- `KERNEL32!GetCurrentProcessId` at `0x1400044d1`
- `KERNEL32!GetCurrentProcessId` at `0x1400044d1`
- `KERNEL32!GetProcessHeap` at `0x1400046cb`
- `KERNEL32!GetProcessHeap` at `0x1400046cb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
  _DWORD *v24; // r14
  int v25; // eax
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  __int128 v35; // xmm0
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
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
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v40);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v41);
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
  v21 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v24 = (_DWORD *)v21;
  if ( !v21 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, (unsigned int)"wil", (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)v15, v42);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v31, v32);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return v15;
  }
  *(_OWORD *)hObject = 0;
  if ( (v21 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  v25 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v23,
          v21 >> 2);
  v15 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, (unsigned int)"wil", (const char *)(unsigned int)v25, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    goto LABEL_23;
  }
  v35 = *(_OWORD *)hObject;
  *v24 = 1;
  *((_QWORD *)v24 + 1) = v6;
  *((_OWORD *)v24 + 1) = v35;
  memset_0(v24 + 10, 0, 0x108u);
  *((_QWORD *)v24 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v24 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v24 + 58), 0, 0);
  *((_QWORD *)v24 + 34) = 0;
  *((_QWORD *)v24 + 35) = 0;
  *((_QWORD *)v24 + 36) = 0;
  *((_QWORD *)v24 + 37) = 0;
  v6 = 0;
  *a2 = v24;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return 0;
}

```

## disassembly

```asm
0x140004498  mov     [rsp-8+arg_10], rbx
0x14000449d  push    rbp
0x14000449e  push    rsi
0x14000449f  push    rdi
0x1400044a0  push    r14
0x1400044a2  push    r15
0x1400044a4  lea     rbp, [rsp-160h]
0x1400044ac  sub     rsp, 260h
0x1400044b3  mov     rax, cs:__security_cookie
0x1400044ba  xor     rax, rsp
0x1400044bd  mov     [rbp+180h+var_30], rax
0x1400044c4  mov     r15, rdx
0x1400044c7  mov     qword ptr [rdx], 0
0x1400044ce  mov     rbx, rcx
0x1400044d1  call    cs:__imp_GetCurrentProcessId
0x1400044d7  mov     r14d, 130h
0x1400044dd  mov     [rsp+280h+var_258], rbx
0x1400044e2  mov     r9d, eax
0x1400044e5  mov     [rsp+280h+var_260], r14d; int
0x1400044ea  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400044f1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400044f6  lea     edx, [r14-2Ch]; unsigned __int64
0x1400044fa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400044ff  mov     r9d, 1F0001h; dwDesiredAccess
0x140004505  lea     rdx, [rsp+280h+Name]; lpName
0x14000450a  xor     r8d, r8d; dwFlags
0x14000450d  xor     ecx, ecx; lpMutexAttributes
0x14000450f  call    cs:__imp_CreateMutexExW
0x140004515  mov     rbx, rax
0x140004518  test    rax, rax
0x14000451b  jnz     short loc_140004527
0x14000451d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140004522  jmp     loc_1400047C0
0x140004527  xor     r8d, r8d; bAlertable
0x14000452a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000452d  mov     rcx, rbx; hHandle
0x140004530  call    cs:__imp_WaitForSingleObjectEx
0x140004536  cmp     eax, 102h
0x14000453b  jz      short loc_14000454D
0x14000453d  test    eax, 0FFFFFF7Fh
0x140004542  jnz     loc_14000480A
0x140004548  mov     rdi, rbx
0x14000454b  jmp     short loc_14000454F
0x14000454d  xor     edi, edi
0x14000454f  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140004554  mov     [rsp+280h+hObject], 0
0x14000455d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140004562  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140004567  mov     esi, eax
0x140004569  test    eax, eax
0x14000456b  jns     short loc_1400045EC
0x14000456d  mov     rcx, [rbp+188h]; this
0x140004574  lea     r8, aWil; "wil"
0x14000457b  mov     r9d, eax; char *
0x14000457e  mov     edx, 66h ; 'f'; void *
0x140004583  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004588  mov     rcx, [rbp+188h]; this
0x14000458f  lea     r8, aWil; "wil"
0x140004596  mov     r9d, esi; char *
0x140004599  mov     edx, 6Fh ; 'o'; void *
0x14000459e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400045a3  mov     rcx, [rbp+188h]; this
0x1400045aa  lea     r8, aWil; "wil"
0x1400045b1  mov     r9d, esi; char *
0x1400045b4  mov     edx, 12Eh; void *
0x1400045b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400045be  test    rdi, rdi
0x1400045c1  jz      short loc_1400045D4
0x1400045c3  mov     rcx, rdi; hMutex
0x1400045c6  call    cs:__imp_ReleaseMutex
0x1400045cc  test    eax, eax
0x1400045ce  jz      loc_140004817
0x1400045d4  mov     rcx, rbx; hObject
0x1400045d7  call    cs:__imp_CloseHandle
0x1400045dd  test    eax, eax
0x1400045df  jz      loc_140004829
0x1400045e5  mov     eax, esi
0x1400045e7  jmp     loc_1400047C0
0x1400045ec  mov     rax, [rsp+280h+hObject]
0x1400045f1  lea     rcx, ds:0[rax*4]
0x1400045f9  test    rcx, rcx
0x1400045fc  jz      short loc_14000460C
0x1400045fe  mov     [r15], rcx
0x140004601  mov     eax, [rcx]
0x140004603  inc     eax
0x140004605  mov     [rcx], eax
0x140004607  jmp     loc_140004796
0x14000460c  mov     rdx, r14; dwBytes
0x14000460f  mov     qword ptr [r15], 0
0x140004616  mov     ecx, 8; dwFlags
0x14000461b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004620  mov     r14, rax
0x140004623  test    rax, rax
0x140004626  jnz     short loc_14000464D
0x140004628  mov     rcx, [rbp+188h]; this
0x14000462f  lea     r8, aWil; "wil"
0x140004636  mov     esi, 8007000Eh
0x14000463b  mov     edx, 14Bh; void *
0x140004640  mov     r9d, esi; char *
0x140004643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004648  jmp     loc_1400046DF
0x14000464d  xorps   xmm0, xmm0
0x140004650  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140004656  test    r14b, 3
0x14000465a  jnz     loc_14000483B
0x140004660  mov     r9, r14
0x140004663  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140004668  shr     r9, 2; unsigned __int64
0x14000466c  lea     rcx, [rsp+280h+hObject]; this
0x140004671  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140004676  mov     esi, eax
0x140004678  test    eax, eax
0x14000467a  jns     loc_140004726
0x140004680  mov     rcx, [rbp+188h]; this
0x140004687  lea     r8, aWil; "wil"
0x14000468e  mov     r9d, eax; char *
0x140004691  mov     edx, 14Eh; void *
0x140004696  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000469b  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1400046a0  test    rcx, rcx
0x1400046a3  jz      short loc_1400046B3
0x1400046a5  call    cs:__imp_CloseHandle
0x1400046ab  test    eax, eax
0x1400046ad  jz      loc_140004841
0x1400046b3  mov     rcx, [rsp+280h+hObject]; hObject
0x1400046b8  test    rcx, rcx
0x1400046bb  jz      short loc_1400046CB
0x1400046bd  call    cs:__imp_CloseHandle
0x1400046c3  test    eax, eax
0x1400046c5  jz      loc_140004853
0x1400046cb  call    cs:__imp_GetProcessHeap
0x1400046d1  mov     r8, r14; lpMem
0x1400046d4  xor     edx, edx; dwFlags
0x1400046d6  mov     rcx, rax; hHeap
0x1400046d9  call    cs:__imp_HeapFree
0x1400046df  mov     rcx, [rbp+188h]; this
0x1400046e6  lea     r8, aWil; "wil"
0x1400046ed  mov     r9d, esi; char *
0x1400046f0  mov     edx, 137h; void *
0x1400046f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400046fa  test    rdi, rdi
0x1400046fd  jz      short loc_140004710
0x1400046ff  mov     rcx, rdi; hMutex
0x140004702  call    cs:__imp_ReleaseMutex
0x140004708  test    eax, eax
0x14000470a  jz      loc_140004865
0x140004710  mov     rcx, rbx; hObject
0x140004713  call    cs:__imp_CloseHandle
0x140004719  test    eax, eax
0x14000471b  jz      loc_1400047F8
0x140004721  jmp     loc_1400045E5
0x140004726  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x14000472b  lea     rcx, [r14+28h]; void *
0x14000472f  mov     dword ptr [r14], 1
0x140004736  xor     edx, edx; Val
0x140004738  mov     [r14+8], rbx
0x14000473c  mov     r8d, 108h; Size
0x140004742  movdqu  xmmword ptr [r14+10h], xmm0
0x140004748  call    memset_0
0x14000474d  xor     eax, eax
0x14000474f  lea     rcx, [r14+28h]; this
0x140004753  mov     [r14+20h], rax
0x140004757  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000475c  lea     rbx, [r14+0E8h]
0x140004763  xor     r8d, r8d; Flags
0x140004766  mov     rcx, rbx; lpCriticalSection
0x140004769  xor     edx, edx; dwSpinCount
0x14000476b  call    cs:__imp_InitializeCriticalSectionEx
0x140004771  mov     qword ptr [rbx+28h], 0
0x140004779  mov     qword ptr [rbx+30h], 0
0x140004781  mov     qword ptr [rbx+38h], 0
0x140004789  mov     qword ptr [rbx+40h], 0
0x140004791  xor     ebx, ebx
0x140004793  mov     [r15], r14
0x140004796  test    rdi, rdi
0x140004799  jz      short loc_1400047AC
0x14000479b  mov     rcx, rdi; hMutex
0x14000479e  call    cs:__imp_ReleaseMutex
0x1400047a4  test    eax, eax
0x1400047a6  jz      loc_140004877
0x1400047ac  test    rbx, rbx
0x1400047af  jz      short loc_1400047BE
0x1400047b1  mov     rcx, rbx; hObject
0x1400047b4  call    cs:__imp_CloseHandle
0x1400047ba  test    eax, eax
0x1400047bc  jz      short loc_1400047E6
0x1400047be  xor     eax, eax
0x1400047c0  mov     rcx, [rbp+180h+var_30]
0x1400047c7  xor     rcx, rsp; StackCookie
0x1400047ca  call    __security_check_cookie
0x1400047cf  mov     rbx, [rsp+280h+arg_10]
0x1400047d7  add     rsp, 260h
0x1400047de  pop     r15
0x1400047e0  pop     r14
0x1400047e2  pop     rdi
0x1400047e3  pop     rsi
0x1400047e4  pop     rbp
0x1400047e5  retn
0x1400047e6  mov     rcx, [rbp+188h]; this
0x1400047ed  mov     edx, 0A0Bh; void *
0x1400047f2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400047f8  mov     rcx, [rbp+188h]; this
0x1400047ff  mov     edx, 0A0Bh; void *
0x140004804  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000480a  mov     rcx, [rbp+188h]; this
0x140004811  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140004817  mov     rcx, [rbp+188h]; this
0x14000481e  mov     edx, 0A15h; void *
0x140004823  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004829  mov     rcx, [rbp+188h]; this
0x140004830  mov     edx, 0A0Bh; void *
0x140004835  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000483b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004841  mov     rcx, [rbp+188h]; this
0x140004848  mov     edx, 0A0Bh; void *
0x14000484d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004853  mov     rcx, [rbp+188h]; this
0x14000485a  mov     edx, 0A0Bh; void *
0x14000485f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004865  mov     rcx, [rbp+188h]; this
0x14000486c  mov     edx, 0A15h; void *
0x140004871  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140004877  mov     rcx, [rbp+188h]; this
0x14000487e  mov     edx, 0A15h; void *
0x140004883  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
