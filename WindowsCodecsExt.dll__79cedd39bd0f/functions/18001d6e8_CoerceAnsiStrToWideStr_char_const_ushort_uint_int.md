# CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)

- ea: `0x18001d6e8`
- end: `0x18001d832`
- name: `?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z`
- size: `330`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c460`
- `0x18000f760`
- `0x18001d5e0`

## callees

- `0x18000bcc0`
- `0x1800171c4`
- `0x18001d6e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d707`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d7b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d707`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d7b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d78c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d78c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001d72c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001d7d2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001d72c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001d7d2`

## pseudocode

```c
__int64 __fastcall CoerceAnsiStrToWideStr(LPCCH lpMultiByteStr, unsigned __int16 **a2, __int64 a3, UINT a4)
{
  unsigned int v6; // eax
  int cchWideChar; // esi
  signed int LastError; // eax
  signed int v9; // ebx
  HRESULT v10; // eax
  int v11; // ecx
  WCHAR *lpWideCharStr; // rdi
  signed int v13; // eax
  UINT puResult; // [rsp+68h] [rbp+20h] BYREF

  puResult = a4;
  SetLastError(0);
  v6 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2003292268;
LABEL_12:
    if ( g_doStackCaptures )
    {
      v11 = v9;
      goto LABEL_14;
    }
    return (unsigned int)v9;
  }
  puResult = 0;
  v10 = ULongLongToUInt(2LL * v6, &puResult);
  v9 = v10;
  if ( v10 >= 0 )
  {
    lpWideCharStr = (WCHAR *)CoTaskMemAlloc(puResult);
    if ( lpWideCharStr )
    {
      SetLastError(0);
      v9 = 0;
      if ( !MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
      {
        v13 = GetLastError();
        v9 = v13;
        if ( v13 > 0 )
          v9 = (unsigned __int16)v13 | 0x80070000;
        if ( v9 >= 0 )
          v9 = -2003292268;
        if ( g_doStackCaptures )
          DoStackCapture(v9);
      }
      if ( v9 < 0 )
        CoTaskMemFree(lpWideCharStr);
      else
        *a2 = lpWideCharStr;
      return (unsigned int)v9;
    }
    v9 = -2147024882;
    goto LABEL_12;
  }
  if ( g_doStackCaptures )
  {
    v11 = v10;
LABEL_14:
    DoStackCapture(v11);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d6e8  mov     [rsp+arg_0], rbx
0x18001d6ed  mov     [rsp+arg_8], rbp
0x18001d6f2  mov     [rsp+puResult], r9d
0x18001d6f7  push    rsi
0x18001d6f8  push    rdi
0x18001d6f9  push    r14
0x18001d6fb  sub     rsp, 30h
0x18001d6ff  mov     rbp, rcx
0x18001d702  mov     r14, rdx
0x18001d705  xor     ecx, ecx; dwErrCode
0x18001d707  call    cs:__imp_SetLastError
0x18001d70d  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001d711  mov     [rsp+48h+cchWideChar], 0; cchWideChar
0x18001d719  mov     r8, rbp; lpMultiByteStr
0x18001d71c  mov     [rsp+48h+lpWideCharStr], 0; lpWideCharStr
0x18001d725  xor     edx, edx; dwFlags
0x18001d727  mov     ecx, 0FDE9h; CodePage
0x18001d72c  call    cs:__imp_MultiByteToWideChar
0x18001d732  mov     esi, eax
0x18001d734  test    eax, eax
0x18001d736  jnz     short loc_18001D759
0x18001d738  call    cs:__imp_GetLastError
0x18001d73e  mov     ebx, eax
0x18001d740  test    eax, eax
0x18001d742  jle     short loc_18001D74D
0x18001d744  movzx   ebx, ax
0x18001d747  or      ebx, 80070000h
0x18001d74d  test    ebx, ebx
0x18001d74f  mov     eax, 88982F94h
0x18001d754  cmovns  ebx, eax
0x18001d757  jmp     short loc_18001D79F
0x18001d759  mov     rcx, rsi
0x18001d75c  mov     [rsp+48h+puResult], 0
0x18001d764  add     rcx, rcx; ullOperand
0x18001d767  lea     rdx, [rsp+48h+puResult]; puResult
0x18001d76c  call    ULongLongToUInt
0x18001d771  mov     ebx, eax
0x18001d773  test    eax, eax
0x18001d775  jns     short loc_18001D788
0x18001d777  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001d77e  jz      loc_18001D81D
0x18001d784  mov     ecx, eax
0x18001d786  jmp     short loc_18001D7AA
0x18001d788  mov     ecx, [rsp+48h+puResult]; cb
0x18001d78c  call    cs:__imp_CoTaskMemAlloc
0x18001d792  mov     rdi, rax
0x18001d795  test    rax, rax
0x18001d798  jnz     short loc_18001D7B1
0x18001d79a  mov     ebx, 8007000Eh
0x18001d79f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001d7a6  jz      short loc_18001D81D
0x18001d7a8  mov     ecx, ebx; int
0x18001d7aa  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d7af  jmp     short loc_18001D81D
0x18001d7b1  xor     ecx, ecx; dwErrCode
0x18001d7b3  call    cs:__imp_SetLastError
0x18001d7b9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18001d7bd  mov     [rsp+48h+cchWideChar], esi; cchWideChar
0x18001d7c1  mov     r8, rbp; lpMultiByteStr
0x18001d7c4  mov     [rsp+48h+lpWideCharStr], rdi; lpWideCharStr
0x18001d7c9  xor     edx, edx; dwFlags
0x18001d7cb  mov     ecx, 0FDE9h; CodePage
0x18001d7d0  xor     ebx, ebx
0x18001d7d2  call    cs:__imp_MultiByteToWideChar
0x18001d7d8  test    eax, eax
0x18001d7da  jnz     short loc_18001D80B
0x18001d7dc  call    cs:__imp_GetLastError
0x18001d7e2  mov     ebx, eax
0x18001d7e4  test    eax, eax
0x18001d7e6  jle     short loc_18001D7F1
0x18001d7e8  movzx   ebx, ax
0x18001d7eb  or      ebx, 80070000h
0x18001d7f1  test    ebx, ebx
0x18001d7f3  mov     eax, 88982F94h
0x18001d7f8  cmovns  ebx, eax
0x18001d7fb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001d802  jz      short loc_18001D80B
0x18001d804  mov     ecx, ebx; int
0x18001d806  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d80b  test    ebx, ebx
0x18001d80d  js      short loc_18001D814
0x18001d80f  mov     [r14], rdi
0x18001d812  jmp     short loc_18001D81D
0x18001d814  mov     rcx, rdi; pv
0x18001d817  call    cs:__imp_CoTaskMemFree
0x18001d81d  mov     rbp, [rsp+48h+arg_8]
0x18001d822  mov     eax, ebx
0x18001d824  mov     rbx, [rsp+48h+arg_0]
0x18001d829  add     rsp, 30h
0x18001d82d  pop     r14
0x18001d82f  pop     rdi
0x18001d830  pop     rsi
0x18001d831  retn
```
