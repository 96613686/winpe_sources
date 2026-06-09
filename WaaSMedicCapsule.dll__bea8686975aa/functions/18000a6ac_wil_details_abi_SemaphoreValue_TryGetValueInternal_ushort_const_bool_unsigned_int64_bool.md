# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a6ac`
- end: `0x18000a93b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007818`
- `0x1800187b4`

## callees

- `0x180003bb0`
- `0x180008a40`
- `0x180009a34`
- `0x180009a54`
- `0x18000a4ac`
- `0x18000a6ac`
- `0x18000ab48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a740`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a7bc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a740`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a889`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a78d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a810`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a84d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a87a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a78d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a810`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a84d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a87a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000a6ac  push    rbp
0x18000a6ae  push    rbx
0x18000a6af  push    rsi
0x18000a6b0  push    rdi
0x18000a6b1  push    r14
0x18000a6b3  push    r15
0x18000a6b5  lea     rbp, [rsp-158h]
0x18000a6bd  sub     rsp, 258h
0x18000a6c4  mov     rax, cs:__security_cookie
0x18000a6cb  xor     rax, rsp
0x18000a6ce  mov     [rbp+180h+var_40], rax
0x18000a6d5  xor     r15d, r15d
0x18000a6d8  lea     rax, [rsp+280h+Name]
0x18000a6dd  mov     [r8], r15
0x18000a6e0  mov     r14, r8
0x18000a6e3  mov     edx, 104h
0x18000a6e8  mov     r9d, 7FFFFFFEh
0x18000a6ee  test    r9, r9
0x18000a6f1  jz      short loc_18000A712
0x18000a6f3  movzx   r8d, word ptr [rcx]
0x18000a6f7  test    r8w, r8w
0x18000a6fb  jz      short loc_18000A712
0x18000a6fd  mov     [rax], r8w
0x18000a701  add     rcx, 2
0x18000a705  add     rax, 2
0x18000a709  dec     r9
0x18000a70c  sub     rdx, 1; unsigned __int64
0x18000a710  jnz     short loc_18000A6EE
0x18000a712  test    rdx, rdx
0x18000a715  lea     rcx, [rax-2]
0x18000a719  lea     r8, aP0; "_p0"
0x18000a720  cmovnz  rcx, rax
0x18000a724  mov     [rcx], r15w
0x18000a728  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a72d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a732  mov     esi, 1F0003h
0x18000a737  lea     r8, [rsp+280h+Name]; lpName
0x18000a73c  mov     ecx, esi; dwDesiredAccess
0x18000a73e  xor     edx, edx; bInheritHandle
0x18000a740  call    cs:__imp_OpenSemaphoreW
0x18000a746  mov     rbx, rax
0x18000a749  test    rax, rax
0x18000a74c  jz      loc_18000A889
0x18000a752  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a757  mov     [rsp+280h+var_25C], r15d
0x18000a75c  mov     rcx, rax; hHandle
0x18000a75f  mov     [rsp+280h+var_260], r15d; int
0x18000a764  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a769  mov     edi, eax
0x18000a76b  test    eax, eax
0x18000a76d  jns     short loc_18000A7A2
0x18000a76f  mov     rcx, [rbp+188h]; this
0x18000a776  lea     r8, aWil; "wil"
0x18000a77d  mov     r9d, eax; char *
0x18000a780  mov     edx, 0D6h; void *
0x18000a785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a78a  mov     rcx, rbx; hObject
0x18000a78d  call    cs:__imp_CloseHandle
0x18000a793  test    eax, eax
0x18000a795  jz      loc_18000A905
0x18000a79b  mov     eax, edi
0x18000a79d  jmp     loc_18000A8B0
0x18000a7a2  lea     r8, asc_180067D30; "h"
0x18000a7a9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a7ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a7b3  lea     r8, [rsp+280h+Name]; lpName
0x18000a7b8  xor     edx, edx; bInheritHandle
0x18000a7ba  mov     ecx, esi; dwDesiredAccess
0x18000a7bc  call    cs:__imp_OpenSemaphoreW
0x18000a7c2  mov     rdi, rax
0x18000a7c5  test    rax, rax
0x18000a7c8  jz      loc_18000A85D
0x18000a7ce  lea     rdx, [rsp+280h+var_260]; int *
0x18000a7d3  mov     rcx, rax; hHandle
0x18000a7d6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a7db  mov     esi, eax
0x18000a7dd  test    eax, eax
0x18000a7df  jns     short loc_18000A825
0x18000a7e1  mov     rcx, [rbp+188h]; this
0x18000a7e8  lea     r8, aWil; "wil"
0x18000a7ef  mov     r9d, eax; char *
0x18000a7f2  mov     edx, 0DEh; void *
0x18000a7f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7fc  mov     rcx, rdi; hObject
0x18000a7ff  call    cs:__imp_CloseHandle
0x18000a805  test    eax, eax
0x18000a807  jz      loc_18000A917
0x18000a80d  mov     rcx, rbx; hObject
0x18000a810  call    cs:__imp_CloseHandle
0x18000a816  test    eax, eax
0x18000a818  jz      loc_18000A929
0x18000a81e  mov     eax, esi
0x18000a820  jmp     loc_18000A8B0
0x18000a825  mov     rcx, rdi; hObject
0x18000a828  call    cs:__imp_CloseHandle
0x18000a82e  test    eax, eax
0x18000a830  jz      loc_18000A8CF
0x18000a836  movsxd  rax, [rsp+280h+var_25C]
0x18000a83b  movsxd  rcx, [rsp+280h+var_260]
0x18000a840  shl     rcx, 1Fh
0x18000a844  or      rcx, rax
0x18000a847  mov     [r14], rcx
0x18000a84a  mov     rcx, rbx; hObject
0x18000a84d  call    cs:__imp_CloseHandle
0x18000a853  test    eax, eax
0x18000a855  jz      loc_18000A8E1
0x18000a85b  jmp     short loc_18000A894
0x18000a85d  mov     rcx, [rbp+188h]; this
0x18000a864  lea     r8, aWil; "wil"
0x18000a86b  mov     edx, 0DCh; void *
0x18000a870  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a875  mov     rcx, rbx; hObject
0x18000a878  mov     edi, eax
0x18000a87a  call    cs:__imp_CloseHandle
0x18000a880  test    eax, eax
0x18000a882  jz      short loc_18000A8F3
0x18000a884  jmp     loc_18000A79B
0x18000a889  call    cs:__imp_GetLastError
0x18000a88f  cmp     eax, 2
0x18000a892  jnz     short loc_18000A898
0x18000a894  xor     eax, eax
0x18000a896  jmp     short loc_18000A8B0
0x18000a898  mov     rcx, [rbp+188h]; this
0x18000a89f  lea     r8, aWil; "wil"
0x18000a8a6  mov     edx, 0D0h; void *
0x18000a8ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a8b0  mov     rcx, [rbp+180h+var_40]
0x18000a8b7  xor     rcx, rsp; StackCookie
0x18000a8ba  call    __security_check_cookie
0x18000a8bf  add     rsp, 258h
0x18000a8c6  pop     r15
0x18000a8c8  pop     r14
0x18000a8ca  pop     rdi
0x18000a8cb  pop     rsi
0x18000a8cc  pop     rbx
0x18000a8cd  pop     rbp
0x18000a8ce  retn
0x18000a8cf  mov     rcx, [rbp+188h]; this
0x18000a8d6  mov     edx, 0A0Bh; void *
0x18000a8db  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a8e1  mov     rcx, [rbp+188h]; this
0x18000a8e8  mov     edx, 0A0Bh; void *
0x18000a8ed  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a8f3  mov     rcx, [rbp+188h]; this
0x18000a8fa  mov     edx, 0A0Bh; void *
0x18000a8ff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a905  mov     rcx, [rbp+188h]; this
0x18000a90c  mov     edx, 0A0Bh; void *
0x18000a911  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a917  mov     rcx, [rbp+188h]; this
0x18000a91e  mov     edx, 0A0Bh; void *
0x18000a923  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a929  mov     rcx, [rbp+188h]; this
0x18000a930  mov     edx, 0A0Bh; void *
0x18000a935  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
