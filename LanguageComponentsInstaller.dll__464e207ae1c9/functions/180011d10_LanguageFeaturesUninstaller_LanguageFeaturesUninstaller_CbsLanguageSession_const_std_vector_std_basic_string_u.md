# LanguageFeaturesUninstaller::LanguageFeaturesUninstaller(CbsLanguageSession const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>)

- ea: `0x180011d10`
- end: `0x180011f76`
- name: `??0LanguageFeaturesUninstaller@@QEAA@AEBVCbsLanguageSession@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z`
- size: `614`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180013e1c`
- `0x180014788`

## callees

- `0x180003520`
- `0x180005954`
- `0x180006380`
- `0x18000b6b4`
- `0x18000f0a8`
- `0x180010a7c`
- `0x180011d10`
- `0x180013a04`
- `0x1800214f4`
- `0x180021590`

## pseudocode

```c
_QWORD *__fastcall LanguageFeaturesUninstaller::LanguageFeaturesUninstaller(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4)
{
  int v6; // ebx
  char v8; // di
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  char *v24; // rdi
  char *v25; // rbx
  char *v26; // r14
  char *v27; // r14
  char *i; // rdi
  __int64 v30; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v31; // [rsp+38h] [rbp-A1h]
  __int64 v32; // [rsp+40h] [rbp-99h]
  __int64 v33; // [rsp+48h] [rbp-91h] BYREF
  __int64 v34; // [rsp+50h] [rbp-89h]
  __int64 v35; // [rsp+58h] [rbp-81h]
  _QWORD *v36; // [rsp+60h] [rbp-79h] BYREF
  __int64 v37; // [rsp+68h] [rbp-71h] BYREF
  __int64 v38; // [rsp+70h] [rbp-69h]
  __int64 v39; // [rsp+78h] [rbp-61h]
  __int64 *v40; // [rsp+80h] [rbp-59h]
  _QWORD v41[3]; // [rsp+88h] [rbp-51h] BYREF
  _OWORD v42[2]; // [rsp+A0h] [rbp-39h] BYREF
  _QWORD *v43; // [rsp+C0h] [rbp-19h]
  __int64 *v44; // [rsp+D0h] [rbp-9h]
  __int64 *v45; // [rsp+D8h] [rbp-1h]
  __int64 *v46; // [rsp+E0h] [rbp+7h]
  _QWORD *v47; // [rsp+E8h] [rbp+Fh]
  _QWORD *v48; // [rsp+F0h] [rbp+17h]

  v6 = a2;
  v43 = a1;
  v47 = a3;
  v48 = a4;
  v8 = *(_BYTE *)(a2 + 160) & 1;
  v40 = &v33;
  v9 = a4[2];
  a4[2] = 0;
  v10 = a4[1];
  a4[1] = 0;
  v11 = *a4;
  *a4 = 0;
  v33 = v11;
  v34 = v10;
  v35 = v9;
  v44 = &v33;
  v45 = &v30;
  v12 = a3[2];
  a3[2] = 0;
  v13 = a3[1];
  a3[1] = 0;
  v14 = *a3;
  *a3 = 0;
  v30 = v14;
  v31 = v13;
  v32 = v12;
  v46 = &v30;
  memset(v42, 0, sizeof(v42));
  std::wstring::_Construct<1,unsigned short const *>((__int64)v42, L"Language", 8u);
  CbsSession::FeaturesOfCapability<CbsLanguageFeature,bool (CbsLanguageFeature const &)>(
    v6,
    (unsigned int)&v37,
    (unsigned int)v42,
    1,
    (__int64)CbsLanguageSession::IsInstalled);
  std::wstring::~wstring(v42);
  v15 = v39;
  v39 = 0;
  v16 = v38;
  v38 = 0;
  v17 = v37;
  v37 = 0;
  v36 = v41;
  v18 = v32;
  v32 = 0;
  v19 = v31;
  v31 = 0;
  v20 = v30;
  v30 = 0;
  *a1 = v20;
  a1[1] = v19;
  a1[2] = v18;
  v21 = v35;
  v35 = 0;
  v22 = v34;
  v34 = 0;
  v23 = v33;
  v33 = 0;
  a1[3] = v23;
  a1[4] = v22;
  a1[5] = v21;
  memset(v41, 0, sizeof(v41));
  a1[6] = v17;
  a1[7] = v16;
  a1[8] = v15;
  *((_BYTE *)a1 + 72) = v8;
  LOBYTE(v16) = 0;
  std::_Sort_unchecked<std::wstring *,std::less<void>>(*a1, a1[1], (__int64)(a1[1] - *a1) >> 5, v16);
  v24 = (char *)a1[1];
  v25 = *(char **)std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(&v36, *a1, v24);
  if ( v25 != v24 )
  {
    v26 = (char *)a1[1];
    while ( v24 != v26 )
    {
      std::wstring::operator=(v25, v24);
      v25 += 32;
      v24 += 32;
    }
    v27 = (char *)a1[1];
    for ( i = v25; i != v27; i += 32 )
      std::wstring::~wstring(i);
    a1[1] = v25;
  }
  std::vector<CbsLanguageFeature>::_Tidy(v41);
  std::vector<std::wstring>::_Tidy(&v30);
  std::vector<std::wstring>::_Tidy(&v33);
  std::vector<CbsLanguageFeature>::_Tidy(&v37);
  std::vector<std::wstring>::_Tidy(a3);
  std::vector<std::wstring>::_Tidy(a4);
  return a1;
}

