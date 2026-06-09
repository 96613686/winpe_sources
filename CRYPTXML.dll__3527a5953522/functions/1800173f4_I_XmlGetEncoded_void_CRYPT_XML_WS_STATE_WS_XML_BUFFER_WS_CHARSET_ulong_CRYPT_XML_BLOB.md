# I_XmlGetEncoded(void *,_CRYPT_XML_WS_STATE *,_WS_XML_BUFFER *,WS_CHARSET,ulong,_CRYPT_XML_BLOB *)

- ea: `0x1800173f4`
- end: `0x1800176c9`
- name: `?I_XmlGetEncoded@@YAJPEAXPEAU_CRYPT_XML_WS_STATE@@PEAU_WS_XML_BUFFER@@W4WS_CHARSET@@KPEAU_CRYPT_XML_BLOB@@@Z`
- size: `725`
- prototype: `__int64 __usercall@<rax>(HANDLE hHeap@<rcx>, struct _CRYPT_XML_WS_STATE *@<rdx>, struct _WS_XML_BUFFER *@<r8>, enum WS_CHARSET@<r9d>, unsigned int, struct _CRYPT_XML_BLOB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012d90`

## callees

- `0x1800070d0`
- `0x180014ce0`
- `0x1800173f4`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017620`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017620`
- `webservices!WsCopyNode` at `0x180017525`
- `webservices!WsCopyNode` at `0x180017525`
- `webservices!WsFlushWriter` at `0x18001755a`
- `webservices!WsFlushWriter` at `0x18001755a`
- `webservices!WsGetReaderNode` at `0x1800174f6`
- `webservices!WsGetReaderNode` at `0x1800174f6`
- `webservices!WsGetWriterProperty` at `0x1800175a4`
- `webservices!WsGetWriterProperty` at `0x1800175a4`
- `webservices!WsSetOutput` at `0x1800174ba`
- `webservices!WsSetOutput` at `0x1800174ba`
- `webservices!WsSetInputToBuffer` at `0x180017466`
- `webservices!WsSetInputToBuffer` at `0x180017466`

## string_xrefs

