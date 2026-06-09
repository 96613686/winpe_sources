# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000b9ac`
- end: `0x14000bc44`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140006298`
- `0x140006668`

## callees

- `0x140002470`
- `0x14000817c`
- `0x14000a9a4`
- `0x14000a9c4`
- `0x14000b408`
- `0x14000b9ac`
- `0x14000c5ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ba43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bac5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ba43`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bac5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bb92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bb92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ba90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000ba90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb83`

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
0x14000b9ac  push    rbp
0x14000b9ae  push    rbx
0x14000b9af  push    rsi
0x14000b9b0  push    rdi
0x14000b9b1  push    r14
0x14000b9b3  push    r15
0x14000b9b5  lea     rbp, [rsp-158h]
0x14000b9bd  sub     rsp, 258h
0x14000b9c4  mov     rax, cs:__security_cookie
0x14000b9cb  xor     rax, rsp
0x14000b9ce  mov     [rbp+180h+var_40], rax
0x14000b9d5  xor     r15d, r15d
0x14000b9d8  lea     rax, [rsp+280h+Name]
0x14000b9dd  mov     esi, 104h
0x14000b9e2  mov     [r8], r15
0x14000b9e5  mov     edx, esi
0x14000b9e7  mov     r14, r8
0x14000b9ea  mov     r9d, 7FFFFFFEh
0x14000b9f0  test    r9, r9
0x14000b9f3  jz      short loc_14000BA14
0x14000b9f5  movzx   r8d, word ptr [rcx]
0x14000b9f9  test    r8w, r8w
0x14000b9fd  jz      short loc_14000BA14
0x14000b9ff  mov     [rax], r8w
0x14000ba03  add     rcx, 2
0x14000ba07  add     rax, 2
0x14000ba0b  dec     r9
0x14000ba0e  sub     rdx, 1
0x14000ba12  jnz     short loc_14000B9F0
0x14000ba14  test    rdx, rdx
0x14000ba17  lea     rcx, [rax-2]
0x14000ba1b  lea     r8, aP0; "_p0"
0x14000ba22  mov     rdx, rsi; unsigned __int64
0x14000ba25  cmovnz  rcx, rax
0x14000ba29  mov     [rcx], r15w
0x14000ba2d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000ba32  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000ba37  lea     r8, [rsp+280h+Name]; lpName
0x14000ba3c  xor     edx, edx; bInheritHandle
0x14000ba3e  mov     ecx, 1F0003h; dwDesiredAccess
0x14000ba43  call    cs:__imp_OpenSemaphoreW
0x14000ba49  mov     rbx, rax
0x14000ba4c  test    rax, rax
0x14000ba4f  jz      loc_14000BB92
0x14000ba55  lea     rdx, [rsp+280h+var_25C]; int *
0x14000ba5a  mov     [rsp+280h+var_25C], r15d
0x14000ba5f  mov     rcx, rax; hHandle
0x14000ba62  mov     [rsp+280h+var_260], r15d; int
0x14000ba67  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000ba6c  mov     edi, eax
0x14000ba6e  test    eax, eax
0x14000ba70  jns     short loc_14000BAA5
0x14000ba72  mov     rcx, [rbp+188h]; this
0x14000ba79  lea     r8, aWil; "wil"
0x14000ba80  mov     r9d, eax; char *
0x14000ba83  mov     edx, 0D6h; void *
0x14000ba88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ba8d  mov     rcx, rbx; hObject
0x14000ba90  call    cs:__imp_CloseHandle
0x14000ba96  test    eax, eax
0x14000ba98  jz      loc_14000BC0E
0x14000ba9e  mov     eax, edi
0x14000baa0  jmp     loc_14000BBB9
0x14000baa5  lea     r8, asc_140062B58; "h"
0x14000baac  mov     rdx, rsi; unsigned __int64
0x14000baaf  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000bab4  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000bab9  lea     r8, [rsp+280h+Name]; lpName
0x14000babe  xor     edx, edx; bInheritHandle
0x14000bac0  mov     ecx, 1F0003h; dwDesiredAccess
0x14000bac5  call    cs:__imp_OpenSemaphoreW
0x14000bacb  mov     rdi, rax
0x14000bace  test    rax, rax
0x14000bad1  jz      loc_14000BB66
0x14000bad7  lea     rdx, [rsp+280h+var_260]; int *
0x14000badc  mov     rcx, rax; hHandle
0x14000badf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000bae4  mov     esi, eax
0x14000bae6  test    eax, eax
0x14000bae8  jns     short loc_14000BB2E
0x14000baea  mov     rcx, [rbp+188h]; this
0x14000baf1  lea     r8, aWil; "wil"
0x14000baf8  mov     r9d, eax; char *
0x14000bafb  mov     edx, 0DEh; void *
0x14000bb00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bb05  mov     rcx, rdi; hObject
0x14000bb08  call    cs:__imp_CloseHandle
0x14000bb0e  test    eax, eax
0x14000bb10  jz      loc_14000BC20
0x14000bb16  mov     rcx, rbx; hObject
0x14000bb19  call    cs:__imp_CloseHandle
0x14000bb1f  test    eax, eax
0x14000bb21  jz      loc_14000BC32
0x14000bb27  mov     eax, esi
0x14000bb29  jmp     loc_14000BBB9
0x14000bb2e  mov     rcx, rdi; hObject
0x14000bb31  call    cs:__imp_CloseHandle
0x14000bb37  test    eax, eax
0x14000bb39  jz      loc_14000BBD8
0x14000bb3f  movsxd  rax, [rsp+280h+var_25C]
0x14000bb44  movsxd  rcx, [rsp+280h+var_260]
0x14000bb49  shl     rcx, 1Fh
0x14000bb4d  or      rcx, rax
0x14000bb50  mov     [r14], rcx
0x14000bb53  mov     rcx, rbx; hObject
0x14000bb56  call    cs:__imp_CloseHandle
0x14000bb5c  test    eax, eax
0x14000bb5e  jz      loc_14000BBEA
0x14000bb64  jmp     short loc_14000BB9D
0x14000bb66  mov     rcx, [rbp+188h]; this
0x14000bb6d  lea     r8, aWil; "wil"
0x14000bb74  mov     edx, 0DCh; void *
0x14000bb79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bb7e  mov     rcx, rbx; hObject
0x14000bb81  mov     edi, eax
0x14000bb83  call    cs:__imp_CloseHandle
0x14000bb89  test    eax, eax
0x14000bb8b  jz      short loc_14000BBFC
0x14000bb8d  jmp     loc_14000BA9E
0x14000bb92  call    cs:__imp_GetLastError
0x14000bb98  cmp     eax, 2
0x14000bb9b  jnz     short loc_14000BBA1
0x14000bb9d  xor     eax, eax
0x14000bb9f  jmp     short loc_14000BBB9
0x14000bba1  mov     rcx, [rbp+188h]; this
0x14000bba8  lea     r8, aWil; "wil"
0x14000bbaf  mov     edx, 0D0h; void *
0x14000bbb4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bbb9  mov     rcx, [rbp+180h+var_40]
0x14000bbc0  xor     rcx, rsp; StackCookie
0x14000bbc3  call    __security_check_cookie
0x14000bbc8  add     rsp, 258h
0x14000bbcf  pop     r15
0x14000bbd1  pop     r14
0x14000bbd3  pop     rdi
0x14000bbd4  pop     rsi
0x14000bbd5  pop     rbx
0x14000bbd6  pop     rbp
0x14000bbd7  retn
0x14000bbd8  mov     rcx, [rbp+188h]; this
0x14000bbdf  mov     edx, 0A0Bh; void *
0x14000bbe4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bbea  mov     rcx, [rbp+188h]; this
0x14000bbf1  mov     edx, 0A0Bh; void *
0x14000bbf6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bbfc  mov     rcx, [rbp+188h]; this
0x14000bc03  mov     edx, 0A0Bh; void *
0x14000bc08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc0e  mov     rcx, [rbp+188h]; this
0x14000bc15  mov     edx, 0A0Bh; void *
0x14000bc1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc20  mov     rcx, [rbp+188h]; this
0x14000bc27  mov     edx, 0A0Bh; void *
0x14000bc2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc32  mov     rcx, [rbp+188h]; this
0x14000bc39  mov     edx, 0A0Bh; void *
0x14000bc3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
