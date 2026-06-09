# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f7a8`
- end: `0x18000fa22`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007de8`

## callees

- `0x180001dc0`
- `0x18000bbd4`
- `0x18000ecf0`
- `0x18000ed10`
- `0x18000f7a8`
- `0x1800107b0`
- `0x18001168c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f83c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f8b8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f83c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f8b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f977`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f889`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f90c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f889`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f90c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f921`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f968`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v4; // rax
  size_t v6; // rdx
  __int64 v7; // r9
  wchar_t *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  size_t v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t pszDest[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = pszDest;
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
  StringCchCatW(pszDest, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(pszDest, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000f7a8  push    rbp
0x18000f7aa  push    rbx
0x18000f7ab  push    rsi
0x18000f7ac  push    rdi
0x18000f7ad  push    r14
0x18000f7af  push    r15
0x18000f7b1  lea     rbp, [rsp-158h]
0x18000f7b9  sub     rsp, 258h
0x18000f7c0  mov     rax, cs:__security_cookie
0x18000f7c7  xor     rax, rsp
0x18000f7ca  mov     [rbp+180h+var_40], rax
0x18000f7d1  xor     r15d, r15d
0x18000f7d4  lea     rax, [rsp+280h+pszDest]
0x18000f7d9  mov     [r8], r15
0x18000f7dc  mov     r14, r8
0x18000f7df  mov     edx, 104h
0x18000f7e4  mov     r9d, 7FFFFFFEh
0x18000f7ea  test    r9, r9
0x18000f7ed  jz      short loc_18000F80E
0x18000f7ef  movzx   r8d, word ptr [rcx]
0x18000f7f3  test    r8w, r8w
0x18000f7f7  jz      short loc_18000F80E
0x18000f7f9  mov     [rax], r8w
0x18000f7fd  add     rcx, 2
0x18000f801  add     rax, 2
0x18000f805  dec     r9
0x18000f808  sub     rdx, 1; cchDest
0x18000f80c  jnz     short loc_18000F7EA
0x18000f80e  test    rdx, rdx
0x18000f811  lea     rcx, [rax-2]
0x18000f815  lea     r8, aP0; "_p0"
0x18000f81c  cmovnz  rcx, rax
0x18000f820  mov     [rcx], r15w
0x18000f824  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000f829  call    StringCchCatW
0x18000f82e  mov     esi, 1F0003h
0x18000f833  lea     r8, [rsp+280h+pszDest]; lpName
0x18000f838  mov     ecx, esi; dwDesiredAccess
0x18000f83a  xor     edx, edx; bInheritHandle
0x18000f83c  call    cs:__imp_OpenSemaphoreW
0x18000f842  mov     rbx, rax
0x18000f845  test    rax, rax
0x18000f848  jz      loc_18000F977
0x18000f84e  lea     rdx, [rsp+280h+var_25C]; int *
0x18000f853  mov     [rsp+280h+var_25C], r15d
0x18000f858  mov     rcx, rax; hHandle
0x18000f85b  mov     [rsp+280h+var_260], r15d; int
0x18000f860  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f865  mov     edi, eax
0x18000f867  test    eax, eax
0x18000f869  jns     short loc_18000F89E
0x18000f86b  mov     rcx, [rbp+188h]; this
0x18000f872  lea     r8, aWil; "wil"
0x18000f879  mov     r9d, eax; char *
0x18000f87c  mov     edx, 0D6h; void *
0x18000f881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f886  mov     rcx, rbx; hObject
0x18000f889  call    cs:__imp_CloseHandle
0x18000f88f  test    eax, eax
0x18000f891  jz      loc_18000F9EC
0x18000f897  mov     eax, edi
0x18000f899  jmp     loc_18000F997
0x18000f89e  lea     r8, asc_18001D8F8; "h"
0x18000f8a5  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18000f8aa  call    StringCchCatW
0x18000f8af  lea     r8, [rsp+280h+pszDest]; lpName
0x18000f8b4  xor     edx, edx; bInheritHandle
0x18000f8b6  mov     ecx, esi; dwDesiredAccess
0x18000f8b8  call    cs:__imp_OpenSemaphoreW
0x18000f8be  mov     rdi, rax
0x18000f8c1  test    rax, rax
0x18000f8c4  jz      loc_18000F952
0x18000f8ca  lea     rdx, [rsp+280h+var_260]; int *
0x18000f8cf  mov     rcx, rax; hHandle
0x18000f8d2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f8d7  mov     esi, eax
0x18000f8d9  test    eax, eax
0x18000f8db  jns     short loc_18000F91E
0x18000f8dd  mov     rcx, [rbp+188h]; this
0x18000f8e4  lea     r8, aWil; "wil"
0x18000f8eb  mov     r9d, eax; char *
0x18000f8ee  mov     edx, 0DEh; void *
0x18000f8f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f8f8  mov     rcx, rdi; hObject
0x18000f8fb  call    cs:__imp_CloseHandle
0x18000f901  test    eax, eax
0x18000f903  jz      loc_18000F9FE
0x18000f909  mov     rcx, rbx; hObject
0x18000f90c  call    cs:__imp_CloseHandle
0x18000f912  test    eax, eax
0x18000f914  jz      loc_18000FA10
0x18000f91a  mov     eax, esi
0x18000f91c  jmp     short loc_18000F997
0x18000f91e  mov     rcx, rdi; hObject
0x18000f921  call    cs:__imp_CloseHandle
0x18000f927  test    eax, eax
0x18000f929  jz      loc_18000F9B6
0x18000f92f  movsxd  rax, [rsp+280h+var_25C]
0x18000f934  movsxd  rcx, [rsp+280h+var_260]
0x18000f939  shl     rcx, 1Fh
0x18000f93d  or      rcx, rax
0x18000f940  mov     [r14], rcx
0x18000f943  mov     rcx, rbx; hObject
0x18000f946  call    cs:__imp_CloseHandle
0x18000f94c  test    eax, eax
0x18000f94e  jz      short loc_18000F9C8
0x18000f950  jmp     short loc_18000F982
0x18000f952  mov     rcx, [rbp+188h]; this
0x18000f959  mov     edx, 0DCh; void *
0x18000f95e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f963  mov     rcx, rbx; hObject
0x18000f966  mov     edi, eax
0x18000f968  call    cs:__imp_CloseHandle
0x18000f96e  test    eax, eax
0x18000f970  jz      short loc_18000F9DA
0x18000f972  jmp     loc_18000F897
0x18000f977  call    cs:__imp_GetLastError
0x18000f97d  cmp     eax, 2
0x18000f980  jnz     short loc_18000F986
0x18000f982  xor     eax, eax
0x18000f984  jmp     short loc_18000F997
0x18000f986  mov     rcx, [rbp+188h]; this
0x18000f98d  mov     edx, 0D0h; void *
0x18000f992  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f997  mov     rcx, [rbp+180h+var_40]
0x18000f99e  xor     rcx, rsp; StackCookie
0x18000f9a1  call    __security_check_cookie
0x18000f9a6  add     rsp, 258h
0x18000f9ad  pop     r15
0x18000f9af  pop     r14
0x18000f9b1  pop     rdi
0x18000f9b2  pop     rsi
0x18000f9b3  pop     rbx
0x18000f9b4  pop     rbp
0x18000f9b5  retn
0x18000f9b6  mov     rcx, [rbp+188h]; this
0x18000f9bd  mov     edx, 0A0Bh; void *
0x18000f9c2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f9c8  mov     rcx, [rbp+188h]; this
0x18000f9cf  mov     edx, 0A0Bh; void *
0x18000f9d4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f9da  mov     rcx, [rbp+188h]; this
0x18000f9e1  mov     edx, 0A0Bh; void *
0x18000f9e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f9ec  mov     rcx, [rbp+188h]; this
0x18000f9f3  mov     edx, 0A0Bh; void *
0x18000f9f8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f9fe  mov     rcx, [rbp+188h]; this
0x18000fa05  mov     edx, 0A0Bh; void *
0x18000fa0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fa10  mov     rcx, [rbp+188h]; this
0x18000fa17  mov     edx, 0A0Bh; void *
0x18000fa1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
