# _parseMmsConfigurationNode

- ea: `0x18000ba90`
- end: `0x18000bbd1`
- name: `_parseMmsConfigurationNode`
- size: `321`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001670`
- `0x18000ba90`
- `0x180012bc8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000bb47`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000bba8`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000bb47`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000bba8`

## pseudocode

```c
__int64 __fastcall parseMmsConfigurationNode(struct IXMLDOMNode *a1, __int64 a2)
{
  _WORD *v2; // rbx
  __int64 result; // rax
  int v6; // eax
  int v7; // eax
  unsigned __int16 v8[8]; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 v9[12]; // [rsp+50h] [rbp-28h] BYREF

  v2 = (_WORD *)(a2 + 4720);
  result = XcGetNodeStringValue(a1, L"MBNProfileV4:MmscUrl", (unsigned __int16 *)(a2 + 4720), 0x100u, 1, 0, 0);
  if ( (_DWORD)result == 1168 )
  {
    *v2 = 0;
  }
  else if ( (_DWORD)result )
  {
    return result;
  }
  result = XcGetNodeStringValue(a1, L"MBNProfileV4:MmscPort", v8, 6u, 1, 0, 0);
  if ( (_DWORD)result == 1168 )
  {
    v6 = 0;
  }
  else
  {
    if ( (_DWORD)result )
      return result;
    v6 = _o__wtoi(v8);
  }
  *(_DWORD *)(a2 + 5232) = v6;
  *(_DWORD *)(a2 + 5236) = 0;
  result = XcGetNodeStringValue(a1, L"MBNProfileV4:MmsMaximumMessageSize", v9, 0xCu, 1, 0, 0);
  if ( (_DWORD)result == 1168 )
  {
    v7 = 0;
  }
  else
  {
    if ( (_DWORD)result )
      return result;
    v7 = _o__wtoi(v9);
  }
  *(_DWORD *)(a2 + 5236) = v7;
  return 0;
}

```

## disassembly

```asm
0x18000ba90  mov     r11, rsp
0x18000ba93  mov     [r11+18h], rbx
0x18000ba97  mov     [r11+20h], rsi
0x18000ba9b  push    rdi
0x18000ba9c  sub     rsp, 70h
0x18000baa0  mov     rax, cs:__security_cookie
0x18000baa7  xor     rax, rsp
0x18000baaa  mov     [rsp+78h+var_10], rax
0x18000baaf  lea     rbx, [rdx+1270h]
0x18000bab6  mov     qword ptr [r11-48h], 0
0x18000babe  mov     rsi, rdx
0x18000bac1  mov     qword ptr [r11-50h], 0
0x18000bac9  mov     r8, rbx; unsigned __int16 *
0x18000bacc  mov     [rsp+78h+var_58], 1; int
0x18000bad4  mov     r9d, 100h; unsigned __int64
0x18000bada  lea     rdx, aMbnprofilev4Mm_2; "MBNProfileV4:MmscUrl"
0x18000bae1  mov     rdi, rcx
0x18000bae4  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000bae9  cmp     eax, 490h
0x18000baee  jnz     short loc_18000BAF7
0x18000baf0  xor     eax, eax
0x18000baf2  mov     [rbx], ax
0x18000baf5  jmp     short loc_18000BAFF
0x18000baf7  test    eax, eax
0x18000baf9  jnz     loc_18000BBB2
0x18000baff  mov     [rsp+78h+var_48], 0; int *
0x18000bb08  lea     r8, [rsp+78h+var_38]; unsigned __int16 *
0x18000bb0d  mov     [rsp+78h+var_50], 0; unsigned __int16 *
0x18000bb16  lea     rdx, aMbnprofilev4Mm; "MBNProfileV4:MmscPort"
0x18000bb1d  mov     r9d, 6; unsigned __int64
0x18000bb23  mov     [rsp+78h+var_58], 1; int
0x18000bb2b  mov     rcx, rdi; struct IXMLDOMNode *
0x18000bb2e  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000bb33  cmp     eax, 490h
0x18000bb38  jnz     short loc_18000BB3E
0x18000bb3a  xor     eax, eax
0x18000bb3c  jmp     short loc_18000BB4D
0x18000bb3e  test    eax, eax
0x18000bb40  jnz     short loc_18000BBB2
0x18000bb42  lea     rcx, [rsp+78h+var_38]
0x18000bb47  call    cs:__imp__o__wtoi
0x18000bb4d  mov     [rsp+78h+var_48], 0; int *
0x18000bb56  lea     rbx, [rsi+1474h]
0x18000bb5d  mov     [rsi+1470h], eax
0x18000bb63  lea     r8, [rsp+78h+var_28]; unsigned __int16 *
0x18000bb68  mov     [rsp+78h+var_50], 0; unsigned __int16 *
0x18000bb71  lea     rdx, aMbnprofilev4Mm_0; "MBNProfileV4:MmsMaximumMessageSize"
0x18000bb78  mov     r9d, 0Ch; unsigned __int64
0x18000bb7e  mov     dword ptr [rbx], 0
0x18000bb84  mov     rcx, rdi; struct IXMLDOMNode *
0x18000bb87  mov     [rsp+78h+var_58], 1; int
0x18000bb8f  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000bb94  cmp     eax, 490h
0x18000bb99  jnz     short loc_18000BB9F
0x18000bb9b  xor     eax, eax
0x18000bb9d  jmp     short loc_18000BBAE
0x18000bb9f  test    eax, eax
0x18000bba1  jnz     short loc_18000BBB2
0x18000bba3  lea     rcx, [rsp+78h+var_28]
0x18000bba8  call    cs:__imp__o__wtoi
0x18000bbae  mov     [rbx], eax
0x18000bbb0  xor     eax, eax
0x18000bbb2  mov     rcx, [rsp+78h+var_10]
0x18000bbb7  xor     rcx, rsp; StackCookie
0x18000bbba  call    __security_check_cookie
0x18000bbbf  lea     r11, [rsp+78h+var_8]
0x18000bbc4  mov     rbx, [r11+20h]
0x18000bbc8  mov     rsi, [r11+28h]
0x18000bbcc  mov     rsp, r11
0x18000bbcf  pop     rdi
0x18000bbd0  retn
```
