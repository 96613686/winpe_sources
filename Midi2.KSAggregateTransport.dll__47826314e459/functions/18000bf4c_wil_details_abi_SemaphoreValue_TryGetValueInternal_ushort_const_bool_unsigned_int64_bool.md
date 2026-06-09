# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bf4c`
- end: `0x18000c1db`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007238`

## callees

- `0x180005020`
- `0x180009278`
- `0x18000b374`
- `0x18000b394`
- `0x18000bd24`
- `0x18000bf4c`
- `0x18000c684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bfe0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c05c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bfe0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c05c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c129`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c129`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c02d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c09f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c11a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c02d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c09f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c0ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c11a`

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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000bf4c  push    rbp
0x18000bf4e  push    rbx
0x18000bf4f  push    rsi
0x18000bf50  push    rdi
0x18000bf51  push    r14
0x18000bf53  push    r15
0x18000bf55  lea     rbp, [rsp-158h]
0x18000bf5d  sub     rsp, 258h
0x18000bf64  mov     rax, cs:__security_cookie
0x18000bf6b  xor     rax, rsp
0x18000bf6e  mov     [rbp+180h+var_40], rax
0x18000bf75  xor     r15d, r15d
0x18000bf78  lea     rax, [rsp+280h+Name]
0x18000bf7d  mov     [r8], r15
0x18000bf80  mov     r14, r8
0x18000bf83  mov     edx, 104h
0x18000bf88  mov     r9d, 7FFFFFFEh
0x18000bf8e  test    r9, r9
0x18000bf91  jz      short loc_18000BFB2
0x18000bf93  movzx   r8d, word ptr [rcx]
0x18000bf97  test    r8w, r8w
0x18000bf9b  jz      short loc_18000BFB2
0x18000bf9d  mov     [rax], r8w
0x18000bfa1  add     rcx, 2
0x18000bfa5  add     rax, 2
0x18000bfa9  dec     r9
0x18000bfac  sub     rdx, 1; unsigned __int64
0x18000bfb0  jnz     short loc_18000BF8E
0x18000bfb2  test    rdx, rdx
0x18000bfb5  lea     rcx, [rax-2]
0x18000bfb9  lea     r8, aP0; "_p0"
0x18000bfc0  cmovnz  rcx, rax
0x18000bfc4  mov     [rcx], r15w
0x18000bfc8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000bfcd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bfd2  mov     esi, 1F0003h
0x18000bfd7  lea     r8, [rsp+280h+Name]; lpName
0x18000bfdc  mov     ecx, esi; dwDesiredAccess
0x18000bfde  xor     edx, edx; bInheritHandle
0x18000bfe0  call    cs:__imp_OpenSemaphoreW
0x18000bfe6  mov     rbx, rax
0x18000bfe9  test    rax, rax
0x18000bfec  jz      loc_18000C129
0x18000bff2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000bff7  mov     [rsp+280h+var_25C], r15d
0x18000bffc  mov     rcx, rax; hHandle
0x18000bfff  mov     [rsp+280h+var_260], r15d; int
0x18000c004  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c009  mov     edi, eax
0x18000c00b  test    eax, eax
0x18000c00d  jns     short loc_18000C042
0x18000c00f  mov     rcx, [rbp+188h]; this
0x18000c016  lea     r8, aWil; "wil"
0x18000c01d  mov     r9d, eax; char *
0x18000c020  mov     edx, 0D6h; void *
0x18000c025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c02a  mov     rcx, rbx; hObject
0x18000c02d  call    cs:__imp_CloseHandle
0x18000c033  test    eax, eax
0x18000c035  jz      loc_18000C1A5
0x18000c03b  mov     eax, edi
0x18000c03d  jmp     loc_18000C150
0x18000c042  lea     r8, asc_18007E610; "h"
0x18000c049  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c04e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c053  lea     r8, [rsp+280h+Name]; lpName
0x18000c058  xor     edx, edx; bInheritHandle
0x18000c05a  mov     ecx, esi; dwDesiredAccess
0x18000c05c  call    cs:__imp_OpenSemaphoreW
0x18000c062  mov     rdi, rax
0x18000c065  test    rax, rax
0x18000c068  jz      loc_18000C0FD
0x18000c06e  lea     rdx, [rsp+280h+var_260]; int *
0x18000c073  mov     rcx, rax; hHandle
0x18000c076  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c07b  mov     esi, eax
0x18000c07d  test    eax, eax
0x18000c07f  jns     short loc_18000C0C5
0x18000c081  mov     rcx, [rbp+188h]; this
0x18000c088  lea     r8, aWil; "wil"
0x18000c08f  mov     r9d, eax; char *
0x18000c092  mov     edx, 0DEh; void *
0x18000c097  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c09c  mov     rcx, rdi; hObject
0x18000c09f  call    cs:__imp_CloseHandle
0x18000c0a5  test    eax, eax
0x18000c0a7  jz      loc_18000C1B7
0x18000c0ad  mov     rcx, rbx; hObject
0x18000c0b0  call    cs:__imp_CloseHandle
0x18000c0b6  test    eax, eax
0x18000c0b8  jz      loc_18000C1C9
0x18000c0be  mov     eax, esi
0x18000c0c0  jmp     loc_18000C150
0x18000c0c5  mov     rcx, rdi; hObject
0x18000c0c8  call    cs:__imp_CloseHandle
0x18000c0ce  test    eax, eax
0x18000c0d0  jz      loc_18000C16F
0x18000c0d6  movsxd  rax, [rsp+280h+var_25C]
0x18000c0db  movsxd  rcx, [rsp+280h+var_260]
0x18000c0e0  shl     rcx, 1Fh
0x18000c0e4  or      rcx, rax
0x18000c0e7  mov     [r14], rcx
0x18000c0ea  mov     rcx, rbx; hObject
0x18000c0ed  call    cs:__imp_CloseHandle
0x18000c0f3  test    eax, eax
0x18000c0f5  jz      loc_18000C181
0x18000c0fb  jmp     short loc_18000C134
0x18000c0fd  mov     rcx, [rbp+188h]; this
0x18000c104  lea     r8, aWil; "wil"
0x18000c10b  mov     edx, 0DCh; void *
0x18000c110  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c115  mov     rcx, rbx; hObject
0x18000c118  mov     edi, eax
0x18000c11a  call    cs:__imp_CloseHandle
0x18000c120  test    eax, eax
0x18000c122  jz      short loc_18000C193
0x18000c124  jmp     loc_18000C03B
0x18000c129  call    cs:__imp_GetLastError
0x18000c12f  cmp     eax, 2
0x18000c132  jnz     short loc_18000C138
0x18000c134  xor     eax, eax
0x18000c136  jmp     short loc_18000C150
0x18000c138  mov     rcx, [rbp+188h]; this
0x18000c13f  lea     r8, aWil; "wil"
0x18000c146  mov     edx, 0D0h; void *
0x18000c14b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c150  mov     rcx, [rbp+180h+var_40]
0x18000c157  xor     rcx, rsp; StackCookie
0x18000c15a  call    __security_check_cookie
0x18000c15f  add     rsp, 258h
0x18000c166  pop     r15
0x18000c168  pop     r14
0x18000c16a  pop     rdi
0x18000c16b  pop     rsi
0x18000c16c  pop     rbx
0x18000c16d  pop     rbp
0x18000c16e  retn
0x18000c16f  mov     rcx, [rbp+188h]; this
0x18000c176  mov     edx, 0A0Bh; void *
0x18000c17b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c181  mov     rcx, [rbp+188h]; this
0x18000c188  mov     edx, 0A0Bh; void *
0x18000c18d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c193  mov     rcx, [rbp+188h]; this
0x18000c19a  mov     edx, 0A0Bh; void *
0x18000c19f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c1a5  mov     rcx, [rbp+188h]; this
0x18000c1ac  mov     edx, 0A0Bh; void *
0x18000c1b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c1b7  mov     rcx, [rbp+188h]; this
0x18000c1be  mov     edx, 0A0Bh; void *
0x18000c1c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c1c9  mov     rcx, [rbp+188h]; this
0x18000c1d0  mov     edx, 0A0Bh; void *
0x18000c1d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
