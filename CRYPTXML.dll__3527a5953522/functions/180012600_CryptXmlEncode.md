# CryptXmlEncode

- ea: `0x180012600`
- end: `0x180012831`
- name: `CryptXmlEncode`
- size: `561`
- prototype: `HRESULT __stdcall(HCRYPTXML hCryptXml, CRYPT_XML_CHARSET dwCharset, const CRYPT_XML_PROPERTY *rgProperty, ULONG cProperty, void *pvCallbackState, PFN_CRYPT_XML_WRITE_CALLBACK pfnWrite)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180009478`
- `0x1800109c0`
- `0x180011040`
- `0x180012600`
- `0x180012b24`
- `0x180014ce0`
- `0x1800164cc`
- `0x180019010`

## string_xrefs

- `0x180012698`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800126e6`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x18001278c`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800127b2`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
HRESULT __stdcall CryptXmlEncode(
        HCRYPTXML hCryptXml,
        CRYPT_XML_CHARSET dwCharset,
        const CRYPT_XML_PROPERTY *rgProperty,
        ULONG cProperty,
        void *pvCallbackState,
        PFN_CRYPT_XML_WRITE_CALLBACK pfnWrite)
{
  PFN_CRYPT_XML_WRITE_CALLBACK v9; // rdi
  int v10; // r10d
  const char *v11; // rax
  HRESULT v12; // edi
  const char *v13; // rdx
  bool v14; // zf
  int v15; // r9d
  __int64 DocCtxt; // rax
  __int64 v17; // rbx
  __int64 v18; // r8
  WS_XML_NODE *v19; // rsi
  const char *v20; // rax
  const char *v21; // r10
  __int64 v22; // r9
  const char *v23; // rdx
  int v24; // edx
  void (__fastcall *v25)(__int64); // rax
  int v27; // [rsp+30h] [rbp-40h] BYREF
  WS_XML_WRITER_PROPERTY v28; // [rsp+38h] [rbp-38h] BYREF
  int v29; // [rsp+50h] [rbp-20h]
  int *v30; // [rsp+58h] [rbp-18h]
  int v31; // [rsp+60h] [rbp-10h]
  int v32; // [rsp+A0h] [rbp+30h] BYREF

  v32 = 2147483640;
  v28.value = &v27;
  v27 = 1;
  v30 = &v32;
  v28.id = WS_XML_WRITER_PROPERTY_WRITE_DECLARATION;
  v28.valueSize = 4;
  v29 = 8;
  v31 = 4;
  if ( hCryptXml && (v9 = pfnWrite) != 0 && (!cProperty || rgProperty) )
  {
    if ( *(_DWORD *)hCryptXml != 1145324610 )
    {
      v10 = -2146885370;
      v11 = "";
      v12 = -2146885370;
      while ( 1 )
      {
        v13 = v11--;
        v14 = *v11 == 92;
        if ( *v11 == 92 )
          break;
        if ( v11 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
        {
          v14 = *v11 == 92;
          break;
        }
      }
      if ( v14 )
        v11 = v13;
      v15 = 2896;
      goto LABEL_13;
    }
    DocCtxt = I_CryptXmlGetDocCtxt(hCryptXml, dwCharset, rgProperty);
    v17 = DocCtxt;
    if ( !DocCtxt )
    {
      v12 = -2146885370;
      v11 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      v15 = 2905;
LABEL_13:
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v10, v11, v15);
      return v12;
    }
    I_CryptXmlLock(DocCtxt);
    I_GetProperty(4, rgProperty, cProperty, &v27, 4);
    if ( (unsigned int)I_GetProperty(1, rgProperty, cProperty, &v32, 4)
      && (unsigned int)I_GetProperty(1, *(_QWORD *)(v17 + 168), *(unsigned int *)(v17 + 176), &v32, 4) )
    {
      v32 = 2147483640;
    }
    v19 = *(WS_XML_NODE **)(v17 + 152);
    v12 = I_XmlEncodeFromBuffer(dwCharset, &v28, v18, (__int64)pvCallbackState, (__int64)v9, v19);
    if ( v12 >= 0 )
      goto LABEL_29;
    v20 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    v22 = 2951;
  }
  else
  {
    v17 = 0;
    v20 = "";
    v19 = 0;
    v12 = -2147024809;
    do
      v23 = v20--;
    while ( *v20 != 92 && v20 > "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" );
    v21 = "ERROR  : (0x%08x) %s:%u";
    v22 = 2889;
    if ( *v20 == 92 )
      v20 = v23;
  }
  WPPTraceLogA(v21, (unsigned int)v12, v20, v22);
  if ( v19 )
    I_TraceWsError(*(struct _WS_ERROR **)&v19->nodeType, v24);
  if ( v17 )
  {
LABEL_29:
    v25 = *(void (__fastcall **)(__int64))(v17 + 128);
    if ( v25 )
      v25(v17);
  }
  return v12;
}

```

