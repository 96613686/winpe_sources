# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009bac`
- end: `0x180009e50`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `676`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004e58`
- `0x18000522c`

## callees

- `0x180002350`
- `0x180006954`
- `0x180008c04`
- `0x180008c24`
- `0x180009668`
- `0x180009bac`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009cbc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d6c`

## string_xrefs

- `0x180009dc1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009dda`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009df3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009e0c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009e25`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009e3e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v14; // r9
  HANDLE v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  int v29; // [rsp+20h] [rbp-E0h] BYREF
  int v30[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v27, v28);
    return 0;
  }
  v30[0] = 0;
  v29 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v30);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v29);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v14);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v26);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v29);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    *a3 = v30[0] | (unsigned __int64)((__int64)v29 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v29);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v23);
  return v21;
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
0x180009bdd  mov     [r8], r15
0x180009be0  mov     r14, r8
0x180009be3  mov     edx, 104h
0x180009be8  mov     r9d, 7FFFFFFEh
0x180009bee  test    r9, r9
0x180009bf1  jz      short loc_180009C12
0x180009bf3  movzx   r8d, word ptr [rcx]
0x180009bf7  test    r8w, r8w
0x180009bfb  jz      short loc_180009C12
0x180009bfd  mov     [rax], r8w
0x180009c01  add     rcx, 2
0x180009c05  add     rax, 2
0x180009c09  dec     r9
0x180009c0c  sub     rdx, 1; unsigned __int64
0x180009c10  jnz     short loc_180009BEE
0x180009c12  test    rdx, rdx
0x180009c15  lea     rcx, [rax-2]
0x180009c19  lea     r8, aP0; "_p0"
0x180009c20  cmovnz  rcx, rax
0x180009c24  mov     [rcx], r15w
0x180009c28  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009c2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009c32  mov     esi, 1F0003h
0x180009c37  lea     r8, [rsp+280h+Name]; lpName
0x180009c3c  mov     ecx, esi; dwDesiredAccess
0x180009c3e  xor     edx, edx; bInheritHandle
0x180009c40  call    cs:__imp_OpenSemaphoreW
0x180009c46  mov     rbx, rax
0x180009c49  test    rax, rax
0x180009c4c  jz      loc_180009D7B
0x180009c52  lea     rdx, [rsp+280h+var_25C]; int *
0x180009c57  mov     [rsp+280h+var_25C], r15d
0x180009c5c  mov     rcx, rax; hHandle
0x180009c5f  mov     [rsp+280h+var_260], r15d; int
0x180009c64  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c69  mov     edi, eax
0x180009c6b  test    eax, eax
0x180009c6d  jns     short loc_180009CA2
0x180009c6f  mov     rcx, [rbp+188h]; this
0x180009c76  lea     r8, aWil; "wil"
0x180009c7d  mov     r9d, eax; char *
0x180009c80  mov     edx, 0D6h; void *
0x180009c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c8a  mov     rcx, rbx; hObject
0x180009c8d  call    cs:__imp_CloseHandle
0x180009c93  test    eax, eax
0x180009c95  jz      loc_180009E05
0x180009c9b  mov     eax, edi
0x180009c9d  jmp     loc_180009D9B
0x180009ca2  lea     r8, asc_180032668; "h"
0x180009ca9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009cae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009cb3  lea     r8, [rsp+280h+Name]; lpName
0x180009cb8  xor     edx, edx; bInheritHandle
0x180009cba  mov     ecx, esi; dwDesiredAccess
0x180009cbc  call    cs:__imp_OpenSemaphoreW
0x180009cc2  mov     rdi, rax
0x180009cc5  test    rax, rax
0x180009cc8  jz      loc_180009D56
0x180009cce  lea     rdx, [rsp+280h+var_260]; int *
0x180009cd3  mov     rcx, rax; hHandle
0x180009cd6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009cdb  mov     esi, eax
0x180009cdd  test    eax, eax
0x180009cdf  jns     short loc_180009D22
0x180009ce1  mov     rcx, [rbp+188h]; this
0x180009ce8  lea     r8, aWil; "wil"
0x180009cef  mov     r9d, eax; char *
0x180009cf2  mov     edx, 0DEh; void *
0x180009cf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cfc  mov     rcx, rdi; hObject
0x180009cff  call    cs:__imp_CloseHandle
0x180009d05  test    eax, eax
0x180009d07  jz      loc_180009E1E
0x180009d0d  mov     rcx, rbx; hObject
0x180009d10  call    cs:__imp_CloseHandle
0x180009d16  test    eax, eax
0x180009d18  jz      loc_180009E37
0x180009d1e  mov     eax, esi
0x180009d20  jmp     short loc_180009D9B
0x180009d22  mov     rcx, rdi; hObject
0x180009d25  call    cs:__imp_CloseHandle
0x180009d2b  test    eax, eax
0x180009d2d  jz      loc_180009DBA
0x180009d33  movsxd  rax, [rsp+280h+var_25C]
0x180009d38  movsxd  rcx, [rsp+280h+var_260]
0x180009d3d  shl     rcx, 1Fh
0x180009d41  or      rcx, rax
0x180009d44  mov     [r14], rcx
0x180009d47  mov     rcx, rbx; hObject
0x180009d4a  call    cs:__imp_CloseHandle
0x180009d50  test    eax, eax
0x180009d52  jz      short loc_180009DD3
0x180009d54  jmp     short loc_180009D86
0x180009d56  mov     rcx, [rbp+188h]; this
0x180009d5d  mov     edx, 0DCh; void *
0x180009d62  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009d67  mov     rcx, rbx; hObject
0x180009d6a  mov     edi, eax
0x180009d6c  call    cs:__imp_CloseHandle
0x180009d72  test    eax, eax
0x180009d74  jz      short loc_180009DEC
0x180009d76  jmp     loc_180009C9B
0x180009d7b  call    cs:__imp_GetLastError
0x180009d81  cmp     eax, 2
0x180009d84  jnz     short loc_180009D8A
0x180009d86  xor     eax, eax
0x180009d88  jmp     short loc_180009D9B
0x180009d8a  mov     rcx, [rbp+188h]; this
0x180009d91  mov     edx, 0D0h; void *
0x180009d96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009d9b  mov     rcx, [rbp+180h+var_40]
0x180009da2  xor     rcx, rsp; StackCookie
0x180009da5  call    __security_check_cookie
0x180009daa  add     rsp, 258h
0x180009db1  pop     r15
0x180009db3  pop     r14
0x180009db5  pop     rdi
0x180009db6  pop     rsi
0x180009db7  pop     rbx
0x180009db8  pop     rbp
0x180009db9  retn
0x180009dba  mov     rcx, [rbp+188h]; this
0x180009dc1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009dc8  mov     edx, 0A0Bh; void *
0x180009dcd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dd3  mov     rcx, [rbp+188h]; this
0x180009dda  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009de1  mov     edx, 0A0Bh; void *
0x180009de6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dec  mov     rcx, [rbp+188h]; this
0x180009df3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009dfa  mov     edx, 0A0Bh; void *
0x180009dff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009e05  mov     rcx, [rbp+188h]; this
0x180009e0c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009e13  mov     edx, 0A0Bh; void *
0x180009e18  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009e1e  mov     rcx, [rbp+188h]; this
0x180009e25  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009e2c  mov     edx, 0A0Bh; void *
0x180009e31  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009e37  mov     rcx, [rbp+188h]; this
0x180009e3e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009e45  mov     edx, 0A0Bh; void *
0x180009e4a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
