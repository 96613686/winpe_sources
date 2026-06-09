# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c49c`
- end: `0x18000c76b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006f1c`
- `0x1800072fc`

## callees

- `0x180003400`
- `0x180008d88`
- `0x18000b444`
- `0x18000b470`
- `0x18000be68`
- `0x18000c49c`
- `0x18000ce74`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18000c533`
- `KERNEL32!OpenSemaphoreW` at `0x18000c5c1`
- `KERNEL32!OpenSemaphoreW` at `0x18000c533`
- `KERNEL32!OpenSemaphoreW` at `0x18000c5c1`
- `KERNEL32!CloseHandle` at `0x18000c586`
- `KERNEL32!CloseHandle` at `0x18000c60a`
- `KERNEL32!CloseHandle` at `0x18000c621`
- `KERNEL32!CloseHandle` at `0x18000c63f`
- `KERNEL32!CloseHandle` at `0x18000c66a`
- `KERNEL32!CloseHandle` at `0x18000c69d`
- `KERNEL32!CloseHandle` at `0x18000c586`
- `KERNEL32!CloseHandle` at `0x18000c60a`
- `KERNEL32!CloseHandle` at `0x18000c621`
- `KERNEL32!CloseHandle` at `0x18000c63f`
- `KERNEL32!CloseHandle` at `0x18000c66a`
- `KERNEL32!CloseHandle` at `0x18000c69d`
- `KERNEL32!GetLastError` at `0x18000c6b2`
- `KERNEL32!GetLastError` at `0x18000c6b2`

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
  unsigned int LastError; // edi
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
  StringCchCatW(Name, 260, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (__int64)"wil",
      (const char *)(unsigned int)ValueFromSemaphore);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 260, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (__int64)"wil", (const char *)(unsigned int)v19);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x18000c49c  push    rbp
0x18000c49e  push    rbx
0x18000c49f  push    rsi
0x18000c4a0  push    rdi
0x18000c4a1  push    r14
0x18000c4a3  push    r15
0x18000c4a5  lea     rbp, [rsp-158h]
0x18000c4ad  sub     rsp, 258h
0x18000c4b4  mov     rax, cs:__security_cookie
0x18000c4bb  xor     rax, rsp
0x18000c4be  mov     [rbp+180h+var_40], rax
0x18000c4c5  xor     r15d, r15d
0x18000c4c8  lea     rax, [rsp+280h+Name]
0x18000c4cd  mov     esi, 104h
0x18000c4d2  mov     [r8], r15
0x18000c4d5  mov     edx, esi
0x18000c4d7  mov     r14, r8
0x18000c4da  mov     r9d, 7FFFFFFEh
0x18000c4e0  test    r9, r9
0x18000c4e3  jz      short loc_18000C504
0x18000c4e5  movzx   r8d, word ptr [rcx]
0x18000c4e9  test    r8w, r8w
0x18000c4ed  jz      short loc_18000C504
0x18000c4ef  mov     [rax], r8w
0x18000c4f3  add     rcx, 2
0x18000c4f7  add     rax, 2
0x18000c4fb  dec     r9
0x18000c4fe  sub     rdx, 1
0x18000c502  jnz     short loc_18000C4E0
0x18000c504  test    rdx, rdx
0x18000c507  lea     rcx, [rax-2]
0x18000c50b  lea     r8, aP0; "_p0"
0x18000c512  mov     rdx, rsi; unsigned __int64
0x18000c515  cmovnz  rcx, rax
0x18000c519  mov     [rcx], r15w
0x18000c51d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c522  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c527  lea     r8, [rsp+280h+Name]; lpName
0x18000c52c  xor     edx, edx; bInheritHandle
0x18000c52e  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c533  call    cs:__imp_OpenSemaphoreW
0x18000c53a  nop     dword ptr [rax+rax+00h]
0x18000c53f  mov     rbx, rax
0x18000c542  test    rax, rax
0x18000c545  jz      loc_18000C6B2
0x18000c54b  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c550  mov     [rsp+280h+var_25C], r15d
0x18000c555  mov     rcx, rax; hHandle
0x18000c558  mov     [rsp+280h+var_260], r15d; int
0x18000c55d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c562  mov     edi, eax
0x18000c564  test    eax, eax
0x18000c566  jns     short loc_18000C5A1
0x18000c568  mov     rcx, [rbp+188h]; this
0x18000c56f  lea     r8, aWil; "wil"
0x18000c576  mov     r9d, eax; char *
0x18000c579  mov     edx, 0D6h; void *
0x18000c57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c583  mov     rcx, rbx; hObject
0x18000c586  call    cs:__imp_CloseHandle
0x18000c58d  nop     dword ptr [rax+rax+00h]
0x18000c592  test    eax, eax
0x18000c594  jz      loc_18000C735
0x18000c59a  mov     eax, edi
0x18000c59c  jmp     loc_18000C6DF
0x18000c5a1  lea     r8, asc_1801E4D30; "h"
0x18000c5a8  mov     rdx, rsi; unsigned __int64
0x18000c5ab  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c5b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c5b5  lea     r8, [rsp+280h+Name]; lpName
0x18000c5ba  xor     edx, edx; bInheritHandle
0x18000c5bc  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c5c1  call    cs:__imp_OpenSemaphoreW
0x18000c5c8  nop     dword ptr [rax+rax+00h]
0x18000c5cd  mov     rdi, rax
0x18000c5d0  test    rax, rax
0x18000c5d3  jz      loc_18000C680
0x18000c5d9  lea     rdx, [rsp+280h+var_260]; int *
0x18000c5de  mov     rcx, rax; hHandle
0x18000c5e1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c5e6  mov     esi, eax
0x18000c5e8  test    eax, eax
0x18000c5ea  jns     short loc_18000C63C
0x18000c5ec  mov     rcx, [rbp+188h]; this
0x18000c5f3  lea     r8, aWil; "wil"
0x18000c5fa  mov     r9d, eax; char *
0x18000c5fd  mov     edx, 0DEh; void *
0x18000c602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c607  mov     rcx, rdi; hObject
0x18000c60a  call    cs:__imp_CloseHandle
0x18000c611  nop     dword ptr [rax+rax+00h]
0x18000c616  test    eax, eax
0x18000c618  jz      loc_18000C747
0x18000c61e  mov     rcx, rbx; hObject
0x18000c621  call    cs:__imp_CloseHandle
0x18000c628  nop     dword ptr [rax+rax+00h]
0x18000c62d  test    eax, eax
0x18000c62f  jz      loc_18000C759
0x18000c635  mov     eax, esi
0x18000c637  jmp     loc_18000C6DF
0x18000c63c  mov     rcx, rdi; hObject
0x18000c63f  call    cs:__imp_CloseHandle
0x18000c646  nop     dword ptr [rax+rax+00h]
0x18000c64b  test    eax, eax
0x18000c64d  jz      loc_18000C6FF
0x18000c653  movsxd  rax, [rsp+280h+var_25C]
0x18000c658  movsxd  rcx, [rsp+280h+var_260]
0x18000c65d  shl     rcx, 1Fh
0x18000c661  or      rcx, rax
0x18000c664  mov     [r14], rcx
0x18000c667  mov     rcx, rbx; hObject
0x18000c66a  call    cs:__imp_CloseHandle
0x18000c671  nop     dword ptr [rax+rax+00h]
0x18000c676  test    eax, eax
0x18000c678  jz      loc_18000C711
0x18000c67e  jmp     short loc_18000C6C3
0x18000c680  mov     rcx, [rbp+188h]; this
0x18000c687  lea     r8, aWil; "wil"
0x18000c68e  mov     edx, 0DCh; void *
0x18000c693  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c698  mov     rcx, rbx; hObject
0x18000c69b  mov     edi, eax
0x18000c69d  call    cs:__imp_CloseHandle
0x18000c6a4  nop     dword ptr [rax+rax+00h]
0x18000c6a9  test    eax, eax
0x18000c6ab  jz      short loc_18000C723
0x18000c6ad  jmp     loc_18000C59A
0x18000c6b2  call    cs:__imp_GetLastError
0x18000c6b9  nop     dword ptr [rax+rax+00h]
0x18000c6be  cmp     eax, 2
0x18000c6c1  jnz     short loc_18000C6C7
0x18000c6c3  xor     eax, eax
0x18000c6c5  jmp     short loc_18000C6DF
0x18000c6c7  mov     rcx, [rbp+188h]; this
0x18000c6ce  lea     r8, aWil; "wil"
0x18000c6d5  mov     edx, 0D0h; void *
0x18000c6da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c6df  mov     rcx, [rbp+180h+var_40]
0x18000c6e6  xor     rcx, rsp; StackCookie
0x18000c6e9  call    __security_check_cookie
0x18000c6ee  add     rsp, 258h
0x18000c6f5  pop     r15
0x18000c6f7  pop     r14
0x18000c6f9  pop     rdi
0x18000c6fa  pop     rsi
0x18000c6fb  pop     rbx
0x18000c6fc  pop     rbp
0x18000c6fd  retn
0x18000c6ff  mov     rcx, [rbp+188h]; this
0x18000c706  mov     edx, 0A0Bh; void *
0x18000c70b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c711  mov     rcx, [rbp+188h]; this
0x18000c718  mov     edx, 0A0Bh; void *
0x18000c71d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c723  mov     rcx, [rbp+188h]; this
0x18000c72a  mov     edx, 0A0Bh; void *
0x18000c72f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c735  mov     rcx, [rbp+188h]; this
0x18000c73c  mov     edx, 0A0Bh; void *
0x18000c741  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c747  mov     rcx, [rbp+188h]; this
0x18000c74e  mov     edx, 0A0Bh; void *
0x18000c753  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c759  mov     rcx, [rbp+188h]; this
0x18000c760  mov     edx, 0A0Bh; void *
0x18000c765  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
