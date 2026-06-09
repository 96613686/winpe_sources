# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000fb7c`
- end: `0x18000fe3e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `706`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a82c`
- `0x18000abf0`

## callees

- `0x180002880`
- `0x18000c51c`
- `0x18000eae4`
- `0x18000eb04`
- `0x18000f5a0`
- `0x18000fb7c`
- `0x180010474`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000fc1b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000fc9c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000fc1b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000fc9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd6a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fc67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fcf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd6a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        char *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rdx
  signed __int64 v5; // rcx
  __int64 v7; // r9
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE v10; // rax
  void *v11; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v13; // rdx
  unsigned int v14; // r8d
  unsigned int LastError; // edi
  unsigned int v16; // r8d
  const char *v17; // r9
  HANDLE v19; // rax
  unsigned int v20; // r8d
  const char *v21; // r9
  void *v22; // rdi
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // esi
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  int v38; // [rsp+28h] [rbp-E0h] BYREF
  int v39[3]; // [rsp+2Ch] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  *a3 = 0;
  v4 = Name;
  v5 = a1 - (char *)Name;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v4 + v5);
    if ( !v8 )
      break;
    *v4++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  *v9 = 0;
  StringCchCatW(Name, (unsigned __int64)v4, L"_p0");
  v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v11 = v10;
  if ( !v10 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v36, v37);
    return 0;
  }
  v39[0] = 0;
  v38 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, v39);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v14, (const char *)(unsigned int)ValueFromSemaphore, v38);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v16, v17);
    return LastError;
  }
  StringCchCatW(Name, v13, L"h");
  v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v19;
  if ( !v19 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v20, v21);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v34, v35);
    return LastError;
  }
  v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v38);
  v25 = v23;
  if ( v23 >= 0 )
  {
    if ( !CloseHandle(v22) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v30, v31);
    *a3 = v39[0] | (unsigned __int64)((__int64)v38 << 31);
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v32, v33);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v24, (const char *)(unsigned int)v23, v38);
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v26, v27);
  if ( !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v28, v29);
  return v25;
}

