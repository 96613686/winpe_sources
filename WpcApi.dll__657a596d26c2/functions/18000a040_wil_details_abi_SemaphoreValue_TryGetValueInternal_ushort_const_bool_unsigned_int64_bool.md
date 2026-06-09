# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a040`
- end: `0x18000a2ac`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800064a8`
- `0x18000fa9c`

## callees

- `0x1800032a0`
- `0x180007fb4`
- `0x180009414`
- `0x180009434`
- `0x180009d74`
- `0x18000a040`
- `0x18000a8ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a149`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a149`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a11a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a11a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a196`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a1f2`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  __int64 v15; // r8
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18000a040  push    rbp
0x18000a042  push    rbx
0x18000a043  push    rsi
0x18000a044  push    rdi
0x18000a045  push    r14
0x18000a047  push    r15
0x18000a049  lea     rbp, [rsp-158h]
0x18000a051  sub     rsp, 258h
0x18000a058  mov     rax, cs:__security_cookie
0x18000a05f  xor     rax, rsp
0x18000a062  mov     [rbp+180h+var_40], rax
0x18000a069  xor     r15d, r15d
0x18000a06c  lea     rax, [rsp+280h+Name]
0x18000a071  mov     [r8], r15
0x18000a074  mov     r14, r8
0x18000a077  mov     edx, 104h
0x18000a07c  mov     r9d, 7FFFFFFEh
0x18000a082  test    r9, r9
0x18000a085  jz      short loc_18000A0A6
0x18000a087  movzx   r8d, word ptr [rcx]
0x18000a08b  test    r8w, r8w
0x18000a08f  jz      short loc_18000A0A6
0x18000a091  mov     [rax], r8w
0x18000a095  add     rcx, 2
0x18000a099  add     rax, 2
0x18000a09d  dec     r9
0x18000a0a0  sub     rdx, 1; unsigned __int64
0x18000a0a4  jnz     short loc_18000A082
0x18000a0a6  test    rdx, rdx
0x18000a0a9  lea     rcx, [rax-2]
0x18000a0ad  lea     r8, aP0; "_p0"
0x18000a0b4  cmovnz  rcx, rax
0x18000a0b8  mov     [rcx], r15w
0x18000a0bc  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a0c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a0c6  mov     esi, 1F0003h
0x18000a0cb  lea     r8, [rsp+280h+Name]; lpName
0x18000a0d0  mov     ecx, esi; dwDesiredAccess
0x18000a0d2  xor     edx, edx; bInheritHandle
0x18000a0d4  call    cs:__imp_OpenSemaphoreW
0x18000a0da  mov     rbx, rax
0x18000a0dd  test    rax, rax
0x18000a0e0  jz      loc_18000A201
0x18000a0e6  lea     rdx, [rsp+280h+var_25C]; int *
0x18000a0eb  mov     [rsp+280h+var_25C], r15d
0x18000a0f0  mov     rcx, rax; hHandle
0x18000a0f3  mov     [rsp+280h+var_260], r15d; int
0x18000a0f8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a0fd  mov     edi, eax
0x18000a0ff  test    eax, eax
0x18000a101  jns     short loc_18000A12F
0x18000a103  mov     rcx, [rbp+188h]; this
0x18000a10a  mov     r9d, eax; char *
0x18000a10d  mov     edx, 0D6h; void *
0x18000a112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a117  mov     rcx, rbx; hObject
0x18000a11a  call    cs:__imp_CloseHandle
0x18000a120  test    eax, eax
0x18000a122  jz      loc_18000A276
0x18000a128  mov     eax, edi
0x18000a12a  jmp     loc_18000A221
0x18000a12f  lea     r8, asc_180032320; "h"
0x18000a136  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000a13b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a140  lea     r8, [rsp+280h+Name]; lpName
0x18000a145  xor     edx, edx; bInheritHandle
0x18000a147  mov     ecx, esi; dwDesiredAccess
0x18000a149  call    cs:__imp_OpenSemaphoreW
0x18000a14f  mov     rdi, rax
0x18000a152  test    rax, rax
0x18000a155  jz      loc_18000A1DC
0x18000a15b  lea     rdx, [rsp+280h+var_260]; int *
0x18000a160  mov     rcx, rax; hHandle
0x18000a163  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a168  mov     esi, eax
0x18000a16a  test    eax, eax
0x18000a16c  jns     short loc_18000A1A8
0x18000a16e  mov     rcx, [rbp+188h]; this
0x18000a175  mov     r9d, eax; char *
0x18000a178  mov     edx, 0DEh; void *
0x18000a17d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a182  mov     rcx, rdi; hObject
0x18000a185  call    cs:__imp_CloseHandle
0x18000a18b  test    eax, eax
0x18000a18d  jz      loc_18000A288
0x18000a193  mov     rcx, rbx; hObject
0x18000a196  call    cs:__imp_CloseHandle
0x18000a19c  test    eax, eax
0x18000a19e  jz      loc_18000A29A
0x18000a1a4  mov     eax, esi
0x18000a1a6  jmp     short loc_18000A221
0x18000a1a8  mov     rcx, rdi; hObject
0x18000a1ab  call    cs:__imp_CloseHandle
0x18000a1b1  test    eax, eax
0x18000a1b3  jz      loc_18000A240
0x18000a1b9  movsxd  rax, [rsp+280h+var_25C]
0x18000a1be  movsxd  rcx, [rsp+280h+var_260]
0x18000a1c3  shl     rcx, 1Fh
0x18000a1c7  or      rcx, rax
0x18000a1ca  mov     [r14], rcx
0x18000a1cd  mov     rcx, rbx; hObject
0x18000a1d0  call    cs:__imp_CloseHandle
0x18000a1d6  test    eax, eax
0x18000a1d8  jz      short loc_18000A252
0x18000a1da  jmp     short loc_18000A20C
0x18000a1dc  mov     rcx, [rbp+188h]; this
0x18000a1e3  mov     edx, 0DCh; void *
0x18000a1e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a1ed  mov     rcx, rbx; hObject
0x18000a1f0  mov     edi, eax
0x18000a1f2  call    cs:__imp_CloseHandle
0x18000a1f8  test    eax, eax
0x18000a1fa  jz      short loc_18000A264
0x18000a1fc  jmp     loc_18000A128
0x18000a201  call    cs:__imp_GetLastError
0x18000a207  cmp     eax, 2
0x18000a20a  jnz     short loc_18000A210
0x18000a20c  xor     eax, eax
0x18000a20e  jmp     short loc_18000A221
0x18000a210  mov     rcx, [rbp+188h]; this
0x18000a217  mov     edx, 0D0h; void *
0x18000a21c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a221  mov     rcx, [rbp+180h+var_40]
0x18000a228  xor     rcx, rsp; StackCookie
0x18000a22b  call    __security_check_cookie
0x18000a230  add     rsp, 258h
0x18000a237  pop     r15
0x18000a239  pop     r14
0x18000a23b  pop     rdi
0x18000a23c  pop     rsi
0x18000a23d  pop     rbx
0x18000a23e  pop     rbp
0x18000a23f  retn
0x18000a240  mov     rcx, [rbp+188h]; this
0x18000a247  mov     edx, 0A0Bh; void *
0x18000a24c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a252  mov     rcx, [rbp+188h]; this
0x18000a259  mov     edx, 0A0Bh; void *
0x18000a25e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a264  mov     rcx, [rbp+188h]; this
0x18000a26b  mov     edx, 0A0Bh; void *
0x18000a270  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a276  mov     rcx, [rbp+188h]; this
0x18000a27d  mov     edx, 0A0Bh; void *
0x18000a282  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a288  mov     rcx, [rbp+188h]; this
0x18000a28f  mov     edx, 0A0Bh; void *
0x18000a294  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000a29a  mov     rcx, [rbp+188h]; this
0x18000a2a1  mov     edx, 0A0Bh; void *
0x18000a2a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
