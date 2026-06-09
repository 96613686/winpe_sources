# sub_1800A3BDC

- ea: `0x1800a3bdc`
- end: `0x1800a3d15`
- name: `sub_1800A3BDC`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a2b84`

## callees

- `0x1800048f0`
- `0x1800057e4`
- `0x18001d80c`
- `0x18009fd10`
- `0x1800a3bdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__fseeki64` at `0x1800a3c18`
- `api-ms-win-crt-private-l1-1-0!_o__fseeki64` at `0x1800a3c18`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a3c6e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800a3c6e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a3c9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a3cd9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a3c9d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800a3cd9`

## string_xrefs

- `0x1800a3ca5`: `Failed to write archive header to file.`

## pseudocode

```c
__int64 __fastcall sub_1800A3BDC(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  __int64 result; // rax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  _QWORD v12[4]; // [rsp+20h] [rbp-89h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v14[10]; // [rsp+90h] [rbp-19h] BYREF

  v4 = a4;
  v5 = a3;
  if ( (unsigned int)o__fseeki64(a2, 0, 0) )
  {
    v11 = *(_DWORD *)o__errno(0);
    sub_18001D80C(v12, L"File seek failed.");
    sub_18009FD10(pExceptionObject, v12, v11);
    throw (Uev::PackageArchiveException *)pExceptionObject;
  }
  v14[0] = 0x4418270605182312LL;
  v14[1] = *(_QWORD *)(a1 + 96) + 72LL;
  v14[2] = 1;
  v14[3] = 0;
  v14[4] = v4;
  v14[5] = v5;
  memset(&v14[6], 0, 24);
  result = o_fwrite(v14, 72, 1, a2);
  if ( result != 1 )
  {
    v10 = *(_DWORD *)o__errno(v9);
    sub_18001D80C(v12, L"Failed to write archive header to file.");
    sub_18009FD10(pExceptionObject, v12, v10);
    throw (Uev::PackageArchiveException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800a3bdc  mov     [rsp-8+arg_0], rbx
0x1800a3be1  mov     [rsp-8+arg_10], rsi
0x1800a3be6  push    rbp
0x1800a3be7  push    rdi
0x1800a3be8  push    r14
0x1800a3bea  lea     rbp, [rsp-47h]
0x1800a3bef  sub     rsp, 0F0h
0x1800a3bf6  mov     rax, cs:__security_cookie
0x1800a3bfd  xor     rax, rsp
0x1800a3c00  mov     [rbp+57h+var_20], rax
0x1800a3c04  mov     edi, r9d
0x1800a3c07  mov     esi, r8d
0x1800a3c0a  mov     rbx, rdx
0x1800a3c0d  mov     r14, rcx
0x1800a3c10  xor     r8d, r8d
0x1800a3c13  xor     edx, edx
0x1800a3c15  mov     rcx, rbx
0x1800a3c18  call    cs:_o__fseeki64
0x1800a3c1e  xor     ecx, ecx
0x1800a3c20  test    eax, eax
0x1800a3c22  jnz     loc_1800A3CD9
0x1800a3c28  mov     rax, 4418270605182312h
0x1800a3c32  mov     [rbp+57h+var_70], rax
0x1800a3c36  mov     rax, [r14+60h]
0x1800a3c3a  lea     edx, [rcx+48h]
0x1800a3c3d  add     rax, rdx
0x1800a3c40  mov     [rbp+57h+var_68], rax
0x1800a3c44  lea     r14d, [rcx+1]
0x1800a3c48  mov     [rbp+57h+var_60], r14
0x1800a3c4c  mov     [rbp+57h+var_58], rcx
0x1800a3c50  mov     [rbp+57h+var_50], rdi
0x1800a3c54  mov     [rbp+57h+var_48], rsi
0x1800a3c58  mov     [rbp+57h+var_40], rcx
0x1800a3c5c  mov     [rbp+57h+var_38], rcx
0x1800a3c60  mov     [rbp+57h+var_30], rcx
0x1800a3c64  mov     r9, rbx
0x1800a3c67  mov     r8d, r14d
0x1800a3c6a  lea     rcx, [rbp+57h+var_70]
0x1800a3c6e  call    cs:_o_fwrite
0x1800a3c74  cmp     rax, r14
0x1800a3c77  jnz     short loc_1800A3C9D
0x1800a3c79  mov     rcx, [rbp+57h+var_20]
0x1800a3c7d  xor     rcx, rsp; StackCookie
0x1800a3c80  call    __security_check_cookie
0x1800a3c85  lea     r11, [rsp+100h+var_10]
0x1800a3c8d  mov     rbx, [r11+20h]
0x1800a3c91  mov     rsi, [r11+30h]
0x1800a3c95  mov     rsp, r11
0x1800a3c98  pop     r14
0x1800a3c9a  pop     rdi
0x1800a3c9b  pop     rbp
0x1800a3c9c  retn
0x1800a3c9d  call    cs:_o__errno
0x1800a3ca3  mov     ebx, [rax]
0x1800a3ca5  lea     rdx, aFailedToWriteA; "Failed to write archive header to file."
0x1800a3cac  lea     rcx, [rsp+100h+var_E0]
0x1800a3cb1  call    sub_18001D80C
0x1800a3cb6  nop
0x1800a3cb7  mov     r8d, ebx
0x1800a3cba  lea     rdx, [rsp+100h+var_E0]
0x1800a3cbf  lea     rcx, [rbp+57h+pExceptionObject]
0x1800a3cc3  call    sub_18009FD10
0x1800a3cc8  lea     rdx, __TI4?AVPackageArchiveException@Uev@@; pThrowInfo
0x1800a3ccf  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800a3cd3  call    _CxxThrowException
0x1800a3cd9  call    cs:_o__errno
0x1800a3cdf  mov     ebx, [rax]
0x1800a3ce1  lea     rdx, aFileSeekFailed; "File seek failed."
0x1800a3ce8  lea     rcx, [rsp+100h+var_E0]
0x1800a3ced  call    sub_18001D80C
0x1800a3cf2  nop
0x1800a3cf3  mov     r8d, ebx
0x1800a3cf6  lea     rdx, [rsp+100h+var_E0]
0x1800a3cfb  lea     rcx, [rbp+57h+pExceptionObject]
0x1800a3cff  call    sub_18009FD10
0x1800a3d04  lea     rdx, __TI4?AVPackageArchiveException@Uev@@; pThrowInfo
0x1800a3d0b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800a3d0f  call    _CxxThrowException
```
