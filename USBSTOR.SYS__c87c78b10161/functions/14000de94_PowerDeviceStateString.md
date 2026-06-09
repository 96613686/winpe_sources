# PowerDeviceStateString

- ea: `0x14000de94`
- end: `0x14000deef`
- name: `PowerDeviceStateString`
- size: `91`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400084c0`
- `0x14000cd00`
- `0x14000ced4`
- `0x14000d1f0`

## callees

- `0x14000de94`

## pseudocode

```c
const char *__fastcall PowerDeviceStateString(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx

  if ( !a1 )
    return "PowerDeviceUnspecified";
  v1 = a1 - 1;
  if ( !v1 )
    return "PowerDeviceD0";
  v2 = v1 - 1;
  if ( !v2 )
    return "PowerDeviceD1";
  v3 = v2 - 1;
  if ( !v3 )
    return "PowerDeviceD2";
  v4 = v3 - 1;
  if ( !v4 )
    return "PowerDeviceD3";
  if ( v4 == 1 )
    return "PowerDeviceMaximum";
  return "PowerDevice?????";
}

```

## disassembly

```asm
0x14000de94  test    ecx, ecx
0x14000de96  jz      short loc_14000DEE7
0x14000de98  sub     ecx, 1
0x14000de9b  jz      short loc_14000DEDE
0x14000de9d  sub     ecx, 1
0x14000dea0  jz      short loc_14000DED5
0x14000dea2  sub     ecx, 1
0x14000dea5  jz      short loc_14000DECC
0x14000dea7  sub     ecx, 1
0x14000deaa  jz      short loc_14000DEC3
0x14000deac  cmp     ecx, 1
0x14000deaf  jz      short loc_14000DEBA
0x14000deb1  lea     rax, aPowerdevice; "PowerDevice?????"
0x14000deb8  retn
0x14000deba  lea     rax, aPowerdevicemax; "PowerDeviceMaximum"
0x14000dec1  retn
0x14000dec3  lea     rax, aPowerdeviced3; "PowerDeviceD3"
0x14000deca  retn
0x14000decc  lea     rax, aPowerdeviced2; "PowerDeviceD2"
0x14000ded3  retn
0x14000ded5  lea     rax, aPowerdeviced1; "PowerDeviceD1"
0x14000dedc  retn
0x14000dede  lea     rax, aPowerdeviced0; "PowerDeviceD0"
0x14000dee5  retn
0x14000dee7  lea     rax, aPowerdeviceuns; "PowerDeviceUnspecified"
0x14000deee  retn
```
