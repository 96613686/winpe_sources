# _generateRouteSelectionDescriptorsNode(IXMLDOMDocument2 *,IXMLDOMNode *,ROUTE_SELECTION_DESCRIPTOR_LIST *,ulong)

- ea: `0x1800100ac`
- end: `0x180010274`
- name: `?_generateRouteSelectionDescriptorsNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUROUTE_SELECTION_DESCRIPTOR_LIST@@K@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct ROUTE_SELECTION_DESCRIPTOR_LIST *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a298`

## callees

- `0x18000fc08`
- `0x1800100ac`
- `0x180011f90`
- `0x180014010`

## string_xrefs

- `0x1800100da`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18001015b`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x1800100e3`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x180010164`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x1800100cd`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x1800101e2`: `http://www.microsoft.com/networking/WWAN/profile/v1`
- `0x180010104`: `RouteSelectionDescriptors`
- `0x180010185`: `RouteSelectionDescriptor`

## pseudocode

```c
__int64 __fastcall _generateRouteSelectionDescriptorsNode(
        struct IXMLDOMDocument2 *a1,
        struct IXMLDOMNode *a2,
        struct ROUTE_SELECTION_DESCRIPTOR_LIST *a3,
        unsigned int a4)
{
  OLECHAR *v7; // r9
  unsigned int v8; // ebx
  struct IXMLDOMNode *v10; // rbx
  __int64 v11; // rsi
  OLECHAR *v12; // r9
  unsigned int v13; // edi
  struct IXMLDOMNode *v14; // rdi
  unsigned int RSDNode; // r15d
  struct IXMLDOMNode *v16; // [rsp+30h] [rbp-48h] BYREF
  struct IXMLDOMNode *v17; // [rsp+38h] [rbp-40h] BYREF

  v16 = 0;
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
  v8 = XcAddChildElement(a1, a2, (OLECHAR *)L"RouteSelectionDescriptors", v7, 0, &v16);
  if ( v8 )
  {
    if ( v16 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
    return v8;
  }
  else
  {
    v10 = v16;
    if ( a3 && (v11 = 0, *(_DWORD *)a3) )
    {
      while ( 1 )
      {
        v17 = 0;
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
        v13 = XcAddChildElement(a1, v10, (OLECHAR *)L"RouteSelectionDescriptor", v12, 0, &v17);
        if ( v13 )
          break;
        v14 = v17;
        RSDNode = _generateRSDNode(
                    a1,
                    v17,
                    (struct ROUTE_SELECTION_DESCRIPTOR_LIST *)((char *)a3 + 32 * v11 + 8 * (unsigned int)v11 + 8),
                    a4);
        if ( RSDNode )
        {
          if ( v14 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
          if ( v10 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
          return RSDNode;
        }
        if ( v14 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v14->lpVtbl->Release)(v14);
        v11 = (unsigned int)(v11 + 1);
        if ( (unsigned int)v11 >= *(_DWORD *)a3 )
          goto LABEL_20;
      }
      if ( v17 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return v13;
    }
    else
    {
LABEL_20:
      if ( v10 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800100ac  push    rbx
0x1800100ae  push    rbp
0x1800100af  push    rsi
0x1800100b0  push    rdi
0x1800100b1  push    r12
0x1800100b3  push    r14
0x1800100b5  push    r15
0x1800100b7  sub     rsp, 40h
0x1800100bb  mov     ebp, r9d
0x1800100be  mov     r14, r8
0x1800100c1  mov     r12, rcx
0x1800100c4  mov     [rsp+78h+var_48], 0
0x1800100cd  lea     rdi, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800100d4  cmp     r9d, 3
0x1800100d8  jb      short loc_1800100E3
0x1800100da  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x1800100e1  jmp     short loc_1800100F1
0x1800100e3  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x1800100ea  cmp     ebp, 2
0x1800100ed  cmovnz  r9, rdi; OLECHAR *
0x1800100f1  lea     rax, [rsp+78h+var_48]
0x1800100f6  mov     [rsp+78h+var_50], rax; struct IXMLDOMNode **
0x1800100fb  mov     [rsp+78h+var_58], 0; OLECHAR *
0x180010104  lea     r8, aRouteselection; "RouteSelectionDescriptors"
0x18001010b  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180010110  mov     ebx, eax
0x180010112  test    eax, eax
0x180010114  jz      short loc_180010134
0x180010116  mov     rcx, [rsp+78h+var_48]
0x18001011b  test    rcx, rcx
0x18001011e  jz      short loc_18001012D
0x180010120  mov     rdx, [rcx]
0x180010123  mov     rax, [rdx+10h]
0x180010127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001012c  nop
0x18001012d  mov     eax, ebx
0x18001012f  jmp     loc_180010206
0x180010134  mov     rbx, [rsp+78h+var_48]
0x180010139  test    r14, r14
0x18001013c  jz      loc_1800101EF
0x180010142  xor     esi, esi
0x180010144  cmp     [r14], esi
0x180010147  jbe     loc_1800101EF
0x18001014d  mov     [rsp+78h+var_40], 0
0x180010156  cmp     ebp, 3
0x180010159  jb      short loc_180010164
0x18001015b  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x180010162  jmp     short loc_180010172
0x180010164  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18001016b  cmp     ebp, 2
0x18001016e  cmovnz  r9, rdi; OLECHAR *
0x180010172  lea     rax, [rsp+78h+var_40]
0x180010177  mov     [rsp+78h+var_50], rax; struct IXMLDOMNode **
0x18001017c  mov     [rsp+78h+var_58], 0; OLECHAR *
0x180010185  lea     r8, aRouteselection_1; "RouteSelectionDescriptor"
0x18001018c  mov     rdx, rbx; struct IXMLDOMNode *
0x18001018f  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180010192  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180010197  mov     edi, eax
0x180010199  test    eax, eax
0x18001019b  jnz     loc_180010244
0x1800101a1  mov     ecx, esi
0x1800101a3  inc     rcx
0x1800101a6  lea     rcx, [rcx+rsi*4]
0x1800101aa  lea     r8, [r14+rcx*8]; struct ROUTE_SELECTION_DESCRIPTOR *
0x1800101ae  mov     r9d, ebp; unsigned int
0x1800101b1  mov     rdi, [rsp+78h+var_40]
0x1800101b6  mov     rdx, rdi; struct IXMLDOMNode *
0x1800101b9  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800101bc  call    ?_generateRSDNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAUROUTE_SELECTION_DESCRIPTOR@@K@Z; _generateRSDNode(IXMLDOMDocument2 *,IXMLDOMNode *,ROUTE_SELECTION_DESCRIPTOR *,ulong)
0x1800101c1  mov     r15d, eax
0x1800101c4  test    eax, eax
0x1800101c6  jnz     short loc_180010215
0x1800101c8  test    rdi, rdi
0x1800101cb  jz      short loc_1800101DD
0x1800101cd  mov     rax, [rdi]
0x1800101d0  mov     rcx, rdi
0x1800101d3  mov     rax, [rax+10h]
0x1800101d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101dc  nop
0x1800101dd  inc     esi
0x1800101df  cmp     esi, [r14]
0x1800101e2  lea     rdi, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WWA"...
0x1800101e9  jb      loc_18001014D
0x1800101ef  test    rbx, rbx
0x1800101f2  jz      short loc_180010204
0x1800101f4  mov     rax, [rbx]
0x1800101f7  mov     rcx, rbx
0x1800101fa  mov     rax, [rax+10h]
0x1800101fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010203  nop
0x180010204  xor     eax, eax
0x180010206  add     rsp, 40h
0x18001020a  pop     r15
0x18001020c  pop     r14
0x18001020e  pop     r12
0x180010210  pop     rdi
0x180010211  pop     rsi
0x180010212  pop     rbp
0x180010213  pop     rbx
0x180010214  retn
0x180010215  test    rdi, rdi
0x180010218  jz      short loc_18001022A
0x18001021a  mov     rax, [rdi]
0x18001021d  mov     rcx, rdi
0x180010220  mov     rax, [rax+10h]
0x180010224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010229  nop
0x18001022a  test    rbx, rbx
0x18001022d  jz      short loc_18001023F
0x18001022f  mov     rax, [rbx]
0x180010232  mov     rcx, rbx
0x180010235  mov     rax, [rax+10h]
0x180010239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001023e  nop
0x18001023f  mov     eax, r15d
0x180010242  jmp     short loc_180010206
0x180010244  mov     rcx, [rsp+78h+var_40]
0x180010249  test    rcx, rcx
0x18001024c  jz      short loc_18001025B
0x18001024e  mov     rax, [rcx]
0x180010251  mov     rax, [rax+10h]
0x180010255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001025a  nop
0x18001025b  test    rbx, rbx
0x18001025e  jz      short loc_180010270
0x180010260  mov     rax, [rbx]
0x180010263  mov     rcx, rbx
0x180010266  mov     rax, [rax+10h]
0x18001026a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001026f  nop
0x180010270  mov     eax, edi
0x180010272  jmp     short loc_180010206
```
