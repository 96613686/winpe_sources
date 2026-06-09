# NgcCtnrCommon::GenerateKeyNameHash(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18006fac8`
- end: `0x18006fcf9`
- name: `?GenerateKeyNameHash@NgcCtnrCommon@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c134`

## callees

- `0x180007670`
- `0x18000d60c`
- `0x18000d62c`
- `0x180011c1c`
- `0x180011c9c`
- `0x180017d70`
- `0x180018388`
- `0x18001ddec`
- `0x1800273c4`
- `0x18006f588`
- `0x18006fa04`
- `0x18006fa84`
- `0x18006fac8`
- `0x18006ff8c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006fb5b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18006fb5b`
- `bcrypt!BCryptHash` at `0x18006fbf8`
- `bcrypt!BCryptHash` at `0x18006fbf8`
- `bcrypt!BCryptGetProperty` at `0x18006fba0`
- `bcrypt!BCryptGetProperty` at `0x18006fba0`
- `CRYPT32!CryptBinaryToStringW` at `0x18006fc6d`
- `CRYPT32!CryptBinaryToStringW` at `0x18006fc6d`

## string_xrefs

- `0x18006fb11`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x18006fbaf`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x18006fc09`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`
- `0x18006fc7b`: `onecore\ds\security\ngc\ctnrsvc\common\ngcctnrcommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcCtnrCommon::GenerateKeyNameHash(const unsigned __int16 *a1, __int64 a2)
{
  unsigned int LastError; // ebx
  __int64 v5; // rdx
  int v6; // ebx
  NTSTATUS Property; // eax
  __int64 v8; // rdx
  int v9; // eax
  const char *v10; // r9
  int pcbResult; // [rsp+20h] [rbp-59h]
  unsigned __int64 v13; // [rsp+40h] [rbp-39h] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-31h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-29h] BYREF
  ULONG v16; // [rsp+58h] [rbp-21h] BYREF
  DWORD pcchString; // [rsp+5Ch] [rbp-1Dh] BYREF
  BYTE *pbBinary; // [rsp+60h] [rbp-19h] BYREF
  __int64 v19; // [rsp+68h] [rbp-11h]
  LPWSTR pszString[3]; // [rsp+78h] [rbp-1h] BYREF
  _BYTE v21[32]; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v13 = 0;
  LastError = StringCbLengthW(a1, 0xFFFFFFFE, &v13);
  if ( (LastError & 0x80000000) == 0 )
  {
    v6 = v13;
    if ( !v13 )
    {
      LastError = -2147024809;
      v5 = 41;
      goto LABEL_3;
    }
    phAlgorithm = 0;
    Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
    if ( Property >= 0 )
    {
      *(_DWORD *)pbOutput = 0;
      v16 = 0;
      Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &v16, 0);
      if ( Property >= 0 )
      {
        std::vector<unsigned char>::vector<unsigned char>(&pbBinary, *(unsigned int *)pbOutput);
        v9 = BCryptHash(phAlgorithm, 0, 0, a1);
        if ( v9 >= 0 )
        {
          std::vector<unsigned short>::vector<unsigned short>(pszString, 2 * (v19 - (_QWORD)pbBinary) + 1);
          pcchString = pszString[1] - pszString[0];
          if ( CryptBinaryToStringW(pbBinary, v19 - (_DWORD)pbBinary, 0x4000000Cu, pszString[0], &pcchString) )
          {
            std::wstring::wstring(v21, pszString[0]);
            std::wstring::operator=(a2, v21);
            std::wstring::_Tidy_deallocate(v21);
            std::vector<unsigned short>::_Tidy(pszString);
            std::vector<unsigned char>::_Tidy(&pbBinary);
            LastError = 0;
            goto LABEL_17;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x51,
                        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
                        v10);
          std::vector<unsigned short>::_Tidy(pszString);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x46,
                        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
                        (const char *)(unsigned int)v9,
                        v6);
        }
        std::vector<unsigned char>::_Tidy(&pbBinary);
LABEL_17:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
        return LastError;
      }
      v8 = 58;
    }
    else
    {
      v8 = 48;
    }
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
                  (const char *)(unsigned int)Property,
                  pcbResult);
    goto LABEL_17;
  }
  v5 = 36;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\ngcctnrcommon.cpp",
    (const char *)LastError,
    pcbResult);
  return LastError;
}

