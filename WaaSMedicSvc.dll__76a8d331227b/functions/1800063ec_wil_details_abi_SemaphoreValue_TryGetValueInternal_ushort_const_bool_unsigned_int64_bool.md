# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800063ec`
- end: `0x18000667b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003dd8`

## callees

- `0x180002200`
- `0x180004d64`
- `0x180005964`
- `0x180005984`
- `0x180006260`
- `0x1800063ec`
- `0x1800067dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006480`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006480`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800064fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000653f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006568`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000658d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800064cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000653f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006568`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000658d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800065ba`

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
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
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
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
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
0x1800063ec  push    rbp
0x1800063ee  push    rbx
0x1800063ef  push    rsi
0x1800063f0  push    rdi
0x1800063f1  push    r14
0x1800063f3  push    r15
0x1800063f5  lea     rbp, [rsp-158h]
0x1800063fd  sub     rsp, 258h
0x180006404  mov     rax, cs:__security_cookie
0x18000640b  xor     rax, rsp
0x18000640e  mov     [rbp+180h+var_40], rax
0x180006415  xor     r15d, r15d
0x180006418  lea     rax, [rsp+280h+Name]
0x18000641d  mov     [r8], r15
0x180006420  mov     r14, r8
0x180006423  mov     edx, 104h
0x180006428  mov     r9d, 7FFFFFFEh
0x18000642e  test    r9, r9
0x180006431  jz      short loc_180006452
0x180006433  movzx   r8d, word ptr [rcx]
0x180006437  test    r8w, r8w
0x18000643b  jz      short loc_180006452
0x18000643d  mov     [rax], r8w
0x180006441  add     rcx, 2
0x180006445  add     rax, 2
0x180006449  dec     r9
0x18000644c  sub     rdx, 1; unsigned __int64
0x180006450  jnz     short loc_18000642E
0x180006452  test    rdx, rdx
0x180006455  lea     rcx, [rax-2]
0x180006459  lea     r8, aP0; "_p0"
0x180006460  cmovnz  rcx, rax
0x180006464  mov     [rcx], r15w
0x180006468  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000646d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006472  mov     esi, 1F0003h
0x180006477  lea     r8, [rsp+280h+Name]; lpName
0x18000647c  mov     ecx, esi; dwDesiredAccess
0x18000647e  xor     edx, edx; bInheritHandle
0x180006480  call    cs:__imp_OpenSemaphoreW
0x180006486  mov     rbx, rax
0x180006489  test    rax, rax
0x18000648c  jz      loc_1800065C9
0x180006492  lea     rdx, [rsp+280h+var_25C]; int *
0x180006497  mov     [rsp+280h+var_25C], r15d
0x18000649c  mov     rcx, rax; hHandle
0x18000649f  mov     [rsp+280h+var_260], r15d; int
0x1800064a4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800064a9  mov     edi, eax
0x1800064ab  test    eax, eax
0x1800064ad  jns     short loc_1800064E2
0x1800064af  mov     rcx, [rbp+188h]; this
0x1800064b6  lea     r8, aWil; "wil"
0x1800064bd  mov     r9d, eax; char *
0x1800064c0  mov     edx, 0D6h; void *
0x1800064c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064ca  mov     rcx, rbx; hObject
0x1800064cd  call    cs:__imp_CloseHandle
0x1800064d3  test    eax, eax
0x1800064d5  jz      loc_180006645
0x1800064db  mov     eax, edi
0x1800064dd  jmp     loc_1800065F0
0x1800064e2  lea     r8, asc_18000EDD8; "h"
0x1800064e9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800064ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800064f3  lea     r8, [rsp+280h+Name]; lpName
0x1800064f8  xor     edx, edx; bInheritHandle
0x1800064fa  mov     ecx, esi; dwDesiredAccess
0x1800064fc  call    cs:__imp_OpenSemaphoreW
0x180006502  mov     rdi, rax
0x180006505  test    rax, rax
0x180006508  jz      loc_18000659D
0x18000650e  lea     rdx, [rsp+280h+var_260]; int *
0x180006513  mov     rcx, rax; hHandle
0x180006516  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000651b  mov     esi, eax
0x18000651d  test    eax, eax
0x18000651f  jns     short loc_180006565
0x180006521  mov     rcx, [rbp+188h]; this
0x180006528  lea     r8, aWil; "wil"
0x18000652f  mov     r9d, eax; char *
0x180006532  mov     edx, 0DEh; void *
0x180006537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000653c  mov     rcx, rdi; hObject
0x18000653f  call    cs:__imp_CloseHandle
0x180006545  test    eax, eax
0x180006547  jz      loc_180006657
0x18000654d  mov     rcx, rbx; hObject
0x180006550  call    cs:__imp_CloseHandle
0x180006556  test    eax, eax
0x180006558  jz      loc_180006669
0x18000655e  mov     eax, esi
0x180006560  jmp     loc_1800065F0
0x180006565  mov     rcx, rdi; hObject
0x180006568  call    cs:__imp_CloseHandle
0x18000656e  test    eax, eax
0x180006570  jz      loc_18000660F
0x180006576  movsxd  rax, [rsp+280h+var_25C]
0x18000657b  movsxd  rcx, [rsp+280h+var_260]
0x180006580  shl     rcx, 1Fh
0x180006584  or      rcx, rax
0x180006587  mov     [r14], rcx
0x18000658a  mov     rcx, rbx; hObject
0x18000658d  call    cs:__imp_CloseHandle
0x180006593  test    eax, eax
0x180006595  jz      loc_180006621
0x18000659b  jmp     short loc_1800065D4
0x18000659d  mov     rcx, [rbp+188h]; this
0x1800065a4  lea     r8, aWil; "wil"
0x1800065ab  mov     edx, 0DCh; void *
0x1800065b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800065b5  mov     rcx, rbx; hObject
0x1800065b8  mov     edi, eax
0x1800065ba  call    cs:__imp_CloseHandle
0x1800065c0  test    eax, eax
0x1800065c2  jz      short loc_180006633
0x1800065c4  jmp     loc_1800064DB
0x1800065c9  call    cs:__imp_GetLastError
0x1800065cf  cmp     eax, 2
0x1800065d2  jnz     short loc_1800065D8
0x1800065d4  xor     eax, eax
0x1800065d6  jmp     short loc_1800065F0
0x1800065d8  mov     rcx, [rbp+188h]; this
0x1800065df  lea     r8, aWil; "wil"
0x1800065e6  mov     edx, 0D0h; void *
0x1800065eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800065f0  mov     rcx, [rbp+180h+var_40]
0x1800065f7  xor     rcx, rsp; StackCookie
0x1800065fa  call    __security_check_cookie
0x1800065ff  add     rsp, 258h
0x180006606  pop     r15
0x180006608  pop     r14
0x18000660a  pop     rdi
0x18000660b  pop     rsi
0x18000660c  pop     rbx
0x18000660d  pop     rbp
0x18000660e  retn
0x18000660f  mov     rcx, [rbp+188h]; this
0x180006616  mov     edx, 0A0Bh; void *
0x18000661b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006621  mov     rcx, [rbp+188h]; this
0x180006628  mov     edx, 0A0Bh; void *
0x18000662d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006633  mov     rcx, [rbp+188h]; this
0x18000663a  mov     edx, 0A0Bh; void *
0x18000663f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006645  mov     rcx, [rbp+188h]; this
0x18000664c  mov     edx, 0A0Bh; void *
0x180006651  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006657  mov     rcx, [rbp+188h]; this
0x18000665e  mov     edx, 0A0Bh; void *
0x180006663  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006669  mov     rcx, [rbp+188h]; this
0x180006670  mov     edx, 0A0Bh; void *
0x180006675  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
