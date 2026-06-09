# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009bac`
- end: `0x180009e21`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003eb0`
- `0x180004254`

## callees

- `0x1800066a4`
- `0x180008c64`
- `0x180008c84`
- `0x180009620`
- `0x180009bac`
- `0x18000b858`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009cbe`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d67`

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
  int v12; // r8d
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  int v22; // r8d
  unsigned int v23; // esi
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
  StringCchCatW(Name, 260, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180009bac  push    rbp
0x180009bae  push    rbx
0x180009baf  push    rsi
0x180009bb0  push    rdi
0x180009bb1  push    r14
0x180009bb3  push    r15
0x180009bb5  lea     rbp, [rsp-158h]
0x180009bbd  sub     rsp, 258h
0x180009bc4  mov     rax, cs:__security_cookie
0x180009bcb  xor     rax, rsp
0x180009bce  mov     [rbp+180h+var_40], rax
0x180009bd5  xor     r15d, r15d
0x180009bd8  lea     rax, [rsp+280h+Name]
0x180009bdd  mov     esi, 104h
0x180009be2  mov     [r8], r15
0x180009be5  mov     edx, esi
0x180009be7  mov     r14, r8
0x180009bea  mov     r9d, 7FFFFFFEh
0x180009bf0  test    r9, r9
0x180009bf3  jz      short loc_180009C14
0x180009bf5  movzx   r8d, word ptr [rcx]
0x180009bf9  test    r8w, r8w
0x180009bfd  jz      short loc_180009C14
0x180009bff  mov     [rax], r8w
0x180009c03  add     rcx, 2
0x180009c07  add     rax, 2
0x180009c0b  dec     r9
0x180009c0e  sub     rdx, 1
0x180009c12  jnz     short loc_180009BF0
0x180009c14  test    rdx, rdx
0x180009c17  lea     rcx, [rax-2]
0x180009c1b  lea     r8, aP0; "_p0"
0x180009c22  mov     rdx, rsi; unsigned __int64
0x180009c25  cmovnz  rcx, rax
0x180009c29  mov     [rcx], r15w
0x180009c2d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009c32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009c37  lea     r8, [rsp+280h+Name]; lpName
0x180009c3c  xor     edx, edx; bInheritHandle
0x180009c3e  mov     ecx, 1F0003h; dwDesiredAccess
0x180009c43  call    cs:__imp_OpenSemaphoreW
0x180009c49  mov     rbx, rax
0x180009c4c  test    rax, rax
0x180009c4f  jz      loc_180009D76
0x180009c55  lea     rdx, [rsp+280h+var_25C]; int *
0x180009c5a  mov     [rsp+280h+var_25C], r15d
0x180009c5f  mov     rcx, rax; hHandle
0x180009c62  mov     [rsp+280h+var_260], r15d; int
0x180009c67  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c6c  mov     edi, eax
0x180009c6e  test    eax, eax
0x180009c70  jns     short loc_180009C9E
0x180009c72  mov     rcx, [rbp+188h]; this
0x180009c79  mov     r9d, eax; char *
0x180009c7c  mov     edx, 0D6h; void *
0x180009c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c86  mov     rcx, rbx; hObject
0x180009c89  call    cs:__imp_CloseHandle
0x180009c8f  test    eax, eax
0x180009c91  jz      loc_180009DEB
0x180009c97  mov     eax, edi
0x180009c99  jmp     loc_180009D96
0x180009c9e  lea     r8, asc_180015360; "h"
0x180009ca5  mov     rdx, rsi; unsigned __int64
0x180009ca8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009cad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009cb2  lea     r8, [rsp+280h+Name]; lpName
0x180009cb7  xor     edx, edx; bInheritHandle
0x180009cb9  mov     ecx, 1F0003h; dwDesiredAccess
0x180009cbe  call    cs:__imp_OpenSemaphoreW
0x180009cc4  mov     rdi, rax
0x180009cc7  test    rax, rax
0x180009cca  jz      loc_180009D51
0x180009cd0  lea     rdx, [rsp+280h+var_260]; int *
0x180009cd5  mov     rcx, rax; hHandle
0x180009cd8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009cdd  mov     esi, eax
0x180009cdf  test    eax, eax
0x180009ce1  jns     short loc_180009D1D
0x180009ce3  mov     rcx, [rbp+188h]; this
0x180009cea  mov     r9d, eax; char *
0x180009ced  mov     edx, 0DEh; void *
0x180009cf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cf7  mov     rcx, rdi; hObject
0x180009cfa  call    cs:__imp_CloseHandle
0x180009d00  test    eax, eax
0x180009d02  jz      loc_180009DFD
0x180009d08  mov     rcx, rbx; hObject
0x180009d0b  call    cs:__imp_CloseHandle
0x180009d11  test    eax, eax
0x180009d13  jz      loc_180009E0F
0x180009d19  mov     eax, esi
0x180009d1b  jmp     short loc_180009D96
0x180009d1d  mov     rcx, rdi; hObject
0x180009d20  call    cs:__imp_CloseHandle
0x180009d26  test    eax, eax
0x180009d28  jz      loc_180009DB5
0x180009d2e  movsxd  rax, [rsp+280h+var_25C]
0x180009d33  movsxd  rcx, [rsp+280h+var_260]
0x180009d38  shl     rcx, 1Fh
0x180009d3c  or      rcx, rax
0x180009d3f  mov     [r14], rcx
0x180009d42  mov     rcx, rbx; hObject
0x180009d45  call    cs:__imp_CloseHandle
0x180009d4b  test    eax, eax
0x180009d4d  jz      short loc_180009DC7
0x180009d4f  jmp     short loc_180009D81
0x180009d51  mov     rcx, [rbp+188h]; this
0x180009d58  mov     edx, 0DCh; void *
0x180009d5d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009d62  mov     rcx, rbx; hObject
0x180009d65  mov     edi, eax
0x180009d67  call    cs:__imp_CloseHandle
0x180009d6d  test    eax, eax
0x180009d6f  jz      short loc_180009DD9
0x180009d71  jmp     loc_180009C97
0x180009d76  call    cs:__imp_GetLastError
0x180009d7c  cmp     eax, 2
0x180009d7f  jnz     short loc_180009D85
0x180009d81  xor     eax, eax
0x180009d83  jmp     short loc_180009D96
0x180009d85  mov     rcx, [rbp+188h]; this
0x180009d8c  mov     edx, 0D0h; void *
0x180009d91  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009d96  mov     rcx, [rbp+180h+var_40]
0x180009d9d  xor     rcx, rsp; StackCookie
0x180009da0  call    __security_check_cookie
0x180009da5  add     rsp, 258h
0x180009dac  pop     r15
0x180009dae  pop     r14
0x180009db0  pop     rdi
0x180009db1  pop     rsi
0x180009db2  pop     rbx
0x180009db3  pop     rbp
0x180009db4  retn
0x180009db5  mov     rcx, [rbp+188h]; this
0x180009dbc  mov     edx, 0A0Bh; void *
0x180009dc1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dc7  mov     rcx, [rbp+188h]; this
0x180009dce  mov     edx, 0A0Bh; void *
0x180009dd3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dd9  mov     rcx, [rbp+188h]; this
0x180009de0  mov     edx, 0A0Bh; void *
0x180009de5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009deb  mov     rcx, [rbp+188h]; this
0x180009df2  mov     edx, 0A0Bh; void *
0x180009df7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dfd  mov     rcx, [rbp+188h]; this
0x180009e04  mov     edx, 0A0Bh; void *
0x180009e09  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009e0f  mov     rcx, [rbp+188h]; this
0x180009e16  mov     edx, 0A0Bh; void *
0x180009e1b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
