# _parseDMConfigRootNodeExt

- ea: `0x18000f26c`
- end: `0x18000f50a`
- name: `_parseDMConfigRootNodeExt`
- size: `670`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f1d8`

## callees

- `0x180001670`
- `0x18000bbd8`
- `0x18000f26c`
- `0x180012968`
- `0x180012bc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000f338`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000f338`

## pseudocode

```c
__int64 __fastcall parseDMConfigRootNodeExt(
        struct IXMLDOMNode *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 result; // rax
  unsigned int v9[4]; // [rsp+40h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-88h] BYREF

  result = XcGetNodeStringValue(a1, L"MBNProfileV4:Name", a2, 0x100u, 0, 0, 0);
  if ( !(_DWORD)result )
  {
    result = XcGetNodeStringValue(a1, L"MBNProfileV4:SimIccID", a2 + 1556, 0x15u, 0, 0, 0);
    if ( !(_DWORD)result )
    {
      result = XcGetNodeStringValue(a1, L"MBNProfileV4:OemConnectionId", sz, 0x28u, 0, 0, 0);
      if ( !(_DWORD)result )
      {
        if ( IIDFromString(sz, (LPIID)a2 + 294) )
        {
          return 1206;
        }
        else
        {
          result = XcGetNodeEnumValue(
                     a1,
                     L"MBNProfileV4:RoamApplicability",
                     (LPCWSTR *)&_roamApplicabilityType,
                     6u,
                     (unsigned int *)a2 + 1175,
                     1,
                     0,
                     0);
          if ( !(_DWORD)result )
          {
            result = _parseNode(
                       a1,
                       L"MBNProfileV4:Context",
                       0,
                       (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))_parseContextNode,
                       (struct WWAN_PROFILE *)a2,
                       a3,
                       a4);
            if ( !(_DWORD)result )
            {
              result = XcGetNodeEnumValue(
                         a1,
                         L"MBNProfileV4:AdminEnable",
                         (LPCWSTR *)&off_180015490,
                         4u,
                         (unsigned int *)a2 + 1174,
                         1,
                         1u,
                         0);
              if ( !(_DWORD)result )
              {
                result = XcGetNodeEnumValue(
                           a1,
                           L"MBNProfileV4:AdminRoamControl",
                           (LPCWSTR *)&_roamControl,
                           3u,
                           (unsigned int *)a2 + 1172,
                           0,
                           0,
                           0);
                if ( !(_DWORD)result )
                {
                  result = XcGetNodeEnumValue(
                             a1,
                             L"MBNProfileV4:ProfileCreationType",
                             (LPCWSTR *)&_creationType,
                             4u,
                             (unsigned int *)a2 + 769,
                             1,
                             3u,
                             0);
                  if ( !(_DWORD)result )
                  {
                    v9[0] = 0;
                    result = XcGetNodeEnumValue(
                               a1,
                               L"MBNProfileV7:IsBasedOnModemProvisionedContext",
                               (LPCWSTR *)&off_180015490,
                               4u,
                               v9,
                               1,
                               0,
                               0);
                    if ( !(_DWORD)result )
                    {
                      if ( v9[0] )
                        *((_DWORD *)a2 + 769) = 4;
                      return _parseNode(
                               a1,
                               L"MBNProfileV7:ModemDMProfilePurposes",
                               1,
                               parseModemDMProfilePurposesNode,
                               (struct WWAN_PROFILE *)a2,
                               0,
                               a4);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f26c  mov     [rsp+arg_10], rbx
0x18000f271  push    rbp
0x18000f272  push    rsi
0x18000f273  push    rdi
0x18000f274  push    r14
0x18000f276  push    r15
0x18000f278  sub     rsp, 0B0h
0x18000f27f  mov     rax, cs:__security_cookie
0x18000f286  xor     rax, rsp
0x18000f289  mov     [rsp+0D8h+var_38], rax
0x18000f291  xor     r14d, r14d
0x18000f294  mov     esi, r8d
0x18000f297  mov     [rsp+0D8h+var_A8], r14; int *
0x18000f29c  mov     ebp, r9d
0x18000f29f  mov     rdi, rdx
0x18000f2a2  mov     [rsp+0D8h+var_B0], r14; unsigned __int16 *
0x18000f2a7  mov     r8, rdx; unsigned __int16 *
0x18000f2aa  mov     dword ptr [rsp+0D8h+var_B8], r14d; int
0x18000f2af  mov     r9d, 100h; unsigned __int64
0x18000f2b5  lea     rdx, aMbnprofilev4Na; "MBNProfileV4:Name"
0x18000f2bc  mov     rbx, rcx
0x18000f2bf  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000f2c4  test    eax, eax
0x18000f2c6  jnz     loc_18000F4E3
0x18000f2cc  mov     [rsp+0D8h+var_A8], r14; int *
0x18000f2d1  lea     r8, [rdi+0C28h]; unsigned __int16 *
0x18000f2d8  mov     [rsp+0D8h+var_B0], r14; unsigned __int16 *
0x18000f2dd  lea     r9d, [r14+15h]; unsigned __int64
0x18000f2e1  lea     rdx, aMbnprofilev4Si; "MBNProfileV4:SimIccID"
0x18000f2e8  mov     dword ptr [rsp+0D8h+var_B8], r14d; int
0x18000f2ed  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f2f0  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000f2f5  test    eax, eax
0x18000f2f7  jnz     loc_18000F4E3
0x18000f2fd  mov     [rsp+0D8h+var_A8], r14; int *
0x18000f302  lea     r9d, [r14+28h]; unsigned __int64
0x18000f306  mov     [rsp+0D8h+var_B0], r14; unsigned __int16 *
0x18000f30b  lea     r8, [rsp+0D8h+sz]; unsigned __int16 *
0x18000f310  lea     rdx, aMbnprofilev4Oe; "MBNProfileV4:OemConnectionId"
0x18000f317  mov     dword ptr [rsp+0D8h+var_B8], r14d; int
0x18000f31c  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f31f  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000f324  test    eax, eax
0x18000f326  jnz     loc_18000F4E3
0x18000f32c  lea     rdx, [rdi+1260h]; lpiid
0x18000f333  lea     rcx, [rsp+0D8h+sz]; lpsz
0x18000f338  call    cs:__imp_IIDFromString
0x18000f33e  test    eax, eax
0x18000f340  jz      short loc_18000F34C
0x18000f342  mov     eax, 4B6h
0x18000f347  jmp     loc_18000F4E3
0x18000f34c  mov     [rsp+0D8h+var_A0], r14; int *
0x18000f351  lea     rax, [rdi+125Ch]
0x18000f358  mov     r15d, 1
0x18000f35e  mov     dword ptr [rsp+0D8h+var_A8], r14d; unsigned int
0x18000f363  mov     dword ptr [rsp+0D8h+var_B0], r15d; int
0x18000f368  lea     r8, ?_roamApplicabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000f36f  lea     rdx, aMbnprofilev4Ro; "MBNProfileV4:RoamApplicability"
0x18000f376  mov     [rsp+0D8h+var_B8], rax; unsigned int *
0x18000f37b  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f37e  lea     r9d, [r15+5]; unsigned int
0x18000f382  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000f387  test    eax, eax
0x18000f389  jnz     loc_18000F4E3
0x18000f38f  mov     dword ptr [rsp+0D8h+var_A8], ebp; unsigned int
0x18000f393  lea     r9, ?_parseContextNode@@YAKPEAUIXMLDOMNode@@PEAUWWAN_PROFILE@@HK@Z; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x18000f39a  mov     dword ptr [rsp+0D8h+var_B0], esi; int
0x18000f39e  lea     rdx, aMbnprofilev4Co_3; "MBNProfileV4:Context"
0x18000f3a5  xor     r8d, r8d; int
0x18000f3a8  mov     [rsp+0D8h+var_B8], rdi; struct WWAN_PROFILE *
0x18000f3ad  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f3b0  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x18000f3b5  test    eax, eax
0x18000f3b7  jnz     loc_18000F4E3
0x18000f3bd  mov     [rsp+0D8h+var_A0], r14; int *
0x18000f3c2  lea     rax, [rdi+1258h]
0x18000f3c9  mov     dword ptr [rsp+0D8h+var_A8], r15d; unsigned int
0x18000f3ce  lea     r9d, [r15+3]; unsigned int
0x18000f3d2  mov     dword ptr [rsp+0D8h+var_B0], r15d; int
0x18000f3d7  lea     r8, off_180015490; struct _XC_STRING_VALUE_MAPPING *
0x18000f3de  lea     rdx, aMbnprofilev4Ad; "MBNProfileV4:AdminEnable"
0x18000f3e5  mov     [rsp+0D8h+var_B8], rax; unsigned int *
0x18000f3ea  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f3ed  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000f3f2  test    eax, eax
0x18000f3f4  jnz     loc_18000F4E3
0x18000f3fa  mov     [rsp+0D8h+var_A0], r14; int *
0x18000f3ff  lea     rax, [rdi+1250h]
0x18000f406  mov     dword ptr [rsp+0D8h+var_A8], r14d; unsigned int
0x18000f40b  lea     r9d, [r15+2]; unsigned int
0x18000f40f  mov     dword ptr [rsp+0D8h+var_B0], r14d; int
0x18000f414  lea     r8, ?_roamControl@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000f41b  lea     rdx, aMbnprofilev4Ad_0; "MBNProfileV4:AdminRoamControl"
0x18000f422  mov     [rsp+0D8h+var_B8], rax; unsigned int *
0x18000f427  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f42a  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000f42f  test    eax, eax
0x18000f431  jnz     loc_18000F4E3
0x18000f437  mov     [rsp+0D8h+var_A0], r14; int *
0x18000f43c  lea     rsi, [rdi+0C04h]
0x18000f443  mov     dword ptr [rsp+0D8h+var_A8], 3; unsigned int
0x18000f44b  lea     r9d, [r15+3]; unsigned int
0x18000f44f  mov     dword ptr [rsp+0D8h+var_B0], r15d; int
0x18000f454  lea     r8, ?_creationType@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000f45b  lea     rdx, aMbnprofilev4Pr_0; "MBNProfileV4:ProfileCreationType"
0x18000f462  mov     [rsp+0D8h+var_B8], rsi; unsigned int *
0x18000f467  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f46a  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000f46f  test    eax, eax
0x18000f471  jnz     short loc_18000F4E3
0x18000f473  mov     [rsp+0D8h+var_A0], r14; int *
0x18000f478  lea     rax, [rsp+0D8h+var_98]
0x18000f47d  mov     dword ptr [rsp+0D8h+var_A8], r14d; unsigned int
0x18000f482  lea     r9d, [r15+3]; unsigned int
0x18000f486  mov     dword ptr [rsp+0D8h+var_B0], r15d; int
0x18000f48b  lea     r8, off_180015490; struct _XC_STRING_VALUE_MAPPING *
0x18000f492  lea     rdx, aMbnprofilev7Is; "MBNProfileV7:IsBasedOnModemProvisionedC"...
0x18000f499  mov     [rsp+0D8h+var_B8], rax; unsigned int *
0x18000f49e  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f4a1  mov     [rsp+0D8h+var_98], r14d
0x18000f4a6  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000f4ab  test    eax, eax
0x18000f4ad  jnz     short loc_18000F4E3
0x18000f4af  cmp     [rsp+0D8h+var_98], r14d
0x18000f4b4  jz      short loc_18000F4BC
0x18000f4b6  mov     dword ptr [rsi], 4
0x18000f4bc  mov     dword ptr [rsp+0D8h+var_A8], ebp; unsigned int
0x18000f4c0  lea     r9, _parseModemDMProfilePurposesNode; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x18000f4c7  mov     dword ptr [rsp+0D8h+var_B0], r14d; int
0x18000f4cc  lea     rdx, aMbnprofilev7Mo; "MBNProfileV7:ModemDMProfilePurposes"
0x18000f4d3  mov     r8d, r15d; int
0x18000f4d6  mov     [rsp+0D8h+var_B8], rdi; struct WWAN_PROFILE *
0x18000f4db  mov     rcx, rbx; struct IXMLDOMNode *
0x18000f4de  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x18000f4e3  mov     rcx, [rsp+0D8h+var_38]
0x18000f4eb  xor     rcx, rsp; StackCookie
0x18000f4ee  call    __security_check_cookie
0x18000f4f3  mov     rbx, [rsp+0D8h+arg_10]
0x18000f4fb  add     rsp, 0B0h
0x18000f502  pop     r15
0x18000f504  pop     r14
0x18000f506  pop     rdi
0x18000f507  pop     rsi
0x18000f508  pop     rbp
0x18000f509  retn
```
