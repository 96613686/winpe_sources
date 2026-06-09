# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000521c`
- end: `0x140005496`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140002d18`
- `0x140006064`

## callees

- `0x140001530`
- `0x140003d54`
- `0x140004744`
- `0x140004764`
- `0x1400050a4`
- `0x14000521c`
- `0x1400055ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400052b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000532c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400052b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000532c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400053eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000536f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005380`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400053ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400053dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000536f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005380`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400053ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400053dc`

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
0x14000521c  push    rbp
0x14000521e  push    rbx
0x14000521f  push    rsi
0x140005220  push    rdi
0x140005221  push    r14
0x140005223  push    r15
0x140005225  lea     rbp, [rsp-158h]
0x14000522d  sub     rsp, 258h
0x140005234  mov     rax, cs:__security_cookie
0x14000523b  xor     rax, rsp
0x14000523e  mov     [rbp+180h+var_40], rax
0x140005245  xor     r15d, r15d
0x140005248  lea     rax, [rsp+280h+Name]
0x14000524d  mov     [r8], r15
0x140005250  mov     r14, r8
0x140005253  mov     edx, 104h
0x140005258  mov     r9d, 7FFFFFFEh
0x14000525e  test    r9, r9
0x140005261  jz      short loc_140005282
0x140005263  movzx   r8d, word ptr [rcx]
0x140005267  test    r8w, r8w
0x14000526b  jz      short loc_140005282
0x14000526d  mov     [rax], r8w
0x140005271  add     rcx, 2
0x140005275  add     rax, 2
0x140005279  dec     r9
0x14000527c  sub     rdx, 1; unsigned __int64
0x140005280  jnz     short loc_14000525E
0x140005282  test    rdx, rdx
0x140005285  lea     rcx, [rax-2]
0x140005289  lea     r8, aP0; "_p0"
0x140005290  cmovnz  rcx, rax
0x140005294  mov     [rcx], r15w
0x140005298  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000529d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400052a2  mov     esi, 1F0003h
0x1400052a7  lea     r8, [rsp+280h+Name]; lpName
0x1400052ac  mov     ecx, esi; dwDesiredAccess
0x1400052ae  xor     edx, edx; bInheritHandle
0x1400052b0  call    cs:__imp_OpenSemaphoreW
0x1400052b6  mov     rbx, rax
0x1400052b9  test    rax, rax
0x1400052bc  jz      loc_1400053EB
0x1400052c2  lea     rdx, [rsp+280h+var_25C]; int *
0x1400052c7  mov     [rsp+280h+var_25C], r15d
0x1400052cc  mov     rcx, rax; hHandle
0x1400052cf  mov     [rsp+280h+var_260], r15d; int
0x1400052d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400052d9  mov     edi, eax
0x1400052db  test    eax, eax
0x1400052dd  jns     short loc_140005312
0x1400052df  mov     rcx, [rbp+188h]; this
0x1400052e6  lea     r8, aWil; "wil"
0x1400052ed  mov     r9d, eax; char *
0x1400052f0  mov     edx, 0D6h; void *
0x1400052f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400052fa  mov     rcx, rbx; hObject
0x1400052fd  call    cs:__imp_CloseHandle
0x140005303  test    eax, eax
0x140005305  jz      loc_140005460
0x14000530b  mov     eax, edi
0x14000530d  jmp     loc_14000540B
0x140005312  lea     r8, asc_14000A900; "h"
0x140005319  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000531e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005323  lea     r8, [rsp+280h+Name]; lpName
0x140005328  xor     edx, edx; bInheritHandle
0x14000532a  mov     ecx, esi; dwDesiredAccess
0x14000532c  call    cs:__imp_OpenSemaphoreW
0x140005332  mov     rdi, rax
0x140005335  test    rax, rax
0x140005338  jz      loc_1400053C6
0x14000533e  lea     rdx, [rsp+280h+var_260]; int *
0x140005343  mov     rcx, rax; hHandle
0x140005346  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000534b  mov     esi, eax
0x14000534d  test    eax, eax
0x14000534f  jns     short loc_140005392
0x140005351  mov     rcx, [rbp+188h]; this
0x140005358  lea     r8, aWil; "wil"
0x14000535f  mov     r9d, eax; char *
0x140005362  mov     edx, 0DEh; void *
0x140005367  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000536c  mov     rcx, rdi; hObject
0x14000536f  call    cs:__imp_CloseHandle
0x140005375  test    eax, eax
0x140005377  jz      loc_140005472
0x14000537d  mov     rcx, rbx; hObject
0x140005380  call    cs:__imp_CloseHandle
0x140005386  test    eax, eax
0x140005388  jz      loc_140005484
0x14000538e  mov     eax, esi
0x140005390  jmp     short loc_14000540B
0x140005392  mov     rcx, rdi; hObject
0x140005395  call    cs:__imp_CloseHandle
0x14000539b  test    eax, eax
0x14000539d  jz      loc_14000542A
0x1400053a3  movsxd  rax, [rsp+280h+var_25C]
0x1400053a8  movsxd  rcx, [rsp+280h+var_260]
0x1400053ad  shl     rcx, 1Fh
0x1400053b1  or      rcx, rax
0x1400053b4  mov     [r14], rcx
0x1400053b7  mov     rcx, rbx; hObject
0x1400053ba  call    cs:__imp_CloseHandle
0x1400053c0  test    eax, eax
0x1400053c2  jz      short loc_14000543C
0x1400053c4  jmp     short loc_1400053F6
0x1400053c6  mov     rcx, [rbp+188h]; this
0x1400053cd  mov     edx, 0DCh; void *
0x1400053d2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400053d7  mov     rcx, rbx; hObject
0x1400053da  mov     edi, eax
0x1400053dc  call    cs:__imp_CloseHandle
0x1400053e2  test    eax, eax
0x1400053e4  jz      short loc_14000544E
0x1400053e6  jmp     loc_14000530B
0x1400053eb  call    cs:__imp_GetLastError
0x1400053f1  cmp     eax, 2
0x1400053f4  jnz     short loc_1400053FA
0x1400053f6  xor     eax, eax
0x1400053f8  jmp     short loc_14000540B
0x1400053fa  mov     rcx, [rbp+188h]; this
0x140005401  mov     edx, 0D0h; void *
0x140005406  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000540b  mov     rcx, [rbp+180h+var_40]
0x140005412  xor     rcx, rsp; StackCookie
0x140005415  call    __security_check_cookie
0x14000541a  add     rsp, 258h
0x140005421  pop     r15
0x140005423  pop     r14
0x140005425  pop     rdi
0x140005426  pop     rsi
0x140005427  pop     rbx
0x140005428  pop     rbp
0x140005429  retn
0x14000542a  mov     rcx, [rbp+188h]; this
0x140005431  mov     edx, 0A0Bh; void *
0x140005436  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000543c  mov     rcx, [rbp+188h]; this
0x140005443  mov     edx, 0A0Bh; void *
0x140005448  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000544e  mov     rcx, [rbp+188h]; this
0x140005455  mov     edx, 0A0Bh; void *
0x14000545a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005460  mov     rcx, [rbp+188h]; this
0x140005467  mov     edx, 0A0Bh; void *
0x14000546c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005472  mov     rcx, [rbp+188h]; this
0x140005479  mov     edx, 0A0Bh; void *
0x14000547e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005484  mov     rcx, [rbp+188h]; this
0x14000548b  mov     edx, 0A0Bh; void *
0x140005490  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
