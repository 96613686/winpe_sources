# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005d7c`
- end: `0x140005ff6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003960`
- `0x140008710`

## callees

- `0x1400048d4`
- `0x140005454`
- `0x140005474`
- `0x140005bf4`
- `0x140005d7c`
- `0x140006244`
- `0x14000e1c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005f4b`
- `KERNEL32!GetLastError` at `0x140005f4b`
- `KERNEL32!OpenSemaphoreW` at `0x140005e10`
- `KERNEL32!OpenSemaphoreW` at `0x140005e8c`
- `KERNEL32!OpenSemaphoreW` at `0x140005e10`
- `KERNEL32!OpenSemaphoreW` at `0x140005e8c`
- `KERNEL32!CloseHandle` at `0x140005e5d`
- `KERNEL32!CloseHandle` at `0x140005ecf`
- `KERNEL32!CloseHandle` at `0x140005ee0`
- `KERNEL32!CloseHandle` at `0x140005ef5`
- `KERNEL32!CloseHandle` at `0x140005f1a`
- `KERNEL32!CloseHandle` at `0x140005f3c`
- `KERNEL32!CloseHandle` at `0x140005e5d`
- `KERNEL32!CloseHandle` at `0x140005ecf`
- `KERNEL32!CloseHandle` at `0x140005ee0`
- `KERNEL32!CloseHandle` at `0x140005ef5`
- `KERNEL32!CloseHandle` at `0x140005f1a`
- `KERNEL32!CloseHandle` at `0x140005f3c`

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
0x140005d7c  push    rbp
0x140005d7e  push    rbx
0x140005d7f  push    rsi
0x140005d80  push    rdi
0x140005d81  push    r14
0x140005d83  push    r15
0x140005d85  lea     rbp, [rsp-158h]
0x140005d8d  sub     rsp, 258h
0x140005d94  mov     rax, cs:__security_cookie
0x140005d9b  xor     rax, rsp
0x140005d9e  mov     [rbp+180h+var_40], rax
0x140005da5  xor     r15d, r15d
0x140005da8  lea     rax, [rsp+280h+Name]
0x140005dad  mov     [r8], r15
0x140005db0  mov     r14, r8
0x140005db3  mov     edx, 104h
0x140005db8  mov     r9d, 7FFFFFFEh
0x140005dbe  test    r9, r9
0x140005dc1  jz      short loc_140005DE2
0x140005dc3  movzx   r8d, word ptr [rcx]
0x140005dc7  test    r8w, r8w
0x140005dcb  jz      short loc_140005DE2
0x140005dcd  mov     [rax], r8w
0x140005dd1  add     rcx, 2
0x140005dd5  add     rax, 2
0x140005dd9  dec     r9
0x140005ddc  sub     rdx, 1; unsigned __int64
0x140005de0  jnz     short loc_140005DBE
0x140005de2  test    rdx, rdx
0x140005de5  lea     rcx, [rax-2]
0x140005de9  lea     r8, aP0; "_p0"
0x140005df0  cmovnz  rcx, rax
0x140005df4  mov     [rcx], r15w
0x140005df8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005dfd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005e02  mov     esi, 1F0003h
0x140005e07  lea     r8, [rsp+280h+Name]; lpName
0x140005e0c  mov     ecx, esi; dwDesiredAccess
0x140005e0e  xor     edx, edx; bInheritHandle
0x140005e10  call    cs:__imp_OpenSemaphoreW
0x140005e16  mov     rbx, rax
0x140005e19  test    rax, rax
0x140005e1c  jz      loc_140005F4B
0x140005e22  lea     rdx, [rsp+280h+var_25C]; int *
0x140005e27  mov     [rsp+280h+var_25C], r15d
0x140005e2c  mov     rcx, rax; hHandle
0x140005e2f  mov     [rsp+280h+var_260], r15d; int
0x140005e34  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005e39  mov     edi, eax
0x140005e3b  test    eax, eax
0x140005e3d  jns     short loc_140005E72
0x140005e3f  mov     rcx, [rbp+188h]; this
0x140005e46  lea     r8, aWil; "wil"
0x140005e4d  mov     r9d, eax; char *
0x140005e50  mov     edx, 0D6h; void *
0x140005e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005e5a  mov     rcx, rbx; hObject
0x140005e5d  call    cs:__imp_CloseHandle
0x140005e63  test    eax, eax
0x140005e65  jz      loc_140005FC0
0x140005e6b  mov     eax, edi
0x140005e6d  jmp     loc_140005F6B
0x140005e72  lea     r8, asc_140013478; "h"
0x140005e79  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140005e7e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005e83  lea     r8, [rsp+280h+Name]; lpName
0x140005e88  xor     edx, edx; bInheritHandle
0x140005e8a  mov     ecx, esi; dwDesiredAccess
0x140005e8c  call    cs:__imp_OpenSemaphoreW
0x140005e92  mov     rdi, rax
0x140005e95  test    rax, rax
0x140005e98  jz      loc_140005F26
0x140005e9e  lea     rdx, [rsp+280h+var_260]; int *
0x140005ea3  mov     rcx, rax; hHandle
0x140005ea6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005eab  mov     esi, eax
0x140005ead  test    eax, eax
0x140005eaf  jns     short loc_140005EF2
0x140005eb1  mov     rcx, [rbp+188h]; this
0x140005eb8  lea     r8, aWil; "wil"
0x140005ebf  mov     r9d, eax; char *
0x140005ec2  mov     edx, 0DEh; void *
0x140005ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005ecc  mov     rcx, rdi; hObject
0x140005ecf  call    cs:__imp_CloseHandle
0x140005ed5  test    eax, eax
0x140005ed7  jz      loc_140005FD2
0x140005edd  mov     rcx, rbx; hObject
0x140005ee0  call    cs:__imp_CloseHandle
0x140005ee6  test    eax, eax
0x140005ee8  jz      loc_140005FE4
0x140005eee  mov     eax, esi
0x140005ef0  jmp     short loc_140005F6B
0x140005ef2  mov     rcx, rdi; hObject
0x140005ef5  call    cs:__imp_CloseHandle
0x140005efb  test    eax, eax
0x140005efd  jz      loc_140005F8A
0x140005f03  movsxd  rax, [rsp+280h+var_25C]
0x140005f08  movsxd  rcx, [rsp+280h+var_260]
0x140005f0d  shl     rcx, 1Fh
0x140005f11  or      rcx, rax
0x140005f14  mov     [r14], rcx
0x140005f17  mov     rcx, rbx; hObject
0x140005f1a  call    cs:__imp_CloseHandle
0x140005f20  test    eax, eax
0x140005f22  jz      short loc_140005F9C
0x140005f24  jmp     short loc_140005F56
0x140005f26  mov     rcx, [rbp+188h]; this
0x140005f2d  mov     edx, 0DCh; void *
0x140005f32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005f37  mov     rcx, rbx; hObject
0x140005f3a  mov     edi, eax
0x140005f3c  call    cs:__imp_CloseHandle
0x140005f42  test    eax, eax
0x140005f44  jz      short loc_140005FAE
0x140005f46  jmp     loc_140005E6B
0x140005f4b  call    cs:__imp_GetLastError
0x140005f51  cmp     eax, 2
0x140005f54  jnz     short loc_140005F5A
0x140005f56  xor     eax, eax
0x140005f58  jmp     short loc_140005F6B
0x140005f5a  mov     rcx, [rbp+188h]; this
0x140005f61  mov     edx, 0D0h; void *
0x140005f66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005f6b  mov     rcx, [rbp+180h+var_40]
0x140005f72  xor     rcx, rsp; StackCookie
0x140005f75  call    __security_check_cookie
0x140005f7a  add     rsp, 258h
0x140005f81  pop     r15
0x140005f83  pop     r14
0x140005f85  pop     rdi
0x140005f86  pop     rsi
0x140005f87  pop     rbx
0x140005f88  pop     rbp
0x140005f89  retn
0x140005f8a  mov     rcx, [rbp+188h]; this
0x140005f91  mov     edx, 0A0Bh; void *
0x140005f96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005f9c  mov     rcx, [rbp+188h]; this
0x140005fa3  mov     edx, 0A0Bh; void *
0x140005fa8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005fae  mov     rcx, [rbp+188h]; this
0x140005fb5  mov     edx, 0A0Bh; void *
0x140005fba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005fc0  mov     rcx, [rbp+188h]; this
0x140005fc7  mov     edx, 0A0Bh; void *
0x140005fcc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005fd2  mov     rcx, [rbp+188h]; this
0x140005fd9  mov     edx, 0A0Bh; void *
0x140005fde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140005fe4  mov     rcx, [rbp+188h]; this
0x140005feb  mov     edx, 0A0Bh; void *
0x140005ff0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
