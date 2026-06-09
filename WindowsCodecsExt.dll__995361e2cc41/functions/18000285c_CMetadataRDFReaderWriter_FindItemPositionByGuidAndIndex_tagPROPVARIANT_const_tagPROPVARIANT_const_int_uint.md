# CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)

- ea: `0x18000285c`
- end: `0x180002917`
- name: `?FindItemPositionByGuidAndIndex@CMetadataRDFReaderWriter@@IEAAJPEBUtagPROPVARIANT@@0PEAHPEAI@Z`
- size: `187`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *, unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001630`
- `0x1800017a0`
- `0x180001b50`
- `0x18001e950`

## callees

- `0x180001010`
- `0x1800027e0`
- `0x18000285c`
- `0x1800171c4`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::FindItemPositionByGuidAndIndex(
        CMetadataRDFReaderWriter *this,
        const struct tagPROPVARIANT *a2,
        const struct tagPROPVARIANT *a3,
        int *a4,
        unsigned int *a5)
{
  bool v6; // zf
  unsigned __int16 v7; // ax
  int ItemPosition; // eax
  unsigned int v12; // ebx
  int v13; // ecx
  unsigned __int16 v15; // [rsp+90h] [rbp+18h] BYREF

  v6 = a3->vt == 72;
  v7 = 0;
  v15 = 0;
  if ( v6 && a3->hVal.QuadPart )
  {
    if ( a2 && a2->vt )
    {
      ItemPosition = CMetadataHandler::CoerceVariantToUShort(this, a2, &v15);
      v12 = ItemPosition;
      if ( ItemPosition < 0 )
      {
LABEL_6:
        if ( g_doStackCaptures )
        {
          v13 = ItemPosition;
LABEL_13:
          DoStackCapture(v13);
          return v12;
        }
        return v12;
      }
      v7 = v15;
    }
    ItemPosition = CMetadataRDFReaderWriter::FindItemPosition(
                     this,
                     (__int64 (__fastcall *)(__int64, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, unsigned int **))CMetadataRDFReaderWriter::CompareItemEmbeddedGUID,
                     v7,
                     a2,
                     a3,
                     a4,
                     a5);
    v12 = ItemPosition;
    if ( ItemPosition >= 0 )
      return v12;
    goto LABEL_6;
  }
  v12 = -2147024809;
  if ( g_doStackCaptures )
  {
    v13 = -2147024809;
    goto LABEL_13;
  }
  return v12;
}

```

## disassembly

```asm
0x18000285c  mov     r11, rsp
0x18000285f  push    rbx
0x180002860  push    rbp
0x180002861  push    rsi
0x180002862  push    rdi
0x180002863  push    r14
0x180002865  push    r15
0x180002867  sub     rsp, 48h
0x18000286b  xor     r15d, r15d
0x18000286e  mov     rbp, r9
0x180002871  cmp     word ptr [r8], 48h ; 'H'
0x180002876  mov     eax, r15d
0x180002879  mov     [r11+18h], ax
0x18000287e  mov     rsi, r8
0x180002881  mov     rdi, rdx
0x180002884  mov     r14, rcx
0x180002887  jnz     short loc_1800028F3
0x180002889  cmp     [r8+8], r15
0x18000288d  jz      short loc_1800028F3
0x18000288f  test    rdx, rdx
0x180002892  jz      short loc_1800028BE
0x180002894  cmp     [rdx], r15w
0x180002898  jz      short loc_1800028BE
0x18000289a  lea     r8, [r11+18h]; unsigned __int16 *
0x18000289e  call    ?CoerceVariantToUShort@CMetadataHandler@@IEAAJPEBUtagPROPVARIANT@@PEAG@Z; CMetadataHandler::CoerceVariantToUShort(tagPROPVARIANT const *,ushort *)
0x1800028a3  mov     ebx, eax
0x1800028a5  test    eax, eax
0x1800028a7  jns     short loc_1800028B6
0x1800028a9  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800028b0  jz      short loc_180002908
0x1800028b2  mov     ecx, eax
0x1800028b4  jmp     short loc_180002903
0x1800028b6  movzx   eax, [rsp+78h+arg_10]
0x1800028be  movzx   r8d, ax; unsigned int
0x1800028c2  lea     rdx, ?CompareItemEmbeddedGUID@CMetadataRDFReaderWriter@@KAJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@Z; int (*)(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *)
0x1800028c9  mov     rax, [rsp+78h+arg_20]
0x1800028d1  mov     r9, rdi; struct tagPROPVARIANT *
0x1800028d4  mov     [rsp+78h+var_48], rax; unsigned int *
0x1800028d9  mov     rcx, r14; this
0x1800028dc  mov     [rsp+78h+var_50], rbp; int *
0x1800028e1  mov     [rsp+78h+var_58], rsi; struct tagPROPVARIANT *
0x1800028e6  call    ?FindItemPosition@CMetadataRDFReaderWriter@@IEAAJP6AJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@ZI112PEAI@Z; CMetadataRDFReaderWriter::FindItemPosition(long (*)(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *),uint,tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x1800028eb  mov     ebx, eax
0x1800028ed  test    eax, eax
0x1800028ef  jns     short loc_180002908
0x1800028f1  jmp     short loc_1800028A9
0x1800028f3  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800028fa  mov     ebx, 80070057h
0x1800028ff  jz      short loc_180002908
0x180002901  mov     ecx, ebx; int
0x180002903  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180002908  mov     eax, ebx
0x18000290a  add     rsp, 48h
0x18000290e  pop     r15
0x180002910  pop     r14
0x180002912  pop     rdi
0x180002913  pop     rsi
0x180002914  pop     rbp
0x180002915  pop     rbx
0x180002916  retn
```
