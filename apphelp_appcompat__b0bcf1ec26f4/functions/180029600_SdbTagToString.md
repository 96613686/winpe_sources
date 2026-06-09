# SdbTagToString

- ea: `0x180029600`
- end: `0x18002a331`
- name: `SdbTagToString`
- size: `3377`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009130`
- `0x180029220`
- `0x1800377ac`
- `0x180041adc`
- `0x1800426fc`
- `0x180042b6c`
- `0x180042ee4`

## callees

- `0x180029600`

## string_xrefs

- `0x180029b62`: `COMPANY_NAME`
- `0x180029baa`: `LEGAL_COPYRIGHT`
- `0x180029f87`: `LINKER_VERSION`
- `0x180029f8f`: `LINK_DATE`
- `0x180029f97`: `UPTO_LINK_DATE`
- `0x18002a017`: `FROM_LINK_DATE`

## pseudocode

```c
const wchar_t *__fastcall SdbTagToString(unsigned __int16 a1)
{
  int v1; // eax
  const wchar_t *result; // rax

  v1 = a1 & 0xF000;
  switch ( v1 )
  {
    case 0x1000:
      switch ( a1 )
      {
        case 0x1001u:
          result = L"0x1001";
          break;
        case 0x1002u:
          result = L"0x1002";
          break;
        case 0x1003u:
          result = L"0x1003";
          break;
        case 0x1004u:
          result = L"0x1004";
          break;
        case 0x1005u:
          result = L"0x1005";
          break;
        case 0x1006u:
          result = L"0x1006";
          break;
        case 0x1007u:
          result = L"0x1007";
          break;
        case 0x1008u:
          result = L"0x1008";
          break;
        case 0x1009u:
          result = L"0x1009";
          break;
        case 0x100Au:
          result = L"0x100A";
          break;
        case 0x100Bu:
          result = L"0x100B";
          break;
        case 0x100Cu:
          result = L"0x100C";
          break;
        case 0x100Du:
          result = L"0x100D";
          break;
        case 0x100Eu:
          result = L"0x100E";
          break;
        case 0x100Fu:
          result = L"0x100F";
          break;
        case 0x1010u:
          result = L"0x1010";
          break;
        case 0x1011u:
          result = L"0x1011";
          break;
        case 0x1012u:
          result = L"0x1012";
          break;
        case 0x1013u:
          result = L"0x1013";
          break;
        case 0x1014u:
          result = L"0x1014";
          break;
        case 0x1015u:
          result = L"0x1015";
          break;
        case 0x1016u:
          result = L"0x1016";
          break;
        case 0x1017u:
          result = L"0x1017";
          break;
        case 0x1018u:
          result = L"0x1018";
          break;
        case 0x1019u:
          result = L"0x1019";
          break;
        case 0x101Au:
          result = L"0x101A";
          break;
        case 0x101Bu:
          result = L"0x101B";
          break;
        case 0x101Cu:
          result = L"0x101C";
          break;
        case 0x101Du:
          result = L"0x101D";
          break;
        case 0x101Eu:
          result = L"0x101E";
          break;
        default:
          return L"InvalidTag";
      }
      break;
    case 0x3000:
      switch ( a1 )
      {
        case 0x3001u:
          return L"0x3001";
        case 0x3002u:
          return L"0x3002";
        case 0x3003u:
          return L"0x3003";
        case 0x3004u:
          return L"0x3004";
        case 0x3801u:
          return L"0x3801";
        case 0x3802u:
          return L"0x3802";
        case 0x3803u:
          return L"0x3803";
      }
      return L"InvalidTag";
    case 0x4000:
      if ( a1 > 0x4801u )
        return L"InvalidTag";
      if ( a1 == 18433 )
      {
        return L"0x4801";
      }
      else
      {
        switch ( a1 )
        {
          case 0x4001u:
            result = L"SIZE";
            break;
          case 0x4002u:
            result = L"0x4002";
            break;
          case 0x4003u:
            result = L"CHECKSUM";
            break;
          case 0x4004u:
            result = L"0x4004";
            break;
          case 0x4005u:
            result = L"0x4005";
            break;
          case 0x4006u:
            result = L"MODULE_TYPE";
            break;
          case 0x4007u:
            result = L"VERDATEHI";
            break;
          case 0x4008u:
            result = L"VERDATELO";
            break;
          case 0x4009u:
            result = L"VERFILEOS";
            break;
          case 0x400Au:
            result = L"VERFILETYPE";
            break;
          case 0x400Bu:
            result = L"0x400B";
            break;
          case 0x400Cu:
            result = L"0x400C";
            break;
          case 0x400Du:
            result = L"0x400D";
            break;
          case 0x400Eu:
            result = L"0x400E";
            break;
          case 0x400Fu:
            result = L"0x400F";
            break;
          case 0x4010u:
            result = L"0x4010";
            break;
          case 0x4011u:
            result = L"0x4011";
            break;
          case 0x4012u:
            result = L"VER_LANGUAGE";
            break;
          case 0x4013u:
            result = L"0x4013";
            break;
          case 0x4014u:
            result = L"0x4014";
            break;
          case 0x4015u:
            result = L"0x4015";
            break;
          case 0x4016u:
            result = L"0x4016";
            break;
          case 0x4017u:
            result = L"0x4017";
            break;
          case 0x4018u:
            result = L"0x4018";
            break;
          case 0x4019u:
            result = L"0x4019";
            break;
          case 0x401Au:
            result = L"0x401A";
            break;
          case 0x401Bu:
            result = L"0x401B";
            break;
          case 0x401Cu:
            result = L"LINKER_VERSION";
            break;
          case 0x401Du:
            result = L"LINK_DATE";
            break;
          case 0x401Eu:
            result = L"UPTO_LINK_DATE";
            break;
          case 0x4020u:
            result = L"0x4020";
            break;
          case 0x4021u:
            result = L"0x4021";
            break;
          case 0x4023u:
            result = L"0x4023";
            break;
          case 0x4024u:
            result = L"0x4024";
            break;
          case 0x4025u:
            result = L"0x4025";
            break;
          case 0x4026u:
            result = L"0x4026";
            break;
          case 0x4027u:
            result = L"0x4027";
            break;
          case 0x4028u:
            result = L"0x4028";
            break;
          case 0x4029u:
            result = L"0x4029";
            break;
          case 0x402Au:
            result = L"0x402A";
            break;
          case 0x402Bu:
            result = L"0x402B";
            break;
          case 0x402Cu:
            result = L"0x402C";
            break;
          case 0x4030u:
            result = L"0x4030";
            break;
          case 0x4031u:
            result = L"EXE_WRAPPER";
            break;
          case 0x4032u:
            result = L"0x4032";
            break;
          case 0x4033u:
            result = L"FROM_LINK_DATE";
            break;
          case 0x4034u:
            result = L"0x4034";
            break;
          case 0x4035u:
            result = L"0x4035";
            break;
          case 0x4036u:
            result = L"0x4036";
            break;
          case 0x4037u:
            result = L"0x4037";
            break;
          case 0x4038u:
            result = L"0x4038";
            break;
          case 0x4039u:
            result = L"0x4039";
            break;
          case 0x403Au:
            result = L"0x403A";
            break;
          case 0x403Bu:
            result = L"0x403B";
            break;
          case 0x403Cu:
            result = L"0x403C";
            break;
          case 0x403Du:
            result = L"0x403D";
            break;
          case 0x403Eu:
            result = L"0x403E";
            break;
          case 0x403Fu:
            result = L"0x403F";
            break;
          case 0x4040u:
            result = L"0x4040";
            break;
          case 0x4041u:
            result = L"0x4041";
            break;
          case 0x4042u:
            result = L"0x4042";
            break;
          case 0x4043u:
            result = L"SIZE_OF_IMAGE";
            break;
          case 0x4044u:
            result = L"0x4044";
            break;
          case 0x4045u:
            result = L"0x4045";
            break;
          case 0x4046u:
            result = L"0x4046";
            break;
          case 0x4047u:
            result = L"0x4047";
            break;
          case 0x4048u:
            result = L"0x4048";
            break;
          case 0x4049u:
            result = L"0x4049";
            break;
          case 0x404Au:
            result = L"CRC_CHECKSUM";
            break;
          case 0x404Bu:
            result = L"0x404B";
            break;
          case 0x404Cu:
            result = L"0x404C";
            break;
          case 0x404Du:
            result = L"0x404D";
            break;
          case 0x404Eu:
            result = L"0x404E";
            break;
          case 0x404Fu:
            result = L"0x404F";
            break;
          case 0x4050u:
            result = L"0x4050";
            break;
          case 0x4051u:
            result = L"0x4051";
            break;
          case 0x4052u:
            result = L"0x4052";
            break;
          case 0x4053u:
            result = L"0x4053";
            break;
          case 0x4054u:
            result = L"0x4054";
            break;
          case 0x4055u:
            result = L"0x4055";
            break;
          case 0x4056u:
            result = L"0x4056";
            break;
          case 0x4057u:
            result = L"0x4057";
            break;
          case 0x4059u:
            result = L"0x4059";
            break;
          case 0x405Au:
            result = L"0x405A";
            break;
          case 0x405Bu:
            result = L"0x405B";
            break;
          case 0x405Cu:
            result = L"0x405C";
            break;
          case 0x405Du:
            result = L"0x405D";
            break;
          case 0x405Eu:
            result = L"0x405E";
            break;
          case 0x405Fu:
            result = L"0x405F";
            break;
          case 0x4060u:
            result = L"0x4060";
            break;
          case 0x4061u:
            result = L"0x4061";
            break;
          case 0x4062u:
            result = L"0x4062";
            break;
          case 0x4063u:
            result = L"FILE_KIND_DETAIL";
            break;
          case 0x4064u:
            result = L"0x4064";
            break;
          case 0x4065u:
            result = L"0x4065";
            break;
          default:
            return L"InvalidTag";
        }
      }
      break;
    case 0x5000:
      switch ( a1 )
      {
        case 0x5001u:
          result = L"0x5001";
          break;
        case 0x5002u:
          result = L"BIN_FILE_VERSION";
          break;
        case 0x5003u:
          result = L"BIN_PRODUCT_VERSION";
          break;
        case 0x5004u:
          result = L"0x5004";
          break;
        case 0x5005u:
          result = L"0x5005";
          break;
        case 0x5006u:
          result = L"UPTO_BIN_PRODUCT_VERSION";
          break;
        case 0x5007u:
          result = L"0x5007";
          break;
        case 0x5008u:
          result = L"0x5008";
          break;
        case 0x5009u:
          result = L"0x5009";
          break;
        case 0x500Au:
          result = L"0x500A";
          break;
        case 0x500Bu:
          result = L"0x500B";
          break;
        case 0x500Cu:
          result = L"0x500C";
          break;
        case 0x500Du:
          result = L"UPTO_BIN_FILE_VERSION";
          break;
        case 0x500Eu:
          result = L"0x500E";
          break;
        case 0x500Fu:
          result = L"0x500F";
          break;
        case 0x5010u:
          result = L"0x5010";
          break;
        case 0x5011u:
          result = L"0x5011";
          break;
        case 0x5012u:
          result = L"FROM_BIN_PRODUCT_VERSION";
          break;
        case 0x5013u:
          result = L"FROM_BIN_FILE_VERSION";
          break;
        case 0x5014u:
          result = L"PACKAGEID_VERSION";
          break;
        case 0x5015u:
          result = L"FROM_PACKAGEID_VERSION";
          break;
        case 0x5016u:
          result = L"UPTO_PACKAGEID_VERSION";
          break;
        case 0x5017u:
          result = L"OSMAXVERSIONTESTED";
          break;
        case 0x5018u:
          result = L"FROM_OSMAXVERSIONTESTED";
          break;
        case 0x5019u:
          result = L"UPTO_OSMAXVERSIONTESTED";
          break;
        case 0x501Au:
          result = L"0x501A";
          break;
        case 0x501Bu:
          result = L"0x501B";
          break;
        case 0x501Cu:
          result = L"0x501C";
          break;
        case 0x501Du:
          result = L"0x501D";
          break;
        case 0x501Eu:
          result = L"0x501E";
          break;
        case 0x501Fu:
          result = L"0x501F";
          break;
        case 0x5020u:
          result = L"FILESIZE";
          break;
        default:
          return L"InvalidTag";
      }
      break;
    case 0x6000:
      switch ( a1 )
      {
        case 0x6001u:
          result = L"0x6001";
          break;
        case 0x6002u:
          result = L"0x6002";
          break;
        case 0x6003u:
          result = L"0x6003";
          break;
        case 0x6004u:
          result = L"0x6004";
          break;
        case 0x6005u:
          result = L"0x6005";
          break;
        case 0x6006u:
          result = L"0x6006";
          break;
        case 0x6008u:
          result = L"0x6008";
          break;
        case 0x6009u:
          result = L"COMPANY_NAME";
          break;
        case 0x600Au:
          result = L"0x600A";
          break;
        case 0x600Bu:
          result = L"0x600B";
          break;
        case 0x6010u:
          result = L"PRODUCT_NAME";
          break;
        case 0x6011u:
          result = L"PRODUCT_VERSION";
          break;
        case 0x6012u:
          result = L"FILE_DESCRIPTION";
          break;
        case 0x6013u:
          result = L"FILE_VERSION";
          break;
        case 0x6014u:
          result = L"ORIGINAL_FILENAME";
          break;
        case 0x6015u:
          result = L"INTERNAL_NAME";
          break;
        case 0x6016u:
          result = L"LEGAL_COPYRIGHT";
          break;
        case 0x6017u:
          result = L"16BIT_DESCRIPTION";
          break;
        case 0x6018u:
          result = L"0x6018";
          break;
        case 0x6019u:
          result = L"0x6019";
          break;
        case 0x601Au:
          result = L"0x601A";
          break;
        case 0x601Bu:
          result = L"0x601B";
          break;
        case 0x601Cu:
          result = L"0x601C";
          break;
        case 0x601Du:
          result = L"0x601D";
          break;
        case 0x601Eu:
          result = L"0x601E";
          break;
        case 0x601Fu:
          result = L"0x601F";
          break;
        case 0x6020u:
          result = L"16BIT_MODULE_NAME";
          break;
        case 0x6021u:
          result = L"0x6021";
          break;
        case 0x6022u:
          result = L"0x6022";
          break;
        case 0x6023u:
          result = L"0x6023";
          break;
        case 0x6024u:
          result = L"EXPORT_NAME";
          break;
        case 0x6025u:
          result = L"0x6025";
          break;
        case 0x6026u:
          result = L"0x6026";
          break;
        case 0x6027u:
          result = L"0x6027";
          break;
        case 0x6028u:
          result = L"0x6028";
          break;
        case 0x6029u:
          result = L"0x6029";
          break;
        case 0x602Au:
          result = L"0x602A";
          break;
        case 0x602Bu:
          result = L"0x602B";
          break;
        case 0x602Cu:
          result = L"0x602C";
          break;
        case 0x602Du:
          result = L"0x602D";
          break;
        case 0x602Eu:
          result = L"0x602E";
          break;
        case 0x602Fu:
          result = L"0x602F";
          break;
        case 0x6030u:
          result = L"0x6030";
          break;
        case 0x6031u:
          result = L"0x6031";
          break;
        case 0x6032u:
          result = L"0x6032";
          break;
        case 0x6033u:
          result = L"0x6033";
          break;
        case 0x6034u:
          result = L"0x6034";
          break;
        case 0x6035u:
          result = L"0x6035";
          break;
        case 0x6036u:
          result = L"0x6036";
          break;
        case 0x6037u:
          result = L"0x6037";
          break;
        case 0x6038u:
          result = L"0x6038";
          break;
        case 0x6039u:
          result = L"0x6039";
          break;
        case 0x603Au:
          result = L"0x603A";
          break;
        case 0x603Bu:
          result = L"0x603B";
          break;
        case 0x603Cu:
          result = L"0x603C";
          break;
        case 0x603Du:
          result = L"0x603D";
          break;
        case 0x603Eu:
          result = L"0x603E";
          break;
        case 0x603Fu:
          result = L"0x603F";
          break;
        case 0x6040u:
          result = L"0x6040";
          break;
        case 0x6041u:
          result = L"0x6041";
          break;
        case 0x6042u:
          result = L"0x6042";
          break;
        case 0x6043u:
          result = L"0x6043";
          break;
        case 0x6044u:
          result = L"UPTO_PRODUCT_VERSION";
          break;
        case 0x6045u:
          result = L"UPTO_FILE_VERSION";
          break;
        case 0x6046u:
          result = L"FROM_PRODUCT_VERSION";
          break;
        case 0x6047u:
          result = L"FROM_FILE_VERSION";
          break;
        case 0x6048u:
          result = L"0x6048";
          break;
        case 0x6049u:
          result = L"0x6049";
          break;
        case 0x6050u:
          result = L"0x6050";
          break;
        default:
          return L"InvalidTag";
      }
      break;
    case 0x7000:
      if ( a1 > 0x7801u )
      {
        switch ( a1 )
        {
          case 0x7802u:
            return L"0x7802";
          case 0x7803u:
            return L"0x7803";
          case 0x7804u:
            return L"0x7804";
        }
        return L"InvalidTag";
      }
      if ( a1 == 30721 )
      {
        return L"0x7801";
      }
      else
      {
        switch ( a1 )
        {
          case 0x7001u:
            result = L"0x7001";
            break;
          case 0x7002u:
            result = L"0x7002";
            break;
          case 0x7003u:
            result = L"0x7003";
            break;
          case 0x7004u:
            result = L"0x7004";
            break;
          case 0x7005u:
            result = L"0x7005";
            break;
          case 0x7006u:
            result = L"0x7006";
            break;
          case 0x7007u:
            result = L"0x7007";
            break;
          case 0x7008u:
            result = L"0x7008";
            break;
          case 0x7009u:
            result = L"0x7009";
            break;
          case 0x700Au:
            result = L"0x700A";
            break;
          case 0x700Bu:
            result = L"0x700B";
            break;
          case 0x700Cu:
            result = L"0x700C";
            break;
          case 0x700Du:
            result = L"0x700D";
            break;
          case 0x700Eu:
            result = L"0x700E";
            break;
          case 0x700Fu:
            result = L"0x700F";
            break;
          case 0x7010u:
            result = L"0x7010";
            break;
          case 0x7011u:
            result = L"0x7011";
            break;
          case 0x7012u:
            result = L"0x7012";
            break;
          case 0x7013u:
            result = L"0x7013";
            break;
          case 0x7014u:
            result = L"0x7014";
            break;
          case 0x7015u:
            result = L"0x7015";
            break;
          case 0x7016u:
            result = L"0x7016";
            break;
          case 0x7017u:
            result = L"0x7017";
            break;
          case 0x7018u:
            result = L"0x7018";
            break;
          case 0x7019u:
            result = L"0x7019";
            break;
          case 0x701Au:
            result = L"0x701A";
            break;
          case 0x701Cu:
            result = L"0x701C";
            break;
          case 0x701Eu:
            result = L"0x701E";
            break;
          case 0x701Fu:
            result = L"0x701F";
            break;
          case 0x7020u:
            result = L"0x7020";
            break;
          case 0x7021u:
            result = L"0x7021";
            break;
          case 0x7022u:
            result = L"0x7022";
            break;
          case 0x7023u:
            result = L"0x7023";
            break;
          case 0x7024u:
            result = L"0x7024";
            break;
          case 0x7025u:
            result = L"0x7025";
            break;
          case 0x7026u:
            result = L"0x7026";
            break;
          case 0x7027u:
            result = L"0x7027";
            break;
          case 0x7028u:
            result = L"0x7028";
            break;
          case 0x7029u:
            result = L"0x7029";
            break;
          case 0x702Au:
            result = L"0x702A";
            break;
          case 0x702Bu:
            result = L"0x702B";
            break;
          case 0x702Cu:
            result = L"0x702C";
            break;
          case 0x702Du:
            result = L"0x702D";
            break;
          case 0x702Eu:
            result = L"0x702E";
            break;
          case 0x702Fu:
            result = L"0x702F";
            break;
          case 0x7030u:
            result = L"0x7030";
            break;
          case 0x7031u:
            result = L"0x7031";
            break;
          case 0x7032u:
            result = L"0x7032";
            break;
          case 0x7033u:
            result = L"0x7033";
            break;
          case 0x7034u:
            result = L"0x7034";
            break;
          case 0x7035u:
            result = L"0x7035";
            break;
          case 0x7036u:
            result = L"0x7036";
            break;
          case 0x7037u:
            result = L"0x7037";
            break;
          case 0x7038u:
            result = L"0x7038";
            break;
          case 0x7039u:
            result = L"0x7039";
            break;
          case 0x703Au:
            result = L"0x703A";
            break;
          case 0x703Bu:
            result = L"0x703B";
            break;
          case 0x703Cu:
            result = L"0x703C";
            break;
          case 0x703Du:
            result = L"0x703D";
            break;
          case 0x703Eu:
            result = L"0x703E";
            break;
          case 0x703Fu:
            result = L"0x703F";
            break;
          case 0x7040u:
            result = L"0x7040";
            break;
          case 0x7041u:
            result = L"0x7041";
            break;
          case 0x7042u:
            result = L"0x7042";
            break;
          case 0x7043u:
            result = L"0x7043";
            break;
          case 0x7044u:
            result = L"0x7044";
            break;
          case 0x7045u:
            result = L"0x7045";
            break;
          case 0x7046u:
            result = L"0x7046";
            break;
          case 0x7047u:
            result = L"0x7047";
            break;
          case 0x7048u:
            result = L"0x7048";
            break;
          case 0x7049u:
            result = L"0x7049";
            break;
          case 0x704Au:
            result = L"0x704A";
            break;
          case 0x704Bu:
            result = L"0x704B";
            break;
          case 0x704Cu:
            result = L"0x704C";
            break;
          case 0x704Du:
            result = L"0x704D";
            break;
          case 0x704Eu:
            result = L"0x704E";
            break;
          case 0x704Fu:
            result = L"0x704F";
            break;
          case 0x7050u:
            result = L"0x7050";
            break;
          case 0x7051u:
            result = L"0x7051";
            break;
          case 0x7052u:
            result = L"0x7052";
            break;
          case 0x7053u:
            result = L"0x7053";
            break;
          case 0x7054u:
            result = L"0x7054";
            break;
          case 0x7055u:
            result = L"0x7055";
            break;
          case 0x7056u:
            result = L"0x7056";
            break;
          case 0x7057u:
            result = L"0x7057";
            break;
          case 0x7058u:
            result = L"0x7058";
            break;
          case 0x7059u:
            result = L"0x7059";
            break;
          case 0x705Au:
            result = L"0x705A";
            break;
          case 0x705Bu:
            result = L"0x705B";
            break;
          case 0x705Cu:
            result = L"0x705C";
            break;
          case 0x705Du:
            result = L"0x705D";
            break;
          case 0x705Eu:
            result = L"0x705E";
            break;
          case 0x705Fu:
            result = L"0x705F";
            break;
          case 0x7060u:
            result = L"0x7060";
            break;
          case 0x7061u:
            result = L"0x7061";
            break;
          case 0x7062u:
            result = L"0x7062";
            break;
          case 0x7063u:
            result = L"0x7063";
            break;
          case 0x7064u:
            result = L"0x7064";
            break;
          case 0x7065u:
            result = L"0x7065";
            break;
          case 0x7066u:
            result = L"0x7066";
            break;
          case 0x7067u:
            result = L"0x7067";
            break;
          case 0x7068u:
            result = L"0x7068";
            break;
          case 0x7069u:
            result = L"0x7069";
            break;
          default:
            return L"InvalidTag";
        }
      }
      break;
    case 0x8000:
      result = L"InvalidTag";
      if ( a1 == 0x8801 )
        return L"0x8801";
      break;
    default:
      if ( v1 == 36864 && a1 <= 0x9801u )
      {
        if ( a1 == 38913 )
          return L"0x9801";
        switch ( a1 )
        {
          case 0x9002u:
            result = L"0x9002";
            break;
          case 0x9003u:
            result = L"0x9003";
            break;
          case 0x9004u:
            result = L"0x9004";
            break;
          case 0x9005u:
            result = L"0x9005";
            break;
          case 0x9006u:
            result = L"0x9006";
            break;
          case 0x9007u:
            result = L"0x9007";
            break;
          case 0x9008u:
            result = L"0x9008";
            break;
          case 0x9009u:
            result = L"0x9009";
            break;
          case 0x900Au:
            result = L"0x900A";
            break;
          case 0x900Bu:
            result = L"0x900B";
            break;
          case 0x900Cu:
            result = L"0x900C";
            break;
          case 0x900Du:
            result = L"0x900D";
            break;
          case 0x900Eu:
            result = L"0x900E";
            break;
          case 0x900Fu:
            result = L"0x900F";
            break;
          case 0x9010u:
            result = L"0x9010";
            break;
          case 0x9011u:
            result = L"0x9011";
            break;
          case 0x9012u:
            result = L"0x9012";
            break;
          case 0x9013u:
            result = L"0x9013";
            break;
          case 0x9014u:
            result = L"0x9014";
            break;
          case 0x9015u:
            result = L"0x9015";
            break;
          default:
            return L"InvalidTag";
        }
        return result;
      }
      return L"InvalidTag";
  }
  return result;
}

