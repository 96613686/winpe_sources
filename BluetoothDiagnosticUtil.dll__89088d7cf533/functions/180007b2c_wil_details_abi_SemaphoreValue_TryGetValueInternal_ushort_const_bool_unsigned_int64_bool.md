# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007b2c`
- end: `0x180007dd6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004cb4`

## callees

- `0x180005a44`
- `0x180007214`
- `0x180007234`
- `0x18000798c`
- `0x180007b2c`
- `0x180008068`
- `0x180009c90`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180007bc0`
- `KERNEL32!OpenSemaphoreW` at `0x180007c41`
- `KERNEL32!OpenSemaphoreW` at `0x180007bc0`
- `KERNEL32!OpenSemaphoreW` at `0x180007c41`
- `KERNEL32!CloseHandle` at `0x180007c0c`
- `KERNEL32!CloseHandle` at `0x180007c83`
- `KERNEL32!CloseHandle` at `0x180007c9a`
- `KERNEL32!CloseHandle` at `0x180007cb8`
- `KERNEL32!CloseHandle` at `0x180007ce3`
- `KERNEL32!CloseHandle` at `0x180007d0f`
- `KERNEL32!CloseHandle` at `0x180007c0c`
- `KERNEL32!CloseHandle` at `0x180007c83`
- `KERNEL32!CloseHandle` at `0x180007c9a`
- `KERNEL32!CloseHandle` at `0x180007cb8`
- `KERNEL32!CloseHandle` at `0x180007ce3`
- `KERNEL32!CloseHandle` at `0x180007d0f`
- `KERNEL32!GetLastError` at `0x180007d24`
- `KERNEL32!GetLastError` at `0x180007d24`

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
0x180007b2c  push    rbp
0x180007b2e  push    rbx
0x180007b2f  push    rsi
0x180007b30  push    rdi
0x180007b31  push    r14
0x180007b33  push    r15
0x180007b35  lea     rbp, [rsp-158h]
0x180007b3d  sub     rsp, 258h
0x180007b44  mov     rax, cs:__security_cookie
0x180007b4b  xor     rax, rsp
0x180007b4e  mov     [rbp+180h+var_40], rax
0x180007b55  xor     r15d, r15d
0x180007b58  lea     rax, [rsp+280h+Name]
0x180007b5d  mov     [r8], r15
0x180007b60  mov     r14, r8
0x180007b63  mov     edx, 104h
0x180007b68  mov     r9d, 7FFFFFFEh
0x180007b6e  test    r9, r9
0x180007b71  jz      short loc_180007B92
0x180007b73  movzx   r8d, word ptr [rcx]
0x180007b77  test    r8w, r8w
0x180007b7b  jz      short loc_180007B92
0x180007b7d  mov     [rax], r8w
0x180007b81  add     rcx, 2
0x180007b85  add     rax, 2
0x180007b89  dec     r9
0x180007b8c  sub     rdx, 1; unsigned __int64
0x180007b90  jnz     short loc_180007B6E
0x180007b92  test    rdx, rdx
0x180007b95  lea     rcx, [rax-2]
0x180007b99  lea     r8, aP0; "_p0"
0x180007ba0  cmovnz  rcx, rax
0x180007ba4  mov     [rcx], r15w
0x180007ba8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007bad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007bb2  mov     esi, 1F0003h
0x180007bb7  lea     r8, [rsp+280h+Name]; lpName
0x180007bbc  mov     ecx, esi; dwDesiredAccess
0x180007bbe  xor     edx, edx; bInheritHandle
0x180007bc0  call    cs:__imp_OpenSemaphoreW
0x180007bc7  nop     dword ptr [rax+rax+00h]
0x180007bcc  mov     rbx, rax
0x180007bcf  test    rax, rax
0x180007bd2  jz      loc_180007D24
0x180007bd8  lea     rdx, [rsp+280h+var_25C]; int *
0x180007bdd  mov     [rsp+280h+var_25C], r15d
0x180007be2  mov     rcx, rax; hHandle
0x180007be5  mov     [rsp+280h+var_260], r15d; int
0x180007bea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007bef  mov     edi, eax
0x180007bf1  test    eax, eax
0x180007bf3  jns     short loc_180007C27
0x180007bf5  mov     rcx, [rbp+188h]; this
0x180007bfc  mov     r9d, eax; char *
0x180007bff  mov     edx, 0D6h; void *
0x180007c04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c09  mov     rcx, rbx; hObject
0x180007c0c  call    cs:__imp_CloseHandle
0x180007c13  nop     dword ptr [rax+rax+00h]
0x180007c18  test    eax, eax
0x180007c1a  jz      loc_180007DA0
0x180007c20  mov     eax, edi
0x180007c22  jmp     loc_180007D4A
0x180007c27  lea     r8, asc_18000CF10; "h"
0x180007c2e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007c33  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007c38  lea     r8, [rsp+280h+Name]; lpName
0x180007c3d  xor     edx, edx; bInheritHandle
0x180007c3f  mov     ecx, esi; dwDesiredAccess
0x180007c41  call    cs:__imp_OpenSemaphoreW
0x180007c48  nop     dword ptr [rax+rax+00h]
0x180007c4d  mov     rdi, rax
0x180007c50  test    rax, rax
0x180007c53  jz      loc_180007CF9
0x180007c59  lea     rdx, [rsp+280h+var_260]; int *
0x180007c5e  mov     rcx, rax; hHandle
0x180007c61  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007c66  mov     esi, eax
0x180007c68  test    eax, eax
0x180007c6a  jns     short loc_180007CB5
0x180007c6c  mov     rcx, [rbp+188h]; this
0x180007c73  mov     r9d, eax; char *
0x180007c76  mov     edx, 0DEh; void *
0x180007c7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c80  mov     rcx, rdi; hObject
0x180007c83  call    cs:__imp_CloseHandle
0x180007c8a  nop     dword ptr [rax+rax+00h]
0x180007c8f  test    eax, eax
0x180007c91  jz      loc_180007DB2
0x180007c97  mov     rcx, rbx; hObject
0x180007c9a  call    cs:__imp_CloseHandle
0x180007ca1  nop     dword ptr [rax+rax+00h]
0x180007ca6  test    eax, eax
0x180007ca8  jz      loc_180007DC4
0x180007cae  mov     eax, esi
0x180007cb0  jmp     loc_180007D4A
0x180007cb5  mov     rcx, rdi; hObject
0x180007cb8  call    cs:__imp_CloseHandle
0x180007cbf  nop     dword ptr [rax+rax+00h]
0x180007cc4  test    eax, eax
0x180007cc6  jz      loc_180007D6A
0x180007ccc  movsxd  rax, [rsp+280h+var_25C]
0x180007cd1  movsxd  rcx, [rsp+280h+var_260]
0x180007cd6  shl     rcx, 1Fh
0x180007cda  or      rcx, rax
0x180007cdd  mov     [r14], rcx
0x180007ce0  mov     rcx, rbx; hObject
0x180007ce3  call    cs:__imp_CloseHandle
0x180007cea  nop     dword ptr [rax+rax+00h]
0x180007cef  test    eax, eax
0x180007cf1  jz      loc_180007D7C
0x180007cf7  jmp     short loc_180007D35
0x180007cf9  mov     rcx, [rbp+188h]; this
0x180007d00  mov     edx, 0DCh; void *
0x180007d05  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007d0a  mov     rcx, rbx; hObject
0x180007d0d  mov     edi, eax
0x180007d0f  call    cs:__imp_CloseHandle
0x180007d16  nop     dword ptr [rax+rax+00h]
0x180007d1b  test    eax, eax
0x180007d1d  jz      short loc_180007D8E
0x180007d1f  jmp     loc_180007C20
0x180007d24  call    cs:__imp_GetLastError
0x180007d2b  nop     dword ptr [rax+rax+00h]
0x180007d30  cmp     eax, 2
0x180007d33  jnz     short loc_180007D39
0x180007d35  xor     eax, eax
0x180007d37  jmp     short loc_180007D4A
0x180007d39  mov     rcx, [rbp+188h]; this
0x180007d40  mov     edx, 0D0h; void *
0x180007d45  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007d4a  mov     rcx, [rbp+180h+var_40]
0x180007d51  xor     rcx, rsp; StackCookie
0x180007d54  call    __security_check_cookie
0x180007d59  add     rsp, 258h
0x180007d60  pop     r15
0x180007d62  pop     r14
0x180007d64  pop     rdi
0x180007d65  pop     rsi
0x180007d66  pop     rbx
0x180007d67  pop     rbp
0x180007d68  retn
0x180007d6a  mov     rcx, [rbp+188h]; this
0x180007d71  mov     edx, 0A0Bh; void *
0x180007d76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d7c  mov     rcx, [rbp+188h]; this
0x180007d83  mov     edx, 0A0Bh; void *
0x180007d88  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007d8e  mov     rcx, [rbp+188h]; this
0x180007d95  mov     edx, 0A0Bh; void *
0x180007d9a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007da0  mov     rcx, [rbp+188h]; this
0x180007da7  mov     edx, 0A0Bh; void *
0x180007dac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007db2  mov     rcx, [rbp+188h]; this
0x180007db9  mov     edx, 0A0Bh; void *
0x180007dbe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007dc4  mov     rcx, [rbp+188h]; this
0x180007dcb  mov     edx, 0A0Bh; void *
0x180007dd0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
