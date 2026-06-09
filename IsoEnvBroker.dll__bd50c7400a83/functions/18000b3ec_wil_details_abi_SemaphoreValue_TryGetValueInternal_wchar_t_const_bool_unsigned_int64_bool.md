# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b3ec`
- end: `0x18000b6a5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800068a8`
- `0x180006c88`

## callees

- `0x180002520`
- `0x1800082d8`
- `0x18000a444`
- `0x18000a464`
- `0x18000aeb4`
- `0x18000b3ec`
- `0x18000bd98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b480`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b4fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b480`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b4fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b568`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b53f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b568`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b5ba`

## string_xrefs

- `0x18000b616`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b62f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b648`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b661`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b67a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b693`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v23);
    *a3 = v28[0] | (unsigned __int64)((__int64)v27 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v24);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v27);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v21);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v22);
  return v20;
}

```

## disassembly

```asm
0x18000b3ec  push    rbp
0x18000b3ee  push    rbx
0x18000b3ef  push    rsi
0x18000b3f0  push    rdi
0x18000b3f1  push    r14
0x18000b3f3  push    r15
0x18000b3f5  lea     rbp, [rsp-158h]
0x18000b3fd  sub     rsp, 258h
0x18000b404  mov     rax, cs:__security_cookie
0x18000b40b  xor     rax, rsp
0x18000b40e  mov     [rbp+180h+var_40], rax
0x18000b415  xor     r15d, r15d
0x18000b418  lea     rax, [rsp+280h+Name]
0x18000b41d  mov     [r8], r15
0x18000b420  mov     r14, r8
0x18000b423  mov     edx, 104h
0x18000b428  mov     r9d, 7FFFFFFEh
0x18000b42e  test    r9, r9
0x18000b431  jz      short loc_18000B452
0x18000b433  movzx   r8d, word ptr [rcx]
0x18000b437  test    r8w, r8w
0x18000b43b  jz      short loc_18000B452
0x18000b43d  mov     [rax], r8w
0x18000b441  add     rcx, 2
0x18000b445  add     rax, 2
0x18000b449  dec     r9
0x18000b44c  sub     rdx, 1; unsigned __int64
0x18000b450  jnz     short loc_18000B42E
0x18000b452  test    rdx, rdx
0x18000b455  lea     rcx, [rax-2]
0x18000b459  lea     r8, aP0; "_p0"
0x18000b460  cmovnz  rcx, rax
0x18000b464  mov     [rcx], r15w
0x18000b468  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b46d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b472  mov     esi, 1F0003h
0x18000b477  lea     r8, [rsp+280h+Name]; lpName
0x18000b47c  mov     ecx, esi; dwDesiredAccess
0x18000b47e  xor     edx, edx; bInheritHandle
0x18000b480  call    cs:__imp_OpenSemaphoreW
0x18000b486  mov     rbx, rax
0x18000b489  test    rax, rax
0x18000b48c  jz      loc_18000B5C9
0x18000b492  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b497  mov     [rsp+280h+var_25C], r15d
0x18000b49c  mov     rcx, rax; hHandle
0x18000b49f  mov     [rsp+280h+var_260], r15d; int
0x18000b4a4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b4a9  mov     edi, eax
0x18000b4ab  test    eax, eax
0x18000b4ad  jns     short loc_18000B4E2
0x18000b4af  mov     rcx, [rbp+188h]; this
0x18000b4b6  lea     r8, aWil; "wil"
0x18000b4bd  mov     r9d, eax; char *
0x18000b4c0  mov     edx, 0D6h; void *
0x18000b4c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4ca  mov     rcx, rbx; hObject
0x18000b4cd  call    cs:__imp_CloseHandle
0x18000b4d3  test    eax, eax
0x18000b4d5  jz      loc_18000B65A
0x18000b4db  mov     eax, edi
0x18000b4dd  jmp     loc_18000B5F0
0x18000b4e2  lea     r8, asc_180095A60; "h"
0x18000b4e9  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b4ee  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b4f3  lea     r8, [rsp+280h+Name]; lpName
0x18000b4f8  xor     edx, edx; bInheritHandle
0x18000b4fa  mov     ecx, esi; dwDesiredAccess
0x18000b4fc  call    cs:__imp_OpenSemaphoreW
0x18000b502  mov     rdi, rax
0x18000b505  test    rax, rax
0x18000b508  jz      loc_18000B59D
0x18000b50e  lea     rdx, [rsp+280h+var_260]; int *
0x18000b513  mov     rcx, rax; hHandle
0x18000b516  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b51b  mov     esi, eax
0x18000b51d  test    eax, eax
0x18000b51f  jns     short loc_18000B565
0x18000b521  mov     rcx, [rbp+188h]; this
0x18000b528  lea     r8, aWil; "wil"
0x18000b52f  mov     r9d, eax; char *
0x18000b532  mov     edx, 0DEh; void *
0x18000b537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b53c  mov     rcx, rdi; hObject
0x18000b53f  call    cs:__imp_CloseHandle
0x18000b545  test    eax, eax
0x18000b547  jz      loc_18000B673
0x18000b54d  mov     rcx, rbx; hObject
0x18000b550  call    cs:__imp_CloseHandle
0x18000b556  test    eax, eax
0x18000b558  jz      loc_18000B68C
0x18000b55e  mov     eax, esi
0x18000b560  jmp     loc_18000B5F0
0x18000b565  mov     rcx, rdi; hObject
0x18000b568  call    cs:__imp_CloseHandle
0x18000b56e  test    eax, eax
0x18000b570  jz      loc_18000B60F
0x18000b576  movsxd  rax, [rsp+280h+var_25C]
0x18000b57b  movsxd  rcx, [rsp+280h+var_260]
0x18000b580  shl     rcx, 1Fh
0x18000b584  or      rcx, rax
0x18000b587  mov     [r14], rcx
0x18000b58a  mov     rcx, rbx; hObject
0x18000b58d  call    cs:__imp_CloseHandle
0x18000b593  test    eax, eax
0x18000b595  jz      loc_18000B628
0x18000b59b  jmp     short loc_18000B5D4
0x18000b59d  mov     rcx, [rbp+188h]; this
0x18000b5a4  lea     r8, aWil; "wil"
0x18000b5ab  mov     edx, 0DCh; void *
0x18000b5b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b5b5  mov     rcx, rbx; hObject
0x18000b5b8  mov     edi, eax
0x18000b5ba  call    cs:__imp_CloseHandle
0x18000b5c0  test    eax, eax
0x18000b5c2  jz      short loc_18000B641
0x18000b5c4  jmp     loc_18000B4DB
0x18000b5c9  call    cs:__imp_GetLastError
0x18000b5cf  cmp     eax, 2
0x18000b5d2  jnz     short loc_18000B5D8
0x18000b5d4  xor     eax, eax
0x18000b5d6  jmp     short loc_18000B5F0
0x18000b5d8  mov     rcx, [rbp+188h]; this
0x18000b5df  lea     r8, aWil; "wil"
0x18000b5e6  mov     edx, 0D0h; void *
0x18000b5eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b5f0  mov     rcx, [rbp+180h+var_40]
0x18000b5f7  xor     rcx, rsp; StackCookie
0x18000b5fa  call    __security_check_cookie
0x18000b5ff  add     rsp, 258h
0x18000b606  pop     r15
0x18000b608  pop     r14
0x18000b60a  pop     rdi
0x18000b60b  pop     rsi
0x18000b60c  pop     rbx
0x18000b60d  pop     rbp
0x18000b60e  retn
0x18000b60f  mov     rcx, [rbp+188h]; this
0x18000b616  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b61d  mov     edx, 0A0Bh; void *
0x18000b622  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b628  mov     rcx, [rbp+188h]; this
0x18000b62f  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b636  mov     edx, 0A0Bh; void *
0x18000b63b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b641  mov     rcx, [rbp+188h]; this
0x18000b648  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b64f  mov     edx, 0A0Bh; void *
0x18000b654  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b65a  mov     rcx, [rbp+188h]; this
0x18000b661  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b668  mov     edx, 0A0Bh; void *
0x18000b66d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b673  mov     rcx, [rbp+188h]; this
0x18000b67a  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b681  mov     edx, 0A0Bh; void *
0x18000b686  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b68c  mov     rcx, [rbp+188h]; this
0x18000b693  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b69a  mov     edx, 0A0Bh; void *
0x18000b69f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
