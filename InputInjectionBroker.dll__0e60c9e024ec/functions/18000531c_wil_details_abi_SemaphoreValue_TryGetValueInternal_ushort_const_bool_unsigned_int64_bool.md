# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000531c`
- end: `0x180005596`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800030a0`
- `0x180009ed8`

## callees

- `0x180004024`
- `0x180004a14`
- `0x180004a34`
- `0x1800051b4`
- `0x18000531c`
- `0x1800057e4`
- `0x180011460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800053b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000542c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800053b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000542c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000546f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800053fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000546f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005480`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800054dc`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
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
0x18000531c  push    rbp
0x18000531e  push    rbx
0x18000531f  push    rsi
0x180005320  push    rdi
0x180005321  push    r14
0x180005323  push    r15
0x180005325  lea     rbp, [rsp-158h]
0x18000532d  sub     rsp, 258h
0x180005334  mov     rax, cs:__security_cookie
0x18000533b  xor     rax, rsp
0x18000533e  mov     [rbp+180h+var_40], rax
0x180005345  xor     r15d, r15d
0x180005348  lea     rax, [rsp+280h+Name]
0x18000534d  mov     [r8], r15
0x180005350  mov     r14, r8
0x180005353  mov     edx, 104h
0x180005358  mov     r9d, 7FFFFFFEh
0x18000535e  test    r9, r9
0x180005361  jz      short loc_180005382
0x180005363  movzx   r8d, word ptr [rcx]
0x180005367  test    r8w, r8w
0x18000536b  jz      short loc_180005382
0x18000536d  mov     [rax], r8w
0x180005371  add     rcx, 2
0x180005375  add     rax, 2
0x180005379  dec     r9
0x18000537c  sub     rdx, 1; unsigned __int64
0x180005380  jnz     short loc_18000535E
0x180005382  test    rdx, rdx
0x180005385  lea     rcx, [rax-2]
0x180005389  lea     r8, aP0; "_p0"
0x180005390  cmovnz  rcx, rax
0x180005394  mov     [rcx], r15w
0x180005398  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000539d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800053a2  mov     esi, 1F0003h
0x1800053a7  lea     r8, [rsp+280h+Name]; lpName
0x1800053ac  mov     ecx, esi; dwDesiredAccess
0x1800053ae  xor     edx, edx; bInheritHandle
0x1800053b0  call    cs:__imp_OpenSemaphoreW
0x1800053b6  mov     rbx, rax
0x1800053b9  test    rax, rax
0x1800053bc  jz      loc_1800054EB
0x1800053c2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800053c7  mov     [rsp+280h+var_25C], r15d
0x1800053cc  mov     rcx, rax; hHandle
0x1800053cf  mov     [rsp+280h+var_260], r15d; int
0x1800053d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800053d9  mov     edi, eax
0x1800053db  test    eax, eax
0x1800053dd  jns     short loc_180005412
0x1800053df  mov     rcx, [rbp+188h]; this
0x1800053e6  lea     r8, aWil; "wil"
0x1800053ed  mov     r9d, eax; char *
0x1800053f0  mov     edx, 0D6h; void *
0x1800053f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053fa  mov     rcx, rbx; hObject
0x1800053fd  call    cs:__imp_CloseHandle
0x180005403  test    eax, eax
0x180005405  jz      loc_180005560
0x18000540b  mov     eax, edi
0x18000540d  jmp     loc_18000550B
0x180005412  lea     r8, asc_18001B8B0; "h"
0x180005419  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000541e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005423  lea     r8, [rsp+280h+Name]; lpName
0x180005428  xor     edx, edx; bInheritHandle
0x18000542a  mov     ecx, esi; dwDesiredAccess
0x18000542c  call    cs:__imp_OpenSemaphoreW
0x180005432  mov     rdi, rax
0x180005435  test    rax, rax
0x180005438  jz      loc_1800054C6
0x18000543e  lea     rdx, [rsp+280h+var_260]; int *
0x180005443  mov     rcx, rax; hHandle
0x180005446  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000544b  mov     esi, eax
0x18000544d  test    eax, eax
0x18000544f  jns     short loc_180005492
0x180005451  mov     rcx, [rbp+188h]; this
0x180005458  lea     r8, aWil; "wil"
0x18000545f  mov     r9d, eax; char *
0x180005462  mov     edx, 0DEh; void *
0x180005467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000546c  mov     rcx, rdi; hObject
0x18000546f  call    cs:__imp_CloseHandle
0x180005475  test    eax, eax
0x180005477  jz      loc_180005572
0x18000547d  mov     rcx, rbx; hObject
0x180005480  call    cs:__imp_CloseHandle
0x180005486  test    eax, eax
0x180005488  jz      loc_180005584
0x18000548e  mov     eax, esi
0x180005490  jmp     short loc_18000550B
0x180005492  mov     rcx, rdi; hObject
0x180005495  call    cs:__imp_CloseHandle
0x18000549b  test    eax, eax
0x18000549d  jz      loc_18000552A
0x1800054a3  movsxd  rax, [rsp+280h+var_25C]
0x1800054a8  movsxd  rcx, [rsp+280h+var_260]
0x1800054ad  shl     rcx, 1Fh
0x1800054b1  or      rcx, rax
0x1800054b4  mov     [r14], rcx
0x1800054b7  mov     rcx, rbx; hObject
0x1800054ba  call    cs:__imp_CloseHandle
0x1800054c0  test    eax, eax
0x1800054c2  jz      short loc_18000553C
0x1800054c4  jmp     short loc_1800054F6
0x1800054c6  mov     rcx, [rbp+188h]; this
0x1800054cd  mov     edx, 0DCh; void *
0x1800054d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800054d7  mov     rcx, rbx; hObject
0x1800054da  mov     edi, eax
0x1800054dc  call    cs:__imp_CloseHandle
0x1800054e2  test    eax, eax
0x1800054e4  jz      short loc_18000554E
0x1800054e6  jmp     loc_18000540B
0x1800054eb  call    cs:__imp_GetLastError
0x1800054f1  cmp     eax, 2
0x1800054f4  jnz     short loc_1800054FA
0x1800054f6  xor     eax, eax
0x1800054f8  jmp     short loc_18000550B
0x1800054fa  mov     rcx, [rbp+188h]; this
0x180005501  mov     edx, 0D0h; void *
0x180005506  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000550b  mov     rcx, [rbp+180h+var_40]
0x180005512  xor     rcx, rsp; StackCookie
0x180005515  call    __security_check_cookie
0x18000551a  add     rsp, 258h
0x180005521  pop     r15
0x180005523  pop     r14
0x180005525  pop     rdi
0x180005526  pop     rsi
0x180005527  pop     rbx
0x180005528  pop     rbp
0x180005529  retn
0x18000552a  mov     rcx, [rbp+188h]; this
0x180005531  mov     edx, 0A0Bh; void *
0x180005536  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000553c  mov     rcx, [rbp+188h]; this
0x180005543  mov     edx, 0A0Bh; void *
0x180005548  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000554e  mov     rcx, [rbp+188h]; this
0x180005555  mov     edx, 0A0Bh; void *
0x18000555a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005560  mov     rcx, [rbp+188h]; this
0x180005567  mov     edx, 0A0Bh; void *
0x18000556c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005572  mov     rcx, [rbp+188h]; this
0x180005579  mov     edx, 0A0Bh; void *
0x18000557e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005584  mov     rcx, [rbp+188h]; this
0x18000558b  mov     edx, 0A0Bh; void *
0x180005590  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
