# _generateRATApplicabilityNode(IXMLDOMDocument2 *,IXMLDOMNode *,ulong,ulong)

- ea: `0x18000a0f0`
- end: `0x18000a290`
- name: `?_generateRATApplicabilityNode@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@KK@Z`
- size: `416`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a298`

## callees

- `0x18000a0f0`
- `0x180011f90`
- `0x180014010`

## string_xrefs

- `0x18000a11f`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a190`: `http://www.microsoft.com/networking/WWAN/profile/v9`
- `0x18000a1c7`: `http://www.microsoft.com/networking/WWAN/profile/v9`

## pseudocode

```c
__int64 __fastcall _generateRATApplicabilityNode(struct IXMLDOMDocument2 *a1, struct IXMLDOMNode *a2, int a3)
{
  unsigned int v5; // ebx
  unsigned int v7; // edi
  struct IXMLDOMNode *v8; // rbx
  unsigned int v9; // ebp
  unsigned int v10; // esi
  struct IXMLDOMNode *v11; // [rsp+30h] [rbp-48h] BYREF
  struct IXMLDOMNode *v12; // [rsp+38h] [rbp-40h] BYREF

  v12 = 0;
  v5 = XcAddChildElement(
         a1,
         a2,
         (OLECHAR *)L"RATApplicabilityCheck",
         (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9",
         0,
         &v12);
  if ( v5 )
  {
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
    return v5;
  }
  v7 = 0;
  v8 = v12;
  while ( 1 )
  {
    if ( (a3 & *(_DWORD *)(&_RATType + 2 * v7 + 1)) == 0 )
      goto LABEL_11;
    v11 = 0;
    v9 = XcAddChildElement(
           a1,
           v8,
           (OLECHAR *)L"RATType",
           (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9",
           0,
           &v11);
    if ( v9 )
      break;
    v10 = XcAddChildElement(
            a1,
            v11,
            (OLECHAR *)L"BaseRAT",
            (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v9",
            *((OLECHAR **)&_RATType + 2 * v7),
            &v11);
    if ( v10 )
    {
      if ( v11 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
      if ( v8 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
      return v10;
    }
    if ( v11 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
LABEL_11:
    if ( ++v7 >= 4 )
    {
      if ( v8 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
      return 0;
    }
  }
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  return v9;
}

```

## disassembly

