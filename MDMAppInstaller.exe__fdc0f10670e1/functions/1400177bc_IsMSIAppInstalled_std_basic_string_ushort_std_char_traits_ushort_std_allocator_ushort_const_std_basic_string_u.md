# IsMSIAppInstalled(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400177bc`
- end: `0x140017a82`
- name: `?IsMSIAppInstalled@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `710`
- prototype: `char __fastcall(LPCWSTR szProduct, char *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000d470`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x1400074d4`
- `0x1400168b4`
- `0x1400177bc`
- `0x14001a8d0`

## string_xrefs

- `0x140017817`: `InstalledProductName`
- `0x1400178e8`: `MSI DB Query: App [Name = %1] [ProductCode = %2] is INSTALLED for user %3.`
- `0x1400179a2`: `MSI DB Query: ProductVersion = %1 for app [Name = %2] [ProductCode = %3] is NOT INSTALLED for user %4.`
- `0x1400179e4`: `MSI DB Query: App [Name = %1] [ProductCode = %2] [ProductVersion = %3] is INSTALLED for user %4.`
- `0x140017a03`: `GetProductInfoFromMsi failed to get product version (hr=0x%1!x!)`
- `0x140017a2e`: `MSI DB Query: App [ProductCode = %1] is NOT INSTALLED for user %2. (hr = 0x%3!x!)`

## pseudocode

```c
char __fastcall IsMSIAppInstalled(LPCWSTR szProduct, char *a2, __int64 *a3)
{
  char v6; // r15
  char v7; // r13
  char v8; // r14
  int ProductInfoFromMsi; // r12d
  _QWORD *v10; // rdx
  int v11; // r14d
  char *v12; // rcx
  char *v13; // rax
  signed __int64 v14; // rcx
  int v15; // edx
  int v16; // r8d
  _QWORD *v17; // r8
  char *v18; // rax
  LPCWSTR v19; // r8
  _QWORD *v20; // rsi
  _QWORD v22[3]; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int64 v23; // [rsp+50h] [rbp-49h]
  _QWORD v24[3]; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int64 v25; // [rsp+70h] [rbp-29h]
  WCHAR szAttribute[16]; // [rsp+78h] [rbp-21h] BYREF
  WCHAR v27[16]; // [rsp+98h] [rbp-1h] BYREF

  v6 = 0;
  v7 = 0;
  v23 = 7;
  v25 = 7;
  v22[2] = 0;
  LOWORD(v22[0]) = 0;
  v24[2] = 0;
  LOWORD(v24[0]) = 0;
  std::wstring::wstring((__int64)szAttribute, (__int64)L"InstalledProductName");
  v8 = 1;
  ProductInfoFromMsi = GetProductInfoFromMsi(szProduct, szAttribute, v22, (char *)a3);
  if ( ProductInfoFromMsi >= 0
    || (std::wstring::wstring((__int64)v27, (__int64)L"ProductName"),
        v8 = 3,
        ProductInfoFromMsi = GetProductInfoFromMsi(szProduct, v27, v22, (char *)a3),
        ProductInfoFromMsi >= 0) )
  {
    v6 = 1;
  }
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    std::wstring::_Tidy(v27, 1, 0);
  }
  if ( (v8 & 1) != 0 )
    std::wstring::_Tidy(szAttribute, 1, 0);
  if ( v6 )
  {
    if ( *((_QWORD *)a2 + 2) )
    {
      std::wstring::wstring((__int64)szAttribute, (__int64)L"VersionString");
      v11 = GetProductInfoFromMsi(szProduct, szAttribute, v24, (char *)a3);
      std::wstring::_Tidy(szAttribute, 1, 0);
      if ( v11 < 0 )
      {
        LogInfo(L"GetProductInfoFromMsi failed to get product version (hr=0x%1!x!)", (unsigned int)v11);
      }
      else
      {
        v12 = (char *)v24;
        if ( v25 >= 8 )
          v12 = (char *)v24[0];
        if ( *((_QWORD *)a2 + 3) < 8u )
          v13 = a2;
        else
          v13 = *(char **)a2;
        v14 = v12 - v13;
        do
        {
          v15 = *(unsigned __int16 *)&v13[v14];
          v16 = *(unsigned __int16 *)v13 - v15;
          if ( v16 )
            break;
          v13 += 2;
        }
        while ( v15 );
        if ( v16 )
        {
          if ( (unsigned __int64)a3[3] >= 8 )
            a3 = (__int64 *)*a3;
          if ( *((_QWORD *)szProduct + 3) >= 8u )
            szProduct = *(LPCWSTR *)szProduct;
          v17 = v22;
          if ( v23 >= 8 )
            v17 = (_QWORD *)v22[0];
          if ( *((_QWORD *)a2 + 3) >= 8u )
            a2 = *(char **)a2;
          LogInfo(
            L"MSI DB Query: ProductVersion = %1 for app [Name = %2] [ProductCode = %3] is NOT INSTALLED for user %4.",
            a2,
            v17,
            szProduct,
            a3);
        }
        else
        {
          v7 = 1;
          if ( (unsigned __int64)a3[3] >= 8 )
            a3 = (__int64 *)*a3;
          if ( *((_QWORD *)a2 + 3) < 8u )
            v18 = a2;
          else
            v18 = *(char **)a2;
          if ( *((_QWORD *)szProduct + 3) < 8u )
            v19 = szProduct;
          else
            v19 = *(LPCWSTR *)szProduct;
          v20 = v22;
          if ( v23 >= 8 )
            v20 = (_QWORD *)v22[0];
          LogInfo(
            L"MSI DB Query: App [Name = %1] [ProductCode = %2] [ProductVersion = %3] is INSTALLED for user %4.",
            v20,
            v19,
            v18,
            a3);
        }
      }
    }
    else
    {
      v7 = 1;
      if ( (unsigned __int64)a3[3] >= 8 )
        a3 = (__int64 *)*a3;
      if ( *((_QWORD *)szProduct + 3) >= 8u )
        szProduct = *(LPCWSTR *)szProduct;
      v10 = v22;
      if ( v23 >= 8 )
        v10 = (_QWORD *)v22[0];
      LogInfo(L"MSI DB Query: App [Name = %1] [ProductCode = %2] is INSTALLED for user %3.", v10, szProduct, a3);
    }
  }
  else
  {
    if ( (unsigned __int64)a3[3] >= 8 )
      a3 = (__int64 *)*a3;
    if ( *((_QWORD *)szProduct + 3) >= 8u )
      szProduct = *(LPCWSTR *)szProduct;
    LogInfo(
      L"MSI DB Query: App [ProductCode = %1] is NOT INSTALLED for user %2. (hr = 0x%3!x!)",
      szProduct,
      a3,
      (unsigned int)ProductInfoFromMsi);
  }
  std::wstring::_Tidy(v24, 1, 0);
  std::wstring::_Tidy(v22, 1, 0);
  return v7;
}

```

## disassembly

```asm
0x1400177bc  mov     [rsp-8+arg_18], rbx
0x1400177c1  push    rbp
0x1400177c2  push    rsi
0x1400177c3  push    rdi
0x1400177c4  push    r12
0x1400177c6  push    r13
0x1400177c8  push    r14
0x1400177ca  push    r15
0x1400177cc  lea     rbp, [rsp-27h]
0x1400177d1  sub     rsp, 0C0h
0x1400177d8  mov     rax, cs:__security_cookie
0x1400177df  xor     rax, rsp
0x1400177e2  mov     [rbp+57h+var_38], rax
0x1400177e6  mov     rdi, r8
0x1400177e9  mov     rsi, rdx
0x1400177ec  mov     rbx, rcx
0x1400177ef  xor     r15d, r15d
0x1400177f2  mov     [rbp+57h+var_C0], r15d
0x1400177f6  mov     r13b, r15b
0x1400177f9  lea     eax, [r15+7]
0x1400177fd  mov     [rbp+57h+var_A0], rax
0x140017801  mov     [rbp+57h+var_80], rax
0x140017805  mov     [rbp+57h+var_A8], r15
0x140017809  mov     word ptr [rbp+57h+var_B8], r15w
0x14001780e  mov     [rbp+57h+var_88], r15
0x140017812  mov     word ptr [rbp+57h+var_98], r15w
0x140017817  lea     rdx, aInstalledprodu; "InstalledProductName"
0x14001781e  lea     rcx, [rbp+57h+szAttribute]
0x140017822  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140017827  nop
0x140017828  lea     r14d, [r15+1]
0x14001782c  mov     [rbp+57h+var_C0], r14d
0x140017830  mov     r9, rdi
0x140017833  lea     r8, [rbp+57h+var_B8]
0x140017837  lea     rdx, [rbp+57h+szAttribute]; szAttribute
0x14001783b  mov     rcx, rbx; szProduct
0x14001783e  call    ?GetProductInfoFromMsi@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@0@Z; GetProductInfoFromMsi(std::wstring const &,std::wstring const &,std::wstring &,std::wstring const &)
0x140017843  mov     r12d, eax
0x140017846  test    eax, eax
0x140017848  jns     short loc_14001787D
0x14001784a  lea     rdx, aProductname; "ProductName"
0x140017851  lea     rcx, [rbp+57h+var_58]
0x140017855  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14001785a  nop
0x14001785b  lea     r14d, [r15+3]
0x14001785f  mov     [rbp+57h+var_C0], r14d
0x140017863  mov     r9, rdi
0x140017866  lea     r8, [rbp+57h+var_B8]
0x14001786a  lea     rdx, [rbp+57h+var_58]; szAttribute
0x14001786e  mov     rcx, rbx; szProduct
0x140017871  call    ?GetProductInfoFromMsi@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@0@Z; GetProductInfoFromMsi(std::wstring const &,std::wstring const &,std::wstring &,std::wstring const &)
0x140017876  mov     r12d, eax
0x140017879  test    eax, eax
0x14001787b  js      short loc_140017880
0x14001787d  mov     r15b, 1
0x140017880  test    r14b, 2
0x140017884  jz      short loc_140017899
0x140017886  and     r14d, 0FFFFFFFDh
0x14001788a  xor     r8d, r8d
0x14001788d  mov     dl, 1
0x14001788f  lea     rcx, [rbp+57h+var_58]
0x140017893  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140017898  nop
0x140017899  test    r14b, 1
0x14001789d  jz      short loc_1400178AD
0x14001789f  xor     r8d, r8d
0x1400178a2  mov     dl, 1
0x1400178a4  lea     rcx, [rbp+57h+szAttribute]
0x1400178a8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400178ad  test    r15b, r15b
0x1400178b0  jz      loc_140017A11
0x1400178b6  cmp     qword ptr [rsi+10h], 0
0x1400178bb  jnz     short loc_1400178F9
0x1400178bd  mov     r13b, 1
0x1400178c0  cmp     qword ptr [rdi+18h], 8
0x1400178c5  jb      short loc_1400178CA
0x1400178c7  mov     rdi, [rdi]
0x1400178ca  cmp     qword ptr [rbx+18h], 8
0x1400178cf  jb      short loc_1400178D4
0x1400178d1  mov     rbx, [rbx]
0x1400178d4  lea     rdx, [rbp+57h+var_B8]
0x1400178d8  cmp     [rbp+57h+var_A0], 8
0x1400178dd  cmovnb  rdx, [rbp+57h+var_B8]
0x1400178e2  mov     r9, rdi
0x1400178e5  mov     r8, rbx
0x1400178e8  lea     rcx, aMsiDbQueryAppN; "MSI DB Query: App [Name = %1] [ProductC"...
0x1400178ef  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400178f4  jmp     loc_140017A3B
0x1400178f9  lea     rdx, aVersionstring; "VersionString"
0x140017900  lea     rcx, [rbp+57h+szAttribute]
0x140017904  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140017909  nop
0x14001790a  mov     r9, rdi
0x14001790d  lea     r8, [rbp+57h+var_98]
0x140017911  lea     rdx, [rbp+57h+szAttribute]; szAttribute
0x140017915  mov     rcx, rbx; szProduct
0x140017918  call    ?GetProductInfoFromMsi@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV12@0@Z; GetProductInfoFromMsi(std::wstring const &,std::wstring const &,std::wstring &,std::wstring const &)
0x14001791d  mov     r14d, eax
0x140017920  xor     r8d, r8d
0x140017923  mov     dl, 1
0x140017925  lea     rcx, [rbp+57h+szAttribute]
0x140017929  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14001792e  mov     eax, r14d
0x140017931  shr     eax, 1Fh
0x140017934  xor     al, 1
0x140017936  jz      loc_140017A00
0x14001793c  lea     rcx, [rbp+57h+var_98]
0x140017940  cmp     [rbp+57h+var_80], 8
0x140017945  cmovnb  rcx, [rbp+57h+var_98]
0x14001794a  cmp     qword ptr [rsi+18h], 8
0x14001794f  jb      short loc_140017956
0x140017951  mov     rax, [rsi]
0x140017954  jmp     short loc_140017959
0x140017956  mov     rax, rsi
0x140017959  sub     rcx, rax
0x14001795c  movzx   r8d, word ptr [rax]
0x140017960  movzx   edx, word ptr [rax+rcx]
0x140017964  sub     r8d, edx
0x140017967  jnz     short loc_140017971
0x140017969  add     rax, 2
0x14001796d  test    edx, edx
0x14001796f  jnz     short loc_14001795C
0x140017971  test    r8d, r8d
0x140017974  jz      short loc_1400179AB
0x140017976  cmp     qword ptr [rdi+18h], 8
0x14001797b  jb      short loc_140017980
0x14001797d  mov     rdi, [rdi]
0x140017980  cmp     qword ptr [rbx+18h], 8
0x140017985  jb      short loc_14001798A
0x140017987  mov     rbx, [rbx]
0x14001798a  lea     r8, [rbp+57h+var_B8]
0x14001798e  cmp     [rbp+57h+var_A0], 8
0x140017993  cmovnb  r8, [rbp+57h+var_B8]
0x140017998  cmp     qword ptr [rsi+18h], 8
0x14001799d  jb      short loc_1400179A2
0x14001799f  mov     rsi, [rsi]
0x1400179a2  lea     rcx, aMsiDbQueryProd; "MSI DB Query: ProductVersion = %1 for a"...
0x1400179a9  jmp     short loc_1400179EE
0x1400179ab  mov     r13b, 1
0x1400179ae  cmp     qword ptr [rdi+18h], 8
0x1400179b3  jb      short loc_1400179B8
0x1400179b5  mov     rdi, [rdi]
0x1400179b8  cmp     qword ptr [rsi+18h], 8
0x1400179bd  jb      short loc_1400179C4
0x1400179bf  mov     rax, [rsi]
0x1400179c2  jmp     short loc_1400179C7
0x1400179c4  mov     rax, rsi
0x1400179c7  cmp     qword ptr [rbx+18h], 8
0x1400179cc  jb      short loc_1400179D3
0x1400179ce  mov     r8, [rbx]
0x1400179d1  jmp     short loc_1400179D6
0x1400179d3  mov     r8, rbx
0x1400179d6  lea     rsi, [rbp+57h+var_B8]
0x1400179da  cmp     [rbp+57h+var_A0], 8
0x1400179df  cmovnb  rsi, [rbp+57h+var_B8]
0x1400179e4  lea     rcx, aMsiDbQueryAppN_0; "MSI DB Query: App [Name = %1] [ProductC"...
0x1400179eb  mov     rbx, rax
0x1400179ee  mov     [rsp+0F0h+var_D0], rdi
0x1400179f3  mov     r9, rbx
0x1400179f6  mov     rdx, rsi
0x1400179f9  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400179fe  jmp     short loc_140017A3B
0x140017a00  mov     edx, r14d
0x140017a03  lea     rcx, aGetproductinfo; "GetProductInfoFromMsi failed to get pro"...
0x140017a0a  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140017a0f  jmp     short loc_140017A3B
0x140017a11  cmp     qword ptr [rdi+18h], 8
0x140017a16  jb      short loc_140017A1B
0x140017a18  mov     rdi, [rdi]
0x140017a1b  cmp     qword ptr [rbx+18h], 8
0x140017a20  jb      short loc_140017A25
0x140017a22  mov     rbx, [rbx]
0x140017a25  mov     r9d, r12d
0x140017a28  mov     r8, rdi
0x140017a2b  mov     rdx, rbx
0x140017a2e  lea     rcx, aMsiDbQueryAppP; "MSI DB Query: App [ProductCode = %1] is"...
0x140017a35  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140017a3a  nop
0x140017a3b  xor     r8d, r8d
0x140017a3e  mov     dl, 1
0x140017a40  lea     rcx, [rbp+57h+var_98]
0x140017a44  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140017a49  nop
0x140017a4a  xor     r8d, r8d
0x140017a4d  mov     dl, 1
0x140017a4f  lea     rcx, [rbp+57h+var_B8]
0x140017a53  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140017a58  mov     al, r13b
0x140017a5b  mov     rcx, [rbp+57h+var_38]
0x140017a5f  xor     rcx, rsp; StackCookie
0x140017a62  call    __security_check_cookie
0x140017a67  mov     rbx, [rsp+0F0h+arg_18]
0x140017a6f  add     rsp, 0C0h
0x140017a76  pop     r15
0x140017a78  pop     r14
0x140017a7a  pop     r13
0x140017a7c  pop     r12
0x140017a7e  pop     rdi
0x140017a7f  pop     rsi
0x140017a80  pop     rbp
0x140017a81  retn
```
