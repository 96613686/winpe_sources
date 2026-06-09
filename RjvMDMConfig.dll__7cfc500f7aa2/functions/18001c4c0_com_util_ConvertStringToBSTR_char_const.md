# _com_util::ConvertStringToBSTR(char const *)

- ea: `0x18001c4c0`
- end: `0x18001c674`
- name: `?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z`
- size: `436`
- prototype: `unsigned __int16 *__fastcall(LPCCH lpMultiByteStr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800071e8`

## callees

- `0x180001c60`
- `0x18001c484`
- `0x18001c4c0`
- `0x18001cf10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c5f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c648`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c5f9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001c648`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c58e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001c58e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c654`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c5df`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c5df`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c540`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c5cc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c540`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c5cc`

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
0x18001c4c0  mov     [rsp-8+arg_0], rcx
0x18001c4c5  push    rbp
0x18001c4c6  push    rdi
0x18001c4c7  push    r15
0x18001c4c9  sub     rsp, 50h
0x18001c4cd  lea     rbp, [rsp+30h]
0x18001c4d2  mov     [rbp+30h+arg_8], rbx
0x18001c4d6  mov     [rbp+30h+arg_10], rsi
0x18001c4da  mov     rax, cs:__security_cookie
0x18001c4e1  xor     rax, rbp
0x18001c4e4  mov     [rbp+30h+var_20], rax
0x18001c4e8  mov     rsi, rcx
0x18001c4eb  test    rcx, rcx
0x18001c4ee  jnz     short loc_18001C510
0x18001c4f0  xor     eax, eax
0x18001c4f2  mov     rcx, [rbp+30h+var_20]
0x18001c4f6  xor     rcx, rbp; StackCookie
0x18001c4f9  call    __security_check_cookie
0x18001c4fe  mov     rbx, [rbp+30h+arg_8]
0x18001c502  mov     rsi, [rbp+30h+arg_10]
0x18001c506  lea     rsp, [rbp+20h]
0x18001c50a  pop     r15
0x18001c50c  pop     rdi
0x18001c50d  pop     rbp
0x18001c50e  retn
0x18001c510  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c514  inc     rax
0x18001c517  cmp     byte ptr [rcx+rax], 0
0x18001c51b  jnz     short loc_18001C514
0x18001c51d  lea     r15d, [rax+1]
0x18001c521  mov     [rbp+30h+var_2C], r15d
0x18001c525  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x18001c52d  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x18001c536  mov     r9d, r15d; cbMultiByte
0x18001c539  mov     r8, rcx; lpMultiByteStr
0x18001c53c  xor     edx, edx; dwFlags
0x18001c53e  xor     ecx, ecx; CodePage
0x18001c540  call    cs:__imp_MultiByteToWideChar
0x18001c547  nop     dword ptr [rax+rax+00h]
0x18001c54c  movsxd  rdi, eax
0x18001c54f  mov     dword ptr [rbp+30h+WideCharStr], edi
0x18001c552  test    eax, eax
0x18001c554  jz      loc_18001C61D
0x18001c55a  mov     rcx, rdi
0x18001c55d  add     rcx, rcx; Size
0x18001c560  cmp     edi, 1000h
0x18001c566  jge     short loc_18001C58E
0x18001c568  lea     rax, [rcx+0Fh]
0x18001c56c  cmp     rax, rcx
0x18001c56f  ja      short loc_18001C57B
0x18001c571  mov     rax, 0FFFFFFFFFFFFFF0h
0x18001c57b  and     rax, 0FFFFFFFFFFFFFFF0h
0x18001c57f  call    _alloca_probe
0x18001c584  sub     rsp, rax
0x18001c587  lea     rbx, [rsp+60h+WideCharStr]
0x18001c58c  jmp     short loc_18001C59D
0x18001c58e  call    cs:__imp_malloc
0x18001c595  nop     dword ptr [rax+rax+00h]
0x18001c59a  mov     rbx, rax
0x18001c59d  mov     [rbp+30h+var_28], rbx
0x18001c5a1  jmp     short loc_18001C5B4
0x18001c5a3  xor     ebx, ebx
0x18001c5a5  mov     [rbp+30h+var_28], rbx
0x18001c5a9  mov     rsi, [rbp+30h+arg_0]
0x18001c5ad  mov     edi, dword ptr [rbp+30h+WideCharStr]
0x18001c5b0  mov     r15d, [rbp+30h+var_2C]
0x18001c5b4  test    rbx, rbx
0x18001c5b7  jz      short loc_18001C612
0x18001c5b9  mov     [rsp+60h+cchWideChar], edi; cchWideChar
0x18001c5bd  mov     [rsp+60h+lpWideCharStr], rbx; lpWideCharStr
0x18001c5c2  mov     r9d, r15d; cbMultiByte
0x18001c5c5  mov     r8, rsi; lpMultiByteStr
0x18001c5c8  xor     edx, edx; dwFlags
0x18001c5ca  xor     ecx, ecx; CodePage
0x18001c5cc  call    cs:__imp_MultiByteToWideChar
0x18001c5d3  nop     dword ptr [rax+rax+00h]
0x18001c5d8  test    eax, eax
0x18001c5da  jz      short loc_18001C63D
0x18001c5dc  mov     rcx, rbx; psz
0x18001c5df  call    cs:__imp_SysAllocString
0x18001c5e6  nop     dword ptr [rax+rax+00h]
0x18001c5eb  mov     rsi, rax
0x18001c5ee  cmp     edi, 1000h
0x18001c5f4  jl      short loc_18001C605
0x18001c5f6  mov     rcx, rbx; Block
0x18001c5f9  call    cs:__imp_free
0x18001c600  nop     dword ptr [rax+rax+00h]
0x18001c605  test    rsi, rsi
0x18001c608  jz      short loc_18001C612
0x18001c60a  mov     rax, rsi
0x18001c60d  jmp     loc_18001C4F2
0x18001c612  mov     ecx, 8007000Eh; int
0x18001c617  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001c61d  call    cs:__imp_GetLastError
0x18001c624  nop     dword ptr [rax+rax+00h]
0x18001c629  test    eax, eax
0x18001c62b  jle     short loc_18001C635
0x18001c62d  movzx   eax, ax
0x18001c630  or      eax, 80070000h
0x18001c635  mov     ecx, eax; int
0x18001c637  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001c63d  cmp     edi, 1000h
0x18001c643  jl      short loc_18001C654
0x18001c645  mov     rcx, rbx; Block
0x18001c648  call    cs:__imp_free
0x18001c64f  nop     dword ptr [rax+rax+00h]
0x18001c654  call    cs:__imp_GetLastError
0x18001c65b  nop     dword ptr [rax+rax+00h]
0x18001c660  test    eax, eax
0x18001c662  jle     short loc_18001C66C
0x18001c664  movzx   eax, ax
0x18001c667  or      eax, 80070000h
0x18001c66c  mov     ecx, eax; int
0x18001c66e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
