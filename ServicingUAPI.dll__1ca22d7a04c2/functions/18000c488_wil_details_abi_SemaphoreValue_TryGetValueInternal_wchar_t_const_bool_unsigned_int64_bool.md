# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c488`
- end: `0x18000c757`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009b4c`
- `0x180039c94`

## callees

- `0x1800031d0`
- `0x18000ab70`
- `0x18000ba14`
- `0x18000ba40`
- `0x18000c218`
- `0x18000c488`
- `0x18000c9f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c69e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c69e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c51f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c5ad`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c51f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c5ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c60d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c62b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c60d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c62b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c656`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c689`

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
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000c488  push    rbp
0x18000c48a  push    rbx
0x18000c48b  push    rsi
0x18000c48c  push    rdi
0x18000c48d  push    r14
0x18000c48f  push    r15
0x18000c491  lea     rbp, [rsp-158h]
0x18000c499  sub     rsp, 258h
0x18000c4a0  mov     rax, cs:__security_cookie
0x18000c4a7  xor     rax, rsp
0x18000c4aa  mov     [rbp+180h+var_40], rax
0x18000c4b1  xor     r15d, r15d
0x18000c4b4  lea     rax, [rsp+280h+Name]
0x18000c4b9  mov     esi, 104h
0x18000c4be  mov     [r8], r15
0x18000c4c1  mov     edx, esi
0x18000c4c3  mov     r14, r8
0x18000c4c6  mov     r9d, 7FFFFFFEh
0x18000c4cc  test    r9, r9
0x18000c4cf  jz      short loc_18000C4F0
0x18000c4d1  movzx   r8d, word ptr [rcx]
0x18000c4d5  test    r8w, r8w
0x18000c4d9  jz      short loc_18000C4F0
0x18000c4db  mov     [rax], r8w
0x18000c4df  add     rcx, 2
0x18000c4e3  add     rax, 2
0x18000c4e7  dec     r9
0x18000c4ea  sub     rdx, 1
0x18000c4ee  jnz     short loc_18000C4CC
0x18000c4f0  test    rdx, rdx
0x18000c4f3  lea     rcx, [rax-2]
0x18000c4f7  lea     r8, aP0; "_p0"
0x18000c4fe  mov     rdx, rsi; unsigned __int64
0x18000c501  cmovnz  rcx, rax
0x18000c505  mov     [rcx], r15w
0x18000c509  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000c50e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c513  lea     r8, [rsp+280h+Name]; lpName
0x18000c518  xor     edx, edx; bInheritHandle
0x18000c51a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c51f  call    cs:__imp_OpenSemaphoreW
0x18000c526  nop     dword ptr [rax+rax+00h]
0x18000c52b  mov     rbx, rax
0x18000c52e  test    rax, rax
0x18000c531  jz      loc_18000C69E
0x18000c537  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c53c  mov     [rsp+280h+var_25C], r15d
0x18000c541  mov     rcx, rax; hHandle
0x18000c544  mov     [rsp+280h+var_260], r15d; int
0x18000c549  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c54e  mov     edi, eax
0x18000c550  test    eax, eax
0x18000c552  jns     short loc_18000C58D
0x18000c554  mov     rcx, [rbp+188h]; this
0x18000c55b  lea     r8, aWil; "wil"
0x18000c562  mov     r9d, eax; char *
0x18000c565  mov     edx, 0D6h; void *
0x18000c56a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c56f  mov     rcx, rbx; hObject
0x18000c572  call    cs:__imp_CloseHandle
0x18000c579  nop     dword ptr [rax+rax+00h]
0x18000c57e  test    eax, eax
0x18000c580  jz      loc_18000C721
0x18000c586  mov     eax, edi
0x18000c588  jmp     loc_18000C6CB
0x18000c58d  lea     r8, asc_1801CAAD0; "h"
0x18000c594  mov     rdx, rsi; unsigned __int64
0x18000c597  lea     rcx, [rsp+280h+Name]; wchar_t *
0x18000c59c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c5a1  lea     r8, [rsp+280h+Name]; lpName
0x18000c5a6  xor     edx, edx; bInheritHandle
0x18000c5a8  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c5ad  call    cs:__imp_OpenSemaphoreW
0x18000c5b4  nop     dword ptr [rax+rax+00h]
0x18000c5b9  mov     rdi, rax
0x18000c5bc  test    rax, rax
0x18000c5bf  jz      loc_18000C66C
0x18000c5c5  lea     rdx, [rsp+280h+var_260]; int *
0x18000c5ca  mov     rcx, rax; hHandle
0x18000c5cd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c5d2  mov     esi, eax
0x18000c5d4  test    eax, eax
0x18000c5d6  jns     short loc_18000C628
0x18000c5d8  mov     rcx, [rbp+188h]; this
0x18000c5df  lea     r8, aWil; "wil"
0x18000c5e6  mov     r9d, eax; char *
0x18000c5e9  mov     edx, 0DEh; void *
0x18000c5ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c5f3  mov     rcx, rdi; hObject
0x18000c5f6  call    cs:__imp_CloseHandle
0x18000c5fd  nop     dword ptr [rax+rax+00h]
0x18000c602  test    eax, eax
0x18000c604  jz      loc_18000C733
0x18000c60a  mov     rcx, rbx; hObject
0x18000c60d  call    cs:__imp_CloseHandle
0x18000c614  nop     dword ptr [rax+rax+00h]
0x18000c619  test    eax, eax
0x18000c61b  jz      loc_18000C745
0x18000c621  mov     eax, esi
0x18000c623  jmp     loc_18000C6CB
0x18000c628  mov     rcx, rdi; hObject
0x18000c62b  call    cs:__imp_CloseHandle
0x18000c632  nop     dword ptr [rax+rax+00h]
0x18000c637  test    eax, eax
0x18000c639  jz      loc_18000C6EB
0x18000c63f  movsxd  rax, [rsp+280h+var_25C]
0x18000c644  movsxd  rcx, [rsp+280h+var_260]
0x18000c649  shl     rcx, 1Fh
0x18000c64d  or      rcx, rax
0x18000c650  mov     [r14], rcx
0x18000c653  mov     rcx, rbx; hObject
0x18000c656  call    cs:__imp_CloseHandle
0x18000c65d  nop     dword ptr [rax+rax+00h]
0x18000c662  test    eax, eax
0x18000c664  jz      loc_18000C6FD
0x18000c66a  jmp     short loc_18000C6AF
0x18000c66c  mov     rcx, [rbp+188h]; this
0x18000c673  lea     r8, aWil; "wil"
0x18000c67a  mov     edx, 0DCh; void *
0x18000c67f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c684  mov     rcx, rbx; hObject
0x18000c687  mov     edi, eax
0x18000c689  call    cs:__imp_CloseHandle
0x18000c690  nop     dword ptr [rax+rax+00h]
0x18000c695  test    eax, eax
0x18000c697  jz      short loc_18000C70F
0x18000c699  jmp     loc_18000C586
0x18000c69e  call    cs:__imp_GetLastError
0x18000c6a5  nop     dword ptr [rax+rax+00h]
0x18000c6aa  cmp     eax, 2
0x18000c6ad  jnz     short loc_18000C6B3
0x18000c6af  xor     eax, eax
0x18000c6b1  jmp     short loc_18000C6CB
0x18000c6b3  mov     rcx, [rbp+188h]; this
0x18000c6ba  lea     r8, aWil; "wil"
0x18000c6c1  mov     edx, 0D0h; void *
0x18000c6c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c6cb  mov     rcx, [rbp+180h+var_40]
0x18000c6d2  xor     rcx, rsp; StackCookie
0x18000c6d5  call    __security_check_cookie
0x18000c6da  add     rsp, 258h
0x18000c6e1  pop     r15
0x18000c6e3  pop     r14
0x18000c6e5  pop     rdi
0x18000c6e6  pop     rsi
0x18000c6e7  pop     rbx
0x18000c6e8  pop     rbp
0x18000c6e9  retn
0x18000c6eb  mov     rcx, [rbp+188h]; this
0x18000c6f2  mov     edx, 0A0Bh; void *
0x18000c6f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c6fd  mov     rcx, [rbp+188h]; this
0x18000c704  mov     edx, 0A0Bh; void *
0x18000c709  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c70f  mov     rcx, [rbp+188h]; this
0x18000c716  mov     edx, 0A0Bh; void *
0x18000c71b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c721  mov     rcx, [rbp+188h]; this
0x18000c728  mov     edx, 0A0Bh; void *
0x18000c72d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c733  mov     rcx, [rbp+188h]; this
0x18000c73a  mov     edx, 0A0Bh; void *
0x18000c73f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c745  mov     rcx, [rbp+188h]; this
0x18000c74c  mov     edx, 0A0Bh; void *
0x18000c751  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
