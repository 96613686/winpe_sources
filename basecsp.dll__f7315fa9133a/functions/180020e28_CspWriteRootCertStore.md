# CspWriteRootCertStore

- ea: `0x180020e28`
- end: `0x180020fcb`
- name: `CspWriteRootCertStore`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013420`

## callees

- `0x18000de80`
- `0x180019430`
- `0x18001db2c`
- `0x18001dd04`
- `0x18001e398`
- `0x18001ebf4`
- `0x180020e28`
- `0x180027edc`
- `0x18002cfa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e8c`
- `CRYPT32!CertSaveStore` at `0x180020e82`
- `CRYPT32!CertSaveStore` at `0x180020ed1`
- `CRYPT32!CertSaveStore` at `0x180020e82`
- `CRYPT32!CertSaveStore` at `0x180020ed1`

## pseudocode

```c
__int64 __fastcall CspWriteRootCertStore(__int64 a1, void *a2)
{
  unsigned int LastError; // eax
  unsigned int File; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  void *v8; // rax
  size_t v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r9
  size_t v14; // [rsp+30h] [rbp-30h] BYREF
  size_t size[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  int v17; // [rsp+50h] [rbp-10h]

  LODWORD(v14) = 0;
  v16 = 0;
  v17 = 0;
  *(_OWORD *)size = 0;
  if ( !CertSaveStore(a2, 0x10001u, 2u, 2u, size, 0) )
    goto LABEL_2;
  size[1] = (size_t)MIDL_user_allocate(LODWORD(size[0]));
  if ( !size[1] )
  {
LABEL_4:
    File = 8;
    goto LABEL_15;
  }
  if ( !CertSaveStore(a2, 0x10001u, 2u, 2u, size, 0) )
  {
LABEL_2:
    LastError = GetLastError();
LABEL_14:
    File = LastError;
    goto LABEL_15;
  }
  File = CspQueryCapabilities(a1, &v16);
  if ( File )
    goto LABEL_15;
  if ( HIDWORD(v16) )
  {
LABEL_12:
    CspDeleteFile(a1, v6, v7, "msroots");
    File = CspCreateFile(a1, v10, "msroots", LODWORD(size[0]));
    if ( File )
      goto LABEL_15;
    LastError = CspWriteFile(a1, v11, "msroots", v12, (void *)size[1], size[0]);
    goto LABEL_14;
  }
  File = CompressData(LODWORD(size[0]), 0, &v14, 0);
  if ( File )
    goto LABEL_15;
  v8 = MIDL_user_allocate((unsigned int)v14);
  v9 = (size_t)v8;
  if ( !v8 )
    goto LABEL_4;
  File = CompressData(LODWORD(size[0]), size[1], &v14, v8);
  if ( !File )
  {
    CspFreeH(size[1]);
    LODWORD(size[0]) = v14;
    size[1] = v9;
    goto LABEL_12;
  }
  CspFreeH(v9);
LABEL_15:
  if ( size[1] )
    CspFreeH(size[1]);
  return File;
}

```

## disassembly

```asm
0x180020e28  mov     [rsp-18h+arg_10], rbx
0x180020e2d  push    rbp
0x180020e2e  push    rsi
0x180020e2f  push    rdi
0x180020e30  mov     rbp, rsp
0x180020e33  sub     rsp, 60h
0x180020e37  mov     rax, cs:__security_cookie
0x180020e3e  xor     rax, rsp
0x180020e41  mov     [rbp+var_8], rax
0x180020e45  xor     eax, eax
0x180020e47  mov     dword ptr [rbp+var_30], 0
0x180020e4e  mov     [rsp+60h+dwFlags], eax; dwFlags
0x180020e52  mov     rbx, rdx
0x180020e55  mov     [rbp+var_18], rax
0x180020e59  mov     edi, 2
0x180020e5e  mov     [rbp+var_10], eax
0x180020e61  mov     rsi, rcx
0x180020e64  lea     rax, [rbp+size]
0x180020e68  xorps   xmm0, xmm0
0x180020e6b  mov     r9d, edi; dwSaveTo
0x180020e6e  mov     [rsp+60h+pvSaveToPara], rax; pvSaveToPara
0x180020e73  mov     r8d, edi; dwSaveAs
0x180020e76  mov     edx, 10001h; dwEncodingType
0x180020e7b  mov     rcx, rbx; hCertStore
0x180020e7e  movups  xmmword ptr [rbp+size], xmm0
0x180020e82  call    cs:__imp_CertSaveStore
0x180020e88  test    eax, eax
0x180020e8a  jnz     short loc_180020E97
0x180020e8c  call    cs:__imp_GetLastError
0x180020e92  jmp     loc_180020F93
0x180020e97  mov     ecx, dword ptr [rbp+size]; size
0x180020e9a  call    MIDL_user_allocate
0x180020e9f  mov     [rbp+size+8], rax
0x180020ea3  test    rax, rax
0x180020ea6  jnz     short loc_180020EB2
0x180020ea8  mov     ebx, 8
0x180020ead  jmp     loc_180020F95
0x180020eb2  lea     rax, [rbp+size]
0x180020eb6  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180020ebe  mov     r9d, edi; dwSaveTo
0x180020ec1  mov     [rsp+60h+pvSaveToPara], rax; pvSaveToPara
0x180020ec6  mov     r8d, edi; dwSaveAs
0x180020ec9  mov     edx, 10001h; dwEncodingType
0x180020ece  mov     rcx, rbx; hCertStore
0x180020ed1  call    cs:__imp_CertSaveStore
0x180020ed7  test    eax, eax
0x180020ed9  jz      short loc_180020E8C
0x180020edb  lea     rdx, [rbp+var_18]
0x180020edf  mov     rcx, rsi
0x180020ee2  call    CspQueryCapabilities
0x180020ee7  mov     ebx, eax
0x180020ee9  test    eax, eax
0x180020eeb  jnz     loc_180020F95
0x180020ef1  cmp     dword ptr [rbp+var_18+4], eax
0x180020ef4  jnz     short loc_180020F51
0x180020ef6  mov     ecx, dword ptr [rbp+size]
0x180020ef9  lea     r8, [rbp+var_30]
0x180020efd  xor     r9d, r9d
0x180020f00  xor     edx, edx
0x180020f02  call    CompressData
0x180020f07  mov     ebx, eax
0x180020f09  test    eax, eax
0x180020f0b  jnz     loc_180020F95
0x180020f11  mov     ecx, dword ptr [rbp+var_30]; size
0x180020f14  call    MIDL_user_allocate
0x180020f19  mov     rdi, rax
0x180020f1c  test    rax, rax
0x180020f1f  jz      short loc_180020EA8
0x180020f21  mov     rdx, [rbp+size+8]
0x180020f25  lea     r8, [rbp+var_30]
0x180020f29  mov     ecx, dword ptr [rbp+size]
0x180020f2c  mov     r9, rax
0x180020f2f  call    CompressData
0x180020f34  mov     ebx, eax
0x180020f36  test    eax, eax
0x180020f38  jnz     loc_180020FC1
0x180020f3e  mov     rcx, [rbp+size+8]
0x180020f42  call    CspFreeH
0x180020f47  mov     eax, dword ptr [rbp+var_30]
0x180020f4a  mov     dword ptr [rbp+size], eax
0x180020f4d  mov     [rbp+size+8], rdi
0x180020f51  lea     rdi, aMsroots; "msroots"
0x180020f58  mov     rcx, rsi
0x180020f5b  mov     r9, rdi
0x180020f5e  call    CspDeleteFile
0x180020f63  mov     r9d, dword ptr [rbp+size]
0x180020f67  mov     r8, rdi
0x180020f6a  mov     rcx, rsi
0x180020f6d  call    CspCreateFile
0x180020f72  mov     ebx, eax
0x180020f74  test    eax, eax
0x180020f76  jnz     short loc_180020F95
0x180020f78  mov     eax, dword ptr [rbp+size]
0x180020f7b  mov     r8, rdi
0x180020f7e  mov     [rsp+60h+dwFlags], eax
0x180020f82  mov     rcx, rsi
0x180020f85  mov     rax, [rbp+size+8]
0x180020f89  mov     [rsp+60h+pvSaveToPara], rax
0x180020f8e  call    CspWriteFile
0x180020f93  mov     ebx, eax
0x180020f95  mov     rcx, [rbp+size+8]
0x180020f99  test    rcx, rcx
0x180020f9c  jz      short loc_180020FA3
0x180020f9e  call    CspFreeH
0x180020fa3  mov     eax, ebx
0x180020fa5  mov     rcx, [rbp+var_8]
0x180020fa9  xor     rcx, rsp; StackCookie
0x180020fac  call    __security_check_cookie
0x180020fb1  mov     rbx, [rsp+60h+arg_10]
0x180020fb9  add     rsp, 60h
0x180020fbd  pop     rdi
0x180020fbe  pop     rsi
0x180020fbf  pop     rbp
0x180020fc0  retn
0x180020fc1  mov     rcx, rdi
0x180020fc4  call    CspFreeH
0x180020fc9  jmp     short loc_180020F95
```
