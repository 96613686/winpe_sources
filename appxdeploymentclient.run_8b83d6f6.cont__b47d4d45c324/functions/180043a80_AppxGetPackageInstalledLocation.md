# AppxGetPackageInstalledLocation

- ea: `0x180043a80`
- end: `0x180043d76`
- name: `AppxGetPackageInstalledLocation`
- size: `758`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x18000b614`
- `0x18000b644`
- `0x180025ab8`
- `0x180043a80`
- `0x1800863b4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043cc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043d54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043b5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043cc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043d06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043d54`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180043ad2`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180043ad2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180043d5d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180043d5d`

## pseudocode

```c
__int64 __fastcall AppxGetPackageInstalledLocation(
        __int64 (__fastcall ***a1)(_QWORD, __int64 *, HSTRING *),
        HSTRING *a2)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  HSTRING v8; // rcx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v10)(_QWORD, __int64 *, HSTRING *); // rbx
  HSTRING v11; // rsi
  int v12; // eax
  unsigned int v13; // r14d
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, HSTRING *)); // r14
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v18)(_QWORD, __int64 *, HSTRING *); // r14
  int v19; // eax
  HSTRING v20; // r14
  __int64 (__fastcall *v21)(HSTRING, HSTRING *); // rbx
  int v22; // eax
  HSTRING v23[2]; // [rsp+20h] [rbp-10h] BYREF
  void *retaddr; // [rsp+58h] [rbp+28h]
  __int64 (__fastcall ***v25)(_QWORD, __int64 *, HSTRING *); // [rsp+60h] [rbp+30h] BYREF
  __int64 v26; // [rsp+70h] [rbp+40h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  v25 = a1;
  if ( !a1 )
    return 2147942487LL;
  if ( !a2 )
    return 2147500035LL;
  v4 = *(_QWORD *)&qword_1801534C8;
  *a2 = 0;
  *(_WORD *)(v4 + 8) = 257;
  v5 = RoInitialize(1);
  v6 = v5;
  if ( v5 >= 0 )
  {
    string = 0;
    v7 = sub_180025AB8(&string, &v25);
    v6 = v7;
    if ( v7 < 0 )
    {
      sub_18000B614(retaddr, 784, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v7);
      v8 = string;
      if ( !string )
      {
LABEL_36:
        RoUninitialize();
        return v6;
      }
LABEL_23:
      WindowsDeleteString(v8);
      goto LABEL_36;
    }
    sub_1800863B4(&v25);
    v9 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
    if ( !v25 )
    {
      if ( string )
        WindowsDeleteString(string);
      v6 = -2147024882;
      goto LABEL_36;
    }
    v26 = 0;
    v10 = (*v25)[17];
    sub_18000B644(&v26);
    v11 = string;
    v12 = v10(v9, (__int64 *)string, (HSTRING *)&v26);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v14 = v26;
      if ( v26 )
      {
        v25 = 0;
        v15 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, HSTRING *)))(*(_QWORD *)v26 + 56LL);
        sub_18000B644(&v25);
        v16 = v15(v14, &v25);
        v6 = v16;
        if ( v16 >= 0 )
        {
          v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
          string = 0;
          v18 = **v25;
          sub_18000B644(&string);
          v19 = v18(v17, qword_18010BB78, &string);
          v6 = v19;
          if ( v19 >= 0 )
          {
            v20 = string;
            v23[0] = 0;
            v21 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)string + 96LL);
            WindowsDeleteString(0);
            v23[0] = 0;
            v22 = v21(v20, v23);
            v13 = v22;
            if ( v22 >= 0 )
            {
              *a2 = v23[0];
              v23[0] = 0;
            }
            else
            {
              sub_18000B614(
                retaddr,
                802,
                "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
                (unsigned int)v22);
              if ( v23[0] )
                WindowsDeleteString(v23[0]);
            }
            sub_18000B644(&string);
            sub_18000B644(&v25);
            goto LABEL_31;
          }
          sub_18000B614(
            retaddr,
            799,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v19);
          sub_18000B644(&string);
        }
        else
        {
          sub_18000B614(
            retaddr,
            796,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v16);
        }
        sub_18000B644(&v25);
        sub_18000B644(&v26);
        if ( v9 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v9)[2])(v9);
        if ( !v11 )
          goto LABEL_36;
        v8 = v11;
        goto LABEL_23;
      }
    }
    else
    {
      sub_18000B614(retaddr, 791, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v12);
    }
LABEL_31:
    sub_18000B644(&v26);
    if ( v9 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v9)[2])(v9);
    if ( v11 )
      WindowsDeleteString(v11);
    v6 = v13;
    goto LABEL_36;
  }
  sub_18000B614(retaddr, 781, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v5);
  return v6;
}

