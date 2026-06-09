# _parseDataRoamingProviderListNode

- ea: `0x18000b880`
- end: `0x18000ba89`
- name: `_parseDataRoamingProviderListNode`
- size: `521`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, _QWORD *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000b880`
- `0x18000bf80`
- `0x1800127d0`
- `0x1800130e0`
- `0x1800134f8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b950`

## pseudocode

```c
__int64 __fastcall parseDataRoamingProviderListNode(struct IXMLDOMNode *a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  const unsigned __int16 *v5; // rdx
  DWORD Nodes; // ebx
  int v8; // edi
  int *v9; // rax
  int v10; // esi
  struct IXMLDOMNodeList *v11; // rbx
  unsigned int Item; // r14d
  struct IXMLDOMNodeList *v13; // [rsp+20h] [rbp-10h] BYREF
  struct IXMLDOMNode *v14; // [rsp+28h] [rbp-8h] BYREF
  int v15; // [rsp+78h] [rbp+48h] BYREF

  v15 = 0;
  v13 = 0;
  if ( a4 < 3 )
  {
    v5 = L"MBNProfileV4:Provider";
    if ( a4 != 2 )
      v5 = L"MBNProfile:Provider";
  }
  else
  {
    v5 = L"MBNProfileV9:Provider";
  }
  Nodes = XcGetNodes(a1, v5, &v13, &v15);
  if ( Nodes )
  {
    if ( v13 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v13->lpVtbl->Release)(v13);
    return Nodes;
  }
  v8 = v15;
  if ( v15 > 0 )
  {
    if ( 56 * (unsigned __int64)(unsigned int)v15 > 0xFFFFFFFF )
    {
      if ( v13 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v13->lpVtbl->Release)(v13);
      return 87;
    }
    else
    {
      v9 = (int *)WwanMemAlloc((unsigned int)(56 * v15 + 4));
      a2[559] = v9;
      if ( !v9 )
      {
        Nodes = GetLastError();
        if ( v13 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v13->lpVtbl->Release)(v13);
        return Nodes;
      }
      *v9 = v8;
      v10 = 0;
      v11 = v13;
      if ( v8 <= 0 )
      {
LABEL_24:
        if ( v11 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v11->lpVtbl->Release)(v11);
        return 0;
      }
      else
      {
        while ( 1 )
        {
          v14 = 0;
          Item = XcGetItem(v11, v10, &v14);
          if ( Item )
            break;
          Item = parseProviderNode(v14, (unsigned __int16 *)(a2[559] + 4LL + 56LL * v10));
          if ( Item )
          {
            if ( v14 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNodeList *))v11->lpVtbl->Release)(v11);
            return Item;
          }
          if ( v14 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
          if ( ++v10 >= v8 )
            goto LABEL_24;
        }
        if ( v14 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
        if ( v11 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v11->lpVtbl->Release)(v11);
        return Item;
      }
    }
  }
  else
  {
    if ( v13 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v13->lpVtbl->Release)(v13);
    return 1206;
  }
}