```asm
0x18000a0f0  mov     r11, rsp
0x18000a0f3  push    rbx
0x18000a0f4  push    rbp
0x18000a0f5  push    rsi
0x18000a0f6  push    rdi
0x18000a0f7  push    r13
0x18000a0f9  push    r14
0x18000a0fb  push    r15
0x18000a0fd  sub     rsp, 40h
0x18000a101  mov     r15d, r8d
0x18000a104  mov     r14, rcx
0x18000a107  mov     qword ptr [r11-40h], 0
0x18000a10f  lea     rax, [r11-40h]
0x18000a113  mov     [r11-50h], rax
0x18000a117  mov     qword ptr [r11-58h], 0
0x18000a11f  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a126  lea     r8, aRatapplicabili; "RATApplicabilityCheck"
0x18000a12d  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a132  mov     ebx, eax
0x18000a134  test    eax, eax
0x18000a136  jz      short loc_18000A156
0x18000a138  mov     rcx, [rsp+78h+var_40]
0x18000a13d  test    rcx, rcx
0x18000a140  jz      short loc_18000A14F
0x18000a142  mov     rdx, [rcx]
0x18000a145  mov     rax, [rdx+10h]
0x18000a149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a14e  nop
0x18000a14f  mov     eax, ebx
0x18000a151  jmp     loc_18000A221
0x18000a156  xor     edi, edi
0x18000a158  lea     r13, ?_RATType@@3QBU_XC_STRING_VALUE_MAPPING@@B; _XC_STRING_VALUE_MAPPING const near * const _RATType
0x18000a15f  mov     rbx, [rsp+78h+var_40]
0x18000a164  mov     esi, edi
0x18000a166  add     rsi, rsi
0x18000a169  test    [r13+rsi*8+8], r15d
0x18000a16e  jz      loc_18000A1FF
0x18000a174  mov     [rsp+78h+var_48], 0
0x18000a17d  lea     rax, [rsp+78h+var_48]
0x18000a182  mov     [rsp+78h+var_50], rax; struct IXMLDOMNode **
0x18000a187  mov     [rsp+78h+var_58], 0; OLECHAR *
0x18000a190  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a197  lea     r8, aRattype; "RATType"
0x18000a19e  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a1a1  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a1a4  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a1a9  mov     ebp, eax
0x18000a1ab  test    eax, eax
0x18000a1ad  jnz     loc_18000A260
0x18000a1b3  lea     rax, [rsp+78h+var_48]
0x18000a1b8  mov     [rsp+78h+var_50], rax; struct IXMLDOMNode **
0x18000a1bd  mov     rax, [r13+rsi*8+0]
0x18000a1c2  mov     [rsp+78h+var_58], rax; OLECHAR *
0x18000a1c7  lea     r9, aHttpWwwMicroso_6; "http://www.microsoft.com/networking/WWA"...
0x18000a1ce  lea     r8, aBaserat; "BaseRAT"
0x18000a1d5  mov     rdx, [rsp+78h+var_48]; struct IXMLDOMNode *
0x18000a1da  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a1dd  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a1e2  mov     esi, eax
0x18000a1e4  test    eax, eax
0x18000a1e6  jnz     short loc_18000A230
0x18000a1e8  mov     rcx, [rsp+78h+var_48]
0x18000a1ed  test    rcx, rcx
0x18000a1f0  jz      short loc_18000A1FF
0x18000a1f2  mov     rax, [rcx]
0x18000a1f5  mov     rax, [rax+10h]
0x18000a1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fe  nop
0x18000a1ff  inc     edi
0x18000a201  cmp     edi, 4
0x18000a204  jb      loc_18000A164
0x18000a20a  test    rbx, rbx
0x18000a20d  jz      short loc_18000A21F
0x18000a20f  mov     rax, [rbx]
0x18000a212  mov     rcx, rbx
0x18000a215  mov     rax, [rax+10h]
0x18000a219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a21e  nop
0x18000a21f  xor     eax, eax
0x18000a221  add     rsp, 40h
0x18000a225  pop     r15
0x18000a227  pop     r14
0x18000a229  pop     r13
0x18000a22b  pop     rdi
0x18000a22c  pop     rsi
0x18000a22d  pop     rbp
0x18000a22e  pop     rbx
0x18000a22f  retn
0x18000a230  mov     rcx, [rsp+78h+var_48]
0x18000a235  test    rcx, rcx
0x18000a238  jz      short loc_18000A247
0x18000a23a  mov     rax, [rcx]
0x18000a23d  mov     rax, [rax+10h]
0x18000a241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a246  nop
0x18000a247  test    rbx, rbx
0x18000a24a  jz      short loc_18000A25C
0x18000a24c  mov     rax, [rbx]
0x18000a24f  mov     rcx, rbx
0x18000a252  mov     rax, [rax+10h]
0x18000a256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25b  nop
0x18000a25c  mov     eax, esi
0x18000a25e  jmp     short loc_18000A221
0x18000a260  mov     rcx, [rsp+78h+var_48]
0x18000a265  test    rcx, rcx
0x18000a268  jz      short loc_18000A277
0x18000a26a  mov     rax, [rcx]
0x18000a26d  mov     rax, [rax+10h]
0x18000a271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a276  nop
0x18000a277  test    rbx, rbx
0x18000a27a  jz      short loc_18000A28C
0x18000a27c  mov     rax, [rbx]
0x18000a27f  mov     rcx, rbx
0x18000a282  mov     rax, [rax+10h]
0x18000a286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a28b  nop
0x18000a28c  mov     eax, ebp
0x18000a28e  jmp     short loc_18000A221
```
