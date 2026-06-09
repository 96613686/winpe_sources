# _parseRouteSelectionDescriptors(IXMLDOMNode *,WWAN_PROFILE *,int,ulong)

- ea: `0x1800114a0`
- end: `0x1800117b0`
- name: `?_parseRouteSelectionDescriptors@@YAKPEAUIXMLDOMNode@@PEAUWWAN_PROFILE@@HK@Z`
- size: `784`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct WWAN_PROFILE *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180001694`
- `0x180002034`
- `0x180011164`
- `0x1800114a0`
- `0x1800127d0`
- `0x1800130e0`
- `0x1800134f8`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011564`

## string_xrefs

- `0x1800114cf`: `MBNProfileV9:RouteSelectionDescriptor`
- `0x1800114d8`: `MBNProfileV4:RouteSelectionDescriptor`
- `0x1800114df`: `MBNProfile:RouteSelectionDescriptor`

## pseudocode

```c
__int64 __fastcall _parseRouteSelectionDescriptors(
        struct IXMLDOMNode *a1,
        struct WWAN_PROFILE *a2,
        __int64 a3,
        unsigned int a4)
{
  const unsigned __int16 *v6; // rdx
  unsigned int Nodes; // ebx
  struct IXMLDOMNodeList *v9; // rbx
  int v10; // r14d
  size_t v11; // rcx
  size_t v12; // rdi
  void *v13; // rax
  DWORD LastError; // edi
  int v15; // edi
  unsigned int Item; // r15d
  unsigned int v17; // r12d
  __int64 v18; // r9
  _BYTE *v19; // rcx
  unsigned __int8 v20; // dl
  __int128 v21; // xmm2
  __int128 v22; // xmm3
  __int64 v23; // xmm4_8
  int v24; // r11d
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // rax
  struct IXMLDOMNode *v28; // [rsp+20h] [rbp-18h] BYREF
  struct IXMLDOMNodeList *v29; // [rsp+28h] [rbp-10h] BYREF
  int v30; // [rsp+98h] [rbp+60h] BYREF

  v30 = 0;
  v29 = 0;
  if ( a4 < 3 )
  {
    v6 = L"MBNProfileV4:RouteSelectionDescriptor";
    if ( a4 != 2 )
      v6 = L"MBNProfile:RouteSelectionDescriptor";
  }
  else
  {
    v6 = L"MBNProfileV9:RouteSelectionDescriptor";
  }
  Nodes = XcGetNodes(a1, v6, &v29, &v30);
  if ( Nodes )
  {
    if ( v29 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v29->lpVtbl->Release)(v29);
    return Nodes;
  }
  v9 = v29;
  v10 = v30;
  if ( v30 <= 0 )
    goto LABEL_33;
  if ( 40 * (unsigned __int64)(unsigned int)v30 > 0xFFFFFFFF
    || (v11 = (unsigned int)(40 * v30 + 8), (unsigned int)v11 < 8) )
  {
    if ( v29 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v29->lpVtbl->Release)(v29);
    return 87;
  }
  v12 = (unsigned int)v11;
  v13 = (void *)WwanMemAlloc(v11);
  *((_QWORD *)a2 + 789) = v13;
  if ( !v13 )
  {
    LastError = GetLastError();
    if ( v9 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v9->lpVtbl->Release)(v9);
    return LastError;
  }
  memset_0(v13, 0, v12);
  if ( v10 <= 0 )
  {
LABEL_32:
    **((_DWORD **)a2 + 789) = v10;
LABEL_33:
    if ( v9 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v9->lpVtbl->Release)(v9);
    return 0;
  }
  v15 = 0;
  while ( 1 )
  {
    v28 = 0;
    Item = XcGetItem(v9, v15, &v28);
    if ( Item )
    {
      if ( v28 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
      if ( v9 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v9->lpVtbl->Release)(v9);
      return Item;
    }
    v17 = _parseRSDNode(v28, (struct ROUTE_SELECTION_DESCRIPTOR *)(*((_QWORD *)a2 + 789) + 8LL + 40LL * v15), a4);
    if ( v17 )
    {
      if ( v28 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
      if ( v9 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v9->lpVtbl->Release)(v9);
      return v17;
    }
    if ( v15 > 0 )
      break;
LABEL_29:
    if ( v28 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
    if ( ++v15 >= v10 )
      goto LABEL_32;
  }
  v18 = 0;
  v19 = (_BYTE *)*((_QWORD *)a2 + 789);
  v20 = v19[40 * v15 + 8];
  while ( v19[40 * v18 + 8] != v20 )
  {
    if ( v19[40 * v18 + 8] > v20 )
    {
      v21 = *(_OWORD *)&v19[40 * v15 + 8];
      v22 = *(_OWORD *)&v19[40 * v15 + 24];
      v23 = *(_QWORD *)&v19[40 * v15 + 40];
      v24 = v15;
      do
      {
        v25 = *((_QWORD *)a2 + 789);
        v26 = 5LL * v24;
        *(_OWORD *)(v25 + 8 * v26 + 8) = *(_OWORD *)(v25 + 40LL * v24 - 32);
        *(_OWORD *)(v25 + 8 * v26 + 24) = *(_OWORD *)(v25 + 40LL * v24 - 16);
        *(_QWORD *)(v25 + 8 * v26 + 40) = *(_QWORD *)(v25 + 40LL * v24--);
      }
      while ( v24 > (int)v18 );
      v27 = *((_QWORD *)a2 + 789);
      *(_OWORD *)(v27 + 40 * v18 + 8) = v21;
      *(_OWORD *)(v27 + 40 * v18 + 24) = v22;
      *(_QWORD *)(v27 + 40 * v18 + 40) = v23;
      goto LABEL_29;
    }
    v18 = (unsigned int)(v18 + 1);
    if ( (int)v18 >= v15 )
      goto LABEL_29;
  }
  if ( v19 )
    operator delete(v19);
  *((_QWORD *)a2 + 789) = 0;
  if ( v28 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
  if ( v9 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v9->lpVtbl->Release)(v9);
  return 1206;
}

```

