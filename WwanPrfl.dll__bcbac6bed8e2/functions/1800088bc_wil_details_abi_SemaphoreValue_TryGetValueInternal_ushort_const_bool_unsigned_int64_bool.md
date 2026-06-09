# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800088bc`
- end: `0x180008b28`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003b08`
- `0x180003eac`

## callees

- `0x180001670`
- `0x1800055b4`
- `0x180007944`
- `0x180007964`
- `0x1800083a8`
- `0x1800088bc`
- `0x18000917c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a7d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008950`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800089c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008950`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800089c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008996`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a6e`

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
0x1800088bc  push    rbp
0x1800088be  push    rbx
0x1800088bf  push    rsi
0x1800088c0  push    rdi
0x1800088c1  push    r14
0x1800088c3  push    r15
0x1800088c5  lea     rbp, [rsp-158h]
0x1800088cd  sub     rsp, 258h
0x1800088d4  mov     rax, cs:__security_cookie
0x1800088db  xor     rax, rsp
0x1800088de  mov     [rbp+180h+var_40], rax
0x1800088e5  xor     r15d, r15d
0x1800088e8  lea     rax, [rsp+280h+Name]
0x1800088ed  mov     [r8], r15
0x1800088f0  mov     r14, r8
0x1800088f3  mov     edx, 104h
0x1800088f8  mov     r9d, 7FFFFFFEh
0x1800088fe  test    r9, r9
0x180008901  jz      short loc_180008922
0x180008903  movzx   r8d, word ptr [rcx]
0x180008907  test    r8w, r8w
0x18000890b  jz      short loc_180008922
0x18000890d  mov     [rax], r8w
0x180008911  add     rcx, 2
0x180008915  add     rax, 2
0x180008919  dec     r9
0x18000891c  sub     rdx, 1; unsigned __int64
0x180008920  jnz     short loc_1800088FE
0x180008922  test    rdx, rdx
0x180008925  lea     rcx, [rax-2]
0x180008929  lea     r8, aP0; "_p0"
0x180008930  cmovnz  rcx, rax
0x180008934  mov     [rcx], r15w
0x180008938  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000893d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008942  mov     esi, 1F0003h
0x180008947  lea     r8, [rsp+280h+Name]; lpName
0x18000894c  mov     ecx, esi; dwDesiredAccess
0x18000894e  xor     edx, edx; bInheritHandle
0x180008950  call    cs:__imp_OpenSemaphoreW
0x180008956  mov     rbx, rax
0x180008959  test    rax, rax
0x18000895c  jz      loc_180008A7D
0x180008962  lea     rdx, [rsp+280h+var_25C]; int *
0x180008967  mov     [rsp+280h+var_25C], r15d
0x18000896c  mov     rcx, rax; hHandle
0x18000896f  mov     [rsp+280h+var_260], r15d; int
0x180008974  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008979  mov     edi, eax
0x18000897b  test    eax, eax
0x18000897d  jns     short loc_1800089AB
0x18000897f  mov     rcx, [rbp+188h]; this
0x180008986  mov     r9d, eax; char *
0x180008989  mov     edx, 0D6h; void *
0x18000898e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008993  mov     rcx, rbx; hObject
0x180008996  call    cs:__imp_CloseHandle
0x18000899c  test    eax, eax
0x18000899e  jz      loc_180008AF2
0x1800089a4  mov     eax, edi
0x1800089a6  jmp     loc_180008A9D
0x1800089ab  lea     r8, asc_180016458; "h"
0x1800089b2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800089b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800089bc  lea     r8, [rsp+280h+Name]; lpName
0x1800089c1  xor     edx, edx; bInheritHandle
0x1800089c3  mov     ecx, esi; dwDesiredAccess
0x1800089c5  call    cs:__imp_OpenSemaphoreW
0x1800089cb  mov     rdi, rax
0x1800089ce  test    rax, rax
0x1800089d1  jz      loc_180008A58
0x1800089d7  lea     rdx, [rsp+280h+var_260]; int *
0x1800089dc  mov     rcx, rax; hHandle
0x1800089df  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800089e4  mov     esi, eax
0x1800089e6  test    eax, eax
0x1800089e8  jns     short loc_180008A24
0x1800089ea  mov     rcx, [rbp+188h]; this
0x1800089f1  mov     r9d, eax; char *
0x1800089f4  mov     edx, 0DEh; void *
0x1800089f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089fe  mov     rcx, rdi; hObject
0x180008a01  call    cs:__imp_CloseHandle
0x180008a07  test    eax, eax
0x180008a09  jz      loc_180008B04
0x180008a0f  mov     rcx, rbx; hObject
0x180008a12  call    cs:__imp_CloseHandle
0x180008a18  test    eax, eax
0x180008a1a  jz      loc_180008B16
0x180008a20  mov     eax, esi
0x180008a22  jmp     short loc_180008A9D
0x180008a24  mov     rcx, rdi; hObject
0x180008a27  call    cs:__imp_CloseHandle
0x180008a2d  test    eax, eax
0x180008a2f  jz      loc_180008ABC
0x180008a35  movsxd  rax, [rsp+280h+var_25C]
0x180008a3a  movsxd  rcx, [rsp+280h+var_260]
0x180008a3f  shl     rcx, 1Fh
0x180008a43  or      rcx, rax
0x180008a46  mov     [r14], rcx
0x180008a49  mov     rcx, rbx; hObject
0x180008a4c  call    cs:__imp_CloseHandle
0x180008a52  test    eax, eax
0x180008a54  jz      short loc_180008ACE
0x180008a56  jmp     short loc_180008A88
0x180008a58  mov     rcx, [rbp+188h]; this
0x180008a5f  mov     edx, 0DCh; void *
0x180008a64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008a69  mov     rcx, rbx; hObject
0x180008a6c  mov     edi, eax
0x180008a6e  call    cs:__imp_CloseHandle
0x180008a74  test    eax, eax
0x180008a76  jz      short loc_180008AE0
0x180008a78  jmp     loc_1800089A4
0x180008a7d  call    cs:__imp_GetLastError
0x180008a83  cmp     eax, 2
0x180008a86  jnz     short loc_180008A8C
0x180008a88  xor     eax, eax
0x180008a8a  jmp     short loc_180008A9D
0x180008a8c  mov     rcx, [rbp+188h]; this
0x180008a93  mov     edx, 0D0h; void *
0x180008a98  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008a9d  mov     rcx, [rbp+180h+var_40]
0x180008aa4  xor     rcx, rsp; StackCookie
0x180008aa7  call    __security_check_cookie
0x180008aac  add     rsp, 258h
0x180008ab3  pop     r15
0x180008ab5  pop     r14
0x180008ab7  pop     rdi
0x180008ab8  pop     rsi
0x180008ab9  pop     rbx
0x180008aba  pop     rbp
0x180008abb  retn
0x180008abc  mov     rcx, [rbp+188h]; this
0x180008ac3  mov     edx, 0A0Bh; void *
0x180008ac8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ace  mov     rcx, [rbp+188h]; this
0x180008ad5  mov     edx, 0A0Bh; void *
0x180008ada  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008ae0  mov     rcx, [rbp+188h]; this
0x180008ae7  mov     edx, 0A0Bh; void *
0x180008aec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008af2  mov     rcx, [rbp+188h]; this
0x180008af9  mov     edx, 0A0Bh; void *
0x180008afe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b04  mov     rcx, [rbp+188h]; this
0x180008b0b  mov     edx, 0A0Bh; void *
0x180008b10  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008b16  mov     rcx, [rbp+188h]; this
0x180008b1d  mov     edx, 0A0Bh; void *
0x180008b22  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
