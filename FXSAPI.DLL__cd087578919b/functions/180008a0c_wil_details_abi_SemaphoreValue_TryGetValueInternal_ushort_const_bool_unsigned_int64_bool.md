# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008a0c`
- end: `0x180008cbf`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003648`
- `0x1800039f4`

## callees

- `0x180005920`
- `0x180007a74`
- `0x180007a94`
- `0x180008374`
- `0x180008a0c`
- `0x180009500`
- `0x18003d510`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180008aa3`
- `KERNEL32!OpenSemaphoreW` at `0x180008b2a`
- `KERNEL32!OpenSemaphoreW` at `0x180008aa3`
- `KERNEL32!OpenSemaphoreW` at `0x180008b2a`
- `KERNEL32!CloseHandle` at `0x180008aef`
- `KERNEL32!CloseHandle` at `0x180008b6c`
- `KERNEL32!CloseHandle` at `0x180008b83`
- `KERNEL32!CloseHandle` at `0x180008ba1`
- `KERNEL32!CloseHandle` at `0x180008bcc`
- `KERNEL32!CloseHandle` at `0x180008bf8`
- `KERNEL32!CloseHandle` at `0x180008aef`
- `KERNEL32!CloseHandle` at `0x180008b6c`
- `KERNEL32!CloseHandle` at `0x180008b83`
- `KERNEL32!CloseHandle` at `0x180008ba1`
- `KERNEL32!CloseHandle` at `0x180008bcc`
- `KERNEL32!CloseHandle` at `0x180008bf8`
- `KERNEL32!GetLastError` at `0x180008c0d`
- `KERNEL32!GetLastError` at `0x180008c0d`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
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
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180008a0c  push    rbp
0x180008a0e  push    rbx
0x180008a0f  push    rsi
0x180008a10  push    rdi
0x180008a11  push    r14
0x180008a13  push    r15
0x180008a15  lea     rbp, [rsp-158h]
0x180008a1d  sub     rsp, 258h
0x180008a24  mov     rax, cs:__security_cookie
0x180008a2b  xor     rax, rsp
0x180008a2e  mov     [rbp+180h+var_40], rax
0x180008a35  xor     r15d, r15d
0x180008a38  lea     rax, [rsp+280h+Name]
0x180008a3d  mov     esi, 104h
0x180008a42  mov     [r8], r15
0x180008a45  mov     edx, esi
0x180008a47  mov     r14, r8
0x180008a4a  mov     r9d, 7FFFFFFEh
0x180008a50  test    r9, r9
0x180008a53  jz      short loc_180008A74
0x180008a55  movzx   r8d, word ptr [rcx]
0x180008a59  test    r8w, r8w
0x180008a5d  jz      short loc_180008A74
0x180008a5f  mov     [rax], r8w
0x180008a63  add     rcx, 2
0x180008a67  add     rax, 2
0x180008a6b  dec     r9
0x180008a6e  sub     rdx, 1
0x180008a72  jnz     short loc_180008A50
0x180008a74  test    rdx, rdx
0x180008a77  lea     rcx, [rax-2]
0x180008a7b  lea     r8, aP0; "_p0"
0x180008a82  mov     rdx, rsi; unsigned __int64
0x180008a85  cmovnz  rcx, rax
0x180008a89  mov     [rcx], r15w
0x180008a8d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008a92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008a97  lea     r8, [rsp+280h+Name]; lpName
0x180008a9c  xor     edx, edx; bInheritHandle
0x180008a9e  mov     ecx, 1F0003h; dwDesiredAccess
0x180008aa3  call    cs:__imp_OpenSemaphoreW
0x180008aaa  nop     dword ptr [rax+rax+00h]
0x180008aaf  mov     rbx, rax
0x180008ab2  test    rax, rax
0x180008ab5  jz      loc_180008C0D
0x180008abb  lea     rdx, [rsp+280h+var_25C]; int *
0x180008ac0  mov     [rsp+280h+var_25C], r15d
0x180008ac5  mov     rcx, rax; hHandle
0x180008ac8  mov     [rsp+280h+var_260], r15d; int
0x180008acd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008ad2  mov     edi, eax
0x180008ad4  test    eax, eax
0x180008ad6  jns     short loc_180008B0A
0x180008ad8  mov     rcx, [rbp+188h]; this
0x180008adf  mov     r9d, eax; char *
0x180008ae2  mov     edx, 0D6h; void *
0x180008ae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008aec  mov     rcx, rbx; hObject
0x180008aef  call    cs:__imp_CloseHandle
0x180008af6  nop     dword ptr [rax+rax+00h]
0x180008afb  test    eax, eax
0x180008afd  jz      loc_180008C89
0x180008b03  mov     eax, edi
0x180008b05  jmp     loc_180008C33
0x180008b0a  lea     r8, asc_180043298; "h"
0x180008b11  mov     rdx, rsi; unsigned __int64
0x180008b14  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008b19  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b1e  lea     r8, [rsp+280h+Name]; lpName
0x180008b23  xor     edx, edx; bInheritHandle
0x180008b25  mov     ecx, 1F0003h; dwDesiredAccess
0x180008b2a  call    cs:__imp_OpenSemaphoreW
0x180008b31  nop     dword ptr [rax+rax+00h]
0x180008b36  mov     rdi, rax
0x180008b39  test    rax, rax
0x180008b3c  jz      loc_180008BE2
0x180008b42  lea     rdx, [rsp+280h+var_260]; int *
0x180008b47  mov     rcx, rax; hHandle
0x180008b4a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008b4f  mov     esi, eax
0x180008b51  test    eax, eax
0x180008b53  jns     short loc_180008B9E
0x180008b55  mov     rcx, [rbp+188h]; this
0x180008b5c  mov     r9d, eax; char *
0x180008b5f  mov     edx, 0DEh; void *
0x180008b64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b69  mov     rcx, rdi; hObject
0x180008b6c  call    cs:__imp_CloseHandle
0x180008b73  nop     dword ptr [rax+rax+00h]
0x180008b78  test    eax, eax
0x180008b7a  jz      loc_180008C9B
0x180008b80  mov     rcx, rbx; hObject
0x180008b83  call    cs:__imp_CloseHandle
0x180008b8a  nop     dword ptr [rax+rax+00h]
0x180008b8f  test    eax, eax
0x180008b91  jz      loc_180008CAD
0x180008b97  mov     eax, esi
0x180008b99  jmp     loc_180008C33
0x180008b9e  mov     rcx, rdi; hObject
0x180008ba1  call    cs:__imp_CloseHandle
0x180008ba8  nop     dword ptr [rax+rax+00h]
0x180008bad  test    eax, eax
0x180008baf  jz      loc_180008C53
0x180008bb5  movsxd  rax, [rsp+280h+var_25C]
0x180008bba  movsxd  rcx, [rsp+280h+var_260]
0x180008bbf  shl     rcx, 1Fh
0x180008bc3  or      rcx, rax
0x180008bc6  mov     [r14], rcx
0x180008bc9  mov     rcx, rbx; hObject
0x180008bcc  call    cs:__imp_CloseHandle
0x180008bd3  nop     dword ptr [rax+rax+00h]
0x180008bd8  test    eax, eax
0x180008bda  jz      loc_180008C65
0x180008be0  jmp     short loc_180008C1E
0x180008be2  mov     rcx, [rbp+188h]; this
0x180008be9  mov     edx, 0DCh; void *
0x180008bee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008bf3  mov     rcx, rbx; hObject
0x180008bf6  mov     edi, eax
0x180008bf8  call    cs:__imp_CloseHandle
0x180008bff  nop     dword ptr [rax+rax+00h]
0x180008c04  test    eax, eax
0x180008c06  jz      short loc_180008C77
0x180008c08  jmp     loc_180008B03
0x180008c0d  call    cs:__imp_GetLastError
0x180008c14  nop     dword ptr [rax+rax+00h]
0x180008c19  cmp     eax, 2
0x180008c1c  jnz     short loc_180008C22
0x180008c1e  xor     eax, eax
0x180008c20  jmp     short loc_180008C33
0x180008c22  mov     rcx, [rbp+188h]; this
0x180008c29  mov     edx, 0D0h; void *
0x180008c2e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008c33  mov     rcx, [rbp+180h+var_40]
0x180008c3a  xor     rcx, rsp; StackCookie
0x180008c3d  call    __security_check_cookie
0x180008c42  add     rsp, 258h
0x180008c49  pop     r15
0x180008c4b  pop     r14
0x180008c4d  pop     rdi
0x180008c4e  pop     rsi
0x180008c4f  pop     rbx
0x180008c50  pop     rbp
0x180008c51  retn
0x180008c53  mov     rcx, [rbp+188h]; this
0x180008c5a  mov     edx, 0A0Bh; void *
0x180008c5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c65  mov     rcx, [rbp+188h]; this
0x180008c6c  mov     edx, 0A0Bh; void *
0x180008c71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c77  mov     rcx, [rbp+188h]; this
0x180008c7e  mov     edx, 0A0Bh; void *
0x180008c83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c89  mov     rcx, [rbp+188h]; this
0x180008c90  mov     edx, 0A0Bh; void *
0x180008c95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008c9b  mov     rcx, [rbp+188h]; this
0x180008ca2  mov     edx, 0A0Bh; void *
0x180008ca7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008cad  mov     rcx, [rbp+188h]; this
0x180008cb4  mov     edx, 0A0Bh; void *
0x180008cb9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
