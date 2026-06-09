# LicenseManagerCore::ContentIdMap<KeyEntry>::operator[](ContentIdString const &)

- ea: `0x18001e334`
- end: `0x18001e5a1`
- name: `??A?$ContentIdMap@UKeyEntry@@@LicenseManagerCore@@QEAAAEAUKeyEntry@@AEBVContentIdString@@@Z`
- size: `621`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003f5ec`
- `0x180067674`
- `0x1800944fc`

## callees

- `0x180004738`
- `0x180012dc0`
- `0x1800171b0`
- `0x18001e334`
- `0x18001f2d4`
- `0x18001f5ac`
- `0x180039dd0`
- `0x180044054`
- `0x1800445b4`
- `0x180075e60`
- `0x180076e64`
- `0x18008251f`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e3a9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e3a9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001e540`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001e540`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18001e506`
- `ext-ms-win-core-licensemanager-l1-1-0!CompareContentId` at `0x18001e506`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
const WCHAR *__fastcall LicenseManagerCore::ContentIdMap<KeyEntry>::operator[](const WCHAR **a1, const WCHAR *a2)
{
  const WCHAR *i; // rbx
  const WCHAR *v5; // rdi
  __int64 v6; // r15
  __int64 v7; // r12
  const WCHAR *v8; // rcx
  int v9; // eax
  unsigned __int64 v11; // r15
  const WCHAR *v12; // rdi
  const WCHAR *v13; // r14
  const WCHAR *v14; // rcx
  __int64 v15; // rdi
  _QWORD v16[2]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v17[48]; // [rsp+48h] [rbp-31h] BYREF
  __int128 v18; // [rsp+78h] [rbp-1h] BYREF
  __int128 v19; // [rsp+88h] [rbp+Fh]
  int v20; // [rsp+98h] [rbp+1Fh]
  __int64 v21; // [rsp+A0h] [rbp+27h] BYREF

  for ( i = *a1; i != a1[1]; i += 24 )
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v5 = a2;
    else
      v5 = *(const WCHAR **)a2;
    v6 = *((_QWORD *)a2 + 2);
    v7 = *((_QWORD *)i + 2);
    if ( (unsigned __int8)IsCompareContentIdPresent(a1) )
    {
      if ( *((_QWORD *)i + 3) <= 7u )
        v14 = i;
      else
        v14 = *(const WCHAR **)i;
      v9 = CompareContentId(v14, (unsigned int)v7, v5, (unsigned int)v6);
    }
    else
    {
      if ( *((_QWORD *)i + 3) <= 7u )
        v8 = i;
      else
        v8 = *(const WCHAR **)i;
      v9 = CompareStringOrdinal(v8, v7, v5, v6, 1) - 2;
    }
    if ( !v9 )
      goto LABEL_12;
  }
  i = a1[1];
LABEL_12:
  if ( i == a1[1] )
  {
    v16[0] = 0;
    v18 = 0;
    v19 = 0;
    v11 = *((_QWORD *)a2 + 2);
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const WCHAR **)a2;
    if ( v11 > 0x7FFFFFFFFFFFFFFELL )
      std::_Xlength_error("string too long");
    if ( v11 > 7 )
    {
      v15 = std::basic_string<unsigned short,content_id_char_traits,std::allocator<unsigned short>>::_Calculate_growth(
              v11,
              7,
              0x7FFFFFFFFFFFFFFELL);
      *(_QWORD *)&v18 = std::allocator<unsigned short>::allocate(&v18, v15 + 1);
      *(_QWORD *)&v19 = v11;
      *((_QWORD *)&v19 + 1) = v15;
      memcpy_0((void *)v18, a2, 2 * v11 + 2);
    }
    else
    {
      *(_QWORD *)&v19 = v11;
      *((_QWORD *)&v19 + 1) = 7;
      v18 = *(_OWORD *)a2;
    }
    v20 = 0;
    v21 = 0;
    v16[0] = 0;
    v12 = a1[1];
    if ( v12 == a1[2] )
    {
      i = (const WCHAR *)std::vector<std::pair<ContentIdString,KeyEntry>>::_Emplace_reallocate<std::pair<ContentIdString,KeyEntry>>(
                           a1,
                           i,
                           &v18);
    }
    else if ( i == v12 )
    {
      std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(a1[1], &v18);
      a1[1] += 24;
    }
    else
    {
      v16[1] = a1;
      std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(v17, &v18);
      v13 = v12 - 24;
      std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(v12, v12 - 24);
      a1[1] += 24;
      while ( v13 != i )
      {
        v13 -= 24;
        v12 -= 24;
        std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(v12, v13);
      }
      std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(i, v17);
      std::pair<ContentIdString,KeyEntry>::~pair<ContentIdString,KeyEntry>((ContentIdString *)v17);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
    ContentIdString::~ContentIdString((ContentIdString *)&v18);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v16);
  }
  return i + 16;
}

