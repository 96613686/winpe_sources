# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800125e0`
- end: `0x1800129a7`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `967`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180012c84`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180003d7c`
- `0x18000c600`
- `0x180011b2c`
- `0x1800125e0`
- `0x1800129b0`
- `0x180012e14`
- `0x180013738`
- `0x180015630`
- `0x180015d78`
- `0x1800165b8`
- `0x1800165c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012619`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001270a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800128d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001270a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800127e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800128d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012678`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180012678`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012820`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800128bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012820`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800128bc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180012889`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180012889`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012657`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012657`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800127fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800127fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800127f0`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _DWORD *v26; // r14
  unsigned int v27; // r8d
  int v28; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  __int128 v39; // xmm0
  unsigned int v40; // r8d
  const char *v41; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v44);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v45);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v14);
  v26 = (_DWORD *)v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v27, (const char *)v15, v46);
    if ( v12 && !ReleaseMutex(v12) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v35, v36);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
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
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
    goto LABEL_23;
  }
  v39 = *(_OWORD *)hObject;
  *v26 = 1;
  *((_QWORD *)v26 + 1) = v6;
  *((_OWORD *)v26 + 1) = v39;
  memset_0(v26 + 10, 0, 0x108u);
  *((_QWORD *)v26 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v26 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v26 + 58), 0, 0);
  *((_QWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 35) = 0;
  *((_QWORD *)v26 + 36) = 0;
  *((_QWORD *)v26 + 37) = 0;
  v6 = 0;
  *a2 = v26;
LABEL_28:
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v40, v41);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  return 0;
}

```

## disassembly

