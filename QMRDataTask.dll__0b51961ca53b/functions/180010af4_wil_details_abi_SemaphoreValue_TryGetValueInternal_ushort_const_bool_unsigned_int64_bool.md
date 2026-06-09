# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180010af4`
- end: `0x180010d60`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006108`
- `0x1800064ac`

## callees

- `0x18000ab90`
- `0x18000df64`
- `0x18000df84`
- `0x180010548`
- `0x180010af4`
- `0x18001139c`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010cb5`
- `KERNEL32!GetLastError` at `0x180010cb5`
- `KERNEL32!CloseHandle` at `0x180010bce`
- `KERNEL32!CloseHandle` at `0x180010c39`
- `KERNEL32!CloseHandle` at `0x180010c4a`
- `KERNEL32!CloseHandle` at `0x180010c5f`
- `KERNEL32!CloseHandle` at `0x180010c84`
- `KERNEL32!CloseHandle` at `0x180010ca6`
- `KERNEL32!CloseHandle` at `0x180010bce`
- `KERNEL32!CloseHandle` at `0x180010c39`
- `KERNEL32!CloseHandle` at `0x180010c4a`
- `KERNEL32!CloseHandle` at `0x180010c5f`
- `KERNEL32!CloseHandle` at `0x180010c84`
- `KERNEL32!CloseHandle` at `0x180010ca6`
- `KERNEL32!OpenSemaphoreW` at `0x180010b88`
- `KERNEL32!OpenSemaphoreW` at `0x180010bfd`
- `KERNEL32!OpenSemaphoreW` at `0x180010b88`
- `KERNEL32!OpenSemaphoreW` at `0x180010bfd`

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
  int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  int v23; // r8d
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x180010af4  push    rbp
0x180010af6  push    rbx
0x180010af7  push    rsi
0x180010af8  push    rdi
0x180010af9  push    r14
0x180010afb  push    r15
0x180010afd  lea     rbp, [rsp-158h]
0x180010b05  sub     rsp, 258h
0x180010b0c  mov     rax, cs:__security_cookie
0x180010b13  xor     rax, rsp
0x180010b16  mov     [rbp+180h+var_40], rax
0x180010b1d  xor     r15d, r15d
0x180010b20  lea     rax, [rsp+280h+Name]
0x180010b25  mov     [r8], r15
0x180010b28  mov     r14, r8
0x180010b2b  mov     edx, 104h
0x180010b30  mov     r9d, 7FFFFFFEh
0x180010b36  test    r9, r9
0x180010b39  jz      short loc_180010B5A
0x180010b3b  movzx   r8d, word ptr [rcx]
0x180010b3f  test    r8w, r8w
0x180010b43  jz      short loc_180010B5A
0x180010b45  mov     [rax], r8w
0x180010b49  add     rcx, 2
0x180010b4d  add     rax, 2
0x180010b51  dec     r9
0x180010b54  sub     rdx, 1; unsigned __int64
0x180010b58  jnz     short loc_180010B36
0x180010b5a  test    rdx, rdx
0x180010b5d  lea     rcx, [rax-2]
0x180010b61  lea     r8, aP0; "_p0"
0x180010b68  cmovnz  rcx, rax
0x180010b6c  mov     [rcx], r15w
0x180010b70  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010b75  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010b7a  mov     esi, 1F0003h
0x180010b7f  lea     r8, [rsp+280h+Name]; lpName
0x180010b84  mov     ecx, esi; dwDesiredAccess
0x180010b86  xor     edx, edx; bInheritHandle
0x180010b88  call    cs:__imp_OpenSemaphoreW
0x180010b8e  mov     rbx, rax
0x180010b91  test    rax, rax
0x180010b94  jz      loc_180010CB5
0x180010b9a  lea     rdx, [rsp+280h+var_25C]; int *
0x180010b9f  mov     [rsp+280h+var_25C], r15d
0x180010ba4  mov     rcx, rax; hHandle
0x180010ba7  mov     [rsp+280h+var_260], r15d; int
0x180010bac  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010bb1  mov     edi, eax
0x180010bb3  test    eax, eax
0x180010bb5  jns     short loc_180010BE3
0x180010bb7  mov     rcx, [rbp+188h]; this
0x180010bbe  mov     r9d, eax; char *
0x180010bc1  mov     edx, 0D6h; void *
0x180010bc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bcb  mov     rcx, rbx; hObject
0x180010bce  call    cs:__imp_CloseHandle
0x180010bd4  test    eax, eax
0x180010bd6  jz      loc_180010D2A
0x180010bdc  mov     eax, edi
0x180010bde  jmp     loc_180010CD5
0x180010be3  lea     r8, asc_180018C38; "h"
0x180010bea  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180010bef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010bf4  lea     r8, [rsp+280h+Name]; lpName
0x180010bf9  xor     edx, edx; bInheritHandle
0x180010bfb  mov     ecx, esi; dwDesiredAccess
0x180010bfd  call    cs:__imp_OpenSemaphoreW
0x180010c03  mov     rdi, rax
0x180010c06  test    rax, rax
0x180010c09  jz      loc_180010C90
0x180010c0f  lea     rdx, [rsp+280h+var_260]; int *
0x180010c14  mov     rcx, rax; hHandle
0x180010c17  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010c1c  mov     esi, eax
0x180010c1e  test    eax, eax
0x180010c20  jns     short loc_180010C5C
0x180010c22  mov     rcx, [rbp+188h]; this
0x180010c29  mov     r9d, eax; char *
0x180010c2c  mov     edx, 0DEh; void *
0x180010c31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c36  mov     rcx, rdi; hObject
0x180010c39  call    cs:__imp_CloseHandle
0x180010c3f  test    eax, eax
0x180010c41  jz      loc_180010D3C
0x180010c47  mov     rcx, rbx; hObject
0x180010c4a  call    cs:__imp_CloseHandle
0x180010c50  test    eax, eax
0x180010c52  jz      loc_180010D4E
0x180010c58  mov     eax, esi
0x180010c5a  jmp     short loc_180010CD5
0x180010c5c  mov     rcx, rdi; hObject
0x180010c5f  call    cs:__imp_CloseHandle
0x180010c65  test    eax, eax
0x180010c67  jz      loc_180010CF4
0x180010c6d  movsxd  rax, [rsp+280h+var_25C]
0x180010c72  movsxd  rcx, [rsp+280h+var_260]
0x180010c77  shl     rcx, 1Fh
0x180010c7b  or      rcx, rax
0x180010c7e  mov     [r14], rcx
0x180010c81  mov     rcx, rbx; hObject
0x180010c84  call    cs:__imp_CloseHandle
0x180010c8a  test    eax, eax
0x180010c8c  jz      short loc_180010D06
0x180010c8e  jmp     short loc_180010CC0
0x180010c90  mov     rcx, [rbp+188h]; this
0x180010c97  mov     edx, 0DCh; void *
0x180010c9c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010ca1  mov     rcx, rbx; hObject
0x180010ca4  mov     edi, eax
0x180010ca6  call    cs:__imp_CloseHandle
0x180010cac  test    eax, eax
0x180010cae  jz      short loc_180010D18
0x180010cb0  jmp     loc_180010BDC
0x180010cb5  call    cs:__imp_GetLastError
0x180010cbb  cmp     eax, 2
0x180010cbe  jnz     short loc_180010CC4
0x180010cc0  xor     eax, eax
0x180010cc2  jmp     short loc_180010CD5
0x180010cc4  mov     rcx, [rbp+188h]; this
0x180010ccb  mov     edx, 0D0h; void *
0x180010cd0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010cd5  mov     rcx, [rbp+180h+var_40]
0x180010cdc  xor     rcx, rsp; StackCookie
0x180010cdf  call    __security_check_cookie
0x180010ce4  add     rsp, 258h
0x180010ceb  pop     r15
0x180010ced  pop     r14
0x180010cef  pop     rdi
0x180010cf0  pop     rsi
0x180010cf1  pop     rbx
0x180010cf2  pop     rbp
0x180010cf3  retn
0x180010cf4  mov     rcx, [rbp+188h]; this
0x180010cfb  mov     edx, 0A0Bh; void *
0x180010d00  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d06  mov     rcx, [rbp+188h]; this
0x180010d0d  mov     edx, 0A0Bh; void *
0x180010d12  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d18  mov     rcx, [rbp+188h]; this
0x180010d1f  mov     edx, 0A0Bh; void *
0x180010d24  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d2a  mov     rcx, [rbp+188h]; this
0x180010d31  mov     edx, 0A0Bh; void *
0x180010d36  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d3c  mov     rcx, [rbp+188h]; this
0x180010d43  mov     edx, 0A0Bh; void *
0x180010d48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180010d4e  mov     rcx, [rbp+188h]; this
0x180010d55  mov     edx, 0A0Bh; void *
0x180010d5a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
