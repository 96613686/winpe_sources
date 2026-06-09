# _parseProfileConditionsNode

- ea: `0x18000bd80`
- end: `0x18000bf79`
- name: `_parseProfileConditionsNode`
- size: `505`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x18000bd80`
- `0x18000d4bc`
- `0x180012968`
- `0x180012bc8`

## string_xrefs

- `0x18000beb8`: `MBNProfileV9:IMSI`
- `0x18000bec4`: `MBNProfileV4:IMSI`
- `0x18000becb`: `MBNProfile:IMSI`

## pseudocode

```c
unsigned int __fastcall parseProfileConditionsNode(struct IXMLDOMNode *a1, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rbp
  const unsigned __int16 *v7; // rdx
  unsigned int result; // eax
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx

  v4 = a2 + 4632;
  if ( a4 < 3 )
  {
    v7 = L"MBNProfileV4:CellularClass";
    if ( a4 != 2 )
      v7 = L"MBNProfile:CellularClass";
  }
  else
  {
    v7 = L"MBNProfileV9:CellularClass";
  }
  result = XcGetNodeEnumValue(
             a1,
             v7,
             (const struct _XC_STRING_VALUE_MAPPING *)&_cellularClass,
             2u,
             (unsigned int *)v4,
             1,
             0,
             0);
  if ( !result )
  {
    if ( a4 < 3 )
    {
      v9 = L"MBNProfileV4:RATApplicability";
      if ( a4 != 2 )
        v9 = L"MBNProfile:RATApplicability";
    }
    else
    {
      v9 = L"MBNProfileV9:RATApplicability";
    }
    result = XcGetNodeEnumValue(
               a1,
               v9,
               (const struct _XC_STRING_VALUE_MAPPING *)&_rATApplicability,
               2u,
               (unsigned int *)(v4 + 4),
               1,
               0,
               0);
    if ( !result )
    {
      if ( a4 < 3 )
      {
        v10 = L"MBNProfileV4:RoamApplicability";
        if ( a4 != 2 )
          v10 = L"MBNProfile:RoamApplicability";
      }
      else
      {
        v10 = L"MBNProfileV9:RoamApplicability";
      }
      result = XcGetNodeEnumValue(
                 a1,
                 v10,
                 (const struct _XC_STRING_VALUE_MAPPING *)&_roamApplicabilityType,
                 6u,
                 (unsigned int *)(v4 + 12),
                 1,
                 0,
                 0);
      if ( !result )
      {
        if ( a4 < 3 )
        {
          v11 = L"MBNProfileV4:IMSI";
          if ( a4 != 2 )
            v11 = L"MBNProfile:IMSI";
        }
        else
        {
          v11 = L"MBNProfileV9:IMSI";
        }
        result = XcGetNodeStringValue(a1, v11, (unsigned __int16 *)(v4 + 16), 0x10u, 1, 0, 0);
        if ( !result && (!*(_WORD *)(v4 + 16) || (result = validateSubId(v4 + 16)) == 0) )
        {
          if ( a4 < 3 )
          {
            v12 = L"MBNProfileV4:IwlanApplicability";
            if ( a4 != 2 )
              v12 = L"MBNProfile:IwlanApplicability";
          }
          else
          {
            v12 = L"MBNProfileV9:IwlanApplicability";
          }
          return XcGetNodeEnumValue(
                   a1,
                   v12,
                   (const struct _XC_STRING_VALUE_MAPPING *)&_iwlanApplicabilityType,
                   3u,
                   (unsigned int *)(v4 + 48),
                   1,
                   0,
                   0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bd80  push    rbx
0x18000bd82  push    rbp
0x18000bd83  push    rsi
0x18000bd84  push    rdi
0x18000bd85  push    r13
0x18000bd87  sub     rsp, 40h
0x18000bd8b  lea     rbp, [rdx+1218h]
0x18000bd92  mov     ebx, r9d
0x18000bd95  mov     rsi, rcx
0x18000bd98  cmp     r9d, 3
0x18000bd9c  jb      short loc_18000BDA7
0x18000bd9e  lea     rdx, aMbnprofilev9Ce; "MBNProfileV9:CellularClass"
0x18000bda5  jmp     short loc_18000BDBC
0x18000bda7  cmp     ebx, 2
0x18000bdaa  lea     rdx, aMbnprofilev4Ce; "MBNProfileV4:CellularClass"
0x18000bdb1  lea     rax, aMbnprofileCell; "MBNProfile:CellularClass"
0x18000bdb8  cmovnz  rdx, rax; unsigned __int16 *
0x18000bdbc  mov     [rsp+68h+var_30], 0; int *
0x18000bdc5  lea     r8, ?_cellularClass@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000bdcc  mov     r13d, 1
0x18000bdd2  mov     dword ptr [rsp+68h+var_38], 0; unsigned int
0x18000bdda  mov     dword ptr [rsp+68h+var_40], r13d; int
0x18000bddf  mov     [rsp+68h+var_48], rbp; unsigned int *
0x18000bde4  lea     r9d, [r13+1]; unsigned int
0x18000bde8  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000bded  test    eax, eax
0x18000bdef  jnz     loc_18000BF6E
0x18000bdf5  cmp     ebx, 3
0x18000bdf8  jb      short loc_18000BE03
0x18000bdfa  lea     rdx, aMbnprofilev9Ra_0; "MBNProfileV9:RATApplicability"
0x18000be01  jmp     short loc_18000BE18
0x18000be03  cmp     ebx, 2
0x18000be06  lea     rdx, aMbnprofilev4Ra; "MBNProfileV4:RATApplicability"
0x18000be0d  lea     rax, aMbnprofileRata; "MBNProfile:RATApplicability"
0x18000be14  cmovnz  rdx, rax; unsigned __int16 *
0x18000be18  mov     [rsp+68h+var_30], 0; int *
0x18000be21  lea     rax, [rbp+4]
0x18000be25  mov     dword ptr [rsp+68h+var_38], 0; unsigned int
0x18000be2d  lea     r8, ?_rATApplicability@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000be34  mov     dword ptr [rsp+68h+var_40], r13d; int
0x18000be39  mov     r9d, 2; unsigned int
0x18000be3f  mov     rcx, rsi; struct IXMLDOMNode *
0x18000be42  mov     [rsp+68h+var_48], rax; unsigned int *
0x18000be47  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000be4c  test    eax, eax
0x18000be4e  jnz     loc_18000BF6E
0x18000be54  cmp     ebx, 3
0x18000be57  jb      short loc_18000BE62
0x18000be59  lea     rdx, aMbnprofilev9Ro_2; "MBNProfileV9:RoamApplicability"
0x18000be60  jmp     short loc_18000BE77
0x18000be62  cmp     ebx, 2
0x18000be65  lea     rdx, aMbnprofilev4Ro; "MBNProfileV4:RoamApplicability"
0x18000be6c  lea     rax, aMbnprofileRoam; "MBNProfile:RoamApplicability"
0x18000be73  cmovnz  rdx, rax; unsigned __int16 *
0x18000be77  mov     [rsp+68h+var_30], 0; int *
0x18000be80  lea     rax, [rbp+0Ch]
0x18000be84  mov     dword ptr [rsp+68h+var_38], 0; unsigned int
0x18000be8c  lea     r8, ?_roamApplicabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000be93  mov     dword ptr [rsp+68h+var_40], r13d; int
0x18000be98  mov     r9d, 6; unsigned int
0x18000be9e  mov     rcx, rsi; struct IXMLDOMNode *
0x18000bea1  mov     [rsp+68h+var_48], rax; unsigned int *
0x18000bea6  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000beab  test    eax, eax
0x18000bead  jnz     loc_18000BF6E
0x18000beb3  cmp     ebx, 3
0x18000beb6  jb      short loc_18000BEC1
0x18000beb8  lea     rdx, aMbnprofilev9Im; "MBNProfileV9:IMSI"
0x18000bebf  jmp     short loc_18000BED6
0x18000bec1  cmp     ebx, 2
0x18000bec4  lea     rdx, aMbnprofilev4Im; "MBNProfileV4:IMSI"
0x18000becb  lea     rax, aMbnprofileImsi; "MBNProfile:IMSI"
0x18000bed2  cmovnz  rdx, rax; unsigned __int16 *
0x18000bed6  mov     [rsp+68h+var_38], 0; int *
0x18000bedf  lea     rdi, [rbp+10h]
0x18000bee3  mov     r8, rdi; unsigned __int16 *
0x18000bee6  mov     [rsp+68h+var_40], 0; unsigned __int16 *
0x18000beef  mov     r9d, 10h; unsigned __int64
0x18000bef5  mov     dword ptr [rsp+68h+var_48], r13d; int
0x18000befa  mov     rcx, rsi; struct IXMLDOMNode *
0x18000befd  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000bf02  test    eax, eax
0x18000bf04  jnz     short loc_18000BF6E
0x18000bf06  cmp     ax, [rdi]
0x18000bf09  jz      short loc_18000BF17
0x18000bf0b  mov     rcx, rdi
0x18000bf0e  call    _validateSubId
0x18000bf13  test    eax, eax
0x18000bf15  jnz     short loc_18000BF6E
0x18000bf17  cmp     ebx, 3
0x18000bf1a  jb      short loc_18000BF25
0x18000bf1c  lea     rdx, aMbnprofilev9Iw; "MBNProfileV9:IwlanApplicability"
0x18000bf23  jmp     short loc_18000BF3A
0x18000bf25  cmp     ebx, 2
0x18000bf28  lea     rdx, aMbnprofilev4Iw; "MBNProfileV4:IwlanApplicability"
0x18000bf2f  lea     rax, aMbnprofileIwla; "MBNProfile:IwlanApplicability"
0x18000bf36  cmovnz  rdx, rax; unsigned __int16 *
0x18000bf3a  mov     [rsp+68h+var_30], 0; int *
0x18000bf43  lea     rax, [rbp+30h]
0x18000bf47  mov     dword ptr [rsp+68h+var_38], 0; unsigned int
0x18000bf4f  lea     r8, ?_iwlanApplicabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000bf56  mov     dword ptr [rsp+68h+var_40], r13d; int
0x18000bf5b  mov     r9d, 3; unsigned int
0x18000bf61  mov     rcx, rsi; struct IXMLDOMNode *
0x18000bf64  mov     [rsp+68h+var_48], rax; unsigned int *
0x18000bf69  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000bf6e  add     rsp, 40h
0x18000bf72  pop     r13
0x18000bf74  pop     rdi
0x18000bf75  pop     rsi
0x18000bf76  pop     rbp
0x18000bf77  pop     rbx
0x18000bf78  retn
```
