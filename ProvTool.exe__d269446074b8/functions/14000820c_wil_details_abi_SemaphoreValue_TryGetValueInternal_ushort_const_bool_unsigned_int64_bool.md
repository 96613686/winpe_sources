# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000820c`
- end: `0x14000849b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003de0`

## callees

- `0x140005854`
- `0x140007714`
- `0x140007734`
- `0x140008084`
- `0x14000820c`
- `0x140008804`
- `0x14000ded0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400082a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000831c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400082a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000831c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400083e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400082ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000835f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008388`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400082ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000835f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008370`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008388`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400083da`

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
0x14000820c  push    rbp
0x14000820e  push    rbx
0x14000820f  push    rsi
0x140008210  push    rdi
0x140008211  push    r14
0x140008213  push    r15
0x140008215  lea     rbp, [rsp-158h]
0x14000821d  sub     rsp, 258h
0x140008224  mov     rax, cs:__security_cookie
0x14000822b  xor     rax, rsp
0x14000822e  mov     [rbp+180h+var_40], rax
0x140008235  xor     r15d, r15d
0x140008238  lea     rax, [rsp+280h+Name]
0x14000823d  mov     [r8], r15
0x140008240  mov     r14, r8
0x140008243  mov     edx, 104h
0x140008248  mov     r9d, 7FFFFFFEh
0x14000824e  test    r9, r9
0x140008251  jz      short loc_140008272
0x140008253  movzx   r8d, word ptr [rcx]
0x140008257  test    r8w, r8w
0x14000825b  jz      short loc_140008272
0x14000825d  mov     [rax], r8w
0x140008261  add     rcx, 2
0x140008265  add     rax, 2
0x140008269  dec     r9
0x14000826c  sub     rdx, 1; unsigned __int64
0x140008270  jnz     short loc_14000824E
0x140008272  test    rdx, rdx
0x140008275  lea     rcx, [rax-2]
0x140008279  lea     r8, aP0; "_p0"
0x140008280  cmovnz  rcx, rax
0x140008284  mov     [rcx], r15w
0x140008288  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000828d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008292  mov     esi, 1F0003h
0x140008297  lea     r8, [rsp+280h+Name]; lpName
0x14000829c  mov     ecx, esi; dwDesiredAccess
0x14000829e  xor     edx, edx; bInheritHandle
0x1400082a0  call    cs:__imp_OpenSemaphoreW
0x1400082a6  mov     rbx, rax
0x1400082a9  test    rax, rax
0x1400082ac  jz      loc_1400083E9
0x1400082b2  lea     rdx, [rsp+280h+var_25C]; int *
0x1400082b7  mov     [rsp+280h+var_25C], r15d
0x1400082bc  mov     rcx, rax; hHandle
0x1400082bf  mov     [rsp+280h+var_260], r15d; int
0x1400082c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400082c9  mov     edi, eax
0x1400082cb  test    eax, eax
0x1400082cd  jns     short loc_140008302
0x1400082cf  mov     rcx, [rbp+188h]; this
0x1400082d6  lea     r8, aWil; "wil"
0x1400082dd  mov     r9d, eax; char *
0x1400082e0  mov     edx, 0D6h; void *
0x1400082e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400082ea  mov     rcx, rbx; hObject
0x1400082ed  call    cs:__imp_CloseHandle
0x1400082f3  test    eax, eax
0x1400082f5  jz      loc_140008465
0x1400082fb  mov     eax, edi
0x1400082fd  jmp     loc_140008410
0x140008302  lea     r8, asc_140012120; "h"
0x140008309  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000830e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008313  lea     r8, [rsp+280h+Name]; lpName
0x140008318  xor     edx, edx; bInheritHandle
0x14000831a  mov     ecx, esi; dwDesiredAccess
0x14000831c  call    cs:__imp_OpenSemaphoreW
0x140008322  mov     rdi, rax
0x140008325  test    rax, rax
0x140008328  jz      loc_1400083BD
0x14000832e  lea     rdx, [rsp+280h+var_260]; int *
0x140008333  mov     rcx, rax; hHandle
0x140008336  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000833b  mov     esi, eax
0x14000833d  test    eax, eax
0x14000833f  jns     short loc_140008385
0x140008341  mov     rcx, [rbp+188h]; this
0x140008348  lea     r8, aWil; "wil"
0x14000834f  mov     r9d, eax; char *
0x140008352  mov     edx, 0DEh; void *
0x140008357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000835c  mov     rcx, rdi; hObject
0x14000835f  call    cs:__imp_CloseHandle
0x140008365  test    eax, eax
0x140008367  jz      loc_140008477
0x14000836d  mov     rcx, rbx; hObject
0x140008370  call    cs:__imp_CloseHandle
0x140008376  test    eax, eax
0x140008378  jz      loc_140008489
0x14000837e  mov     eax, esi
0x140008380  jmp     loc_140008410
0x140008385  mov     rcx, rdi; hObject
0x140008388  call    cs:__imp_CloseHandle
0x14000838e  test    eax, eax
0x140008390  jz      loc_14000842F
0x140008396  movsxd  rax, [rsp+280h+var_25C]
0x14000839b  movsxd  rcx, [rsp+280h+var_260]
0x1400083a0  shl     rcx, 1Fh
0x1400083a4  or      rcx, rax
0x1400083a7  mov     [r14], rcx
0x1400083aa  mov     rcx, rbx; hObject
0x1400083ad  call    cs:__imp_CloseHandle
0x1400083b3  test    eax, eax
0x1400083b5  jz      loc_140008441
0x1400083bb  jmp     short loc_1400083F4
0x1400083bd  mov     rcx, [rbp+188h]; this
0x1400083c4  lea     r8, aWil; "wil"
0x1400083cb  mov     edx, 0DCh; void *
0x1400083d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400083d5  mov     rcx, rbx; hObject
0x1400083d8  mov     edi, eax
0x1400083da  call    cs:__imp_CloseHandle
0x1400083e0  test    eax, eax
0x1400083e2  jz      short loc_140008453
0x1400083e4  jmp     loc_1400082FB
0x1400083e9  call    cs:__imp_GetLastError
0x1400083ef  cmp     eax, 2
0x1400083f2  jnz     short loc_1400083F8
0x1400083f4  xor     eax, eax
0x1400083f6  jmp     short loc_140008410
0x1400083f8  mov     rcx, [rbp+188h]; this
0x1400083ff  lea     r8, aWil; "wil"
0x140008406  mov     edx, 0D0h; void *
0x14000840b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008410  mov     rcx, [rbp+180h+var_40]
0x140008417  xor     rcx, rsp; StackCookie
0x14000841a  call    __security_check_cookie
0x14000841f  add     rsp, 258h
0x140008426  pop     r15
0x140008428  pop     r14
0x14000842a  pop     rdi
0x14000842b  pop     rsi
0x14000842c  pop     rbx
0x14000842d  pop     rbp
0x14000842e  retn
0x14000842f  mov     rcx, [rbp+188h]; this
0x140008436  mov     edx, 0A0Bh; void *
0x14000843b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008441  mov     rcx, [rbp+188h]; this
0x140008448  mov     edx, 0A0Bh; void *
0x14000844d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008453  mov     rcx, [rbp+188h]; this
0x14000845a  mov     edx, 0A0Bh; void *
0x14000845f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008465  mov     rcx, [rbp+188h]; this
0x14000846c  mov     edx, 0A0Bh; void *
0x140008471  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008477  mov     rcx, [rbp+188h]; this
0x14000847e  mov     edx, 0A0Bh; void *
0x140008483  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140008489  mov     rcx, [rbp+188h]; this
0x140008490  mov     edx, 0A0Bh; void *
0x140008495  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
