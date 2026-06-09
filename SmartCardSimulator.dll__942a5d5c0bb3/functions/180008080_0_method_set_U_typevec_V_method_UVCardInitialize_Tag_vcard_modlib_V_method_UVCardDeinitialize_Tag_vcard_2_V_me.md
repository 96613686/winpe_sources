# ??0?$method_set@U?$typevec@V?$method@UVCardInitialize_Tag@vcard@@@modlib@@V?$method@UVCardDeinitialize_Tag@vcard@@@2@V?$method@UVCardOpen_Tag@vcard@@@2@V?$method@UVCardClose_Tag@vcard@@@2@V?$method@UVCardOpenChannel_Tag@vcard@@@2@V?$method@UVCardCloseChannel_Tag@vcard@@@2@V?$method@UVCardGetChallenge_Tag@vcard@@@2@V?$method@UVCardSetResponse_Tag@vcard@@@2@V?$method@UVCardInvalidateChallenge_Tag@vcard@@@2@V?$method@UVCardAuthenticatePin_Tag@vcard@@@2@V?$method@UVCardDeauthenticate_Tag@vcard@@@2@V?$method@UVCardGetPinLength_Tag@vcard@@@2@V?$method@UVCardGetRemainingRetryCount_Tag@vcard@@@2@V?$method@UVCardChangePin_Tag@vcard@@@2@V?$method@UVCardUnblockPin_Tag@vcard@@@2@V?$method@UVCardResetPin_Tag@vcard@@@2@V?$method@UVCardCreateKey_Tag@vcard@@@2@V?$method@UVCardGetTransportKeyAlg_Tag@vcard@@@2@V?$method@UVCardImportRsaKey_Tag@vcard@@@2@V?$method@UVCardImportSymKey_Tag@vcard@@@2@V?$method@UVCardDeleteKey_Tag@vcard@@@2@V?$method@UVCardGetKeyType_Tag@vcard@@@2@V?$method@UVCardExportRsaPubKey_Tag@vcard@@@2@V?$method@UVCardEncrypt_Tag@vcard@@@2@V?$method@UVCardDecrypt_Tag@vcard@@@2@V?$method@UVCardSignHash_Tag@vcard@@@2@V?$method@UVCardCreateClaim_Tag@vcard@@@2@V?$method@UVCardGetAikCertificate_Tag@vcard@@@2@V?$method@UVCardGetAikContainerName_Tag@vcard@@@2@@typveclib@@@modlib@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z

- ea: `0x180008080`
- end: `0x180008140`
- name: `??0?$method_set@U?$typevec@V?$method@UVCardInitialize_Tag@vcard@@@modlib@@V?$method@UVCardDeinitialize_Tag@vcard@@@2@V?$method@UVCardOpen_Tag@vcard@@@2@V?$method@UVCardClose_Tag@vcard@@@2@V?$method@UVCardOpenChannel_Tag@vcard@@@2@V?$method@UVCardCloseChannel_Tag@vcard@@@2@V?$method@UVCardGetChallenge_Tag@vcard@@@2@V?$method@UVCardSetResponse_Tag@vcard@@@2@V?$method@UVCardInvalidateChallenge_Tag@vcard@@@2@V?$method@UVCardAuthenticatePin_Tag@vcard@@@2@V?$method@UVCardDeauthenticate_Tag@vcard@@@2@V?$method@UVCardGetPinLength_Tag@vcard@@@2@V?$method@UVCardGetRemainingRetryCount_Tag@vcard@@@2@V?$method@UVCardChangePin_Tag@vcard@@@2@V?$method@UVCardUnblockPin_Tag@vcard@@@2@V?$method@UVCardResetPin_Tag@vcard@@@2@V?$method@UVCardCreateKey_Tag@vcard@@@2@V?$method@UVCardGetTransportKeyAlg_Tag@vcard@@@2@V?$method@UVCardImportRsaKey_Tag@vcard@@@2@V?$method@UVCardImportSymKey_Tag@vcard@@@2@V?$method@UVCardDeleteKey_Tag@vcard@@@2@V?$method@UVCardGetKeyType_Tag@vcard@@@2@V?$method@UVCardExportRsaPubKey_Tag@vcard@@@2@V?$method@UVCardEncrypt_Tag@vcard@@@2@V?$method@UVCardDecrypt_Tag@vcard@@@2@V?$method@UVCardSignHash_Tag@vcard@@@2@V?$method@UVCardCreateClaim_Tag@vcard@@@2@V?$method@UVCardGetAikCertificate_Tag@vcard@@@2@V?$method@UVCardGetAikContainerName_Tag@vcard@@@2@@typveclib@@@modlib@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000835c`
- `0x18001f6dc`

