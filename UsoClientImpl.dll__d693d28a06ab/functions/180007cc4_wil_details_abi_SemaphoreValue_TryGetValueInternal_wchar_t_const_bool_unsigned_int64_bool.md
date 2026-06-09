# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007cc4`
- end: `0x180007f02`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `574`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009ac4`

## callees

- `0x180005f88`
- `0x180007804`
- `0x180007828`
- `0x180007848`
- `0x180007b50`
- `0x180007cc4`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d66`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e2f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d66`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ebd`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v4; // r9
  WCHAR *v5; // rdx
  signed __int64 v6; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rsi
  const char *v12; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // r8d
  const char *v21; // r9
  unsigned int v22; // r8d
  const char *v23; // r9
  unsigned int v24; // r8d
  const char *v25; // r9
  int v26; // [rsp+28h] [rbp-E0h] BYREF
  int v27[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = 260;
  v5 = Name;
  v6 = (char *)a1 - (char *)Name;
  do
  {
    if ( v4 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v5 + v6);
    if ( !v8 )
      break;
    *v5++ = v8;
    --v4;
  }
  while ( v4 );
  v9 = v5 - 1;
  if ( v4 )
    v9 = v5;
  *v9 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v12);
LABEL_13:
    if ( !v11 )
      return LastError;
    goto LABEL_22;
  }
  v26 = 0;
  v27[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v26);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD3,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v26);
    goto LABEL_13;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( v16 )
  {
    v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, v27);
    LastError = v19;
    if ( v19 >= 0 )
    {
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v22, v23);
      LastError = 0;
      *a3 = v26 | (unsigned __int64)((__int64)v27[0] << 31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v19,
        v26);
      if ( !CloseHandle(v18) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v20, v21);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v17);
  }
LABEL_22:
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v24, v25);
  return LastError;
}

