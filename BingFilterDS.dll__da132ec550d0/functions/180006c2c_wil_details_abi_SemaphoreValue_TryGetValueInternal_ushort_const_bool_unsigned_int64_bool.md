# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006c2c`
- end: `0x180006ea6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003df0`

## callees

- `0x180005038`
- `0x180006244`
- `0x180006264`
- `0x180006980`
- `0x180006c2c`
- `0x1800070f4`
- `0x18000c530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006cc0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d3c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006cc0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006da5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006da5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006dec`

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
0x180006c2c  push    rbp
0x180006c2e  push    rbx
0x180006c2f  push    rsi
0x180006c30  push    rdi
0x180006c31  push    r14
0x180006c33  push    r15
0x180006c35  lea     rbp, [rsp-158h]
0x180006c3d  sub     rsp, 258h
0x180006c44  mov     rax, cs:__security_cookie
0x180006c4b  xor     rax, rsp
0x180006c4e  mov     [rbp+180h+var_40], rax
0x180006c55  xor     r15d, r15d
0x180006c58  lea     rax, [rsp+280h+Name]
0x180006c5d  mov     [r8], r15
0x180006c60  mov     r14, r8
0x180006c63  mov     edx, 104h
0x180006c68  mov     r9d, 7FFFFFFEh
0x180006c6e  test    r9, r9
0x180006c71  jz      short loc_180006C92
0x180006c73  movzx   r8d, word ptr [rcx]
0x180006c77  test    r8w, r8w
0x180006c7b  jz      short loc_180006C92
0x180006c7d  mov     [rax], r8w
0x180006c81  add     rcx, 2
0x180006c85  add     rax, 2
0x180006c89  dec     r9
0x180006c8c  sub     rdx, 1; unsigned __int64
0x180006c90  jnz     short loc_180006C6E
0x180006c92  test    rdx, rdx
0x180006c95  lea     rcx, [rax-2]
0x180006c99  lea     r8, aP0; "_p0"
0x180006ca0  cmovnz  rcx, rax
0x180006ca4  mov     [rcx], r15w
0x180006ca8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006cad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006cb2  mov     esi, 1F0003h
0x180006cb7  lea     r8, [rsp+280h+Name]; lpName
0x180006cbc  mov     ecx, esi; dwDesiredAccess
0x180006cbe  xor     edx, edx; bInheritHandle
0x180006cc0  call    cs:__imp_OpenSemaphoreW
0x180006cc6  mov     rbx, rax
0x180006cc9  test    rax, rax
0x180006ccc  jz      loc_180006DFB
0x180006cd2  lea     rdx, [rsp+280h+var_25C]; int *
0x180006cd7  mov     [rsp+280h+var_25C], r15d
0x180006cdc  mov     rcx, rax; hHandle
0x180006cdf  mov     [rsp+280h+var_260], r15d; int
0x180006ce4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006ce9  mov     edi, eax
0x180006ceb  test    eax, eax
0x180006ced  jns     short loc_180006D22
0x180006cef  mov     rcx, [rbp+188h]; this
0x180006cf6  lea     r8, aWil; "wil"
0x180006cfd  mov     r9d, eax; char *
0x180006d00  mov     edx, 0D6h; void *
0x180006d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d0a  mov     rcx, rbx; hObject
0x180006d0d  call    cs:__imp_CloseHandle
0x180006d13  test    eax, eax
0x180006d15  jz      loc_180006E70
0x180006d1b  mov     eax, edi
0x180006d1d  jmp     loc_180006E1B
0x180006d22  lea     r8, asc_180011248; "h"
0x180006d29  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006d2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006d33  lea     r8, [rsp+280h+Name]; lpName
0x180006d38  xor     edx, edx; bInheritHandle
0x180006d3a  mov     ecx, esi; dwDesiredAccess
0x180006d3c  call    cs:__imp_OpenSemaphoreW
0x180006d42  mov     rdi, rax
0x180006d45  test    rax, rax
0x180006d48  jz      loc_180006DD6
0x180006d4e  lea     rdx, [rsp+280h+var_260]; int *
0x180006d53  mov     rcx, rax; hHandle
0x180006d56  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006d5b  mov     esi, eax
0x180006d5d  test    eax, eax
0x180006d5f  jns     short loc_180006DA2
0x180006d61  mov     rcx, [rbp+188h]; this
0x180006d68  lea     r8, aWil; "wil"
0x180006d6f  mov     r9d, eax; char *
0x180006d72  mov     edx, 0DEh; void *
0x180006d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d7c  mov     rcx, rdi; hObject
0x180006d7f  call    cs:__imp_CloseHandle
0x180006d85  test    eax, eax
0x180006d87  jz      loc_180006E82
0x180006d8d  mov     rcx, rbx; hObject
0x180006d90  call    cs:__imp_CloseHandle
0x180006d96  test    eax, eax
0x180006d98  jz      loc_180006E94
0x180006d9e  mov     eax, esi
0x180006da0  jmp     short loc_180006E1B
0x180006da2  mov     rcx, rdi; hObject
0x180006da5  call    cs:__imp_CloseHandle
0x180006dab  test    eax, eax
0x180006dad  jz      loc_180006E3A
0x180006db3  movsxd  rax, [rsp+280h+var_25C]
0x180006db8  movsxd  rcx, [rsp+280h+var_260]
0x180006dbd  shl     rcx, 1Fh
0x180006dc1  or      rcx, rax
0x180006dc4  mov     [r14], rcx
0x180006dc7  mov     rcx, rbx; hObject
0x180006dca  call    cs:__imp_CloseHandle
0x180006dd0  test    eax, eax
0x180006dd2  jz      short loc_180006E4C
0x180006dd4  jmp     short loc_180006E06
0x180006dd6  mov     rcx, [rbp+188h]; this
0x180006ddd  mov     edx, 0DCh; void *
0x180006de2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006de7  mov     rcx, rbx; hObject
0x180006dea  mov     edi, eax
0x180006dec  call    cs:__imp_CloseHandle
0x180006df2  test    eax, eax
0x180006df4  jz      short loc_180006E5E
0x180006df6  jmp     loc_180006D1B
0x180006dfb  call    cs:__imp_GetLastError
0x180006e01  cmp     eax, 2
0x180006e04  jnz     short loc_180006E0A
0x180006e06  xor     eax, eax
0x180006e08  jmp     short loc_180006E1B
0x180006e0a  mov     rcx, [rbp+188h]; this
0x180006e11  mov     edx, 0D0h; void *
0x180006e16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006e1b  mov     rcx, [rbp+180h+var_40]
0x180006e22  xor     rcx, rsp; StackCookie
0x180006e25  call    __security_check_cookie
0x180006e2a  add     rsp, 258h
0x180006e31  pop     r15
0x180006e33  pop     r14
0x180006e35  pop     rdi
0x180006e36  pop     rsi
0x180006e37  pop     rbx
0x180006e38  pop     rbp
0x180006e39  retn
0x180006e3a  mov     rcx, [rbp+188h]; this
0x180006e41  mov     edx, 0A0Bh; void *
0x180006e46  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e4c  mov     rcx, [rbp+188h]; this
0x180006e53  mov     edx, 0A0Bh; void *
0x180006e58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e5e  mov     rcx, [rbp+188h]; this
0x180006e65  mov     edx, 0A0Bh; void *
0x180006e6a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e70  mov     rcx, [rbp+188h]; this
0x180006e77  mov     edx, 0A0Bh; void *
0x180006e7c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e82  mov     rcx, [rbp+188h]; this
0x180006e89  mov     edx, 0A0Bh; void *
0x180006e8e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006e94  mov     rcx, [rbp+188h]; this
0x180006e9b  mov     edx, 0A0Bh; void *
0x180006ea0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