```

## disassembly

```asm
0x180043a80  mov     [rsp-28h+arg_8], rbx
0x180043a85  mov     [rsp-28h+arg_0], rcx
0x180043a8a  push    rbp
0x180043a8b  push    rsi
0x180043a8c  push    rdi
0x180043a8d  push    r14
0x180043a8f  push    r15
0x180043a91  mov     rbp, rsp
0x180043a94  sub     rsp, 30h
0x180043a98  mov     r15, rdx
0x180043a9b  test    rcx, rcx
0x180043a9e  jnz     short loc_180043AAA
0x180043aa0  mov     eax, 80070057h
0x180043aa5  jmp     loc_180043D65
0x180043aaa  test    r15, r15
0x180043aad  jnz     short loc_180043AB9
0x180043aaf  mov     eax, 80004003h
0x180043ab4  jmp     loc_180043D65
0x180043ab9  mov     rax, cs:qword_1801534C8
0x180043ac0  mov     ecx, 1
0x180043ac5  mov     qword ptr [rdx], 0
0x180043acc  mov     word ptr [rax+8], 101h
0x180043ad2  call    cs:RoInitialize
0x180043ad8  mov     ebx, eax
0x180043ada  test    eax, eax
0x180043adc  jns     short loc_180043AFB
0x180043ade  mov     rcx, [rbp+28h]
0x180043ae2  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180043ae9  mov     r9d, eax
0x180043aec  mov     edx, 30Dh
0x180043af1  call    sub_18000B614
0x180043af6  jmp     loc_180043D63
0x180043afb  lea     rdx, [rbp+arg_0]
0x180043aff  mov     [rbp+string], 0
0x180043b07  lea     rcx, [rbp+string]
0x180043b0b  call    sub_180025AB8
0x180043b10  mov     ebx, eax
0x180043b12  test    eax, eax
0x180043b14  jns     short loc_180043B40
0x180043b16  mov     rcx, [rbp+28h]
0x180043b1a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180043b21  mov     r9d, eax
0x180043b24  mov     edx, 310h
0x180043b29  call    sub_18000B614
0x180043b2e  mov     rcx, [rbp+string]
0x180043b32  test    rcx, rcx
0x180043b35  jz      loc_180043D5D
0x180043b3b  jmp     loc_180043C44
0x180043b40  lea     rcx, [rbp+arg_0]
0x180043b44  call    sub_1800863B4
0x180043b49  mov     rdi, [rbp+arg_0]
0x180043b4d  test    rdi, rdi
0x180043b50  jnz     short loc_180043B6B
0x180043b52  mov     rcx, [rbp+string]; string
0x180043b56  test    rcx, rcx
0x180043b59  jz      short loc_180043B61
0x180043b5b  call    cs:WindowsDeleteString
0x180043b61  mov     ebx, 8007000Eh
0x180043b66  jmp     loc_180043D5D
0x180043b6b  mov     [rbp+arg_10], 0
0x180043b73  lea     rcx, [rbp+arg_10]
0x180043b77  mov     rax, [rdi]
0x180043b7a  mov     rbx, [rax+88h]
0x180043b81  call    sub_18000B644
0x180043b86  mov     rsi, [rbp+string]
0x180043b8a  lea     r8, [rbp+arg_10]
0x180043b8e  mov     rdx, rsi
0x180043b91  mov     rcx, rdi
0x180043b94  mov     rax, rbx
0x180043b97  call    j__guard_dispatch_icall
0x180043b9c  mov     r14d, eax
0x180043b9f  test    eax, eax
0x180043ba1  jns     short loc_180043BC0
0x180043ba3  mov     rcx, [rbp+28h]
0x180043ba7  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180043bae  mov     r9d, eax
0x180043bb1  mov     edx, 317h
0x180043bb6  call    sub_18000B614
0x180043bbb  jmp     loc_180043D2F
0x180043bc0  mov     rbx, [rbp+arg_10]
0x180043bc4  test    rbx, rbx
0x180043bc7  jz      loc_180043D2F
0x180043bcd  mov     [rbp+arg_0], 0
0x180043bd5  lea     rcx, [rbp+arg_0]
0x180043bd9  mov     rax, [rbx]
0x180043bdc  mov     r14, [rax+38h]
0x180043be0  call    sub_18000B644
0x180043be5  lea     rdx, [rbp+arg_0]
0x180043be9  mov     rcx, rbx
0x180043bec  mov     rax, r14
0x180043bef  call    j__guard_dispatch_icall
0x180043bf4  mov     ebx, eax
0x180043bf6  test    eax, eax
0x180043bf8  jns     short loc_180043C4F
0x180043bfa  mov     rcx, [rbp+28h]
0x180043bfe  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180043c05  mov     r9d, eax
0x180043c08  mov     edx, 31Ch
0x180043c0d  call    sub_18000B614
0x180043c12  lea     rcx, [rbp+arg_0]
0x180043c16  call    sub_18000B644
0x180043c1b  lea     rcx, [rbp+arg_10]
0x180043c1f  call    sub_18000B644
0x180043c24  test    rdi, rdi
0x180043c27  jz      short loc_180043C38
0x180043c29  mov     rax, [rdi]
0x180043c2c  mov     rcx, rdi
0x180043c2f  mov     rax, [rax+10h]
0x180043c33  call    j__guard_dispatch_icall
0x180043c38  test    rsi, rsi
0x180043c3b  jz      loc_180043D5D
0x180043c41  mov     rcx, rsi; string
0x180043c44  call    cs:WindowsDeleteString
0x180043c4a  jmp     loc_180043D5D
0x180043c4f  mov     rbx, [rbp+arg_0]
0x180043c53  lea     rcx, [rbp+string]
0x180043c57  mov     [rbp+string], 0
0x180043c5f  mov     rax, [rbx]
0x180043c62  mov     r14, [rax]
0x180043c65  call    sub_18000B644
0x180043c6a  lea     r8, [rbp+string]
0x180043c6e  mov     rcx, rbx
0x180043c71  lea     rdx, qword_18010BB78
0x180043c78  mov     rax, r14
0x180043c7b  call    j__guard_dispatch_icall
0x180043c80  mov     ebx, eax
0x180043c82  test    eax, eax
0x180043c84  jns     short loc_180043CAC
0x180043c86  mov     rcx, [rbp+28h]
0x180043c8a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180043c91  mov     r9d, eax
0x180043c94  mov     edx, 31Fh
0x180043c99  call    sub_18000B614
0x180043c9e  lea     rcx, [rbp+string]
0x180043ca2  call    sub_18000B644
0x180043ca7  jmp     loc_180043C12
0x180043cac  mov     r14, [rbp+string]
0x180043cb0  xor     ecx, ecx; string
0x180043cb2  mov     [rbp+var_10], 0
0x180043cba  mov     rax, [r14]
0x180043cbd  mov     rbx, [rax+60h]
0x180043cc1  call    cs:WindowsDeleteString
0x180043cc7  lea     rdx, [rbp+var_10]
0x180043ccb  mov     [rbp+var_10], 0
0x180043cd3  mov     rcx, r14
0x180043cd6  mov     rax, rbx
0x180043cd9  call    j__guard_dispatch_icall
0x180043cde  mov     r14d, eax
0x180043ce1  test    eax, eax
0x180043ce3  jns     short loc_180043D0E
0x180043ce5  mov     rcx, [rbp+28h]
0x180043ce9  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180043cf0  mov     r9d, eax
0x180043cf3  mov     edx, 322h
0x180043cf8  call    sub_18000B614
0x180043cfd  mov     rcx, [rbp+var_10]; string
0x180043d01  test    rcx, rcx
0x180043d04  jz      short loc_180043D1D
0x180043d06  call    cs:WindowsDeleteString
0x180043d0c  jmp     short loc_180043D1D
0x180043d0e  mov     rax, [rbp+var_10]
0x180043d12  mov     [r15], rax
0x180043d15  mov     [rbp+var_10], 0
0x180043d1d  lea     rcx, [rbp+string]
0x180043d21  call    sub_18000B644
0x180043d26  lea     rcx, [rbp+arg_0]
0x180043d2a  call    sub_18000B644
0x180043d2f  lea     rcx, [rbp+arg_10]
0x180043d33  call    sub_18000B644
0x180043d38  test    rdi, rdi
0x180043d3b  jz      short loc_180043D4C
0x180043d3d  mov     rax, [rdi]
0x180043d40  mov     rcx, rdi
0x180043d43  mov     rax, [rax+10h]
0x180043d47  call    j__guard_dispatch_icall
0x180043d4c  test    rsi, rsi
0x180043d4f  jz      short loc_180043D5A
0x180043d51  mov     rcx, rsi; string
0x180043d54  call    cs:WindowsDeleteString
0x180043d5a  mov     ebx, r14d
0x180043d5d  call    cs:RoUninitialize
0x180043d63  mov     eax, ebx
0x180043d65  mov     rbx, [rsp+30h+arg_8]
0x180043d6a  add     rsp, 30h
0x180043d6e  pop     r15
0x180043d70  pop     r14
0x180043d72  pop     rdi
0x180043d73  pop     rsi
0x180043d74  pop     rbp
0x180043d75  retn
```
