# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140008710`
- end: `0x140008b01`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140008f64`

## callees

- `0x14000295f`
- `0x140003d30`
- `0x140004014`
- `0x1400045a8`
- `0x140005088`
- `0x140005474`
- `0x140005ca4`
- `0x140005d7c`
- `0x140006234`
- `0x140006244`
- `0x140007af8`
- `0x140008710`
- `0x14000e1c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008951`
- `KERNEL32!HeapFree` at `0x140008951`
- `KERNEL32!ReleaseMutex` at `0x14000883e`
- `KERNEL32!ReleaseMutex` at `0x14000897a`
- `KERNEL32!ReleaseMutex` at `0x140008a16`
- `KERNEL32!ReleaseMutex` at `0x14000883e`
- `KERNEL32!ReleaseMutex` at `0x14000897a`
- `KERNEL32!ReleaseMutex` at `0x140008a16`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400087a8`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400087a8`
- `KERNEL32!CloseHandle` at `0x14000884f`
- `KERNEL32!CloseHandle` at `0x14000891d`
- `KERNEL32!CloseHandle` at `0x140008935`
- `KERNEL32!CloseHandle` at `0x14000898b`
- `KERNEL32!CloseHandle` at `0x140008a2c`
- `KERNEL32!CloseHandle` at `0x14000884f`
- `KERNEL32!CloseHandle` at `0x14000891d`
- `KERNEL32!CloseHandle` at `0x140008935`
- `KERNEL32!CloseHandle` at `0x14000898b`
- `KERNEL32!CloseHandle` at `0x140008a2c`
- `KERNEL32!CreateMutexExW` at `0x140008787`
- `KERNEL32!CreateMutexExW` at `0x140008787`
- `KERNEL32!GetCurrentProcessId` at `0x140008749`
- `KERNEL32!GetCurrentProcessId` at `0x140008749`
- `KERNEL32!GetProcessHeap` at `0x140008943`
- `KERNEL32!GetProcessHeap` at `0x140008943`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400089e3`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1400089e3`

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
0x140008710  mov     [rsp-8+arg_10], rbx
0x140008715  push    rbp
0x140008716  push    rsi
0x140008717  push    rdi
0x140008718  push    r14
0x14000871a  push    r15
0x14000871c  lea     rbp, [rsp-160h]
0x140008724  sub     rsp, 260h
0x14000872b  mov     rax, cs:__security_cookie
0x140008732  xor     rax, rsp
0x140008735  mov     [rbp+180h+var_30], rax
0x14000873c  mov     r15, rdx
0x14000873f  mov     qword ptr [rdx], 0
0x140008746  mov     rbx, rcx
0x140008749  call    cs:__imp_GetCurrentProcessId
0x14000874f  mov     r14d, 130h
0x140008755  mov     [rsp+280h+var_258], rbx
0x14000875a  mov     r9d, eax
0x14000875d  mov     [rsp+280h+var_260], r14d; int
0x140008762  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140008769  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000876e  lea     edx, [r14-2Ch]; unsigned __int64
0x140008772  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008777  mov     r9d, 1F0001h; dwDesiredAccess
0x14000877d  lea     rdx, [rsp+280h+Name]; lpName
0x140008782  xor     r8d, r8d; dwFlags
0x140008785  xor     ecx, ecx; lpMutexAttributes
0x140008787  call    cs:__imp_CreateMutexExW
0x14000878d  mov     rbx, rax
0x140008790  test    rax, rax
0x140008793  jnz     short loc_14000879F
0x140008795  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000879a  jmp     loc_140008A38
0x14000879f  xor     r8d, r8d; bAlertable
0x1400087a2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400087a5  mov     rcx, rbx; hHandle
0x1400087a8  call    cs:__imp_WaitForSingleObjectEx
0x1400087ae  cmp     eax, 102h
0x1400087b3  jz      short loc_1400087C5
0x1400087b5  test    eax, 0FFFFFF7Fh
0x1400087ba  jnz     loc_140008A82
0x1400087c0  mov     rdi, rbx
0x1400087c3  jmp     short loc_1400087C7
0x1400087c5  xor     edi, edi
0x1400087c7  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x1400087cc  mov     [rsp+280h+hObject], 0
0x1400087d5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400087da  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1400087df  mov     esi, eax
0x1400087e1  test    eax, eax
0x1400087e3  jns     short loc_140008864
0x1400087e5  mov     rcx, [rbp+188h]; this
0x1400087ec  lea     r8, aWil; "wil"
0x1400087f3  mov     r9d, eax; char *
0x1400087f6  mov     edx, 66h ; 'f'; void *
0x1400087fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008800  mov     rcx, [rbp+188h]; this
0x140008807  lea     r8, aWil; "wil"
0x14000880e  mov     r9d, esi; char *
0x140008811  mov     edx, 6Fh ; 'o'; void *
0x140008816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000881b  mov     rcx, [rbp+188h]; this
0x140008822  lea     r8, aWil; "wil"
0x140008829  mov     r9d, esi; char *
0x14000882c  mov     edx, 12Eh; void *
0x140008831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008836  test    rdi, rdi
0x140008839  jz      short loc_14000884C
0x14000883b  mov     rcx, rdi; hMutex
0x14000883e  call    cs:__imp_ReleaseMutex
0x140008844  test    eax, eax
0x140008846  jz      loc_140008A8F
0x14000884c  mov     rcx, rbx; hObject
0x14000884f  call    cs:__imp_CloseHandle
0x140008855  test    eax, eax
0x140008857  jz      loc_140008AA1
0x14000885d  mov     eax, esi
0x14000885f  jmp     loc_140008A38
0x140008864  mov     rax, [rsp+280h+hObject]
0x140008869  lea     rcx, ds:0[rax*4]
0x140008871  test    rcx, rcx
0x140008874  jz      short loc_140008884
0x140008876  mov     [r15], rcx
0x140008879  mov     eax, [rcx]
0x14000887b  inc     eax
0x14000887d  mov     [rcx], eax
0x14000887f  jmp     loc_140008A0E
0x140008884  mov     rdx, r14; dwBytes
0x140008887  mov     qword ptr [r15], 0
0x14000888e  mov     ecx, 8; dwFlags
0x140008893  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008898  mov     r14, rax
0x14000889b  test    rax, rax
0x14000889e  jnz     short loc_1400088C5
0x1400088a0  mov     rcx, [rbp+188h]; this
0x1400088a7  lea     r8, aWil; "wil"
0x1400088ae  mov     esi, 8007000Eh
0x1400088b3  mov     edx, 14Bh; void *
0x1400088b8  mov     r9d, esi; char *
0x1400088bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400088c0  jmp     loc_140008957
0x1400088c5  xorps   xmm0, xmm0
0x1400088c8  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x1400088ce  test    r14b, 3
0x1400088d2  jnz     loc_140008AB3
0x1400088d8  mov     r9, r14
0x1400088db  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x1400088e0  shr     r9, 2; unsigned __int64
0x1400088e4  lea     rcx, [rsp+280h+hObject]; this
0x1400088e9  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1400088ee  mov     esi, eax
0x1400088f0  test    eax, eax
0x1400088f2  jns     loc_14000899E
0x1400088f8  mov     rcx, [rbp+188h]; this
0x1400088ff  lea     r8, aWil; "wil"
0x140008906  mov     r9d, eax; char *
0x140008909  mov     edx, 14Eh; void *
0x14000890e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008913  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140008918  test    rcx, rcx
0x14000891b  jz      short loc_14000892B
0x14000891d  call    cs:__imp_CloseHandle
0x140008923  test    eax, eax
0x140008925  jz      loc_140008AB9
0x14000892b  mov     rcx, [rsp+280h+hObject]; hObject
0x140008930  test    rcx, rcx
0x140008933  jz      short loc_140008943
0x140008935  call    cs:__imp_CloseHandle
0x14000893b  test    eax, eax
0x14000893d  jz      loc_140008ACB
0x140008943  call    cs:__imp_GetProcessHeap
0x140008949  mov     r8, r14; lpMem
0x14000894c  xor     edx, edx; dwFlags
0x14000894e  mov     rcx, rax; hHeap
0x140008951  call    cs:__imp_HeapFree
0x140008957  mov     rcx, [rbp+188h]; this
0x14000895e  lea     r8, aWil; "wil"
0x140008965  mov     r9d, esi; char *
0x140008968  mov     edx, 137h; void *
0x14000896d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008972  test    rdi, rdi
0x140008975  jz      short loc_140008988
0x140008977  mov     rcx, rdi; hMutex
0x14000897a  call    cs:__imp_ReleaseMutex
0x140008980  test    eax, eax
0x140008982  jz      loc_140008ADD
0x140008988  mov     rcx, rbx; hObject
0x14000898b  call    cs:__imp_CloseHandle
0x140008991  test    eax, eax
0x140008993  jz      loc_140008A70
0x140008999  jmp     loc_14000885D
0x14000899e  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400089a3  lea     rcx, [r14+28h]; void *
0x1400089a7  mov     dword ptr [r14], 1
0x1400089ae  xor     edx, edx; Val
0x1400089b0  mov     [r14+8], rbx
0x1400089b4  mov     r8d, 108h; Size
0x1400089ba  movdqu  xmmword ptr [r14+10h], xmm0
0x1400089c0  call    memset_0
0x1400089c5  xor     eax, eax
0x1400089c7  lea     rcx, [r14+28h]; this
0x1400089cb  mov     [r14+20h], rax
0x1400089cf  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400089d4  lea     rbx, [r14+0E8h]
0x1400089db  xor     r8d, r8d; Flags
0x1400089de  mov     rcx, rbx; lpCriticalSection
0x1400089e1  xor     edx, edx; dwSpinCount
0x1400089e3  call    cs:__imp_InitializeCriticalSectionEx
0x1400089e9  mov     qword ptr [rbx+28h], 0
0x1400089f1  mov     qword ptr [rbx+30h], 0
0x1400089f9  mov     qword ptr [rbx+38h], 0
0x140008a01  mov     qword ptr [rbx+40h], 0
0x140008a09  xor     ebx, ebx
0x140008a0b  mov     [r15], r14
0x140008a0e  test    rdi, rdi
0x140008a11  jz      short loc_140008A24
0x140008a13  mov     rcx, rdi; hMutex
0x140008a16  call    cs:__imp_ReleaseMutex
0x140008a1c  test    eax, eax
0x140008a1e  jz      loc_140008AEF
0x140008a24  test    rbx, rbx
0x140008a27  jz      short loc_140008A36
0x140008a29  mov     rcx, rbx; hObject
0x140008a2c  call    cs:__imp_CloseHandle
0x140008a32  test    eax, eax
0x140008a34  jz      short loc_140008A5E
0x140008a36  xor     eax, eax
0x140008a38  mov     rcx, [rbp+180h+var_30]
0x140008a3f  xor     rcx, rsp; StackCookie
0x140008a42  call    __security_check_cookie
0x140008a47  mov     rbx, [rsp+280h+arg_10]
0x140008a4f  add     rsp, 260h
0x140008a56  pop     r15
0x140008a58  pop     r14
0x140008a5a  pop     rdi
0x140008a5b  pop     rsi
0x140008a5c  pop     rbp
0x140008a5d  retn
0x140008a5e  mov     rcx, [rbp+188h]; this
0x140008a65  mov     edx, 0A0Bh; void *
0x140008a6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008a70  mov     rcx, [rbp+188h]; this
0x140008a77  mov     edx, 0A0Bh; void *
0x140008a7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008a82  mov     rcx, [rbp+188h]; this
0x140008a89  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140008a8f  mov     rcx, [rbp+188h]; this
0x140008a96  mov     edx, 0A15h; void *
0x140008a9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008aa1  mov     rcx, [rbp+188h]; this
0x140008aa8  mov     edx, 0A0Bh; void *
0x140008aad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008ab3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140008ab9  mov     rcx, [rbp+188h]; this
0x140008ac0  mov     edx, 0A0Bh; void *
0x140008ac5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008acb  mov     rcx, [rbp+188h]; this
0x140008ad2  mov     edx, 0A0Bh; void *
0x140008ad7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008add  mov     rcx, [rbp+188h]; this
0x140008ae4  mov     edx, 0A15h; void *
0x140008ae9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008aef  mov     rcx, [rbp+188h]; this
0x140008af6  mov     edx, 0A15h; void *
0x140008afb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