```

## disassembly

```asm
0x18000b880  mov     [rsp-28h+arg_0], rbx
0x18000b885  mov     [rsp-28h+arg_8], rsi
0x18000b88a  push    rbp
0x18000b88b  push    rdi
0x18000b88c  push    r13
0x18000b88e  push    r14
0x18000b890  push    r15
0x18000b892  mov     rbp, rsp
0x18000b895  sub     rsp, 30h
0x18000b899  mov     r15d, r9d
0x18000b89c  mov     r13, rdx
0x18000b89f  mov     [rbp+arg_18], 0
0x18000b8a6  mov     [rbp+var_10], 0
0x18000b8ae  cmp     r9d, 3
0x18000b8b2  jb      short loc_18000B8BD
0x18000b8b4  lea     rdx, aMbnprofilev9Pr_0; "MBNProfileV9:Provider"
0x18000b8bb  jmp     short loc_18000B8D3
0x18000b8bd  lea     rdx, aMbnprofilev4Pr_2; "MBNProfileV4:Provider"
0x18000b8c4  lea     rax, aMbnprofileProv_0; "MBNProfile:Provider"
0x18000b8cb  cmp     r15d, 2
0x18000b8cf  cmovnz  rdx, rax; unsigned __int16 *
0x18000b8d3  lea     r9, [rbp+arg_18]; int *
0x18000b8d7  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x18000b8db  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000b8e0  mov     ebx, eax
0x18000b8e2  test    eax, eax
0x18000b8e4  jz      short loc_18000B903
0x18000b8e6  mov     rcx, [rbp+var_10]
0x18000b8ea  test    rcx, rcx
0x18000b8ed  jz      short loc_18000B8FC
0x18000b8ef  mov     rdx, [rcx]
0x18000b8f2  mov     rax, [rdx+10h]
0x18000b8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8fb  nop
0x18000b8fc  mov     eax, ebx
0x18000b8fe  jmp     loc_18000BA72
0x18000b903  mov     edi, [rbp+arg_18]
0x18000b906  test    edi, edi
0x18000b908  jg      short loc_18000B92A
0x18000b90a  mov     rcx, [rbp+var_10]
0x18000b90e  test    rcx, rcx
0x18000b911  jz      short loc_18000B920
0x18000b913  mov     rax, [rcx]
0x18000b916  mov     rax, [rax+10h]
0x18000b91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b91f  nop
0x18000b920  mov     eax, 4B6h
0x18000b925  jmp     loc_18000BA72
0x18000b92a  imul    rax, rdi, 38h ; '8'
0x18000b92e  mov     ecx, 0FFFFFFFFh
0x18000b933  cmp     rax, rcx
0x18000b936  ja      loc_18000BA57
0x18000b93c  lea     ecx, [rax+4]; Size
0x18000b93f  call    WwanMemAlloc
0x18000b944  mov     [r13+1178h], rax
0x18000b94b  test    rax, rax
0x18000b94e  jnz     short loc_18000B970
0x18000b950  call    cs:__imp_GetLastError
0x18000b956  mov     ebx, eax
0x18000b958  mov     rcx, [rbp+var_10]
0x18000b95c  test    rcx, rcx
0x18000b95f  jz      short loc_18000B96E
0x18000b961  mov     rdx, [rcx]
0x18000b964  mov     rax, [rdx+10h]
0x18000b968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b96d  nop
0x18000b96e  jmp     short loc_18000B8FC
0x18000b970  mov     [rax], edi
0x18000b972  xor     esi, esi
0x18000b974  mov     rbx, [rbp+var_10]
0x18000b978  test    edi, edi
0x18000b97a  jle     short loc_18000B9E1
0x18000b97c  mov     [rbp+var_8], 0
0x18000b984  lea     r8, [rbp+var_8]; struct IXMLDOMNode **
0x18000b988  mov     edx, esi; int
0x18000b98a  mov     rcx, rbx; struct IXMLDOMNodeList *
0x18000b98d  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x18000b992  mov     r14d, eax
0x18000b995  test    eax, eax
0x18000b997  jnz     loc_18000BA27
0x18000b99d  movsxd  rax, esi
0x18000b9a0  imul    rdx, rax, 38h ; '8'
0x18000b9a4  mov     rax, [r13+1178h]
0x18000b9ab  add     rax, 4
0x18000b9af  add     rdx, rax; unsigned __int16 *
0x18000b9b2  mov     r8d, r15d
0x18000b9b5  mov     rcx, [rbp+var_8]; struct IXMLDOMNode *
0x18000b9b9  call    _parseProviderNode
0x18000b9be  mov     r14d, eax
0x18000b9c1  test    eax, eax
0x18000b9c3  jnz     short loc_18000B9FA
0x18000b9c5  mov     rcx, [rbp+var_8]
0x18000b9c9  test    rcx, rcx
0x18000b9cc  jz      short loc_18000B9DB
0x18000b9ce  mov     rax, [rcx]
0x18000b9d1  mov     rax, [rax+10h]
0x18000b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9da  nop
0x18000b9db  inc     esi
0x18000b9dd  cmp     esi, edi
0x18000b9df  jl      short loc_18000B97C
0x18000b9e1  test    rbx, rbx
0x18000b9e4  jz      short loc_18000B9F6
0x18000b9e6  mov     rax, [rbx]
0x18000b9e9  mov     rcx, rbx
0x18000b9ec  mov     rax, [rax+10h]
0x18000b9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f5  nop
0x18000b9f6  xor     eax, eax
0x18000b9f8  jmp     short loc_18000BA72
0x18000b9fa  mov     rcx, [rbp+var_8]
0x18000b9fe  test    rcx, rcx
0x18000ba01  jz      short loc_18000BA10
0x18000ba03  mov     rax, [rcx]
0x18000ba06  mov     rax, [rax+10h]
0x18000ba0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba0f  nop
0x18000ba10  test    rbx, rbx
0x18000ba13  jz      short loc_18000BA25
0x18000ba15  mov     rax, [rbx]
0x18000ba18  mov     rcx, rbx
0x18000ba1b  mov     rax, [rax+10h]
0x18000ba1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba24  nop
0x18000ba25  jmp     short loc_18000BA52
0x18000ba27  mov     rcx, [rbp+var_8]
0x18000ba2b  test    rcx, rcx
0x18000ba2e  jz      short loc_18000BA3D
0x18000ba30  mov     rax, [rcx]
0x18000ba33  mov     rax, [rax+10h]
0x18000ba37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba3c  nop
0x18000ba3d  test    rbx, rbx
0x18000ba40  jz      short loc_18000BA52
0x18000ba42  mov     rax, [rbx]
0x18000ba45  mov     rcx, rbx
0x18000ba48  mov     rax, [rax+10h]
0x18000ba4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba51  nop
0x18000ba52  mov     eax, r14d
0x18000ba55  jmp     short loc_18000BA72
0x18000ba57  mov     rcx, [rbp+var_10]
0x18000ba5b  test    rcx, rcx
0x18000ba5e  jz      short loc_18000BA6D
0x18000ba60  mov     rax, [rcx]
0x18000ba63  mov     rax, [rax+10h]
0x18000ba67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba6c  nop
0x18000ba6d  mov     eax, 57h ; 'W'
0x18000ba72  mov     rbx, [rsp+30h+arg_0]
0x18000ba77  mov     rsi, [rsp+30h+arg_8]
0x18000ba7c  add     rsp, 30h
0x18000ba80  pop     r15
0x18000ba82  pop     r14
0x18000ba84  pop     r13
0x18000ba86  pop     rdi
0x18000ba87  pop     rbp
0x18000ba88  retn
```
