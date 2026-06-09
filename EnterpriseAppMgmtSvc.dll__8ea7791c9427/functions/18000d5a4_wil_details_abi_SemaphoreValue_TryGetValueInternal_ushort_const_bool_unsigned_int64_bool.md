# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000d5a4`
- end: `0x18000d83c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a3b8`
- `0x1800298b4`

## callees

- `0x18000b378`
- `0x18000cfc8`
- `0x18000cfe8`
- `0x18000d11c`
- `0x18000d5a4`
- `0x18000e248`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d78a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d77b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d700`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d77b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d63b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d6bd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d63b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000d6bd`

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
0x18000d5a4  push    rbp
0x18000d5a6  push    rbx
0x18000d5a7  push    rsi
0x18000d5a8  push    rdi
0x18000d5a9  push    r14
0x18000d5ab  push    r15
0x18000d5ad  lea     rbp, [rsp-158h]
0x18000d5b5  sub     rsp, 258h
0x18000d5bc  mov     rax, cs:__security_cookie
0x18000d5c3  xor     rax, rsp
0x18000d5c6  mov     [rbp+180h+var_40], rax
0x18000d5cd  xor     r15d, r15d
0x18000d5d0  lea     rax, [rsp+280h+Name]
0x18000d5d5  mov     esi, 104h
0x18000d5da  mov     [r8], r15
0x18000d5dd  mov     edx, esi
0x18000d5df  mov     r14, r8
0x18000d5e2  mov     r9d, 7FFFFFFEh
0x18000d5e8  test    r9, r9
0x18000d5eb  jz      short loc_18000D60C
0x18000d5ed  movzx   r8d, word ptr [rcx]
0x18000d5f1  test    r8w, r8w
0x18000d5f5  jz      short loc_18000D60C
0x18000d5f7  mov     [rax], r8w
0x18000d5fb  add     rcx, 2
0x18000d5ff  add     rax, 2
0x18000d603  dec     r9
0x18000d606  sub     rdx, 1
0x18000d60a  jnz     short loc_18000D5E8
0x18000d60c  test    rdx, rdx
0x18000d60f  lea     rcx, [rax-2]
0x18000d613  lea     r8, aP0; "_p0"
0x18000d61a  mov     rdx, rsi; unsigned __int64
0x18000d61d  cmovnz  rcx, rax
0x18000d621  mov     [rcx], r15w
0x18000d625  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d62a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d62f  lea     r8, [rsp+280h+Name]; lpName
0x18000d634  xor     edx, edx; bInheritHandle
0x18000d636  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d63b  call    cs:__imp_OpenSemaphoreW
0x18000d641  mov     rbx, rax
0x18000d644  test    rax, rax
0x18000d647  jz      loc_18000D78A
0x18000d64d  lea     rdx, [rsp+280h+var_25C]; int *
0x18000d652  mov     [rsp+280h+var_25C], r15d
0x18000d657  mov     rcx, rax; hHandle
0x18000d65a  mov     [rsp+280h+var_260], r15d; int
0x18000d65f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d664  mov     edi, eax
0x18000d666  test    eax, eax
0x18000d668  jns     short loc_18000D69D
0x18000d66a  mov     rcx, [rbp+188h]; this
0x18000d671  lea     r8, aWil; "wil"
0x18000d678  mov     r9d, eax; char *
0x18000d67b  mov     edx, 0D6h; void *
0x18000d680  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d685  mov     rcx, rbx; hObject
0x18000d688  call    cs:__imp_CloseHandle
0x18000d68e  test    eax, eax
0x18000d690  jz      loc_18000D806
0x18000d696  mov     eax, edi
0x18000d698  jmp     loc_18000D7B1
0x18000d69d  lea     r8, asc_1800713B8; "h"
0x18000d6a4  mov     rdx, rsi; unsigned __int64
0x18000d6a7  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000d6ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d6b1  lea     r8, [rsp+280h+Name]; lpName
0x18000d6b6  xor     edx, edx; bInheritHandle
0x18000d6b8  mov     ecx, 1F0003h; dwDesiredAccess
0x18000d6bd  call    cs:__imp_OpenSemaphoreW
0x18000d6c3  mov     rdi, rax
0x18000d6c6  test    rax, rax
0x18000d6c9  jz      loc_18000D75E
0x18000d6cf  lea     rdx, [rsp+280h+var_260]; int *
0x18000d6d4  mov     rcx, rax; hHandle
0x18000d6d7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000d6dc  mov     esi, eax
0x18000d6de  test    eax, eax
0x18000d6e0  jns     short loc_18000D726
0x18000d6e2  mov     rcx, [rbp+188h]; this
0x18000d6e9  lea     r8, aWil; "wil"
0x18000d6f0  mov     r9d, eax; char *
0x18000d6f3  mov     edx, 0DEh; void *
0x18000d6f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d6fd  mov     rcx, rdi; hObject
0x18000d700  call    cs:__imp_CloseHandle
0x18000d706  test    eax, eax
0x18000d708  jz      loc_18000D818
0x18000d70e  mov     rcx, rbx; hObject
0x18000d711  call    cs:__imp_CloseHandle
0x18000d717  test    eax, eax
0x18000d719  jz      loc_18000D82A
0x18000d71f  mov     eax, esi
0x18000d721  jmp     loc_18000D7B1
0x18000d726  mov     rcx, rdi; hObject
0x18000d729  call    cs:__imp_CloseHandle
0x18000d72f  test    eax, eax
0x18000d731  jz      loc_18000D7D0
0x18000d737  movsxd  rax, [rsp+280h+var_25C]
0x18000d73c  movsxd  rcx, [rsp+280h+var_260]
0x18000d741  shl     rcx, 1Fh
0x18000d745  or      rcx, rax
0x18000d748  mov     [r14], rcx
0x18000d74b  mov     rcx, rbx; hObject
0x18000d74e  call    cs:__imp_CloseHandle
0x18000d754  test    eax, eax
0x18000d756  jz      loc_18000D7E2
0x18000d75c  jmp     short loc_18000D795
0x18000d75e  mov     rcx, [rbp+188h]; this
0x18000d765  lea     r8, aWil; "wil"
0x18000d76c  mov     edx, 0DCh; void *
0x18000d771  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d776  mov     rcx, rbx; hObject
0x18000d779  mov     edi, eax
0x18000d77b  call    cs:__imp_CloseHandle
0x18000d781  test    eax, eax
0x18000d783  jz      short loc_18000D7F4
0x18000d785  jmp     loc_18000D696
0x18000d78a  call    cs:__imp_GetLastError
0x18000d790  cmp     eax, 2
0x18000d793  jnz     short loc_18000D799
0x18000d795  xor     eax, eax
0x18000d797  jmp     short loc_18000D7B1
0x18000d799  mov     rcx, [rbp+188h]; this
0x18000d7a0  lea     r8, aWil; "wil"
0x18000d7a7  mov     edx, 0D0h; void *
0x18000d7ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000d7b1  mov     rcx, [rbp+180h+var_40]
0x18000d7b8  xor     rcx, rsp; StackCookie
0x18000d7bb  call    __security_check_cookie
0x18000d7c0  add     rsp, 258h
0x18000d7c7  pop     r15
0x18000d7c9  pop     r14
0x18000d7cb  pop     rdi
0x18000d7cc  pop     rsi
0x18000d7cd  pop     rbx
0x18000d7ce  pop     rbp
0x18000d7cf  retn
0x18000d7d0  mov     rcx, [rbp+188h]; this
0x18000d7d7  mov     edx, 0A0Bh; void *
0x18000d7dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d7e2  mov     rcx, [rbp+188h]; this
0x18000d7e9  mov     edx, 0A0Bh; void *
0x18000d7ee  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d7f4  mov     rcx, [rbp+188h]; this
0x18000d7fb  mov     edx, 0A0Bh; void *
0x18000d800  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d806  mov     rcx, [rbp+188h]; this
0x18000d80d  mov     edx, 0A0Bh; void *
0x18000d812  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d818  mov     rcx, [rbp+188h]; this
0x18000d81f  mov     edx, 0A0Bh; void *
0x18000d824  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000d82a  mov     rcx, [rbp+188h]; this
0x18000d831  mov     edx, 0A0Bh; void *
0x18000d836  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
