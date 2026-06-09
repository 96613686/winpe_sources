# _parseRSDNode(IXMLDOMNode *,ROUTE_SELECTION_DESCRIPTOR *,ulong)

- ea: `0x180011164`
- end: `0x180011497`
- name: `?_parseRSDNode@@YAKPEAUIXMLDOMNode@@PEAUROUTE_SELECTION_DESCRIPTOR@@K@Z`
- size: `819`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct ROUTE_SELECTION_DESCRIPTOR *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800114a0`

## callees

- `0x180010a24`
- `0x180011164`
- `0x180011974`
- `0x18001288c`
- `0x180012968`
- `0x1800131e4`
- `0x180014010`

## string_xrefs

- `0x180011181`: `MBNProfileV9:RouteSelectionDescriptorPrecedence`
- `0x18001118a`: `MBNProfileV4:RouteSelectionDescriptorPrecedence`
- `0x180011191`: `MBNProfile:RouteSelectionDescriptorPrecedence`
- `0x1800112ea`: `MBNProfileV9:AccessTypePreference`
- `0x1800112f3`: `MBNProfileV4:AccessTypePreference`
- `0x1800112fa`: `MBNProfile:AccessTypePreference`

## pseudocode

```c
unsigned int __fastcall _parseRSDNode(
        struct IXMLDOMNode *a1,
        struct ROUTE_SELECTION_DESCRIPTOR *a2,
        unsigned int a3,
        unsigned int a4)
{
  const unsigned __int16 *v7; // rdx
  unsigned int result; // eax
  unsigned int v9; // r9d
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  unsigned int SingleNode; // edi
  const unsigned __int16 *v16; // rdx
  struct IXMLDOMNode *v17; // [rsp+78h] [rbp+38h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  struct IXMLDOMNode *v19; // [rsp+88h] [rbp+48h] BYREF

  if ( a3 < 3 )
  {
    v7 = L"MBNProfileV4:RouteSelectionDescriptorPrecedence";
    if ( a3 != 2 )
      v7 = L"MBNProfile:RouteSelectionDescriptorPrecedence";
  }
  else
  {
    v7 = L"MBNProfileV9:RouteSelectionDescriptorPrecedence";
  }
  result = XcGetNodeDWORDValue(a1, v7, (unsigned int *)a2, a4, 0xFFu, 0, 0, &v18);
  if ( !result )
  {
    if ( a3 < 3 )
    {
      v10 = L"MBNProfileV4:SSCMode";
      if ( a3 != 2 )
        v10 = L"MBNProfile:SSCMode";
    }
    else
    {
      v10 = L"MBNProfileV9:SSCMode";
    }
    result = XcGetNodeDWORDValue(a1, v10, (unsigned int *)((char *)a2 + 1), v9, 3u, 1, 0, (int *)a2 + 1);
    if ( !result )
    {
      if ( a3 < 3 )
      {
        v11 = L"MBNProfileV4:PDUSession";
        if ( a3 != 2 )
          v11 = L"MBNProfile:PDUSession";
      }
      else
      {
        v11 = L"MBNProfileV9:PDUSession";
      }
      result = XcGetNodeEnumValue(
                 a1,
                 v11,
                 (const struct _XC_STRING_VALUE_MAPPING *)&_SessionType,
                 7u,
                 (unsigned int *)a2 + 2,
                 1,
                 0,
                 &v18);
      if ( !result )
      {
        if ( a3 < 3 )
        {
          v12 = L"MBNProfileV4:NonSeamlessSOffloadIndication";
          if ( a3 != 2 )
            v12 = L"MBNProfile:NonSeamlessSOffloadIndication";
        }
        else
        {
          v12 = L"MBNProfileV9:NonSeamlessSOffloadIndication";
        }
        result = XcGetNodeEnumValue(
                   a1,
                   v12,
                   (const struct _XC_STRING_VALUE_MAPPING *)&off_180015490,
                   4u,
                   (unsigned int *)a2 + 3,
                   1,
                   0,
                   0);
        if ( !result )
        {
          if ( a3 < 3 )
          {
            v13 = L"MBNProfileV4:AccessTypePreference";
            if ( a3 != 2 )
              v13 = L"MBNProfile:AccessTypePreference";
          }
          else
          {
            v13 = L"MBNProfileV9:AccessTypePreference";
          }
          result = XcGetNodeEnumValue(
                     a1,
                     v13,
                     (const struct _XC_STRING_VALUE_MAPPING *)&_AccessTypePreference,
                     2u,
                     (unsigned int *)a2 + 4,
                     1,
                     0,
                     0);
          if ( !result )
          {
            v17 = 0;
            if ( a3 < 3 )
            {
              v14 = L"MBNProfileV4:SNSSAIs";
              if ( a3 != 2 )
                v14 = L"MBNProfile:SNSSAIs";
            }
            else
            {
              v14 = L"MBNProfileV9:SNSSAIs";
            }
            SingleNode = XcGetSingleNode(a1, v14, &v17);
            if ( SingleNode )
            {
              if ( SingleNode != 1168 )
              {
                if ( v17 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
                return SingleNode;
              }
            }
            else
            {
              SingleNode = parseSNSSAIs(v17, a2, a3);
              if ( SingleNode )
              {
                if ( v17 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
                return SingleNode;
              }
            }
            v19 = 0;
            if ( a3 < 3 )
            {
              v16 = L"MBNProfileV4:DNNSelections";
              if ( a3 != 2 )
                v16 = L"MBNProfile:DNNSelections";
            }
            else
            {
              v16 = L"MBNProfileV9:DNNSelections";
            }
            SingleNode = XcGetSingleNode(a1, v16, &v19);
            if ( SingleNode )
            {
              if ( SingleNode == 1168 )
                SingleNode = 0;
            }
            else
            {
              SingleNode = parseDNNSelections(v19, a2, a3);
              if ( SingleNode )
              {
                if ( v19 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
                if ( v17 )
                  ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
                return SingleNode;
              }
            }
            if ( v19 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
            if ( v17 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
            return SingleNode;
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
0x180011164  push    rbp
0x180011166  push    rbx
0x180011167  push    rsi
0x180011168  push    rdi
0x180011169  push    r14
0x18001116b  mov     rbp, rsp
0x18001116e  sub     rsp, 40h
0x180011172  mov     ebx, r8d
0x180011175  mov     rsi, rdx
0x180011178  mov     r14, rcx
0x18001117b  cmp     r8d, 3
0x18001117f  jb      short loc_18001118A
0x180011181  lea     rdx, aMbnprofilev9Ro; "MBNProfileV9:RouteSelectionDescriptorPr"...
0x180011188  jmp     short loc_18001119F
0x18001118a  lea     rdx, aMbnprofilev4Ro_1; "MBNProfileV4:RouteSelectionDescriptorPr"...
0x180011191  lea     rax, aMbnprofileRout; "MBNProfile:RouteSelectionDescriptorPrec"...
0x180011198  cmp     ebx, 2
0x18001119b  cmovnz  rdx, rax; unsigned __int16 *
0x18001119f  lea     rax, [rbp+arg_10]
0x1800111a3  mov     [rsp+40h+var_8], rax; int *
0x1800111a8  mov     [rsp+40h+var_10], 0; unsigned int
0x1800111b0  mov     [rsp+40h+var_18], 0; int
0x1800111b8  mov     dword ptr [rsp+40h+var_20], 0FFh; unsigned int
0x1800111c0  mov     r8, rsi; unsigned int *
0x1800111c3  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x1800111c8  test    eax, eax
0x1800111ca  jnz     loc_18001148C
0x1800111d0  cmp     ebx, 3
0x1800111d3  jb      short loc_1800111DE
0x1800111d5  lea     rdx, aMbnprofilev9Ss_0; "MBNProfileV9:SSCMode"
0x1800111dc  jmp     short loc_1800111F3
0x1800111de  lea     rdx, aMbnprofilev4Ss; "MBNProfileV4:SSCMode"
0x1800111e5  lea     rax, aMbnprofileSscm; "MBNProfile:SSCMode"
0x1800111ec  cmp     ebx, 2
0x1800111ef  cmovnz  rdx, rax; unsigned __int16 *
0x1800111f3  lea     rax, [rsi+4]
0x1800111f7  lea     r8, [rsi+1]; unsigned int *
0x1800111fb  mov     [rsp+40h+var_8], rax; int *
0x180011200  mov     [rsp+40h+var_10], 0; unsigned int
0x180011208  mov     edi, 1
0x18001120d  mov     [rsp+40h+var_18], edi; int
0x180011211  mov     dword ptr [rsp+40h+var_20], 3; unsigned int
0x180011219  mov     rcx, r14; struct IXMLDOMNode *
0x18001121c  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180011221  test    eax, eax
0x180011223  jnz     loc_18001148C
0x180011229  cmp     ebx, 3
0x18001122c  jb      short loc_180011237
0x18001122e  lea     rdx, aMbnprofilev9Pd; "MBNProfileV9:PDUSession"
0x180011235  jmp     short loc_18001124C
0x180011237  lea     rdx, aMbnprofilev4Pd; "MBNProfileV4:PDUSession"
0x18001123e  lea     rax, aMbnprofilePdus; "MBNProfile:PDUSession"
0x180011245  cmp     ebx, 2
0x180011248  cmovnz  rdx, rax; unsigned __int16 *
0x18001124c  lea     rax, [rsi+8]
0x180011250  lea     rcx, [rbp+arg_10]
0x180011254  mov     [rsp+40h+var_8], rcx; int *
0x180011259  mov     [rsp+40h+var_10], 0; unsigned int
0x180011261  mov     [rsp+40h+var_18], edi; int
0x180011265  mov     [rsp+40h+var_20], rax; unsigned int *
0x18001126a  mov     r9d, 7; unsigned int
0x180011270  lea     r8, ?_SessionType@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x180011277  mov     rcx, r14; struct IXMLDOMNode *
0x18001127a  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18001127f  test    eax, eax
0x180011281  jnz     loc_18001148C
0x180011287  cmp     ebx, 3
0x18001128a  jb      short loc_180011295
0x18001128c  lea     rdx, aMbnprofilev9No; "MBNProfileV9:NonSeamlessSOffloadIndicat"...
0x180011293  jmp     short loc_1800112AA
0x180011295  lea     rdx, aMbnprofilev4No; "MBNProfileV4:NonSeamlessSOffloadIndicat"...
0x18001129c  lea     rax, aMbnprofileNons; "MBNProfile:NonSeamlessSOffloadIndicatio"...
0x1800112a3  cmp     ebx, 2
0x1800112a6  cmovnz  rdx, rax; unsigned __int16 *
0x1800112aa  lea     rax, [rsi+0Ch]
0x1800112ae  mov     [rsp+40h+var_8], 0; int *
0x1800112b7  mov     [rsp+40h+var_10], 0; unsigned int
0x1800112bf  mov     [rsp+40h+var_18], edi; int
0x1800112c3  mov     [rsp+40h+var_20], rax; unsigned int *
0x1800112c8  mov     r9d, 4; unsigned int
0x1800112ce  lea     r8, off_180015490; struct _XC_STRING_VALUE_MAPPING *
0x1800112d5  mov     rcx, r14; struct IXMLDOMNode *
0x1800112d8  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x1800112dd  test    eax, eax
0x1800112df  jnz     loc_18001148C
0x1800112e5  cmp     ebx, 3
0x1800112e8  jb      short loc_1800112F3
0x1800112ea  lea     rdx, aMbnprofilev9Ac; "MBNProfileV9:AccessTypePreference"
0x1800112f1  jmp     short loc_180011308
0x1800112f3  lea     rdx, aMbnprofilev4Ac; "MBNProfileV4:AccessTypePreference"
0x1800112fa  lea     rax, aMbnprofileAcce; "MBNProfile:AccessTypePreference"
0x180011301  cmp     ebx, 2
0x180011304  cmovnz  rdx, rax; unsigned __int16 *
0x180011308  lea     rax, [rsi+10h]
0x18001130c  mov     [rsp+40h+var_8], 0; int *
0x180011315  mov     [rsp+40h+var_10], 0; unsigned int
0x18001131d  mov     [rsp+40h+var_18], edi; int
0x180011321  mov     [rsp+40h+var_20], rax; unsigned int *
0x180011326  mov     r9d, 2; unsigned int
0x18001132c  lea     r8, ?_AccessTypePreference@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x180011333  mov     rcx, r14; struct IXMLDOMNode *
0x180011336  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18001133b  test    eax, eax
0x18001133d  jnz     loc_18001148C
0x180011343  mov     [rbp+arg_8], 0
0x18001134b  cmp     ebx, 3
0x18001134e  jb      short loc_180011359
0x180011350  lea     rdx, aMbnprofilev9Sn; "MBNProfileV9:SNSSAIs"
0x180011357  jmp     short loc_18001136E
0x180011359  lea     rdx, aMbnprofilev4Sn; "MBNProfileV4:SNSSAIs"
0x180011360  lea     rax, aMbnprofileSnss_0; "MBNProfile:SNSSAIs"
0x180011367  cmp     ebx, 2
0x18001136a  cmovnz  rdx, rax; unsigned __int16 *
0x18001136e  lea     r8, [rbp+arg_8]; struct IXMLDOMNode **
0x180011372  mov     rcx, r14; struct IXMLDOMNode *
0x180011375  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18001137a  mov     edi, eax
0x18001137c  test    eax, eax
0x18001137e  jnz     short loc_1800113B0
0x180011380  mov     r8d, ebx
0x180011383  mov     rdx, rsi
0x180011386  mov     rcx, [rbp+arg_8]
0x18001138a  call    _parseSNSSAIs
0x18001138f  mov     edi, eax
0x180011391  test    eax, eax
0x180011393  jz      short loc_1800113D3
0x180011395  mov     rcx, [rbp+arg_8]
0x180011399  test    rcx, rcx
0x18001139c  jz      short loc_1800113AB
0x18001139e  mov     rdx, [rcx]
0x1800113a1  mov     rax, [rdx+10h]
0x1800113a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113aa  nop
0x1800113ab  jmp     loc_18001148A
0x1800113b0  cmp     edi, 490h
0x1800113b6  jz      short loc_1800113D3
0x1800113b8  mov     rcx, [rbp+arg_8]
0x1800113bc  test    rcx, rcx
0x1800113bf  jz      short loc_1800113CE
0x1800113c1  mov     rax, [rcx]
0x1800113c4  mov     rax, [rax+10h]
0x1800113c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113cd  nop
0x1800113ce  jmp     loc_18001148A
0x1800113d3  mov     [rbp+arg_18], 0
0x1800113db  cmp     ebx, 3
0x1800113de  jb      short loc_1800113E9
0x1800113e0  lea     rdx, aMbnprofilev9Dn_1; "MBNProfileV9:DNNSelections"
0x1800113e7  jmp     short loc_1800113FE
0x1800113e9  lea     rdx, aMbnprofilev4Dn_0; "MBNProfileV4:DNNSelections"
0x1800113f0  lea     rax, aMbnprofileDnns; "MBNProfile:DNNSelections"
0x1800113f7  cmp     ebx, 2
0x1800113fa  cmovnz  rdx, rax; unsigned __int16 *
0x1800113fe  lea     r8, [rbp+arg_18]; struct IXMLDOMNode **
0x180011402  mov     rcx, r14; struct IXMLDOMNode *
0x180011405  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18001140a  mov     edi, eax
0x18001140c  test    eax, eax
0x18001140e  jnz     short loc_180011453
0x180011410  mov     r8d, ebx
0x180011413  mov     rdx, rsi
0x180011416  mov     rcx, [rbp+arg_18]
0x18001141a  call    _parseDNNSelections
0x18001141f  mov     edi, eax
0x180011421  test    eax, eax
0x180011423  jz      short loc_18001145E
0x180011425  mov     rcx, [rbp+arg_18]
0x180011429  test    rcx, rcx
0x18001142c  jz      short loc_18001143B
0x18001142e  mov     rdx, [rcx]
0x180011431  mov     rax, [rdx+10h]
0x180011435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001143a  nop
0x18001143b  mov     rcx, [rbp+arg_8]
0x18001143f  test    rcx, rcx
0x180011442  jz      short loc_180011451
0x180011444  mov     rax, [rcx]
0x180011447  mov     rax, [rax+10h]
0x18001144b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011450  nop
0x180011451  jmp     short loc_18001148A
0x180011453  xor     eax, eax
0x180011455  cmp     edi, 490h
0x18001145b  cmovz   edi, eax
0x18001145e  mov     rcx, [rbp+arg_18]
0x180011462  test    rcx, rcx
0x180011465  jz      short loc_180011474
0x180011467  mov     rax, [rcx]
0x18001146a  mov     rax, [rax+10h]
0x18001146e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011473  nop
0x180011474  mov     rcx, [rbp+arg_8]
0x180011478  test    rcx, rcx
0x18001147b  jz      short loc_18001148A
0x18001147d  mov     rax, [rcx]
0x180011480  mov     rax, [rax+10h]
0x180011484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011489  nop
0x18001148a  mov     eax, edi
0x18001148c  add     rsp, 40h
0x180011490  pop     r14
0x180011492  pop     rdi
0x180011493  pop     rsi
0x180011494  pop     rbx
0x180011495  pop     rbp
0x180011496  retn
```
