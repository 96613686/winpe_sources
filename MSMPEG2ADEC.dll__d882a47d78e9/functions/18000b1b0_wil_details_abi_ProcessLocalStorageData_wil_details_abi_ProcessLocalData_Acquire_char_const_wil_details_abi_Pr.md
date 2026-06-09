# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000b1b0`
- end: `0x18000b5d5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `1061`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x18000ff70`

## callees

- `0x1800017b0`
- `0x18000b1b0`
- `0x18000cf80`
- `0x18000de20`
- `0x18000eee0`
- `0x180012bf0`
- `0x180013af0`
- `0x180017ba0`
- `0x180017c70`
- `0x1800187e0`
- `0x1800187f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b2df`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b437`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b4c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b2df`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b437`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000b4c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b24d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000b24d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b21c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000b21c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b40e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b40e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b3fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b3fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b1da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b1da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b44e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b3e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b44e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4e3`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  char *v26; // rdi
  unsigned int v27; // ebp
  unsigned int v28; // r8d
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int v38; // r8d
  const char *v39; // r9
  __int128 v40; // xmm0
  unsigned int v41; // r8d
  const char *v42; // r9
  unsigned int v43; // r8d
  const char *v44; // r9
  int v45; // [rsp+20h] [rbp-258h]
  int v46; // [rsp+20h] [rbp-258h]
  int v47; // [rsp+20h] [rbp-258h]
  HANDLE hObject[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v14, (const char *)(unsigned int)ValueInternal, 120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v16, (const char *)v15, v45);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v17, (const char *)v15, v46);
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
  v23 = (unsigned __int64)wil::details::ProcessHeapAlloc(8u, 0x78u, v14);
  v26 = (char *)v23;
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
      v40 = *(_OWORD *)hObject;
      *((_QWORD *)v26 + 1) = v6;
      *(_DWORD *)v26 = 1;
      v6 = 0;
      *((_OWORD *)v26 + 1) = v40;
      *(_OWORD *)(v26 + 34) = 0;
      *(_OWORD *)(v26 + 50) = 0;
      *(_OWORD *)(v26 + 66) = 0;
      *(_OWORD *)(v26 + 82) = 0;
      *(_OWORD *)(v26 + 98) = 0;
      *((_QWORD *)v26 + 14) = 0;
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      *(_OWORD *)(v26 + 40) = 0;
      *(_OWORD *)(v26 + 56) = 0;
      *(_OWORD *)(v26 + 72) = 0;
      *(_OWORD *)(v26 + 88) = 0;
      *(_OWORD *)(v26 + 104) = 0;
      *a2 = v26;