```asm
0x1800125e0  mov     [rsp-8+arg_10], rbx
0x1800125e5  push    rbp
0x1800125e6  push    rsi
0x1800125e7  push    rdi
0x1800125e8  push    r14
0x1800125ea  push    r15
0x1800125ec  lea     rbp, [rsp-160h]
0x1800125f4  sub     rsp, 260h
0x1800125fb  mov     rax, cs:__security_cookie
0x180012602  xor     rax, rsp
0x180012605  mov     [rbp+180h+var_30], rax
0x18001260c  mov     r15, rdx
0x18001260f  mov     qword ptr [rdx], 0
0x180012616  mov     rbx, rcx
0x180012619  call    cs:__imp_GetCurrentProcessId
0x18001261f  mov     r14d, 130h
0x180012625  mov     [rsp+280h+var_258], rbx
0x18001262a  mov     r9d, eax
0x18001262d  mov     [rsp+280h+var_260], r14d; int
0x180012632  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180012639  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001263e  lea     edx, [r14-2Ch]; unsigned __int64
0x180012642  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012647  mov     r9d, 1F0001h; dwDesiredAccess
0x18001264d  lea     rdx, [rsp+280h+Name]; lpName
0x180012652  xor     r8d, r8d; dwFlags
0x180012655  xor     ecx, ecx; lpMutexAttributes
0x180012657  call    cs:__imp_CreateMutexExW
0x18001265d  mov     rbx, rax
0x180012660  test    rax, rax
0x180012663  jnz     short loc_18001266F
0x180012665  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001266a  jmp     loc_1800128DE
0x18001266f  xor     r8d, r8d; bAlertable
0x180012672  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012675  mov     rcx, rbx; hHandle
0x180012678  call    cs:__imp_WaitForSingleObjectEx
0x18001267e  cmp     eax, 102h
0x180012683  jz      short loc_180012695
0x180012685  test    eax, 0FFFFFF7Fh
0x18001268a  jnz     loc_180012928
0x180012690  mov     rdi, rbx
0x180012693  jmp     short loc_180012697
0x180012695  xor     edi, edi
0x180012697  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x18001269c  mov     [rsp+280h+hObject], 0
0x1800126a5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800126aa  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800126af  mov     esi, eax
0x1800126b1  test    eax, eax
0x1800126b3  jns     short loc_18001271F
0x1800126b5  mov     rcx, [rbp+188h]; this
0x1800126bc  mov     r9d, eax; char *
0x1800126bf  mov     edx, 66h ; 'f'; void *
0x1800126c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126c9  mov     rcx, [rbp+188h]; this
0x1800126d0  mov     r9d, esi; char *
0x1800126d3  mov     edx, 6Fh ; 'o'; void *
0x1800126d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126dd  mov     rcx, [rbp+188h]; this
0x1800126e4  mov     r9d, esi; char *
0x1800126e7  mov     edx, 12Eh; void *
0x1800126ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800126f1  test    rdi, rdi
0x1800126f4  jz      short loc_180012707
0x1800126f6  mov     rcx, rdi; hMutex
0x1800126f9  call    cs:__imp_ReleaseMutex
0x1800126ff  test    eax, eax
0x180012701  jz      loc_180012935
0x180012707  mov     rcx, rbx; hObject
0x18001270a  call    cs:__imp_CloseHandle
0x180012710  test    eax, eax
0x180012712  jz      loc_180012947
0x180012718  mov     eax, esi
0x18001271a  jmp     loc_1800128DE
0x18001271f  mov     rax, [rsp+280h+hObject]
0x180012724  lea     rcx, ds:0[rax*4]
0x18001272c  test    rcx, rcx
0x18001272f  jz      short loc_18001273F
0x180012731  mov     [r15], rcx
0x180012734  mov     eax, [rcx]
0x180012736  inc     eax
0x180012738  mov     [rcx], eax
0x18001273a  jmp     loc_1800128B4
0x18001273f  mov     rdx, r14; dwBytes
0x180012742  mov     qword ptr [r15], 0
0x180012749  mov     ecx, 8; dwFlags
0x18001274e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180012753  mov     r14, rax
0x180012756  test    rax, rax
0x180012759  jnz     short loc_180012779
0x18001275b  mov     rcx, [rbp+188h]; this
0x180012762  mov     esi, 8007000Eh
0x180012767  mov     r9d, esi; char *
0x18001276a  mov     edx, 14Bh; void *
0x18001276f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012774  jmp     loc_180012804
0x180012779  xorps   xmm0, xmm0
0x18001277c  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180012782  test    r14b, 3
0x180012786  jnz     loc_180012959
0x18001278c  mov     r9, r14
0x18001278f  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180012794  shr     r9, 2; unsigned __int64
0x180012798  lea     rcx, [rsp+280h+hObject]; this
0x18001279d  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x1800127a2  mov     esi, eax
0x1800127a4  test    eax, eax
0x1800127a6  jns     loc_180012844
0x1800127ac  mov     rcx, [rbp+188h]; this
0x1800127b3  mov     r9d, eax; char *
0x1800127b6  mov     edx, 14Eh; void *
0x1800127bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800127c0  mov     rcx, [rsp+280h+hObject+8]; hObject
0x1800127c5  test    rcx, rcx
0x1800127c8  jz      short loc_1800127D8
0x1800127ca  call    cs:__imp_CloseHandle
0x1800127d0  test    eax, eax
0x1800127d2  jz      loc_18001295F
0x1800127d8  mov     rcx, [rsp+280h+hObject]; hObject
0x1800127dd  test    rcx, rcx
0x1800127e0  jz      short loc_1800127F0
0x1800127e2  call    cs:__imp_CloseHandle
0x1800127e8  test    eax, eax
0x1800127ea  jz      loc_180012971
0x1800127f0  call    cs:__imp_GetProcessHeap
0x1800127f6  mov     r8, r14; lpMem
0x1800127f9  xor     edx, edx; dwFlags
0x1800127fb  mov     rcx, rax; hHeap
0x1800127fe  call    cs:__imp_HeapFree
0x180012804  mov     rcx, [rbp+188h]; this
0x18001280b  mov     r9d, esi; char *
0x18001280e  mov     edx, 137h; void *
0x180012813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012818  test    rdi, rdi
0x18001281b  jz      short loc_18001282E
0x18001281d  mov     rcx, rdi; hMutex
0x180012820  call    cs:__imp_ReleaseMutex
0x180012826  test    eax, eax
0x180012828  jz      loc_180012983
0x18001282e  mov     rcx, rbx; hObject
0x180012831  call    cs:__imp_CloseHandle
0x180012837  test    eax, eax
0x180012839  jz      loc_180012916
0x18001283f  jmp     loc_180012718
0x180012844  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180012849  lea     rcx, [r14+28h]; void *
0x18001284d  mov     dword ptr [r14], 1
0x180012854  xor     edx, edx; Val
0x180012856  mov     [r14+8], rbx
0x18001285a  mov     r8d, 108h; Size
0x180012860  movdqu  xmmword ptr [r14+10h], xmm0
0x180012866  call    memset_0
0x18001286b  xor     eax, eax
0x18001286d  lea     rcx, [r14+28h]; this
0x180012871  mov     [r14+20h], rax
0x180012875  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001287a  lea     rbx, [r14+0E8h]
0x180012881  xor     r8d, r8d; Flags
0x180012884  mov     rcx, rbx; lpCriticalSection
0x180012887  xor     edx, edx; dwSpinCount
0x180012889  call    cs:__imp_InitializeCriticalSectionEx
0x18001288f  mov     qword ptr [rbx+28h], 0
0x180012897  mov     qword ptr [rbx+30h], 0
0x18001289f  mov     qword ptr [rbx+38h], 0
0x1800128a7  mov     qword ptr [rbx+40h], 0
0x1800128af  xor     ebx, ebx
0x1800128b1  mov     [r15], r14
0x1800128b4  test    rdi, rdi
0x1800128b7  jz      short loc_1800128CA
0x1800128b9  mov     rcx, rdi; hMutex
0x1800128bc  call    cs:__imp_ReleaseMutex
0x1800128c2  test    eax, eax
0x1800128c4  jz      loc_180012995
0x1800128ca  test    rbx, rbx
0x1800128cd  jz      short loc_1800128DC
0x1800128cf  mov     rcx, rbx; hObject
0x1800128d2  call    cs:__imp_CloseHandle
0x1800128d8  test    eax, eax
0x1800128da  jz      short loc_180012904
0x1800128dc  xor     eax, eax
0x1800128de  mov     rcx, [rbp+180h+var_30]
0x1800128e5  xor     rcx, rsp; StackCookie
0x1800128e8  call    __security_check_cookie
0x1800128ed  mov     rbx, [rsp+280h+arg_10]
0x1800128f5  add     rsp, 260h
0x1800128fc  pop     r15
0x1800128fe  pop     r14
0x180012900  pop     rdi
0x180012901  pop     rsi
0x180012902  pop     rbp
0x180012903  retn
0x180012904  mov     rcx, [rbp+188h]; this
0x18001290b  mov     edx, 0A0Bh; void *
0x180012910  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012916  mov     rcx, [rbp+188h]; this
0x18001291d  mov     edx, 0A0Bh; void *
0x180012922  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012928  mov     rcx, [rbp+188h]; this
0x18001292f  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180012935  mov     rcx, [rbp+188h]; this
0x18001293c  mov     edx, 0A15h; void *
0x180012941  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012947  mov     rcx, [rbp+188h]; this
0x18001294e  mov     edx, 0A0Bh; void *
0x180012953  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012959  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001295f  mov     rcx, [rbp+188h]; this
0x180012966  mov     edx, 0A0Bh; void *
0x18001296b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012971  mov     rcx, [rbp+188h]; this
0x180012978  mov     edx, 0A0Bh; void *
0x18001297d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012983  mov     rcx, [rbp+188h]; this
0x18001298a  mov     edx, 0A15h; void *
0x18001298f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012995  mov     rcx, [rbp+188h]; this
0x18001299c  mov     edx, 0A15h; void *
0x1800129a1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
