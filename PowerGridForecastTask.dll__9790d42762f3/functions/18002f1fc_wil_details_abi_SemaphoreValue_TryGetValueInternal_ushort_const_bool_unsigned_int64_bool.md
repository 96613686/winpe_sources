# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002f1fc`
- end: `0x18002f476`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180028a60`
- `0x180028e30`

## callees

- `0x18002ae78`
- `0x18002dcb4`
- `0x18002dcd4`
- `0x18002ed40`
- `0x18002f1fc`
- `0x18002fecc`
- `0x1800350e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f34f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f39a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f2dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f34f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f39a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f3bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f3cb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f290`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f30c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f290`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002f30c`

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
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
  const char *v30; // r9
  __int64 v31; // r8
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v21);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x18002f1fc  push    rbp
0x18002f1fe  push    rbx
0x18002f1ff  push    rsi
0x18002f200  push    rdi
0x18002f201  push    r14
0x18002f203  push    r15
0x18002f205  lea     rbp, [rsp-158h]
0x18002f20d  sub     rsp, 258h
0x18002f214  mov     rax, cs:__security_cookie
0x18002f21b  xor     rax, rsp
0x18002f21e  mov     [rbp+180h+var_40], rax
0x18002f225  xor     r15d, r15d
0x18002f228  lea     rax, [rsp+280h+Name]
0x18002f22d  mov     [r8], r15
0x18002f230  mov     r14, r8
0x18002f233  mov     edx, 104h
0x18002f238  mov     r9d, 7FFFFFFEh
0x18002f23e  test    r9, r9
0x18002f241  jz      short loc_18002F262
0x18002f243  movzx   r8d, word ptr [rcx]
0x18002f247  test    r8w, r8w
0x18002f24b  jz      short loc_18002F262
0x18002f24d  mov     [rax], r8w
0x18002f251  add     rcx, 2
0x18002f255  add     rax, 2
0x18002f259  dec     r9
0x18002f25c  sub     rdx, 1; unsigned __int64
0x18002f260  jnz     short loc_18002F23E
0x18002f262  test    rdx, rdx
0x18002f265  lea     rcx, [rax-2]
0x18002f269  lea     r8, aP0; "_p0"
0x18002f270  cmovnz  rcx, rax
0x18002f274  mov     [rcx], r15w
0x18002f278  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002f27d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f282  mov     esi, 1F0003h
0x18002f287  lea     r8, [rsp+280h+Name]; lpName
0x18002f28c  mov     ecx, esi; dwDesiredAccess
0x18002f28e  xor     edx, edx; bInheritHandle
0x18002f290  call    cs:__imp_OpenSemaphoreW
0x18002f296  mov     rbx, rax
0x18002f299  test    rax, rax
0x18002f29c  jz      loc_18002F3CB
0x18002f2a2  lea     rdx, [rsp+280h+var_25C]; int *
0x18002f2a7  mov     [rsp+280h+var_25C], r15d
0x18002f2ac  mov     rcx, rax; hHandle
0x18002f2af  mov     [rsp+280h+var_260], r15d; int
0x18002f2b4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002f2b9  mov     edi, eax
0x18002f2bb  test    eax, eax
0x18002f2bd  jns     short loc_18002F2F2
0x18002f2bf  mov     rcx, [rbp+188h]; this
0x18002f2c6  lea     r8, aWil; "wil"
0x18002f2cd  mov     r9d, eax; char *
0x18002f2d0  mov     edx, 0D6h; void *
0x18002f2d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2da  mov     rcx, rbx; hObject
0x18002f2dd  call    cs:__imp_CloseHandle
0x18002f2e3  test    eax, eax
0x18002f2e5  jz      loc_18002F440
0x18002f2eb  mov     eax, edi
0x18002f2ed  jmp     loc_18002F3EB
0x18002f2f2  lea     r8, asc_18003D418; "h"
0x18002f2f9  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002f2fe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002f303  lea     r8, [rsp+280h+Name]; lpName
0x18002f308  xor     edx, edx; bInheritHandle
0x18002f30a  mov     ecx, esi; dwDesiredAccess
0x18002f30c  call    cs:__imp_OpenSemaphoreW
0x18002f312  mov     rdi, rax
0x18002f315  test    rax, rax
0x18002f318  jz      loc_18002F3A6
0x18002f31e  lea     rdx, [rsp+280h+var_260]; int *
0x18002f323  mov     rcx, rax; hHandle
0x18002f326  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002f32b  mov     esi, eax
0x18002f32d  test    eax, eax
0x18002f32f  jns     short loc_18002F372
0x18002f331  mov     rcx, [rbp+188h]; this
0x18002f338  lea     r8, aWil; "wil"
0x18002f33f  mov     r9d, eax; char *
0x18002f342  mov     edx, 0DEh; void *
0x18002f347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f34c  mov     rcx, rdi; hObject
0x18002f34f  call    cs:__imp_CloseHandle
0x18002f355  test    eax, eax
0x18002f357  jz      loc_18002F452
0x18002f35d  mov     rcx, rbx; hObject
0x18002f360  call    cs:__imp_CloseHandle
0x18002f366  test    eax, eax
0x18002f368  jz      loc_18002F464
0x18002f36e  mov     eax, esi
0x18002f370  jmp     short loc_18002F3EB
0x18002f372  mov     rcx, rdi; hObject
0x18002f375  call    cs:__imp_CloseHandle
0x18002f37b  test    eax, eax
0x18002f37d  jz      loc_18002F40A
0x18002f383  movsxd  rax, [rsp+280h+var_25C]
0x18002f388  movsxd  rcx, [rsp+280h+var_260]
0x18002f38d  shl     rcx, 1Fh
0x18002f391  or      rcx, rax
0x18002f394  mov     [r14], rcx
0x18002f397  mov     rcx, rbx; hObject
0x18002f39a  call    cs:__imp_CloseHandle
0x18002f3a0  test    eax, eax
0x18002f3a2  jz      short loc_18002F41C
0x18002f3a4  jmp     short loc_18002F3D6
0x18002f3a6  mov     rcx, [rbp+188h]; this
0x18002f3ad  mov     edx, 0DCh; void *
0x18002f3b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f3b7  mov     rcx, rbx; hObject
0x18002f3ba  mov     edi, eax
0x18002f3bc  call    cs:__imp_CloseHandle
0x18002f3c2  test    eax, eax
0x18002f3c4  jz      short loc_18002F42E
0x18002f3c6  jmp     loc_18002F2EB
0x18002f3cb  call    cs:__imp_GetLastError
0x18002f3d1  cmp     eax, 2
0x18002f3d4  jnz     short loc_18002F3DA
0x18002f3d6  xor     eax, eax
0x18002f3d8  jmp     short loc_18002F3EB
0x18002f3da  mov     rcx, [rbp+188h]; this
0x18002f3e1  mov     edx, 0D0h; void *
0x18002f3e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f3eb  mov     rcx, [rbp+180h+var_40]
0x18002f3f2  xor     rcx, rsp; StackCookie
0x18002f3f5  call    __security_check_cookie
0x18002f3fa  add     rsp, 258h
0x18002f401  pop     r15
0x18002f403  pop     r14
0x18002f405  pop     rdi
0x18002f406  pop     rsi
0x18002f407  pop     rbx
0x18002f408  pop     rbp
0x18002f409  retn
0x18002f40a  mov     rcx, [rbp+188h]; this
0x18002f411  mov     edx, 0A0Bh; void *
0x18002f416  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f41c  mov     rcx, [rbp+188h]; this
0x18002f423  mov     edx, 0A0Bh; void *
0x18002f428  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f42e  mov     rcx, [rbp+188h]; this
0x18002f435  mov     edx, 0A0Bh; void *
0x18002f43a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f440  mov     rcx, [rbp+188h]; this
0x18002f447  mov     edx, 0A0Bh; void *
0x18002f44c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f452  mov     rcx, [rbp+188h]; this
0x18002f459  mov     edx, 0A0Bh; void *
0x18002f45e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002f464  mov     rcx, [rbp+188h]; this
0x18002f46b  mov     edx, 0A0Bh; void *
0x18002f470  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