```

## disassembly

```asm
0x18000fb7c  mov     rax, rsp
0x18000fb7f  mov     [rax+8], rbx
0x18000fb83  mov     [rax+10h], rsi
0x18000fb87  mov     [rax+20h], rdi
0x18000fb8b  push    rbp
0x18000fb8c  push    r14
0x18000fb8e  push    r15
0x18000fb90  lea     rbp, [rax-168h]
0x18000fb97  sub     rsp, 250h
0x18000fb9e  mov     rax, cs:__security_cookie
0x18000fba5  xor     rax, rsp
0x18000fba8  mov     [rbp+160h+var_20], rax
0x18000fbaf  xor     r15d, r15d
0x18000fbb2  lea     rax, [rsp+260h+Name]
0x18000fbb7  mov     [r8], r15
0x18000fbba  lea     rdx, [rsp+260h+Name]
0x18000fbbf  sub     rcx, rax
0x18000fbc2  mov     r14, r8
0x18000fbc5  mov     r9d, 104h
0x18000fbcb  lea     rax, [r9+7FFFFEFAh]
0x18000fbd2  test    rax, rax
0x18000fbd5  jz      short loc_18000FBED
0x18000fbd7  movzx   eax, word ptr [rcx+rdx]
0x18000fbdb  test    ax, ax
0x18000fbde  jz      short loc_18000FBED
0x18000fbe0  mov     [rdx], ax
0x18000fbe3  add     rdx, 2; unsigned __int64
0x18000fbe7  sub     r9, 1
0x18000fbeb  jnz     short loc_18000FBCB
0x18000fbed  test    r9, r9
0x18000fbf0  lea     rax, [rdx-2]
0x18000fbf4  lea     r8, aP0; "_p0"
0x18000fbfb  cmovnz  rax, rdx
0x18000fbff  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000fc04  mov     [rax], r15w
0x18000fc08  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fc0d  mov     esi, 1F0003h
0x18000fc12  lea     r8, [rsp+260h+Name]; lpName
0x18000fc17  mov     ecx, esi; dwDesiredAccess
0x18000fc19  xor     edx, edx; bInheritHandle
0x18000fc1b  call    cs:__imp_OpenSemaphoreW
0x18000fc22  nop     dword ptr [rax+rax+00h]
0x18000fc27  mov     rbx, rax
0x18000fc2a  test    rax, rax
0x18000fc2d  jz      loc_18000FD7F
0x18000fc33  lea     rdx, [rsp+260h+var_23C]; int *
0x18000fc38  mov     [rsp+260h+var_23C], r15d
0x18000fc3d  mov     rcx, rax; hHandle
0x18000fc40  mov     [rsp+260h+var_240], r15d; int
0x18000fc45  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000fc4a  mov     edi, eax
0x18000fc4c  test    eax, eax
0x18000fc4e  jns     short loc_18000FC82
0x18000fc50  mov     rcx, [rbp+168h]; this
0x18000fc57  mov     r9d, eax; char *
0x18000fc5a  mov     edx, 0D3h; void *
0x18000fc5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc64  mov     rcx, rbx; hObject
0x18000fc67  call    cs:__imp_CloseHandle
0x18000fc6e  nop     dword ptr [rax+rax+00h]
0x18000fc73  test    eax, eax
0x18000fc75  jz      loc_18000FE08
0x18000fc7b  mov     eax, edi
0x18000fc7d  jmp     loc_18000FDA5
0x18000fc82  lea     r8, asc_180030EF0; "h"
0x18000fc89  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000fc8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000fc93  lea     r8, [rsp+260h+Name]; lpName
0x18000fc98  xor     edx, edx; bInheritHandle
0x18000fc9a  mov     ecx, esi; dwDesiredAccess
0x18000fc9c  call    cs:__imp_OpenSemaphoreW
0x18000fca3  nop     dword ptr [rax+rax+00h]
0x18000fca8  mov     rdi, rax
0x18000fcab  test    rax, rax
0x18000fcae  jz      loc_18000FD54
0x18000fcb4  lea     rdx, [rsp+260h+var_240]; int *
0x18000fcb9  mov     rcx, rax; hHandle
0x18000fcbc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000fcc1  mov     esi, eax
0x18000fcc3  test    eax, eax
0x18000fcc5  jns     short loc_18000FD10
0x18000fcc7  mov     rcx, [rbp+168h]; this
0x18000fcce  mov     r9d, eax; char *
0x18000fcd1  mov     edx, 0DBh; void *
0x18000fcd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fcdb  mov     rcx, rdi; hObject
0x18000fcde  call    cs:__imp_CloseHandle
0x18000fce5  nop     dword ptr [rax+rax+00h]
0x18000fcea  test    eax, eax
0x18000fcec  jz      loc_18000FE1A
0x18000fcf2  mov     rcx, rbx; hObject
0x18000fcf5  call    cs:__imp_CloseHandle
0x18000fcfc  nop     dword ptr [rax+rax+00h]
0x18000fd01  test    eax, eax
0x18000fd03  jz      loc_18000FE2C
0x18000fd09  mov     eax, esi
0x18000fd0b  jmp     loc_18000FDA5
0x18000fd10  mov     rcx, rdi; hObject
0x18000fd13  call    cs:__imp_CloseHandle
0x18000fd1a  nop     dword ptr [rax+rax+00h]
0x18000fd1f  test    eax, eax
0x18000fd21  jz      loc_18000FDD2
0x18000fd27  movsxd  rax, [rsp+260h+var_23C]
0x18000fd2c  movsxd  rcx, [rsp+260h+var_240]
0x18000fd31  shl     rcx, 1Fh
0x18000fd35  or      rcx, rax
0x18000fd38  mov     [r14], rcx
0x18000fd3b  mov     rcx, rbx; hObject
0x18000fd3e  call    cs:__imp_CloseHandle
0x18000fd45  nop     dword ptr [rax+rax+00h]
0x18000fd4a  test    eax, eax
0x18000fd4c  jz      loc_18000FDE4
0x18000fd52  jmp     short loc_18000FD90
0x18000fd54  mov     rcx, [rbp+168h]; this
0x18000fd5b  mov     edx, 0D9h; void *
0x18000fd60  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fd65  mov     rcx, rbx; hObject
0x18000fd68  mov     edi, eax
0x18000fd6a  call    cs:__imp_CloseHandle
0x18000fd71  nop     dword ptr [rax+rax+00h]
0x18000fd76  test    eax, eax
0x18000fd78  jz      short loc_18000FDF6
0x18000fd7a  jmp     loc_18000FC7B
0x18000fd7f  call    cs:__imp_GetLastError
0x18000fd86  nop     dword ptr [rax+rax+00h]
0x18000fd8b  cmp     eax, 2
0x18000fd8e  jnz     short loc_18000FD94
0x18000fd90  xor     eax, eax
0x18000fd92  jmp     short loc_18000FDA5
0x18000fd94  mov     rcx, [rbp+168h]; this
0x18000fd9b  mov     edx, 0CDh; void *
0x18000fda0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fda5  mov     rcx, [rbp+160h+var_20]
0x18000fdac  xor     rcx, rsp; StackCookie
0x18000fdaf  call    __security_check_cookie
0x18000fdb4  lea     r11, [rsp+260h+var_10]
0x18000fdbc  mov     rbx, [r11+20h]
0x18000fdc0  mov     rsi, [r11+28h]
0x18000fdc4  mov     rdi, [r11+38h]
0x18000fdc8  mov     rsp, r11
0x18000fdcb  pop     r15
0x18000fdcd  pop     r14
0x18000fdcf  pop     rbp
0x18000fdd0  retn
0x18000fdd2  mov     rcx, [rbp+168h]; this
0x18000fdd9  mov     edx, 9DDh; void *
0x18000fdde  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fde4  mov     rcx, [rbp+168h]; this
0x18000fdeb  mov     edx, 9DDh; void *
0x18000fdf0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fdf6  mov     rcx, [rbp+168h]; this
0x18000fdfd  mov     edx, 9DDh; void *
0x18000fe02  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe08  mov     rcx, [rbp+168h]; this
0x18000fe0f  mov     edx, 9DDh; void *
0x18000fe14  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe1a  mov     rcx, [rbp+168h]; this
0x18000fe21  mov     edx, 9DDh; void *
0x18000fe26  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fe2c  mov     rcx, [rbp+168h]; this
0x18000fe33  mov     edx, 9DDh; void *
0x18000fe38  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
