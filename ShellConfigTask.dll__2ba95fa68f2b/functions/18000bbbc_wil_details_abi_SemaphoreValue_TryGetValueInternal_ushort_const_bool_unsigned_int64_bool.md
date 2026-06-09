# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bbbc`
- end: `0x18000be75`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005a58`
- `0x180005e38`

## callees

- `0x180002590`
- `0x180007fb8`
- `0x18000aaf4`
- `0x18000ab14`
- `0x18000b680`
- `0x18000bbbc`
- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd99`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bccc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd8a`

## string_xrefs

- `0x18000bde6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bdff`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000be18`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000be31`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000be4a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000be63`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000bbbc  push    rbp
0x18000bbbe  push    rbx
0x18000bbbf  push    rsi
0x18000bbc0  push    rdi
0x18000bbc1  push    r14
0x18000bbc3  push    r15
0x18000bbc5  lea     rbp, [rsp-158h]
0x18000bbcd  sub     rsp, 258h
0x18000bbd4  mov     rax, cs:__security_cookie
0x18000bbdb  xor     rax, rsp
0x18000bbde  mov     [rbp+180h+var_40], rax
0x18000bbe5  xor     r15d, r15d
0x18000bbe8  lea     rax, [rsp+280h+Name]
0x18000bbed  mov     [r8], r15
0x18000bbf0  mov     r14, r8
0x18000bbf3  mov     edx, 104h
0x18000bbf8  mov     r9d, 7FFFFFFEh
0x18000bbfe  test    r9, r9
0x18000bc01  jz      short loc_18000BC22
0x18000bc03  movzx   r8d, word ptr [rcx]
0x18000bc07  test    r8w, r8w
0x18000bc0b  jz      short loc_18000BC22
0x18000bc0d  mov     [rax], r8w
0x18000bc11  add     rcx, 2
0x18000bc15  add     rax, 2
0x18000bc19  dec     r9
0x18000bc1c  sub     rdx, 1; unsigned __int64
0x18000bc20  jnz     short loc_18000BBFE
0x18000bc22  test    rdx, rdx
0x18000bc25  lea     rcx, [rax-2]
0x18000bc29  lea     r8, aP0; "_p0"
0x18000bc30  cmovnz  rcx, rax
0x18000bc34  mov     [rcx], r15w
0x18000bc38  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bc3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc42  mov     esi, 1F0003h
0x18000bc47  lea     r8, [rsp+280h+Name]; lpName
0x18000bc4c  mov     ecx, esi; dwDesiredAccess
0x18000bc4e  xor     edx, edx; bInheritHandle
0x18000bc50  call    cs:__imp_OpenSemaphoreW
0x18000bc56  mov     rbx, rax
0x18000bc59  test    rax, rax
0x18000bc5c  jz      loc_18000BD99
0x18000bc62  lea     rdx, [rsp+280h+var_25C]; int *
0x18000bc67  mov     [rsp+280h+var_25C], r15d
0x18000bc6c  mov     rcx, rax; hHandle
0x18000bc6f  mov     [rsp+280h+var_260], r15d; int
0x18000bc74  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bc79  mov     edi, eax
0x18000bc7b  test    eax, eax
0x18000bc7d  jns     short loc_18000BCB2
0x18000bc7f  mov     rcx, [rbp+188h]; this
0x18000bc86  lea     r8, aWil; "wil"
0x18000bc8d  mov     r9d, eax; char *
0x18000bc90  mov     edx, 0D6h; void *
0x18000bc95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc9a  mov     rcx, rbx; hObject
0x18000bc9d  call    cs:__imp_CloseHandle
0x18000bca3  test    eax, eax
0x18000bca5  jz      loc_18000BE2A
0x18000bcab  mov     eax, edi
0x18000bcad  jmp     loc_18000BDC0
0x18000bcb2  lea     r8, asc_180035AE0; "h"
0x18000bcb9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bcbe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bcc3  lea     r8, [rsp+280h+Name]; lpName
0x18000bcc8  xor     edx, edx; bInheritHandle
0x18000bcca  mov     ecx, esi; dwDesiredAccess
0x18000bccc  call    cs:__imp_OpenSemaphoreW
0x18000bcd2  mov     rdi, rax
0x18000bcd5  test    rax, rax
0x18000bcd8  jz      loc_18000BD6D
0x18000bcde  lea     rdx, [rsp+280h+var_260]; int *
0x18000bce3  mov     rcx, rax; hHandle
0x18000bce6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bceb  mov     esi, eax
0x18000bced  test    eax, eax
0x18000bcef  jns     short loc_18000BD35
0x18000bcf1  mov     rcx, [rbp+188h]; this
0x18000bcf8  lea     r8, aWil; "wil"
0x18000bcff  mov     r9d, eax; char *
0x18000bd02  mov     edx, 0DEh; void *
0x18000bd07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bd0c  mov     rcx, rdi; hObject
0x18000bd0f  call    cs:__imp_CloseHandle
0x18000bd15  test    eax, eax
0x18000bd17  jz      loc_18000BE43
0x18000bd1d  mov     rcx, rbx; hObject
0x18000bd20  call    cs:__imp_CloseHandle
0x18000bd26  test    eax, eax
0x18000bd28  jz      loc_18000BE5C
0x18000bd2e  mov     eax, esi
0x18000bd30  jmp     loc_18000BDC0
0x18000bd35  mov     rcx, rdi; hObject
0x18000bd38  call    cs:__imp_CloseHandle
0x18000bd3e  test    eax, eax
0x18000bd40  jz      loc_18000BDDF
0x18000bd46  movsxd  rax, [rsp+280h+var_25C]
0x18000bd4b  movsxd  rcx, [rsp+280h+var_260]
0x18000bd50  shl     rcx, 1Fh
0x18000bd54  or      rcx, rax
0x18000bd57  mov     [r14], rcx
0x18000bd5a  mov     rcx, rbx; hObject
0x18000bd5d  call    cs:__imp_CloseHandle
0x18000bd63  test    eax, eax
0x18000bd65  jz      loc_18000BDF8
0x18000bd6b  jmp     short loc_18000BDA4
0x18000bd6d  mov     rcx, [rbp+188h]; this
0x18000bd74  lea     r8, aWil; "wil"
0x18000bd7b  mov     edx, 0DCh; void *
0x18000bd80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bd85  mov     rcx, rbx; hObject
0x18000bd88  mov     edi, eax
0x18000bd8a  call    cs:__imp_CloseHandle
0x18000bd90  test    eax, eax
0x18000bd92  jz      short loc_18000BE11
0x18000bd94  jmp     loc_18000BCAB
0x18000bd99  call    cs:__imp_GetLastError
0x18000bd9f  cmp     eax, 2
0x18000bda2  jnz     short loc_18000BDA8
0x18000bda4  xor     eax, eax
0x18000bda6  jmp     short loc_18000BDC0
0x18000bda8  mov     rcx, [rbp+188h]; this
0x18000bdaf  lea     r8, aWil; "wil"
0x18000bdb6  mov     edx, 0D0h; void *
0x18000bdbb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bdc0  mov     rcx, [rbp+180h+var_40]
0x18000bdc7  xor     rcx, rsp; StackCookie
0x18000bdca  call    __security_check_cookie
0x18000bdcf  add     rsp, 258h
0x18000bdd6  pop     r15
0x18000bdd8  pop     r14
0x18000bdda  pop     rdi
0x18000bddb  pop     rsi
0x18000bddc  pop     rbx
0x18000bddd  pop     rbp
0x18000bdde  retn
0x18000bddf  mov     rcx, [rbp+188h]; this
0x18000bde6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bded  mov     edx, 0A0Bh; void *
0x18000bdf2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bdf8  mov     rcx, [rbp+188h]; this
0x18000bdff  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000be06  mov     edx, 0A0Bh; void *
0x18000be0b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000be11  mov     rcx, [rbp+188h]; this
0x18000be18  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000be1f  mov     edx, 0A0Bh; void *
0x18000be24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000be2a  mov     rcx, [rbp+188h]; this
0x18000be31  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000be38  mov     edx, 0A0Bh; void *
0x18000be3d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000be43  mov     rcx, [rbp+188h]; this
0x18000be4a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000be51  mov     edx, 0A0Bh; void *
0x18000be56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000be5c  mov     rcx, [rbp+188h]; this
0x18000be63  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000be6a  mov     edx, 0A0Bh; void *
0x18000be6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
