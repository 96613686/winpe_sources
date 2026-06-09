# SniffAndConvertToWideString(char const *,int *,ushort * *)

- ea: `0x180008b60`
- end: `0x180008dd6`
- name: `?SniffAndConvertToWideString@@YAJPEBDPEAHPEAPEAG@Z`
- size: `630`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, int *, LPVOID *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007828`
- `0x1800081a0`
- `0x1800084a0`

## callees

- `0x180008b60`
- `0x1800129d8`
- `0x1800169b8`
- `0x180016c26`
- `0x180016c5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008c27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008d6b`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180008d86`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180008d86`

## pseudocode

```c
__int64 __fastcall SniffAndConvertToWideString(LPCCH lpMultiByteStr, int *a2, LPVOID *a3)
{
  __int64 result; // rax
  int cchWideChar; // ebp
  signed int v7; // ebx
  unsigned __int16 *v8; // rax
  signed int LastError_0; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // eax
  int *CodePage; // [rsp+58h] [rbp+10h] BYREF

  CodePage = a2;
  *a3 = 0;
  result = 0;
  if ( lpMultiByteStr )
  {
    LODWORD(CodePage) = 65001;
    cchWideChar = MultiByteToWideChar_0(0xFDE9u, 8u, lpMultiByteStr, -1, 0, 0);
    if ( cchWideChar )
      goto LABEL_7;
    LastError_0 = GetLastError_0();
    v7 = LastError_0;
    if ( LastError_0 > 0 )
      v7 = (unsigned __int16)LastError_0 | 0x80070000;
    if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147023783 )
    {
      SetLastError(0);
      v7 = 0;
      if ( !GetLocaleInfoEx(0, 0x20001004u, (LPWSTR)&CodePage, 2) )
      {
        v10 = GetLastError_0();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2003292268;
        if ( g_doStackCaptures )
          DoStackCapture(v7);
      }
      if ( v7 < 0 )
        goto LABEL_4;
      cchWideChar = MultiByteToWideChar_0((UINT)CodePage, 0, lpMultiByteStr, -1, 0, 0);
      if ( cchWideChar )
        goto LABEL_7;
      v11 = GetLastError_0();
      v7 = v11;
      if ( v11 > 0 )
        v7 = (unsigned __int16)v11 | 0x80070000;
      if ( v7 >= 0 )
      {
LABEL_7:
        if ( !is_mul_ok(cchWideChar, 2u) )
        {
          v7 = -2147024362;
          if ( !g_doStackCaptures )
          {
LABEL_9:
            CoTaskMemFree(*a3);
            *a3 = 0;
            return (unsigned int)v7;
          }
LABEL_15:
          DoStackCapture(v7);
          goto LABEL_9;
        }
        v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * cchWideChar);
        *a3 = v8;
        if ( !v8 )
        {
          v7 = -2147024882;
          if ( !g_doStackCaptures )
            goto LABEL_9;
          goto LABEL_15;
        }
        memset_0(v8, 0, 2LL * cchWideChar);
        if ( MultiByteToWideChar_0((UINT)CodePage, 0, lpMultiByteStr, -1, (LPWSTR)*a3, cchWideChar) )
          return 0;
        v12 = GetLastError_0();
        v7 = v12;
        if ( v12 > 0 )
          v7 = (unsigned __int16)v12 | 0x80070000;
        if ( v7 >= 0 )
          return (unsigned int)v7;
        if ( g_doStackCaptures )
LABEL_12:
          DoStackCapture(v7);
LABEL_5:
        if ( v7 >= 0 )
          return (unsigned int)v7;
        goto LABEL_9;
      }
      if ( !g_doStackCaptures )
      {
LABEL_4:
        if ( !g_doStackCaptures )
          goto LABEL_5;
        goto LABEL_12;
      }
    }
    else if ( !g_doStackCaptures )
    {
      goto LABEL_5;
    }
    DoStackCapture(v7);
    goto LABEL_4;
  }
  return result;
}

