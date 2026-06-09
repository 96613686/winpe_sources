# _bidLdrIsPathLocal

- ea: `0x1800196ec`
- end: `0x180019801`
- name: `_bidLdrIsPathLocal`
- size: `277`
- prototype: `__int64 __fastcall(LPCWSTR lpRootPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180019808`

## callees

- `0x1800196ec`
- `0x18002e060`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800197b3`
- `msvcrt!wcsncpy_s` at `0x1800197b3`
- `KERNEL32!GetDriveTypeW` at `0x1800197c4`
- `KERNEL32!GetDriveTypeW` at `0x1800197c4`
- `KERNEL32!SearchPathW` at `0x18001978c`
- `KERNEL32!SearchPathW` at `0x18001978c`
- `KERNEL32!GetFullPathNameW` at `0x180019762`
- `KERNEL32!GetFullPathNameW` at `0x180019762`

## pseudocode

```c
_BOOL8 __fastcall bidLdrIsPathLocal(WCHAR *lpRootPathName)
{
  unsigned __int64 v2; // rax
  bool v3; // zf
  DWORD FullPathNameW; // eax
  WCHAR v5; // bx
  UINT DriveTypeW; // eax
  LPWSTR FilePart[2]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Buffer[272]; // [rsp+40h] [rbp-238h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( lpRootPathName[v2] );
  if ( v2 >= 3 )
  {
    if ( *lpRootPathName != 46 && (*lpRootPathName == 92 || *lpRootPathName == 47 || lpRootPathName[1] == 58) )
      goto LABEL_13;
    v3 = *lpRootPathName == 46;
    FilePart[0] = 0;
    if ( v3 )
      FullPathNameW = GetFullPathNameW(lpRootPathName, 0x10Eu, Buffer, FilePart);
    else
      FullPathNameW = SearchPathW(0, lpRootPathName, 0, 0x10Eu, Buffer, FilePart);
    if ( FullPathNameW - 1 <= 0x10C )
    {
      Buffer[269] = 0;
      wcsncpy_s(lpRootPathName, 0x10Eu, Buffer, 0xFFFFFFFFFFFFFFFFuLL);
LABEL_13:
      v5 = lpRootPathName[3];
      lpRootPathName[3] = 0;
      DriveTypeW = GetDriveTypeW(lpRootPathName);
      lpRootPathName[3] = v5;
      return DriveTypeW == 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800196ec  mov     [rsp+arg_8], rbx
0x1800196f1  mov     [rsp+arg_10], rsi
0x1800196f6  push    rdi
0x1800196f7  sub     rsp, 270h
0x1800196fe  mov     rax, cs:__security_cookie
0x180019705  xor     rax, rsp
0x180019708  mov     [rsp+278h+var_18], rax
0x180019710  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180019714  mov     rdi, rcx
0x180019717  mov     rax, rbx
0x18001971a  xor     esi, esi
0x18001971c  inc     rax
0x18001971f  cmp     [rcx+rax*2], si
0x180019723  jnz     short loc_18001971C
0x180019725  cmp     rax, 3
0x180019729  jb      loc_1800197DA
0x18001972f  cmp     word ptr [rcx], 2Eh ; '.'
0x180019733  jz      short loc_180019748
0x180019735  cmp     word ptr [rcx], 5Ch ; '\'
0x180019739  jz      short loc_1800197B9
0x18001973b  cmp     word ptr [rcx], 2Fh ; '/'
0x18001973f  jz      short loc_1800197B9
0x180019741  cmp     word ptr [rcx+2], 3Ah ; ':'
0x180019746  jz      short loc_1800197B9
0x180019748  cmp     word ptr [rcx], 2Eh ; '.'
0x18001974c  mov     [rsp+278h+FilePart], rsi
0x180019751  jnz     short loc_18001976A
0x180019753  lea     r9, [rsp+278h+FilePart]; lpFilePart
0x180019758  mov     edx, 10Eh; nBufferLength
0x18001975d  lea     r8, [rsp+278h+Buffer]; lpBuffer
0x180019762  call    cs:__imp_GetFullPathNameW
0x180019768  jmp     short loc_180019792
0x18001976a  lea     rax, [rsp+278h+FilePart]
0x18001976f  mov     r9d, 10Eh; nBufferLength
0x180019775  mov     [rsp+278h+lpFilePart], rax; lpFilePart
0x18001977a  xor     r8d, r8d; lpExtension
0x18001977d  lea     rax, [rsp+278h+Buffer]
0x180019782  mov     rdx, rdi; lpFileName
0x180019785  xor     ecx, ecx; lpPath
0x180019787  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001978c  call    cs:__imp_SearchPathW
0x180019792  dec     eax
0x180019794  cmp     eax, 10Ch
0x180019799  ja      short loc_1800197DA
0x18001979b  mov     r9, rbx; MaxCount
0x18001979e  mov     [rsp+278h+var_1E], si
0x1800197a6  lea     r8, [rsp+278h+Buffer]; Source
0x1800197ab  mov     edx, 10Eh; SizeInWords
0x1800197b0  mov     rcx, rdi; Destination
0x1800197b3  call    cs:__imp_wcsncpy_s
0x1800197b9  movzx   ebx, word ptr [rdi+6]
0x1800197bd  mov     rcx, rdi; lpRootPathName
0x1800197c0  mov     [rdi+6], si
0x1800197c4  call    cs:__imp_GetDriveTypeW
0x1800197ca  mov     ecx, esi
0x1800197cc  mov     [rdi+6], bx
0x1800197d0  cmp     eax, 3
0x1800197d3  setz    cl
0x1800197d6  mov     eax, ecx
0x1800197d8  jmp     short loc_1800197DC
0x1800197da  xor     eax, eax
0x1800197dc  mov     rcx, [rsp+278h+var_18]
0x1800197e4  xor     rcx, rsp; StackCookie
0x1800197e7  call    __security_check_cookie
0x1800197ec  lea     r11, [rsp+278h+var_8]
0x1800197f4  mov     rbx, [r11+18h]
0x1800197f8  mov     rsi, [r11+20h]
0x1800197fc  mov     rsp, r11
0x1800197ff  pop     rdi
0x180019800  retn
```
