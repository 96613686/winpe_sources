# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a534`
- end: `0x18000a7b0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `636`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800044a8`
- `0x18000487c`

## callees

- `0x180007078`
- `0x1800095a4`
- `0x1800095c4`
- `0x180009f0c`
- `0x18000a534`
- `0x18000b3c8`
- `0x18000f5f0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000a614`
- `KERNEL32!CloseHandle` at `0x18000a68c`
- `KERNEL32!CloseHandle` at `0x18000a6a4`
- `KERNEL32!CloseHandle` at `0x18000a6c3`
- `KERNEL32!CloseHandle` at `0x18000a6ef`
- `KERNEL32!CloseHandle` at `0x18000a718`
- `KERNEL32!CloseHandle` at `0x18000a614`
- `KERNEL32!CloseHandle` at `0x18000a68c`
- `KERNEL32!CloseHandle` at `0x18000a6a4`
- `KERNEL32!CloseHandle` at `0x18000a6c3`
- `KERNEL32!CloseHandle` at `0x18000a6ef`
- `KERNEL32!CloseHandle` at `0x18000a718`
- `KERNEL32!OpenSemaphoreW` at `0x18000a5c8`
- `KERNEL32!OpenSemaphoreW` at `0x18000a64a`
- `KERNEL32!OpenSemaphoreW` at `0x18000a5c8`
- `KERNEL32!OpenSemaphoreW` at `0x18000a64a`
- `KERNEL32!GetLastError` at `0x18000a72e`
- `KERNEL32!GetLastError` at `0x18000a72e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  __int64 v6; // r9
  WCHAR *v7; // rax
  WCHAR v8; // r8
  WCHAR *v9; // rcx
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v13; // rdx
  unsigned int v14; // r8d
  unsigned int LastError; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rdi
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // esi
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h] BYREF
  int v39; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v40; // [rsp+28h] [rbp-D8h]
  HANDLE v41; // [rsp+30h] [rbp-D0h]
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  v5 = 260;
  v6 = 2147483646;
  v7 = Name;
  do
  {
    if ( !v6 )
      break;
    v8 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v7++ = v8;
    --v6;
    --v5;
  }
  while ( v5 );
  v9 = v7 - 1;
  if ( v5 )
    v9 = v7;
  *v9 = 0;
  StringCchCatW(Name, v5, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  v40 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v36, v37);
    return 0;
  }
  v39 = 0;
  v38 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v39);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v14, (const char *)(unsigned int)ValueFromSemaphore, v38);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    return LastError;
  }
  StringCchCatW(Name, v13, L"h");
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v19;
  v41 = v19;
  if ( !v19 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v20, v21);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
    return LastError;
  }
  v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v38);
  v25 = v23;
  if ( v23 >= 0 )
  {
    if ( !CloseHandle(v22) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    *a3 = v39 | (unsigned __int64)((__int64)v38 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v24, (const char *)(unsigned int)v23, v38);
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x18000a534  push    rbp
0x18000a536  push    rbx
0x18000a537  push    rsi
0x18000a538  push    rdi
0x18000a539  push    r14
0x18000a53b  push    r15
0x18000a53d  lea     rbp, [rsp-168h]
0x18000a545  sub     rsp, 268h
0x18000a54c  mov     rax, cs:__security_cookie
0x18000a553  xor     rax, rsp
0x18000a556  mov     [rbp+190h+var_40], rax
0x18000a55d  mov     r14, r8
0x18000a560  xor     r15d, r15d
0x18000a563  mov     [r8], r15
0x18000a566  mov     edx, 104h
0x18000a56b  mov     r9d, 7FFFFFFEh
0x18000a571  lea     rax, [rsp+290h+Name]
0x18000a576  test    r9, r9
0x18000a579  jz      short loc_18000A59A
0x18000a57b  movzx   r8d, word ptr [rcx]
0x18000a57f  test    r8w, r8w
0x18000a583  jz      short loc_18000A59A
0x18000a585  add     rcx, 2
0x18000a589  mov     [rax], r8w
0x18000a58d  add     rax, 2
0x18000a591  dec     r9
0x18000a594  sub     rdx, 1; unsigned __int64
0x18000a598  jnz     short loc_18000A576
0x18000a59a  lea     rcx, [rax-2]
0x18000a59e  test    rdx, rdx
0x18000a5a1  cmovnz  rcx, rax
0x18000a5a5  mov     [rcx], r15w
0x18000a5a9  lea     r8, aP0; "_p0"
0x18000a5b0  lea     rcx, [rsp+290h+Name]; wchar_t *
0x18000a5b5  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a5ba  lea     r8, [rsp+290h+Name]; lpName
0x18000a5bf  xor     edx, edx; bInheritHandle
0x18000a5c1  mov     esi, 1F0003h
0x18000a5c6  mov     ecx, esi; dwDesiredAccess
0x18000a5c8  call    cs:__imp_OpenSemaphoreW
0x18000a5ce  mov     rbx, rax
0x18000a5d1  mov     [rsp+290h+var_268], rax
0x18000a5d6  test    rax, rax
0x18000a5d9  jz      loc_18000A72E
0x18000a5df  mov     [rsp+290h+var_26C], r15d
0x18000a5e4  mov     [rsp+290h+var_270], r15d; int
0x18000a5e9  lea     rdx, [rsp+290h+var_26C]; int *
0x18000a5ee  mov     rcx, rax; hHandle
0x18000a5f1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a5f6  mov     edi, eax
0x18000a5f8  test    eax, eax
0x18000a5fa  jns     short loc_18000A630
0x18000a5fc  mov     rcx, [rbp+198h]; this
0x18000a603  mov     r9d, eax; char *
0x18000a606  mov     edx, 0D6h; void *
0x18000a60b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a610  nop
0x18000a611  mov     rcx, rbx; hObject
0x18000a614  call    cs:__imp_CloseHandle
0x18000a61a  mov     rcx, [rbp+198h]; this
0x18000a621  test    eax, eax
0x18000a623  jz      loc_18000A784
0x18000a629  mov     eax, edi
0x18000a62b  jmp     loc_18000A74F
0x18000a630  lea     r8, asc_180013090; "h"
0x18000a637  lea     rcx, [rsp+290h+Name]; wchar_t *
0x18000a63c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a641  lea     r8, [rsp+290h+Name]; lpName
0x18000a646  xor     edx, edx; bInheritHandle
0x18000a648  mov     ecx, esi; dwDesiredAccess
0x18000a64a  call    cs:__imp_OpenSemaphoreW
0x18000a650  mov     rdi, rax
0x18000a653  mov     [rsp+290h+var_260], rax
0x18000a658  test    rax, rax
0x18000a65b  jz      loc_18000A702
0x18000a661  lea     rdx, [rsp+290h+var_270]; int *
0x18000a666  mov     rcx, rax; hHandle
0x18000a669  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a66e  mov     esi, eax
0x18000a670  test    eax, eax
0x18000a672  jns     short loc_18000A6C0
0x18000a674  mov     rcx, [rbp+198h]; this
0x18000a67b  mov     r9d, eax; char *
0x18000a67e  mov     edx, 0DEh; void *
0x18000a683  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a688  nop
0x18000a689  mov     rcx, rdi; hObject
0x18000a68c  call    cs:__imp_CloseHandle
0x18000a692  mov     rcx, [rbp+198h]; this
0x18000a699  test    eax, eax
0x18000a69b  jz      loc_18000A78F
0x18000a6a1  mov     rcx, rbx; hObject
0x18000a6a4  call    cs:__imp_CloseHandle
0x18000a6aa  mov     rcx, [rbp+198h]; this
0x18000a6b1  test    eax, eax
0x18000a6b3  jz      loc_18000A79A
0x18000a6b9  mov     eax, esi
0x18000a6bb  jmp     loc_18000A74F
0x18000a6c0  mov     rcx, rdi; hObject
0x18000a6c3  call    cs:__imp_CloseHandle
0x18000a6c9  mov     rcx, [rbp+198h]; this
0x18000a6d0  test    eax, eax
0x18000a6d2  jz      loc_18000A7A5
0x18000a6d8  movsxd  rcx, [rsp+290h+var_270]
0x18000a6dd  shl     rcx, 1Fh
0x18000a6e1  movsxd  rax, [rsp+290h+var_26C]
0x18000a6e6  or      rcx, rax
0x18000a6e9  mov     [r14], rcx
0x18000a6ec  mov     rcx, rbx; hObject
0x18000a6ef  call    cs:__imp_CloseHandle
0x18000a6f5  mov     rcx, [rbp+198h]; this
0x18000a6fc  test    eax, eax
0x18000a6fe  jz      short loc_18000A779
0x18000a700  jmp     short loc_18000A739
0x18000a702  mov     rcx, [rbp+198h]; this
0x18000a709  mov     edx, 0DCh; void *
0x18000a70e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a713  mov     edi, eax
0x18000a715  mov     rcx, rbx; hObject
0x18000a718  call    cs:__imp_CloseHandle
0x18000a71e  mov     rcx, [rbp+198h]; this
0x18000a725  test    eax, eax
0x18000a727  jz      short loc_18000A76E
0x18000a729  jmp     loc_18000A629
0x18000a72e  call    cs:__imp_GetLastError
0x18000a734  cmp     eax, 2
0x18000a737  jnz     short loc_18000A73D
0x18000a739  xor     eax, eax
0x18000a73b  jmp     short loc_18000A74F
0x18000a73d  mov     rcx, [rbp+198h]; this
0x18000a744  mov     edx, 0D0h; void *
0x18000a749  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a74e  nop
0x18000a74f  mov     rcx, [rbp+190h+var_40]
0x18000a756  xor     rcx, rsp; StackCookie
0x18000a759  call    __security_check_cookie
0x18000a75e  add     rsp, 268h
0x18000a765  pop     r15
0x18000a767  pop     r14
0x18000a769  pop     rdi
0x18000a76a  pop     rsi
0x18000a76b  pop     rbx
0x18000a76c  pop     rbp
0x18000a76d  retn
0x18000a76e  mov     edx, 0A0Bh; void *
0x18000a773  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a779  mov     edx, 0A0Bh; void *
0x18000a77e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a784  mov     edx, 0A0Bh; void *
0x18000a789  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a78f  mov     edx, 0A0Bh; void *
0x18000a794  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a79a  mov     edx, 0A0Bh; void *
0x18000a79f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a7a5  mov     edx, 0A0Bh; void *
0x18000a7aa  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
