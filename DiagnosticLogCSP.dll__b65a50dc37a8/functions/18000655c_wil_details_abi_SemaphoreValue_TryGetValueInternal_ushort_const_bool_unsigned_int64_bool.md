# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000655c`
- end: `0x18000681d`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `705`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000422c`

## callees

- `0x180001b90`
- `0x180004e28`
- `0x180005c04`
- `0x180005c24`
- `0x180006360`
- `0x18000655c`
- `0x180006988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000676b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000676b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065f3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006681`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065f3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006681`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000672a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006756`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800066ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000672a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006756`

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
  StringCchCatW(Name, 0x104u, L"_p0");
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
  StringCchCatW(Name, 0x104u, L"h");
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
0x18000655c  push    rbp
0x18000655e  push    rbx
0x18000655f  push    rsi
0x180006560  push    rdi
0x180006561  push    r14
0x180006563  push    r15
0x180006565  lea     rbp, [rsp-158h]
0x18000656d  sub     rsp, 258h
0x180006574  mov     rax, cs:__security_cookie
0x18000657b  xor     rax, rsp
0x18000657e  mov     [rbp+180h+var_40], rax
0x180006585  xor     r15d, r15d
0x180006588  lea     rax, [rsp+280h+Name]
0x18000658d  mov     esi, 104h
0x180006592  mov     [r8], r15
0x180006595  mov     edx, esi
0x180006597  mov     r14, r8
0x18000659a  mov     r9d, 7FFFFFFEh
0x1800065a0  test    r9, r9
0x1800065a3  jz      short loc_1800065C4
0x1800065a5  movzx   r8d, word ptr [rcx]
0x1800065a9  test    r8w, r8w
0x1800065ad  jz      short loc_1800065C4
0x1800065af  mov     [rax], r8w
0x1800065b3  add     rcx, 2
0x1800065b7  add     rax, 2
0x1800065bb  dec     r9
0x1800065be  sub     rdx, 1
0x1800065c2  jnz     short loc_1800065A0
0x1800065c4  test    rdx, rdx
0x1800065c7  lea     rcx, [rax-2]
0x1800065cb  lea     r8, aP0; "_p0"
0x1800065d2  mov     rdx, rsi; unsigned __int64
0x1800065d5  cmovnz  rcx, rax
0x1800065d9  mov     [rcx], r15w
0x1800065dd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800065e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065e7  lea     r8, [rsp+280h+Name]; lpName
0x1800065ec  xor     edx, edx; bInheritHandle
0x1800065ee  mov     ecx, 1F0003h; dwDesiredAccess
0x1800065f3  call    cs:__imp_OpenSemaphoreW
0x1800065fa  nop     dword ptr [rax+rax+00h]
0x1800065ff  mov     rbx, rax
0x180006602  test    rax, rax
0x180006605  jz      loc_18000676B
0x18000660b  lea     rdx, [rsp+280h+var_25C]; int *
0x180006610  mov     [rsp+280h+var_25C], r15d
0x180006615  mov     rcx, rax; hHandle
0x180006618  mov     [rsp+280h+var_260], r15d; int
0x18000661d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006622  mov     edi, eax
0x180006624  test    eax, eax
0x180006626  jns     short loc_180006661
0x180006628  mov     rcx, [rbp+188h]; this
0x18000662f  lea     r8, aWil; "wil"
0x180006636  mov     r9d, eax; char *
0x180006639  mov     edx, 0D6h; void *
0x18000663e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006643  mov     rcx, rbx; hObject
0x180006646  call    cs:__imp_CloseHandle
0x18000664d  nop     dword ptr [rax+rax+00h]
0x180006652  test    eax, eax
0x180006654  jz      loc_1800067E7
0x18000665a  mov     eax, edi
0x18000665c  jmp     loc_180006791
0x180006661  lea     r8, asc_18003D670; "h"
0x180006668  mov     rdx, rsi; unsigned __int64
0x18000666b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006670  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006675  lea     r8, [rsp+280h+Name]; lpName
0x18000667a  xor     edx, edx; bInheritHandle
0x18000667c  mov     ecx, 1F0003h; dwDesiredAccess
0x180006681  call    cs:__imp_OpenSemaphoreW
0x180006688  nop     dword ptr [rax+rax+00h]
0x18000668d  mov     rdi, rax
0x180006690  test    rax, rax
0x180006693  jz      loc_180006740
0x180006699  lea     rdx, [rsp+280h+var_260]; int *
0x18000669e  mov     rcx, rax; hHandle
0x1800066a1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800066a6  mov     esi, eax
0x1800066a8  test    eax, eax
0x1800066aa  jns     short loc_1800066FC
0x1800066ac  mov     rcx, [rbp+188h]; this
0x1800066b3  lea     r8, aWil; "wil"
0x1800066ba  mov     r9d, eax; char *
0x1800066bd  mov     edx, 0DEh; void *
0x1800066c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066c7  mov     rcx, rdi; hObject
0x1800066ca  call    cs:__imp_CloseHandle
0x1800066d1  nop     dword ptr [rax+rax+00h]
0x1800066d6  test    eax, eax
0x1800066d8  jz      loc_1800067F9
0x1800066de  mov     rcx, rbx; hObject
0x1800066e1  call    cs:__imp_CloseHandle
0x1800066e8  nop     dword ptr [rax+rax+00h]
0x1800066ed  test    eax, eax
0x1800066ef  jz      loc_18000680B
0x1800066f5  mov     eax, esi
0x1800066f7  jmp     loc_180006791
0x1800066fc  mov     rcx, rdi; hObject
0x1800066ff  call    cs:__imp_CloseHandle
0x180006706  nop     dword ptr [rax+rax+00h]
0x18000670b  test    eax, eax
0x18000670d  jz      loc_1800067B1
0x180006713  movsxd  rax, [rsp+280h+var_25C]
0x180006718  movsxd  rcx, [rsp+280h+var_260]
0x18000671d  shl     rcx, 1Fh
0x180006721  or      rcx, rax
0x180006724  mov     [r14], rcx
0x180006727  mov     rcx, rbx; hObject
0x18000672a  call    cs:__imp_CloseHandle
0x180006731  nop     dword ptr [rax+rax+00h]
0x180006736  test    eax, eax
0x180006738  jz      loc_1800067C3
0x18000673e  jmp     short loc_18000677C
0x180006740  mov     rcx, [rbp+188h]; this
0x180006747  mov     edx, 0DCh; void *
0x18000674c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006751  mov     rcx, rbx; hObject
0x180006754  mov     edi, eax
0x180006756  call    cs:__imp_CloseHandle
0x18000675d  nop     dword ptr [rax+rax+00h]
0x180006762  test    eax, eax
0x180006764  jz      short loc_1800067D5
0x180006766  jmp     loc_18000665A
0x18000676b  call    cs:__imp_GetLastError
0x180006772  nop     dword ptr [rax+rax+00h]
0x180006777  cmp     eax, 2
0x18000677a  jnz     short loc_180006780
0x18000677c  xor     eax, eax
0x18000677e  jmp     short loc_180006791
0x180006780  mov     rcx, [rbp+188h]; this
0x180006787  mov     edx, 0D0h; void *
0x18000678c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006791  mov     rcx, [rbp+180h+var_40]
0x180006798  xor     rcx, rsp; StackCookie
0x18000679b  call    __security_check_cookie
0x1800067a0  add     rsp, 258h
0x1800067a7  pop     r15
0x1800067a9  pop     r14
0x1800067ab  pop     rdi
0x1800067ac  pop     rsi
0x1800067ad  pop     rbx
0x1800067ae  pop     rbp
0x1800067af  retn
0x1800067b1  mov     rcx, [rbp+188h]; this
0x1800067b8  mov     edx, 0A0Bh; void *
0x1800067bd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067c3  mov     rcx, [rbp+188h]; this
0x1800067ca  mov     edx, 0A0Bh; void *
0x1800067cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067d5  mov     rcx, [rbp+188h]; this
0x1800067dc  mov     edx, 0A0Bh; void *
0x1800067e1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067e7  mov     rcx, [rbp+188h]; this
0x1800067ee  mov     edx, 0A0Bh; void *
0x1800067f3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800067f9  mov     rcx, [rbp+188h]; this
0x180006800  mov     edx, 0A0Bh; void *
0x180006805  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000680b  mov     rcx, [rbp+188h]; this
0x180006812  mov     edx, 0A0Bh; void *
0x180006817  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
