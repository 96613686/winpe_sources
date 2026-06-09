# _parseModemDMProfilePurposesNode

- ea: `0x18000f510`
- end: `0x18000f733`
- name: `_parseModemDMProfilePurposesNode`
- size: `547`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001670`
- `0x18000f510`
- `0x1800127d0`
- `0x180012bc8`
- `0x1800130e0`
- `0x1800136f4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000f607`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000f607`

## pseudocode

```c
__int64 __fastcall parseModemDMProfilePurposesNode(struct IXMLDOMNode *a1, _DWORD *a2)
{
  unsigned int Nodes; // ebx
  int v5; // r14d
  unsigned int v6; // esi
  struct IXMLDOMNodeList *v7; // rbx
  __int64 v8; // rdi
  unsigned int NodeStringValue; // eax
  int v10; // eax
  struct IXMLDOMNode *v11; // [rsp+40h] [rbp-49h] BYREF
  struct IXMLDOMNodeList *v12; // [rsp+48h] [rbp-41h] BYREF
  GUID iid; // [rsp+50h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-29h] BYREF

  LODWORD(v11) = 0;
  v12 = 0;
  Nodes = XcGetNodes(a1, L"MBNProfileV7:DMProfilePurposeGuid", &v12, (int *)&v11);
  if ( Nodes )
  {
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
    return Nodes;
  }
  else
  {
    v5 = (int)v11;
    if ( (unsigned int)((_DWORD)v11 - 1) > 9 )
    {
      if ( v12 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
      return 1206;
    }
    else
    {
      v6 = 0;
      v7 = v12;
      if ( (int)v11 <= 0 )
      {
LABEL_17:
        if ( v7 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
        return 0;
      }
      else
      {
        while ( 1 )
        {
          v11 = 0;
          LODWORD(v8) = XcGetItem(v7, v6, &v11);
          if ( (_DWORD)v8 )
            break;
          iid = 0;
          NodeStringValue = XcGetNodeStringValue(v11, 0, sz, 0x28u, 0, 0, 0);
          v8 = NodeStringValue;
          if ( NodeStringValue )
            goto LABEL_21;
          if ( IIDFromString(sz, &iid) )
          {
            LODWORD(v8) = 1206;
LABEL_21:
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
            if ( v7 )
              ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
            return (unsigned int)v8;
          }
          while ( memcmp_0(&iid, (char *)qword_18001F480 + 20 * v8 + 4, 0x10u) )
          {
            v8 = (unsigned int)(v8 + 1);
            if ( (unsigned int)v8 >= 0xB )
            {
              v10 = 0;
              goto LABEL_14;
            }
          }
          v10 = *((_DWORD *)qword_18001F480 + 5 * v8);
LABEL_14:
          a2[1384] |= v10;
          if ( v11 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
          if ( (int)++v6 >= v5 )
            goto LABEL_17;
        }
        if ( v11 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
        if ( v7 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
        return (unsigned int)v8;
      }
    }
  }
}

```

## disassembly

