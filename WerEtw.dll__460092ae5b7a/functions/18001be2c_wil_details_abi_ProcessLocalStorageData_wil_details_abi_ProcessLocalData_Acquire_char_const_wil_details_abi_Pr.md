# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001be2c`
- end: `0x18001c1e9`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `957`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x18001d210`

## callees

- `0x180001870`
- `0x180002420`
- `0x180015700`
- `0x18001be2c`
- `0x18001c280`
- `0x18001c9e0`
- `0x18001cfa8`
- `0x18001e448`
- `0x18001e744`
- `0x18001f524`
- `0x18001f8ec`
- `0x18001f8fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bea5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001bea5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001becc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001becc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bf53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c09e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c11a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001bf53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c09e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001c11a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001be65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001be65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c137`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001bf6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c034`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c137`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c07b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c07b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c06d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c06d`

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
  void *v12; // rsi
  int ValueInternal; // eax
  unsigned __int64 v14; // r8
  unsigned int v15; // edi
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
  _QWORD *v26; // rdi
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
0x18001be2c  mov     [rsp-8+arg_10], rbx
0x18001be31  push    rbp
0x18001be32  push    rsi
0x18001be33  push    rdi
0x18001be34  push    r14
0x18001be36  push    r15
0x18001be38  lea     rbp, [rsp-180h]
0x18001be40  sub     rsp, 280h
0x18001be47  mov     rax, cs:__security_cookie
0x18001be4e  xor     rax, rsp
0x18001be51  mov     [rbp+1A0h+var_30], rax
0x18001be58  mov     r15, rdx
0x18001be5b  mov     rbx, rcx
0x18001be5e  mov     qword ptr [rdx], 0
0x18001be65  call    cs:__imp_GetCurrentProcessId
0x18001be6b  mov     r9d, eax
0x18001be6e  mov     [rsp+2A0h+var_278], rbx
0x18001be73  mov     r14d, 78h ; 'x'
0x18001be79  mov     [rsp+2A0h+var_280], r14d; int
0x18001be7e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001be85  mov     edx, 104h; unsigned __int64
0x18001be8a  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18001be8f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001be94  nop
0x18001be95  mov     r9d, 1F0001h; dwDesiredAccess
0x18001be9b  xor     r8d, r8d; dwFlags
0x18001be9e  lea     rdx, [rsp+2A0h+Name]; lpName
0x18001bea3  xor     ecx, ecx; lpMutexAttributes
0x18001bea5  call    cs:__imp_CreateMutexExW
0x18001beab  mov     rbx, rax
0x18001beae  mov     [rsp+2A0h+var_258], rax
0x18001beb3  test    rax, rax
0x18001beb6  jnz     short loc_18001BEC3
0x18001beb8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001bebd  nop
0x18001bebe  jmp     loc_18001C143
0x18001bec3  xor     r8d, r8d; bAlertable
0x18001bec6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001bec9  mov     rcx, rbx; hHandle
0x18001becc  call    cs:__imp_WaitForSingleObjectEx
0x18001bed2  cmp     eax, 102h
0x18001bed7  jz      short loc_18001BEE9
0x18001bed9  test    eax, 0FFFFFF7Fh
0x18001bede  jnz     loc_18001C17B
0x18001bee4  mov     rsi, rbx
0x18001bee7  jmp     short loc_18001BEEB
0x18001bee9  xor     esi, esi
0x18001beeb  mov     [rsp+2A0h+var_250], rsi
0x18001bef0  mov     [rsp+2A0h+var_270], 0
0x18001bef9  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x18001befe  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18001bf03  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18001bf08  mov     edi, eax
0x18001bf0a  test    eax, eax
0x18001bf0c  jns     short loc_18001BF80
0x18001bf0e  mov     rcx, [rbp+1A8h]; this
0x18001bf15  mov     r9d, eax; char *
0x18001bf18  mov     edx, 66h ; 'f'; void *
0x18001bf1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bf22  mov     rcx, [rbp+1A8h]; this
0x18001bf29  mov     r9d, edi; char *
0x18001bf2c  mov     edx, 6Fh ; 'o'; void *
0x18001bf31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bf36  mov     rcx, [rbp+1A8h]; this
0x18001bf3d  mov     r9d, edi; char *
0x18001bf40  mov     edx, 12Eh; void *
0x18001bf45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bf4a  nop
0x18001bf4b  test    rsi, rsi
0x18001bf4e  jz      short loc_18001BF68
0x18001bf50  mov     rcx, rsi; hMutex
0x18001bf53  call    cs:__imp_ReleaseMutex
0x18001bf59  mov     rcx, [rbp+1A8h]; this
0x18001bf60  test    eax, eax
0x18001bf62  jz      loc_18001C188
0x18001bf68  mov     rcx, rbx; hObject
0x18001bf6b  call    cs:__imp_CloseHandle
0x18001bf71  test    eax, eax
0x18001bf73  jz      loc_18001C193
0x18001bf79  mov     eax, edi
0x18001bf7b  jmp     loc_18001C143
0x18001bf80  mov     rax, [rsp+2A0h+var_270]
0x18001bf85  lea     rcx, ds:0[rax*4]
0x18001bf8d  test    rcx, rcx
0x18001bf90  jz      short loc_18001BFA0
0x18001bf92  mov     [r15], rcx
0x18001bf95  mov     eax, [rcx]
0x18001bf97  inc     eax
0x18001bf99  mov     [rcx], eax
0x18001bf9b  jmp     loc_18001C112
0x18001bfa0  mov     qword ptr [r15], 0
0x18001bfa7  mov     rdx, r14; dwBytes
0x18001bfaa  mov     ecx, 8; dwFlags
0x18001bfaf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001bfb4  mov     rdi, rax
0x18001bfb7  mov     [rsp+2A0h+var_270], rax
0x18001bfbc  test    rax, rax
0x18001bfbf  jnz     short loc_18001BFE1
0x18001bfc1  mov     rcx, [rbp+1A8h]; this
0x18001bfc8  mov     r14d, 8007000Eh
0x18001bfce  mov     r9d, r14d; char *
0x18001bfd1  mov     edx, 14Bh; void *
0x18001bfd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bfdb  nop
0x18001bfdc  jmp     loc_18001C081
0x18001bfe1  xorps   xmm0, xmm0
0x18001bfe4  movdqu  xmmword ptr [rsp+2A0h+hObject], xmm0
0x18001bfea  test    dil, 3
0x18001bfee  jnz     loc_18001C1A5
0x18001bff4  mov     r9, rdi
0x18001bff7  shr     r9, 2; unsigned __int64
0x18001bffb  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x18001c000  lea     rcx, [rsp+2A0h+hObject]; this
0x18001c005  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18001c00a  mov     r14d, eax
0x18001c00d  test    eax, eax
0x18001c00f  jns     loc_18001C0CE
0x18001c015  mov     rcx, [rbp+1A8h]; this
0x18001c01c  mov     r9d, eax; char *
0x18001c01f  mov     edx, 14Eh; void *
0x18001c024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c029  nop
0x18001c02a  mov     rcx, [rsp+2A0h+hObject+8]; hObject
0x18001c02f  test    rcx, rcx
0x18001c032  jz      short loc_18001C049
0x18001c034  call    cs:__imp_CloseHandle
0x18001c03a  mov     rcx, [rbp+1A8h]; this
0x18001c041  test    eax, eax
0x18001c043  jz      loc_18001C1AB
0x18001c049  mov     rcx, [rsp+2A0h+hObject]; hObject
0x18001c04e  test    rcx, rcx
0x18001c051  jz      short loc_18001C068
0x18001c053  call    cs:__imp_CloseHandle
0x18001c059  mov     rcx, [rbp+1A8h]; this
0x18001c060  test    eax, eax
0x18001c062  jz      loc_18001C1B6
0x18001c068  test    rdi, rdi
0x18001c06b  jz      short loc_18001C081
0x18001c06d  call    cs:__imp_GetProcessHeap
0x18001c073  mov     rcx, rax; hHeap
0x18001c076  mov     r8, rdi; lpMem
0x18001c079  xor     edx, edx; dwFlags
0x18001c07b  call    cs:__imp_HeapFree
0x18001c081  mov     rcx, [rbp+1A8h]; this
0x18001c088  mov     r9d, r14d; char *
0x18001c08b  mov     edx, 137h; void *
0x18001c090  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c095  nop
0x18001c096  test    rsi, rsi
0x18001c099  jz      short loc_18001C0B3
0x18001c09b  mov     rcx, rsi; hMutex
0x18001c09e  call    cs:__imp_ReleaseMutex
0x18001c0a4  mov     rcx, [rbp+1A8h]; this
0x18001c0ab  test    eax, eax
0x18001c0ad  jz      loc_18001C1C1
0x18001c0b3  test    rbx, rbx
0x18001c0b6  jz      short loc_18001C0C9
0x18001c0b8  mov     rcx, rbx; hObject
0x18001c0bb  call    cs:__imp_CloseHandle
0x18001c0c1  test    eax, eax
0x18001c0c3  jz      loc_18001C1CC
0x18001c0c9  mov     eax, r14d
0x18001c0cc  jmp     short loc_18001C143
0x18001c0ce  mov     dword ptr [rdi], 1
0x18001c0d4  mov     [rdi+8], rbx
0x18001c0d8  xor     ebx, ebx
0x18001c0da  movups  xmm0, xmmword ptr [rsp+2A0h+hObject]
0x18001c0df  movdqu  xmmword ptr [rdi+10h], xmm0
0x18001c0e4  lea     rcx, [rdi+22h]; void *
0x18001c0e8  xor     edx, edx; Val
0x18001c0ea  lea     r8d, [rbx+56h]; Size
0x18001c0ee  call    memset_0
0x18001c0f3  mov     word ptr [rdi+20h], 58h ; 'X'
0x18001c0f9  mov     dword ptr [rdi+24h], 1
0x18001c100  lea     rcx, [rdi+28h]; void *
0x18001c104  xor     edx, edx; Val
0x18001c106  lea     r8d, [rbx+50h]; Size
0x18001c10a  call    memset_0
0x18001c10f  mov     [r15], rdi
0x18001c112  test    rsi, rsi
0x18001c115  jz      short loc_18001C12F
0x18001c117  mov     rcx, rsi; hMutex
0x18001c11a  call    cs:__imp_ReleaseMutex
0x18001c120  mov     rcx, [rbp+1A8h]; this
0x18001c127  test    eax, eax
0x18001c129  jz      loc_18001C1DE
0x18001c12f  test    rbx, rbx
0x18001c132  jz      short loc_18001C141
0x18001c134  mov     rcx, rbx; hObject
0x18001c137  call    cs:__imp_CloseHandle
0x18001c13d  test    eax, eax
0x18001c13f  jz      short loc_18001C169
0x18001c141  xor     eax, eax
0x18001c143  mov     rcx, [rbp+1A0h+var_30]
0x18001c14a  xor     rcx, rsp; StackCookie
0x18001c14d  call    __security_check_cookie
0x18001c152  mov     rbx, [rsp+2A0h+arg_10]
0x18001c15a  add     rsp, 280h
0x18001c161  pop     r15
0x18001c163  pop     r14
0x18001c165  pop     rdi
0x18001c166  pop     rsi
0x18001c167  pop     rbp
0x18001c168  retn
0x18001c169  mov     rcx, [rbp+1A8h]; this
0x18001c170  mov     edx, 0A0Bh; void *
0x18001c175  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c17b  mov     rcx, [rbp+1A8h]; this
0x18001c182  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001c188  mov     edx, 0A15h; void *
0x18001c18d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c193  mov     rcx, [rbp+1A8h]; this
0x18001c19a  mov     edx, 0A0Bh; void *
0x18001c19f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c1a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001c1ab  mov     edx, 0A0Bh; void *
0x18001c1b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c1b6  mov     edx, 0A0Bh; void *
0x18001c1bb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c1c1  mov     edx, 0A15h; void *
0x18001c1c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c1cc  mov     rcx, [rbp+1A8h]; this
0x18001c1d3  mov     edx, 0A0Bh; void *
0x18001c1d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001c1de  mov     edx, 0A15h; void *
0x18001c1e3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
