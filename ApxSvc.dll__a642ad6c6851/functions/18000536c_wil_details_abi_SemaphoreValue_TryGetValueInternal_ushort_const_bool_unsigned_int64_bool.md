# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000536c`
- end: `0x1800055e6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180002f08`

## callees

- `0x180001560`
- `0x180003e94`
- `0x180004904`
- `0x180004924`
- `0x180005200`
- `0x18000536c`
- `0x18000573c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005400`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000547c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005400`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000547c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000553b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000553b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000544d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000550a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000552c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000544d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000550a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000552c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
  unsigned int LastError; // edi
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  __int64 v18; // r8
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
  const char *v32; // r9
  __int64 v33; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000536c  push    rbp
0x18000536e  push    rbx
0x18000536f  push    rsi
0x180005370  push    rdi
0x180005371  push    r14
0x180005373  push    r15
0x180005375  lea     rbp, [rsp-158h]
0x18000537d  sub     rsp, 258h
0x180005384  mov     rax, cs:__security_cookie
0x18000538b  xor     rax, rsp
0x18000538e  mov     [rbp+180h+var_40], rax
0x180005395  xor     r15d, r15d
0x180005398  lea     rax, [rsp+280h+Name]
0x18000539d  mov     [r8], r15
0x1800053a0  mov     r14, r8
0x1800053a3  mov     edx, 104h
0x1800053a8  mov     r9d, 7FFFFFFEh
0x1800053ae  test    r9, r9
0x1800053b1  jz      short loc_1800053D2
0x1800053b3  movzx   r8d, word ptr [rcx]
0x1800053b7  test    r8w, r8w
0x1800053bb  jz      short loc_1800053D2
0x1800053bd  mov     [rax], r8w
0x1800053c1  add     rcx, 2
0x1800053c5  add     rax, 2
0x1800053c9  dec     r9
0x1800053cc  sub     rdx, 1; unsigned __int64
0x1800053d0  jnz     short loc_1800053AE
0x1800053d2  test    rdx, rdx
0x1800053d5  lea     rcx, [rax-2]
0x1800053d9  lea     r8, aP0; "_p0"
0x1800053e0  cmovnz  rcx, rax
0x1800053e4  mov     [rcx], r15w
0x1800053e8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800053ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800053f2  mov     esi, 1F0003h
0x1800053f7  lea     r8, [rsp+280h+Name]; lpName
0x1800053fc  mov     ecx, esi; dwDesiredAccess
0x1800053fe  xor     edx, edx; bInheritHandle
0x180005400  call    cs:__imp_OpenSemaphoreW
0x180005406  mov     rbx, rax
0x180005409  test    rax, rax
0x18000540c  jz      loc_18000553B
0x180005412  lea     rdx, [rsp+280h+var_25C]; int *
0x180005417  mov     [rsp+280h+var_25C], r15d
0x18000541c  mov     rcx, rax; hHandle
0x18000541f  mov     [rsp+280h+var_260], r15d; int
0x180005424  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005429  mov     edi, eax
0x18000542b  test    eax, eax
0x18000542d  jns     short loc_180005462
0x18000542f  mov     rcx, [rbp+188h]; this
0x180005436  lea     r8, aWil; "wil"
0x18000543d  mov     r9d, eax; char *
0x180005440  mov     edx, 0D6h; void *
0x180005445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000544a  mov     rcx, rbx; hObject
0x18000544d  call    cs:__imp_CloseHandle
0x180005453  test    eax, eax
0x180005455  jz      loc_1800055B0
0x18000545b  mov     eax, edi
0x18000545d  jmp     loc_18000555B
0x180005462  lea     r8, asc_18000AEE0; "h"
0x180005469  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000546e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005473  lea     r8, [rsp+280h+Name]; lpName
0x180005478  xor     edx, edx; bInheritHandle
0x18000547a  mov     ecx, esi; dwDesiredAccess
0x18000547c  call    cs:__imp_OpenSemaphoreW
0x180005482  mov     rdi, rax
0x180005485  test    rax, rax
0x180005488  jz      loc_180005516
0x18000548e  lea     rdx, [rsp+280h+var_260]; int *
0x180005493  mov     rcx, rax; hHandle
0x180005496  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000549b  mov     esi, eax
0x18000549d  test    eax, eax
0x18000549f  jns     short loc_1800054E2
0x1800054a1  mov     rcx, [rbp+188h]; this
0x1800054a8  lea     r8, aWil; "wil"
0x1800054af  mov     r9d, eax; char *
0x1800054b2  mov     edx, 0DEh; void *
0x1800054b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800054bc  mov     rcx, rdi; hObject
0x1800054bf  call    cs:__imp_CloseHandle
0x1800054c5  test    eax, eax
0x1800054c7  jz      loc_1800055C2
0x1800054cd  mov     rcx, rbx; hObject
0x1800054d0  call    cs:__imp_CloseHandle
0x1800054d6  test    eax, eax
0x1800054d8  jz      loc_1800055D4
0x1800054de  mov     eax, esi
0x1800054e0  jmp     short loc_18000555B
0x1800054e2  mov     rcx, rdi; hObject
0x1800054e5  call    cs:__imp_CloseHandle
0x1800054eb  test    eax, eax
0x1800054ed  jz      loc_18000557A
0x1800054f3  movsxd  rax, [rsp+280h+var_25C]
0x1800054f8  movsxd  rcx, [rsp+280h+var_260]
0x1800054fd  shl     rcx, 1Fh
0x180005501  or      rcx, rax
0x180005504  mov     [r14], rcx
0x180005507  mov     rcx, rbx; hObject
0x18000550a  call    cs:__imp_CloseHandle
0x180005510  test    eax, eax
0x180005512  jz      short loc_18000558C
0x180005514  jmp     short loc_180005546
0x180005516  mov     rcx, [rbp+188h]; this
0x18000551d  mov     edx, 0DCh; void *
0x180005522  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005527  mov     rcx, rbx; hObject
0x18000552a  mov     edi, eax
0x18000552c  call    cs:__imp_CloseHandle
0x180005532  test    eax, eax
0x180005534  jz      short loc_18000559E
0x180005536  jmp     loc_18000545B
0x18000553b  call    cs:__imp_GetLastError
0x180005541  cmp     eax, 2
0x180005544  jnz     short loc_18000554A
0x180005546  xor     eax, eax
0x180005548  jmp     short loc_18000555B
0x18000554a  mov     rcx, [rbp+188h]; this
0x180005551  mov     edx, 0D0h; void *
0x180005556  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000555b  mov     rcx, [rbp+180h+var_40]
0x180005562  xor     rcx, rsp; StackCookie
0x180005565  call    __security_check_cookie
0x18000556a  add     rsp, 258h
0x180005571  pop     r15
0x180005573  pop     r14
0x180005575  pop     rdi
0x180005576  pop     rsi
0x180005577  pop     rbx
0x180005578  pop     rbp
0x180005579  retn
0x18000557a  mov     rcx, [rbp+188h]; this
0x180005581  mov     edx, 0A0Bh; void *
0x180005586  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000558c  mov     rcx, [rbp+188h]; this
0x180005593  mov     edx, 0A0Bh; void *
0x180005598  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000559e  mov     rcx, [rbp+188h]; this
0x1800055a5  mov     edx, 0A0Bh; void *
0x1800055aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800055b0  mov     rcx, [rbp+188h]; this
0x1800055b7  mov     edx, 0A0Bh; void *
0x1800055bc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800055c2  mov     rcx, [rbp+188h]; this
0x1800055c9  mov     edx, 0A0Bh; void *
0x1800055ce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800055d4  mov     rcx, [rbp+188h]; this
0x1800055db  mov     edx, 0A0Bh; void *
0x1800055e0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
