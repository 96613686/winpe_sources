# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000c10c`
- end: `0x14000c39b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140008448`

## callees

- `0x1400054c0`
- `0x14000951c`
- `0x14000a694`
- `0x14000a6b4`
- `0x14000b01c`
- `0x14000c10c`
- `0x14000c55c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c1a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c21c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c1a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c21c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c2e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c2e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c25f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c270`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c25f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c270`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c288`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c2da`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  const char *v18; // r9
  void *v19; // rdi
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  const char *v23; // r9
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
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
0x14000c10c  push    rbp
0x14000c10e  push    rbx
0x14000c10f  push    rsi
0x14000c110  push    rdi
0x14000c111  push    r14
0x14000c113  push    r15
0x14000c115  lea     rbp, [rsp-158h]
0x14000c11d  sub     rsp, 258h
0x14000c124  mov     rax, cs:__security_cookie
0x14000c12b  xor     rax, rsp
0x14000c12e  mov     [rbp+180h+var_40], rax
0x14000c135  xor     r15d, r15d
0x14000c138  lea     rax, [rsp+280h+Name]
0x14000c13d  mov     [r8], r15
0x14000c140  mov     r14, r8
0x14000c143  mov     edx, 104h
0x14000c148  mov     r9d, 7FFFFFFEh
0x14000c14e  test    r9, r9
0x14000c151  jz      short loc_14000C172
0x14000c153  movzx   r8d, word ptr [rcx]
0x14000c157  test    r8w, r8w
0x14000c15b  jz      short loc_14000C172
0x14000c15d  mov     [rax], r8w
0x14000c161  add     rcx, 2
0x14000c165  add     rax, 2
0x14000c169  dec     r9
0x14000c16c  sub     rdx, 1; unsigned __int64
0x14000c170  jnz     short loc_14000C14E
0x14000c172  test    rdx, rdx
0x14000c175  lea     rcx, [rax-2]
0x14000c179  lea     r8, aP0; "_p0"
0x14000c180  cmovnz  rcx, rax
0x14000c184  mov     [rcx], r15w
0x14000c188  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c18d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c192  mov     esi, 1F0003h
0x14000c197  lea     r8, [rsp+280h+Name]; lpName
0x14000c19c  mov     ecx, esi; dwDesiredAccess
0x14000c19e  xor     edx, edx; bInheritHandle
0x14000c1a0  call    cs:__imp_OpenSemaphoreW
0x14000c1a6  mov     rbx, rax
0x14000c1a9  test    rax, rax
0x14000c1ac  jz      loc_14000C2E9
0x14000c1b2  lea     rdx, [rsp+280h+var_25C]; int *
0x14000c1b7  mov     [rsp+280h+var_25C], r15d
0x14000c1bc  mov     rcx, rax; hHandle
0x14000c1bf  mov     [rsp+280h+var_260], r15d; int
0x14000c1c4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c1c9  mov     edi, eax
0x14000c1cb  test    eax, eax
0x14000c1cd  jns     short loc_14000C202
0x14000c1cf  mov     rcx, [rbp+188h]; this
0x14000c1d6  lea     r8, aWil; "wil"
0x14000c1dd  mov     r9d, eax; char *
0x14000c1e0  mov     edx, 0D6h; void *
0x14000c1e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c1ea  mov     rcx, rbx; hObject
0x14000c1ed  call    cs:__imp_CloseHandle
0x14000c1f3  test    eax, eax
0x14000c1f5  jz      loc_14000C365
0x14000c1fb  mov     eax, edi
0x14000c1fd  jmp     loc_14000C310
0x14000c202  lea     r8, asc_14007ACA8; "h"
0x14000c209  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000c20e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c213  lea     r8, [rsp+280h+Name]; lpName
0x14000c218  xor     edx, edx; bInheritHandle
0x14000c21a  mov     ecx, esi; dwDesiredAccess
0x14000c21c  call    cs:__imp_OpenSemaphoreW
0x14000c222  mov     rdi, rax
0x14000c225  test    rax, rax
0x14000c228  jz      loc_14000C2BD
0x14000c22e  lea     rdx, [rsp+280h+var_260]; int *
0x14000c233  mov     rcx, rax; hHandle
0x14000c236  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c23b  mov     esi, eax
0x14000c23d  test    eax, eax
0x14000c23f  jns     short loc_14000C285
0x14000c241  mov     rcx, [rbp+188h]; this
0x14000c248  lea     r8, aWil; "wil"
0x14000c24f  mov     r9d, eax; char *
0x14000c252  mov     edx, 0DEh; void *
0x14000c257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c25c  mov     rcx, rdi; hObject
0x14000c25f  call    cs:__imp_CloseHandle
0x14000c265  test    eax, eax
0x14000c267  jz      loc_14000C377
0x14000c26d  mov     rcx, rbx; hObject
0x14000c270  call    cs:__imp_CloseHandle
0x14000c276  test    eax, eax
0x14000c278  jz      loc_14000C389
0x14000c27e  mov     eax, esi
0x14000c280  jmp     loc_14000C310
0x14000c285  mov     rcx, rdi; hObject
0x14000c288  call    cs:__imp_CloseHandle
0x14000c28e  test    eax, eax
0x14000c290  jz      loc_14000C32F
0x14000c296  movsxd  rax, [rsp+280h+var_25C]
0x14000c29b  movsxd  rcx, [rsp+280h+var_260]
0x14000c2a0  shl     rcx, 1Fh
0x14000c2a4  or      rcx, rax
0x14000c2a7  mov     [r14], rcx
0x14000c2aa  mov     rcx, rbx; hObject
0x14000c2ad  call    cs:__imp_CloseHandle
0x14000c2b3  test    eax, eax
0x14000c2b5  jz      loc_14000C341
0x14000c2bb  jmp     short loc_14000C2F4
0x14000c2bd  mov     rcx, [rbp+188h]; this
0x14000c2c4  lea     r8, aWil; "wil"
0x14000c2cb  mov     edx, 0DCh; void *
0x14000c2d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c2d5  mov     rcx, rbx; hObject
0x14000c2d8  mov     edi, eax
0x14000c2da  call    cs:__imp_CloseHandle
0x14000c2e0  test    eax, eax
0x14000c2e2  jz      short loc_14000C353
0x14000c2e4  jmp     loc_14000C1FB
0x14000c2e9  call    cs:__imp_GetLastError
0x14000c2ef  cmp     eax, 2
0x14000c2f2  jnz     short loc_14000C2F8
0x14000c2f4  xor     eax, eax
0x14000c2f6  jmp     short loc_14000C310
0x14000c2f8  mov     rcx, [rbp+188h]; this
0x14000c2ff  lea     r8, aWil; "wil"
0x14000c306  mov     edx, 0D0h; void *
0x14000c30b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c310  mov     rcx, [rbp+180h+var_40]
0x14000c317  xor     rcx, rsp; StackCookie
0x14000c31a  call    __security_check_cookie
0x14000c31f  add     rsp, 258h
0x14000c326  pop     r15
0x14000c328  pop     r14
0x14000c32a  pop     rdi
0x14000c32b  pop     rsi
0x14000c32c  pop     rbx
0x14000c32d  pop     rbp
0x14000c32e  retn
0x14000c32f  mov     rcx, [rbp+188h]; this
0x14000c336  mov     edx, 0A0Bh; void *
0x14000c33b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c341  mov     rcx, [rbp+188h]; this
0x14000c348  mov     edx, 0A0Bh; void *
0x14000c34d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c353  mov     rcx, [rbp+188h]; this
0x14000c35a  mov     edx, 0A0Bh; void *
0x14000c35f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c365  mov     rcx, [rbp+188h]; this
0x14000c36c  mov     edx, 0A0Bh; void *
0x14000c371  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c377  mov     rcx, [rbp+188h]; this
0x14000c37e  mov     edx, 0A0Bh; void *
0x14000c383  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000c389  mov     rcx, [rbp+188h]; this
0x14000c390  mov     edx, 0A0Bh; void *
0x14000c395  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