```

## disassembly

```asm
0x18001e334  mov     [rsp-8+arg_10], rbx
0x18001e339  mov     [rsp-8+arg_18], rsi
0x18001e33e  push    rbp
0x18001e33f  push    rdi
0x18001e340  push    r12
0x18001e342  push    r14
0x18001e344  push    r15
0x18001e346  lea     rbp, [rsp-37h]
0x18001e34b  sub     rsp, 0B0h
0x18001e352  mov     rax, cs:__security_cookie
0x18001e359  xor     rax, rsp
0x18001e35c  mov     [rbp+57h+var_28], rax
0x18001e360  mov     r14, rdx
0x18001e363  mov     rsi, rcx
0x18001e366  mov     rbx, [rcx]
0x18001e369  cmp     rbx, [rsi+8]
0x18001e36d  jz      short loc_18001E3BC
0x18001e36f  cmp     qword ptr [r14+18h], 7
0x18001e374  jbe     short loc_18001E3F2
0x18001e376  mov     rdi, [r14]
0x18001e379  mov     r15, [r14+10h]
0x18001e37d  mov     r12, [rbx+10h]
0x18001e381  call    IsCompareContentIdPresent
0x18001e386  test    al, al
0x18001e388  jnz     loc_18001E4F3
0x18001e38e  cmp     qword ptr [rbx+18h], 7
0x18001e393  jbe     short loc_18001E3F7
0x18001e395  mov     rcx, [rbx]; lpString1
0x18001e398  mov     r9d, r15d; cchCount2
0x18001e39b  mov     edx, r12d; cchCount1
0x18001e39e  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18001e3a6  mov     r8, rdi; lpString2
0x18001e3a9  call    cs:__imp_CompareStringOrdinal
0x18001e3af  sub     eax, 2
0x18001e3b2  test    eax, eax
0x18001e3b4  jz      short loc_18001E3C0
0x18001e3b6  add     rbx, 30h ; '0'
0x18001e3ba  jmp     short loc_18001E369
0x18001e3bc  mov     rbx, [rsi+8]
0x18001e3c0  cmp     rbx, [rsi+8]
0x18001e3c4  jz      short loc_18001E3FC
0x18001e3c6  lea     rax, [rbx+20h]
0x18001e3ca  mov     rcx, [rbp+57h+var_28]
0x18001e3ce  xor     rcx, rsp; StackCookie
0x18001e3d1  call    __security_check_cookie
0x18001e3d6  lea     r11, [rsp+0D0h+var_20]
0x18001e3de  mov     rbx, [r11+40h]
0x18001e3e2  mov     rsi, [r11+48h]
0x18001e3e6  mov     rsp, r11
0x18001e3e9  pop     r15
0x18001e3eb  pop     r14
0x18001e3ed  pop     r12
0x18001e3ef  pop     rdi
0x18001e3f0  pop     rbp
0x18001e3f1  retn
0x18001e3f2  mov     rdi, r14
0x18001e3f5  jmp     short loc_18001E379
0x18001e3f7  mov     rcx, rbx
0x18001e3fa  jmp     short loc_18001E398
0x18001e3fc  mov     [rbp+57h+var_A0], 0
0x18001e403  mov     [rbp+57h+var_98], 0
0x18001e40b  xorps   xmm0, xmm0
0x18001e40e  movups  [rbp+57h+var_58], xmm0
0x18001e412  xorps   xmm1, xmm1
0x18001e415  movdqu  [rbp+57h+var_48], xmm1
0x18001e41a  mov     r15, [r14+10h]
0x18001e41e  cmp     qword ptr [r14+18h], 7
0x18001e423  jbe     short loc_18001E428
0x18001e425  mov     r14, [r14]
0x18001e428  mov     r8, 7FFFFFFFFFFFFFFEh
0x18001e432  cmp     r15, r8
0x18001e435  ja      loc_18001E539
0x18001e43b  cmp     r15, 7
0x18001e43f  ja      loc_18001E547
0x18001e445  mov     qword ptr [rbp+57h+var_48], r15
0x18001e449  mov     qword ptr [rbp+57h+var_48+8], 7
0x18001e451  mov     rax, [r14]
0x18001e454  mov     qword ptr [rbp+57h+var_58], rax
0x18001e458  mov     rax, [r14+8]
0x18001e45c  mov     qword ptr [rbp+57h+var_58+8], rax
0x18001e460  mov     [rbp+57h+var_38], 0
0x18001e467  mov     [rbp+57h+var_30], 0
0x18001e46f  mov     [rbp+57h+var_98], 0
0x18001e477  mov     rdi, [rsi+8]
0x18001e47b  cmp     rdi, [rsi+10h]
0x18001e47f  jz      loc_18001E525
0x18001e485  lea     rdx, [rbp+57h+var_58]
0x18001e489  cmp     rbx, rdi
0x18001e48c  jz      loc_18001E516
0x18001e492  mov     [rbp+57h+var_90], rsi
0x18001e496  lea     rcx, [rbp+57h+var_88]
0x18001e49a  call    ??0?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(std::pair<ContentIdString,KeyEntry> &&)
0x18001e49f  lea     r14, [rdi-30h]
0x18001e4a3  mov     rdx, r14
0x18001e4a6  mov     rcx, rdi
0x18001e4a9  call    ??0?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(std::pair<ContentIdString,KeyEntry> &&)
0x18001e4ae  add     qword ptr [rsi+8], 30h ; '0'
0x18001e4b3  cmp     r14, rbx
0x18001e4b6  jnz     loc_18001E588
0x18001e4bc  lea     rdx, [rbp+57h+var_88]
0x18001e4c0  mov     rcx, rbx
0x18001e4c3  call    ??$?4U?$pair@VContentIdString@@UKeyEntry@@@std@@$0A@@?$pair@VContentIdString@@UKeyEntry@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(std::pair<ContentIdString,KeyEntry> &&)
0x18001e4c8  lea     rcx, [rbp+57h+var_88]; this
0x18001e4cc  call    ??1?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@XZ; std::pair<ContentIdString,KeyEntry>::~pair<ContentIdString,KeyEntry>(void)
0x18001e4d1  nop
0x18001e4d2  lea     rcx, [rbp+57h+var_30]
0x18001e4d6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e4db  lea     rcx, [rbp+57h+var_58]; this
0x18001e4df  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18001e4e4  nop
0x18001e4e5  lea     rcx, [rbp+57h+var_98]
0x18001e4e9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e4ee  jmp     loc_18001E3C6
0x18001e4f3  cmp     qword ptr [rbx+18h], 7
0x18001e4f8  jbe     short loc_18001E511
0x18001e4fa  mov     rcx, [rbx]
0x18001e4fd  mov     r9d, r15d
0x18001e500  mov     edx, r12d
0x18001e503  mov     r8, rdi
0x18001e506  call    cs:__imp_CompareContentId
0x18001e50c  jmp     loc_18001E3B2
0x18001e511  mov     rcx, rbx
0x18001e514  jmp     short loc_18001E4FD
0x18001e516  mov     rcx, rdi
0x18001e519  call    ??0?$pair@VContentIdString@@UKeyEntry@@@std@@QEAA@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::pair<ContentIdString,KeyEntry>(std::pair<ContentIdString,KeyEntry> &&)
0x18001e51e  add     qword ptr [rsi+8], 30h ; '0'
0x18001e523  jmp     short loc_18001E4D2
0x18001e525  lea     r8, [rbp+57h+var_58]
0x18001e529  mov     rdx, rbx
0x18001e52c  mov     rcx, rsi
0x18001e52f  call    ??$_Emplace_reallocate@U?$pair@VContentIdString@@UKeyEntry@@@std@@@?$vector@U?$pair@VContentIdString@@UKeyEntry@@@std@@V?$allocator@U?$pair@VContentIdString@@UKeyEntry@@@std@@@2@@std@@AEAAPEAU?$pair@VContentIdString@@UKeyEntry@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<ContentIdString,KeyEntry>>::_Emplace_reallocate<std::pair<ContentIdString,KeyEntry>>(std::pair<ContentIdString,KeyEntry> * const,std::pair<ContentIdString,KeyEntry> &&)
0x18001e534  mov     rbx, rax
0x18001e537  jmp     short loc_18001E4D2
0x18001e539  lea     rcx, aStringTooLong; "string too long"
0x18001e540  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001e547  mov     edx, 7
0x18001e54c  mov     rcx, r15
0x18001e54f  call    ?_Calculate_growth@?$basic_string@GUcontent_id_char_traits@@V?$allocator@G@std@@@std@@CA_K_K00@Z; std::basic_string<ushort,content_id_char_traits,std::allocator<ushort>>::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001e554  mov     rdi, rax
0x18001e557  lea     rdx, [rax+1]
0x18001e55b  lea     rcx, [rbp+57h+var_58]
0x18001e55f  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x18001e564  mov     qword ptr [rbp+57h+var_58], rax
0x18001e568  mov     qword ptr [rbp+57h+var_48], r15
0x18001e56c  mov     qword ptr [rbp+57h+var_48+8], rdi
0x18001e570  lea     r8, ds:2[r15*2]; Size
0x18001e578  mov     rdx, r14; Src
0x18001e57b  mov     rcx, rax; void *
0x18001e57e  call    memcpy_0
0x18001e583  jmp     loc_18001E460
0x18001e588  sub     r14, 30h ; '0'
0x18001e58c  sub     rdi, 30h ; '0'
0x18001e590  mov     rdx, r14
0x18001e593  mov     rcx, rdi
0x18001e596  call    ??$?4U?$pair@VContentIdString@@UKeyEntry@@@std@@$0A@@?$pair@VContentIdString@@UKeyEntry@@@std@@QEAAAEAU01@$$QEAU01@@Z; std::pair<ContentIdString,KeyEntry>::operator=<std::pair<ContentIdString,KeyEntry>,0>(std::pair<ContentIdString,KeyEntry> &&)
0x18001e59b  jmp     loc_18001E4B3
```
