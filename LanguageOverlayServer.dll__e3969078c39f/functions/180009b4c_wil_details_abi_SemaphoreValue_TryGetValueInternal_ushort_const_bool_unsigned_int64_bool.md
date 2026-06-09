# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009b4c`
- end: `0x180009e05`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007168`
- `0x18000cbb8`

## callees

- `0x180003a00`
- `0x1800082a8`
- `0x180009064`
- `0x180009084`
- `0x1800099c4`
- `0x180009b4c`
- `0x18000a008`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009be0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c5c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009be0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ced`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009cc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009ced`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009d1a`

## string_xrefs

- `0x180009d76`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009d8f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009da8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009dc1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009dda`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009df3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  int v27; // [rsp+20h] [rbp-E0h] BYREF
  int v28[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v26);
    return 0;
  }
  v28[0] = 0;
  v27 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v28);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v27);
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
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v27);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    *a3 = v28[0] | (unsigned __int64)((__int64)v27 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v27);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  return v20;
}

```

## disassembly

```asm
0x180009b4c  push    rbp
0x180009b4e  push    rbx
0x180009b4f  push    rsi
0x180009b50  push    rdi
0x180009b51  push    r14
0x180009b53  push    r15
0x180009b55  lea     rbp, [rsp-158h]
0x180009b5d  sub     rsp, 258h
0x180009b64  mov     rax, cs:__security_cookie
0x180009b6b  xor     rax, rsp
0x180009b6e  mov     [rbp+180h+var_40], rax
0x180009b75  xor     r15d, r15d
0x180009b78  lea     rax, [rsp+280h+Name]
0x180009b7d  mov     [r8], r15
0x180009b80  mov     r14, r8
0x180009b83  mov     edx, 104h
0x180009b88  mov     r9d, 7FFFFFFEh
0x180009b8e  test    r9, r9
0x180009b91  jz      short loc_180009BB2
0x180009b93  movzx   r8d, word ptr [rcx]
0x180009b97  test    r8w, r8w
0x180009b9b  jz      short loc_180009BB2
0x180009b9d  mov     [rax], r8w
0x180009ba1  add     rcx, 2
0x180009ba5  add     rax, 2
0x180009ba9  dec     r9
0x180009bac  sub     rdx, 1; unsigned __int64
0x180009bb0  jnz     short loc_180009B8E
0x180009bb2  test    rdx, rdx
0x180009bb5  lea     rcx, [rax-2]
0x180009bb9  lea     r8, aP0; "_p0"
0x180009bc0  cmovnz  rcx, rax
0x180009bc4  mov     [rcx], r15w
0x180009bc8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009bcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009bd2  mov     esi, 1F0003h
0x180009bd7  lea     r8, [rsp+280h+Name]; lpName
0x180009bdc  mov     ecx, esi; dwDesiredAccess
0x180009bde  xor     edx, edx; bInheritHandle
0x180009be0  call    cs:__imp_OpenSemaphoreW
0x180009be6  mov     rbx, rax
0x180009be9  test    rax, rax
0x180009bec  jz      loc_180009D29
0x180009bf2  lea     rdx, [rsp+280h+var_25C]; int *
0x180009bf7  mov     [rsp+280h+var_25C], r15d
0x180009bfc  mov     rcx, rax; hHandle
0x180009bff  mov     [rsp+280h+var_260], r15d; int
0x180009c04  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c09  mov     edi, eax
0x180009c0b  test    eax, eax
0x180009c0d  jns     short loc_180009C42
0x180009c0f  mov     rcx, [rbp+188h]; this
0x180009c16  lea     r8, aWil; "wil"
0x180009c1d  mov     r9d, eax; char *
0x180009c20  mov     edx, 0D6h; void *
0x180009c25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c2a  mov     rcx, rbx; hObject
0x180009c2d  call    cs:__imp_CloseHandle
0x180009c33  test    eax, eax
0x180009c35  jz      loc_180009DBA
0x180009c3b  mov     eax, edi
0x180009c3d  jmp     loc_180009D50
0x180009c42  lea     r8, asc_180070378; "h"
0x180009c49  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009c4e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009c53  lea     r8, [rsp+280h+Name]; lpName
0x180009c58  xor     edx, edx; bInheritHandle
0x180009c5a  mov     ecx, esi; dwDesiredAccess
0x180009c5c  call    cs:__imp_OpenSemaphoreW
0x180009c62  mov     rdi, rax
0x180009c65  test    rax, rax
0x180009c68  jz      loc_180009CFD
0x180009c6e  lea     rdx, [rsp+280h+var_260]; int *
0x180009c73  mov     rcx, rax; hHandle
0x180009c76  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c7b  mov     esi, eax
0x180009c7d  test    eax, eax
0x180009c7f  jns     short loc_180009CC5
0x180009c81  mov     rcx, [rbp+188h]; this
0x180009c88  lea     r8, aWil; "wil"
0x180009c8f  mov     r9d, eax; char *
0x180009c92  mov     edx, 0DEh; void *
0x180009c97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c9c  mov     rcx, rdi; hObject
0x180009c9f  call    cs:__imp_CloseHandle
0x180009ca5  test    eax, eax
0x180009ca7  jz      loc_180009DD3
0x180009cad  mov     rcx, rbx; hObject
0x180009cb0  call    cs:__imp_CloseHandle
0x180009cb6  test    eax, eax
0x180009cb8  jz      loc_180009DEC
0x180009cbe  mov     eax, esi
0x180009cc0  jmp     loc_180009D50
0x180009cc5  mov     rcx, rdi; hObject
0x180009cc8  call    cs:__imp_CloseHandle
0x180009cce  test    eax, eax
0x180009cd0  jz      loc_180009D6F
0x180009cd6  movsxd  rax, [rsp+280h+var_25C]
0x180009cdb  movsxd  rcx, [rsp+280h+var_260]
0x180009ce0  shl     rcx, 1Fh
0x180009ce4  or      rcx, rax
0x180009ce7  mov     [r14], rcx
0x180009cea  mov     rcx, rbx; hObject
0x180009ced  call    cs:__imp_CloseHandle
0x180009cf3  test    eax, eax
0x180009cf5  jz      loc_180009D88
0x180009cfb  jmp     short loc_180009D34
0x180009cfd  mov     rcx, [rbp+188h]; this
0x180009d04  lea     r8, aWil; "wil"
0x180009d0b  mov     edx, 0DCh; void *
0x180009d10  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009d15  mov     rcx, rbx; hObject
0x180009d18  mov     edi, eax
0x180009d1a  call    cs:__imp_CloseHandle
0x180009d20  test    eax, eax
0x180009d22  jz      short loc_180009DA1
0x180009d24  jmp     loc_180009C3B
0x180009d29  call    cs:__imp_GetLastError
0x180009d2f  cmp     eax, 2
0x180009d32  jnz     short loc_180009D38
0x180009d34  xor     eax, eax
0x180009d36  jmp     short loc_180009D50
0x180009d38  mov     rcx, [rbp+188h]; this
0x180009d3f  lea     r8, aWil; "wil"
0x180009d46  mov     edx, 0D0h; void *
0x180009d4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009d50  mov     rcx, [rbp+180h+var_40]
0x180009d57  xor     rcx, rsp; StackCookie
0x180009d5a  call    __security_check_cookie
0x180009d5f  add     rsp, 258h
0x180009d66  pop     r15
0x180009d68  pop     r14
0x180009d6a  pop     rdi
0x180009d6b  pop     rsi
0x180009d6c  pop     rbx
0x180009d6d  pop     rbp
0x180009d6e  retn
0x180009d6f  mov     rcx, [rbp+188h]; this
0x180009d76  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009d7d  mov     edx, 0A0Bh; void *
0x180009d82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009d88  mov     rcx, [rbp+188h]; this
0x180009d8f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009d96  mov     edx, 0A0Bh; void *
0x180009d9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009da1  mov     rcx, [rbp+188h]; this
0x180009da8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009daf  mov     edx, 0A0Bh; void *
0x180009db4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dba  mov     rcx, [rbp+188h]; this
0x180009dc1  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009dc8  mov     edx, 0A0Bh; void *
0x180009dcd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dd3  mov     rcx, [rbp+188h]; this
0x180009dda  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009de1  mov     edx, 0A0Bh; void *
0x180009de6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009dec  mov     rcx, [rbp+188h]; this
0x180009df3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009dfa  mov     edx, 0A0Bh; void *
0x180009dff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
