# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000823c`
- end: `0x1400084a8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003a78`
- `0x140003e1c`

## callees

- `0x1400016f0`
- `0x140005364`
- `0x1400072c4`
- `0x1400072e4`
- `0x140007d28`
- `0x14000823c`
- `0x140008afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400082d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008345`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400082d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008316`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008381`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008316`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008381`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083ee`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
  unsigned int v24; // esi
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
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x14000823c  push    rbp
0x14000823e  push    rbx
0x14000823f  push    rsi
0x140008240  push    rdi
0x140008241  push    r14
0x140008243  push    r15
0x140008245  lea     rbp, [rsp-158h]
0x14000824d  sub     rsp, 258h
0x140008254  mov     rax, cs:__security_cookie
0x14000825b  xor     rax, rsp
0x14000825e  mov     [rbp+180h+var_40], rax
0x140008265  xor     r15d, r15d
0x140008268  lea     rax, [rsp+280h+Name]
0x14000826d  mov     [r8], r15
0x140008270  mov     r14, r8
0x140008273  mov     edx, 104h
0x140008278  mov     r9d, 7FFFFFFEh
0x14000827e  test    r9, r9
0x140008281  jz      short loc_1400082A2
0x140008283  movzx   r8d, word ptr [rcx]
0x140008287  test    r8w, r8w
0x14000828b  jz      short loc_1400082A2
0x14000828d  mov     [rax], r8w
0x140008291  add     rcx, 2
0x140008295  add     rax, 2
0x140008299  dec     r9
0x14000829c  sub     rdx, 1; unsigned __int64
0x1400082a0  jnz     short loc_14000827E
0x1400082a2  test    rdx, rdx
0x1400082a5  lea     rcx, [rax-2]
0x1400082a9  lea     r8, aP0; "_p0"
0x1400082b0  cmovnz  rcx, rax
0x1400082b4  mov     [rcx], r15w
0x1400082b8  lea     rcx, [rsp+280h+Name]; wchar_t *
0x1400082bd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400082c2  mov     esi, 1F0003h
0x1400082c7  lea     r8, [rsp+280h+Name]; lpName
0x1400082cc  mov     ecx, esi; dwDesiredAccess
0x1400082ce  xor     edx, edx; bInheritHandle
0x1400082d0  call    cs:__imp_OpenSemaphoreW
0x1400082d6  mov     rbx, rax
0x1400082d9  test    rax, rax
0x1400082dc  jz      loc_1400083FD
0x1400082e2  lea     rdx, [rsp+280h+var_25C]; int *
0x1400082e7  mov     [rsp+280h+var_25C], r15d
0x1400082ec  mov     rcx, rax; hHandle
0x1400082ef  mov     [rsp+280h+var_260], r15d; int
0x1400082f4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400082f9  mov     edi, eax
0x1400082fb  test    eax, eax
0x1400082fd  jns     short loc_14000832B
0x1400082ff  mov     rcx, [rbp+188h]; this
0x140008306  mov     r9d, eax; char *
0x140008309  mov     edx, 0D6h; void *
0x14000830e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008313  mov     rcx, rbx; hObject
0x140008316  call    cs:__imp_CloseHandle
0x14000831c  test    eax, eax
0x14000831e  jz      loc_140008472
0x140008324  mov     eax, edi
0x140008326  jmp     loc_14000841D
0x14000832b  lea     r8, asc_14000DA80; "h"
0x140008332  lea     rcx, [rsp+280h+Name]; wchar_t *
0x140008337  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000833c  lea     r8, [rsp+280h+Name]; lpName
0x140008341  xor     edx, edx; bInheritHandle
0x140008343  mov     ecx, esi; dwDesiredAccess
0x140008345  call    cs:__imp_OpenSemaphoreW
0x14000834b  mov     rdi, rax
0x14000834e  test    rax, rax
0x140008351  jz      loc_1400083D8
0x140008357  lea     rdx, [rsp+280h+var_260]; int *
0x14000835c  mov     rcx, rax; hHandle
0x14000835f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008364  mov     esi, eax
0x140008366  test    eax, eax
0x140008368  jns     short loc_1400083A4
0x14000836a  mov     rcx, [rbp+188h]; this
0x140008371  mov     r9d, eax; char *
0x140008374  mov     edx, 0DEh; void *
0x140008379  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000837e  mov     rcx, rdi; hObject
0x140008381  call    cs:__imp_CloseHandle
0x140008387  test    eax, eax
0x140008389  jz      loc_140008484
0x14000838f  mov     rcx, rbx; hObject
0x140008392  call    cs:__imp_CloseHandle
0x140008398  test    eax, eax
0x14000839a  jz      loc_140008496
0x1400083a0  mov     eax, esi
0x1400083a2  jmp     short loc_14000841D
0x1400083a4  mov     rcx, rdi; hObject
0x1400083a7  call    cs:__imp_CloseHandle
0x1400083ad  test    eax, eax
0x1400083af  jz      loc_14000843C
0x1400083b5  movsxd  rax, [rsp+280h+var_25C]
0x1400083ba  movsxd  rcx, [rsp+280h+var_260]
0x1400083bf  shl     rcx, 1Fh
0x1400083c3  or      rcx, rax
0x1400083c6  mov     [r14], rcx
0x1400083c9  mov     rcx, rbx; hObject
0x1400083cc  call    cs:__imp_CloseHandle
0x1400083d2  test    eax, eax
0x1400083d4  jz      short loc_14000844E
0x1400083d6  jmp     short loc_140008408
0x1400083d8  mov     rcx, [rbp+188h]; this
0x1400083df  mov     edx, 0DCh; void *
0x1400083e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400083e9  mov     rcx, rbx; hObject
0x1400083ec  mov     edi, eax
0x1400083ee  call    cs:__imp_CloseHandle
0x1400083f4  test    eax, eax
0x1400083f6  jz      short loc_140008460
0x1400083f8  jmp     loc_140008324
0x1400083fd  call    cs:__imp_GetLastError
0x140008403  cmp     eax, 2
0x140008406  jnz     short loc_14000840C
0x140008408  xor     eax, eax
0x14000840a  jmp     short loc_14000841D
0x14000840c  mov     rcx, [rbp+188h]; this
0x140008413  mov     edx, 0D0h; void *
0x140008418  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000841d  mov     rcx, [rbp+180h+var_40]
0x140008424  xor     rcx, rsp; StackCookie
0x140008427  call    __security_check_cookie
0x14000842c  add     rsp, 258h
0x140008433  pop     r15
0x140008435  pop     r14
0x140008437  pop     rdi
0x140008438  pop     rsi
0x140008439  pop     rbx
0x14000843a  pop     rbp
0x14000843b  retn
0x14000843c  mov     rcx, [rbp+188h]; this
0x140008443  mov     edx, 0A0Bh; void *
0x140008448  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000844e  mov     rcx, [rbp+188h]; this
0x140008455  mov     edx, 0A0Bh; void *
0x14000845a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008460  mov     rcx, [rbp+188h]; this
0x140008467  mov     edx, 0A0Bh; void *
0x14000846c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008472  mov     rcx, [rbp+188h]; this
0x140008479  mov     edx, 0A0Bh; void *
0x14000847e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008484  mov     rcx, [rbp+188h]; this
0x14000848b  mov     edx, 0A0Bh; void *
0x140008490  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008496  mov     rcx, [rbp+188h]; this
0x14000849d  mov     edx, 0A0Bh; void *
0x1400084a2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
