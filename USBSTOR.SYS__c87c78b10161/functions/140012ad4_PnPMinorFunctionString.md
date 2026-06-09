# PnPMinorFunctionString

- ea: `0x140012ad4`
- end: `0x140012c36`
- name: `PnPMinorFunctionString`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140023f70`

## callees

- `0x140012ad4`

## string_xrefs

- `0x140012b24`: `IRP_MN_QUERY_REMOVE_DEVICE`
- `0x140012b1b`: `IRP_MN_REMOVE_DEVICE`
- `0x140012b12`: `IRP_MN_CANCEL_REMOVE_DEVICE`
- `0x140012bc4`: `IRP_MN_READ_CONFIG`
- `0x140012bbb`: `IRP_MN_WRITE_CONFIG`

## pseudocode

```c
const char *__fastcall PnPMinorFunctionString(unsigned __int8 a1)
{
  if ( a1 <= 0xBu )
  {
    if ( a1 == 11 )
      return "IRP_MN_QUERY_RESOURCE_REQUIREMENTS";
    if ( a1 > 5u )
    {
      switch ( a1 )
      {
        case 6u:
          return "IRP_MN_CANCEL_STOP_DEVICE";
        case 7u:
          return "IRP_MN_QUERY_DEVICE_RELATIONS";
        case 8u:
          return "IRP_MN_QUERY_INTERFACE";
        case 9u:
          return "IRP_MN_QUERY_CAPABILITIES";
        case 0xAu:
          return "IRP_MN_QUERY_RESOURCES";
      }
    }
    else
    {
      switch ( a1 )
      {
        case 5u:
          return "IRP_MN_QUERY_STOP_DEVICE";
        case 0u:
          return "IRP_MN_START_DEVICE";
        case 1u:
          return "IRP_MN_QUERY_REMOVE_DEVICE";
        case 2u:
          return "IRP_MN_REMOVE_DEVICE";
        case 3u:
          return "IRP_MN_CANCEL_REMOVE_DEVICE";
        case 4u:
          return "IRP_MN_STOP_DEVICE";
      }
    }
    return "IRP_MN_?????";
  }
  if ( a1 <= 0x12u )
  {
    switch ( a1 )
    {
      case 0x12u:
        return "IRP_MN_SET_LOCK";
      case 0xCu:
        return "IRP_MN_QUERY_DEVICE_TEXT";
      case 0xDu:
        return "IRP_MN_FILTER_RESOURCE_REQUIREMENTS";
      case 0xFu:
        return "IRP_MN_READ_CONFIG";
      case 0x10u:
        return "IRP_MN_WRITE_CONFIG";
      case 0x11u:
        return "IRP_MN_EJECT";
    }
    return "IRP_MN_?????";
  }
  switch ( a1 )
  {
    case 0x13u:
      return "IRP_MN_QUERY_ID";
    case 0x14u:
      return "IRP_MN_QUERY_PNP_DEVICE_STATE";
    case 0x15u:
      return "IRP_MN_QUERY_BUS_INFORMATION";
    case 0x16u:
      return "IRP_MN_DEVICE_USAGE_NOTIFICATION";
  }
  if ( a1 != 23 )
    return "IRP_MN_?????";
  return "IRP_MN_SURPRISE_REMOVAL";
}

