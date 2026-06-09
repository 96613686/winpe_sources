# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b81c`
- end: `0x18000bad5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006c68`
- `0x180007048`

## callees

- `0x1800033d0`
- `0x180008698`
- `0x18000a874`
- `0x18000a894`
- `0x18000b2e4`
- `0x18000b81c`
- `0x18000c268`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b8b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b92c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b8b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b92c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b8fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9ea`

## string_xrefs

- `0x18000ba46`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ba5f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ba78`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000ba91`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000baaa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bac3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000b81c  push    rbp
0x18000b81e  push    rbx
0x18000b81f  push    rsi
0x18000b820  push    rdi
0x18000b821  push    r14
0x18000b823  push    r15
0x18000b825  lea     rbp, [rsp-158h]
0x18000b82d  sub     rsp, 258h
0x18000b834  mov     rax, cs:__security_cookie
0x18000b83b  xor     rax, rsp
0x18000b83e  mov     [rbp+180h+var_40], rax
0x18000b845  xor     r15d, r15d
0x18000b848  lea     rax, [rsp+280h+Name]
0x18000b84d  mov     [r8], r15
0x18000b850  mov     r14, r8
0x18000b853  mov     edx, 104h
0x18000b858  mov     r9d, 7FFFFFFEh
0x18000b85e  test    r9, r9
0x18000b861  jz      short loc_18000B882
0x18000b863  movzx   r8d, word ptr [rcx]
0x18000b867  test    r8w, r8w
0x18000b86b  jz      short loc_18000B882
0x18000b86d  mov     [rax], r8w
0x18000b871  add     rcx, 2
0x18000b875  add     rax, 2
0x18000b879  dec     r9
0x18000b87c  sub     rdx, 1; unsigned __int64
0x18000b880  jnz     short loc_18000B85E
0x18000b882  test    rdx, rdx
0x18000b885  lea     rcx, [rax-2]
0x18000b889  lea     r8, aP0; "_p0"
0x18000b890  cmovnz  rcx, rax
0x18000b894  mov     [rcx], r15w
0x18000b898  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b89d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b8a2  mov     esi, 1F0003h
0x18000b8a7  lea     r8, [rsp+280h+Name]; lpName
0x18000b8ac  mov     ecx, esi; dwDesiredAccess
0x18000b8ae  xor     edx, edx; bInheritHandle
0x18000b8b0  call    cs:__imp_OpenSemaphoreW
0x18000b8b6  mov     rbx, rax
0x18000b8b9  test    rax, rax
0x18000b8bc  jz      loc_18000B9F9
0x18000b8c2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b8c7  mov     [rsp+280h+var_25C], r15d
0x18000b8cc  mov     rcx, rax; hHandle
0x18000b8cf  mov     [rsp+280h+var_260], r15d; int
0x18000b8d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b8d9  mov     edi, eax
0x18000b8db  test    eax, eax
0x18000b8dd  jns     short loc_18000B912
0x18000b8df  mov     rcx, [rbp+188h]; this
0x18000b8e6  lea     r8, aWil; "wil"
0x18000b8ed  mov     r9d, eax; char *
0x18000b8f0  mov     edx, 0D6h; void *
0x18000b8f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b8fa  mov     rcx, rbx; hObject
0x18000b8fd  call    cs:__imp_CloseHandle
0x18000b903  test    eax, eax
0x18000b905  jz      loc_18000BA8A
0x18000b90b  mov     eax, edi
0x18000b90d  jmp     loc_18000BA20
0x18000b912  lea     r8, asc_18012C4E0; "h"
0x18000b919  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000b91e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b923  lea     r8, [rsp+280h+Name]; lpName
0x18000b928  xor     edx, edx; bInheritHandle
0x18000b92a  mov     ecx, esi; dwDesiredAccess
0x18000b92c  call    cs:__imp_OpenSemaphoreW
0x18000b932  mov     rdi, rax
0x18000b935  test    rax, rax
0x18000b938  jz      loc_18000B9CD
0x18000b93e  lea     rdx, [rsp+280h+var_260]; int *
0x18000b943  mov     rcx, rax; hHandle
0x18000b946  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b94b  mov     esi, eax
0x18000b94d  test    eax, eax
0x18000b94f  jns     short loc_18000B995
0x18000b951  mov     rcx, [rbp+188h]; this
0x18000b958  lea     r8, aWil; "wil"
0x18000b95f  mov     r9d, eax; char *
0x18000b962  mov     edx, 0DEh; void *
0x18000b967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b96c  mov     rcx, rdi; hObject
0x18000b96f  call    cs:__imp_CloseHandle
0x18000b975  test    eax, eax
0x18000b977  jz      loc_18000BAA3
0x18000b97d  mov     rcx, rbx; hObject
0x18000b980  call    cs:__imp_CloseHandle
0x18000b986  test    eax, eax
0x18000b988  jz      loc_18000BABC
0x18000b98e  mov     eax, esi
0x18000b990  jmp     loc_18000BA20
0x18000b995  mov     rcx, rdi; hObject
0x18000b998  call    cs:__imp_CloseHandle
0x18000b99e  test    eax, eax
0x18000b9a0  jz      loc_18000BA3F
0x18000b9a6  movsxd  rax, [rsp+280h+var_25C]
0x18000b9ab  movsxd  rcx, [rsp+280h+var_260]
0x18000b9b0  shl     rcx, 1Fh
0x18000b9b4  or      rcx, rax
0x18000b9b7  mov     [r14], rcx
0x18000b9ba  mov     rcx, rbx; hObject
0x18000b9bd  call    cs:__imp_CloseHandle
0x18000b9c3  test    eax, eax
0x18000b9c5  jz      loc_18000BA58
0x18000b9cb  jmp     short loc_18000BA04
0x18000b9cd  mov     rcx, [rbp+188h]; this
0x18000b9d4  lea     r8, aWil; "wil"
0x18000b9db  mov     edx, 0DCh; void *
0x18000b9e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b9e5  mov     rcx, rbx; hObject
0x18000b9e8  mov     edi, eax
0x18000b9ea  call    cs:__imp_CloseHandle
0x18000b9f0  test    eax, eax
0x18000b9f2  jz      short loc_18000BA71
0x18000b9f4  jmp     loc_18000B90B
0x18000b9f9  call    cs:__imp_GetLastError
0x18000b9ff  cmp     eax, 2
0x18000ba02  jnz     short loc_18000BA08
0x18000ba04  xor     eax, eax
0x18000ba06  jmp     short loc_18000BA20
0x18000ba08  mov     rcx, [rbp+188h]; this
0x18000ba0f  lea     r8, aWil; "wil"
0x18000ba16  mov     edx, 0D0h; void *
0x18000ba1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ba20  mov     rcx, [rbp+180h+var_40]
0x18000ba27  xor     rcx, rsp; StackCookie
0x18000ba2a  call    __security_check_cookie
0x18000ba2f  add     rsp, 258h
0x18000ba36  pop     r15
0x18000ba38  pop     r14
0x18000ba3a  pop     rdi
0x18000ba3b  pop     rsi
0x18000ba3c  pop     rbx
0x18000ba3d  pop     rbp
0x18000ba3e  retn
0x18000ba3f  mov     rcx, [rbp+188h]; this
0x18000ba46  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ba4d  mov     edx, 0A0Bh; void *
0x18000ba52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba58  mov     rcx, [rbp+188h]; this
0x18000ba5f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ba66  mov     edx, 0A0Bh; void *
0x18000ba6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba71  mov     rcx, [rbp+188h]; this
0x18000ba78  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ba7f  mov     edx, 0A0Bh; void *
0x18000ba84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000ba8a  mov     rcx, [rbp+188h]; this
0x18000ba91  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ba98  mov     edx, 0A0Bh; void *
0x18000ba9d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000baa3  mov     rcx, [rbp+188h]; this
0x18000baaa  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bab1  mov     edx, 0A0Bh; void *
0x18000bab6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000babc  mov     rcx, [rbp+188h]; this
0x18000bac3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000baca  mov     edx, 0A0Bh; void *
0x18000bacf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
