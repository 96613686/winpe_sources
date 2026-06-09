# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000698c`
- end: `0x180006c06`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800038c8`

## callees

- `0x180001c00`
- `0x1800051a4`
- `0x180005d94`
- `0x180005db4`
- `0x1800067a0`
- `0x18000698c`
- `0x180006e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a20`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a9c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a20`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006a9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006b5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006a6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006adf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006af0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b4c`

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
0x18000698c  push    rbp
0x18000698e  push    rbx
0x18000698f  push    rsi
0x180006990  push    rdi
0x180006991  push    r14
0x180006993  push    r15
0x180006995  lea     rbp, [rsp-158h]
0x18000699d  sub     rsp, 258h
0x1800069a4  mov     rax, cs:__security_cookie
0x1800069ab  xor     rax, rsp
0x1800069ae  mov     [rbp+180h+var_40], rax
0x1800069b5  xor     r15d, r15d
0x1800069b8  lea     rax, [rsp+280h+Name]
0x1800069bd  mov     [r8], r15
0x1800069c0  mov     r14, r8
0x1800069c3  mov     edx, 104h
0x1800069c8  mov     r9d, 7FFFFFFEh
0x1800069ce  test    r9, r9
0x1800069d1  jz      short loc_1800069F2
0x1800069d3  movzx   r8d, word ptr [rcx]
0x1800069d7  test    r8w, r8w
0x1800069db  jz      short loc_1800069F2
0x1800069dd  mov     [rax], r8w
0x1800069e1  add     rcx, 2
0x1800069e5  add     rax, 2
0x1800069e9  dec     r9
0x1800069ec  sub     rdx, 1; unsigned __int64
0x1800069f0  jnz     short loc_1800069CE
0x1800069f2  test    rdx, rdx
0x1800069f5  lea     rcx, [rax-2]
0x1800069f9  lea     r8, aP0; "_p0"
0x180006a00  cmovnz  rcx, rax
0x180006a04  mov     [rcx], r15w
0x180006a08  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006a0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006a12  mov     esi, 1F0003h
0x180006a17  lea     r8, [rsp+280h+Name]; lpName
0x180006a1c  mov     ecx, esi; dwDesiredAccess
0x180006a1e  xor     edx, edx; bInheritHandle
0x180006a20  call    cs:__imp_OpenSemaphoreW
0x180006a26  mov     rbx, rax
0x180006a29  test    rax, rax
0x180006a2c  jz      loc_180006B5B
0x180006a32  lea     rdx, [rsp+280h+var_25C]; int *
0x180006a37  mov     [rsp+280h+var_25C], r15d
0x180006a3c  mov     rcx, rax; hHandle
0x180006a3f  mov     [rsp+280h+var_260], r15d; int
0x180006a44  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006a49  mov     edi, eax
0x180006a4b  test    eax, eax
0x180006a4d  jns     short loc_180006A82
0x180006a4f  mov     rcx, [rbp+188h]; this
0x180006a56  lea     r8, aWil; "wil"
0x180006a5d  mov     r9d, eax; char *
0x180006a60  mov     edx, 0D6h; void *
0x180006a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006a6a  mov     rcx, rbx; hObject
0x180006a6d  call    cs:__imp_CloseHandle
0x180006a73  test    eax, eax
0x180006a75  jz      loc_180006BD0
0x180006a7b  mov     eax, edi
0x180006a7d  jmp     loc_180006B7B
0x180006a82  lea     r8, asc_1800170C0; "h"
0x180006a89  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006a8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006a93  lea     r8, [rsp+280h+Name]; lpName
0x180006a98  xor     edx, edx; bInheritHandle
0x180006a9a  mov     ecx, esi; dwDesiredAccess
0x180006a9c  call    cs:__imp_OpenSemaphoreW
0x180006aa2  mov     rdi, rax
0x180006aa5  test    rax, rax
0x180006aa8  jz      loc_180006B36
0x180006aae  lea     rdx, [rsp+280h+var_260]; int *
0x180006ab3  mov     rcx, rax; hHandle
0x180006ab6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006abb  mov     esi, eax
0x180006abd  test    eax, eax
0x180006abf  jns     short loc_180006B02
0x180006ac1  mov     rcx, [rbp+188h]; this
0x180006ac8  lea     r8, aWil; "wil"
0x180006acf  mov     r9d, eax; char *
0x180006ad2  mov     edx, 0DEh; void *
0x180006ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006adc  mov     rcx, rdi; hObject
0x180006adf  call    cs:__imp_CloseHandle
0x180006ae5  test    eax, eax
0x180006ae7  jz      loc_180006BE2
0x180006aed  mov     rcx, rbx; hObject
0x180006af0  call    cs:__imp_CloseHandle
0x180006af6  test    eax, eax
0x180006af8  jz      loc_180006BF4
0x180006afe  mov     eax, esi
0x180006b00  jmp     short loc_180006B7B
0x180006b02  mov     rcx, rdi; hObject
0x180006b05  call    cs:__imp_CloseHandle
0x180006b0b  test    eax, eax
0x180006b0d  jz      loc_180006B9A
0x180006b13  movsxd  rax, [rsp+280h+var_25C]
0x180006b18  movsxd  rcx, [rsp+280h+var_260]
0x180006b1d  shl     rcx, 1Fh
0x180006b21  or      rcx, rax
0x180006b24  mov     [r14], rcx
0x180006b27  mov     rcx, rbx; hObject
0x180006b2a  call    cs:__imp_CloseHandle
0x180006b30  test    eax, eax
0x180006b32  jz      short loc_180006BAC
0x180006b34  jmp     short loc_180006B66
0x180006b36  mov     rcx, [rbp+188h]; this
0x180006b3d  mov     edx, 0DCh; void *
0x180006b42  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006b47  mov     rcx, rbx; hObject
0x180006b4a  mov     edi, eax
0x180006b4c  call    cs:__imp_CloseHandle
0x180006b52  test    eax, eax
0x180006b54  jz      short loc_180006BBE
0x180006b56  jmp     loc_180006A7B
0x180006b5b  call    cs:__imp_GetLastError
0x180006b61  cmp     eax, 2
0x180006b64  jnz     short loc_180006B6A
0x180006b66  xor     eax, eax
0x180006b68  jmp     short loc_180006B7B
0x180006b6a  mov     rcx, [rbp+188h]; this
0x180006b71  mov     edx, 0D0h; void *
0x180006b76  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006b7b  mov     rcx, [rbp+180h+var_40]
0x180006b82  xor     rcx, rsp; StackCookie
0x180006b85  call    __security_check_cookie
0x180006b8a  add     rsp, 258h
0x180006b91  pop     r15
0x180006b93  pop     r14
0x180006b95  pop     rdi
0x180006b96  pop     rsi
0x180006b97  pop     rbx
0x180006b98  pop     rbp
0x180006b99  retn
0x180006b9a  mov     rcx, [rbp+188h]; this
0x180006ba1  mov     edx, 0A0Bh; void *
0x180006ba6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bac  mov     rcx, [rbp+188h]; this
0x180006bb3  mov     edx, 0A0Bh; void *
0x180006bb8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bbe  mov     rcx, [rbp+188h]; this
0x180006bc5  mov     edx, 0A0Bh; void *
0x180006bca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bd0  mov     rcx, [rbp+188h]; this
0x180006bd7  mov     edx, 0A0Bh; void *
0x180006bdc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006be2  mov     rcx, [rbp+188h]; this
0x180006be9  mov     edx, 0A0Bh; void *
0x180006bee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006bf4  mov     rcx, [rbp+188h]; this
0x180006bfb  mov     edx, 0A0Bh; void *
0x180006c00  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
