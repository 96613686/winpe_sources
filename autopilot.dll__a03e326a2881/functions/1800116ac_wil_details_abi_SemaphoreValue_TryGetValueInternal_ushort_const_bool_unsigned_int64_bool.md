# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800116ac`
- end: `0x18001196e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b848`
- `0x18000bc20`

## callees

- `0x1800045b0`
- `0x18000da34`
- `0x1800105d4`
- `0x1800105f4`
- `0x180011160`
- `0x1800116ac`
- `0x180012114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011743`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800117c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011743`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800117c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011892`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011790`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011883`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011790`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011808`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011883`

## string_xrefs

- `0x1800118df`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800118f8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011911`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001192a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011943`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001195c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800116ac  push    rbp
0x1800116ae  push    rbx
0x1800116af  push    rsi
0x1800116b0  push    rdi
0x1800116b1  push    r14
0x1800116b3  push    r15
0x1800116b5  lea     rbp, [rsp-158h]
0x1800116bd  sub     rsp, 258h
0x1800116c4  mov     rax, cs:__security_cookie
0x1800116cb  xor     rax, rsp
0x1800116ce  mov     [rbp+180h+var_40], rax
0x1800116d5  xor     r15d, r15d
0x1800116d8  lea     rax, [rsp+280h+Name]
0x1800116dd  mov     esi, 104h
0x1800116e2  mov     [r8], r15
0x1800116e5  mov     edx, esi
0x1800116e7  mov     r14, r8
0x1800116ea  mov     r9d, 7FFFFFFEh
0x1800116f0  test    r9, r9
0x1800116f3  jz      short loc_180011714
0x1800116f5  movzx   r8d, word ptr [rcx]
0x1800116f9  test    r8w, r8w
0x1800116fd  jz      short loc_180011714
0x1800116ff  mov     [rax], r8w
0x180011703  add     rcx, 2
0x180011707  add     rax, 2
0x18001170b  dec     r9
0x18001170e  sub     rdx, 1
0x180011712  jnz     short loc_1800116F0
0x180011714  test    rdx, rdx
0x180011717  lea     rcx, [rax-2]
0x18001171b  lea     r8, aP0; "_p0"
0x180011722  mov     rdx, rsi; unsigned __int64
0x180011725  cmovnz  rcx, rax
0x180011729  mov     [rcx], r15w
0x18001172d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180011732  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011737  lea     r8, [rsp+280h+Name]; lpName
0x18001173c  xor     edx, edx; bInheritHandle
0x18001173e  mov     ecx, 1F0003h; dwDesiredAccess
0x180011743  call    cs:__imp_OpenSemaphoreW
0x180011749  mov     rbx, rax
0x18001174c  test    rax, rax
0x18001174f  jz      loc_180011892
0x180011755  lea     rdx, [rsp+280h+var_25C]; int *
0x18001175a  mov     [rsp+280h+var_25C], r15d
0x18001175f  mov     rcx, rax; hHandle
0x180011762  mov     [rsp+280h+var_260], r15d; int
0x180011767  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001176c  mov     edi, eax
0x18001176e  test    eax, eax
0x180011770  jns     short loc_1800117A5
0x180011772  mov     rcx, [rbp+188h]; this
0x180011779  lea     r8, aWil; "wil"
0x180011780  mov     r9d, eax; char *
0x180011783  mov     edx, 0D6h; void *
0x180011788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001178d  mov     rcx, rbx; hObject
0x180011790  call    cs:__imp_CloseHandle
0x180011796  test    eax, eax
0x180011798  jz      loc_180011923
0x18001179e  mov     eax, edi
0x1800117a0  jmp     loc_1800118B9
0x1800117a5  lea     r8, asc_180036368; "h"
0x1800117ac  mov     rdx, rsi; unsigned __int64
0x1800117af  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800117b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800117b9  lea     r8, [rsp+280h+Name]; lpName
0x1800117be  xor     edx, edx; bInheritHandle
0x1800117c0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800117c5  call    cs:__imp_OpenSemaphoreW
0x1800117cb  mov     rdi, rax
0x1800117ce  test    rax, rax
0x1800117d1  jz      loc_180011866
0x1800117d7  lea     rdx, [rsp+280h+var_260]; int *
0x1800117dc  mov     rcx, rax; hHandle
0x1800117df  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800117e4  mov     esi, eax
0x1800117e6  test    eax, eax
0x1800117e8  jns     short loc_18001182E
0x1800117ea  mov     rcx, [rbp+188h]; this
0x1800117f1  lea     r8, aWil; "wil"
0x1800117f8  mov     r9d, eax; char *
0x1800117fb  mov     edx, 0DEh; void *
0x180011800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011805  mov     rcx, rdi; hObject
0x180011808  call    cs:__imp_CloseHandle
0x18001180e  test    eax, eax
0x180011810  jz      loc_18001193C
0x180011816  mov     rcx, rbx; hObject
0x180011819  call    cs:__imp_CloseHandle
0x18001181f  test    eax, eax
0x180011821  jz      loc_180011955
0x180011827  mov     eax, esi
0x180011829  jmp     loc_1800118B9
0x18001182e  mov     rcx, rdi; hObject
0x180011831  call    cs:__imp_CloseHandle
0x180011837  test    eax, eax
0x180011839  jz      loc_1800118D8
0x18001183f  movsxd  rax, [rsp+280h+var_25C]
0x180011844  movsxd  rcx, [rsp+280h+var_260]
0x180011849  shl     rcx, 1Fh
0x18001184d  or      rcx, rax
0x180011850  mov     [r14], rcx
0x180011853  mov     rcx, rbx; hObject
0x180011856  call    cs:__imp_CloseHandle
0x18001185c  test    eax, eax
0x18001185e  jz      loc_1800118F1
0x180011864  jmp     short loc_18001189D
0x180011866  mov     rcx, [rbp+188h]; this
0x18001186d  lea     r8, aWil; "wil"
0x180011874  mov     edx, 0DCh; void *
0x180011879  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001187e  mov     rcx, rbx; hObject
0x180011881  mov     edi, eax
0x180011883  call    cs:__imp_CloseHandle
0x180011889  test    eax, eax
0x18001188b  jz      short loc_18001190A
0x18001188d  jmp     loc_18001179E
0x180011892  call    cs:__imp_GetLastError
0x180011898  cmp     eax, 2
0x18001189b  jnz     short loc_1800118A1
0x18001189d  xor     eax, eax
0x18001189f  jmp     short loc_1800118B9
0x1800118a1  mov     rcx, [rbp+188h]; this
0x1800118a8  lea     r8, aWil; "wil"
0x1800118af  mov     edx, 0D0h; void *
0x1800118b4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800118b9  mov     rcx, [rbp+180h+var_40]
0x1800118c0  xor     rcx, rsp; StackCookie
0x1800118c3  call    __security_check_cookie
0x1800118c8  add     rsp, 258h
0x1800118cf  pop     r15
0x1800118d1  pop     r14
0x1800118d3  pop     rdi
0x1800118d4  pop     rsi
0x1800118d5  pop     rbx
0x1800118d6  pop     rbp
0x1800118d7  retn
0x1800118d8  mov     rcx, [rbp+188h]; this
0x1800118df  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800118e6  mov     edx, 0A0Bh; void *
0x1800118eb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800118f1  mov     rcx, [rbp+188h]; this
0x1800118f8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800118ff  mov     edx, 0A0Bh; void *
0x180011904  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001190a  mov     rcx, [rbp+188h]; this
0x180011911  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011918  mov     edx, 0A0Bh; void *
0x18001191d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011923  mov     rcx, [rbp+188h]; this
0x18001192a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011931  mov     edx, 0A0Bh; void *
0x180011936  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001193c  mov     rcx, [rbp+188h]; this
0x180011943  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001194a  mov     edx, 0A0Bh; void *
0x18001194f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011955  mov     rcx, [rbp+188h]; this
0x18001195c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011963  mov     edx, 0A0Bh; void *
0x180011968  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
