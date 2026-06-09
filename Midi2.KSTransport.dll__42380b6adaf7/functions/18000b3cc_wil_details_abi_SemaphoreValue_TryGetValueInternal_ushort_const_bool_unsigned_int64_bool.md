# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b3cc`
- end: `0x18000b65b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800066b8`

## callees

- `0x180004410`
- `0x1800086f8`
- `0x18000a7f4`
- `0x18000a814`
- `0x18000b1a4`
- `0x18000b3cc`
- `0x18000bb04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b460`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b4dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b460`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b51f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b56d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b59a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b51f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b56d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b59a`

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
0x18000b3cc  push    rbp
0x18000b3ce  push    rbx
0x18000b3cf  push    rsi
0x18000b3d0  push    rdi
0x18000b3d1  push    r14
0x18000b3d3  push    r15
0x18000b3d5  lea     rbp, [rsp-158h]
0x18000b3dd  sub     rsp, 258h
0x18000b3e4  mov     rax, cs:__security_cookie
0x18000b3eb  xor     rax, rsp
0x18000b3ee  mov     [rbp+180h+var_40], rax
0x18000b3f5  xor     r15d, r15d
0x18000b3f8  lea     rax, [rsp+280h+Name]
0x18000b3fd  mov     [r8], r15
0x18000b400  mov     r14, r8
0x18000b403  mov     edx, 104h
0x18000b408  mov     r9d, 7FFFFFFEh
0x18000b40e  test    r9, r9
0x18000b411  jz      short loc_18000B432
0x18000b413  movzx   r8d, word ptr [rcx]
0x18000b417  test    r8w, r8w
0x18000b41b  jz      short loc_18000B432
0x18000b41d  mov     [rax], r8w
0x18000b421  add     rcx, 2
0x18000b425  add     rax, 2
0x18000b429  dec     r9
0x18000b42c  sub     rdx, 1; unsigned __int64
0x18000b430  jnz     short loc_18000B40E
0x18000b432  test    rdx, rdx
0x18000b435  lea     rcx, [rax-2]
0x18000b439  lea     r8, aP0; "_p0"
0x18000b440  cmovnz  rcx, rax
0x18000b444  mov     [rcx], r15w
0x18000b448  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b44d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b452  mov     esi, 1F0003h
0x18000b457  lea     r8, [rsp+280h+Name]; lpName
0x18000b45c  mov     ecx, esi; dwDesiredAccess
0x18000b45e  xor     edx, edx; bInheritHandle
0x18000b460  call    cs:__imp_OpenSemaphoreW
0x18000b466  mov     rbx, rax
0x18000b469  test    rax, rax
0x18000b46c  jz      loc_18000B5A9
0x18000b472  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b477  mov     [rsp+280h+var_25C], r15d
0x18000b47c  mov     rcx, rax; hHandle
0x18000b47f  mov     [rsp+280h+var_260], r15d; int
0x18000b484  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b489  mov     edi, eax
0x18000b48b  test    eax, eax
0x18000b48d  jns     short loc_18000B4C2
0x18000b48f  mov     rcx, [rbp+188h]; this
0x18000b496  lea     r8, aWil; "wil"
0x18000b49d  mov     r9d, eax; char *
0x18000b4a0  mov     edx, 0D6h; void *
0x18000b4a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4aa  mov     rcx, rbx; hObject
0x18000b4ad  call    cs:__imp_CloseHandle
0x18000b4b3  test    eax, eax
0x18000b4b5  jz      loc_18000B625
0x18000b4bb  mov     eax, edi
0x18000b4bd  jmp     loc_18000B5D0
0x18000b4c2  lea     r8, asc_1800610F0; "h"
0x18000b4c9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b4ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b4d3  lea     r8, [rsp+280h+Name]; lpName
0x18000b4d8  xor     edx, edx; bInheritHandle
0x18000b4da  mov     ecx, esi; dwDesiredAccess
0x18000b4dc  call    cs:__imp_OpenSemaphoreW
0x18000b4e2  mov     rdi, rax
0x18000b4e5  test    rax, rax
0x18000b4e8  jz      loc_18000B57D
0x18000b4ee  lea     rdx, [rsp+280h+var_260]; int *
0x18000b4f3  mov     rcx, rax; hHandle
0x18000b4f6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b4fb  mov     esi, eax
0x18000b4fd  test    eax, eax
0x18000b4ff  jns     short loc_18000B545
0x18000b501  mov     rcx, [rbp+188h]; this
0x18000b508  lea     r8, aWil; "wil"
0x18000b50f  mov     r9d, eax; char *
0x18000b512  mov     edx, 0DEh; void *
0x18000b517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b51c  mov     rcx, rdi; hObject
0x18000b51f  call    cs:__imp_CloseHandle
0x18000b525  test    eax, eax
0x18000b527  jz      loc_18000B637
0x18000b52d  mov     rcx, rbx; hObject
0x18000b530  call    cs:__imp_CloseHandle
0x18000b536  test    eax, eax
0x18000b538  jz      loc_18000B649
0x18000b53e  mov     eax, esi
0x18000b540  jmp     loc_18000B5D0
0x18000b545  mov     rcx, rdi; hObject
0x18000b548  call    cs:__imp_CloseHandle
0x18000b54e  test    eax, eax
0x18000b550  jz      loc_18000B5EF
0x18000b556  movsxd  rax, [rsp+280h+var_25C]
0x18000b55b  movsxd  rcx, [rsp+280h+var_260]
0x18000b560  shl     rcx, 1Fh
0x18000b564  or      rcx, rax
0x18000b567  mov     [r14], rcx
0x18000b56a  mov     rcx, rbx; hObject
0x18000b56d  call    cs:__imp_CloseHandle
0x18000b573  test    eax, eax
0x18000b575  jz      loc_18000B601
0x18000b57b  jmp     short loc_18000B5B4
0x18000b57d  mov     rcx, [rbp+188h]; this
0x18000b584  lea     r8, aWil; "wil"
0x18000b58b  mov     edx, 0DCh; void *
0x18000b590  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b595  mov     rcx, rbx; hObject
0x18000b598  mov     edi, eax
0x18000b59a  call    cs:__imp_CloseHandle
0x18000b5a0  test    eax, eax
0x18000b5a2  jz      short loc_18000B613
0x18000b5a4  jmp     loc_18000B4BB
0x18000b5a9  call    cs:__imp_GetLastError
0x18000b5af  cmp     eax, 2
0x18000b5b2  jnz     short loc_18000B5B8
0x18000b5b4  xor     eax, eax
0x18000b5b6  jmp     short loc_18000B5D0
0x18000b5b8  mov     rcx, [rbp+188h]; this
0x18000b5bf  lea     r8, aWil; "wil"
0x18000b5c6  mov     edx, 0D0h; void *
0x18000b5cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b5d0  mov     rcx, [rbp+180h+var_40]
0x18000b5d7  xor     rcx, rsp; StackCookie
0x18000b5da  call    __security_check_cookie
0x18000b5df  add     rsp, 258h
0x18000b5e6  pop     r15
0x18000b5e8  pop     r14
0x18000b5ea  pop     rdi
0x18000b5eb  pop     rsi
0x18000b5ec  pop     rbx
0x18000b5ed  pop     rbp
0x18000b5ee  retn
0x18000b5ef  mov     rcx, [rbp+188h]; this
0x18000b5f6  mov     edx, 0A0Bh; void *
0x18000b5fb  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b601  mov     rcx, [rbp+188h]; this
0x18000b608  mov     edx, 0A0Bh; void *
0x18000b60d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b613  mov     rcx, [rbp+188h]; this
0x18000b61a  mov     edx, 0A0Bh; void *
0x18000b61f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b625  mov     rcx, [rbp+188h]; this
0x18000b62c  mov     edx, 0A0Bh; void *
0x18000b631  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b637  mov     rcx, [rbp+188h]; this
0x18000b63e  mov     edx, 0A0Bh; void *
0x18000b643  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b649  mov     rcx, [rbp+188h]; this
0x18000b650  mov     edx, 0A0Bh; void *
0x18000b655  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