```

## disassembly

```asm
0x180008b60  mov     [rsp+CodePage], rdx
0x180008b65  push    rsi
0x180008b66  push    rdi
0x180008b67  push    r14
0x180008b69  sub     rsp, 30h
0x180008b6d  xor     r14d, r14d
0x180008b70  mov     rdi, r8
0x180008b73  mov     [r8], r14
0x180008b76  mov     rsi, rcx
0x180008b79  mov     eax, r14d
0x180008b7c  test    rcx, rcx
0x180008b7f  jz      loc_180008C12
0x180008b85  mov     r8, rcx; lpMultiByteStr
0x180008b88  mov     [rsp+48h+arg_10], rbx
0x180008b8d  mov     ecx, 0FDE9h; CodePage
0x180008b92  mov     [rsp+48h+cchWideChar], r14d; cchWideChar
0x180008b97  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180008b9d  mov     [rsp+48h+arg_18], rbp
0x180008ba2  mov     edx, 8; dwFlags
0x180008ba7  mov     dword ptr [rsp+48h+CodePage], 0FDE9h
0x180008baf  mov     ebx, r14d
0x180008bb2  mov     [rsp+48h+lpWideCharStr], r14; lpWideCharStr
0x180008bb7  call    MultiByteToWideChar_0
0x180008bbc  mov     ebp, eax
0x180008bbe  test    eax, eax
0x180008bc0  jz      loc_180008C86
0x180008bc6  test    ebx, ebx
0x180008bc8  jns     short loc_180008BD9
0x180008bca  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008bd1  jnz     short loc_180008C1B
0x180008bd3  test    ebx, ebx
0x180008bd5  js      short loc_180008BFA
0x180008bd7  jmp     short loc_180008C06
0x180008bd9  movsxd  rcx, ebp
0x180008bdc  mov     eax, 2
0x180008be1  mul     rcx
0x180008be4  mov     rbx, rax
0x180008be7  test    rdx, rdx
0x180008bea  jz      short loc_180008C24
0x180008bec  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008bf3  mov     ebx, 80070216h
0x180008bf8  jnz     short loc_180008C43
0x180008bfa  mov     rcx, [rdi]; pv
0x180008bfd  call    cs:__imp_CoTaskMemFree
0x180008c03  mov     [rdi], r14
0x180008c06  mov     eax, ebx
0x180008c08  mov     rbx, [rsp+48h+arg_10]
0x180008c0d  mov     rbp, [rsp+48h+arg_18]
0x180008c12  add     rsp, 30h
0x180008c16  pop     r14
0x180008c18  pop     rdi
0x180008c19  pop     rsi
0x180008c1a  retn
0x180008c1b  mov     ecx, ebx; int
0x180008c1d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008c22  jmp     short loc_180008BD3
0x180008c24  mov     rcx, rbx; cb
0x180008c27  call    cs:__imp_CoTaskMemAlloc
0x180008c2d  mov     [rdi], rax
0x180008c30  test    rax, rax
0x180008c33  jnz     short loc_180008C4C
0x180008c35  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008c3c  mov     ebx, 8007000Eh
0x180008c41  jz      short loc_180008BFA
0x180008c43  mov     ecx, ebx; int
0x180008c45  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008c4a  jmp     short loc_180008BFA
0x180008c4c  mov     r8, rbx; Size
0x180008c4f  xor     edx, edx; Val
0x180008c51  mov     rcx, rax; void *
0x180008c54  call    memset_0
0x180008c59  mov     rax, [rdi]
0x180008c5c  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180008c62  mov     ecx, dword ptr [rsp+48h+CodePage]; CodePage
0x180008c66  mov     r8, rsi; lpMultiByteStr
0x180008c69  mov     [rsp+48h+cchWideChar], ebp; cchWideChar
0x180008c6d  xor     edx, edx; dwFlags
0x180008c6f  mov     [rsp+48h+lpWideCharStr], rax; lpWideCharStr
0x180008c74  call    MultiByteToWideChar_0
0x180008c79  test    eax, eax
0x180008c7b  jz      loc_180008D3B
0x180008c81  mov     eax, r14d
0x180008c84  jmp     short loc_180008C08
0x180008c86  call    GetLastError_0
0x180008c8b  mov     ebx, eax
0x180008c8d  test    eax, eax
0x180008c8f  jle     short loc_180008C9A
0x180008c91  movzx   ebx, ax
0x180008c94  or      ebx, 80070000h
0x180008c9a  mov     ecx, 80000000h
0x180008c9f  lea     eax, [rbx+rcx]
0x180008ca2  test    ecx, eax
0x180008ca4  jnz     loc_180008D69
0x180008caa  cmp     ebx, 80070459h
0x180008cb0  jz      loc_180008D69
0x180008cb6  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008cbd  jz      loc_180008BD3
0x180008cc3  mov     ecx, ebx; int
0x180008cc5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008cca  jmp     loc_180008BCA
0x180008ccf  call    GetLastError_0
0x180008cd4  mov     ebx, eax
0x180008cd6  test    eax, eax
0x180008cd8  jle     short loc_180008CE3
0x180008cda  movzx   ebx, ax
0x180008cdd  or      ebx, 80070000h
0x180008ce3  test    ebx, ebx
0x180008ce5  mov     eax, 88982F94h
0x180008cea  cmovns  ebx, eax
0x180008ced  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008cf4  jz      loc_180008D94
0x180008cfa  mov     ecx, ebx; int
0x180008cfc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008d01  jmp     loc_180008D94
0x180008d06  call    GetLastError_0
0x180008d0b  mov     ebx, eax
0x180008d0d  test    eax, eax
0x180008d0f  jle     short loc_180008D1A
0x180008d11  movzx   ebx, ax
0x180008d14  or      ebx, 80070000h
0x180008d1a  test    ebx, ebx
0x180008d1c  jns     loc_180008BD9
0x180008d22  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008d29  jz      loc_180008DC9
0x180008d2f  mov     ecx, ebx; int
0x180008d31  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008d36  jmp     loc_180008BCA
0x180008d3b  call    GetLastError_0
0x180008d40  mov     ebx, eax
0x180008d42  test    eax, eax
0x180008d44  jle     short loc_180008D4F
0x180008d46  movzx   ebx, ax
0x180008d49  or      ebx, 80070000h
0x180008d4f  test    ebx, ebx
0x180008d51  jns     loc_180008C06
0x180008d57  cmp     cs:?g_doStackCaptures@@3HA, r14d; int g_doStackCaptures
0x180008d5e  jz      loc_180008BD3
0x180008d64  jmp     loc_180008C1B
0x180008d69  xor     ecx, ecx; dwErrCode
0x180008d6b  call    cs:__imp_SetLastError
0x180008d71  mov     r9d, 2; cchData
0x180008d77  lea     r8, [rsp+48h+CodePage]; lpLCData
0x180008d7c  mov     edx, 20001004h; LCType
0x180008d81  xor     ecx, ecx; lpLocaleName
0x180008d83  mov     ebx, r14d
0x180008d86  call    cs:__imp_GetLocaleInfoEx
0x180008d8c  test    eax, eax
0x180008d8e  jz      loc_180008CCF
0x180008d94  test    ebx, ebx
0x180008d96  js      loc_180008BCA
0x180008d9c  mov     ecx, dword ptr [rsp+48h+CodePage]; CodePage
0x180008da0  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180008da6  mov     [rsp+48h+cchWideChar], r14d; cchWideChar
0x180008dab  mov     r8, rsi; lpMultiByteStr
0x180008dae  xor     edx, edx; dwFlags
0x180008db0  mov     [rsp+48h+lpWideCharStr], r14; lpWideCharStr
0x180008db5  call    MultiByteToWideChar_0
0x180008dba  mov     ebp, eax
0x180008dbc  test    eax, eax
0x180008dbe  jnz     loc_180008BC6
0x180008dc4  jmp     loc_180008D06
0x180008dc9  test    ebx, ebx
0x180008dcb  js      loc_180008BCA
0x180008dd1  jmp     loc_180008BC6
```
