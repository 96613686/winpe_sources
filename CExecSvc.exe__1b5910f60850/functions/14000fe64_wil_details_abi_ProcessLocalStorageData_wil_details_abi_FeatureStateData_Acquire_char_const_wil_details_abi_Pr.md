# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x14000fe64`
- end: `0x140010237`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x1400104d0`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x140009108`
- `0x140009490`
- `0x140009b40`
- `0x14000ba08`
- `0x14000bf34`
- `0x14000d17c`
- `0x14000d358`
- `0x14000e394`
- `0x14000e3a4`
- `0x14000f6dc`
- `0x14000fe64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ff7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400100a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010140`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x14000ff7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400100a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140010140`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000fefc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14000fefc`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000fedb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000fedb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14001010d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x14001010d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010082`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010074`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010074`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000fe9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000fe9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ff8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001004e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400100b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010156`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ff8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001004e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400100b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140010156`

## string_xrefs

- `0x1400101b3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  bool v9; // dl
  char *v10; // r9
  void *v11; // rdi
  int ValueInternal; // eax
  unsigned __int64 v13; // r8
  unsigned int v14; // esi
  unsigned int v15; // r8d
  unsigned int v16; // r8d
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  const char *v20; // r9
  _DWORD *v21; // rcx
  unsigned __int64 v22; // rax
  wil::details::in1diag3 *v23; // rcx
  unsigned int v24; // r8d
  _DWORD *v25; // r14
  unsigned int v26; // r8d
  int v27; // eax
  unsigned int v28; // r8d
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  HANDLE ProcessHeap; // rax
  __int64 v34; // r8
  const char *v35; // r9
  __int64 v36; // r8
  const char *v37; // r9
  __int128 v38; // xmm0
  __int64 v39; // r8
  const char *v40; // r9
  __int64 v41; // r8
  const char *v42; // r9
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
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
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  hObject[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(
                    Name,
                    v9,
                    (unsigned __int64 *)hObject,
                    (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v13, (const char *)(unsigned int)ValueInternal, 304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v15, (const char *)v14, v43);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v16, (const char *)v14, v44);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v17, v18);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
    return v14;
  }
  v21 = (_DWORD *)(4 * (__int64)hObject[0]);
  if ( 4 * (__int64)hObject[0] )
  {
    *a2 = v21;
    ++*v21;
    goto LABEL_28;
  }
  *a2 = 0;
  v22 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x130u, v13);
  v25 = (_DWORD *)v22;
  if ( !v22 )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v24, (const char *)0x8007000ELL, 304);
LABEL_23:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v26, (const char *)v14, v45);
    if ( v11 && !ReleaseMutex(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v34, v35);
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
    return v14;
  }
  *(_OWORD *)hObject = 0;
  if ( (v22 & 3) != 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
  v27 = wil::details_abi::SemaphoreValue::CreateFromValueInternal(
          (wil::details_abi::SemaphoreValue *)hObject,
          Name,
          v24,
          v22 >> 2);
  v14 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v28, (const char *)(unsigned int)v27, 304);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v25);
    goto LABEL_23;
  }
  v38 = *(_OWORD *)hObject;
  *v25 = 1;
  *((_QWORD *)v25 + 1) = v6;
  *((_OWORD *)v25 + 1) = v38;
  memset_0(v25 + 10, 0, 0x108u);
  *((_QWORD *)v25 + 4) = 0;
  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)(v25 + 10));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v25 + 58), 0, 0);
  *((_QWORD *)v25 + 34) = 0;
  *((_QWORD *)v25 + 35) = 0;
  *((_QWORD *)v25 + 36) = 0;
  *((_QWORD *)v25 + 37) = 0;
  v6 = 0;
  *a2 = v25;
LABEL_28:
  if ( v11 && !ReleaseMutex(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v39, v40);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v41, v42);
  return 0;
}

