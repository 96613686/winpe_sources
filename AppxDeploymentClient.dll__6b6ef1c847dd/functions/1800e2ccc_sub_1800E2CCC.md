# sub_1800E2CCC

- ea: `0x1800e2ccc`
- end: `0x1800e301e`
- name: `sub_1800E2CCC`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d157c`

## callees

- `0x180008a1c`
- `0x180046eb8`
- `0x180051870`
- `0x1800522e8`
- `0x1800e2aa8`
- `0x1800e2ccc`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2d30`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2e4d`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2ed6`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2f9d`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2d30`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2e4d`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2ed6`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!EnumerateExtensionNames` at `0x1800e2f9d`

## string_xrefs

- `0x1800e2d71`: `onecore\admin\appmodel\packagerepository\common\extensions.cpp`
- `0x1800e2ec2`: `windows.protocol`
- `0x1800e2f27`: `windows.protocol`
- `0x1800e2f5e`: `windows.protocol`
- `0x1800e2f88`: `windows.protocol`

## pseudocode

```c
__int64 __fastcall sub_1800E2CCC(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v8; // ebx
  int v9; // edx
  unsigned int v11; // r15d
  int v12; // eax
  unsigned int v13; // r15d
  _BYTE v14[80]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[144]; // [rsp+90h] [rbp-70h] BYREF
  _UNKNOWN *retaddr; // [rsp+178h] [rbp+78h]

  memset(v15, 0, 0x82u);
  v8 = EnumerateExtensionNames(0, a2, a3, L"windows.fileTypeAssociation", 65, v15);
  if ( v8 != -2147024894 )
  {
    if ( ((v8 + 0x80000000) & 0x80000000) == 0 && v8 != -2147024637 )
    {
      v9 = 1887;
LABEL_5:
      sub_180008A1C((int)retaddr, v9, (int)"onecore\\admin\\appmodel\\packagerepository\\common\\extensions.cpp", v8);
      return (unsigned int)v8;
    }
    v11 = 1;
    while ( v8 >= 0 )
    {
      v8 = sub_1800E2AA8(
             a2,
             a3,
             (unsigned int)L"windows.fileTypeAssociation",
             (unsigned int)v15,
             (__int64)L"Logo",
             0,
             a4);
      if ( v8 < 0 )
      {
        v9 = 1890;
        goto LABEL_5;
      }
      v8 = sub_1800E2AA8(
             a2,
             a3,
             (unsigned int)L"windows.fileTypeAssociation",
             (unsigned int)v15,
             (__int64)L"DisplayName",
             1,
             a4);
      if ( v8 < 0 )
      {
        v9 = 1891;
        goto LABEL_5;
      }
      v8 = sub_1800E2AA8(
             a2,
             a3,
             (unsigned int)L"windows.fileTypeAssociation",
             (unsigned int)v15,
             (__int64)L"InfoTip",
             1,
             a4);
      if ( v8 < 0 )
      {
        v9 = 1892;
        goto LABEL_5;
      }
      v8 = EnumerateExtensionNames(v11, a2, a3, L"windows.fileTypeAssociation", 65, v15);
      if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147024637 )
      {
        v9 = 1895;
        goto LABEL_5;
      }
      ++v11;
    }
  }
  memset(v14, 0, sizeof(v14));
  v12 = EnumerateExtensionNames(0, a2, a3, L"windows.protocol", 40, v14);
  v8 = v12;
  if ( v12 != -2147024894 )
  {
    if ( ((v12 + 0x80000000) & 0x80000000) == 0 && v12 != -2147024637 )
    {
      v9 = 1908;
      goto LABEL_5;
    }
    v13 = 1;
    while ( v8 >= 0 )
    {
      v8 = sub_1800E2AA8(a2, a3, (unsigned int)L"windows.protocol", (unsigned int)v14, (__int64)L"Logo", 0, a4);
      if ( v8 < 0 )
      {
        v9 = 1911;
        goto LABEL_5;
      }
      v8 = sub_1800E2AA8(a2, a3, (unsigned int)L"windows.protocol", (unsigned int)v14, (__int64)L"DisplayName", 1, a4);
      if ( v8 < 0 )
      {
        v9 = 1912;
        goto LABEL_5;
      }
      v8 = EnumerateExtensionNames(v13, a2, a3, L"windows.protocol", 40, v14);
      if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147024637 )
      {
        v9 = 1915;
        goto LABEL_5;
      }
      ++v13;
    }
  }
  v8 = sub_180046EB8(a1, a3, a4);
  if ( v8 < 0 )
  {
    v9 = 1920;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800e2ccc  push    rbp
0x1800e2cce  push    rbx
0x1800e2ccf  push    rsi
0x1800e2cd0  push    rdi
0x1800e2cd1  push    r12
0x1800e2cd3  push    r13
0x1800e2cd5  push    r14
0x1800e2cd7  push    r15
0x1800e2cd9  lea     rbp, [rsp-38h]
0x1800e2cde  sub     rsp, 138h
0x1800e2ce5  mov     rax, cs:__security_cookie
0x1800e2cec  xor     rax, rsp
0x1800e2cef  mov     [rbp+70h+var_50], rax
0x1800e2cf3  mov     rdi, r8
0x1800e2cf6  mov     rsi, rdx
0x1800e2cf9  mov     r12, rcx
0x1800e2cfc  xor     edx, edx; Val
0x1800e2cfe  mov     r8d, 82h; Size
0x1800e2d04  lea     rcx, [rbp+70h+var_E0]; void *
0x1800e2d08  mov     r14, r9
0x1800e2d0b  call    memset
0x1800e2d10  lea     rax, [rbp+70h+var_E0]
0x1800e2d14  mov     r8, rdi
0x1800e2d17  mov     [rsp+170h+var_148], rax
0x1800e2d1c  lea     r9, aWindowsFiletyp; "windows.fileTypeAssociation"
0x1800e2d23  mov     rdx, rsi
0x1800e2d26  mov     dword ptr [rsp+170h+var_150], 41h ; 'A'
0x1800e2d2e  xor     ecx, ecx
0x1800e2d30  call    cs:EnumerateExtensionNames
0x1800e2d36  mov     r15d, 80000000h
0x1800e2d3c  mov     r13d, 1
0x1800e2d42  mov     ebx, eax
0x1800e2d44  lea     rax, aLogo; "Logo"
0x1800e2d4b  cmp     ebx, 80070002h
0x1800e2d51  jz      loc_1800E2EA5
0x1800e2d57  lea     ecx, [rbx+r15]
0x1800e2d5b  test    r15d, ecx
0x1800e2d5e  jnz     short loc_1800E2D87
0x1800e2d60  cmp     ebx, 80070103h
0x1800e2d66  jz      short loc_1800E2D87
0x1800e2d68  mov     edx, 75Fh
0x1800e2d6d  mov     rcx, [rbp+78h]
0x1800e2d71  lea     r8, aOnecoreAdminAp_44; "onecore\\admin\\appmodel\\packagereposi"...
0x1800e2d78  mov     r9d, ebx
0x1800e2d7b  call    sub_180008A1C
0x1800e2d80  mov     eax, ebx
0x1800e2d82  jmp     loc_1800E2FFE
0x1800e2d87  mov     r15d, r13d
0x1800e2d8a  test    ebx, ebx
0x1800e2d8c  js      loc_1800E2E9F
0x1800e2d92  mov     [rsp+170h+var_140], r14
0x1800e2d97  lea     r9, [rbp+70h+var_E0]
0x1800e2d9b  mov     dword ptr [rsp+170h+var_148], 0
0x1800e2da3  lea     r8, aWindowsFiletyp; "windows.fileTypeAssociation"
0x1800e2daa  mov     rdx, rdi
0x1800e2dad  mov     [rsp+170h+var_150], rax
0x1800e2db2  mov     rcx, rsi
0x1800e2db5  call    sub_1800E2AA8
0x1800e2dba  mov     ebx, eax
0x1800e2dbc  test    eax, eax
0x1800e2dbe  js      loc_1800E2E95
0x1800e2dc4  mov     [rsp+170h+var_140], r14
0x1800e2dc9  lea     rax, aDisplayname; "DisplayName"
0x1800e2dd0  mov     dword ptr [rsp+170h+var_148], r13d
0x1800e2dd5  lea     r9, [rbp+70h+var_E0]
0x1800e2dd9  lea     r8, aWindowsFiletyp; "windows.fileTypeAssociation"
0x1800e2de0  mov     [rsp+170h+var_150], rax
0x1800e2de5  mov     rdx, rdi
0x1800e2de8  mov     rcx, rsi
0x1800e2deb  call    sub_1800E2AA8
0x1800e2df0  mov     ebx, eax
0x1800e2df2  test    eax, eax
0x1800e2df4  js      loc_1800E2E8B
0x1800e2dfa  mov     [rsp+170h+var_140], r14
0x1800e2dff  lea     rax, aInfotip; "InfoTip"
0x1800e2e06  mov     dword ptr [rsp+170h+var_148], r13d
0x1800e2e0b  lea     r9, [rbp+70h+var_E0]
0x1800e2e0f  lea     r8, aWindowsFiletyp; "windows.fileTypeAssociation"
0x1800e2e16  mov     [rsp+170h+var_150], rax
0x1800e2e1b  mov     rdx, rdi
0x1800e2e1e  mov     rcx, rsi
0x1800e2e21  call    sub_1800E2AA8
0x1800e2e26  mov     ebx, eax
0x1800e2e28  test    eax, eax
0x1800e2e2a  js      short loc_1800E2E81
0x1800e2e2c  lea     rax, [rbp+70h+var_E0]
0x1800e2e30  mov     r8, rdi
0x1800e2e33  mov     [rsp+170h+var_148], rax
0x1800e2e38  lea     r9, aWindowsFiletyp; "windows.fileTypeAssociation"
0x1800e2e3f  mov     rdx, rsi
0x1800e2e42  mov     dword ptr [rsp+170h+var_150], 41h ; 'A'
0x1800e2e4a  mov     ecx, r15d
0x1800e2e4d  call    cs:EnumerateExtensionNames
0x1800e2e53  mov     ecx, 80000000h
0x1800e2e58  mov     ebx, eax
0x1800e2e5a  add     eax, ecx
0x1800e2e5c  test    ecx, eax
0x1800e2e5e  jnz     short loc_1800E2E68
0x1800e2e60  cmp     ebx, 80070103h
0x1800e2e66  jnz     short loc_1800E2E77
0x1800e2e68  add     r15d, r13d
0x1800e2e6b  lea     rax, aLogo; "Logo"
0x1800e2e72  jmp     loc_1800E2D8A
0x1800e2e77  mov     edx, 767h
0x1800e2e7c  jmp     loc_1800E2D6D
0x1800e2e81  mov     edx, 764h
0x1800e2e86  jmp     loc_1800E2D6D
0x1800e2e8b  mov     edx, 763h
0x1800e2e90  jmp     loc_1800E2D6D
0x1800e2e95  mov     edx, 762h
0x1800e2e9a  jmp     loc_1800E2D6D
0x1800e2e9f  mov     r15d, 80000000h
0x1800e2ea5  xor     edx, edx; Val
0x1800e2ea7  lea     rcx, [rsp+170h+var_130]; void *
0x1800e2eac  lea     r8d, [rdx+50h]; Size
0x1800e2eb0  call    memset
0x1800e2eb5  lea     rax, [rsp+170h+var_130]
0x1800e2eba  mov     r8, rdi
0x1800e2ebd  mov     [rsp+170h+var_148], rax
0x1800e2ec2  lea     r9, aWindowsProtoco; "windows.protocol"
0x1800e2ec9  mov     rdx, rsi
0x1800e2ecc  mov     dword ptr [rsp+170h+var_150], 28h ; '('
0x1800e2ed4  xor     ecx, ecx
0x1800e2ed6  call    cs:EnumerateExtensionNames
0x1800e2edc  mov     ebx, eax
0x1800e2ede  cmp     eax, 80070002h
0x1800e2ee3  jz      loc_1800E2FDE
0x1800e2ee9  lea     ecx, [rax+r15]
0x1800e2eed  test    r15d, ecx
0x1800e2ef0  jnz     short loc_1800E2F03
0x1800e2ef2  cmp     eax, 80070103h
0x1800e2ef7  jz      short loc_1800E2F03
0x1800e2ef9  mov     edx, 774h
0x1800e2efe  jmp     loc_1800E2D6D
0x1800e2f03  mov     r15d, r13d
0x1800e2f06  test    ebx, ebx
0x1800e2f08  js      loc_1800E2FDE
0x1800e2f0e  mov     [rsp+170h+var_140], r14
0x1800e2f13  lea     rax, aLogo; "Logo"
0x1800e2f1a  mov     dword ptr [rsp+170h+var_148], 0
0x1800e2f22  lea     r9, [rsp+170h+var_130]
0x1800e2f27  lea     r8, aWindowsProtoco; "windows.protocol"
0x1800e2f2e  mov     [rsp+170h+var_150], rax
0x1800e2f33  mov     rdx, rdi
0x1800e2f36  mov     rcx, rsi
0x1800e2f39  call    sub_1800E2AA8
0x1800e2f3e  mov     ebx, eax
0x1800e2f40  test    eax, eax
0x1800e2f42  js      loc_1800E2FD4
0x1800e2f48  mov     [rsp+170h+var_140], r14
0x1800e2f4d  lea     rax, aDisplayname; "DisplayName"
0x1800e2f54  mov     dword ptr [rsp+170h+var_148], r13d
0x1800e2f59  lea     r9, [rsp+170h+var_130]
0x1800e2f5e  lea     r8, aWindowsProtoco; "windows.protocol"
0x1800e2f65  mov     [rsp+170h+var_150], rax
0x1800e2f6a  mov     rdx, rdi
0x1800e2f6d  mov     rcx, rsi
0x1800e2f70  call    sub_1800E2AA8
0x1800e2f75  mov     ebx, eax
0x1800e2f77  test    eax, eax
0x1800e2f79  js      short loc_1800E2FCA
0x1800e2f7b  lea     rax, [rsp+170h+var_130]
0x1800e2f80  mov     r8, rdi
0x1800e2f83  mov     [rsp+170h+var_148], rax
0x1800e2f88  lea     r9, aWindowsProtoco; "windows.protocol"
0x1800e2f8f  mov     rdx, rsi
0x1800e2f92  mov     dword ptr [rsp+170h+var_150], 28h ; '('
0x1800e2f9a  mov     ecx, r15d
0x1800e2f9d  call    cs:EnumerateExtensionNames
0x1800e2fa3  mov     ecx, 80000000h
0x1800e2fa8  mov     ebx, eax
0x1800e2faa  add     eax, ecx
0x1800e2fac  test    ecx, eax
0x1800e2fae  jnz     short loc_1800E2FB8
0x1800e2fb0  cmp     ebx, 80070103h
0x1800e2fb6  jnz     short loc_1800E2FC0
0x1800e2fb8  add     r15d, r13d
0x1800e2fbb  jmp     loc_1800E2F06
0x1800e2fc0  mov     edx, 77Bh
0x1800e2fc5  jmp     loc_1800E2D6D
0x1800e2fca  mov     edx, 778h
0x1800e2fcf  jmp     loc_1800E2D6D
0x1800e2fd4  mov     edx, 777h
0x1800e2fd9  jmp     loc_1800E2D6D
0x1800e2fde  mov     r8, r14
0x1800e2fe1  mov     rdx, rdi
0x1800e2fe4  mov     rcx, r12
0x1800e2fe7  call    sub_180046EB8
0x1800e2fec  mov     ebx, eax
0x1800e2fee  test    eax, eax
0x1800e2ff0  jns     short loc_1800E2FFC
0x1800e2ff2  mov     edx, 780h
0x1800e2ff7  jmp     loc_1800E2D6D
0x1800e2ffc  xor     eax, eax
0x1800e2ffe  mov     rcx, [rbp+70h+var_50]
0x1800e3002  xor     rcx, rsp; StackCookie
0x1800e3005  call    __security_check_cookie
0x1800e300a  add     rsp, 138h
0x1800e3011  pop     r15
0x1800e3013  pop     r14
0x1800e3015  pop     r13
0x1800e3017  pop     r12
0x1800e3019  pop     rdi
0x1800e301a  pop     rsi
0x1800e301b  pop     rbx
0x1800e301c  pop     rbp
0x1800e301d  retn
```
