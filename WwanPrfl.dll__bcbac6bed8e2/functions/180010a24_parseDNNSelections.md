# _parseDNNSelections

- ea: `0x180010a24`
- end: `0x180010c59`
- name: `_parseDNNSelections`
- size: `565`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180011164`

## callees

- `0x180002034`
- `0x180010a24`
- `0x1800127d0`
- `0x180012bc8`
- `0x1800130e0`
- `0x1800134f8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010af6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010af6`

## pseudocode

```c
__int64 __fastcall parseDNNSelections(struct IXMLDOMNode *a1, __int64 a2, unsigned int a3)
{
  const unsigned __int16 *v4; // rdx
  DWORD Nodes; // ebx
  int v7; // edi
  size_t v8; // rcx
  size_t v9; // rbx
  void *v10; // rax
  int v11; // esi
  struct IXMLDOMNodeList *v12; // rbx
  unsigned int Item; // r14d
  struct IXMLDOMNode *v14; // [rsp+40h] [rbp-10h] BYREF
  int v15; // [rsp+90h] [rbp+40h] BYREF
  struct IXMLDOMNodeList *v16; // [rsp+98h] [rbp+48h] BYREF

  v15 = 0;
  v16 = 0;
  if ( a3 < 3 )
  {
    v4 = L"MBNProfileV4:DNNSelection";
    if ( a3 != 2 )
      v4 = L"MBNProfile:DNNSelection";
  }
  else
  {
    v4 = L"MBNProfileV9:DNNSelection";
  }
  Nodes = XcGetNodes(a1, v4, &v16, &v15);
  if ( Nodes )
  {
    if ( v16 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v16->lpVtbl->Release)(v16);
    return Nodes;
  }
  v7 = v15;
  if ( v15 > 0 )
  {
    if ( 202 * (unsigned __int64)(unsigned int)v15 > 0xFFFFFFFF
      || (v8 = (unsigned int)(202 * v15 + 4), (unsigned int)v8 < 4) )
    {
      if ( v16 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v16->lpVtbl->Release)(v16);
      return 87;
    }
    else
    {
      v9 = (unsigned int)v8;
      v10 = WwanMemAlloc(v8);
      *(_QWORD *)(a2 + 32) = v10;
      if ( !v10 )
      {
        Nodes = GetLastError();
        if ( v16 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v16->lpVtbl->Release)(v16);
        return Nodes;
      }
      memset_0(v10, 0, v9);
      v11 = 0;
      v12 = v16;
      if ( v7 <= 0 )
      {
LABEL_25:
        **(_DWORD **)(a2 + 32) = v7;
        if ( v12 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
        return 0;
      }
      else
      {
        while ( 1 )
        {
          v14 = 0;
          Item = XcGetItem(v12, v11, &v14);
          if ( Item )
            break;
          Item = XcGetNodeStringValue(
                   v14,
                   0,
                   (unsigned __int16 *)(202LL * v11 + *(_QWORD *)(a2 + 32) + 4LL),
                   0x65u,
                   0,
                   0,
                   0);
          if ( Item )
          {
            if ( v14 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
            if ( v12 )
              ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
            return Item;
          }
          if ( v14 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
          if ( ++v11 >= v7 )
            goto LABEL_25;
        }
        if ( v14 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
        if ( v12 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
        return Item;
      }
    }
  }
  else
  {
    if ( v16 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v16->lpVtbl->Release)(v16);
    return 1206;
  }
}

```

## disassembly

```asm
0x180010a24  mov     [rsp-28h+arg_0], rbx
0x180010a29  push    rbp
0x180010a2a  push    rsi
0x180010a2b  push    rdi
0x180010a2c  push    r14
0x180010a2e  push    r15
0x180010a30  mov     rbp, rsp
0x180010a33  sub     rsp, 50h
0x180010a37  mov     r15, rdx
0x180010a3a  mov     [rbp+arg_10], 0
0x180010a41  mov     [rbp+arg_18], 0
0x180010a49  cmp     r8d, 3
0x180010a4d  jb      short loc_180010A58
0x180010a4f  lea     rdx, aMbnprofilev9Dn_0; "MBNProfileV9:DNNSelection"
0x180010a56  jmp     short loc_180010A6E
0x180010a58  lea     rdx, aMbnprofilev4Dn; "MBNProfileV4:DNNSelection"
0x180010a5f  lea     rax, aMbnprofileDnns_0; "MBNProfile:DNNSelection"
0x180010a66  cmp     r8d, 2
0x180010a6a  cmovnz  rdx, rax; unsigned __int16 *
0x180010a6e  lea     r9, [rbp+arg_10]; int *
0x180010a72  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x180010a76  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x180010a7b  mov     ebx, eax
0x180010a7d  test    eax, eax
0x180010a7f  jz      short loc_180010A9E
0x180010a81  mov     rcx, [rbp+arg_18]
0x180010a85  test    rcx, rcx
0x180010a88  jz      short loc_180010A97
0x180010a8a  mov     rdx, [rcx]
0x180010a8d  mov     rax, [rdx+10h]
0x180010a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a96  nop
0x180010a97  mov     eax, ebx
0x180010a99  jmp     loc_180010C45
0x180010a9e  mov     edi, [rbp+arg_10]
0x180010aa1  test    edi, edi
0x180010aa3  jg      short loc_180010AC5
0x180010aa5  mov     rcx, [rbp+arg_18]
0x180010aa9  test    rcx, rcx
0x180010aac  jz      short loc_180010ABB
0x180010aae  mov     rax, [rcx]
0x180010ab1  mov     rax, [rax+10h]
0x180010ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aba  nop
0x180010abb  mov     eax, 4B6h
0x180010ac0  jmp     loc_180010C45
0x180010ac5  imul    rcx, rdi, 0CAh
0x180010acc  mov     eax, 0FFFFFFFFh
0x180010ad1  cmp     rcx, rax
0x180010ad4  ja      loc_180010C2A
0x180010ada  add     ecx, 4; Size
0x180010add  cmp     ecx, 4
0x180010ae0  jb      loc_180010C28
0x180010ae6  mov     ebx, ecx
0x180010ae8  call    WwanMemAlloc
0x180010aed  mov     [r15+20h], rax
0x180010af1  test    rax, rax
0x180010af4  jnz     short loc_180010B16
0x180010af6  call    cs:__imp_GetLastError
0x180010afc  mov     ebx, eax
0x180010afe  mov     rcx, [rbp+arg_18]
0x180010b02  test    rcx, rcx
0x180010b05  jz      short loc_180010B14
0x180010b07  mov     rdx, [rcx]
0x180010b0a  mov     rax, [rdx+10h]
0x180010b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b13  nop
0x180010b14  jmp     short loc_180010A97
0x180010b16  mov     r8, rbx; Size
0x180010b19  xor     edx, edx; Val
0x180010b1b  mov     rcx, rax; void *
0x180010b1e  call    memset_0
0x180010b23  xor     esi, esi
0x180010b25  mov     rbx, [rbp+arg_18]
0x180010b29  test    edi, edi
0x180010b2b  jle     short loc_180010BAC
0x180010b2d  mov     [rbp+var_10], 0
0x180010b35  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x180010b39  mov     edx, esi; int
0x180010b3b  mov     rcx, rbx; struct IXMLDOMNodeList *
0x180010b3e  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x180010b43  mov     r14d, eax
0x180010b46  test    eax, eax
0x180010b48  jnz     loc_180010BF8
0x180010b4e  movsxd  rax, esi
0x180010b51  imul    rdx, rax, 0CAh
0x180010b58  mov     r8, [r15+20h]
0x180010b5c  add     r8, 4
0x180010b60  add     r8, rdx; unsigned __int16 *
0x180010b63  mov     [rsp+50h+var_20], 0; int *
0x180010b6c  mov     [rsp+50h+var_28], 0; unsigned __int16 *
0x180010b75  mov     [rsp+50h+var_30], r14d; int
0x180010b7a  xor     edx, edx; unsigned __int16 *
0x180010b7c  lea     r9d, [r14+65h]; unsigned __int64
0x180010b80  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x180010b84  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x180010b89  mov     r14d, eax
0x180010b8c  test    eax, eax
0x180010b8e  jnz     short loc_180010BCB
0x180010b90  mov     rcx, [rbp+var_10]
0x180010b94  test    rcx, rcx
0x180010b97  jz      short loc_180010BA6
0x180010b99  mov     rax, [rcx]
0x180010b9c  mov     rax, [rax+10h]
0x180010ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ba5  nop
0x180010ba6  inc     esi
0x180010ba8  cmp     esi, edi
0x180010baa  jl      short loc_180010B2D
0x180010bac  mov     rax, [r15+20h]
0x180010bb0  mov     [rax], edi
0x180010bb2  test    rbx, rbx
0x180010bb5  jz      short loc_180010BC7
0x180010bb7  mov     rax, [rbx]
0x180010bba  mov     rcx, rbx
0x180010bbd  mov     rax, [rax+10h]
0x180010bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bc6  nop
0x180010bc7  xor     eax, eax
0x180010bc9  jmp     short loc_180010C45
0x180010bcb  mov     rcx, [rbp+var_10]
0x180010bcf  test    rcx, rcx
0x180010bd2  jz      short loc_180010BE1
0x180010bd4  mov     rax, [rcx]
0x180010bd7  mov     rax, [rax+10h]
0x180010bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be0  nop
0x180010be1  test    rbx, rbx
0x180010be4  jz      short loc_180010BF6
0x180010be6  mov     rax, [rbx]
0x180010be9  mov     rcx, rbx
0x180010bec  mov     rax, [rax+10h]
0x180010bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bf5  nop
0x180010bf6  jmp     short loc_180010C23
0x180010bf8  mov     rcx, [rbp+var_10]
0x180010bfc  test    rcx, rcx
0x180010bff  jz      short loc_180010C0E
0x180010c01  mov     rax, [rcx]
0x180010c04  mov     rax, [rax+10h]
0x180010c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c0d  nop
0x180010c0e  test    rbx, rbx
0x180010c11  jz      short loc_180010C23
0x180010c13  mov     rax, [rbx]
0x180010c16  mov     rcx, rbx
0x180010c19  mov     rax, [rax+10h]
0x180010c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c22  nop
0x180010c23  mov     eax, r14d
0x180010c26  jmp     short loc_180010C45
0x180010c28  jmp     short $+2
0x180010c2a  mov     rcx, [rbp+arg_18]
0x180010c2e  test    rcx, rcx
0x180010c31  jz      short loc_180010C40
0x180010c33  mov     rax, [rcx]
0x180010c36  mov     rax, [rax+10h]
0x180010c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c3f  nop
0x180010c40  mov     eax, 57h ; 'W'
0x180010c45  mov     rbx, [rsp+50h+arg_0]
0x180010c4d  add     rsp, 50h
0x180010c51  pop     r15
0x180010c53  pop     r14
0x180010c55  pop     rdi
0x180010c56  pop     rsi
0x180010c57  pop     rbp
0x180010c58  retn
```
