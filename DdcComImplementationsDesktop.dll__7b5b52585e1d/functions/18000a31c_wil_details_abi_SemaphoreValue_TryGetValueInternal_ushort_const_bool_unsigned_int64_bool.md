# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a31c`
- end: `0x18000a588`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800060bc`
- `0x180006460`

## callees

- `0x1800016b0`
- `0x1800078e4`
- `0x1800094b4`
- `0x1800094d4`
- `0x180009f18`
- `0x18000a31c`
- `0x18000ab0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a4dd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a3b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a425`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a3b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a472`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a461`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a472`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a487`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a4ce`

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
0x18000a31c  push    rbp
0x18000a31e  push    rbx
0x18000a31f  push    rsi
0x18000a320  push    rdi
0x18000a321  push    r14
0x18000a323  push    r15
0x18000a325  lea     rbp, [rsp-158h]
0x18000a32d  sub     rsp, 258h
0x18000a334  mov     rax, cs:__security_cookie
0x18000a33b  xor     rax, rsp
0x18000a33e  mov     [rbp+180h+var_40], rax
0x18000a345  xor     r15d, r15d
0x18000a348  lea     rax, [rsp+280h+Name]
0x18000a34d  mov     [r8], r15
0x18000a350  mov     r14, r8
0x18000a353  mov     edx, 104h
0x18000a358  mov     r9d, 7FFFFFFEh
0x18000a35e  test    r9, r9
0x18000a361  jz      short loc_18000A382
0x18000a363  movzx   r8d, word ptr [rcx]
0x18000a367  test    r8w, r8w
0x18000a36b  jz      short loc_18000A382
0x18000a36d  mov     [rax], r8w
0x18000a371  add     rcx, 2
0x18000a375  add     rax, 2
0x18000a379  dec     r9
0x18000a37c  sub     rdx, 1; unsigned __int64
0x18000a380  jnz     short loc_18000A35E
0x18000a382  test    rdx, rdx
0x18000a385  lea     rcx, [rax-2]
0x18000a389  lea     r8, aP0; "_p0"
0x18000a390  cmovnz  rcx, rax
0x18000a394  mov     [rcx], r15w
0x18000a398  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a39d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3a2  mov     esi, 1F0003h
0x18000a3a7  lea     r8, [rsp+280h+Name]; lpName
0x18000a3ac  mov     ecx, esi; dwDesiredAccess
0x18000a3ae  xor     edx, edx; bInheritHandle
0x18000a3b0  call    cs:__imp_OpenSemaphoreW
0x18000a3b6  mov     rbx, rax
0x18000a3b9  test    rax, rax
0x18000a3bc  jz      loc_18000A4DD
0x18000a3c2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a3c7  mov     [rsp+280h+var_25C], r15d
0x18000a3cc  mov     rcx, rax; hHandle
0x18000a3cf  mov     [rsp+280h+var_260], r15d; int
0x18000a3d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a3d9  mov     edi, eax
0x18000a3db  test    eax, eax
0x18000a3dd  jns     short loc_18000A40B
0x18000a3df  mov     rcx, [rbp+188h]; this
0x18000a3e6  mov     r9d, eax; char *
0x18000a3e9  mov     edx, 0D6h; void *
0x18000a3ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3f3  mov     rcx, rbx; hObject
0x18000a3f6  call    cs:__imp_CloseHandle
0x18000a3fc  test    eax, eax
0x18000a3fe  jz      loc_18000A552
0x18000a404  mov     eax, edi
0x18000a406  jmp     loc_18000A4FD
0x18000a40b  lea     r8, asc_18000F4E8; "h"
0x18000a412  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a417  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a41c  lea     r8, [rsp+280h+Name]; lpName
0x18000a421  xor     edx, edx; bInheritHandle
0x18000a423  mov     ecx, esi; dwDesiredAccess
0x18000a425  call    cs:__imp_OpenSemaphoreW
0x18000a42b  mov     rdi, rax
0x18000a42e  test    rax, rax
0x18000a431  jz      loc_18000A4B8
0x18000a437  lea     rdx, [rsp+280h+var_260]; int *
0x18000a43c  mov     rcx, rax; hHandle
0x18000a43f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a444  mov     esi, eax
0x18000a446  test    eax, eax
0x18000a448  jns     short loc_18000A484
0x18000a44a  mov     rcx, [rbp+188h]; this
0x18000a451  mov     r9d, eax; char *
0x18000a454  mov     edx, 0DEh; void *
0x18000a459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a45e  mov     rcx, rdi; hObject
0x18000a461  call    cs:__imp_CloseHandle
0x18000a467  test    eax, eax
0x18000a469  jz      loc_18000A564
0x18000a46f  mov     rcx, rbx; hObject
0x18000a472  call    cs:__imp_CloseHandle
0x18000a478  test    eax, eax
0x18000a47a  jz      loc_18000A576
0x18000a480  mov     eax, esi
0x18000a482  jmp     short loc_18000A4FD
0x18000a484  mov     rcx, rdi; hObject
0x18000a487  call    cs:__imp_CloseHandle
0x18000a48d  test    eax, eax
0x18000a48f  jz      loc_18000A51C
0x18000a495  movsxd  rax, [rsp+280h+var_25C]
0x18000a49a  movsxd  rcx, [rsp+280h+var_260]
0x18000a49f  shl     rcx, 1Fh
0x18000a4a3  or      rcx, rax
0x18000a4a6  mov     [r14], rcx
0x18000a4a9  mov     rcx, rbx; hObject
0x18000a4ac  call    cs:__imp_CloseHandle
0x18000a4b2  test    eax, eax
0x18000a4b4  jz      short loc_18000A52E
0x18000a4b6  jmp     short loc_18000A4E8
0x18000a4b8  mov     rcx, [rbp+188h]; this
0x18000a4bf  mov     edx, 0DCh; void *
0x18000a4c4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a4c9  mov     rcx, rbx; hObject
0x18000a4cc  mov     edi, eax
0x18000a4ce  call    cs:__imp_CloseHandle
0x18000a4d4  test    eax, eax
0x18000a4d6  jz      short loc_18000A540
0x18000a4d8  jmp     loc_18000A404
0x18000a4dd  call    cs:__imp_GetLastError
0x18000a4e3  cmp     eax, 2
0x18000a4e6  jnz     short loc_18000A4EC
0x18000a4e8  xor     eax, eax
0x18000a4ea  jmp     short loc_18000A4FD
0x18000a4ec  mov     rcx, [rbp+188h]; this
0x18000a4f3  mov     edx, 0D0h; void *
0x18000a4f8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a4fd  mov     rcx, [rbp+180h+var_40]
0x18000a504  xor     rcx, rsp; StackCookie
0x18000a507  call    __security_check_cookie
0x18000a50c  add     rsp, 258h
0x18000a513  pop     r15
0x18000a515  pop     r14
0x18000a517  pop     rdi
0x18000a518  pop     rsi
0x18000a519  pop     rbx
0x18000a51a  pop     rbp
0x18000a51b  retn
0x18000a51c  mov     rcx, [rbp+188h]; this
0x18000a523  mov     edx, 0A0Bh; void *
0x18000a528  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a52e  mov     rcx, [rbp+188h]; this
0x18000a535  mov     edx, 0A0Bh; void *
0x18000a53a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a540  mov     rcx, [rbp+188h]; this
0x18000a547  mov     edx, 0A0Bh; void *
0x18000a54c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a552  mov     rcx, [rbp+188h]; this
0x18000a559  mov     edx, 0A0Bh; void *
0x18000a55e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a564  mov     rcx, [rbp+188h]; this
0x18000a56b  mov     edx, 0A0Bh; void *
0x18000a570  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a576  mov     rcx, [rbp+188h]; this
0x18000a57d  mov     edx, 0A0Bh; void *
0x18000a582  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
