# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001178c`
- end: `0x180011a89`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `765`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b8cc`
- `0x18000bcd4`

## callees

- `0x1800045d0`
- `0x18000da64`
- `0x180010744`
- `0x180010764`
- `0x18001115c`
- `0x18001178c`
- `0x180012220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011823`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800118b1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011823`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800118b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001192f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001195a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001198d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011876`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001192f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001195a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001198d`

## string_xrefs

- `0x1800119fa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011a13`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011a2c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011a45`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011a5e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011a77`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  const char *v13; // r9
  HANDLE v15; // rax
  const char *v16; // r9
  void *v17; // rdi
  int v18; // eax
  unsigned int v19; // esi
  const char *v20; // r9
  const char *v21; // r9
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v25);
    return 0;
  }
  v27[0] = 0;
  v26 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v17 = v15;
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v16);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return LastError;
  }
  v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v26);
  v19 = v18;
  if ( v18 >= 0 )
  {
    if ( !CloseHandle(v17) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    *a3 = v27[0] | (unsigned __int64)((__int64)v26 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v18);
  if ( !CloseHandle(v17) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v20);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  return v19;
}

```

## disassembly

```asm
0x18001178c  push    rbp
0x18001178e  push    rbx
0x18001178f  push    rsi
0x180011790  push    rdi
0x180011791  push    r14
0x180011793  push    r15
0x180011795  lea     rbp, [rsp-158h]
0x18001179d  sub     rsp, 258h
0x1800117a4  mov     rax, cs:__security_cookie
0x1800117ab  xor     rax, rsp
0x1800117ae  mov     [rbp+180h+var_40], rax
0x1800117b5  xor     r15d, r15d
0x1800117b8  lea     rax, [rsp+280h+Name]
0x1800117bd  mov     esi, 104h
0x1800117c2  mov     [r8], r15
0x1800117c5  mov     edx, esi
0x1800117c7  mov     r14, r8
0x1800117ca  mov     r9d, 7FFFFFFEh
0x1800117d0  test    r9, r9
0x1800117d3  jz      short loc_1800117F4
0x1800117d5  movzx   r8d, word ptr [rcx]
0x1800117d9  test    r8w, r8w
0x1800117dd  jz      short loc_1800117F4
0x1800117df  mov     [rax], r8w
0x1800117e3  add     rcx, 2
0x1800117e7  add     rax, 2
0x1800117eb  dec     r9
0x1800117ee  sub     rdx, 1
0x1800117f2  jnz     short loc_1800117D0
0x1800117f4  test    rdx, rdx
0x1800117f7  lea     rcx, [rax-2]
0x1800117fb  lea     r8, aP0; "_p0"
0x180011802  mov     rdx, rsi; unsigned __int64
0x180011805  cmovnz  rcx, rax
0x180011809  mov     [rcx], r15w
0x18001180d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180011812  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011817  lea     r8, [rsp+280h+Name]; lpName
0x18001181c  xor     edx, edx; bInheritHandle
0x18001181e  mov     ecx, 1F0003h; dwDesiredAccess
0x180011823  call    cs:__imp_OpenSemaphoreW
0x18001182a  nop     dword ptr [rax+rax+00h]
0x18001182f  mov     rbx, rax
0x180011832  test    rax, rax
0x180011835  jz      loc_1800119A6
0x18001183b  lea     rdx, [rsp+280h+var_25C]; int *
0x180011840  mov     [rsp+280h+var_25C], r15d
0x180011845  mov     rcx, rax; hHandle
0x180011848  mov     [rsp+280h+var_260], r15d; int
0x18001184d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011852  mov     edi, eax
0x180011854  test    eax, eax
0x180011856  jns     short loc_180011891
0x180011858  mov     rcx, [rbp+188h]; this
0x18001185f  lea     r8, aWil; "wil"
0x180011866  mov     r9d, eax; char *
0x180011869  mov     edx, 0D6h; void *
0x18001186e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011873  mov     rcx, rbx; hObject
0x180011876  call    cs:__imp_CloseHandle
0x18001187d  nop     dword ptr [rax+rax+00h]
0x180011882  test    eax, eax
0x180011884  jz      loc_180011A3E
0x18001188a  mov     eax, edi
0x18001188c  jmp     loc_1800119D3
0x180011891  lea     r8, asc_180037388; "h"
0x180011898  mov     rdx, rsi; unsigned __int64
0x18001189b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800118a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800118a5  lea     r8, [rsp+280h+Name]; lpName
0x1800118aa  xor     edx, edx; bInheritHandle
0x1800118ac  mov     ecx, 1F0003h; dwDesiredAccess
0x1800118b1  call    cs:__imp_OpenSemaphoreW
0x1800118b8  nop     dword ptr [rax+rax+00h]
0x1800118bd  mov     rdi, rax
0x1800118c0  test    rax, rax
0x1800118c3  jz      loc_180011970
0x1800118c9  lea     rdx, [rsp+280h+var_260]; int *
0x1800118ce  mov     rcx, rax; hHandle
0x1800118d1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800118d6  mov     esi, eax
0x1800118d8  test    eax, eax
0x1800118da  jns     short loc_18001192C
0x1800118dc  mov     rcx, [rbp+188h]; this
0x1800118e3  lea     r8, aWil; "wil"
0x1800118ea  mov     r9d, eax; char *
0x1800118ed  mov     edx, 0DEh; void *
0x1800118f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118f7  mov     rcx, rdi; hObject
0x1800118fa  call    cs:__imp_CloseHandle
0x180011901  nop     dword ptr [rax+rax+00h]
0x180011906  test    eax, eax
0x180011908  jz      loc_180011A57
0x18001190e  mov     rcx, rbx; hObject
0x180011911  call    cs:__imp_CloseHandle
0x180011918  nop     dword ptr [rax+rax+00h]
0x18001191d  test    eax, eax
0x18001191f  jz      loc_180011A70
0x180011925  mov     eax, esi
0x180011927  jmp     loc_1800119D3
0x18001192c  mov     rcx, rdi; hObject
0x18001192f  call    cs:__imp_CloseHandle
0x180011936  nop     dword ptr [rax+rax+00h]
0x18001193b  test    eax, eax
0x18001193d  jz      loc_1800119F3
0x180011943  movsxd  rax, [rsp+280h+var_25C]
0x180011948  movsxd  rcx, [rsp+280h+var_260]
0x18001194d  shl     rcx, 1Fh
0x180011951  or      rcx, rax
0x180011954  mov     [r14], rcx
0x180011957  mov     rcx, rbx; hObject
0x18001195a  call    cs:__imp_CloseHandle
0x180011961  nop     dword ptr [rax+rax+00h]
0x180011966  test    eax, eax
0x180011968  jz      loc_180011A0C
0x18001196e  jmp     short loc_1800119B7
0x180011970  mov     rcx, [rbp+188h]; this
0x180011977  lea     r8, aWil; "wil"
0x18001197e  mov     edx, 0DCh; void *
0x180011983  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011988  mov     rcx, rbx; hObject
0x18001198b  mov     edi, eax
0x18001198d  call    cs:__imp_CloseHandle
0x180011994  nop     dword ptr [rax+rax+00h]
0x180011999  test    eax, eax
0x18001199b  jz      loc_180011A25
0x1800119a1  jmp     loc_18001188A
0x1800119a6  call    cs:__imp_GetLastError
0x1800119ad  nop     dword ptr [rax+rax+00h]
0x1800119b2  cmp     eax, 2
0x1800119b5  jnz     short loc_1800119BB
0x1800119b7  xor     eax, eax
0x1800119b9  jmp     short loc_1800119D3
0x1800119bb  mov     rcx, [rbp+188h]; this
0x1800119c2  lea     r8, aWil; "wil"
0x1800119c9  mov     edx, 0D0h; void *
0x1800119ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800119d3  mov     rcx, [rbp+180h+var_40]
0x1800119da  xor     rcx, rsp; StackCookie
0x1800119dd  call    __security_check_cookie
0x1800119e2  add     rsp, 258h
0x1800119e9  pop     r15
0x1800119eb  pop     r14
0x1800119ed  pop     rdi
0x1800119ee  pop     rsi
0x1800119ef  pop     rbx
0x1800119f0  pop     rbp
0x1800119f1  retn
0x1800119f3  mov     rcx, [rbp+188h]; this
0x1800119fa  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011a01  mov     edx, 0A0Bh; void *
0x180011a06  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011a0c  mov     rcx, [rbp+188h]; this
0x180011a13  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011a1a  mov     edx, 0A0Bh; void *
0x180011a1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011a25  mov     rcx, [rbp+188h]; this
0x180011a2c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011a33  mov     edx, 0A0Bh; void *
0x180011a38  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011a3e  mov     rcx, [rbp+188h]; this
0x180011a45  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011a4c  mov     edx, 0A0Bh; void *
0x180011a51  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011a57  mov     rcx, [rbp+188h]; this
0x180011a5e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011a65  mov     edx, 0A0Bh; void *
0x180011a6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011a70  mov     rcx, [rbp+188h]; this
0x180011a77  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011a7e  mov     edx, 0A0Bh; void *
0x180011a83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
