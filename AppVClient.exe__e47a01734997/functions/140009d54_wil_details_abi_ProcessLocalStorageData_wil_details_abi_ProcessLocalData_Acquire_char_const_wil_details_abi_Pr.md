# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140009d54`
- end: `0x14000a0f2`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x14000d26c`

## callees

- `0x140004280`
- `0x1400050e0`
- `0x140009d54`
- `0x14000a998`
- `0x14000baec`
- `0x14000ca7c`
- `0x14001102c`
- `0x140011564`
- `0x140013384`
- `0x14001347c`
- `0x140013c48`
- `0x140013c58`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140009f67`
- `KERNEL32!GetProcessHeap` at `0x140009f67`
- `KERNEL32!CreateMutexExW` at `0x140009dcc`
- `KERNEL32!CreateMutexExW` at `0x140009dcc`
- `KERNEL32!CloseHandle` at `0x140009e7f`
- `KERNEL32!CloseHandle` at `0x140009f41`
- `KERNEL32!CloseHandle` at `0x140009f59`
- `KERNEL32!CloseHandle` at `0x140009fa8`
- `KERNEL32!CloseHandle` at `0x14000a01d`
- `KERNEL32!CloseHandle` at `0x140009e7f`
- `KERNEL32!CloseHandle` at `0x140009f41`
- `KERNEL32!CloseHandle` at `0x140009f59`
- `KERNEL32!CloseHandle` at `0x140009fa8`
- `KERNEL32!CloseHandle` at `0x14000a01d`
- `KERNEL32!WaitForSingleObjectEx` at `0x140009ded`
- `KERNEL32!WaitForSingleObjectEx` at `0x140009ded`
- `KERNEL32!ReleaseMutex` at `0x140009e6e`
- `KERNEL32!ReleaseMutex` at `0x140009f97`
- `KERNEL32!ReleaseMutex` at `0x14000a007`
- `KERNEL32!ReleaseMutex` at `0x140009e6e`
- `KERNEL32!ReleaseMutex` at `0x140009f97`
- `KERNEL32!ReleaseMutex` at `0x14000a007`
- `KERNEL32!GetCurrentProcessId` at `0x140009d8d`
- `KERNEL32!GetCurrentProcessId` at `0x140009d8d`
- `KERNEL32!HeapFree` at `0x140009f75`
- `KERNEL32!HeapFree` at `0x140009f75`

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
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  const char *v19; // r9
  unsigned int v20; // r8d
  const char *v21; // r9
  _DWORD *v22; // rcx
  unsigned __int64 v23; // rax
  wil::details::in1diag3 *v24; // rcx
  __int64 v25; // r8
  _QWORD *v26; // rsi
  unsigned int v27; // r14d
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
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
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
  v26 = (_QWORD *)v23;
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
      *(_DWORD *)v26 = 1;
      v26[1] = v6;
      *((_OWORD *)v26 + 1) = v40;
      memset_0((char *)v26 + 34, 0, 0x56u);
      *((_WORD *)v26 + 16) = 88;
      *((_DWORD *)v26 + 9) = 1;
      memset_0(v26 + 5, 0, 0x50u);
      v6 = 0;
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
0x140009d54  mov     [rsp-8+arg_10], rbx
0x140009d59  push    rbp
0x140009d5a  push    rsi
0x140009d5b  push    rdi
0x140009d5c  push    r14
0x140009d5e  push    r15
0x140009d60  lea     rbp, [rsp-160h]
0x140009d68  sub     rsp, 260h
0x140009d6f  mov     rax, cs:__security_cookie
0x140009d76  xor     rax, rsp
0x140009d79  mov     [rbp+180h+var_30], rax
0x140009d80  mov     r15, rdx
0x140009d83  mov     qword ptr [rdx], 0
0x140009d8a  mov     rbx, rcx
0x140009d8d  call    cs:__imp_GetCurrentProcessId
0x140009d93  mov     r14d, 78h ; 'x'
0x140009d99  mov     [rsp+280h+var_258], rbx
0x140009d9e  mov     r9d, eax
0x140009da1  mov     [rsp+280h+var_260], r14d; int
0x140009da6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009dad  mov     edx, 104h; unsigned __int64
0x140009db2  lea     rcx, [rsp+280h+Name]; Buffer
0x140009db7  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140009dbc  mov     r9d, 1F0001h; dwDesiredAccess
0x140009dc2  lea     rdx, [rsp+280h+Name]; lpName
0x140009dc7  xor     r8d, r8d; dwFlags
0x140009dca  xor     ecx, ecx; lpMutexAttributes
0x140009dcc  call    cs:__imp_CreateMutexExW
0x140009dd2  mov     rbx, rax
0x140009dd5  test    rax, rax
0x140009dd8  jnz     short loc_140009DE4
0x140009dda  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009ddf  jmp     loc_14000A029
0x140009de4  xor     r8d, r8d; bAlertable
0x140009de7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140009dea  mov     rcx, rbx; hHandle
0x140009ded  call    cs:__imp_WaitForSingleObjectEx
0x140009df3  cmp     eax, 102h
0x140009df8  jz      short loc_140009E0A
0x140009dfa  test    eax, 0FFFFFF7Fh
0x140009dff  jnz     loc_14000A061
0x140009e05  mov     rdi, rbx
0x140009e08  jmp     short loc_140009E0C
0x140009e0a  xor     edi, edi
0x140009e0c  lea     r8, [rsp+280h+hObject]; unsigned __int64 *
0x140009e11  mov     [rsp+280h+hObject], 0
0x140009e1a  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140009e1f  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)
0x140009e24  mov     esi, eax
0x140009e26  test    eax, eax
0x140009e28  jns     short loc_140009E94
0x140009e2a  mov     rcx, [rbp+188h]; this
0x140009e31  mov     r9d, eax; char *
0x140009e34  mov     edx, 66h ; 'f'; void *
0x140009e39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009e3e  mov     rcx, [rbp+188h]; this
0x140009e45  mov     r9d, esi; char *
0x140009e48  mov     edx, 6Fh ; 'o'; void *
0x140009e4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009e52  mov     rcx, [rbp+188h]; this
0x140009e59  mov     r9d, esi; char *
0x140009e5c  mov     edx, 12Eh; void *
0x140009e61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009e66  test    rdi, rdi
0x140009e69  jz      short loc_140009E7C
0x140009e6b  mov     rcx, rdi; hMutex
0x140009e6e  call    cs:__imp_ReleaseMutex
0x140009e74  test    eax, eax
0x140009e76  jz      loc_14000A06E
0x140009e7c  mov     rcx, rbx; hObject
0x140009e7f  call    cs:__imp_CloseHandle
0x140009e85  test    eax, eax
0x140009e87  jz      loc_14000A080
0x140009e8d  mov     eax, esi
0x140009e8f  jmp     loc_14000A029
0x140009e94  mov     rax, [rsp+280h+hObject]
0x140009e99  lea     rcx, ds:0[rax*4]
0x140009ea1  test    rcx, rcx
0x140009ea4  jz      short loc_140009EB4
0x140009ea6  mov     [r15], rcx
0x140009ea9  mov     eax, [rcx]
0x140009eab  inc     eax
0x140009ead  mov     [rcx], eax
0x140009eaf  jmp     loc_140009FFF
0x140009eb4  mov     rdx, r14; dwBytes
0x140009eb7  mov     qword ptr [r15], 0
0x140009ebe  mov     ecx, 8; dwFlags
0x140009ec3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140009ec8  mov     rsi, rax
0x140009ecb  test    rax, rax
0x140009ece  jnz     short loc_140009EEF
0x140009ed0  mov     rcx, [rbp+188h]; this
0x140009ed7  mov     r14d, 8007000Eh
0x140009edd  mov     r9d, r14d; char *
0x140009ee0  mov     edx, 14Bh; void *
0x140009ee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009eea  jmp     loc_140009F7B
0x140009eef  xorps   xmm0, xmm0
0x140009ef2  movdqu  xmmword ptr [rsp+280h+hObject], xmm0
0x140009ef8  test    sil, 3
0x140009efc  jnz     loc_14000A092
0x140009f02  mov     r9, rsi
0x140009f05  lea     rdx, [rsp+280h+Name]; wchar_t *
0x140009f0a  shr     r9, 2; unsigned __int64
0x140009f0e  lea     rcx, [rsp+280h+hObject]; this
0x140009f13  call    ?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z; wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)
0x140009f18  mov     r14d, eax
0x140009f1b  test    eax, eax
0x140009f1d  jns     loc_140009FBB
0x140009f23  mov     rcx, [rbp+188h]; this
0x140009f2a  mov     r9d, eax; char *
0x140009f2d  mov     edx, 14Eh; void *
0x140009f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009f37  mov     rcx, [rsp+280h+hObject+8]; hObject
0x140009f3c  test    rcx, rcx
0x140009f3f  jz      short loc_140009F4F
0x140009f41  call    cs:__imp_CloseHandle
0x140009f47  test    eax, eax
0x140009f49  jz      loc_14000A098
0x140009f4f  mov     rcx, [rsp+280h+hObject]; hObject
0x140009f54  test    rcx, rcx
0x140009f57  jz      short loc_140009F67
0x140009f59  call    cs:__imp_CloseHandle
0x140009f5f  test    eax, eax
0x140009f61  jz      loc_14000A0AA
0x140009f67  call    cs:__imp_GetProcessHeap
0x140009f6d  mov     r8, rsi; lpMem
0x140009f70  xor     edx, edx; dwFlags
0x140009f72  mov     rcx, rax; hHeap
0x140009f75  call    cs:__imp_HeapFree
0x140009f7b  mov     rcx, [rbp+188h]; this
0x140009f82  mov     r9d, r14d; char *
0x140009f85  mov     edx, 137h; void *
0x140009f8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009f8f  test    rdi, rdi
0x140009f92  jz      short loc_140009FA5
0x140009f94  mov     rcx, rdi; hMutex
0x140009f97  call    cs:__imp_ReleaseMutex
0x140009f9d  test    eax, eax
0x140009f9f  jz      loc_14000A0BC
0x140009fa5  mov     rcx, rbx; hObject
0x140009fa8  call    cs:__imp_CloseHandle
0x140009fae  test    eax, eax
0x140009fb0  jz      loc_14000A0CE
0x140009fb6  mov     eax, r14d
0x140009fb9  jmp     short loc_14000A029
0x140009fbb  movups  xmm0, xmmword ptr [rsp+280h+hObject]
0x140009fc0  xor     edx, edx; Val
0x140009fc2  mov     dword ptr [rsi], 1
0x140009fc8  lea     rcx, [rsi+22h]; void *
0x140009fcc  mov     [rsi+8], rbx
0x140009fd0  movdqu  xmmword ptr [rsi+10h], xmm0
0x140009fd5  lea     r8d, [rdx+56h]; Size
0x140009fd9  call    memset_0
0x140009fde  xor     edx, edx; Val
0x140009fe0  mov     word ptr [rsi+20h], 58h ; 'X'
0x140009fe6  lea     rcx, [rsi+28h]; void *
0x140009fea  mov     dword ptr [rsi+24h], 1
0x140009ff1  lea     r8d, [rdx+50h]; Size
0x140009ff5  call    memset_0
0x140009ffa  xor     ebx, ebx
0x140009ffc  mov     [r15], rsi
0x140009fff  test    rdi, rdi
0x14000a002  jz      short loc_14000A015
0x14000a004  mov     rcx, rdi; hMutex
0x14000a007  call    cs:__imp_ReleaseMutex
0x14000a00d  test    eax, eax
0x14000a00f  jz      loc_14000A0E0
0x14000a015  test    rbx, rbx
0x14000a018  jz      short loc_14000A027
0x14000a01a  mov     rcx, rbx; hObject
0x14000a01d  call    cs:__imp_CloseHandle
0x14000a023  test    eax, eax
0x14000a025  jz      short loc_14000A04F
0x14000a027  xor     eax, eax
0x14000a029  mov     rcx, [rbp+180h+var_30]
0x14000a030  xor     rcx, rsp; StackCookie
0x14000a033  call    __security_check_cookie
0x14000a038  mov     rbx, [rsp+280h+arg_10]
0x14000a040  add     rsp, 260h
0x14000a047  pop     r15
0x14000a049  pop     r14
0x14000a04b  pop     rdi
0x14000a04c  pop     rsi
0x14000a04d  pop     rbp
0x14000a04e  retn
0x14000a04f  mov     rcx, [rbp+188h]; this
0x14000a056  mov     edx, 0A0Bh; void *
0x14000a05b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a061  mov     rcx, [rbp+188h]; this
0x14000a068  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000a06e  mov     rcx, [rbp+188h]; this
0x14000a075  mov     edx, 0A15h; void *
0x14000a07a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a080  mov     rcx, [rbp+188h]; this
0x14000a087  mov     edx, 0A0Bh; void *
0x14000a08c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a092  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000a098  mov     rcx, [rbp+188h]; this
0x14000a09f  mov     edx, 0A0Bh; void *
0x14000a0a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0aa  mov     rcx, [rbp+188h]; this
0x14000a0b1  mov     edx, 0A0Bh; void *
0x14000a0b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0bc  mov     rcx, [rbp+188h]; this
0x14000a0c3  mov     edx, 0A15h; void *
0x14000a0c8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0ce  mov     rcx, [rbp+188h]; this
0x14000a0d5  mov     edx, 0A0Bh; void *
0x14000a0da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a0e0  mov     rcx, [rbp+188h]; this
0x14000a0e7  mov     edx, 0A15h; void *
0x14000a0ec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
