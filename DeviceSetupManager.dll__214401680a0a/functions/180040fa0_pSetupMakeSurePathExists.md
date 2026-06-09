# pSetupMakeSurePathExists

- ea: `0x180040fa0`
- end: `0x1800411a0`
- name: `pSetupMakeSurePathExists`
- size: `512`
- prototype: `DWORD __fastcall(const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180040c78`
- `0x1800415e4`

## callees

- `0x18001af70`
- `0x180040fa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180041077`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004108d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180041077`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18004108d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800410fc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800410fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ffd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800410a4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180041118`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800410a4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180041118`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180040feb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180040feb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004113f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004113f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180040fa0  mov     [rsp-8+arg_8], rbx
0x180040fa5  mov     [rsp-8+arg_10], rsi
0x180040faa  push    rbp
0x180040fab  push    rdi
0x180040fac  push    r12
0x180040fae  push    r14
0x180040fb0  push    r15
0x180040fb2  lea     rbp, [rsp-150h]
0x180040fba  sub     rsp, 250h
0x180040fc1  mov     rax, cs:__security_cookie
0x180040fc8  xor     rax, rsp
0x180040fcb  mov     [rbp+170h+var_30], rax
0x180040fd2  mov     ebx, 104h
0x180040fd7  lea     r9, [rsp+270h+FilePart]; lpFilePart
0x180040fdc  xor     r15d, r15d
0x180040fdf  lea     r8, [rsp+270h+Buffer]; lpBuffer
0x180040fe4  mov     edx, ebx; nBufferLength
0x180040fe6  mov     [rsp+270h+FilePart], r15
0x180040feb  call    cs:__imp_GetFullPathNameW
0x180040ff1  cmp     eax, ebx
0x180040ff3  jnb     loc_180041170
0x180040ff9  test    eax, eax
0x180040ffb  jnz     short loc_180041008
0x180040ffd  call    cs:__imp_GetLastError
0x180041003  jmp     loc_180041175
0x180041008  mov     rcx, [rsp+270h+FilePart]
0x18004100d  test    rcx, rcx
0x180041010  jz      loc_180041170
0x180041016  lea     rax, [rsp+270h+Buffer]
0x18004101b  cmp     rcx, rax
0x18004101e  jz      loc_180041170
0x180041024  mov     [rcx], r15w
0x180041028  mov     rsi, r15
0x18004102b  movzx   ecx, [rsp+270h+Buffer]
0x180041030  mov     r12d, 5Ch ; '\'
0x180041036  lea     eax, [rcx-41h]
0x180041039  cmp     ax, 19h
0x18004103d  jbe     short loc_180041048
0x18004103f  lea     eax, [rcx-61h]
0x180041042  cmp     ax, 19h
0x180041046  ja      short loc_180041061
0x180041048  cmp     [rsp+270h+var_23E], 3Ah ; ':'
0x18004104e  jnz     short loc_180041061
0x180041050  cmp     [rsp+270h+Str], r12w
0x180041056  jnz     loc_180041170
0x18004105c  lea     rsi, [rsp+270h+Str]
0x180041061  cmp     cx, r12w
0x180041065  jnz     short loc_18004109F
0x180041067  cmp     [rsp+270h+var_23E], r12w
0x18004106d  jnz     short loc_18004109F
0x18004106f  mov     edx, r12d; Ch
0x180041072  lea     rcx, [rsp+270h+Str]; Str
0x180041077  call    cs:__imp_wcschr
0x18004107d  test    rax, rax
0x180041080  jz      loc_180041170
0x180041086  mov     edx, r12d; Ch
0x180041089  lea     rcx, [rax+2]; Str
0x18004108d  call    cs:__imp_wcschr
0x180041093  mov     rsi, rax
0x180041096  test    rax, rax
0x180041099  jz      loc_180041170
0x18004109f  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x1800410a4  call    cs:__imp_GetFileAttributesW
0x1800410aa  cmp     eax, 0FFFFFFFFh
0x1800410ad  jz      short loc_1800410BA
0x1800410af  test    al, 10h
0x1800410b1  jz      short loc_180041131
0x1800410b3  xor     eax, eax
0x1800410b5  jmp     loc_180041175
0x1800410ba  mov     rdi, [rsp+270h+FilePart]
0x1800410bf  lea     rax, [rsp+270h+Buffer]
0x1800410c4  cmp     rdi, rax
0x1800410c7  jnz     short loc_1800410D0
0x1800410c9  lea     rdi, [rsp+270h+Buffer]
0x1800410ce  jmp     short loc_1800410D4
0x1800410d0  add     rdi, 0FFFFFFFFFFFFFFFEh
0x1800410d4  cmp     rdi, rsi
0x1800410d7  jz      loc_180041170
0x1800410dd  cmp     [rdi], r12w
0x1800410e1  jnz     loc_180041170
0x1800410e7  cmp     rdi, rsi
0x1800410ea  jbe     loc_180041170
0x1800410f0  mov     edx, r12d; Ch
0x1800410f3  mov     [rdi], r15w
0x1800410f7  lea     rcx, [rsp+270h+Buffer]; Str
0x1800410fc  call    cs:__imp_wcsrchr
0x180041102  mov     r14, rax
0x180041105  test    rax, rax
0x180041108  jz      short loc_180041170
0x18004110a  movzx   ebx, word ptr [rax+2]
0x18004110e  lea     rcx, [rsp+270h+Buffer]; lpFileName
0x180041113  mov     [rax+2], r15w
0x180041118  call    cs:__imp_GetFileAttributesW
0x18004111e  mov     [r14+2], bx
0x180041123  cmp     eax, 0FFFFFFFFh
0x180041126  jnz     short loc_18004112D
0x180041128  mov     rdi, r14
0x18004112b  jmp     short loc_1800410E7
0x18004112d  test    al, 10h
0x18004112f  jnz     short loc_180041138
0x180041131  mov     eax, 10Bh
0x180041136  jmp     short loc_180041175
0x180041138  xor     edx, edx; lpSecurityAttributes
0x18004113a  lea     rcx, [rsp+270h+Buffer]; lpPathName
0x18004113f  call    cs:__imp_CreateDirectoryW
0x180041145  test    eax, eax
0x180041147  jz      loc_180040FFD
0x18004114d  cmp     [rdi+2], r15w
0x180041152  jz      loc_1800410B3
0x180041158  mov     [rdi], r12w
0x18004115c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180041160  inc     rax
0x180041163  cmp     [rdi+rax*2], r15w
0x180041168  jnz     short loc_180041160
0x18004116a  lea     rdi, [rdi+rax*2]
0x18004116e  jmp     short loc_180041138
0x180041170  mov     eax, 7Bh ; '{'
0x180041175  mov     rcx, [rbp+170h+var_30]
0x18004117c  xor     rcx, rsp; StackCookie
0x18004117f  call    __security_check_cookie
0x180041184  lea     r11, [rsp+270h+var_20]
0x18004118c  mov     rbx, [r11+38h]
0x180041190  mov     rsi, [r11+40h]
0x180041194  mov     rsp, r11
0x180041197  pop     r15
0x180041199  pop     r14
0x18004119b  pop     r12
0x18004119d  pop     rdi
0x18004119e  pop     rbp
0x18004119f  retn
```
