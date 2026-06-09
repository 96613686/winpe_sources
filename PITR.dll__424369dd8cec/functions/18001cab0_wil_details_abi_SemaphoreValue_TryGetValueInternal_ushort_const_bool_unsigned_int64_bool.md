# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001cab0`
- end: `0x18001cd25`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180007610`
- `0x1800079b4`

## callees

- `0x1800107a0`
- `0x18001b1f4`
- `0x18001b214`
- `0x18001c484`
- `0x18001cab0`
- `0x18001dd74`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cb47`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cbc2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cb47`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001cbc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cbfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc6b`

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
  __int64 v14; // r8
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
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
0x18001cab0  push    rbp
0x18001cab2  push    rbx
0x18001cab3  push    rsi
0x18001cab4  push    rdi
0x18001cab5  push    r14
0x18001cab7  push    r15
0x18001cab9  lea     rbp, [rsp-158h]
0x18001cac1  sub     rsp, 258h
0x18001cac8  mov     rax, cs:__security_cookie
0x18001cacf  xor     rax, rsp
0x18001cad2  mov     [rbp+180h+var_40], rax
0x18001cad9  xor     r15d, r15d
0x18001cadc  lea     rax, [rsp+280h+Name]
0x18001cae1  mov     esi, 104h
0x18001cae6  mov     [r8], r15
0x18001cae9  mov     edx, esi
0x18001caeb  mov     r14, r8
0x18001caee  mov     r9d, 7FFFFFFEh
0x18001caf4  test    r9, r9
0x18001caf7  jz      short loc_18001CB18
0x18001caf9  movzx   r8d, word ptr [rcx]
0x18001cafd  test    r8w, r8w
0x18001cb01  jz      short loc_18001CB18
0x18001cb03  mov     [rax], r8w
0x18001cb07  add     rcx, 2
0x18001cb0b  add     rax, 2
0x18001cb0f  dec     r9
0x18001cb12  sub     rdx, 1
0x18001cb16  jnz     short loc_18001CAF4
0x18001cb18  test    rdx, rdx
0x18001cb1b  lea     rcx, [rax-2]
0x18001cb1f  lea     r8, aP0; "_p0"
0x18001cb26  mov     rdx, rsi; unsigned __int64
0x18001cb29  cmovnz  rcx, rax
0x18001cb2d  mov     [rcx], r15w
0x18001cb31  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001cb36  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cb3b  lea     r8, [rsp+280h+Name]; lpName
0x18001cb40  xor     edx, edx; bInheritHandle
0x18001cb42  mov     ecx, 1F0003h; dwDesiredAccess
0x18001cb47  call    cs:__imp_OpenSemaphoreW
0x18001cb4d  mov     rbx, rax
0x18001cb50  test    rax, rax
0x18001cb53  jz      loc_18001CC7A
0x18001cb59  lea     rdx, [rsp+280h+var_25C]; int *
0x18001cb5e  mov     [rsp+280h+var_25C], r15d
0x18001cb63  mov     rcx, rax; hHandle
0x18001cb66  mov     [rsp+280h+var_260], r15d; int
0x18001cb6b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001cb70  mov     edi, eax
0x18001cb72  test    eax, eax
0x18001cb74  jns     short loc_18001CBA2
0x18001cb76  mov     rcx, [rbp+188h]; this
0x18001cb7d  mov     r9d, eax; char *
0x18001cb80  mov     edx, 0D6h; void *
0x18001cb85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cb8a  mov     rcx, rbx; hObject
0x18001cb8d  call    cs:__imp_CloseHandle
0x18001cb93  test    eax, eax
0x18001cb95  jz      loc_18001CCEF
0x18001cb9b  mov     eax, edi
0x18001cb9d  jmp     loc_18001CC9A
0x18001cba2  lea     r8, asc_1800596E8; "h"
0x18001cba9  mov     rdx, rsi; unsigned __int64
0x18001cbac  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001cbb1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cbb6  lea     r8, [rsp+280h+Name]; lpName
0x18001cbbb  xor     edx, edx; bInheritHandle
0x18001cbbd  mov     ecx, 1F0003h; dwDesiredAccess
0x18001cbc2  call    cs:__imp_OpenSemaphoreW
0x18001cbc8  mov     rdi, rax
0x18001cbcb  test    rax, rax
0x18001cbce  jz      loc_18001CC55
0x18001cbd4  lea     rdx, [rsp+280h+var_260]; int *
0x18001cbd9  mov     rcx, rax; hHandle
0x18001cbdc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001cbe1  mov     esi, eax
0x18001cbe3  test    eax, eax
0x18001cbe5  jns     short loc_18001CC21
0x18001cbe7  mov     rcx, [rbp+188h]; this
0x18001cbee  mov     r9d, eax; char *
0x18001cbf1  mov     edx, 0DEh; void *
0x18001cbf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbfb  mov     rcx, rdi; hObject
0x18001cbfe  call    cs:__imp_CloseHandle
0x18001cc04  test    eax, eax
0x18001cc06  jz      loc_18001CD01
0x18001cc0c  mov     rcx, rbx; hObject
0x18001cc0f  call    cs:__imp_CloseHandle
0x18001cc15  test    eax, eax
0x18001cc17  jz      loc_18001CD13
0x18001cc1d  mov     eax, esi
0x18001cc1f  jmp     short loc_18001CC9A
0x18001cc21  mov     rcx, rdi; hObject
0x18001cc24  call    cs:__imp_CloseHandle
0x18001cc2a  test    eax, eax
0x18001cc2c  jz      loc_18001CCB9
0x18001cc32  movsxd  rax, [rsp+280h+var_25C]
0x18001cc37  movsxd  rcx, [rsp+280h+var_260]
0x18001cc3c  shl     rcx, 1Fh
0x18001cc40  or      rcx, rax
0x18001cc43  mov     [r14], rcx
0x18001cc46  mov     rcx, rbx; hObject
0x18001cc49  call    cs:__imp_CloseHandle
0x18001cc4f  test    eax, eax
0x18001cc51  jz      short loc_18001CCCB
0x18001cc53  jmp     short loc_18001CC85
0x18001cc55  mov     rcx, [rbp+188h]; this
0x18001cc5c  mov     edx, 0DCh; void *
0x18001cc61  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cc66  mov     rcx, rbx; hObject
0x18001cc69  mov     edi, eax
0x18001cc6b  call    cs:__imp_CloseHandle
0x18001cc71  test    eax, eax
0x18001cc73  jz      short loc_18001CCDD
0x18001cc75  jmp     loc_18001CB9B
0x18001cc7a  call    cs:__imp_GetLastError
0x18001cc80  cmp     eax, 2
0x18001cc83  jnz     short loc_18001CC89
0x18001cc85  xor     eax, eax
0x18001cc87  jmp     short loc_18001CC9A
0x18001cc89  mov     rcx, [rbp+188h]; this
0x18001cc90  mov     edx, 0D0h; void *
0x18001cc95  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001cc9a  mov     rcx, [rbp+180h+var_40]
0x18001cca1  xor     rcx, rsp; StackCookie
0x18001cca4  call    __security_check_cookie
0x18001cca9  add     rsp, 258h
0x18001ccb0  pop     r15
0x18001ccb2  pop     r14
0x18001ccb4  pop     rdi
0x18001ccb5  pop     rsi
0x18001ccb6  pop     rbx
0x18001ccb7  pop     rbp
0x18001ccb8  retn
0x18001ccb9  mov     rcx, [rbp+188h]; this
0x18001ccc0  mov     edx, 0A0Bh; void *
0x18001ccc5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cccb  mov     rcx, [rbp+188h]; this
0x18001ccd2  mov     edx, 0A0Bh; void *
0x18001ccd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ccdd  mov     rcx, [rbp+188h]; this
0x18001cce4  mov     edx, 0A0Bh; void *
0x18001cce9  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001ccef  mov     rcx, [rbp+188h]; this
0x18001ccf6  mov     edx, 0A0Bh; void *
0x18001ccfb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cd01  mov     rcx, [rbp+188h]; this
0x18001cd08  mov     edx, 0A0Bh; void *
0x18001cd0d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001cd13  mov     rcx, [rbp+188h]; this
0x18001cd1a  mov     edx, 0A0Bh; void *
0x18001cd1f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
