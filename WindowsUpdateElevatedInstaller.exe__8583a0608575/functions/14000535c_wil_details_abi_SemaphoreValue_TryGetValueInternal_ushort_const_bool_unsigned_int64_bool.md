# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000535c`
- end: `0x1400055df`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140002d28`

## callees

- `0x140001480`
- `0x140003cc4`
- `0x1400048c4`
- `0x1400048e4`
- `0x1400051c0`
- `0x14000535c`
- `0x14000573c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005534`
- `KERNEL32!GetLastError` at `0x140005534`
- `KERNEL32!OpenSemaphoreW` at `0x1400053f3`
- `KERNEL32!OpenSemaphoreW` at `0x140005475`
- `KERNEL32!OpenSemaphoreW` at `0x1400053f3`
- `KERNEL32!OpenSemaphoreW` at `0x140005475`
- `KERNEL32!CloseHandle` at `0x140005440`
- `KERNEL32!CloseHandle` at `0x1400054b8`
- `KERNEL32!CloseHandle` at `0x1400054c9`
- `KERNEL32!CloseHandle` at `0x1400054de`
- `KERNEL32!CloseHandle` at `0x140005503`
- `KERNEL32!CloseHandle` at `0x140005525`
- `KERNEL32!CloseHandle` at `0x140005440`
- `KERNEL32!CloseHandle` at `0x1400054b8`
- `KERNEL32!CloseHandle` at `0x1400054c9`
- `KERNEL32!CloseHandle` at `0x1400054de`
- `KERNEL32!CloseHandle` at `0x140005503`
- `KERNEL32!CloseHandle` at `0x140005525`

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
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  __int64 v17; // r8
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
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
  StringCchCatW(Name, 260, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
    return 0;
  }
  v35[0] = 0;
  v34 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v35);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v17, v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v34);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v35[0] | (unsigned __int64)((__int64)v34 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x14000535c  push    rbp
0x14000535e  push    rbx
0x14000535f  push    rsi
0x140005360  push    rdi
0x140005361  push    r14
0x140005363  push    r15
0x140005365  lea     rbp, [rsp-158h]
0x14000536d  sub     rsp, 258h
0x140005374  mov     rax, cs:__security_cookie
0x14000537b  xor     rax, rsp
0x14000537e  mov     [rbp+180h+var_40], rax
0x140005385  xor     r15d, r15d
0x140005388  lea     rax, [rsp+280h+Name]
0x14000538d  mov     esi, 104h
0x140005392  mov     [r8], r15
0x140005395  mov     edx, esi
0x140005397  mov     r14, r8
0x14000539a  mov     r9d, 7FFFFFFEh
0x1400053a0  test    r9, r9
0x1400053a3  jz      short loc_1400053C4
0x1400053a5  movzx   r8d, word ptr [rcx]
0x1400053a9  test    r8w, r8w
0x1400053ad  jz      short loc_1400053C4
0x1400053af  mov     [rax], r8w
0x1400053b3  add     rcx, 2
0x1400053b7  add     rax, 2
0x1400053bb  dec     r9
0x1400053be  sub     rdx, 1
0x1400053c2  jnz     short loc_1400053A0
0x1400053c4  test    rdx, rdx
0x1400053c7  lea     rcx, [rax-2]
0x1400053cb  lea     r8, aP0; "_p0"
0x1400053d2  mov     rdx, rsi; unsigned __int64
0x1400053d5  cmovnz  rcx, rax
0x1400053d9  mov     [rcx], r15w
0x1400053dd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400053e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400053e7  lea     r8, [rsp+280h+Name]; lpName
0x1400053ec  xor     edx, edx; bInheritHandle
0x1400053ee  mov     ecx, 1F0003h; dwDesiredAccess
0x1400053f3  call    cs:__imp_OpenSemaphoreW
0x1400053f9  mov     rbx, rax
0x1400053fc  test    rax, rax
0x1400053ff  jz      loc_140005534
0x140005405  lea     rdx, [rsp+280h+var_25C]; int *
0x14000540a  mov     [rsp+280h+var_25C], r15d
0x14000540f  mov     rcx, rax; hHandle
0x140005412  mov     [rsp+280h+var_260], r15d; int
0x140005417  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000541c  mov     edi, eax
0x14000541e  test    eax, eax
0x140005420  jns     short loc_140005455
0x140005422  mov     rcx, [rbp+188h]; this
0x140005429  lea     r8, aWil; "wil"
0x140005430  mov     r9d, eax; char *
0x140005433  mov     edx, 0D6h; void *
0x140005438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000543d  mov     rcx, rbx; hObject
0x140005440  call    cs:__imp_CloseHandle
0x140005446  test    eax, eax
0x140005448  jz      loc_1400055A9
0x14000544e  mov     eax, edi
0x140005450  jmp     loc_140005554
0x140005455  lea     r8, asc_140009880; "h"
0x14000545c  mov     rdx, rsi; unsigned __int64
0x14000545f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005464  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005469  lea     r8, [rsp+280h+Name]; lpName
0x14000546e  xor     edx, edx; bInheritHandle
0x140005470  mov     ecx, 1F0003h; dwDesiredAccess
0x140005475  call    cs:__imp_OpenSemaphoreW
0x14000547b  mov     rdi, rax
0x14000547e  test    rax, rax
0x140005481  jz      loc_14000550F
0x140005487  lea     rdx, [rsp+280h+var_260]; int *
0x14000548c  mov     rcx, rax; hHandle
0x14000548f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005494  mov     esi, eax
0x140005496  test    eax, eax
0x140005498  jns     short loc_1400054DB
0x14000549a  mov     rcx, [rbp+188h]; this
0x1400054a1  lea     r8, aWil; "wil"
0x1400054a8  mov     r9d, eax; char *
0x1400054ab  mov     edx, 0DEh; void *
0x1400054b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400054b5  mov     rcx, rdi; hObject
0x1400054b8  call    cs:__imp_CloseHandle
0x1400054be  test    eax, eax
0x1400054c0  jz      loc_1400055BB
0x1400054c6  mov     rcx, rbx; hObject
0x1400054c9  call    cs:__imp_CloseHandle
0x1400054cf  test    eax, eax
0x1400054d1  jz      loc_1400055CD
0x1400054d7  mov     eax, esi
0x1400054d9  jmp     short loc_140005554
0x1400054db  mov     rcx, rdi; hObject
0x1400054de  call    cs:__imp_CloseHandle
0x1400054e4  test    eax, eax
0x1400054e6  jz      loc_140005573
0x1400054ec  movsxd  rax, [rsp+280h+var_25C]
0x1400054f1  movsxd  rcx, [rsp+280h+var_260]
0x1400054f6  shl     rcx, 1Fh
0x1400054fa  or      rcx, rax
0x1400054fd  mov     [r14], rcx
0x140005500  mov     rcx, rbx; hObject
0x140005503  call    cs:__imp_CloseHandle
0x140005509  test    eax, eax
0x14000550b  jz      short loc_140005585
0x14000550d  jmp     short loc_14000553F
0x14000550f  mov     rcx, [rbp+188h]; this
0x140005516  mov     edx, 0DCh; void *
0x14000551b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005520  mov     rcx, rbx; hObject
0x140005523  mov     edi, eax
0x140005525  call    cs:__imp_CloseHandle
0x14000552b  test    eax, eax
0x14000552d  jz      short loc_140005597
0x14000552f  jmp     loc_14000544E
0x140005534  call    cs:__imp_GetLastError
0x14000553a  cmp     eax, 2
0x14000553d  jnz     short loc_140005543
0x14000553f  xor     eax, eax
0x140005541  jmp     short loc_140005554
0x140005543  mov     rcx, [rbp+188h]; this
0x14000554a  mov     edx, 0D0h; void *
0x14000554f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005554  mov     rcx, [rbp+180h+var_40]
0x14000555b  xor     rcx, rsp; StackCookie
0x14000555e  call    __security_check_cookie
0x140005563  add     rsp, 258h
0x14000556a  pop     r15
0x14000556c  pop     r14
0x14000556e  pop     rdi
0x14000556f  pop     rsi
0x140005570  pop     rbx
0x140005571  pop     rbp
0x140005572  retn
0x140005573  mov     rcx, [rbp+188h]; this
0x14000557a  mov     edx, 0A0Bh; void *
0x14000557f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005585  mov     rcx, [rbp+188h]; this
0x14000558c  mov     edx, 0A0Bh; void *
0x140005591  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005597  mov     rcx, [rbp+188h]; this
0x14000559e  mov     edx, 0A0Bh; void *
0x1400055a3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400055a9  mov     rcx, [rbp+188h]; this
0x1400055b0  mov     edx, 0A0Bh; void *
0x1400055b5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400055bb  mov     rcx, [rbp+188h]; this
0x1400055c2  mov     edx, 0A0Bh; void *
0x1400055c7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400055cd  mov     rcx, [rbp+188h]; this
0x1400055d4  mov     edx, 0A0Bh; void *
0x1400055d9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
