# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006b70`
- end: `0x180006e29`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003fd0`

## callees

- `0x180001550`
- `0x180005224`
- `0x1800066c4`
- `0x1800066e4`
- `0x180006a34`
- `0x180006b70`
- `0x18000700c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006c04`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006c80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006c04`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006c51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006cec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d3e`

## string_xrefs

- `0x180006d9a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006db3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006dcc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006de5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006dfe`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006e17`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180006b70  push    rbp
0x180006b72  push    rbx
0x180006b73  push    rsi
0x180006b74  push    rdi
0x180006b75  push    r14
0x180006b77  push    r15
0x180006b79  lea     rbp, [rsp-158h]
0x180006b81  sub     rsp, 258h
0x180006b88  mov     rax, cs:__security_cookie
0x180006b8f  xor     rax, rsp
0x180006b92  mov     [rbp+180h+var_40], rax
0x180006b99  xor     r15d, r15d
0x180006b9c  lea     rax, [rsp+280h+Name]
0x180006ba1  mov     [r8], r15
0x180006ba4  mov     r14, r8
0x180006ba7  mov     edx, 104h
0x180006bac  mov     r9d, 7FFFFFFEh
0x180006bb2  test    r9, r9
0x180006bb5  jz      short loc_180006BD6
0x180006bb7  movzx   r8d, word ptr [rcx]
0x180006bbb  test    r8w, r8w
0x180006bbf  jz      short loc_180006BD6
0x180006bc1  mov     [rax], r8w
0x180006bc5  add     rcx, 2
0x180006bc9  add     rax, 2
0x180006bcd  dec     r9
0x180006bd0  sub     rdx, 1; unsigned __int64
0x180006bd4  jnz     short loc_180006BB2
0x180006bd6  test    rdx, rdx
0x180006bd9  lea     rcx, [rax-2]
0x180006bdd  lea     r8, aP0; "_p0"
0x180006be4  cmovnz  rcx, rax
0x180006be8  mov     [rcx], r15w
0x180006bec  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006bf1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006bf6  mov     esi, 1F0003h
0x180006bfb  lea     r8, [rsp+280h+Name]; lpName
0x180006c00  mov     ecx, esi; dwDesiredAccess
0x180006c02  xor     edx, edx; bInheritHandle
0x180006c04  call    cs:__imp_OpenSemaphoreW
0x180006c0a  mov     rbx, rax
0x180006c0d  test    rax, rax
0x180006c10  jz      loc_180006D4D
0x180006c16  lea     rdx, [rsp+280h+var_25C]; int *
0x180006c1b  mov     [rsp+280h+var_25C], r15d
0x180006c20  mov     rcx, rax; hHandle
0x180006c23  mov     [rsp+280h+var_260], r15d; int
0x180006c28  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006c2d  mov     edi, eax
0x180006c2f  test    eax, eax
0x180006c31  jns     short loc_180006C66
0x180006c33  mov     rcx, [rbp+188h]; this
0x180006c3a  lea     r8, aWil; "wil"
0x180006c41  mov     r9d, eax; char *
0x180006c44  mov     edx, 0D6h; void *
0x180006c49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c4e  mov     rcx, rbx; hObject
0x180006c51  call    cs:__imp_CloseHandle
0x180006c57  test    eax, eax
0x180006c59  jz      loc_180006DDE
0x180006c5f  mov     eax, edi
0x180006c61  jmp     loc_180006D74
0x180006c66  lea     r8, asc_180014CA8; "h"
0x180006c6d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006c72  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006c77  lea     r8, [rsp+280h+Name]; lpName
0x180006c7c  xor     edx, edx; bInheritHandle
0x180006c7e  mov     ecx, esi; dwDesiredAccess
0x180006c80  call    cs:__imp_OpenSemaphoreW
0x180006c86  mov     rdi, rax
0x180006c89  test    rax, rax
0x180006c8c  jz      loc_180006D21
0x180006c92  lea     rdx, [rsp+280h+var_260]; int *
0x180006c97  mov     rcx, rax; hHandle
0x180006c9a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006c9f  mov     esi, eax
0x180006ca1  test    eax, eax
0x180006ca3  jns     short loc_180006CE9
0x180006ca5  mov     rcx, [rbp+188h]; this
0x180006cac  lea     r8, aWil; "wil"
0x180006cb3  mov     r9d, eax; char *
0x180006cb6  mov     edx, 0DEh; void *
0x180006cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006cc0  mov     rcx, rdi; hObject
0x180006cc3  call    cs:__imp_CloseHandle
0x180006cc9  test    eax, eax
0x180006ccb  jz      loc_180006DF7
0x180006cd1  mov     rcx, rbx; hObject
0x180006cd4  call    cs:__imp_CloseHandle
0x180006cda  test    eax, eax
0x180006cdc  jz      loc_180006E10
0x180006ce2  mov     eax, esi
0x180006ce4  jmp     loc_180006D74
0x180006ce9  mov     rcx, rdi; hObject
0x180006cec  call    cs:__imp_CloseHandle
0x180006cf2  test    eax, eax
0x180006cf4  jz      loc_180006D93
0x180006cfa  movsxd  rax, [rsp+280h+var_25C]
0x180006cff  movsxd  rcx, [rsp+280h+var_260]
0x180006d04  shl     rcx, 1Fh
0x180006d08  or      rcx, rax
0x180006d0b  mov     [r14], rcx
0x180006d0e  mov     rcx, rbx; hObject
0x180006d11  call    cs:__imp_CloseHandle
0x180006d17  test    eax, eax
0x180006d19  jz      loc_180006DAC
0x180006d1f  jmp     short loc_180006D58
0x180006d21  mov     rcx, [rbp+188h]; this
0x180006d28  lea     r8, aWil; "wil"
0x180006d2f  mov     edx, 0DCh; void *
0x180006d34  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006d39  mov     rcx, rbx; hObject
0x180006d3c  mov     edi, eax
0x180006d3e  call    cs:__imp_CloseHandle
0x180006d44  test    eax, eax
0x180006d46  jz      short loc_180006DC5
0x180006d48  jmp     loc_180006C5F
0x180006d4d  call    cs:__imp_GetLastError
0x180006d53  cmp     eax, 2
0x180006d56  jnz     short loc_180006D5C
0x180006d58  xor     eax, eax
0x180006d5a  jmp     short loc_180006D74
0x180006d5c  mov     rcx, [rbp+188h]; this
0x180006d63  lea     r8, aWil; "wil"
0x180006d6a  mov     edx, 0D0h; void *
0x180006d6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006d74  mov     rcx, [rbp+180h+var_40]
0x180006d7b  xor     rcx, rsp; StackCookie
0x180006d7e  call    __security_check_cookie
0x180006d83  add     rsp, 258h
0x180006d8a  pop     r15
0x180006d8c  pop     r14
0x180006d8e  pop     rdi
0x180006d8f  pop     rsi
0x180006d90  pop     rbx
0x180006d91  pop     rbp
0x180006d92  retn
0x180006d93  mov     rcx, [rbp+188h]; this
0x180006d9a  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006da1  mov     edx, 0A0Bh; void *
0x180006da6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006dac  mov     rcx, [rbp+188h]; this
0x180006db3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006dba  mov     edx, 0A0Bh; void *
0x180006dbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006dc5  mov     rcx, [rbp+188h]; this
0x180006dcc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006dd3  mov     edx, 0A0Bh; void *
0x180006dd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006dde  mov     rcx, [rbp+188h]; this
0x180006de5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006dec  mov     edx, 0A0Bh; void *
0x180006df1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006df7  mov     rcx, [rbp+188h]; this
0x180006dfe  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006e05  mov     edx, 0A0Bh; void *
0x180006e0a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e10  mov     rcx, [rbp+188h]; this
0x180006e17  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006e1e  mov     edx, 0A0Bh; void *
0x180006e23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
