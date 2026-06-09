# _parseRATApplicability

- ea: `0x18000c280`
- end: `0x18000c496`
- name: `_parseRATApplicability`
- size: `534`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001670`
- `0x18000c280`
- `0x1800127d0`
- `0x180012bc8`
- `0x1800130e0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall parseRATApplicability(struct IXMLDOMNode *a1, _DWORD *a2)
{
  unsigned int Nodes; // ebx
  unsigned int v5; // edi
  struct IXMLDOMNodeList *v6; // rbx
  unsigned int Item; // esi
  unsigned int NodeStringValue; // eax
  unsigned __int16 *v9; // rcx
  int v10; // r8d
  int v11; // edx
  int v12; // [rsp+40h] [rbp-79h] BYREF
  struct IXMLDOMNode *v13; // [rsp+48h] [rbp-71h] BYREF
  struct IXMLDOMNodeList *v14; // [rsp+50h] [rbp-69h] BYREF
  int v15; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 v16[64]; // [rsp+60h] [rbp-59h] BYREF

  v14 = 0;
  v12 = 0;
  if ( a2[1159] )
    return 1206;
  Nodes = XcGetNodes(a1, L"MBNProfileV9:RATType", &v14, &v12);
  if ( Nodes )
  {
    if ( v14 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v14->lpVtbl->Release)(v14);
    return Nodes;
  }
  else
  {
    v5 = 0;
    v6 = v14;
    if ( v12 <= 0 )
    {
LABEL_23:
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
      return 0;
    }
    else
    {
      while ( 1 )
      {
        v13 = 0;
        Item = XcGetItem(v6, v5, &v13);
        if ( Item )
          break;
        NodeStringValue = XcGetNodeStringValue(v13, L"MBNProfileV9:BaseRAT", v16, 0x40u, 0, 0, &v15);
        Item = NodeStringValue;
        if ( NodeStringValue )
        {
          if ( v13 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v13->lpVtbl->Release)(v13);
          if ( v6 )
            ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
          return Item;
        }
        while ( 1 )
        {
          v9 = v16;
          do
          {
            v10 = *(unsigned __int16 *)((char *)v9 + *((_QWORD *)&_RATType + 2 * NodeStringValue) - (_QWORD)v16);
            v11 = *v9 - v10;
            if ( v11 )
              break;
            ++v9;
          }
          while ( v10 );
          if ( !v11 )
            break;
          if ( ++NodeStringValue >= 4 )
          {
            if ( v13 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v13->lpVtbl->Release)(v13);
            if ( v6 )
              ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
            return 1206;
          }
        }
        a2[1160] |= *((_DWORD *)&_RATType + 4 * NodeStringValue + 2);
        if ( v13 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v13->lpVtbl->Release)(v13);
        if ( (int)++v5 >= v12 )
          goto LABEL_23;
      }
      if ( v13 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v13->lpVtbl->Release)(v13);
      if ( v6 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v6->lpVtbl->Release)(v6);
      return Item;
    }
  }
}