```

## disassembly

```asm
0x18006fac8  mov     [rsp-8+arg_10], rbx
0x18006facd  push    rbp
0x18006face  push    rsi
0x18006facf  push    rdi
0x18006fad0  lea     rbp, [rsp-47h]
0x18006fad5  sub     rsp, 0C0h
0x18006fadc  mov     rax, cs:__security_cookie
0x18006fae3  xor     rax, rsp
0x18006fae6  mov     [rbp+57h+var_20], rax
0x18006faea  mov     rsi, rdx
0x18006faed  mov     rdi, rcx
0x18006faf0  mov     [rbp+57h+var_90], 0
0x18006faf8  lea     r8, [rbp+57h+var_90]; unsigned __int64 *
0x18006fafc  mov     edx, 0FFFFFFFEh; unsigned __int64
0x18006fb01  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18006fb06  mov     ebx, eax
0x18006fb08  test    eax, eax
0x18006fb0a  jns     short loc_18006FB29
0x18006fb0c  mov     edx, 24h ; '$'; void *
0x18006fb11  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006fb18  mov     r9d, ebx; char *
0x18006fb1b  mov     rcx, [rbp+5Fh]; this
0x18006fb1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006fb24  jmp     loc_18006FCD8
0x18006fb29  mov     rbx, [rbp+57h+var_90]
0x18006fb2d  test    rbx, rbx
0x18006fb30  jnz     short loc_18006FB3E
0x18006fb32  mov     ebx, 80070057h
0x18006fb37  mov     edx, 29h ; ')'
0x18006fb3c  jmp     short loc_18006FB11
0x18006fb3e  mov     [rbp+57h+phAlgorithm], 0
0x18006fb46  xor     r9d, r9d; dwFlags
0x18006fb49  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18006fb50  lea     rdx, aSha256; "SHA256"
0x18006fb57  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18006fb5b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18006fb61  test    eax, eax
0x18006fb63  jns     short loc_18006FB6C
0x18006fb65  mov     edx, 30h ; '0'
0x18006fb6a  jmp     short loc_18006FBAF
0x18006fb6c  mov     dword ptr [rbp+57h+pbOutput], 0
0x18006fb73  mov     [rbp+57h+var_78], 0
0x18006fb7a  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x18006fb82  lea     rax, [rbp+57h+var_78]
0x18006fb86  mov     [rsp+0D0h+pcbResult], rax; int
0x18006fb8b  mov     r9d, 4; cbOutput
0x18006fb91  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18006fb95  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18006fb9c  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18006fba0  call    cs:__imp_BCryptGetProperty
0x18006fba6  test    eax, eax
0x18006fba8  jns     short loc_18006FBC9
0x18006fbaa  mov     edx, 3Ah ; ':'; void *
0x18006fbaf  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006fbb6  mov     r9d, eax; char *
0x18006fbb9  mov     rcx, [rbp+5Fh]; this
0x18006fbbd  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18006fbc2  mov     ebx, eax
0x18006fbc4  jmp     loc_18006FCCF
0x18006fbc9  mov     edx, dword ptr [rbp+57h+pbOutput]
0x18006fbcc  lea     rcx, [rbp+57h+pbBinary]
0x18006fbd0  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18006fbd5  nop
0x18006fbd6  mov     rcx, [rbp+57h+pbBinary]
0x18006fbda  mov     eax, dword ptr [rbp+57h+var_68]
0x18006fbdd  sub     eax, ecx
0x18006fbdf  mov     [rsp+0D0h+var_A0], eax
0x18006fbe3  mov     qword ptr [rsp+0D0h+dwFlags], rcx
0x18006fbe8  mov     dword ptr [rsp+0D0h+pcbResult], ebx; int
0x18006fbec  mov     r9, rdi
0x18006fbef  xor     r8d, r8d
0x18006fbf2  xor     edx, edx
0x18006fbf4  mov     rcx, [rbp+57h+phAlgorithm]
0x18006fbf8  call    cs:__imp_BCryptHash
0x18006fbfe  test    eax, eax
0x18006fc00  jns     short loc_18006FC2A
0x18006fc02  mov     rcx, [rbp+5Fh]; this
0x18006fc06  mov     r9d, eax; char *
0x18006fc09  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006fc10  mov     edx, 46h ; 'F'; void *
0x18006fc15  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18006fc1a  mov     ebx, eax
0x18006fc1c  lea     rcx, [rbp+57h+pbBinary]
0x18006fc20  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18006fc25  jmp     loc_18006FCCF
0x18006fc2a  mov     rdx, [rbp+57h+var_68]
0x18006fc2e  sub     rdx, [rbp+57h+pbBinary]
0x18006fc32  lea     rdx, ds:1[rdx*2]
0x18006fc3a  lea     rcx, [rbp+57h+pszString]
0x18006fc3e  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18006fc43  nop
0x18006fc44  mov     r9, [rbp+57h+pszString]; pszString
0x18006fc48  mov     rax, [rbp+57h+var_50]
0x18006fc4c  sub     rax, r9
0x18006fc4f  sar     rax, 1
0x18006fc52  mov     [rbp+57h+pcchString], eax
0x18006fc55  mov     rcx, [rbp+57h+pbBinary]; pbBinary
0x18006fc59  mov     edx, dword ptr [rbp+57h+var_68]
0x18006fc5c  sub     edx, ecx; cbBinary
0x18006fc5e  lea     rax, [rbp+57h+pcchString]
0x18006fc62  mov     [rsp+0D0h+pcbResult], rax; pcchString
0x18006fc67  mov     r8d, 4000000Ch; dwFlags
0x18006fc6d  call    cs:__imp_CryptBinaryToStringW
0x18006fc73  test    eax, eax
0x18006fc75  jnz     short loc_18006FC97
0x18006fc77  mov     rcx, [rbp+5Fh]; this
0x18006fc7b  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006fc82  lea     edx, [rax+51h]; void *
0x18006fc85  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006fc8a  mov     ebx, eax
0x18006fc8c  lea     rcx, [rbp+57h+pszString]
0x18006fc90  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18006fc95  jmp     short loc_18006FC1C
0x18006fc97  mov     rdx, [rbp+57h+pszString]
0x18006fc9b  lea     rcx, [rbp+57h+var_40]
0x18006fc9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006fca4  lea     rdx, [rbp+57h+var_40]
0x18006fca8  mov     rcx, rsi
0x18006fcab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006fcb0  lea     rcx, [rbp+57h+var_40]
0x18006fcb4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006fcb9  nop
0x18006fcba  lea     rcx, [rbp+57h+pszString]
0x18006fcbe  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18006fcc3  nop
0x18006fcc4  lea     rcx, [rbp+57h+pbBinary]
0x18006fcc8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18006fccd  xor     ebx, ebx
0x18006fccf  lea     rcx, [rbp+57h+phAlgorithm]
0x18006fcd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006fcd8  mov     eax, ebx
0x18006fcda  mov     rcx, [rbp+57h+var_20]
0x18006fcde  xor     rcx, rsp; StackCookie
0x18006fce1  call    __security_check_cookie
0x18006fce6  mov     rbx, [rsp+0D0h+arg_10]
0x18006fcee  add     rsp, 0C0h
0x18006fcf5  pop     rdi
0x18006fcf6  pop     rsi
0x18006fcf7  pop     rbp
0x18006fcf8  retn
```
