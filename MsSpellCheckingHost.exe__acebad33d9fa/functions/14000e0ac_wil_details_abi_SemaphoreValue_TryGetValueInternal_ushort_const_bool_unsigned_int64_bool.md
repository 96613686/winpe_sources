# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000e0ac`
- end: `0x14000e318`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140009088`
- `0x14000942c`

## callees

- `0x14000ab30`
- `0x14000d284`
- `0x14000d2a4`
- `0x14000dbd0`
- `0x14000e0ac`
- `0x14000ece4`
- `0x140011e10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e26d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e26d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e23c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e25e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e186`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e1f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e202`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e217`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e23c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000e25e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000e140`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000e1b5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000e140`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000e1b5`

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
0x14000e0ac  push    rbp
0x14000e0ae  push    rbx
0x14000e0af  push    rsi
0x14000e0b0  push    rdi
0x14000e0b1  push    r14
0x14000e0b3  push    r15
0x14000e0b5  lea     rbp, [rsp-158h]
0x14000e0bd  sub     rsp, 258h
0x14000e0c4  mov     rax, cs:__security_cookie
0x14000e0cb  xor     rax, rsp
0x14000e0ce  mov     [rbp+180h+var_40], rax
0x14000e0d5  xor     r15d, r15d
0x14000e0d8  lea     rax, [rsp+280h+Name]
0x14000e0dd  mov     [r8], r15
0x14000e0e0  mov     r14, r8
0x14000e0e3  mov     edx, 104h
0x14000e0e8  mov     r9d, 7FFFFFFEh
0x14000e0ee  test    r9, r9
0x14000e0f1  jz      short loc_14000E112
0x14000e0f3  movzx   r8d, word ptr [rcx]
0x14000e0f7  test    r8w, r8w
0x14000e0fb  jz      short loc_14000E112
0x14000e0fd  mov     [rax], r8w
0x14000e101  add     rcx, 2
0x14000e105  add     rax, 2
0x14000e109  dec     r9
0x14000e10c  sub     rdx, 1; unsigned __int64
0x14000e110  jnz     short loc_14000E0EE
0x14000e112  test    rdx, rdx
0x14000e115  lea     rcx, [rax-2]
0x14000e119  lea     r8, aP0; "_p0"
0x14000e120  cmovnz  rcx, rax
0x14000e124  mov     [rcx], r15w
0x14000e128  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000e12d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000e132  mov     esi, 1F0003h
0x14000e137  lea     r8, [rsp+280h+Name]; lpName
0x14000e13c  mov     ecx, esi; dwDesiredAccess
0x14000e13e  xor     edx, edx; bInheritHandle
0x14000e140  call    cs:__imp_OpenSemaphoreW
0x14000e146  mov     rbx, rax
0x14000e149  test    rax, rax
0x14000e14c  jz      loc_14000E26D
0x14000e152  lea     rdx, [rsp+280h+var_25C]; int *
0x14000e157  mov     [rsp+280h+var_25C], r15d
0x14000e15c  mov     rcx, rax; hHandle
0x14000e15f  mov     [rsp+280h+var_260], r15d; int
0x14000e164  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000e169  mov     edi, eax
0x14000e16b  test    eax, eax
0x14000e16d  jns     short loc_14000E19B
0x14000e16f  mov     rcx, [rbp+188h]; this
0x14000e176  mov     r9d, eax; char *
0x14000e179  mov     edx, 0D6h; void *
0x14000e17e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e183  mov     rcx, rbx; hObject
0x14000e186  call    cs:__imp_CloseHandle
0x14000e18c  test    eax, eax
0x14000e18e  jz      loc_14000E2E2
0x14000e194  mov     eax, edi
0x14000e196  jmp     loc_14000E28D
0x14000e19b  lea     r8, asc_140016FF0; "h"
0x14000e1a2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000e1a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000e1ac  lea     r8, [rsp+280h+Name]; lpName
0x14000e1b1  xor     edx, edx; bInheritHandle
0x14000e1b3  mov     ecx, esi; dwDesiredAccess
0x14000e1b5  call    cs:__imp_OpenSemaphoreW
0x14000e1bb  mov     rdi, rax
0x14000e1be  test    rax, rax
0x14000e1c1  jz      loc_14000E248
0x14000e1c7  lea     rdx, [rsp+280h+var_260]; int *
0x14000e1cc  mov     rcx, rax; hHandle
0x14000e1cf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000e1d4  mov     esi, eax
0x14000e1d6  test    eax, eax
0x14000e1d8  jns     short loc_14000E214
0x14000e1da  mov     rcx, [rbp+188h]; this
0x14000e1e1  mov     r9d, eax; char *
0x14000e1e4  mov     edx, 0DEh; void *
0x14000e1e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e1ee  mov     rcx, rdi; hObject
0x14000e1f1  call    cs:__imp_CloseHandle
0x14000e1f7  test    eax, eax
0x14000e1f9  jz      loc_14000E2F4
0x14000e1ff  mov     rcx, rbx; hObject
0x14000e202  call    cs:__imp_CloseHandle
0x14000e208  test    eax, eax
0x14000e20a  jz      loc_14000E306
0x14000e210  mov     eax, esi
0x14000e212  jmp     short loc_14000E28D
0x14000e214  mov     rcx, rdi; hObject
0x14000e217  call    cs:__imp_CloseHandle
0x14000e21d  test    eax, eax
0x14000e21f  jz      loc_14000E2AC
0x14000e225  movsxd  rax, [rsp+280h+var_25C]
0x14000e22a  movsxd  rcx, [rsp+280h+var_260]
0x14000e22f  shl     rcx, 1Fh
0x14000e233  or      rcx, rax
0x14000e236  mov     [r14], rcx
0x14000e239  mov     rcx, rbx; hObject
0x14000e23c  call    cs:__imp_CloseHandle
0x14000e242  test    eax, eax
0x14000e244  jz      short loc_14000E2BE
0x14000e246  jmp     short loc_14000E278
0x14000e248  mov     rcx, [rbp+188h]; this
0x14000e24f  mov     edx, 0DCh; void *
0x14000e254  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e259  mov     rcx, rbx; hObject
0x14000e25c  mov     edi, eax
0x14000e25e  call    cs:__imp_CloseHandle
0x14000e264  test    eax, eax
0x14000e266  jz      short loc_14000E2D0
0x14000e268  jmp     loc_14000E194
0x14000e26d  call    cs:__imp_GetLastError
0x14000e273  cmp     eax, 2
0x14000e276  jnz     short loc_14000E27C
0x14000e278  xor     eax, eax
0x14000e27a  jmp     short loc_14000E28D
0x14000e27c  mov     rcx, [rbp+188h]; this
0x14000e283  mov     edx, 0D0h; void *
0x14000e288  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e28d  mov     rcx, [rbp+180h+var_40]
0x14000e294  xor     rcx, rsp; StackCookie
0x14000e297  call    __security_check_cookie
0x14000e29c  add     rsp, 258h
0x14000e2a3  pop     r15
0x14000e2a5  pop     r14
0x14000e2a7  pop     rdi
0x14000e2a8  pop     rsi
0x14000e2a9  pop     rbx
0x14000e2aa  pop     rbp
0x14000e2ab  retn
0x14000e2ac  mov     rcx, [rbp+188h]; this
0x14000e2b3  mov     edx, 0A0Bh; void *
0x14000e2b8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e2be  mov     rcx, [rbp+188h]; this
0x14000e2c5  mov     edx, 0A0Bh; void *
0x14000e2ca  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e2d0  mov     rcx, [rbp+188h]; this
0x14000e2d7  mov     edx, 0A0Bh; void *
0x14000e2dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e2e2  mov     rcx, [rbp+188h]; this
0x14000e2e9  mov     edx, 0A0Bh; void *
0x14000e2ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e2f4  mov     rcx, [rbp+188h]; this
0x14000e2fb  mov     edx, 0A0Bh; void *
0x14000e300  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000e306  mov     rcx, [rbp+188h]; this
0x14000e30d  mov     edx, 0A0Bh; void *
0x14000e312  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
