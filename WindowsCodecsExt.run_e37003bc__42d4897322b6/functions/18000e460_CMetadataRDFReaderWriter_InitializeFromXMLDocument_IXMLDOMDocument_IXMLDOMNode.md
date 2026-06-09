# CMetadataRDFReaderWriter::InitializeFromXMLDocument(IXMLDOMDocument *,IXMLDOMNode * *)

- ea: `0x18000e460`
- end: `0x18000e823`
- name: `?InitializeFromXMLDocument@CMetadataRDFReaderWriter@@MEAAJPEAUIXMLDOMDocument@@PEAPEAUIXMLDOMNode@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct IXMLDOMDocument *, struct IXMLDOMNode **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000e460`
- `0x18000e82c`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::InitializeFromXMLDocument(
        CMetadataRDFReaderWriter *this,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode **a3)
{
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  HRESULT (__stdcall *get_nodeType)(IXMLDOMDocument *, DOMNodeType *); // rax
  int v8; // eax
  int v9; // ebx
  int v11; // ecx
  unsigned int i; // esi
  int v13; // eax
  bool v14; // zf
  __int64 v15; // [rsp+20h] [rbp-20h] BYREF
  __int64 v16; // [rsp+28h] [rbp-18h] BYREF
  struct IXMLDOMNode *v17; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+38h] [rbp-8h] BYREF
  int v19; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v20; // [rsp+88h] [rbp+48h] BYREF

  lpVtbl = a2->lpVtbl;
  v19 = 0;
  v18 = 0;
  v16 = 0;
  get_nodeType = lpVtbl->get_nodeType;
  v15 = 0;
  v17 = 0;
  v20 = 0;
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, int *))get_nodeType)(a2, &v19);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_2;
  if ( v8 )
    goto LABEL_63;
  if ( v19 != 9 )
  {
    v9 = -2003292271;
    goto LABEL_65;
  }
  v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))a2->lpVtbl->get_childNodes)(a2, &v15);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_2;
  if ( !v8 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 64LL))(v15, &v20);
    v9 = v8;
    if ( v8 < 0 )
      goto LABEL_2;
    if ( !v8 )
    {
      if ( v20 != 1 )
        goto LABEL_64;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v15 + 56LL))(v15, 0, &v17);
      v9 = v8;
      if ( v8 < 0 )
        goto LABEL_2;
      if ( !v8 )
      {
        v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, int *))v17->lpVtbl->get_nodeType)(v17, &v19);
        v9 = v8;
        if ( v8 < 0 )
          goto LABEL_2;
        if ( !v8 )
        {
          if ( v19 == 1 )
          {
            v8 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct IXMLDOMNode *))(*(_QWORD *)this + 368LL))(
                   this,
                   v17);
            v9 = v8;
            if ( v8 < 0 )
              goto LABEL_2;
            if ( v15 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              v15 = 0;
            }
            v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 *))v17->lpVtbl->get_childNodes)(v17, &v15);
            v9 = v8;
            if ( v8 < 0 )
              goto LABEL_2;
            if ( v8 )
              goto LABEL_63;
            v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 64LL))(v15, &v20);
            v9 = v8;
            if ( v8 >= 0 )
            {
              if ( !v8 )
              {
                for ( i = 0; ; ++i )
                {
                  if ( i >= v20 )
                  {
                    v9 = 0;
                    *a3 = v17;
                    v17 = 0;
                    goto LABEL_3;
                  }
                  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 56LL))(v15, i, &v16);
                  v13 = g_doStackCaptures;
                  if ( v9 < 0 )
                  {
                    if ( g_doStackCaptures )
                      goto LABEL_62;
                    goto LABEL_3;
                  }
                  if ( v9 )
                    goto LABEL_67;
                  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v16 + 80LL))(v16, &v19);
                  v13 = g_doStackCaptures;
                  if ( v9 < 0 )
                  {
                    if ( g_doStackCaptures )
                      goto LABEL_62;
                    goto LABEL_3;
                  }
                  if ( v9 )
                  {
LABEL_67:
                    v9 = -2147467259;
                    v14 = v13 == 0;
                    goto LABEL_61;
                  }
                  if ( v19 == 1 )
                  {
                    v8 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64 *))(*(_QWORD *)this + 384LL))(
                           this,
                           &v18);
                    v9 = v8;
                    if ( v8 < 0 )
                    {
                      if ( g_doStackCaptures )
                        goto LABEL_12;
                      goto LABEL_3;
                    }
                    v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 8LL))(v18, v16);
                    v9 = v8;
                    if ( v8 < 0 )
                    {
                      if ( g_doStackCaptures )
                        goto LABEL_12;
                      goto LABEL_3;
                    }
                    v8 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64))(*(_QWORD *)this + 336LL))(
                           this,
                           v18);
                    v9 = v8;
                    if ( v8 < 0 )
                    {
                      if ( g_doStackCaptures )
                        goto LABEL_12;
                      goto LABEL_3;
                    }
                    v8 = CMILObjectArray<RDFItem *>::Add((char *)this + 208, &v18);
                    v9 = v8;
                    if ( v8 < 0 )
                    {
                      if ( g_doStackCaptures )
                        goto LABEL_12;
                      goto LABEL_3;
                    }
                    ++*((_DWORD *)this + 43);
                    v18 = 0;
                  }
                  if ( v16 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                    v16 = 0;
                  }
                }
              }
              goto LABEL_63;
            }