## disassembly

```asm
0x180012600  mov     [rsp-28h+arg_8], rbx
0x180012605  mov     [rsp-28h+arg_10], rsi
0x18001260a  push    rbp
0x18001260b  push    rdi
0x18001260c  push    r12
0x18001260e  push    r14
0x180012610  push    r15
0x180012612  mov     rbp, rsp
0x180012615  sub     rsp, 70h
0x180012619  mov     [rbp+arg_0], 7FFFFFF8h
0x180012620  lea     rax, [rbp+var_40]
0x180012624  mov     [rbp+var_30], rax
0x180012628  mov     r12d, 4
0x18001262e  mov     [rbp+var_40], 1
0x180012635  lea     rax, [rbp+arg_0]
0x180012639  mov     [rbp+var_18], rax
0x18001263d  mov     esi, r9d
0x180012640  mov     [rbp+var_38], 3
0x180012647  mov     r14, r8
0x18001264a  mov     [rbp+var_28], r12d
0x18001264e  mov     r15d, edx
0x180012651  mov     [rbp+var_20], 8
0x180012658  mov     [rbp+var_10], r12d
0x18001265c  test    rcx, rcx
0x18001265f  jz      loc_1800127A7
0x180012665  mov     rdi, [rbp+pfnWrite]
0x180012669  test    rdi, rdi
0x18001266c  jz      loc_1800127A7
0x180012672  test    r9d, r9d
0x180012675  jz      short loc_180012680
0x180012677  test    r8, r8
0x18001267a  jz      loc_1800127A7
0x180012680  cmp     dword ptr [rcx], 44444442h
0x180012686  jz      short loc_1800126D3
0x180012688  mov     r10d, 80092106h
0x18001268e  lea     rax, aOnecoreDsSecur_5+30h; ""
0x180012695  mov     edi, r10d
0x180012698  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001269f  mov     rdx, rax
0x1800126a2  dec     rax
0x1800126a5  cmp     byte ptr [rax], 5Ch ; '\'
0x1800126a8  jz      short loc_1800126B2
0x1800126aa  cmp     rax, rcx
0x1800126ad  ja      short loc_18001269F
0x1800126af  cmp     byte ptr [rax], 5Ch ; '\'
0x1800126b2  cmovz   rax, rdx
0x1800126b6  mov     r9d, 0B50h
0x1800126bc  mov     r8, rax
0x1800126bf  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800126c6  mov     edx, r10d
0x1800126c9  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800126ce  jmp     loc_180012815
0x1800126d3  call    I_CryptXmlGetDocCtxt
0x1800126d8  mov     rbx, rax
0x1800126db  test    rax, rax
0x1800126de  jnz     short loc_1800126FD
0x1800126e0  mov     r10d, 80092106h
0x1800126e6  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800126ed  mov     edi, r10d
0x1800126f0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800126f5  mov     r9d, 0B59h
0x1800126fb  jmp     short loc_1800126BC
0x1800126fd  mov     rcx, rbx
0x180012700  call    I_CryptXmlLock
0x180012705  lea     r9, [rbp+var_40]
0x180012709  mov     dword ptr [rsp+70h+var_50], r12d
0x18001270e  mov     r8d, esi
0x180012711  mov     rdx, r14
0x180012714  mov     ecx, r12d
0x180012717  call    I_GetProperty
0x18001271c  lea     r9, [rbp+arg_0]
0x180012720  mov     dword ptr [rsp+70h+var_50], r12d
0x180012725  mov     r8d, esi
0x180012728  mov     rdx, r14
0x18001272b  mov     ecx, 1
0x180012730  call    I_GetProperty
0x180012735  test    eax, eax
0x180012737  jz      short loc_180012765
0x180012739  mov     r8d, [rbx+0B0h]
0x180012740  lea     r9, [rbp+arg_0]
0x180012744  mov     rdx, [rbx+0A8h]
0x18001274b  mov     ecx, 1
0x180012750  mov     dword ptr [rsp+70h+var_50], r12d
0x180012755  call    I_GetProperty
0x18001275a  test    eax, eax
0x18001275c  jz      short loc_180012765
0x18001275e  mov     [rbp+arg_0], 7FFFFFF8h
0x180012765  mov     rsi, [rbx+98h]
0x18001276c  lea     rdx, [rbp+var_38]
0x180012770  mov     r9, [rbp+pvCallbackState]
0x180012774  mov     ecx, r15d
0x180012777  mov     [rsp+70h+var_48], rsi
0x18001277c  mov     [rsp+70h+var_50], rdi
0x180012781  call    I_XmlEncodeFromBuffer
0x180012786  mov     edi, eax
0x180012788  test    eax, eax
0x18001278a  jns     short loc_180012801
0x18001278c  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012793  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18001279a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001279f  mov     r9d, 0B87h
0x1800127a5  jmp     short loc_1800127E2
0x1800127a7  xor     ebx, ebx
0x1800127a9  lea     rax, aOnecoreDsSecur_5+30h; ""
0x1800127b0  xor     esi, esi
0x1800127b2  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800127b9  mov     edi, 80070057h
0x1800127be  mov     rdx, rax
0x1800127c1  dec     rax
0x1800127c4  cmp     byte ptr [rax], 5Ch ; '\'
0x1800127c7  jz      short loc_1800127CE
0x1800127c9  cmp     rax, rcx
0x1800127cc  ja      short loc_1800127BE
0x1800127ce  cmp     byte ptr [rax], 5Ch ; '\'
0x1800127d1  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800127d8  mov     r9d, 0B49h
0x1800127de  cmovz   rax, rdx
0x1800127e2  mov     r8, rax
0x1800127e5  mov     edx, edi
0x1800127e7  mov     rcx, r10; char *
0x1800127ea  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800127ef  test    rsi, rsi
0x1800127f2  jz      short loc_1800127FC
0x1800127f4  mov     rcx, [rsi]; error
0x1800127f7  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x1800127fc  test    rbx, rbx
0x1800127ff  jz      short loc_180012815
0x180012801  mov     rax, [rbx+80h]
0x180012808  test    rax, rax
0x18001280b  jz      short loc_180012815
0x18001280d  mov     rcx, rbx
0x180012810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012815  lea     r11, [rsp+70h+var_s0]
0x18001281a  mov     eax, edi
0x18001281c  mov     rbx, [r11+38h]
0x180012820  mov     rsi, [r11+40h]
0x180012824  mov     rsp, r11
0x180012827  pop     r15
0x180012829  pop     r14
0x18001282b  pop     r12
0x18001282d  pop     rdi
0x18001282e  pop     rbp
0x18001282f  retn
```