- `0x180017478`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800174cc`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017537`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18001756c`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800175b6`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x1800175f3`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180017635`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x18001768a`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlGetEncoded(
        HANDLE hHeap,
        WS_ERROR **a2,
        struct _WS_XML_BUFFER *a3,
        CRYPT_XML_CHARSET a4,
        unsigned int a5,
        struct _CRYPT_XML_BLOB *encoding)
{
  struct _CRYPT_XML_BLOB *v6; // r14
  bool v7; // zf
  ULONG v10; // esi
  WS_ERROR *v11; // rax
  WS_XML_READER *v13; // rcx
  HRESULT ReaderNode; // ebx
  const char *v15; // rax
  int v16; // r9d
  WS_XML_WRITER *v17; // rcx
  WS_ERROR *v18; // r8
  WS_XML_READER *v19; // rcx
  WS_XML_WRITER *v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned int i; // edx
  BYTE *v23; // rax
  __int64 v24; // rsi
  unsigned int v25; // edi
  __int64 v26; // rdx
  __int64 v27; // rbx
  WS_ERROR *error; // [rsp+20h] [rbp-40h]
  __int128 value; // [rsp+30h] [rbp-30h] BYREF
  WS_XML_WRITER_PROPERTY properties; // [rsp+40h] [rbp-20h] BYREF
  WS_XML_NODE *node; // [rsp+98h] [rbp+38h] BYREF
  WS_XML_WRITER_OUTPUT output; // [rsp+A8h] [rbp+48h] BYREF

  v6 = encoding;
  properties.value = &a5;
  v7 = a5 == 0;
  properties.id = WS_XML_WRITER_PROPERTY_BUFFER_MAX_SIZE;
  encoding->dwCharset = a4;
  v6->pbData = 0;
  v10 = !v7;
  v6->cbData = 0;
  v11 = *a2;
  v13 = a2[1];
  properties.valueSize = 4;
  ReaderNode = WsSetInputToBuffer(v13, a3, 0, 0, v11);
  if ( ReaderNode < 0 )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v16 = 356;
LABEL_27:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", ReaderNode, v15, v16);
    return (unsigned int)ReaderNode;
  }
  v17 = a2[2];
  HIDWORD(encoding) = a4;
  output.outputType = WS_XML_WRITER_OUTPUT_TYPE_BUFFER;
  LODWORD(encoding) = 1;
  ReaderNode = WsSetOutput(v17, (const WS_XML_WRITER_ENCODING *)&encoding, &output, &properties, v10, *a2);
  if ( ReaderNode < 0 )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v16 = 379;
    goto LABEL_27;
  }
  while ( 1 )
  {
    v18 = *a2;
    v19 = a2[1];
    node = 0;
    ReaderNode = WsGetReaderNode(v19, (const WS_XML_NODE **)&node, v18);
    if ( ReaderNode < 0 )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v16 = 397;
      goto LABEL_27;
    }
    if ( node->nodeType == WS_XML_NODE_TYPE_END_ELEMENT || node->nodeType == WS_XML_NODE_TYPE_EOF )
      break;
    ReaderNode = WsCopyNode(a2[2], a2[1], *a2);
    if ( ReaderNode < 0 )
    {
      v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v16 = 414;
      goto LABEL_27;
    }
  }
  ReaderNode = WsFlushWriter(a2[2], 0, 0, *a2);
  if ( ReaderNode < 0 )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v16 = 431;
    goto LABEL_27;
  }
  v20 = a2[2];
  error = *a2;
  value = 0;
  ReaderNode = WsGetWriterProperty(v20, WS_XML_WRITER_PROPERTY_BUFFERS, &value, 0x10u, error);
  if ( ReaderNode < 0 )
  {
    v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v16 = 449;
    goto LABEL_27;
  }
  v21 = 0;
  for ( i = 0; i < (unsigned int)value; ++i )
  {
    v21 += *(unsigned int *)(*((_QWORD *)&value + 1) + 16LL * i);
    if ( v21 > 0x7FFFFFF8 )
    {
      ReaderNode = -2146885375;
      v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v16 = 459;
      goto LABEL_27;
    }
  }
  if ( v21 )
  {
    v6->cbData = v21;
    v23 = (BYTE *)HeapAlloc(hHeap, 0, (unsigned int)v21);
    v6->pbData = v23;
    if ( !v23 )
    {
      ReaderNode = -2147024882;
      v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
      v16 = 474;
      goto LABEL_27;
    }
    v24 = 0;
    v25 = 0;
    if ( (_DWORD)value )
    {
      v26 = *((_QWORD *)&value + 1);
      do
      {
        v27 = 2LL * v25;
        memcpy_0(&v6->pbData[v24], *(const void **)(v26 + 16LL * v25 + 8), *(unsigned int *)(v26 + 16LL * v25));
        v26 = *((_QWORD *)&value + 1);
        ++v25;
        v24 += *(unsigned int *)(*((_QWORD *)&value + 1) + 8 * v27);
      }
      while ( v25 < (unsigned int)value );
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800173f4  mov     [rsp-28h+arg_0], rbx
0x1800173f9  mov     [rsp-28h+arg_10], rsi
0x1800173fe  push    rbp
0x1800173ff  push    rdi
0x180017400  push    r12
0x180017402  push    r14
0x180017404  push    r15
0x180017406  mov     rbp, rsp
0x180017409  sub     rsp, 60h
0x18001740d  mov     r14, qword ptr [rbp+encoding.encodingType]
0x180017411  lea     rax, [rbp+arg_20]
0x180017415  xor     esi, esi
0x180017417  mov     [rbp+properties.value], rax
0x18001741b  cmp     [rbp+arg_20], esi
0x18001741e  mov     rdi, rdx
0x180017421  mov     r10, r8
0x180017424  mov     [rbp+properties.id], 8
0x18001742b  mov     [r14], r9d
0x18001742e  mov     r15d, r9d
0x180017431  mov     qword ptr [r14+8], 0
0x180017439  lea     eax, [rsi+1]
0x18001743c  cmova   esi, eax
0x18001743f  mov     dword ptr [r14+4], 0
0x180017447  mov     rax, [rdx]
0x18001744a  mov     r12, rcx
0x18001744d  mov     rcx, [rdi+8]; reader
0x180017451  mov     rdx, r10; buffer
0x180017454  xor     r9d, r9d; propertyCount
0x180017457  mov     [rsp+60h+error], rax; error
0x18001745c  xor     r8d, r8d; properties
0x18001745f  mov     [rbp+properties.valueSize], 4
0x180017466  call    cs:__imp_WsSetInputToBuffer
0x18001746d  nop     dword ptr [rax+rax+00h]
0x180017472  mov     ebx, eax
0x180017474  test    eax, eax
0x180017476  jns     short loc_18001748F
0x180017478  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001747f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017484  mov     r9d, 164h
0x18001748a  jmp     loc_18001769C
0x18001748f  mov     rcx, [rdi+10h]; writer
0x180017493  lea     r9, [rbp+properties]; properties
0x180017497  mov     eax, 1
0x18001749c  mov     [rbp+5Ch], r15d
0x1800174a0  mov     [rbp+output.outputType], eax
0x1800174a3  lea     r8, [rbp+output]; output
0x1800174a7  mov     [rbp+encoding.encodingType], eax
0x1800174aa  lea     rdx, [rbp+encoding]; encoding
0x1800174ae  mov     rax, [rdi]
0x1800174b1  mov     [rsp+60h+var_38], rax; error
0x1800174b6  mov     dword ptr [rsp+60h+error], esi; propertyCount
0x1800174ba  call    cs:__imp_WsSetOutput
0x1800174c1  nop     dword ptr [rax+rax+00h]
0x1800174c6  mov     ebx, eax
0x1800174c8  test    eax, eax
0x1800174ca  jns     short loc_1800174E3
0x1800174cc  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800174d3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800174d8  mov     r9d, 17Bh
0x1800174de  jmp     loc_18001769C
0x1800174e3  mov     r8, [rdi]; error
0x1800174e6  lea     rdx, [rbp+node]; node
0x1800174ea  mov     rcx, [rdi+8]; xmlReader
0x1800174ee  mov     [rbp+node], 0
0x1800174f6  call    cs:__imp_WsGetReaderNode
0x1800174fd  nop     dword ptr [rax+rax+00h]
0x180017502  mov     ebx, eax
0x180017504  test    eax, eax
0x180017506  js      loc_18001768A
0x18001750c  mov     rax, [rbp+node]
0x180017510  cmp     dword ptr [rax], 3
0x180017513  jz      short loc_18001754E
0x180017515  cmp     dword ptr [rax], 8
0x180017518  jz      short loc_18001754E
0x18001751a  mov     r8, [rdi]; error
0x18001751d  mov     rdx, [rdi+8]; reader
0x180017521  mov     rcx, [rdi+10h]; writer
0x180017525  call    cs:__imp_WsCopyNode
0x18001752c  nop     dword ptr [rax+rax+00h]
0x180017531  mov     ebx, eax
0x180017533  test    eax, eax
0x180017535  jns     short loc_1800174E3
0x180017537  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001753e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017543  mov     r9d, 19Eh
0x180017549  jmp     loc_18001769C
0x18001754e  mov     r9, [rdi]; error
0x180017551  xor     r8d, r8d; asyncContext
0x180017554  mov     rcx, [rdi+10h]; writer
0x180017558  xor     edx, edx; minSize
0x18001755a  call    cs:__imp_WsFlushWriter
0x180017561  nop     dword ptr [rax+rax+00h]
0x180017566  mov     ebx, eax
0x180017568  test    eax, eax
0x18001756a  jns     short loc_180017583
0x18001756c  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017573  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017578  mov     r9d, 1AFh
0x18001757e  jmp     loc_18001769C
0x180017583  mov     rax, [rdi]
0x180017586  lea     r8, [rbp+value]; value
0x18001758a  mov     rcx, [rdi+10h]; writer
0x18001758e  mov     r9d, 10h; valueSize
0x180017594  xorps   xmm0, xmm0
0x180017597  mov     [rsp+60h+error], rax; error
0x18001759c  movups  [rbp+value], xmm0
0x1800175a0  lea     edx, [r9-9]; id
0x1800175a4  call    cs:__imp_WsGetWriterProperty
0x1800175ab  nop     dword ptr [rax+rax+00h]
0x1800175b0  mov     ebx, eax
0x1800175b2  test    eax, eax
0x1800175b4  jns     short loc_1800175CD
0x1800175b6  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800175bd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800175c2  mov     r9d, 1C1h
0x1800175c8  jmp     loc_18001769C
0x1800175cd  mov     r8, qword ptr [rbp+value+8]
0x1800175d1  xor     ecx, ecx
0x1800175d3  xor     edx, edx
0x1800175d5  cmp     edx, dword ptr [rbp+value]
0x1800175d8  jnb     short loc_18001760F
0x1800175da  mov     eax, edx
0x1800175dc  add     rax, rax
0x1800175df  mov     eax, [r8+rax*8]
0x1800175e3  add     rcx, rax
0x1800175e6  cmp     rcx, 7FFFFFF8h
0x1800175ed  ja      short loc_1800175F3
0x1800175ef  inc     edx
0x1800175f1  jmp     short loc_1800175D5
0x1800175f3  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800175fa  mov     ebx, 80092101h
0x1800175ff  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017604  mov     r9d, 1CBh
0x18001760a  jmp     loc_18001769C
0x18001760f  test    rcx, rcx
0x180017612  jz      short loc_180017686
0x180017614  mov     r8d, ecx; dwBytes
0x180017617  xor     edx, edx; dwFlags
0x180017619  mov     rcx, r12; hHeap
0x18001761c  mov     [r14+4], r8d
0x180017620  call    cs:__imp_HeapAlloc
0x180017627  nop     dword ptr [rax+rax+00h]
0x18001762c  mov     [r14+8], rax
0x180017630  test    rax, rax
0x180017633  jnz     short loc_18001764E
0x180017635  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18001763c  mov     ebx, 8007000Eh
0x180017641  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017646  mov     r9d, 1DAh
0x18001764c  jmp     short loc_18001769C
0x18001764e  xor     esi, esi
0x180017650  xor     edi, edi
0x180017652  cmp     dword ptr [rbp+value], esi
0x180017655  jbe     short loc_180017686
0x180017657  mov     rdx, qword ptr [rbp+value+8]
0x18001765b  mov     rcx, [r14+8]
0x18001765f  mov     ebx, edi
0x180017661  add     rcx, rsi; void *
0x180017664  add     rbx, rbx
0x180017667  mov     r8d, [rdx+rbx*8]; Size
0x18001766b  mov     rdx, [rdx+rbx*8+8]; Src
0x180017670  call    memcpy_0
0x180017675  mov     rdx, qword ptr [rbp+value+8]
0x180017679  inc     edi
0x18001767b  mov     eax, [rdx+rbx*8]
0x18001767e  add     rsi, rax
0x180017681  cmp     edi, dword ptr [rbp+value]
0x180017684  jb      short loc_18001765B
0x180017686  xor     ebx, ebx
0x180017688  jmp     short loc_1800176AD
0x18001768a  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180017691  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180017696  mov     r9d, 18Dh
0x18001769c  mov     r8, rax
0x18001769f  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800176a6  mov     edx, ebx
0x1800176a8  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x1800176ad  lea     r11, [rsp+60h+var_s0]
0x1800176b2  mov     eax, ebx
0x1800176b4  mov     rbx, [r11+30h]
0x1800176b8  mov     rsi, [r11+40h]
0x1800176bc  mov     rsp, r11
0x1800176bf  pop     r15
0x1800176c1  pop     r14
0x1800176c3  pop     r12
0x1800176c5  pop     rdi
0x1800176c6  pop     rbp
0x1800176c7  retn
```
