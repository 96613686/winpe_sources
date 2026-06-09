# I_XmlGetEncodedElement(WS_CHARSET,_CRYPT_XML_WS_STATE *,_WS_ELEMENT_DESCRIPTION const *,void const *,ulong,ulong,_CRYPT_XML_BLOB *)

- ea: `0x180001d00`
- end: `0x180001fd4`
- name: `?I_XmlGetEncodedElement@@YAJW4WS_CHARSET@@PEAU_CRYPT_XML_WS_STATE@@PEBU_WS_ELEMENT_DESCRIPTION@@PEBXKKPEAU_CRYPT_XML_BLOB@@@Z`
- size: `724`
- prototype: `int(enum WS_CHARSET, struct _CRYPT_XML_WS_STATE *, const struct _WS_ELEMENT_DESCRIPTION *, const void *, unsigned int, unsigned int, struct _CRYPT_XML_BLOB *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001010`
- `0x180001a40`
- `0x1800029b0`

## callees

- `0x180001d00`
- `0x1800070d0`
- `0x18000b1a0`
- `0x180014ce0`
- `0x1800164cc`
- `0x18001860d`

## import_xrefs

- `webservices!WsFlushWriter` at `0x180001e3f`
- `webservices!WsFlushWriter` at `0x180001e3f`
- `webservices!WsWriteElement` at `0x180001de0`
- `webservices!WsWriteElement` at `0x180001de0`
- `webservices!WsGetWriterProperty` at `0x180001e9d`
- `webservices!WsGetWriterProperty` at `0x180001e9d`
- `webservices!WsSetOutput` at `0x180001d6d`
- `webservices!WsSetOutput` at `0x180001d6d`

## string_xrefs

- `0x180001d86`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180001df9`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180001e51`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180001eb6`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x180001f15`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlGetEncodedElement(
        __int32 a1,
        WS_ERROR **a2,
        const struct _WS_ELEMENT_DESCRIPTION *a3,
        const void *a4,
        ULONG valueSize,
        unsigned int a6,
        struct _CRYPT_XML_BLOB *a7)
{
  WS_ERROR *error; // rax
  WS_XML_WRITER *v12; // rcx
  HRESULT WriterProperty; // edi
  const char *v14; // r8
  char v15; // al
  const char *v16; // rdx
  bool v17; // zf
  int v18; // edx
  const char *v19; // r8
  char v20; // al
  const char *v21; // rdx
  bool v22; // zf
  const char *v23; // rax
  WS_XML_WRITER *v24; // rcx
  const char *v25; // r8
  char v26; // al
  const char *v27; // rdx
  bool v28; // zf
  unsigned __int64 v29; // rdx
  __int64 i; // rcx
  const char *v31; // rax
  struct _CRYPT_XML_BLOB *v32; // rdi
  __int64 v33; // rax
  unsigned int v35; // esi
  __int64 v36; // r14
  __int64 v37; // rdx
  __int64 v38; // rbx
  WS_ERROR *propertyCount; // [rsp+20h] [rbp-68h]
  __int128 value; // [rsp+30h] [rbp-58h] BYREF
  WS_XML_WRITER_PROPERTY v41; // [rsp+40h] [rbp-48h] BYREF
  WS_XML_WRITER_OUTPUT v42; // [rsp+90h] [rbp+8h] BYREF
  WS_XML_WRITER_ENCODING v43; // [rsp+98h] [rbp+10h] BYREF
  enum WS_CHARSET v44; // [rsp+9Ch] [rbp+14h]

