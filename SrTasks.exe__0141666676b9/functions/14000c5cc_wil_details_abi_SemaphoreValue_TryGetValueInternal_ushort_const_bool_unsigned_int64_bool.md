# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000c5cc`
- end: `0x14000c838`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008c5c`
- `0x140009000`

## callees

- `0x140005d74`
- `0x14000a480`
- `0x14000bf10`
- `0x14000bf30`
- `0x14000c5cc`
- `0x14000cdbc`
- `0x140010980`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x14000c660`
- `KERNEL32!OpenSemaphoreW` at `0x14000c6d5`
- `KERNEL32!OpenSemaphoreW` at `0x14000c660`
- `KERNEL32!OpenSemaphoreW` at `0x14000c6d5`
- `KERNEL32!GetLastError` at `0x14000c78d`
- `KERNEL32!GetLastError` at `0x14000c78d`
- `KERNEL32!CloseHandle` at `0x14000c6a6`
- `KERNEL32!CloseHandle` at `0x14000c711`
- `KERNEL32!CloseHandle` at `0x14000c722`
- `KERNEL32!CloseHandle` at `0x14000c737`
- `KERNEL32!CloseHandle` at `0x14000c75c`
- `KERNEL32!CloseHandle` at `0x14000c77e`
- `KERNEL32!CloseHandle` at `0x14000c6a6`
- `KERNEL32!CloseHandle` at `0x14000c711`
- `KERNEL32!CloseHandle` at `0x14000c722`
- `KERNEL32!CloseHandle` at `0x14000c737`
- `KERNEL32!CloseHandle` at `0x14000c75c`
- `KERNEL32!CloseHandle` at `0x14000c77e`

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
0x14000c5cc  push    rbp
0x14000c5ce  push    rbx
0x14000c5cf  push    rsi
0x14000c5d0  push    rdi
0x14000c5d1  push    r14
0x14000c5d3  push    r15
0x14000c5d5  lea     rbp, [rsp-158h]
0x14000c5dd  sub     rsp, 258h
0x14000c5e4  mov     rax, cs:__security_cookie
0x14000c5eb  xor     rax, rsp
0x14000c5ee  mov     [rbp+180h+var_40], rax
0x14000c5f5  xor     r15d, r15d
0x14000c5f8  lea     rax, [rsp+280h+Name]
0x14000c5fd  mov     [r8], r15
0x14000c600  mov     r14, r8
0x14000c603  mov     edx, 104h
0x14000c608  mov     r9d, 7FFFFFFEh
0x14000c60e  test    r9, r9
0x14000c611  jz      short loc_14000C632
0x14000c613  movzx   r8d, word ptr [rcx]
0x14000c617  test    r8w, r8w
0x14000c61b  jz      short loc_14000C632
0x14000c61d  mov     [rax], r8w
0x14000c621  add     rcx, 2
0x14000c625  add     rax, 2
0x14000c629  dec     r9
0x14000c62c  sub     rdx, 1; unsigned __int64
0x14000c630  jnz     short loc_14000C60E
0x14000c632  test    rdx, rdx
0x14000c635  lea     rcx, [rax-2]
0x14000c639  lea     r8, aP0; "_p0"
0x14000c640  cmovnz  rcx, rax
0x14000c644  mov     [rcx], r15w
0x14000c648  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c64d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c652  mov     esi, 1F0003h
0x14000c657  lea     r8, [rsp+280h+Name]; lpName
0x14000c65c  mov     ecx, esi; dwDesiredAccess
0x14000c65e  xor     edx, edx; bInheritHandle
0x14000c660  call    cs:__imp_OpenSemaphoreW
0x14000c666  mov     rbx, rax
0x14000c669  test    rax, rax
0x14000c66c  jz      loc_14000C78D
0x14000c672  lea     rdx, [rsp+280h+var_25C]; int *
0x14000c677  mov     [rsp+280h+var_25C], r15d
0x14000c67c  mov     rcx, rax; hHandle
0x14000c67f  mov     [rsp+280h+var_260], r15d; int
0x14000c684  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c689  mov     edi, eax
0x14000c68b  test    eax, eax
0x14000c68d  jns     short loc_14000C6BB
0x14000c68f  mov     rcx, [rbp+188h]; this
0x14000c696  mov     r9d, eax; char *
0x14000c699  mov     edx, 0D6h; void *
0x14000c69e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c6a3  mov     rcx, rbx; hObject
0x14000c6a6  call    cs:__imp_CloseHandle
0x14000c6ac  test    eax, eax
0x14000c6ae  jz      loc_14000C802
0x14000c6b4  mov     eax, edi
0x14000c6b6  jmp     loc_14000C7AD
0x14000c6bb  lea     r8, asc_140013628; "h"
0x14000c6c2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c6c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c6cc  lea     r8, [rsp+280h+Name]; lpName
0x14000c6d1  xor     edx, edx; bInheritHandle
0x14000c6d3  mov     ecx, esi; dwDesiredAccess
0x14000c6d5  call    cs:__imp_OpenSemaphoreW
0x14000c6db  mov     rdi, rax
0x14000c6de  test    rax, rax
0x14000c6e1  jz      loc_14000C768
0x14000c6e7  lea     rdx, [rsp+280h+var_260]; int *
0x14000c6ec  mov     rcx, rax; hHandle
0x14000c6ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c6f4  mov     esi, eax
0x14000c6f6  test    eax, eax
0x14000c6f8  jns     short loc_14000C734
0x14000c6fa  mov     rcx, [rbp+188h]; this
0x14000c701  mov     r9d, eax; char *
0x14000c704  mov     edx, 0DEh; void *
0x14000c709  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c70e  mov     rcx, rdi; hObject
0x14000c711  call    cs:__imp_CloseHandle
0x14000c717  test    eax, eax
0x14000c719  jz      loc_14000C814
0x14000c71f  mov     rcx, rbx; hObject
0x14000c722  call    cs:__imp_CloseHandle
0x14000c728  test    eax, eax
0x14000c72a  jz      loc_14000C826
0x14000c730  mov     eax, esi
0x14000c732  jmp     short loc_14000C7AD
0x14000c734  mov     rcx, rdi; hObject
0x14000c737  call    cs:__imp_CloseHandle
0x14000c73d  test    eax, eax
0x14000c73f  jz      loc_14000C7CC
0x14000c745  movsxd  rax, [rsp+280h+var_25C]
0x14000c74a  movsxd  rcx, [rsp+280h+var_260]
0x14000c74f  shl     rcx, 1Fh
0x14000c753  or      rcx, rax
0x14000c756  mov     [r14], rcx
0x14000c759  mov     rcx, rbx; hObject
0x14000c75c  call    cs:__imp_CloseHandle
0x14000c762  test    eax, eax
0x14000c764  jz      short loc_14000C7DE
0x14000c766  jmp     short loc_14000C798
0x14000c768  mov     rcx, [rbp+188h]; this
0x14000c76f  mov     edx, 0DCh; void *
0x14000c774  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c779  mov     rcx, rbx; hObject
0x14000c77c  mov     edi, eax
0x14000c77e  call    cs:__imp_CloseHandle
0x14000c784  test    eax, eax
0x14000c786  jz      short loc_14000C7F0
0x14000c788  jmp     loc_14000C6B4
0x14000c78d  call    cs:__imp_GetLastError
0x14000c793  cmp     eax, 2
0x14000c796  jnz     short loc_14000C79C
0x14000c798  xor     eax, eax
0x14000c79a  jmp     short loc_14000C7AD
0x14000c79c  mov     rcx, [rbp+188h]; this
0x14000c7a3  mov     edx, 0D0h; void *
0x14000c7a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c7ad  mov     rcx, [rbp+180h+var_40]
0x14000c7b4  xor     rcx, rsp; StackCookie
0x14000c7b7  call    __security_check_cookie
0x14000c7bc  add     rsp, 258h
0x14000c7c3  pop     r15
0x14000c7c5  pop     r14
0x14000c7c7  pop     rdi
0x14000c7c8  pop     rsi
0x14000c7c9  pop     rbx
0x14000c7ca  pop     rbp
0x14000c7cb  retn
0x14000c7cc  mov     rcx, [rbp+188h]; this
0x14000c7d3  mov     edx, 0A0Bh; void *
0x14000c7d8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c7de  mov     rcx, [rbp+188h]; this
0x14000c7e5  mov     edx, 0A0Bh; void *
0x14000c7ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c7f0  mov     rcx, [rbp+188h]; this
0x14000c7f7  mov     edx, 0A0Bh; void *
0x14000c7fc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c802  mov     rcx, [rbp+188h]; this
0x14000c809  mov     edx, 0A0Bh; void *
0x14000c80e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c814  mov     rcx, [rbp+188h]; this
0x14000c81b  mov     edx, 0A0Bh; void *
0x14000c820  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c826  mov     rcx, [rbp+188h]; this
0x14000c82d  mov     edx, 0A0Bh; void *
0x14000c832  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