LABEL_2:
            if ( !g_doStackCaptures )
              goto LABEL_3;
LABEL_12:
            v11 = v8;
            goto LABEL_13;
          }
LABEL_64:
          v9 = -2003292273;
          goto LABEL_65;
        }
      }
    }
  }
LABEL_63:
  v9 = -2147467259;
LABEL_65:
  v14 = g_doStackCaptures == 0;
LABEL_61:
  if ( !v14 )
  {
LABEL_62:
    v11 = v9;
LABEL_13:
    DoStackCapture(v11);
  }
LABEL_3:
  if ( v18 )
    (**(void (__fastcall ***)(__int64, __int64))v18)(v18, 1);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  if ( v17 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e460  mov     [rsp-28h+arg_0], rbx
0x18000e465  push    rbp
0x18000e466  push    rsi
0x18000e467  push    rdi
0x18000e468  push    r14
0x18000e46a  push    r15
0x18000e46c  mov     rbp, rsp
0x18000e46f  sub     rsp, 40h
0x18000e473  mov     rax, [rdx]
0x18000e476  xor     r15d, r15d
0x18000e479  mov     rsi, rdx
0x18000e47c  mov     [rbp+arg_8], r15d
0x18000e480  mov     rdi, rcx
0x18000e483  mov     [rbp+var_8], r15
0x18000e487  lea     rdx, [rbp+arg_8]
0x18000e48b  mov     [rbp+var_18], r15
0x18000e48f  mov     rax, [rax+50h]
0x18000e493  mov     rcx, rsi
0x18000e496  mov     r14, r8
0x18000e499  mov     [rbp+var_20], r15
0x18000e49d  mov     [rbp+var_10], r15
0x18000e4a1  mov     [rbp+arg_18], r15d
0x18000e4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4aa  mov     ebx, eax
0x18000e4ac  test    eax, eax
0x18000e4ae  jns     short loc_18000E529
0x18000e4b0  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000e4b7  jnz     short loc_18000E520
0x18000e4b9  mov     rcx, [rbp+var_8]
0x18000e4bd  test    rcx, rcx
0x18000e4c0  jnz     loc_18000E80E
0x18000e4c6  mov     rcx, [rbp+var_20]
0x18000e4ca  test    rcx, rcx
0x18000e4cd  jz      short loc_18000E4DF
0x18000e4cf  mov     rax, [rcx]
0x18000e4d2  mov     rax, [rax+10h]
0x18000e4d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4db  mov     [rbp+var_20], r15
0x18000e4df  mov     rcx, [rbp+var_18]
0x18000e4e3  test    rcx, rcx
0x18000e4e6  jz      short loc_18000E4F8
0x18000e4e8  mov     rax, [rcx]
0x18000e4eb  mov     rax, [rax+10h]
0x18000e4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4f4  mov     [rbp+var_18], r15
0x18000e4f8  mov     rcx, [rbp+var_10]
0x18000e4fc  test    rcx, rcx
0x18000e4ff  jz      short loc_18000E50D
0x18000e501  mov     rdx, [rcx]
0x18000e504  mov     rax, [rdx+10h]
0x18000e508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e50d  mov     eax, ebx
0x18000e50f  mov     rbx, [rsp+40h+arg_0]
0x18000e514  add     rsp, 40h
0x18000e518  pop     r15
0x18000e51a  pop     r14
0x18000e51c  pop     rdi
0x18000e51d  pop     rsi
0x18000e51e  pop     rbp
0x18000e51f  retn
0x18000e520  mov     ecx, eax; int
0x18000e522  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000e527  jmp     short loc_18000E4B9
0x18000e529  jnz     loc_18000E7E9
0x18000e52f  cmp     [rbp+arg_8], 9
0x18000e533  jnz     loc_18000E7FE
0x18000e539  mov     rax, [rsi]
0x18000e53c  lea     rdx, [rbp+var_20]
0x18000e540  mov     rcx, rsi
0x18000e543  mov     rax, [rax+60h]
0x18000e547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e54c  mov     ebx, eax
0x18000e54e  test    eax, eax
0x18000e550  js      loc_18000E4B0
0x18000e556  jnz     loc_18000E7E9
0x18000e55c  mov     rcx, [rbp+var_20]
0x18000e560  lea     rdx, [rbp+arg_18]
0x18000e564  mov     rax, [rcx]
0x18000e567  mov     rax, [rax+40h]
0x18000e56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e570  mov     ebx, eax
0x18000e572  test    eax, eax
0x18000e574  js      loc_18000E4B0
0x18000e57a  jnz     loc_18000E7E9
0x18000e580  cmp     [rbp+arg_18], 1
0x18000e584  jnz     loc_18000E7F0
0x18000e58a  mov     rcx, [rbp+var_20]
0x18000e58e  lea     r8, [rbp+var_10]
0x18000e592  xor     edx, edx
0x18000e594  mov     rax, [rcx]
0x18000e597  mov     rax, [rax+38h]
0x18000e59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5a0  mov     ebx, eax
0x18000e5a2  test    eax, eax
0x18000e5a4  js      loc_18000E4B0
0x18000e5aa  jnz     loc_18000E7E9
0x18000e5b0  mov     rcx, [rbp+var_10]
0x18000e5b4  lea     rdx, [rbp+arg_8]
0x18000e5b8  mov     rax, [rcx]
0x18000e5bb  mov     rax, [rax+50h]
0x18000e5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5c4  mov     ebx, eax
0x18000e5c6  test    eax, eax
0x18000e5c8  js      loc_18000E4B0
0x18000e5ce  jnz     loc_18000E7E9
0x18000e5d4  cmp     [rbp+arg_8], 1
0x18000e5d8  jnz     loc_18000E7F0
0x18000e5de  mov     rax, [rdi]
0x18000e5e1  mov     rcx, rdi
0x18000e5e4  mov     rdx, [rbp+var_10]
0x18000e5e8  mov     rax, [rax+170h]
0x18000e5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f4  mov     ebx, eax
0x18000e5f6  test    eax, eax
0x18000e5f8  js      loc_18000E4B0
0x18000e5fe  mov     rcx, [rbp+var_20]
0x18000e602  test    rcx, rcx
0x18000e605  jz      short loc_18000E617
0x18000e607  mov     rax, [rcx]
0x18000e60a  mov     rax, [rax+10h]
0x18000e60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e613  mov     [rbp+var_20], r15
0x18000e617  mov     rcx, [rbp+var_10]
0x18000e61b  lea     rdx, [rbp+var_20]
0x18000e61f  mov     rax, [rcx]
0x18000e622  mov     rax, [rax+60h]
0x18000e626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e62b  mov     ebx, eax
0x18000e62d  test    eax, eax
0x18000e62f  js      loc_18000E4B0
0x18000e635  jnz     loc_18000E7E9
0x18000e63b  mov     rcx, [rbp+var_20]
0x18000e63f  lea     rdx, [rbp+arg_18]
0x18000e643  mov     rax, [rcx]
0x18000e646  mov     rax, [rax+40h]
0x18000e64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e64f  mov     ebx, eax
0x18000e651  test    eax, eax
0x18000e653  js      loc_18000E4B0
0x18000e659  jnz     loc_18000E7E9
0x18000e65f  mov     esi, r15d
0x18000e662  cmp     esi, [rbp+arg_18]
0x18000e665  jnb     loc_18000E7C9
0x18000e66b  mov     rcx, [rbp+var_20]
0x18000e66f  lea     r8, [rbp+var_18]
0x18000e673  mov     edx, esi
0x18000e675  mov     rax, [rcx]
0x18000e678  mov     rax, [rax+38h]
0x18000e67c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e681  mov     ebx, eax
0x18000e683  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000e689  test    ebx, ebx
0x18000e68b  jns     short loc_18000E69D
0x18000e68d  test    eax, eax
0x18000e68f  jnz     loc_18000E7E2
0x18000e695  test    ebx, ebx
0x18000e697  js      loc_18000E4B9
0x18000e69d  jnz     loc_18000E805
0x18000e6a3  mov     rcx, [rbp+var_18]
0x18000e6a7  lea     rdx, [rbp+arg_8]
0x18000e6ab  mov     rax, [rcx]
0x18000e6ae  mov     rax, [rax+50h]
0x18000e6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6b7  mov     ebx, eax
0x18000e6b9  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000e6bf  test    ebx, ebx
0x18000e6c1  jns     short loc_18000E6D3
0x18000e6c3  test    eax, eax
0x18000e6c5  jnz     loc_18000E7E2
0x18000e6cb  test    ebx, ebx
0x18000e6cd  js      loc_18000E4B9
0x18000e6d3  jnz     loc_18000E805
0x18000e6d9  cmp     [rbp+arg_8], 1
0x18000e6dd  jnz     loc_18000E7A9
0x18000e6e3  mov     rax, [rdi]
0x18000e6e6  lea     rdx, [rbp+var_8]
0x18000e6ea  mov     rcx, rdi
0x18000e6ed  mov     rax, [rax+180h]
0x18000e6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6f9  mov     ebx, eax
0x18000e6fb  test    eax, eax
0x18000e6fd  jns     short loc_18000E714
0x18000e6ff  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000e706  jnz     loc_18000E520
0x18000e70c  test    eax, eax
0x18000e70e  js      loc_18000E4B9
0x18000e714  mov     rcx, [rbp+var_8]
0x18000e718  mov     rdx, [rbp+var_18]
0x18000e71c  mov     rax, [rcx]
0x18000e71f  mov     rax, [rax+8]
0x18000e723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e728  mov     ebx, eax
0x18000e72a  test    eax, eax
0x18000e72c  jns     short loc_18000E743
0x18000e72e  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000e735  jnz     loc_18000E520
0x18000e73b  test    eax, eax
0x18000e73d  js      loc_18000E4B9
0x18000e743  mov     rax, [rdi]
0x18000e746  mov     rcx, rdi
0x18000e749  mov     rdx, [rbp+var_8]
0x18000e74d  mov     rax, [rax+150h]
0x18000e754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e759  mov     ebx, eax
0x18000e75b  test    eax, eax
0x18000e75d  jns     short loc_18000E774
0x18000e75f  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000e766  jnz     loc_18000E520
0x18000e76c  test    eax, eax
0x18000e76e  js      loc_18000E4B9
0x18000e774  lea     rcx, [rdi+0D0h]
0x18000e77b  lea     rdx, [rbp+var_8]
0x18000e77f  call    ?Add@?$CMILObjectArray@PEAVRDFItem@@@@QEAAJAEAPEAVRDFItem@@@Z; CMILObjectArray<RDFItem *>::Add(RDFItem * &)
0x18000e784  mov     ebx, eax
0x18000e786  test    eax, eax
0x18000e788  jns     short loc_18000E79F
0x18000e78a  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000e791  jnz     loc_18000E520
0x18000e797  test    eax, eax
0x18000e799  js      loc_18000E4B9
0x18000e79f  inc     dword ptr [rdi+0ACh]
0x18000e7a5  mov     [rbp+var_8], r15
0x18000e7a9  mov     rcx, [rbp+var_18]
0x18000e7ad  test    rcx, rcx
0x18000e7b0  jz      short loc_18000E7C2
0x18000e7b2  mov     rax, [rcx]
0x18000e7b5  mov     rax, [rax+10h]
0x18000e7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7be  mov     [rbp+var_18], r15
0x18000e7c2  inc     esi
0x18000e7c4  jmp     loc_18000E662
0x18000e7c9  mov     rax, [rbp+var_10]
0x18000e7cd  mov     ebx, r15d
0x18000e7d0  mov     [r14], rax
0x18000e7d3  mov     [rbp+var_10], r15
0x18000e7d7  jmp     loc_18000E4B9
0x18000e7dc  jz      loc_18000E4B9
0x18000e7e2  mov     ecx, ebx
0x18000e7e4  jmp     loc_18000E522
0x18000e7e9  mov     ebx, 80004005h
0x18000e7ee  jmp     short loc_18000E7F5
0x18000e7f0  mov     ebx, 88982F8Fh
0x18000e7f5  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000e7fc  jmp     short loc_18000E7DC
0x18000e7fe  mov     ebx, 88982F91h
0x18000e803  jmp     short loc_18000E7F5
0x18000e805  mov     ebx, 80004005h
0x18000e80a  test    eax, eax
0x18000e80c  jmp     short loc_18000E7DC
0x18000e80e  mov     rax, [rcx]
0x18000e811  mov     edx, 1
0x18000e816  mov     rax, [rax]
0x18000e819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e81e  jmp     loc_18000E4C6
```
