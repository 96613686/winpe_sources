# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000c81c`
- end: `0x14000caab`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `655`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140008f9c`
- `0x14000936c`

## callees

- `0x1400023d0`
- `0x14000a828`
- `0x14000c168`
- `0x14000c188`
- `0x14000c4d0`
- `0x14000c81c`
- `0x14000db34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c9f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c8fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c9bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c9ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c8fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c96f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c980`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c9bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c9ea`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c8b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c92c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c8b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000c92c`

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
0x14000c81c  push    rbp
0x14000c81e  push    rbx
0x14000c81f  push    rsi
0x14000c820  push    rdi
0x14000c821  push    r14
0x14000c823  push    r15
0x14000c825  lea     rbp, [rsp-158h]
0x14000c82d  sub     rsp, 258h
0x14000c834  mov     rax, cs:__security_cookie
0x14000c83b  xor     rax, rsp
0x14000c83e  mov     [rbp+180h+var_40], rax
0x14000c845  xor     r15d, r15d
0x14000c848  lea     rax, [rsp+280h+Name]
0x14000c84d  mov     [r8], r15
0x14000c850  mov     r14, r8
0x14000c853  mov     edx, 104h
0x14000c858  mov     r9d, 7FFFFFFEh
0x14000c85e  test    r9, r9
0x14000c861  jz      short loc_14000C882
0x14000c863  movzx   r8d, word ptr [rcx]
0x14000c867  test    r8w, r8w
0x14000c86b  jz      short loc_14000C882
0x14000c86d  mov     [rax], r8w
0x14000c871  add     rcx, 2
0x14000c875  add     rax, 2
0x14000c879  dec     r9
0x14000c87c  sub     rdx, 1; unsigned __int64
0x14000c880  jnz     short loc_14000C85E
0x14000c882  test    rdx, rdx
0x14000c885  lea     rcx, [rax-2]
0x14000c889  lea     r8, aP0; "_p0"
0x14000c890  cmovnz  rcx, rax
0x14000c894  mov     [rcx], r15w
0x14000c898  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000c89d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000c8a2  mov     esi, 1F0003h
0x14000c8a7  lea     r8, [rsp+280h+Name]; lpName
0x14000c8ac  mov     ecx, esi; dwDesiredAccess
0x14000c8ae  xor     edx, edx; bInheritHandle
0x14000c8b0  call    cs:__imp_OpenSemaphoreW
0x14000c8b6  mov     rbx, rax
0x14000c8b9  test    rax, rax
0x14000c8bc  jz      loc_14000C9F9
0x14000c8c2  lea     rdx, [rsp+280h+var_25C]; int *
0x14000c8c7  mov     [rsp+280h+var_25C], r15d
0x14000c8cc  mov     rcx, rax; hHandle
0x14000c8cf  mov     [rsp+280h+var_260], r15d; int
0x14000c8d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c8d9  mov     edi, eax
0x14000c8db  test    eax, eax
0x14000c8dd  jns     short loc_14000C912
0x14000c8df  mov     rcx, [rbp+188h]; this
0x14000c8e6  lea     r8, aWil; "wil"
0x14000c8ed  mov     r9d, eax; char *
0x14000c8f0  mov     edx, 0D6h; void *
0x14000c8f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c8fa  mov     rcx, rbx; hObject
0x14000c8fd  call    cs:__imp_CloseHandle
0x14000c903  test    eax, eax
0x14000c905  jz      loc_14000CA75
0x14000c90b  mov     eax, edi
0x14000c90d  jmp     loc_14000CA20
0x14000c912  lea     r8, asc_140014C78; "h"
0x14000c919  lea     rcx, [rsp+280h+Name]; wchar_t *
0x14000c91e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000c923  lea     r8, [rsp+280h+Name]; lpName
0x14000c928  xor     edx, edx; bInheritHandle
0x14000c92a  mov     ecx, esi; dwDesiredAccess
0x14000c92c  call    cs:__imp_OpenSemaphoreW
0x14000c932  mov     rdi, rax
0x14000c935  test    rax, rax
0x14000c938  jz      loc_14000C9CD
0x14000c93e  lea     rdx, [rsp+280h+var_260]; int *
0x14000c943  mov     rcx, rax; hHandle
0x14000c946  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c94b  mov     esi, eax
0x14000c94d  test    eax, eax
0x14000c94f  jns     short loc_14000C995
0x14000c951  mov     rcx, [rbp+188h]; this
0x14000c958  lea     r8, aWil; "wil"
0x14000c95f  mov     r9d, eax; char *
0x14000c962  mov     edx, 0DEh; void *
0x14000c967  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c96c  mov     rcx, rdi; hObject
0x14000c96f  call    cs:__imp_CloseHandle
0x14000c975  test    eax, eax
0x14000c977  jz      loc_14000CA87
0x14000c97d  mov     rcx, rbx; hObject
0x14000c980  call    cs:__imp_CloseHandle
0x14000c986  test    eax, eax
0x14000c988  jz      loc_14000CA99
0x14000c98e  mov     eax, esi
0x14000c990  jmp     loc_14000CA20
0x14000c995  mov     rcx, rdi; hObject
0x14000c998  call    cs:__imp_CloseHandle
0x14000c99e  test    eax, eax
0x14000c9a0  jz      loc_14000CA3F
0x14000c9a6  movsxd  rax, [rsp+280h+var_25C]
0x14000c9ab  movsxd  rcx, [rsp+280h+var_260]
0x14000c9b0  shl     rcx, 1Fh
0x14000c9b4  or      rcx, rax
0x14000c9b7  mov     [r14], rcx
0x14000c9ba  mov     rcx, rbx; hObject
0x14000c9bd  call    cs:__imp_CloseHandle
0x14000c9c3  test    eax, eax
0x14000c9c5  jz      loc_14000CA51
0x14000c9cb  jmp     short loc_14000CA04
0x14000c9cd  mov     rcx, [rbp+188h]; this
0x14000c9d4  lea     r8, aWil; "wil"
0x14000c9db  mov     edx, 0DCh; void *
0x14000c9e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c9e5  mov     rcx, rbx; hObject
0x14000c9e8  mov     edi, eax
0x14000c9ea  call    cs:__imp_CloseHandle
0x14000c9f0  test    eax, eax
0x14000c9f2  jz      short loc_14000CA63
0x14000c9f4  jmp     loc_14000C90B
0x14000c9f9  call    cs:__imp_GetLastError
0x14000c9ff  cmp     eax, 2
0x14000ca02  jnz     short loc_14000CA08
0x14000ca04  xor     eax, eax
0x14000ca06  jmp     short loc_14000CA20
0x14000ca08  mov     rcx, [rbp+188h]; this
0x14000ca0f  lea     r8, aWil; "wil"
0x14000ca16  mov     edx, 0D0h; void *
0x14000ca1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000ca20  mov     rcx, [rbp+180h+var_40]
0x14000ca27  xor     rcx, rsp; StackCookie
0x14000ca2a  call    __security_check_cookie
0x14000ca2f  add     rsp, 258h
0x14000ca36  pop     r15
0x14000ca38  pop     r14
0x14000ca3a  pop     rdi
0x14000ca3b  pop     rsi
0x14000ca3c  pop     rbx
0x14000ca3d  pop     rbp
0x14000ca3e  retn
0x14000ca3f  mov     rcx, [rbp+188h]; this
0x14000ca46  mov     edx, 0A0Bh; void *
0x14000ca4b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ca51  mov     rcx, [rbp+188h]; this
0x14000ca58  mov     edx, 0A0Bh; void *
0x14000ca5d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ca63  mov     rcx, [rbp+188h]; this
0x14000ca6a  mov     edx, 0A0Bh; void *
0x14000ca6f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ca75  mov     rcx, [rbp+188h]; this
0x14000ca7c  mov     edx, 0A0Bh; void *
0x14000ca81  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ca87  mov     rcx, [rbp+188h]; this
0x14000ca8e  mov     edx, 0A0Bh; void *
0x14000ca93  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000ca99  mov     rcx, [rbp+188h]; this
0x14000caa0  mov     edx, 0A0Bh; void *
0x14000caa5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
