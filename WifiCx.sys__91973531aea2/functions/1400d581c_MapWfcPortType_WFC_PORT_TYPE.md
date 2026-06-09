# MapWfcPortType(_WFC_PORT_TYPE)

- ea: `0x1400d581c`
- end: `0x1400d58bf`
- name: `?MapWfcPortType@@YAPEBGW4_WFC_PORT_TYPE@@@Z`
- size: `163`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400cecf0`
- `0x1400d6f94`
- `0x1400d7970`
- `0x1400d9b7c`

## callees

- `0x1400d581c`

## string_xrefs

- `0x1400d58a5`: `WfcPortTypeWithDataPath`

## pseudocode

```c
const wchar_t *__fastcall MapWfcPortType(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx

  if ( a1 <= 14 )
  {
    if ( a1 == 14 )
      return L"WfcPortTypeNonSta";
    if ( !a1 )
      return L"WfcPortTypeUnspecified";
    v1 = a1 - 1;
    if ( !v1 )
      return L"WfcPortTypeExtSTA";
    v2 = v1 - 1;
    if ( !v2 )
      return L"WfcPortTypeExtAP";
    v3 = v2 - 2;
    if ( !v3 )
      return L"WfcPortTypeWFDDevice";
    if ( v3 == 4 )
      return L"WfcPortTypeWFDRole";
    return L"WfcPortTypeUnknown";
  }
  v5 = a1 - 16;
  if ( !v5 )
    return L"WfcPortTypeSecondarySTA";
  v6 = v5 - 1;
  if ( !v6 )
    return L"WfcPortTypeAnySta";
  v7 = v6 - 10;
  if ( !v7 )
    return L"WfcPortTypeWithDataPath";
  v8 = v7 - 3;
  if ( !v8 )
    return L"WfcPortTypeNonPrimarySta";
  if ( v8 != 1 )
    return L"WfcPortTypeUnknown";
  return L"WfcPortTypeAll";
}

```

## disassembly

```asm
0x1400d581c  cmp     ecx, 0Eh
0x1400d581f  jg      short loc_1400D5871
0x1400d5821  jz      short loc_1400D5868
0x1400d5823  test    ecx, ecx
0x1400d5825  jz      short loc_1400D585F
0x1400d5827  sub     ecx, 1
0x1400d582a  jz      short loc_1400D5856
0x1400d582c  sub     ecx, 1
0x1400d582f  jz      short loc_1400D584D
0x1400d5831  sub     ecx, 2
0x1400d5834  jz      short loc_1400D5844
0x1400d5836  cmp     ecx, 4
0x1400d5839  jnz     short loc_1400D588A
0x1400d583b  lea     rax, aWfcporttypewfd; "WfcPortTypeWFDRole"
0x1400d5842  retn
0x1400d5844  lea     rax, aWfcporttypewfd_0; "WfcPortTypeWFDDevice"
0x1400d584b  retn
0x1400d584d  lea     rax, aWfcporttypeext_0; "WfcPortTypeExtAP"
0x1400d5854  retn
0x1400d5856  lea     rax, aWfcporttypeext; "WfcPortTypeExtSTA"
0x1400d585d  retn
0x1400d585f  lea     rax, aWfcporttypeuns; "WfcPortTypeUnspecified"
0x1400d5866  retn
0x1400d5868  lea     rax, aWfcporttypenon; "WfcPortTypeNonSta"
0x1400d586f  retn
0x1400d5871  sub     ecx, 10h
0x1400d5874  jz      short loc_1400D58B7
0x1400d5876  sub     ecx, 1
0x1400d5879  jz      short loc_1400D58AE
0x1400d587b  sub     ecx, 0Ah
0x1400d587e  jz      short loc_1400D58A5
0x1400d5880  sub     ecx, 3
0x1400d5883  jz      short loc_1400D589C
0x1400d5885  cmp     ecx, 1
0x1400d5888  jz      short loc_1400D5893
0x1400d588a  lea     rax, aWfcporttypeunk; "WfcPortTypeUnknown"
0x1400d5891  retn
0x1400d5893  lea     rax, aWfcporttypeall; "WfcPortTypeAll"
0x1400d589a  retn
0x1400d589c  lea     rax, aWfcporttypenon_0; "WfcPortTypeNonPrimarySta"
0x1400d58a3  retn
0x1400d58a5  lea     rax, aWfcporttypewit; "WfcPortTypeWithDataPath"
0x1400d58ac  retn
0x1400d58ae  lea     rax, aWfcporttypeany; "WfcPortTypeAnySta"
0x1400d58b5  retn
0x1400d58b7  lea     rax, aWfcporttypesec; "WfcPortTypeSecondarySTA"
0x1400d58be  retn
```