```

## disassembly

```asm
0x180007cc4  mov     rax, rsp
0x180007cc7  mov     [rax+8], rbx
0x180007ccb  mov     [rax+10h], rsi
0x180007ccf  mov     [rax+20h], rdi
0x180007cd3  push    rbp
0x180007cd4  push    r14
0x180007cd6  push    r15
0x180007cd8  lea     rbp, [rax-168h]
0x180007cdf  sub     rsp, 250h
0x180007ce6  mov     rax, cs:__security_cookie
0x180007ced  xor     rax, rsp
0x180007cf0  mov     [rbp+160h+var_20], rax
0x180007cf7  xor     r15d, r15d
0x180007cfa  lea     rax, [rsp+260h+Name]
0x180007cff  mov     edi, 104h
0x180007d04  mov     [r8], r15
0x180007d07  mov     r9d, edi
0x180007d0a  lea     rdx, [rsp+260h+Name]
0x180007d0f  sub     rcx, rax
0x180007d12  mov     r14, r8
0x180007d15  lea     rax, [r9+7FFFFEFAh]
0x180007d1c  test    rax, rax
0x180007d1f  jz      short loc_180007D37
0x180007d21  movzx   eax, word ptr [rdx+rcx]
0x180007d25  test    ax, ax
0x180007d28  jz      short loc_180007D37
0x180007d2a  mov     [rdx], ax
0x180007d2d  add     rdx, 2
0x180007d31  sub     r9, 1
0x180007d35  jnz     short loc_180007D15
0x180007d37  lea     rax, [rdx-2]
0x180007d3b  test    r9, r9
0x180007d3e  lea     r8, aP0; "_p0"
0x180007d45  cmovnz  rax, rdx
0x180007d49  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180007d4e  mov     rdx, rdi; unsigned __int64
0x180007d51  mov     [rax], r15w
0x180007d55  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007d5a  lea     r8, [rsp+260h+Name]; lpName
0x180007d5f  xor     edx, edx; bInheritHandle
0x180007d61  mov     ecx, 1F0003h; dwDesiredAccess
0x180007d66  call    cs:__imp_OpenSemaphoreW
0x180007d6c  mov     rsi, rax
0x180007d6f  test    rax, rax
0x180007d72  jnz     short loc_180007DA0
0x180007d74  call    cs:__imp_GetLastError
0x180007d7a  cmp     eax, 2
0x180007d7d  jnz     short loc_180007D84
0x180007d7f  mov     ebx, r15d
0x180007d82  jmp     short loc_180007DD8
0x180007d84  mov     rcx, [rbp+168h]; this
0x180007d8b  lea     r8, aWil; "wil"
0x180007d92  mov     edx, 0CDh; void *
0x180007d97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007d9c  mov     ebx, eax
0x180007d9e  jmp     short loc_180007DD8
0x180007da0  lea     rdx, [rsp+260h+var_240]; int *
0x180007da5  mov     [rsp+260h+var_240], r15d; int
0x180007daa  mov     rcx, rsi; hHandle
0x180007dad  mov     [rsp+260h+var_23C], r15d
0x180007db2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007db7  mov     ebx, eax
0x180007db9  test    eax, eax
0x180007dbb  jns     short loc_180007E0F
0x180007dbd  mov     rcx, [rbp+168h]; this
0x180007dc4  lea     r8, aWil; "wil"
0x180007dcb  mov     r9d, eax; char *
0x180007dce  mov     edx, 0D3h; void *
0x180007dd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007dd8  test    rsi, rsi
0x180007ddb  jnz     loc_180007EBA
0x180007de1  mov     eax, ebx
0x180007de3  mov     rcx, [rbp+160h+var_20]
0x180007dea  xor     rcx, rsp; StackCookie
0x180007ded  call    __security_check_cookie
0x180007df2  lea     r11, [rsp+260h+var_10]
0x180007dfa  mov     rbx, [r11+20h]
0x180007dfe  mov     rsi, [r11+28h]
0x180007e02  mov     rdi, [r11+38h]
0x180007e06  mov     rsp, r11
0x180007e09  pop     r15
0x180007e0b  pop     r14
0x180007e0d  pop     rbp
0x180007e0e  retn
0x180007e0f  lea     r8, asc_180065ED8; "h"
0x180007e16  mov     rdx, rdi; unsigned __int64
0x180007e19  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180007e1e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007e23  lea     r8, [rsp+260h+Name]; lpName
0x180007e28  xor     edx, edx; bInheritHandle
0x180007e2a  mov     ecx, 1F0003h; dwDesiredAccess
0x180007e2f  call    cs:__imp_OpenSemaphoreW
0x180007e35  mov     rdi, rax
0x180007e38  test    rax, rax
0x180007e3b  jnz     short loc_180007E59
0x180007e3d  mov     rcx, [rbp+168h]; this
0x180007e44  lea     r8, aWil; "wil"
0x180007e4b  mov     edx, 0D9h; void *
0x180007e50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007e55  mov     ebx, eax
0x180007e57  jmp     short loc_180007EBA
0x180007e59  lea     rdx, [rsp+260h+var_23C]; int *
0x180007e5e  mov     rcx, rdi; hHandle
0x180007e61  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007e66  mov     ebx, eax
0x180007e68  test    eax, eax
0x180007e6a  jns     short loc_180007E96
0x180007e6c  mov     rcx, [rbp+168h]; this
0x180007e73  lea     r8, aWil; "wil"
0x180007e7a  mov     r9d, eax; char *
0x180007e7d  mov     edx, 0DBh; void *
0x180007e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e87  mov     rcx, rdi; hObject
0x180007e8a  call    cs:__imp_CloseHandle
0x180007e90  test    eax, eax
0x180007e92  jz      short loc_180007EDE
0x180007e94  jmp     short loc_180007EBA
0x180007e96  mov     rcx, rdi; hObject
0x180007e99  call    cs:__imp_CloseHandle
0x180007e9f  test    eax, eax
0x180007ea1  jz      short loc_180007ECC
0x180007ea3  movsxd  rcx, [rsp+260h+var_23C]
0x180007ea8  mov     ebx, r15d
0x180007eab  movsxd  rax, [rsp+260h+var_240]
0x180007eb0  shl     rcx, 1Fh
0x180007eb4  or      rcx, rax
0x180007eb7  mov     [r14], rcx
0x180007eba  mov     rcx, rsi; hObject
0x180007ebd  call    cs:__imp_CloseHandle
0x180007ec3  test    eax, eax
0x180007ec5  jz      short loc_180007EF0
0x180007ec7  jmp     loc_180007DE1
0x180007ecc  mov     rcx, [rbp+168h]; this
0x180007ed3  mov     edx, 9D1h; void *
0x180007ed8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007ede  mov     rcx, [rbp+168h]; this
0x180007ee5  mov     edx, 9D1h; void *
0x180007eea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007ef0  mov     rcx, [rbp+168h]; this
0x180007ef7  mov     edx, 9D1h; void *
0x180007efc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
