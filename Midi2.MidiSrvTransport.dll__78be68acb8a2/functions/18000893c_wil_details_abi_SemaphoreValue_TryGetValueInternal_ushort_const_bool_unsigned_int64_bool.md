# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000893c`
- end: `0x180008bcb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004038`

## callees

- `0x180002470`
- `0x180005fa4`
- `0x180007e04`
- `0x180007e24`
- `0x1800087b4`
- `0x18000893c`
- `0x180009014`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800089d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008a4c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800089d0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008a4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008b0a`

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
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  const char *v32; // r9
  int v33; // [rsp+20h] [rbp-E0h] BYREF
  int v34[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v32);
    return 0;
  }
  v34[0] = 0;
  v33 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v34);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v33);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v18);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return LastError;
  }
  v20 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v33);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( !CloseHandle(v19) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    *a3 = v34[0] | (unsigned __int64)((__int64)v33 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v20, v33);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x18000893c  push    rbp
0x18000893e  push    rbx
0x18000893f  push    rsi
0x180008940  push    rdi
0x180008941  push    r14
0x180008943  push    r15
0x180008945  lea     rbp, [rsp-158h]
0x18000894d  sub     rsp, 258h
0x180008954  mov     rax, cs:__security_cookie
0x18000895b  xor     rax, rsp
0x18000895e  mov     [rbp+180h+var_40], rax
0x180008965  xor     r15d, r15d
0x180008968  lea     rax, [rsp+280h+Name]
0x18000896d  mov     [r8], r15
0x180008970  mov     r14, r8
0x180008973  mov     edx, 104h
0x180008978  mov     r9d, 7FFFFFFEh
0x18000897e  test    r9, r9
0x180008981  jz      short loc_1800089A2
0x180008983  movzx   r8d, word ptr [rcx]
0x180008987  test    r8w, r8w
0x18000898b  jz      short loc_1800089A2
0x18000898d  mov     [rax], r8w
0x180008991  add     rcx, 2
0x180008995  add     rax, 2
0x180008999  dec     r9
0x18000899c  sub     rdx, 1; unsigned __int64
0x1800089a0  jnz     short loc_18000897E
0x1800089a2  test    rdx, rdx
0x1800089a5  lea     rcx, [rax-2]
0x1800089a9  lea     r8, aP0; "_p0"
0x1800089b0  cmovnz  rcx, rax
0x1800089b4  mov     [rcx], r15w
0x1800089b8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800089bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800089c2  mov     esi, 1F0003h
0x1800089c7  lea     r8, [rsp+280h+Name]; lpName
0x1800089cc  mov     ecx, esi; dwDesiredAccess
0x1800089ce  xor     edx, edx; bInheritHandle
0x1800089d0  call    cs:__imp_OpenSemaphoreW
0x1800089d6  mov     rbx, rax
0x1800089d9  test    rax, rax
0x1800089dc  jz      loc_180008B19
0x1800089e2  lea     rdx, [rsp+280h+var_25C]; int *
0x1800089e7  mov     [rsp+280h+var_25C], r15d
0x1800089ec  mov     rcx, rax; hHandle
0x1800089ef  mov     [rsp+280h+var_260], r15d; int
0x1800089f4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800089f9  mov     edi, eax
0x1800089fb  test    eax, eax
0x1800089fd  jns     short loc_180008A32
0x1800089ff  mov     rcx, [rbp+188h]; this
0x180008a06  lea     r8, aWil; "wil"
0x180008a0d  mov     r9d, eax; char *
0x180008a10  mov     edx, 0D6h; void *
0x180008a15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a1a  mov     rcx, rbx; hObject
0x180008a1d  call    cs:__imp_CloseHandle
0x180008a23  test    eax, eax
0x180008a25  jz      loc_180008B95
0x180008a2b  mov     eax, edi
0x180008a2d  jmp     loc_180008B40
0x180008a32  lea     r8, asc_180017A90; "h"
0x180008a39  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008a3e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008a43  lea     r8, [rsp+280h+Name]; lpName
0x180008a48  xor     edx, edx; bInheritHandle
0x180008a4a  mov     ecx, esi; dwDesiredAccess
0x180008a4c  call    cs:__imp_OpenSemaphoreW
0x180008a52  mov     rdi, rax
0x180008a55  test    rax, rax
0x180008a58  jz      loc_180008AED
0x180008a5e  lea     rdx, [rsp+280h+var_260]; int *
0x180008a63  mov     rcx, rax; hHandle
0x180008a66  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008a6b  mov     esi, eax
0x180008a6d  test    eax, eax
0x180008a6f  jns     short loc_180008AB5
0x180008a71  mov     rcx, [rbp+188h]; this
0x180008a78  lea     r8, aWil; "wil"
0x180008a7f  mov     r9d, eax; char *
0x180008a82  mov     edx, 0DEh; void *
0x180008a87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a8c  mov     rcx, rdi; hObject
0x180008a8f  call    cs:__imp_CloseHandle
0x180008a95  test    eax, eax
0x180008a97  jz      loc_180008BA7
0x180008a9d  mov     rcx, rbx; hObject
0x180008aa0  call    cs:__imp_CloseHandle
0x180008aa6  test    eax, eax
0x180008aa8  jz      loc_180008BB9
0x180008aae  mov     eax, esi
0x180008ab0  jmp     loc_180008B40
0x180008ab5  mov     rcx, rdi; hObject
0x180008ab8  call    cs:__imp_CloseHandle
0x180008abe  test    eax, eax
0x180008ac0  jz      loc_180008B5F
0x180008ac6  movsxd  rax, [rsp+280h+var_25C]
0x180008acb  movsxd  rcx, [rsp+280h+var_260]
0x180008ad0  shl     rcx, 1Fh
0x180008ad4  or      rcx, rax
0x180008ad7  mov     [r14], rcx
0x180008ada  mov     rcx, rbx; hObject
0x180008add  call    cs:__imp_CloseHandle
0x180008ae3  test    eax, eax
0x180008ae5  jz      loc_180008B71
0x180008aeb  jmp     short loc_180008B24
0x180008aed  mov     rcx, [rbp+188h]; this
0x180008af4  lea     r8, aWil; "wil"
0x180008afb  mov     edx, 0DCh; void *
0x180008b00  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008b05  mov     rcx, rbx; hObject
0x180008b08  mov     edi, eax
0x180008b0a  call    cs:__imp_CloseHandle
0x180008b10  test    eax, eax
0x180008b12  jz      short loc_180008B83
0x180008b14  jmp     loc_180008A2B
0x180008b19  call    cs:__imp_GetLastError
0x180008b1f  cmp     eax, 2
0x180008b22  jnz     short loc_180008B28
0x180008b24  xor     eax, eax
0x180008b26  jmp     short loc_180008B40
0x180008b28  mov     rcx, [rbp+188h]; this
0x180008b2f  lea     r8, aWil; "wil"
0x180008b36  mov     edx, 0D0h; void *
0x180008b3b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008b40  mov     rcx, [rbp+180h+var_40]
0x180008b47  xor     rcx, rsp; StackCookie
0x180008b4a  call    __security_check_cookie
0x180008b4f  add     rsp, 258h
0x180008b56  pop     r15
0x180008b58  pop     r14
0x180008b5a  pop     rdi
0x180008b5b  pop     rsi
0x180008b5c  pop     rbx
0x180008b5d  pop     rbp
0x180008b5e  retn
0x180008b5f  mov     rcx, [rbp+188h]; this
0x180008b66  mov     edx, 0A0Bh; void *
0x180008b6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b71  mov     rcx, [rbp+188h]; this
0x180008b78  mov     edx, 0A0Bh; void *
0x180008b7d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b83  mov     rcx, [rbp+188h]; this
0x180008b8a  mov     edx, 0A0Bh; void *
0x180008b8f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b95  mov     rcx, [rbp+188h]; this
0x180008b9c  mov     edx, 0A0Bh; void *
0x180008ba1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ba7  mov     rcx, [rbp+188h]; this
0x180008bae  mov     edx, 0A0Bh; void *
0x180008bb3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008bb9  mov     rcx, [rbp+188h]; this
0x180008bc0  mov     edx, 0A0Bh; void *
0x180008bc5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
