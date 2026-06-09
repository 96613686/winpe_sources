# TextizeHresult(long)

- ea: `0x140018560`
- end: `0x140018beb`
- name: `?TextizeHresult@@YAPEBDJ@Z`
- size: `1675`
- prototype: `const char *__fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001272c`

## callees

- `0x140018560`

## string_xrefs

- `0x140018606`: `E_ACCESSDENIED`
- `0x1400186b5`: `CRYPT_E_ALREADY_DECRYPTED`
- `0x1400186ed`: `CRYPT_E_STREAM_MSG_NOT_READY`
- `0x1400187bf`: `CRYPT_E_DELETED_PREV`
- `0x14001881c`: `CRYPT_E_NO_REVOCATION_DLL`
- `0x140018929`: `CRYPT_E_SECURITY_SETTINGS`
- `0x140018921`: `CRYPT_E_NO_VERIFY_USAGE_DLL`
- `0x140018abb`: `CERT_E_PATHLENCONST`

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
0x140018560  mov     eax, 80092024h
0x140018565  cmp     ecx, eax
0x140018567  jg      loc_1400188A6
0x14001856d  jz      loc_14001889E
0x140018573  mov     eax, 80091010h
0x140018578  cmp     ecx, eax
0x14001857a  jg      loc_1400186F5
0x140018580  jz      loc_1400186ED
0x140018586  mov     eax, 80091003h
0x14001858b  cmp     ecx, eax
0x14001858d  jg      loc_140018668
0x140018593  jz      loc_140018660
0x140018599  mov     eax, 80070005h
0x14001859e  cmp     ecx, eax
0x1400185a0  jg      short loc_14001860E
0x1400185a2  jz      short loc_140018606
0x1400185a4  cmp     ecx, 80004001h
0x1400185aa  jz      short loc_1400185FE
0x1400185ac  cmp     ecx, 80004002h
0x1400185b2  jz      short loc_1400185F6
0x1400185b4  cmp     ecx, 80004003h
0x1400185ba  jz      short loc_1400185EE
0x1400185bc  cmp     ecx, 80004004h
0x1400185c2  jz      short loc_1400185E6
0x1400185c4  cmp     ecx, 80004005h
0x1400185ca  jz      short loc_1400185DE
0x1400185cc  lea     rax, aEUnexpected; "E_UNEXPECTED"
0x1400185d3  cmp     ecx, 8000FFFFh
0x1400185d9  jmp     loc_140018B5A
0x1400185de  lea     rax, aEFail; "E_FAIL"
0x1400185e5  retn
0x1400185e6  lea     rax, aEAbort; "E_ABORT"
0x1400185ed  retn
0x1400185ee  lea     rax, aEPointer; "E_POINTER"
0x1400185f5  retn
0x1400185f6  lea     rax, aENointerface; "E_NOINTERFACE"
0x1400185fd  retn
0x1400185fe  lea     rax, aENotimpl; "E_NOTIMPL"
0x140018605  retn
0x140018606  lea     rax, aEAccessdenied; "E_ACCESSDENIED"
0x14001860d  retn
0x14001860e  cmp     ecx, 80070006h
0x140018614  jz      short loc_140018658
0x140018616  cmp     ecx, 8007000Eh
0x14001861c  jz      short loc_140018650
0x14001861e  cmp     ecx, 80070057h
0x140018624  jz      short loc_140018648
0x140018626  cmp     ecx, 80091001h
0x14001862c  jz      short loc_140018640
0x14001862e  lea     rax, aCryptEUnknownA; "CRYPT_E_UNKNOWN_ALGO"
0x140018635  cmp     ecx, 80091002h
0x14001863b  jmp     loc_140018B5A
0x140018640  lea     rax, aCryptEMsgError; "CRYPT_E_MSG_ERROR"
0x140018647  retn
0x140018648  lea     rax, aEInvalidarg; "E_INVALIDARG"
0x14001864f  retn
0x140018650  lea     rax, aEOutofmemory; "E_OUTOFMEMORY"
0x140018657  retn
0x140018658  lea     rax, aEHandle; "E_HANDLE"
0x14001865f  retn
0x140018660  lea     rax, aCryptEOidForma; "CRYPT_E_OID_FORMAT"
0x140018667  retn
0x140018668  add     ecx, 7FF6EFFCh; switch 12 cases
0x14001866e  cmp     ecx, 0Bh
0x140018671  ja      def_14001868B; jumptable 000000014001868B default case
0x140018677  movsxd  rax, ecx
0x14001867a  lea     rcx, cs:140000000h
0x140018681  mov     eax, ds:(jpt_14001868B - 140000000h)[rcx+rax*4]
0x140018688  add     rax, rcx
0x14001868b  jmp     rax; switch jump
0x14001868d  lea     rax, aCryptEInvalidM; jumptable 000000014001868B case -2146889724
0x140018694  retn
0x140018695  lea     rax, aCryptEUnexpect_0; jumptable 000000014001868B case -2146889723
0x14001869c  retn
0x14001869d  lea     rax, aCryptEAuthAttr; jumptable 000000014001868B case -2146889722
0x1400186a4  retn
0x1400186a5  lea     rax, aCryptEHashValu; jumptable 000000014001868B case -2146889721
0x1400186ac  retn
0x1400186ad  lea     rax, aCryptEInvalidI_0; jumptable 000000014001868B case -2146889720
0x1400186b4  retn
0x1400186b5  lea     rax, aCryptEAlreadyD; jumptable 000000014001868B case -2146889719
0x1400186bc  retn
0x1400186bd  lea     rax, aCryptENotDecry; jumptable 000000014001868B case -2146889718
0x1400186c4  retn
0x1400186c5  lea     rax, aCryptERecipien; jumptable 000000014001868B case -2146889717
0x1400186cc  retn
0x1400186cd  lea     rax, aCryptEControlT; jumptable 000000014001868B case -2146889716
0x1400186d4  retn
0x1400186d5  lea     rax, aCryptEIssuerSe; jumptable 000000014001868B case -2146889715
0x1400186dc  retn
0x1400186dd  lea     rax, aCryptESignerNo; jumptable 000000014001868B case -2146889714
0x1400186e4  retn
0x1400186e5  lea     rax, aCryptEAttribut; jumptable 000000014001868B case -2146889713
0x1400186ec  retn
0x1400186ed  lea     rax, aCryptEStreamMs; "CRYPT_E_STREAM_MSG_NOT_READY"
0x1400186f4  retn
0x1400186f5  mov     eax, 8009200Ch
0x1400186fa  cmp     ecx, eax
0x1400186fc  jg      loc_1400187D7
0x140018702  jz      loc_1400187CF
0x140018708  mov     eax, 80092006h
0x14001870d  cmp     ecx, eax
0x14001870f  jg      short loc_14001877D
0x140018711  jz      short loc_140018775
0x140018713  cmp     ecx, 80091011h
0x140018719  jz      short loc_14001876D
0x14001871b  cmp     ecx, 80092001h
0x140018721  jz      short loc_140018765
0x140018723  cmp     ecx, 80092002h
0x140018729  jz      short loc_14001875D
0x14001872b  cmp     ecx, 80092003h
0x140018731  jz      short loc_140018755
0x140018733  cmp     ecx, 80092004h
0x140018739  jz      short loc_14001874D
0x14001873b  lea     rax, aCryptEExists; "CRYPT_E_EXISTS"
0x140018742  cmp     ecx, 80092005h
0x140018748  jmp     loc_140018B5A
0x14001874d  lea     rax, aCryptENotFound; "CRYPT_E_NOT_FOUND"
0x140018754  retn
0x140018755  lea     rax, aCryptEFileErro; "CRYPT_E_FILE_ERROR"
0x14001875c  retn
0x14001875d  lea     rax, aCryptEBadEncod; "CRYPT_E_BAD_ENCODE"
0x140018764  retn
0x140018765  lea     rax, aCryptEBadLen; "CRYPT_E_BAD_LEN"
0x14001876c  retn
0x14001876d  lea     rax, aCryptEStreamIn; "CRYPT_E_STREAM_INSUFFICIENT_DATA"
0x140018774  retn
0x140018775  lea     rax, aCryptENoProvid; "CRYPT_E_NO_PROVIDER"
0x14001877c  retn
0x14001877d  cmp     ecx, 80092007h
0x140018783  jz      short loc_1400187C7
0x140018785  cmp     ecx, 80092008h
0x14001878b  jz      short loc_1400187BF
0x14001878d  cmp     ecx, 80092009h
0x140018793  jz      short loc_1400187B7
0x140018795  cmp     ecx, 8009200Ah
0x14001879b  jz      short loc_1400187AF
0x14001879d  lea     rax, aCryptENoKeyPro; "CRYPT_E_NO_KEY_PROPERTY"
0x1400187a4  cmp     ecx, 8009200Bh
0x1400187aa  jmp     loc_140018B5A
0x1400187af  lea     rax, aCryptEUnexpect; "CRYPT_E_UNEXPECTED_MSG_TYPE"
0x1400187b6  retn
0x1400187b7  lea     rax, aCryptENoMatch; "CRYPT_E_NO_MATCH"
0x1400187be  retn
0x1400187bf  lea     rax, aCryptEDeletedP; "CRYPT_E_DELETED_PREV"
0x1400187c6  retn
0x1400187c7  lea     rax, aCryptESelfSign; "CRYPT_E_SELF_SIGNED"
0x1400187ce  retn
0x1400187cf  lea     rax, aCryptENoDecryp; "CRYPT_E_NO_DECRYPT_CERT"
0x1400187d6  retn
0x1400187d7  mov     eax, 80092013h
0x1400187dc  cmp     ecx, eax
0x1400187de  jg      short loc_14001884C
0x1400187e0  jz      short loc_140018844
0x1400187e2  cmp     ecx, 8009200Dh
0x1400187e8  jz      short loc_14001883C
0x1400187ea  cmp     ecx, 8009200Eh
0x1400187f0  jz      short loc_140018834
0x1400187f2  cmp     ecx, 8009200Fh
0x1400187f8  jz      short loc_14001882C
0x1400187fa  cmp     ecx, 80092010h
0x140018800  jz      short loc_140018824
0x140018802  cmp     ecx, 80092011h
0x140018808  jz      short loc_14001881C
0x14001880a  lea     rax, aCryptENoRevoca; "CRYPT_E_NO_REVOCATION_CHECK"
0x140018811  cmp     ecx, 80092012h
0x140018817  jmp     loc_140018B5A
0x14001881c  lea     rax, aCryptENoRevoca_0; "CRYPT_E_NO_REVOCATION_DLL"
0x140018823  retn
0x140018824  lea     rax, aCryptERevoked; "CRYPT_E_REVOKED"
0x14001882b  retn
0x14001882c  lea     rax, aCryptEPendingC; "CRYPT_E_PENDING_CLOSE"
0x140018833  retn
0x140018834  lea     rax, aCryptENoSigner; "CRYPT_E_NO_SIGNER"
0x14001883b  retn
0x14001883c  lea     rax, aCryptEBadMsg; "CRYPT_E_BAD_MSG"
0x140018843  retn
0x140018844  lea     rax, aCryptERevocati; "CRYPT_E_REVOCATION_OFFLINE"
0x14001884b  retn
0x14001884c  cmp     ecx, 80092014h
0x140018852  jz      short loc_140018896
0x140018854  cmp     ecx, 80092020h
0x14001885a  jz      short loc_14001888E
0x14001885c  cmp     ecx, 80092021h
0x140018862  jz      short loc_140018886
0x140018864  cmp     ecx, 80092022h
0x14001886a  jz      short loc_14001887E
0x14001886c  lea     rax, aCryptEInvalidX; "CRYPT_E_INVALID_X500_STRING"
0x140018873  cmp     ecx, 80092023h
0x140018879  jmp     loc_140018B5A
0x14001887e  lea     rax, aCryptEInvalidI; "CRYPT_E_INVALID_IA5_STRING"
0x140018885  retn
0x140018886  lea     rax, aCryptEInvalidP; "CRYPT_E_INVALID_PRINTABLE_STRING"
0x14001888d  retn
0x14001888e  lea     rax, aCryptEInvalidN; "CRYPT_E_INVALID_NUMERIC_STRING"
0x140018895  retn
0x140018896  lea     rax, aCryptENotInRev; "CRYPT_E_NOT_IN_REVOCATION_DATABASE"
0x14001889d  retn
0x14001889e  lea     rax, aCryptENotCharS; "CRYPT_E_NOT_CHAR_STRING"
0x1400188a5  retn
0x1400188a6  mov     eax, 80093134h
0x1400188ab  cmp     ecx, eax
0x1400188ad  jg      loc_140018A3B
0x1400188b3  jz      loc_140018A33
0x1400188b9  mov     eax, 80093103h
0x1400188be  cmp     ecx, eax
0x1400188c0  jg      loc_14001899B
0x1400188c6  jz      loc_140018993
0x1400188cc  mov     eax, 8009202Bh
0x1400188d1  cmp     ecx, eax
0x1400188d3  jg      short loc_140018941
0x1400188d5  jz      short loc_140018939
0x1400188d7  cmp     ecx, 80092025h
0x1400188dd  jz      short loc_140018931
0x1400188df  cmp     ecx, 80092026h
0x1400188e5  jz      short loc_140018929
0x1400188e7  cmp     ecx, 80092027h
0x1400188ed  jz      short loc_140018921
0x1400188ef  cmp     ecx, 80092028h
0x1400188f5  jz      short loc_140018919
0x1400188f7  cmp     ecx, 80092029h
0x1400188fd  jz      short loc_140018911
0x1400188ff  lea     rax, aCryptENotInCtl; "CRYPT_E_NOT_IN_CTL"
0x140018906  cmp     ecx, 8009202Ah
0x14001890c  jmp     loc_140018B5A
0x140018911  lea     rax, aCryptEVerifyUs; "CRYPT_E_VERIFY_USAGE_OFFLINE"
0x140018918  retn
0x140018919  lea     rax, aCryptENoVerify; "CRYPT_E_NO_VERIFY_USAGE_CHECK"
0x140018920  retn
0x140018921  lea     rax, aCryptENoVerify_0; "CRYPT_E_NO_VERIFY_USAGE_DLL"
0x140018928  retn
0x140018929  lea     rax, aCryptESecurity; "CRYPT_E_SECURITY_SETTINGS"
0x140018930  retn
0x140018931  lea     rax, aCryptEFileresi; "CRYPT_E_FILERESIZED"
0x140018938  retn
0x140018939  lea     rax, aCryptENoTruste; "CRYPT_E_NO_TRUSTED_SIGNER"
0x140018940  retn
0x140018941  cmp     ecx, 8009202Ch
0x140018947  jz      short loc_14001898B
0x140018949  cmp     ecx, 80093000h
0x14001894f  jz      short loc_140018983
0x140018951  cmp     ecx, 80093100h
0x140018957  jz      short loc_14001897B
0x140018959  cmp     ecx, 80093101h
0x14001895f  jz      short loc_140018973
0x140018961  lea     rax, aCryptEAsn1Eod; "CRYPT_E_ASN1_EOD"
0x140018968  cmp     ecx, 80093102h
0x14001896e  jmp     loc_140018B5A
0x140018973  lea     rax, aCryptEAsn1Inte; "CRYPT_E_ASN1_INTERNAL"
0x14001897a  retn
0x14001897b  lea     rax, aCryptEAsn1Erro; "CRYPT_E_ASN1_ERROR"
0x140018982  retn
0x140018983  lea     rax, aCryptEOssError; "CRYPT_E_OSS_ERROR"
0x14001898a  retn
0x14001898b  lea     rax, aCryptEMissingP; "CRYPT_E_MISSING_PUBKEY_PARA"
0x140018992  retn
0x140018993  lea     rax, aCryptEAsn1Corr; "CRYPT_E_ASN1_CORRUPT"
0x14001899a  retn
0x14001899b  mov     eax, 80093133h
0x1400189a0  cmp     ecx, eax
0x1400189a2  jg      def_14001868B; jumptable 000000014001868B default case
0x1400189a8  jz      short loc_140018A23
0x1400189aa  add     ecx, 7FF6CEFCh; switch 11 cases
0x1400189b0  cmp     ecx, 0Ah
0x1400189b3  ja      short def_14001868B; jumptable 000000014001868B default case
0x1400189b5  movsxd  rax, ecx
0x1400189b8  lea     rcx, cs:140000000h
0x1400189bf  mov     eax, ds:(jpt_1400189C9 - 140000000h)[rcx+rax*4]
0x1400189c6  add     rax, rcx
0x1400189c9  jmp     rax; switch jump
0x1400189cb  lea     rax, aCryptEAsn1Larg; jumptable 00000001400189C9 case -2146881276
0x1400189d2  retn
0x1400189d3  lea     rax, aCryptEAsn1Cons; jumptable 00000001400189C9 case -2146881275
0x1400189da  retn
0x1400189db  lea     rax, aCryptEAsn1Memo; jumptable 00000001400189C9 case -2146881274
0x1400189e2  retn
0x1400189e3  lea     rax, aCryptEAsn1Over; jumptable 00000001400189C9 case -2146881273
0x1400189ea  retn
0x1400189eb  lea     rax, aCryptEAsn1Badp; jumptable 00000001400189C9 case -2146881272
0x1400189f2  retn
0x1400189f3  lea     rax, aCryptEAsn1Bada; jumptable 00000001400189C9 case -2146881271
0x1400189fa  retn
0x1400189fb  lea     rax, aCryptEAsn1Badr; jumptable 00000001400189C9 case -2146881270
0x140018a02  retn
0x140018a03  lea     rax, aCryptEAsn1Badt; jumptable 00000001400189C9 case -2146881269
0x140018a0a  retn
0x140018a0b  lea     rax, aCryptEAsn1Choi; jumptable 00000001400189C9 case -2146881268
0x140018a12  retn
0x140018a13  lea     rax, aCryptEAsn1Rule; jumptable 00000001400189C9 case -2146881267
0x140018a1a  retn
0x140018a1b  lea     rax, aCryptEAsn1Utf8; jumptable 00000001400189C9 case -2146881266
0x140018a22  retn
0x140018a23  lea     rax, aCryptEAsn1PduT; "CRYPT_E_ASN1_PDU_TYPE"
0x140018a2a  retn
0x140018a2b  lea     rax, Str2; jumptable 000000014001868B default case
0x140018a32  retn
0x140018a33  lea     rax, aCryptEAsn1Nyi; "CRYPT_E_ASN1_NYI"
0x140018a3a  retn
0x140018a3b  mov     eax, 800B010Ah
0x140018a40  cmp     ecx, eax
  ... truncated ...
```
