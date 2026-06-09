# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b39c`
- end: `0x18000b608`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180005ad8`
- `0x180005e7c`

## callees

- `0x1800017c0`
- `0x180008574`
- `0x18000a514`
- `0x18000a534`
- `0x18000af90`
- `0x18000b39c`
- `0x18000bb8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b55d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b55d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b52c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b54e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b476`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b507`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b52c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b54e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b430`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b4a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b430`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b4a5`

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
0x18000b39c  push    rbp
0x18000b39e  push    rbx
0x18000b39f  push    rsi
0x18000b3a0  push    rdi
0x18000b3a1  push    r14
0x18000b3a3  push    r15
0x18000b3a5  lea     rbp, [rsp-158h]
0x18000b3ad  sub     rsp, 258h
0x18000b3b4  mov     rax, cs:__security_cookie
0x18000b3bb  xor     rax, rsp
0x18000b3be  mov     [rbp+180h+var_40], rax
0x18000b3c5  xor     r15d, r15d
0x18000b3c8  lea     rax, [rsp+280h+Name]
0x18000b3cd  mov     [r8], r15
0x18000b3d0  mov     r14, r8
0x18000b3d3  mov     edx, 104h
0x18000b3d8  mov     r9d, 7FFFFFFEh
0x18000b3de  test    r9, r9
0x18000b3e1  jz      short loc_18000B402
0x18000b3e3  movzx   r8d, word ptr [rcx]
0x18000b3e7  test    r8w, r8w
0x18000b3eb  jz      short loc_18000B402
0x18000b3ed  mov     [rax], r8w
0x18000b3f1  add     rcx, 2
0x18000b3f5  add     rax, 2
0x18000b3f9  dec     r9
0x18000b3fc  sub     rdx, 1; unsigned __int64
0x18000b400  jnz     short loc_18000B3DE
0x18000b402  test    rdx, rdx
0x18000b405  lea     rcx, [rax-2]
0x18000b409  lea     r8, aP0; "_p0"
0x18000b410  cmovnz  rcx, rax
0x18000b414  mov     [rcx], r15w
0x18000b418  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b41d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b422  mov     esi, 1F0003h
0x18000b427  lea     r8, [rsp+280h+Name]; lpName
0x18000b42c  mov     ecx, esi; dwDesiredAccess
0x18000b42e  xor     edx, edx; bInheritHandle
0x18000b430  call    cs:__imp_OpenSemaphoreW
0x18000b436  mov     rbx, rax
0x18000b439  test    rax, rax
0x18000b43c  jz      loc_18000B55D
0x18000b442  lea     rdx, [rsp+280h+var_25C]; int *
0x18000b447  mov     [rsp+280h+var_25C], r15d
0x18000b44c  mov     rcx, rax; hHandle
0x18000b44f  mov     [rsp+280h+var_260], r15d; int
0x18000b454  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b459  mov     edi, eax
0x18000b45b  test    eax, eax
0x18000b45d  jns     short loc_18000B48B
0x18000b45f  mov     rcx, [rbp+188h]; this
0x18000b466  mov     r9d, eax; char *
0x18000b469  mov     edx, 0D6h; void *
0x18000b46e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b473  mov     rcx, rbx; hObject
0x18000b476  call    cs:__imp_CloseHandle
0x18000b47c  test    eax, eax
0x18000b47e  jz      loc_18000B5D2
0x18000b484  mov     eax, edi
0x18000b486  jmp     loc_18000B57D
0x18000b48b  lea     r8, asc_18000EC28; "h"
0x18000b492  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000b497  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b49c  lea     r8, [rsp+280h+Name]; lpName
0x18000b4a1  xor     edx, edx; bInheritHandle
0x18000b4a3  mov     ecx, esi; dwDesiredAccess
0x18000b4a5  call    cs:__imp_OpenSemaphoreW
0x18000b4ab  mov     rdi, rax
0x18000b4ae  test    rax, rax
0x18000b4b1  jz      loc_18000B538
0x18000b4b7  lea     rdx, [rsp+280h+var_260]; int *
0x18000b4bc  mov     rcx, rax; hHandle
0x18000b4bf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b4c4  mov     esi, eax
0x18000b4c6  test    eax, eax
0x18000b4c8  jns     short loc_18000B504
0x18000b4ca  mov     rcx, [rbp+188h]; this
0x18000b4d1  mov     r9d, eax; char *
0x18000b4d4  mov     edx, 0DEh; void *
0x18000b4d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b4de  mov     rcx, rdi; hObject
0x18000b4e1  call    cs:__imp_CloseHandle
0x18000b4e7  test    eax, eax
0x18000b4e9  jz      loc_18000B5E4
0x18000b4ef  mov     rcx, rbx; hObject
0x18000b4f2  call    cs:__imp_CloseHandle
0x18000b4f8  test    eax, eax
0x18000b4fa  jz      loc_18000B5F6
0x18000b500  mov     eax, esi
0x18000b502  jmp     short loc_18000B57D
0x18000b504  mov     rcx, rdi; hObject
0x18000b507  call    cs:__imp_CloseHandle
0x18000b50d  test    eax, eax
0x18000b50f  jz      loc_18000B59C
0x18000b515  movsxd  rax, [rsp+280h+var_25C]
0x18000b51a  movsxd  rcx, [rsp+280h+var_260]
0x18000b51f  shl     rcx, 1Fh
0x18000b523  or      rcx, rax
0x18000b526  mov     [r14], rcx
0x18000b529  mov     rcx, rbx; hObject
0x18000b52c  call    cs:__imp_CloseHandle
0x18000b532  test    eax, eax
0x18000b534  jz      short loc_18000B5AE
0x18000b536  jmp     short loc_18000B568
0x18000b538  mov     rcx, [rbp+188h]; this
0x18000b53f  mov     edx, 0DCh; void *
0x18000b544  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b549  mov     rcx, rbx; hObject
0x18000b54c  mov     edi, eax
0x18000b54e  call    cs:__imp_CloseHandle
0x18000b554  test    eax, eax
0x18000b556  jz      short loc_18000B5C0
0x18000b558  jmp     loc_18000B484
0x18000b55d  call    cs:__imp_GetLastError
0x18000b563  cmp     eax, 2
0x18000b566  jnz     short loc_18000B56C
0x18000b568  xor     eax, eax
0x18000b56a  jmp     short loc_18000B57D
0x18000b56c  mov     rcx, [rbp+188h]; this
0x18000b573  mov     edx, 0D0h; void *
0x18000b578  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b57d  mov     rcx, [rbp+180h+var_40]
0x18000b584  xor     rcx, rsp; StackCookie
0x18000b587  call    __security_check_cookie
0x18000b58c  add     rsp, 258h
0x18000b593  pop     r15
0x18000b595  pop     r14
0x18000b597  pop     rdi
0x18000b598  pop     rsi
0x18000b599  pop     rbx
0x18000b59a  pop     rbp
0x18000b59b  retn
0x18000b59c  mov     rcx, [rbp+188h]; this
0x18000b5a3  mov     edx, 0A0Bh; void *
0x18000b5a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b5ae  mov     rcx, [rbp+188h]; this
0x18000b5b5  mov     edx, 0A0Bh; void *
0x18000b5ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b5c0  mov     rcx, [rbp+188h]; this
0x18000b5c7  mov     edx, 0A0Bh; void *
0x18000b5cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b5d2  mov     rcx, [rbp+188h]; this
0x18000b5d9  mov     edx, 0A0Bh; void *
0x18000b5de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b5e4  mov     rcx, [rbp+188h]; this
0x18000b5eb  mov     edx, 0A0Bh; void *
0x18000b5f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b5f6  mov     rcx, [rbp+188h]; this
0x18000b5fd  mov     edx, 0A0Bh; void *
0x18000b602  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
