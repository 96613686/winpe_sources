# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008f3c`
- end: `0x1800091f5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `697`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800073b8`

## callees

- `0x1800016c0`
- `0x1800061f4`
- `0x180006214`
- `0x180008010`
- `0x180008db0`
- `0x180008f3c`
- `0x180009260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009119`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fd0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000904c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fd0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000904c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000901d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000908f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000910a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000901d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000908f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800090dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000910a`

## string_xrefs

- `0x180009166`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000917f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180009198`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800091b1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800091ca`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800091e3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v26);
    return 0;
  }
  v28[0] = 0;
  v27 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v28);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v14);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
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
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v23);
    *a3 = v28[0] | (unsigned __int64)((__int64)v27 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v24);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v21);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  return v20;
}

```

## disassembly

```asm
0x180008f3c  push    rbp
0x180008f3e  push    rbx
0x180008f3f  push    rsi
0x180008f40  push    rdi
0x180008f41  push    r14
0x180008f43  push    r15
0x180008f45  lea     rbp, [rsp-158h]
0x180008f4d  sub     rsp, 258h
0x180008f54  mov     rax, cs:__security_cookie
0x180008f5b  xor     rax, rsp
0x180008f5e  mov     [rbp+180h+var_40], rax
0x180008f65  xor     r15d, r15d
0x180008f68  lea     rax, [rsp+280h+Name]
0x180008f6d  mov     [r8], r15
0x180008f70  mov     r14, r8
0x180008f73  mov     edx, 104h
0x180008f78  mov     r9d, 7FFFFFFEh
0x180008f7e  test    r9, r9
0x180008f81  jz      short loc_180008FA2
0x180008f83  movzx   r8d, word ptr [rcx]
0x180008f87  test    r8w, r8w
0x180008f8b  jz      short loc_180008FA2
0x180008f8d  mov     [rax], r8w
0x180008f91  add     rcx, 2
0x180008f95  add     rax, 2
0x180008f99  dec     r9
0x180008f9c  sub     rdx, 1; unsigned __int64
0x180008fa0  jnz     short loc_180008F7E
0x180008fa2  test    rdx, rdx
0x180008fa5  lea     rcx, [rax-2]
0x180008fa9  lea     r8, aP0; "_p0"
0x180008fb0  cmovnz  rcx, rax
0x180008fb4  mov     [rcx], r15w
0x180008fb8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008fbd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008fc2  mov     esi, 1F0003h
0x180008fc7  lea     r8, [rsp+280h+Name]; lpName
0x180008fcc  mov     ecx, esi; dwDesiredAccess
0x180008fce  xor     edx, edx; bInheritHandle
0x180008fd0  call    cs:__imp_OpenSemaphoreW
0x180008fd6  mov     rbx, rax
0x180008fd9  test    rax, rax
0x180008fdc  jz      loc_180009119
0x180008fe2  lea     rdx, [rsp+280h+var_25C]; int *
0x180008fe7  mov     [rsp+280h+var_25C], r15d
0x180008fec  mov     rcx, rax; hHandle
0x180008fef  mov     [rsp+280h+var_260], r15d; int
0x180008ff4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008ff9  mov     edi, eax
0x180008ffb  test    eax, eax
0x180008ffd  jns     short loc_180009032
0x180008fff  mov     rcx, [rbp+188h]; this
0x180009006  lea     r8, aWil; "wil"
0x18000900d  mov     r9d, eax; char *
0x180009010  mov     edx, 0D6h; void *
0x180009015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000901a  mov     rcx, rbx; hObject
0x18000901d  call    cs:__imp_CloseHandle
0x180009023  test    eax, eax
0x180009025  jz      loc_1800091AA
0x18000902b  mov     eax, edi
0x18000902d  jmp     loc_180009140
0x180009032  lea     r8, asc_180015C58; "h"
0x180009039  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000903e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009043  lea     r8, [rsp+280h+Name]; lpName
0x180009048  xor     edx, edx; bInheritHandle
0x18000904a  mov     ecx, esi; dwDesiredAccess
0x18000904c  call    cs:__imp_OpenSemaphoreW
0x180009052  mov     rdi, rax
0x180009055  test    rax, rax
0x180009058  jz      loc_1800090ED
0x18000905e  lea     rdx, [rsp+280h+var_260]; int *
0x180009063  mov     rcx, rax; hHandle
0x180009066  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000906b  mov     esi, eax
0x18000906d  test    eax, eax
0x18000906f  jns     short loc_1800090B5
0x180009071  mov     rcx, [rbp+188h]; this
0x180009078  lea     r8, aWil; "wil"
0x18000907f  mov     r9d, eax; char *
0x180009082  mov     edx, 0DEh; void *
0x180009087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000908c  mov     rcx, rdi; hObject
0x18000908f  call    cs:__imp_CloseHandle
0x180009095  test    eax, eax
0x180009097  jz      loc_1800091C3
0x18000909d  mov     rcx, rbx; hObject
0x1800090a0  call    cs:__imp_CloseHandle
0x1800090a6  test    eax, eax
0x1800090a8  jz      loc_1800091DC
0x1800090ae  mov     eax, esi
0x1800090b0  jmp     loc_180009140
0x1800090b5  mov     rcx, rdi; hObject
0x1800090b8  call    cs:__imp_CloseHandle
0x1800090be  test    eax, eax
0x1800090c0  jz      loc_18000915F
0x1800090c6  movsxd  rax, [rsp+280h+var_25C]
0x1800090cb  movsxd  rcx, [rsp+280h+var_260]
0x1800090d0  shl     rcx, 1Fh
0x1800090d4  or      rcx, rax
0x1800090d7  mov     [r14], rcx
0x1800090da  mov     rcx, rbx; hObject
0x1800090dd  call    cs:__imp_CloseHandle
0x1800090e3  test    eax, eax
0x1800090e5  jz      loc_180009178
0x1800090eb  jmp     short loc_180009124
0x1800090ed  mov     rcx, [rbp+188h]; this
0x1800090f4  lea     r8, aWil; "wil"
0x1800090fb  mov     edx, 0DCh; void *
0x180009100  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009105  mov     rcx, rbx; hObject
0x180009108  mov     edi, eax
0x18000910a  call    cs:__imp_CloseHandle
0x180009110  test    eax, eax
0x180009112  jz      short loc_180009191
0x180009114  jmp     loc_18000902B
0x180009119  call    cs:__imp_GetLastError
0x18000911f  cmp     eax, 2
0x180009122  jnz     short loc_180009128
0x180009124  xor     eax, eax
0x180009126  jmp     short loc_180009140
0x180009128  mov     rcx, [rbp+188h]; this
0x18000912f  lea     r8, aWil; "wil"
0x180009136  mov     edx, 0D0h; void *
0x18000913b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009140  mov     rcx, [rbp+180h+var_40]
0x180009147  xor     rcx, rsp; StackCookie
0x18000914a  call    __security_check_cookie
0x18000914f  add     rsp, 258h
0x180009156  pop     r15
0x180009158  pop     r14
0x18000915a  pop     rdi
0x18000915b  pop     rsi
0x18000915c  pop     rbx
0x18000915d  pop     rbp
0x18000915e  retn
0x18000915f  mov     rcx, [rbp+188h]; this
0x180009166  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000916d  mov     edx, 0A0Bh; void *
0x180009172  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009178  mov     rcx, [rbp+188h]; this
0x18000917f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009186  mov     edx, 0A0Bh; void *
0x18000918b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009191  mov     rcx, [rbp+188h]; this
0x180009198  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000919f  mov     edx, 0A0Bh; void *
0x1800091a4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800091aa  mov     rcx, [rbp+188h]; this
0x1800091b1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800091b8  mov     edx, 0A0Bh; void *
0x1800091bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800091c3  mov     rcx, [rbp+188h]; this
0x1800091ca  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800091d1  mov     edx, 0A0Bh; void *
0x1800091d6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800091dc  mov     rcx, [rbp+188h]; this
0x1800091e3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800091ea  mov     edx, 0A0Bh; void *
0x1800091ef  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
