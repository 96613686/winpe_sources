# CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)

- ea: `0x180087780`
- end: `0x1800878a3`
- name: `?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z`
- size: `291`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **, unsigned int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800875f0`
- `0x1800d7300`

## callees

- `0x180087780`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087815`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087793`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800877c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008783e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800877c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008783e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800877fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800877fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087879`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800877b8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087834`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800877b8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087834`

## pseudocode

```c
__int64 __fastcall CoerceAnsiStrToWideStr(LPCCH lpMultiByteStr, unsigned __int16 **a2)
{
  unsigned int v4; // eax
  __int64 cchWideChar; // rsi
  signed int LastError; // eax
  signed int v7; // ebx
  unsigned int v8; // eax
  WCHAR *lpWideCharStr; // rdi
  signed int v10; // eax

  SetLastError(0);
  v4 = MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2003292268;
    goto LABEL_21;
  }
  v8 = 2 * v4;
  if ( (unsigned __int64)(2 * cchWideChar) > 0xFFFFFFFF )
  {
    v7 = -2147024362;
LABEL_21:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v7);
    return (unsigned int)v7;
  }
  lpWideCharStr = (WCHAR *)CoTaskMemAlloc(v8);
  if ( !lpWideCharStr )
  {
    v7 = -2147024882;
    goto LABEL_21;
  }
  SetLastError(0);
  v7 = 0;
  if ( !MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
  {
    v10 = GetLastError();
    v7 = v10;
    if ( v10 > 0 )
      v7 = (unsigned __int16)v10 | 0x80070000;
    if ( v7 >= 0 )
      v7 = -2003292268;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v7);
  }
  if ( v7 < 0 )
    CoTaskMemFree(lpWideCharStr);
  else
    *a2 = lpWideCharStr;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180087780  push    rbx
0x180087782  push    rbp
0x180087783  push    rsi
0x180087784  push    rdi
0x180087785  push    r14
0x180087787  sub     rsp, 30h
0x18008778b  mov     rbp, rcx
0x18008778e  mov     r14, rdx
0x180087791  xor     ecx, ecx; dwErrCode
0x180087793  call    cs:__imp_SetLastError
0x180087799  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18008779d  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x1800877a5  mov     r8, rbp; lpMultiByteStr
0x1800877a8  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x1800877b1  xor     edx, edx; dwFlags
0x1800877b3  mov     ecx, 0FDE9h; CodePage
0x1800877b8  call    cs:__imp_MultiByteToWideChar
0x1800877be  mov     esi, eax
0x1800877c0  test    eax, eax
0x1800877c2  jnz     short loc_1800877E8
0x1800877c4  call    cs:__imp_GetLastError
0x1800877ca  mov     ebx, eax
0x1800877cc  test    eax, eax
0x1800877ce  jle     short loc_1800877D9
0x1800877d0  movzx   ebx, ax
0x1800877d3  or      ebx, 80070000h
0x1800877d9  test    ebx, ebx
0x1800877db  mov     eax, 88982F94h
0x1800877e0  cmovns  ebx, eax
0x1800877e3  jmp     loc_180087886
0x1800877e8  mov     rax, rsi
0x1800877eb  mov     ecx, 0FFFFFFFFh
0x1800877f0  add     rax, rax
0x1800877f3  cmp     rax, rcx
0x1800877f6  ja      loc_180087881
0x1800877fc  mov     ecx, eax; cb
0x1800877fe  call    cs:__imp_CoTaskMemAlloc
0x180087804  mov     rdi, rax
0x180087807  test    rax, rax
0x18008780a  jnz     short loc_180087813
0x18008780c  mov     ebx, 8007000Eh
0x180087811  jmp     short loc_180087886
0x180087813  xor     ecx, ecx; dwErrCode
0x180087815  call    cs:__imp_SetLastError
0x18008781b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18008781f  mov     [rsp+58h+cchWideChar], esi; cchWideChar
0x180087823  mov     r8, rbp; lpMultiByteStr
0x180087826  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x18008782b  xor     edx, edx; dwFlags
0x18008782d  mov     ecx, 0FDE9h; CodePage
0x180087832  xor     ebx, ebx
0x180087834  call    cs:__imp_MultiByteToWideChar
0x18008783a  test    eax, eax
0x18008783c  jnz     short loc_18008786D
0x18008783e  call    cs:__imp_GetLastError
0x180087844  mov     ebx, eax
0x180087846  test    eax, eax
0x180087848  jle     short loc_180087853
0x18008784a  movzx   ebx, ax
0x18008784d  or      ebx, 80070000h
0x180087853  test    ebx, ebx
0x180087855  mov     eax, 88982F94h
0x18008785a  cmovns  ebx, eax
0x18008785d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180087864  jz      short loc_18008786D
0x180087866  mov     ecx, ebx; int
0x180087868  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008786d  test    ebx, ebx
0x18008786f  js      short loc_180087876
0x180087871  mov     [r14], rdi
0x180087874  jmp     short loc_180087896
0x180087876  mov     rcx, rdi; pv
0x180087879  call    cs:__imp_CoTaskMemFree
0x18008787f  jmp     short loc_180087896
0x180087881  mov     ebx, 80070216h
0x180087886  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18008788d  jz      short loc_180087896
0x18008788f  mov     ecx, ebx; int
0x180087891  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180087896  mov     eax, ebx
0x180087898  add     rsp, 30h
0x18008789c  pop     r14
0x18008789e  pop     rdi
0x18008789f  pop     rsi
0x1800878a0  pop     rbp
0x1800878a1  pop     rbx
0x1800878a2  retn
```
