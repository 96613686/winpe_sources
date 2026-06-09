# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000bacc`
- end: `0x14000bd9b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `719`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400062cc`
- `0x1400066a8`

## callees

- `0x140002490`
- `0x1400080a0`
- `0x14000aab4`
- `0x14000aad4`
- `0x14000b448`
- `0x14000bacc`
- `0x14000c720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bb63`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bbf1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bb63`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bbf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bce2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bccd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bc9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bccd`

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
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x14000bacc  push    rbp
0x14000bace  push    rbx
0x14000bacf  push    rsi
0x14000bad0  push    rdi
0x14000bad1  push    r14
0x14000bad3  push    r15
0x14000bad5  lea     rbp, [rsp-158h]
0x14000badd  sub     rsp, 258h
0x14000bae4  mov     rax, cs:__security_cookie
0x14000baeb  xor     rax, rsp
0x14000baee  mov     [rbp+180h+var_40], rax
0x14000baf5  xor     r15d, r15d
0x14000baf8  lea     rax, [rsp+280h+Name]
0x14000bafd  mov     esi, 104h
0x14000bb02  mov     [r8], r15
0x14000bb05  mov     edx, esi
0x14000bb07  mov     r14, r8
0x14000bb0a  mov     r9d, 7FFFFFFEh
0x14000bb10  test    r9, r9
0x14000bb13  jz      short loc_14000BB34
0x14000bb15  movzx   r8d, word ptr [rcx]
0x14000bb19  test    r8w, r8w
0x14000bb1d  jz      short loc_14000BB34
0x14000bb1f  mov     [rax], r8w
0x14000bb23  add     rcx, 2
0x14000bb27  add     rax, 2
0x14000bb2b  dec     r9
0x14000bb2e  sub     rdx, 1
0x14000bb32  jnz     short loc_14000BB10
0x14000bb34  test    rdx, rdx
0x14000bb37  lea     rcx, [rax-2]
0x14000bb3b  lea     r8, aP0; "_p0"
0x14000bb42  mov     rdx, rsi; unsigned __int64
0x14000bb45  cmovnz  rcx, rax
0x14000bb49  mov     [rcx], r15w
0x14000bb4d  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000bb52  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000bb57  lea     r8, [rsp+280h+Name]; lpName
0x14000bb5c  xor     edx, edx; bInheritHandle
0x14000bb5e  mov     ecx, 1F0003h; dwDesiredAccess
0x14000bb63  call    cs:__imp_OpenSemaphoreW
0x14000bb6a  nop     dword ptr [rax+rax+00h]
0x14000bb6f  mov     rbx, rax
0x14000bb72  test    rax, rax
0x14000bb75  jz      loc_14000BCE2
0x14000bb7b  lea     rdx, [rsp+280h+var_25C]; int *
0x14000bb80  mov     [rsp+280h+var_25C], r15d
0x14000bb85  mov     rcx, rax; hHandle
0x14000bb88  mov     [rsp+280h+var_260], r15d; int
0x14000bb8d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000bb92  mov     edi, eax
0x14000bb94  test    eax, eax
0x14000bb96  jns     short loc_14000BBD1
0x14000bb98  mov     rcx, [rbp+188h]; this
0x14000bb9f  lea     r8, aWil; "wil"
0x14000bba6  mov     r9d, eax; char *
0x14000bba9  mov     edx, 0D6h; void *
0x14000bbae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bbb3  mov     rcx, rbx; hObject
0x14000bbb6  call    cs:__imp_CloseHandle
0x14000bbbd  nop     dword ptr [rax+rax+00h]
0x14000bbc2  test    eax, eax
0x14000bbc4  jz      loc_14000BD65
0x14000bbca  mov     eax, edi
0x14000bbcc  jmp     loc_14000BD0F
0x14000bbd1  lea     r8, asc_140066B58; "h"
0x14000bbd8  mov     rdx, rsi; unsigned __int64
0x14000bbdb  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000bbe0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000bbe5  lea     r8, [rsp+280h+Name]; lpName
0x14000bbea  xor     edx, edx; bInheritHandle
0x14000bbec  mov     ecx, 1F0003h; dwDesiredAccess
0x14000bbf1  call    cs:__imp_OpenSemaphoreW
0x14000bbf8  nop     dword ptr [rax+rax+00h]
0x14000bbfd  mov     rdi, rax
0x14000bc00  test    rax, rax
0x14000bc03  jz      loc_14000BCB0
0x14000bc09  lea     rdx, [rsp+280h+var_260]; int *
0x14000bc0e  mov     rcx, rax; hHandle
0x14000bc11  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000bc16  mov     esi, eax
0x14000bc18  test    eax, eax
0x14000bc1a  jns     short loc_14000BC6C
0x14000bc1c  mov     rcx, [rbp+188h]; this
0x14000bc23  lea     r8, aWil; "wil"
0x14000bc2a  mov     r9d, eax; char *
0x14000bc2d  mov     edx, 0DEh; void *
0x14000bc32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bc37  mov     rcx, rdi; hObject
0x14000bc3a  call    cs:__imp_CloseHandle
0x14000bc41  nop     dword ptr [rax+rax+00h]
0x14000bc46  test    eax, eax
0x14000bc48  jz      loc_14000BD77
0x14000bc4e  mov     rcx, rbx; hObject
0x14000bc51  call    cs:__imp_CloseHandle
0x14000bc58  nop     dword ptr [rax+rax+00h]
0x14000bc5d  test    eax, eax
0x14000bc5f  jz      loc_14000BD89
0x14000bc65  mov     eax, esi
0x14000bc67  jmp     loc_14000BD0F
0x14000bc6c  mov     rcx, rdi; hObject
0x14000bc6f  call    cs:__imp_CloseHandle
0x14000bc76  nop     dword ptr [rax+rax+00h]
0x14000bc7b  test    eax, eax
0x14000bc7d  jz      loc_14000BD2F
0x14000bc83  movsxd  rax, [rsp+280h+var_25C]
0x14000bc88  movsxd  rcx, [rsp+280h+var_260]
0x14000bc8d  shl     rcx, 1Fh
0x14000bc91  or      rcx, rax
0x14000bc94  mov     [r14], rcx
0x14000bc97  mov     rcx, rbx; hObject
0x14000bc9a  call    cs:__imp_CloseHandle
0x14000bca1  nop     dword ptr [rax+rax+00h]
0x14000bca6  test    eax, eax
0x14000bca8  jz      loc_14000BD41
0x14000bcae  jmp     short loc_14000BCF3
0x14000bcb0  mov     rcx, [rbp+188h]; this
0x14000bcb7  lea     r8, aWil; "wil"
0x14000bcbe  mov     edx, 0DCh; void *
0x14000bcc3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bcc8  mov     rcx, rbx; hObject
0x14000bccb  mov     edi, eax
0x14000bccd  call    cs:__imp_CloseHandle
0x14000bcd4  nop     dword ptr [rax+rax+00h]
0x14000bcd9  test    eax, eax
0x14000bcdb  jz      short loc_14000BD53
0x14000bcdd  jmp     loc_14000BBCA
0x14000bce2  call    cs:__imp_GetLastError
0x14000bce9  nop     dword ptr [rax+rax+00h]
0x14000bcee  cmp     eax, 2
0x14000bcf1  jnz     short loc_14000BCF7
0x14000bcf3  xor     eax, eax
0x14000bcf5  jmp     short loc_14000BD0F
0x14000bcf7  mov     rcx, [rbp+188h]; this
0x14000bcfe  lea     r8, aWil; "wil"
0x14000bd05  mov     edx, 0D0h; void *
0x14000bd0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bd0f  mov     rcx, [rbp+180h+var_40]
0x14000bd16  xor     rcx, rsp; StackCookie
0x14000bd19  call    __security_check_cookie
0x14000bd1e  add     rsp, 258h
0x14000bd25  pop     r15
0x14000bd27  pop     r14
0x14000bd29  pop     rdi
0x14000bd2a  pop     rsi
0x14000bd2b  pop     rbx
0x14000bd2c  pop     rbp
0x14000bd2d  retn
0x14000bd2f  mov     rcx, [rbp+188h]; this
0x14000bd36  mov     edx, 0A0Bh; void *
0x14000bd3b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd41  mov     rcx, [rbp+188h]; this
0x14000bd48  mov     edx, 0A0Bh; void *
0x14000bd4d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd53  mov     rcx, [rbp+188h]; this
0x14000bd5a  mov     edx, 0A0Bh; void *
0x14000bd5f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd65  mov     rcx, [rbp+188h]; this
0x14000bd6c  mov     edx, 0A0Bh; void *
0x14000bd71  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd77  mov     rcx, [rbp+188h]; this
0x14000bd7e  mov     edx, 0A0Bh; void *
0x14000bd83  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bd89  mov     rcx, [rbp+188h]; this
0x14000bd90  mov     edx, 0A0Bh; void *
0x14000bd95  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
