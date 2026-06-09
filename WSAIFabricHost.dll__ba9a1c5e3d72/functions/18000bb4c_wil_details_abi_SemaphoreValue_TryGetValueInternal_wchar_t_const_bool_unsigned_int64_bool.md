# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bb4c`
- end: `0x18000be0e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009608`
- `0x18000d264`

## callees

- `0x180004ca0`
- `0x18000a718`
- `0x18000b044`
- `0x18000b064`
- `0x18000b9a4`
- `0x18000bb4c`
- `0x18000c018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bbe3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc65`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bbe3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bc30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bcf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd23`

## string_xrefs

- `0x18000bd7f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bd98`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bdb1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bdca`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bde3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000bdfc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
    return 0;
  }
  v27[0] = 0;
  v26 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v27);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v13);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v17 = v15;
  if ( !v15 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v16);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v22);
    *a3 = v27[0] | (unsigned __int64)((__int64)v26 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v18, v26);
  if ( !CloseHandle(v17) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v20);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  return v19;
}

```

## disassembly

```asm
0x18000bb4c  push    rbp
0x18000bb4e  push    rbx
0x18000bb4f  push    rsi
0x18000bb50  push    rdi
0x18000bb51  push    r14
0x18000bb53  push    r15
0x18000bb55  lea     rbp, [rsp-158h]
0x18000bb5d  sub     rsp, 258h
0x18000bb64  mov     rax, cs:__security_cookie
0x18000bb6b  xor     rax, rsp
0x18000bb6e  mov     [rbp+180h+var_40], rax
0x18000bb75  xor     r15d, r15d
0x18000bb78  lea     rax, [rsp+280h+Name]
0x18000bb7d  mov     esi, 104h
0x18000bb82  mov     [r8], r15
0x18000bb85  mov     edx, esi
0x18000bb87  mov     r14, r8
0x18000bb8a  mov     r9d, 7FFFFFFEh
0x18000bb90  test    r9, r9
0x18000bb93  jz      short loc_18000BBB4
0x18000bb95  movzx   r8d, word ptr [rcx]
0x18000bb99  test    r8w, r8w
0x18000bb9d  jz      short loc_18000BBB4
0x18000bb9f  mov     [rax], r8w
0x18000bba3  add     rcx, 2
0x18000bba7  add     rax, 2
0x18000bbab  dec     r9
0x18000bbae  sub     rdx, 1
0x18000bbb2  jnz     short loc_18000BB90
0x18000bbb4  test    rdx, rdx
0x18000bbb7  lea     rcx, [rax-2]
0x18000bbbb  lea     r8, aP0; "_p0"
0x18000bbc2  mov     rdx, rsi; unsigned __int64
0x18000bbc5  cmovnz  rcx, rax
0x18000bbc9  mov     [rcx], r15w
0x18000bbcd  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000bbd2  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000bbd7  lea     r8, [rsp+280h+Name]; lpName
0x18000bbdc  xor     edx, edx; bInheritHandle
0x18000bbde  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bbe3  call    cs:__imp_OpenSemaphoreW
0x18000bbe9  mov     rbx, rax
0x18000bbec  test    rax, rax
0x18000bbef  jz      loc_18000BD32
0x18000bbf5  lea     rdx, [rsp+280h+var_25C]; int *
0x18000bbfa  mov     [rsp+280h+var_25C], r15d
0x18000bbff  mov     rcx, rax; hHandle
0x18000bc02  mov     [rsp+280h+var_260], r15d; int
0x18000bc07  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bc0c  mov     edi, eax
0x18000bc0e  test    eax, eax
0x18000bc10  jns     short loc_18000BC45
0x18000bc12  mov     rcx, [rbp+188h]; this
0x18000bc19  lea     r8, aWil; "wil"
0x18000bc20  mov     r9d, eax; char *
0x18000bc23  mov     edx, 0D6h; void *
0x18000bc28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc2d  mov     rcx, rbx; hObject
0x18000bc30  call    cs:__imp_CloseHandle
0x18000bc36  test    eax, eax
0x18000bc38  jz      loc_18000BDC3
0x18000bc3e  mov     eax, edi
0x18000bc40  jmp     loc_18000BD59
0x18000bc45  lea     r8, asc_18008E5C0; "h"
0x18000bc4c  mov     rdx, rsi; unsigned __int64
0x18000bc4f  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000bc54  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000bc59  lea     r8, [rsp+280h+Name]; lpName
0x18000bc5e  xor     edx, edx; bInheritHandle
0x18000bc60  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bc65  call    cs:__imp_OpenSemaphoreW
0x18000bc6b  mov     rdi, rax
0x18000bc6e  test    rax, rax
0x18000bc71  jz      loc_18000BD06
0x18000bc77  lea     rdx, [rsp+280h+var_260]; int *
0x18000bc7c  mov     rcx, rax; hHandle
0x18000bc7f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bc84  mov     esi, eax
0x18000bc86  test    eax, eax
0x18000bc88  jns     short loc_18000BCCE
0x18000bc8a  mov     rcx, [rbp+188h]; this
0x18000bc91  lea     r8, aWil; "wil"
0x18000bc98  mov     r9d, eax; char *
0x18000bc9b  mov     edx, 0DEh; void *
0x18000bca0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bca5  mov     rcx, rdi; hObject
0x18000bca8  call    cs:__imp_CloseHandle
0x18000bcae  test    eax, eax
0x18000bcb0  jz      loc_18000BDDC
0x18000bcb6  mov     rcx, rbx; hObject
0x18000bcb9  call    cs:__imp_CloseHandle
0x18000bcbf  test    eax, eax
0x18000bcc1  jz      loc_18000BDF5
0x18000bcc7  mov     eax, esi
0x18000bcc9  jmp     loc_18000BD59
0x18000bcce  mov     rcx, rdi; hObject
0x18000bcd1  call    cs:__imp_CloseHandle
0x18000bcd7  test    eax, eax
0x18000bcd9  jz      loc_18000BD78
0x18000bcdf  movsxd  rax, [rsp+280h+var_25C]
0x18000bce4  movsxd  rcx, [rsp+280h+var_260]
0x18000bce9  shl     rcx, 1Fh
0x18000bced  or      rcx, rax
0x18000bcf0  mov     [r14], rcx
0x18000bcf3  mov     rcx, rbx; hObject
0x18000bcf6  call    cs:__imp_CloseHandle
0x18000bcfc  test    eax, eax
0x18000bcfe  jz      loc_18000BD91
0x18000bd04  jmp     short loc_18000BD3D
0x18000bd06  mov     rcx, [rbp+188h]; this
0x18000bd0d  lea     r8, aWil; "wil"
0x18000bd14  mov     edx, 0DCh; void *
0x18000bd19  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bd1e  mov     rcx, rbx; hObject
0x18000bd21  mov     edi, eax
0x18000bd23  call    cs:__imp_CloseHandle
0x18000bd29  test    eax, eax
0x18000bd2b  jz      short loc_18000BDAA
0x18000bd2d  jmp     loc_18000BC3E
0x18000bd32  call    cs:__imp_GetLastError
0x18000bd38  cmp     eax, 2
0x18000bd3b  jnz     short loc_18000BD41
0x18000bd3d  xor     eax, eax
0x18000bd3f  jmp     short loc_18000BD59
0x18000bd41  mov     rcx, [rbp+188h]; this
0x18000bd48  lea     r8, aWil; "wil"
0x18000bd4f  mov     edx, 0D0h; void *
0x18000bd54  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bd59  mov     rcx, [rbp+180h+var_40]
0x18000bd60  xor     rcx, rsp; StackCookie
0x18000bd63  call    __security_check_cookie
0x18000bd68  add     rsp, 258h
0x18000bd6f  pop     r15
0x18000bd71  pop     r14
0x18000bd73  pop     rdi
0x18000bd74  pop     rsi
0x18000bd75  pop     rbx
0x18000bd76  pop     rbp
0x18000bd77  retn
0x18000bd78  mov     rcx, [rbp+188h]; this
0x18000bd7f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bd86  mov     edx, 0A0Bh; void *
0x18000bd8b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bd91  mov     rcx, [rbp+188h]; this
0x18000bd98  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bd9f  mov     edx, 0A0Bh; void *
0x18000bda4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bdaa  mov     rcx, [rbp+188h]; this
0x18000bdb1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bdb8  mov     edx, 0A0Bh; void *
0x18000bdbd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bdc3  mov     rcx, [rbp+188h]; this
0x18000bdca  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bdd1  mov     edx, 0A0Bh; void *
0x18000bdd6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bddc  mov     rcx, [rbp+188h]; this
0x18000bde3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000bdea  mov     edx, 0A0Bh; void *
0x18000bdef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000bdf5  mov     rcx, [rbp+188h]; this
0x18000bdfc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000be03  mov     edx, 0A0Bh; void *
0x18000be08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
