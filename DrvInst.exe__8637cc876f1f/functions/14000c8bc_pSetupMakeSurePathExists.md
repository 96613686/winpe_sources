# pSetupMakeSurePathExists

- ea: `0x14000c8bc`
- end: `0x14000cabc`
- name: `pSetupMakeSurePathExists`
- size: `512`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x14000aab0`
- `0x14000e938`
- `0x14002e91c`

## callees

- `0x14000c8bc`
- `0x140045f30`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000ca18`
- `msvcrt!wcsrchr` at `0x14000ca18`
- `msvcrt!wcschr` at `0x14000c993`
- `msvcrt!wcschr` at `0x14000c9a9`
- `msvcrt!wcschr` at `0x14000c993`
- `msvcrt!wcschr` at `0x14000c9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c919`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000ca5b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000ca5b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c9c0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000ca34`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000c9c0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000ca34`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000c907`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14000c907`

## pseudocode

```c
DWORD __fastcall pSetupMakeSurePathExists(const WCHAR *a1)
{
  DWORD FullPathNameW; // eax
  wchar_t *v3; // rsi
  wchar_t *v4; // rax
  DWORD FileAttributesW; // eax
  WCHAR *p_Buffer; // rdi
  wchar_t *v7; // rax
  wchar_t *v8; // r14
  wchar_t v9; // bx
  DWORD v10; // eax
  __int64 v11; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v14; // [rsp+32h] [rbp-CEh]
  wchar_t Str[262]; // [rsp+34h] [rbp-CCh] BYREF

  FilePart = 0;
  FullPathNameW = GetFullPathNameW(a1, 0x104u, &Buffer, &FilePart);
  if ( FullPathNameW >= 0x104 )
    return 123;
  if ( !FullPathNameW )
    return GetLastError();
  if ( !FilePart || FilePart == &Buffer )
    return 123;
  *FilePart = 0;
  v3 = 0;
  if ( ((unsigned __int16)(Buffer - 65) <= 0x19u || (unsigned __int16)(Buffer - 97) <= 0x19u) && v14 == 58 )
  {
    if ( Str[0] != 92 )
      return 123;
    v3 = Str;
  }
  if ( Buffer == 92 && v14 == 92 )
  {
    v4 = wcschr(Str, 0x5Cu);
    if ( !v4 )
      return 123;
    v3 = wcschr(v4 + 1, 0x5Cu);
    if ( !v3 )
      return 123;
  }
  FileAttributesW = GetFileAttributesW(&Buffer);
  if ( FileAttributesW == -1 )
  {
    if ( FilePart == &Buffer )
      p_Buffer = &Buffer;
    else
      p_Buffer = FilePart - 1;
    if ( p_Buffer != v3 && *p_Buffer == 92 )
    {
      while ( p_Buffer > v3 )
      {
        *p_Buffer = 0;
        v7 = wcsrchr(&Buffer, 0x5Cu);
        v8 = v7;
        if ( !v7 )
          break;
        v9 = v7[1];
        v7[1] = 0;
        v10 = GetFileAttributesW(&Buffer);
        v8[1] = v9;
        if ( v10 != -1 )
        {
          if ( (v10 & 0x10) == 0 )
            return 267;
          while ( CreateDirectoryW(&Buffer, 0) )
          {
            if ( !p_Buffer[1] )
              return 0;
            *p_Buffer = 92;
            v11 = -1;
            do
              ++v11;
            while ( p_Buffer[v11] );
            p_Buffer += v11;
          }
          return GetLastError();
        }
        p_Buffer = v8;
      }
    }
    return 123;
  }
  if ( (FileAttributesW & 0x10) != 0 )
    return 0;
  else
    return 267;
}

```

## disassembly

