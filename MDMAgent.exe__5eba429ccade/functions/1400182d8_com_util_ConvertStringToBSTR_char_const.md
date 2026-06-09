# _com_util::ConvertStringToBSTR(char const *)

- ea: `0x1400182d8`
- end: `0x14001845b`
- name: `?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z`
- size: `387`
- prototype: `BSTR __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008d58`

## callees

- `0x140002930`
- `0x140008830`
- `0x1400182d8`
- `0x1400185e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400183f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001843b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400183f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001843b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001839f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001839f`
- `OLEAUT32!__imp_SysAllocString` at `0x1400183e4`
- `OLEAUT32!__imp_SysAllocString` at `0x1400183e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018441`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140018357`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400183d7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140018357`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400183d7`

## pseudocode

```c
BSTR __fastcall _com_util::ConvertStringToBSTR(LPCCH lpMultiByteStr)
{
  __int64 v3; // rax
  int v4; // r15d
  int v5; // eax
  int cchWideChar; // edi
  size_t v7; // rcx
  __int64 v8; // rax
  void *v9; // rsp
  void *lpWideCharStr; // rbx
  BSTR v11; // rsi
  signed int LastError; // eax
  signed int v13; // eax
  WCHAR WideCharStr[2]; // [rsp+30h] [rbp+0h] BYREF
  int v15; // [rsp+34h] [rbp+4h]
  void *v16; // [rsp+38h] [rbp+8h]

  if ( !lpMultiByteStr )
    return 0;
  v3 = -1;
  do
    ++v3;
  while ( lpMultiByteStr[v3] );
  v4 = v3 + 1;
  v15 = v3 + 1;
  v5 = MultiByteToWideChar(0, 0, lpMultiByteStr, v3 + 1, 0, 0);
  cchWideChar = v5;
  *(_DWORD *)WideCharStr = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    _com_issue_error(LastError);
  }
  v7 = 2LL * v5;
  if ( v5 >= 4096 )
  {
    lpWideCharStr = malloc(v7);
  }
  else
  {
    v8 = v7 + 15;
    if ( v7 + 15 < v7 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
    lpWideCharStr = WideCharStr;
  }
  v16 = lpWideCharStr;
  if ( !lpWideCharStr )
    goto LABEL_17;
  if ( !MultiByteToWideChar(0, 0, lpMultiByteStr, v4, (LPWSTR)lpWideCharStr, cchWideChar) )
  {
    if ( cchWideChar >= 4096 )
      free(lpWideCharStr);
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    _com_issue_error(v13);
  }
  v11 = SysAllocString((const OLECHAR *)lpWideCharStr);
  if ( cchWideChar >= 4096 )
    free(lpWideCharStr);
  if ( !v11 )
LABEL_17:
    _com_issue_error(-2147024882);
  return v11;
}

