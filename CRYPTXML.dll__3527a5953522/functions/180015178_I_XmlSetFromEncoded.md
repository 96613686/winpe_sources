# I_XmlSetFromEncoded

- ea: `0x180015178`
- end: `0x18001527a`
- name: `I_XmlSetFromEncoded`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010520`
- `0x180010730`

## callees

- `0x1800070d0`
- `0x180014ce0`
- `0x180015178`

## import_xrefs

- `webservices!WsReadElement` at `0x180015230`
- `webservices!WsReadElement` at `0x180015230`
- `webservices!WsSetInput` at `0x1800151d9`
- `webservices!WsSetInput` at `0x1800151d9`

## string_xrefs

- `0x1800151eb`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`
- `0x180015242`: `onecore\ds\security\cryptoapi\xml\lib\ws_marshall.cpp`

## pseudocode

```c
__int64 __fastcall I_XmlSetFromEncoded(
        WS_ERROR **a1,
        int *a2,
        const WS_ELEMENT_DESCRIPTION *a3,
        __int64 a4,
        void *value,
        ULONG valueSize)
{
  __int64 v7; // rax
  WS_ERROR *v9; // rax
  WS_XML_READER *v10; // rcx
  HRESULT Element; // ebx
  const char *v12; // rax
  int v13; // r9d
  _QWORD v15[2]; // [rsp+40h] [rbp-28h] BYREF
  int v16; // [rsp+50h] [rbp-18h]
  int v17; // [rsp+54h] [rbp-14h]
  WS_XML_READER_ENCODING v18; // [rsp+70h] [rbp+8h] BYREF
  int v19; // [rsp+74h] [rbp+Ch]

  v19 = *a2;
  v7 = *((_QWORD *)a2 + 1);
  v15[0] = 1;
  v17 = 0;
  v15[1] = v7;
  v16 = a2[1];
  v9 = *a1;
  v10 = a1[1];
  v18.encodingType = WS_XML_READER_ENCODING_TYPE_TEXT;
  Element = WsSetInput(v10, &v18, (const WS_XML_READER_INPUT *)v15, 0, 0, v9);
  if ( Element < 0 )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v13 = 2401;
LABEL_5:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", Element, v12, v13);
    return (unsigned int)Element;
  }
  Element = WsReadElement(a1[1], a3, WS_READ_REQUIRED_VALUE, a1[6], value, valueSize, *a1);
  if ( Element < 0 )
  {
    v12 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_marshall.cpp");
    v13 = 2416;
    goto LABEL_5;
  }
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180015178  mov     r11, rsp
0x18001517b  mov     [r11+10h], rbx
0x18001517f  mov     [r11+18h], rsi
0x180015183  push    rdi
0x180015184  sub     rsp, 60h
0x180015188  mov     eax, [rdx]
0x18001518a  mov     rsi, r8
0x18001518d  mov     [rsp+68h+arg_4], eax
0x180015191  lea     r8, [r11-28h]; input
0x180015195  mov     rax, [rdx+8]
0x180015199  mov     rdi, rcx
0x18001519c  mov     qword ptr [r11-28h], 1
0x1800151a4  xor     r9d, r9d; properties
0x1800151a7  mov     [rsp+68h+var_14], 0
0x1800151af  mov     [r11-20h], rax
0x1800151b3  mov     eax, [rdx+4]
0x1800151b6  lea     rdx, [r11+8]; encoding
0x1800151ba  mov     [rsp+68h+var_18], eax
0x1800151be  mov     rax, [rcx]
0x1800151c1  mov     rcx, [rcx+8]; reader
0x1800151c5  mov     [r11-40h], rax
0x1800151c9  mov     [rsp+68h+propertyCount], 0; propertyCount
0x1800151d1  mov     [rsp+68h+arg_0], 1
0x1800151d9  call    cs:__imp_WsSetInput
0x1800151e0  nop     dword ptr [rax+rax+00h]
0x1800151e5  mov     ebx, eax
0x1800151e7  test    eax, eax
0x1800151e9  jns     short loc_1800151FF
0x1800151eb  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800151f2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800151f7  mov     r9d, 961h
0x1800151fd  jmp     short loc_180015254
0x1800151ff  mov     rax, [rdi]
0x180015202  mov     r8d, 1; readOption
0x180015208  mov     r9, [rdi+30h]; heap
0x18001520c  mov     rdx, rsi; elementDescription
0x18001520f  mov     rcx, [rdi+8]; reader
0x180015213  mov     [rsp+68h+error], rax; error
0x180015218  mov     eax, [rsp+68h+arg_28]
0x18001521f  mov     [rsp+68h+valueSize], eax; valueSize
0x180015223  mov     rax, [rsp+68h+value]
0x18001522b  mov     qword ptr [rsp+68h+propertyCount], rax; value
0x180015230  call    cs:__imp_WsReadElement
0x180015237  nop     dword ptr [rax+rax+00h]
0x18001523c  mov     ebx, eax
0x18001523e  test    eax, eax
0x180015240  jns     short loc_180015265
0x180015242  lea     rcx, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180015249  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001524e  mov     r9d, 970h
0x180015254  mov     r8, rax
0x180015257  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18001525e  mov     edx, ebx
0x180015260  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180015265  lea     r11, [rsp+68h+var_8]
0x18001526a  mov     eax, ebx
0x18001526c  mov     rbx, [r11+18h]
0x180015270  mov     rsi, [r11+20h]
0x180015274  mov     rsp, r11
0x180015277  pop     rdi
0x180015278  retn
```
