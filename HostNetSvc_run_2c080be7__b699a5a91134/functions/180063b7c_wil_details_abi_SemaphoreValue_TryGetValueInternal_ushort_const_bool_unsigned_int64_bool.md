# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180063b7c`
- end: `0x180063e14`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800616f8`
- `0x180070068`

## callees

- `0x18005f0c0`
- `0x1800627e8`
- `0x180063074`
- `0x180063094`
- `0x1800639d4`
- `0x180063b7c`
- `0x180064018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180063c13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180063c95`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180063c13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180063c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063d62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063d62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063cd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063ce9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063d53`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x180063b7c  push    rbp
0x180063b7e  push    rbx
0x180063b7f  push    rsi
0x180063b80  push    rdi
0x180063b81  push    r14
0x180063b83  push    r15
0x180063b85  lea     rbp, [rsp-158h]
0x180063b8d  sub     rsp, 258h
0x180063b94  mov     rax, cs:__security_cookie
0x180063b9b  xor     rax, rsp
0x180063b9e  mov     [rbp+180h+var_40], rax
0x180063ba5  xor     r15d, r15d
0x180063ba8  lea     rax, [rsp+280h+Name]
0x180063bad  mov     esi, 104h
0x180063bb2  mov     [r8], r15
0x180063bb5  mov     edx, esi
0x180063bb7  mov     r14, r8
0x180063bba  mov     r9d, 7FFFFFFEh
0x180063bc0  test    r9, r9
0x180063bc3  jz      short loc_180063BE4
0x180063bc5  movzx   r8d, word ptr [rcx]
0x180063bc9  test    r8w, r8w
0x180063bcd  jz      short loc_180063BE4
0x180063bcf  mov     [rax], r8w
0x180063bd3  add     rcx, 2
0x180063bd7  add     rax, 2
0x180063bdb  dec     r9
0x180063bde  sub     rdx, 1
0x180063be2  jnz     short loc_180063BC0
0x180063be4  test    rdx, rdx
0x180063be7  lea     rcx, [rax-2]
0x180063beb  lea     r8, aP0; "_p0"
0x180063bf2  mov     rdx, rsi; unsigned __int64
0x180063bf5  cmovnz  rcx, rax
0x180063bf9  mov     [rcx], r15w
0x180063bfd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180063c02  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180063c07  lea     r8, [rsp+280h+Name]; lpName
0x180063c0c  xor     edx, edx; bInheritHandle
0x180063c0e  mov     ecx, 1F0003h; dwDesiredAccess
0x180063c13  call    cs:__imp_OpenSemaphoreW
0x180063c19  mov     rbx, rax
0x180063c1c  test    rax, rax
0x180063c1f  jz      loc_180063D62
0x180063c25  lea     rdx, [rsp+280h+var_25C]; int *
0x180063c2a  mov     [rsp+280h+var_25C], r15d
0x180063c2f  mov     rcx, rax; hHandle
0x180063c32  mov     [rsp+280h+var_260], r15d; int
0x180063c37  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180063c3c  mov     edi, eax
0x180063c3e  test    eax, eax
0x180063c40  jns     short loc_180063C75
0x180063c42  mov     rcx, [rbp+188h]; this
0x180063c49  lea     r8, aWil; "wil"
0x180063c50  mov     r9d, eax; char *
0x180063c53  mov     edx, 0D6h; void *
0x180063c58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063c5d  mov     rcx, rbx; hObject
0x180063c60  call    cs:__imp_CloseHandle
0x180063c66  test    eax, eax
0x180063c68  jz      loc_180063DDE
0x180063c6e  mov     eax, edi
0x180063c70  jmp     loc_180063D89
0x180063c75  lea     r8, asc_1802E2990; "h"
0x180063c7c  mov     rdx, rsi; unsigned __int64
0x180063c7f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180063c84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180063c89  lea     r8, [rsp+280h+Name]; lpName
0x180063c8e  xor     edx, edx; bInheritHandle
0x180063c90  mov     ecx, 1F0003h; dwDesiredAccess
0x180063c95  call    cs:__imp_OpenSemaphoreW
0x180063c9b  mov     rdi, rax
0x180063c9e  test    rax, rax
0x180063ca1  jz      loc_180063D36
0x180063ca7  lea     rdx, [rsp+280h+var_260]; int *
0x180063cac  mov     rcx, rax; hHandle
0x180063caf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180063cb4  mov     esi, eax
0x180063cb6  test    eax, eax
0x180063cb8  jns     short loc_180063CFE
0x180063cba  mov     rcx, [rbp+188h]; this
0x180063cc1  lea     r8, aWil; "wil"
0x180063cc8  mov     r9d, eax; char *
0x180063ccb  mov     edx, 0DEh; void *
0x180063cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180063cd5  mov     rcx, rdi; hObject
0x180063cd8  call    cs:__imp_CloseHandle
0x180063cde  test    eax, eax
0x180063ce0  jz      loc_180063DF0
0x180063ce6  mov     rcx, rbx; hObject
0x180063ce9  call    cs:__imp_CloseHandle
0x180063cef  test    eax, eax
0x180063cf1  jz      loc_180063E02
0x180063cf7  mov     eax, esi
0x180063cf9  jmp     loc_180063D89
0x180063cfe  mov     rcx, rdi; hObject
0x180063d01  call    cs:__imp_CloseHandle
0x180063d07  test    eax, eax
0x180063d09  jz      loc_180063DA8
0x180063d0f  movsxd  rax, [rsp+280h+var_25C]
0x180063d14  movsxd  rcx, [rsp+280h+var_260]
0x180063d19  shl     rcx, 1Fh
0x180063d1d  or      rcx, rax
0x180063d20  mov     [r14], rcx
0x180063d23  mov     rcx, rbx; hObject
0x180063d26  call    cs:__imp_CloseHandle
0x180063d2c  test    eax, eax
0x180063d2e  jz      loc_180063DBA
0x180063d34  jmp     short loc_180063D6D
0x180063d36  mov     rcx, [rbp+188h]; this
0x180063d3d  lea     r8, aWil; "wil"
0x180063d44  mov     edx, 0DCh; void *
0x180063d49  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180063d4e  mov     rcx, rbx; hObject
0x180063d51  mov     edi, eax
0x180063d53  call    cs:__imp_CloseHandle
0x180063d59  test    eax, eax
0x180063d5b  jz      short loc_180063DCC
0x180063d5d  jmp     loc_180063C6E
0x180063d62  call    cs:__imp_GetLastError
0x180063d68  cmp     eax, 2
0x180063d6b  jnz     short loc_180063D71
0x180063d6d  xor     eax, eax
0x180063d6f  jmp     short loc_180063D89
0x180063d71  mov     rcx, [rbp+188h]; this
0x180063d78  lea     r8, aWil; "wil"
0x180063d7f  mov     edx, 0D0h; void *
0x180063d84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180063d89  mov     rcx, [rbp+180h+var_40]
0x180063d90  xor     rcx, rsp; StackCookie
0x180063d93  call    __security_check_cookie
0x180063d98  add     rsp, 258h
0x180063d9f  pop     r15
0x180063da1  pop     r14
0x180063da3  pop     rdi
0x180063da4  pop     rsi
0x180063da5  pop     rbx
0x180063da6  pop     rbp
0x180063da7  retn
0x180063da8  mov     rcx, [rbp+188h]; this
0x180063daf  mov     edx, 0A0Bh; void *
0x180063db4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180063dba  mov     rcx, [rbp+188h]; this
0x180063dc1  mov     edx, 0A0Bh; void *
0x180063dc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180063dcc  mov     rcx, [rbp+188h]; this
0x180063dd3  mov     edx, 0A0Bh; void *
0x180063dd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180063dde  mov     rcx, [rbp+188h]; this
0x180063de5  mov     edx, 0A0Bh; void *
0x180063dea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180063df0  mov     rcx, [rbp+188h]; this
0x180063df7  mov     edx, 0A0Bh; void *
0x180063dfc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180063e02  mov     rcx, [rbp+188h]; this
0x180063e09  mov     edx, 0A0Bh; void *
0x180063e0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
