# GetSHA256Hash(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002dd34`
- end: `0x18002e170`
- name: `?GetSHA256Hash@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `1084`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c9f8`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000cb10`
- `0x18000d410`
- `0x18000d8b0`
- `0x18000eb18`
- `0x18000efa4`
- `0x18002382c`
- `0x18002386c`
- `0x180024de0`
- `0x180026c70`
- `0x18002dd34`
- `0x18002fc44`
- `0x18003084c`
- `0x18003c0b8`

## import_xrefs

- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18002dff3`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x18002dff3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18002e017`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x18002e017`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002dfdd`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002dfdd`
- `bcrypt!BCryptCreateHash` at `0x18002df37`
- `bcrypt!BCryptCreateHash` at `0x18002df37`
- `bcrypt!BCryptHashData` at `0x18002df79`
- `bcrypt!BCryptHashData` at `0x18002df79`
- `bcrypt!BCryptDestroyHash` at `0x18002de30`
- `bcrypt!BCryptDestroyHash` at `0x18002e070`
- `bcrypt!BCryptDestroyHash` at `0x18002e0cb`
- `bcrypt!BCryptDestroyHash` at `0x18002e105`
- `bcrypt!BCryptDestroyHash` at `0x18002de30`
- `bcrypt!BCryptDestroyHash` at `0x18002e070`
- `bcrypt!BCryptDestroyHash` at `0x18002e0cb`
- `bcrypt!BCryptDestroyHash` at `0x18002e105`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002de42`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002e082`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002e0dd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002e117`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002de42`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002e082`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002e0dd`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002e117`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002ddfa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002ddfa`
- `bcrypt!BCryptGetProperty` at `0x18002de9c`
- `bcrypt!BCryptGetProperty` at `0x18002de9c`
- `bcrypt!BCryptFinishHash` at `0x18002dfa6`
- `bcrypt!BCryptFinishHash` at `0x18002dfa6`

## string_xrefs

