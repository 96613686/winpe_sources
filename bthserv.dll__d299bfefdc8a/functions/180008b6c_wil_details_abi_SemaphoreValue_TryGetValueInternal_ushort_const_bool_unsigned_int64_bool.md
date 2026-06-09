# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008b6c`
- end: `0x180008dfb`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004148`
- `0x18000451c`

## callees

- `0x180001790`
- `0x180005ab4`
- `0x180007bc4`
- `0x180007be4`
- `0x180008628`
- `0x180008b6c`
- `0x18000944c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c7c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008cd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008d3a`

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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
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
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v20);
  if ( !CloseHandle(v19) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v22, v23);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  return v21;
}

```

## disassembly

```asm
0x180008b6c  push    rbp
0x180008b6e  push    rbx
0x180008b6f  push    rsi
0x180008b70  push    rdi
0x180008b71  push    r14
0x180008b73  push    r15
0x180008b75  lea     rbp, [rsp-158h]
0x180008b7d  sub     rsp, 258h
0x180008b84  mov     rax, cs:__security_cookie
0x180008b8b  xor     rax, rsp
0x180008b8e  mov     [rbp+180h+var_40], rax
0x180008b95  xor     r15d, r15d
0x180008b98  lea     rax, [rsp+280h+Name]
0x180008b9d  mov     [r8], r15
0x180008ba0  mov     r14, r8
0x180008ba3  mov     edx, 104h
0x180008ba8  mov     r9d, 7FFFFFFEh
0x180008bae  test    r9, r9
0x180008bb1  jz      short loc_180008BD2
0x180008bb3  movzx   r8d, word ptr [rcx]
0x180008bb7  test    r8w, r8w
0x180008bbb  jz      short loc_180008BD2
0x180008bbd  mov     [rax], r8w
0x180008bc1  add     rcx, 2
0x180008bc5  add     rax, 2
0x180008bc9  dec     r9
0x180008bcc  sub     rdx, 1; unsigned __int64
0x180008bd0  jnz     short loc_180008BAE
0x180008bd2  test    rdx, rdx
0x180008bd5  lea     rcx, [rax-2]
0x180008bd9  lea     r8, aP0; "_p0"
0x180008be0  cmovnz  rcx, rax
0x180008be4  mov     [rcx], r15w
0x180008be8  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008bed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008bf2  mov     esi, 1F0003h
0x180008bf7  lea     r8, [rsp+280h+Name]; lpName
0x180008bfc  mov     ecx, esi; dwDesiredAccess
0x180008bfe  xor     edx, edx; bInheritHandle
0x180008c00  call    cs:__imp_OpenSemaphoreW
0x180008c06  mov     rbx, rax
0x180008c09  test    rax, rax
0x180008c0c  jz      loc_180008D49
0x180008c12  lea     rdx, [rsp+280h+var_25C]; int *
0x180008c17  mov     [rsp+280h+var_25C], r15d
0x180008c1c  mov     rcx, rax; hHandle
0x180008c1f  mov     [rsp+280h+var_260], r15d; int
0x180008c24  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008c29  mov     edi, eax
0x180008c2b  test    eax, eax
0x180008c2d  jns     short loc_180008C62
0x180008c2f  mov     rcx, [rbp+188h]; this
0x180008c36  lea     r8, aWil; "wil"
0x180008c3d  mov     r9d, eax; char *
0x180008c40  mov     edx, 0D6h; void *
0x180008c45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c4a  mov     rcx, rbx; hObject
0x180008c4d  call    cs:__imp_CloseHandle
0x180008c53  test    eax, eax
0x180008c55  jz      loc_180008DC5
0x180008c5b  mov     eax, edi
0x180008c5d  jmp     loc_180008D70
0x180008c62  lea     r8, asc_18003ACF8; "h"
0x180008c69  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180008c6e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008c73  lea     r8, [rsp+280h+Name]; lpName
0x180008c78  xor     edx, edx; bInheritHandle
0x180008c7a  mov     ecx, esi; dwDesiredAccess
0x180008c7c  call    cs:__imp_OpenSemaphoreW
0x180008c82  mov     rdi, rax
0x180008c85  test    rax, rax
0x180008c88  jz      loc_180008D1D
0x180008c8e  lea     rdx, [rsp+280h+var_260]; int *
0x180008c93  mov     rcx, rax; hHandle
0x180008c96  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008c9b  mov     esi, eax
0x180008c9d  test    eax, eax
0x180008c9f  jns     short loc_180008CE5
0x180008ca1  mov     rcx, [rbp+188h]; this
0x180008ca8  lea     r8, aWil; "wil"
0x180008caf  mov     r9d, eax; char *
0x180008cb2  mov     edx, 0DEh; void *
0x180008cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008cbc  mov     rcx, rdi; hObject
0x180008cbf  call    cs:__imp_CloseHandle
0x180008cc5  test    eax, eax
0x180008cc7  jz      loc_180008DD7
0x180008ccd  mov     rcx, rbx; hObject
0x180008cd0  call    cs:__imp_CloseHandle
0x180008cd6  test    eax, eax
0x180008cd8  jz      loc_180008DE9
0x180008cde  mov     eax, esi
0x180008ce0  jmp     loc_180008D70
0x180008ce5  mov     rcx, rdi; hObject
0x180008ce8  call    cs:__imp_CloseHandle
0x180008cee  test    eax, eax
0x180008cf0  jz      loc_180008D8F
0x180008cf6  movsxd  rax, [rsp+280h+var_25C]
0x180008cfb  movsxd  rcx, [rsp+280h+var_260]
0x180008d00  shl     rcx, 1Fh
0x180008d04  or      rcx, rax
0x180008d07  mov     [r14], rcx
0x180008d0a  mov     rcx, rbx; hObject
0x180008d0d  call    cs:__imp_CloseHandle
0x180008d13  test    eax, eax
0x180008d15  jz      loc_180008DA1
0x180008d1b  jmp     short loc_180008D54
0x180008d1d  mov     rcx, [rbp+188h]; this
0x180008d24  lea     r8, aWil; "wil"
0x180008d2b  mov     edx, 0DCh; void *
0x180008d30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008d35  mov     rcx, rbx; hObject
0x180008d38  mov     edi, eax
0x180008d3a  call    cs:__imp_CloseHandle
0x180008d40  test    eax, eax
0x180008d42  jz      short loc_180008DB3
0x180008d44  jmp     loc_180008C5B
0x180008d49  call    cs:__imp_GetLastError
0x180008d4f  cmp     eax, 2
0x180008d52  jnz     short loc_180008D58
0x180008d54  xor     eax, eax
0x180008d56  jmp     short loc_180008D70
0x180008d58  mov     rcx, [rbp+188h]; this
0x180008d5f  lea     r8, aWil; "wil"
0x180008d66  mov     edx, 0D0h; void *
0x180008d6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008d70  mov     rcx, [rbp+180h+var_40]
0x180008d77  xor     rcx, rsp; StackCookie
0x180008d7a  call    __security_check_cookie
0x180008d7f  add     rsp, 258h
0x180008d86  pop     r15
0x180008d88  pop     r14
0x180008d8a  pop     rdi
0x180008d8b  pop     rsi
0x180008d8c  pop     rbx
0x180008d8d  pop     rbp
0x180008d8e  retn
0x180008d8f  mov     rcx, [rbp+188h]; this
0x180008d96  mov     edx, 0A0Bh; void *
0x180008d9b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008da1  mov     rcx, [rbp+188h]; this
0x180008da8  mov     edx, 0A0Bh; void *
0x180008dad  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008db3  mov     rcx, [rbp+188h]; this
0x180008dba  mov     edx, 0A0Bh; void *
0x180008dbf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008dc5  mov     rcx, [rbp+188h]; this
0x180008dcc  mov     edx, 0A0Bh; void *
0x180008dd1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008dd7  mov     rcx, [rbp+188h]; this
0x180008dde  mov     edx, 0A0Bh; void *
0x180008de3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008de9  mov     rcx, [rbp+188h]; this
0x180008df0  mov     edx, 0A0Bh; void *
0x180008df5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
