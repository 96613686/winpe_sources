# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180019b7c`
- end: `0x180019e26`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800180dc`

## callees

- `0x180001520`
- `0x1800189cc`
- `0x180019344`
- `0x180019364`
- `0x180019aa0`
- `0x180019b7c`
- `0x180019e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019cea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d5f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019c10`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019c91`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019c10`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019c91`

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
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
0x180019b7c  push    rbp
0x180019b7e  push    rbx
0x180019b7f  push    rsi
0x180019b80  push    rdi
0x180019b81  push    r14
0x180019b83  push    r15
0x180019b85  lea     rbp, [rsp-158h]
0x180019b8d  sub     rsp, 258h
0x180019b94  mov     rax, cs:__security_cookie
0x180019b9b  xor     rax, rsp
0x180019b9e  mov     [rbp+180h+var_40], rax
0x180019ba5  xor     r15d, r15d
0x180019ba8  lea     rax, [rsp+280h+Name]
0x180019bad  mov     [r8], r15
0x180019bb0  mov     r14, r8
0x180019bb3  mov     edx, 104h
0x180019bb8  mov     r9d, 7FFFFFFEh
0x180019bbe  test    r9, r9
0x180019bc1  jz      short loc_180019BE2
0x180019bc3  movzx   r8d, word ptr [rcx]
0x180019bc7  test    r8w, r8w
0x180019bcb  jz      short loc_180019BE2
0x180019bcd  mov     [rax], r8w
0x180019bd1  add     rcx, 2
0x180019bd5  add     rax, 2
0x180019bd9  dec     r9
0x180019bdc  sub     rdx, 1; unsigned __int64
0x180019be0  jnz     short loc_180019BBE
0x180019be2  test    rdx, rdx
0x180019be5  lea     rcx, [rax-2]
0x180019be9  lea     r8, aP0; "_p0"
0x180019bf0  cmovnz  rcx, rax
0x180019bf4  mov     [rcx], r15w
0x180019bf8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019bfd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019c02  mov     esi, 1F0003h
0x180019c07  lea     r8, [rsp+280h+Name]; lpName
0x180019c0c  mov     ecx, esi; dwDesiredAccess
0x180019c0e  xor     edx, edx; bInheritHandle
0x180019c10  call    cs:__imp_OpenSemaphoreW
0x180019c17  nop     dword ptr [rax+rax+00h]
0x180019c1c  mov     rbx, rax
0x180019c1f  test    rax, rax
0x180019c22  jz      loc_180019D74
0x180019c28  lea     rdx, [rsp+280h+var_25C]; int *
0x180019c2d  mov     [rsp+280h+var_25C], r15d
0x180019c32  mov     rcx, rax; hHandle
0x180019c35  mov     [rsp+280h+var_260], r15d; int
0x180019c3a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019c3f  mov     edi, eax
0x180019c41  test    eax, eax
0x180019c43  jns     short loc_180019C77
0x180019c45  mov     rcx, [rbp+188h]; this
0x180019c4c  mov     r9d, eax; char *
0x180019c4f  mov     edx, 0D6h; void *
0x180019c54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c59  mov     rcx, rbx; hObject
0x180019c5c  call    cs:__imp_CloseHandle
0x180019c63  nop     dword ptr [rax+rax+00h]
0x180019c68  test    eax, eax
0x180019c6a  jz      loc_180019DF0
0x180019c70  mov     eax, edi
0x180019c72  jmp     loc_180019D9A
0x180019c77  lea     r8, asc_180029D30; "h"
0x180019c7e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019c83  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019c88  lea     r8, [rsp+280h+Name]; lpName
0x180019c8d  xor     edx, edx; bInheritHandle
0x180019c8f  mov     ecx, esi; dwDesiredAccess
0x180019c91  call    cs:__imp_OpenSemaphoreW
0x180019c98  nop     dword ptr [rax+rax+00h]
0x180019c9d  mov     rdi, rax
0x180019ca0  test    rax, rax
0x180019ca3  jz      loc_180019D49
0x180019ca9  lea     rdx, [rsp+280h+var_260]; int *
0x180019cae  mov     rcx, rax; hHandle
0x180019cb1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019cb6  mov     esi, eax
0x180019cb8  test    eax, eax
0x180019cba  jns     short loc_180019D05
0x180019cbc  mov     rcx, [rbp+188h]; this
0x180019cc3  mov     r9d, eax; char *
0x180019cc6  mov     edx, 0DEh; void *
0x180019ccb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019cd0  mov     rcx, rdi; hObject
0x180019cd3  call    cs:__imp_CloseHandle
0x180019cda  nop     dword ptr [rax+rax+00h]
0x180019cdf  test    eax, eax
0x180019ce1  jz      loc_180019E02
0x180019ce7  mov     rcx, rbx; hObject
0x180019cea  call    cs:__imp_CloseHandle
0x180019cf1  nop     dword ptr [rax+rax+00h]
0x180019cf6  test    eax, eax
0x180019cf8  jz      loc_180019E14
0x180019cfe  mov     eax, esi
0x180019d00  jmp     loc_180019D9A
0x180019d05  mov     rcx, rdi; hObject
0x180019d08  call    cs:__imp_CloseHandle
0x180019d0f  nop     dword ptr [rax+rax+00h]
0x180019d14  test    eax, eax
0x180019d16  jz      loc_180019DBA
0x180019d1c  movsxd  rax, [rsp+280h+var_25C]
0x180019d21  movsxd  rcx, [rsp+280h+var_260]
0x180019d26  shl     rcx, 1Fh
0x180019d2a  or      rcx, rax
0x180019d2d  mov     [r14], rcx
0x180019d30  mov     rcx, rbx; hObject
0x180019d33  call    cs:__imp_CloseHandle
0x180019d3a  nop     dword ptr [rax+rax+00h]
0x180019d3f  test    eax, eax
0x180019d41  jz      loc_180019DCC
0x180019d47  jmp     short loc_180019D85
0x180019d49  mov     rcx, [rbp+188h]; this
0x180019d50  mov     edx, 0DCh; void *
0x180019d55  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019d5a  mov     rcx, rbx; hObject
0x180019d5d  mov     edi, eax
0x180019d5f  call    cs:__imp_CloseHandle
0x180019d66  nop     dword ptr [rax+rax+00h]
0x180019d6b  test    eax, eax
0x180019d6d  jz      short loc_180019DDE
0x180019d6f  jmp     loc_180019C70
0x180019d74  call    cs:__imp_GetLastError
0x180019d7b  nop     dword ptr [rax+rax+00h]
0x180019d80  cmp     eax, 2
0x180019d83  jnz     short loc_180019D89
0x180019d85  xor     eax, eax
0x180019d87  jmp     short loc_180019D9A
0x180019d89  mov     rcx, [rbp+188h]; this
0x180019d90  mov     edx, 0D0h; void *
0x180019d95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019d9a  mov     rcx, [rbp+180h+var_40]
0x180019da1  xor     rcx, rsp; StackCookie
0x180019da4  call    __security_check_cookie
0x180019da9  add     rsp, 258h
0x180019db0  pop     r15
0x180019db2  pop     r14
0x180019db4  pop     rdi
0x180019db5  pop     rsi
0x180019db6  pop     rbx
0x180019db7  pop     rbp
0x180019db8  retn
0x180019dba  mov     rcx, [rbp+188h]; this
0x180019dc1  mov     edx, 0A0Bh; void *
0x180019dc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019dcc  mov     rcx, [rbp+188h]; this
0x180019dd3  mov     edx, 0A0Bh; void *
0x180019dd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019dde  mov     rcx, [rbp+188h]; this
0x180019de5  mov     edx, 0A0Bh; void *
0x180019dea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019df0  mov     rcx, [rbp+188h]; this
0x180019df7  mov     edx, 0A0Bh; void *
0x180019dfc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019e02  mov     rcx, [rbp+188h]; this
0x180019e09  mov     edx, 0A0Bh; void *
0x180019e0e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180019e14  mov     rcx, [rbp+188h]; this
0x180019e1b  mov     edx, 0A0Bh; void *
0x180019e20  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
