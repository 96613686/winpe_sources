# _parseSNSSAIs

- ea: `0x180011974`
- end: `0x180011b9a`
- name: `_parseSNSSAIs`
- size: `550`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180011164`

## callees

- `0x180002034`
- `0x1800117b8`
- `0x180011974`
- `0x1800127d0`
- `0x1800130e0`
- `0x1800134f8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a50`

## pseudocode

```c
__int64 __fastcall parseSNSSAIs(struct IXMLDOMNode *a1, __int64 a2, unsigned int a3)
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
  struct IXMLDOMNode *v14; // [rsp+20h] [rbp-10h] BYREF
  int v15; // [rsp+70h] [rbp+40h] BYREF
  struct IXMLDOMNodeList *v16; // [rsp+78h] [rbp+48h] BYREF

  v15 = 0;
  v16 = 0;
  if ( a3 < 3 )
  {
    v4 = L"MBNProfileV4:SNSSAI";
    if ( a3 != 2 )
      v4 = L"MBNProfile:SNSSAI";
  }
  else
  {
    v4 = L"MBNProfileV9:SNSSAI";
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
    if ( 20 * (unsigned __int64)(unsigned int)v15 > 0xFFFFFFFF
      || (v8 = (unsigned int)(20 * v15 + 4), (unsigned int)v8 < 4) )
    {
      if ( v16 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v16->lpVtbl->Release)(v16);
      return 87;
    }
    else
    {
      v9 = (unsigned int)v8;
      v10 = WwanMemAlloc(v8);
      *(_QWORD *)(a2 + 24) = v10;
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
        **(_DWORD **)(a2 + 24) = v7;
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
          Item = parseSNSSAINode(v14);
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
0x180011974  mov     [rsp-28h+arg_0], rbx
0x180011979  mov     [rsp-28h+arg_8], rsi
0x18001197e  push    rbp
0x18001197f  push    rdi
0x180011980  push    r13
0x180011982  push    r14
0x180011984  push    r15
0x180011986  mov     rbp, rsp
0x180011989  sub     rsp, 30h
0x18001198d  mov     r15d, r8d
0x180011990  mov     r13, rdx
0x180011993  mov     [rbp+arg_10], 0
0x18001199a  mov     [rbp+arg_18], 0
0x1800119a2  cmp     r8d, 3
0x1800119a6  jb      short loc_1800119B1
0x1800119a8  lea     rdx, aMbnprofilev9Sn_0; "MBNProfileV9:SNSSAI"
0x1800119af  jmp     short loc_1800119C7
0x1800119b1  lea     rdx, aMbnprofilev4Sn_0; "MBNProfileV4:SNSSAI"
0x1800119b8  lea     rax, aMbnprofileSnss; "MBNProfile:SNSSAI"
0x1800119bf  cmp     r15d, 2
0x1800119c3  cmovnz  rdx, rax; unsigned __int16 *
0x1800119c7  lea     r9, [rbp+arg_10]; int *
0x1800119cb  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x1800119cf  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x1800119d4  mov     ebx, eax
0x1800119d6  test    eax, eax
0x1800119d8  jz      short loc_1800119F7
0x1800119da  mov     rcx, [rbp+arg_18]
0x1800119de  test    rcx, rcx
0x1800119e1  jz      short loc_1800119F0
0x1800119e3  mov     rdx, [rcx]
0x1800119e6  mov     rax, [rdx+10h]
0x1800119ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119ef  nop
0x1800119f0  mov     eax, ebx
0x1800119f2  jmp     loc_180011B83
0x1800119f7  mov     edi, [rbp+arg_10]
0x1800119fa  test    edi, edi
0x1800119fc  jg      short loc_180011A1E
0x1800119fe  mov     rcx, [rbp+arg_18]
0x180011a02  test    rcx, rcx
0x180011a05  jz      short loc_180011A14
0x180011a07  mov     rax, [rcx]
0x180011a0a  mov     rax, [rax+10h]
0x180011a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a13  nop
0x180011a14  mov     eax, 4B6h
0x180011a19  jmp     loc_180011B83
0x180011a1e  lea     rcx, [rdi+rdi*4]
0x180011a22  shl     rcx, 2
0x180011a26  mov     eax, 0FFFFFFFFh
0x180011a2b  cmp     rcx, rax
0x180011a2e  ja      loc_180011B68
0x180011a34  add     ecx, 4; Size
0x180011a37  cmp     ecx, 4
0x180011a3a  jb      loc_180011B66
0x180011a40  mov     ebx, ecx
0x180011a42  call    WwanMemAlloc
0x180011a47  mov     [r13+18h], rax
0x180011a4b  test    rax, rax
0x180011a4e  jnz     short loc_180011A70
0x180011a50  call    cs:__imp_GetLastError
0x180011a56  mov     ebx, eax
0x180011a58  mov     rcx, [rbp+arg_18]
0x180011a5c  test    rcx, rcx
0x180011a5f  jz      short loc_180011A6E
0x180011a61  mov     rdx, [rcx]
0x180011a64  mov     rax, [rdx+10h]
0x180011a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a6d  nop
0x180011a6e  jmp     short loc_1800119F0
0x180011a70  mov     r8, rbx; Size
0x180011a73  xor     edx, edx; Val
0x180011a75  mov     rcx, rax; void *
0x180011a78  call    memset_0
0x180011a7d  xor     esi, esi
0x180011a7f  mov     rbx, [rbp+arg_18]
0x180011a83  test    edi, edi
0x180011a85  jle     short loc_180011AEA
0x180011a87  mov     [rbp+var_10], 0
0x180011a8f  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x180011a93  mov     edx, esi; int
0x180011a95  mov     rcx, rbx; struct IXMLDOMNodeList *
0x180011a98  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x180011a9d  mov     r14d, eax
0x180011aa0  test    eax, eax
0x180011aa2  jnz     loc_180011B36
0x180011aa8  movsxd  rax, esi
0x180011aab  lea     rdx, [rax+rax*4]
0x180011aaf  mov     rax, [r13+18h]
0x180011ab3  lea     rdx, [rdx+1]
0x180011ab7  lea     rdx, [rax+rdx*4]
0x180011abb  mov     r8d, r15d
0x180011abe  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x180011ac2  call    _parseSNSSAINode
0x180011ac7  mov     r14d, eax
0x180011aca  test    eax, eax
0x180011acc  jnz     short loc_180011B09
0x180011ace  mov     rcx, [rbp+var_10]
0x180011ad2  test    rcx, rcx
0x180011ad5  jz      short loc_180011AE4
0x180011ad7  mov     rax, [rcx]
0x180011ada  mov     rax, [rax+10h]
0x180011ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ae3  nop
0x180011ae4  inc     esi
0x180011ae6  cmp     esi, edi
0x180011ae8  jl      short loc_180011A87
0x180011aea  mov     rax, [r13+18h]
0x180011aee  mov     [rax], edi
0x180011af0  test    rbx, rbx
0x180011af3  jz      short loc_180011B05
0x180011af5  mov     rax, [rbx]
0x180011af8  mov     rcx, rbx
0x180011afb  mov     rax, [rax+10h]
0x180011aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b04  nop
0x180011b05  xor     eax, eax
0x180011b07  jmp     short loc_180011B83
0x180011b09  mov     rcx, [rbp+var_10]
0x180011b0d  test    rcx, rcx
0x180011b10  jz      short loc_180011B1F
0x180011b12  mov     rax, [rcx]
0x180011b15  mov     rax, [rax+10h]
0x180011b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b1e  nop
0x180011b1f  test    rbx, rbx
0x180011b22  jz      short loc_180011B34
0x180011b24  mov     rax, [rbx]
0x180011b27  mov     rcx, rbx
0x180011b2a  mov     rax, [rax+10h]
0x180011b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b33  nop
0x180011b34  jmp     short loc_180011B61
0x180011b36  mov     rcx, [rbp+var_10]
0x180011b3a  test    rcx, rcx
0x180011b3d  jz      short loc_180011B4C
0x180011b3f  mov     rax, [rcx]
0x180011b42  mov     rax, [rax+10h]
0x180011b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b4b  nop
0x180011b4c  test    rbx, rbx
0x180011b4f  jz      short loc_180011B61
0x180011b51  mov     rax, [rbx]
0x180011b54  mov     rcx, rbx
0x180011b57  mov     rax, [rax+10h]
0x180011b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b60  nop
0x180011b61  mov     eax, r14d
0x180011b64  jmp     short loc_180011B83
0x180011b66  jmp     short $+2
0x180011b68  mov     rcx, [rbp+arg_18]
0x180011b6c  test    rcx, rcx
0x180011b6f  jz      short loc_180011B7E
0x180011b71  mov     rax, [rcx]
0x180011b74  mov     rax, [rax+10h]
0x180011b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b7d  nop
0x180011b7e  mov     eax, 57h ; 'W'
0x180011b83  mov     rbx, [rsp+30h+arg_0]
0x180011b88  mov     rsi, [rsp+30h+arg_8]
0x180011b8d  add     rsp, 30h
0x180011b91  pop     r15
0x180011b93  pop     r14
0x180011b95  pop     r13
0x180011b97  pop     rdi
0x180011b98  pop     rbp
0x180011b99  retn
```