## callees

- `0x180003590`
- `0x180006b58`
- `0x180008018`
- `0x180008080`
- `0x1800086cc`
- `0x18000879c`
- `0x18000a960`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080db`

## string_xrefs

- `0x1800080ed`: `missing export on dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPCWSTR __fastcall __0__method_set_U__typevec_V__method_UVCardInitialize_Tag_vcard___modlib__V__method_UVCardDeinitialize_Tag_vcard___2_V__method_UVCardOpen_Tag_vcard___2_V__method_UVCardClose_Tag_vcard___2_V__method_UVCardOpenChannel_Tag_vcard___2_V__method_UVCardCloseChannel_Tag_vcard___2_V__method_UVCardGetChallenge_Tag_vcard___2_V__method_UVCardSetResponse_Tag_vcard___2_V__method_UVCardInvalidateChallenge_Tag_vcard___2_V__method_UVCardAuthenticatePin_Tag_vcard___2_V__method_UVCardDeauthenticate_Tag_vcard___2_V__method_UVCardGetPinLength_Tag_vcard___2_V__method_UVCardGetRemainingRetryCount_Tag_vcard___2_V__method_UVCardChangePin_Tag_vcard___2_V__method_UVCardUnblockPin_Tag_vcard___2_V__method_UVCardResetPin_Tag_vcard___2_V__method_UVCardCreateKey_Tag_vcard___2_V__method_UVCardGetTransportKeyAlg_Tag_vcard___2_V__method_UVCardImportRsaKey_Tag_vcard___2_V__method_UVCardImportSymKey_Tag_vcard___2_V__method_UVCardDeleteKey_Tag_vcard___2_V__method_UVCardGetKeyType_Tag_vcard___2_V__method_UVCardExportRsaPubKey_Tag_vcard___2_V__method_UVCardEncrypt_Tag_vcard___2_V__method_UVCardDecrypt_Tag_vcard___2_V__method_UVCardSignHash_Tag_vcard___2_V__method_UVCardCreateClaim_Tag_vcard___2_V__method_UVCardGetAikCertificate_Tag_vcard___2_V__method_UVCardGetAikContainerName_Tag_vcard___2__typveclib___modlib__QEAA_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___Z(
        LPCWSTR lpLibFileName,
        __int64 a2)
{
  __int64 v4; // rax
  FARPROC ProcAddress; // rax
  __int64 v6; // rdx
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v9[6]; // [rsp+48h] [rbp-50h] BYREF

  v9[5] = a2;
  v4 = std::wstring::wstring(v9, a2);
  modlib::library::library(lpLibFileName, v4);
  ____0AEAPEAUHINSTANCE_______scatter_U__typevec_iterator_U__typevec_V__method_UVCardInitialize_Tag_vcard___modlib__V__method_UVCardDeinitialize_Tag_vcard___2_V__method_UVCardOpen_Tag_vcard___2_V__method_UVCardClose_Tag_vcard___2_V__method_UVCardOpenChannel_Tag_vcard___2_V__method_UVCardCloseChannel_Tag_vcard___2_V__method_UVCardGetChallenge_Tag_vcard___2_V__method_UVCardSetResponse_Tag_vcard___2_V__method_UVCardInvalidateChallenge_Tag_vcard___2_V__method_UVCardAuthenticatePin_Tag_vcard___2_V__method_UVCardDeauthenticate_Tag_vcard___2_V__method_UVCardGetPinLength_Tag_vcard___2_V__method_UVCardGetRemainingRetryCount_Tag_vcard___2_V__method_UVCardChangePin_Tag_vcard___2_V__method_UVCardUnblockPin_Tag_vcard___2_V__method_UVCardResetPin_Tag_vcard___2_V__method_UVCardCreateKey_Tag_vcard___2_V__method_UVCardGetTransportKeyAlg_Tag_vcard___2_V__method_UVCardImportRsaKey_Tag_vcard___2_V__method_UVCardImportSymKey_Tag_vcard___2_V__method_UVCardDeleteKey_Tag_vcard___2_V__method_UVCardGetKeyType_Tag_vcard___2_V__method_UVCardExportRsaPubKey_Tag_vcard___2_V__method_UVCardEncrypt_Tag_vcard___2_V__method_UVCardDecrypt_Tag_vcard___2_V__method_UVCardSignHash_Tag_vcard___2_V__method_UVCardCreateClaim_Tag_vcard___2_V__method_UVCardGetAikCertificate_Tag_vcard___2_V__method_UVCardGetAikContainerName_Tag_vcard___2__typveclib___00_detail_typveclib__U__typevec_iterator_U__typevec_V__method_UVCardInitialize_Tag_vcard___modlib__V__method_UVCardDeinitialize_Tag_vcard___2_V__method_UVCardOpen_Tag_vcard___2_V__method_UVCardClose_Tag_vcard___2_V__method_UVCardOpenChannel_Tag_vcard___2_V__method_UVCardCloseChannel_Tag_vcard___2_V__method_UVCardGetChallenge_Tag_vcard___2_V__method_UVCardSetResponse_Tag_vcard___2_V__method_UVCardInvalidateChallenge_Tag_vcard___2_V__method_UVCardAuthenticatePin_Tag_vcard___2_V__method_UVCardDeauthenticate_Tag_vcard___2_V__method_UVCardGetPinLength_Tag_vcard___2_V__method_UVCardGetRemainingRetryCount_Tag_vcard___2_V__method_UVCardChangePin_Tag_vcard___2_V__method_UVCardUnblockPin_Tag_vcard___2_V__method_UVCardResetPin_Tag_vcard___2_V__method_UVCardCreateKey_Tag_vcard___2_V__method_UVCardGetTransportKeyAlg_Tag_vcard___2_V__method_UVCardImportRsaKey_Tag_vcard___2_V__method_UVCardImportSymKey_Tag_vcard___2_V__method_UVCardDeleteKey_Tag_vcard___2_V__method_UVCardGetKeyType_Tag_vcard___2_V__method_UVCardExportRsaPubKey_Tag_vcard___2_V__method_UVCardEncrypt_Tag_vcard___2_V__method_UVCardDecrypt_Tag_vcard___2_V__method_UVCardSignHash_Tag_vcard___2_V__method_UVCardCreateClaim_Tag_vcard___2_V__method_UVCardGetAikCertificate_Tag_vcard___2_V__method_UVCardGetAikContainerName_Tag_vcard___2__typveclib___0BN__23__00_detail_modlib__QEAA_AEAPEAUHINSTANCE_____Z(
    (__int64)(lpLibFileName + 28),
    (HMODULE *)lpLibFileName + 5);
  ProcAddress = GetProcAddress(*((HMODULE *)lpLibFileName + 5), "VCardInitialize");
  *((_QWORD *)lpLibFileName + 35) = ProcAddress;
  if ( !ProcAddress )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "missing export on dll");
    throw (std::runtime_error *)pExceptionObject;
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(a2, v6, 0);
  return lpLibFileName;
}

