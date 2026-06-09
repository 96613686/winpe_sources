# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c71c`
- end: `0x18000c9ab`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180009f58`
- `0x180011864`

## callees

- `0x1800050a0`
- `0x18000b038`
- `0x18000bbb4`
- `0x18000bbd4`
- `0x18000c514`
- `0x18000c71c`
- `0x18000cbb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c7b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c82c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c7b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c82c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c8f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c86f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c86f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c880`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c8ea`

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
0x18000c71c  push    rbp
0x18000c71e  push    rbx
0x18000c71f  push    rsi
0x18000c720  push    rdi
0x18000c721  push    r14
0x18000c723  push    r15
0x18000c725  lea     rbp, [rsp-158h]
0x18000c72d  sub     rsp, 258h
0x18000c734  mov     rax, cs:__security_cookie
0x18000c73b  xor     rax, rsp
0x18000c73e  mov     [rbp+180h+var_40], rax
0x18000c745  xor     r15d, r15d
0x18000c748  lea     rax, [rsp+280h+Name]
0x18000c74d  mov     [r8], r15
0x18000c750  mov     r14, r8
0x18000c753  mov     edx, 104h
0x18000c758  mov     r9d, 7FFFFFFEh
0x18000c75e  test    r9, r9
0x18000c761  jz      short loc_18000C782
0x18000c763  movzx   r8d, word ptr [rcx]
0x18000c767  test    r8w, r8w
0x18000c76b  jz      short loc_18000C782
0x18000c76d  mov     [rax], r8w
0x18000c771  add     rcx, 2
0x18000c775  add     rax, 2
0x18000c779  dec     r9
0x18000c77c  sub     rdx, 1; unsigned __int64
0x18000c780  jnz     short loc_18000C75E
0x18000c782  test    rdx, rdx
0x18000c785  lea     rcx, [rax-2]
0x18000c789  lea     r8, aP0; "_p0"
0x18000c790  cmovnz  rcx, rax
0x18000c794  mov     [rcx], r15w
0x18000c798  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c79d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c7a2  mov     esi, 1F0003h
0x18000c7a7  lea     r8, [rsp+280h+Name]; lpName
0x18000c7ac  mov     ecx, esi; dwDesiredAccess
0x18000c7ae  xor     edx, edx; bInheritHandle
0x18000c7b0  call    cs:__imp_OpenSemaphoreW
0x18000c7b6  mov     rbx, rax
0x18000c7b9  test    rax, rax
0x18000c7bc  jz      loc_18000C8F9
0x18000c7c2  lea     rdx, [rsp+280h+var_25C]; int *
0x18000c7c7  mov     [rsp+280h+var_25C], r15d
0x18000c7cc  mov     rcx, rax; hHandle
0x18000c7cf  mov     [rsp+280h+var_260], r15d; int
0x18000c7d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c7d9  mov     edi, eax
0x18000c7db  test    eax, eax
0x18000c7dd  jns     short loc_18000C812
0x18000c7df  mov     rcx, [rbp+188h]; this
0x18000c7e6  lea     r8, aWil; "wil"
0x18000c7ed  mov     r9d, eax; char *
0x18000c7f0  mov     edx, 0D6h; void *
0x18000c7f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c7fa  mov     rcx, rbx; hObject
0x18000c7fd  call    cs:__imp_CloseHandle
0x18000c803  test    eax, eax
0x18000c805  jz      loc_18000C975
0x18000c80b  mov     eax, edi
0x18000c80d  jmp     loc_18000C920
0x18000c812  lea     r8, asc_180072ED0; "h"
0x18000c819  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000c81e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c823  lea     r8, [rsp+280h+Name]; lpName
0x18000c828  xor     edx, edx; bInheritHandle
0x18000c82a  mov     ecx, esi; dwDesiredAccess
0x18000c82c  call    cs:__imp_OpenSemaphoreW
0x18000c832  mov     rdi, rax
0x18000c835  test    rax, rax
0x18000c838  jz      loc_18000C8CD
0x18000c83e  lea     rdx, [rsp+280h+var_260]; int *
0x18000c843  mov     rcx, rax; hHandle
0x18000c846  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c84b  mov     esi, eax
0x18000c84d  test    eax, eax
0x18000c84f  jns     short loc_18000C895
0x18000c851  mov     rcx, [rbp+188h]; this
0x18000c858  lea     r8, aWil; "wil"
0x18000c85f  mov     r9d, eax; char *
0x18000c862  mov     edx, 0DEh; void *
0x18000c867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c86c  mov     rcx, rdi; hObject
0x18000c86f  call    cs:__imp_CloseHandle
0x18000c875  test    eax, eax
0x18000c877  jz      loc_18000C987
0x18000c87d  mov     rcx, rbx; hObject
0x18000c880  call    cs:__imp_CloseHandle
0x18000c886  test    eax, eax
0x18000c888  jz      loc_18000C999
0x18000c88e  mov     eax, esi
0x18000c890  jmp     loc_18000C920
0x18000c895  mov     rcx, rdi; hObject
0x18000c898  call    cs:__imp_CloseHandle
0x18000c89e  test    eax, eax
0x18000c8a0  jz      loc_18000C93F
0x18000c8a6  movsxd  rax, [rsp+280h+var_25C]
0x18000c8ab  movsxd  rcx, [rsp+280h+var_260]
0x18000c8b0  shl     rcx, 1Fh
0x18000c8b4  or      rcx, rax
0x18000c8b7  mov     [r14], rcx
0x18000c8ba  mov     rcx, rbx; hObject
0x18000c8bd  call    cs:__imp_CloseHandle
0x18000c8c3  test    eax, eax
0x18000c8c5  jz      loc_18000C951
0x18000c8cb  jmp     short loc_18000C904
0x18000c8cd  mov     rcx, [rbp+188h]; this
0x18000c8d4  lea     r8, aWil; "wil"
0x18000c8db  mov     edx, 0DCh; void *
0x18000c8e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c8e5  mov     rcx, rbx; hObject
0x18000c8e8  mov     edi, eax
0x18000c8ea  call    cs:__imp_CloseHandle
0x18000c8f0  test    eax, eax
0x18000c8f2  jz      short loc_18000C963
0x18000c8f4  jmp     loc_18000C80B
0x18000c8f9  call    cs:__imp_GetLastError
0x18000c8ff  cmp     eax, 2
0x18000c902  jnz     short loc_18000C908
0x18000c904  xor     eax, eax
0x18000c906  jmp     short loc_18000C920
0x18000c908  mov     rcx, [rbp+188h]; this
0x18000c90f  lea     r8, aWil; "wil"
0x18000c916  mov     edx, 0D0h; void *
0x18000c91b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c920  mov     rcx, [rbp+180h+var_40]
0x18000c927  xor     rcx, rsp; StackCookie
0x18000c92a  call    __security_check_cookie
0x18000c92f  add     rsp, 258h
0x18000c936  pop     r15
0x18000c938  pop     r14
0x18000c93a  pop     rdi
0x18000c93b  pop     rsi
0x18000c93c  pop     rbx
0x18000c93d  pop     rbp
0x18000c93e  retn
0x18000c93f  mov     rcx, [rbp+188h]; this
0x18000c946  mov     edx, 0A0Bh; void *
0x18000c94b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c951  mov     rcx, [rbp+188h]; this
0x18000c958  mov     edx, 0A0Bh; void *
0x18000c95d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c963  mov     rcx, [rbp+188h]; this
0x18000c96a  mov     edx, 0A0Bh; void *
0x18000c96f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c975  mov     rcx, [rbp+188h]; this
0x18000c97c  mov     edx, 0A0Bh; void *
0x18000c981  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c987  mov     rcx, [rbp+188h]; this
0x18000c98e  mov     edx, 0A0Bh; void *
0x18000c993  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000c999  mov     rcx, [rbp+188h]; this
0x18000c9a0  mov     edx, 0A0Bh; void *
0x18000c9a5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
