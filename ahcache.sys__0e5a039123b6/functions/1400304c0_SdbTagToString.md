# SdbTagToString

- ea: `0x1400304c0`
- end: `0x140031374`
- name: `SdbTagToString`
- size: `3764`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140059bc0`

## callees

- `0x1400304c0`

## string_xrefs

- `0x140030f5c`: `LINKER_VERSION`
- `0x140030f65`: `LINK_DATE`
- `0x140030f6e`: `UPTO_LINK_DATE`
- `0x140030ffe`: `FROM_LINK_DATE`
- `0x140030ab6`: `COMPANY_NAME`
- `0x140030b07`: `LEGAL_COPYRIGHT`

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
0x1400304c0  movzx   edx, cx
0x1400304c3  mov     eax, edx
0x1400304c5  and     eax, 0F000h
0x1400304ca  cmp     eax, 1000h
0x1400304cf  jz      loc_140031235
0x1400304d5  cmp     eax, 3000h
0x1400304da  jz      loc_1400311C9
0x1400304e0  cmp     eax, 4000h
0x1400304e5  jz      loc_140030E2D
0x1400304eb  cmp     eax, 5000h
0x1400304f0  jz      loc_140030CE4
0x1400304f6  cmp     eax, 6000h
0x1400304fb  jz      loc_140030A4E
0x140030501  cmp     eax, 7000h
0x140030506  jz      loc_140030639
0x14003050c  cmp     eax, 8000h
0x140030511  jz      loc_14003061B
0x140030517  cmp     eax, 9000h
0x14003051c  jnz     def_140030558; jumptable 0000000140030558 default case
0x140030522  mov     eax, 9801h
0x140030527  cmp     edx, eax
0x140030529  ja      def_140030558; jumptable 0000000140030558 default case
0x14003052f  jz      loc_140030612
0x140030535  add     edx, 0FFFF6FFEh; switch 20 cases
0x14003053b  cmp     edx, 13h
0x14003053e  ja      def_140030558; jumptable 0000000140030558 default case
0x140030544  lea     rcx, cs:140000000h
0x14003054b  movsxd  rax, edx
0x14003054e  mov     eax, ds:(jpt_140030558 - 140000000h)[rcx+rax*4]
0x140030555  add     rax, rcx
0x140030558  jmp     rax; switch jump
0x14003055e  lea     rax, a0x9002; jumptable 0000000140030558 case 36866
0x140030565  retn
0x140030567  lea     rax, a0x9003; jumptable 0000000140030558 case 36867
0x14003056e  retn
0x140030570  lea     rax, a0x9004; jumptable 0000000140030558 case 36868
0x140030577  retn
0x140030579  lea     rax, a0x9005; jumptable 0000000140030558 case 36869
0x140030580  retn
0x140030582  lea     rax, a0x9006; jumptable 0000000140030558 case 36870
0x140030589  retn
0x14003058b  lea     rax, a0x9007; jumptable 0000000140030558 case 36871
0x140030592  retn
0x140030594  lea     rax, a0x9008; jumptable 0000000140030558 case 36872
0x14003059b  retn
0x14003059d  lea     rax, a0x9009; jumptable 0000000140030558 case 36873
0x1400305a4  retn
0x1400305a6  lea     rax, a0x900a; jumptable 0000000140030558 case 36874
0x1400305ad  retn
0x1400305af  lea     rax, a0x900b; jumptable 0000000140030558 case 36875
0x1400305b6  retn
0x1400305b8  lea     rax, a0x900c; jumptable 0000000140030558 case 36876
0x1400305bf  retn
0x1400305c1  lea     rax, a0x900d; jumptable 0000000140030558 case 36877
0x1400305c8  retn
0x1400305ca  lea     rax, a0x900e; jumptable 0000000140030558 case 36878
0x1400305d1  retn
0x1400305d3  lea     rax, a0x900f; jumptable 0000000140030558 case 36879
0x1400305da  retn
0x1400305dc  lea     rax, a0x9010; jumptable 0000000140030558 case 36880
0x1400305e3  retn
0x1400305e5  lea     rax, a0x9011; jumptable 0000000140030558 case 36881
0x1400305ec  retn
0x1400305ee  lea     rax, a0x9012; jumptable 0000000140030558 case 36882
0x1400305f5  retn
0x1400305f7  lea     rax, a0x9013; jumptable 0000000140030558 case 36883
0x1400305fe  retn
0x140030600  lea     rax, a0x9014; jumptable 0000000140030558 case 36884
0x140030607  retn
0x140030609  lea     rax, a0x9015; jumptable 0000000140030558 case 36885
0x140030610  retn
0x140030612  lea     rax, a0x9801; "0x9801"
0x140030619  retn
0x14003061b  mov     r8d, 8801h
0x140030621  lea     rdx, a0x8801; "0x8801"
0x140030628  cmp     cx, r8w
0x14003062c  lea     rax, aInvalidtag; "InvalidTag"
0x140030633  cmovz   rax, rdx
0x140030637  retn
0x140030639  mov     eax, 7801h
0x14003063e  cmp     edx, eax
0x140030640  ja      loc_140030A1D
0x140030646  jz      loc_140030A14
0x14003064c  add     edx, 0FFFF8FFFh; switch 105 cases
0x140030652  cmp     edx, 68h
0x140030655  ja      def_140030558; jumptable 0000000140030558 default case
0x14003065b  lea     rcx, cs:140000000h
0x140030662  movsxd  rax, edx
0x140030665  mov     eax, ds:(jpt_14003066F - 140000000h)[rcx+rax*4]
0x14003066c  add     rax, rcx
0x14003066f  jmp     rax; switch jump
0x140030675  lea     rax, a0x7001; jumptable 000000014003066F case 28673
0x14003067c  retn
0x14003067e  lea     rax, a0x7002; jumptable 000000014003066F case 28674
0x140030685  retn
0x140030687  lea     rax, a0x7003; jumptable 000000014003066F case 28675
0x14003068e  retn
0x140030690  lea     rax, a0x7004; jumptable 000000014003066F case 28676
0x140030697  retn
0x140030699  lea     rax, a0x7005; jumptable 000000014003066F case 28677
0x1400306a0  retn
0x1400306a2  lea     rax, a0x7006; jumptable 000000014003066F case 28678
0x1400306a9  retn
0x1400306ab  lea     rax, a0x7007; jumptable 000000014003066F case 28679
0x1400306b2  retn
0x1400306b4  lea     rax, a0x7008; jumptable 000000014003066F case 28680
0x1400306bb  retn
0x1400306bd  lea     rax, a0x7009; jumptable 000000014003066F case 28681
0x1400306c4  retn
0x1400306c6  lea     rax, a0x700a; jumptable 000000014003066F case 28682
0x1400306cd  retn
0x1400306cf  lea     rax, a0x700b; jumptable 000000014003066F case 28683
0x1400306d6  retn
0x1400306d8  lea     rax, a0x700c; jumptable 000000014003066F case 28684
0x1400306df  retn
0x1400306e1  lea     rax, a0x700d; jumptable 000000014003066F case 28685
0x1400306e8  retn
0x1400306ea  lea     rax, a0x700e; jumptable 000000014003066F case 28686
0x1400306f1  retn
0x1400306f3  lea     rax, a0x700f; jumptable 000000014003066F case 28687
0x1400306fa  retn
0x1400306fc  lea     rax, a0x7010; jumptable 000000014003066F case 28688
0x140030703  retn
0x140030705  lea     rax, a0x7011; jumptable 000000014003066F case 28689
0x14003070c  retn
0x14003070e  lea     rax, a0x7012; jumptable 000000014003066F case 28690
0x140030715  retn
0x140030717  lea     rax, a0x7013; jumptable 000000014003066F case 28691
0x14003071e  retn
0x140030720  lea     rax, a0x7014; jumptable 000000014003066F case 28692
0x140030727  retn
0x140030729  lea     rax, a0x7015; jumptable 000000014003066F case 28693
0x140030730  retn
0x140030732  lea     rax, a0x7016; jumptable 000000014003066F case 28694
0x140030739  retn
0x14003073b  lea     rax, a0x7017; jumptable 000000014003066F case 28695
0x140030742  retn
0x140030744  lea     rax, a0x7018; jumptable 000000014003066F case 28696
0x14003074b  retn
0x14003074d  lea     rax, a0x7019; jumptable 000000014003066F case 28697
0x140030754  retn
0x140030756  lea     rax, a0x701a; jumptable 000000014003066F case 28698
0x14003075d  retn
0x14003075f  lea     rax, a0x701c; jumptable 000000014003066F case 28700
0x140030766  retn
0x140030768  lea     rax, a0x701e; jumptable 000000014003066F case 28702
0x14003076f  retn
0x140030771  lea     rax, a0x701f; jumptable 000000014003066F case 28703
0x140030778  retn
0x14003077a  lea     rax, a0x7020; jumptable 000000014003066F case 28704
0x140030781  retn
0x140030783  lea     rax, a0x7021; jumptable 000000014003066F case 28705
0x14003078a  retn
0x14003078c  lea     rax, a0x7022; jumptable 000000014003066F case 28706
0x140030793  retn
0x140030795  lea     rax, a0x7023; jumptable 000000014003066F case 28707
0x14003079c  retn
0x14003079e  lea     rax, a0x7024; jumptable 000000014003066F case 28708
0x1400307a5  retn
0x1400307a7  lea     rax, a0x7025; jumptable 000000014003066F case 28709
0x1400307ae  retn
0x1400307b0  lea     rax, a0x7026; jumptable 000000014003066F case 28710
0x1400307b7  retn
0x1400307b9  lea     rax, a0x7027; jumptable 000000014003066F case 28711
0x1400307c0  retn
0x1400307c2  lea     rax, a0x7028; jumptable 000000014003066F case 28712
0x1400307c9  retn
0x1400307cb  lea     rax, a0x7029; jumptable 000000014003066F case 28713
0x1400307d2  retn
0x1400307d4  lea     rax, a0x702a; jumptable 000000014003066F case 28714
0x1400307db  retn
0x1400307dd  lea     rax, a0x702b; jumptable 000000014003066F case 28715
0x1400307e4  retn
0x1400307e6  lea     rax, a0x702c; jumptable 000000014003066F case 28716
0x1400307ed  retn
0x1400307ef  lea     rax, a0x702d; jumptable 000000014003066F case 28717
0x1400307f6  retn
0x1400307f8  lea     rax, a0x702e; jumptable 000000014003066F case 28718
0x1400307ff  retn
0x140030801  lea     rax, a0x702f; jumptable 000000014003066F case 28719
0x140030808  retn
0x14003080a  lea     rax, a0x7030; jumptable 000000014003066F case 28720
0x140030811  retn
0x140030813  lea     rax, a0x7031; jumptable 000000014003066F case 28721
0x14003081a  retn
0x14003081c  lea     rax, a0x7032; jumptable 000000014003066F case 28722
0x140030823  retn
0x140030825  lea     rax, a0x7033; jumptable 000000014003066F case 28723
0x14003082c  retn
0x14003082e  lea     rax, a0x7034; jumptable 000000014003066F case 28724
0x140030835  retn
0x140030837  lea     rax, a0x7035; jumptable 000000014003066F case 28725
0x14003083e  retn
0x140030840  lea     rax, a0x7036; jumptable 000000014003066F case 28726
0x140030847  retn
0x140030849  lea     rax, a0x7037; jumptable 000000014003066F case 28727
0x140030850  retn
0x140030852  lea     rax, a0x7038; jumptable 000000014003066F case 28728
0x140030859  retn
0x14003085b  lea     rax, a0x7039; jumptable 000000014003066F case 28729
0x140030862  retn
0x140030864  lea     rax, a0x703a; jumptable 000000014003066F case 28730
0x14003086b  retn
0x14003086d  lea     rax, a0x703b; jumptable 000000014003066F case 28731
0x140030874  retn
0x140030876  lea     rax, a0x703c; jumptable 000000014003066F case 28732
0x14003087d  retn
0x14003087f  lea     rax, a0x703d; jumptable 000000014003066F case 28733
0x140030886  retn
0x140030888  lea     rax, a0x703e; jumptable 000000014003066F case 28734
0x14003088f  retn
0x140030891  lea     rax, a0x703f; jumptable 000000014003066F case 28735
0x140030898  retn
0x14003089a  lea     rax, a0x7040; jumptable 000000014003066F case 28736
0x1400308a1  retn
0x1400308a3  lea     rax, a0x7041; jumptable 000000014003066F case 28737
0x1400308aa  retn
0x1400308ac  lea     rax, a0x7042; jumptable 000000014003066F case 28738
0x1400308b3  retn
0x1400308b5  lea     rax, a0x7043; jumptable 000000014003066F case 28739
0x1400308bc  retn
0x1400308be  lea     rax, a0x7044; jumptable 000000014003066F case 28740
0x1400308c5  retn
0x1400308c7  lea     rax, a0x7045; jumptable 000000014003066F case 28741
0x1400308ce  retn
0x1400308d0  lea     rax, a0x7046; jumptable 000000014003066F case 28742
0x1400308d7  retn
0x1400308d9  lea     rax, a0x7047; jumptable 000000014003066F case 28743
0x1400308e0  retn
0x1400308e2  lea     rax, a0x7048; jumptable 000000014003066F case 28744
0x1400308e9  retn
0x1400308eb  lea     rax, a0x7049; jumptable 000000014003066F case 28745
0x1400308f2  retn
0x1400308f4  lea     rax, a0x704a; jumptable 000000014003066F case 28746
0x1400308fb  retn
0x1400308fd  lea     rax, a0x704b; jumptable 000000014003066F case 28747
0x140030904  retn
0x140030906  lea     rax, a0x704c; jumptable 000000014003066F case 28748
0x14003090d  retn
0x14003090f  lea     rax, a0x704d; jumptable 000000014003066F case 28749
0x140030916  retn
0x140030918  lea     rax, a0x704e; jumptable 000000014003066F case 28750
0x14003091f  retn
0x140030921  lea     rax, a0x704f; jumptable 000000014003066F case 28751
0x140030928  retn
0x14003092a  lea     rax, a0x7050; jumptable 000000014003066F case 28752
0x140030931  retn
0x140030933  lea     rax, a0x7051; jumptable 000000014003066F case 28753
0x14003093a  retn
0x14003093c  lea     rax, a0x7052; jumptable 000000014003066F case 28754
0x140030943  retn
0x140030945  lea     rax, a0x7053; jumptable 000000014003066F case 28755
0x14003094c  retn
0x14003094e  lea     rax, a0x7054; jumptable 000000014003066F case 28756
0x140030955  retn
0x140030957  lea     rax, a0x7055; jumptable 000000014003066F case 28757
0x14003095e  retn
0x140030960  lea     rax, a0x7056; jumptable 000000014003066F case 28758
0x140030967  retn
0x140030969  lea     rax, a0x7057; jumptable 000000014003066F case 28759
0x140030970  retn
0x140030972  lea     rax, a0x7058; jumptable 000000014003066F case 28760
0x140030979  retn
0x14003097b  lea     rax, a0x7059; jumptable 000000014003066F case 28761
0x140030982  retn
0x140030984  lea     rax, a0x705a; jumptable 000000014003066F case 28762
0x14003098b  retn
0x14003098d  lea     rax, a0x705b; jumptable 000000014003066F case 28763
0x140030994  retn
0x140030996  lea     rax, a0x705c; jumptable 000000014003066F case 28764
0x14003099d  retn
0x14003099f  lea     rax, a0x705d; jumptable 000000014003066F case 28765
0x1400309a6  retn
0x1400309a8  lea     rax, a0x705e; jumptable 000000014003066F case 28766
0x1400309af  retn
0x1400309b1  lea     rax, a0x705f; jumptable 000000014003066F case 28767
0x1400309b8  retn
0x1400309ba  lea     rax, a0x7060; jumptable 000000014003066F case 28768
0x1400309c1  retn
0x1400309c3  lea     rax, a0x7061; jumptable 000000014003066F case 28769
0x1400309ca  retn
0x1400309cc  lea     rax, a0x7062; jumptable 000000014003066F case 28770
0x1400309d3  retn
0x1400309d5  lea     rax, a0x7063; jumptable 000000014003066F case 28771
0x1400309dc  retn
0x1400309de  lea     rax, a0x7064; jumptable 000000014003066F case 28772
0x1400309e5  retn
0x1400309e7  lea     rax, a0x7065; jumptable 000000014003066F case 28773
0x1400309ee  retn
0x1400309f0  lea     rax, a0x7066; jumptable 000000014003066F case 28774
0x1400309f7  retn
0x1400309f9  lea     rax, a0x7067; jumptable 000000014003066F case 28775
0x140030a00  retn
0x140030a02  lea     rax, a0x7068; jumptable 000000014003066F case 28776
0x140030a09  retn
0x140030a0b  lea     rax, a0x7069; jumptable 000000014003066F case 28777
0x140030a12  retn
0x140030a14  lea     rax, a0x7801; "0x7801"
0x140030a1b  retn
0x140030a1d  sub     edx, 7802h
  ... truncated ...
```