- `0x18002de06`: `BCryptOpenAlgorithmProvider failed %x`
- `0x18002df43`: `BCryptCreateHash failed %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetSHA256Hash(__int64 a1, __int64 a2)
{
  NTSTATUS Property; // ebx
  wchar_t *v5; // rcx
  unsigned int v6; // ebx
  PUCHAR v8; // rdi
  UCHAR *v9; // rax
  size_t v10; // rbx
  UCHAR *v11; // rdx
  PUCHAR v12; // r14
  UCHAR *v13; // r15
  unsigned int v14; // edi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-1B8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-1B0h] BYREF
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-1A8h] BYREF
  ULONG pcbResult; // [rsp+54h] [rbp-1A4h] BYREF
  PUCHAR pbHashObject[2]; // [rsp+58h] [rbp-1A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-190h]
  PUCHAR v24; // [rsp+70h] [rbp-188h] BYREF
  UCHAR *v25; // [rsp+78h] [rbp-180h]
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+88h] [rbp-170h]
  BCRYPT_ALG_HANDLE *p_phAlgorithm; // [rsp+90h] [rbp-168h]
  char v28; // [rsp+98h] [rbp-160h]
  char v29[8]; // [rsp+A0h] [rbp-158h] BYREF
  char v30[232]; // [rsp+A8h] [rbp-150h] BYREF
  PUCHAR pbInput[2]; // [rsp+190h] [rbp-68h] BYREF
  ULONG cbInput; // [rsp+1A0h] [rbp-58h]
  unsigned __int64 v33; // [rsp+1A8h] [rbp-50h]
  _BYTE v34[32]; // [rsp+1B0h] [rbp-48h] BYREF

  phAlgorithm = 0;
  hHash = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  *(_OWORD *)pbHashObject = 0;
  v23 = 0;
  std::vector<unsigned char>::vector<unsigned char>(&v24, 32);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v29);
  p_hHash = &hHash;
  p_phAlgorithm = &phAlgorithm;
  v28 = 1;
  WideToUtf8(pbInput, a1);
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property < 0 )
  {
    v5 = (wchar_t *)L"BCryptOpenAlgorithmProvider failed %x";
LABEL_3:
    SBServicingLogMessage(v5, (unsigned int)Property);
    v6 = Property | 0x10000000;
    std::string::_Tidy_deallocate(pbInput);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
LABEL_7:
    std::basic_ostringstream<unsigned short>::`vbase destructor'(v29);
    std::vector<unsigned char>::_Tidy(&v24);
    std::vector<unsigned char>::_Tidy(pbHashObject);
    return v6;
  }
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v5 = L"BCryptGetProperty failed %x";
    goto LABEL_3;
  }
  v8 = pbHashObject[1];
  if ( (PUCHAR)*(unsigned int *)pbOutput < (PUCHAR)(pbHashObject[1] - pbHashObject[0]) )
  {
    v9 = &pbHashObject[0][*(unsigned int *)pbOutput];
LABEL_15:
    pbHashObject[1] = v9;
    goto LABEL_16;
  }
  if ( (PUCHAR)*(unsigned int *)pbOutput > (PUCHAR)(pbHashObject[1] - pbHashObject[0]) )
  {
    if ( *(unsigned int *)pbOutput <= v23 - (unsigned __int64)pbHashObject[0] )
    {
      v10 = *(unsigned int *)pbOutput - (unsigned __int64)(pbHashObject[1] - pbHashObject[0]);
      memset_0(pbHashObject[1], 0, v10);
      v9 = &v8[v10];
      goto LABEL_15;
    }
    try
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(pbHashObject, *(unsigned int *)pbOutput);
    }
    catch ( std::bad_alloc )
    {
      SBServicingLogMessage((wchar_t *)L"GetSHA256Hash: failed to allocate hashObject buffer");
      std::string::_Tidy_deallocate(pbInput);
      if ( hHash )
        BCryptDestroyHash(hHash);
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      std::basic_ostringstream<unsigned short>::`vbase destructor'(v29);
      std::vector<unsigned char>::_Tidy(&v24);
      std::vector<unsigned char>::_Tidy(pbHashObject);
      return 2147942414LL;
    }
    catch ( std::exception )
    {
      SBServicingLogMessage((wchar_t *)L"GetSHA256Hash: unexpected exception during hashObject allocation");
      std::string::_Tidy_deallocate(pbInput);
      if ( hHash )
        BCryptDestroyHash(hHash);
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      v6 = -2147467259;
      goto LABEL_7;
    }
  }
LABEL_16:
  Property = BCryptCreateHash(phAlgorithm, &hHash, pbHashObject[0], *(ULONG *)pbOutput, 0, 0, 0);
  if ( Property < 0 )
  {
    v5 = L"BCryptCreateHash failed %x";
    goto LABEL_3;
  }
  v11 = (UCHAR *)pbInput;
  if ( v33 > 0xF )
    v11 = pbInput[0];
  Property = BCryptHashData(hHash, v11, cbInput, 0);
  if ( Property < 0 )
  {
    v5 = L"BCryptHashData failed %x";
    goto LABEL_3;
  }
  Property = BCryptFinishHash(hHash, v24, (_DWORD)v25 - (_DWORD)v24, 0);
  if ( Property < 0 )
  {
    v5 = L"BCryptFinishHash failed %x";
    goto LABEL_3;
  }
  v12 = v24;
  v13 = v25;
  while ( v12 != v13 )
  {
    v14 = *v12;
    v15 = std::basic_ostream<unsigned short>::operator<<(v29, std::hex);
    v16 = std::setw(v34, 2);
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, v16);
    *(_WORD *)(*(int *)(*(_QWORD *)v17 + 4LL) + v17 + 88) = 48;
    std::basic_ostream<unsigned short>::operator<<(v17, v14);
    ++v12;
  }
  std::basic_stringbuf<unsigned short>::str(v30, v34);
  std::wstring::operator=(a2, v34);
  std::wstring::_Tidy_deallocate(v34);
  std::string::_Tidy_deallocate(pbInput);
  if ( hHash )
    BCryptDestroyHash(hHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  std::basic_ostringstream<unsigned short>::`vbase destructor'(v29);
  std::vector<unsigned char>::_Tidy(&v24);
  std::vector<unsigned char>::_Tidy(pbHashObject);
  return 0;
}

