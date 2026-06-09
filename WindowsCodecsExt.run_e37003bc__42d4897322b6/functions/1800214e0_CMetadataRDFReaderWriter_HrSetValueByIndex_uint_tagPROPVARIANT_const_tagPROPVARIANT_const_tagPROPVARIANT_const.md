# CMetadataRDFReaderWriter::HrSetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x1800214e0`
- end: `0x18002156f`
- name: `?HrSetValueByIndex@CMetadataRDFReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `143`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800213c0`
- `0x180021430`
- `0x180024bd0`

## callees

- `0x180001010`
- `0x180002aa0`
- `0x1800171c4`
- `0x1800214e0`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrSetValueByIndex(
        CMetadataRDFReaderWriter *this,
        int a2,
        const struct tagPROPVARIANT *a3,
        const struct tagPROPVARIANT *a4,
        struct tagPROPVARIANT *a5)
{
  int ItemPosition; // eax
  unsigned int v9; // ebx
  unsigned int v11; // [rsp+40h] [rbp-38h] BYREF
  int v12[13]; // [rsp+44h] [rbp-34h] BYREF

  v11 = 0;
  v12[0] = 0;
  ItemPosition = CMetadataRDFReaderWriter::FindItemPosition(this, 0, a2, 0, 0, v12, &v11);
  v9 = ItemPosition;
  if ( ItemPosition < 0
    || (ItemPosition = CMetadataRDFReaderWriter::SetItemByPosition(this, v11, a3, a4, a5),
        v9 = ItemPosition,
        ItemPosition < 0) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(ItemPosition);
  }
  return v9;
}

```

## disassembly

```asm
0x1800214e0  mov     r11, rsp
0x1800214e3  push    rbx
0x1800214e4  push    rbp
0x1800214e5  push    rsi
0x1800214e6  push    rdi
0x1800214e7  sub     rsp, 58h
0x1800214eb  lea     rax, [r11-38h]
0x1800214ef  mov     [rsp+78h+var_38], 0
0x1800214f7  mov     [r11-48h], rax
0x1800214fb  mov     rbp, r8
0x1800214fe  lea     rax, [r11-34h]
0x180021502  mov     [rsp+78h+var_34], 0
0x18002150a  mov     rsi, r9
0x18002150d  mov     [r11-50h], rax
0x180021511  mov     r8d, edx; unsigned int
0x180021514  mov     qword ptr [r11-58h], 0
0x18002151c  xor     r9d, r9d; struct tagPROPVARIANT *
0x18002151f  xor     edx, edx; int (*)(struct RDFItem *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, int *)
0x180021521  mov     rdi, rcx
0x180021524  call    ?FindItemPosition@CMetadataRDFReaderWriter@@IEAAJP6AJPEAVRDFItem@@PEBUtagPROPVARIANT@@1PEAH@ZI112PEAI@Z; CMetadataRDFReaderWriter::FindItemPosition(long (*)(RDFItem *,tagPROPVARIANT const *,tagPROPVARIANT const *,int *),uint,tagPROPVARIANT const *,tagPROPVARIANT const *,int *,uint *)
0x180021529  mov     ebx, eax
0x18002152b  test    eax, eax
0x18002152d  js      short loc_180021554
0x18002152f  mov     rax, [rsp+78h+arg_20]
0x180021537  mov     r9, rsi; struct tagPROPVARIANT *
0x18002153a  mov     edx, [rsp+78h+var_38]; unsigned int
0x18002153e  mov     r8, rbp; struct tagPROPVARIANT *
0x180021541  mov     rcx, rdi; this
0x180021544  mov     [rsp+78h+var_58], rax; struct tagPROPVARIANT *
0x180021549  call    ?SetItemByPosition@CMetadataRDFReaderWriter@@IEAAJIPEBUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::SetItemByPosition(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)
0x18002154e  mov     ebx, eax
0x180021550  test    eax, eax
0x180021552  jns     short loc_180021564
0x180021554  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002155b  jz      short loc_180021564
0x18002155d  mov     ecx, eax; int
0x18002155f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180021564  mov     eax, ebx
0x180021566  add     rsp, 58h
0x18002156a  pop     rdi
0x18002156b  pop     rsi
0x18002156c  pop     rbp
0x18002156d  pop     rbx
0x18002156e  retn
```
