# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000a1dc`
- end: `0x14000a474`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400074e8`
- `0x14000d1ac`

## callees

- `0x1400042f0`
- `0x140008724`
- `0x140009594`
- `0x1400095b4`
- `0x140009fc4`
- `0x14000a1dc`
- `0x14000a6a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a273`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a2f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a273`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000a2f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a3c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a3c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a2c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a386`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a3b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a2c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a349`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a361`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a386`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a3b3`

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
  __int64 v13; // r8
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  __int64 v29; // r8
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
0x14000a1dc  push    rbp
0x14000a1de  push    rbx
0x14000a1df  push    rsi
0x14000a1e0  push    rdi
0x14000a1e1  push    r14
0x14000a1e3  push    r15
0x14000a1e5  lea     rbp, [rsp-158h]
0x14000a1ed  sub     rsp, 258h
0x14000a1f4  mov     rax, cs:__security_cookie
0x14000a1fb  xor     rax, rsp
0x14000a1fe  mov     [rbp+180h+var_40], rax
0x14000a205  xor     r15d, r15d
0x14000a208  lea     rax, [rsp+280h+Name]
0x14000a20d  mov     esi, 104h
0x14000a212  mov     [r8], r15
0x14000a215  mov     edx, esi
0x14000a217  mov     r14, r8
0x14000a21a  mov     r9d, 7FFFFFFEh
0x14000a220  test    r9, r9
0x14000a223  jz      short loc_14000A244
0x14000a225  movzx   r8d, word ptr [rcx]
0x14000a229  test    r8w, r8w
0x14000a22d  jz      short loc_14000A244
0x14000a22f  mov     [rax], r8w
0x14000a233  add     rcx, 2
0x14000a237  add     rax, 2
0x14000a23b  dec     r9
0x14000a23e  sub     rdx, 1
0x14000a242  jnz     short loc_14000A220
0x14000a244  test    rdx, rdx
0x14000a247  lea     rcx, [rax-2]
0x14000a24b  lea     r8, aP0; "_p0"
0x14000a252  mov     rdx, rsi; unsigned __int64
0x14000a255  cmovnz  rcx, rax
0x14000a259  mov     [rcx], r15w
0x14000a25d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000a262  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a267  lea     r8, [rsp+280h+Name]; lpName
0x14000a26c  xor     edx, edx; bInheritHandle
0x14000a26e  mov     ecx, 1F0003h; dwDesiredAccess
0x14000a273  call    cs:__imp_OpenSemaphoreW
0x14000a279  mov     rbx, rax
0x14000a27c  test    rax, rax
0x14000a27f  jz      loc_14000A3C2
0x14000a285  lea     rdx, [rsp+280h+var_25C]; int *
0x14000a28a  mov     [rsp+280h+var_25C], r15d
0x14000a28f  mov     rcx, rax; hHandle
0x14000a292  mov     [rsp+280h+var_260], r15d; int
0x14000a297  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000a29c  mov     edi, eax
0x14000a29e  test    eax, eax
0x14000a2a0  jns     short loc_14000A2D5
0x14000a2a2  mov     rcx, [rbp+188h]; this
0x14000a2a9  lea     r8, aWil; "wil"
0x14000a2b0  mov     r9d, eax; char *
0x14000a2b3  mov     edx, 0D6h; void *
0x14000a2b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a2bd  mov     rcx, rbx; hObject
0x14000a2c0  call    cs:__imp_CloseHandle
0x14000a2c6  test    eax, eax
0x14000a2c8  jz      loc_14000A43E
0x14000a2ce  mov     eax, edi
0x14000a2d0  jmp     loc_14000A3E9
0x14000a2d5  lea     r8, asc_140060F00; "h"
0x14000a2dc  mov     rdx, rsi; unsigned __int64
0x14000a2df  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000a2e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a2e9  lea     r8, [rsp+280h+Name]; lpName
0x14000a2ee  xor     edx, edx; bInheritHandle
0x14000a2f0  mov     ecx, 1F0003h; dwDesiredAccess
0x14000a2f5  call    cs:__imp_OpenSemaphoreW
0x14000a2fb  mov     rdi, rax
0x14000a2fe  test    rax, rax
0x14000a301  jz      loc_14000A396
0x14000a307  lea     rdx, [rsp+280h+var_260]; int *
0x14000a30c  mov     rcx, rax; hHandle
0x14000a30f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000a314  mov     esi, eax
0x14000a316  test    eax, eax
0x14000a318  jns     short loc_14000A35E
0x14000a31a  mov     rcx, [rbp+188h]; this
0x14000a321  lea     r8, aWil; "wil"
0x14000a328  mov     r9d, eax; char *
0x14000a32b  mov     edx, 0DEh; void *
0x14000a330  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a335  mov     rcx, rdi; hObject
0x14000a338  call    cs:__imp_CloseHandle
0x14000a33e  test    eax, eax
0x14000a340  jz      loc_14000A450
0x14000a346  mov     rcx, rbx; hObject
0x14000a349  call    cs:__imp_CloseHandle
0x14000a34f  test    eax, eax
0x14000a351  jz      loc_14000A462
0x14000a357  mov     eax, esi
0x14000a359  jmp     loc_14000A3E9
0x14000a35e  mov     rcx, rdi; hObject
0x14000a361  call    cs:__imp_CloseHandle
0x14000a367  test    eax, eax
0x14000a369  jz      loc_14000A408
0x14000a36f  movsxd  rax, [rsp+280h+var_25C]
0x14000a374  movsxd  rcx, [rsp+280h+var_260]
0x14000a379  shl     rcx, 1Fh
0x14000a37d  or      rcx, rax
0x14000a380  mov     [r14], rcx
0x14000a383  mov     rcx, rbx; hObject
0x14000a386  call    cs:__imp_CloseHandle
0x14000a38c  test    eax, eax
0x14000a38e  jz      loc_14000A41A
0x14000a394  jmp     short loc_14000A3CD
0x14000a396  mov     rcx, [rbp+188h]; this
0x14000a39d  lea     r8, aWil; "wil"
0x14000a3a4  mov     edx, 0DCh; void *
0x14000a3a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a3ae  mov     rcx, rbx; hObject
0x14000a3b1  mov     edi, eax
0x14000a3b3  call    cs:__imp_CloseHandle
0x14000a3b9  test    eax, eax
0x14000a3bb  jz      short loc_14000A42C
0x14000a3bd  jmp     loc_14000A2CE
0x14000a3c2  call    cs:__imp_GetLastError
0x14000a3c8  cmp     eax, 2
0x14000a3cb  jnz     short loc_14000A3D1
0x14000a3cd  xor     eax, eax
0x14000a3cf  jmp     short loc_14000A3E9
0x14000a3d1  mov     rcx, [rbp+188h]; this
0x14000a3d8  lea     r8, aWil; "wil"
0x14000a3df  mov     edx, 0D0h; void *
0x14000a3e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a3e9  mov     rcx, [rbp+180h+var_40]
0x14000a3f0  xor     rcx, rsp; StackCookie
0x14000a3f3  call    __security_check_cookie
0x14000a3f8  add     rsp, 258h
0x14000a3ff  pop     r15
0x14000a401  pop     r14
0x14000a403  pop     rdi
0x14000a404  pop     rsi
0x14000a405  pop     rbx
0x14000a406  pop     rbp
0x14000a407  retn
0x14000a408  mov     rcx, [rbp+188h]; this
0x14000a40f  mov     edx, 0A0Bh; void *
0x14000a414  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a41a  mov     rcx, [rbp+188h]; this
0x14000a421  mov     edx, 0A0Bh; void *
0x14000a426  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a42c  mov     rcx, [rbp+188h]; this
0x14000a433  mov     edx, 0A0Bh; void *
0x14000a438  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a43e  mov     rcx, [rbp+188h]; this
0x14000a445  mov     edx, 0A0Bh; void *
0x14000a44a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a450  mov     rcx, [rbp+188h]; this
0x14000a457  mov     edx, 0A0Bh; void *
0x14000a45c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a462  mov     rcx, [rbp+188h]; this
0x14000a469  mov     edx, 0A0Bh; void *
0x14000a46e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