```

## disassembly

```asm
0x14000fe64  mov     [rsp-8+arg_10], rbx
0x14000fe69  push    rbp
0x14000fe6a  push    rsi
0x14000fe6b  push    rdi
0x14000fe6c  push    r14
0x14000fe6e  push    r15
0x14000fe70  lea     rbp, [rsp-160h]
0x14000fe78  sub     rsp, 260h
0x14000fe7f  mov     rax, cs:__security_cookie
0x14000fe86  xor     rax, rsp
0x14000fe89  mov     [rbp+180h+var_30], rax
0x14000fe90  mov     r15, rdx
0x14000fe93  mov     qword ptr [rdx], 0
0x14000fe9a  mov     rbx, rcx
0x14000fe9d  call    cs:__imp_GetCurrentProcessId
0x14000fea3  mov     r14d, 130h
0x14000fea9  mov     [rsp+280h+var_258], rbx
0x14000feae  mov     r9d, eax
0x14000feb1  mov     [rsp+280h+var_260], r14d; int
0x14000feb6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000febd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000fec2  lea     edx, [r14-2Ch]; unsigned __int64
0x14000fec6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000fecb  mov     r9d, 1F0001h; dwDesiredAccess
0x14000fed1  lea     rdx, [rsp+280h+Name]; lpName
0x14000fed6  xor     r8d, r8d; dwFlags
0x14000fed9  xor     ecx, ecx; lpMutexAttributes
0x14000fedb  call    cs:__imp_CreateMutexExW
0x14000fee1  mov     rbx, rax
0x14000fee4  test    rax, rax
0x14000fee7  jnz     short loc_14000FEF3
0x14000fee9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000feee  jmp     loc_140010162
0x14000fef3  xor     r8d, r8d; bAlertable
0x14000fef6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000fef9  mov     rcx, rbx; hHandle
0x14000fefc  call    cs:__imp_WaitForSingleObjectEx
0x14000ff02  cmp     eax, 102h
0x14000ff07  jz      short loc_14000FF19
0x14000ff09  test    eax, 0FFFFFF7Fh
0x14000ff0e  jnz     loc_1400101AC
0x14000ff14  mov     rdi, rbx
0x14000ff17  jmp     short loc_14000FF1B
0x14000ff19  xor     edi, edi
0x14000ff1b  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x14000ff20  mov     [rsp+280h+hObject], 0
0x14000ff29  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ff2e  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000ff33  mov     esi, eax
0x14000ff35  test    eax, eax
0x14000ff37  jns     short loc_14000FFA3
0x14000ff39  mov     rcx, [rbp+188h]; this
0x14000ff40  mov     r9d, eax; char *
0x14000ff43  mov     edx, 66h ; 'f'; void *
0x14000ff48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ff4d  mov     rcx, [rbp+188h]; this
0x14000ff54  mov     r9d, esi; char *
0x14000ff57  mov     edx, 6Fh ; 'o'; void *
0x14000ff5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ff61  mov     rcx, [rbp+188h]; this
0x14000ff68  mov     r9d, esi; char *
0x14000ff6b  mov     edx, 12Eh; void *
0x14000ff70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ff75  test    rdi, rdi
0x14000ff78  jz      short loc_14000FF8B
0x14000ff7a  mov     rcx, rdi; hMutex
0x14000ff7d  call    cs:__imp_ReleaseMutex
0x14000ff83  test    eax, eax
0x14000ff85  jz      loc_1400101C5
0x14000ff8b  mov     rcx, rbx; hObject
0x14000ff8e  call    cs:__imp_CloseHandle
0x14000ff94  test    eax, eax
0x14000ff96  jz      loc_1400101D7
0x14000ff9c  mov     eax, esi
0x14000ff9e  jmp     loc_140010162
0x14000ffa3  mov     rax, [rsp+280h+hObject]
0x14000ffa8  lea     rcx, ds:0[rax*4]
0x14000ffb0  test    rcx, rcx
0x14000ffb3  jz      short loc_14000FFC3
0x14000ffb5  mov     [r15], rcx
0x14000ffb8  mov     eax, [rcx]
0x14000ffba  inc     eax
0x14000ffbc  mov     [rcx], eax
0x14000ffbe  jmp     loc_140010138
0x14000ffc3  mov     rdx, r14; dwBytes
0x14000ffc6  mov     qword ptr [r15], 0
0x14000ffcd  mov     ecx, 8; dwFlags
0x14000ffd2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000ffd7  mov     r14, rax
0x14000ffda  test    rax, rax
0x14000ffdd  jnz     short loc_14000FFFD
0x14000ffdf  mov     rcx, [rbp+188h]; this
0x14000ffe6  mov     esi, 8007000Eh
0x14000ffeb  mov     r9d, esi; char *
0x14000ffee  mov     edx, 14Bh; void *
0x14000fff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000fff8  jmp     loc_140010088
0x14000fffd  xorps   xmm0, xmm0
0x140010000  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140010006  test    r14b, 3
0x14001000a  jnz     loc_1400101E9
0x140010010  mov     r9, r14
0x140010013  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140010018  shr     r9, 2; unsigned __int64
0x14001001c  lea     rcx, [rsp+280h+hObject]; this
0x140010021  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140010026  mov     esi, eax
0x140010028  test    eax, eax
0x14001002a  jns     loc_1400100C8
0x140010030  mov     rcx, [rbp+188h]; this
0x140010037  mov     r9d, eax; char *
0x14001003a  mov     edx, 14Eh; void *
0x14001003f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010044  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140010049  test    rcx, rcx
0x14001004c  jz      short loc_14001005C
0x14001004e  call    cs:__imp_CloseHandle
0x140010054  test    eax, eax
0x140010056  jz      loc_1400101EF
0x14001005c  mov     rcx, [rsp+280h+hObject]; hObject
0x140010061  test    rcx, rcx
0x140010064  jz      short loc_140010074
0x140010066  call    cs:__imp_CloseHandle
0x14001006c  test    eax, eax
0x14001006e  jz      loc_140010201
0x140010074  call    cs:__imp_GetProcessHeap
0x14001007a  mov     r8, r14; lpMem
0x14001007d  xor     edx, edx; dwFlags
0x14001007f  mov     rcx, rax; hHeap
0x140010082  call    cs:__imp_HeapFree
0x140010088  mov     rcx, [rbp+188h]; this
0x14001008f  mov     r9d, esi; char *
0x140010092  mov     edx, 137h; void *
0x140010097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001009c  test    rdi, rdi
0x14001009f  jz      short loc_1400100B2
0x1400100a1  mov     rcx, rdi; hMutex
0x1400100a4  call    cs:__imp_ReleaseMutex
0x1400100aa  test    eax, eax
0x1400100ac  jz      loc_140010213
0x1400100b2  mov     rcx, rbx; hObject
0x1400100b5  call    cs:__imp_CloseHandle
0x1400100bb  test    eax, eax
0x1400100bd  jz      loc_14001019A
0x1400100c3  jmp     loc_14000FF9C
0x1400100c8  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x1400100cd  lea     rcx, [r14+28h]; void *
0x1400100d1  mov     dword ptr [r14], 1
0x1400100d8  xor     edx, edx; Val
0x1400100da  mov     [r14+8], rbx
0x1400100de  mov     r8d, 108h; Size
0x1400100e4  movdqu  xmmword ptr [r14+10h], xmm0
0x1400100ea  call    memset_0
0x1400100ef  xor     eax, eax
0x1400100f1  lea     rcx, [r14+28h]; this
0x1400100f5  mov     [r14+20h], rax
0x1400100f9  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400100fe  lea     rbx, [r14+0E8h]
0x140010105  xor     r8d, r8d; Flags
0x140010108  mov     rcx, rbx; lpCriticalSection
0x14001010b  xor     edx, edx; dwSpinCount
0x14001010d  call    cs:__imp_InitializeCriticalSectionEx
0x140010113  mov     qword ptr [rbx+28h], 0
0x14001011b  mov     qword ptr [rbx+30h], 0
0x140010123  mov     qword ptr [rbx+38h], 0
0x14001012b  mov     qword ptr [rbx+40h], 0
0x140010133  xor     ebx, ebx
0x140010135  mov     [r15], r14
0x140010138  test    rdi, rdi
0x14001013b  jz      short loc_14001014E
0x14001013d  mov     rcx, rdi; hMutex
0x140010140  call    cs:__imp_ReleaseMutex
0x140010146  test    eax, eax
0x140010148  jz      loc_140010225
0x14001014e  test    rbx, rbx
0x140010151  jz      short loc_140010160
0x140010153  mov     rcx, rbx; hObject
0x140010156  call    cs:__imp_CloseHandle
0x14001015c  test    eax, eax
0x14001015e  jz      short loc_140010188
0x140010160  xor     eax, eax
0x140010162  mov     rcx, [rbp+180h+var_30]
0x140010169  xor     rcx, rsp; StackCookie
0x14001016c  call    __security_check_cookie
0x140010171  mov     rbx, [rsp+280h+arg_10]
0x140010179  add     rsp, 260h
0x140010180  pop     r15
0x140010182  pop     r14
0x140010184  pop     rdi
0x140010185  pop     rsi
0x140010186  pop     rbp
0x140010187  retn
0x140010188  mov     rcx, [rbp+188h]; this
0x14001018f  mov     edx, 0A0Bh; void *
0x140010194  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14001019a  mov     rcx, [rbp+188h]; this
0x1400101a1  mov     edx, 0A0Bh; void *
0x1400101a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400101ac  mov     rcx, [rbp+188h]; this
0x1400101b3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400101ba  mov     edx, 0E01h; void *
0x1400101bf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400101c5  mov     rcx, [rbp+188h]; this
0x1400101cc  mov     edx, 0A15h; void *
0x1400101d1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400101d7  mov     rcx, [rbp+188h]; this
0x1400101de  mov     edx, 0A0Bh; void *
0x1400101e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400101e9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400101ef  mov     rcx, [rbp+188h]; this
0x1400101f6  mov     edx, 0A0Bh; void *
0x1400101fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010201  mov     rcx, [rbp+188h]; this
0x140010208  mov     edx, 0A0Bh; void *
0x14001020d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010213  mov     rcx, [rbp+188h]; this
0x14001021a  mov     edx, 0A15h; void *
0x14001021f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140010225  mov     rcx, [rbp+188h]; this
0x14001022c  mov     edx, 0A15h; void *
0x140010231  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
