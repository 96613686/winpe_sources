# _com_util::ConvertStringToBSTR(char const *)

- ea: `0x14001900c`
- end: `0x1400191c0`
- name: `?ConvertStringToBSTR@_com_util@@YAPEAGPEBD@Z`
- size: `436`
- prototype: `unsigned __int16 *__fastcall(LPCCH lpMultiByteStr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009170`

## callees

- `0x1400029c0`
- `0x140008c18`
- `0x14001900c`
- `0x140019340`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140019145`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140019194`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140019145`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140019194`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400190da`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400190da`
- `OLEAUT32!__imp_SysAllocString` at `0x14001912b`
- `OLEAUT32!__imp_SysAllocString` at `0x14001912b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400191a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400191a0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001908c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140019118`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x14001908c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140019118`

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
0x14001900c  mov     [rsp-8+arg_0], rcx
0x140019011  push    rbp
0x140019012  push    rdi
0x140019013  push    r15
0x140019015  sub     rsp, 50h
0x140019019  lea     rbp, [rsp+30h]
0x14001901e  mov     [rbp+30h+arg_8], rbx
0x140019022  mov     [rbp+30h+arg_10], rsi
0x140019026  mov     rax, cs:__security_cookie
0x14001902d  xor     rax, rbp
0x140019030  mov     [rbp+30h+var_20], rax
0x140019034  mov     rsi, rcx
0x140019037  test    rcx, rcx
0x14001903a  jnz     short loc_14001905C
0x14001903c  xor     eax, eax
0x14001903e  mov     rcx, [rbp+30h+var_20]
0x140019042  xor     rcx, rbp; StackCookie
0x140019045  call    __security_check_cookie
0x14001904a  mov     rbx, [rbp+30h+arg_8]
0x14001904e  mov     rsi, [rbp+30h+arg_10]
0x140019052  lea     rsp, [rbp+20h]
0x140019056  pop     r15
0x140019058  pop     rdi
0x140019059  pop     rbp
0x14001905a  retn
0x14001905c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019060  inc     rax
0x140019063  cmp     byte ptr [rcx+rax], 0
0x140019067  jnz     short loc_140019060
0x140019069  lea     r15d, [rax+1]
0x14001906d  mov     [rbp+30h+var_2C], r15d
0x140019071  mov     [rsp+60h+cchWideChar], 0; cchWideChar
0x140019079  mov     [rsp+60h+lpWideCharStr], 0; lpWideCharStr
0x140019082  mov     r9d, r15d; cbMultiByte
0x140019085  mov     r8, rcx; lpMultiByteStr
0x140019088  xor     edx, edx; dwFlags
0x14001908a  xor     ecx, ecx; CodePage
0x14001908c  call    cs:__imp_MultiByteToWideChar
0x140019093  nop     dword ptr [rax+rax+00h]
0x140019098  movsxd  rdi, eax
0x14001909b  mov     dword ptr [rbp+30h+WideCharStr], edi
0x14001909e  test    eax, eax
0x1400190a0  jz      loc_140019169
0x1400190a6  mov     rcx, rdi
0x1400190a9  add     rcx, rcx; Size
0x1400190ac  cmp     edi, 1000h
0x1400190b2  jge     short loc_1400190DA
0x1400190b4  lea     rax, [rcx+0Fh]
0x1400190b8  cmp     rax, rcx
0x1400190bb  ja      short loc_1400190C7
0x1400190bd  mov     rax, 0FFFFFFFFFFFFFF0h
0x1400190c7  and     rax, 0FFFFFFFFFFFFFFF0h
0x1400190cb  call    _alloca_probe
0x1400190d0  sub     rsp, rax
0x1400190d3  lea     rbx, [rsp+60h+WideCharStr]
0x1400190d8  jmp     short loc_1400190E9
0x1400190da  call    cs:__imp_malloc
0x1400190e1  nop     dword ptr [rax+rax+00h]
0x1400190e6  mov     rbx, rax
0x1400190e9  mov     [rbp+30h+var_28], rbx
0x1400190ed  jmp     short loc_140019100
0x1400190ef  xor     ebx, ebx
0x1400190f1  mov     [rbp+30h+var_28], rbx
0x1400190f5  mov     rsi, [rbp+30h+arg_0]
0x1400190f9  mov     edi, dword ptr [rbp+30h+WideCharStr]
0x1400190fc  mov     r15d, [rbp+30h+var_2C]
0x140019100  test    rbx, rbx
0x140019103  jz      short loc_14001915E
0x140019105  mov     [rsp+60h+cchWideChar], edi; cchWideChar
0x140019109  mov     [rsp+60h+lpWideCharStr], rbx; lpWideCharStr
0x14001910e  mov     r9d, r15d; cbMultiByte
0x140019111  mov     r8, rsi; lpMultiByteStr
0x140019114  xor     edx, edx; dwFlags
0x140019116  xor     ecx, ecx; CodePage
0x140019118  call    cs:__imp_MultiByteToWideChar
0x14001911f  nop     dword ptr [rax+rax+00h]
0x140019124  test    eax, eax
0x140019126  jz      short loc_140019189
0x140019128  mov     rcx, rbx; psz
0x14001912b  call    cs:__imp_SysAllocString
0x140019132  nop     dword ptr [rax+rax+00h]
0x140019137  mov     rsi, rax
0x14001913a  cmp     edi, 1000h
0x140019140  jl      short loc_140019151
0x140019142  mov     rcx, rbx; Block
0x140019145  call    cs:__imp_free
0x14001914c  nop     dword ptr [rax+rax+00h]
0x140019151  test    rsi, rsi
0x140019154  jz      short loc_14001915E
0x140019156  mov     rax, rsi
0x140019159  jmp     loc_14001903E
0x14001915e  mov     ecx, 8007000Eh; int
0x140019163  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140019169  call    cs:__imp_GetLastError
0x140019170  nop     dword ptr [rax+rax+00h]
0x140019175  test    eax, eax
0x140019177  jle     short loc_140019181
0x140019179  movzx   eax, ax
0x14001917c  or      eax, 80070000h
0x140019181  mov     ecx, eax; int
0x140019183  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140019189  cmp     edi, 1000h
0x14001918f  jl      short loc_1400191A0
0x140019191  mov     rcx, rbx; Block
0x140019194  call    cs:__imp_free
0x14001919b  nop     dword ptr [rax+rax+00h]
0x1400191a0  call    cs:__imp_GetLastError
0x1400191a7  nop     dword ptr [rax+rax+00h]
0x1400191ac  test    eax, eax
0x1400191ae  jle     short loc_1400191B8
0x1400191b0  movzx   eax, ax
0x1400191b3  or      eax, 80070000h
0x1400191b8  mov     ecx, eax; int
0x1400191ba  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
