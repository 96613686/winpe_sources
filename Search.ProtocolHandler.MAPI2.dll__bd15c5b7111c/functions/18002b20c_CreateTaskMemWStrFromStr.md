# CreateTaskMemWStrFromStr

- ea: `0x18002b20c`
- end: `0x18002b39c`
- name: `CreateTaskMemWStrFromStr`
- size: `400`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr, WCHAR **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b428`

## callees

- `0x18000835c`
- `0x18002b20c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b2d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b350`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18002b23b`
- `api-ms-win-core-localization-l1-2-0!IsValidCodePage` at `0x18002b23b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b2b7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b30b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b33f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b2b7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b30b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002b33f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b37b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b37b`

## string_xrefs

- `0x18002b283`: `onecoreuap\base\appmodel\search\common\pkmutild\propvarcvt.cxx`

## pseudocode

```c
__int64 __fastcall CreateTaskMemWStrFromStr(UINT CodePage, LPCCH lpMultiByteStr, WCHAR **a3)
{
  UINT v5; // edi
  __int64 v6; // rax
  unsigned int v7; // r12d
  unsigned int cchWideChar; // r13d
  WCHAR *v9; // rax
  WCHAR *v10; // r14
  unsigned int v11; // ebx
  WCHAR *v13; // rsi
  signed int LastError; // eax
  signed int v15; // eax
  int lpWideCharStr; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = CodePage;
  if ( lpMultiByteStr && a3 )
  {
    if ( CodePage )
      v5 = IsValidCodePage(CodePage) ? CodePage : 0;
    v6 = -1;
    do
      ++v6;
    while ( lpMultiByteStr[v6] );
    v7 = v6 + 1;
    cchWideChar = v7 / 0xA + v7;
    v9 = (WCHAR *)CoTaskMemAlloc(2LL * cchWideChar);
    v10 = v9;
    if ( !v9 )
    {
      v11 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\propvarcvt.cxx",
        (const char *)0x8007000ELL,
        lpWideCharStr);
      return v11;
    }
    if ( MultiByteToWideChar(v5, 0, lpMultiByteStr, v7, v9, cchWideChar) )
    {
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 == -2147024774 )
      {
        MultiByteToWideChar(v5, 0, lpMultiByteStr, v7, 0, 0);
        v13 = (WCHAR *)CoTaskMemAlloc(2LL * (v7 / 0xA + v7));
        CoTaskMemFree(v10);
        if ( !v13 )
          return (unsigned int)-2147024882;
        if ( MultiByteToWideChar(v5, 0, lpMultiByteStr, v7, v13, cchWideChar) )
        {
          v11 = 0;
        }
        else
        {
          v15 = GetLastError();
          v11 = v15;
          if ( v15 > 0 )
            v11 = (unsigned __int16)v15 | 0x80070000;
        }
LABEL_13:
        if ( (v11 & 0x80000000) != 0 )
          CoTaskMemFree(v13);
        else
          *a3 = v13;
        return v11;
      }
    }
    v13 = v10;
    goto LABEL_13;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18002b20c  push    rbx
0x18002b20e  push    rbp
0x18002b20f  push    rsi
0x18002b210  push    rdi
0x18002b211  push    r12
0x18002b213  push    r13
0x18002b215  push    r14
0x18002b217  push    r15
0x18002b219  sub     rsp, 38h
0x18002b21d  mov     r15, r8
0x18002b220  mov     rbp, rdx
0x18002b223  mov     edi, ecx
0x18002b225  test    rdx, rdx
0x18002b228  jz      loc_18002B386
0x18002b22e  test    r8, r8
0x18002b231  jz      loc_18002B386
0x18002b237  test    ecx, ecx
0x18002b239  jz      short loc_18002B247
0x18002b23b  call    cs:__imp_IsValidCodePage
0x18002b241  neg     eax
0x18002b243  sbb     ecx, ecx
0x18002b245  and     edi, ecx
0x18002b247  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b24b  inc     rax
0x18002b24e  cmp     byte ptr [rax+rbp], 0
0x18002b252  jnz     short loc_18002B24B
0x18002b254  lea     r12d, [rax+1]
0x18002b258  mov     eax, 0CCCCCCCDh
0x18002b25d  mul     r12d
0x18002b260  shr     edx, 3
0x18002b263  lea     r13d, [rdx+r12]
0x18002b267  mov     esi, r13d
0x18002b26a  add     rsi, rsi
0x18002b26d  mov     rcx, rsi; cb
0x18002b270  call    cs:__imp_CoTaskMemAlloc
0x18002b276  mov     r14, rax
0x18002b279  test    rax, rax
0x18002b27c  jnz     short loc_18002B2A3
0x18002b27e  mov     rcx, [rsp+78h]; this
0x18002b283  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002b28a  mov     ebx, 8007000Eh
0x18002b28f  mov     edx, 5AFh; void *
0x18002b294  mov     r9d, ebx; char *
0x18002b297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b29c  mov     eax, ebx
0x18002b29e  jmp     loc_18002B38B
0x18002b2a3  mov     [rsp+78h+cchWideChar], r13d; cchWideChar
0x18002b2a8  mov     r9d, r12d; cbMultiByte
0x18002b2ab  mov     r8, rbp; lpMultiByteStr
0x18002b2ae  mov     [rsp+78h+lpWideCharStr], r14; lpWideCharStr
0x18002b2b3  xor     edx, edx; dwFlags
0x18002b2b5  mov     ecx, edi; CodePage
0x18002b2b7  call    cs:__imp_MultiByteToWideChar
0x18002b2bd  test    eax, eax
0x18002b2bf  jz      short loc_18002B2D3
0x18002b2c1  xor     ebx, ebx
0x18002b2c3  mov     rsi, r14
0x18002b2c6  test    ebx, ebx
0x18002b2c8  js      loc_18002B378
0x18002b2ce  mov     [r15], rsi
0x18002b2d1  jmp     short loc_18002B29C
0x18002b2d3  call    cs:__imp_GetLastError
0x18002b2d9  mov     ebx, eax
0x18002b2db  test    eax, eax
0x18002b2dd  jle     short loc_18002B2E8
0x18002b2df  movzx   ebx, ax
0x18002b2e2  or      ebx, 80070000h
0x18002b2e8  cmp     ebx, 8007007Ah
0x18002b2ee  jnz     short loc_18002B2C3
0x18002b2f0  mov     [rsp+78h+cchWideChar], 0; cchWideChar
0x18002b2f8  mov     r9d, r12d; cbMultiByte
0x18002b2fb  mov     r8, rbp; lpMultiByteStr
0x18002b2fe  mov     [rsp+78h+lpWideCharStr], 0; lpWideCharStr
0x18002b307  xor     edx, edx; dwFlags
0x18002b309  mov     ecx, edi; CodePage
0x18002b30b  call    cs:__imp_MultiByteToWideChar
0x18002b311  mov     rcx, rsi; cb
0x18002b314  call    cs:__imp_CoTaskMemAlloc
0x18002b31a  mov     rcx, r14; pv
0x18002b31d  mov     rsi, rax
0x18002b320  call    cs:__imp_CoTaskMemFree
0x18002b326  test    rsi, rsi
0x18002b329  jz      short loc_18002B36E
0x18002b32b  mov     [rsp+78h+cchWideChar], r13d; cchWideChar
0x18002b330  mov     r9d, r12d; cbMultiByte
0x18002b333  mov     r8, rbp; lpMultiByteStr
0x18002b336  mov     [rsp+78h+lpWideCharStr], rsi; lpWideCharStr
0x18002b33b  xor     edx, edx; dwFlags
0x18002b33d  mov     ecx, edi; CodePage
0x18002b33f  call    cs:__imp_MultiByteToWideChar
0x18002b345  test    eax, eax
0x18002b347  jz      short loc_18002B350
0x18002b349  xor     ebx, ebx
0x18002b34b  jmp     loc_18002B2C6
0x18002b350  call    cs:__imp_GetLastError
0x18002b356  mov     ebx, eax
0x18002b358  test    eax, eax
0x18002b35a  jle     loc_18002B2C6
0x18002b360  movzx   ebx, ax
0x18002b363  or      ebx, 80070000h
0x18002b369  jmp     loc_18002B2C6
0x18002b36e  mov     ebx, 8007000Eh
0x18002b373  jmp     loc_18002B29C
0x18002b378  mov     rcx, rsi; pv
0x18002b37b  call    cs:__imp_CoTaskMemFree
0x18002b381  jmp     loc_18002B29C
0x18002b386  mov     eax, 80004003h
0x18002b38b  add     rsp, 38h
0x18002b38f  pop     r15
0x18002b391  pop     r14
0x18002b393  pop     r13
0x18002b395  pop     r12
0x18002b397  pop     rdi
0x18002b398  pop     rsi
0x18002b399  pop     rbp
0x18002b39a  pop     rbx
0x18002b39b  retn
```