```

## disassembly

```asm
0x18002dd34  mov     [rsp+arg_10], rbx
0x18002dd39  mov     [rsp+arg_18], rdi
0x18002dd3e  push    r12
0x18002dd40  push    r14
0x18002dd42  push    r15
0x18002dd44  sub     rsp, 1E0h
0x18002dd4b  mov     rax, cs:__security_cookie
0x18002dd52  xor     rax, rsp
0x18002dd55  mov     [rsp+1F8h+var_28], rax
0x18002dd5d  mov     r12, rdx
0x18002dd60  mov     rbx, rcx
0x18002dd63  mov     [rsp+1F8h+phAlgorithm], 0
0x18002dd6c  mov     [rsp+1F8h+hHash], 0
0x18002dd75  mov     dword ptr [rsp+1F8h+pbOutput], 0
0x18002dd7d  mov     [rsp+1F8h+var_1A4], 0
0x18002dd85  xorps   xmm0, xmm0
0x18002dd88  movdqu  xmmword ptr [rsp+1F8h+pbHashObject], xmm0
0x18002dd8e  mov     [rsp+1F8h+var_190], 0
0x18002dd97  mov     edx, 20h ; ' '
0x18002dd9c  lea     rcx, [rsp+1F8h+var_188]
0x18002dda1  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002dda6  nop
0x18002dda7  lea     rcx, [rsp+1F8h+var_158]
0x18002ddaf  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x18002ddb4  nop
0x18002ddb5  lea     rax, [rsp+1F8h+hHash]
0x18002ddba  mov     [rsp+1F8h+var_170], rax
0x18002ddc2  lea     rax, [rsp+1F8h+phAlgorithm]
0x18002ddc7  mov     [rsp+1F8h+var_168], rax
0x18002ddcf  mov     [rsp+1F8h+var_160], 1
0x18002ddd7  mov     rdx, rbx
0x18002ddda  lea     rcx, [rsp+1F8h+pbInput]
0x18002dde2  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x18002dde7  nop
0x18002dde8  xor     r9d, r9d; dwFlags
0x18002ddeb  xor     r8d, r8d; pszImplementation
0x18002ddee  lea     rdx, pszAlgId; "SHA256"
0x18002ddf5  lea     rcx, [rsp+1F8h+phAlgorithm]; phAlgorithm
0x18002ddfa  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002de00  mov     ebx, eax
0x18002de02  test    eax, eax
0x18002de04  jns     short loc_18002DE73
0x18002de06  lea     rcx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider failed %x"
0x18002de0d  mov     edx, ebx
0x18002de0f  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002de14  bts     ebx, 1Ch
0x18002de18  lea     rcx, [rsp+1F8h+pbInput]
0x18002de20  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002de25  nop
0x18002de26  mov     rcx, [rsp+1F8h+hHash]; hHash
0x18002de2b  test    rcx, rcx
0x18002de2e  jz      short loc_18002DE36
0x18002de30  call    cs:__imp_BCryptDestroyHash
0x18002de36  mov     rcx, [rsp+1F8h+phAlgorithm]; hAlgorithm
0x18002de3b  test    rcx, rcx
0x18002de3e  jz      short loc_18002DE49
0x18002de40  xor     edx, edx; dwFlags
0x18002de42  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002de48  nop
0x18002de49  lea     rcx, [rsp+1F8h+var_158]
0x18002de51  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18002de56  nop
0x18002de57  lea     rcx, [rsp+1F8h+var_188]
0x18002de5c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002de61  nop
0x18002de62  lea     rcx, [rsp+1F8h+pbHashObject]
0x18002de67  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002de6c  mov     eax, ebx
0x18002de6e  jmp     loc_18002E146
0x18002de73  mov     [rsp+1F8h+dwFlags], 0; dwFlags
0x18002de7b  lea     rax, [rsp+1F8h+var_1A4]
0x18002de80  mov     [rsp+1F8h+pcbResult], rax; pcbResult
0x18002de85  mov     r9d, 4; cbOutput
0x18002de8b  lea     r8, [rsp+1F8h+pbOutput]; pbOutput
0x18002de90  lea     rdx, aObjectlength; "ObjectLength"
0x18002de97  mov     rcx, [rsp+1F8h+phAlgorithm]; hObject
0x18002de9c  call    cs:__imp_BCryptGetProperty
0x18002dea2  mov     ebx, eax
0x18002dea4  test    eax, eax
0x18002dea6  jns     short loc_18002DEB4
0x18002dea8  lea     rcx, aBcryptgetprope_0; "BCryptGetProperty failed %x"
0x18002deaf  jmp     loc_18002DE0D
0x18002deb4  mov     ebx, dword ptr [rsp+1F8h+pbOutput]
0x18002deb8  mov     rdx, [rsp+1F8h+pbHashObject]
0x18002debd  mov     rdi, [rsp+1F8h+pbHashObject+8]
0x18002dec2  mov     rcx, rdi
0x18002dec5  sub     rcx, rdx
0x18002dec8  cmp     rbx, rcx
0x18002decb  jnb     short loc_18002DED3
0x18002decd  lea     rax, [rbx+rdx]
0x18002ded1  jmp     short loc_18002DF05
0x18002ded3  jbe     short loc_18002DF0A
0x18002ded5  mov     rax, [rsp+1F8h+var_190]
0x18002deda  sub     rax, rdx
0x18002dedd  cmp     rbx, rax
0x18002dee0  jbe     short loc_18002DEF1
0x18002dee2  mov     rdx, rbx
0x18002dee5  lea     rcx, [rsp+1F8h+pbHashObject]
0x18002deea  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002deef  jmp     short loc_18002DF0A
0x18002def1  sub     rbx, rcx
0x18002def4  mov     r8, rbx; Size
0x18002def7  xor     edx, edx; Val
0x18002def9  mov     rcx, rdi; void *
0x18002defc  call    memset_0
0x18002df01  lea     rax, [rbx+rdi]
0x18002df05  mov     [rsp+1F8h+pbHashObject+8], rax
0x18002df0a  mov     [rsp+1F8h+var_1C8], 0; dwFlags
0x18002df12  mov     [rsp+1F8h+dwFlags], 0; cbSecret
0x18002df1a  mov     [rsp+1F8h+pcbResult], 0; pbSecret
0x18002df23  mov     r9d, dword ptr [rsp+1F8h+pbOutput]; cbHashObject
0x18002df28  mov     r8, [rsp+1F8h+pbHashObject]; pbHashObject
0x18002df2d  lea     rdx, [rsp+1F8h+hHash]; phHash
0x18002df32  mov     rcx, [rsp+1F8h+phAlgorithm]; hAlgorithm
0x18002df37  call    cs:__imp_BCryptCreateHash
0x18002df3d  mov     ebx, eax
0x18002df3f  test    eax, eax
0x18002df41  jns     short loc_18002DF4F
0x18002df43  lea     rcx, aBcryptcreateha_0; "BCryptCreateHash failed %x"
0x18002df4a  jmp     loc_18002DE0D
0x18002df4f  lea     rdx, [rsp+1F8h+pbInput]
0x18002df57  cmp     [rsp+1F8h+var_50], 0Fh
0x18002df60  cmova   rdx, [rsp+1F8h+pbInput]; pbInput
0x18002df69  xor     r9d, r9d; dwFlags
0x18002df6c  mov     r8d, [rsp+1F8h+cbInput]; cbInput
0x18002df74  mov     rcx, [rsp+1F8h+hHash]; hHash
0x18002df79  call    cs:__imp_BCryptHashData
0x18002df7f  mov     ebx, eax
0x18002df81  test    eax, eax
0x18002df83  jns     short loc_18002DF91
0x18002df85  lea     rcx, aBcrypthashdata_0; "BCryptHashData failed %x"
0x18002df8c  jmp     loc_18002DE0D
0x18002df91  mov     rdx, [rsp+1F8h+var_188]; pbOutput
0x18002df96  mov     r8d, dword ptr [rsp+1F8h+var_180]
0x18002df9b  sub     r8d, edx; cbOutput
0x18002df9e  xor     r9d, r9d; dwFlags
0x18002dfa1  mov     rcx, [rsp+1F8h+hHash]; hHash
0x18002dfa6  call    cs:__imp_BCryptFinishHash
0x18002dfac  mov     ebx, eax
0x18002dfae  test    eax, eax
0x18002dfb0  jns     short loc_18002DFBE
0x18002dfb2  lea     rcx, aBcryptfinishha_0; "BCryptFinishHash failed %x"
0x18002dfb9  jmp     loc_18002DE0D
0x18002dfbe  mov     r14, [rsp+1F8h+var_188]
0x18002dfc3  mov     r15, [rsp+1F8h+var_180]
0x18002dfc8  jmp     short loc_18002E020
0x18002dfca  movzx   edi, byte ptr [r14]
0x18002dfce  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002dfd5  lea     rcx, [rsp+1F8h+var_158]
0x18002dfdd  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002dfe3  mov     rbx, rax
0x18002dfe6  mov     edx, 2
0x18002dfeb  lea     rcx, [rsp+1F8h+var_48]
0x18002dff3  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x18002dff9  mov     rdx, rax
0x18002dffc  mov     rcx, rbx
0x18002dfff  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBU?$_Smanip@_J@0@@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,std::_Smanip<__int64> const &)
0x18002e004  mov     rcx, [rax]
0x18002e007  movsxd  rdx, dword ptr [rcx+4]
0x18002e00b  mov     word ptr [rdx+rax+58h], 30h ; '0'
0x18002e012  mov     edx, edi
0x18002e014  mov     rcx, rax
0x18002e017  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x18002e01d  inc     r14
0x18002e020  cmp     r14, r15
0x18002e023  jnz     short loc_18002DFCA
0x18002e025  lea     rdx, [rsp+1F8h+var_48]
0x18002e02d  lea     rcx, [rsp+1F8h+var_150]
0x18002e035  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18002e03a  lea     rdx, [rsp+1F8h+var_48]
0x18002e042  mov     rcx, r12
0x18002e045  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002e04a  lea     rcx, [rsp+1F8h+var_48]
0x18002e052  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e057  nop
0x18002e058  lea     rcx, [rsp+1F8h+pbInput]
0x18002e060  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002e065  nop
0x18002e066  mov     rcx, [rsp+1F8h+hHash]; hHash
0x18002e06b  test    rcx, rcx
0x18002e06e  jz      short loc_18002E076
0x18002e070  call    cs:__imp_BCryptDestroyHash
0x18002e076  mov     rcx, [rsp+1F8h+phAlgorithm]; hAlgorithm
0x18002e07b  test    rcx, rcx
0x18002e07e  jz      short loc_18002E089
0x18002e080  xor     edx, edx; dwFlags
0x18002e082  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002e088  nop
0x18002e089  lea     rcx, [rsp+1F8h+var_158]
0x18002e091  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18002e096  nop
0x18002e097  lea     rcx, [rsp+1F8h+var_188]
0x18002e09c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002e0a1  nop
0x18002e0a2  lea     rcx, [rsp+1F8h+pbHashObject]
0x18002e0a7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002e0ac  xor     eax, eax
0x18002e0ae  jmp     loc_18002E146
0x18002e0b3  lea     rcx, [rsp+1F8h+pbInput]
0x18002e0bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002e0c0  nop
0x18002e0c1  mov     rcx, [rsp+1F8h+hHash]; hHash
0x18002e0c6  test    rcx, rcx
0x18002e0c9  jz      short loc_18002E0D1
0x18002e0cb  call    cs:__imp_BCryptDestroyHash
0x18002e0d1  mov     rcx, [rsp+1F8h+phAlgorithm]; hAlgorithm
0x18002e0d6  test    rcx, rcx
0x18002e0d9  jz      short loc_18002E0E3
0x18002e0db  xor     edx, edx; dwFlags
0x18002e0dd  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002e0e3  mov     ebx, 80004005h
0x18002e0e8  jmp     loc_18002DE49
0x18002e0ed  lea     rcx, [rsp+1F8h+pbInput]
0x18002e0f5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002e0fa  nop
0x18002e0fb  mov     rcx, [rsp+1F8h+hHash]; hHash
0x18002e100  test    rcx, rcx
0x18002e103  jz      short loc_18002E10B
0x18002e105  call    cs:__imp_BCryptDestroyHash
0x18002e10b  mov     rcx, [rsp+1F8h+phAlgorithm]; hAlgorithm
0x18002e110  test    rcx, rcx
0x18002e113  jz      short loc_18002E11E
0x18002e115  xor     edx, edx; dwFlags
0x18002e117  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002e11d  nop
0x18002e11e  lea     rcx, [rsp+1F8h+var_158]
0x18002e126  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x18002e12b  nop
0x18002e12c  lea     rcx, [rsp+1F8h+var_188]
0x18002e131  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002e136  nop
0x18002e137  lea     rcx, [rsp+1F8h+pbHashObject]
0x18002e13c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18002e141  mov     eax, 8007000Eh
0x18002e146  mov     rcx, [rsp+1F8h+var_28]
0x18002e14e  xor     rcx, rsp; StackCookie
0x18002e151  call    __security_check_cookie
0x18002e156  lea     r11, [rsp+1F8h+var_18]
0x18002e15e  mov     rbx, [r11+30h]
0x18002e162  mov     rdi, [r11+38h]
0x18002e166  mov     rsp, r11
0x18002e169  pop     r15
0x18002e16b  pop     r14
0x18002e16d  pop     r12
0x18002e16f  retn
```