```

## disassembly

```asm
0x180011d10  push    rbp
0x180011d12  push    rbx
0x180011d13  push    rsi
0x180011d14  push    rdi
0x180011d15  push    r12
0x180011d17  push    r14
0x180011d19  push    r15
0x180011d1b  lea     rbp, [rsp-27h]
0x180011d20  sub     rsp, 100h
0x180011d27  mov     rax, cs:__security_cookie
0x180011d2e  xor     rax, rsp
0x180011d31  mov     [rbp+57h+var_38], rax
0x180011d35  mov     r12, r9
0x180011d38  mov     r15, r8
0x180011d3b  mov     rbx, rdx
0x180011d3e  mov     rsi, rcx
0x180011d41  mov     [rbp+57h+var_70], rcx
0x180011d45  mov     [rbp+57h+var_48], r8
0x180011d49  mov     [rbp+57h+var_40], r9
0x180011d4d  xor     r14d, r14d
0x180011d50  mov     dil, [rdx+0A0h]
0x180011d57  and     dil, 1
0x180011d5b  lea     rax, [rsp+130h+var_E8]
0x180011d60  mov     [rbp+57h+var_B0], rax
0x180011d64  mov     rdx, [r9+10h]
0x180011d68  mov     [r9+10h], r14
0x180011d6c  mov     rcx, [r9+8]
0x180011d70  mov     [r9+8], r14
0x180011d74  mov     rax, [r9]
0x180011d77  mov     [r9], r14
0x180011d7a  mov     [rsp+130h+var_E8], rax
0x180011d7f  mov     [rsp+130h+var_E0], rcx
0x180011d84  mov     [rsp+130h+var_D8], rdx
0x180011d89  lea     rax, [rsp+130h+var_E8]
0x180011d8e  mov     [rbp+57h+var_60], rax
0x180011d92  lea     rax, [rsp+130h+var_100]
0x180011d97  mov     [rbp+57h+var_58], rax
0x180011d9b  mov     rdx, [r8+10h]
0x180011d9f  mov     [r8+10h], r14
0x180011da3  mov     rcx, [r8+8]
0x180011da7  mov     [r8+8], r14
0x180011dab  mov     rax, [r8]
0x180011dae  mov     [r8], r14
0x180011db1  mov     [rsp+130h+var_100], rax
0x180011db6  mov     [rsp+130h+var_F8], rcx
0x180011dbb  mov     [rsp+130h+var_F0], rdx
0x180011dc0  lea     rax, [rsp+130h+var_100]
0x180011dc5  mov     [rbp+57h+var_50], rax
0x180011dc9  xorps   xmm0, xmm0
0x180011dcc  movups  [rbp+57h+var_90], xmm0
0x180011dd0  xorps   xmm1, xmm1
0x180011dd3  movdqu  [rbp+57h+var_80], xmm1
0x180011dd8  lea     r8d, [r14+8]
0x180011ddc  lea     rdx, aLanguage; "Language"
0x180011de3  lea     rcx, [rbp+57h+var_90]
0x180011de7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180011dec  nop
0x180011ded  lea     rax, ?IsInstalled@CbsLanguageSession@@CA_NAEBVCbsLanguageFeature@@@Z; CbsLanguageSession::IsInstalled(CbsLanguageFeature const &)
0x180011df4  mov     [rsp+130h+var_110], rax
0x180011df9  lea     r9d, [r14+1]
0x180011dfd  lea     r8, [rbp+57h+var_90]
0x180011e01  lea     rdx, [rbp+57h+var_C8]
0x180011e05  mov     rcx, rbx
0x180011e08  call    ??$FeaturesOfCapability@VCbsLanguageFeature@@$$A6A_NAEBV1@@Z@CbsSession@@QEBA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@IA6A_NAEBVCbsLanguageFeature@@@Z@Z; CbsSession::FeaturesOfCapability<CbsLanguageFeature,bool (CbsLanguageFeature const &)>(std::wstring const &,uint,bool (&)(CbsLanguageFeature const &))
0x180011e0d  nop
0x180011e0e  lea     rcx, [rbp+57h+var_90]; void *
0x180011e12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011e17  nop
0x180011e18  mov     r10, [rbp+57h+var_B8]
0x180011e1c  mov     [rbp+57h+var_B8], r14
0x180011e20  mov     r9, [rbp+57h+var_C0]
0x180011e24  mov     [rbp+57h+var_C0], r14
0x180011e28  mov     r8, [rbp+57h+var_C8]
0x180011e2c  mov     [rbp+57h+var_C8], r14
0x180011e30  lea     rax, [rbp+57h+var_A8]
0x180011e34  mov     [rbp+57h+var_D0], rax
0x180011e38  mov     rdx, [rsp+130h+var_F0]
0x180011e3d  mov     [rsp+130h+var_F0], r14
0x180011e42  mov     rcx, [rsp+130h+var_F8]
0x180011e47  mov     [rsp+130h+var_F8], r14
0x180011e4c  mov     rax, [rsp+130h+var_100]
0x180011e51  mov     [rsp+130h+var_100], r14
0x180011e56  mov     [rsi], rax
0x180011e59  mov     [rsi+8], rcx
0x180011e5d  mov     [rsi+10h], rdx
0x180011e61  mov     rdx, [rsp+130h+var_D8]
0x180011e66  mov     [rsp+130h+var_D8], r14
0x180011e6b  mov     rcx, [rsp+130h+var_E0]
0x180011e70  mov     [rsp+130h+var_E0], r14
0x180011e75  mov     rax, [rsp+130h+var_E8]
0x180011e7a  mov     [rsp+130h+var_E8], r14
0x180011e7f  mov     [rsi+18h], rax
0x180011e83  mov     [rsi+20h], rcx
0x180011e87  mov     [rsi+28h], rdx
0x180011e8b  mov     [rbp+57h+var_98], r14
0x180011e8f  mov     [rbp+57h+var_A0], r14
0x180011e93  mov     [rbp+57h+var_A8], r14
0x180011e97  mov     [rsi+30h], r8
0x180011e9b  mov     [rsi+38h], r9
0x180011e9f  mov     [rsi+40h], r10
0x180011ea3  mov     [rsi+48h], dil
0x180011ea7  mov     rdx, [rsi+8]
0x180011eab  mov     r9b, r14b
0x180011eae  mov     r8, rdx
0x180011eb1  sub     r8, [rsi]
0x180011eb4  sar     r8, 5
0x180011eb8  mov     rcx, [rsi]
0x180011ebb  call    ??$_Sort_unchecked@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@X@2@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::wstring *,std::less<void>>(std::wstring *,std::wstring *,__int64,std::less<void>)
0x180011ec0  mov     rdi, [rsi+8]
0x180011ec4  mov     r8, rdi
0x180011ec7  mov     rdx, [rsi]
0x180011eca  lea     rcx, [rbp+57h+var_D0]
0x180011ece  call    ??$unique@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@0@Z; std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>)
0x180011ed3  mov     rbx, [rax]
0x180011ed6  cmp     rbx, rdi
0x180011ed9  jz      short loc_180011F1A
0x180011edb  mov     r14, [rsi+8]
0x180011edf  jmp     short loc_180011EF4
0x180011ee1  mov     rdx, rdi
0x180011ee4  mov     rcx, rbx
0x180011ee7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011eec  add     rbx, 20h ; ' '
0x180011ef0  add     rdi, 20h ; ' '
0x180011ef4  cmp     rdi, r14
0x180011ef7  jnz     short loc_180011EE1
0x180011ef9  mov     r14, [rsi+8]
0x180011efd  mov     rdi, rbx
0x180011f00  cmp     rbx, r14
0x180011f03  jz      short loc_180011F16
0x180011f05  mov     rcx, rdi; void *
0x180011f08  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f0d  add     rdi, 20h ; ' '
0x180011f11  cmp     rdi, r14
0x180011f14  jnz     short loc_180011F05
0x180011f16  mov     [rsi+8], rbx
0x180011f1a  lea     rcx, [rbp+57h+var_A8]
0x180011f1e  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x180011f23  nop
0x180011f24  lea     rcx, [rsp+130h+var_100]
0x180011f29  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180011f2e  nop
0x180011f2f  lea     rcx, [rsp+130h+var_E8]
0x180011f34  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180011f39  nop
0x180011f3a  lea     rcx, [rbp+57h+var_C8]
0x180011f3e  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x180011f43  nop
0x180011f44  mov     rcx, r15
0x180011f47  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180011f4c  nop
0x180011f4d  mov     rcx, r12
0x180011f50  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180011f55  mov     rax, rsi
0x180011f58  mov     rcx, [rbp+57h+var_38]
0x180011f5c  xor     rcx, rsp; StackCookie
0x180011f5f  call    __security_check_cookie
0x180011f64  add     rsp, 100h
0x180011f6b  pop     r15
0x180011f6d  pop     r14
0x180011f6f  pop     r12
0x180011f71  pop     rdi
0x180011f72  pop     rsi
0x180011f73  pop     rbx
0x180011f74  pop     rbp
0x180011f75  retn
```
