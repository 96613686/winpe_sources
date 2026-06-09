# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009a5c`
- end: `0x180009cd6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005198`

## callees

- `0x1800033d0`
- `0x180007104`
- `0x180008f44`
- `0x180008f64`
- `0x1800098f4`
- `0x180009a5c`
- `0x18000a114`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009af0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009b6c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009af0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009baf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009baf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009bfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009c1c`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
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
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x180009a5c  push    rbp
0x180009a5e  push    rbx
0x180009a5f  push    rsi
0x180009a60  push    rdi
0x180009a61  push    r14
0x180009a63  push    r15
0x180009a65  lea     rbp, [rsp-158h]
0x180009a6d  sub     rsp, 258h
0x180009a74  mov     rax, cs:__security_cookie
0x180009a7b  xor     rax, rsp
0x180009a7e  mov     [rbp+180h+var_40], rax
0x180009a85  xor     r15d, r15d
0x180009a88  lea     rax, [rsp+280h+Name]
0x180009a8d  mov     [r8], r15
0x180009a90  mov     r14, r8
0x180009a93  mov     edx, 104h
0x180009a98  mov     r9d, 7FFFFFFEh
0x180009a9e  test    r9, r9
0x180009aa1  jz      short loc_180009AC2
0x180009aa3  movzx   r8d, word ptr [rcx]
0x180009aa7  test    r8w, r8w
0x180009aab  jz      short loc_180009AC2
0x180009aad  mov     [rax], r8w
0x180009ab1  add     rcx, 2
0x180009ab5  add     rax, 2
0x180009ab9  dec     r9
0x180009abc  sub     rdx, 1; unsigned __int64
0x180009ac0  jnz     short loc_180009A9E
0x180009ac2  test    rdx, rdx
0x180009ac5  lea     rcx, [rax-2]
0x180009ac9  lea     r8, aP0; "_p0"
0x180009ad0  cmovnz  rcx, rax
0x180009ad4  mov     [rcx], r15w
0x180009ad8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009add  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009ae2  mov     esi, 1F0003h
0x180009ae7  lea     r8, [rsp+280h+Name]; lpName
0x180009aec  mov     ecx, esi; dwDesiredAccess
0x180009aee  xor     edx, edx; bInheritHandle
0x180009af0  call    cs:__imp_OpenSemaphoreW
0x180009af6  mov     rbx, rax
0x180009af9  test    rax, rax
0x180009afc  jz      loc_180009C2B
0x180009b02  lea     rdx, [rsp+280h+var_25C]; int *
0x180009b07  mov     [rsp+280h+var_25C], r15d
0x180009b0c  mov     rcx, rax; hHandle
0x180009b0f  mov     [rsp+280h+var_260], r15d; int
0x180009b14  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009b19  mov     edi, eax
0x180009b1b  test    eax, eax
0x180009b1d  jns     short loc_180009B52
0x180009b1f  mov     rcx, [rbp+188h]; this
0x180009b26  lea     r8, aWil; "wil"
0x180009b2d  mov     r9d, eax; char *
0x180009b30  mov     edx, 0D6h; void *
0x180009b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009b3a  mov     rcx, rbx; hObject
0x180009b3d  call    cs:__imp_CloseHandle
0x180009b43  test    eax, eax
0x180009b45  jz      loc_180009CA0
0x180009b4b  mov     eax, edi
0x180009b4d  jmp     loc_180009C4B
0x180009b52  lea     r8, asc_180015440; "h"
0x180009b59  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180009b5e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009b63  lea     r8, [rsp+280h+Name]; lpName
0x180009b68  xor     edx, edx; bInheritHandle
0x180009b6a  mov     ecx, esi; dwDesiredAccess
0x180009b6c  call    cs:__imp_OpenSemaphoreW
0x180009b72  mov     rdi, rax
0x180009b75  test    rax, rax
0x180009b78  jz      loc_180009C06
0x180009b7e  lea     rdx, [rsp+280h+var_260]; int *
0x180009b83  mov     rcx, rax; hHandle
0x180009b86  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009b8b  mov     esi, eax
0x180009b8d  test    eax, eax
0x180009b8f  jns     short loc_180009BD2
0x180009b91  mov     rcx, [rbp+188h]; this
0x180009b98  lea     r8, aWil; "wil"
0x180009b9f  mov     r9d, eax; char *
0x180009ba2  mov     edx, 0DEh; void *
0x180009ba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009bac  mov     rcx, rdi; hObject
0x180009baf  call    cs:__imp_CloseHandle
0x180009bb5  test    eax, eax
0x180009bb7  jz      loc_180009CB2
0x180009bbd  mov     rcx, rbx; hObject
0x180009bc0  call    cs:__imp_CloseHandle
0x180009bc6  test    eax, eax
0x180009bc8  jz      loc_180009CC4
0x180009bce  mov     eax, esi
0x180009bd0  jmp     short loc_180009C4B
0x180009bd2  mov     rcx, rdi; hObject
0x180009bd5  call    cs:__imp_CloseHandle
0x180009bdb  test    eax, eax
0x180009bdd  jz      loc_180009C6A
0x180009be3  movsxd  rax, [rsp+280h+var_25C]
0x180009be8  movsxd  rcx, [rsp+280h+var_260]
0x180009bed  shl     rcx, 1Fh
0x180009bf1  or      rcx, rax
0x180009bf4  mov     [r14], rcx
0x180009bf7  mov     rcx, rbx; hObject
0x180009bfa  call    cs:__imp_CloseHandle
0x180009c00  test    eax, eax
0x180009c02  jz      short loc_180009C7C
0x180009c04  jmp     short loc_180009C36
0x180009c06  mov     rcx, [rbp+188h]; this
0x180009c0d  mov     edx, 0DCh; void *
0x180009c12  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009c17  mov     rcx, rbx; hObject
0x180009c1a  mov     edi, eax
0x180009c1c  call    cs:__imp_CloseHandle
0x180009c22  test    eax, eax
0x180009c24  jz      short loc_180009C8E
0x180009c26  jmp     loc_180009B4B
0x180009c2b  call    cs:__imp_GetLastError
0x180009c31  cmp     eax, 2
0x180009c34  jnz     short loc_180009C3A
0x180009c36  xor     eax, eax
0x180009c38  jmp     short loc_180009C4B
0x180009c3a  mov     rcx, [rbp+188h]; this
0x180009c41  mov     edx, 0D0h; void *
0x180009c46  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009c4b  mov     rcx, [rbp+180h+var_40]
0x180009c52  xor     rcx, rsp; StackCookie
0x180009c55  call    __security_check_cookie
0x180009c5a  add     rsp, 258h
0x180009c61  pop     r15
0x180009c63  pop     r14
0x180009c65  pop     rdi
0x180009c66  pop     rsi
0x180009c67  pop     rbx
0x180009c68  pop     rbp
0x180009c69  retn
0x180009c6a  mov     rcx, [rbp+188h]; this
0x180009c71  mov     edx, 0A0Bh; void *
0x180009c76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c7c  mov     rcx, [rbp+188h]; this
0x180009c83  mov     edx, 0A0Bh; void *
0x180009c88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009c8e  mov     rcx, [rbp+188h]; this
0x180009c95  mov     edx, 0A0Bh; void *
0x180009c9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009ca0  mov     rcx, [rbp+188h]; this
0x180009ca7  mov     edx, 0A0Bh; void *
0x180009cac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cb2  mov     rcx, [rbp+188h]; this
0x180009cb9  mov     edx, 0A0Bh; void *
0x180009cbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180009cc4  mov     rcx, [rbp+188h]; this
0x180009ccb  mov     edx, 0A0Bh; void *
0x180009cd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
