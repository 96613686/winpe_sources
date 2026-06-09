# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000d358`
- end: `0x14000d5c4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008a58`
- `0x14000fe64`

## callees

- `0x140002310`
- `0x140009de4`
- `0x14000bf14`
- `0x14000bf34`
- `0x14000d0cc`
- `0x14000d358`
- `0x14000e3a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d3ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d461`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d3ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000d461`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d519`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d432`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d49d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d50a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d432`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d49d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d4e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d50a`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x14000d358  push    rbp
0x14000d35a  push    rbx
0x14000d35b  push    rsi
0x14000d35c  push    rdi
0x14000d35d  push    r14
0x14000d35f  push    r15
0x14000d361  lea     rbp, [rsp-158h]
0x14000d369  sub     rsp, 258h
0x14000d370  mov     rax, cs:__security_cookie
0x14000d377  xor     rax, rsp
0x14000d37a  mov     [rbp+180h+var_40], rax
0x14000d381  xor     r15d, r15d
0x14000d384  lea     rax, [rsp+280h+Name]
0x14000d389  mov     [r8], r15
0x14000d38c  mov     r14, r8
0x14000d38f  mov     edx, 104h
0x14000d394  mov     r9d, 7FFFFFFEh
0x14000d39a  test    r9, r9
0x14000d39d  jz      short loc_14000D3BE
0x14000d39f  movzx   r8d, word ptr [rcx]
0x14000d3a3  test    r8w, r8w
0x14000d3a7  jz      short loc_14000D3BE
0x14000d3a9  mov     [rax], r8w
0x14000d3ad  add     rcx, 2
0x14000d3b1  add     rax, 2
0x14000d3b5  dec     r9
0x14000d3b8  sub     rdx, 1; unsigned __int64
0x14000d3bc  jnz     short loc_14000D39A
0x14000d3be  test    rdx, rdx
0x14000d3c1  lea     rcx, [rax-2]
0x14000d3c5  lea     r8, aP0; "_p0"
0x14000d3cc  cmovnz  rcx, rax
0x14000d3d0  mov     [rcx], r15w
0x14000d3d4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000d3d9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d3de  mov     esi, 1F0003h
0x14000d3e3  lea     r8, [rsp+280h+Name]; lpName
0x14000d3e8  mov     ecx, esi; dwDesiredAccess
0x14000d3ea  xor     edx, edx; bInheritHandle
0x14000d3ec  call    cs:__imp_OpenSemaphoreW
0x14000d3f2  mov     rbx, rax
0x14000d3f5  test    rax, rax
0x14000d3f8  jz      loc_14000D519
0x14000d3fe  lea     rdx, [rsp+280h+var_25C]; int *
0x14000d403  mov     [rsp+280h+var_25C], r15d
0x14000d408  mov     rcx, rax; hHandle
0x14000d40b  mov     [rsp+280h+var_260], r15d; int
0x14000d410  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000d415  mov     edi, eax
0x14000d417  test    eax, eax
0x14000d419  jns     short loc_14000D447
0x14000d41b  mov     rcx, [rbp+188h]; this
0x14000d422  mov     r9d, eax; char *
0x14000d425  mov     edx, 0D6h; void *
0x14000d42a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d42f  mov     rcx, rbx; hObject
0x14000d432  call    cs:__imp_CloseHandle
0x14000d438  test    eax, eax
0x14000d43a  jz      loc_14000D58E
0x14000d440  mov     eax, edi
0x14000d442  jmp     loc_14000D539
0x14000d447  lea     r8, asc_140027680; "h"
0x14000d44e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000d453  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000d458  lea     r8, [rsp+280h+Name]; lpName
0x14000d45d  xor     edx, edx; bInheritHandle
0x14000d45f  mov     ecx, esi; dwDesiredAccess
0x14000d461  call    cs:__imp_OpenSemaphoreW
0x14000d467  mov     rdi, rax
0x14000d46a  test    rax, rax
0x14000d46d  jz      loc_14000D4F4
0x14000d473  lea     rdx, [rsp+280h+var_260]; int *
0x14000d478  mov     rcx, rax; hHandle
0x14000d47b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000d480  mov     esi, eax
0x14000d482  test    eax, eax
0x14000d484  jns     short loc_14000D4C0
0x14000d486  mov     rcx, [rbp+188h]; this
0x14000d48d  mov     r9d, eax; char *
0x14000d490  mov     edx, 0DEh; void *
0x14000d495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d49a  mov     rcx, rdi; hObject
0x14000d49d  call    cs:__imp_CloseHandle
0x14000d4a3  test    eax, eax
0x14000d4a5  jz      loc_14000D5A0
0x14000d4ab  mov     rcx, rbx; hObject
0x14000d4ae  call    cs:__imp_CloseHandle
0x14000d4b4  test    eax, eax
0x14000d4b6  jz      loc_14000D5B2
0x14000d4bc  mov     eax, esi
0x14000d4be  jmp     short loc_14000D539
0x14000d4c0  mov     rcx, rdi; hObject
0x14000d4c3  call    cs:__imp_CloseHandle
0x14000d4c9  test    eax, eax
0x14000d4cb  jz      loc_14000D558
0x14000d4d1  movsxd  rax, [rsp+280h+var_25C]
0x14000d4d6  movsxd  rcx, [rsp+280h+var_260]
0x14000d4db  shl     rcx, 1Fh
0x14000d4df  or      rcx, rax
0x14000d4e2  mov     [r14], rcx
0x14000d4e5  mov     rcx, rbx; hObject
0x14000d4e8  call    cs:__imp_CloseHandle
0x14000d4ee  test    eax, eax
0x14000d4f0  jz      short loc_14000D56A
0x14000d4f2  jmp     short loc_14000D524
0x14000d4f4  mov     rcx, [rbp+188h]; this
0x14000d4fb  mov     edx, 0DCh; void *
0x14000d500  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d505  mov     rcx, rbx; hObject
0x14000d508  mov     edi, eax
0x14000d50a  call    cs:__imp_CloseHandle
0x14000d510  test    eax, eax
0x14000d512  jz      short loc_14000D57C
0x14000d514  jmp     loc_14000D440
0x14000d519  call    cs:__imp_GetLastError
0x14000d51f  cmp     eax, 2
0x14000d522  jnz     short loc_14000D528
0x14000d524  xor     eax, eax
0x14000d526  jmp     short loc_14000D539
0x14000d528  mov     rcx, [rbp+188h]; this
0x14000d52f  mov     edx, 0D0h; void *
0x14000d534  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000d539  mov     rcx, [rbp+180h+var_40]
0x14000d540  xor     rcx, rsp; StackCookie
0x14000d543  call    __security_check_cookie
0x14000d548  add     rsp, 258h
0x14000d54f  pop     r15
0x14000d551  pop     r14
0x14000d553  pop     rdi
0x14000d554  pop     rsi
0x14000d555  pop     rbx
0x14000d556  pop     rbp
0x14000d557  retn
0x14000d558  mov     rcx, [rbp+188h]; this
0x14000d55f  mov     edx, 0A0Bh; void *
0x14000d564  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d56a  mov     rcx, [rbp+188h]; this
0x14000d571  mov     edx, 0A0Bh; void *
0x14000d576  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d57c  mov     rcx, [rbp+188h]; this
0x14000d583  mov     edx, 0A0Bh; void *
0x14000d588  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d58e  mov     rcx, [rbp+188h]; this
0x14000d595  mov     edx, 0A0Bh; void *
0x14000d59a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d5a0  mov     rcx, [rbp+188h]; this
0x14000d5a7  mov     edx, 0A0Bh; void *
0x14000d5ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000d5b2  mov     rcx, [rbp+188h]; this
0x14000d5b9  mov     edx, 0A0Bh; void *
0x14000d5be  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
