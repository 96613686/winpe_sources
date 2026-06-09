# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a27c`
- end: `0x18000a4f6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005828`

## callees

- `0x1800038f0`
- `0x180007794`
- `0x180009764`
- `0x180009784`
- `0x18000a114`
- `0x18000a27c`
- `0x18000a934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a310`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a38c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a310`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a38c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a44b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a44b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a35d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a41a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a43c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a35d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a3f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a41a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a43c`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
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
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18000a27c  push    rbp
0x18000a27e  push    rbx
0x18000a27f  push    rsi
0x18000a280  push    rdi
0x18000a281  push    r14
0x18000a283  push    r15
0x18000a285  lea     rbp, [rsp-158h]
0x18000a28d  sub     rsp, 258h
0x18000a294  mov     rax, cs:__security_cookie
0x18000a29b  xor     rax, rsp
0x18000a29e  mov     [rbp+180h+var_40], rax
0x18000a2a5  xor     r15d, r15d
0x18000a2a8  lea     rax, [rsp+280h+Name]
0x18000a2ad  mov     [r8], r15
0x18000a2b0  mov     r14, r8
0x18000a2b3  mov     edx, 104h
0x18000a2b8  mov     r9d, 7FFFFFFEh
0x18000a2be  test    r9, r9
0x18000a2c1  jz      short loc_18000A2E2
0x18000a2c3  movzx   r8d, word ptr [rcx]
0x18000a2c7  test    r8w, r8w
0x18000a2cb  jz      short loc_18000A2E2
0x18000a2cd  mov     [rax], r8w
0x18000a2d1  add     rcx, 2
0x18000a2d5  add     rax, 2
0x18000a2d9  dec     r9
0x18000a2dc  sub     rdx, 1; unsigned __int64
0x18000a2e0  jnz     short loc_18000A2BE
0x18000a2e2  test    rdx, rdx
0x18000a2e5  lea     rcx, [rax-2]
0x18000a2e9  lea     r8, aP0; "_p0"
0x18000a2f0  cmovnz  rcx, rax
0x18000a2f4  mov     [rcx], r15w
0x18000a2f8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a2fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a302  mov     esi, 1F0003h
0x18000a307  lea     r8, [rsp+280h+Name]; lpName
0x18000a30c  mov     ecx, esi; dwDesiredAccess
0x18000a30e  xor     edx, edx; bInheritHandle
0x18000a310  call    cs:__imp_OpenSemaphoreW
0x18000a316  mov     rbx, rax
0x18000a319  test    rax, rax
0x18000a31c  jz      loc_18000A44B
0x18000a322  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a327  mov     [rsp+280h+var_25C], r15d
0x18000a32c  mov     rcx, rax; hHandle
0x18000a32f  mov     [rsp+280h+var_260], r15d; int
0x18000a334  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a339  mov     edi, eax
0x18000a33b  test    eax, eax
0x18000a33d  jns     short loc_18000A372
0x18000a33f  mov     rcx, [rbp+188h]; this
0x18000a346  lea     r8, aWil; "wil"
0x18000a34d  mov     r9d, eax; char *
0x18000a350  mov     edx, 0D6h; void *
0x18000a355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a35a  mov     rcx, rbx; hObject
0x18000a35d  call    cs:__imp_CloseHandle
0x18000a363  test    eax, eax
0x18000a365  jz      loc_18000A4C0
0x18000a36b  mov     eax, edi
0x18000a36d  jmp     loc_18000A46B
0x18000a372  lea     r8, asc_1800239F8; "h"
0x18000a379  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a37e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a383  lea     r8, [rsp+280h+Name]; lpName
0x18000a388  xor     edx, edx; bInheritHandle
0x18000a38a  mov     ecx, esi; dwDesiredAccess
0x18000a38c  call    cs:__imp_OpenSemaphoreW
0x18000a392  mov     rdi, rax
0x18000a395  test    rax, rax
0x18000a398  jz      loc_18000A426
0x18000a39e  lea     rdx, [rsp+280h+var_260]; int *
0x18000a3a3  mov     rcx, rax; hHandle
0x18000a3a6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a3ab  mov     esi, eax
0x18000a3ad  test    eax, eax
0x18000a3af  jns     short loc_18000A3F2
0x18000a3b1  mov     rcx, [rbp+188h]; this
0x18000a3b8  lea     r8, aWil; "wil"
0x18000a3bf  mov     r9d, eax; char *
0x18000a3c2  mov     edx, 0DEh; void *
0x18000a3c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3cc  mov     rcx, rdi; hObject
0x18000a3cf  call    cs:__imp_CloseHandle
0x18000a3d5  test    eax, eax
0x18000a3d7  jz      loc_18000A4D2
0x18000a3dd  mov     rcx, rbx; hObject
0x18000a3e0  call    cs:__imp_CloseHandle
0x18000a3e6  test    eax, eax
0x18000a3e8  jz      loc_18000A4E4
0x18000a3ee  mov     eax, esi
0x18000a3f0  jmp     short loc_18000A46B
0x18000a3f2  mov     rcx, rdi; hObject
0x18000a3f5  call    cs:__imp_CloseHandle
0x18000a3fb  test    eax, eax
0x18000a3fd  jz      loc_18000A48A
0x18000a403  movsxd  rax, [rsp+280h+var_25C]
0x18000a408  movsxd  rcx, [rsp+280h+var_260]
0x18000a40d  shl     rcx, 1Fh
0x18000a411  or      rcx, rax
0x18000a414  mov     [r14], rcx
0x18000a417  mov     rcx, rbx; hObject
0x18000a41a  call    cs:__imp_CloseHandle
0x18000a420  test    eax, eax
0x18000a422  jz      short loc_18000A49C
0x18000a424  jmp     short loc_18000A456
0x18000a426  mov     rcx, [rbp+188h]; this
0x18000a42d  mov     edx, 0DCh; void *
0x18000a432  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a437  mov     rcx, rbx; hObject
0x18000a43a  mov     edi, eax
0x18000a43c  call    cs:__imp_CloseHandle
0x18000a442  test    eax, eax
0x18000a444  jz      short loc_18000A4AE
0x18000a446  jmp     loc_18000A36B
0x18000a44b  call    cs:__imp_GetLastError
0x18000a451  cmp     eax, 2
0x18000a454  jnz     short loc_18000A45A
0x18000a456  xor     eax, eax
0x18000a458  jmp     short loc_18000A46B
0x18000a45a  mov     rcx, [rbp+188h]; this
0x18000a461  mov     edx, 0D0h; void *
0x18000a466  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a46b  mov     rcx, [rbp+180h+var_40]
0x18000a472  xor     rcx, rsp; StackCookie
0x18000a475  call    __security_check_cookie
0x18000a47a  add     rsp, 258h
0x18000a481  pop     r15
0x18000a483  pop     r14
0x18000a485  pop     rdi
0x18000a486  pop     rsi
0x18000a487  pop     rbx
0x18000a488  pop     rbp
0x18000a489  retn
0x18000a48a  mov     rcx, [rbp+188h]; this
0x18000a491  mov     edx, 0A0Bh; void *
0x18000a496  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a49c  mov     rcx, [rbp+188h]; this
0x18000a4a3  mov     edx, 0A0Bh; void *
0x18000a4a8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4ae  mov     rcx, [rbp+188h]; this
0x18000a4b5  mov     edx, 0A0Bh; void *
0x18000a4ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4c0  mov     rcx, [rbp+188h]; this
0x18000a4c7  mov     edx, 0A0Bh; void *
0x18000a4cc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4d2  mov     rcx, [rbp+188h]; this
0x18000a4d9  mov     edx, 0A0Bh; void *
0x18000a4de  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a4e4  mov     rcx, [rbp+188h]; this
0x18000a4eb  mov     edx, 0A0Bh; void *
0x18000a4f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