  v41.id = WS_XML_WRITER_PROPERTY_BUFFER_MAX_SIZE;
  v44 = a1;
  v41.value = &a6;
  error = *a2;
  v41.valueSize = 4;
  v42.outputType = WS_XML_WRITER_OUTPUT_TYPE_BUFFER;
  v12 = a2[2];
  v43.encodingType = WS_XML_WRITER_ENCODING_TYPE_TEXT;
  WriterProperty = WsSetOutput(v12, &v43, &v42, &v41, a6 != 0, error);
  if ( WriterProperty < 0 )
  {
    v14 = "";
    while ( 1 )
    {
      v15 = *(v14 - 1);
      v16 = v14--;
      v17 = v15 == 92;
      if ( v15 == 92 )
        break;
      if ( v14 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
      {
        v17 = v15 == 92;
        break;
      }
    }
    if ( v17 )
      v14 = v16;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", WriterProperty, v14, 2304);
    goto LABEL_34;
  }
  WriterProperty = WsWriteElement(a2[2], a3, WS_WRITE_REQUIRED_VALUE, a4, valueSize, *a2);
  if ( WriterProperty < 0 )
  {
    v19 = "";
    while ( 1 )
    {
      v20 = *(v19 - 1);
      v21 = v19--;
      v22 = v20 == 92;
      if ( v20 == 92 )
        break;
      if ( v19 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
      {
        v22 = v20 == 92;
        break;
      }
    }
    if ( v22 )
      v19 = v21;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", WriterProperty, v19, 2318);
    goto LABEL_34;
  }
  WriterProperty = WsFlushWriter(a2[2], 0, 0, *a2);
  if ( WriterProperty < 0 )
  {
    v23 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", WriterProperty, v23, 2334);
LABEL_34:
    if ( *a2 )
      I_TraceWsError(*a2, v18);
    return (unsigned int)WriterProperty;
  }
  v24 = a2[2];
  propertyCount = *a2;
  value = 0;
  WriterProperty = WsGetWriterProperty(v24, WS_XML_WRITER_PROPERTY_BUFFERS, &value, 0x10u, propertyCount);
  if ( WriterProperty < 0 )
  {
    v25 = "";
    while ( 1 )
    {
      v26 = *(v25 - 1);
      v27 = v25--;
      v28 = v26 == 92;
      if ( v26 == 92 )
        break;
      if ( v25 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
      {
        v28 = v26 == 92;
        break;
      }
    }
    if ( v28 )
      v25 = v27;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", WriterProperty, v25, 2352);
    goto LABEL_34;
  }
  v29 = 0;
  for ( i = 0; (unsigned int)i < (unsigned int)value; i = (unsigned int)(i + 1) )
  {
    v29 += *(unsigned int *)(*((_QWORD *)&value + 1) + 16LL * (unsigned int)i);
    if ( v29 > 0x7FFFFFF8 )
    {
      WriterProperty = -2146885375;
      v31 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v31, 2362);
      goto LABEL_34;
    }
  }
  v32 = a7;
  a7->cbData = v29;
  v33 = CryptXmlAlloc(i, (unsigned int)v29);
  v32->pbData = (BYTE *)v33;
  if ( !v33 )
  {
    WriterProperty = -2147024882;
    goto LABEL_34;
  }
  v32->dwCharset = a1;
  v35 = 0;
  v36 = 0;
  if ( (_DWORD)value )
  {
    v37 = *((_QWORD *)&value + 1);
    do
    {
      v38 = 2LL * v35;
      memcpy_0(&v32->pbData[v36], *(const void **)(v37 + 16LL * v35 + 8), *(unsigned int *)(v37 + 16LL * v35));
      v37 = *((_QWORD *)&value + 1);
      ++v35;
      v36 += *(unsigned int *)(*((_QWORD *)&value + 1) + 8 * v38);
    }
    while ( v35 < (unsigned int)value );
  }
  return 0;
}

```

## disassembly

```asm
0x180001d00  mov     r11, rsp
0x180001d03  mov     [r11+18h], rbx
0x180001d07  push    rbp
0x180001d08  push    rsi
0x180001d09  push    rdi
0x180001d0a  push    r14
0x180001d0c  push    r15
0x180001d0e  sub     rsp, 60h
0x180001d12  mov     rbx, rdx
0x180001d15  mov     [rsp+88h+var_48], 8
0x180001d1d  xor     edx, edx
0x180001d1f  mov     [r11+14h], ecx
0x180001d23  cmp     [r11+30h], edx
0x180001d27  lea     rax, [r11+30h]
0x180001d2b  mov     [r11-40h], rax
0x180001d2f  mov     r15d, 1
0x180001d35  mov     rax, [rbx]
0x180001d38  cmova   edx, r15d
0x180001d3c  mov     [r11-60h], rax
0x180001d40  mov     rsi, r9
0x180001d43  mov     [rsp+88h+propertyCount], edx; propertyCount
0x180001d47  lea     r9, [r11-48h]; properties
0x180001d4b  mov     rbp, r8
0x180001d4e  mov     [rsp+88h+var_38], 4
0x180001d56  mov     r14d, ecx
0x180001d59  mov     [r11+8], r15d
0x180001d5d  mov     rcx, [rbx+10h]; writer
0x180001d61  lea     rdx, [r11+10h]; encoding
0x180001d65  lea     r8, [r11+8]; output
0x180001d69  mov     [r11+10h], r15d
0x180001d6d  call    cs:__imp_WsSetOutput
0x180001d74  nop     dword ptr [rax+rax+00h]
0x180001d79  mov     edi, eax
0x180001d7b  test    eax, eax
0x180001d7d  jns     short loc_180001DC0
0x180001d7f  lea     r8, aOnecoreDsSecur_5+30h; ""
0x180001d86  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001d8d  movzx   eax, byte ptr [r8-1]
0x180001d92  mov     rdx, r8
0x180001d95  dec     r8
0x180001d98  cmp     al, 5Ch ; '\'
0x180001d9a  jz      short loc_180001DA3
0x180001d9c  cmp     r8, rcx
0x180001d9f  ja      short loc_180001D8D
0x180001da1  cmp     al, 5Ch ; '\'
0x180001da3  cmovz   r8, rdx
0x180001da7  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180001dae  mov     edx, edi
0x180001db0  mov     r9d, 900h
0x180001db6  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180001dbb  jmp     loc_180001F5F
0x180001dc0  mov     rax, [rbx]
0x180001dc3  mov     r9, rsi; value
0x180001dc6  mov     rcx, [rbx+10h]; writer
0x180001dca  mov     r8d, r15d; writeOption
0x180001dcd  mov     [rsp+88h+error], rax; error
0x180001dd2  mov     rdx, rbp; elementDescription
0x180001dd5  mov     eax, [rsp+88h+valueSize]
0x180001ddc  mov     [rsp+88h+propertyCount], eax; valueSize
0x180001de0  call    cs:__imp_WsWriteElement
0x180001de7  nop     dword ptr [rax+rax+00h]
0x180001dec  mov     edi, eax
0x180001dee  test    eax, eax
0x180001df0  jns     short loc_180001E33
0x180001df2  lea     r8, aOnecoreDsSecur_5+30h; ""
0x180001df9  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001e00  movzx   eax, byte ptr [r8-1]
0x180001e05  mov     rdx, r8
0x180001e08  dec     r8
0x180001e0b  cmp     al, 5Ch ; '\'
0x180001e0d  jz      short loc_180001E16
0x180001e0f  cmp     r8, rcx
0x180001e12  ja      short loc_180001E00
0x180001e14  cmp     al, 5Ch ; '\'
0x180001e16  cmovz   r8, rdx
0x180001e1a  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180001e21  mov     edx, edi
0x180001e23  mov     r9d, 90Eh
0x180001e29  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180001e2e  jmp     loc_180001F5F
0x180001e33  mov     r9, [rbx]; error
0x180001e36  xor     r8d, r8d; asyncContext
0x180001e39  mov     rcx, [rbx+10h]; writer
0x180001e3d  xor     edx, edx; minSize
0x180001e3f  call    cs:__imp_WsFlushWriter
0x180001e46  nop     dword ptr [rax+rax+00h]
0x180001e4b  mov     edi, eax
0x180001e4d  test    eax, eax
0x180001e4f  jns     short loc_180001E79
0x180001e51  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001e58  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180001e5d  mov     r8, rax
0x180001e60  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180001e67  mov     edx, edi
0x180001e69  mov     r9d, 91Eh
0x180001e6f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180001e74  jmp     loc_180001F5F
0x180001e79  mov     rax, [rbx]
0x180001e7c  lea     r8, [rsp+88h+value]; value
0x180001e81  mov     rcx, [rbx+10h]; writer
0x180001e85  xorps   xmm0, xmm0
0x180001e88  mov     r9d, 10h; valueSize
0x180001e8e  mov     qword ptr [rsp+88h+propertyCount], rax; error
0x180001e93  mov     edx, 7; id
0x180001e98  movups  [rsp+88h+value], xmm0
0x180001e9d  call    cs:__imp_WsGetWriterProperty
0x180001ea4  nop     dword ptr [rax+rax+00h]
0x180001ea9  mov     edi, eax
0x180001eab  test    eax, eax
0x180001ead  jns     short loc_180001EED
0x180001eaf  lea     r8, aOnecoreDsSecur_5+30h; ""
0x180001eb6  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001ebd  movzx   eax, byte ptr [r8-1]
0x180001ec2  mov     rdx, r8
0x180001ec5  dec     r8
0x180001ec8  cmp     al, 5Ch ; '\'
0x180001eca  jz      short loc_180001ED3
0x180001ecc  cmp     r8, rcx
0x180001ecf  ja      short loc_180001EBD
0x180001ed1  cmp     al, 5Ch ; '\'
0x180001ed3  cmovz   r8, rdx
0x180001ed7  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180001ede  mov     edx, edi
0x180001ee0  mov     r9d, 930h
0x180001ee6  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180001eeb  jmp     short loc_180001F5F
0x180001eed  mov     r8, qword ptr [rsp+88h+value+8]
0x180001ef2  xor     edx, edx
0x180001ef4  xor     ecx, ecx
0x180001ef6  cmp     ecx, dword ptr [rsp+88h+value]
0x180001efa  jnb     short loc_180001F3F
0x180001efc  mov     eax, ecx
0x180001efe  add     rax, rax
0x180001f01  mov     eax, [r8+rax*8]
0x180001f05  add     rdx, rax
0x180001f08  cmp     rdx, 7FFFFFF8h
0x180001f0f  ja      short loc_180001F15
0x180001f11  inc     ecx
0x180001f13  jmp     short loc_180001EF6
0x180001f15  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180001f1c  mov     edi, 80092101h
0x180001f21  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180001f26  mov     r8, rax
0x180001f29  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180001f30  mov     edx, edi
0x180001f32  mov     r9d, 93Ah
0x180001f38  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180001f3d  jmp     short loc_180001F5F
0x180001f3f  mov     rdi, [rsp+88h+arg_30]
0x180001f47  mov     edx, edx
0x180001f49  mov     [rdi+4], edx
0x180001f4c  call    CryptXmlAlloc
0x180001f51  mov     [rdi+8], rax
0x180001f55  test    rax, rax
0x180001f58  jnz     short loc_180001F70
0x180001f5a  mov     edi, 8007000Eh
0x180001f5f  mov     rcx, [rbx]; error
0x180001f62  test    rcx, rcx
0x180001f65  jz      short loc_180001F6C
0x180001f67  call    ?I_TraceWsError@@YAXPEAU_WS_ERROR@@J@Z; I_TraceWsError(_WS_ERROR *,long)
0x180001f6c  mov     eax, edi
0x180001f6e  jmp     short loc_180001FBF
0x180001f70  mov     [rdi], r14d
0x180001f73  xor     esi, esi
0x180001f75  xor     r14d, r14d
0x180001f78  cmp     dword ptr [rsp+88h+value], esi
0x180001f7c  jbe     short loc_180001FBD
0x180001f7e  mov     rdx, qword ptr [rsp+88h+value+8]
0x180001f83  nop     dword ptr [rax+00h]
0x180001f87  nop     word ptr [rax+rax+00000000h]
0x180001f90  mov     rcx, [rdi+8]
0x180001f94  mov     ebx, esi
0x180001f96  add     rcx, r14; void *
0x180001f99  add     rbx, rbx
0x180001f9c  mov     r8d, [rdx+rbx*8]; Size
0x180001fa0  mov     rdx, [rdx+rbx*8+8]; Src
0x180001fa5  call    memcpy_0
0x180001faa  mov     rdx, qword ptr [rsp+88h+value+8]
0x180001faf  inc     esi
0x180001fb1  mov     eax, [rdx+rbx*8]
0x180001fb4  add     r14, rax
0x180001fb7  cmp     esi, dword ptr [rsp+88h+value]
0x180001fbb  jb      short loc_180001F90
0x180001fbd  xor     eax, eax
0x180001fbf  mov     rbx, [rsp+88h+arg_10]
0x180001fc7  add     rsp, 60h
0x180001fcb  pop     r15
0x180001fcd  pop     r14
0x180001fcf  pop     rdi
0x180001fd0  pop     rsi
0x180001fd1  pop     rbp
0x180001fd2  retn
```