```asm
0x18000f510  mov     [rsp-8+arg_10], rbx
0x18000f515  mov     [rsp-8+arg_18], rsi
0x18000f51a  push    rbp
0x18000f51b  push    rdi
0x18000f51c  push    r12
0x18000f51e  push    r14
0x18000f520  push    r15
0x18000f522  lea     rbp, [rsp-37h]
0x18000f527  sub     rsp, 0C0h
0x18000f52e  mov     rax, cs:__security_cookie
0x18000f535  xor     rax, rsp
0x18000f538  mov     [rbp+57h+var_30], rax
0x18000f53c  mov     r12, rdx
0x18000f53f  mov     dword ptr [rbp+57h+var_A0], 0
0x18000f546  mov     [rbp+57h+var_98], 0
0x18000f54e  lea     r9, [rbp+57h+var_A0]; int *
0x18000f552  lea     r8, [rbp+57h+var_98]; struct IXMLDOMNodeList **
0x18000f556  lea     rdx, aMbnprofilev7Dm; "MBNProfileV7:DMProfilePurposeGuid"
0x18000f55d  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000f562  mov     ebx, eax
0x18000f564  test    eax, eax
0x18000f566  jz      short loc_18000F585
0x18000f568  mov     rcx, [rbp+57h+var_98]
0x18000f56c  test    rcx, rcx
0x18000f56f  jz      short loc_18000F57E
0x18000f571  mov     rdx, [rcx]
0x18000f574  mov     rax, [rdx+10h]
0x18000f578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f57d  nop
0x18000f57e  mov     eax, ebx
0x18000f580  jmp     loc_18000F70B
0x18000f585  mov     r14d, dword ptr [rbp+57h+var_A0]
0x18000f589  lea     eax, [r14-1]
0x18000f58d  cmp     eax, 9
0x18000f590  ja      loc_18000F6F0
0x18000f596  xor     esi, esi
0x18000f598  mov     rbx, [rbp+57h+var_98]
0x18000f59c  test    r14d, r14d
0x18000f59f  jle     loc_18000F676
0x18000f5a5  mov     [rbp+57h+var_A0], 0
0x18000f5ad  lea     r8, [rbp+57h+var_A0]; struct IXMLDOMNode **
0x18000f5b1  mov     edx, esi; int
0x18000f5b3  mov     rcx, rbx; struct IXMLDOMNodeList *
0x18000f5b6  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x18000f5bb  mov     edi, eax
0x18000f5bd  test    eax, eax
0x18000f5bf  jnz     loc_18000F6C1
0x18000f5c5  xorps   xmm0, xmm0
0x18000f5c8  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18000f5cc  mov     [rsp+0E0h+var_B0], 0; int *
0x18000f5d5  mov     [rsp+0E0h+var_B8], 0; unsigned __int16 *
0x18000f5de  mov     [rsp+0E0h+var_C0], eax; int
0x18000f5e2  lea     r9d, [rax+28h]; unsigned __int64
0x18000f5e6  lea     r8, [rbp+57h+sz]; unsigned __int16 *
0x18000f5ea  xor     edx, edx; unsigned __int16 *
0x18000f5ec  mov     rcx, [rbp+57h+var_A0]; struct IXMLDOMNode *
0x18000f5f0  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000f5f5  mov     edi, eax
0x18000f5f7  test    eax, eax
0x18000f5f9  jnz     loc_18000F694
0x18000f5ff  lea     rdx, [rbp+57h+iid]; lpiid
0x18000f603  lea     rcx, [rbp+57h+sz]; lpsz
0x18000f607  call    cs:__imp_IIDFromString
0x18000f60d  test    eax, eax
0x18000f60f  jnz     short loc_18000F68F
0x18000f611  lea     r15, [rdi+rdi*4]
0x18000f615  lea     rdx, qword_18001F480
0x18000f61c  lea     rdx, [rdx+4]
0x18000f620  lea     rdx, [rdx+r15*4]; Buf2
0x18000f624  mov     r8d, 10h; Size
0x18000f62a  lea     rcx, [rbp+57h+iid]; Buf1
0x18000f62e  call    memcmp_0
0x18000f633  test    eax, eax
0x18000f635  jz      short loc_18000F642
0x18000f637  inc     edi
0x18000f639  cmp     edi, 0Bh
0x18000f63c  jb      short loc_18000F611
0x18000f63e  xor     eax, eax
0x18000f640  jmp     short loc_18000F64D
0x18000f642  lea     rax, qword_18001F480
0x18000f649  mov     eax, [rax+r15*4]
0x18000f64d  or      [r12+15A0h], eax
0x18000f655  mov     rcx, [rbp+57h+var_A0]
0x18000f659  test    rcx, rcx
0x18000f65c  jz      short loc_18000F66B
0x18000f65e  mov     rax, [rcx]
0x18000f661  mov     rax, [rax+10h]
0x18000f665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f66a  nop
0x18000f66b  inc     esi
0x18000f66d  cmp     esi, r14d
0x18000f670  jl      loc_18000F5A5
0x18000f676  test    rbx, rbx
0x18000f679  jz      short loc_18000F68B
0x18000f67b  mov     rax, [rbx]
0x18000f67e  mov     rcx, rbx
0x18000f681  mov     rax, [rax+10h]
0x18000f685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f68a  nop
0x18000f68b  xor     eax, eax
0x18000f68d  jmp     short loc_18000F70B
0x18000f68f  mov     edi, 4B6h
0x18000f694  mov     rcx, [rbp+57h+var_A0]
0x18000f698  test    rcx, rcx
0x18000f69b  jz      short loc_18000F6AA
0x18000f69d  mov     rax, [rcx]
0x18000f6a0  mov     rax, [rax+10h]
0x18000f6a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6a9  nop
0x18000f6aa  test    rbx, rbx
0x18000f6ad  jz      short loc_18000F6BF
0x18000f6af  mov     rcx, [rbx]
0x18000f6b2  mov     rax, [rcx+10h]
0x18000f6b6  mov     rcx, rbx
0x18000f6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6be  nop
0x18000f6bf  jmp     short loc_18000F6EC
0x18000f6c1  mov     rcx, [rbp+57h+var_A0]
0x18000f6c5  test    rcx, rcx
0x18000f6c8  jz      short loc_18000F6D7
0x18000f6ca  mov     rax, [rcx]
0x18000f6cd  mov     rax, [rax+10h]
0x18000f6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d6  nop
0x18000f6d7  test    rbx, rbx
0x18000f6da  jz      short loc_18000F6EC
0x18000f6dc  mov     rax, [rbx]
0x18000f6df  mov     rcx, rbx
0x18000f6e2  mov     rax, [rax+10h]
0x18000f6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6eb  nop
0x18000f6ec  mov     eax, edi
0x18000f6ee  jmp     short loc_18000F70B
0x18000f6f0  mov     rcx, [rbp+57h+var_98]
0x18000f6f4  test    rcx, rcx
0x18000f6f7  jz      short loc_18000F706
0x18000f6f9  mov     rax, [rcx]
0x18000f6fc  mov     rax, [rax+10h]
0x18000f700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f705  nop
0x18000f706  mov     eax, 4B6h
0x18000f70b  mov     rcx, [rbp+57h+var_30]
0x18000f70f  xor     rcx, rsp; StackCookie
0x18000f712  call    __security_check_cookie
0x18000f717  lea     r11, [rsp+0E0h+var_20]
0x18000f71f  mov     rbx, [r11+40h]
0x18000f723  mov     rsi, [r11+48h]
0x18000f727  mov     rsp, r11
0x18000f72a  pop     r15
0x18000f72c  pop     r14
0x18000f72e  pop     r12
0x18000f730  pop     rdi
0x18000f731  pop     rbp
0x18000f732  retn
```
