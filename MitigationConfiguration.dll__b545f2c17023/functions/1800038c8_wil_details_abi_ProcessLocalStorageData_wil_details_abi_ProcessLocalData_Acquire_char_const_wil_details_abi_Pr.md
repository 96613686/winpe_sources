# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800038c8`
- end: `0x180003c90`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x1800050e0`

## callees

- `0x180001c00`
- `0x180002648`
- `0x1800038c8`
- `0x180003cd4`
- `0x180004828`
- `0x180004e78`
- `0x18000598c`
- `0x180005db4`
- `0x180006850`
- `0x18000698c`
- `0x180006e34`
- `0x180006e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800039f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003b35`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180003ba5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003940`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180003940`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003961`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180003961`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003afe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003afe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003901`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003901`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003ad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003bbb`

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
  __int64 v16; // r8
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  bool v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  __int64 v32; // r8
  const char *v33; // r9
  __int64 v34; // r8
  const char *v35; // r9
  __int128 v36; // xmm0
  __int64 v37; // r8
  const char *v38; // r9
  __int64 v39; // r8
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
0x1800038c8  mov     [rsp-8+arg_10], rbx
0x1800038cd  push    rbp
0x1800038ce  push    rsi
0x1800038cf  push    rdi
0x1800038d0  push    r14
0x1800038d2  push    r15
0x1800038d4  lea     rbp, [rsp-160h]
0x1800038dc  sub     rsp, 260h
0x1800038e3  mov     rax, cs:__security_cookie
0x1800038ea  xor     rax, rsp
0x1800038ed  mov     [rbp+180h+var_30], rax
0x1800038f4  mov     r15, rdx
0x1800038f7  mov     qword ptr [rdx], 0
0x1800038fe  mov     rbx, rcx
0x180003901  call    cs:__imp_GetCurrentProcessId
0x180003907  mov     r14d, 78h ; 'x'
0x18000390d  mov     [rsp+280h+var_258], rbx
0x180003912  mov     r9d, eax
0x180003915  mov     [rsp+280h+var_260], r14d; int
0x18000391a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003921  mov     edx, 104h; unsigned __int64
0x180003926  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000392b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003930  mov     r9d, 1F0001h; dwDesiredAccess
0x180003936  lea     rdx, [rsp+280h+Name]; lpName
0x18000393b  xor     r8d, r8d; dwFlags
0x18000393e  xor     ecx, ecx; lpMutexAttributes
0x180003940  call    cs:__imp_CreateMutexExW
0x180003946  mov     rbx, rax
0x180003949  test    rax, rax
0x18000394c  jnz     short loc_180003958
0x18000394e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180003953  jmp     loc_180003BC7
0x180003958  xor     r8d, r8d; bAlertable
0x18000395b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000395e  mov     rcx, rbx; hHandle
0x180003961  call    cs:__imp_WaitForSingleObjectEx
0x180003967  cmp     eax, 102h
0x18000396c  jz      short loc_18000397E
0x18000396e  test    eax, 0FFFFFF7Fh
0x180003973  jnz     loc_180003BFF
0x180003979  mov     rdi, rbx
0x18000397c  jmp     short loc_180003980
0x18000397e  xor     edi, edi
0x180003980  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x180003985  mov     [rsp+280h+hObject], 0
0x18000398e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180003993  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180003998  mov     esi, eax
0x18000399a  test    eax, eax
0x18000399c  jns     short loc_180003A1D
0x18000399e  mov     rcx, [rbp+188h]; this
0x1800039a5  lea     r8, aWil; "wil"
0x1800039ac  mov     r9d, eax; char *
0x1800039af  mov     edx, 66h ; 'f'; void *
0x1800039b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039b9  mov     rcx, [rbp+188h]; this
0x1800039c0  lea     r8, aWil; "wil"
0x1800039c7  mov     r9d, esi; char *
0x1800039ca  mov     edx, 6Fh ; 'o'; void *
0x1800039cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039d4  mov     rcx, [rbp+188h]; this
0x1800039db  lea     r8, aWil; "wil"
0x1800039e2  mov     r9d, esi; char *
0x1800039e5  mov     edx, 12Eh; void *
0x1800039ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039ef  test    rdi, rdi
0x1800039f2  jz      short loc_180003A05
0x1800039f4  mov     rcx, rdi; hMutex
0x1800039f7  call    cs:__imp_ReleaseMutex
0x1800039fd  test    eax, eax
0x1800039ff  jz      loc_180003C0C
0x180003a05  mov     rcx, rbx; hObject
0x180003a08  call    cs:__imp_CloseHandle
0x180003a0e  test    eax, eax
0x180003a10  jz      loc_180003C1E
0x180003a16  mov     eax, esi
0x180003a18  jmp     loc_180003BC7
0x180003a1d  mov     rax, [rsp+280h+hObject]
0x180003a22  lea     rcx, ds:0[rax*4]
0x180003a2a  test    rcx, rcx
0x180003a2d  jz      short loc_180003A3D
0x180003a2f  mov     [r15], rcx
0x180003a32  mov     eax, [rcx]
0x180003a34  inc     eax
0x180003a36  mov     [rcx], eax
0x180003a38  jmp     loc_180003B9D
0x180003a3d  mov     rdx, r14; dwBytes
0x180003a40  mov     qword ptr [r15], 0
0x180003a47  mov     ecx, 8; dwFlags
0x180003a4c  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003a51  mov     rsi, rax
0x180003a54  test    rax, rax
0x180003a57  jnz     short loc_180003A7F
0x180003a59  mov     rcx, [rbp+188h]; this
0x180003a60  lea     r8, aWil; "wil"
0x180003a67  mov     r14d, 8007000Eh
0x180003a6d  mov     edx, 14Bh; void *
0x180003a72  mov     r9d, r14d; char *
0x180003a75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003a7a  jmp     loc_180003B12
0x180003a7f  xorps   xmm0, xmm0
0x180003a82  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x180003a88  test    sil, 3
0x180003a8c  jnz     loc_180003C30
0x180003a92  mov     r9, rsi
0x180003a95  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x180003a9a  shr     r9, 2; unsigned __int64
0x180003a9e  lea     rcx, [rsp+280h+hObject]; this
0x180003aa3  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x180003aa8  mov     r14d, eax
0x180003aab  test    eax, eax
0x180003aad  jns     loc_180003B59
0x180003ab3  mov     rcx, [rbp+188h]; this
0x180003aba  lea     r8, aWil; "wil"
0x180003ac1  mov     r9d, eax; char *
0x180003ac4  mov     edx, 14Eh; void *
0x180003ac9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ace  mov     rcx, [rsp+280h+hObject+8]; hObject
0x180003ad3  test    rcx, rcx
0x180003ad6  jz      short loc_180003AE6
0x180003ad8  call    cs:__imp_CloseHandle
0x180003ade  test    eax, eax
0x180003ae0  jz      loc_180003C36
0x180003ae6  mov     rcx, [rsp+280h+hObject]; hObject
0x180003aeb  test    rcx, rcx
0x180003aee  jz      short loc_180003AFE
0x180003af0  call    cs:__imp_CloseHandle
0x180003af6  test    eax, eax
0x180003af8  jz      loc_180003C48
0x180003afe  call    cs:__imp_GetProcessHeap
0x180003b04  mov     r8, rsi; lpMem
0x180003b07  xor     edx, edx; dwFlags
0x180003b09  mov     rcx, rax; hHeap
0x180003b0c  call    cs:__imp_HeapFree
0x180003b12  mov     rcx, [rbp+188h]; this
0x180003b19  lea     r8, aWil; "wil"
0x180003b20  mov     r9d, r14d; char *
0x180003b23  mov     edx, 137h; void *
0x180003b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b2d  test    rdi, rdi
0x180003b30  jz      short loc_180003B43
0x180003b32  mov     rcx, rdi; hMutex
0x180003b35  call    cs:__imp_ReleaseMutex
0x180003b3b  test    eax, eax
0x180003b3d  jz      loc_180003C5A
0x180003b43  mov     rcx, rbx; hObject
0x180003b46  call    cs:__imp_CloseHandle
0x180003b4c  test    eax, eax
0x180003b4e  jz      loc_180003C6C
0x180003b54  mov     eax, r14d
0x180003b57  jmp     short loc_180003BC7
0x180003b59  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x180003b5e  xor     edx, edx; Val
0x180003b60  mov     dword ptr [rsi], 1
0x180003b66  lea     rcx, [rsi+22h]; void *
0x180003b6a  mov     [rsi+8], rbx
0x180003b6e  movdqu  xmmword ptr [rsi+10h], xmm0
0x180003b73  lea     r8d, [rdx+56h]; Size
0x180003b77  call    memset_0
0x180003b7c  xor     edx, edx; Val
0x180003b7e  mov     word ptr [rsi+20h], 58h ; 'X'
0x180003b84  lea     rcx, [rsi+28h]; void *
0x180003b88  mov     dword ptr [rsi+24h], 1
0x180003b8f  lea     r8d, [rdx+50h]; Size
0x180003b93  call    memset_0
0x180003b98  xor     ebx, ebx
0x180003b9a  mov     [r15], rsi
0x180003b9d  test    rdi, rdi
0x180003ba0  jz      short loc_180003BB3
0x180003ba2  mov     rcx, rdi; hMutex
0x180003ba5  call    cs:__imp_ReleaseMutex
0x180003bab  test    eax, eax
0x180003bad  jz      loc_180003C7E
0x180003bb3  test    rbx, rbx
0x180003bb6  jz      short loc_180003BC5
0x180003bb8  mov     rcx, rbx; hObject
0x180003bbb  call    cs:__imp_CloseHandle
0x180003bc1  test    eax, eax
0x180003bc3  jz      short loc_180003BED
0x180003bc5  xor     eax, eax
0x180003bc7  mov     rcx, [rbp+180h+var_30]
0x180003bce  xor     rcx, rsp; StackCookie
0x180003bd1  call    __security_check_cookie
0x180003bd6  mov     rbx, [rsp+280h+arg_10]
0x180003bde  add     rsp, 260h
0x180003be5  pop     r15
0x180003be7  pop     r14
0x180003be9  pop     rdi
0x180003bea  pop     rsi
0x180003beb  pop     rbp
0x180003bec  retn
0x180003bed  mov     rcx, [rbp+188h]; this
0x180003bf4  mov     edx, 0A0Bh; void *
0x180003bf9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003bff  mov     rcx, [rbp+188h]; this
0x180003c06  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180003c0c  mov     rcx, [rbp+188h]; this
0x180003c13  mov     edx, 0A15h; void *
0x180003c18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c1e  mov     rcx, [rbp+188h]; this
0x180003c25  mov     edx, 0A0Bh; void *
0x180003c2a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c30  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003c36  mov     rcx, [rbp+188h]; this
0x180003c3d  mov     edx, 0A0Bh; void *
0x180003c42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c48  mov     rcx, [rbp+188h]; this
0x180003c4f  mov     edx, 0A0Bh; void *
0x180003c54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c5a  mov     rcx, [rbp+188h]; this
0x180003c61  mov     edx, 0A15h; void *
0x180003c66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c6c  mov     rcx, [rbp+188h]; this
0x180003c73  mov     edx, 0A0Bh; void *
0x180003c78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003c7e  mov     rcx, [rbp+188h]; this
0x180003c85  mov     edx, 0A15h; void *
0x180003c8a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