```

## disassembly

```asm
0x1400182d8  mov     [rsp-8+arg_0], rcx
0x1400182dd  push    rbp
0x1400182de  push    rdi
0x1400182df  push    r15
0x1400182e1  sub     rsp, 50h
0x1400182e5  lea     rbp, [rsp+30h]
0x1400182ea  mov     [rbp+30h+arg_8], rbx
0x1400182ee  mov     [rbp+30h+arg_10], rsi
0x1400182f2  mov     rax, cs:__security_cookie
0x1400182f9  xor     rax, rbp
0x1400182fc  mov     [rbp+30h+var_20], rax
0x140018300  mov     rsi, rcx
0x140018303  test    rcx, rcx
0x140018306  jnz     short loc_140018327
0x140018308  xor     eax, eax
0x14001830a  mov     rcx, [rbp+30h+var_20]
0x14001830e  xor     rcx, rbp; StackCookie
0x140018311  call    __security_check_cookie
0x140018316  mov     rbx, [rbp+30h+arg_8]
0x14001831a  mov     rsi, [rbp+30h+arg_10]
0x14001831e  lea     rsp, [rbp+20h]
0x140018322  pop     r15
0x140018324  pop     rdi
0x140018325  pop     rbp
0x140018326  retn
0x140018327  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001832b  inc     rax
0x14001832e  cmp     byte ptr [rcx+rax], 0
0x140018332  jnz     short loc_14001832B
0x140018334  lea     r15d, [rax+1]
0x140018338  mov     [rbp+30h+var_2C], r15d
0x14001833c  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x140018344  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x14001834d  mov     r9d, r15d; cbMultiByte
0x140018350  mov     r8, rcx; lpMultiByteStr
0x140018353  xor     edx, edx; dwFlags
0x140018355  xor     ecx, ecx; CodePage
0x140018357  call    cs:__imp_MultiByteToWideChar
0x14001835d  movsxd  rdi, eax
0x140018360  mov     dword ptr [rbp+30h+WideCharStr], edi
0x140018363  test    eax, eax
0x140018365  jz      loc_140018416
0x14001836b  mov     rcx, rdi
0x14001836e  add     rcx, rcx; Size
0x140018371  cmp     edi, 1000h
0x140018377  jge     short loc_14001839F
0x140018379  lea     rax, [rcx+0Fh]
0x14001837d  cmp     rax, rcx
0x140018380  ja      short loc_14001838C
0x140018382  mov     rax, 0FFFFFFFFFFFFFF0h
0x14001838c  and     rax, 0FFFFFFFFFFFFFFF0h
0x140018390  call    _alloca_probe
0x140018395  sub     rsp, rax
0x140018398  lea     rbx, [rsp+60h+WideCharStr]
0x14001839d  jmp     short loc_1400183A8
0x14001839f  call    cs:__imp_malloc
0x1400183a5  mov     rbx, rax
0x1400183a8  mov     [rbp+30h+var_28], rbx
0x1400183ac  jmp     short loc_1400183BF
0x1400183ae  xor     ebx, ebx
0x1400183b0  mov     [rbp+30h+var_28], rbx
0x1400183b4  mov     rsi, [rbp+30h+arg_0]
0x1400183b8  mov     edi, dword ptr [rbp+30h+WideCharStr]
0x1400183bb  mov     r15d, [rbp+30h+var_2C]
0x1400183bf  test    rbx, rbx
0x1400183c2  jz      short loc_14001840B
0x1400183c4  mov     [rsp+60h+cchWideChar], edi; cchWideChar
0x1400183c8  mov     [rsp+60h+lpWideCharStr], rbx; lpWideCharStr
0x1400183cd  mov     r9d, r15d; cbMultiByte
0x1400183d0  mov     r8, rsi; lpMultiByteStr
0x1400183d3  xor     edx, edx; dwFlags
0x1400183d5  xor     ecx, ecx; CodePage
0x1400183d7  call    cs:__imp_MultiByteToWideChar
0x1400183dd  test    eax, eax
0x1400183df  jz      short loc_140018430
0x1400183e1  mov     rcx, rbx; psz
0x1400183e4  call    cs:__imp_SysAllocString
0x1400183ea  mov     rsi, rax
0x1400183ed  cmp     edi, 1000h
0x1400183f3  jl      short loc_1400183FE
0x1400183f5  mov     rcx, rbx; Block
0x1400183f8  call    cs:__imp_free
0x1400183fe  test    rsi, rsi
0x140018401  jz      short loc_14001840B
0x140018403  mov     rax, rsi
0x140018406  jmp     loc_14001830A
0x14001840b  mov     ecx, 8007000Eh; int
0x140018410  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140018416  call    cs:__imp_GetLastError
0x14001841c  test    eax, eax
0x14001841e  jle     short loc_140018428
0x140018420  movzx   eax, ax
0x140018423  or      eax, 80070000h
0x140018428  mov     ecx, eax; int
0x14001842a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140018430  cmp     edi, 1000h
0x140018436  jl      short loc_140018441
0x140018438  mov     rcx, rbx; Block
0x14001843b  call    cs:__imp_free
0x140018441  call    cs:__imp_GetLastError
0x140018447  test    eax, eax
0x140018449  jle     short loc_140018453
0x14001844b  movzx   eax, ax
0x14001844e  or      eax, 80070000h
0x140018453  mov     ecx, eax; int
0x140018455  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
