# CoerceAnsiStrToWideStr(char const *,ushort * *,uint,int)

- ea: `0x180087ee0`
- end: `0x180088037`
- name: `?CoerceAnsiStrToWideStr@@YAJPEBDPEAPEAGIH@Z`
- size: `343`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180087d30`
- `0x1800d9e00`

## callees

- `0x180087ee0`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087ef3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087f90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087ef3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180087f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180087f70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180087f70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180088006`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087f1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087fb5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087f1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180087fb5`

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
0x180087ee0  push    rbx
0x180087ee2  push    rbp
0x180087ee3  push    rsi
0x180087ee4  push    rdi
0x180087ee5  push    r14
0x180087ee7  sub     rsp, 30h
0x180087eeb  mov     rbp, rcx
0x180087eee  mov     r14, rdx
0x180087ef1  xor     ecx, ecx; dwErrCode
0x180087ef3  call    cs:__imp_SetLastError
0x180087efa  nop     dword ptr [rax+rax+00h]
0x180087eff  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180087f03  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x180087f0b  mov     r8, rbp; lpMultiByteStr
0x180087f0e  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x180087f17  xor     edx, edx; dwFlags
0x180087f19  mov     ecx, 0FDE9h; CodePage
0x180087f1e  call    cs:__imp_MultiByteToWideChar
0x180087f25  nop     dword ptr [rax+rax+00h]
0x180087f2a  mov     esi, eax
0x180087f2c  test    eax, eax
0x180087f2e  jnz     short loc_180087F5A
0x180087f30  call    cs:__imp_GetLastError
0x180087f37  nop     dword ptr [rax+rax+00h]
0x180087f3c  mov     ebx, eax
0x180087f3e  test    eax, eax
0x180087f40  jle     short loc_180087F4B
0x180087f42  movzx   ebx, ax
0x180087f45  or      ebx, 80070000h
0x180087f4b  test    ebx, ebx
0x180087f4d  mov     eax, 88982F94h
0x180087f52  cmovns  ebx, eax
0x180087f55  jmp     loc_180088019
0x180087f5a  mov     rax, rsi
0x180087f5d  mov     ecx, 0FFFFFFFFh
0x180087f62  add     rax, rax
0x180087f65  cmp     rax, rcx
0x180087f68  ja      loc_180088014
0x180087f6e  mov     ecx, eax; cb
0x180087f70  call    cs:__imp_CoTaskMemAlloc
0x180087f77  nop     dword ptr [rax+rax+00h]
0x180087f7c  mov     rdi, rax
0x180087f7f  test    rax, rax
0x180087f82  jnz     short loc_180087F8E
0x180087f84  mov     ebx, 8007000Eh
0x180087f89  jmp     loc_180088019
0x180087f8e  xor     ecx, ecx; dwErrCode
0x180087f90  call    cs:__imp_SetLastError
0x180087f97  nop     dword ptr [rax+rax+00h]
0x180087f9c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180087fa0  mov     [rsp+58h+cchWideChar], esi; cchWideChar
0x180087fa4  mov     r8, rbp; lpMultiByteStr
0x180087fa7  mov     [rsp+58h+lpWideCharStr], rdi; lpWideCharStr
0x180087fac  xor     edx, edx; dwFlags
0x180087fae  mov     ecx, 0FDE9h; CodePage
0x180087fb3  xor     ebx, ebx
0x180087fb5  call    cs:__imp_MultiByteToWideChar
0x180087fbc  nop     dword ptr [rax+rax+00h]
0x180087fc1  test    eax, eax
0x180087fc3  jnz     short loc_180087FFA
0x180087fc5  call    cs:__imp_GetLastError
0x180087fcc  nop     dword ptr [rax+rax+00h]
0x180087fd1  mov     ebx, eax
0x180087fd3  test    eax, eax
0x180087fd5  jle     short loc_180087FE0
0x180087fd7  movzx   ebx, ax
0x180087fda  or      ebx, 80070000h
0x180087fe0  test    ebx, ebx
0x180087fe2  mov     eax, 88982F94h
0x180087fe7  cmovns  ebx, eax
0x180087fea  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180087ff1  jz      short loc_180087FFA
0x180087ff3  mov     ecx, ebx; int
0x180087ff5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180087ffa  test    ebx, ebx
0x180087ffc  js      short loc_180088003
0x180087ffe  mov     [r14], rdi
0x180088001  jmp     short loc_180088029
0x180088003  mov     rcx, rdi; pv
0x180088006  call    cs:__imp_CoTaskMemFree
0x18008800d  nop     dword ptr [rax+rax+00h]
0x180088012  jmp     short loc_180088029
0x180088014  mov     ebx, 80070216h
0x180088019  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180088020  jz      short loc_180088029
0x180088022  mov     ecx, ebx; int
0x180088024  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180088029  mov     eax, ebx
0x18008802b  add     rsp, 30h
0x18008802f  pop     r14
0x180088031  pop     rdi
0x180088032  pop     rsi
0x180088033  pop     rbp
0x180088034  pop     rbx
0x180088035  retn
```
