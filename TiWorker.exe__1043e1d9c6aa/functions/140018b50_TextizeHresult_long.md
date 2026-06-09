# TextizeHresult(long)

- ea: `0x140018b50`
- end: `0x1400191db`
- name: `?TextizeHresult@@YAPEBDJ@Z`
- size: `1675`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000e27c`

## callees

- `0x140018b50`

## string_xrefs

- `0x140018bf6`: `E_ACCESSDENIED`
- `0x140018ca5`: `CRYPT_E_ALREADY_DECRYPTED`
- `0x140018cdd`: `CRYPT_E_STREAM_MSG_NOT_READY`
- `0x140018daf`: `CRYPT_E_DELETED_PREV`
- `0x140018e0c`: `CRYPT_E_NO_REVOCATION_DLL`
- `0x140018f19`: `CRYPT_E_SECURITY_SETTINGS`
- `0x140018f11`: `CRYPT_E_NO_VERIFY_USAGE_DLL`
- `0x1400190ab`: `CERT_E_PATHLENCONST`

## pseudocode

```c
const char *__fastcall TextizeHresult(int a1)
{
  const char *v1; // rax
  bool v2; // zf
  const char *result; // rax
  const char *v4; // rdx

  if ( a1 > -2146885596 )
  {
    if ( a1 > -2146881228 )
    {
      if ( a1 <= -2146762486 )
      {
        if ( a1 == -2146762486 )
          return "CERT_E_CHAINING";
        if ( a1 > -2146762492 )
        {
          switch ( a1 )
          {
            case -2146762491:
              return "CERT_E_CRITICAL";
            case -2146762490:
              return "CERT_E_PURPOSE";
            case -2146762489:
              return "CERT_E_ISSUERCHAINING";
            case -2146762488:
              return "CERT_E_MALFORMED";
          }
          v1 = "CERT_E_UNTRUSTEDROOT";
          v2 = a1 == -2146762487;
        }
        else
        {
          switch ( a1 )
          {
            case -2146762492:
              return "CERT_E_PATHLENCONST";
            case -2146881023:
              return "CRYPT_E_ASN1_EXTENDED";
            case -2146881022:
              return "CRYPT_E_ASN1_NOEOD";
            case -2146762496:
              return "TRUST_E_NOSIGNATURE";
            case -2146762495:
              return "CERT_E_EXPIRED";
            case -2146762494:
              return "CERT_E_VALIDITYPERIODNESTING";
          }
          v1 = "CERT_E_ROLE";
          v2 = a1 == -2146762493;
        }
        goto LABEL_173;
      }
      if ( a1 <= -2146762477 )
      {
        switch ( a1 )
        {
          case -2146762477:
            return "CERT_E_INVALID_POLICY";
          case -2146762484:
            return "CERT_E_REVOKED";
          case -2146762483:
            return "CERT_E_UNTRUSTEDTESTROOT";
          case -2146762482:
            return "CERT_E_REVOCATION_FAILURE";
          case -2146762481:
            return "CERT_E_CN_NO_MATCH";
          case -2146762480:
            return "CERT_E_WRONG_USAGE";
        }
        v1 = "CERT_E_UNTRUSTEDCA";
        v2 = a1 == -2146762478;
        goto LABEL_173;
      }
      switch ( a1 )
      {
        case -2146762476:
          return "CERT_E_INVALID_NAME";
        case -2145124319:
          return "WU_E_TIME_OUT";
        case -2145099760:
          return "WU_E_DM_DOWNLOADSANDBOXNOTFOUND";
        default:
          if ( a1 )
          {
            result = "S_FALSE";
            if ( a1 != 1 )
              return "Unknown Error";
          }
          else
          {
            return "S_OK";
          }
          break;
      }
    }
    else
    {
      if ( a1 == -2146881228 )
        return "CRYPT_E_ASN1_NYI";
      if ( a1 <= -2146881277 )
      {
        if ( a1 == -2146881277 )
          return "CRYPT_E_ASN1_CORRUPT";
        if ( a1 > -2146885589 )
        {
          switch ( a1 )
          {
            case -2146885588:
              return "CRYPT_E_MISSING_PUBKEY_PARA";
            case -2146881536:
              return "CRYPT_E_OSS_ERROR";
            case -2146881280:
              return "CRYPT_E_ASN1_ERROR";
            case -2146881279:
              return "CRYPT_E_ASN1_INTERNAL";
          }
          v1 = "CRYPT_E_ASN1_EOD";
          v2 = a1 == -2146881278;
        }
        else
        {
          switch ( a1 )
          {
            case -2146885589:
              return "CRYPT_E_NO_TRUSTED_SIGNER";
            case -2146885595:
              return "CRYPT_E_FILERESIZED";
            case -2146885594:
              return "CRYPT_E_SECURITY_SETTINGS";
            case -2146885593:
              return "CRYPT_E_NO_VERIFY_USAGE_DLL";
            case -2146885592:
              return "CRYPT_E_NO_VERIFY_USAGE_CHECK";
            case -2146885591:
              return "CRYPT_E_VERIFY_USAGE_OFFLINE";
          }
          v1 = "CRYPT_E_NOT_IN_CTL";
          v2 = a1 == -2146885590;
        }
        goto LABEL_173;
      }
      if ( a1 == -2146881229 )
      {
        return "CRYPT_E_ASN1_PDU_TYPE";
      }
      else
      {
        switch ( a1 )
        {
          case -2146881276:
            result = "CRYPT_E_ASN1_LARGE";
            break;
          case -2146881275:
            result = "CRYPT_E_ASN1_CONSTRAINT";
            break;
          case -2146881274:
            result = "CRYPT_E_ASN1_MEMORY";
            break;
          case -2146881273:
            result = "CRYPT_E_ASN1_OVERFLOW";
            break;
          case -2146881272:
            result = "CRYPT_E_ASN1_BADPDU";
            break;
          case -2146881271:
            result = "CRYPT_E_ASN1_BADARGS";
            break;
          case -2146881270:
            result = "CRYPT_E_ASN1_BADREAL";
            break;
          case -2146881269:
            result = "CRYPT_E_ASN1_BADTAG";
            break;
          case -2146881268:
            result = "CRYPT_E_ASN1_CHOICE";
            break;
          case -2146881267:
            result = "CRYPT_E_ASN1_RULE";
            break;
          case -2146881266:
            result = "CRYPT_E_ASN1_UTF8";
            break;
          default:
LABEL_137:
            result = "Unknown Error";
            break;
        }
      }
    }
  }
  else
  {
    if ( a1 == -2146885596 )
      return "CRYPT_E_NOT_CHAR_STRING";
    if ( a1 > -2146889712 )
    {
      if ( a1 > -2146885620 )
      {
        if ( a1 > -2146885613 )
        {
          switch ( a1 )
          {
            case -2146885612:
              return "CRYPT_E_NOT_IN_REVOCATION_DATABASE";
            case -2146885600:
              return "CRYPT_E_INVALID_NUMERIC_STRING";
            case -2146885599:
              return "CRYPT_E_INVALID_PRINTABLE_STRING";
            case -2146885598:
              return "CRYPT_E_INVALID_IA5_STRING";
          }
          v1 = "CRYPT_E_INVALID_X500_STRING";
          v2 = a1 == -2146885597;
        }
        else
        {
          switch ( a1 )
          {
            case -2146885613:
              return "CRYPT_E_REVOCATION_OFFLINE";
            case -2146885619:
              return "CRYPT_E_BAD_MSG";
            case -2146885618:
              return "CRYPT_E_NO_SIGNER";
            case -2146885617:
              return "CRYPT_E_PENDING_CLOSE";
            case -2146885616:
              return "CRYPT_E_REVOKED";
            case -2146885615:
              return "CRYPT_E_NO_REVOCATION_DLL";
          }
          v1 = "CRYPT_E_NO_REVOCATION_CHECK";
          v2 = a1 == -2146885614;
        }
      }
      else
      {
        if ( a1 == -2146885620 )
          return "CRYPT_E_NO_DECRYPT_CERT";
        if ( a1 > -2146885626 )
        {
          switch ( a1 )
          {
            case -2146885625:
              return "CRYPT_E_SELF_SIGNED";
            case -2146885624:
              return "CRYPT_E_DELETED_PREV";
            case -2146885623:
              return "CRYPT_E_NO_MATCH";
            case -2146885622:
              return "CRYPT_E_UNEXPECTED_MSG_TYPE";
          }
          v1 = "CRYPT_E_NO_KEY_PROPERTY";
          v2 = a1 == -2146885621;
        }
        else
        {
          switch ( a1 )
          {
            case -2146885626:
              return "CRYPT_E_NO_PROVIDER";
            case -2146889711:
              return "CRYPT_E_STREAM_INSUFFICIENT_DATA";
            case -2146885631:
              return "CRYPT_E_BAD_LEN";
            case -2146885630:
              return "CRYPT_E_BAD_ENCODE";
            case -2146885629:
              return "CRYPT_E_FILE_ERROR";
            case -2146885628:
              return "CRYPT_E_NOT_FOUND";
          }
          v1 = "CRYPT_E_EXISTS";
          v2 = a1 == -2146885627;
        }
      }
      goto LABEL_173;
    }
    if ( a1 == -2146889712 )
      return "CRYPT_E_STREAM_MSG_NOT_READY";
    if ( a1 <= -2146889725 )
    {
      if ( a1 == -2146889725 )
        return "CRYPT_E_OID_FORMAT";
      if ( a1 > -2147024891 )
      {
        switch ( a1 )
        {
          case -2147024890:
            return "E_HANDLE";
          case -2147024882:
            return "E_OUTOFMEMORY";
          case -2147024809:
            return "E_INVALIDARG";
          case -2146889727:
            return "CRYPT_E_MSG_ERROR";
        }
        v1 = "CRYPT_E_UNKNOWN_ALGO";
        v2 = a1 == -2146889726;
      }
      else
      {
        switch ( a1 )
        {
          case -2147024891:
            return "E_ACCESSDENIED";
          case -2147467263:
            return "E_NOTIMPL";
          case -2147467262:
            return "E_NOINTERFACE";
          case -2147467261:
            return "E_POINTER";
          case -2147467260:
            return "E_ABORT";
          case -2147467259:
            return "E_FAIL";
        }
        v1 = "E_UNEXPECTED";
        v2 = a1 == -2147418113;
      }
LABEL_173:
      v4 = "Unknown Error";
      if ( v2 )
        return v1;
      return v4;
    }
    switch ( a1 )
    {
      case -2146889724:
        result = "CRYPT_E_INVALID_MSG_TYPE";
        break;
      case -2146889723:
        result = "CRYPT_E_UNEXPECTED_ENCODING";
        break;
      case -2146889722:
        result = "CRYPT_E_AUTH_ATTR_MISSING";
        break;
      case -2146889721:
        result = "CRYPT_E_HASH_VALUE";
        break;
      case -2146889720:
        result = "CRYPT_E_INVALID_INDEX";
        break;
      case -2146889719:
        result = "CRYPT_E_ALREADY_DECRYPTED";
        break;
      case -2146889718:
        result = "CRYPT_E_NOT_DECRYPTED";
        break;
      case -2146889717:
        result = "CRYPT_E_RECIPIENT_NOT_FOUND";
        break;
      case -2146889716:
        result = "CRYPT_E_CONTROL_TYPE";
        break;
      case -2146889715:
        result = "CRYPT_E_ISSUER_SERIALNUMBER";
        break;
      case -2146889714:
        result = "CRYPT_E_SIGNER_NOT_FOUND";
        break;
      case -2146889713:
        result = "CRYPT_E_ATTRIBUTES_MISSING";
        break;
      default:
        goto LABEL_137;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140018b50  mov     eax, 80092024h
0x140018b55  cmp     ecx, eax
0x140018b57  jg      loc_140018E96
0x140018b5d  jz      loc_140018E8E
0x140018b63  mov     eax, 80091010h
0x140018b68  cmp     ecx, eax
0x140018b6a  jg      loc_140018CE5
0x140018b70  jz      loc_140018CDD
0x140018b76  mov     eax, 80091003h
0x140018b7b  cmp     ecx, eax
0x140018b7d  jg      loc_140018C58
0x140018b83  jz      loc_140018C50
0x140018b89  mov     eax, 80070005h
0x140018b8e  cmp     ecx, eax
0x140018b90  jg      short loc_140018BFE
0x140018b92  jz      short loc_140018BF6
0x140018b94  cmp     ecx, 80004001h
0x140018b9a  jz      short loc_140018BEE
0x140018b9c  cmp     ecx, 80004002h
0x140018ba2  jz      short loc_140018BE6
0x140018ba4  cmp     ecx, 80004003h
0x140018baa  jz      short loc_140018BDE
0x140018bac  cmp     ecx, 80004004h
0x140018bb2  jz      short loc_140018BD6
0x140018bb4  cmp     ecx, 80004005h
0x140018bba  jz      short loc_140018BCE
0x140018bbc  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x140018bc3  cmp     ecx, 8000FFFFh
0x140018bc9  jmp     loc_14001914A
0x140018bce  lea     rax, aEFail; "E_FAIL"
0x140018bd5  retn
0x140018bd6  lea     rax, aEAbort; "E_ABORT"
0x140018bdd  retn
0x140018bde  lea     rax, aEPointer; "E_POINTER"
0x140018be5  retn
0x140018be6  lea     rax, aENointerface; "E_NOINTERFACE"
0x140018bed  retn
0x140018bee  lea     rax, aENotimpl; "E_NOTIMPL"
0x140018bf5  retn
0x140018bf6  lea     rax, aEAccessdenied; "E_ACCESSDENIED"
0x140018bfd  retn
0x140018bfe  cmp     ecx, 80070006h
0x140018c04  jz      short loc_140018C48
0x140018c06  cmp     ecx, 8007000Eh
0x140018c0c  jz      short loc_140018C40
0x140018c0e  cmp     ecx, 80070057h
0x140018c14  jz      short loc_140018C38
0x140018c16  cmp     ecx, 80091001h
0x140018c1c  jz      short loc_140018C30
0x140018c1e  lea     rax, aCryptEUnknownA; "CRYPT_E_UNKNOWN_ALGO"
0x140018c25  cmp     ecx, 80091002h
0x140018c2b  jmp     loc_14001914A
0x140018c30  lea     rax, aCryptEMsgError; "CRYPT_E_MSG_ERROR"
0x140018c37  retn
0x140018c38  lea     rax, aEInvalidarg; "E_INVALIDARG"
0x140018c3f  retn
0x140018c40  lea     rax, aEOutofmemory; "E_OUTOFMEMORY"
0x140018c47  retn
0x140018c48  lea     rax, aEHandle; "E_HANDLE"
0x140018c4f  retn
0x140018c50  lea     rax, aCryptEOidForma; "CRYPT_E_OID_FORMAT"
0x140018c57  retn
0x140018c58  add     ecx, 7FF6EFFCh; switch 12 cases
0x140018c5e  cmp     ecx, 0Bh
0x140018c61  ja      def_140018C7B; jumptable 0000000140018C7B default case
0x140018c67  movsxd  rax, ecx
0x140018c6a  lea     rcx, cs:140000000h
0x140018c71  mov     eax, ds:(jpt_140018C7B - 140000000h)[rcx+rax*4]
0x140018c78  add     rax, rcx
0x140018c7b  jmp     rax; switch jump
0x140018c7d  lea     rax, aCryptEInvalidM; jumptable 0000000140018C7B case -2146889724
0x140018c84  retn
0x140018c85  lea     rax, aCryptEUnexpect_0; jumptable 0000000140018C7B case -2146889723
0x140018c8c  retn
0x140018c8d  lea     rax, aCryptEAuthAttr; jumptable 0000000140018C7B case -2146889722
0x140018c94  retn
0x140018c95  lea     rax, aCryptEHashValu; jumptable 0000000140018C7B case -2146889721
0x140018c9c  retn
0x140018c9d  lea     rax, aCryptEInvalidI_0; jumptable 0000000140018C7B case -2146889720
0x140018ca4  retn
0x140018ca5  lea     rax, aCryptEAlreadyD; jumptable 0000000140018C7B case -2146889719
0x140018cac  retn
0x140018cad  lea     rax, aCryptENotDecry; jumptable 0000000140018C7B case -2146889718
0x140018cb4  retn
0x140018cb5  lea     rax, aCryptERecipien; jumptable 0000000140018C7B case -2146889717
0x140018cbc  retn
0x140018cbd  lea     rax, aCryptEControlT; jumptable 0000000140018C7B case -2146889716
0x140018cc4  retn
0x140018cc5  lea     rax, aCryptEIssuerSe; jumptable 0000000140018C7B case -2146889715
0x140018ccc  retn
0x140018ccd  lea     rax, aCryptESignerNo; jumptable 0000000140018C7B case -2146889714
0x140018cd4  retn
0x140018cd5  lea     rax, aCryptEAttribut; jumptable 0000000140018C7B case -2146889713
0x140018cdc  retn
0x140018cdd  lea     rax, aCryptEStreamMs; "CRYPT_E_STREAM_MSG_NOT_READY"
0x140018ce4  retn
0x140018ce5  mov     eax, 8009200Ch
0x140018cea  cmp     ecx, eax
0x140018cec  jg      loc_140018DC7
0x140018cf2  jz      loc_140018DBF
0x140018cf8  mov     eax, 80092006h
0x140018cfd  cmp     ecx, eax
0x140018cff  jg      short loc_140018D6D
0x140018d01  jz      short loc_140018D65
0x140018d03  cmp     ecx, 80091011h
0x140018d09  jz      short loc_140018D5D
0x140018d0b  cmp     ecx, 80092001h
0x140018d11  jz      short loc_140018D55
0x140018d13  cmp     ecx, 80092002h
0x140018d19  jz      short loc_140018D4D
0x140018d1b  cmp     ecx, 80092003h
0x140018d21  jz      short loc_140018D45
0x140018d23  cmp     ecx, 80092004h
0x140018d29  jz      short loc_140018D3D
0x140018d2b  lea     rax, aCryptEExists; "CRYPT_E_EXISTS"
0x140018d32  cmp     ecx, 80092005h
0x140018d38  jmp     loc_14001914A
0x140018d3d  lea     rax, aCryptENotFound; "CRYPT_E_NOT_FOUND"
0x140018d44  retn
0x140018d45  lea     rax, aCryptEFileErro; "CRYPT_E_FILE_ERROR"
0x140018d4c  retn
0x140018d4d  lea     rax, aCryptEBadEncod; "CRYPT_E_BAD_ENCODE"
0x140018d54  retn
0x140018d55  lea     rax, aCryptEBadLen; "CRYPT_E_BAD_LEN"
0x140018d5c  retn
0x140018d5d  lea     rax, aCryptEStreamIn; "CRYPT_E_STREAM_INSUFFICIENT_DATA"
0x140018d64  retn
0x140018d65  lea     rax, aCryptENoProvid; "CRYPT_E_NO_PROVIDER"
0x140018d6c  retn
0x140018d6d  cmp     ecx, 80092007h
0x140018d73  jz      short loc_140018DB7
0x140018d75  cmp     ecx, 80092008h
0x140018d7b  jz      short loc_140018DAF
0x140018d7d  cmp     ecx, 80092009h
0x140018d83  jz      short loc_140018DA7
0x140018d85  cmp     ecx, 8009200Ah
0x140018d8b  jz      short loc_140018D9F
0x140018d8d  lea     rax, aCryptENoKeyPro; "CRYPT_E_NO_KEY_PROPERTY"
0x140018d94  cmp     ecx, 8009200Bh
0x140018d9a  jmp     loc_14001914A
0x140018d9f  lea     rax, aCryptEUnexpect; "CRYPT_E_UNEXPECTED_MSG_TYPE"
0x140018da6  retn
0x140018da7  lea     rax, aCryptENoMatch; "CRYPT_E_NO_MATCH"
0x140018dae  retn
0x140018daf  lea     rax, aCryptEDeletedP; "CRYPT_E_DELETED_PREV"
0x140018db6  retn
0x140018db7  lea     rax, aCryptESelfSign; "CRYPT_E_SELF_SIGNED"
0x140018dbe  retn
0x140018dbf  lea     rax, aCryptENoDecryp; "CRYPT_E_NO_DECRYPT_CERT"
0x140018dc6  retn
0x140018dc7  mov     eax, 80092013h
0x140018dcc  cmp     ecx, eax
0x140018dce  jg      short loc_140018E3C
0x140018dd0  jz      short loc_140018E34
0x140018dd2  cmp     ecx, 8009200Dh
0x140018dd8  jz      short loc_140018E2C
0x140018dda  cmp     ecx, 8009200Eh
0x140018de0  jz      short loc_140018E24
0x140018de2  cmp     ecx, 8009200Fh
0x140018de8  jz      short loc_140018E1C
0x140018dea  cmp     ecx, 80092010h
0x140018df0  jz      short loc_140018E14
0x140018df2  cmp     ecx, 80092011h
0x140018df8  jz      short loc_140018E0C
0x140018dfa  lea     rax, aCryptENoRevoca; "CRYPT_E_NO_REVOCATION_CHECK"
0x140018e01  cmp     ecx, 80092012h
0x140018e07  jmp     loc_14001914A
0x140018e0c  lea     rax, aCryptENoRevoca_0; "CRYPT_E_NO_REVOCATION_DLL"
0x140018e13  retn
0x140018e14  lea     rax, aCryptERevoked; "CRYPT_E_REVOKED"
0x140018e1b  retn
0x140018e1c  lea     rax, aCryptEPendingC; "CRYPT_E_PENDING_CLOSE"
0x140018e23  retn
0x140018e24  lea     rax, aCryptENoSigner; "CRYPT_E_NO_SIGNER"
0x140018e2b  retn
0x140018e2c  lea     rax, aCryptEBadMsg; "CRYPT_E_BAD_MSG"
0x140018e33  retn
0x140018e34  lea     rax, aCryptERevocati; "CRYPT_E_REVOCATION_OFFLINE"
0x140018e3b  retn
0x140018e3c  cmp     ecx, 80092014h
0x140018e42  jz      short loc_140018E86
0x140018e44  cmp     ecx, 80092020h
0x140018e4a  jz      short loc_140018E7E
0x140018e4c  cmp     ecx, 80092021h
0x140018e52  jz      short loc_140018E76
0x140018e54  cmp     ecx, 80092022h
0x140018e5a  jz      short loc_140018E6E
0x140018e5c  lea     rax, aCryptEInvalidX; "CRYPT_E_INVALID_X500_STRING"
0x140018e63  cmp     ecx, 80092023h
0x140018e69  jmp     loc_14001914A
0x140018e6e  lea     rax, aCryptEInvalidI; "CRYPT_E_INVALID_IA5_STRING"
0x140018e75  retn
0x140018e76  lea     rax, aCryptEInvalidP; "CRYPT_E_INVALID_PRINTABLE_STRING"
0x140018e7d  retn
0x140018e7e  lea     rax, aCryptEInvalidN; "CRYPT_E_INVALID_NUMERIC_STRING"
0x140018e85  retn
0x140018e86  lea     rax, aCryptENotInRev; "CRYPT_E_NOT_IN_REVOCATION_DATABASE"
0x140018e8d  retn
0x140018e8e  lea     rax, aCryptENotCharS; "CRYPT_E_NOT_CHAR_STRING"
0x140018e95  retn
0x140018e96  mov     eax, 80093134h
0x140018e9b  cmp     ecx, eax
0x140018e9d  jg      loc_14001902B
0x140018ea3  jz      loc_140019023
0x140018ea9  mov     eax, 80093103h
0x140018eae  cmp     ecx, eax
0x140018eb0  jg      loc_140018F8B
0x140018eb6  jz      loc_140018F83
0x140018ebc  mov     eax, 8009202Bh
0x140018ec1  cmp     ecx, eax
0x140018ec3  jg      short loc_140018F31
0x140018ec5  jz      short loc_140018F29
0x140018ec7  cmp     ecx, 80092025h
0x140018ecd  jz      short loc_140018F21
0x140018ecf  cmp     ecx, 80092026h
0x140018ed5  jz      short loc_140018F19
0x140018ed7  cmp     ecx, 80092027h
0x140018edd  jz      short loc_140018F11
0x140018edf  cmp     ecx, 80092028h
0x140018ee5  jz      short loc_140018F09
0x140018ee7  cmp     ecx, 80092029h
0x140018eed  jz      short loc_140018F01
0x140018eef  lea     rax, aCryptENotInCtl; "CRYPT_E_NOT_IN_CTL"
0x140018ef6  cmp     ecx, 8009202Ah
0x140018efc  jmp     loc_14001914A
0x140018f01  lea     rax, aCryptEVerifyUs; "CRYPT_E_VERIFY_USAGE_OFFLINE"
0x140018f08  retn
0x140018f09  lea     rax, aCryptENoVerify; "CRYPT_E_NO_VERIFY_USAGE_CHECK"
0x140018f10  retn
0x140018f11  lea     rax, aCryptENoVerify_0; "CRYPT_E_NO_VERIFY_USAGE_DLL"
0x140018f18  retn
0x140018f19  lea     rax, aCryptESecurity; "CRYPT_E_SECURITY_SETTINGS"
0x140018f20  retn
0x140018f21  lea     rax, aCryptEFileresi; "CRYPT_E_FILERESIZED"
0x140018f28  retn
0x140018f29  lea     rax, aCryptENoTruste; "CRYPT_E_NO_TRUSTED_SIGNER"
0x140018f30  retn
0x140018f31  cmp     ecx, 8009202Ch
0x140018f37  jz      short loc_140018F7B
0x140018f39  cmp     ecx, 80093000h
0x140018f3f  jz      short loc_140018F73
0x140018f41  cmp     ecx, 80093100h
0x140018f47  jz      short loc_140018F6B
0x140018f49  cmp     ecx, 80093101h
0x140018f4f  jz      short loc_140018F63
0x140018f51  lea     rax, aCryptEAsn1Eod; "CRYPT_E_ASN1_EOD"
0x140018f58  cmp     ecx, 80093102h
0x140018f5e  jmp     loc_14001914A
0x140018f63  lea     rax, aCryptEAsn1Inte; "CRYPT_E_ASN1_INTERNAL"
0x140018f6a  retn
0x140018f6b  lea     rax, aCryptEAsn1Erro; "CRYPT_E_ASN1_ERROR"
0x140018f72  retn
0x140018f73  lea     rax, aCryptEOssError; "CRYPT_E_OSS_ERROR"
0x140018f7a  retn
0x140018f7b  lea     rax, aCryptEMissingP; "CRYPT_E_MISSING_PUBKEY_PARA"
0x140018f82  retn
0x140018f83  lea     rax, aCryptEAsn1Corr; "CRYPT_E_ASN1_CORRUPT"
0x140018f8a  retn
0x140018f8b  mov     eax, 80093133h
0x140018f90  cmp     ecx, eax
0x140018f92  jg      def_140018C7B; jumptable 0000000140018C7B default case
0x140018f98  jz      short loc_140019013
0x140018f9a  add     ecx, 7FF6CEFCh; switch 11 cases
0x140018fa0  cmp     ecx, 0Ah
0x140018fa3  ja      short def_140018C7B; jumptable 0000000140018C7B default case
0x140018fa5  movsxd  rax, ecx
0x140018fa8  lea     rcx, cs:140000000h
0x140018faf  mov     eax, ds:(jpt_140018FB9 - 140000000h)[rcx+rax*4]
0x140018fb6  add     rax, rcx
0x140018fb9  jmp     rax; switch jump
0x140018fbb  lea     rax, aCryptEAsn1Larg; jumptable 0000000140018FB9 case -2146881276
0x140018fc2  retn
0x140018fc3  lea     rax, aCryptEAsn1Cons; jumptable 0000000140018FB9 case -2146881275
0x140018fca  retn
0x140018fcb  lea     rax, aCryptEAsn1Memo; jumptable 0000000140018FB9 case -2146881274
0x140018fd2  retn
0x140018fd3  lea     rax, aCryptEAsn1Over; jumptable 0000000140018FB9 case -2146881273
0x140018fda  retn
0x140018fdb  lea     rax, aCryptEAsn1Badp; jumptable 0000000140018FB9 case -2146881272
0x140018fe2  retn
0x140018fe3  lea     rax, aCryptEAsn1Bada; jumptable 0000000140018FB9 case -2146881271
0x140018fea  retn
0x140018feb  lea     rax, aCryptEAsn1Badr; jumptable 0000000140018FB9 case -2146881270
0x140018ff2  retn
0x140018ff3  lea     rax, aCryptEAsn1Badt; jumptable 0000000140018FB9 case -2146881269
0x140018ffa  retn
0x140018ffb  lea     rax, aCryptEAsn1Choi; jumptable 0000000140018FB9 case -2146881268
0x140019002  retn
0x140019003  lea     rax, aCryptEAsn1Rule; jumptable 0000000140018FB9 case -2146881267
0x14001900a  retn
0x14001900b  lea     rax, aCryptEAsn1Utf8; jumptable 0000000140018FB9 case -2146881266
0x140019012  retn
0x140019013  lea     rax, aCryptEAsn1PduT; "CRYPT_E_ASN1_PDU_TYPE"
0x14001901a  retn
0x14001901b  lea     rax, Str2; jumptable 0000000140018C7B default case
0x140019022  retn
0x140019023  lea     rax, aCryptEAsn1Nyi; "CRYPT_E_ASN1_NYI"
0x14001902a  retn
0x14001902b  mov     eax, 800B010Ah
0x140019030  cmp     ecx, eax
  ... truncated ...
```