```

## disassembly

```asm
0x180029600  movzx   edx, cx
0x180029603  mov     eax, edx
0x180029605  and     eax, 0F000h
0x18002960a  cmp     eax, 1000h
0x18002960f  jz      loc_18002A214
0x180029615  cmp     eax, 3000h
0x18002961a  jz      loc_18002A1AF
0x180029620  cmp     eax, 4000h
0x180029625  jz      loc_180029E77
0x18002962b  cmp     eax, 5000h
0x180029630  jz      loc_180029D52
0x180029636  cmp     eax, 6000h
0x18002963b  jz      loc_180029B05
0x180029641  cmp     eax, 7000h
0x180029646  jz      loc_18002975F
0x18002964c  cmp     eax, 8000h
0x180029651  jz      loc_180029742
0x180029657  cmp     eax, 9000h
0x18002965c  jnz     def_180029698; jumptable 0000000180029698 default case
0x180029662  mov     eax, 9801h
0x180029667  cmp     edx, eax
0x180029669  ja      def_180029698; jumptable 0000000180029698 default case
0x18002966f  jz      loc_18002973A
0x180029675  add     edx, 0FFFF6FFEh; switch 20 cases
0x18002967b  cmp     edx, 13h
0x18002967e  ja      def_180029698; jumptable 0000000180029698 default case
0x180029684  lea     rcx, __ImageBase
0x18002968b  movsxd  rax, edx
0x18002968e  mov     eax, ds:(jpt_180029698 - 180000000h)[rcx+rax*4]
0x180029695  add     rax, rcx
0x180029698  jmp     rax; switch jump
0x18002969a  lea     rax, a0x9002; jumptable 0000000180029698 case 36866
0x1800296a1  retn
0x1800296a2  lea     rax, a0x9003; jumptable 0000000180029698 case 36867
0x1800296a9  retn
0x1800296aa  lea     rax, a0x9004; jumptable 0000000180029698 case 36868
0x1800296b1  retn
0x1800296b2  lea     rax, a0x9005; jumptable 0000000180029698 case 36869
0x1800296b9  retn
0x1800296ba  lea     rax, a0x9006; jumptable 0000000180029698 case 36870
0x1800296c1  retn
0x1800296c2  lea     rax, a0x9007; jumptable 0000000180029698 case 36871
0x1800296c9  retn
0x1800296ca  lea     rax, a0x9008; jumptable 0000000180029698 case 36872
0x1800296d1  retn
0x1800296d2  lea     rax, a0x9009; jumptable 0000000180029698 case 36873
0x1800296d9  retn
0x1800296da  lea     rax, a0x900a; jumptable 0000000180029698 case 36874
0x1800296e1  retn
0x1800296e2  lea     rax, a0x900b; jumptable 0000000180029698 case 36875
0x1800296e9  retn
0x1800296ea  lea     rax, a0x900c; jumptable 0000000180029698 case 36876
0x1800296f1  retn
0x1800296f2  lea     rax, a0x900d; jumptable 0000000180029698 case 36877
0x1800296f9  retn
0x1800296fa  lea     rax, a0x900e; jumptable 0000000180029698 case 36878
0x180029701  retn
0x180029702  lea     rax, a0x900f; jumptable 0000000180029698 case 36879
0x180029709  retn
0x18002970a  lea     rax, a0x9010; jumptable 0000000180029698 case 36880
0x180029711  retn
0x180029712  lea     rax, a0x9011; jumptable 0000000180029698 case 36881
0x180029719  retn
0x18002971a  lea     rax, a0x9012; jumptable 0000000180029698 case 36882
0x180029721  retn
0x180029722  lea     rax, a0x9013; jumptable 0000000180029698 case 36883
0x180029729  retn
0x18002972a  lea     rax, a0x9014; jumptable 0000000180029698 case 36884
0x180029731  retn
0x180029732  lea     rax, a0x9015; jumptable 0000000180029698 case 36885
0x180029739  retn
0x18002973a  lea     rax, a0x9801; "0x9801"
0x180029741  retn
0x180029742  mov     r8d, 8801h
0x180029748  lea     rdx, a0x8801; "0x8801"
0x18002974f  cmp     cx, r8w
0x180029753  lea     rax, aInvalidtag; "InvalidTag"
0x18002975a  cmovz   rax, rdx
0x18002975e  retn
0x18002975f  mov     eax, 7801h
0x180029764  cmp     edx, eax
0x180029766  ja      loc_180029AD7
0x18002976c  jz      loc_180029ACF
0x180029772  add     edx, 0FFFF8FFFh; switch 105 cases
0x180029778  cmp     edx, 68h
0x18002977b  ja      def_180029698; jumptable 0000000180029698 default case
0x180029781  lea     rcx, __ImageBase
0x180029788  movsxd  rax, edx
0x18002978b  mov     eax, ds:(jpt_180029795 - 180000000h)[rcx+rax*4]
0x180029792  add     rax, rcx
0x180029795  jmp     rax; switch jump
0x180029797  lea     rax, a0x7001; jumptable 0000000180029795 case 28673
0x18002979e  retn
0x18002979f  lea     rax, a0x7002; jumptable 0000000180029795 case 28674
0x1800297a6  retn
0x1800297a7  lea     rax, a0x7003; jumptable 0000000180029795 case 28675
0x1800297ae  retn
0x1800297af  lea     rax, a0x7004; jumptable 0000000180029795 case 28676
0x1800297b6  retn
0x1800297b7  lea     rax, a0x7005; jumptable 0000000180029795 case 28677
0x1800297be  retn
0x1800297bf  lea     rax, a0x7006; jumptable 0000000180029795 case 28678
0x1800297c6  retn
0x1800297c7  lea     rax, a0x7007; jumptable 0000000180029795 case 28679
0x1800297ce  retn
0x1800297cf  lea     rax, a0x7008; jumptable 0000000180029795 case 28680
0x1800297d6  retn
0x1800297d7  lea     rax, a0x7009; jumptable 0000000180029795 case 28681
0x1800297de  retn
0x1800297df  lea     rax, a0x700a; jumptable 0000000180029795 case 28682
0x1800297e6  retn
0x1800297e7  lea     rax, a0x700b; jumptable 0000000180029795 case 28683
0x1800297ee  retn
0x1800297ef  lea     rax, a0x700c; jumptable 0000000180029795 case 28684
0x1800297f6  retn
0x1800297f7  lea     rax, a0x700d; jumptable 0000000180029795 case 28685
0x1800297fe  retn
0x1800297ff  lea     rax, a0x700e; jumptable 0000000180029795 case 28686
0x180029806  retn
0x180029807  lea     rax, a0x700f; jumptable 0000000180029795 case 28687
0x18002980e  retn
0x18002980f  lea     rax, a0x7010; jumptable 0000000180029795 case 28688
0x180029816  retn
0x180029817  lea     rax, a0x7011; jumptable 0000000180029795 case 28689
0x18002981e  retn
0x18002981f  lea     rax, a0x7012; jumptable 0000000180029795 case 28690
0x180029826  retn
0x180029827  lea     rax, a0x7013; jumptable 0000000180029795 case 28691
0x18002982e  retn
0x18002982f  lea     rax, a0x7014; jumptable 0000000180029795 case 28692
0x180029836  retn
0x180029837  lea     rax, a0x7015; jumptable 0000000180029795 case 28693
0x18002983e  retn
0x18002983f  lea     rax, a0x7016; jumptable 0000000180029795 case 28694
0x180029846  retn
0x180029847  lea     rax, a0x7017; jumptable 0000000180029795 case 28695
0x18002984e  retn
0x18002984f  lea     rax, a0x7018; jumptable 0000000180029795 case 28696
0x180029856  retn
0x180029857  lea     rax, a0x7019; jumptable 0000000180029795 case 28697
0x18002985e  retn
0x18002985f  lea     rax, a0x701a; jumptable 0000000180029795 case 28698
0x180029866  retn
0x180029867  lea     rax, a0x701c; jumptable 0000000180029795 case 28700
0x18002986e  retn
0x18002986f  lea     rax, a0x701e; jumptable 0000000180029795 case 28702
0x180029876  retn
0x180029877  lea     rax, a0x701f; jumptable 0000000180029795 case 28703
0x18002987e  retn
0x18002987f  lea     rax, a0x7020; jumptable 0000000180029795 case 28704
0x180029886  retn
0x180029887  lea     rax, a0x7021; jumptable 0000000180029795 case 28705
0x18002988e  retn
0x18002988f  lea     rax, a0x7022; jumptable 0000000180029795 case 28706
0x180029896  retn
0x180029897  lea     rax, a0x7023; jumptable 0000000180029795 case 28707
0x18002989e  retn
0x18002989f  lea     rax, a0x7024; jumptable 0000000180029795 case 28708
0x1800298a6  retn
0x1800298a7  lea     rax, a0x7025; jumptable 0000000180029795 case 28709
0x1800298ae  retn
0x1800298af  lea     rax, a0x7026; jumptable 0000000180029795 case 28710
0x1800298b6  retn
0x1800298b7  lea     rax, a0x7027; jumptable 0000000180029795 case 28711
0x1800298be  retn
0x1800298bf  lea     rax, a0x7028; jumptable 0000000180029795 case 28712
0x1800298c6  retn
0x1800298c7  lea     rax, a0x7029; jumptable 0000000180029795 case 28713
0x1800298ce  retn
0x1800298cf  lea     rax, a0x702a; jumptable 0000000180029795 case 28714
0x1800298d6  retn
0x1800298d7  lea     rax, a0x702b; jumptable 0000000180029795 case 28715
0x1800298de  retn
0x1800298df  lea     rax, a0x702c; jumptable 0000000180029795 case 28716
0x1800298e6  retn
0x1800298e7  lea     rax, a0x702d; jumptable 0000000180029795 case 28717
0x1800298ee  retn
0x1800298ef  lea     rax, a0x702e; jumptable 0000000180029795 case 28718
0x1800298f6  retn
0x1800298f7  lea     rax, a0x702f; jumptable 0000000180029795 case 28719
0x1800298fe  retn
0x1800298ff  lea     rax, a0x7030; jumptable 0000000180029795 case 28720
0x180029906  retn
0x180029907  lea     rax, a0x7031; jumptable 0000000180029795 case 28721
0x18002990e  retn
0x18002990f  lea     rax, a0x7032; jumptable 0000000180029795 case 28722
0x180029916  retn
0x180029917  lea     rax, a0x7033; jumptable 0000000180029795 case 28723
0x18002991e  retn
0x18002991f  lea     rax, a0x7034; jumptable 0000000180029795 case 28724
0x180029926  retn
0x180029927  lea     rax, a0x7035; jumptable 0000000180029795 case 28725
0x18002992e  retn
0x18002992f  lea     rax, a0x7036; jumptable 0000000180029795 case 28726
0x180029936  retn
0x180029937  lea     rax, a0x7037; jumptable 0000000180029795 case 28727
0x18002993e  retn
0x18002993f  lea     rax, a0x7038; jumptable 0000000180029795 case 28728
0x180029946  retn
0x180029947  lea     rax, a0x7039; jumptable 0000000180029795 case 28729
0x18002994e  retn
0x18002994f  lea     rax, a0x703a; jumptable 0000000180029795 case 28730
0x180029956  retn
0x180029957  lea     rax, a0x703b; jumptable 0000000180029795 case 28731
0x18002995e  retn
0x18002995f  lea     rax, a0x703c; jumptable 0000000180029795 case 28732
0x180029966  retn
0x180029967  lea     rax, a0x703d; jumptable 0000000180029795 case 28733
0x18002996e  retn
0x18002996f  lea     rax, a0x703e; jumptable 0000000180029795 case 28734
0x180029976  retn
0x180029977  lea     rax, a0x703f; jumptable 0000000180029795 case 28735
0x18002997e  retn
0x18002997f  lea     rax, a0x7040; jumptable 0000000180029795 case 28736
0x180029986  retn
0x180029987  lea     rax, a0x7041; jumptable 0000000180029795 case 28737
0x18002998e  retn
0x18002998f  lea     rax, a0x7042; jumptable 0000000180029795 case 28738
0x180029996  retn
0x180029997  lea     rax, a0x7043; jumptable 0000000180029795 case 28739
0x18002999e  retn
0x18002999f  lea     rax, a0x7044; jumptable 0000000180029795 case 28740
0x1800299a6  retn
0x1800299a7  lea     rax, a0x7045; jumptable 0000000180029795 case 28741
0x1800299ae  retn
0x1800299af  lea     rax, a0x7046; jumptable 0000000180029795 case 28742
0x1800299b6  retn
0x1800299b7  lea     rax, a0x7047; jumptable 0000000180029795 case 28743
0x1800299be  retn
0x1800299bf  lea     rax, a0x7048; jumptable 0000000180029795 case 28744
0x1800299c6  retn
0x1800299c7  lea     rax, a0x7049; jumptable 0000000180029795 case 28745
0x1800299ce  retn
0x1800299cf  lea     rax, a0x704a; jumptable 0000000180029795 case 28746
0x1800299d6  retn
0x1800299d7  lea     rax, a0x704b; jumptable 0000000180029795 case 28747
0x1800299de  retn
0x1800299df  lea     rax, a0x704c; jumptable 0000000180029795 case 28748
0x1800299e6  retn
0x1800299e7  lea     rax, a0x704d; jumptable 0000000180029795 case 28749
0x1800299ee  retn
0x1800299ef  lea     rax, a0x704e; jumptable 0000000180029795 case 28750
0x1800299f6  retn
0x1800299f7  lea     rax, a0x704f; jumptable 0000000180029795 case 28751
0x1800299fe  retn
0x1800299ff  lea     rax, a0x7050; jumptable 0000000180029795 case 28752
0x180029a06  retn
0x180029a07  lea     rax, a0x7051; jumptable 0000000180029795 case 28753
0x180029a0e  retn
0x180029a0f  lea     rax, a0x7052; jumptable 0000000180029795 case 28754
0x180029a16  retn
0x180029a17  lea     rax, a0x7053; jumptable 0000000180029795 case 28755
0x180029a1e  retn
0x180029a1f  lea     rax, a0x7054; jumptable 0000000180029795 case 28756
0x180029a26  retn
0x180029a27  lea     rax, a0x7055; jumptable 0000000180029795 case 28757
0x180029a2e  retn
0x180029a2f  lea     rax, a0x7056; jumptable 0000000180029795 case 28758
0x180029a36  retn
0x180029a37  lea     rax, a0x7057; jumptable 0000000180029795 case 28759
0x180029a3e  retn
0x180029a3f  lea     rax, a0x7058; jumptable 0000000180029795 case 28760
0x180029a46  retn
0x180029a47  lea     rax, a0x7059; jumptable 0000000180029795 case 28761
0x180029a4e  retn
0x180029a4f  lea     rax, a0x705a; jumptable 0000000180029795 case 28762
0x180029a56  retn
0x180029a57  lea     rax, a0x705b; jumptable 0000000180029795 case 28763
0x180029a5e  retn
0x180029a5f  lea     rax, a0x705c; jumptable 0000000180029795 case 28764
0x180029a66  retn
0x180029a67  lea     rax, a0x705d; jumptable 0000000180029795 case 28765
0x180029a6e  retn
0x180029a6f  lea     rax, a0x705e; jumptable 0000000180029795 case 28766
0x180029a76  retn
0x180029a77  lea     rax, a0x705f; jumptable 0000000180029795 case 28767
0x180029a7e  retn
0x180029a7f  lea     rax, a0x7060; jumptable 0000000180029795 case 28768
0x180029a86  retn
0x180029a87  lea     rax, a0x7061; jumptable 0000000180029795 case 28769
0x180029a8e  retn
0x180029a8f  lea     rax, a0x7062; jumptable 0000000180029795 case 28770
0x180029a96  retn
0x180029a97  lea     rax, a0x7063; jumptable 0000000180029795 case 28771
0x180029a9e  retn
0x180029a9f  lea     rax, a0x7064; jumptable 0000000180029795 case 28772
0x180029aa6  retn
0x180029aa7  lea     rax, a0x7065; jumptable 0000000180029795 case 28773
0x180029aae  retn
0x180029aaf  lea     rax, a0x7066; jumptable 0000000180029795 case 28774
0x180029ab6  retn
0x180029ab7  lea     rax, a0x7067; jumptable 0000000180029795 case 28775
0x180029abe  retn
0x180029abf  lea     rax, a0x7068; jumptable 0000000180029795 case 28776
0x180029ac6  retn
0x180029ac7  lea     rax, a0x7069; jumptable 0000000180029795 case 28777
0x180029ace  retn
0x180029acf  lea     rax, a0x7801; "0x7801"
0x180029ad6  retn
0x180029ad7  sub     edx, 7802h
  ... truncated ...
```