## disassembly

```asm
0x1800114a0  push    rbp
0x1800114a2  push    rbx
0x1800114a3  push    rsi
0x1800114a4  push    rdi
0x1800114a5  push    r12
0x1800114a7  push    r13
0x1800114a9  push    r14
0x1800114ab  push    r15
0x1800114ad  mov     rbp, rsp
0x1800114b0  sub     rsp, 38h
0x1800114b4  mov     r13d, r9d
0x1800114b7  mov     rsi, rdx
0x1800114ba  mov     [rbp+arg_18], 0
0x1800114c1  mov     [rbp+var_10], 0
0x1800114c9  cmp     r9d, 3
0x1800114cd  jb      short loc_1800114D8
0x1800114cf  lea     rdx, aMbnprofilev9Ro_0; "MBNProfileV9:RouteSelectionDescriptor"
0x1800114d6  jmp     short loc_1800114EE
0x1800114d8  lea     rdx, aMbnprofilev4Ro_0; "MBNProfileV4:RouteSelectionDescriptor"
0x1800114df  lea     rax, aMbnprofileRout_0; "MBNProfile:RouteSelectionDescriptor"
0x1800114e6  cmp     r13d, 2
0x1800114ea  cmovnz  rdx, rax; unsigned __int16 *
0x1800114ee  lea     r9, [rbp+arg_18]; int *
0x1800114f2  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x1800114f6  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x1800114fb  mov     ebx, eax
0x1800114fd  test    eax, eax
0x1800114ff  jz      short loc_18001151E
0x180011501  mov     rcx, [rbp+var_10]
0x180011505  test    rcx, rcx
0x180011508  jz      short loc_180011517
0x18001150a  mov     rdx, [rcx]
0x18001150d  mov     rax, [rdx+10h]
0x180011511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011516  nop
0x180011517  mov     eax, ebx
0x180011519  jmp     loc_1800116D1
0x18001151e  mov     rbx, [rbp+var_10]
0x180011522  mov     r14d, [rbp+arg_18]
0x180011526  test    r14d, r14d
0x180011529  jle     loc_1800116BA
0x18001152f  lea     rcx, [r14+r14*4]
0x180011533  shl     rcx, 3
0x180011537  mov     eax, 0FFFFFFFFh
0x18001153c  cmp     rcx, rax
0x18001153f  ja      loc_180011791
0x180011545  add     ecx, 8; Size
0x180011548  cmp     ecx, 8
0x18001154b  jb      loc_18001178F
0x180011551  mov     edi, ecx
0x180011553  call    WwanMemAlloc
0x180011558  mov     [rsi+18A8h], rax
0x18001155f  test    rax, rax
0x180011562  jnz     short loc_180011588
0x180011564  call    cs:__imp_GetLastError
0x18001156a  mov     edi, eax
0x18001156c  test    rbx, rbx
0x18001156f  jz      short loc_180011581
0x180011571  mov     rcx, [rbx]
0x180011574  mov     rax, [rcx+10h]
0x180011578  mov     rcx, rbx
0x18001157b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011580  nop
0x180011581  mov     eax, edi
0x180011583  jmp     loc_1800116D1
0x180011588  mov     r8, rdi; Size
0x18001158b  xor     edx, edx; Val
0x18001158d  mov     rcx, rax; void *
0x180011590  call    memset_0
0x180011595  test    r14d, r14d
0x180011598  jle     loc_1800116B0
0x18001159e  xor     edi, edi
0x1800115a0  mov     [rbp+var_18], 0
0x1800115a8  lea     r8, [rbp+var_18]; struct IXMLDOMNode **
0x1800115ac  mov     edx, edi; int
0x1800115ae  mov     rcx, rbx; struct IXMLDOMNodeList *
0x1800115b1  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x1800115b6  mov     r15d, eax
0x1800115b9  test    eax, eax
0x1800115bb  jnz     loc_18001175C
0x1800115c1  movsxd  rax, edi
0x1800115c4  lea     r15, [rax+rax*4]
0x1800115c8  mov     rdx, [rsi+18A8h]
0x1800115cf  add     rdx, 8
0x1800115d3  lea     rdx, [rdx+r15*8]; struct ROUTE_SELECTION_DESCRIPTOR *
0x1800115d7  mov     r8d, r13d; unsigned int
0x1800115da  mov     rcx, [rbp+var_18]; struct IXMLDOMNode *
0x1800115de  call    ?_parseRSDNode@@YAKPEAUIXMLDOMNode@@PEAUROUTE_SELECTION_DESCRIPTOR@@K@Z; _parseRSDNode(IXMLDOMNode *,ROUTE_SELECTION_DESCRIPTOR *,ulong)
0x1800115e3  mov     r12d, eax
0x1800115e6  test    eax, eax
0x1800115e8  jnz     loc_180011729
0x1800115ee  test    edi, edi
0x1800115f0  jle     loc_18001168F
0x1800115f6  xor     r9d, r9d
0x1800115f9  mov     rcx, [rsi+18A8h]; Block
0x180011600  mov     dl, [rcx+r15*8+8]
0x180011605  lea     r10, [r9+r9*4]
0x180011609  cmp     [rcx+r10*8+8], dl
0x18001160e  jz      loc_1800116E2
0x180011614  ja      short loc_180011620
0x180011616  inc     r9d
0x180011619  cmp     r9d, edi
0x18001161c  jl      short loc_180011605
0x18001161e  jmp     short loc_18001168F
0x180011620  movups  xmm2, xmmword ptr [rcx+r15*8+8]
0x180011626  movups  xmm3, xmmword ptr [rcx+r15*8+18h]
0x18001162c  movsd   xmm4, qword ptr [rcx+r15*8+28h]
0x180011633  mov     r11d, edi
0x180011636  movsxd  rax, r11d
0x180011639  mov     r8, [rsi+18A8h]
0x180011640  lea     rcx, [rax+rax*4]
0x180011644  lea     rdx, [rax+rax*4]
0x180011648  movups  xmm0, xmmword ptr [r8+rcx*8-20h]
0x18001164e  movups  xmmword ptr [r8+rdx*8+8], xmm0
0x180011654  movups  xmm1, xmmword ptr [r8+rcx*8-10h]
0x18001165a  movups  xmmword ptr [r8+rdx*8+18h], xmm1
0x180011660  movsd   xmm0, qword ptr [r8+rcx*8]
0x180011666  movsd   qword ptr [r8+rdx*8+28h], xmm0
0x18001166d  dec     r11d
0x180011670  cmp     r11d, r9d
0x180011673  jg      short loc_180011636
0x180011675  mov     rax, [rsi+18A8h]
0x18001167c  movups  xmmword ptr [rax+r10*8+8], xmm2
0x180011682  movups  xmmword ptr [rax+r10*8+18h], xmm3
0x180011688  movsd   qword ptr [rax+r10*8+28h], xmm4
0x18001168f  mov     rcx, [rbp+var_18]
0x180011693  test    rcx, rcx
0x180011696  jz      short loc_1800116A5
0x180011698  mov     rax, [rcx]
0x18001169b  mov     rax, [rax+10h]
0x18001169f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a4  nop
0x1800116a5  inc     edi
0x1800116a7  cmp     edi, r14d
0x1800116aa  jl      loc_1800115A0
0x1800116b0  mov     rax, [rsi+18A8h]
0x1800116b7  mov     [rax], r14d
0x1800116ba  test    rbx, rbx
0x1800116bd  jz      short loc_1800116CF
0x1800116bf  mov     rax, [rbx]
0x1800116c2  mov     rcx, rbx
0x1800116c5  mov     rax, [rax+10h]
0x1800116c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116ce  nop
0x1800116cf  xor     eax, eax
0x1800116d1  add     rsp, 38h
0x1800116d5  pop     r15
0x1800116d7  pop     r14
0x1800116d9  pop     r13
0x1800116db  pop     r12
0x1800116dd  pop     rdi
0x1800116de  pop     rsi
0x1800116df  pop     rbx
0x1800116e0  pop     rbp
0x1800116e1  retn
0x1800116e2  test    rcx, rcx
0x1800116e5  jz      short loc_1800116EC
0x1800116e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800116ec  mov     qword ptr [rsi+18A8h], 0
0x1800116f7  mov     rcx, [rbp+var_18]
0x1800116fb  test    rcx, rcx
0x1800116fe  jz      short loc_18001170D
0x180011700  mov     rax, [rcx]
0x180011703  mov     rax, [rax+10h]
0x180011707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001170c  nop
0x18001170d  test    rbx, rbx
0x180011710  jz      short loc_180011722
0x180011712  mov     rax, [rbx]
0x180011715  mov     rcx, rbx
0x180011718  mov     rax, [rax+10h]
0x18001171c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011721  nop
0x180011722  mov     eax, 4B6h
0x180011727  jmp     short loc_1800116D1
0x180011729  mov     rcx, [rbp+var_18]
0x18001172d  test    rcx, rcx
0x180011730  jz      short loc_18001173F
0x180011732  mov     rax, [rcx]
0x180011735  mov     rax, [rax+10h]
0x180011739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001173e  nop
0x18001173f  test    rbx, rbx
0x180011742  jz      short loc_180011754
0x180011744  mov     rax, [rbx]
0x180011747  mov     rcx, rbx
0x18001174a  mov     rax, [rax+10h]
0x18001174e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011753  nop
0x180011754  mov     eax, r12d
0x180011757  jmp     loc_1800116D1
0x18001175c  mov     rcx, [rbp+var_18]
0x180011760  test    rcx, rcx
0x180011763  jz      short loc_180011772
0x180011765  mov     rax, [rcx]
0x180011768  mov     rax, [rax+10h]
0x18001176c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011771  nop
0x180011772  test    rbx, rbx
0x180011775  jz      short loc_180011787
0x180011777  mov     rax, [rbx]
0x18001177a  mov     rcx, rbx
0x18001177d  mov     rax, [rax+10h]
0x180011781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011786  nop
0x180011787  mov     eax, r15d
0x18001178a  jmp     loc_1800116D1
0x18001178f  jmp     short $+2
0x180011791  test    rbx, rbx
0x180011794  jz      short loc_1800117A6
0x180011796  mov     rax, [rbx]
0x180011799  mov     rcx, rbx
0x18001179c  mov     rax, [rax+10h]
0x1800117a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a5  nop
0x1800117a6  mov     eax, 57h ; 'W'
0x1800117ab  jmp     loc_1800116D1
```