```asm
0x14000c8bc  mov     [rsp-8+arg_8], rbx
0x14000c8c1  mov     [rsp-8+arg_10], rsi
0x14000c8c6  push    rbp
0x14000c8c7  push    rdi
0x14000c8c8  push    r12
0x14000c8ca  push    r14
0x14000c8cc  push    r15
0x14000c8ce  lea     rbp, [rsp-150h]
0x14000c8d6  sub     rsp, 250h
0x14000c8dd  mov     rax, cs:__security_cookie
0x14000c8e4  xor     rax, rsp
0x14000c8e7  mov     [rbp+170h+var_30], rax
0x14000c8ee  mov     ebx, 104h
0x14000c8f3  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x14000c8f8  xor     r15d, r15d
0x14000c8fb  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x14000c900  mov     edx, ebx; nBufferLength
0x14000c902  mov     [rsp+270h+FilePart], r15
0x14000c907  call    cs:__imp_GetFullPathNameW
0x14000c90d  cmp     eax, ebx
0x14000c90f  jnb     loc_14000CA8C
0x14000c915  test    eax, eax
0x14000c917  jnz     short loc_14000C924
0x14000c919  call    cs:__imp_GetLastError
0x14000c91f  jmp     loc_14000CA91
0x14000c924  mov     rcx, [rsp+270h+FilePart]
0x14000c929  test    rcx, rcx
0x14000c92c  jz      loc_14000CA8C
0x14000c932  lea     rax, [rsp+270h+Buffer]
0x14000c937  cmp     rcx, rax
0x14000c93a  jz      loc_14000CA8C
0x14000c940  mov     [rcx], r15w
0x14000c944  mov     rsi, r15
0x14000c947  movzx   ecx, [rsp+270h+Buffer]
0x14000c94c  mov     r12d, 5Ch ; '\'
0x14000c952  lea     eax, [rcx-41h]
0x14000c955  cmp     ax, 19h
0x14000c959  jbe     short loc_14000C964
0x14000c95b  lea     eax, [rcx-61h]
0x14000c95e  cmp     ax, 19h
0x14000c962  ja      short loc_14000C97D
0x14000c964  cmp     [rsp+270h+var_23E], 3Ah ; ':'
0x14000c96a  jnz     short loc_14000C97D
0x14000c96c  cmp     [rsp+270h+Str], r12w
0x14000c972  jnz     loc_14000CA8C
0x14000c978  lea     rsi, [rsp+270h+Str]
0x14000c97d  cmp     cx, r12w
0x14000c981  jnz     short loc_14000C9BB
0x14000c983  cmp     [rsp+270h+var_23E], r12w
0x14000c989  jnz     short loc_14000C9BB
0x14000c98b  mov     edx, r12d; Ch
0x14000c98e  lea     rcx, [rsp+270h+Str]; Str
0x14000c993  call    cs:__imp_wcschr
0x14000c999  test    rax, rax
0x14000c99c  jz      loc_14000CA8C
0x14000c9a2  mov     edx, r12d; Ch
0x14000c9a5  lea     rcx, [rax+2]; Str
0x14000c9a9  call    cs:__imp_wcschr
0x14000c9af  mov     rsi, rax
0x14000c9b2  test    rax, rax
0x14000c9b5  jz      loc_14000CA8C
0x14000c9bb  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x14000c9c0  call    cs:__imp_GetFileAttributesW
0x14000c9c6  cmp     eax, 0FFFFFFFFh
0x14000c9c9  jz      short loc_14000C9D6
0x14000c9cb  test    al, 10h
0x14000c9cd  jz      short loc_14000CA4D
0x14000c9cf  xor     eax, eax
0x14000c9d1  jmp     loc_14000CA91
0x14000c9d6  mov     rdi, [rsp+270h+FilePart]
0x14000c9db  lea     rax, [rsp+270h+Buffer]
0x14000c9e0  cmp     rdi, rax
0x14000c9e3  jnz     short loc_14000C9EC
0x14000c9e5  lea     rdi, [rsp+270h+Buffer]
0x14000c9ea  jmp     short loc_14000C9F0
0x14000c9ec  add     rdi, 0FFFFFFFFFFFFFFFEh
0x14000c9f0  cmp     rdi, rsi
0x14000c9f3  jz      loc_14000CA8C
0x14000c9f9  cmp     [rdi], r12w
0x14000c9fd  jnz     loc_14000CA8C
0x14000ca03  cmp     rdi, rsi
0x14000ca06  jbe     loc_14000CA8C
0x14000ca0c  mov     edx, r12d; Ch
0x14000ca0f  mov     [rdi], r15w
0x14000ca13  lea     rcx, [rsp+270h+Buffer]; Str
0x14000ca18  call    cs:__imp_wcsrchr
0x14000ca1e  mov     r14, rax
0x14000ca21  test    rax, rax
0x14000ca24  jz      short loc_14000CA8C
0x14000ca26  movzx   ebx, word ptr [rax+2]
0x14000ca2a  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x14000ca2f  mov     [rax+2], r15w
0x14000ca34  call    cs:__imp_GetFileAttributesW
0x14000ca3a  mov     [r14+2], bx
0x14000ca3f  cmp     eax, 0FFFFFFFFh
0x14000ca42  jnz     short loc_14000CA49
0x14000ca44  mov     rdi, r14
0x14000ca47  jmp     short loc_14000CA03
0x14000ca49  test    al, 10h
0x14000ca4b  jnz     short loc_14000CA54
0x14000ca4d  mov     eax, 10Bh
0x14000ca52  jmp     short loc_14000CA91
0x14000ca54  xor     edx, edx; lpSecurityAttributes
0x14000ca56  lea     rcx, [rsp+270h+Buffer]; lpPathName
0x14000ca5b  call    cs:__imp_CreateDirectoryW
0x14000ca61  test    eax, eax
0x14000ca63  jz      loc_14000C919
0x14000ca69  cmp     [rdi+2], r15w
0x14000ca6e  jz      loc_14000C9CF
0x14000ca74  mov     [rdi], r12w
0x14000ca78  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ca7c  inc     rax
0x14000ca7f  cmp     [rdi+rax*2], r15w
0x14000ca84  jnz     short loc_14000CA7C
0x14000ca86  lea     rdi, [rdi+rax*2]
0x14000ca8a  jmp     short loc_14000CA54
0x14000ca8c  mov     eax, 7Bh ; '{'
0x14000ca91  mov     rcx, [rbp+170h+var_30]
0x14000ca98  xor     rcx, rsp; StackCookie
0x14000ca9b  call    __security_check_cookie
0x14000caa0  lea     r11, [rsp+270h+var_20]
0x14000caa8  mov     rbx, [r11+38h]
0x14000caac  mov     rsi, [r11+40h]
0x14000cab0  mov     rsp, r11
0x14000cab3  pop     r15
0x14000cab5  pop     r14
0x14000cab7  pop     r12
0x14000cab9  pop     rdi
0x14000caba  pop     rbp
0x14000cabb  retn
```
