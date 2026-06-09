# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005d2c`
- end: `0x180005f6c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `576`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037a8`

## callees

- `0x180001960`
- `0x1800046b8`
- `0x180005284`
- `0x1800052a8`
- `0x180005b90`
- `0x180005d2c`
- `0x1800060cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005dbf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005e38`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005dbf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005e38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005eda`

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
  int v12; // r9d
  unsigned int LastError; // edi
  unsigned int v14; // edx
  const char *v15; // r8
  HANDLE v17; // rax
  unsigned int v18; // edx
  const char *v19; // r8
  void *v20; // rdi
  int v21; // eax
  int v22; // r9d
  unsigned int v23; // esi
  unsigned int v24; // edx
  const char *v25; // r8
  unsigned int v26; // edx
  const char *v27; // r8
  unsigned int v28; // edx
  const char *v29; // r8
  unsigned int v30; // edx
  const char *v31; // r8
  unsigned int v32; // edx
  const char *v33; // r8
  unsigned int v34; // edx
  const char *v35; // r8
  int v36; // [rsp+20h] [rbp-248h] BYREF
  int v37[3]; // [rsp+24h] [rbp-244h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF

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
      return wil::details::in1diag3::Return_GetLastError((wil::details::in1diag3 *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      (wil::details::in1diag3 *)0xD6,
      (unsigned int)"wil",
      (wil::details *)(unsigned int)ValueFromSemaphore,
      v12);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError((wil::details::in1diag3 *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    (wil::details::in1diag3 *)0xDE,
    (unsigned int)"wil",
    (wil::details *)(unsigned int)v21,
    v22);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError((wil::details::in1diag3 *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x180005d2c  mov     [rsp+arg_0], rbx
0x180005d31  mov     [rsp+arg_8], rbp
0x180005d36  push    rsi
0x180005d37  push    rdi
0x180005d38  push    r14
0x180005d3a  sub     rsp, 250h
0x180005d41  mov     rax, cs:__security_cookie
0x180005d48  xor     rax, rsp
0x180005d4b  mov     [rsp+268h+var_28], rax
0x180005d53  xor     ebp, ebp
0x180005d55  lea     rax, [rsp+268h+Name]
0x180005d5a  mov     esi, 104h
0x180005d5f  mov     [r8], rbp
0x180005d62  mov     edx, esi
0x180005d64  mov     r14, r8
0x180005d67  mov     r9d, 7FFFFFFEh
0x180005d6d  test    r9, r9
0x180005d70  jz      short loc_180005D91
0x180005d72  movzx   r8d, word ptr [rcx]
0x180005d76  test    r8w, r8w
0x180005d7a  jz      short loc_180005D91
0x180005d7c  mov     [rax], r8w
0x180005d80  add     rcx, 2
0x180005d84  add     rax, 2
0x180005d88  dec     r9
0x180005d8b  sub     rdx, 1
0x180005d8f  jnz     short loc_180005D6D
0x180005d91  test    rdx, rdx
0x180005d94  lea     rcx, [rax-2]
0x180005d98  lea     r8, aP0; "_p0"
0x180005d9f  mov     rdx, rsi; unsigned __int64
0x180005da2  cmovnz  rcx, rax
0x180005da6  mov     [rcx], bp
0x180005da9  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180005dae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005db3  lea     r8, [rsp+268h+Name]; lpName
0x180005db8  xor     edx, edx; bInheritHandle
0x180005dba  mov     ecx, 1F0003h; dwDesiredAccess
0x180005dbf  call    cs:__imp_OpenSemaphoreW
0x180005dc5  mov     rbx, rax
0x180005dc8  test    rax, rax
0x180005dcb  jz      loc_180005EE9
0x180005dd1  lea     rdx, [rsp+268h+var_244]; int *
0x180005dd6  mov     [rsp+268h+var_244], ebp
0x180005dda  mov     rcx, rax; hHandle
0x180005ddd  mov     [rsp+268h+var_248], ebp
0x180005de1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005de6  mov     edi, eax
0x180005de8  test    eax, eax
0x180005dea  jns     short loc_180005E18
0x180005dec  mov     r8d, eax; wil::details *
0x180005def  lea     rdx, aWil; "wil"
0x180005df6  mov     ecx, 0D6h; this
0x180005dfb  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180005e00  mov     rcx, rbx; hObject
0x180005e03  call    cs:__imp_CloseHandle
0x180005e09  test    eax, eax
0x180005e0b  jz      loc_180005F4B
0x180005e11  mov     eax, edi
0x180005e13  jmp     loc_180005F02
0x180005e18  lea     r8, asc_180015368; "h"
0x180005e1f  mov     rdx, rsi; unsigned __int64
0x180005e22  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180005e27  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005e2c  lea     r8, [rsp+268h+Name]; lpName
0x180005e31  xor     edx, edx; bInheritHandle
0x180005e33  mov     ecx, 1F0003h; dwDesiredAccess
0x180005e38  call    cs:__imp_OpenSemaphoreW
0x180005e3e  mov     rdi, rax
0x180005e41  test    rax, rax
0x180005e44  jz      loc_180005ECB
0x180005e4a  lea     rdx, [rsp+268h+var_248]; int *
0x180005e4f  mov     rcx, rax; hHandle
0x180005e52  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005e57  mov     esi, eax
0x180005e59  test    eax, eax
0x180005e5b  jns     short loc_180005E97
0x180005e5d  mov     r8d, eax; wil::details *
0x180005e60  lea     rdx, aWil; "wil"
0x180005e67  mov     ecx, 0DEh; this
0x180005e6c  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180005e71  mov     rcx, rdi; hObject
0x180005e74  call    cs:__imp_CloseHandle
0x180005e7a  test    eax, eax
0x180005e7c  jz      loc_180005F56
0x180005e82  mov     rcx, rbx; hObject
0x180005e85  call    cs:__imp_CloseHandle
0x180005e8b  test    eax, eax
0x180005e8d  jz      loc_180005F61
0x180005e93  mov     eax, esi
0x180005e95  jmp     short loc_180005F02
0x180005e97  mov     rcx, rdi; hObject
0x180005e9a  call    cs:__imp_CloseHandle
0x180005ea0  test    eax, eax
0x180005ea2  jz      loc_180005F2A
0x180005ea8  movsxd  rax, [rsp+268h+var_244]
0x180005ead  movsxd  rcx, [rsp+268h+var_248]
0x180005eb2  shl     rcx, 1Fh
0x180005eb6  or      rcx, rax
0x180005eb9  mov     [r14], rcx
0x180005ebc  mov     rcx, rbx; hObject
0x180005ebf  call    cs:__imp_CloseHandle
0x180005ec5  test    eax, eax
0x180005ec7  jz      short loc_180005F35
0x180005ec9  jmp     short loc_180005EF4
0x180005ecb  mov     ecx, 0DCh; this
0x180005ed0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJIPEBD@Z; wil::details::in1diag3::Return_GetLastError(uint,char const *)
0x180005ed5  mov     rcx, rbx; hObject
0x180005ed8  mov     edi, eax
0x180005eda  call    cs:__imp_CloseHandle
0x180005ee0  test    eax, eax
0x180005ee2  jz      short loc_180005F40
0x180005ee4  jmp     loc_180005E11
0x180005ee9  call    cs:__imp_GetLastError
0x180005eef  cmp     eax, 2
0x180005ef2  jnz     short loc_180005EF8
0x180005ef4  xor     eax, eax
0x180005ef6  jmp     short loc_180005F02
0x180005ef8  mov     ecx, 0D0h; this
0x180005efd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJIPEBD@Z; wil::details::in1diag3::Return_GetLastError(uint,char const *)
0x180005f02  mov     rcx, [rsp+268h+var_28]
0x180005f0a  xor     rcx, rsp; StackCookie
0x180005f0d  call    __security_check_cookie
0x180005f12  lea     r11, [rsp+268h+var_18]
0x180005f1a  mov     rbx, [r11+20h]
0x180005f1e  mov     rbp, [r11+28h]
0x180005f22  mov     rsp, r11
0x180005f25  pop     r14
0x180005f27  pop     rdi
0x180005f28  pop     rsi
0x180005f29  retn
0x180005f2a  mov     ecx, 0A0Bh; this
0x180005f2f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180005f35  mov     ecx, 0A0Bh; this
0x180005f3a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180005f40  mov     ecx, 0A0Bh; this
0x180005f45  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180005f4b  mov     ecx, 0A0Bh; this
0x180005f50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180005f56  mov     ecx, 0A0Bh; this
0x180005f5b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
0x180005f61  mov     ecx, 0A0Bh; this
0x180005f66  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(uint,char const *)
```
