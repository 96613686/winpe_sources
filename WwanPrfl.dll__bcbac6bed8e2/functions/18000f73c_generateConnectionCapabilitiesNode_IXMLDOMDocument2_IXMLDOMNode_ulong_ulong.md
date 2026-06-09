# _generateConnectionCapabilitiesNode(IXMLDOMDocument2 *,IXMLDOMNode *,ulong,ulong)

- ea: `0x18000f73c`
- end: `0x18000f84d`
- name: `?_generateConnectionCapabilitiesNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@KK@Z`
- size: `273`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800103ac`

## callees

- `0x18000f73c`
- `0x180011f90`
- `0x180014010`

## string_xrefs

- `0x18000f76a`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000f7c3`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000f773`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000f7cc`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000f75d`: `http://www.microsoft.com/networking/WWAN/profile/v1`

## pseudocode

```c
__int64 __fastcall _generateConnectionCapabilitiesNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        int a3,
        unsigned int a4)
{
  OLECHAR *v7; // r9
  unsigned int v8; // edi
  struct IXMLDOMNode *v9; // rbx
  OLECHAR *v10; // r9
  unsigned int v11; // ebp
  struct IXMLDOMNode *v13; // [rsp+30h] [rbp-48h] BYREF

  v13 = 0;
  if ( a4 < 3 )
  {
    v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4";
    if ( a4 != 2 )
      v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v1";
  }
  else
  {
    v7 = (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9";
  }
  XcAddChildElement(a1, a2, (OLECHAR *)L"ConnectionCapabilities", v7, 0, &v13);
  v8 = 0;
  v9 = v13;
  while ( 1 )
  {
    if ( (a3 & *(_DWORD *)(&_ConnectionCapabilityType + 2 * v8 + 1)) != 0 )
    {
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
      v11 = XcAddChildElement(
              a1,
              v9,
              (OLECHAR *)L"ConnectionCapability",
              v10,
              *((OLECHAR **)&_ConnectionCapabilityType + 2 * v8),
              0);
      if ( v11 )
        break;
    }
    if ( ++v8 >= 0xB )
    {
      if ( v9 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v9->lpVtbl->Release)(v9);
      return 0;
    }
  }
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v9->lpVtbl->Release)(v9);
  return v11;
}

```

## disassembly

```asm
0x18000f73c  push    rbx
0x18000f73e  push    rbp
0x18000f73f  push    rsi
0x18000f740  push    rdi
0x18000f741  push    r13
0x18000f743  push    r14
0x18000f745  push    r15
0x18000f747  sub     rsp, 40h
0x18000f74b  mov     esi, r9d
0x18000f74e  mov     r15d, r8d
0x18000f751  mov     r14, rcx
0x18000f754  mov     [rsp+78h+var_48], 0
0x18000f75d  lea     r13, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x18000f764  cmp     r9d, 3
0x18000f768  jb      short loc_18000F773
0x18000f76a  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000f771  jmp     short loc_18000F781
0x18000f773  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000f77a  cmp     esi, 2
0x18000f77d  cmovnz  r9, r13; OLECHAR *
0x18000f781  lea     rax, [rsp+78h+var_48]
0x18000f786  mov     [rsp+78h+var_50], rax; struct IXMLDOMNode **
0x18000f78b  mov     [rsp+78h+var_58], 0; OLECHAR *
0x18000f794  lea     r8, aConnectioncapa; "ConnectionCapabilities"
0x18000f79b  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f7a0  xor     edi, edi
0x18000f7a2  lea     rcx, ?_ConnectionCapabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _ConnectionCapabilityType
0x18000f7a9  mov     rbx, [rsp+78h+var_48]
0x18000f7ae  mov     eax, edi
0x18000f7b0  add     rax, rax
0x18000f7b3  test    [rcx+rax*8+8], r15d
0x18000f7b8  jz      short loc_18000F807
0x18000f7ba  mov     rcx, [rcx+rax*8]
0x18000f7be  cmp     esi, 3
0x18000f7c1  jb      short loc_18000F7CC
0x18000f7c3  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000f7ca  jmp     short loc_18000F7DA
0x18000f7cc  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000f7d3  cmp     esi, 2
0x18000f7d6  cmovnz  r9, r13; OLECHAR *
0x18000f7da  mov     [rsp+78h+var_50], 0; struct IXMLDOMNode **
0x18000f7e3  mov     [rsp+78h+var_58], rcx; OLECHAR *
0x18000f7e8  lea     r8, aConnectioncapa_0; "ConnectionCapability"
0x18000f7ef  mov     rdx, rbx; struct IXMLDOMNode *
0x18000f7f2  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000f7f5  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f7fa  mov     ebp, eax
0x18000f7fc  test    eax, eax
0x18000f7fe  jnz     short loc_18000F834
0x18000f800  lea     rcx, ?_ConnectionCapabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _ConnectionCapabilityType
0x18000f807  inc     edi
0x18000f809  cmp     edi, 0Bh
0x18000f80c  jb      short loc_18000F7AE
0x18000f80e  test    rbx, rbx
0x18000f811  jz      short loc_18000F823
0x18000f813  mov     rax, [rbx]
0x18000f816  mov     rcx, rbx
0x18000f819  mov     rax, [rax+10h]
0x18000f81d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f822  nop
0x18000f823  xor     eax, eax
0x18000f825  add     rsp, 40h
0x18000f829  pop     r15
0x18000f82b  pop     r14
0x18000f82d  pop     r13
0x18000f82f  pop     rdi
0x18000f830  pop     rsi
0x18000f831  pop     rbp
0x18000f832  pop     rbx
0x18000f833  retn
0x18000f834  test    rbx, rbx
0x18000f837  jz      short loc_18000F849
0x18000f839  mov     rax, [rbx]
0x18000f83c  mov     rcx, rbx
0x18000f83f  mov     rax, [rax+10h]
0x18000f843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f848  nop
0x18000f849  mov     eax, ebp
0x18000f84b  jmp     short loc_18000F825
```