```

## disassembly

```asm
0x180008080  mov     r11, rsp
0x180008083  mov     [r11+18h], rbx
0x180008087  push    rbp
0x180008088  push    rsi
0x180008089  push    rdi
0x18000808a  sub     rsp, 80h
0x180008091  mov     rax, cs:__security_cookie
0x180008098  xor     rax, rsp
0x18000809b  mov     [rsp+98h+var_20], rax
0x1800080a0  mov     rbp, rdx
0x1800080a3  mov     rsi, rcx
0x1800080a6  mov     [r11-78h], rcx
0x1800080aa  mov     [r11-28h], rdx
0x1800080ae  lea     rcx, [r11-50h]
0x1800080b2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800080b7  mov     rdx, rax
0x1800080ba  mov     rcx, rsi; lpLibFileName
0x1800080bd  call    ??0library@modlib@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; modlib::library::library(std::wstring)
0x1800080c2  nop
0x1800080c3  lea     rdx, [rsi+28h]
0x1800080c7  lea     rcx, [rsi+38h]
0x1800080cb  call    ??$?0AEAPEAUHINSTANCE__@@@?$scatter@U?$typevec_iterator@U?$typevec@V?$method@UVCardInitialize_Tag@vcard@@@modlib@@V?$method@UVCardDeinitialize_Tag@vcard@@@2@V?$method@UVCardOpen_Tag@vcard@@@2@V?$method@UVCardClose_Tag@vcard@@@2@V?$method@UVCardOpenChannel_Tag@vcard@@@2@V?$method@UVCardCloseChannel_Tag@vcard@@@2@V?$method@UVCardGetChallenge_Tag@vcard@@@2@V?$method@UVCardSetResponse_Tag@vcard@@@2@V?$method@UVCardInvalidateChallenge_Tag@vcard@@@2@V?$method@UVCardAuthenticatePin_Tag@vcard@@@2@V?$method@UVCardDeauthenticate_Tag@vcard@@@2@V?$method@UVCardGetPinLength_Tag@vcard@@@2@V?$method@UVCardGetRemainingRetryCount_Tag@vcard@@@2@V?$method@UVCardChangePin_Tag@vcard@@@2@V?$method@UVCardUnblockPin_Tag@vcard@@@2@V?$method@UVCardResetPin_Tag@vcard@@@2@V?$method@UVCardCreateKey_Tag@vcard@@@2@V?$method@UVCardGetTransportKeyAlg_Tag@vcard@@@2@V?$method@UVCardImportRsaKey_Tag@vcard@@@2@V?$method@UVCardImportSymKey_Tag@vcard@@@2@V?$method@UVCardDeleteKey_Tag@vcard@@@2@V?$method@UVCardGetKeyType_Tag@vcard@@@2@V?$method@UVCardExportRsaPubKey_Tag@vcard@@@2@V?$method@UVCardEncrypt_Tag@vcard@@@2@V?$method@UVCardDecrypt_Tag@vcard@@@2@V?$method@UVCardSignHash_Tag@vcard@@@2@V?$method@UVCardCreateClaim_Tag@vcard@@@2@V?$method@UVCardGetAikCertificate_Tag@vcard@@@2@V?$method@UVCardGetAikContainerName_Tag@vcard@@@2@@typveclib@@$00@detail@typveclib@@U?$typevec_iterator@U?$typevec@V?$method@UVCardInitialize_Tag@vcard@@@modlib@@V?$method@UVCardDeinitialize_Tag@vcard@@@2@V?$method@UVCardOpen_Tag@vcard@@@2@V?$method@UVCardClose_Tag@vcard@@@2@V?$method@UVCardOpenChannel_Tag@vcard@@@2@V?$method@UVCardCloseChannel_Tag@vcard@@@2@V?$method@UVCardGetChallenge_Tag@vcard@@@2@V?$method@UVCardSetResponse_Tag@vcard@@@2@V?$method@UVCardInvalidateChallenge_Tag@vcard@@@2@V?$method@UVCardAuthenticatePin_Tag@vcard@@@2@V?$method@UVCardDeauthenticate_Tag@vcard@@@2@V?$method@UVCardGetPinLength_Tag@vcard@@@2@V?$method@UVCardGetRemainingRetryCount_Tag@vcard@@@2@V?$method@UVCardChangePin_Tag@vcard@@@2@V?$method@UVCardUnblockPin_Tag@vcard@@@2@V?$method@UVCardResetPin_Tag@vcard@@@2@V?$method@UVCardCreateKey_Tag@vcard@@@2@V?$method@UVCardGetTransportKeyAlg_Tag@vcard@@@2@V?$method@UVCardImportRsaKey_Tag@vcard@@@2@V?$method@UVCardImportSymKey_Tag@vcard@@@2@V?$method@UVCardDeleteKey_Tag@vcard@@@2@V?$method@UVCardGetKeyType_Tag@vcard@@@2@V?$method@UVCardExportRsaPubKey_Tag@vcard@@@2@V?$method@UVCardEncrypt_Tag@vcard@@@2@V?$method@UVCardDecrypt_Tag@vcard@@@2@V?$method@UVCardSignHash_Tag@vcard@@@2@V?$method@UVCardCreateClaim_Tag@vcard@@@2@V?$method@UVCardGetAikCertificate_Tag@vcard@@@2@V?$method@UVCardGetAikContainerName_Tag@vcard@@@2@@typveclib@@$0BN@@23@$00@detail@modlib@@QEAA@AEAPEAUHINSTANCE__@@@Z
0x1800080d0  lea     rdx, aVcardinitializ; "VCardInitialize"
0x1800080d7  mov     rcx, [rsi+28h]; hModule
0x1800080db  call    cs:__imp_GetProcAddress
0x1800080e1  mov     [rsi+118h], rax
0x1800080e8  test    rax, rax
0x1800080eb  jnz     short loc_180008110
0x1800080ed  lea     rdx, aMissingExportO; "missing export on dll"
0x1800080f4  lea     rcx, [rsp+98h+pExceptionObject]; this
0x1800080f9  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800080fe  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180008105  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000810a  call    _CxxThrowException_0
0x180008110  xor     r8d, r8d
0x180008113  mov     dl, 1
0x180008115  mov     rcx, rbp
0x180008118  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000811d  mov     rax, rsi
0x180008120  mov     rcx, [rsp+98h+var_20]
0x180008125  xor     rcx, rsp; StackCookie
0x180008128  call    __security_check_cookie
0x18000812d  mov     rbx, [rsp+98h+arg_10]
0x180008135  add     rsp, 80h
0x18000813c  pop     rdi
0x18000813d  pop     rsi
0x18000813e  pop     rbp
0x18000813f  retn
```
