# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a44c`
- end: `0x18000a6db`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180006128`
- `0x180023de4`

## callees

- `0x1800021c0`
- `0x180007d54`
- `0x180009524`
- `0x180009544`
- `0x18000a2b8`
- `0x18000a44c`
- `0x18000a948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a4e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a55c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a4e0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a52d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a59f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a61a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a52d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a59f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a5ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a61a`

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
0x18000a44c  push    rbp
0x18000a44e  push    rbx
0x18000a44f  push    rsi
0x18000a450  push    rdi
0x18000a451  push    r14
0x18000a453  push    r15
0x18000a455  lea     rbp, [rsp-158h]
0x18000a45d  sub     rsp, 258h
0x18000a464  mov     rax, cs:__security_cookie
0x18000a46b  xor     rax, rsp
0x18000a46e  mov     [rbp+180h+var_40], rax
0x18000a475  xor     r15d, r15d
0x18000a478  lea     rax, [rsp+280h+Name]
0x18000a47d  mov     [r8], r15
0x18000a480  mov     r14, r8
0x18000a483  mov     edx, 104h
0x18000a488  mov     r9d, 7FFFFFFEh
0x18000a48e  test    r9, r9
0x18000a491  jz      short loc_18000A4B2
0x18000a493  movzx   r8d, word ptr [rcx]
0x18000a497  test    r8w, r8w
0x18000a49b  jz      short loc_18000A4B2
0x18000a49d  mov     [rax], r8w
0x18000a4a1  add     rcx, 2
0x18000a4a5  add     rax, 2
0x18000a4a9  dec     r9
0x18000a4ac  sub     rdx, 1; unsigned __int64
0x18000a4b0  jnz     short loc_18000A48E
0x18000a4b2  test    rdx, rdx
0x18000a4b5  lea     rcx, [rax-2]
0x18000a4b9  lea     r8, aP0; "_p0"
0x18000a4c0  cmovnz  rcx, rax
0x18000a4c4  mov     [rcx], r15w
0x18000a4c8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a4cd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a4d2  mov     esi, 1F0003h
0x18000a4d7  lea     r8, [rsp+280h+Name]; lpName
0x18000a4dc  mov     ecx, esi; dwDesiredAccess
0x18000a4de  xor     edx, edx; bInheritHandle
0x18000a4e0  call    cs:__imp_OpenSemaphoreW
0x18000a4e6  mov     rbx, rax
0x18000a4e9  test    rax, rax
0x18000a4ec  jz      loc_18000A629
0x18000a4f2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a4f7  mov     [rsp+280h+var_25C], r15d
0x18000a4fc  mov     rcx, rax; hHandle
0x18000a4ff  mov     [rsp+280h+var_260], r15d; int
0x18000a504  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a509  mov     edi, eax
0x18000a50b  test    eax, eax
0x18000a50d  jns     short loc_18000A542
0x18000a50f  mov     rcx, [rbp+188h]; this
0x18000a516  lea     r8, aWil; "wil"
0x18000a51d  mov     r9d, eax; char *
0x18000a520  mov     edx, 0D6h; void *
0x18000a525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a52a  mov     rcx, rbx; hObject
0x18000a52d  call    cs:__imp_CloseHandle
0x18000a533  test    eax, eax
0x18000a535  jz      loc_18000A6A5
0x18000a53b  mov     eax, edi
0x18000a53d  jmp     loc_18000A650
0x18000a542  lea     r8, asc_1800300B0; "h"
0x18000a549  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a54e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a553  lea     r8, [rsp+280h+Name]; lpName
0x18000a558  xor     edx, edx; bInheritHandle
0x18000a55a  mov     ecx, esi; dwDesiredAccess
0x18000a55c  call    cs:__imp_OpenSemaphoreW
0x18000a562  mov     rdi, rax
0x18000a565  test    rax, rax
0x18000a568  jz      loc_18000A5FD
0x18000a56e  lea     rdx, [rsp+280h+var_260]; int *
0x18000a573  mov     rcx, rax; hHandle
0x18000a576  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a57b  mov     esi, eax
0x18000a57d  test    eax, eax
0x18000a57f  jns     short loc_18000A5C5
0x18000a581  mov     rcx, [rbp+188h]; this
0x18000a588  lea     r8, aWil; "wil"
0x18000a58f  mov     r9d, eax; char *
0x18000a592  mov     edx, 0DEh; void *
0x18000a597  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a59c  mov     rcx, rdi; hObject
0x18000a59f  call    cs:__imp_CloseHandle
0x18000a5a5  test    eax, eax
0x18000a5a7  jz      loc_18000A6B7
0x18000a5ad  mov     rcx, rbx; hObject
0x18000a5b0  call    cs:__imp_CloseHandle
0x18000a5b6  test    eax, eax
0x18000a5b8  jz      loc_18000A6C9
0x18000a5be  mov     eax, esi
0x18000a5c0  jmp     loc_18000A650
0x18000a5c5  mov     rcx, rdi; hObject
0x18000a5c8  call    cs:__imp_CloseHandle
0x18000a5ce  test    eax, eax
0x18000a5d0  jz      loc_18000A66F
0x18000a5d6  movsxd  rax, [rsp+280h+var_25C]
0x18000a5db  movsxd  rcx, [rsp+280h+var_260]
0x18000a5e0  shl     rcx, 1Fh
0x18000a5e4  or      rcx, rax
0x18000a5e7  mov     [r14], rcx
0x18000a5ea  mov     rcx, rbx; hObject
0x18000a5ed  call    cs:__imp_CloseHandle
0x18000a5f3  test    eax, eax
0x18000a5f5  jz      loc_18000A681
0x18000a5fb  jmp     short loc_18000A634
0x18000a5fd  mov     rcx, [rbp+188h]; this
0x18000a604  lea     r8, aWil; "wil"
0x18000a60b  mov     edx, 0DCh; void *
0x18000a610  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a615  mov     rcx, rbx; hObject
0x18000a618  mov     edi, eax
0x18000a61a  call    cs:__imp_CloseHandle
0x18000a620  test    eax, eax
0x18000a622  jz      short loc_18000A693
0x18000a624  jmp     loc_18000A53B
0x18000a629  call    cs:__imp_GetLastError
0x18000a62f  cmp     eax, 2
0x18000a632  jnz     short loc_18000A638
0x18000a634  xor     eax, eax
0x18000a636  jmp     short loc_18000A650
0x18000a638  mov     rcx, [rbp+188h]; this
0x18000a63f  lea     r8, aWil; "wil"
0x18000a646  mov     edx, 0D0h; void *
0x18000a64b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a650  mov     rcx, [rbp+180h+var_40]
0x18000a657  xor     rcx, rsp; StackCookie
0x18000a65a  call    __security_check_cookie
0x18000a65f  add     rsp, 258h
0x18000a666  pop     r15
0x18000a668  pop     r14
0x18000a66a  pop     rdi
0x18000a66b  pop     rsi
0x18000a66c  pop     rbx
0x18000a66d  pop     rbp
0x18000a66e  retn
0x18000a66f  mov     rcx, [rbp+188h]; this
0x18000a676  mov     edx, 0A0Bh; void *
0x18000a67b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a681  mov     rcx, [rbp+188h]; this
0x18000a688  mov     edx, 0A0Bh; void *
0x18000a68d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a693  mov     rcx, [rbp+188h]; this
0x18000a69a  mov     edx, 0A0Bh; void *
0x18000a69f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6a5  mov     rcx, [rbp+188h]; this
0x18000a6ac  mov     edx, 0A0Bh; void *
0x18000a6b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6b7  mov     rcx, [rbp+188h]; this
0x18000a6be  mov     edx, 0A0Bh; void *
0x18000a6c3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a6c9  mov     rcx, [rbp+188h]; this
0x18000a6d0  mov     edx, 0A0Bh; void *
0x18000a6d5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
