# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006dbc`
- end: `0x180007028`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800042e8`

## callees

- `0x180002650`
- `0x180005428`
- `0x180006204`
- `0x180006224`
- `0x180006b00`
- `0x180006dbc`
- `0x18000717c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ec5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006e50`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6e`

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
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
0x180006dbc  push    rbp
0x180006dbe  push    rbx
0x180006dbf  push    rsi
0x180006dc0  push    rdi
0x180006dc1  push    r14
0x180006dc3  push    r15
0x180006dc5  lea     rbp, [rsp-158h]
0x180006dcd  sub     rsp, 258h
0x180006dd4  mov     rax, cs:__security_cookie
0x180006ddb  xor     rax, rsp
0x180006dde  mov     [rbp+180h+var_40], rax
0x180006de5  xor     r15d, r15d
0x180006de8  lea     rax, [rsp+280h+Name]
0x180006ded  mov     [r8], r15
0x180006df0  mov     r14, r8
0x180006df3  mov     edx, 104h
0x180006df8  mov     r9d, 7FFFFFFEh
0x180006dfe  test    r9, r9
0x180006e01  jz      short loc_180006E22
0x180006e03  movzx   r8d, word ptr [rcx]
0x180006e07  test    r8w, r8w
0x180006e0b  jz      short loc_180006E22
0x180006e0d  mov     [rax], r8w
0x180006e11  add     rcx, 2
0x180006e15  add     rax, 2
0x180006e19  dec     r9
0x180006e1c  sub     rdx, 1; unsigned __int64
0x180006e20  jnz     short loc_180006DFE
0x180006e22  test    rdx, rdx
0x180006e25  lea     rcx, [rax-2]
0x180006e29  lea     r8, aP0; "_p0"
0x180006e30  cmovnz  rcx, rax
0x180006e34  mov     [rcx], r15w
0x180006e38  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006e3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006e42  mov     esi, 1F0003h
0x180006e47  lea     r8, [rsp+280h+Name]; lpName
0x180006e4c  mov     ecx, esi; dwDesiredAccess
0x180006e4e  xor     edx, edx; bInheritHandle
0x180006e50  call    cs:__imp_OpenSemaphoreW
0x180006e56  mov     rbx, rax
0x180006e59  test    rax, rax
0x180006e5c  jz      loc_180006F7D
0x180006e62  lea     rdx, [rsp+280h+var_25C]; int *
0x180006e67  mov     [rsp+280h+var_25C], r15d
0x180006e6c  mov     rcx, rax; hHandle
0x180006e6f  mov     [rsp+280h+var_260], r15d; int
0x180006e74  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006e79  mov     edi, eax
0x180006e7b  test    eax, eax
0x180006e7d  jns     short loc_180006EAB
0x180006e7f  mov     rcx, [rbp+188h]; this
0x180006e86  mov     r9d, eax; char *
0x180006e89  mov     edx, 0D6h; void *
0x180006e8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e93  mov     rcx, rbx; hObject
0x180006e96  call    cs:__imp_CloseHandle
0x180006e9c  test    eax, eax
0x180006e9e  jz      loc_180006FF2
0x180006ea4  mov     eax, edi
0x180006ea6  jmp     loc_180006F9D
0x180006eab  lea     r8, asc_18000F0A8; "h"
0x180006eb2  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180006eb7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ebc  lea     r8, [rsp+280h+Name]; lpName
0x180006ec1  xor     edx, edx; bInheritHandle
0x180006ec3  mov     ecx, esi; dwDesiredAccess
0x180006ec5  call    cs:__imp_OpenSemaphoreW
0x180006ecb  mov     rdi, rax
0x180006ece  test    rax, rax
0x180006ed1  jz      loc_180006F58
0x180006ed7  lea     rdx, [rsp+280h+var_260]; int *
0x180006edc  mov     rcx, rax; hHandle
0x180006edf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006ee4  mov     esi, eax
0x180006ee6  test    eax, eax
0x180006ee8  jns     short loc_180006F24
0x180006eea  mov     rcx, [rbp+188h]; this
0x180006ef1  mov     r9d, eax; char *
0x180006ef4  mov     edx, 0DEh; void *
0x180006ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006efe  mov     rcx, rdi; hObject
0x180006f01  call    cs:__imp_CloseHandle
0x180006f07  test    eax, eax
0x180006f09  jz      loc_180007004
0x180006f0f  mov     rcx, rbx; hObject
0x180006f12  call    cs:__imp_CloseHandle
0x180006f18  test    eax, eax
0x180006f1a  jz      loc_180007016
0x180006f20  mov     eax, esi
0x180006f22  jmp     short loc_180006F9D
0x180006f24  mov     rcx, rdi; hObject
0x180006f27  call    cs:__imp_CloseHandle
0x180006f2d  test    eax, eax
0x180006f2f  jz      loc_180006FBC
0x180006f35  movsxd  rax, [rsp+280h+var_25C]
0x180006f3a  movsxd  rcx, [rsp+280h+var_260]
0x180006f3f  shl     rcx, 1Fh
0x180006f43  or      rcx, rax
0x180006f46  mov     [r14], rcx
0x180006f49  mov     rcx, rbx; hObject
0x180006f4c  call    cs:__imp_CloseHandle
0x180006f52  test    eax, eax
0x180006f54  jz      short loc_180006FCE
0x180006f56  jmp     short loc_180006F88
0x180006f58  mov     rcx, [rbp+188h]; this
0x180006f5f  mov     edx, 0DCh; void *
0x180006f64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f69  mov     rcx, rbx; hObject
0x180006f6c  mov     edi, eax
0x180006f6e  call    cs:__imp_CloseHandle
0x180006f74  test    eax, eax
0x180006f76  jz      short loc_180006FE0
0x180006f78  jmp     loc_180006EA4
0x180006f7d  call    cs:__imp_GetLastError
0x180006f83  cmp     eax, 2
0x180006f86  jnz     short loc_180006F8C
0x180006f88  xor     eax, eax
0x180006f8a  jmp     short loc_180006F9D
0x180006f8c  mov     rcx, [rbp+188h]; this
0x180006f93  mov     edx, 0D0h; void *
0x180006f98  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f9d  mov     rcx, [rbp+180h+var_40]
0x180006fa4  xor     rcx, rsp; StackCookie
0x180006fa7  call    __security_check_cookie
0x180006fac  add     rsp, 258h
0x180006fb3  pop     r15
0x180006fb5  pop     r14
0x180006fb7  pop     rdi
0x180006fb8  pop     rsi
0x180006fb9  pop     rbx
0x180006fba  pop     rbp
0x180006fbb  retn
0x180006fbc  mov     rcx, [rbp+188h]; this
0x180006fc3  mov     edx, 0A0Bh; void *
0x180006fc8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fce  mov     rcx, [rbp+188h]; this
0x180006fd5  mov     edx, 0A0Bh; void *
0x180006fda  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006fe0  mov     rcx, [rbp+188h]; this
0x180006fe7  mov     edx, 0A0Bh; void *
0x180006fec  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006ff2  mov     rcx, [rbp+188h]; this
0x180006ff9  mov     edx, 0A0Bh; void *
0x180006ffe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007004  mov     rcx, [rbp+188h]; this
0x18000700b  mov     edx, 0A0Bh; void *
0x180007010  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007016  mov     rcx, [rbp+188h]; this
0x18000701d  mov     edx, 0A0Bh; void *
0x180007022  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