```

## disassembly

```asm
0x18000c280  mov     [rsp-8+arg_10], rbx
0x18000c285  push    rbp
0x18000c286  push    rsi
0x18000c287  push    rdi
0x18000c288  push    r13
0x18000c28a  push    r15
0x18000c28c  lea     rbp, [rsp-37h]
0x18000c291  sub     rsp, 0F0h
0x18000c298  mov     rax, cs:__security_cookie
0x18000c29f  xor     rax, rsp
0x18000c2a2  mov     [rbp+57h+var_30], rax
0x18000c2a6  mov     r15, rdx
0x18000c2a9  mov     [rbp+57h+var_C0], 0
0x18000c2b1  mov     [rbp+57h+var_D0], 0
0x18000c2b8  cmp     dword ptr [rdx+121Ch], 0
0x18000c2bf  jz      short loc_18000C2CB
0x18000c2c1  mov     eax, 4B6h
0x18000c2c6  jmp     loc_18000C417
0x18000c2cb  lea     r9, [rbp+57h+var_D0]; int *
0x18000c2cf  lea     r8, [rbp+57h+var_C0]; struct IXMLDOMNodeList **
0x18000c2d3  lea     rdx, aMbnprofilev9Ra_1; "MBNProfileV9:RATType"
0x18000c2da  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000c2df  mov     ebx, eax
0x18000c2e1  test    eax, eax
0x18000c2e3  jz      short loc_18000C302
0x18000c2e5  mov     rcx, [rbp+57h+var_C0]
0x18000c2e9  test    rcx, rcx
0x18000c2ec  jz      short loc_18000C2FB
0x18000c2ee  mov     rdx, [rcx]
0x18000c2f1  mov     rax, [rdx+10h]
0x18000c2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2fa  nop
0x18000c2fb  mov     eax, ebx
0x18000c2fd  jmp     loc_18000C417
0x18000c302  xor     edi, edi
0x18000c304  mov     rbx, [rbp+57h+var_C0]
0x18000c308  cmp     [rbp+57h+var_D0], edi
0x18000c30b  jle     loc_18000C400
0x18000c311  lea     r13, ?_RATType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _RATType
0x18000c318  mov     [rbp+57h+var_C8], 0
0x18000c320  lea     r8, [rbp+57h+var_C8]; struct IXMLDOMNode **
0x18000c324  mov     edx, edi; int
0x18000c326  mov     rcx, rbx; struct IXMLDOMNodeList *
0x18000c329  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x18000c32e  mov     esi, eax
0x18000c330  test    eax, eax
0x18000c332  jnz     loc_18000C467
0x18000c338  lea     rax, [rbp+57h+var_B8]
0x18000c33c  mov     [rsp+110h+var_E0], rax; int *
0x18000c341  mov     [rsp+110h+var_E8], 0; unsigned __int16 *
0x18000c34a  mov     [rsp+110h+var_F0], esi; int
0x18000c34e  lea     r9d, [rsi+40h]; unsigned __int64
0x18000c352  lea     r8, [rbp+57h+var_B0]; unsigned __int16 *
0x18000c356  lea     rdx, aMbnprofilev9Ba; "MBNProfileV9:BaseRAT"
0x18000c35d  mov     rcx, [rbp+57h+var_C8]; struct IXMLDOMNode *
0x18000c361  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000c366  mov     esi, eax
0x18000c368  test    eax, eax
0x18000c36a  jnz     loc_18000C43A
0x18000c370  mov     r9d, eax
0x18000c373  add     r9, r9
0x18000c376  lea     rcx, [rbp+57h+var_B0]
0x18000c37a  mov     r10, [r13+r9*8+0]
0x18000c37f  sub     r10, rcx
0x18000c382  movzx   edx, word ptr [rcx]
0x18000c385  movzx   r8d, word ptr [rcx+r10]
0x18000c38a  sub     edx, r8d
0x18000c38d  jnz     short loc_18000C398
0x18000c38f  add     rcx, 2
0x18000c393  test    r8d, r8d
0x18000c396  jnz     short loc_18000C382
0x18000c398  test    edx, edx
0x18000c39a  jz      short loc_18000C3D3
0x18000c39c  inc     eax
0x18000c39e  cmp     eax, 4
0x18000c3a1  jb      short loc_18000C370
0x18000c3a3  mov     rcx, [rbp+57h+var_C8]
0x18000c3a7  test    rcx, rcx
0x18000c3aa  jz      short loc_18000C3B9
0x18000c3ac  mov     rax, [rcx]
0x18000c3af  mov     rax, [rax+10h]
0x18000c3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b8  nop
0x18000c3b9  test    rbx, rbx
0x18000c3bc  jz      short loc_18000C3CE
0x18000c3be  mov     rax, [rbx]
0x18000c3c1  mov     rcx, rbx
0x18000c3c4  mov     rax, [rax+10h]
0x18000c3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3cd  nop
0x18000c3ce  jmp     loc_18000C2C1
0x18000c3d3  mov     eax, [r13+r9*8+8]
0x18000c3d8  or      [r15+1220h], eax
0x18000c3df  mov     rcx, [rbp+57h+var_C8]
0x18000c3e3  test    rcx, rcx
0x18000c3e6  jz      short loc_18000C3F5
0x18000c3e8  mov     rax, [rcx]
0x18000c3eb  mov     rax, [rax+10h]
0x18000c3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3f4  nop
0x18000c3f5  inc     edi
0x18000c3f7  cmp     edi, [rbp+57h+var_D0]
0x18000c3fa  jl      loc_18000C318
0x18000c400  test    rbx, rbx
0x18000c403  jz      short loc_18000C415
0x18000c405  mov     rax, [rbx]
0x18000c408  mov     rcx, rbx
0x18000c40b  mov     rax, [rax+10h]
0x18000c40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c414  nop
0x18000c415  xor     eax, eax
0x18000c417  mov     rcx, [rbp+57h+var_30]
0x18000c41b  xor     rcx, rsp; StackCookie
0x18000c41e  call    __security_check_cookie
0x18000c423  mov     rbx, [rsp+110h+arg_10]
0x18000c42b  add     rsp, 0F0h
0x18000c432  pop     r15
0x18000c434  pop     r13
0x18000c436  pop     rdi
0x18000c437  pop     rsi
0x18000c438  pop     rbp
0x18000c439  retn
0x18000c43a  mov     rcx, [rbp+57h+var_C8]
0x18000c43e  test    rcx, rcx
0x18000c441  jz      short loc_18000C450
0x18000c443  mov     rax, [rcx]
0x18000c446  mov     rax, [rax+10h]
0x18000c44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c44f  nop
0x18000c450  test    rbx, rbx
0x18000c453  jz      short loc_18000C465
0x18000c455  mov     rax, [rbx]
0x18000c458  mov     rcx, rbx
0x18000c45b  mov     rax, [rax+10h]
0x18000c45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c464  nop
0x18000c465  jmp     short loc_18000C492
0x18000c467  mov     rcx, [rbp+57h+var_C8]
0x18000c46b  test    rcx, rcx
0x18000c46e  jz      short loc_18000C47D
0x18000c470  mov     rax, [rcx]
0x18000c473  mov     rax, [rax+10h]
0x18000c477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c47c  nop
0x18000c47d  test    rbx, rbx
0x18000c480  jz      short loc_18000C492
0x18000c482  mov     rax, [rbx]
0x18000c485  mov     rcx, rbx
0x18000c488  mov     rax, [rax+10h]
0x18000c48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c491  nop
0x18000c492  mov     eax, esi
0x18000c494  jmp     short loc_18000C417
```
