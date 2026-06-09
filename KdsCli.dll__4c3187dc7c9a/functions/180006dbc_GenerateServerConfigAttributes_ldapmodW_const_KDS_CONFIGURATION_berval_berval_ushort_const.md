# GenerateServerConfigAttributes(ldapmodW * * const,_KDS_CONFIGURATION *,berval *,berval *,ushort * const)

- ea: `0x180006dbc`
- end: `0x180006fa7`
- name: `?GenerateServerConfigAttributes@@YAJQEAPEAUldapmodW@@PEAU_KDS_CONFIGURATION@@PEAUberval@@2QEAG@Z`
- size: `491`
- prototype: `__int64 __usercall@<rax>(struct ldapmodW **const@<rcx>, struct _KDS_CONFIGURATION *@<rdx>, struct berval *@<r8>, struct berval *@<r9>, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007a10`

## callees

- `0x180002a14`
- `0x180002a5c`
- `0x180002b28`
- `0x180006dbc`
- `0x18001a450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180006df3`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180006e22`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180006df3`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180006e22`

## string_xrefs

- `0x180006f77`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdssrvconfig.cxx`

## pseudocode

```c
__int64 __fastcall GenerateServerConfigAttributes(
        struct ldapmodW **const a1,
        unsigned __int16 **a2,
        WCHAR *a3,
        WCHAR *a4,
        unsigned __int16 *const a5)
{
  unsigned int v6; // edi
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // r9d
  int SingleValueStrAttribute; // eax
  struct ldapmodW **v14; // r9
  struct ldapmodW **v15; // r9

  v6 = 0;
  if ( (unsigned int)_o__ultow_s(*((unsigned int *)a2 + 14), a5, 11, 10) )
  {
    v10 = -2147467259;
    v11 = -2147467259;
    v12 = 801;
LABEL_24:
    SidKeyDebugTraceError(v11, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdssrvconfig.cxx", v12);
    DeleteAttrsList(a1, v6);
    return v10;
  }
  if ( (unsigned int)_o__ultow_s(*((unsigned int *)a2 + 13), a5 + 11, 11, 10) )
  {
    v10 = -2147467259;
    v11 = -2147467259;
    v12 = 809;
    goto LABEL_24;
  }
  SingleValueStrAttribute = GenerateSingleValueStrAttribute(2u, L"msKds-KDFAlgorithmID", a2[1], a1);
  v10 = SingleValueStrAttribute;
  if ( SingleValueStrAttribute < 0 )
  {
    v12 = 820;
LABEL_23:
    v11 = SingleValueStrAttribute;
    goto LABEL_24;
  }
  SingleValueStrAttribute = GenerateSingleValueStrAttribute(2u, L"msKds-SecretAgreementAlgorithmID", a2[4], a1 + 1);
  v10 = SingleValueStrAttribute;
  if ( SingleValueStrAttribute < 0 )
  {
    v6 = 1;
    v12 = 833;
    goto LABEL_23;
  }
  SingleValueStrAttribute = GenerateSingleValueStrAttribute(2u, L"msKds-PublicKeyLength", a5, a1 + 2);
  v10 = SingleValueStrAttribute;
  if ( SingleValueStrAttribute < 0 )
  {
    v6 = 2;
    v12 = 846;
    goto LABEL_23;
  }
  SingleValueStrAttribute = GenerateSingleValueStrAttribute(2u, L"msKds-PrivateKeyLength", a5 + 11, a1 + 3);
  v10 = SingleValueStrAttribute;
  if ( SingleValueStrAttribute < 0 )
  {
    v6 = 3;
    v12 = 858;
    goto LABEL_23;
  }
  v14 = a1 + 4;
  v6 = 4;
  if ( *((_QWORD *)a3 + 1) )
  {
    SingleValueStrAttribute = GenerateSingleValueBervalAttribute(2, L"msKds-SecretAgreementParam", a3, v14);
    v10 = SingleValueStrAttribute;
    if ( SingleValueStrAttribute < 0 )
    {
      v12 = 873;
      goto LABEL_23;
    }
  }
  else
  {
    SingleValueStrAttribute = GenerateSingleValueStrAttribute(2u, L"msKds-SecretAgreementParam", 0, v14);
    v10 = SingleValueStrAttribute;
    if ( SingleValueStrAttribute < 0 )
    {
      v12 = 887;
      goto LABEL_23;
    }
  }
  v15 = a1 + 5;
  v6 = 5;
  if ( *((_QWORD *)a4 + 1) )
  {
    SingleValueStrAttribute = GenerateSingleValueBervalAttribute(2, L"msKds-KDFParam", a4, v15);
    v10 = SingleValueStrAttribute;
    if ( SingleValueStrAttribute < 0 )
    {
      v12 = 902;
      goto LABEL_23;
    }
  }
  else
  {
    SingleValueStrAttribute = GenerateSingleValueStrAttribute(2u, L"msKds-KDFParam", 0, v15);
    v10 = SingleValueStrAttribute;
    if ( SingleValueStrAttribute < 0 )
    {
      v12 = 917;
      goto LABEL_23;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180006dbc  push    rbx
0x180006dbe  push    rbp
0x180006dbf  push    rsi
0x180006dc0  push    rdi
0x180006dc1  push    r12
0x180006dc3  push    r13
0x180006dc5  push    r14
0x180006dc7  push    r15
0x180006dc9  sub     rsp, 28h
0x180006dcd  mov     r14, [rsp+68h+arg_20]
0x180006dd5  mov     rbp, rdx
0x180006dd8  xor     edi, edi
0x180006dda  mov     r13, r9
0x180006ddd  mov     r15, r8
0x180006de0  mov     rsi, rcx
0x180006de3  mov     rdx, r14
0x180006de6  mov     ecx, [rbp+38h]
0x180006de9  lea     ebx, [rdi+0Ah]
0x180006dec  mov     r9d, ebx
0x180006def  lea     r8d, [rdi+0Bh]
0x180006df3  call    cs:__imp__o__ultow_s
0x180006df9  test    eax, eax
0x180006dfb  jz      short loc_180006E12
0x180006dfd  mov     ebx, 80004005h
0x180006e02  mov     ecx, 80004005h
0x180006e07  mov     r9d, 321h
0x180006e0d  jmp     loc_180006F77
0x180006e12  mov     ecx, [rbp+34h]
0x180006e15  lea     rdx, [r14+16h]
0x180006e19  mov     r9d, ebx
0x180006e1c  mov     r8d, 0Bh
0x180006e22  call    cs:__imp__o__ultow_s
0x180006e28  test    eax, eax
0x180006e2a  jz      short loc_180006E41
0x180006e2c  mov     ebx, 80004005h
0x180006e31  mov     ecx, 80004005h
0x180006e36  mov     r9d, 329h
0x180006e3c  jmp     loc_180006F77
0x180006e41  mov     r8, [rbp+8]; unsigned __int16 *
0x180006e45  lea     rdx, aMskdsKdfalgori; "msKds-KDFAlgorithmID"
0x180006e4c  mov     r9, rsi; struct ldapmodW **
0x180006e4f  mov     ecx, 2; unsigned int
0x180006e54  call    ?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z; GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)
0x180006e59  mov     ebx, eax
0x180006e5b  test    eax, eax
0x180006e5d  jns     short loc_180006E6A
0x180006e5f  mov     r9d, 334h
0x180006e65  jmp     loc_180006F75
0x180006e6a  mov     r8, [rbp+20h]; unsigned __int16 *
0x180006e6e  lea     r9, [rsi+8]; struct ldapmodW **
0x180006e72  mov     ebp, 2
0x180006e77  lea     rdx, aMskdsSecretagr; "msKds-SecretAgreementAlgorithmID"
0x180006e7e  mov     ecx, ebp; unsigned int
0x180006e80  call    ?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z; GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)
0x180006e85  mov     ebx, eax
0x180006e87  test    eax, eax
0x180006e89  jns     short loc_180006E99
0x180006e8b  lea     edi, [rbp-1]
0x180006e8e  mov     r9d, 341h
0x180006e94  jmp     loc_180006F75
0x180006e99  lea     r9, [rsi+10h]; struct ldapmodW **
0x180006e9d  mov     r8, r14; unsigned __int16 *
0x180006ea0  lea     rdx, aMskdsPublickey; "msKds-PublicKeyLength"
0x180006ea7  mov     ecx, ebp; unsigned int
0x180006ea9  call    ?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z; GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)
0x180006eae  mov     ebx, eax
0x180006eb0  test    eax, eax
0x180006eb2  jns     short loc_180006EC1
0x180006eb4  mov     edi, ebp
0x180006eb6  mov     r9d, 34Eh
0x180006ebc  jmp     loc_180006F75
0x180006ec1  lea     r9, [rsi+18h]; struct ldapmodW **
0x180006ec5  mov     ecx, ebp; unsigned int
0x180006ec7  lea     r8, [r14+16h]; unsigned __int16 *
0x180006ecb  lea     rdx, aMskdsPrivateke; "msKds-PrivateKeyLength"
0x180006ed2  call    ?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z; GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)
0x180006ed7  mov     ebx, eax
0x180006ed9  test    eax, eax
0x180006edb  jns     short loc_180006EED
0x180006edd  mov     edi, 3
0x180006ee2  mov     r9d, 35Ah
0x180006ee8  jmp     loc_180006F75
0x180006eed  cmp     qword ptr [r15+8], 0
0x180006ef2  lea     r9, [rsi+20h]; struct ldapmodW **
0x180006ef6  mov     edi, 4
0x180006efb  lea     rdx, aMskdsSecretagr_0; "msKds-SecretAgreementParam"
0x180006f02  mov     ecx, ebp; unsigned int
0x180006f04  jz      short loc_180006F1C
0x180006f06  mov     r8, r15; struct berval *
0x180006f09  call    ?GenerateSingleValueBervalAttribute@@YAJKPEAGPEAUberval@@PEAPEAUldapmodW@@@Z; GenerateSingleValueBervalAttribute(ulong,ushort *,berval *,ldapmodW * *)
0x180006f0e  mov     ebx, eax
0x180006f10  test    eax, eax
0x180006f12  jns     short loc_180006F32
0x180006f14  mov     r9d, 369h
0x180006f1a  jmp     short loc_180006F75
0x180006f1c  xor     r8d, r8d; unsigned __int16 *
0x180006f1f  call    ?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z; GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)
0x180006f24  mov     ebx, eax
0x180006f26  test    eax, eax
0x180006f28  jns     short loc_180006F32
0x180006f2a  mov     r9d, 377h
0x180006f30  jmp     short loc_180006F75
0x180006f32  cmp     qword ptr [r13+8], 0
0x180006f37  lea     r9, [rsi+28h]; struct ldapmodW **
0x180006f3b  mov     edi, 5
0x180006f40  lea     rdx, aMskdsKdfparam; "msKds-KDFParam"
0x180006f47  mov     ecx, ebp; unsigned int
0x180006f49  jz      short loc_180006F61
0x180006f4b  mov     r8, r13; struct berval *
0x180006f4e  call    ?GenerateSingleValueBervalAttribute@@YAJKPEAGPEAUberval@@PEAPEAUldapmodW@@@Z; GenerateSingleValueBervalAttribute(ulong,ushort *,berval *,ldapmodW * *)
0x180006f53  mov     ebx, eax
0x180006f55  test    eax, eax
0x180006f57  jns     short loc_180006F94
0x180006f59  mov     r9d, 386h
0x180006f5f  jmp     short loc_180006F75
0x180006f61  xor     r8d, r8d; unsigned __int16 *
0x180006f64  call    ?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z; GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)
0x180006f69  mov     ebx, eax
0x180006f6b  test    eax, eax
0x180006f6d  jns     short loc_180006F94
0x180006f6f  mov     r9d, 395h; unsigned int
0x180006f75  mov     ecx, eax; unsigned int
0x180006f77  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180006f7e  lea     rdx, aHr; "hr"
0x180006f85  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180006f8a  mov     edx, edi; unsigned int
0x180006f8c  mov     rcx, rsi; struct ldapmodW **
0x180006f8f  call    ?DeleteAttrsList@@YAXPEAPEAUldapmodW@@K@Z; DeleteAttrsList(ldapmodW * *,ulong)
0x180006f94  mov     eax, ebx
0x180006f96  add     rsp, 28h
0x180006f9a  pop     r15
0x180006f9c  pop     r14
0x180006f9e  pop     r13
0x180006fa0  pop     r12
0x180006fa2  pop     rdi
0x180006fa3  pop     rsi
0x180006fa4  pop     rbp
0x180006fa5  pop     rbx
0x180006fa6  retn
```
