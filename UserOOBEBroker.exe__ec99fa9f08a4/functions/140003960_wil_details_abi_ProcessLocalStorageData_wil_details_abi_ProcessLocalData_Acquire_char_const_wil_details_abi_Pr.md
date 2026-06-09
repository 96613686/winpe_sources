# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140003960`
- end: `0x140003d28`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140004810`

## callees

- `0x14000295f`
- `0x140003960`
- `0x140003d30`
- `0x140004014`
- `0x1400045a8`
- `0x140005088`
- `0x140005474`
- `0x140005ca4`
- `0x140005d7c`
- `0x140006234`
- `0x140006244`
- `0x14000e1c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003ba4`
- `KERNEL32!HeapFree` at `0x140003ba4`
- `KERNEL32!ReleaseMutex` at `0x140003a8f`
- `KERNEL32!ReleaseMutex` at `0x140003bcd`
- `KERNEL32!ReleaseMutex` at `0x140003c3d`
- `KERNEL32!ReleaseMutex` at `0x140003a8f`
- `KERNEL32!ReleaseMutex` at `0x140003bcd`
- `KERNEL32!ReleaseMutex` at `0x140003c3d`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400039f9`
- `KERNEL32!WaitForSingleObjectEx` at `0x1400039f9`
- `KERNEL32!CloseHandle` at `0x140003aa0`
- `KERNEL32!CloseHandle` at `0x140003b70`
- `KERNEL32!CloseHandle` at `0x140003b88`
- `KERNEL32!CloseHandle` at `0x140003bde`
- `KERNEL32!CloseHandle` at `0x140003c53`
- `KERNEL32!CloseHandle` at `0x140003aa0`
- `KERNEL32!CloseHandle` at `0x140003b70`
- `KERNEL32!CloseHandle` at `0x140003b88`
- `KERNEL32!CloseHandle` at `0x140003bde`
- `KERNEL32!CloseHandle` at `0x140003c53`
- `KERNEL32!CreateMutexExW` at `0x1400039d8`
- `KERNEL32!CreateMutexExW` at `0x1400039d8`
- `KERNEL32!GetCurrentProcessId` at `0x140003999`
- `KERNEL32!GetCurrentProcessId` at `0x140003999`
- `KERNEL32!GetProcessHeap` at `0x140003b96`
- `KERNEL32!GetProcessHeap` at `0x140003b96`

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
  unsigned int v16; // r8d
  const char *v17; // r9
  unsigned int v18; // r8d
  const char *v19; // r9
  _DWORD *v20; // rcx
  unsigned __int64 v21; // rax
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // r8
  _QWORD *v24; // rsi
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  __int128 v36; // xmm0
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
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
0x140003960  mov     [rsp-8+arg_10], rbx
0x140003965  push    rbp
0x140003966  push    rsi
0x140003967  push    rdi
0x140003968  push    r14
0x14000396a  push    r15
0x14000396c  lea     rbp, [rsp-160h]
0x140003974  sub     rsp, 260h
0x14000397b  mov     rax, cs:__security_cookie
0x140003982  xor     rax, rsp
0x140003985  mov     [rbp+180h+var_30], rax
0x14000398c  mov     r15, rdx
0x14000398f  mov     qword ptr [rdx], 0
0x140003996  mov     rbx, rcx
0x140003999  call    cs:__imp_GetCurrentProcessId
0x14000399f  mov     r14d, 78h ; 'x'
0x1400039a5  mov     [rsp+280h+var_258], rbx
0x1400039aa  mov     r9d, eax
0x1400039ad  mov     [rsp+280h+var_260], r14d; int
0x1400039b2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400039b9  mov     edx, 104h; unsigned __int64
0x1400039be  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400039c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400039c8  mov     r9d, 1F0001h; dwDesiredAccess
0x1400039ce  lea     rdx, [rsp+280h+Name]; lpName
0x1400039d3  xor     r8d, r8d; dwFlags
0x1400039d6  xor     ecx, ecx; lpMutexAttributes
0x1400039d8  call    cs:__imp_CreateMutexExW
0x1400039de  mov     rbx, rax
0x1400039e1  test    rax, rax
0x1400039e4  jnz     short loc_1400039F0
0x1400039e6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400039eb  jmp     loc_140003C5F
0x1400039f0  xor     r8d, r8d; bAlertable
0x1400039f3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400039f6  mov     rcx, rbx; hHandle
0x1400039f9  call    cs:__imp_WaitForSingleObjectEx
0x1400039ff  cmp     eax, 102h
0x140003a04  jz      short loc_140003A16
0x140003a06  test    eax, 0FFFFFF7Fh
0x140003a0b  jnz     loc_140003C97
0x140003a11  mov     rdi, rbx
0x140003a14  jmp     short loc_140003A18
0x140003a16  xor     edi, edi
0x140003a18  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140003a1d  mov     [rsp+280h+hObject], 0
0x140003a26  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140003a2b  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x140003a30  mov     esi, eax
0x140003a32  test    eax, eax
0x140003a34  jns     short loc_140003AB5
0x140003a36  mov     rcx, [rbp+188h]; this
0x140003a3d  lea     r8, aWil; "wil"
0x140003a44  mov     r9d, eax; char *
0x140003a47  mov     edx, 66h ; 'f'; void *
0x140003a4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a51  mov     rcx, [rbp+188h]; this
0x140003a58  lea     r8, aWil; "wil"
0x140003a5f  mov     r9d, esi; char *
0x140003a62  mov     edx, 6Fh ; 'o'; void *
0x140003a67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a6c  mov     rcx, [rbp+188h]; this
0x140003a73  lea     r8, aWil; "wil"
0x140003a7a  mov     r9d, esi; char *
0x140003a7d  mov     edx, 12Eh; void *
0x140003a82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003a87  test    rdi, rdi
0x140003a8a  jz      short loc_140003A9D
0x140003a8c  mov     rcx, rdi; hMutex
0x140003a8f  call    cs:__imp_ReleaseMutex
0x140003a95  test    eax, eax
0x140003a97  jz      loc_140003CA4
0x140003a9d  mov     rcx, rbx; hObject
0x140003aa0  call    cs:__imp_CloseHandle
0x140003aa6  test    eax, eax
0x140003aa8  jz      loc_140003CB6
0x140003aae  mov     eax, esi
0x140003ab0  jmp     loc_140003C5F
0x140003ab5  mov     rax, [rsp+280h+hObject]
0x140003aba  lea     rcx, ds:0[rax*4]
0x140003ac2  test    rcx, rcx
0x140003ac5  jz      short loc_140003AD5
0x140003ac7  mov     [r15], rcx
0x140003aca  mov     eax, [rcx]
0x140003acc  inc     eax
0x140003ace  mov     [rcx], eax
0x140003ad0  jmp     loc_140003C35
0x140003ad5  mov     rdx, r14; dwBytes
0x140003ad8  mov     qword ptr [r15], 0
0x140003adf  mov     ecx, 8; dwFlags
0x140003ae4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003ae9  mov     rsi, rax
0x140003aec  test    rax, rax
0x140003aef  jnz     short loc_140003B17
0x140003af1  mov     rcx, [rbp+188h]; this
0x140003af8  lea     r8, aWil; "wil"
0x140003aff  mov     r14d, 8007000Eh
0x140003b05  mov     edx, 14Bh; void *
0x140003b0a  mov     r9d, r14d; char *
0x140003b0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b12  jmp     loc_140003BAA
0x140003b17  xorps   xmm0, xmm0
0x140003b1a  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140003b20  test    sil, 3
0x140003b24  jnz     loc_140003CC8
0x140003b2a  mov     r9, rsi
0x140003b2d  lea     rdx, [rsp+280h+Name]; unsigned __int16 *
0x140003b32  shr     r9, 2; unsigned __int64
0x140003b36  lea     rcx, [rsp+280h+hObject]; this
0x140003b3b  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEBG_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(ushort const *,bool,unsigned __int64)
0x140003b40  mov     r14d, eax
0x140003b43  test    eax, eax
0x140003b45  jns     loc_140003BF1
0x140003b4b  mov     rcx, [rbp+188h]; this
0x140003b52  lea     r8, aWil; "wil"
0x140003b59  mov     r9d, eax; char *
0x140003b5c  mov     edx, 14Eh; void *
0x140003b61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003b66  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140003b6b  test    rcx, rcx
0x140003b6e  jz      short loc_140003B7E
0x140003b70  call    cs:__imp_CloseHandle
0x140003b76  test    eax, eax
0x140003b78  jz      loc_140003CCE
0x140003b7e  mov     rcx, [rsp+280h+hObject]; hObject
0x140003b83  test    rcx, rcx
0x140003b86  jz      short loc_140003B96
0x140003b88  call    cs:__imp_CloseHandle
0x140003b8e  test    eax, eax
0x140003b90  jz      loc_140003CE0
0x140003b96  call    cs:__imp_GetProcessHeap
0x140003b9c  mov     r8, rsi; lpMem
0x140003b9f  xor     edx, edx; dwFlags
0x140003ba1  mov     rcx, rax; hHeap
0x140003ba4  call    cs:__imp_HeapFree
0x140003baa  mov     rcx, [rbp+188h]; this
0x140003bb1  lea     r8, aWil; "wil"
0x140003bb8  mov     r9d, r14d; char *
0x140003bbb  mov     edx, 137h; void *
0x140003bc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003bc5  test    rdi, rdi
0x140003bc8  jz      short loc_140003BDB
0x140003bca  mov     rcx, rdi; hMutex
0x140003bcd  call    cs:__imp_ReleaseMutex
0x140003bd3  test    eax, eax
0x140003bd5  jz      loc_140003CF2
0x140003bdb  mov     rcx, rbx; hObject
0x140003bde  call    cs:__imp_CloseHandle
0x140003be4  test    eax, eax
0x140003be6  jz      loc_140003D04
0x140003bec  mov     eax, r14d
0x140003bef  jmp     short loc_140003C5F
0x140003bf1  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140003bf6  xor     edx, edx; Val
0x140003bf8  mov     dword ptr [rsi], 1
0x140003bfe  lea     rcx, [rsi+22h]; void *
0x140003c02  mov     [rsi+8], rbx
0x140003c06  movdqu  xmmword ptr [rsi+10h], xmm0
0x140003c0b  lea     r8d, [rdx+56h]; Size
0x140003c0f  call    memset_0
0x140003c14  xor     edx, edx; Val
0x140003c16  mov     word ptr [rsi+20h], 58h ; 'X'
0x140003c1c  lea     rcx, [rsi+28h]; void *
0x140003c20  mov     dword ptr [rsi+24h], 1
0x140003c27  lea     r8d, [rdx+50h]; Size
0x140003c2b  call    memset_0
0x140003c30  xor     ebx, ebx
0x140003c32  mov     [r15], rsi
0x140003c35  test    rdi, rdi
0x140003c38  jz      short loc_140003C4B
0x140003c3a  mov     rcx, rdi; hMutex
0x140003c3d  call    cs:__imp_ReleaseMutex
0x140003c43  test    eax, eax
0x140003c45  jz      loc_140003D16
0x140003c4b  test    rbx, rbx
0x140003c4e  jz      short loc_140003C5D
0x140003c50  mov     rcx, rbx; hObject
0x140003c53  call    cs:__imp_CloseHandle
0x140003c59  test    eax, eax
0x140003c5b  jz      short loc_140003C85
0x140003c5d  xor     eax, eax
0x140003c5f  mov     rcx, [rbp+180h+var_30]
0x140003c66  xor     rcx, rsp; StackCookie
0x140003c69  call    __security_check_cookie
0x140003c6e  mov     rbx, [rsp+280h+arg_10]
0x140003c76  add     rsp, 260h
0x140003c7d  pop     r15
0x140003c7f  pop     r14
0x140003c81  pop     rdi
0x140003c82  pop     rsi
0x140003c83  pop     rbp
0x140003c84  retn
0x140003c85  mov     rcx, [rbp+188h]; this
0x140003c8c  mov     edx, 0A0Bh; void *
0x140003c91  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003c97  mov     rcx, [rbp+188h]; this
0x140003c9e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140003ca4  mov     rcx, [rbp+188h]; this
0x140003cab  mov     edx, 0A15h; void *
0x140003cb0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003cb6  mov     rcx, [rbp+188h]; this
0x140003cbd  mov     edx, 0A0Bh; void *
0x140003cc2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003cc8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003cce  mov     rcx, [rbp+188h]; this
0x140003cd5  mov     edx, 0A0Bh; void *
0x140003cda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003ce0  mov     rcx, [rbp+188h]; this
0x140003ce7  mov     edx, 0A0Bh; void *
0x140003cec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003cf2  mov     rcx, [rbp+188h]; this
0x140003cf9  mov     edx, 0A15h; void *
0x140003cfe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d04  mov     rcx, [rbp+188h]; this
0x140003d0b  mov     edx, 0A0Bh; void *
0x140003d10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140003d16  mov     rcx, [rbp+188h]; this
0x140003d1d  mov     edx, 0A15h; void *
0x140003d22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