LABEL_28:
      if ( v12 && !ReleaseMutex(v12) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v41, v42);
      if ( v6 && !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v43, v44);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14E, v30, (const char *)(unsigned int)v29, 120);
    if ( hObject[1] && !CloseHandle(hObject[1]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    if ( hObject[0] && !CloseHandle(hObject[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v26);
  }
  else
  {
    v27 = -2147024882;
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x14B, v25, (const char *)0x8007000ELL, 120);
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v28, (const char *)v27, v47);
  if ( v12 && !ReleaseMutex(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v36, v37);
  if ( !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v38, v39);
  return v27;
}

```

## disassembly

```asm
0x18000b1b0  push    rbx
0x18000b1b2  push    r14
0x18000b1b4  sub     rsp, 268h
0x18000b1bb  mov     rax, cs:__security_cookie
0x18000b1c2  xor     rax, rsp
0x18000b1c5  mov     [rsp+278h+var_28], rax
0x18000b1cd  mov     r14, rdx
0x18000b1d0  mov     qword ptr [rdx], 0
0x18000b1d7  mov     rbx, rcx
0x18000b1da  call    cs:__imp_GetCurrentProcessId
0x18000b1e1  nop     dword ptr [rax+rax+00h]
0x18000b1e6  mov     [rsp+278h+var_250], rbx
0x18000b1eb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000b1f2  mov     r9d, eax
0x18000b1f5  mov     [rsp+278h+var_258], 78h ; 'x'; int
0x18000b1fd  mov     edx, 104h; unsigned __int64
0x18000b202  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000b207  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b20c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000b212  lea     rdx, [rsp+278h+Name]; lpName
0x18000b217  xor     r8d, r8d; dwFlags
0x18000b21a  xor     ecx, ecx; lpMutexAttributes
0x18000b21c  call    cs:__imp_CreateMutexExW
0x18000b223  nop     dword ptr [rax+rax+00h]
0x18000b228  mov     rbx, rax
0x18000b22b  test    rax, rax
0x18000b22e  jnz     short loc_18000B23A
0x18000b230  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000b235  jmp     loc_18000B50D
0x18000b23a  xor     r8d, r8d; bAlertable
0x18000b23d  mov     [rsp+278h+arg_18], rsi
0x18000b245  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000b24a  mov     rcx, rbx; hHandle
0x18000b24d  call    cs:__imp_WaitForSingleObjectEx
0x18000b254  nop     dword ptr [rax+rax+00h]
0x18000b259  cmp     eax, 102h
0x18000b25e  jz      short loc_18000B270
0x18000b260  test    eax, 0FFFFFF7Fh
0x18000b265  jnz     loc_18000B53C
0x18000b26b  mov     rsi, rbx
0x18000b26e  jmp     short loc_18000B272
0x18000b270  xor     esi, esi
0x18000b272  lea     r8, [rsp+278h+hObject]; unsigned __int64 *
0x18000b277  mov     [rsp+278h+var_18], rdi
0x18000b27f  lea     rcx, [rsp+278h+Name]; unsigned __int16 *
0x18000b284  mov     [rsp+278h+hObject], 0
0x18000b28d  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000b292  mov     edi, eax
0x18000b294  test    eax, eax
0x18000b296  jns     short loc_18000B311
0x18000b298  mov     rcx, [rsp+278h]; this
0x18000b2a0  mov     r9d, eax; char *
0x18000b2a3  mov     edx, 66h ; 'f'; void *
0x18000b2a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2ad  mov     rcx, [rsp+278h]; this
0x18000b2b5  mov     r9d, edi; char *
0x18000b2b8  mov     edx, 6Fh ; 'o'; void *
0x18000b2bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2c2  mov     rcx, [rsp+278h]; this
0x18000b2ca  mov     r9d, edi; char *
0x18000b2cd  mov     edx, 12Eh; void *
0x18000b2d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2d7  test    rsi, rsi
0x18000b2da  jz      short loc_18000B2F3
0x18000b2dc  mov     rcx, rsi; hMutex
0x18000b2df  call    cs:__imp_ReleaseMutex
0x18000b2e6  nop     dword ptr [rax+rax+00h]
0x18000b2eb  test    eax, eax
0x18000b2ed  jz      loc_18000B54A
0x18000b2f3  mov     rcx, rbx; hObject
0x18000b2f6  call    cs:__imp_CloseHandle
0x18000b2fd  nop     dword ptr [rax+rax+00h]
0x18000b302  test    eax, eax
0x18000b304  jz      loc_18000B55D
0x18000b30a  mov     eax, edi
0x18000b30c  jmp     loc_18000B4FD
0x18000b311  mov     rax, [rsp+278h+hObject]
0x18000b316  mov     [rsp+278h+arg_10], rbp
0x18000b31e  lea     rcx, ds:0[rax*4]
0x18000b326  test    rcx, rcx
0x18000b329  jz      short loc_18000B339
0x18000b32b  mov     [r14], rcx
0x18000b32e  mov     eax, [rcx]
0x18000b330  inc     eax
0x18000b332  mov     [rcx], eax
0x18000b334  jmp     loc_18000B4BF
0x18000b339  mov     edx, 78h ; 'x'; dwBytes
0x18000b33e  mov     qword ptr [r14], 0
0x18000b345  mov     ecx, 8; dwFlags
0x18000b34a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b34f  mov     rdi, rax
0x18000b352  test    rax, rax
0x18000b355  jnz     short loc_18000B376
0x18000b357  mov     rcx, [rsp+278h]; this
0x18000b35f  mov     ebp, 8007000Eh
0x18000b364  mov     r9d, ebp; char *
0x18000b367  mov     edx, 14Bh; void *
0x18000b36c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b371  jmp     loc_18000B41A
0x18000b376  xorps   xmm0, xmm0
0x18000b379  movdqu  xmmword ptr [rsp+278h+hObject], xmm0
0x18000b37f  test    dil, 3
0x18000b383  jnz     loc_18000B570
0x18000b389  mov     r9, rdi
0x18000b38c  lea     rdx, [rsp+278h+Name]; unsigned __int16 *
0x18000b391  shr     r9, 2; unsigned __int64
0x18000b395  lea     rcx, [rsp+278h+hObject]; this
0x18000b39a  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x18000b39f  mov     ebp, eax
0x18000b3a1  test    eax, eax
0x18000b3a3  jns     loc_18000B469
0x18000b3a9  mov     rcx, [rsp+278h]; this
0x18000b3b1  mov     r9d, eax; char *
0x18000b3b4  mov     edx, 14Eh; void *
0x18000b3b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3be  mov     rcx, [rsp+278h+hObject+8]; hObject
0x18000b3c3  test    rcx, rcx
0x18000b3c6  jz      short loc_18000B3DC
0x18000b3c8  call    cs:__imp_CloseHandle
0x18000b3cf  nop     dword ptr [rax+rax+00h]
0x18000b3d4  test    eax, eax
0x18000b3d6  jz      loc_18000B576
0x18000b3dc  mov     rcx, [rsp+278h+hObject]; hObject
0x18000b3e1  test    rcx, rcx
0x18000b3e4  jz      short loc_18000B3FA
0x18000b3e6  call    cs:__imp_CloseHandle
0x18000b3ed  nop     dword ptr [rax+rax+00h]
0x18000b3f2  test    eax, eax
0x18000b3f4  jz      loc_18000B589
0x18000b3fa  call    cs:__imp_GetProcessHeap
0x18000b401  nop     dword ptr [rax+rax+00h]
0x18000b406  mov     r8, rdi; lpMem
0x18000b409  xor     edx, edx; dwFlags
0x18000b40b  mov     rcx, rax; hHeap
0x18000b40e  call    cs:__imp_HeapFree
0x18000b415  nop     dword ptr [rax+rax+00h]
0x18000b41a  mov     rcx, [rsp+278h]; this
0x18000b422  mov     r9d, ebp; char *
0x18000b425  mov     edx, 137h; void *
0x18000b42a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b42f  test    rsi, rsi
0x18000b432  jz      short loc_18000B44B
0x18000b434  mov     rcx, rsi; hMutex
0x18000b437  call    cs:__imp_ReleaseMutex
0x18000b43e  nop     dword ptr [rax+rax+00h]
0x18000b443  test    eax, eax
0x18000b445  jz      loc_18000B59C
0x18000b44b  mov     rcx, rbx; hObject
0x18000b44e  call    cs:__imp_CloseHandle
0x18000b455  nop     dword ptr [rax+rax+00h]
0x18000b45a  test    eax, eax
0x18000b45c  jz      loc_18000B5AF
0x18000b462  mov     eax, ebp
0x18000b464  jmp     loc_18000B4F5
0x18000b469  movups  xmm0, xmmword ptr [rsp+278h+hObject]
0x18000b46e  mov     [rdi+8], rbx
0x18000b472  xor     eax, eax
0x18000b474  mov     dword ptr [rdi], 1
0x18000b47a  xor     ebx, ebx
0x18000b47c  movups  xmmword ptr [rdi+10h], xmm0
0x18000b480  xorps   xmm0, xmm0
0x18000b483  movups  xmmword ptr [rdi+22h], xmm0
0x18000b487  movups  xmmword ptr [rdi+32h], xmm0
0x18000b48b  movups  xmmword ptr [rdi+42h], xmm0
0x18000b48f  movups  xmmword ptr [rdi+52h], xmm0
0x18000b493  movups  xmmword ptr [rdi+62h], xmm0
0x18000b497  mov     [rdi+70h], rax
0x18000b49b  mov     word ptr [rdi+20h], 58h ; 'X'
0x18000b4a1  mov     dword ptr [rdi+24h], 1
0x18000b4a8  movups  xmmword ptr [rdi+28h], xmm0
0x18000b4ac  movups  xmmword ptr [rdi+38h], xmm0
0x18000b4b0  movups  xmmword ptr [rdi+48h], xmm0
0x18000b4b4  movups  xmmword ptr [rdi+58h], xmm0
0x18000b4b8  movups  xmmword ptr [rdi+68h], xmm0
0x18000b4bc  mov     [r14], rdi
0x18000b4bf  test    rsi, rsi
0x18000b4c2  jz      short loc_18000B4DB
0x18000b4c4  mov     rcx, rsi; hMutex
0x18000b4c7  call    cs:__imp_ReleaseMutex
0x18000b4ce  nop     dword ptr [rax+rax+00h]
0x18000b4d3  test    eax, eax
0x18000b4d5  jz      loc_18000B5C2
0x18000b4db  test    rbx, rbx
0x18000b4de  jz      short loc_18000B4F3
0x18000b4e0  mov     rcx, rbx; hObject
0x18000b4e3  call    cs:__imp_CloseHandle
0x18000b4ea  nop     dword ptr [rax+rax+00h]
0x18000b4ef  test    eax, eax
0x18000b4f1  jz      short loc_18000B529
0x18000b4f3  xor     eax, eax
0x18000b4f5  mov     rbp, [rsp+278h+arg_10]
0x18000b4fd  mov     rdi, [rsp+278h+var_18]
0x18000b505  mov     rsi, [rsp+278h+arg_18]
0x18000b50d  mov     rcx, [rsp+278h+var_28]
0x18000b515  xor     rcx, rsp; StackCookie
0x18000b518  call    __security_check_cookie
0x18000b51d  add     rsp, 268h
0x18000b524  pop     r14
0x18000b526  pop     rbx
0x18000b527  retn
0x18000b529  mov     rcx, [rsp+278h]; this
0x18000b531  mov     edx, 0A0Bh; void *
0x18000b536  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b53c  mov     rcx, [rsp+278h]; this
0x18000b544  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000b54a  mov     rcx, [rsp+278h]; this
0x18000b552  mov     edx, 0A15h; void *
0x18000b557  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b55d  mov     rcx, [rsp+278h]; this
0x18000b565  mov     edx, 0A0Bh; void *
0x18000b56a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b570  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b576  mov     rcx, [rsp+278h]; this
0x18000b57e  mov     edx, 0A0Bh; void *
0x18000b583  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b589  mov     rcx, [rsp+278h]; this
0x18000b591  mov     edx, 0A0Bh; void *
0x18000b596  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b59c  mov     rcx, [rsp+278h]; this
0x18000b5a4  mov     edx, 0A15h; void *
0x18000b5a9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b5af  mov     rcx, [rsp+278h]; this
0x18000b5b7  mov     edx, 0A0Bh; void *
0x18000b5bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b5c2  mov     rcx, [rsp+278h]; this
0x18000b5ca  mov     edx, 0A15h; void *
0x18000b5cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
