# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f2cc`
- end: `0x18000f538`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a1f8`
- `0x18000a59c`

## callees

- `0x1800028f0`
- `0x18000bfc4`
- `0x18000e334`
- `0x18000e354`
- `0x18000ed98`
- `0x18000f2cc`
- `0x18000fb8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f360`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f3d5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f360`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f3d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f48d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f48d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f411`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f45c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f47e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f3a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f411`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f422`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f45c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f47e`

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
0x18000f2cc  push    rbp
0x18000f2ce  push    rbx
0x18000f2cf  push    rsi
0x18000f2d0  push    rdi
0x18000f2d1  push    r14
0x18000f2d3  push    r15
0x18000f2d5  lea     rbp, [rsp-158h]
0x18000f2dd  sub     rsp, 258h
0x18000f2e4  mov     rax, cs:__security_cookie
0x18000f2eb  xor     rax, rsp
0x18000f2ee  mov     [rbp+180h+var_40], rax
0x18000f2f5  xor     r15d, r15d
0x18000f2f8  lea     rax, [rsp+280h+Name]
0x18000f2fd  mov     [r8], r15
0x18000f300  mov     r14, r8
0x18000f303  mov     edx, 104h
0x18000f308  mov     r9d, 7FFFFFFEh
0x18000f30e  test    r9, r9
0x18000f311  jz      short loc_18000F332
0x18000f313  movzx   r8d, word ptr [rcx]
0x18000f317  test    r8w, r8w
0x18000f31b  jz      short loc_18000F332
0x18000f31d  mov     [rax], r8w
0x18000f321  add     rcx, 2
0x18000f325  add     rax, 2
0x18000f329  dec     r9
0x18000f32c  sub     rdx, 1; unsigned __int64
0x18000f330  jnz     short loc_18000F30E
0x18000f332  test    rdx, rdx
0x18000f335  lea     rcx, [rax-2]
0x18000f339  lea     r8, aP0; "_p0"
0x18000f340  cmovnz  rcx, rax
0x18000f344  mov     [rcx], r15w
0x18000f348  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000f34d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f352  mov     esi, 1F0003h
0x18000f357  lea     r8, [rsp+280h+Name]; lpName
0x18000f35c  mov     ecx, esi; dwDesiredAccess
0x18000f35e  xor     edx, edx; bInheritHandle
0x18000f360  call    cs:__imp_OpenSemaphoreW
0x18000f366  mov     rbx, rax
0x18000f369  test    rax, rax
0x18000f36c  jz      loc_18000F48D
0x18000f372  lea     rdx, [rsp+280h+var_25C]; int *
0x18000f377  mov     [rsp+280h+var_25C], r15d
0x18000f37c  mov     rcx, rax; hHandle
0x18000f37f  mov     [rsp+280h+var_260], r15d; int
0x18000f384  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f389  mov     edi, eax
0x18000f38b  test    eax, eax
0x18000f38d  jns     short loc_18000F3BB
0x18000f38f  mov     rcx, [rbp+188h]; this
0x18000f396  mov     r9d, eax; char *
0x18000f399  mov     edx, 0D6h; void *
0x18000f39e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f3a3  mov     rcx, rbx; hObject
0x18000f3a6  call    cs:__imp_CloseHandle
0x18000f3ac  test    eax, eax
0x18000f3ae  jz      loc_18000F502
0x18000f3b4  mov     eax, edi
0x18000f3b6  jmp     loc_18000F4AD
0x18000f3bb  lea     r8, asc_18002EE40; "h"
0x18000f3c2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000f3c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f3cc  lea     r8, [rsp+280h+Name]; lpName
0x18000f3d1  xor     edx, edx; bInheritHandle
0x18000f3d3  mov     ecx, esi; dwDesiredAccess
0x18000f3d5  call    cs:__imp_OpenSemaphoreW
0x18000f3db  mov     rdi, rax
0x18000f3de  test    rax, rax
0x18000f3e1  jz      loc_18000F468
0x18000f3e7  lea     rdx, [rsp+280h+var_260]; int *
0x18000f3ec  mov     rcx, rax; hHandle
0x18000f3ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f3f4  mov     esi, eax
0x18000f3f6  test    eax, eax
0x18000f3f8  jns     short loc_18000F434
0x18000f3fa  mov     rcx, [rbp+188h]; this
0x18000f401  mov     r9d, eax; char *
0x18000f404  mov     edx, 0DEh; void *
0x18000f409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f40e  mov     rcx, rdi; hObject
0x18000f411  call    cs:__imp_CloseHandle
0x18000f417  test    eax, eax
0x18000f419  jz      loc_18000F514
0x18000f41f  mov     rcx, rbx; hObject
0x18000f422  call    cs:__imp_CloseHandle
0x18000f428  test    eax, eax
0x18000f42a  jz      loc_18000F526
0x18000f430  mov     eax, esi
0x18000f432  jmp     short loc_18000F4AD
0x18000f434  mov     rcx, rdi; hObject
0x18000f437  call    cs:__imp_CloseHandle
0x18000f43d  test    eax, eax
0x18000f43f  jz      loc_18000F4CC
0x18000f445  movsxd  rax, [rsp+280h+var_25C]
0x18000f44a  movsxd  rcx, [rsp+280h+var_260]
0x18000f44f  shl     rcx, 1Fh
0x18000f453  or      rcx, rax
0x18000f456  mov     [r14], rcx
0x18000f459  mov     rcx, rbx; hObject
0x18000f45c  call    cs:__imp_CloseHandle
0x18000f462  test    eax, eax
0x18000f464  jz      short loc_18000F4DE
0x18000f466  jmp     short loc_18000F498
0x18000f468  mov     rcx, [rbp+188h]; this
0x18000f46f  mov     edx, 0DCh; void *
0x18000f474  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f479  mov     rcx, rbx; hObject
0x18000f47c  mov     edi, eax
0x18000f47e  call    cs:__imp_CloseHandle
0x18000f484  test    eax, eax
0x18000f486  jz      short loc_18000F4F0
0x18000f488  jmp     loc_18000F3B4
0x18000f48d  call    cs:__imp_GetLastError
0x18000f493  cmp     eax, 2
0x18000f496  jnz     short loc_18000F49C
0x18000f498  xor     eax, eax
0x18000f49a  jmp     short loc_18000F4AD
0x18000f49c  mov     rcx, [rbp+188h]; this
0x18000f4a3  mov     edx, 0D0h; void *
0x18000f4a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f4ad  mov     rcx, [rbp+180h+var_40]
0x18000f4b4  xor     rcx, rsp; StackCookie
0x18000f4b7  call    __security_check_cookie
0x18000f4bc  add     rsp, 258h
0x18000f4c3  pop     r15
0x18000f4c5  pop     r14
0x18000f4c7  pop     rdi
0x18000f4c8  pop     rsi
0x18000f4c9  pop     rbx
0x18000f4ca  pop     rbp
0x18000f4cb  retn
0x18000f4cc  mov     rcx, [rbp+188h]; this
0x18000f4d3  mov     edx, 0A0Bh; void *
0x18000f4d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f4de  mov     rcx, [rbp+188h]; this
0x18000f4e5  mov     edx, 0A0Bh; void *
0x18000f4ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f4f0  mov     rcx, [rbp+188h]; this
0x18000f4f7  mov     edx, 0A0Bh; void *
0x18000f4fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f502  mov     rcx, [rbp+188h]; this
0x18000f509  mov     edx, 0A0Bh; void *
0x18000f50e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f514  mov     rcx, [rbp+188h]; this
0x18000f51b  mov     edx, 0A0Bh; void *
0x18000f520  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f526  mov     rcx, [rbp+188h]; this
0x18000f52d  mov     edx, 0A0Bh; void *
0x18000f532  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
