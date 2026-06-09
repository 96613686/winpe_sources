# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000940c`
- end: `0x18000968f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004a28`
- `0x180004df8`

## callees

- `0x180001cf0`
- `0x1800063d4`
- `0x180008594`
- `0x1800085bc`
- `0x18000940c`
- `0x180009cdc`
- `0x18000a51c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800094f0`
- `KERNEL32!CloseHandle` at `0x180009568`
- `KERNEL32!CloseHandle` at `0x180009579`
- `KERNEL32!CloseHandle` at `0x18000958e`
- `KERNEL32!CloseHandle` at `0x1800095b3`
- `KERNEL32!CloseHandle` at `0x1800095d5`
- `KERNEL32!CloseHandle` at `0x1800094f0`
- `KERNEL32!CloseHandle` at `0x180009568`
- `KERNEL32!CloseHandle` at `0x180009579`
- `KERNEL32!CloseHandle` at `0x18000958e`
- `KERNEL32!CloseHandle` at `0x1800095b3`
- `KERNEL32!CloseHandle` at `0x1800095d5`
- `KERNEL32!OpenSemaphoreW` at `0x1800094a3`
- `KERNEL32!OpenSemaphoreW` at `0x180009525`
- `KERNEL32!OpenSemaphoreW` at `0x1800094a3`
- `KERNEL32!OpenSemaphoreW` at `0x180009525`
- `KERNEL32!GetLastError` at `0x1800095e4`
- `KERNEL32!GetLastError` at `0x1800095e4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  wchar_t *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  unsigned int v17; // r8d
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35[3]; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t pszDest[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = pszDest;
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
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v34);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(pszDest, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v34);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000940c  push    rbp
0x18000940e  push    rbx
0x18000940f  push    rsi
0x180009410  push    rdi
0x180009411  push    r14
0x180009413  push    r15
0x180009415  lea     rbp, [rsp-158h]
0x18000941d  sub     rsp, 258h
0x180009424  mov     rax, cs:__security_cookie
0x18000942b  xor     rax, rsp
0x18000942e  mov     [rbp+180h+var_40], rax
0x180009435  xor     r15d, r15d
0x180009438  lea     rax, [rsp+280h+pszDest]
0x18000943d  mov     esi, 104h
0x180009442  mov     [r8], r15
0x180009445  mov     edx, esi
0x180009447  mov     r14, r8
0x18000944a  mov     r9d, 7FFFFFFEh
0x180009450  test    r9, r9
0x180009453  jz      short loc_180009474
0x180009455  movzx   r8d, word ptr [rcx]
0x180009459  test    r8w, r8w
0x18000945d  jz      short loc_180009474
0x18000945f  mov     [rax], r8w
0x180009463  add     rcx, 2
0x180009467  add     rax, 2
0x18000946b  dec     r9
0x18000946e  sub     rdx, 1
0x180009472  jnz     short loc_180009450
0x180009474  test    rdx, rdx
0x180009477  lea     rcx, [rax-2]
0x18000947b  lea     r8, aP0; "_p0"
0x180009482  mov     rdx, rsi; cchDest
0x180009485  cmovnz  rcx, rax
0x180009489  mov     [rcx], r15w
0x18000948d  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180009492  call    StringCchCatW
0x180009497  lea     r8, [rsp+280h+pszDest]; lpName
0x18000949c  xor     edx, edx; bInheritHandle
0x18000949e  mov     ecx, 1F0003h; dwDesiredAccess
0x1800094a3  call    cs:__imp_OpenSemaphoreW
0x1800094a9  mov     rbx, rax
0x1800094ac  test    rax, rax
0x1800094af  jz      loc_1800095E4
0x1800094b5  lea     rdx, [rsp+280h+var_25C]; int *
0x1800094ba  mov     [rsp+280h+var_25C], r15d
0x1800094bf  mov     rcx, rax; hHandle
0x1800094c2  mov     [rsp+280h+var_260], r15d; int
0x1800094c7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800094cc  mov     edi, eax
0x1800094ce  test    eax, eax
0x1800094d0  jns     short loc_180009505
0x1800094d2  mov     rcx, [rbp+188h]; this
0x1800094d9  lea     r8, aWil; "wil"
0x1800094e0  mov     r9d, eax; char *
0x1800094e3  mov     edx, 0D6h; void *
0x1800094e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094ed  mov     rcx, rbx; hObject
0x1800094f0  call    cs:__imp_CloseHandle
0x1800094f6  test    eax, eax
0x1800094f8  jz      loc_180009659
0x1800094fe  mov     eax, edi
0x180009500  jmp     loc_180009604
0x180009505  lea     r8, asc_18006E308; "h"
0x18000950c  mov     rdx, rsi; cchDest
0x18000950f  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180009514  call    StringCchCatW
0x180009519  lea     r8, [rsp+280h+pszDest]; lpName
0x18000951e  xor     edx, edx; bInheritHandle
0x180009520  mov     ecx, 1F0003h; dwDesiredAccess
0x180009525  call    cs:__imp_OpenSemaphoreW
0x18000952b  mov     rdi, rax
0x18000952e  test    rax, rax
0x180009531  jz      loc_1800095BF
0x180009537  lea     rdx, [rsp+280h+var_260]; int *
0x18000953c  mov     rcx, rax; hHandle
0x18000953f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009544  mov     esi, eax
0x180009546  test    eax, eax
0x180009548  jns     short loc_18000958B
0x18000954a  mov     rcx, [rbp+188h]; this
0x180009551  lea     r8, aWil; "wil"
0x180009558  mov     r9d, eax; char *
0x18000955b  mov     edx, 0DEh; void *
0x180009560  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009565  mov     rcx, rdi; hObject
0x180009568  call    cs:__imp_CloseHandle
0x18000956e  test    eax, eax
0x180009570  jz      loc_18000966B
0x180009576  mov     rcx, rbx; hObject
0x180009579  call    cs:__imp_CloseHandle
0x18000957f  test    eax, eax
0x180009581  jz      loc_18000967D
0x180009587  mov     eax, esi
0x180009589  jmp     short loc_180009604
0x18000958b  mov     rcx, rdi; hObject
0x18000958e  call    cs:__imp_CloseHandle
0x180009594  test    eax, eax
0x180009596  jz      loc_180009623
0x18000959c  movsxd  rax, [rsp+280h+var_25C]
0x1800095a1  movsxd  rcx, [rsp+280h+var_260]
0x1800095a6  shl     rcx, 1Fh
0x1800095aa  or      rcx, rax
0x1800095ad  mov     [r14], rcx
0x1800095b0  mov     rcx, rbx; hObject
0x1800095b3  call    cs:__imp_CloseHandle
0x1800095b9  test    eax, eax
0x1800095bb  jz      short loc_180009635
0x1800095bd  jmp     short loc_1800095EF
0x1800095bf  mov     rcx, [rbp+188h]; this
0x1800095c6  mov     edx, 0DCh; void *
0x1800095cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800095d0  mov     rcx, rbx; hObject
0x1800095d3  mov     edi, eax
0x1800095d5  call    cs:__imp_CloseHandle
0x1800095db  test    eax, eax
0x1800095dd  jz      short loc_180009647
0x1800095df  jmp     loc_1800094FE
0x1800095e4  call    cs:__imp_GetLastError
0x1800095ea  cmp     eax, 2
0x1800095ed  jnz     short loc_1800095F3
0x1800095ef  xor     eax, eax
0x1800095f1  jmp     short loc_180009604
0x1800095f3  mov     rcx, [rbp+188h]; this
0x1800095fa  mov     edx, 0D0h; void *
0x1800095ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009604  mov     rcx, [rbp+180h+var_40]
0x18000960b  xor     rcx, rsp; StackCookie
0x18000960e  call    __security_check_cookie
0x180009613  add     rsp, 258h
0x18000961a  pop     r15
0x18000961c  pop     r14
0x18000961e  pop     rdi
0x18000961f  pop     rsi
0x180009620  pop     rbx
0x180009621  pop     rbp
0x180009622  retn
0x180009623  mov     rcx, [rbp+188h]; this
0x18000962a  mov     edx, 0A0Bh; void *
0x18000962f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009635  mov     rcx, [rbp+188h]; this
0x18000963c  mov     edx, 0A0Bh; void *
0x180009641  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009647  mov     rcx, [rbp+188h]; this
0x18000964e  mov     edx, 0A0Bh; void *
0x180009653  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009659  mov     rcx, [rbp+188h]; this
0x180009660  mov     edx, 0A0Bh; void *
0x180009665  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000966b  mov     rcx, [rbp+188h]; this
0x180009672  mov     edx, 0A0Bh; void *
0x180009677  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000967d  mov     rcx, [rbp+188h]; this
0x180009684  mov     edx, 0A0Bh; void *
0x180009689  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
