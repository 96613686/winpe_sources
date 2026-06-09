# I_CryptXmlDecodeKeyInfo

- ea: `0x180016820`
- end: `0x180016a05`
- name: `I_CryptXmlDecodeKeyInfo`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x180006da0`
- `0x1800070d0`
- `0x180011040`
- `0x180012d90`
- `0x180014ce0`
- `0x1800164cc`
- `0x180016820`

## import_xrefs

- `webservices!WsReadElement` at `0x180016943`
- `webservices!WsReadElement` at `0x180016943`
- `webservices!WsSetInput` at `0x1800168f8`
- `webservices!WsSetInput` at `0x1800168f8`

## string_xrefs

- `0x1800169bf`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_CryptXmlDecodeKeyInfo(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  WS_ERROR **v4; // rdi
  __int64 v8; // rax
  int v9; // ebx
  unsigned int v10; // r15d
  struct WS_TYPE_KeyInfo *v11; // rcx
  const char *v12; // rax
  const char *v13; // r10
  int v14; // edx
  WS_XML_READER_INPUT input[4]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  __int64 encoding; // [rsp+A0h] [rbp+40h] BYREF
  __int64 value; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v20; // [rsp+B0h] [rbp+50h] BYREF

  v20 = a3;
  v4 = *(WS_ERROR ***)(a1 + 152);
  v17 = 0;
  encoding = 0;
  value = 0;
  v20 = 0;
  v8 = *(_QWORD *)(a2 + 144);
  *(_OWORD *)&input[0].inputType = 0;
  if ( *(_QWORD *)(v8 + 152) )
  {
    v9 = -2146885369;
    goto LABEL_11;
  }
  I_GetProperty(1, *(_QWORD *)(a1 + 168), *(unsigned int *)(a1 + 176), &v20, 4);
  v10 = v20;
  *(_QWORD *)&input[0].inputType = 1;
  HIDWORD(v17) = 0;
  LODWORD(encoding) = 1;
  if ( !v20 )
    v10 = 2147483640;
  HIDWORD(encoding) = *(_DWORD *)a4;
  *(_QWORD *)&input[2].inputType = *(_QWORD *)(a4 + 8);
  LODWORD(v17) = *(_DWORD *)(a4 + 4);
  v9 = WsSetInput(v4[1], (const WS_XML_READER_ENCODING *)&encoding, input, 0, 0, *v4);
  if ( v9 < 0 )
    goto LABEL_11;
  v9 = WsReadElement(v4[1], &KeyInfo_ElementDescription, WS_READ_REQUIRED_POINTER, v4[6], &value, 8u, *v4);
  if ( v9 < 0 )
    goto LABEL_11;
  v11 = (struct WS_TYPE_KeyInfo *)value;
  if ( *(_DWORD *)value )
  {
    v9 = I_CryptXmlCheckUniqueId(a1, *(const WCHAR **)(value + 8), *(_DWORD *)value, 1);
    if ( v9 < 0 )
      goto LABEL_11;
    v11 = (struct WS_TYPE_KeyInfo *)value;
  }
  v9 = I_XmlUnmarshallKeyInfo(
         *(HANDLE *)(a2 + 48),
         WS_CHARSET_UTF8,
         v10,
         v11,
         v4,
         (struct _CRYPT_XML_KEY_INFO **)(*(_QWORD *)(a2 + 144) + 152LL));
  if ( v9 >= 0 )
    return 0;
LABEL_11:
  v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
  WPPTraceLogA(v13, (unsigned int)v9, v12);
  if ( *v4 )
    I_TraceWsError(*v4, v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016820  mov     [rsp-38h+arg_10], r8d
0x180016825  push    rbp
0x180016826  push    rbx
0x180016827  push    rsi
0x180016828  push    rdi
0x180016829  push    r13
0x18001682b  push    r14
0x18001682d  push    r15
0x18001682f  mov     rbp, rsp
0x180016832  sub     rsp, 60h
0x180016836  mov     rdi, [rcx+98h]
0x18001683d  xor     eax, eax
0x18001683f  mov     [rbp+var_10], rax
0x180016843  xorps   xmm0, xmm0
0x180016846  mov     [rbp+encoding], rax
0x18001684a  mov     rbx, r9
0x18001684d  mov     [rbp+value], rax
0x180016851  mov     rsi, rdx
0x180016854  mov     [rbp+arg_10], eax
0x180016857  mov     r14, rcx
0x18001685a  mov     rax, [rdx+90h]
0x180016861  movups  xmmword ptr [rbp+input.inputType], xmm0
0x180016865  cmp     qword ptr [rax+98h], 0
0x18001686d  jz      short loc_18001687F
0x18001686f  mov     ebx, 80092107h
0x180016874  mov     r9d, 856h
0x18001687a  jmp     loc_1800169BF
0x18001687f  mov     r8d, [rcx+0B0h]
0x180016886  lea     r9, [rbp+arg_10]
0x18001688a  mov     rdx, [rcx+0A8h]
0x180016891  mov     r13d, 1
0x180016897  mov     ecx, r13d
0x18001689a  mov     [rsp+60h+propertyCount], 4
0x1800168a2  call    I_GetProperty
0x1800168a7  mov     r15d, [rbp+arg_10]
0x1800168ab  lea     r8, [rbp+input]; input
0x1800168af  mov     eax, 7FFFFFF8h
0x1800168b4  mov     qword ptr [rbp+input.inputType], r13
0x1800168b8  mov     dword ptr [rbp+var_10+4], 0
0x1800168bf  lea     rdx, [rbp+encoding]; encoding
0x1800168c3  mov     dword ptr [rbp+encoding], r13d
0x1800168c7  test    r15d, r15d
0x1800168ca  cmovz   r15d, eax
0x1800168ce  mov     eax, [rbx]
0x1800168d0  mov     dword ptr [rbp+encoding+4], eax
0x1800168d3  xor     r9d, r9d; properties
0x1800168d6  mov     rax, [rbx+8]
0x1800168da  mov     qword ptr [rbp+input.inputType+8], rax
0x1800168de  mov     eax, [rbx+4]
0x1800168e1  mov     dword ptr [rbp+var_10], eax
0x1800168e4  mov     rax, [rdi]
0x1800168e7  mov     rcx, [rdi+8]; reader
0x1800168eb  mov     [rsp+60h+error], rax; error
0x1800168f0  mov     [rsp+60h+propertyCount], 0; propertyCount
0x1800168f8  call    cs:__imp_WsSetInput
0x1800168ff  nop     dword ptr [rax+rax+00h]
0x180016904  mov     ebx, eax
0x180016906  test    eax, eax
0x180016908  jns     short loc_180016915
0x18001690a  mov     r9d, 884h
0x180016910  jmp     loc_1800169BF
0x180016915  mov     rax, [rdi]
0x180016918  lea     rdx, ?KeyInfo_ElementDescription@@3U_WS_ELEMENT_DESCRIPTION@@B; elementDescription
0x18001691f  mov     r9, [rdi+30h]; heap
0x180016923  mov     r8d, 2; readOption
0x180016929  mov     rcx, [rdi+8]; reader
0x18001692d  mov     [rsp+60h+var_30], rax; error
0x180016932  lea     rax, [rbp+value]
0x180016936  mov     dword ptr [rsp+60h+error], 8; valueSize
0x18001693e  mov     qword ptr [rsp+60h+propertyCount], rax; value
0x180016943  call    cs:__imp_WsReadElement
0x18001694a  nop     dword ptr [rax+rax+00h]
0x18001694f  mov     ebx, eax
0x180016951  test    eax, eax
0x180016953  jns     short loc_18001695D
0x180016955  mov     r9d, 893h
0x18001695b  jmp     short loc_1800169BF
0x18001695d  mov     rcx, [rbp+value]
0x180016961  mov     r8d, [rcx]
0x180016964  test    r8d, r8d
0x180016967  jz      short loc_18001698A
0x180016969  mov     rdx, [rcx+8]
0x18001696d  mov     r9d, r13d
0x180016970  mov     rcx, r14
0x180016973  call    I_CryptXmlCheckUniqueId
0x180016978  mov     ebx, eax
0x18001697a  test    eax, eax
0x18001697c  jns     short loc_180016986
0x18001697e  mov     r9d, 8A1h
0x180016984  jmp     short loc_1800169BF
0x180016986  mov     rcx, [rbp+value]
0x18001698a  mov     rax, [rsi+90h]
0x180016991  mov     r9, rcx; struct WS_TYPE_KeyInfo *
0x180016994  mov     rcx, [rsi+30h]; hHeap
0x180016998  add     rax, 98h
0x18001699e  mov     [rsp+60h+error], rax; struct _CRYPT_XML_KEY_INFO **
0x1800169a3  mov     r8d, r15d; unsigned int
0x1800169a6  mov     edx, r13d; enum WS_CHARSET
0x1800169a9  mov     qword ptr [rsp+60h+propertyCount], rdi; struct _CRYPT_XML_WS_STATE *
0x1800169ae  call    ?I_XmlUnmarshallKeyInfo@@YAJPEAXW4WS_CHARSET@@KPEAUWS_TYPE_KeyInfo@@PEAU_CRYPT_XML_WS_STATE@@PEAPEAU_CRYPT_XML_KEY_INFO@@@Z; I_XmlUnmarshallKeyInfo(void *,WS_CHARSET,ulong,WS_TYPE_KeyInfo *,_CRYPT_XML_WS_STATE *,_CRYPT_XML_KEY_INFO * *)
0x1800169b3  mov     ebx, eax
0x1800169b5  test    eax, eax
0x1800169b7  jns     short loc_1800169F1
0x1800169b9  mov     r9d, 8B5h
0x1800169bf  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800169c6  mov     r11d, ebx
0x1800169c9  lea     r10, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800169d0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800169d5  mov     r8, rax
0x1800169d8  mov     edx, ebx
0x1800169da  mov     rcx, r10; char *
0x1800169dd  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800169e2  mov     rcx, [rdi]; error
0x1800169e5  test    rcx, rcx
0x1800169e8  jz      short loc_1800169F3
0x1800169ea  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x1800169ef  jmp     short loc_1800169F3
0x1800169f1  xor     ebx, ebx
0x1800169f3  mov     eax, ebx
0x1800169f5  add     rsp, 60h
0x1800169f9  pop     r15
0x1800169fb  pop     r14
0x1800169fd  pop     r13
0x1800169ff  pop     rdi
0x180016a00  pop     rsi
0x180016a01  pop     rbx
0x180016a02  pop     rbp
0x180016a03  retn
```
