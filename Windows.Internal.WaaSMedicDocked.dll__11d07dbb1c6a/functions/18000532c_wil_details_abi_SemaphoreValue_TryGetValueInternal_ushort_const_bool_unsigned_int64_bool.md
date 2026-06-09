# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000532c`
- end: `0x1800055a6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002eb8`

## callees

- `0x180001570`
- `0x180003e54`
- `0x1800048c4`
- `0x1800048e4`
- `0x1800051c0`
- `0x18000532c`
- `0x1800056fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800053c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000543c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800053c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000543c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000540d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000547f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000540d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000547f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005490`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ec`

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
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000532c  push    rbp
0x18000532e  push    rbx
0x18000532f  push    rsi
0x180005330  push    rdi
0x180005331  push    r14
0x180005333  push    r15
0x180005335  lea     rbp, [rsp-158h]
0x18000533d  sub     rsp, 258h
0x180005344  mov     rax, cs:__security_cookie
0x18000534b  xor     rax, rsp
0x18000534e  mov     [rbp+180h+var_40], rax
0x180005355  xor     r15d, r15d
0x180005358  lea     rax, [rsp+280h+Name]
0x18000535d  mov     [r8], r15
0x180005360  mov     r14, r8
0x180005363  mov     edx, 104h
0x180005368  mov     r9d, 7FFFFFFEh
0x18000536e  test    r9, r9
0x180005371  jz      short loc_180005392
0x180005373  movzx   r8d, word ptr [rcx]
0x180005377  test    r8w, r8w
0x18000537b  jz      short loc_180005392
0x18000537d  mov     [rax], r8w
0x180005381  add     rcx, 2
0x180005385  add     rax, 2
0x180005389  dec     r9
0x18000538c  sub     rdx, 1; unsigned __int64
0x180005390  jnz     short loc_18000536E
0x180005392  test    rdx, rdx
0x180005395  lea     rcx, [rax-2]
0x180005399  lea     r8, aP0; "_p0"
0x1800053a0  cmovnz  rcx, rax
0x1800053a4  mov     [rcx], r15w
0x1800053a8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800053ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800053b2  mov     esi, 1F0003h
0x1800053b7  lea     r8, [rsp+280h+Name]; lpName
0x1800053bc  mov     ecx, esi; dwDesiredAccess
0x1800053be  xor     edx, edx; bInheritHandle
0x1800053c0  call    cs:__imp_OpenSemaphoreW
0x1800053c6  mov     rbx, rax
0x1800053c9  test    rax, rax
0x1800053cc  jz      loc_1800054FB
0x1800053d2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800053d7  mov     [rsp+280h+var_25C], r15d
0x1800053dc  mov     rcx, rax; hHandle
0x1800053df  mov     [rsp+280h+var_260], r15d; int
0x1800053e4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800053e9  mov     edi, eax
0x1800053eb  test    eax, eax
0x1800053ed  jns     short loc_180005422
0x1800053ef  mov     rcx, [rbp+188h]; this
0x1800053f6  lea     r8, aWil; "wil"
0x1800053fd  mov     r9d, eax; char *
0x180005400  mov     edx, 0D6h; void *
0x180005405  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000540a  mov     rcx, rbx; hObject
0x18000540d  call    cs:__imp_CloseHandle
0x180005413  test    eax, eax
0x180005415  jz      loc_180005570
0x18000541b  mov     eax, edi
0x18000541d  jmp     loc_18000551B
0x180005422  lea     r8, asc_18000F138; "h"
0x180005429  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000542e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005433  lea     r8, [rsp+280h+Name]; lpName
0x180005438  xor     edx, edx; bInheritHandle
0x18000543a  mov     ecx, esi; dwDesiredAccess
0x18000543c  call    cs:__imp_OpenSemaphoreW
0x180005442  mov     rdi, rax
0x180005445  test    rax, rax
0x180005448  jz      loc_1800054D6
0x18000544e  lea     rdx, [rsp+280h+var_260]; int *
0x180005453  mov     rcx, rax; hHandle
0x180005456  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000545b  mov     esi, eax
0x18000545d  test    eax, eax
0x18000545f  jns     short loc_1800054A2
0x180005461  mov     rcx, [rbp+188h]; this
0x180005468  lea     r8, aWil; "wil"
0x18000546f  mov     r9d, eax; char *
0x180005472  mov     edx, 0DEh; void *
0x180005477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000547c  mov     rcx, rdi; hObject
0x18000547f  call    cs:__imp_CloseHandle
0x180005485  test    eax, eax
0x180005487  jz      loc_180005582
0x18000548d  mov     rcx, rbx; hObject
0x180005490  call    cs:__imp_CloseHandle
0x180005496  test    eax, eax
0x180005498  jz      loc_180005594
0x18000549e  mov     eax, esi
0x1800054a0  jmp     short loc_18000551B
0x1800054a2  mov     rcx, rdi; hObject
0x1800054a5  call    cs:__imp_CloseHandle
0x1800054ab  test    eax, eax
0x1800054ad  jz      loc_18000553A
0x1800054b3  movsxd  rax, [rsp+280h+var_25C]
0x1800054b8  movsxd  rcx, [rsp+280h+var_260]
0x1800054bd  shl     rcx, 1Fh
0x1800054c1  or      rcx, rax
0x1800054c4  mov     [r14], rcx
0x1800054c7  mov     rcx, rbx; hObject
0x1800054ca  call    cs:__imp_CloseHandle
0x1800054d0  test    eax, eax
0x1800054d2  jz      short loc_18000554C
0x1800054d4  jmp     short loc_180005506
0x1800054d6  mov     rcx, [rbp+188h]; this
0x1800054dd  mov     edx, 0DCh; void *
0x1800054e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800054e7  mov     rcx, rbx; hObject
0x1800054ea  mov     edi, eax
0x1800054ec  call    cs:__imp_CloseHandle
0x1800054f2  test    eax, eax
0x1800054f4  jz      short loc_18000555E
0x1800054f6  jmp     loc_18000541B
0x1800054fb  call    cs:__imp_GetLastError
0x180005501  cmp     eax, 2
0x180005504  jnz     short loc_18000550A
0x180005506  xor     eax, eax
0x180005508  jmp     short loc_18000551B
0x18000550a  mov     rcx, [rbp+188h]; this
0x180005511  mov     edx, 0D0h; void *
0x180005516  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000551b  mov     rcx, [rbp+180h+var_40]
0x180005522  xor     rcx, rsp; StackCookie
0x180005525  call    __security_check_cookie
0x18000552a  add     rsp, 258h
0x180005531  pop     r15
0x180005533  pop     r14
0x180005535  pop     rdi
0x180005536  pop     rsi
0x180005537  pop     rbx
0x180005538  pop     rbp
0x180005539  retn
0x18000553a  mov     rcx, [rbp+188h]; this
0x180005541  mov     edx, 0A0Bh; void *
0x180005546  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000554c  mov     rcx, [rbp+188h]; this
0x180005553  mov     edx, 0A0Bh; void *
0x180005558  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000555e  mov     rcx, [rbp+188h]; this
0x180005565  mov     edx, 0A0Bh; void *
0x18000556a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005570  mov     rcx, [rbp+188h]; this
0x180005577  mov     edx, 0A0Bh; void *
0x18000557c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005582  mov     rcx, [rbp+188h]; this
0x180005589  mov     edx, 0A0Bh; void *
0x18000558e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005594  mov     rcx, [rbp+188h]; this
0x18000559b  mov     edx, 0A0Bh; void *
0x1800055a0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
