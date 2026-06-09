# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006d0c`
- end: `0x180006f9b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800045b8`
- `0x18000896c`

## callees

- `0x180002bc0`
- `0x1800056a8`
- `0x180006224`
- `0x180006244`
- `0x180006b84`
- `0x180006d0c`
- `0x1800071a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006da0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e1c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006da0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ead`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ead`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006eda`

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
0x180006d0c  push    rbp
0x180006d0e  push    rbx
0x180006d0f  push    rsi
0x180006d10  push    rdi
0x180006d11  push    r14
0x180006d13  push    r15
0x180006d15  lea     rbp, [rsp-158h]
0x180006d1d  sub     rsp, 258h
0x180006d24  mov     rax, cs:__security_cookie
0x180006d2b  xor     rax, rsp
0x180006d2e  mov     [rbp+180h+var_40], rax
0x180006d35  xor     r15d, r15d
0x180006d38  lea     rax, [rsp+280h+Name]
0x180006d3d  mov     [r8], r15
0x180006d40  mov     r14, r8
0x180006d43  mov     edx, 104h
0x180006d48  mov     r9d, 7FFFFFFEh
0x180006d4e  test    r9, r9
0x180006d51  jz      short loc_180006D72
0x180006d53  movzx   r8d, word ptr [rcx]
0x180006d57  test    r8w, r8w
0x180006d5b  jz      short loc_180006D72
0x180006d5d  mov     [rax], r8w
0x180006d61  add     rcx, 2
0x180006d65  add     rax, 2
0x180006d69  dec     r9
0x180006d6c  sub     rdx, 1; unsigned __int64
0x180006d70  jnz     short loc_180006D4E
0x180006d72  test    rdx, rdx
0x180006d75  lea     rcx, [rax-2]
0x180006d79  lea     r8, aP0; "_p0"
0x180006d80  cmovnz  rcx, rax
0x180006d84  mov     [rcx], r15w
0x180006d88  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006d8d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006d92  mov     esi, 1F0003h
0x180006d97  lea     r8, [rsp+280h+Name]; lpName
0x180006d9c  mov     ecx, esi; dwDesiredAccess
0x180006d9e  xor     edx, edx; bInheritHandle
0x180006da0  call    cs:__imp_OpenSemaphoreW
0x180006da6  mov     rbx, rax
0x180006da9  test    rax, rax
0x180006dac  jz      loc_180006EE9
0x180006db2  lea     rdx, [rsp+280h+var_25C]; int *
0x180006db7  mov     [rsp+280h+var_25C], r15d
0x180006dbc  mov     rcx, rax; hHandle
0x180006dbf  mov     [rsp+280h+var_260], r15d; int
0x180006dc4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006dc9  mov     edi, eax
0x180006dcb  test    eax, eax
0x180006dcd  jns     short loc_180006E02
0x180006dcf  mov     rcx, [rbp+188h]; this
0x180006dd6  lea     r8, aWil; "wil"
0x180006ddd  mov     r9d, eax; char *
0x180006de0  mov     edx, 0D6h; void *
0x180006de5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006dea  mov     rcx, rbx; hObject
0x180006ded  call    cs:__imp_CloseHandle
0x180006df3  test    eax, eax
0x180006df5  jz      loc_180006F65
0x180006dfb  mov     eax, edi
0x180006dfd  jmp     loc_180006F10
0x180006e02  lea     r8, asc_180013DD8; "h"
0x180006e09  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006e0e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006e13  lea     r8, [rsp+280h+Name]; lpName
0x180006e18  xor     edx, edx; bInheritHandle
0x180006e1a  mov     ecx, esi; dwDesiredAccess
0x180006e1c  call    cs:__imp_OpenSemaphoreW
0x180006e22  mov     rdi, rax
0x180006e25  test    rax, rax
0x180006e28  jz      loc_180006EBD
0x180006e2e  lea     rdx, [rsp+280h+var_260]; int *
0x180006e33  mov     rcx, rax; hHandle
0x180006e36  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006e3b  mov     esi, eax
0x180006e3d  test    eax, eax
0x180006e3f  jns     short loc_180006E85
0x180006e41  mov     rcx, [rbp+188h]; this
0x180006e48  lea     r8, aWil; "wil"
0x180006e4f  mov     r9d, eax; char *
0x180006e52  mov     edx, 0DEh; void *
0x180006e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e5c  mov     rcx, rdi; hObject
0x180006e5f  call    cs:__imp_CloseHandle
0x180006e65  test    eax, eax
0x180006e67  jz      loc_180006F77
0x180006e6d  mov     rcx, rbx; hObject
0x180006e70  call    cs:__imp_CloseHandle
0x180006e76  test    eax, eax
0x180006e78  jz      loc_180006F89
0x180006e7e  mov     eax, esi
0x180006e80  jmp     loc_180006F10
0x180006e85  mov     rcx, rdi; hObject
0x180006e88  call    cs:__imp_CloseHandle
0x180006e8e  test    eax, eax
0x180006e90  jz      loc_180006F2F
0x180006e96  movsxd  rax, [rsp+280h+var_25C]
0x180006e9b  movsxd  rcx, [rsp+280h+var_260]
0x180006ea0  shl     rcx, 1Fh
0x180006ea4  or      rcx, rax
0x180006ea7  mov     [r14], rcx
0x180006eaa  mov     rcx, rbx; hObject
0x180006ead  call    cs:__imp_CloseHandle
0x180006eb3  test    eax, eax
0x180006eb5  jz      loc_180006F41
0x180006ebb  jmp     short loc_180006EF4
0x180006ebd  mov     rcx, [rbp+188h]; this
0x180006ec4  lea     r8, aWil; "wil"
0x180006ecb  mov     edx, 0DCh; void *
0x180006ed0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006ed5  mov     rcx, rbx; hObject
0x180006ed8  mov     edi, eax
0x180006eda  call    cs:__imp_CloseHandle
0x180006ee0  test    eax, eax
0x180006ee2  jz      short loc_180006F53
0x180006ee4  jmp     loc_180006DFB
0x180006ee9  call    cs:__imp_GetLastError
0x180006eef  cmp     eax, 2
0x180006ef2  jnz     short loc_180006EF8
0x180006ef4  xor     eax, eax
0x180006ef6  jmp     short loc_180006F10
0x180006ef8  mov     rcx, [rbp+188h]; this
0x180006eff  lea     r8, aWil; "wil"
0x180006f06  mov     edx, 0D0h; void *
0x180006f0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f10  mov     rcx, [rbp+180h+var_40]
0x180006f17  xor     rcx, rsp; StackCookie
0x180006f1a  call    __security_check_cookie
0x180006f1f  add     rsp, 258h
0x180006f26  pop     r15
0x180006f28  pop     r14
0x180006f2a  pop     rdi
0x180006f2b  pop     rsi
0x180006f2c  pop     rbx
0x180006f2d  pop     rbp
0x180006f2e  retn
0x180006f2f  mov     rcx, [rbp+188h]; this
0x180006f36  mov     edx, 0A0Bh; void *
0x180006f3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f41  mov     rcx, [rbp+188h]; this
0x180006f48  mov     edx, 0A0Bh; void *
0x180006f4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f53  mov     rcx, [rbp+188h]; this
0x180006f5a  mov     edx, 0A0Bh; void *
0x180006f5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f65  mov     rcx, [rbp+188h]; this
0x180006f6c  mov     edx, 0A0Bh; void *
0x180006f71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f77  mov     rcx, [rbp+188h]; this
0x180006f7e  mov     edx, 0A0Bh; void *
0x180006f83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006f89  mov     rcx, [rbp+188h]; this
0x180006f90  mov     edx, 0A0Bh; void *
0x180006f95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
