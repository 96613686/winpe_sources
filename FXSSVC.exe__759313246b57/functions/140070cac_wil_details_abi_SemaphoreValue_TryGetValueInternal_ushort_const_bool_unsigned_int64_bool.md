# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140070cac`
- end: `0x140070f5f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14006c548`
- `0x14006c8f4`

## callees

- `0x14000cae8`
- `0x14006dde0`
- `0x14006fdd4`
- `0x14006fdf4`
- `0x140070cac`
- `0x1400714b0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x140070d43`
- `KERNEL32!OpenSemaphoreW` at `0x140070dca`
- `KERNEL32!OpenSemaphoreW` at `0x140070d43`
- `KERNEL32!OpenSemaphoreW` at `0x140070dca`
- `KERNEL32!GetLastError` at `0x140070ead`
- `KERNEL32!GetLastError` at `0x140070ead`
- `KERNEL32!CloseHandle` at `0x140070d8f`
- `KERNEL32!CloseHandle` at `0x140070e0c`
- `KERNEL32!CloseHandle` at `0x140070e23`
- `KERNEL32!CloseHandle` at `0x140070e41`
- `KERNEL32!CloseHandle` at `0x140070e6c`
- `KERNEL32!CloseHandle` at `0x140070e98`
- `KERNEL32!CloseHandle` at `0x140070d8f`
- `KERNEL32!CloseHandle` at `0x140070e0c`
- `KERNEL32!CloseHandle` at `0x140070e23`
- `KERNEL32!CloseHandle` at `0x140070e41`
- `KERNEL32!CloseHandle` at `0x140070e6c`
- `KERNEL32!CloseHandle` at `0x140070e98`

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
0x140070cac  push    rbp
0x140070cae  push    rbx
0x140070caf  push    rsi
0x140070cb0  push    rdi
0x140070cb1  push    r14
0x140070cb3  push    r15
0x140070cb5  lea     rbp, [rsp-158h]
0x140070cbd  sub     rsp, 258h
0x140070cc4  mov     rax, cs:__security_cookie
0x140070ccb  xor     rax, rsp
0x140070cce  mov     [rbp+180h+var_40], rax
0x140070cd5  xor     r15d, r15d
0x140070cd8  lea     rax, [rsp+280h+Name]
0x140070cdd  mov     esi, 104h
0x140070ce2  mov     [r8], r15
0x140070ce5  mov     edx, esi
0x140070ce7  mov     r14, r8
0x140070cea  mov     r9d, 7FFFFFFEh
0x140070cf0  test    r9, r9
0x140070cf3  jz      short loc_140070D14
0x140070cf5  movzx   r8d, word ptr [rcx]
0x140070cf9  test    r8w, r8w
0x140070cfd  jz      short loc_140070D14
0x140070cff  mov     [rax], r8w
0x140070d03  add     rcx, 2
0x140070d07  add     rax, 2
0x140070d0b  dec     r9
0x140070d0e  sub     rdx, 1
0x140070d12  jnz     short loc_140070CF0
0x140070d14  test    rdx, rdx
0x140070d17  lea     rcx, [rax-2]
0x140070d1b  lea     r8, aP0; "_p0"
0x140070d22  mov     rdx, rsi; unsigned __int64
0x140070d25  cmovnz  rcx, rax
0x140070d29  mov     [rcx], r15w
0x140070d2d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140070d32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140070d37  lea     r8, [rsp+280h+Name]; lpName
0x140070d3c  xor     edx, edx; bInheritHandle
0x140070d3e  mov     ecx, 1F0003h; dwDesiredAccess
0x140070d43  call    cs:__imp_OpenSemaphoreW
0x140070d4a  nop     dword ptr [rax+rax+00h]
0x140070d4f  mov     rbx, rax
0x140070d52  test    rax, rax
0x140070d55  jz      loc_140070EAD
0x140070d5b  lea     rdx, [rsp+280h+var_25C]; int *
0x140070d60  mov     [rsp+280h+var_25C], r15d
0x140070d65  mov     rcx, rax; hHandle
0x140070d68  mov     [rsp+280h+var_260], r15d; int
0x140070d6d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140070d72  mov     edi, eax
0x140070d74  test    eax, eax
0x140070d76  jns     short loc_140070DAA
0x140070d78  mov     rcx, [rbp+188h]; this
0x140070d7f  mov     r9d, eax; char *
0x140070d82  mov     edx, 0D6h; void *
0x140070d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140070d8c  mov     rcx, rbx; hObject
0x140070d8f  call    cs:__imp_CloseHandle
0x140070d96  nop     dword ptr [rax+rax+00h]
0x140070d9b  test    eax, eax
0x140070d9d  jz      loc_140070F29
0x140070da3  mov     eax, edi
0x140070da5  jmp     loc_140070ED3
0x140070daa  lea     r8, asc_1400955B4; "h"
0x140070db1  mov     rdx, rsi; unsigned __int64
0x140070db4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140070db9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140070dbe  lea     r8, [rsp+280h+Name]; lpName
0x140070dc3  xor     edx, edx; bInheritHandle
0x140070dc5  mov     ecx, 1F0003h; dwDesiredAccess
0x140070dca  call    cs:__imp_OpenSemaphoreW
0x140070dd1  nop     dword ptr [rax+rax+00h]
0x140070dd6  mov     rdi, rax
0x140070dd9  test    rax, rax
0x140070ddc  jz      loc_140070E82
0x140070de2  lea     rdx, [rsp+280h+var_260]; int *
0x140070de7  mov     rcx, rax; hHandle
0x140070dea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140070def  mov     esi, eax
0x140070df1  test    eax, eax
0x140070df3  jns     short loc_140070E3E
0x140070df5  mov     rcx, [rbp+188h]; this
0x140070dfc  mov     r9d, eax; char *
0x140070dff  mov     edx, 0DEh; void *
0x140070e04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140070e09  mov     rcx, rdi; hObject
0x140070e0c  call    cs:__imp_CloseHandle
0x140070e13  nop     dword ptr [rax+rax+00h]
0x140070e18  test    eax, eax
0x140070e1a  jz      loc_140070F3B
0x140070e20  mov     rcx, rbx; hObject
0x140070e23  call    cs:__imp_CloseHandle
0x140070e2a  nop     dword ptr [rax+rax+00h]
0x140070e2f  test    eax, eax
0x140070e31  jz      loc_140070F4D
0x140070e37  mov     eax, esi
0x140070e39  jmp     loc_140070ED3
0x140070e3e  mov     rcx, rdi; hObject
0x140070e41  call    cs:__imp_CloseHandle
0x140070e48  nop     dword ptr [rax+rax+00h]
0x140070e4d  test    eax, eax
0x140070e4f  jz      loc_140070EF3
0x140070e55  movsxd  rax, [rsp+280h+var_25C]
0x140070e5a  movsxd  rcx, [rsp+280h+var_260]
0x140070e5f  shl     rcx, 1Fh
0x140070e63  or      rcx, rax
0x140070e66  mov     [r14], rcx
0x140070e69  mov     rcx, rbx; hObject
0x140070e6c  call    cs:__imp_CloseHandle
0x140070e73  nop     dword ptr [rax+rax+00h]
0x140070e78  test    eax, eax
0x140070e7a  jz      loc_140070F05
0x140070e80  jmp     short loc_140070EBE
0x140070e82  mov     rcx, [rbp+188h]; this
0x140070e89  mov     edx, 0DCh; void *
0x140070e8e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140070e93  mov     rcx, rbx; hObject
0x140070e96  mov     edi, eax
0x140070e98  call    cs:__imp_CloseHandle
0x140070e9f  nop     dword ptr [rax+rax+00h]
0x140070ea4  test    eax, eax
0x140070ea6  jz      short loc_140070F17
0x140070ea8  jmp     loc_140070DA3
0x140070ead  call    cs:__imp_GetLastError
0x140070eb4  nop     dword ptr [rax+rax+00h]
0x140070eb9  cmp     eax, 2
0x140070ebc  jnz     short loc_140070EC2
0x140070ebe  xor     eax, eax
0x140070ec0  jmp     short loc_140070ED3
0x140070ec2  mov     rcx, [rbp+188h]; this
0x140070ec9  mov     edx, 0D0h; void *
0x140070ece  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140070ed3  mov     rcx, [rbp+180h+var_40]
0x140070eda  xor     rcx, rsp; StackCookie
0x140070edd  call    __security_check_cookie
0x140070ee2  add     rsp, 258h
0x140070ee9  pop     r15
0x140070eeb  pop     r14
0x140070eed  pop     rdi
0x140070eee  pop     rsi
0x140070eef  pop     rbx
0x140070ef0  pop     rbp
0x140070ef1  retn
0x140070ef3  mov     rcx, [rbp+188h]; this
0x140070efa  mov     edx, 0A0Bh; void *
0x140070eff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140070f05  mov     rcx, [rbp+188h]; this
0x140070f0c  mov     edx, 0A0Bh; void *
0x140070f11  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140070f17  mov     rcx, [rbp+188h]; this
0x140070f1e  mov     edx, 0A0Bh; void *
0x140070f23  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140070f29  mov     rcx, [rbp+188h]; this
0x140070f30  mov     edx, 0A0Bh; void *
0x140070f35  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140070f3b  mov     rcx, [rbp+188h]; this
0x140070f42  mov     edx, 0A0Bh; void *
0x140070f47  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140070f4d  mov     rcx, [rbp+188h]; this
0x140070f54  mov     edx, 0A0Bh; void *
0x140070f59  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
