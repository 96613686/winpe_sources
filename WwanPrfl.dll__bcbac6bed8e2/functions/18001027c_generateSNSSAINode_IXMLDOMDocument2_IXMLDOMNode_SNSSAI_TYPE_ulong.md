# _generateSNSSAINode(IXMLDOMDocument2 *,IXMLDOMNode *,SNSSAI_TYPE *,ulong)

- ea: `0x18001027c`
- end: `0x1800103a3`
- name: `?_generateSNSSAINode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUSNSSAI_TYPE@@K@Z`
- size: `295`
- prototype: `unsigned int __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct SNSSAI_TYPE *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fc08`

## callees

- `0x18001027c`
- `0x180012260`

## string_xrefs

- `0x18001028b`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x1800102c1`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800102fc`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18001033a`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180010372`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180010299`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
unsigned int __fastcall _generateSNSSAINode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct SNSSAI_TYPE *a3,
        unsigned int a4)
{
  unsigned int result; // eax
  OLECHAR *v5; // rsi
  OLECHAR *v10; // r9
  OLECHAR *v11; // r9
  OLECHAR *v12; // r9
  struct IXMLDOMNode **v13; // [rsp+28h] [rbp-40h]

  result = 0;
  v5 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  if ( (*(_DWORD *)a3 & 0x8000) == 0 )
    goto LABEL_26;
  if ( a4 < 3 )
  {
    v10 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v10 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v10 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"SST", v10, *((unsigned __int8 *)a3 + 4), v13);
  if ( !result )
  {
LABEL_26:
    if ( (*(_DWORD *)a3 & 0x10000) == 0 )
      goto LABEL_27;
    if ( a4 < 3 )
    {
      v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
      if ( a4 != 2 )
        v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
    }
    else
    {
      v11 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
    }
    result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"SD", v11, *((_DWORD *)a3 + 2), v13);
    if ( !result )
    {
LABEL_27:
      if ( (*(_DWORD *)a3 & 0x20000) == 0 )
        goto LABEL_19;
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
      result = XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"MappedSST", v12, *((unsigned __int8 *)a3 + 12), v13);
      if ( !result )
      {
LABEL_19:
        if ( (*(_DWORD *)a3 & 0x40000) != 0 )
        {
          if ( a4 < 3 )
          {
            v5 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
            if ( a4 != 2 )
              v5 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
          }
          return XcAddChildElementDWORD(a1, a2, (OLECHAR *)L"MappedSD", v5, *((_DWORD *)a3 + 4), v13);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001027c  push    rbx
0x18001027e  push    rbp
0x18001027f  push    rsi
0x180010280  push    rdi
0x180010281  push    r12
0x180010283  push    r14
0x180010285  sub     rsp, 38h
0x180010289  xor     eax, eax
0x18001028b  lea     rsi, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x180010292  test    dword ptr [r8], 8000h
0x180010299  lea     r12, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800102a0  mov     edi, r9d
0x1800102a3  mov     rbx, r8
0x1800102a6  mov     rbp, rdx
0x1800102a9  mov     r14, rcx
0x1800102ac  jz      short loc_1800102E4
0x1800102ae  movzx   eax, byte ptr [r8+4]
0x1800102b3  cmp     r9d, 3
0x1800102b7  jb      short loc_1800102BE
0x1800102b9  mov     r9, rsi
0x1800102bc  jmp     short loc_1800102CC
0x1800102be  cmp     edi, 2
0x1800102c1  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800102c8  cmovnz  r9, r12; OLECHAR *
0x1800102cc  lea     r8, aSst; "SST"
0x1800102d3  mov     [rsp+68h+var_48], eax; unsigned int
0x1800102d7  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x1800102dc  test    eax, eax
0x1800102de  jnz     loc_180010396
0x1800102e4  test    dword ptr [rbx], 10000h
0x1800102ea  jz      short loc_180010321
0x1800102ec  mov     eax, [rbx+8]
0x1800102ef  cmp     edi, 3
0x1800102f2  jb      short loc_1800102F9
0x1800102f4  mov     r9, rsi
0x1800102f7  jmp     short loc_180010307
0x1800102f9  cmp     edi, 2
0x1800102fc  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180010303  cmovnz  r9, r12; OLECHAR *
0x180010307  lea     r8, aSd; "SD"
0x18001030e  mov     [rsp+68h+var_48], eax; unsigned int
0x180010312  mov     rdx, rbp; struct IXMLDOMNode *
0x180010315  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180010318  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18001031d  test    eax, eax
0x18001031f  jnz     short loc_180010396
0x180010321  test    dword ptr [rbx], 20000h
0x180010327  jz      short loc_18001035F
0x180010329  movzx   eax, byte ptr [rbx+0Ch]
0x18001032d  cmp     edi, 3
0x180010330  jb      short loc_180010337
0x180010332  mov     r9, rsi
0x180010335  jmp     short loc_180010345
0x180010337  cmp     edi, 2
0x18001033a  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180010341  cmovnz  r9, r12; OLECHAR *
0x180010345  lea     r8, aMappedsst; "MappedSST"
0x18001034c  mov     [rsp+68h+var_48], eax; unsigned int
0x180010350  mov     rdx, rbp; struct IXMLDOMNode *
0x180010353  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180010356  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x18001035b  test    eax, eax
0x18001035d  jnz     short loc_180010396
0x18001035f  test    dword ptr [rbx], 40000h
0x180010365  jz      short loc_180010396
0x180010367  mov     eax, [rbx+10h]
0x18001036a  cmp     edi, 3
0x18001036d  jnb     short loc_18001037D
0x18001036f  cmp     edi, 2
0x180010372  lea     rsi, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180010379  cmovnz  rsi, r12
0x18001037d  mov     r9, rsi; OLECHAR *
0x180010380  mov     [rsp+68h+var_48], eax; unsigned int
0x180010384  lea     r8, aMappedsd; "MappedSD"
0x18001038b  mov     rdx, rbp; struct IXMLDOMNode *
0x18001038e  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180010391  call    ?XcAddChildElementDWORD@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG2KPEAPEAU2@@Z; XcAddChildElementDWORD(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ulong,IXMLDOMNode * *)
0x180010396  add     rsp, 38h
0x18001039a  pop     r14
0x18001039c  pop     r12
0x18001039e  pop     rdi
0x18001039f  pop     rsi
0x1800103a0  pop     rbp
0x1800103a1  pop     rbx
0x1800103a2  retn
```
