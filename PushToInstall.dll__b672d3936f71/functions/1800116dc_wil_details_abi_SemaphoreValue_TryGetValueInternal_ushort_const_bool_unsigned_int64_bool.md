# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800116dc`
- end: `0x18001199e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ef68`
- `0x180012814`

## callees

- `0x1800026b0`
- `0x18000ffd4`
- `0x180010b64`
- `0x180010b84`
- `0x1800114c4`
- `0x1800116dc`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011773`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800117f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011773`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800117f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011886`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800117c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011849`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011886`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800118b3`

## string_xrefs

- `0x18001190f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011928`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011941`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001195a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011973`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001198c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v18, v26);
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
0x1800116dc  push    rbp
0x1800116de  push    rbx
0x1800116df  push    rsi
0x1800116e0  push    rdi
0x1800116e1  push    r14
0x1800116e3  push    r15
0x1800116e5  lea     rbp, [rsp-158h]
0x1800116ed  sub     rsp, 258h
0x1800116f4  mov     rax, cs:__security_cookie
0x1800116fb  xor     rax, rsp
0x1800116fe  mov     [rbp+180h+var_40], rax
0x180011705  xor     r15d, r15d
0x180011708  lea     rax, [rsp+280h+Name]
0x18001170d  mov     esi, 104h
0x180011712  mov     [r8], r15
0x180011715  mov     edx, esi
0x180011717  mov     r14, r8
0x18001171a  mov     r9d, 7FFFFFFEh
0x180011720  test    r9, r9
0x180011723  jz      short loc_180011744
0x180011725  movzx   r8d, word ptr [rcx]
0x180011729  test    r8w, r8w
0x18001172d  jz      short loc_180011744
0x18001172f  mov     [rax], r8w
0x180011733  add     rcx, 2
0x180011737  add     rax, 2
0x18001173b  dec     r9
0x18001173e  sub     rdx, 1
0x180011742  jnz     short loc_180011720
0x180011744  test    rdx, rdx
0x180011747  lea     rcx, [rax-2]
0x18001174b  lea     r8, aP0; "_p0"
0x180011752  mov     rdx, rsi; unsigned __int64
0x180011755  cmovnz  rcx, rax
0x180011759  mov     [rcx], r15w
0x18001175d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180011762  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011767  lea     r8, [rsp+280h+Name]; lpName
0x18001176c  xor     edx, edx; bInheritHandle
0x18001176e  mov     ecx, 1F0003h; dwDesiredAccess
0x180011773  call    cs:__imp_OpenSemaphoreW
0x180011779  mov     rbx, rax
0x18001177c  test    rax, rax
0x18001177f  jz      loc_1800118C2
0x180011785  lea     rdx, [rsp+280h+var_25C]; int *
0x18001178a  mov     [rsp+280h+var_25C], r15d
0x18001178f  mov     rcx, rax; hHandle
0x180011792  mov     [rsp+280h+var_260], r15d; int
0x180011797  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001179c  mov     edi, eax
0x18001179e  test    eax, eax
0x1800117a0  jns     short loc_1800117D5
0x1800117a2  mov     rcx, [rbp+188h]; this
0x1800117a9  lea     r8, aWil; "wil"
0x1800117b0  mov     r9d, eax; char *
0x1800117b3  mov     edx, 0D6h; void *
0x1800117b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117bd  mov     rcx, rbx; hObject
0x1800117c0  call    cs:__imp_CloseHandle
0x1800117c6  test    eax, eax
0x1800117c8  jz      loc_180011953
0x1800117ce  mov     eax, edi
0x1800117d0  jmp     loc_1800118E9
0x1800117d5  lea     r8, asc_180053518; "h"
0x1800117dc  mov     rdx, rsi; unsigned __int64
0x1800117df  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800117e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800117e9  lea     r8, [rsp+280h+Name]; lpName
0x1800117ee  xor     edx, edx; bInheritHandle
0x1800117f0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800117f5  call    cs:__imp_OpenSemaphoreW
0x1800117fb  mov     rdi, rax
0x1800117fe  test    rax, rax
0x180011801  jz      loc_180011896
0x180011807  lea     rdx, [rsp+280h+var_260]; int *
0x18001180c  mov     rcx, rax; hHandle
0x18001180f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011814  mov     esi, eax
0x180011816  test    eax, eax
0x180011818  jns     short loc_18001185E
0x18001181a  mov     rcx, [rbp+188h]; this
0x180011821  lea     r8, aWil; "wil"
0x180011828  mov     r9d, eax; char *
0x18001182b  mov     edx, 0DEh; void *
0x180011830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011835  mov     rcx, rdi; hObject
0x180011838  call    cs:__imp_CloseHandle
0x18001183e  test    eax, eax
0x180011840  jz      loc_18001196C
0x180011846  mov     rcx, rbx; hObject
0x180011849  call    cs:__imp_CloseHandle
0x18001184f  test    eax, eax
0x180011851  jz      loc_180011985
0x180011857  mov     eax, esi
0x180011859  jmp     loc_1800118E9
0x18001185e  mov     rcx, rdi; hObject
0x180011861  call    cs:__imp_CloseHandle
0x180011867  test    eax, eax
0x180011869  jz      loc_180011908
0x18001186f  movsxd  rax, [rsp+280h+var_25C]
0x180011874  movsxd  rcx, [rsp+280h+var_260]
0x180011879  shl     rcx, 1Fh
0x18001187d  or      rcx, rax
0x180011880  mov     [r14], rcx
0x180011883  mov     rcx, rbx; hObject
0x180011886  call    cs:__imp_CloseHandle
0x18001188c  test    eax, eax
0x18001188e  jz      loc_180011921
0x180011894  jmp     short loc_1800118CD
0x180011896  mov     rcx, [rbp+188h]; this
0x18001189d  lea     r8, aWil; "wil"
0x1800118a4  mov     edx, 0DCh; void *
0x1800118a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800118ae  mov     rcx, rbx; hObject
0x1800118b1  mov     edi, eax
0x1800118b3  call    cs:__imp_CloseHandle
0x1800118b9  test    eax, eax
0x1800118bb  jz      short loc_18001193A
0x1800118bd  jmp     loc_1800117CE
0x1800118c2  call    cs:__imp_GetLastError
0x1800118c8  cmp     eax, 2
0x1800118cb  jnz     short loc_1800118D1
0x1800118cd  xor     eax, eax
0x1800118cf  jmp     short loc_1800118E9
0x1800118d1  mov     rcx, [rbp+188h]; this
0x1800118d8  lea     r8, aWil; "wil"
0x1800118df  mov     edx, 0D0h; void *
0x1800118e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800118e9  mov     rcx, [rbp+180h+var_40]
0x1800118f0  xor     rcx, rsp; StackCookie
0x1800118f3  call    __security_check_cookie
0x1800118f8  add     rsp, 258h
0x1800118ff  pop     r15
0x180011901  pop     r14
0x180011903  pop     rdi
0x180011904  pop     rsi
0x180011905  pop     rbx
0x180011906  pop     rbp
0x180011907  retn
0x180011908  mov     rcx, [rbp+188h]; this
0x18001190f  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011916  mov     edx, 0A0Bh; void *
0x18001191b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011921  mov     rcx, [rbp+188h]; this
0x180011928  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001192f  mov     edx, 0A0Bh; void *
0x180011934  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001193a  mov     rcx, [rbp+188h]; this
0x180011941  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011948  mov     edx, 0A0Bh; void *
0x18001194d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011953  mov     rcx, [rbp+188h]; this
0x18001195a  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011961  mov     edx, 0A0Bh; void *
0x180011966  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001196c  mov     rcx, [rbp+188h]; this
0x180011973  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001197a  mov     edx, 0A0Bh; void *
0x18001197f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011985  mov     rcx, [rbp+188h]; this
0x18001198c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011993  mov     edx, 0A0Bh; void *
0x180011998  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
