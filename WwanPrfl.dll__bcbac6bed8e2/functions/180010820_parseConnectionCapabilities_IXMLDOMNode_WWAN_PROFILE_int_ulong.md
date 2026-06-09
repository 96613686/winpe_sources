# _parseConnectionCapabilities(IXMLDOMNode *,WWAN_PROFILE *,int,ulong)

- ea: `0x180010820`
- end: `0x180010a1b`
- name: `?_parseConnectionCapabilities@@YAKPEAUIXMLDOMNode@@PEAUWWAN_PROFILE@@HK@Z`
- size: `507`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct WWAN_PROFILE *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001670`
- `0x180010820`
- `0x1800127d0`
- `0x180012bc8`
- `0x1800130e0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall _parseConnectionCapabilities(
        struct IXMLDOMNode *a1,
        struct WWAN_PROFILE *a2,
        __int64 a3,
        unsigned int a4)
{
  const unsigned __int16 *v5; // rdx
  int v6; // esi
  struct IXMLDOMNodeList *v7; // rbx
  unsigned int Item; // edi
  unsigned int NodeStringValue; // eax
  unsigned __int16 *v10; // rcx
  int v11; // r8d
  int v12; // edx
  int v14; // [rsp+40h] [rbp-79h] BYREF
  struct IXMLDOMNode *v15; // [rsp+48h] [rbp-71h] BYREF
  struct IXMLDOMNodeList *v16; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int16 v17[64]; // [rsp+60h] [rbp-59h] BYREF

  v14 = 0;
  v16 = 0;
  if ( a4 < 3 )
  {
    v5 = L"MBNProfileV4:ConnectionCapability";
    if ( a4 != 2 )
      v5 = L"MBNProfile:ConnectionCapability";
  }
  else
  {
    v5 = L"MBNProfileV9:ConnectionCapability";
  }
  XcGetNodes(a1, v5, &v16, &v14);
  v6 = 0;
  v7 = v16;
  if ( v14 <= 0 )
  {
LABEL_21:
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
    return 0;
  }
  else
  {
    while ( 1 )
    {
      v15 = 0;
      Item = XcGetItem(v7, v6, &v15);
      if ( Item )
        break;
      NodeStringValue = XcGetNodeStringValue(v15, 0, v17, 0x40u, 0, 0, 0);
      Item = NodeStringValue;
      if ( NodeStringValue )
      {
        if ( v15 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
        if ( v7 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
        return Item;
      }
      while ( 1 )
      {
        v10 = v17;
        do
        {
          v11 = *(unsigned __int16 *)((char *)v10
                                    + *((_QWORD *)&_ConnectionCapabilityType + 2 * NodeStringValue)
                                    - (_QWORD)v17);
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( !v12 )
          break;
        if ( ++NodeStringValue >= 0xB )
        {
          if ( v15 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
          if ( v7 )
            ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
          return 1206;
        }
      }
      *((_DWORD *)a2 + 1384) |= *((_DWORD *)&_ConnectionCapabilityType + 4 * NodeStringValue + 2);
      if ( v15 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
      if ( ++v6 >= v14 )
        goto LABEL_21;
    }
    if ( v15 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v15->lpVtbl->Release)(v15);
    if ( v7 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
    return Item;
  }
}

```

## disassembly

```asm
0x180010820  mov     [rsp-8+arg_10], rbx
0x180010825  push    rbp
0x180010826  push    rsi
0x180010827  push    rdi
0x180010828  push    r13
0x18001082a  push    r15
0x18001082c  lea     rbp, [rsp-37h]
0x180010831  sub     rsp, 0F0h
0x180010838  mov     rax, cs:__security_cookie
0x18001083f  xor     rax, rsp
0x180010842  mov     [rbp+57h+var_30], rax
0x180010846  mov     r15, rdx
0x180010849  mov     [rbp+57h+var_D0], 0
0x180010850  mov     [rbp+57h+var_C0], 0
0x180010858  cmp     r9d, 3
0x18001085c  jb      short loc_180010867
0x18001085e  lea     rdx, aMbnprofilev9Co_2; "MBNProfileV9:ConnectionCapability"
0x180010865  jmp     short loc_18001087D
0x180010867  lea     rdx, aMbnprofilev4Co_0; "MBNProfileV4:ConnectionCapability"
0x18001086e  lea     rax, aMbnprofileConn; "MBNProfile:ConnectionCapability"
0x180010875  cmp     r9d, 2
0x180010879  cmovnz  rdx, rax; unsigned __int16 *
0x18001087d  lea     r9, [rbp+57h+var_D0]; int *
0x180010881  lea     r8, [rbp+57h+var_C0]; struct IXMLDOMNodeList **
0x180010885  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18001088a  xor     esi, esi
0x18001088c  mov     rbx, [rbp+57h+var_C0]
0x180010890  cmp     [rbp+57h+var_D0], esi
0x180010893  jle     loc_180010985
0x180010899  lea     r13, ?_ConnectionCapabilityType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _ConnectionCapabilityType
0x1800108a0  mov     [rbp+57h+var_C8], 0
0x1800108a8  lea     r8, [rbp+57h+var_C8]; struct IXMLDOMNode **
0x1800108ac  mov     edx, esi; int
0x1800108ae  mov     rcx, rbx; struct IXMLDOMNodeList *
0x1800108b1  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x1800108b6  mov     edi, eax
0x1800108b8  test    eax, eax
0x1800108ba  jnz     loc_1800109EC
0x1800108c0  mov     [rsp+110h+var_E0], 0; int *
0x1800108c9  mov     [rsp+110h+var_E8], 0; unsigned __int16 *
0x1800108d2  mov     [rsp+110h+var_F0], eax; int
0x1800108d6  lea     r9d, [rax+40h]; unsigned __int64
0x1800108da  lea     r8, [rbp+57h+var_B0]; unsigned __int16 *
0x1800108de  xor     edx, edx; unsigned __int16 *
0x1800108e0  mov     rcx, [rbp+57h+var_C8]; struct IXMLDOMNode *
0x1800108e4  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x1800108e9  mov     edi, eax
0x1800108eb  test    eax, eax
0x1800108ed  jnz     loc_1800109BF
0x1800108f3  mov     r9d, eax
0x1800108f6  add     r9, r9
0x1800108f9  lea     rcx, [rbp+57h+var_B0]
0x1800108fd  mov     r10, [r13+r9*8+0]
0x180010902  sub     r10, rcx
0x180010905  movzx   edx, word ptr [rcx]
0x180010908  movzx   r8d, word ptr [rcx+r10]
0x18001090d  sub     edx, r8d
0x180010910  jnz     short loc_18001091B
0x180010912  add     rcx, 2
0x180010916  test    r8d, r8d
0x180010919  jnz     short loc_180010905
0x18001091b  test    edx, edx
0x18001091d  jz      short loc_180010958
0x18001091f  inc     eax
0x180010921  cmp     eax, 0Bh
0x180010924  jb      short loc_1800108F3
0x180010926  mov     rcx, [rbp+57h+var_C8]
0x18001092a  test    rcx, rcx
0x18001092d  jz      short loc_18001093C
0x18001092f  mov     rax, [rcx]
0x180010932  mov     rax, [rax+10h]
0x180010936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001093b  nop
0x18001093c  test    rbx, rbx
0x18001093f  jz      short loc_180010951
0x180010941  mov     rax, [rbx]
0x180010944  mov     rcx, rbx
0x180010947  mov     rax, [rax+10h]
0x18001094b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010950  nop
0x180010951  mov     eax, 4B6h
0x180010956  jmp     short loc_18001099C
0x180010958  mov     eax, [r13+r9*8+8]
0x18001095d  or      [r15+15A0h], eax
0x180010964  mov     rcx, [rbp+57h+var_C8]
0x180010968  test    rcx, rcx
0x18001096b  jz      short loc_18001097A
0x18001096d  mov     rax, [rcx]
0x180010970  mov     rax, [rax+10h]
0x180010974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010979  nop
0x18001097a  inc     esi
0x18001097c  cmp     esi, [rbp+57h+var_D0]
0x18001097f  jl      loc_1800108A0
0x180010985  test    rbx, rbx
0x180010988  jz      short loc_18001099A
0x18001098a  mov     rax, [rbx]
0x18001098d  mov     rcx, rbx
0x180010990  mov     rax, [rax+10h]
0x180010994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010999  nop
0x18001099a  xor     eax, eax
0x18001099c  mov     rcx, [rbp+57h+var_30]
0x1800109a0  xor     rcx, rsp; StackCookie
0x1800109a3  call    __security_check_cookie
0x1800109a8  mov     rbx, [rsp+110h+arg_10]
0x1800109b0  add     rsp, 0F0h
0x1800109b7  pop     r15
0x1800109b9  pop     r13
0x1800109bb  pop     rdi
0x1800109bc  pop     rsi
0x1800109bd  pop     rbp
0x1800109be  retn
0x1800109bf  mov     rcx, [rbp+57h+var_C8]
0x1800109c3  test    rcx, rcx
0x1800109c6  jz      short loc_1800109D5
0x1800109c8  mov     rax, [rcx]
0x1800109cb  mov     rax, [rax+10h]
0x1800109cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d4  nop
0x1800109d5  test    rbx, rbx
0x1800109d8  jz      short loc_1800109EA
0x1800109da  mov     rax, [rbx]
0x1800109dd  mov     rcx, rbx
0x1800109e0  mov     rax, [rax+10h]
0x1800109e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109e9  nop
0x1800109ea  jmp     short loc_180010A17
0x1800109ec  mov     rcx, [rbp+57h+var_C8]
0x1800109f0  test    rcx, rcx
0x1800109f3  jz      short loc_180010A02
0x1800109f5  mov     rax, [rcx]
0x1800109f8  mov     rax, [rax+10h]
0x1800109fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a01  nop
0x180010a02  test    rbx, rbx
0x180010a05  jz      short loc_180010A17
0x180010a07  mov     rax, [rbx]
0x180010a0a  mov     rcx, rbx
0x180010a0d  mov     rax, [rax+10h]
0x180010a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a16  nop
0x180010a17  mov     eax, edi
0x180010a19  jmp     short loc_18001099C
```
