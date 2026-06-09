# _anonymous_namespace_::ObjectTypeToString

- ea: `0x18001957c`
- end: `0x180019621`
- name: `_anonymous_namespace_::ObjectTypeToString`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001949c`

## callees

- `0x18001957c`

## string_xrefs

- `0x1800195a8`: `NetSetupObjectTypeProtocolDriver`
- `0x1800195a0`: `NetSetupObjectTypeServiceDriver`
- `0x180019619`: `NetSetupObjectTypeBindingPath`

## pseudocode

```c
const wchar_t *__fastcall anonymous_namespace_::ObjectTypeToString(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx

  if ( a1 <= 6 )
  {
    if ( a1 == 6 )
      return L"NetSetupObjectTypeClientDriver";
    if ( !a1 )
      return L"NetSetupObjectTypeUnknown";
    v1 = a1 - 1;
    if ( !v1 )
      return L"NetSetupObjectTypeGlobal";
    v2 = v1 - 1;
    if ( !v2 )
      return L"NetSetupObjectTypeInterface";
    v3 = v2 - 1;
    if ( !v3 )
      return L"NetSetupObjectTypeFilterDriver";
    v4 = v3 - 1;
    if ( !v4 )
      return L"NetSetupObjectTypeProtocolDriver";
    if ( v4 == 1 )
      return L"NetSetupObjectTypeServiceDriver";
    return L"NetSetupObjectTypeInvalid";
  }
  v6 = a1 - 7;
  if ( !v6 )
    return L"NetSetupObjectTypeBindingPath";
  v7 = v6 - 1;
  if ( !v7 )
    return L"NetSetupObjectTypeMux";
  v8 = v7 - 1;
  if ( !v8 )
    return L"NetSetupObjectTypeTransaction";
  v9 = v8 - 1;
  if ( !v9 )
    return L"NetSetupObjectTypeReflectedProperty";
  if ( v9 != 1 )
    return L"NetSetupObjectTypeInvalid";
  return L"NetSetupObjectTypeBindRule";
}

```

## disassembly

```asm
0x18001957c  cmp     ecx, 6
0x18001957f  jg      short loc_1800195D8
0x180019581  jz      short loc_1800195D0
0x180019583  test    ecx, ecx
0x180019585  jz      short loc_1800195C8
0x180019587  sub     ecx, 1
0x18001958a  jz      short loc_1800195C0
0x18001958c  sub     ecx, 1
0x18001958f  jz      short loc_1800195B8
0x180019591  sub     ecx, 1
0x180019594  jz      short loc_1800195B0
0x180019596  sub     ecx, 1
0x180019599  jz      short loc_1800195A8
0x18001959b  cmp     ecx, 1
0x18001959e  jnz     short loc_1800195F1
0x1800195a0  lea     rax, aNetsetupobject_1; "NetSetupObjectTypeServiceDriver"
0x1800195a7  retn
0x1800195a8  lea     rax, aNetsetupobject; "NetSetupObjectTypeProtocolDriver"
0x1800195af  retn
0x1800195b0  lea     rax, aNetsetupobject_6; "NetSetupObjectTypeFilterDriver"
0x1800195b7  retn
0x1800195b8  lea     rax, aNetsetupobject_10; "NetSetupObjectTypeInterface"
0x1800195bf  retn
0x1800195c0  lea     rax, aNetsetupobject_4; "NetSetupObjectTypeGlobal"
0x1800195c7  retn
0x1800195c8  lea     rax, aNetsetupobject_7; "NetSetupObjectTypeUnknown"
0x1800195cf  retn
0x1800195d0  lea     rax, aNetsetupobject_0; "NetSetupObjectTypeClientDriver"
0x1800195d7  retn
0x1800195d8  sub     ecx, 7
0x1800195db  jz      short loc_180019619
0x1800195dd  sub     ecx, 1
0x1800195e0  jz      short loc_180019611
0x1800195e2  sub     ecx, 1
0x1800195e5  jz      short loc_180019609
0x1800195e7  sub     ecx, 1
0x1800195ea  jz      short loc_180019601
0x1800195ec  cmp     ecx, 1
0x1800195ef  jz      short loc_1800195F9
0x1800195f1  lea     rax, aNetsetupobject_9; "NetSetupObjectTypeInvalid"
0x1800195f8  retn
0x1800195f9  lea     rax, aNetsetupobject_3; "NetSetupObjectTypeBindRule"
0x180019600  retn
0x180019601  lea     rax, aNetsetupobject_8; "NetSetupObjectTypeReflectedProperty"
0x180019608  retn
0x180019609  lea     rax, aNetsetupobject_11; "NetSetupObjectTypeTransaction"
0x180019610  retn
0x180019611  lea     rax, aNetsetupobject_5; "NetSetupObjectTypeMux"
0x180019618  retn
0x180019619  lea     rax, aNetsetupobject_2; "NetSetupObjectTypeBindingPath"
0x180019620  retn
```
