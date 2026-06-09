# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000823c`
- end: `0x1800084b6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003978`

## callees

- `0x180001ef0`
- `0x1800058e4`
- `0x180007724`
- `0x180007744`
- `0x1800080d4`
- `0x18000823c`
- `0x1800088f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000834c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800082d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000834c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000840b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000840b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000831d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000838f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000831d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000838f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800083fc`

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
0x18000823c  push    rbp
0x18000823e  push    rbx
0x18000823f  push    rsi
0x180008240  push    rdi
0x180008241  push    r14
0x180008243  push    r15
0x180008245  lea     rbp, [rsp-158h]
0x18000824d  sub     rsp, 258h
0x180008254  mov     rax, cs:__security_cookie
0x18000825b  xor     rax, rsp
0x18000825e  mov     [rbp+180h+var_40], rax
0x180008265  xor     r15d, r15d
0x180008268  lea     rax, [rsp+280h+Name]
0x18000826d  mov     [r8], r15
0x180008270  mov     r14, r8
0x180008273  mov     edx, 104h
0x180008278  mov     r9d, 7FFFFFFEh
0x18000827e  test    r9, r9
0x180008281  jz      short loc_1800082A2
0x180008283  movzx   r8d, word ptr [rcx]
0x180008287  test    r8w, r8w
0x18000828b  jz      short loc_1800082A2
0x18000828d  mov     [rax], r8w
0x180008291  add     rcx, 2
0x180008295  add     rax, 2
0x180008299  dec     r9
0x18000829c  sub     rdx, 1; unsigned __int64
0x1800082a0  jnz     short loc_18000827E
0x1800082a2  test    rdx, rdx
0x1800082a5  lea     rcx, [rax-2]
0x1800082a9  lea     r8, aP0; "_p0"
0x1800082b0  cmovnz  rcx, rax
0x1800082b4  mov     [rcx], r15w
0x1800082b8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800082bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082c2  mov     esi, 1F0003h
0x1800082c7  lea     r8, [rsp+280h+Name]; lpName
0x1800082cc  mov     ecx, esi; dwDesiredAccess
0x1800082ce  xor     edx, edx; bInheritHandle
0x1800082d0  call    cs:__imp_OpenSemaphoreW
0x1800082d6  mov     rbx, rax
0x1800082d9  test    rax, rax
0x1800082dc  jz      loc_18000840B
0x1800082e2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800082e7  mov     [rsp+280h+var_25C], r15d
0x1800082ec  mov     rcx, rax; hHandle
0x1800082ef  mov     [rsp+280h+var_260], r15d; int
0x1800082f4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800082f9  mov     edi, eax
0x1800082fb  test    eax, eax
0x1800082fd  jns     short loc_180008332
0x1800082ff  mov     rcx, [rbp+188h]; this
0x180008306  lea     r8, aWil; "wil"
0x18000830d  mov     r9d, eax; char *
0x180008310  mov     edx, 0D6h; void *
0x180008315  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000831a  mov     rcx, rbx; hObject
0x18000831d  call    cs:__imp_CloseHandle
0x180008323  test    eax, eax
0x180008325  jz      loc_180008480
0x18000832b  mov     eax, edi
0x18000832d  jmp     loc_18000842B
0x180008332  lea     r8, asc_180011060; "h"
0x180008339  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000833e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008343  lea     r8, [rsp+280h+Name]; lpName
0x180008348  xor     edx, edx; bInheritHandle
0x18000834a  mov     ecx, esi; dwDesiredAccess
0x18000834c  call    cs:__imp_OpenSemaphoreW
0x180008352  mov     rdi, rax
0x180008355  test    rax, rax
0x180008358  jz      loc_1800083E6
0x18000835e  lea     rdx, [rsp+280h+var_260]; int *
0x180008363  mov     rcx, rax; hHandle
0x180008366  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000836b  mov     esi, eax
0x18000836d  test    eax, eax
0x18000836f  jns     short loc_1800083B2
0x180008371  mov     rcx, [rbp+188h]; this
0x180008378  lea     r8, aWil; "wil"
0x18000837f  mov     r9d, eax; char *
0x180008382  mov     edx, 0DEh; void *
0x180008387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000838c  mov     rcx, rdi; hObject
0x18000838f  call    cs:__imp_CloseHandle
0x180008395  test    eax, eax
0x180008397  jz      loc_180008492
0x18000839d  mov     rcx, rbx; hObject
0x1800083a0  call    cs:__imp_CloseHandle
0x1800083a6  test    eax, eax
0x1800083a8  jz      loc_1800084A4
0x1800083ae  mov     eax, esi
0x1800083b0  jmp     short loc_18000842B
0x1800083b2  mov     rcx, rdi; hObject
0x1800083b5  call    cs:__imp_CloseHandle
0x1800083bb  test    eax, eax
0x1800083bd  jz      loc_18000844A
0x1800083c3  movsxd  rax, [rsp+280h+var_25C]
0x1800083c8  movsxd  rcx, [rsp+280h+var_260]
0x1800083cd  shl     rcx, 1Fh
0x1800083d1  or      rcx, rax
0x1800083d4  mov     [r14], rcx
0x1800083d7  mov     rcx, rbx; hObject
0x1800083da  call    cs:__imp_CloseHandle
0x1800083e0  test    eax, eax
0x1800083e2  jz      short loc_18000845C
0x1800083e4  jmp     short loc_180008416
0x1800083e6  mov     rcx, [rbp+188h]; this
0x1800083ed  mov     edx, 0DCh; void *
0x1800083f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800083f7  mov     rcx, rbx; hObject
0x1800083fa  mov     edi, eax
0x1800083fc  call    cs:__imp_CloseHandle
0x180008402  test    eax, eax
0x180008404  jz      short loc_18000846E
0x180008406  jmp     loc_18000832B
0x18000840b  call    cs:__imp_GetLastError
0x180008411  cmp     eax, 2
0x180008414  jnz     short loc_18000841A
0x180008416  xor     eax, eax
0x180008418  jmp     short loc_18000842B
0x18000841a  mov     rcx, [rbp+188h]; this
0x180008421  mov     edx, 0D0h; void *
0x180008426  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000842b  mov     rcx, [rbp+180h+var_40]
0x180008432  xor     rcx, rsp; StackCookie
0x180008435  call    __security_check_cookie
0x18000843a  add     rsp, 258h
0x180008441  pop     r15
0x180008443  pop     r14
0x180008445  pop     rdi
0x180008446  pop     rsi
0x180008447  pop     rbx
0x180008448  pop     rbp
0x180008449  retn
0x18000844a  mov     rcx, [rbp+188h]; this
0x180008451  mov     edx, 0A0Bh; void *
0x180008456  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000845c  mov     rcx, [rbp+188h]; this
0x180008463  mov     edx, 0A0Bh; void *
0x180008468  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000846e  mov     rcx, [rbp+188h]; this
0x180008475  mov     edx, 0A0Bh; void *
0x18000847a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008480  mov     rcx, [rbp+188h]; this
0x180008487  mov     edx, 0A0Bh; void *
0x18000848c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008492  mov     rcx, [rbp+188h]; this
0x180008499  mov     edx, 0A0Bh; void *
0x18000849e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800084a4  mov     rcx, [rbp+188h]; this
0x1800084ab  mov     edx, 0A0Bh; void *
0x1800084b0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
