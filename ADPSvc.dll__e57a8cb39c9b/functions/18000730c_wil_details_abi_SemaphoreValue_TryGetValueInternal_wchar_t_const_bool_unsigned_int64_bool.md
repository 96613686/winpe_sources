# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000730c`
- end: `0x1800075c5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004ba8`
- `0x180008b94`

## callees

- `0x180002250`
- `0x180005c14`
- `0x180006824`
- `0x180006844`
- `0x180007184`
- `0x18000730c`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000741c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800073a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000741c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000745f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000745f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007470`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800074da`

## string_xrefs

- `0x180007536`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000754f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007568`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007581`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000759a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800075b3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000730c  push    rbp
0x18000730e  push    rbx
0x18000730f  push    rsi
0x180007310  push    rdi
0x180007311  push    r14
0x180007313  push    r15
0x180007315  lea     rbp, [rsp-158h]
0x18000731d  sub     rsp, 258h
0x180007324  mov     rax, cs:__security_cookie
0x18000732b  xor     rax, rsp
0x18000732e  mov     [rbp+180h+var_40], rax
0x180007335  xor     r15d, r15d
0x180007338  lea     rax, [rsp+280h+Name]
0x18000733d  mov     [r8], r15
0x180007340  mov     r14, r8
0x180007343  mov     edx, 104h
0x180007348  mov     r9d, 7FFFFFFEh
0x18000734e  test    r9, r9
0x180007351  jz      short loc_180007372
0x180007353  movzx   r8d, word ptr [rcx]
0x180007357  test    r8w, r8w
0x18000735b  jz      short loc_180007372
0x18000735d  mov     [rax], r8w
0x180007361  add     rcx, 2
0x180007365  add     rax, 2
0x180007369  dec     r9
0x18000736c  sub     rdx, 1; unsigned __int64
0x180007370  jnz     short loc_18000734E
0x180007372  test    rdx, rdx
0x180007375  lea     rcx, [rax-2]
0x180007379  lea     r8, aP0; "_p0"
0x180007380  cmovnz  rcx, rax
0x180007384  mov     [rcx], r15w
0x180007388  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000738d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007392  mov     esi, 1F0003h
0x180007397  lea     r8, [rsp+280h+Name]; lpName
0x18000739c  mov     ecx, esi; dwDesiredAccess
0x18000739e  xor     edx, edx; bInheritHandle
0x1800073a0  call    cs:__imp_OpenSemaphoreW
0x1800073a6  mov     rbx, rax
0x1800073a9  test    rax, rax
0x1800073ac  jz      loc_1800074E9
0x1800073b2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800073b7  mov     [rsp+280h+var_25C], r15d
0x1800073bc  mov     rcx, rax; hHandle
0x1800073bf  mov     [rsp+280h+var_260], r15d; int
0x1800073c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800073c9  mov     edi, eax
0x1800073cb  test    eax, eax
0x1800073cd  jns     short loc_180007402
0x1800073cf  mov     rcx, [rbp+188h]; this
0x1800073d6  lea     r8, aWil; "wil"
0x1800073dd  mov     r9d, eax; char *
0x1800073e0  mov     edx, 0D6h; void *
0x1800073e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800073ea  mov     rcx, rbx; hObject
0x1800073ed  call    cs:__imp_CloseHandle
0x1800073f3  test    eax, eax
0x1800073f5  jz      loc_18000757A
0x1800073fb  mov     eax, edi
0x1800073fd  jmp     loc_180007510
0x180007402  lea     r8, asc_1800ED060; "h"
0x180007409  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000740e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007413  lea     r8, [rsp+280h+Name]; lpName
0x180007418  xor     edx, edx; bInheritHandle
0x18000741a  mov     ecx, esi; dwDesiredAccess
0x18000741c  call    cs:__imp_OpenSemaphoreW
0x180007422  mov     rdi, rax
0x180007425  test    rax, rax
0x180007428  jz      loc_1800074BD
0x18000742e  lea     rdx, [rsp+280h+var_260]; int *
0x180007433  mov     rcx, rax; hHandle
0x180007436  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000743b  mov     esi, eax
0x18000743d  test    eax, eax
0x18000743f  jns     short loc_180007485
0x180007441  mov     rcx, [rbp+188h]; this
0x180007448  lea     r8, aWil; "wil"
0x18000744f  mov     r9d, eax; char *
0x180007452  mov     edx, 0DEh; void *
0x180007457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000745c  mov     rcx, rdi; hObject
0x18000745f  call    cs:__imp_CloseHandle
0x180007465  test    eax, eax
0x180007467  jz      loc_180007593
0x18000746d  mov     rcx, rbx; hObject
0x180007470  call    cs:__imp_CloseHandle
0x180007476  test    eax, eax
0x180007478  jz      loc_1800075AC
0x18000747e  mov     eax, esi
0x180007480  jmp     loc_180007510
0x180007485  mov     rcx, rdi; hObject
0x180007488  call    cs:__imp_CloseHandle
0x18000748e  test    eax, eax
0x180007490  jz      loc_18000752F
0x180007496  movsxd  rax, [rsp+280h+var_25C]
0x18000749b  movsxd  rcx, [rsp+280h+var_260]
0x1800074a0  shl     rcx, 1Fh
0x1800074a4  or      rcx, rax
0x1800074a7  mov     [r14], rcx
0x1800074aa  mov     rcx, rbx; hObject
0x1800074ad  call    cs:__imp_CloseHandle
0x1800074b3  test    eax, eax
0x1800074b5  jz      loc_180007548
0x1800074bb  jmp     short loc_1800074F4
0x1800074bd  mov     rcx, [rbp+188h]; this
0x1800074c4  lea     r8, aWil; "wil"
0x1800074cb  mov     edx, 0DCh; void *
0x1800074d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800074d5  mov     rcx, rbx; hObject
0x1800074d8  mov     edi, eax
0x1800074da  call    cs:__imp_CloseHandle
0x1800074e0  test    eax, eax
0x1800074e2  jz      short loc_180007561
0x1800074e4  jmp     loc_1800073FB
0x1800074e9  call    cs:__imp_GetLastError
0x1800074ef  cmp     eax, 2
0x1800074f2  jnz     short loc_1800074F8
0x1800074f4  xor     eax, eax
0x1800074f6  jmp     short loc_180007510
0x1800074f8  mov     rcx, [rbp+188h]; this
0x1800074ff  lea     r8, aWil; "wil"
0x180007506  mov     edx, 0D0h; void *
0x18000750b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007510  mov     rcx, [rbp+180h+var_40]
0x180007517  xor     rcx, rsp; StackCookie
0x18000751a  call    __security_check_cookie
0x18000751f  add     rsp, 258h
0x180007526  pop     r15
0x180007528  pop     r14
0x18000752a  pop     rdi
0x18000752b  pop     rsi
0x18000752c  pop     rbx
0x18000752d  pop     rbp
0x18000752e  retn
0x18000752f  mov     rcx, [rbp+188h]; this
0x180007536  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000753d  mov     edx, 0A0Bh; void *
0x180007542  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007548  mov     rcx, [rbp+188h]; this
0x18000754f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007556  mov     edx, 0A0Bh; void *
0x18000755b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007561  mov     rcx, [rbp+188h]; this
0x180007568  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000756f  mov     edx, 0A0Bh; void *
0x180007574  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000757a  mov     rcx, [rbp+188h]; this
0x180007581  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007588  mov     edx, 0A0Bh; void *
0x18000758d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007593  mov     rcx, [rbp+188h]; this
0x18000759a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800075a1  mov     edx, 0A0Bh; void *
0x1800075a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800075ac  mov     rcx, [rbp+188h]; this
0x1800075b3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800075ba  mov     edx, 0A0Bh; void *
0x1800075bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
