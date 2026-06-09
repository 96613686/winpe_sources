# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007c1c`
- end: `0x180007e88`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003818`
- `0x180003bbc`

## callees

- `0x180001760`
- `0x180005034`
- `0x180006d94`
- `0x180006db4`
- `0x1800077f8`
- `0x180007c1c`
- `0x18000840c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007cb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d25`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007cb0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ddd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007dce`

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
0x180007c1c  push    rbp
0x180007c1e  push    rbx
0x180007c1f  push    rsi
0x180007c20  push    rdi
0x180007c21  push    r14
0x180007c23  push    r15
0x180007c25  lea     rbp, [rsp-158h]
0x180007c2d  sub     rsp, 258h
0x180007c34  mov     rax, cs:__security_cookie
0x180007c3b  xor     rax, rsp
0x180007c3e  mov     [rbp+180h+var_40], rax
0x180007c45  xor     r15d, r15d
0x180007c48  lea     rax, [rsp+280h+Name]
0x180007c4d  mov     [r8], r15
0x180007c50  mov     r14, r8
0x180007c53  mov     edx, 104h
0x180007c58  mov     r9d, 7FFFFFFEh
0x180007c5e  test    r9, r9
0x180007c61  jz      short loc_180007C82
0x180007c63  movzx   r8d, word ptr [rcx]
0x180007c67  test    r8w, r8w
0x180007c6b  jz      short loc_180007C82
0x180007c6d  mov     [rax], r8w
0x180007c71  add     rcx, 2
0x180007c75  add     rax, 2
0x180007c79  dec     r9
0x180007c7c  sub     rdx, 1; unsigned __int64
0x180007c80  jnz     short loc_180007C5E
0x180007c82  test    rdx, rdx
0x180007c85  lea     rcx, [rax-2]
0x180007c89  lea     r8, aP0; "_p0"
0x180007c90  cmovnz  rcx, rax
0x180007c94  mov     [rcx], r15w
0x180007c98  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007c9d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007ca2  mov     esi, 1F0003h
0x180007ca7  lea     r8, [rsp+280h+Name]; lpName
0x180007cac  mov     ecx, esi; dwDesiredAccess
0x180007cae  xor     edx, edx; bInheritHandle
0x180007cb0  call    cs:__imp_OpenSemaphoreW
0x180007cb6  mov     rbx, rax
0x180007cb9  test    rax, rax
0x180007cbc  jz      loc_180007DDD
0x180007cc2  lea     rdx, [rsp+280h+var_25C]; int *
0x180007cc7  mov     [rsp+280h+var_25C], r15d
0x180007ccc  mov     rcx, rax; hHandle
0x180007ccf  mov     [rsp+280h+var_260], r15d; int
0x180007cd4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007cd9  mov     edi, eax
0x180007cdb  test    eax, eax
0x180007cdd  jns     short loc_180007D0B
0x180007cdf  mov     rcx, [rbp+188h]; this
0x180007ce6  mov     r9d, eax; char *
0x180007ce9  mov     edx, 0D6h; void *
0x180007cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007cf3  mov     rcx, rbx; hObject
0x180007cf6  call    cs:__imp_CloseHandle
0x180007cfc  test    eax, eax
0x180007cfe  jz      loc_180007E52
0x180007d04  mov     eax, edi
0x180007d06  jmp     loc_180007DFD
0x180007d0b  lea     r8, asc_180012FD8; "h"
0x180007d12  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007d17  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007d1c  lea     r8, [rsp+280h+Name]; lpName
0x180007d21  xor     edx, edx; bInheritHandle
0x180007d23  mov     ecx, esi; dwDesiredAccess
0x180007d25  call    cs:__imp_OpenSemaphoreW
0x180007d2b  mov     rdi, rax
0x180007d2e  test    rax, rax
0x180007d31  jz      loc_180007DB8
0x180007d37  lea     rdx, [rsp+280h+var_260]; int *
0x180007d3c  mov     rcx, rax; hHandle
0x180007d3f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007d44  mov     esi, eax
0x180007d46  test    eax, eax
0x180007d48  jns     short loc_180007D84
0x180007d4a  mov     rcx, [rbp+188h]; this
0x180007d51  mov     r9d, eax; char *
0x180007d54  mov     edx, 0DEh; void *
0x180007d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007d5e  mov     rcx, rdi; hObject
0x180007d61  call    cs:__imp_CloseHandle
0x180007d67  test    eax, eax
0x180007d69  jz      loc_180007E64
0x180007d6f  mov     rcx, rbx; hObject
0x180007d72  call    cs:__imp_CloseHandle
0x180007d78  test    eax, eax
0x180007d7a  jz      loc_180007E76
0x180007d80  mov     eax, esi
0x180007d82  jmp     short loc_180007DFD
0x180007d84  mov     rcx, rdi; hObject
0x180007d87  call    cs:__imp_CloseHandle
0x180007d8d  test    eax, eax
0x180007d8f  jz      loc_180007E1C
0x180007d95  movsxd  rax, [rsp+280h+var_25C]
0x180007d9a  movsxd  rcx, [rsp+280h+var_260]
0x180007d9f  shl     rcx, 1Fh
0x180007da3  or      rcx, rax
0x180007da6  mov     [r14], rcx
0x180007da9  mov     rcx, rbx; hObject
0x180007dac  call    cs:__imp_CloseHandle
0x180007db2  test    eax, eax
0x180007db4  jz      short loc_180007E2E
0x180007db6  jmp     short loc_180007DE8
0x180007db8  mov     rcx, [rbp+188h]; this
0x180007dbf  mov     edx, 0DCh; void *
0x180007dc4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007dc9  mov     rcx, rbx; hObject
0x180007dcc  mov     edi, eax
0x180007dce  call    cs:__imp_CloseHandle
0x180007dd4  test    eax, eax
0x180007dd6  jz      short loc_180007E40
0x180007dd8  jmp     loc_180007D04
0x180007ddd  call    cs:__imp_GetLastError
0x180007de3  cmp     eax, 2
0x180007de6  jnz     short loc_180007DEC
0x180007de8  xor     eax, eax
0x180007dea  jmp     short loc_180007DFD
0x180007dec  mov     rcx, [rbp+188h]; this
0x180007df3  mov     edx, 0D0h; void *
0x180007df8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007dfd  mov     rcx, [rbp+180h+var_40]
0x180007e04  xor     rcx, rsp; StackCookie
0x180007e07  call    __security_check_cookie
0x180007e0c  add     rsp, 258h
0x180007e13  pop     r15
0x180007e15  pop     r14
0x180007e17  pop     rdi
0x180007e18  pop     rsi
0x180007e19  pop     rbx
0x180007e1a  pop     rbp
0x180007e1b  retn
0x180007e1c  mov     rcx, [rbp+188h]; this
0x180007e23  mov     edx, 0A0Bh; void *
0x180007e28  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e2e  mov     rcx, [rbp+188h]; this
0x180007e35  mov     edx, 0A0Bh; void *
0x180007e3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e40  mov     rcx, [rbp+188h]; this
0x180007e47  mov     edx, 0A0Bh; void *
0x180007e4c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e52  mov     rcx, [rbp+188h]; this
0x180007e59  mov     edx, 0A0Bh; void *
0x180007e5e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e64  mov     rcx, [rbp+188h]; this
0x180007e6b  mov     edx, 0A0Bh; void *
0x180007e70  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007e76  mov     rcx, [rbp+188h]; this
0x180007e7d  mov     edx, 0A0Bh; void *
0x180007e82  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