```

## disassembly

```asm
0x140012ad4  movzx   edx, cl
0x140012ad7  cmp     edx, 0Bh
0x140012ada  ja      loc_140012B92
0x140012ae0  jz      loc_140012B89
0x140012ae6  cmp     edx, 5
0x140012ae9  ja      short loc_140012B3F
0x140012aeb  jz      short loc_140012B36
0x140012aed  test    cl, cl
0x140012aef  jz      short loc_140012B2D
0x140012af1  sub     edx, 1
0x140012af4  jz      short loc_140012B24
0x140012af6  sub     edx, 1
0x140012af9  jz      short loc_140012B1B
0x140012afb  sub     edx, 1
0x140012afe  jz      short loc_140012B12
0x140012b00  cmp     edx, 1
0x140012b03  jnz     loc_140012C01
0x140012b09  lea     rax, aIrpMnStopDevic; "IRP_MN_STOP_DEVICE"
0x140012b10  retn
0x140012b12  lea     rax, aIrpMnCancelRem; "IRP_MN_CANCEL_REMOVE_DEVICE"
0x140012b19  retn
0x140012b1b  lea     rax, aIrpMnRemoveDev; "IRP_MN_REMOVE_DEVICE"
0x140012b22  retn
0x140012b24  lea     rax, aIrpMnQueryRemo; "IRP_MN_QUERY_REMOVE_DEVICE"
0x140012b2b  retn
0x140012b2d  lea     rax, aIrpMnStartDevi; "IRP_MN_START_DEVICE"
0x140012b34  retn
0x140012b36  lea     rax, aIrpMnQueryStop; "IRP_MN_QUERY_STOP_DEVICE"
0x140012b3d  retn
0x140012b3f  sub     edx, 6
0x140012b42  jz      short loc_140012B80
0x140012b44  sub     edx, 1
0x140012b47  jz      short loc_140012B77
0x140012b49  sub     edx, 1
0x140012b4c  jz      short loc_140012B6E
0x140012b4e  sub     edx, 1
0x140012b51  jz      short loc_140012B65
0x140012b53  cmp     edx, 1
0x140012b56  jnz     loc_140012C01
0x140012b5c  lea     rax, aIrpMnQueryReso; "IRP_MN_QUERY_RESOURCES"
0x140012b63  retn
0x140012b65  lea     rax, aIrpMnQueryCapa; "IRP_MN_QUERY_CAPABILITIES"
0x140012b6c  retn
0x140012b6e  lea     rax, aIrpMnQueryInte; "IRP_MN_QUERY_INTERFACE"
0x140012b75  retn
0x140012b77  lea     rax, aIrpMnQueryDevi; "IRP_MN_QUERY_DEVICE_RELATIONS"
0x140012b7e  retn
0x140012b80  lea     rax, aIrpMnCancelSto; "IRP_MN_CANCEL_STOP_DEVICE"
0x140012b87  retn
0x140012b89  lea     rax, aIrpMnQueryReso_0; "IRP_MN_QUERY_RESOURCE_REQUIREMENTS"
0x140012b90  retn
0x140012b92  cmp     edx, 12h
0x140012b95  ja      short loc_140012BE8
0x140012b97  jz      short loc_140012BDF
0x140012b99  sub     edx, 0Ch
0x140012b9c  jz      short loc_140012BD6
0x140012b9e  sub     edx, 1
0x140012ba1  jz      short loc_140012BCD
0x140012ba3  sub     edx, 2
0x140012ba6  jz      short loc_140012BC4
0x140012ba8  sub     edx, 1
0x140012bab  jz      short loc_140012BBB
0x140012bad  cmp     edx, 1
0x140012bb0  jnz     short loc_140012C01
0x140012bb2  lea     rax, aIrpMnEject; "IRP_MN_EJECT"
0x140012bb9  retn
0x140012bbb  lea     rax, aIrpMnWriteConf; "IRP_MN_WRITE_CONFIG"
0x140012bc2  retn
0x140012bc4  lea     rax, aIrpMnReadConfi; "IRP_MN_READ_CONFIG"
0x140012bcb  retn
0x140012bcd  lea     rax, aIrpMnFilterRes; "IRP_MN_FILTER_RESOURCE_REQUIREMENTS"
0x140012bd4  retn
0x140012bd6  lea     rax, aIrpMnQueryDevi_0; "IRP_MN_QUERY_DEVICE_TEXT"
0x140012bdd  retn
0x140012bdf  lea     rax, aIrpMnSetLock; "IRP_MN_SET_LOCK"
0x140012be6  retn
0x140012be8  sub     edx, 13h
0x140012beb  jz      short loc_140012C2E
0x140012bed  sub     edx, 1
0x140012bf0  jz      short loc_140012C25
0x140012bf2  sub     edx, 1
0x140012bf5  jz      short loc_140012C1C
0x140012bf7  sub     edx, 1
0x140012bfa  jz      short loc_140012C13
0x140012bfc  cmp     edx, 1
0x140012bff  jz      short loc_140012C0A
0x140012c01  lea     rax, aIrpMn; "IRP_MN_?????"
0x140012c08  retn
0x140012c0a  lea     rax, aIrpMnSurpriseR; "IRP_MN_SURPRISE_REMOVAL"
0x140012c11  retn
0x140012c13  lea     rax, aIrpMnDeviceUsa; "IRP_MN_DEVICE_USAGE_NOTIFICATION"
0x140012c1a  retn
0x140012c1c  lea     rax, aIrpMnQueryBusI; "IRP_MN_QUERY_BUS_INFORMATION"
0x140012c23  retn
0x140012c25  lea     rax, aIrpMnQueryPnpD; "IRP_MN_QUERY_PNP_DEVICE_STATE"
0x140012c2c  retn
0x140012c2e  lea     rax, aIrpMnQueryId; "IRP_MN_QUERY_ID"
0x140012c35  retn
```
