# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006cdc`
- end: `0x180006f56`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800041d4`

## callees

- `0x180002550`
- `0x180005338`
- `0x1800061f4`
- `0x180006214`
- `0x180006b54`
- `0x180006cdc`
- `0x180007158`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d70`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006dec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d70`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006dec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e9c`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x180006cdc  push    rbp
0x180006cde  push    rbx
0x180006cdf  push    rsi
0x180006ce0  push    rdi
0x180006ce1  push    r14
0x180006ce3  push    r15
0x180006ce5  lea     rbp, [rsp-158h]
0x180006ced  sub     rsp, 258h
0x180006cf4  mov     rax, cs:__security_cookie
0x180006cfb  xor     rax, rsp
0x180006cfe  mov     [rbp+180h+var_40], rax
0x180006d05  xor     r15d, r15d
0x180006d08  lea     rax, [rsp+280h+Name]
0x180006d0d  mov     [r8], r15
0x180006d10  mov     r14, r8
0x180006d13  mov     edx, 104h
0x180006d18  mov     r9d, 7FFFFFFEh
0x180006d1e  test    r9, r9
0x180006d21  jz      short loc_180006D42
0x180006d23  movzx   r8d, word ptr [rcx]
0x180006d27  test    r8w, r8w
0x180006d2b  jz      short loc_180006D42
0x180006d2d  mov     [rax], r8w
0x180006d31  add     rcx, 2
0x180006d35  add     rax, 2
0x180006d39  dec     r9
0x180006d3c  sub     rdx, 1; unsigned __int64
0x180006d40  jnz     short loc_180006D1E
0x180006d42  test    rdx, rdx
0x180006d45  lea     rcx, [rax-2]
0x180006d49  lea     r8, aP0; "_p0"
0x180006d50  cmovnz  rcx, rax
0x180006d54  mov     [rcx], r15w
0x180006d58  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006d5d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006d62  mov     esi, 1F0003h
0x180006d67  lea     r8, [rsp+280h+Name]; lpName
0x180006d6c  mov     ecx, esi; dwDesiredAccess
0x180006d6e  xor     edx, edx; bInheritHandle
0x180006d70  call    cs:__imp_OpenSemaphoreW
0x180006d76  mov     rbx, rax
0x180006d79  test    rax, rax
0x180006d7c  jz      loc_180006EAB
0x180006d82  lea     rdx, [rsp+280h+var_25C]; int *
0x180006d87  mov     [rsp+280h+var_25C], r15d
0x180006d8c  mov     rcx, rax; hHandle
0x180006d8f  mov     [rsp+280h+var_260], r15d; int
0x180006d94  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006d99  mov     edi, eax
0x180006d9b  test    eax, eax
0x180006d9d  jns     short loc_180006DD2
0x180006d9f  mov     rcx, [rbp+188h]; this
0x180006da6  lea     r8, aWil; "wil"
0x180006dad  mov     r9d, eax; char *
0x180006db0  mov     edx, 0D6h; void *
0x180006db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006dba  mov     rcx, rbx; hObject
0x180006dbd  call    cs:__imp_CloseHandle
0x180006dc3  test    eax, eax
0x180006dc5  jz      loc_180006F20
0x180006dcb  mov     eax, edi
0x180006dcd  jmp     loc_180006ECB
0x180006dd2  lea     r8, asc_180015C48; "h"
0x180006dd9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006dde  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006de3  lea     r8, [rsp+280h+Name]; lpName
0x180006de8  xor     edx, edx; bInheritHandle
0x180006dea  mov     ecx, esi; dwDesiredAccess
0x180006dec  call    cs:__imp_OpenSemaphoreW
0x180006df2  mov     rdi, rax
0x180006df5  test    rax, rax
0x180006df8  jz      loc_180006E86
0x180006dfe  lea     rdx, [rsp+280h+var_260]; int *
0x180006e03  mov     rcx, rax; hHandle
0x180006e06  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006e0b  mov     esi, eax
0x180006e0d  test    eax, eax
0x180006e0f  jns     short loc_180006E52
0x180006e11  mov     rcx, [rbp+188h]; this
0x180006e18  lea     r8, aWil; "wil"
0x180006e1f  mov     r9d, eax; char *
0x180006e22  mov     edx, 0DEh; void *
0x180006e27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e2c  mov     rcx, rdi; hObject
0x180006e2f  call    cs:__imp_CloseHandle
0x180006e35  test    eax, eax
0x180006e37  jz      loc_180006F32
0x180006e3d  mov     rcx, rbx; hObject
0x180006e40  call    cs:__imp_CloseHandle
0x180006e46  test    eax, eax
0x180006e48  jz      loc_180006F44
0x180006e4e  mov     eax, esi
0x180006e50  jmp     short loc_180006ECB
0x180006e52  mov     rcx, rdi; hObject
0x180006e55  call    cs:__imp_CloseHandle
0x180006e5b  test    eax, eax
0x180006e5d  jz      loc_180006EEA
0x180006e63  movsxd  rax, [rsp+280h+var_25C]
0x180006e68  movsxd  rcx, [rsp+280h+var_260]
0x180006e6d  shl     rcx, 1Fh
0x180006e71  or      rcx, rax
0x180006e74  mov     [r14], rcx
0x180006e77  mov     rcx, rbx; hObject
0x180006e7a  call    cs:__imp_CloseHandle
0x180006e80  test    eax, eax
0x180006e82  jz      short loc_180006EFC
0x180006e84  jmp     short loc_180006EB6
0x180006e86  mov     rcx, [rbp+188h]; this
0x180006e8d  mov     edx, 0DCh; void *
0x180006e92  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006e97  mov     rcx, rbx; hObject
0x180006e9a  mov     edi, eax
0x180006e9c  call    cs:__imp_CloseHandle
0x180006ea2  test    eax, eax
0x180006ea4  jz      short loc_180006F0E
0x180006ea6  jmp     loc_180006DCB
0x180006eab  call    cs:__imp_GetLastError
0x180006eb1  cmp     eax, 2
0x180006eb4  jnz     short loc_180006EBA
0x180006eb6  xor     eax, eax
0x180006eb8  jmp     short loc_180006ECB
0x180006eba  mov     rcx, [rbp+188h]; this
0x180006ec1  mov     edx, 0D0h; void *
0x180006ec6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006ecb  mov     rcx, [rbp+180h+var_40]
0x180006ed2  xor     rcx, rsp; StackCookie
0x180006ed5  call    __security_check_cookie
0x180006eda  add     rsp, 258h
0x180006ee1  pop     r15
0x180006ee3  pop     r14
0x180006ee5  pop     rdi
0x180006ee6  pop     rsi
0x180006ee7  pop     rbx
0x180006ee8  pop     rbp
0x180006ee9  retn
0x180006eea  mov     rcx, [rbp+188h]; this
0x180006ef1  mov     edx, 0A0Bh; void *
0x180006ef6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006efc  mov     rcx, [rbp+188h]; this
0x180006f03  mov     edx, 0A0Bh; void *
0x180006f08  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f0e  mov     rcx, [rbp+188h]; this
0x180006f15  mov     edx, 0A0Bh; void *
0x180006f1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f20  mov     rcx, [rbp+188h]; this
0x180006f27  mov     edx, 0A0Bh; void *
0x180006f2c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f32  mov     rcx, [rbp+188h]; this
0x180006f39  mov     edx, 0A0Bh; void *
0x180006f3e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f44  mov     rcx, [rbp+188h]; this
0x180006f4b  mov     edx, 0A0Bh; void *
0x180006f50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
