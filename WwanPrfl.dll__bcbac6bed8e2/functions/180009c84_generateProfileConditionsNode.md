# _generateProfileConditionsNode

- ea: `0x180009c84`
- end: `0x180009f6d`
- name: `_generateProfileConditionsNode`
- size: `745`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000a298`

## callees

- `0x180009c84`
- `0x180011f90`
- `0x180012310`
- `0x180014010`

## string_xrefs

- `0x180009cd5`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x180009ce6`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009d53`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009dc3`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009e33`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009ea7`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009f05`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180009cce`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009d5d`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009dcd`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009e3d`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009eb1`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180009f0f`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
__int64 __fastcall generateProfileConditionsNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 result; // rax
  OLECHAR *v8; // r14
  OLECHAR *v9; // r9
  unsigned int v10; // edi
  struct IXMLDOMNode *v11; // rbx
  OLECHAR *v12; // r9
  unsigned int v13; // eax
  OLECHAR *v14; // r9
  unsigned int v15; // eax
  OLECHAR *v16; // r9
  OLECHAR *v17; // r9
  unsigned int v18; // eax
  struct IXMLDOMNode *v19; // [rsp+90h] [rbp+18h] BYREF

  if ( *(_QWORD *)a3 || *(_DWORD *)(a3 + 12) || *(_DWORD *)(a3 + 48) || (result = 0, *(_WORD *)(a3 + 16)) )
  {
    v19 = 0;
    v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    if ( a4 < 3 )
    {
      v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v9 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    v10 = XcAddChildElement(a1, a2, (OLECHAR *)L"ProfileConditionedOn", v9, 0, &v19);
    if ( v10 )
    {
      if ( v19 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v19->lpVtbl->Release)(v19);
    }
    else
    {
      v11 = v19;
      if ( !*(_DWORD *)a3 )
        goto LABEL_22;
      if ( a4 < 3 )
      {
        v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
        if ( a4 != 2 )
          v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
      }
      else
      {
        v12 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
      }
      v10 = XcAddChildElementEnum(
              a1,
              v19,
              (OLECHAR *)L"CellularClass",
              v12,
              *(_DWORD *)a3,
              (const struct _XC_STRING_VALUE_MAPPING *)&_cellularClass,
              2u);
      if ( v10 )
      {
        if ( v11 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
      }
      else
      {
LABEL_22:
        v13 = *(_DWORD *)(a3 + 4);
        if ( !v13 )
          goto LABEL_31;
        if ( a4 < 3 )
        {
          v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
          if ( a4 != 2 )
            v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
        }
        else
        {
          v14 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
        }
        v10 = XcAddChildElementEnum(
                a1,
                v11,
                (OLECHAR *)L"RATApplicability",
                v14,
                v13,
                (const struct _XC_STRING_VALUE_MAPPING *)&_rATApplicability,
                2u);
        if ( v10 )
        {
          if ( v11 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
        }
        else
        {
LABEL_31:
          v15 = *(_DWORD *)(a3 + 12);
          if ( !v15 )
            goto LABEL_59;
          if ( a4 < 3 )
          {
            v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
            if ( a4 != 2 )
              v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
          }
          else
          {
            v16 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
          }
          v10 = XcAddChildElementEnum(
                  a1,
                  v11,
                  (OLECHAR *)L"RoamApplicability",
                  v16,
                  v15,
                  (const struct _XC_STRING_VALUE_MAPPING *)&_roamApplicabilityType,
                  6u);
          if ( v10 )
          {
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
          }
          else
          {
LABEL_59:
            if ( !*(_WORD *)(a3 + 16) )
              goto LABEL_49;
            if ( a4 < 3 )
            {
              v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
              if ( a4 != 2 )
                v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
            }
            else
            {
              v17 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
            }
            v10 = XcAddChildElement(a1, v11, (OLECHAR *)L"IMSI", v17, (OLECHAR *)(a3 + 16), 0);
            if ( v10 )
            {
              if ( v11 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
            }
            else
            {
LABEL_49:
              v18 = *(_DWORD *)(a3 + 48);
              if ( v18 )
              {
                if ( a4 < 3 )
                {
                  v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
                  if ( a4 != 2 )
                    v8 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
                }
                v10 = XcAddChildElementEnum(
                        a1,
                        v11,
                        (OLECHAR *)L"IwlanApplicability",
                        v8,
                        v18,
                        (const struct _XC_STRING_VALUE_MAPPING *)&_iwlanApplicabilityType,
                        3u);
              }
              if ( v11 )
                ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
            }
          }
        }
      }
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180009c84  push    rbx
0x180009c86  push    rbp
0x180009c87  push    rsi
0x180009c88  push    rdi
0x180009c89  push    r14
0x180009c8b  push    r15
0x180009c8d  sub     rsp, 48h
0x180009c91  mov     ebp, r9d
0x180009c94  mov     rsi, r8
0x180009c97  mov     r15, rcx
0x180009c9a  cmp     dword ptr [r8], 0
0x180009c9e  jnz     short loc_180009CC2
0x180009ca0  cmp     dword ptr [r8+4], 0
0x180009ca5  jnz     short loc_180009CC2
0x180009ca7  cmp     dword ptr [r8+0Ch], 0
0x180009cac  jnz     short loc_180009CC2
0x180009cae  cmp     dword ptr [r8+30h], 0
0x180009cb3  jnz     short loc_180009CC2
0x180009cb5  xor     eax, eax
0x180009cb7  cmp     ax, [r8+10h]
0x180009cbc  jz      loc_180009F60
0x180009cc2  mov     [rsp+78h+arg_10], 0
0x180009cce  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009cd5  lea     r14, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x180009cdc  cmp     ebp, 3
0x180009cdf  jb      short loc_180009CE6
0x180009ce1  mov     r9, r14
0x180009ce4  jmp     short loc_180009CF4
0x180009ce6  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009ced  cmp     ebp, 2
0x180009cf0  cmovnz  r9, rax; OLECHAR *
0x180009cf4  lea     rax, [rsp+78h+arg_10]
0x180009cfc  mov     [rsp+78h+var_50], rax; struct IXMLDOMNode **
0x180009d01  mov     [rsp+78h+var_58], 0; OLECHAR *
0x180009d0a  lea     r8, aProfileconditi; "ProfileConditionedOn"
0x180009d11  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180009d16  mov     edi, eax
0x180009d18  test    eax, eax
0x180009d1a  jz      short loc_180009D3B
0x180009d1c  mov     rcx, [rsp+78h+arg_10]
0x180009d24  test    rcx, rcx
0x180009d27  jz      short loc_180009D36
0x180009d29  mov     rdx, [rcx]
0x180009d2c  mov     rax, [rdx+10h]
0x180009d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d35  nop
0x180009d36  jmp     loc_180009F5E
0x180009d3b  mov     eax, [rsi]
0x180009d3d  mov     rbx, [rsp+78h+arg_10]
0x180009d45  test    eax, eax
0x180009d47  jz      short loc_180009DB2
0x180009d49  cmp     ebp, 3
0x180009d4c  jb      short loc_180009D53
0x180009d4e  mov     r9, r14
0x180009d51  jmp     short loc_180009D68
0x180009d53  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009d5a  cmp     ebp, 2
0x180009d5d  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009d64  cmovnz  r9, rcx; OLECHAR *
0x180009d68  mov     [rsp+78h+var_48], 2; unsigned int
0x180009d70  lea     rcx, ?_cellularClass@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _cellularClass
0x180009d77  mov     [rsp+78h+var_50], rcx; struct _XC_STRING_VALUE_MAPPING *
0x180009d7c  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x180009d80  lea     r8, aCellularclass; "CellularClass"
0x180009d87  mov     rdx, rbx; struct IXMLDOMNode *
0x180009d8a  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180009d8d  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180009d92  mov     edi, eax
0x180009d94  test    eax, eax
0x180009d96  jz      short loc_180009DB2
0x180009d98  test    rbx, rbx
0x180009d9b  jz      short loc_180009DAD
0x180009d9d  mov     rax, [rbx]
0x180009da0  mov     rcx, rbx
0x180009da3  mov     rax, [rax+10h]
0x180009da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dac  nop
0x180009dad  jmp     loc_180009F5E
0x180009db2  mov     eax, [rsi+4]
0x180009db5  test    eax, eax
0x180009db7  jz      short loc_180009E22
0x180009db9  cmp     ebp, 3
0x180009dbc  jb      short loc_180009DC3
0x180009dbe  mov     r9, r14
0x180009dc1  jmp     short loc_180009DD8
0x180009dc3  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009dca  cmp     ebp, 2
0x180009dcd  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009dd4  cmovnz  r9, rcx; OLECHAR *
0x180009dd8  mov     [rsp+78h+var_48], 2; unsigned int
0x180009de0  lea     rcx, ?_rATApplicability@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _rATApplicability
0x180009de7  mov     [rsp+78h+var_50], rcx; struct _XC_STRING_VALUE_MAPPING *
0x180009dec  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x180009df0  lea     r8, aRatapplicabili_0; "RATApplicability"
0x180009df7  mov     rdx, rbx; struct IXMLDOMNode *
0x180009dfa  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180009dfd  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180009e02  mov     edi, eax
0x180009e04  test    eax, eax
0x180009e06  jz      short loc_180009E22
0x180009e08  test    rbx, rbx
0x180009e0b  jz      short loc_180009E1D
0x180009e0d  mov     rax, [rbx]
0x180009e10  mov     rcx, rbx
0x180009e13  mov     rax, [rax+10h]
0x180009e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1c  nop
0x180009e1d  jmp     loc_180009F5E
0x180009e22  mov     eax, [rsi+0Ch]
0x180009e25  test    eax, eax
0x180009e27  jz      short loc_180009E92
0x180009e29  cmp     ebp, 3
0x180009e2c  jb      short loc_180009E33
0x180009e2e  mov     r9, r14
0x180009e31  jmp     short loc_180009E48
0x180009e33  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009e3a  cmp     ebp, 2
0x180009e3d  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009e44  cmovnz  r9, rcx; OLECHAR *
0x180009e48  mov     [rsp+78h+var_48], 6; unsigned int
0x180009e50  lea     rcx, ?_roamApplicabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _roamApplicabilityType
0x180009e57  mov     [rsp+78h+var_50], rcx; struct _XC_STRING_VALUE_MAPPING *
0x180009e5c  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x180009e60  lea     r8, aRoamapplicabil; "RoamApplicability"
0x180009e67  mov     rdx, rbx; struct IXMLDOMNode *
0x180009e6a  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180009e6d  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180009e72  mov     edi, eax
0x180009e74  test    eax, eax
0x180009e76  jz      short loc_180009E92
0x180009e78  test    rbx, rbx
0x180009e7b  jz      short loc_180009E8D
0x180009e7d  mov     rax, [rbx]
0x180009e80  mov     rcx, rbx
0x180009e83  mov     rax, [rax+10h]
0x180009e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e8c  nop
0x180009e8d  jmp     loc_180009F5E
0x180009e92  lea     rcx, [rsi+10h]
0x180009e96  xor     eax, eax
0x180009e98  cmp     ax, [rcx]
0x180009e9b  jz      short loc_180009EF9
0x180009e9d  cmp     ebp, 3
0x180009ea0  jb      short loc_180009EA7
0x180009ea2  mov     r9, r14
0x180009ea5  jmp     short loc_180009EBC
0x180009ea7  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009eae  cmp     ebp, 2
0x180009eb1  lea     rax, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009eb8  cmovnz  r9, rax; OLECHAR *
0x180009ebc  mov     [rsp+78h+var_50], 0; struct IXMLDOMNode **
0x180009ec5  mov     [rsp+78h+var_58], rcx; OLECHAR *
0x180009eca  lea     r8, aImsi; "IMSI"
0x180009ed1  mov     rdx, rbx; struct IXMLDOMNode *
0x180009ed4  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180009ed7  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180009edc  mov     edi, eax
0x180009ede  test    eax, eax
0x180009ee0  jz      short loc_180009EF9
0x180009ee2  test    rbx, rbx
0x180009ee5  jz      short loc_180009EF7
0x180009ee7  mov     rax, [rbx]
0x180009eea  mov     rcx, rbx
0x180009eed  mov     rax, [rax+10h]
0x180009ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef6  nop
0x180009ef7  jmp     short loc_180009F5E
0x180009ef9  mov     eax, [rsi+30h]
0x180009efc  test    eax, eax
0x180009efe  jz      short loc_180009F49
0x180009f00  cmp     ebp, 3
0x180009f03  jnb     short loc_180009F1A
0x180009f05  lea     r14, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009f0c  cmp     ebp, 2
0x180009f0f  lea     rcx, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x180009f16  cmovnz  r14, rcx
0x180009f1a  mov     [rsp+78h+var_48], 3; unsigned int
0x180009f22  lea     rcx, ?_iwlanApplicabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _iwlanApplicabilityType
0x180009f29  mov     [rsp+78h+var_50], rcx; struct _XC_STRING_VALUE_MAPPING *
0x180009f2e  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x180009f32  mov     r9, r14; OLECHAR *
0x180009f35  lea     r8, aIwlanapplicabi; "IwlanApplicability"
0x180009f3c  mov     rdx, rbx; struct IXMLDOMNode *
0x180009f3f  mov     rcx, r15; struct IXMLDOMDocument2 *
0x180009f42  call    ?XcAddChildElementEnum@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEBU_XC_STRING_VALUE_MAPPING@@KPEAPEAU2@@Z; XcAddChildElementEnum(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,_XC_STRING_VALUE_MAPPING const *,ulong,IXMLDOMNode * *)
0x180009f47  mov     edi, eax
0x180009f49  test    rbx, rbx
0x180009f4c  jz      short loc_180009F5E
0x180009f4e  mov     rax, [rbx]
0x180009f51  mov     rcx, rbx
0x180009f54  mov     rax, [rax+10h]
0x180009f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f5d  nop
0x180009f5e  mov     eax, edi
0x180009f60  add     rsp, 48h
0x180009f64  pop     r15
0x180009f66  pop     r14
0x180009f68  pop     rdi
0x180009f69  pop     rsi
0x180009f6a  pop     rbp
0x180009f6b  pop     rbx
0x180009f6c  retn
```
